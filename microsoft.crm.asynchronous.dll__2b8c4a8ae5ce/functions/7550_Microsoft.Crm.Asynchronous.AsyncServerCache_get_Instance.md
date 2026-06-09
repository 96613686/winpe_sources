# Microsoft.Crm.Asynchronous.AsyncServerCache::get_Instance

- ea: `0x7550`
- end: `0x758a`
- name: `Microsoft.Crm.Asynchronous.AsyncServerCache::get_Instance`
- size: `58`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xf300`
- `0xf410`

## callees

- `0x7550`
- `0x7610`

## pseudocode

```c

```

## disassembly

```asm
0x7550  ldsfld   class Microsoft.Crm.Asynchronous.AsyncServerCache Microsoft.Crm.Asynchronous.AsyncServerCache::_instance
0x7555  brtrue.s loc_7584
0x7557  ldsfld   object Microsoft.Crm.Asynchronous.AsyncServerCache::_lock
0x755c  stloc.0
0x755d  ldc.i4.0
0x755e  stloc.1
0x755f  ldloc.0
0x7560  ldloca.s 1
0x7562  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x7567  ldsfld   class Microsoft.Crm.Asynchronous.AsyncServerCache Microsoft.Crm.Asynchronous.AsyncServerCache::_instance
0x756c  brtrue.s loc_7578
0x756e  newobj   instance void Microsoft.Crm.Asynchronous.AsyncServerCache::.ctor()
0x7573  stsfld   class Microsoft.Crm.Asynchronous.AsyncServerCache Microsoft.Crm.Asynchronous.AsyncServerCache::_instance
0x7578  leave.s  loc_7584
0x757a  ldloc.1
0x757b  brfalse.s loc_7583
0x757d  ldloc.0
0x757e  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x7583  endfinally
0x7584  ldsfld   class Microsoft.Crm.Asynchronous.AsyncServerCache Microsoft.Crm.Asynchronous.AsyncServerCache::_instance
0x7589  ret
```
