# Microsoft.Crm.PageParametersCache::GetPageParametersInternal

- ea: `0x480`
- end: `0x632`
- name: `Microsoft.Crm.PageParametersCache::GetPageParametersInternal`
- size: `434`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x3e0`
- `0x3f0`

## callees

- `0x480`
- `0x710`
- `0x760`
- `0x7a0`

## pseudocode

```c

```

## disassembly

```asm
0x480  ldarg.2
0x481  callvirt instance string [System.Web]System.Web.HttpRequest::get_Path()
0x486  stloc.0
0x487  ldarg.2
0x488  callvirt instance string [System.Web]System.Web.HttpRequest::get_CurrentExecutionFilePath()
0x48d  ldstr    aDeferredaction// "/deferredaction.aspx"
0x492  ldc.i4.5
0x493  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x498  brfalse.s loc_4A1
0x49a  ldarg.2
0x49b  callvirt instance string [System.Web]System.Web.HttpRequest::get_CurrentExecutionFilePath()
0x4a0  stloc.0
0x4a1  ldarg.2
0x4a2  callvirt instance string [System.Web]System.Web.HttpRequest::get_Path()
0x4a7  ldstr    aUploadAspx// "/upload.aspx"
0x4ac  ldc.i4.5
0x4ad  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x4b2  brfalse.s loc_4BB
0x4b4  ldarg.2
0x4b5  callvirt instance string [System.Web]System.Web.HttpRequest::get_CurrentExecutionFilePath()
0x4ba  stloc.0
0x4bb  ldloc.0
0x4bc  ldstr    aUserdefinedEdi// "/userdefined/edit.aspx"
0x4c1  ldc.i4.5
0x4c2  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x4c7  brfalse  loc_56D
0x4cc  ldarg.2
0x4cd  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x4d2  ldstr    aEtc// "etc"
0x4d7  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4dc  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4e1  brtrue.s loc_4FC
0x4e3  ldloc.0
0x4e4  ldarg.2
0x4e5  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x4ea  ldstr    aEtc// "etc"
0x4ef  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4f4  call     string [mscorlib]System.String::Concat(string, string)
0x4f9  stloc.0
0x4fa  br.s     loc_52A
0x4fc  ldarg.2
0x4fd  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x502  ldstr    aEtn// "etn"
0x507  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x50c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x511  brtrue.s loc_52A
0x513  ldloc.0
0x514  ldarg.2
0x515  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x51a  ldstr    aEtn// "etn"
0x51f  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x524  call     string [mscorlib]System.String::Concat(string, string)
0x529  stloc.0
0x52a  ldarg.s  4
0x52c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x531  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x536  brfalse.s loc_54C
0x538  ldloc.0
0x539  ldarga.s 4
0x53b  constrained. [mscorlib]System.Guid
0x541  callvirt instance string [mscorlib]System.Object::ToString()
0x546  call     string [mscorlib]System.String::Concat(string, string)
0x54b  stloc.0
0x54c  ldarg.3
0x54d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x552  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x557  brfalse.s loc_56D
0x559  ldloc.0
0x55a  ldarga.s 3
0x55c  constrained. [mscorlib]System.Guid
0x562  callvirt instance string [mscorlib]System.Object::ToString()
0x567  call     string [mscorlib]System.String::Concat(string, string)
0x56c  stloc.0
0x56d  ldloc.0
0x56e  ldstr    aUserdefinedAre// "/userdefined/areas.aspx"
0x573  ldc.i4.5
0x574  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x579  brfalse.s loc_5A9
0x57b  ldarg.2
0x57c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x581  ldstr    aOtype// "otype"
0x586  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x58b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x590  brtrue.s loc_5A9
0x592  ldloc.0
0x593  ldarg.2
0x594  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x599  ldstr    aOtype// "otype"
0x59e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5a3  call     string [mscorlib]System.String::Concat(string, string)
0x5a8  stloc.0
0x5a9  ldloc.0
0x5aa  ldstr    aRootHomepageAs// "/_root/homepage.aspx"
0x5af  ldc.i4.5
0x5b0  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x5b5  brfalse.s loc_615
0x5b7  ldarg.2
0x5b8  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x5bd  ldstr    aEtc// "etc"
0x5c2  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5c7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5cc  brtrue.s loc_5E7
0x5ce  ldloc.0
0x5cf  ldarg.2
0x5d0  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x5d5  ldstr    aEtc// "etc"
0x5da  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5df  call     string [mscorlib]System.String::Concat(string, string)
0x5e4  stloc.0
0x5e5  br.s     loc_615
0x5e7  ldarg.2
0x5e8  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x5ed  ldstr    aEtn// "etn"
0x5f2  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5f7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5fc  brtrue.s loc_615
0x5fe  ldloc.0
0x5ff  ldarg.2
0x600  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x605  ldstr    aEtn// "etn"
0x60a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x60f  call     string [mscorlib]System.String::Concat(string, string)
0x614  stloc.0
0x615  ldarg.0
0x616  ldloc.0
0x617  call     instance class Microsoft.Crm.PageParameters Microsoft.Crm.PageParametersCache::GetPageParametersFromCache(string physicalPath)
0x61c  stloc.1
0x61d  ldloc.1
0x61e  brtrue.s loc_630
0x620  ldarg.0
0x621  ldarg.1
0x622  call     instance class Microsoft.Crm.PageParameters Microsoft.Crm.PageParametersCache::ReadPageParametersFromAttributes(object page)
0x627  stloc.1
0x628  ldarg.0
0x629  ldloc.0
0x62a  ldloc.1
0x62b  call     instance void Microsoft.Crm.PageParametersCache::AddPageParametersToCache(string physicalPath, class Microsoft.Crm.PageParameters pageParameters)
0x630  ldloc.1
0x631  ret
```
