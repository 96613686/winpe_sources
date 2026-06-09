# Microsoft.Crm.Sandbox.SandboxMarshalByRefObject::GetDefaultLeaseTime

- ea: `0x2340`
- end: `0x2373`
- name: `Microsoft.Crm.Sandbox.SandboxMarshalByRefObject::GetDefaultLeaseTime`
- size: `51`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x3e0`
- `0x810`
- `0xb50`
- `0x2310`
- `0x4930`

## callees

- `0x2340`
- `0x39f0`

## pseudocode

```c

```

## disassembly

```asm
0x2340  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerConfiguration Microsoft.Crm.Sandbox.SandboxWorker::get_WorkerConfiguration()
0x2345  ldc.i4.4
0x2346  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerConfiguration::get_Item(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerProperty)
0x234b  stloc.0
0x234c  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerConfiguration Microsoft.Crm.Sandbox.SandboxWorker::get_WorkerConfiguration()
0x2351  ldc.i4.4
0x2352  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerConfiguration::get_Item(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerProperty)
0x2357  stloc.1
0x2358  ldloc.0
0x2359  ldc.i4.0
0x235a  bgt.s    loc_2364
0x235c  ldsfld   int32[] [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPropertyDefaultValues::SandboxWorkerPropertyDefaults
0x2361  ldc.i4.4
0x2362  ldelem.i4
0x2363  pop
0x2364  ldc.i4.s 0xA
0x2366  ldc.i4.0
0x2367  call     T0x2B000009
0x236c  ldc.i4.0
0x236d  ble.s    loc_2371
0x236f  ldc.i4.0
0x2370  stloc.1
0x2371  ldloc.1
0x2372  ret
```
