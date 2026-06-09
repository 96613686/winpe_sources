# FreeGlobalVars(int)

- ea: `0x18002b3f4`
- end: `0x18002b655`
- name: `?FreeGlobalVars@@YAXH@Z`
- size: `609`
- prototype: `void __fastcall(int)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800212e0`
- `0x18002b660`

## callees

- `0x180002098`
- `0x18001edc0`
- `0x180020dac`
- `0x18002b3f4`
- `0x1800986a4`
- `0x1800996b4`
- `0x180099d2c`
- `0x18009d458`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!FInitializeRichEdit` at `0x18002b402`
- `MSOERT2!FInitializeRichEdit` at `0x18002b402`
- `KERNEL32!DeleteCriticalSection` at `0x18002b4d5`
- `KERNEL32!DeleteCriticalSection` at `0x18002b615`
- `KERNEL32!DeleteCriticalSection` at `0x18002b622`
- `KERNEL32!DeleteCriticalSection` at `0x18002b62f`
- `KERNEL32!DeleteCriticalSection` at `0x18002b63c`
- `KERNEL32!DeleteCriticalSection` at `0x18002b4d5`
- `KERNEL32!DeleteCriticalSection` at `0x18002b615`
- `KERNEL32!DeleteCriticalSection` at `0x18002b622`
- `KERNEL32!DeleteCriticalSection` at `0x18002b62f`
- `KERNEL32!DeleteCriticalSection` at `0x18002b63c`
- `KERNEL32!DeleteCriticalSection` at `0x18002b64e`
- `KERNEL32!FreeLibrary` at `0x18002b461`
- `KERNEL32!FreeLibrary` at `0x18002b4f4`
- `KERNEL32!FreeLibrary` at `0x18002b52b`
- `KERNEL32!FreeLibrary` at `0x18002b5b0`
- `KERNEL32!FreeLibrary` at `0x18002b461`
- `KERNEL32!FreeLibrary` at `0x18002b4f4`
- `KERNEL32!FreeLibrary` at `0x18002b52b`
- `KERNEL32!FreeLibrary` at `0x18002b5b0`
- `KERNEL32!LeaveCriticalSection` at `0x18002b479`
- `KERNEL32!LeaveCriticalSection` at `0x18002b4c8`
- `KERNEL32!LeaveCriticalSection` at `0x18002b50c`
- `KERNEL32!LeaveCriticalSection` at `0x18002b543`
- `KERNEL32!LeaveCriticalSection` at `0x18002b479`
- `KERNEL32!LeaveCriticalSection` at `0x18002b4c8`
- `KERNEL32!LeaveCriticalSection` at `0x18002b50c`
- `KERNEL32!LeaveCriticalSection` at `0x18002b543`
- `KERNEL32!EnterCriticalSection` at `0x18002b44f`
- `KERNEL32!EnterCriticalSection` at `0x18002b4e2`
- `KERNEL32!EnterCriticalSection` at `0x18002b519`
- `KERNEL32!EnterCriticalSection` at `0x18002b44f`
- `KERNEL32!EnterCriticalSection` at `0x18002b4e2`
- `KERNEL32!EnterCriticalSection` at `0x18002b519`
- `USER32!UnregisterClassA` at `0x18002b58a`
- `USER32!UnregisterClassA` at `0x18002b59e`
- `USER32!UnregisterClassA` at `0x18002b5cf`
- `USER32!UnregisterClassA` at `0x18002b58a`
- `USER32!UnregisterClassA` at `0x18002b59e`
- `USER32!UnregisterClassA` at `0x18002b5cf`

## pseudocode

```c
void __fastcall FreeGlobalVars()
{
  int v0; // ebx
  CPropertySymbolCache *v1; // rcx
  CMimeInternational *v2; // rcx
  struct CMimeAllocator *v3; // rcx

  v0 = g_bDllUnload;
  FInitializeRichEdit(0);
  if ( g_pSrvErrRoot )
    FreeSrvErr(g_pSrvErrRoot);
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&g_pUrlCache);
  v1 = g_pSymCache;
  if ( g_pSymCache )
  {
    g_pSymCache = 0;
    (*(void (__fastcall **)(CPropertySymbolCache *))(*(_QWORD *)v1 + 16LL))(v1);
  }
  EnterCriticalSection(&g_csRAS);
  if ( g_hinstRAS )
  {
    FreeLibrary(g_hinstRAS);
    g_hinstRAS = 0;
  }
  LeaveCriticalSection(&g_csRAS);
  SSPIUninitialize();
  UnloadSecurity();
  LockLookupGlobal();
  OE_DPA_EnumCallback(lpMem, DestroyLookupInfo, 0);
  OE_DPA_Destroy(lpMem);
  --dword_1800F33E8;
  lpMem = 0;
  LeaveCriticalSection(&stru_1800F30E8);
  DeleteCriticalSection(&stru_1800F30E8);
  EnterCriticalSection(&g_csCSAPI3T1);
  if ( g_hinstCSAPI3T1 )
  {
    FreeLibrary(g_hinstCSAPI3T1);
    g_hinstCSAPI3T1 = 0;
  }
  LeaveCriticalSection(&g_csCSAPI3T1);
  EnterCriticalSection(&g_csMLANG);
  if ( g_hinstMLANG )
  {
    FreeLibrary(g_hinstMLANG);
    g_hinstMLANG = 0;
  }
  LeaveCriticalSection(&g_csMLANG);
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&g_lpIFontCache);
  v2 = g_pInternat;
  if ( g_pInternat )
  {
    g_pInternat = 0;
    (*(void (__fastcall **)(CMimeInternational *))(*(_QWORD *)v2 + 16LL))(v2);
  }
  if ( v0 )
  {
    UnregisterClassA("ThorConnWndClass", g_hLocRes);
    UnregisterClassA("HTTPMailWndClass", g_hLocRes);
  }
  if ( g_hLocRes )
  {
    FreeLibrary(g_hLocRes);
    g_hLocRes = 0;
  }
  UnregisterClassA("Athena_HttpWndClass", g_hInst);
  v3 = g_pMoleAlloc;
  if ( g_pMoleAlloc )
  {
    g_pMoleAlloc = 0;
    (*(void (__fastcall **)(struct CMimeAllocator *))(*(_QWORD *)v3 + 16LL))(v3);
  }
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&g_pMalloc);
  g_fAttached = 0;
  DeleteCriticalSection(&g_csCSAPI3T1);
  DeleteCriticalSection(&g_csMLANG);
  DeleteCriticalSection(&g_csCounter);
  DeleteCriticalSection(&g_csRAS);
  DeleteCriticalSection(&g_csDllMain);
}

```

## disassembly

```asm
0x18002b3f4  push    rbx
0x18002b3f6  sub     rsp, 20h
0x18002b3fa  mov     ebx, cs:?g_bDllUnload@@3HA; int g_bDllUnload
0x18002b400  xor     ecx, ecx
0x18002b402  call    cs:__imp_?FInitializeRichEdit@@YAHH@Z; FInitializeRichEdit(int)
0x18002b408  mov     rcx, cs:?g_pSrvErrRoot@@3PEAU_SRVIGNORABLEERROR@@EA; struct _SRVIGNORABLEERROR *
0x18002b40f  test    rcx, rcx
0x18002b412  jz      short loc_18002B419
0x18002b414  call    ?FreeSrvErr@@YAXPEAU_SRVIGNORABLEERROR@@@Z; FreeSrvErr(_SRVIGNORABLEERROR *)
0x18002b419  lea     rcx, ?g_pUrlCache@@3PEAUIMimeActiveUrlCache@@EA; IMimeActiveUrlCache * g_pUrlCache
0x18002b420  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18002b425  mov     rcx, cs:?g_pSymCache@@3PEAVCPropertySymbolCache@@EA; CPropertySymbolCache * g_pSymCache
0x18002b42c  test    rcx, rcx
0x18002b42f  jz      short loc_18002B448
0x18002b431  mov     cs:?g_pSymCache@@3PEAVCPropertySymbolCache@@EA, 0; CPropertySymbolCache * g_pSymCache
0x18002b43c  mov     rax, [rcx]
0x18002b43f  mov     rax, [rax+10h]
0x18002b443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b448  lea     rcx, ?g_csRAS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002b44f  call    cs:__imp_EnterCriticalSection
0x18002b455  mov     rcx, cs:?g_hinstRAS@@3PEAUHINSTANCE__@@EA; hLibModule
0x18002b45c  test    rcx, rcx
0x18002b45f  jz      short loc_18002B472
0x18002b461  call    cs:__imp_FreeLibrary
0x18002b467  mov     cs:?g_hinstRAS@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_hinstRAS
0x18002b472  lea     rcx, ?g_csRAS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002b479  call    cs:__imp_LeaveCriticalSection
0x18002b47f  call    ?SSPIUninitialize@@YAJXZ; SSPIUninitialize(void)
0x18002b484  call    UnloadSecurity
0x18002b489  call    _LockLookupGlobal
0x18002b48e  mov     rcx, cs:lpMem
0x18002b495  lea     rdx, _DestroyLookupInfo
0x18002b49c  xor     r8d, r8d
0x18002b49f  call    OE_DPA_EnumCallback
0x18002b4a4  mov     rcx, cs:lpMem; lpMem
0x18002b4ab  call    OE_DPA_Destroy
0x18002b4b0  dec     cs:dword_1800F33E8
0x18002b4b6  lea     rcx, stru_1800F30E8; lpCriticalSection
0x18002b4bd  mov     cs:lpMem, 0
0x18002b4c8  call    cs:__imp_LeaveCriticalSection
0x18002b4ce  lea     rcx, stru_1800F30E8; lpCriticalSection
0x18002b4d5  call    cs:__imp_DeleteCriticalSection
0x18002b4db  lea     rcx, ?g_csCSAPI3T1@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002b4e2  call    cs:__imp_EnterCriticalSection
0x18002b4e8  mov     rcx, cs:?g_hinstCSAPI3T1@@3PEAUHINSTANCE__@@EA; hLibModule
0x18002b4ef  test    rcx, rcx
0x18002b4f2  jz      short loc_18002B505
0x18002b4f4  call    cs:__imp_FreeLibrary
0x18002b4fa  mov     cs:?g_hinstCSAPI3T1@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_hinstCSAPI3T1
0x18002b505  lea     rcx, ?g_csCSAPI3T1@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002b50c  call    cs:__imp_LeaveCriticalSection
0x18002b512  lea     rcx, ?g_csMLANG@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002b519  call    cs:__imp_EnterCriticalSection
0x18002b51f  mov     rcx, cs:?g_hinstMLANG@@3PEAUHINSTANCE__@@EA; hLibModule
0x18002b526  test    rcx, rcx
0x18002b529  jz      short loc_18002B53C
0x18002b52b  call    cs:__imp_FreeLibrary
0x18002b531  mov     cs:?g_hinstMLANG@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_hinstMLANG
0x18002b53c  lea     rcx, ?g_csMLANG@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002b543  call    cs:__imp_LeaveCriticalSection
0x18002b549  lea     rcx, ?g_lpIFontCache@@3PEAUIFontCache@@EA; IFontCache * g_lpIFontCache
0x18002b550  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18002b555  mov     rcx, cs:?g_pInternat@@3PEAVCMimeInternational@@EA; CMimeInternational * g_pInternat
0x18002b55c  test    rcx, rcx
0x18002b55f  jz      short loc_18002B578
0x18002b561  mov     cs:?g_pInternat@@3PEAVCMimeInternational@@EA, 0; CMimeInternational * g_pInternat
0x18002b56c  mov     rax, [rcx]
0x18002b56f  mov     rax, [rax+10h]
0x18002b573  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b578  test    ebx, ebx
0x18002b57a  jz      short loc_18002B5A4
0x18002b57c  mov     rdx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; hInstance
0x18002b583  lea     rcx, ClassName; "ThorConnWndClass"
0x18002b58a  call    cs:__imp_UnregisterClassA
0x18002b590  mov     rdx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; hInstance
0x18002b597  lea     rcx, aHttpmailwndcla; "HTTPMailWndClass"
0x18002b59e  call    cs:__imp_UnregisterClassA
0x18002b5a4  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; hLibModule
0x18002b5ab  test    rcx, rcx
0x18002b5ae  jz      short loc_18002B5C1
0x18002b5b0  call    cs:__imp_FreeLibrary
0x18002b5b6  mov     cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_hLocRes
0x18002b5c1  mov     rdx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hInstance
0x18002b5c8  lea     rcx, aAthenaHttpwndc; "Athena_HttpWndClass"
0x18002b5cf  call    cs:__imp_UnregisterClassA
0x18002b5d5  mov     rcx, cs:?g_pMoleAlloc@@3PEAVCMimeAllocator@@EA; CMimeAllocator * g_pMoleAlloc
0x18002b5dc  test    rcx, rcx
0x18002b5df  jz      short loc_18002B5F8
0x18002b5e1  mov     cs:?g_pMoleAlloc@@3PEAVCMimeAllocator@@EA, 0; CMimeAllocator * g_pMoleAlloc
0x18002b5ec  mov     rax, [rcx]
0x18002b5ef  mov     rax, [rax+10h]
0x18002b5f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b5f8  lea     rcx, ?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18002b5ff  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18002b604  lea     rcx, ?g_csCSAPI3T1@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002b60b  mov     cs:?g_fAttached@@3HA, 0; int g_fAttached
0x18002b615  call    cs:__imp_DeleteCriticalSection
0x18002b61b  lea     rcx, ?g_csMLANG@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002b622  call    cs:__imp_DeleteCriticalSection
0x18002b628  lea     rcx, ?g_csCounter@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002b62f  call    cs:__imp_DeleteCriticalSection
0x18002b635  lea     rcx, ?g_csRAS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002b63c  call    cs:__imp_DeleteCriticalSection
0x18002b642  lea     rcx, ?g_csDllMain@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_csDllMain
0x18002b649  add     rsp, 20h
0x18002b64d  pop     rbx
0x18002b64e  jmp     cs:__imp_DeleteCriticalSection
```
