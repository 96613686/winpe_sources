# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetIconParams

- ea: `0x4020`
- end: `0x40f5`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetIconParams`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x37d0`

## callees

- `0x190`
- `0x200`
- `0x4020`
- `0x4150`

## pseudocode

```c

```

## disassembly

```asm
0x4020  ldarg.1
0x4021  ldstr    aIconlarge// "iconlarge"
0x4026  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x402b  brfalse.s loc_4055
0x402d  ldarg.1
0x402e  ldstr    aIconlarge// "iconlarge"
0x4033  ldnull
0x4034  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0x4039  stloc.0
0x403a  ldloc.0
0x403b  ldc.i4   0x80632105
0x4040  ldc.i4   0x80632109
0x4045  ldc.i4.s 0x42
0x4047  ldc.i4.s 0x30
0x4049  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::ValidateIcon(string webResourceName, int32 sizeErrorCode, int32 dimensionsErrorCode, int16 maxWidth, int16 maxHeight)
0x404e  ldarg.0
0x404f  ldloc.0
0x4050  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_IconLargeName(string)
0x4055  ldarg.1
0x4056  ldstr    aIconmedium// "iconmedium"
0x405b  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x4060  brfalse.s loc_408A
0x4062  ldarg.1
0x4063  ldstr    aIconmedium// "iconmedium"
0x4068  ldnull
0x4069  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0x406e  stloc.0
0x406f  ldloc.0
0x4070  ldc.i4   0x80632106
0x4075  ldc.i4   0x8063210A
0x407a  ldc.i4.s 0x20
0x407c  ldc.i4.s 0x20
0x407e  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::ValidateIcon(string webResourceName, int32 sizeErrorCode, int32 dimensionsErrorCode, int16 maxWidth, int16 maxHeight)
0x4083  ldarg.0
0x4084  ldloc.0
0x4085  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_IconMediumName(string)
0x408a  ldarg.1
0x408b  ldstr    aIconsmall// "iconsmall"
0x4090  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x4095  brfalse.s loc_40BF
0x4097  ldarg.1
0x4098  ldstr    aIconsmall// "iconsmall"
0x409d  ldnull
0x409e  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0x40a3  stloc.0
0x40a4  ldloc.0
0x40a5  ldc.i4   0x80632104
0x40aa  ldc.i4   0x80632108
0x40af  ldc.i4.s 0x10
0x40b1  ldc.i4.s 0x10
0x40b3  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::ValidateIcon(string webResourceName, int32 sizeErrorCode, int32 dimensionsErrorCode, int16 maxWidth, int16 maxHeight)
0x40b8  ldarg.0
0x40b9  ldloc.0
0x40ba  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_IconSmallName(string)
0x40bf  ldarg.1
0x40c0  ldstr    aIconvector// "iconvector"
0x40c5  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x40ca  brfalse.s loc_40F4
0x40cc  ldarg.1
0x40cd  ldstr    aIconvector// "iconvector"
0x40d2  ldnull
0x40d3  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0x40d8  stloc.0
0x40d9  ldloc.0
0x40da  ldc.i4   0x80632104
0x40df  ldc.i4   0x80632108
0x40e4  ldc.i4.s 0x10
0x40e6  ldc.i4.s 0x10
0x40e8  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::ValidateIcon(string webResourceName, int32 sizeErrorCode, int32 dimensionsErrorCode, int16 maxWidth, int16 maxHeight)
0x40ed  ldarg.0
0x40ee  ldloc.0
0x40ef  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_IconVectorName(string)
0x40f4  ret
```
