# ATL::CComContainedObject<CCtTuner>::QueryInterface(_GUID const &,void * *)

- ea: `0x140003dd0`
- end: `0x140003ddf`
- name: `?QueryInterface@?$CComContainedObject@VCCtTuner@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `15`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140007010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CCtTuner>::QueryInterface(__int64 a1)
{
  return (***(__int64 (__fastcall ****)(_QWORD))(a1 + 8))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x140003dd0  mov     rcx, [rcx+8]
0x140003dd4  mov     rax, [rcx]
0x140003dd7  mov     rax, [rax]
0x140003dda  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
