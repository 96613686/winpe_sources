# Microsoft.Crm.Application.Components.UI.ImageStrip::.ctor

- ea: `0x1a040`
- end: `0x1a097`
- name: `Microsoft.Crm.Application.Components.UI.ImageStrip::.ctor`
- size: `87`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1a2d0`

## callees

- `0x1a040`
- `0x1a150`

## string_xrefs

- `0x1a075`: `imagestrips.xml`

## pseudocode

```c

```

## disassembly

```asm
0x1a040  ldarg.0
0x1a041  call     instance void [mscorlib]System.Object::.ctor()
0x1a046  ldarg.0
0x1a047  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x1a04c  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Application.Components.UI.ImageStripImageInfo>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x1a051  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Application.Components.UI.ImageStripImageInfo> Microsoft.Crm.Application.Components.UI.ImageStrip::_imageDefinitions
0x1a056  ldstr    aImgsImagestrip// "/_imgs/imagestrips/transparent_spacer.g"...
0x1a05b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1a060  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1a065  stsfld   class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Components.UI.ImageStrip::TransparentImagePathUri
0x1a06a  ldsfld   class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Components.UI.ImageStrip::TransparentImagePathUri
0x1a06f  ldc.i4.0
0x1a070  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::set_UseVersionStamp(bool)
0x1a075  ldstr    aImagestripsXml// "imagestrips.xml"
0x1a07a  call     string [Microsoft.Crm]Microsoft.Crm.ApplicationFileManager::GetApplicationFilePath(string)
0x1a07f  stloc.0
0x1a080  ldloc.0
0x1a081  call     bool [mscorlib]System.IO.File::Exists(string)
0x1a086  brfalse.s loc_1A096
0x1a088  ldloc.0
0x1a089  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::LoadXmlDocumentFromFile(string)
0x1a08e  stloc.1
0x1a08f  ldarg.0
0x1a090  ldloc.1
0x1a091  call     instance void Microsoft.Crm.Application.Components.UI.ImageStrip::ProcessImageDefinitions(class [System.Xml]System.Xml.XmlDocument imageStripXml)
0x1a096  ret
```
