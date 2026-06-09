# CCommand::OnClicked(IUnknown *,HWND__ *)

- ea: `0x180009600`
- end: `0x180009609`
- name: `?OnClicked@CCommand@@UEAAJPEAUIUnknown@@PEAUHWND__@@@Z`
- size: `9`
- prototype: `__int64 __fastcall(CCommand *__hidden this, struct IUnknown *, HWND)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009650`

## pseudocode

```c
__int64 __fastcall CCommand::OnClicked(
        __int64 (__fastcall **this)(struct IUnknown *, HWND),
        struct IUnknown *a2,
        HWND a3)
{
  return CCommandImpl::_OnClicked(this - 4, a2, a3);
}

```

## disassembly

```asm
0x180009600  add     rcx, 0FFFFFFFFFFFFFFE0h; this
0x180009604  jmp     ?_OnClicked@CCommandImpl@@IEAAJPEAUIUnknown@@PEAUHWND__@@@Z; CCommandImpl::_OnClicked(IUnknown *,HWND__ *)
```
