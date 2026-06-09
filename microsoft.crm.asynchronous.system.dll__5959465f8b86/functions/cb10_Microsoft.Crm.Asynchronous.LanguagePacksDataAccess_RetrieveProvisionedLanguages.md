# Microsoft.Crm.Asynchronous.LanguagePacksDataAccess::RetrieveProvisionedLanguages

- ea: `0xcb10`
- end: `0xcb53`
- name: `Microsoft.Crm.Asynchronous.LanguagePacksDataAccess::RetrieveProvisionedLanguages`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xc920`

## callees

- `0xfc20`

## pseudocode

```c

```

## disassembly

```asm
0xcb10  newobj   instance void <>c__DisplayClass4_0::.ctor()
0xcb15  stloc.0
0xcb16  ldloc.0
0xcb17  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Version>::.ctor()
0xcb1c  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Version> <>c__DisplayClass4_0::languages
0xcb21  ldstr    aSelectLanguage_0// "select LanguageId, Version from Metadat"...
0xcb26  ldc.i4.1
0xcb27  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0xcb2c  stloc.1
0xcb2d  ldarg.0
0xcb2e  ldloc.1
0xcb2f  ldloc.0
0xcb30  ldftn    instance void <>c__DisplayClass4_0::<RetrieveProvisionedLanguages>b__0(object[] values)
0xcb36  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0xcb3b  ldarg.0
0xcb3c  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0xcb41  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xcb46  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor, valuetype [mscorlib]System.Guid)
0xcb4b  pop
0xcb4c  ldloc.0
0xcb4d  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Version> <>c__DisplayClass4_0::languages
0xcb52  ret
```
