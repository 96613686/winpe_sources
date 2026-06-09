# _ProcessAttach(HINSTANCE__ *)

- ea: `0x18003a280`
- end: `0x18003ac5e`
- name: `?_ProcessAttach@@YAHPEAUHINSTANCE__@@@Z`
- size: `2526`
- prototype: `__int64 __fastcall(HINSTANCE)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800c6a8c`

## callees

- `0x18003a280`
- `0x18003ac64`
- `0x18003ac90`
- `0x18003ad48`
- `0x18003adbc`
- `0x18003afb0`
- `0x18003b368`
- `0x1800bf0d8`
- `0x180591f80`

## import_xrefs

- `SHLWAPI!SHCreateShellPalette` at `0x18003a6bd`
- `SHLWAPI!SHCreateShellPalette` at `0x18003a6bd`
- `KERNEL32!InitializeCriticalSection` at `0x18003a8a8`
- `KERNEL32!InitializeCriticalSection` at `0x18003a8a8`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x18003a556`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x18003a556`
- `KERNEL32!ReleaseActCtx` at `0x18003ac10`
- `KERNEL32!ReleaseActCtx` at `0x18003ac10`
- `KERNEL32!DeactivateActCtx` at `0x18003abc4`
- `KERNEL32!DeactivateActCtx` at `0x18003abc4`
- `KERNEL32!CreateActCtxW` at `0x18003a642`
- `KERNEL32!CreateActCtxW` at `0x18003a642`
- `KERNEL32!GetModuleFileNameW` at `0x18003a609`
- `KERNEL32!GetModuleFileNameW` at `0x18003a609`
- `KERNEL32!GetModuleHandleW` at `0x18003abfc`
- `KERNEL32!GetModuleHandleW` at `0x18003abfc`
- `KERNEL32!GetProcessHeap` at `0x18003a409`
- `KERNEL32!GetProcessHeap` at `0x18003a46c`
- `KERNEL32!GetProcessHeap` at `0x18003a409`
- `KERNEL32!GetProcessHeap` at `0x18003a46c`
- `KERNEL32!HeapAlloc` at `0x18003a423`
- `KERNEL32!HeapAlloc` at `0x18003a597`
- `KERNEL32!HeapAlloc` at `0x18003a423`
- `KERNEL32!HeapAlloc` at `0x18003a597`
- `KERNEL32!TlsAlloc` at `0x18003a3c5`
- `KERNEL32!TlsAlloc` at `0x18003a3e5`
- `KERNEL32!TlsAlloc` at `0x18003a3f7`
- `KERNEL32!TlsAlloc` at `0x18003a3c5`
- `KERNEL32!TlsAlloc` at `0x18003a3e5`
- `KERNEL32!TlsAlloc` at `0x18003a3f7`
- `KERNEL32!DisableThreadLibraryCalls` at `0x18003a382`
- `KERNEL32!DisableThreadLibraryCalls` at `0x18003a382`
- `KERNEL32!GetACP` at `0x18003a695`
- `KERNEL32!GetACP` at `0x18003a695`
- `KERNEL32!InitializeCriticalSectionEx` at `0x18003a3a1`
- `KERNEL32!InitializeCriticalSectionEx` at `0x18003a4af`
- `KERNEL32!InitializeCriticalSectionEx` at `0x18003a4d1`
- `KERNEL32!InitializeCriticalSectionEx` at `0x18003a4f3`
- `KERNEL32!InitializeCriticalSectionEx` at `0x18003a515`
- `KERNEL32!InitializeCriticalSectionEx` at `0x18003a537`
- `KERNEL32!InitializeCriticalSectionEx` at `0x18003a578`
- `KERNEL32!InitializeCriticalSectionEx` at `0x18003a3a1`
- `KERNEL32!InitializeCriticalSectionEx` at `0x18003a4af`
- `KERNEL32!InitializeCriticalSectionEx` at `0x18003a4d1`
- `KERNEL32!InitializeCriticalSectionEx` at `0x18003a4f3`
- `KERNEL32!InitializeCriticalSectionEx` at `0x18003a515`
- `KERNEL32!InitializeCriticalSectionEx` at `0x18003a537`
- `KERNEL32!InitializeCriticalSectionEx` at `0x18003a578`
- `KERNEL32!LoadLibraryExW` at `0x18003aba9`
- `KERNEL32!LoadLibraryExW` at `0x18003ac37`
- `KERNEL32!LoadLibraryExW` at `0x18003aba9`
- `KERNEL32!LoadLibraryExW` at `0x18003ac37`
- `api-ms-win-downlevel-advapi32-l1-1-0!EventRegister` at `0x18003a34c`
- `api-ms-win-downlevel-advapi32-l1-1-0!EventRegister` at `0x18003a34c`
- `ADVAPI32!EventSetInformation` at `0x18003a373`
- `ADVAPI32!EventSetInformation` at `0x18003a373`
- `USER32!GetSystemMetrics` at `0x18003a735`
- `USER32!GetSystemMetrics` at `0x18003a735`
- `USER32!RegisterWindowMessageW` at `0x18003a70b`
- `USER32!RegisterWindowMessageW` at `0x18003a724`
- `USER32!RegisterWindowMessageW` at `0x18003a70b`
- `USER32!RegisterWindowMessageW` at `0x18003a724`
- `iertutil!__imp_?IESetThreadRefTLSIndex@@YAXK@Z` at `0x18003a3d9`
- `iertutil!__imp_?IESetThreadRefTLSIndex@@YAXK@Z` at `0x18003a3d9`

## string_xrefs

- `0x18003ab9c`: `comctl32.dll`
- `0x18003ac2a`: `comctl32.dll`

## pseudocode

```c
__int64 __fastcall _ProcessAttach(HINSTANCE a1, __int64 a2)
{
  __int64 v3; // rdx
  __int64 v4; // rdx
  __int64 v5; // rdx
  unsigned int v6; // ebx
  HANDLE ProcessHeap; // rax
  CPolicyCache *v8; // rax
  CPolicyCache *v9; // r14
  unsigned __int64 v10; // rdi
  HANDLE v11; // rcx
  unsigned __int128 v12; // rax
  struct ATL::_ATL_MODULE *v13; // rcx
  HMODULE v14; // rdi
  HPALETTE v15; // rax
  HMODULE v17; // rdi
  ACTCTXW pActCtx; // [rsp+20h] [rbp-288h] BYREF
  GUID ProviderId; // [rsp+58h] [rbp-250h] BYREF
  WCHAR Filename[264]; // [rsp+70h] [rbp-238h] BYREF

  McGenEventRegister_EventRegister(BERP_IEFRAME, a2, BERP_IEFRAME_Context, BERP_IEFRAME_Context);
  McGenEventRegister_EventRegister(BERP_MSHTML, v3, BERP_MSHTML_Context, BERP_MSHTML_Context);
  McGenEventRegister_EventRegister(BERP_IEFRAME2, v4, BERP_IEFRAME2_Context, BERP_IEFRAME2_Context);
  McGenEventRegister_EventRegister(BERP_READINGVIEW, v5, BERP_READINGVIEW_Context, BERP_READINGVIEW_Context);
  ProviderId = *(GUID *)&(*off_18069E820)[-16];
  if ( RegHandle )
    __fastfail(5u);
  xmmword_18069E840 = 0;
  if ( !EventRegister(&ProviderId, tlgEnableCallback, &dword_18069E818, &RegHandle) )
    EventSetInformation(RegHandle, 2, (char *)off_18069E820, *(unsigned __int16 *)off_18069E820);
  DisableThreadLibraryCalls(a1);
  g_bDllTerminating = 0;
  v6 = InitializeCriticalSectionEx(&g_csDll, 0, 0);
  if ( v6 )
  {
    v6 = InitializeCriticalSectionEx(&g_csThreadHooks, 0, 0);
    if ( v6 )
    {
      v6 = InitializeCriticalSectionEx(&g_csThumbnail, 0, 0);
      if ( v6 )
      {
        v6 = InitializeCriticalSectionEx(&g_csDownloadManager, 0, 0);
        if ( v6 )
        {
          v6 = InitializeCriticalSectionEx(&g_csNewTabPageData, 0, 0);
          if ( v6 )
          {
            v6 = InitializeCriticalSectionEx(&g_csLocalRoamedTabTimer, 0, 0);
            if ( v6 )
            {
              v6 = InitializeCriticalSectionAndSpinCount(&CAsyncStorage::s_csInCallback, 0);
              if ( v6 )
                InitializeCriticalSectionEx(&g_csNamedWindowList, 0, 0);
            }
          }
        }
      }
    }
  }
  g_hinst = a1;
  g_hinstMUI = a1;
  g_tlsThreadRef = TlsAlloc();
  IESetThreadRefTLSIndex(g_tlsThreadRef);
  g_tlsOtherThreadsRef = TlsAlloc();
  TabThreadMinidumpState::_tlsIndex = TlsAlloc();
  ProcessHeap = GetProcessHeap();
  v8 = (CPolicyCache *)HeapAlloc(ProcessHeap, 8u, 0x18u);
  v9 = v8;
  if ( !v8 )
    std::_Xbad_alloc();
  *((_DWORD *)v8 + 1) = -1;
  *((_QWORD *)v8 + 2) = 0;
  *((_QWORD *)v8 + 1) = 8LL * (unsigned int)dword_18069EA30;
  v10 = (unsigned int)dword_18069EA30;
  v11 = GetProcessHeap();
  *((_QWORD *)v9 + 2) = 0;
  *(_QWORD *)&ProviderId.Data1 = 0;
  v12 = v10 * (unsigned __int128)8uLL;
  if ( !is_mul_ok(v10, 8u) )
  {
    *(_DWORD *)v9 = dword_18069EA18;
LABEL_17:
    CPolicyCache::`scalar deleting destructor'(v9, DWORD2(v12));
    qword_18069EA38 = 0;
    goto LABEL_18;
  }
  *(_QWORD *)&v12 = HeapAlloc(v11, 8u, 8 * v10);
  *((_QWORD *)v9 + 2) = v12;
  v13 = (struct ATL::_ATL_MODULE *)(unsigned int)dword_18069EA18;
  *(_DWORD *)v9 = dword_18069EA18;
  if ( !(_QWORD)v12 )
    goto LABEL_17;
  qword_18069EA38 = v9;
LABEL_18:
  if ( g_hActCtx == (HANDLE)-1LL )
  {
    memset(&pActCtx, 0, sizeof(pActCtx));
    v14 = a1 ? a1 : GetModuleHandleW(0);
    GetModuleFileNameW(v14, Filename, 0x104u);
    pActCtx.cbSize = 56;
    pActCtx.lpSource = Filename;
    pActCtx.dwFlags = 136;
    pActCtx.lpResourceName = (LPCWSTR)123;
    pActCtx.hModule = v14;
    *(_QWORD *)&v12 = CreateActCtxW(&pActCtx);
    v13 = (struct ATL::_ATL_MODULE *)v12;
    if ( (_QWORD)v12 != -1 )
    {
      if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_hActCtx, v12, -1) != -1 )
        ReleaseActCtx((HANDLE)v12);
      if ( !g_hinstCC )
      {
        *(_QWORD *)&ProviderId.Data1 = 0;
        if ( !(unsigned int)SHActivateContext(&ProviderId) )
        {
          g_hinstCC = 0;
LABEL_37:
          g_hinstCC = LoadLibraryExW(L"comctl32.dll", 0, 0x4000u);
          goto LABEL_22;
        }
        *(_QWORD *)&v12 = LoadLibraryExW(L"comctl32.dll", 0, 0x4000u);
        *((_QWORD *)&v12 + 1) = *(_QWORD *)&ProviderId.Data1;
        v17 = (HMODULE)v12;
        if ( *(_QWORD *)&ProviderId.Data1 )
          DeactivateActCtx(0, *(ULONG_PTR *)&ProviderId.Data1);
        g_hinstCC = v17;
        if ( !v17 )
          goto LABEL_37;
      }
    }
  }
LABEL_22:
  _Module = 248;
  qword_1806A4AA8 = (__int64)&ATL::GUID_ATLVer30;
  dword_1806A4A90 = 769;
  if ( (int)ATL::AtlModuleInit(v13, *((struct ATL::_ATL_OBJMAP_ENTRY **)&v12 + 1), a1) >= 0 )
    dword_1806A4AD0 = 1;
  GetACP();
  ProviderId.Data1 = 8;
  *(_DWORD *)&ProviderId.Data2 = 0x2000;
  InitCommonControlsEx((const INITCOMMONCONTROLSEX *)&ProviderId);
  v15 = SHCreateShellPalette(0);
  CSearchActivityProvider::s_iSearchNameTemplateId = 30806;
  g_hpalHalftone = v15;
  CSearchActivityProvider::s_hInstMUI = g_hinstMUI;
  g_pfnGetFavIconBaseResource = (HBITMAP (__high *)(enum tagBASE_ICON_STYLE, unsigned int))&IEFrameGetFaviconBaseImage;
  g_pfnURLHookCreateInstance = (int (*)(const struct _GUID *, void **))CURLSearchHook_CreateInstance2;
  g_msgMSWheel = RegisterWindowMessageW(L"MSWHEEL_ROLLMSG");
  RegisterWindowMessageW(L"ShellGetDragImage");
  GetSystemMetrics(42);
  pkeyIE_DisplayName = PKEY_Title;
  pkeyIE_NavigationUrl = PKEY_Link_TargetUrl;
  pkeyIE_VisitCount = PKEY_History_VisitCount;
  pkeyIE_SelectionCount = PKEY_History_SelectionCount;
  pkeyIE_UrlHost = PKEY_Link_TargetUrlHostName;
  pkeyIE_UrlPath = PKEY_Link_TargetUrlPath;
  pkeyIE_FeedItem = PKEY_Link_FeedItemLocalId;
  pkeyIE_DateVisited = PKEY_Link_DateVisited;
  pkeyIE_DisplayUrl = PKEY_ItemPathDisplay;
  pkeyIE_FolderName = PKEY_ItemFolderNameDisplay;
  pkeyIE_FolderPath = PKEY_ItemFolderPathDisplay;
  pkeyIE_Filename = PKEY_ItemNameDisplay;
  pkeyIE_Author = PKEY_Author;
  g_pfnUpdateFavoritesTimeStamps = _UpdateAllFavoritesTimestamp;
  InitializeCriticalSection(&stru_1806A6550);
  qword_1806A6150 = 0;
  dword_1806A6160 = 0;
  qword_1806A6168[0] = 0;
  qword_1806A6170 = 0;
  dword_1806A6180 = 0;
  qword_1806A6188 = 0;
  qword_1806A6190 = 0;
  dword_1806A61A0 = 0;
  qword_1806A61A8 = 0;
  qword_1806A61B0 = 0;
  dword_1806A61C0 = 0;
  qword_1806A61C8 = 0;
  qword_1806A61D0 = 0;
  dword_1806A61E0 = 0;
  qword_1806A61E8 = 0;
  qword_1806A61F0 = 0;
  dword_1806A6200 = 0;
  qword_1806A6208 = 0;
  qword_1806A6210 = 0;
  dword_1806A6220 = 0;
  qword_1806A6228 = 0;
  qword_1806A6230 = 0;
  dword_1806A6240 = 0;
  qword_1806A6248 = 0;
  qword_1806A6250 = 0;
  dword_1806A6260 = 0;
  qword_1806A6268 = 0;
  qword_1806A6270 = 0;
  dword_1806A6280 = 0;
  qword_1806A6288 = 0;
  qword_1806A6290 = 0;
  dword_1806A62A0 = 0;
  qword_1806A62A8 = 0;
  qword_1806A62B0 = 0;
  dword_1806A62C0 = 0;
  qword_1806A62C8 = 0;
  qword_1806A62D0 = 0;
  dword_1806A62E0 = 0;
  qword_1806A62E8 = 0;
  qword_1806A62F0 = 0;
  dword_1806A6300 = 0;
  qword_1806A6308 = 0;
  qword_1806A6310 = 0;
  dword_1806A6320 = 0;
  qword_1806A6328 = 0;
  qword_1806A6330 = 0;
  dword_1806A6340 = 0;
  qword_1806A6348 = 0;
  qword_1806A6350 = 0;
  dword_1806A6360 = 0;
  qword_1806A6368 = 0;
  qword_1806A6370 = 0;
  dword_1806A6380 = 0;
  qword_1806A6388 = 0;
  qword_1806A6390 = 0;
  dword_1806A63A0 = 0;
  qword_1806A63A8 = 0;
  qword_1806A63B0 = 0;
  dword_1806A63C0 = 0;
  qword_1806A63C8 = 0;
  qword_1806A63D0 = 0;
  dword_1806A63E0 = 0;
  qword_1806A63E8 = 0;
  qword_1806A63F0 = 0;
  dword_1806A6400 = 0;
  qword_1806A6408 = 0;
  qword_1806A6410 = 0;
  dword_1806A6420 = 0;
  qword_1806A6428 = 0;
  qword_1806A6430 = 0;
  dword_1806A6440 = 0;
  qword_1806A6448 = 0;
  qword_1806A6450 = 0;
  dword_1806A6460 = 0;
  qword_1806A6468 = 0;
  qword_1806A6470 = 0;
  dword_1806A6480 = 0;
  qword_1806A6488 = 0;
  qword_1806A6490 = 0;
  dword_1806A64A0 = 0;
  qword_1806A64A8 = 0;
  qword_1806A64B0 = 0;
  dword_1806A64C0 = 0;
  qword_1806A64C8 = 0;
  qword_1806A64D0 = 0;
  dword_1806A64E0 = 0;
  qword_1806A64E8 = 0;
  qword_1806A64F0 = 0;
  dword_1806A6500 = 0;
  qword_1806A6508 = 0;
  qword_1806A6510 = 0;
  dword_1806A6520 = 0;
  qword_1806A6528 = 0;
  qword_1806A6530 = 0;
  dword_1806A6540 = 0;
  qword_1806A6548 = 0;
  BrowserTelemetry::IEFrameProcessAttached();
  return v6;
}

```

## disassembly

```asm
0x18003a280  push    rbx
0x18003a282  push    rsi
0x18003a283  push    r14
0x18003a285  sub     rsp, 290h
0x18003a28c  mov     rax, cs:__security_cookie
0x18003a293  xor     rax, rsp
0x18003a296  mov     [rsp+2A8h+var_28], rax
0x18003a29e  mov     rsi, rcx
0x18003a2a1  lea     r9, BERP_IEFRAME_Context
0x18003a2a8  lea     rcx, BERP_IEFRAME
0x18003a2af  lea     r8, BERP_IEFRAME_Context
0x18003a2b6  call    McGenEventRegister_EventRegister
0x18003a2bb  lea     r9, BERP_MSHTML_Context
0x18003a2c2  lea     r8, BERP_MSHTML_Context
0x18003a2c9  lea     rcx, BERP_MSHTML
0x18003a2d0  call    McGenEventRegister_EventRegister
0x18003a2d5  lea     r9, BERP_IEFRAME2_Context
0x18003a2dc  lea     r8, BERP_IEFRAME2_Context
0x18003a2e3  lea     rcx, BERP_IEFRAME2
0x18003a2ea  call    McGenEventRegister_EventRegister
0x18003a2ef  lea     r9, BERP_READINGVIEW_Context
0x18003a2f6  lea     r8, BERP_READINGVIEW_Context
0x18003a2fd  lea     rcx, BERP_READINGVIEW
0x18003a304  call    McGenEventRegister_EventRegister
0x18003a309  cmp     cs:RegHandle, 0
0x18003a311  mov     rax, cs:off_18069E820
0x18003a318  movups  xmm0, xmmword ptr [rax-10h]
0x18003a31c  movups  xmmword ptr [rsp+2A8h+ProviderId.Data1], xmm0
0x18003a321  jnz     loc_18003ABEE
0x18003a327  xorps   xmm0, xmm0
0x18003a32a  lea     r9, RegHandle; RegHandle
0x18003a331  lea     r8, dword_18069E818; CallbackContext
0x18003a338  lea     rdx, _tlgEnableCallback; EnableCallback
0x18003a33f  lea     rcx, [rsp+2A8h+ProviderId]; ProviderId
0x18003a344  movdqu  cs:xmmword_18069E840, xmm0
0x18003a34c  call    cs:__imp_EventRegister
0x18003a353  nop     dword ptr [rax+rax+00h]
0x18003a358  test    eax, eax
0x18003a35a  jnz     short loc_18003A37F
0x18003a35c  mov     r8, cs:off_18069E820
0x18003a363  mov     edx, 2
0x18003a368  mov     rcx, cs:RegHandle
0x18003a36f  movzx   r9d, word ptr [r8]
0x18003a373  call    cs:__imp_EventSetInformation
0x18003a37a  nop     dword ptr [rax+rax+00h]
0x18003a37f  mov     rcx, rsi; hLibModule
0x18003a382  call    cs:__imp_DisableThreadLibraryCalls
0x18003a389  nop     dword ptr [rax+rax+00h]
0x18003a38e  xor     r8d, r8d; Flags
0x18003a391  mov     cs:?g_bDllTerminating@@3_NA, 0; bool g_bDllTerminating
0x18003a398  xor     edx, edx; dwSpinCount
0x18003a39a  lea     rcx, g_csDll; lpCriticalSection
0x18003a3a1  call    cs:__imp_InitializeCriticalSectionEx
0x18003a3a8  nop     dword ptr [rax+rax+00h]
0x18003a3ad  mov     ebx, eax
0x18003a3af  test    eax, eax
0x18003a3b1  jnz     loc_18003A4A3
0x18003a3b7  mov     cs:g_hinst, rsi
0x18003a3be  mov     cs:g_hinstMUI, rsi
0x18003a3c5  call    cs:__imp_TlsAlloc
0x18003a3cc  nop     dword ptr [rax+rax+00h]
0x18003a3d1  mov     ecx, eax
0x18003a3d3  mov     cs:g_tlsThreadRef, eax
0x18003a3d9  call    cs:__imp_?IESetThreadRefTLSIndex@@YAXK@Z; IESetThreadRefTLSIndex(ulong)
0x18003a3e0  nop     dword ptr [rax+rax+00h]
0x18003a3e5  call    cs:__imp_TlsAlloc
0x18003a3ec  nop     dword ptr [rax+rax+00h]
0x18003a3f1  mov     cs:g_tlsOtherThreadsRef, eax
0x18003a3f7  call    cs:__imp_TlsAlloc
0x18003a3fe  nop     dword ptr [rax+rax+00h]
0x18003a403  mov     cs:?_tlsIndex@TabThreadMinidumpState@@0KA, eax; ulong TabThreadMinidumpState::_tlsIndex
0x18003a409  call    cs:__imp_GetProcessHeap
0x18003a410  nop     dword ptr [rax+rax+00h]
0x18003a415  mov     edx, 8; dwFlags
0x18003a41a  mov     r8d, 18h; dwBytes
0x18003a420  mov     rcx, rax; hHeap
0x18003a423  call    cs:__imp_HeapAlloc
0x18003a42a  nop     dword ptr [rax+rax+00h]
0x18003a42f  mov     r14, rax
0x18003a432  test    rax, rax
0x18003a435  jz      loc_18003A589
0x18003a43b  mov     dword ptr [rax+4], 0FFFFFFFFh
0x18003a442  mov     [rsp+2A8h+arg_8], rbp
0x18003a44a  xor     ebp, ebp
0x18003a44c  mov     [rax+10h], rbp
0x18003a450  mov     eax, cs:dword_18069EA30
0x18003a456  shl     rax, 3
0x18003a45a  mov     [r14+8], rax
0x18003a45e  mov     [rsp+2A8h+arg_10], rdi
0x18003a466  mov     edi, cs:dword_18069EA30
0x18003a46c  call    cs:__imp_GetProcessHeap
0x18003a473  nop     dword ptr [rax+rax+00h]
0x18003a478  mov     rcx, rax; hHeap
0x18003a47b  mov     [r14+10h], rbp
0x18003a47f  mov     eax, 8
0x18003a484  mov     qword ptr [rsp+2A8h+ProviderId.Data1], rbp
0x18003a489  mul     rdi
0x18003a48c  test    rdx, rdx
0x18003a48f  jz      loc_18003A58F
0x18003a495  mov     eax, cs:dword_18069EA18
0x18003a49b  mov     [r14], eax
0x18003a49e  jmp     loc_18003A5B9
0x18003a4a3  xor     r8d, r8d; Flags
0x18003a4a6  lea     rcx, ?g_csThreadHooks@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003a4ad  xor     edx, edx; dwSpinCount
0x18003a4af  call    cs:__imp_InitializeCriticalSectionEx
0x18003a4b6  nop     dword ptr [rax+rax+00h]
0x18003a4bb  mov     ebx, eax
0x18003a4bd  test    eax, eax
0x18003a4bf  jz      loc_18003A3B7
0x18003a4c5  xor     r8d, r8d; Flags
0x18003a4c8  lea     rcx, ?g_csThumbnail@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003a4cf  xor     edx, edx; dwSpinCount
0x18003a4d1  call    cs:__imp_InitializeCriticalSectionEx
0x18003a4d8  nop     dword ptr [rax+rax+00h]
0x18003a4dd  mov     ebx, eax
0x18003a4df  test    eax, eax
0x18003a4e1  jz      loc_18003A3B7
0x18003a4e7  xor     r8d, r8d; Flags
0x18003a4ea  lea     rcx, ?g_csDownloadManager@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003a4f1  xor     edx, edx; dwSpinCount
0x18003a4f3  call    cs:__imp_InitializeCriticalSectionEx
0x18003a4fa  nop     dword ptr [rax+rax+00h]
0x18003a4ff  mov     ebx, eax
0x18003a501  test    eax, eax
0x18003a503  jz      loc_18003A3B7
0x18003a509  xor     r8d, r8d; Flags
0x18003a50c  lea     rcx, ?g_csNewTabPageData@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003a513  xor     edx, edx; dwSpinCount
0x18003a515  call    cs:__imp_InitializeCriticalSectionEx
0x18003a51c  nop     dword ptr [rax+rax+00h]
0x18003a521  mov     ebx, eax
0x18003a523  test    eax, eax
0x18003a525  jz      loc_18003A3B7
0x18003a52b  xor     r8d, r8d; Flags
0x18003a52e  lea     rcx, ?g_csLocalRoamedTabTimer@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003a535  xor     edx, edx; dwSpinCount
0x18003a537  call    cs:__imp_InitializeCriticalSectionEx
0x18003a53e  nop     dword ptr [rax+rax+00h]
0x18003a543  mov     ebx, eax
0x18003a545  test    eax, eax
0x18003a547  jz      loc_18003A3B7
0x18003a54d  xor     edx, edx; dwSpinCount
0x18003a54f  lea     rcx, ?s_csInCallback@CAsyncStorage@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003a556  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18003a55d  nop     dword ptr [rax+rax+00h]
0x18003a562  mov     ebx, eax
0x18003a564  test    eax, eax
0x18003a566  jz      loc_18003A3B7
0x18003a56c  xor     r8d, r8d; Flags
0x18003a56f  lea     rcx, ?g_csNamedWindowList@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003a576  xor     edx, edx; dwSpinCount
0x18003a578  call    cs:__imp_InitializeCriticalSectionEx
0x18003a57f  nop     dword ptr [rax+rax+00h]
0x18003a584  jmp     loc_18003A3B7
0x18003a589  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18003a58f  mov     r8, rax; dwBytes
0x18003a592  mov     edx, 8; dwFlags
0x18003a597  call    cs:__imp_HeapAlloc
0x18003a59e  nop     dword ptr [rax+rax+00h]
0x18003a5a3  mov     [r14+10h], rax
0x18003a5a7  mov     ecx, cs:dword_18069EA18
0x18003a5ad  mov     [r14], ecx
0x18003a5b0  test    rax, rax
0x18003a5b3  jnz     loc_18003ABE2
0x18003a5b9  mov     rcx, r14; this
0x18003a5bc  call    ??_GCPolicyCache@@QEAAPEAXI@Z; CPolicyCache::`scalar deleting destructor'(uint)
0x18003a5c1  mov     cs:qword_18069EA38, rbp
0x18003a5c8  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x18003a5d0  jnz     loc_18003A65B
0x18003a5d6  xorps   xmm0, xmm0
0x18003a5d9  xor     eax, eax
0x18003a5db  mov     [rsp+2A8h+pActCtx.hModule], rax
0x18003a5e0  movups  xmmword ptr [rsp+2A8h+pActCtx.cbSize], xmm0
0x18003a5e5  movups  xmmword ptr [rsp+2A8h+pActCtx.wProcessorArchitecture], xmm0
0x18003a5ea  movups  xmmword ptr [rsp+2A8h+pActCtx.lpResourceName], xmm0
0x18003a5ef  test    rsi, rsi
0x18003a5f2  jz      loc_18003ABFA
0x18003a5f8  mov     rdi, rsi
0x18003a5fb  mov     r8d, 104h; nSize
0x18003a601  lea     rdx, [rsp+2A8h+Filename]; lpFilename
0x18003a606  mov     rcx, rdi; hModule
0x18003a609  call    cs:__imp_GetModuleFileNameW
0x18003a610  nop     dword ptr [rax+rax+00h]
0x18003a615  lea     rcx, [rsp+2A8h+Filename]
0x18003a61a  mov     [rsp+2A8h+pActCtx.cbSize], 38h ; '8'
0x18003a622  mov     [rsp+2A8h+pActCtx.lpSource], rcx
0x18003a627  lea     rcx, [rsp+2A8h+pActCtx]; pActCtx
0x18003a62c  mov     [rsp+2A8h+pActCtx.dwFlags], 88h
0x18003a634  mov     [rsp+2A8h+pActCtx.lpResourceName], 7Bh ; '{'
0x18003a63d  mov     [rsp+2A8h+pActCtx.hModule], rdi
0x18003a642  call    cs:__imp_CreateActCtxW
0x18003a649  nop     dword ptr [rax+rax+00h]
0x18003a64e  mov     rcx, rax; struct ATL::_ATL_MODULE *
0x18003a651  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003a655  jnz     loc_18003AB60
0x18003a65b  lea     rax, ?GUID_ATLVer30@ATL@@3U_GUID@@A; _GUID ATL::GUID_ATLVer30
0x18003a662  mov     cs:?_Module@@3VCComModule@ATL@@A, 0F8h; ATL::CComModule _Module
0x18003a66c  mov     r8, rsi; HINSTANCE
0x18003a66f  mov     cs:qword_1806A4AA8, rax
0x18003a676  mov     cs:dword_1806A4A90, 301h
0x18003a680  call    ?AtlModuleInit@ATL@@YAJPEAU_ATL_MODULE@1@PEAU_ATL_OBJMAP_ENTRY@1@PEAUHINSTANCE__@@@Z; ATL::AtlModuleInit(ATL::_ATL_MODULE *,ATL::_ATL_OBJMAP_ENTRY *,HINSTANCE__ *)
0x18003a685  mov     rdi, [rsp+2A8h+arg_10]
0x18003a68d  test    eax, eax
0x18003a68f  jns     loc_18003AC4F
0x18003a695  call    cs:__imp_GetACP
0x18003a69c  nop     dword ptr [rax+rax+00h]
0x18003a6a1  lea     rcx, [rsp+2A8h+ProviderId]; picce
0x18003a6a6  mov     [rsp+2A8h+ProviderId.Data1], 8
0x18003a6ae  mov     dword ptr [rsp+2A8h+ProviderId.Data2], 2000h
0x18003a6b6  call    InitCommonControlsEx
0x18003a6bb  xor     ecx, ecx; hdc
0x18003a6bd  call    cs:__imp_SHCreateShellPalette
0x18003a6c4  nop     dword ptr [rax+rax+00h]
0x18003a6c9  lea     rcx, aMswheelRollmsg; "MSWHEEL_ROLLMSG"
0x18003a6d0  mov     cs:?s_iSearchNameTemplateId@CSearchActivityProvider@@2IA, 7856h; uint CSearchActivityProvider::s_iSearchNameTemplateId
0x18003a6da  mov     cs:g_hpalHalftone, rax
0x18003a6e1  mov     rax, cs:g_hinstMUI
0x18003a6e8  mov     cs:?s_hInstMUI@CSearchActivityProvider@@2PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * CSearchActivityProvider::s_hInstMUI
0x18003a6ef  lea     rax, ?IEFrameGetFaviconBaseImage@@YAPEAUHBITMAP__@@W4tagBASE_ICON_STYLE@@I@Z; IEFrameGetFaviconBaseImage(tagBASE_ICON_STYLE,uint)
0x18003a6f6  mov     cs:?g_pfnGetFavIconBaseResource@@3P6APEAUHBITMAP__@@W4tagBASE_ICON_STYLE@@I@ZEA, rax; HBITMAP__ * (*g_pfnGetFavIconBaseResource)(tagBASE_ICON_STYLE,uint)
0x18003a6fd  lea     rax, CURLSearchHook_CreateInstance2
0x18003a704  mov     cs:?g_pfnURLHookCreateInstance@@3P6AJAEBU_GUID@@PEAPEAX@ZEA, rax; long (*g_pfnURLHookCreateInstance)(_GUID const &,void * *)
0x18003a70b  call    cs:__imp_RegisterWindowMessageW
0x18003a712  nop     dword ptr [rax+rax+00h]
0x18003a717  lea     rcx, aShellgetdragim; "ShellGetDragImage"
0x18003a71e  mov     cs:g_msgMSWheel, eax
0x18003a724  call    cs:__imp_RegisterWindowMessageW
0x18003a72b  nop     dword ptr [rax+rax+00h]
0x18003a730  mov     ecx, 2Ah ; '*'; nIndex
0x18003a735  call    cs:__imp_GetSystemMetrics
0x18003a73c  nop     dword ptr [rax+rax+00h]
0x18003a741  movups  xmm0, xmmword ptr cs:PKEY_Title.fmtid.Data1
0x18003a748  mov     eax, cs:PKEY_Title.pid
0x18003a74e  lea     rcx, stru_1806A6550; lpCriticalSection
0x18003a755  mov     cs:?pkeyIE_DisplayName@@3U_tagpropertykey@@A.pid, eax; _tagpropertykey pkeyIE_DisplayName ...
0x18003a75b  mov     eax, cs:PKEY_Link_TargetUrl.pid
0x18003a761  movups  xmmword ptr cs:?pkeyIE_DisplayName@@3U_tagpropertykey@@A.fmtid.Data1, xmm0; _tagpropertykey pkeyIE_DisplayName ...
0x18003a768  mov     cs:?pkeyIE_NavigationUrl@@3U_tagpropertykey@@A.pid, eax; _tagpropertykey pkeyIE_NavigationUrl ...
0x18003a76e  movups  xmm0, xmmword ptr cs:PKEY_Link_TargetUrl.fmtid.Data1
0x18003a775  mov     eax, cs:PKEY_History_VisitCount.pid
0x18003a77b  mov     cs:?pkeyIE_VisitCount@@3U_tagpropertykey@@A.pid, eax; _tagpropertykey pkeyIE_VisitCount ...
0x18003a781  mov     eax, cs:PKEY_History_SelectionCount.pid
0x18003a787  movups  xmmword ptr cs:?pkeyIE_NavigationUrl@@3U_tagpropertykey@@A.fmtid.Data1, xmm0; _tagpropertykey pkeyIE_NavigationUrl ...
0x18003a78e  mov     cs:?pkeyIE_SelectionCount@@3U_tagpropertykey@@A.pid, eax; _tagpropertykey pkeyIE_SelectionCount ...
0x18003a794  movups  xmm0, xmmword ptr cs:PKEY_History_VisitCount.fmtid.Data1
0x18003a79b  mov     eax, cs:PKEY_Link_TargetUrlHostName.pid
0x18003a7a1  mov     cs:?pkeyIE_UrlHost@@3U_tagpropertykey@@A.pid, eax; _tagpropertykey pkeyIE_UrlHost ...
0x18003a7a7  mov     eax, cs:PKEY_Link_TargetUrlPath.pid
0x18003a7ad  movups  xmmword ptr cs:?pkeyIE_VisitCount@@3U_tagpropertykey@@A.fmtid.Data1, xmm0; _tagpropertykey pkeyIE_VisitCount ...
0x18003a7b4  mov     dword ptr cs:?pkeyIE_UrlPath@@3U_tagpropertykey@@A+10h, eax; _tagpropertykey pkeyIE_UrlPath
0x18003a7ba  movups  xmm0, xmmword ptr cs:PKEY_History_SelectionCount.fmtid.Data1
0x18003a7c1  mov     eax, cs:PKEY_Link_FeedItemLocalId.pid
0x18003a7c7  mov     dword ptr cs:?pkeyIE_FeedItem@@3U_tagpropertykey@@A+10h, eax; _tagpropertykey pkeyIE_FeedItem
0x18003a7cd  mov     eax, cs:PKEY_Link_DateVisited.pid
0x18003a7d3  movups  xmmword ptr cs:?pkeyIE_SelectionCount@@3U_tagpropertykey@@A.fmtid.Data1, xmm0; _tagpropertykey pkeyIE_SelectionCount ...
0x18003a7da  mov     cs:?pkeyIE_DateVisited@@3U_tagpropertykey@@A.pid, eax; _tagpropertykey pkeyIE_DateVisited ...
0x18003a7e0  movups  xmm0, xmmword ptr cs:PKEY_Link_TargetUrlHostName.fmtid.Data1
0x18003a7e7  mov     eax, cs:PKEY_ItemPathDisplay.pid
0x18003a7ed  mov     cs:?pkeyIE_DisplayUrl@@3U_tagpropertykey@@A.pid, eax; _tagpropertykey pkeyIE_DisplayUrl ...
0x18003a7f3  mov     eax, cs:PKEY_ItemFolderNameDisplay.pid
0x18003a7f9  movups  xmmword ptr cs:?pkeyIE_UrlHost@@3U_tagpropertykey@@A.fmtid.Data1, xmm0; _tagpropertykey pkeyIE_UrlHost ...
0x18003a800  mov     dword ptr cs:?pkeyIE_FolderName@@3U_tagpropertykey@@A+10h, eax; _tagpropertykey pkeyIE_FolderName
0x18003a806  mov     eax, cs:PKEY_ItemFolderPathDisplay.pid
0x18003a80c  movups  xmm0, xmmword ptr cs:PKEY_Link_TargetUrlPath.fmtid.Data1
0x18003a813  mov     dword ptr cs:?pkeyIE_FolderPath@@3U_tagpropertykey@@A+10h, eax; _tagpropertykey pkeyIE_FolderPath
0x18003a819  mov     eax, cs:PKEY_ItemNameDisplay.pid
0x18003a81f  movups  xmmword ptr cs:?pkeyIE_UrlPath@@3U_tagpropertykey@@A, xmm0; _tagpropertykey pkeyIE_UrlPath
0x18003a826  mov     cs:?pkeyIE_Filename@@3U_tagpropertykey@@A.pid, eax; _tagpropertykey pkeyIE_Filename ...
0x18003a82c  movups  xmm0, xmmword ptr cs:PKEY_Link_FeedItemLocalId.fmtid.Data1
0x18003a833  mov     eax, cs:PKEY_Author.pid
0x18003a839  mov     dword ptr cs:?pkeyIE_Author@@3U_tagpropertykey@@A+10h, eax; _tagpropertykey pkeyIE_Author
0x18003a83f  lea     rax, ?_UpdateAllFavoritesTimestamp@@YAXXZ; _UpdateAllFavoritesTimestamp(void)
0x18003a846  movups  xmmword ptr cs:?pkeyIE_FeedItem@@3U_tagpropertykey@@A, xmm0; _tagpropertykey pkeyIE_FeedItem
0x18003a84d  mov     cs:?g_pfnUpdateFavoritesTimeStamps@@3P6AXXZEA, rax; void (*g_pfnUpdateFavoritesTimeStamps)(void)
0x18003a854  movups  xmm0, xmmword ptr cs:PKEY_Link_DateVisited.fmtid.Data1
0x18003a85b  movups  xmmword ptr cs:?pkeyIE_DateVisited@@3U_tagpropertykey@@A.fmtid.Data1, xmm0; _tagpropertykey pkeyIE_DateVisited ...
0x18003a862  movups  xmm0, xmmword ptr cs:PKEY_ItemPathDisplay.fmtid.Data1
0x18003a869  movups  xmmword ptr cs:?pkeyIE_DisplayUrl@@3U_tagpropertykey@@A.fmtid.Data1, xmm0; _tagpropertykey pkeyIE_DisplayUrl ...
0x18003a870  movups  xmm0, xmmword ptr cs:PKEY_ItemFolderNameDisplay.fmtid.Data1
0x18003a877  movups  xmmword ptr cs:?pkeyIE_FolderName@@3U_tagpropertykey@@A, xmm0; _tagpropertykey pkeyIE_FolderName
0x18003a87e  movups  xmm0, xmmword ptr cs:PKEY_ItemFolderPathDisplay.fmtid.Data1
0x18003a885  movups  xmmword ptr cs:?pkeyIE_FolderPath@@3U_tagpropertykey@@A, xmm0; _tagpropertykey pkeyIE_FolderPath
0x18003a88c  movups  xmm0, xmmword ptr cs:PKEY_ItemNameDisplay.fmtid.Data1
0x18003a893  movups  xmmword ptr cs:?pkeyIE_Filename@@3U_tagpropertykey@@A.fmtid.Data1, xmm0; _tagpropertykey pkeyIE_Filename ...
0x18003a89a  movups  xmm0, xmmword ptr cs:PKEY_Author.fmtid.Data1
0x18003a8a1  movups  xmmword ptr cs:?pkeyIE_Author@@3U_tagpropertykey@@A, xmm0; _tagpropertykey pkeyIE_Author
0x18003a8a8  call    cs:__imp_InitializeCriticalSection
0x18003a8af  nop     dword ptr [rax+rax+00h]
0x18003a8b4  mov     cs:qword_1806A6150, rbp
0x18003a8bb  mov     cs:dword_1806A6160, ebp
0x18003a8c1  mov     cs:qword_1806A6168, rbp
0x18003a8c8  mov     cs:qword_1806A6170, rbp
0x18003a8cf  mov     cs:dword_1806A6180, ebp
0x18003a8d5  mov     cs:qword_1806A6188, rbp
0x18003a8dc  mov     cs:qword_1806A6190, rbp
0x18003a8e3  mov     cs:dword_1806A61A0, ebp
0x18003a8e9  mov     cs:qword_1806A61A8, rbp
0x18003a8f0  mov     cs:qword_1806A61B0, rbp
0x18003a8f7  mov     cs:dword_1806A61C0, ebp
  ... truncated ...
```
