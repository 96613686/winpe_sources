# [thunk]:XMLScrSite::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x1400118d0`
- end: `0x1400118d9`
- name: `?QueryInterface@XMLScrSite@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1400082f0`

## pseudocode

```c
__int64 __fastcall XMLScrSite::QueryInterface(__int64 a1, const struct _GUID *a2, XMLScrSite **a3)
{
  return XMLScrSite::QueryInterface((XMLScrSite *)(a1 - 8), a2, a3);
}

```

## disassembly

```asm
0x1400118d0  sub     rcx, 8; this
0x1400118d4  jmp     ?QueryInterface@XMLScrSite@@UEAAJAEBU_GUID@@PEAPEAX@Z; XMLScrSite::QueryInterface(_GUID const &,void * *)
```
