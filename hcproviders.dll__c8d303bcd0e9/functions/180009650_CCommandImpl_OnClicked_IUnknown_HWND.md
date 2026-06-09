# CCommandImpl::_OnClicked(IUnknown *,HWND__ *)

- ea: `0x180009650`
- end: `0x180009662`
- name: `?_OnClicked@CCommandImpl@@IEAAJPEAUIUnknown@@PEAUHWND__@@@Z`
- size: `18`
- prototype: `__int64 __fastcall(CCommandImpl *__hidden this, struct IUnknown *, HWND)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180009600`
- `0x180009700`

## callees

- `0x18000b010`

## pseudocode

```c
__int64 __fastcall CCommandImpl::_OnClicked(
        __int64 (__fastcall **this)(struct IUnknown *, HWND),
        struct IUnknown *a2,
        HWND a3)
{
  return this[2](a2, a3);
}

```

## disassembly

```asm
0x180009650  mov     rax, [rcx+10h]
0x180009654  mov     r9, rdx
0x180009657  mov     rcx, r9
0x18000965a  mov     rdx, r8
0x18000965d  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
