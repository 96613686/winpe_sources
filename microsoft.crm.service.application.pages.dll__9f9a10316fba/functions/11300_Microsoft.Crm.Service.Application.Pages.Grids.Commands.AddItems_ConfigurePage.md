# Microsoft.Crm.Service.Application.Pages.Grids.Commands.AddItems::ConfigurePage

- ea: `0x11300`
- end: `0x11452`
- name: `Microsoft.Crm.Service.Application.Pages.Grids.Commands.AddItems::ConfigurePage`
- size: `338`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x11300`

## pseudocode

```c

```

## disassembly

```asm
0x11300  ldarg.0
0x11301  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x11306  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x1130b  stloc.0
0x1130c  ldloc.0
0x1130d  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x11312  ldc.i4.0
0x11313  conv.i8
0x11314  ble      loc_11451
0x11319  ldloc.0
0x1131a  call     string [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::ReadXmlFromStream(class [mscorlib]System.IO.Stream)
0x1131f  stloc.1
0x11320  ldloc.1
0x11321  ldstr    aResources// "resources"
0x11326  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetNodeValue(string, string)
0x1132b  ldc.i4.1
0x1132c  newarr   [mscorlib]System.Char
0x11331  dup
0x11332  ldc.i4.0
0x11333  ldc.i4.s 0x3B
0x11335  stelem.i2
0x11336  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x1133b  dup
0x1133c  ldlen
0x1133d  conv.i4
0x1133e  newarr   [mscorlib]System.Guid
0x11343  stloc.2
0x11344  ldc.i4.0
0x11345  stloc.3
0x11346  stloc.s  4
0x11348  ldc.i4.0
0x11349  stloc.s  5
0x1134b  br.s     loc_1136C
0x1134d  ldloc.s  4
0x1134f  ldloc.s  5
0x11351  ldelem.ref
0x11352  stloc.s  6
0x11354  ldloc.2
0x11355  ldloc.3
0x11356  dup
0x11357  ldc.i4.1
0x11358  add
0x11359  stloc.3
0x1135a  ldloc.s  6
0x1135c  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x11361  stelem   [mscorlib]System.Guid
0x11366  ldloc.s  5
0x11368  ldc.i4.1
0x11369  add
0x1136a  stloc.s  5
0x1136c  ldloc.s  5
0x1136e  ldloc.s  4
0x11370  ldlen
0x11371  conv.i4
0x11372  blt.s    loc_1134D
0x11374  ldloc.1
0x11375  ldstr    aResourcegroups// "resourcegroups"
0x1137a  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetNodeValue(string, string)
0x1137f  ldc.i4.1
0x11380  newarr   [mscorlib]System.Char
0x11385  dup
0x11386  ldc.i4.0
0x11387  ldc.i4.s 0x3B
0x11389  stelem.i2
0x1138a  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x1138f  stloc.s  4
0x11391  ldc.i4.0
0x11392  stloc.s  5
0x11394  br       loc_11433
0x11399  ldloc.s  4
0x1139b  ldloc.s  5
0x1139d  ldelem.ref
0x1139e  stloc.s  7
0x113a0  ldc.i4.1
0x113a1  newarr   [mscorlib]System.String
0x113a6  dup
0x113a7  ldc.i4.0
0x113a8  ldstr    aObjecttypecode// "objecttypecode"
0x113ad  stelem.ref
0x113ae  stloc.s  8
0x113b0  ldstr    aResourcegroup// "resourcegroup"
0x113b5  ldloc.s  7
0x113b7  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x113bc  ldloc.s  8
0x113be  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x113c3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x113c8  ldstr    aObjecttypecode// "objecttypecode"
0x113cd  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x113d2  unbox.any [mscorlib]System.Int32
0x113d7  ldc.i4   0xFA7
0x113dc  bne.un.s loc_1142D
0x113de  ldc.i4.1
0x113df  newarr   [mscorlib]System.String
0x113e4  dup
0x113e5  ldc.i4.0
0x113e6  ldstr    aGrouptypecode// "grouptypecode"
0x113eb  stelem.ref
0x113ec  pop
0x113ed  ldstr    aConstraintbase// "constraintbasedgroup"
0x113f2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x113f7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x113fc  newobj   instance void [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.ConstraintBasedGroup::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x11401  dup
0x11402  ldloc.s  7
0x11404  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0x11409  dup
0x1140a  ldc.i4.0
0x1140b  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_IsNew(bool)
0x11410  dup
0x11411  ldloc.2
0x11412  callvirt instance void [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.ConstraintBasedGroup::AddMembers(valuetype [mscorlib]System.Guid[])
0x11417  dup
0x11418  ldstr    aGrouptypecode// "grouptypecode"
0x1141d  ldc.i4.0
0x1141e  box      [mscorlib]System.Int32
0x11423  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x11428  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Update()
0x1142d  ldloc.s  5
0x1142f  ldc.i4.1
0x11430  add
0x11431  stloc.s  5
0x11433  ldloc.s  5
0x11435  ldloc.s  4
0x11437  ldlen
0x11438  conv.i4
0x11439  blt      loc_11399
0x1143e  ldarg.0
0x1143f  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x11444  call     void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::RaiseXMLSuccess(class [System.Web]System.Web.UI.Page)
0x11449  leave.s  loc_11451
0x1144b  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x11450  throw
0x11451  ret
```
