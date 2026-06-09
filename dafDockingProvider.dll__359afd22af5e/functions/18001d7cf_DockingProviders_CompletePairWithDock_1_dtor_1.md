# _DockingProviders::CompletePairWithDock_::_1_::dtor$1

- ea: `0x18001d7cf`
- end: `0x18001d7db`
- name: `_DockingProviders::CompletePairWithDock_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000871c`

## pseudocode

```c
void __fastcall DockingProviders::CompletePairWithDock_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  std::unique_ptr<ProviderIndexAndPairingID>::~unique_ptr<ProviderIndexAndPairingID>((void **)(a2 + 128));
}

```

## disassembly

```asm
0x18001d7cf  lea     rcx, [rdx+80h]
0x18001d7d6  jmp     ??1?$unique_ptr@UProviderIndexAndPairingID@@U?$default_delete@UProviderIndexAndPairingID@@@std@@@std@@QEAA@XZ; std::unique_ptr<ProviderIndexAndPairingID>::~unique_ptr<ProviderIndexAndPairingID>(void)
```
