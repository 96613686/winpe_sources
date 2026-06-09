# Microsoft.Crm.Common.Application.Pages.Common.Icon::GetIconBits

- ea: `0x1c110`
- end: `0x1c334`
- name: `Microsoft.Crm.Common.Application.Pages.Common.Icon::GetIconBits`
- size: `548`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1bfa0`

## callees

- `0x1c110`
- `0x1c340`

## string_xrefs

- `0x1c25b`: `image/svg+xml`

## pseudocode

```c

```

## disassembly

```asm
0x1c110  ldsfld   string [mscorlib]System.String::Empty
0x1c115  stloc.0
0x1c116  ldnull
0x1c117  stloc.1
0x1c118  ldnull
0x1c119  stloc.2
0x1c11a  ldarg.1
0x1c11b  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x1c120  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsUserDefinedEntityObjectTypeCode(int32)
0x1c125  brfalse.s loc_1C12F
0x1c127  ldarg.1
0x1c128  ldarg.2
0x1c129  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconUtil::GetIconWebResourceName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconType)
0x1c12e  stloc.2
0x1c12f  ldloc.2
0x1c130  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1c135  brtrue.s loc_1C1B0
0x1c137  ldloc.2
0x1c138  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1c13d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::GetWebResources(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1c142  stloc.3
0x1c143  ldloc.3
0x1c144  brfalse.s loc_1C14E
0x1c146  ldloc.3
0x1c147  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x1c14c  brtrue.s loc_1C164
0x1c14e  ldstr    aCouldNotFindAW// "Could not find a web resource with name"...
0x1c153  ldloc.2
0x1c154  ldstr    asc_32ABE// "."
0x1c159  call     string [mscorlib]System.String::Concat(string, string, string)
0x1c15e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x1c163  throw
0x1c164  ldloc.3
0x1c165  ldc.i4.0
0x1c166  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0x1c16b  stloc.s  4
0x1c16d  ldloc.s  4
0x1c16f  ldstr    aContent// "content"
0x1c174  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x1c179  castclass [mscorlib]System.String
0x1c17e  stloc.s  5
0x1c180  ldloc.s  5
0x1c182  brtrue.s loc_1C18B
0x1c184  ldsfld   string [mscorlib]System.String::Empty
0x1c189  stloc.s  5
0x1c18b  ldloc.s  5
0x1c18d  call     unsigned int8[] [mscorlib]System.Convert::FromBase64String(string)
0x1c192  stloc.1
0x1c193  ldarg.3
0x1c194  ldloc.s  4
0x1c196  ldstr    aWebresourcetyp// "webresourcetype"
0x1c19b  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x1c1a0  unbox.any [mscorlib]System.Int32
0x1c1a5  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.Handlers.WebResource::GetMimeType(int32)
0x1c1aa  stind.ref
0x1c1ab  br       loc_1C309
0x1c1b0  ldarg.1
0x1c1b1  callvirt instance class [mscorlib]System.Type [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EntityType()
0x1c1b6  ldnull
0x1c1b7  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1c1bc  brfalse.s loc_1C1F0
0x1c1be  ldarg.1
0x1c1bf  callvirt instance class [mscorlib]System.Type [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EntityType()
0x1c1c4  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x1c1c9  ldstr    aCustomactivity// "CustomActivity"
0x1c1ce  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1c1d3  brfalse.s loc_1C1F0
0x1c1d5  ldarg.1
0x1c1d6  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsActivity()
0x1c1db  brfalse.s loc_1C1F0
0x1c1dd  ldarg.1
0x1c1de  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsCustomEntity()
0x1c1e3  brfalse.s loc_1C1F0
0x1c1e5  ldarg.1
0x1c1e6  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsActivityParty()
0x1c1eb  ldc.i4.0
0x1c1ec  ceq
0x1c1ee  br.s     loc_1C1F1
0x1c1f0  ldc.i4.0
0x1c1f1  stloc.s  6
0x1c1f3  ldarg.2
0x1c1f4  switch   loc_1C226, loc_1C2FA, loc_1C266, loc_1C291, loc_1C2A0, loc_1C2AF, loc_1C2AF, loc_1C2CF, loc_1C2FA, loc_1C254
0x1c221  br       loc_1C2FA
0x1c226  ldloc.s  6
0x1c228  brfalse.s loc_1C232
0x1c22a  ldstr    aImgsIco16Custo// "/_imgs/ico_16_customActivity.gif"
0x1c22f  stloc.0
0x1c230  br.s     loc_1C248
0x1c232  ldarg.1
0x1c233  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsBPFEntity()
0x1c238  brfalse.s loc_1C242
0x1c23a  ldstr    aImgsIco164703P// "/_imgs/ico_16_4703.png"
0x1c23f  stloc.0
0x1c240  br.s     loc_1C248
0x1c242  ldstr    aImgsIco16Custo_0// "/_imgs/ico_16_customEntity.gif"
0x1c247  stloc.0
0x1c248  ldarg.3
0x1c249  ldstr    aImageGif// "image/gif"
0x1c24e  stind.ref
0x1c24f  br       loc_1C301
0x1c254  ldstr    aImgsIcoSvgCust// "/_imgs/ico_svg_customEntity.svg"
0x1c259  stloc.0
0x1c25a  ldarg.3
0x1c25b  ldstr    aImageSvgXml// "image/svg+xml"
0x1c260  stind.ref
0x1c261  br       loc_1C301
0x1c266  ldloc.s  6
0x1c268  brfalse.s loc_1C272
0x1c26a  ldstr    aImgsIco18Custo// "/_imgs/ico_18_customActivity.gif"
0x1c26f  stloc.0
0x1c270  br.s     loc_1C288
0x1c272  ldarg.1
0x1c273  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsBPFEntity()
0x1c278  brfalse.s loc_1C282
0x1c27a  ldstr    aImgsIco184703P// "/_imgs/ico_18_4703.png"
0x1c27f  stloc.0
0x1c280  br.s     loc_1C288
0x1c282  ldstr    aImgsIco18Custo_0// "/_imgs/ico_18_customEntity.gif"
0x1c287  stloc.0
0x1c288  ldarg.3
0x1c289  ldstr    aImageGif// "image/gif"
0x1c28e  stind.ref
0x1c28f  br.s     loc_1C301
0x1c291  ldstr    aImgsOlkCustome// "/_imgs/olk_customEntity.ico"
0x1c296  stloc.0
0x1c297  ldarg.3
0x1c298  ldstr    aImageXIcon// "image/x-icon"
0x1c29d  stind.ref
0x1c29e  br.s     loc_1C301
0x1c2a0  ldstr    aImgsIcoLrgCust// "/_imgs/ico_lrg_customEntity.gif"
0x1c2a5  stloc.0
0x1c2a6  ldarg.3
0x1c2a7  ldstr    aImageGif// "image/gif"
0x1c2ac  stind.ref
0x1c2ad  br.s     loc_1C301
0x1c2af  ldarg.1
0x1c2b0  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x1c2b5  ldarg.2
0x1c2b6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1c2bb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconUtil::GetIconPath(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1c2c0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Path()
0x1c2c5  stloc.0
0x1c2c6  ldarg.3
0x1c2c7  ldstr    aImagePng// "image/png"
0x1c2cc  stind.ref
0x1c2cd  br.s     loc_1C301
0x1c2cf  ldloc.s  6
0x1c2d1  brfalse.s loc_1C2DB
0x1c2d3  ldstr    aImgsFormentity// "/_imgs/formentity/ico_fhe_CustomActivit"...
0x1c2d8  stloc.0
0x1c2d9  br.s     loc_1C2F1
0x1c2db  ldarg.1
0x1c2dc  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsBPFEntity()
0x1c2e1  brfalse.s loc_1C2EB
0x1c2e3  ldstr    aImgsFormentity_0// "/_imgs/formentity/ico_fhe_4703.png"
0x1c2e8  stloc.0
0x1c2e9  br.s     loc_1C2F1
0x1c2eb  ldstr    aImgsFormentity_1// "/_imgs/formentity/ico_fhe_CustomEntity."...
0x1c2f0  stloc.0
0x1c2f1  ldarg.3
0x1c2f2  ldstr    aImagePng// "image/png"
0x1c2f7  stind.ref
0x1c2f8  br.s     loc_1C301
0x1c2fa  ldarg.3
0x1c2fb  ldstr    aImageGif// "image/gif"
0x1c300  stind.ref
0x1c301  ldarg.0
0x1c302  ldloc.0
0x1c303  call     instance unsigned int8[] Microsoft.Crm.Common.Application.Pages.Common.Icon::GetBytesFromPath(string iconUrl)
0x1c308  stloc.1
0x1c309  ldloc.1
0x1c30a  brtrue.s loc_1C332
0x1c30c  ldarg.2
0x1c30d  ldc.i4.5
0x1c30e  bne.un.s loc_1C320
0x1c310  ldstr    aImgsPlaceholde// "/_imgs/placeholders/ribbon_placeholder_"...
0x1c315  stloc.0
0x1c316  ldarg.0
0x1c317  ldloc.0
0x1c318  call     instance unsigned int8[] Microsoft.Crm.Common.Application.Pages.Common.Icon::GetBytesFromPath(string iconUrl)
0x1c31d  stloc.1
0x1c31e  br.s     loc_1C332
0x1c320  ldarg.2
0x1c321  ldc.i4.6
0x1c322  bne.un.s loc_1C332
0x1c324  ldstr    aImgsPlaceholde_0// "/_imgs/placeholders/ribbon_placeholder_"...
0x1c329  stloc.0
0x1c32a  ldarg.0
0x1c32b  ldloc.0
0x1c32c  call     instance unsigned int8[] Microsoft.Crm.Common.Application.Pages.Common.Icon::GetBytesFromPath(string iconUrl)
0x1c331  stloc.1
0x1c332  ldloc.1
0x1c333  ret
```
