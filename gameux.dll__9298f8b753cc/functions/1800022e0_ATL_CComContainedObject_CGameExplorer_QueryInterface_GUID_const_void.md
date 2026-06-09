# ATL::CComContainedObject<CGameExplorer>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800022e0`
- end: `0x1800022ef`
- name: `?QueryInterface@?$CComContainedObject@VCGameExplorer@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `15`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002300`

## callees

- `0x180004010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CGameExplorer>::QueryInterface(__int64 a1)
{
  return (***(__int64 (__fastcall ****)(_QWORD))(a1 + 16))(*(_QWORD *)(a1 + 16));
}

```

## disassembly

```asm
0x1800022e0  mov     rcx, [rcx+10h]
0x1800022e4  mov     rax, [rcx]
0x1800022e7  mov     rax, [rax]
0x1800022ea  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
