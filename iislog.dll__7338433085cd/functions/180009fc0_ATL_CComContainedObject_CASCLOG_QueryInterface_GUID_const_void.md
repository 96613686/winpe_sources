# ATL::CComContainedObject<CASCLOG>::QueryInterface(_GUID const &,void * *)

- ea: `0x180009fc0`
- end: `0x180009fcf`
- name: `?QueryInterface@?$CComContainedObject@VCASCLOG@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `15`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180009fe0`

## callees

- `0x180010010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CASCLOG>::QueryInterface(__int64 a1)
{
  return (***(__int64 (__fastcall ****)(_QWORD))(a1 + 8))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180009fc0  mov     rcx, [rcx+8]
0x180009fc4  mov     rax, [rcx]
0x180009fc7  mov     rax, [rax]
0x180009fca  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
