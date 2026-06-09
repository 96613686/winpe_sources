# <>c__DisplayClass18_0::<CollectUpdatedDataParallel>b__0

- ea: `0xac600`
- end: `0xac6d7`
- name: `<>c__DisplayClass18_0::<CollectUpdatedDataParallel>b__0`
- size: `215`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, installer_update`

## callees

- `0x52020`
- `0x525d0`
- `0x5c5a0`
- `0x5c640`
- `0x5c6a0`
- `0xac600`

## string_xrefs

- `0xac61a`: `Privilege`
- `0xac689`: `MetadataDescriptions already loaded for `

## pseudocode

```c

```

## disassembly

```asm
0xac600  ldarg.0
0xac601  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext <>c__DisplayClass18_0::organizationContext
0xac606  call     class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.Metadata.NonSharableMetadataCacheLoader::CreateNewCrmDbConnection(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0xac60b  stloc.0
0xac60c  ldarg.0
0xac60d  ldloc.0
0xac60e  ldnull
0xac60f  ldc.i4.0
0xac610  call     class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.ISqlDataAccess Microsoft.Crm.Metadata.Helpers::GetSqlDataAccesser(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection connection, class [System.Data]System.Data.IDbTransaction transaction, [opt] int32 sqlMaxPoolSize)
0xac615  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.ISqlDataAccess <>c__DisplayClass18_0::crmSqlDataAccesser
0xac61a  ldstr    aPrivilege// "Privilege"
0xac61f  ldarg.1
0xac620  callvirt instance string Microsoft.Crm.Metadata.TableFillProperties::get_MetadataEntityName()
0xac625  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xac62a  brfalse.s loc_AC6A6
0xac62c  ldarg.0
0xac62d  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.IMetadataDescription>> <>c__DisplayClass18_0::descriptionsCollection
0xac632  ldarg.1
0xac633  callvirt instance string Microsoft.Crm.Metadata.TableFillProperties::get_MetadataEntityName()
0xac638  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.IMetadataDescription>::.ctor()
0xac63d  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.IMetadataDescription>>::TryAdd(var<u1>, !!T0)
0xac642  brfalse.s loc_AC67B
0xac644  ldarg.0
0xac645  ldfld    class Microsoft.Crm.Metadata.MetadataForMetadata <>c__DisplayClass18_0::metadataForMetadata
0xac64a  ldarg.0
0xac64b  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.ISqlDataAccess <>c__DisplayClass18_0::crmSqlDataAccesser
0xac650  ldarg.0
0xac651  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.IMetadataDescription>> <>c__DisplayClass18_0::descriptionsCollection
0xac656  ldarg.1
0xac657  callvirt instance string Microsoft.Crm.Metadata.TableFillProperties::get_MetadataEntityName()
0xac65c  callvirt instance var<u1> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.IMetadataDescription>>::get_Item(void)
0xac661  ldarg.1
0xac662  ldarg.0
0xac663  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CounterList <>c__DisplayClass18_0::counter
0xac668  ldarg.0
0xac669  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext <>c__DisplayClass18_0::organizationContext
0xac66e  ldarg.0
0xac66f  ldfld    class [mscorlib]System.Func`3<string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, class Microsoft.Crm.Metadata.IFillableMetadataDescription> <>c__DisplayClass18_0::createFillableDescriptionFunction
0xac674  call     void Microsoft.Crm.Metadata.NonSharableMetadataCacheLoader::CollectDescriptions(class Microsoft.Crm.Metadata.MetadataForMetadata metadataForMetadata, class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.ISqlDataAccess crmSqlDataAccesser, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.IMetadataDescription> descriptionsList, class Microsoft.Crm.Metadata.TableFillProperties properties, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList counter, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext, class [mscorlib]System.Func`3<string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, class Microsoft.Crm.Metadata.IFillableMetadataDescription> createFillableDescriptionFunction)
0xac679  leave.s  loc_AC6D6
0xac67b  ldnull
0xac67c  ldarg.0
0xac67d  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext <>c__DisplayClass18_0::organizationContext
0xac682  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0xac687  ldc.i4.s 0x14
0xac689  ldstr    aMetadatadescri_0// "MetadataDescriptions already loaded for"...
0xac68e  ldarg.1
0xac68f  callvirt instance string Microsoft.Crm.Metadata.TableFillProperties::get_MetadataEntityName()
0xac694  call     string [mscorlib]System.String::Concat(string, string)
0xac699  ldc.i4.0
0xac69a  newarr   [mscorlib]System.Object
0xac69f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xac6a4  leave.s  loc_AC6D6
0xac6a6  ldarg.0
0xac6a7  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.ISqlDataAccess <>c__DisplayClass18_0::crmSqlDataAccesser
0xac6ac  ldarg.0
0xac6ad  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.Privilege> <>c__DisplayClass18_0::privilegesList
0xac6b2  ldarg.1
0xac6b3  ldarg.0
0xac6b4  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CounterList <>c__DisplayClass18_0::counter
0xac6b9  ldarg.0
0xac6ba  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext <>c__DisplayClass18_0::organizationContext
0xac6bf  ldarg.0
0xac6c0  ldfld    class [mscorlib]System.Func`3<string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, class Microsoft.Crm.Metadata.IFillableMetadataDescription> <>c__DisplayClass18_0::createFillableDescriptionFunction
0xac6c5  call     void Microsoft.Crm.Metadata.NonSharableMetadataCacheLoader::CollectPrivileges(class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.ISqlDataAccess crmSqlDataAccesser, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.Privilege> privilegesList, class Microsoft.Crm.Metadata.TableFillProperties properties, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList counter, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext, class [mscorlib]System.Func`3<string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, class Microsoft.Crm.Metadata.IFillableMetadataDescription> createFillableDescriptionFunction)
0xac6ca  leave.s  loc_AC6D6
0xac6cc  ldloc.0
0xac6cd  brfalse.s loc_AC6D5
0xac6cf  ldloc.0
0xac6d0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xac6d5  endfinally
0xac6d6  ret
```
