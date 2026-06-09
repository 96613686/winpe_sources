# Microsoft.Crm.Setup.Common.CA.DismWrapper::DismResults

- ea: `0x17580`
- end: `0x175d4`
- name: `Microsoft.Crm.Setup.Common.CA.DismWrapper::DismResults`
- size: `84`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x17180`
- `0x171b0`
- `0x17210`
- `0x17300`
- `0x17360`

## callees

- `0x17580`
- `0x17720`

## string_xrefs

- `0x175b5`: `You cannot service a running 64-bit operating system with a 32-bit version of DISM. Please use the version of DISM that corresponds to your computer's architecture.`
- `0x175c0`: `Elevated permissions are required to run this DISM command and complete its tasks.`

## pseudocode

```c

```

## disassembly

```asm
0x17580  ldarg.2
0x17581  stloc.0
0x17582  ldloc.0
0x17583  ldc.i4.0
0x17584  bgt.s    loc_17593
0x17586  ldloc.0
0x17587  ldc.i4   0x800F080C
0x1758c  beq.s    loc_175AA
0x1758e  ldloc.0
0x1758f  brfalse.s loc_175D2
0x17591  br.s     loc_175CB
0x17593  ldloc.0
0x17594  ldc.i4.s 0xB
0x17596  beq.s    loc_175B5
0x17598  ldloc.0
0x17599  ldc.i4   0x2E4
0x1759e  beq.s    loc_175C0
0x175a0  ldloc.0
0x175a1  ldc.i4   0xBC2
0x175a6  beq.s    loc_175D2
0x175a8  br.s     loc_175CB
0x175aa  ldstr    aFeatureDoesNot// "Feature does not exist"
0x175af  newobj   instance void Microsoft.Crm.Setup.Common.CA.DismException::.ctor(string message)
0x175b4  throw
0x175b5  ldstr    aYouCannotServi// "You cannot service a running 64-bit ope"...
0x175ba  newobj   instance void Microsoft.Crm.Setup.Common.CA.DismException::.ctor(string message)
0x175bf  throw
0x175c0  ldstr    aElevatedPermis// "Elevated permissions are required to ru"...
0x175c5  newobj   instance void Microsoft.Crm.Setup.Common.CA.DismException::.ctor(string message)
0x175ca  throw
0x175cb  ldarg.1
0x175cc  newobj   instance void Microsoft.Crm.Setup.Common.CA.DismException::.ctor(string message)
0x175d1  throw
0x175d2  ldloc.0
0x175d3  ret
```
