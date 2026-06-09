# Microsoft.Crm.Sandbox.SandboxMarshalByRefObject::InitializeLifetimeService

- ea: `0x2380`
- end: `0x23f4`
- name: `Microsoft.Crm.Sandbox.SandboxMarshalByRefObject::InitializeLifetimeService`
- size: `116`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x2380`

## pseudocode

```c

```

## disassembly

```asm
0x2380  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2385  ldc.i4.s 0x28
0x2387  ldarg.0
0x2388  ldftn    instance string Microsoft.Crm.Sandbox.SandboxMarshalByRefObject::<InitializeLifetimeService>b__3_0()
0x238e  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0x2393  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, class [mscorlib]System.Func`1<string>)
0x2398  ldarg.0
0x2399  ldfld    int32 Microsoft.Crm.Sandbox.SandboxMarshalByRefObject::leaseTime
0x239e  brtrue.s loc_23A2
0x23a0  ldnull
0x23a1  ret
0x23a2  ldarg.0
0x23a3  call     instance object [mscorlib]System.MarshalByRefObject::InitializeLifetimeService()
0x23a8  castclass [mscorlib]System.Runtime.Remoting.Lifetime.ILease
0x23ad  stloc.0
0x23ae  ldc.i4.1
0x23af  ldloc.0
0x23b0  callvirt instance valuetype [mscorlib]System.Runtime.Remoting.Lifetime.LeaseState [mscorlib]System.Runtime.Remoting.Lifetime.ILease::get_CurrentState()
0x23b5  bne.un.s loc_23F2
0x23b7  ldc.i4.1
0x23b8  newobj   instance void [mscorlib]System.Security.Permissions.SecurityPermission::.ctor(valuetype [mscorlib]System.Security.Permissions.PermissionState)
0x23bd  call     instance void [mscorlib]System.Security.CodeAccessPermission::Assert()
0x23c2  ldloc.0
0x23c3  ldarg.0
0x23c4  ldfld    int32 Microsoft.Crm.Sandbox.SandboxMarshalByRefObject::leaseTime
0x23c9  conv.r8
0x23ca  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0x23cf  callvirt instance void [mscorlib]System.Runtime.Remoting.Lifetime.ILease::set_InitialLeaseTime(valuetype [mscorlib]System.TimeSpan)
0x23d4  ldloc.0
0x23d5  ldsfld   valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::Zero
0x23da  callvirt instance void [mscorlib]System.Runtime.Remoting.Lifetime.ILease::set_RenewOnCallTime(valuetype [mscorlib]System.TimeSpan)
0x23df  ldloc.0
0x23e0  ldsfld   valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::Zero
0x23e5  callvirt instance void [mscorlib]System.Runtime.Remoting.Lifetime.ILease::set_SponsorshipTimeout(valuetype [mscorlib]System.TimeSpan)
0x23ea  leave.s  loc_23F2
0x23ec  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0x23f1  endfinally
0x23f2  ldloc.0
0x23f3  ret
```
