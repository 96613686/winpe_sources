# Microsoft.Crm.Sandbox.SandboxWorkerMain::.cctor

- ea: `0x4840`
- end: `0x48c0`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerMain::.cctor`
- size: `128`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x4889`: `Microsoft.IdentityModel.Clients.ActiveDirectory`

## pseudocode

```c

```

## disassembly

```asm
0x4840  ldc.i4.7
0x4841  newarr   [mscorlib]System.String
0x4846  dup
0x4847  ldc.i4.0
0x4848  ldstr    aSuccess// "Success"
0x484d  stelem.ref
0x484e  dup
0x484f  ldc.i4.1
0x4850  ldstr    aIncorrectNumbe_0// "Incorrect Number Of Arguments"
0x4855  stelem.ref
0x4856  dup
0x4857  ldc.i4.2
0x4858  ldstr    aIncorrectArgum// "Incorrect Argument Format"
0x485d  stelem.ref
0x485e  dup
0x485f  ldc.i4.3
0x4860  ldstr    aNoParentProces// "No Parent Process"
0x4865  stelem.ref
0x4866  dup
0x4867  ldc.i4.4
0x4868  ldstr    aListenerStartF// "Listener Start Failed"
0x486d  stelem.ref
0x486e  dup
0x486f  ldc.i4.5
0x4870  ldstr    aUnexpectedExce_0// "Unexpected Exception"
0x4875  stelem.ref
0x4876  dup
0x4877  ldc.i4.6
0x4878  ldstr    aBadFormatGuid// "Bad Format Guid"
0x487d  stelem.ref
0x487e  stsfld   string[] Microsoft.Crm.Sandbox.SandboxWorkerMain::_exitReason
0x4883  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Version>::.ctor()
0x4888  dup
0x4889  ldstr    aMicrosoftIdent// "Microsoft.IdentityModel.Clients.ActiveD"...
0x488e  ldc.i4.2
0x488f  ldc.i4.s 0x15
0x4891  ldc.i4.0
0x4892  ldc.i4.0
0x4893  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32, int32, int32)
0x4898  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Version>::Add(var<u1>, !!T0)
0x489d  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Version> Microsoft.Crm.Sandbox.SandboxWorkerMain::_assemblyRedirects
0x48a2  ldc.i4.0
0x48a3  stsfld   bool Microsoft.Crm.Sandbox.SandboxWorkerMain::_drawbridgeEnabled
0x48a8  ldc.i4.0
0x48a9  stsfld   bool Microsoft.Crm.Sandbox.SandboxWorkerMain::_shutdownForMissingAssembly
0x48ae  ldc.i4.0
0x48af  stsfld   bool Microsoft.Crm.Sandbox.SandboxWorkerMain::_shutdownForCrash
0x48b4  ldc.i4.0
0x48b5  newobj   instance void [mscorlib]System.Threading.AutoResetEvent::.ctor(bool)
0x48ba  stsfld   class [mscorlib]System.Threading.AutoResetEvent Microsoft.Crm.Sandbox.SandboxWorkerMain::_mainThreadSync
0x48bf  ret
```
