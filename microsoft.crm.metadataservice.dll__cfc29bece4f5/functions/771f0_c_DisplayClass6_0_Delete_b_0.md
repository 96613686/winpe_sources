# <>c__DisplayClass6_0::<Delete>b__0

- ea: `0x771f0`
- end: `0x772e1`
- name: `<>c__DisplayClass6_0::<Delete>b__0`
- size: `241`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, service_task`

## callees

- `0x471b0`
- `0x57320`
- `0x5a810`
- `0x771f0`

## string_xrefs

- `0x77237`: `prvDeleteRelationship`
- `0x772bc`: `RelationshipService.Delete caught exception: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x771f0  ldarg.0
0x771f1  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass6_0::entityRelationshipId
0x771f6  ldstr    aEntityrelation_9// "entityRelationshipId"
0x771fb  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x77200  ldarg.0
0x77201  ldfld    class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper <>c__DisplayClass6_0::metadataHelper
0x77206  ldstr    aMetadatahelper// "metadataHelper"
0x7720b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x77210  ldarg.0
0x77211  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass6_0::context
0x77216  ldstr    aContext// "context"
0x7721b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x77220  ldarg.0
0x77221  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass6_0::context
0x77226  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7722b  pop
0x7722c  ldarg.0
0x7722d  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass6_0::context
0x77232  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x77237  ldstr    aPrvdeleterelat// "prvDeleteRelationship"
0x7723c  ldarg.0
0x7723d  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass6_0::context
0x77242  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.CustomizationSecurityCache::GetPrivilegeIdFromName(string privilegeName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x77247  ldarg.0
0x77248  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass6_0::context
0x7724d  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x77252  ldarg.0
0x77253  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass6_0::context
0x77258  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::StartTransactionIfRequired()
0x7725d  stloc.0
0x7725e  ldarg.0
0x7725f  ldfld    class Microsoft.Crm.Metadata.ManyToManyRelationshipService <>c__DisplayClass6_0::<>4__this
0x77264  ldarg.0
0x77265  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass6_0::entityRelationshipId
0x7726a  ldarg.0
0x7726b  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass6_0::context
0x77270  call     instance void Microsoft.Crm.Metadata.RelationshipServiceBase::ValidateForDelete(valuetype [mscorlib]System.Guid entityRelationshipId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x77275  ldarg.0
0x77276  ldfld    class Microsoft.Crm.Metadata.ManyToManyRelationshipService <>c__DisplayClass6_0::<>4__this
0x7727b  ldarg.0
0x7727c  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass6_0::entityRelationshipId
0x77281  ldarg.0
0x77282  ldfld    class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper <>c__DisplayClass6_0::metadataHelper
0x77287  ldarg.0
0x77288  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass6_0::context
0x7728d  call     instance void Microsoft.Crm.Metadata.ManyToManyRelationshipService::DeleteInternal(valuetype [mscorlib]System.Guid entityRelationshipId, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x77292  ldarg.0
0x77293  ldfld    class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper <>c__DisplayClass6_0::metadataHelper
0x77298  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::ProcessQueue()
0x7729d  ldloc.0
0x7729e  brfalse.s loc_772AB
0x772a0  ldarg.0
0x772a1  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass6_0::context
0x772a6  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::CommitTransaction()
0x772ab  leave.s  loc_772E0
0x772ad  stloc.1
0x772ae  ldloc.1
0x772af  ldarg.0
0x772b0  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass6_0::context
0x772b5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x772ba  ldc.i4.s 0x19
0x772bc  ldstr    aRelationshipse// "RelationshipService.Delete caught excep"...
0x772c1  ldc.i4.1
0x772c2  newarr   [mscorlib]System.Object
0x772c7  dup
0x772c8  ldc.i4.0
0x772c9  ldloc.1
0x772ca  stelem.ref
0x772cb  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x772d0  ldloc.0
0x772d1  brfalse.s loc_772DE
0x772d3  ldarg.0
0x772d4  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass6_0::context
0x772d9  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::RollbackTransaction()
0x772de  rethrow
0x772e0  ret
```
