# <>c__DisplayClass41_0::<Delete>b__0

- ea: `0x8f0a0`
- end: `0x8f166`
- name: `<>c__DisplayClass41_0::<Delete>b__0`
- size: `198`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x5ecf0`
- `0x66af0`
- `0x8f0a0`

## string_xrefs

- `0x8f0b0`: `Delete Cascade Total execution time`
- `0x8f11e`: `Failed to unistall the component. Exception: {0}, StackTrace: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x8f0a0  ldarg.0
0x8f0a1  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass41_0::context
0x8f0a6  ldstr    aContext// "context"
0x8f0ab  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x8f0b0  ldstr    aDeleteCascadeT// "Delete Cascade Total execution time"
0x8f0b5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmPerformanceCounterExecutionTimeContext::.ctor(string)
0x8f0ba  stloc.0
0x8f0bb  ldarg.0
0x8f0bc  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass41_0::context
0x8f0c1  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction Microsoft.Crm.BusinessEntities.ExecutionContext::get_Transaction()
0x8f0c6  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::get_OpenTransactionCount()
0x8f0cb  ldc.i4.0
0x8f0cc  ceq
0x8f0ce  stloc.1
0x8f0cf  ldloc.1
0x8f0d0  brfalse.s loc_8F0E2
0x8f0d2  ldarg.0
0x8f0d3  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass41_0::context
0x8f0d8  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction Microsoft.Crm.BusinessEntities.ExecutionContext::get_Transaction()
0x8f0dd  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::StartTransaction()
0x8f0e2  nop
0x8f0e3  ldarg.0
0x8f0e4  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid> <>c__DisplayClass41_0::entityIds
0x8f0e9  ldarg.0
0x8f0ea  ldfld    int32 <>c__DisplayClass41_0::entityObjectTypeCode
0x8f0ef  ldarg.0
0x8f0f0  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass41_0::context
0x8f0f5  call     void Microsoft.Crm.BusinessEntities.CascadeEngine::CascadeDeleteDB(class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid> parentEntityIds, int32 parentEntityObjectTypeCode, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x8f0fa  ldloc.1
0x8f0fb  brfalse.s loc_8F10D
0x8f0fd  ldarg.0
0x8f0fe  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass41_0::context
0x8f103  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction Microsoft.Crm.BusinessEntities.ExecutionContext::get_Transaction()
0x8f108  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::CommitTransaction()
0x8f10d  leave.s  loc_8F156
0x8f10f  stloc.2
0x8f110  ldloc.2
0x8f111  ldarg.0
0x8f112  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass41_0::context
0x8f117  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x8f11c  ldc.i4.s 0x14
0x8f11e  ldstr    aFailedToUnista// "Failed to unistall the component. Excep"...
0x8f123  ldc.i4.2
0x8f124  newarr   [mscorlib]System.Object
0x8f129  dup
0x8f12a  ldc.i4.0
0x8f12b  ldloc.2
0x8f12c  callvirt instance string [mscorlib]System.Exception::get_Message()
0x8f131  stelem.ref
0x8f132  dup
0x8f133  ldc.i4.1
0x8f134  ldloc.2
0x8f135  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x8f13a  stelem.ref
0x8f13b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8f140  ldloc.1
0x8f141  brfalse.s loc_8F154
0x8f143  ldarg.0
0x8f144  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass41_0::context
0x8f149  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction Microsoft.Crm.BusinessEntities.ExecutionContext::get_Transaction()
0x8f14e  ldc.i4.0
0x8f14f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::RollbackTransaction(bool)
0x8f154  rethrow
0x8f156  ldc.i4.1
0x8f157  stloc.3
0x8f158  leave.s  loc_8F164
0x8f15a  ldloc.0
0x8f15b  brfalse.s loc_8F163
0x8f15d  ldloc.0
0x8f15e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8f163  endfinally
0x8f164  ldloc.3
0x8f165  ret
```
