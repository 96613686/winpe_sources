# Microsoft::WRL::Module<1,Windows::Internal::ServiceModule>::DecrementObjectCount(void)

- ea: `0x180005130`
- end: `0x18000513e`
- name: `?DecrementObjectCount@?$Module@$00VServiceModule@Internal@Windows@@@WRL@Microsoft@@UEAAKXZ`
- size: `14`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c
__int64 Microsoft::WRL::Module<1,Windows::Internal::ServiceModule>::DecrementObjectCount()
{
  return (unsigned int)_InterlockedDecrement((volatile signed __int32 *)&Microsoft::WRL::Details::ModuleBase::objectCount_);
}

```

## disassembly

```asm
0x180005130  or      eax, 0FFFFFFFFh
0x180005133  lock xadd cs:?objectCount_@ModuleBase@Details@WRL@Microsoft@@1KC, eax; ulong volatile Microsoft::WRL::Details::ModuleBase::objectCount_
0x18000513b  dec     eax
0x18000513d  retn
```
