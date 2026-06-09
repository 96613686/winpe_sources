# Microsoft::WRL::Module<2,HgServiceModule>::~Module<2,HgServiceModule>(void)

- ea: `0x180009558`
- end: `0x18000955d`
- name: `??1?$Module@$01VHgServiceModule@@@WRL@Microsoft@@UEAA@XZ`
- size: `5`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001586e`

## callees

- `0x180009564`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall Microsoft::WRL::Module<2,HgServiceModule>::~Module<2,HgServiceModule>(Microsoft::WRL::Details *a1)
{
  return Microsoft::WRL::Details::OutOfProcModuleBase<HgServiceModule>::~OutOfProcModuleBase<HgServiceModule>(a1);
}

```

## disassembly

```asm
0x180009558  jmp     ??1?$OutOfProcModuleBase@VHgServiceModule@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::OutOfProcModuleBase<HgServiceModule>::~OutOfProcModuleBase<HgServiceModule>(void)
```
