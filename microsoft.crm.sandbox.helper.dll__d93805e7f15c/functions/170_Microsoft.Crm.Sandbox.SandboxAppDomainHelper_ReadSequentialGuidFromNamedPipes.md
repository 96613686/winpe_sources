# Microsoft.Crm.Sandbox.SandboxAppDomainHelper::ReadSequentialGuidFromNamedPipes

- ea: `0x170`
- end: `0x1b2`
- name: `Microsoft.Crm.Sandbox.SandboxAppDomainHelper::ReadSequentialGuidFromNamedPipes`
- size: `66`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1c0`

## callees

- `0x170`

## pseudocode

```c

```

## disassembly

```asm
0x170  ldstr    asc_318C// "."
0x175  ldstr    aMscrmsandboxse// "mscrmsandboxsequentialguid"
0x17a  ldc.i4.1
0x17b  ldc.i4.0
0x17c  ldc.i4.3
0x17d  newobj   instance void [System.Core]System.IO.Pipes.NamedPipeClientStream::.ctor(string, string, valuetype [System.Core]System.IO.Pipes.PipeDirection, valuetype [System.Core]System.IO.Pipes.PipeOptions, valuetype [mscorlib]System.Security.Principal.TokenImpersonationLevel)
0x182  stloc.0
0x183  ldloc.0
0x184  callvirt instance void [System.Core]System.IO.Pipes.NamedPipeClientStream::Connect()
0x189  ldc.i4.s 0x10
0x18b  newarr   [mscorlib]System.Byte
0x190  stloc.1
0x191  ldloc.0
0x192  ldloc.1
0x193  ldc.i4.0
0x194  ldloc.1
0x195  ldlen
0x196  conv.i4
0x197  callvirt instance int32 [mscorlib]System.IO.Stream::Read(unsigned int8[], int32, int32)
0x19c  pop
0x19d  ldloc.1
0x19e  newobj   instance void [mscorlib]System.Guid::.ctor(unsigned int8[])
0x1a3  stloc.2
0x1a4  leave.s  loc_1B0
0x1a6  ldloc.0
0x1a7  brfalse.s loc_1AF
0x1a9  ldloc.0
0x1aa  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1af  endfinally
0x1b0  ldloc.2
0x1b1  ret
```
