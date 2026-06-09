# Microsoft.Crm.Service.Application.Pages.Grids.Commands.AddSiteMembers::ConfigurePage

- ea: `0x11480`
- end: `0x115c1`
- name: `Microsoft.Crm.Service.Application.Pages.Grids.Commands.AddSiteMembers::ConfigurePage`
- size: `321`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x11480`

## pseudocode

```c

```

## disassembly

```asm
0x11480  ldarg.0
0x11481  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x11486  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x1148b  stloc.0
0x1148c  ldloc.0
0x1148d  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x11492  ldc.i4.0
0x11493  conv.i8
0x11494  ble      loc_115C0
0x11499  ldloc.0
0x1149a  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(class [mscorlib]System.IO.Stream)
0x1149f  callvirt instance string [mscorlib]System.IO.TextReader::ReadToEnd()
0x114a4  stloc.1
0x114a5  ldloc.1
0x114a6  ldstr    aUsers// "users"
0x114ab  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetNodeValue(string, string)
0x114b0  ldc.i4.1
0x114b1  newarr   [mscorlib]System.Char
0x114b6  dup
0x114b7  ldc.i4.0
0x114b8  ldc.i4.s 0x3B
0x114ba  stelem.i2
0x114bb  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x114c0  stloc.2
0x114c1  ldloc.1
0x114c2  ldstr    aEquipment// "equipment"
0x114c7  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetNodeValue(string, string)
0x114cc  ldc.i4.1
0x114cd  newarr   [mscorlib]System.Char
0x114d2  dup
0x114d3  ldc.i4.0
0x114d4  ldc.i4.s 0x3B
0x114d6  stelem.i2
0x114d7  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x114dc  stloc.3
0x114dd  ldloca.s 4
0x114df  ldloc.1
0x114e0  ldstr    aSite// "site"
0x114e5  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetNodeValue(string, string)
0x114ea  call     instance void [mscorlib]System.Guid::.ctor(string)
0x114ef  ldloc.2
0x114f0  stloc.s  5
0x114f2  ldc.i4.0
0x114f3  stloc.s  6
0x114f5  br.s     loc_11546
0x114f7  ldloc.s  5
0x114f9  ldloc.s  6
0x114fb  ldelem.ref
0x114fc  stloc.s  7
0x114fe  ldloc.s  7
0x11500  callvirt instance int32 [mscorlib]System.String::get_Length()
0x11505  ldc.i4.0
0x11506  ble.s    loc_11540
0x11508  ldstr    aSystemuser// "systemuser"
0x1150d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x11512  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x11517  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x1151c  dup
0x1151d  ldloc.s  7
0x1151f  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0x11524  dup
0x11525  ldstr    aSiteid// "siteid"
0x1152a  ldloc.s  4
0x1152c  box      [mscorlib]System.Guid
0x11531  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x11536  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1153b  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Update(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x11540  ldloc.s  6
0x11542  ldc.i4.1
0x11543  add
0x11544  stloc.s  6
0x11546  ldloc.s  6
0x11548  ldloc.s  5
0x1154a  ldlen
0x1154b  conv.i4
0x1154c  blt.s    loc_114F7
0x1154e  ldloc.3
0x1154f  stloc.s  5
0x11551  ldc.i4.0
0x11552  stloc.s  6
0x11554  br.s     loc_115A5
0x11556  ldloc.s  5
0x11558  ldloc.s  6
0x1155a  ldelem.ref
0x1155b  stloc.s  8
0x1155d  ldloc.s  8
0x1155f  callvirt instance int32 [mscorlib]System.String::get_Length()
0x11564  ldc.i4.0
0x11565  ble.s    loc_1159F
0x11567  ldstr    aEquipment// "equipment"
0x1156c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x11571  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x11576  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x1157b  dup
0x1157c  ldloc.s  8
0x1157e  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0x11583  dup
0x11584  ldstr    aSiteid// "siteid"
0x11589  ldloc.s  4
0x1158b  box      [mscorlib]System.Guid
0x11590  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x11595  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1159a  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Update(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1159f  ldloc.s  6
0x115a1  ldc.i4.1
0x115a2  add
0x115a3  stloc.s  6
0x115a5  ldloc.s  6
0x115a7  ldloc.s  5
0x115a9  ldlen
0x115aa  conv.i4
0x115ab  blt.s    loc_11556
0x115ad  ldarg.0
0x115ae  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x115b3  call     void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::RaiseXMLSuccess(class [System.Web]System.Web.UI.Page)
0x115b8  leave.s  loc_115C0
0x115ba  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x115bf  throw
0x115c0  ret
```
