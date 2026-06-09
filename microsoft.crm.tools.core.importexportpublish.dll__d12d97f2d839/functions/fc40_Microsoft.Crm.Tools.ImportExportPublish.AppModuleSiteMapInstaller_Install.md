# Microsoft.Crm.Tools.ImportExportPublish.AppModuleSiteMapInstaller::Install

- ea: `0xfc40`
- end: `0xfe22`
- name: `Microsoft.Crm.Tools.ImportExportPublish.AppModuleSiteMapInstaller::Install`
- size: `482`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x3d890`

## callees

- `0xfc40`
- `0x63db0`
- `0x879c0`
- `0x879f0`

## string_xrefs

- `0xfc76`: `AppModuleSiteMapInstaller.Install(): [siteMapUniqueName:{0}]`
- `0xfcb5`: `AppModuleSiteMapInstaller.Install(): [siteMapName:{0}]`
- `0xfd17`: `AppModuleSiteMapInstaller.Install(): [siteMapName:{0}]`
- `0xfdd7`: `AppModuleSiteMapInstaller.Install(): {0}`
- `0xfe03`: `ImportAppModulesHandler.Install(): Exception: {0}`

## pseudocode

```c

```

## disassembly

```asm
0xfc40  ldarg.1
0xfc41  ldstr    aSitemapuniquen// "SiteMapUniqueName"
0xfc46  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xfc4b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0xfc50  stloc.0
0xfc51  ldloc.0
0xfc52  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xfc57  brfalse.s loc_FC69
0xfc59  ldstr    aTheSitemapuniq// "The SiteMapUniqueName in the AppModuleS"...
0xfc5e  ldc.i4   0x80050109
0xfc63  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xfc68  throw
0xfc69  ldarg.0
0xfc6a  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.AppModuleSiteMapInstaller::_context
0xfc6f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xfc74  ldc.i4.s 0x47
0xfc76  ldstr    aAppmodulesitem// "AppModuleSiteMapInstaller.Install(): [s"...
0xfc7b  ldc.i4.1
0xfc7c  newarr   [mscorlib]System.Object
0xfc81  dup
0xfc82  ldc.i4.0
0xfc83  ldloc.0
0xfc84  stelem.ref
0xfc85  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xfc8a  ldarg.2
0xfc8b  brfalse.s loc_FC95
0xfc8d  ldarg.2
0xfc8e  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Count()
0xfc93  brtrue.s loc_FC9C
0xfc95  ldsfld   string [mscorlib]System.String::Empty
0xfc9a  br.s     loc_FCA7
0xfc9c  ldarg.2
0xfc9d  ldstr    aSitemapname// "sitemapname"
0xfca2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0xfca7  stloc.1
0xfca8  ldarg.0
0xfca9  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.AppModuleSiteMapInstaller::_context
0xfcae  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xfcb3  ldc.i4.s 0x47
0xfcb5  ldstr    aAppmodulesitem_0// "AppModuleSiteMapInstaller.Install(): [s"...
0xfcba  ldc.i4.1
0xfcbb  newarr   [mscorlib]System.Object
0xfcc0  dup
0xfcc1  ldc.i4.0
0xfcc2  ldloc.1
0xfcc3  stelem.ref
0xfcc4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xfcc9  ldloc.1
0xfcca  brfalse.s loc_FCD9
0xfccc  ldloc.1
0xfccd  ldstr    asc_9A18C// ""
0xfcd2  call     bool [mscorlib]System.String::op_Equality(string, string)
0xfcd7  brfalse.s loc_FCF2
0xfcd9  ldarg.1
0xfcda  ldstr    aSitemapname_0// "SiteMapName"
0xfcdf  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xfce4  stloc.s  6
0xfce6  ldloc.s  6
0xfce8  brfalse.s loc_FCF2
0xfcea  ldloc.s  6
0xfcec  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0xfcf1  stloc.1
0xfcf2  ldloc.1
0xfcf3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xfcf8  brfalse.s loc_FD0A
0xfcfa  ldstr    aTheSitemapname// "The SiteMapName in the AppModuleSiteMap"...
0xfcff  ldc.i4   0x80050109
0xfd04  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xfd09  throw
0xfd0a  ldarg.0
0xfd0b  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.AppModuleSiteMapInstaller::_context
0xfd10  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xfd15  ldc.i4.s 0x47
0xfd17  ldstr    aAppmodulesitem_0// "AppModuleSiteMapInstaller.Install(): [s"...
0xfd1c  ldc.i4.1
0xfd1d  newarr   [mscorlib]System.Object
0xfd22  dup
0xfd23  ldc.i4.0
0xfd24  ldloc.1
0xfd25  stelem.ref
0xfd26  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xfd2b  ldarg.1
0xfd2c  ldstr    aSitemap// "SiteMap"
0xfd31  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xfd36  stloc.2
0xfd37  ldarg.0
0xfd38  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.AppModuleSiteMapInstaller::_importDocument
0xfd3d  ldstr    aSitemap// "SiteMap"
0xfd42  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0xfd47  stloc.3
0xfd48  ldloc.3
0xfd49  ldloc.2
0xfd4a  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0xfd4f  pop
0xfd50  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xfd55  ldstr    aImportitemProc// "ImportItem: Processing app module sitem"...
0xfd5a  ldc.i4.1
0xfd5b  newarr   [mscorlib]System.Object
0xfd60  dup
0xfd61  ldc.i4.0
0xfd62  ldloc.0
0xfd63  stelem.ref
0xfd64  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xfd69  stloc.s  4
0xfd6b  ldarg.0
0xfd6c  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.AppModuleSiteMapInstaller::_tracer
0xfd71  ldloc.s  4
0xfd73  ldc.i4.1
0xfd74  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddSuccess(string successMessage, int32 count)
0xfd79  ldarg.0
0xfd7a  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.AppModuleSiteMapInstaller::_context
0xfd7f  ldarg.0
0xfd80  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.AppModuleSiteMapInstaller::_tracer
0xfd85  ldarg.0
0xfd86  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.AppModuleSiteMapInstaller::_importDocument
0xfd8b  ldarg.0
0xfd8c  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.AppModuleSiteMapInstaller::_setup
0xfd91  ldc.i4.0
0xfd92  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer tracer, class [System.Xml]System.Xml.XmlDocument importDocument, bool setup, [opt] bool isInternalSolution)
0xfd97  ldloc.3
0xfd98  ldloc.0
0xfd99  ldloc.1
0xfd9a  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::Install(class [System.Xml]System.Xml.XmlNode siteMapNode, [opt] string sitemapUniqueNameParam, [opt] string siteMapNameParam)
0xfd9f  stloc.s  5
0xfda1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xfda6  ldstr    aImportitemAppM// "ImportItem: App module sitemap with uni"...
0xfdab  ldc.i4.1
0xfdac  newarr   [mscorlib]System.Object
0xfdb1  dup
0xfdb2  ldc.i4.0
0xfdb3  ldloc.0
0xfdb4  stelem.ref
0xfdb5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xfdba  stloc.s  4
0xfdbc  ldarg.0
0xfdbd  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.AppModuleSiteMapInstaller::_tracer
0xfdc2  ldloc.s  4
0xfdc4  ldc.i4.1
0xfdc5  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddSuccess(string successMessage, int32 count)
0xfdca  ldarg.0
0xfdcb  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.AppModuleSiteMapInstaller::_context
0xfdd0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xfdd5  ldc.i4.s 0x47
0xfdd7  ldstr    aAppmodulesitem_1// "AppModuleSiteMapInstaller.Install(): {0"...
0xfddc  ldc.i4.1
0xfddd  newarr   [mscorlib]System.Object
0xfde2  dup
0xfde3  ldc.i4.0
0xfde4  ldloc.s  4
0xfde6  stelem.ref
0xfde7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xfdec  ldloc.s  5
0xfdee  stloc.s  7
0xfdf0  leave.s  loc_FE1F
0xfdf2  stloc.s  8
0xfdf4  ldloc.s  8
0xfdf6  ldarg.0
0xfdf7  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.AppModuleSiteMapInstaller::_context
0xfdfc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xfe01  ldc.i4.s 0x47
0xfe03  ldstr    aImportappmodul// "ImportAppModulesHandler.Install(): Exce"...
0xfe08  ldc.i4.1
0xfe09  newarr   [mscorlib]System.Object
0xfe0e  dup
0xfe0f  ldc.i4.0
0xfe10  ldloc.s  8
0xfe12  callvirt instance string [mscorlib]System.Exception::get_Message()
0xfe17  stelem.ref
0xfe18  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xfe1d  rethrow
0xfe1f  ldloc.s  7
0xfe21  ret
```
