# Microsoft.Crm.Sandbox.SandboxSdkClientCache`1::.cctor

- ea: `0x9ba0`
- end: `0x9bfb`
- name: `Microsoft.Crm.Sandbox.SandboxSdkClientCache`1::.cctor`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14d0`

## string_xrefs

- `0x9bc5`: `SandboxClientCache start`
- `0x9beb`: `SandboxClientCache.CleanupThread`

## pseudocode

```c

```

## disassembly

```asm
0x9ba0  newobj   instance void class Microsoft.Crm.Sandbox.SandboxSdkClientCache`1<var<u1>>::.ctor()
0x9ba5  stsfld   class Microsoft.Crm.Sandbox.SandboxSdkClientCache`1<var<u1>> class Microsoft.Crm.Sandbox.SandboxSdkClientCache`1<var<u1>>::_instance
0x9baa  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, var<u1>>::.ctor()
0x9baf  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, var<u1>> class Microsoft.Crm.Sandbox.SandboxSdkClientCache`1<var<u1>>::_clientDictionary
0x9bb4  newobj   instance void [System.Core]System.Threading.ReaderWriterLockSlim::.ctor()
0x9bb9  stsfld   class [System.Core]System.Threading.ReaderWriterLockSlim class Microsoft.Crm.Sandbox.SandboxSdkClientCache`1<var<u1>>::_clientLock
0x9bbe  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x9bc3  ldc.i4.s 0x26
0x9bc5  ldstr    aSandboxclientc// "SandboxClientCache start"
0x9bca  ldc.i4.0
0x9bcb  newarr   [mscorlib]System.Object
0x9bd0  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x9bd5  ldsfld   class Microsoft.Crm.Sandbox.SandboxSdkClientCache`1<var<u1>> class Microsoft.Crm.Sandbox.SandboxSdkClientCache`1<var<u1>>::_instance
0x9bda  ldftn    instance void class Microsoft.Crm.Sandbox.SandboxSdkClientCache`1<var<u1>>::CleanupThread()
0x9be0  newobj   instance void [mscorlib]System.Threading.ThreadStart::.ctor(object, native int)
0x9be5  newobj   instance void [mscorlib]System.Threading.Thread::.ctor(class [mscorlib]System.Threading.ThreadStart)
0x9bea  dup
0x9beb  ldstr    aSandboxclientc_0// "SandboxClientCache.CleanupThread"
0x9bf0  callvirt instance void [mscorlib]System.Threading.Thread::set_Name(string)
0x9bf5  callvirt instance void [mscorlib]System.Threading.Thread::Start()
0x9bfa  ret
```
