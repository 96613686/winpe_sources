# ATL::CComContainedObject<CPnpxPairingHandler>::QueryInterface(_GUID const &,void * *)

- ea: `0x180007650`
- end: `0x18000765f`
- name: `?QueryInterface@?$CComContainedObject@VCPnpxPairingHandler@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `15`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007670`
- `0x180007680`

## callees

- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CPnpxPairingHandler>::QueryInterface(__int64 a1)
{
  return (***(__int64 (__fastcall ****)(_QWORD))(a1 + 24))(*(_QWORD *)(a1 + 24));
}

```

## disassembly

```asm
0x180007650  mov     rcx, [rcx+18h]
0x180007654  mov     rax, [rcx]
0x180007657  mov     rax, [rax]
0x18000765a  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
