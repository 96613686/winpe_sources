# CWnd::OnCommand(unsigned __int64,__int64)

- ea: `0x1800096f0`
- end: `0x1800096f6`
- name: `?OnCommand@CWnd@@MEAAH_K_J@Z_0`
- size: `6`
- prototype: `int(CWnd *__hidden this, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `MFC42u!__imp_?OnCommand@CWnd@@MEAAH_K_J@Z` at `0x1800096f0`

## pseudocode

```c
// attributes: thunk
int __fastcall CWnd::OnCommand(CWnd *this, unsigned __int64 a2, __int64 a3)
{
  return __imp_?OnCommand@CWnd@@MEAAH_K_J@Z(this, a2, a3);
}

```

## disassembly

```asm
0x1800096f0  jmp     cs:__imp_?OnCommand@CWnd@@MEAAH_K_J@Z
```
