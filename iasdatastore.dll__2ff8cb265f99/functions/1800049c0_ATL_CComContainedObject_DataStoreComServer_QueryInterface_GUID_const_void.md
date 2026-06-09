# ATL::CComContainedObject<DataStoreComServer>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800049c0`
- end: `0x1800049d9`
- name: `?QueryInterface@?$CComContainedObject@VDataStoreComServer@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180010010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<DataStoreComServer>::QueryInterface(__int64 a1)
{
  return (***(__int64 (__fastcall ****)(_QWORD))(a1 + 8))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x1800049c0  sub     rsp, 28h
0x1800049c4  mov     rcx, [rcx+8]
0x1800049c8  mov     rax, [rcx]
0x1800049cb  mov     rax, [rax]
0x1800049ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049d3  nop
0x1800049d4  add     rsp, 28h
0x1800049d8  retn
```
