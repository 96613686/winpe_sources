# Windows::Internal::ServiceModule::DecrementObjectCount(void)

- ea: `0x180005190`
- end: `0x180005199`
- name: `?DecrementObjectCount@ServiceModule@Internal@Windows@@UEAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(Windows::Internal::ServiceModule *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800051a0`

## callees

- `0x180005144`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ServiceModule::DecrementObjectCount(Windows::Internal::ServiceModule *this)
{
  return Microsoft::WRL::Module<2,Windows::Internal::ServiceModule>::DecrementObjectCount((__int64)this + 40);
}

```

## disassembly

```asm
0x180005190  add     rcx, 28h ; '('
0x180005194  jmp     ?DecrementObjectCount@?$Module@$01VServiceModule@Internal@Windows@@@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Module<2,Windows::Internal::ServiceModule>::DecrementObjectCount(void)
```
