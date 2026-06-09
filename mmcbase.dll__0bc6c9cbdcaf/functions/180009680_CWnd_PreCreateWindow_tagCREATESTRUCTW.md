# CWnd::PreCreateWindow(tagCREATESTRUCTW &)

- ea: `0x180009680`
- end: `0x180009686`
- name: `?PreCreateWindow@CWnd@@UEAAHAEAUtagCREATESTRUCTW@@@Z_0`
- size: `6`
- prototype: `int(CWnd *__hidden this, struct tagCREATESTRUCTW *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `MFC42u!__imp_?PreCreateWindow@CWnd@@UEAAHAEAUtagCREATESTRUCTW@@@Z` at `0x180009680`

## pseudocode

```c
// attributes: thunk
int __fastcall CWnd::PreCreateWindow(CWnd *this, struct tagCREATESTRUCTW *a2)
{
  return __imp_?PreCreateWindow@CWnd@@UEAAHAEAUtagCREATESTRUCTW@@@Z(this, a2);
}

```

## disassembly

```asm
0x180009680  jmp     cs:__imp_?PreCreateWindow@CWnd@@UEAAHAEAUtagCREATESTRUCTW@@@Z
```
