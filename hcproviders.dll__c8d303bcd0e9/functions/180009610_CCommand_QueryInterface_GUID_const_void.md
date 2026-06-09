# CCommand::QueryInterface(_GUID const &,void * *)

- ea: `0x180009610`
- end: `0x180009628`
- name: `?QueryInterface@CCommand@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `24`
- prototype: `__int64 __fastcall(CCommand *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `SHLWAPI!__imp_QISearch` at `0x180009621`

## pseudocode

```c
HRESULT __fastcall CCommand::QueryInterface(CCommand *this, const struct _GUID *a2, void **a3)
{
  return QISearch((char *)this - 32, (LPCQITAB)&off_18000CA90, a2, a3);
}

```

## disassembly

```asm
0x180009610  mov     r9, r8
0x180009613  add     rcx, 0FFFFFFFFFFFFFFE0h
0x180009617  mov     r8, rdx
0x18000961a  lea     rdx, off_18000CA90
0x180009621  jmp     cs:__imp_QISearch
```
