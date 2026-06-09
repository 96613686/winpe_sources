# CreateCatalogInformation(ICatInformation * *)

- ea: `0x1007618e`
- end: `0x100761fc`
- name: `?CreateCatalogInformation@@YGJPAPAUICatInformation@@@Z`
- size: `110`
- prototype: `HRESULT __stdcall(ICatInformation **ppUnk)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x100e8593`
- `0x100e9ca8`

## callees

- `0x1003fc4a`
- `0x1003fc8f`
- `0x10040bb4`
- `0x1007618e`
- `0x10076346`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x100761c9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x100761c9`

## pseudocode

```c
HRESULT __stdcall CreateCatalogInformation()
{
  HRESULT Instance; // esi
  MutexLock lock; // [esp+4h] [ebp-4h] BYREF

  Instance = 0;
  if ( !g_pCatInfo )
  {
    MutexLock::MutexLock(&lock, g_pMutexSR);
    if ( !g_pCatInfo )
    {
      Instance = CoCreateInstance(&CLSID_StdComponentCategoriesMgr, 0, 1u, &IID_ICatInformation, (LPVOID *)&g_pCatInfo);
      if ( Instance >= 0 )
      {
        Instance = RegisterStaticUnknown(&g_pCatInfo, "Catalog");
        if ( Instance < 0 )
          release(&g_pCatInfo);
      }
    }
    MutexLock::Release(&lock);
  }
  return Instance;
}

```

## disassembly

```asm
0x1007618e  mov     edi, edi
0x10076190  push    ebp
0x10076191  mov     ebp, esp
0x10076193  push    ecx
0x10076194  push    esi
0x10076195  xor     esi, esi
0x10076197  cmp     ?g_pCatInfo@@3PAUICatInformation@@A, esi; ICatInformation * g_pCatInfo
0x1007619d  jnz     short loc_100761F7
0x1007619f  push    ?g_pMutexSR@@3PAVCSMutex@@A; pMutex
0x100761a5  lea     ecx, [ebp+lock]; this
0x100761a8  call    ??0MutexLock@@QAE@PAVMutex@@@Z; MutexLock::MutexLock(Mutex *)
0x100761ad  cmp     ?g_pCatInfo@@3PAUICatInformation@@A, esi; ICatInformation * g_pCatInfo
0x100761b3  jnz     short loc_100761EF
0x100761b5  push    edi
0x100761b6  mov     edi, offset ?g_pCatInfo@@3PAUICatInformation@@A; ICatInformation * g_pCatInfo
0x100761bb  push    edi; ppv
0x100761bc  push    offset _IID_ICatInformation; riid
0x100761c1  push    1; dwClsContext
0x100761c3  push    esi; pUnkOuter
0x100761c4  push    offset _CLSID_StdComponentCategoriesMgr; rclsid
0x100761c9  call    ds:__imp__CoCreateInstance@20; CoCreateInstance(x,x,x,x,x)
0x100761cf  mov     esi, eax
0x100761d1  test    esi, esi
0x100761d3  js      short loc_100761EE
0x100761d5  mov     edx, offset aCatalog; "Catalog"
0x100761da  mov     ecx, edi; ppUnk
0x100761dc  call    ?RegisterStaticUnknown@@YGJPAPAUIUnknown@@PBD@Z; RegisterStaticUnknown(IUnknown * *,char const *)
0x100761e1  mov     esi, eax
0x100761e3  test    esi, esi
0x100761e5  jns     short loc_100761EE
0x100761e7  mov     ecx, edi; ppref
0x100761e9  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x100761ee  pop     edi
0x100761ef  lea     ecx, [ebp+lock]; this
0x100761f2  call    ?Release@MutexLock@@QAEXXZ; MutexLock::Release(void)
0x100761f7  mov     eax, esi
0x100761f9  pop     esi
0x100761fa  leave
0x100761fb  retn
```
