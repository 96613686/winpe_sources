# Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::DequeueLog

- ea: `0x900`
- end: `0x927`
- name: `Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::DequeueLog`
- size: `39`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x720`

## callees

- `0x900`

## pseudocode

```c

```

## disassembly

```asm
0x900  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x905  stloc.0
0x906  ldnull
0x907  stloc.1
0x908  br.s     loc_911
0x90a  ldloc.0
0x90b  ldloc.1
0x90c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x911  ldarg.0
0x912  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<string> Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_jobLog
0x917  ldloca.s 1
0x919  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<string>::TryDequeue(var<u1>&)
0x91e  brtrue.s loc_90A
0x920  ldloc.0
0x921  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0x926  ret
```
