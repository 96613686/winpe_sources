# Microsoft.Crm.Extensibility.OrganizationSdkServiceInternal::GetOrganizationContext

- ea: `0xb160`
- end: `0xb1a7`
- name: `Microsoft.Crm.Extensibility.OrganizationSdkServiceInternal::GetOrganizationContext`
- size: `71`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x4f00`
- `0xac00`

## callees

- `0xb160`

## string_xrefs

- `0xb18c`: `An open execution context was found but did not match organization for current SDK call`

## pseudocode

```c

```

## disassembly

```asm
0xb160  ldnull
0xb161  stloc.0
0xb162  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.OpenExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.OpenExecutionContext::get_Instance()
0xb167  ldarg.0
0xb168  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken::get_TransactionContextId()
0xb16d  ldloca.s 0
0xb16f  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.OpenExecutionContext::TryGetContext(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext&)
0xb174  pop
0xb175  ldloc.0
0xb176  brfalse.s loc_B18B
0xb178  ldloc.0
0xb179  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xb17e  ldarg.1
0xb17f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth::get_OrganizationId()
0xb184  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xb189  br.s     loc_B18C
0xb18b  ldc.i4.1
0xb18c  ldstr    aAnOpenExecutio// "An open execution context was found but"...
0xb191  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0xb196  ldloc.0
0xb197  dup
0xb198  brtrue.s loc_B1A6
0xb19a  pop
0xb19b  ldarg.1
0xb19c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth::get_OrganizationId()
0xb1a1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0xb1a6  ret
```
