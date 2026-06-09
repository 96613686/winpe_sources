# ATL::CComContainedObject<CGameStatisticsMgr>::QueryInterface(_GUID const &,void * *)

- ea: `0x180002ae0`
- end: `0x180002aef`
- name: `?QueryInterface@?$CComContainedObject@VCGameStatisticsMgr@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `15`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CGameStatisticsMgr>::QueryInterface(__int64 a1)
{
  return (***(__int64 (__fastcall ****)(_QWORD))(a1 + 8))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180002ae0  mov     rcx, [rcx+8]
0x180002ae4  mov     rax, [rcx]
0x180002ae7  mov     rax, [rax]
0x180002aea  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
