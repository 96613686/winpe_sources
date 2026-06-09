# Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::CreateSequentialGuid

- ea: `0x149d0`
- end: `0x14a6c`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::CreateSequentialGuid`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x14990`

## callees

- `0x149d0`
- `0x152e0`
- `0x22f00`

## pseudocode

```c

```

## disassembly

```asm
0x149d0  ldc.i4.1
0x149d1  newobj   instance void [mscorlib]System.Security.PermissionSet::.ctor(valuetype [mscorlib]System.Security.Permissions.PermissionState)
0x149d6  callvirt instance void [mscorlib]System.Security.PermissionSet::Assert()
0x149db  ldsfld   class SequentialGuidOverrideDelegate Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::SequentialGuidOverride
0x149e0  brfalse.s loc_149F0
0x149e2  ldsfld   class SequentialGuidOverrideDelegate Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::SequentialGuidOverride
0x149e7  callvirt instance valuetype [mscorlib]System.Guid SequentialGuidOverrideDelegate::Invoke()
0x149ec  stloc.s  4
0x149ee  leave.s  loc_14A69
0x149f0  leave.s  loc_149F8
0x149f2  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0x149f7  endfinally
0x149f8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x149fd  stloc.0
0x149fe  ldc.i4.1
0x149ff  newobj   instance void [mscorlib]System.Security.PermissionSet::.ctor(valuetype [mscorlib]System.Security.Permissions.PermissionState)
0x14a04  call     instance void [mscorlib]System.Security.PermissionSet::Assert()
0x14a09  ldloca.s 0
0x14a0b  call     int64 Microsoft.Xrm.Sdk.Client.NativeMethods::UuidCreateSequential(valuetype [mscorlib]System.Guid& ptrGuid)
0x14a10  stloc.1
0x14a11  leave.s  loc_14A19
0x14a13  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0x14a18  endfinally
0x14a19  ldloc.1
0x14a1a  brfalse.s loc_14A22
0x14a1c  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x14a21  ret
0x14a22  ldloca.s 0
0x14a24  call     instance unsigned int8[] [mscorlib]System.Guid::ToByteArray()
0x14a29  stloc.2
0x14a2a  ldloc.2
0x14a2b  ldc.i4.2
0x14a2c  ldelem.u1
0x14a2d  stloc.3
0x14a2e  ldloc.2
0x14a2f  ldc.i4.2
0x14a30  ldloc.2
0x14a31  ldc.i4.1
0x14a32  ldelem.u1
0x14a33  stelem.i1
0x14a34  ldloc.2
0x14a35  ldc.i4.1
0x14a36  ldloc.3
0x14a37  stelem.i1
0x14a38  ldloc.2
0x14a39  ldc.i4.3
0x14a3a  ldelem.u1
0x14a3b  stloc.3
0x14a3c  ldloc.2
0x14a3d  ldc.i4.3
0x14a3e  ldloc.2
0x14a3f  ldc.i4.0
0x14a40  ldelem.u1
0x14a41  stelem.i1
0x14a42  ldloc.2
0x14a43  ldc.i4.0
0x14a44  ldloc.3
0x14a45  stelem.i1
0x14a46  ldloc.2
0x14a47  ldc.i4.4
0x14a48  ldelem.u1
0x14a49  stloc.3
0x14a4a  ldloc.2
0x14a4b  ldc.i4.4
0x14a4c  ldloc.2
0x14a4d  ldc.i4.5
0x14a4e  ldelem.u1
0x14a4f  stelem.i1
0x14a50  ldloc.2
0x14a51  ldc.i4.5
0x14a52  ldloc.3
0x14a53  stelem.i1
0x14a54  ldloc.2
0x14a55  ldc.i4.6
0x14a56  ldelem.u1
0x14a57  stloc.3
0x14a58  ldloc.2
0x14a59  ldc.i4.6
0x14a5a  ldloc.2
0x14a5b  ldc.i4.7
0x14a5c  ldelem.u1
0x14a5d  stelem.i1
0x14a5e  ldloc.2
0x14a5f  ldc.i4.7
0x14a60  ldloc.3
0x14a61  stelem.i1
0x14a62  ldloc.2
0x14a63  newobj   instance void [mscorlib]System.Guid::.ctor(unsigned int8[])
0x14a68  ret
0x14a69  ldloc.s  4
0x14a6b  ret
```
