# CADMCOMW::CImpExpHelp::QueryInterface(_GUID const &,void * *)

- ea: `0x18000e940`
- end: `0x18000e94f`
- name: `?QueryInterface@CImpExpHelp@CADMCOMW@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `15`
- prototype: `__int64 __fastcall(CADMCOMW::CImpExpHelp *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180010010`

## pseudocode

```c
__int64 __fastcall CADMCOMW::CImpExpHelp::QueryInterface(
        CADMCOMW::CImpExpHelp *this,
        const struct _GUID *a2,
        void **a3)
{
  return (***((__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))this + 1))(
           *((_QWORD *)this + 1),
           a2,
           a3);
}

```

## disassembly

```asm
0x18000e940  mov     rcx, [rcx+8]
0x18000e944  mov     rax, [rcx]
0x18000e947  mov     rax, [rax]
0x18000e94a  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
