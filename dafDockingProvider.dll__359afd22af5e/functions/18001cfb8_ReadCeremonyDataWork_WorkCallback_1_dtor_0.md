# _ReadCeremonyDataWork::WorkCallback_::_1_::dtor$0

- ea: `0x18001cfb8`
- end: `0x18001cfc4`
- name: `_ReadCeremonyDataWork::WorkCallback_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000871c`

## pseudocode

```c
void __fastcall ReadCeremonyDataWork::WorkCallback_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  std::unique_ptr<ProviderIndexAndPairingID>::~unique_ptr<ProviderIndexAndPairingID>((void **)(a2 + 104));
}

```

## disassembly

```asm
0x18001cfb8  lea     rcx, [rdx+68h]
0x18001cfbf  jmp     ??1?$unique_ptr@UProviderIndexAndPairingID@@U?$default_delete@UProviderIndexAndPairingID@@@std@@@std@@QEAA@XZ; std::unique_ptr<ProviderIndexAndPairingID>::~unique_ptr<ProviderIndexAndPairingID>(void)
```
