# ATL::CComCoClass<CIisRestart,&_GUID const CLSID_IisServiceControl>::GetCategoryMap(void)

- ea: `0x140001e70`
- end: `0x140001e73`
- name: `?GetCategoryMap@?$CComCoClass@VCIisRestart@@$1?CLSID_IisServiceControl@@3U_GUID@@B@ATL@@SAPEBU_ATL_CATMAP_ENTRY@2@XZ`
- size: `3`
- prototype: `int __cdecl(struct _exception *)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140001070`

## pseudocode

```c
__int64 __fastcall ATL::CComCoClass<CIisRestart,&_GUID const CLSID_IisServiceControl>::GetCategoryMap(
        struct _exception *a1)
{
  return 0;
}

```

## disassembly

```asm
0x140001e70  xor     eax, eax
0x140001e72  retn
```
