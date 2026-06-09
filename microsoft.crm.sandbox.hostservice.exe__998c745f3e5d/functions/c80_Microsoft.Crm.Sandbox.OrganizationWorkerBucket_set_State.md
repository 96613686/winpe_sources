# Microsoft.Crm.Sandbox.OrganizationWorkerBucket::set_State

- ea: `0xc80`
- end: `0xd71`
- name: `Microsoft.Crm.Sandbox.OrganizationWorkerBucket::set_State`
- size: `241`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0xe70`
- `0x15b0`
- `0x17b0`
- `0x1870`

## callees

- `0xc80`
- `0xd80`
- `0xdd0`

## pseudocode

```c

```

## disassembly

```asm
0xc80  ldarg.0
0xc81  ldfld    valuetype Microsoft.Crm.Sandbox.BucketState Microsoft.Crm.Sandbox.OrganizationWorkerBucket::_state
0xc86  stloc.0
0xc87  ldarg.0
0xc88  ldarg.1
0xc89  stfld    valuetype Microsoft.Crm.Sandbox.BucketState Microsoft.Crm.Sandbox.OrganizationWorkerBucket::_state
0xc8e  ldarg.1
0xc8f  ldloc.0
0xc90  bne.un.s loc_C93
0xc92  ret
0xc93  nop
0xc94  ldarg.0
0xc95  ldloc.0
0xc96  call     instance void Microsoft.Crm.Sandbox.OrganizationWorkerBucket::DecrementStatus(valuetype Microsoft.Crm.Sandbox.BucketState state)
0xc9b  leave.s  loc_D00
0xc9d  stloc.1
0xc9e  ldloc.1
0xc9f  ldarg.0
0xca0  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerBucket::_organizationId
0xca5  ldc.i4.s 0x21
0xca7  ldstr    aErrorDecrement// "Error decrementing status. {0}"
0xcac  ldc.i4.1
0xcad  newarr   [mscorlib]System.Object
0xcb2  dup
0xcb3  ldc.i4.0
0xcb4  ldloc.1
0xcb5  callvirt instance string [mscorlib]System.Object::ToString()
0xcba  stelem.ref
0xcbb  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xcc0  ldarg.0
0xcc1  ldloc.0
0xcc2  stfld    valuetype Microsoft.Crm.Sandbox.BucketState Microsoft.Crm.Sandbox.OrganizationWorkerBucket::_state
0xcc7  ldarg.0
0xcc8  ldloc.0
0xcc9  call     instance void Microsoft.Crm.Sandbox.OrganizationWorkerBucket::IncrementStatus(valuetype Microsoft.Crm.Sandbox.BucketState state)
0xcce  leave.s  loc_CFE
0xcd0  stloc.2
0xcd1  ldloc.2
0xcd2  ldarg.0
0xcd3  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerBucket::_organizationId
0xcd8  ldc.i4.s 0x21
0xcda  ldstr    aErrorResetingS// "Error reseting status from decrement fa"...
0xcdf  ldc.i4.2
0xce0  newarr   [mscorlib]System.Object
0xce5  dup
0xce6  ldc.i4.0
0xce7  ldloc.2
0xce8  callvirt instance string [mscorlib]System.Object::ToString()
0xced  stelem.ref
0xcee  dup
0xcef  ldc.i4.1
0xcf0  ldloc.1
0xcf1  callvirt instance string [mscorlib]System.Object::ToString()
0xcf6  stelem.ref
0xcf7  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xcfc  rethrow
0xcfe  rethrow
0xd00  nop
0xd01  ldarg.0
0xd02  ldarg.1
0xd03  call     instance void Microsoft.Crm.Sandbox.OrganizationWorkerBucket::IncrementStatus(valuetype Microsoft.Crm.Sandbox.BucketState state)
0xd08  leave.s  loc_D70
0xd0a  stloc.3
0xd0b  ldloc.3
0xd0c  ldarg.0
0xd0d  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerBucket::_organizationId
0xd12  ldc.i4.s 0x21
0xd14  ldstr    aErrorIncrement// "Error incrementing status. {0}"
0xd19  ldc.i4.1
0xd1a  newarr   [mscorlib]System.Object
0xd1f  dup
0xd20  ldc.i4.0
0xd21  ldloc.3
0xd22  callvirt instance string [mscorlib]System.Object::ToString()
0xd27  stelem.ref
0xd28  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xd2d  ldarg.0
0xd2e  ldloc.0
0xd2f  stfld    valuetype Microsoft.Crm.Sandbox.BucketState Microsoft.Crm.Sandbox.OrganizationWorkerBucket::_state
0xd34  ldarg.0
0xd35  ldarg.1
0xd36  call     instance void Microsoft.Crm.Sandbox.OrganizationWorkerBucket::DecrementStatus(valuetype Microsoft.Crm.Sandbox.BucketState state)
0xd3b  leave.s  loc_D6E
0xd3d  stloc.s  4
0xd3f  ldloc.s  4
0xd41  ldarg.0
0xd42  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerBucket::_organizationId
0xd47  ldc.i4.s 0x21
0xd49  ldstr    aErrorResetingS_0// "Error reseting status from incrementfai"...
0xd4e  ldc.i4.2
0xd4f  newarr   [mscorlib]System.Object
0xd54  dup
0xd55  ldc.i4.0
0xd56  ldloc.s  4
0xd58  callvirt instance string [mscorlib]System.Object::ToString()
0xd5d  stelem.ref
0xd5e  dup
0xd5f  ldc.i4.1
0xd60  ldloc.3
0xd61  callvirt instance string [mscorlib]System.Object::ToString()
0xd66  stelem.ref
0xd67  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xd6c  rethrow
0xd6e  rethrow
0xd70  ret
```
