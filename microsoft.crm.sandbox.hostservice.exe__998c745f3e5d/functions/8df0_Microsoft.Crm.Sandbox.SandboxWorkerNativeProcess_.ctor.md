# Microsoft.Crm.Sandbox.SandboxWorkerNativeProcess::.ctor

- ea: `0x8df0`
- end: `0x8e37`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerNativeProcess::.ctor`
- size: `71`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x7e30`

## callees

- `0x9640`

## string_xrefs

- `0x8df9`: `CRM_Server_InstallDir`

## pseudocode

```c

```

## disassembly

```asm
0x8df0  ldarg.0
0x8df1  ldarg.1
0x8df2  ldarg.2
0x8df3  call     instance void Microsoft.Crm.Sandbox.SandboxWorkerProcess::.ctor(int32 port, class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<int32> portsQueue)
0x8df8  ldarg.0
0x8df9  ldstr    aCrmServerInsta// "CRM_Server_InstallDir"
0x8dfe  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string)
0x8e03  castclass [mscorlib]System.String
0x8e08  ldstr    aServerBin// "Server\\bin"
0x8e0d  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x8e12  ldstr    aMicrosoftCrmSa_2// "Microsoft.Crm.Sandbox.WorkerProcess.exe"
0x8e17  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x8e1c  stfld    string Microsoft.Crm.Sandbox.SandboxWorkerNativeProcess::_filePath
0x8e21  ldarg.0
0x8e22  ldc.i4.0
0x8e23  stfld    bool Microsoft.Crm.Sandbox.SandboxWorkerProcess::IsDrawbridgeProcess
0x8e28  ldarg.0
0x8e29  ldc.i4.s 0x16
0x8e2b  ldc.i4.0
0x8e2c  call     T0x2B000001
0x8e31  stfld    int32 Microsoft.Crm.Sandbox.SandboxWorkerNativeProcess::enableWorkerProcessAccountIsolation
0x8e36  ret
```
