# CADMCOMW::CImpIConnectionPointContainer::QueryInterface(_GUID const &,void * *)

- ea: `0x18000c4a0`
- end: `0x18000c4af`
- name: `?QueryInterface@CImpIConnectionPointContainer@CADMCOMW@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `15`
- prototype: `__int64 __fastcall(CADMCOMW::CImpIConnectionPointContainer *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180010010`

## pseudocode

```c
__int64 __fastcall CADMCOMW::CImpIConnectionPointContainer::QueryInterface(
        CADMCOMW::CImpIConnectionPointContainer *this,
        const struct _GUID *a2,
        void **a3)
{
  return (***((__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))this + 2))(
           *((_QWORD *)this + 2),
           a2,
           a3);
}

```

## disassembly

```asm
0x18000c4a0  mov     rcx, [rcx+10h]
0x18000c4a4  mov     rax, [rcx]
0x18000c4a7  mov     rax, [rax]
0x18000c4aa  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
