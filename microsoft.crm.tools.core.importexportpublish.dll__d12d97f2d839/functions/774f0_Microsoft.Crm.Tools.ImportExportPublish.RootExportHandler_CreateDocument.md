# Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::CreateDocument

- ea: `0x774f0`
- end: `0x775fc`
- name: `Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::CreateDocument`
- size: `268`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x776a0`

## callees

- `0x52390`
- `0x774f0`

## string_xrefs

- `0x7753c`: `ImportExportXml`
- `0x775c1`: `ImportExportXml`
- `0x775e9`: `FieldSecurityProfiles`
- `0x77576`: `xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"`
- `0x775c9`: `xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"`

## pseudocode

```c

```

## disassembly

```asm
0x774f0  ldsfld   string [mscorlib]System.String::Empty
0x774f5  stloc.0
0x774f6  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x774fb  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x77500  ldc.i4.2
0x77501  bne.un.s loc_7750B
0x77503  ldstr    aCrmlive// "CrmLive"
0x77508  stloc.0
0x77509  br.s     loc_7751E
0x7750b  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x77510  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x77515  ldc.i4.1
0x77516  bne.un.s loc_7751E
0x77518  ldstr    aOnpremise// "OnPremise"
0x7751d  stloc.0
0x7751e  ldsfld   string [mscorlib]System.String::Empty
0x77523  stloc.1
0x77524  ldarg.1
0x77525  brfalse  loc_775AF
0x7752a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7752f  ldstr    a0Version1Solut// "<{0} version=\"{1}\" SolutionPackageVer"...
0x77534  ldc.i4.6
0x77535  newarr   [mscorlib]System.Object
0x7753a  dup
0x7753b  ldc.i4.0
0x7753c  ldstr    aImportexportxm// "ImportExportXml"
0x77541  stelem.ref
0x77542  dup
0x77543  ldc.i4.1
0x77544  ldarg.0
0x77545  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::context
0x7754a  call     string Microsoft.Crm.Tools.ImportExportPublish.ImportHelper::ReadVersion(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x7754f  stelem.ref
0x77550  dup
0x77551  ldc.i4.2
0x77552  ldarg.0
0x77553  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::context
0x77558  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7755d  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_LanguageCode()
0x77562  stloc.2
0x77563  ldloca.s 2
0x77565  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7756a  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x7756f  stelem.ref
0x77570  dup
0x77571  ldc.i4.3
0x77572  ldloc.0
0x77573  stelem.ref
0x77574  dup
0x77575  ldc.i4.4
0x77576  ldstr    aXmlnsXsiHttpWw// "xmlns:xsi=\"http://www.w3.org/2001/XMLS"...
0x7757b  stelem.ref
0x7757c  dup
0x7757d  ldc.i4.5
0x7757e  ldarg.0
0x7757f  ldfld    class [mscorlib]System.Version Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::_targetVersion
0x77584  ldnull
0x77585  call     bool [mscorlib]System.Version::op_Equality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x7758a  brtrue.s loc_7759A
0x7758c  ldarg.0
0x7758d  ldfld    class [mscorlib]System.Version Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::_targetVersion
0x77592  ldc.i4.2
0x77593  callvirt instance string [mscorlib]System.Version::ToString(int32)
0x77598  br.s     loc_775A6
0x7759a  ldarg.0
0x7759b  ldfld    class [mscorlib]System.Version Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::_metadataVersion
0x775a0  ldc.i4.2
0x775a1  callvirt instance string [mscorlib]System.Version::ToString(int32)
0x775a6  stelem.ref
0x775a7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x775ac  stloc.1
0x775ad  br.s     loc_775F5
0x775af  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x775b4  ldstr    a01223344550// "<{0} {1}><{2}></{2}><{3}></{3}><{4}></{"...
0x775b9  ldc.i4.6
0x775ba  newarr   [mscorlib]System.Object
0x775bf  dup
0x775c0  ldc.i4.0
0x775c1  ldstr    aImportexportxm// "ImportExportXml"
0x775c6  stelem.ref
0x775c7  dup
0x775c8  ldc.i4.1
0x775c9  ldstr    aXmlnsXsiHttpWw// "xmlns:xsi=\"http://www.w3.org/2001/XMLS"...
0x775ce  stelem.ref
0x775cf  dup
0x775d0  ldc.i4.2
0x775d1  ldstr    aEntities_0// "Entities"
0x775d6  stelem.ref
0x775d7  dup
0x775d8  ldc.i4.3
0x775d9  ldstr    aRoles// "Roles"
0x775de  stelem.ref
0x775df  dup
0x775e0  ldc.i4.4
0x775e1  ldstr    aWorkflows// "Workflows"
0x775e6  stelem.ref
0x775e7  dup
0x775e8  ldc.i4.5
0x775e9  ldstr    aFieldsecurityp_1// "FieldSecurityProfiles"
0x775ee  stelem.ref
0x775ef  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x775f4  stloc.1
0x775f5  ldloc.1
0x775f6  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x775fb  ret
```
