# CreateCatalogInformation(ICatInformation * *)

- ea: `0x1007615e`
- end: `0x100761cc`
- name: `?CreateCatalogInformation@@YGJPAPAUICatInformation@@@Z`
- size: `110`
- prototype: `HRESULT __stdcall(ICatInformation **ppUnk)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x100e8473`
- `0x100e9b88`

## callees

- `0x1003fcda`
- `0x1003fd1f`
- `0x10040c44`
- `0x1007615e`
- `0x10076316`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x10076199`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x10076199`

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
0x1007615e  mov     edi, edi
0x10076160  push    ebp
0x10076161  mov     ebp, esp
0x10076163  push    ecx
0x10076164  push    esi
0x10076165  xor     esi, esi
0x10076167  cmp     ?g_pCatInfo@@3PAUICatInformation@@A, esi; ICatInformation * g_pCatInfo
0x1007616d  jnz     short loc_100761C7
0x1007616f  push    ?g_pMutexSR@@3PAVCSMutex@@A; pMutex
0x10076175  lea     ecx, [ebp+lock]; this
0x10076178  call    ??0MutexLock@@QAE@PAVMutex@@@Z; MutexLock::MutexLock(Mutex *)
0x1007617d  cmp     ?g_pCatInfo@@3PAUICatInformation@@A, esi; ICatInformation * g_pCatInfo
0x10076183  jnz     short loc_100761BF
0x10076185  push    edi
0x10076186  mov     edi, offset ?g_pCatInfo@@3PAUICatInformation@@A; ICatInformation * g_pCatInfo
0x1007618b  push    edi; ppv
0x1007618c  push    offset _IID_ICatInformation; riid
0x10076191  push    1; dwClsContext
0x10076193  push    esi; pUnkOuter
0x10076194  push    offset _CLSID_StdComponentCategoriesMgr; rclsid
0x10076199  call    ds:__imp__CoCreateInstance@20; CoCreateInstance(x,x,x,x,x)
0x1007619f  mov     esi, eax
0x100761a1  test    esi, esi
0x100761a3  js      short loc_100761BE
0x100761a5  mov     edx, offset aCatalog; "Catalog"
0x100761aa  mov     ecx, edi; ppUnk
0x100761ac  call    ?RegisterStaticUnknown@@YGJPAPAUIUnknown@@PBD@Z; RegisterStaticUnknown(IUnknown * *,char const *)
0x100761b1  mov     esi, eax
0x100761b3  test    esi, esi
0x100761b5  jns     short loc_100761BE
0x100761b7  mov     ecx, edi; ppref
0x100761b9  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x100761be  pop     edi
0x100761bf  lea     ecx, [ebp+lock]; this
0x100761c2  call    ?Release@MutexLock@@QAEXXZ; MutexLock::Release(void)
0x100761c7  mov     eax, esi
0x100761c9  pop     esi
0x100761ca  leave
0x100761cb  retn
```
