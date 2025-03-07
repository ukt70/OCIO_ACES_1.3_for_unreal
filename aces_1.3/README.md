ACES 1.3 OpenColorIO configuration
=

Information about ACES
-

The **ACES** project home page is here: 

- http://www.oscars.org/aces

The latest documentation on the ACES transforms and specifications can be found here:

- http://www.oscars.org/science-technology/aces/aces-documentation


Colorspaces
-

Colorspaces in this configurations are grouped into the following families: *ACES*, *ADX*, *Look*, *Output*, *Input*, *Utility*, *Aliases*. Descriptions for the colorspaces in the different families are provided below.

For ease of use across a broader number of applications, the family name of each colorspace is prepended to the colorspace name when the configuration is authored. Those prefixes are omitted in this document, but will show up when the configuration is loaded and used.


### ACES

##### Colorspaces

- ACES2065-1
- ACEScc
- ACEScct
- ACESproxy
- ACEScg


##### Description

Colorspaces and transforms representing the core ACES working and interchange colorspaces.


##### Technical information

The generated transforms are based on the [ACES CTL Transforms](https://github.com/ampas/aces-dev/tree/v1.3/transforms/ctl)


### Output

##### Colorspaces

- DCDM
- DCDM (P3D60 Limited)
- DCDM (P3D65 Limited)
- P3-D60
- P3-D65 ST2084 (1000 nits)
- P3-D65 ST2084 (2000 nits)
- P3-D65 ST2084 (4000 nits)
- P3-DCI (D60 simulation)
- P3-DCI (D65 simulation)
- P3D65
- P3D65 (D60 simulation)
- P3D65 (Rec.709 Limited)
- P3D65 ST2084 (108 nits)
- Rec.2020
- Rec.2020 (P3D65 Limited)
- Rec.2020 (Rec.709 Limited)
- Rec.2020 HLG (1000 nits)
- Rec.2020 ST2084 (1000 nits)
- Rec.2020 ST2084 (2000 nits)
- Rec.2020 ST2084 (4000 nits)
- Rec.709
- Rec.709 (D60 sim.)
- sRGB
- sRGB (D60 sim.)


##### Description

Colorspaces and transforms implementing the ACES Output Transforms. These colorspaces produce code values ready for display on display devices calibrated to the standard used to name the colorspace.


##### Technical information

- Transforms generated based on the [ACES CTL Transforms](https://github.com/ampas/aces-dev/tree/v1.3/transforms/ctl)
- All transforms produce full-range output. Host applications should be used to apply an full-to-legal scaling if required.


### Input

##### Colorspaces

There are a variety of Input Transforms covering different cameras manufacturers, gamuts, transfer functions and camera settings. See below for specifics.


##### Description

Colorspaces and transforms that implement the ACES Input Transforms. These colorspaces are used to convert from camera-specific formats and encodings to ACES.


##### Technical information

References and descriptions are provided for each group of Input Transforms below:

- The colorspaces whose names include a transfer function and a gamut name are full implementations of ACES Input Transforms.
    - Ex. The ARRI `V3 LogC (EI160) - Wide Gamut` colorspace
    - Ex. The RED `REDlogFilm - DRAGONcolor2` colorspace
    - Ex. The Canon `Canon-Log - DCI-P3 Daylight` colorspace
- The colorspaces starting with `Linear - ` convert to or from a specific gamut but do not apply a transfer function.
- The colorspaces starting with `Curve - ` apply a transfer function but do not convert between gamuts.


#### ADX

##### Colorspaces

- ADX10
- ADX16


##### Description

Colorspaces and transforms representing the ACES ADX spaces used for film scanning and printing.


##### Technical information

- Transforms generated based on the [ACES CTL Transforms](https://github.com/ampas/aces-dev/tree/v1.3/transforms/ctl)
- [Alex Fry's ACES 0.7.1 OCIO config](https://github.com/imageworks/OpenColorIO-Configs/tree/master/aces_0.7.1) was also a valuable resource


#### ARRI

- [ARRI 'Working with ACES'](http://www.arri.com/camera/alexa_mini/learn/working_with_aces/)
- [ARRI Input Transforms](https://github.com/ampas/aces-dev/tree/v1.3/transforms/ctl/idt/vendorSupplied/arri/alexa)
- Conversations with Joseph Goldstone of ARRI


#### Canon

- [Canon ACES landing page](http://usa.canon.com/cusa/professional/standard_display/aces)
- [Clog white paper](http://learn.usa.canon.com/app/pdfs/white_papers/White_Paper_Clog_optoelectronic.pdf)
- [C700 Drivers and Software](https://www.usa.canon.com/internet/portal/us/home/support/details/cameras/cinema-eos/eos-c300-mark-ii?tab=drivers#Z7_MQH8HIC0L88RB0AMD0F1Q42K25)
- [C500 Drivers and Software](http://www.usa.canon.com/cusa/professional/products/professional_cameras/cinema_eos_cameras/eos_c500#DriversAndSoftware)
- [C300 Drivers and Software](http://www.usa.canon.com/cusa/professional/products/professional_cameras/cinema_eos_cameras/eos_c300#DriversAndSoftware)
    - Choose *OSX Mountain Lion v10.8* to download the IDTs
- [C300 Mark II Drivers and Software](https://www.usa.canon.com/internet/portal/us/home/support/details/cameras/cinema-eos/eos-c300-mark-ii)
    - Choose *OSX Mountain Lion v10.8* to download the IDTs, labeled "EOS C300 Mark II Input Transform Version 2.0 (for Cinema Gamut / BT.2020)"
- [C100 Drivers and Software](http://www.usa.canon.com/cusa/professional/products/professional_cameras/cinema_eos_cameras/eos_c100#DriversAndSoftware)
    - Choose *OSX Mountain Lion v10.8* to download the IDTs


#### Panasonic

- [Vlog/V-Gamut white paper](http://pro-av.panasonic.net/en/varicam/common/pdf/VARICAM_V-Log_V-Gamut.pdf)
- [Varicam Drivers and Software](http://pro-av.panasonic.net/en/varicam/35/dl.html)


#### RED

- [Understanding REDlogFilm and REDgamma](http://www.red.com/learn/red-101/redlogfilm-redgamma)
- Conversations with Graeme Nattress of RED


#### Sony

- [Sony Input Transforms](https://github.com/ampas/aces-dev/tree/v1.3/transforms/ctl/idt/vendorSupplied/sony)


#### GoPro (Experimental)

- The quality and consistency of these transforms has not been verified
- Conversations with David Newman of GoPro


### Utility

##### Description

A collection of colorspaces that are used to facilitate the creation of LUTs and other basic functionality.


##### Technical information

- The `Log2 xx nits Shaper` and `Dolby PQ xx nits Shaper` spaces cover the linear range centered around 18% grey. The 48 nits spaces cover -7.2460688 stops (0.0011857) to +10.2739312 stops (222.8609442), effectively matching ACEScc. The 1000 nits spaces cover -12 stops to +10 stops. The 2000 nits spaces cover -12 stops to +11 stops. The 4000 nits spaces cover -12 stops to +12 stops.
- The LMT shaper spaces cover the linear range going from 10 stops below 18% grey (0.0001758) to 6.5 stops above 18% grey (16.2917402)
- The colorspaces starting with `Linear - ` convert to or from a specific gamut but do not apply a transfer function.
- The colorspaces starting with `Curve - ` apply a transfer function but do not convert between gamuts.


#### Look

##### Colorspaces

- ACES 1.0 to 0.1 emulation
- ACES 1.0 to 0.2 emulation
- ACES 1.0 to 0.7 emulation
- Blue Light Artifact Fix
- Gamut Compress


##### Description

Colorspaces and transforms emulating the look of the ACES 0.1, 0.2 and 0.7 release. 

The Blue Light Artifact Fix was intended to address [issues occurring with highly saturated emitters](https://acescentral.com/t/colour-artefacts-or-breakup-using-aces/520/63) such as LED lights. 

- Should be applied to data in the ACES2065-1 colorspace.
- Should be used before an ACES Output Transform.

As of ACES 1.3, the Blue Light Artifact Fix is no longer recommended. The gamut compression transform is the new way to address the problem. For more details, see ACES 1.3 release note.


##### Technical information

Transforms generated based on the [ACES CTL Transforms](https://github.com/ampas/aces-dev/tree/v1.3/transforms/ctl)


#### Roles

##### Description

The role colorspaces are aliases to the colorspaces used for the *OCIO* *roles* functionality.


#### Aliases

##### Description

The alias colorspaces are named with all lower-case letters and no spaces, dashes, parentheses or other characters that would not work well in a filename. They are only references, aliases for the base colorspaces with more user-friendly names. These spaces were added to enable OCIO's token-based colorspace / filename matching.

- These colorspaces should not generally be used by most artists.


Roles
-

The standard *OCIO* roles are defined. They role assignments are:

- `color_picking`: Output - sRGB
- `color_timing`: ACEScc
- `compositing_log`: ADX10
- `data`: Raw
- `default`: ACES2065-1
- `matte_paint`: ACEScc
- `reference`: Raw
- `scene_linear`: ACEScg
- `texture_paint`: Raw

Additionally, a number of colorspaces that are gaining wider adoption have been added to the config. Their names and assignment are:

- **compositing_linear**: ACEScg
- **rendering**: ACEScg


Displays and Views
-

The default config has one Display named **ACES**, which contains the following Views / colorspaces:

- DCDM P3D60 Limited, colorspace: Output - DCDM (P3D60 Limited)
- DCDM P3D65 Limited, colorspace: Output - DCDM (P3D65 Limited)
- DCDM, colorspace: Output - DCDM
- P3-D60, colorspace: Output - P3-D60
- P3-D65 ST2084 1000 nits, colorspace: Output - P3-D65 ST2084 (1000 nits)
- P3-D65 ST2084 2000 nits, colorspace: Output - P3-D65 ST2084 (2000 nits)
- P3-D65 ST2084 4000 nits, colorspace: Output - P3-D65 ST2084 (4000 nits)
- P3-DCI D60 simulation, colorspace: Output - P3-DCI (D60 simulation)
- P3-DCI D65 simulation, colorspace: Output - P3-DCI (D65 simulation)
- P3D65 D60 simulation, colorspace: Output - P3D65 (D60 simulation)
- P3D65 Rec.709 Limited, colorspace: Output - P3D65 (Rec.709 Limited)
- P3D65 ST2084 108 nits, colorspace: Output - P3D65 ST2084 (108 nits)
- P3D65, colorspace: Output - P3D65
- Rec.2020 HLG 1000 nits, colorspace: Output - Rec.2020 HLG (1000 nits)
- Rec.2020 P3D65 Limited, colorspace: Output - Rec.2020 (P3D65 Limited)
- Rec.2020 Rec.709 Limited, colorspace: Output - Rec.2020 (Rec.709 Limited)
- Rec.2020 ST2084 1000 nits, colorspace: Output - Rec.2020 ST2084 (1000 nits)
- Rec.2020 ST2084 2000 nits, colorspace: Output - Rec.2020 ST2084 (2000 nits)
- Rec.2020 ST2084 4000 nits, colorspace: Output - Rec.2020 ST2084 (4000 nits)
- Rec.2020, colorspace: Output - Rec.2020
- Rec.709 D60 sim., colorspace: Output - Rec.709 (D60 sim.)
- Rec.709, colorspace: Output - Rec.709
- sRGB D60 sim., colorspace: Output - sRGB (D60 sim.)
- sRGB, colorspace: Output - sRGB
- Raw, colorspace: Utility - Raw
- Log, colorspace: Input - ADX - ADX10

Considerations for custom config generation:

- The choice of a single Display and many Views may not align well with the implementation of OCIO in an application. 
    - If you would like to generate a config that contains multiple Displays, with a small number of Views for each, review the config generation script's `--createMultipleDisplays` option.
- If a Look is added to the config, a new set of Views will be added, one for each of the Views listed above except Raw and Log, that includes the Look. The Views with Looks will be interleaved in the View list with the original Views.
    - To add a custom Look to the config, review the config generation script's `--addACESLookLUT`, `--addACESLookCDL`, `--addCustomLookLUT` and `--addCustomLookCDL` options.


LUTs
-

The default resolution is 65x65x65 for the 3D LUTs and 4096 for the 1D LUTs. 


### OCIO LUTs

The LUTs used internally by OCIO can be can be retrieved [from the repository here.](https://github.com/Ginurx/OpenColorIO-Configs/tree/master/aces_1.3/luts) 


### Baked LUTs

LUTs that can be used outside of OCIO are included in the ['baked' directory here.](https://github.com/imageworks/OpenColorIO-Configs/tree/master/aces_1.3/baked)

- The LUTs encode the ACES Output Transform for a specific colorspace input and are generally named *{OUTPUT_TRANSFORM_NAME} for {INPUT_COLORSPACE_NAME}.extension* e.g. `sRGB (D60 sim.) for ACEScc.icc`

The LUTs included in the `baked` directory cover the following formats and applications:

- .3dl for Autodesk Flame
- .3dl for Autodesk Lustre
- .lut for SideFX Houdini
- .csp for Autodesk Maya
- .icc for Adobe Photoshop


Generating Configurations
-

### Python

Configurations can be generated by the following *Python* package: [aces_1.3/python](https://github.com/Ginurx/OpenColorIO-Configs/tree/master/aces_1.3/python)

Usage is described on the command line and in the package root [\_\_init__.py](https://github.com/Ginurx/OpenColorIO-Configs/blob/master/aces_1.3/python/aces_ocio/__init__.py) file.

Features exposed for customization by the user include: 

- The resolution of 1D and 3D LUTs
- Inclusion of custom Looks
- Two modes of creating the list of OCIO Displays and Views
- Selection of shaper function: *Log2* or Dolby *PQ*


### CTL Source

The configuration depends on the **ACES 1.3** release.

The CTL is available here:

- https://github.com/ampas/aces-dev/tree/v1.3/transforms/ctl

Clone this repo using the following command:

- git clone --branch v1.3 https://github.com/ampas/aces-dev.git

Dependencies
-

The *Python* configuration generation package depends on the following
libraries:

- **OpenImageIO**: http://openimageio.org
    - Detailed build instructions can be found here: [OpenImageIO Build Instructions](https://sites.google.com/site/openimageio/checking-out-and-building-openimageio)
- **OpenColorIO**: http://opencolorio.org
    - Detailed build instructions can be found here: [OpenColorIO Build Instructions](http://opencolorio.org/installation.html)
- **CTL**: https://github.com/ampas/CTL
- **Numpy**: https://numpy.org/


Acknowledgements
-

The script used to generate these transforms and the transforms themselves were the product of work and conversations with a number of people. Thanks go to:

- Steve Agland
- Joe Bogacz
- Jack Binks
- Scott Dyer
- Alex Fry
- Alex Forsythe
- Joseph Goldstone
- Stephen Hill
- Jim Houston
- Thomas Mansencal
- Robert Molholm
- Nikola Milosevic
- Will McCown
- Graeme Nattress
- David Newman
- Sam Richards
- Erik Strauss
- Doug Walker
- Kevin Wheatley


Authorship and Maintenance
--------------------------

The original author of this OCIO config is:

- Haarm-Pieter Duiker

The current maintainers are:

- Thomas Mansencal
- Michael Parsons

## License Terms for Academy Color Encoding System Components ##

Academy Color Encoding System (ACES) software and tools are provided by the
Academy under the following terms and conditions: A worldwide, royalty-free,
non-exclusive right to copy, modify, create derivatives, and use, in source and
binary forms, is hereby granted, subject to acceptance of this license.

Copyright 2014-2021 Academy of Motion Picture Arts and Sciences (A.M.P.A.S.).
Portions contributed by others as indicated. All rights reserved.

Performance of any of the aforementioned acts indicates acceptance to be bound
by the following terms and conditions:

* Copies of source code, in whole or in part, must retain the above copyright
notice, this list of conditions and the Disclaimer of Warranty.

* Use in binary form must retain the above copyright notice, this list of
conditions and the Disclaimer of Warranty in the documentation and/or other
materials provided with the distribution.

* Nothing in this license shall be deemed to grant any rights to trademarks,
copyrights, patents, trade secrets or any other intellectual property of
A.M.P.A.S. or any contributors, except as expressly stated herein.

* Neither the name "A.M.P.A.S." nor the name of any other contributors to this
software may be used to endorse or promote products derivative of or based on
this software without express prior written permission of A.M.P.A.S. or the
contributors, as appropriate.

This license shall be construed pursuant to the laws of the State of
California, and any disputes related thereto shall be subject to the
jurisdiction of the courts therein.

Disclaimer of Warranty: THIS SOFTWARE IS PROVIDED BY A.M.P.A.S. AND CONTRIBUTORS
"AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO,
THE IMPLIED WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE, AND
NON-INFRINGEMENT ARE DISCLAIMED. IN NO EVENT SHALL A.M.P.A.S., OR ANY
CONTRIBUTORS OR DISTRIBUTORS, BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,
SPECIAL, EXEMPLARY, RESITUTIONARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT
LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR
PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF
LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE
OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF
ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

WITHOUT LIMITING THE GENERALITY OF THE FOREGOING, THE ACADEMY SPECIFICALLY
DISCLAIMS ANY REPRESENTATIONS OR WARRANTIES WHATSOEVER RELATED TO PATENT OR
OTHER INTELLECTUAL PROPERTY RIGHTS IN THE ACADEMY COLOR ENCODING SYSTEM, OR
APPLICATIONS THEREOF, HELD BY PARTIES OTHER THAN A.M.P.A.S.,WHETHER DISCLOSED OR
UNDISCLOSED.
