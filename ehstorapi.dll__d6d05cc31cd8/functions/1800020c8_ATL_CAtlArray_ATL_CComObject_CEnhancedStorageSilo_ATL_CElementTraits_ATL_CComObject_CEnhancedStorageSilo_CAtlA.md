# ATL::CAtlArray<ATL::CComObject<CEnhancedStorageSilo> *,ATL::CElementTraits<ATL::CComObject<CEnhancedStorageSilo> *>>::~CAtlArray<ATL::CComObject<CEnhancedStorageSilo> *,ATL::CElementTraits<ATL::CComObject<CEnhancedStorageSilo> *>>(void)

- ea: `0x1800020c8`
- end: `0x1800020df`
- name: `??1?$CAtlArray@PEAV?$CComObject@VCEnhancedStorageSilo@@@ATL@@V?$CElementTraits@PEAV?$CComObject@VCEnhancedStorageSilo@@@ATL@@@2@@ATL@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000215c`

## callees

- `0x1800020c8`

## import_xrefs

- `msvcrt!free` at `0x1800020d4`
- `msvcrt!free` at `0x1800020d4`

## pseudocode

```c
void __fastcall ATL::CAtlArray<ATL::CComObject<CEnhancedStorageSilo> *,ATL::CElementTraits<ATL::CComObject<CEnhancedStorageSilo> *>>::~CAtlArray<ATL::CComObject<CEnhancedStorageSilo> *,ATL::CElementTraits<ATL::CComObject<CEnhancedStorageSilo> *>>(
        void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    free(v1);
}

```

## disassembly

```asm
0x1800020c8  sub     rsp, 28h
0x1800020cc  mov     rcx, [rcx]; Block
0x1800020cf  test    rcx, rcx
0x1800020d2  jz      short loc_1800020DA
0x1800020d4  call    cs:__imp_free
0x1800020da  add     rsp, 28h
0x1800020de  retn
```
