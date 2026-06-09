# CCollection<IHCCommandCollection,CCommand>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800093f0`
- end: `0x180009404`
- name: `?QueryInterface@?$CCollection@UIHCCommandCollection@@VCCommand@@@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `SHLWAPI!__imp_QISearch` at `0x1800093fd`

## pseudocode

```c
HRESULT __fastcall CCollection<IHCCommandCollection,CCommand>::QueryInterface(void *a1, const IID *a2, void **a3)
{
  return QISearch(a1, (LPCQITAB)&`CCollection<IHCCommandCollection,CCommand>::QueryInterface'::`2'::qit, a2, a3);
}

```

## disassembly

```asm
0x1800093f0  mov     r9, r8
0x1800093f3  mov     r8, rdx
0x1800093f6  lea     rdx, ?qit@?1??QueryInterface@?$CCollection@UIHCCommandCollection@@VCCommand@@@@UEAAJAEBU_GUID@@PEAPEAX@Z@4QBUQITAB@@B; QITAB const near * const `CCollection<IHCCommandCollection,CCommand>::QueryInterface(_GUID const &,void * *)'::`2'::qit
0x1800093fd  jmp     cs:__imp_QISearch
```
