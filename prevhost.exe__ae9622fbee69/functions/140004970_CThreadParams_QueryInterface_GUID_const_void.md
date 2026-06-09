# CThreadParams::QueryInterface(_GUID const &,void * *)

- ea: `0x140004970`
- end: `0x140004984`
- name: `?QueryInterface@CThreadParams@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `20`
- prototype: `__int64 __fastcall(CThreadParams *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `SHLWAPI!__imp_QISearch` at `0x14000497d`

## pseudocode

```c
HRESULT __fastcall CThreadParams::QueryInterface(CThreadParams *this, const struct _GUID *a2, void **a3)
{
  return QISearch(this, (LPCQITAB)&off_1400070C8, a2, a3);
}

```

## disassembly

```asm
0x140004970  mov     r9, r8
0x140004973  mov     r8, rdx
0x140004976  lea     rdx, off_1400070C8
0x14000497d  jmp     cs:__imp_QISearch
```
