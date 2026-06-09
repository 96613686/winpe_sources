# _ProcessAttach(HINSTANCE__ *)

- ea: `0x180038780`
- end: `0x180039095`
- name: `?_ProcessAttach@@YAHPEAUHINSTANCE__@@@Z`
- size: `2325`
- prototype: `__int64 __fastcall(HINSTANCE)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800bfc00`

## callees

- `0x180038780`
- `0x18003909c`
- `0x1800390c0`
- `0x18003916c`
- `0x1800391d8`
- `0x1800393a8`
- `0x1800396ec`
- `0x1800b83c8`
- `0x18054e310`

## import_xrefs

- `SHLWAPI!SHCreateShellPalette` at `0x180038b35`
- `SHLWAPI!SHCreateShellPalette` at `0x180038b35`
- `KERNEL32!InitializeCriticalSection` at `0x180038d08`
- `KERNEL32!InitializeCriticalSection` at `0x180038d08`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x1800389f6`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x1800389f6`
- `KERNEL32!ReleaseActCtx` at `0x180039053`
- `KERNEL32!ReleaseActCtx` at `0x180039053`
- `KERNEL32!DeactivateActCtx` at `0x180039013`
- `KERNEL32!DeactivateActCtx` at `0x180039013`
- `KERNEL32!CreateActCtxW` at `0x180038ac6`
- `KERNEL32!CreateActCtxW` at `0x180038ac6`
- `KERNEL32!GetModuleFileNameW` at `0x180038a93`
- `KERNEL32!GetModuleFileNameW` at `0x180038a93`
- `KERNEL32!GetModuleHandleW` at `0x180039045`
- `KERNEL32!GetModuleHandleW` at `0x180039045`
- `KERNEL32!GetProcessHeap` at `0x1800388d9`
- `KERNEL32!GetProcessHeap` at `0x180038930`
- `KERNEL32!GetProcessHeap` at `0x1800388d9`
- `KERNEL32!GetProcessHeap` at `0x180038930`
- `KERNEL32!HeapAlloc` at `0x1800388ed`
- `KERNEL32!HeapAlloc` at `0x180038a2b`
- `KERNEL32!HeapAlloc` at `0x1800388ed`
- `KERNEL32!HeapAlloc` at `0x180038a2b`
- `KERNEL32!TlsAlloc` at `0x1800388ad`
- `KERNEL32!TlsAlloc` at `0x1800388c1`
- `KERNEL32!TlsAlloc` at `0x1800388cd`
- `KERNEL32!TlsAlloc` at `0x1800388ad`
- `KERNEL32!TlsAlloc` at `0x1800388c1`
- `KERNEL32!TlsAlloc` at `0x1800388cd`
- `KERNEL32!DisableThreadLibraryCalls` at `0x180038876`
- `KERNEL32!DisableThreadLibraryCalls` at `0x180038876`
- `KERNEL32!GetACP` at `0x180038b13`
- `KERNEL32!GetACP` at `0x180038b13`
- `KERNEL32!InitializeCriticalSectionEx` at `0x18003888f`
- `KERNEL32!InitializeCriticalSectionEx` at `0x18003896d`
- `KERNEL32!InitializeCriticalSectionEx` at `0x180038989`
- `KERNEL32!InitializeCriticalSectionEx` at `0x1800389a5`
- `KERNEL32!InitializeCriticalSectionEx` at `0x1800389c1`
- `KERNEL32!InitializeCriticalSectionEx` at `0x1800389dd`
- `KERNEL32!InitializeCriticalSectionEx` at `0x180038a12`
- `KERNEL32!InitializeCriticalSectionEx` at `0x18003888f`
- `KERNEL32!InitializeCriticalSectionEx` at `0x18003896d`
- `KERNEL32!InitializeCriticalSectionEx` at `0x180038989`
- `KERNEL32!InitializeCriticalSectionEx` at `0x1800389a5`
- `KERNEL32!InitializeCriticalSectionEx` at `0x1800389c1`
- `KERNEL32!InitializeCriticalSectionEx` at `0x1800389dd`
- `KERNEL32!InitializeCriticalSectionEx` at `0x180038a12`
- `KERNEL32!LoadLibraryExW` at `0x180038ffe`
- `KERNEL32!LoadLibraryExW` at `0x180039074`
- `KERNEL32!LoadLibraryExW` at `0x180038ffe`
- `KERNEL32!LoadLibraryExW` at `0x180039074`
- `api-ms-win-downlevel-advapi32-l1-1-0!EventRegister` at `0x18003884c`
- `api-ms-win-downlevel-advapi32-l1-1-0!EventRegister` at `0x18003884c`
- `ADVAPI32!EventSetInformation` at `0x18003886d`
- `ADVAPI32!EventSetInformation` at `0x18003886d`
- `USER32!GetSystemMetrics` at `0x180038b9b`
- `USER32!GetSystemMetrics` at `0x180038b9b`
- `USER32!RegisterWindowMessageW` at `0x180038b7d`
- `USER32!RegisterWindowMessageW` at `0x180038b90`
- `USER32!RegisterWindowMessageW` at `0x180038b7d`
- `USER32!RegisterWindowMessageW` at `0x180038b90`
- `iertutil!__imp_?IESetThreadRefTLSIndex@@YAXK@Z` at `0x1800388bb`
- `iertutil!__imp_?IESetThreadRefTLSIndex@@YAXK@Z` at `0x1800388bb`

## string_xrefs

- `0x180038ff1`: `comctl32.dll`
- `0x180039067`: `comctl32.dll`

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
  ProviderId = *(GUID *)&(*off_18065A820)[-16];
  if ( RegHandle )
    __fastfail(5u);
  xmmword_18065A840 = 0;
  if ( !EventRegister(&ProviderId, tlgEnableCallback, &dword_18065A818, &RegHandle) )
    EventSetInformation(RegHandle, 2, (char *)off_18065A820, *(unsigned __int16 *)off_18065A820);
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
  *((_QWORD *)v8 + 1) = 8LL * (unsigned int)dword_18065AA30;
  v10 = (unsigned int)dword_18065AA30;
  v11 = GetProcessHeap();
  *((_QWORD *)v9 + 2) = 0;
  *(_QWORD *)&ProviderId.Data1 = 0;
  v12 = v10 * (unsigned __int128)8uLL;
  if ( !is_mul_ok(v10, 8u) )
  {
    *(_DWORD *)v9 = dword_18065AA18;
LABEL_17:
    CPolicyCache::`scalar deleting destructor'(v9, DWORD2(v12));
    qword_18065AA38 = 0;
    goto LABEL_18;
  }
  *(_QWORD *)&v12 = HeapAlloc(v11, 8u, 8 * v10);
  *((_QWORD *)v9 + 2) = v12;
  v13 = (struct ATL::_ATL_MODULE *)(unsigned int)dword_18065AA18;
  *(_DWORD *)v9 = dword_18065AA18;
  if ( !(_QWORD)v12 )
    goto LABEL_17;
  qword_18065AA38 = v9;
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
  qword_180660AA8 = (__int64)&ATL::GUID_ATLVer30;
  dword_180660A90 = 769;
  if ( (int)ATL::AtlModuleInit(v13, *((struct ATL::_ATL_OBJMAP_ENTRY **)&v12 + 1), a1) >= 0 )
    dword_180660AD0 = 1;
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
  InitializeCriticalSection(&stru_180662540);
  qword_180662140 = 0;
  dword_180662150 = 0;
  qword_180662158[0] = 0;
  qword_180662160 = 0;
  dword_180662170 = 0;
  qword_180662178 = 0;
  qword_180662180 = 0;
  dword_180662190 = 0;
  qword_180662198 = 0;
  qword_1806621A0 = 0;
  dword_1806621B0 = 0;
  qword_1806621B8 = 0;
  qword_1806621C0 = 0;
  dword_1806621D0 = 0;
  qword_1806621D8 = 0;
  qword_1806621E0 = 0;
  dword_1806621F0 = 0;
  qword_1806621F8 = 0;
  qword_180662200 = 0;
  dword_180662210 = 0;
  qword_180662218 = 0;
  qword_180662220 = 0;
  dword_180662230 = 0;
  qword_180662238 = 0;
  qword_180662240 = 0;
  dword_180662250 = 0;
  qword_180662258 = 0;
  qword_180662260 = 0;
  dword_180662270 = 0;
  qword_180662278 = 0;
  qword_180662280 = 0;
  dword_180662290 = 0;
  qword_180662298 = 0;
  qword_1806622A0 = 0;
  dword_1806622B0 = 0;
  qword_1806622B8 = 0;
  qword_1806622C0 = 0;
  dword_1806622D0 = 0;
  qword_1806622D8 = 0;
  qword_1806622E0 = 0;
  dword_1806622F0 = 0;
  qword_1806622F8 = 0;
  qword_180662300 = 0;
  dword_180662310 = 0;
  qword_180662318 = 0;
  qword_180662320 = 0;
  dword_180662330 = 0;
  qword_180662338 = 0;
  qword_180662340 = 0;
  dword_180662350 = 0;
  qword_180662358 = 0;
  qword_180662360 = 0;
  dword_180662370 = 0;
  qword_180662378 = 0;
  qword_180662380 = 0;
  dword_180662390 = 0;
  qword_180662398 = 0;
  qword_1806623A0 = 0;
  dword_1806623B0 = 0;
  qword_1806623B8 = 0;
  qword_1806623C0 = 0;
  dword_1806623D0 = 0;
  qword_1806623D8 = 0;
  qword_1806623E0 = 0;
  dword_1806623F0 = 0;
  qword_1806623F8 = 0;
  qword_180662400 = 0;
  dword_180662410 = 0;
  qword_180662418 = 0;
  qword_180662420 = 0;
  dword_180662430 = 0;
  qword_180662438 = 0;
  qword_180662440 = 0;
  dword_180662450 = 0;
  qword_180662458 = 0;
  qword_180662460 = 0;
  dword_180662470 = 0;
  qword_180662478 = 0;
  qword_180662480 = 0;
  dword_180662490 = 0;
  qword_180662498 = 0;
  qword_1806624A0 = 0;
  dword_1806624B0 = 0;
  qword_1806624B8 = 0;
  qword_1806624C0 = 0;
  dword_1806624D0 = 0;
  qword_1806624D8 = 0;
  qword_1806624E0 = 0;
  dword_1806624F0 = 0;
  qword_1806624F8 = 0;
  qword_180662500 = 0;
  dword_180662510 = 0;
  qword_180662518 = 0;
  qword_180662520 = 0;
  dword_180662530 = 0;
  qword_180662538 = 0;
  BrowserTelemetry::IEFrameProcessAttached();
  return v6;
}

```

## disassembly

```asm
0x180038780  push    rbx
0x180038782  push    rsi
0x180038783  push    r14
0x180038785  sub     rsp, 290h
0x18003878c  mov     rax, cs:__security_cookie
0x180038793  xor     rax, rsp
0x180038796  mov     [rsp+2A8h+var_28], rax
0x18003879e  mov     rsi, rcx
0x1800387a1  lea     r9, BERP_IEFRAME_Context
0x1800387a8  lea     rcx, BERP_IEFRAME
0x1800387af  lea     r8, BERP_IEFRAME_Context
0x1800387b6  call    McGenEventRegister_EventRegister
0x1800387bb  lea     r9, BERP_MSHTML_Context
0x1800387c2  lea     r8, BERP_MSHTML_Context
0x1800387c9  lea     rcx, BERP_MSHTML
0x1800387d0  call    McGenEventRegister_EventRegister
0x1800387d5  lea     r9, BERP_IEFRAME2_Context
0x1800387dc  lea     r8, BERP_IEFRAME2_Context
0x1800387e3  lea     rcx, BERP_IEFRAME2
0x1800387ea  call    McGenEventRegister_EventRegister
0x1800387ef  lea     r9, BERP_READINGVIEW_Context
0x1800387f6  lea     r8, BERP_READINGVIEW_Context
0x1800387fd  lea     rcx, BERP_READINGVIEW
0x180038804  call    McGenEventRegister_EventRegister
0x180038809  cmp     cs:RegHandle, 0
0x180038811  mov     rax, cs:off_18065A820
0x180038818  movups  xmm0, xmmword ptr [rax-10h]
0x18003881c  movups  xmmword ptr [rsp+2A8h+ProviderId.Data1], xmm0
0x180038821  jnz     loc_180039037
0x180038827  xorps   xmm0, xmm0
0x18003882a  lea     r9, RegHandle; RegHandle
0x180038831  lea     r8, dword_18065A818; CallbackContext
0x180038838  lea     rdx, _tlgEnableCallback; EnableCallback
0x18003883f  lea     rcx, [rsp+2A8h+ProviderId]; ProviderId
0x180038844  movdqu  cs:xmmword_18065A840, xmm0
0x18003884c  call    cs:__imp_EventRegister
0x180038852  test    eax, eax
0x180038854  jnz     short loc_180038873
0x180038856  mov     r8, cs:off_18065A820
0x18003885d  mov     edx, 2
0x180038862  mov     rcx, cs:RegHandle
0x180038869  movzx   r9d, word ptr [r8]
0x18003886d  call    cs:__imp_EventSetInformation
0x180038873  mov     rcx, rsi; hLibModule
0x180038876  call    cs:__imp_DisableThreadLibraryCalls
0x18003887c  xor     r8d, r8d; Flags
0x18003887f  mov     cs:?g_bDllTerminating@@3_NA, 0; bool g_bDllTerminating
0x180038886  xor     edx, edx; dwSpinCount
0x180038888  lea     rcx, g_csDll; lpCriticalSection
0x18003888f  call    cs:__imp_InitializeCriticalSectionEx
0x180038895  mov     ebx, eax
0x180038897  test    eax, eax
0x180038899  jnz     loc_180038961
0x18003889f  mov     cs:g_hinst, rsi
0x1800388a6  mov     cs:g_hinstMUI, rsi
0x1800388ad  call    cs:__imp_TlsAlloc
0x1800388b3  mov     ecx, eax
0x1800388b5  mov     cs:g_tlsThreadRef, eax
0x1800388bb  call    cs:__imp_?IESetThreadRefTLSIndex@@YAXK@Z; IESetThreadRefTLSIndex(ulong)
0x1800388c1  call    cs:__imp_TlsAlloc
0x1800388c7  mov     cs:g_tlsOtherThreadsRef, eax
0x1800388cd  call    cs:__imp_TlsAlloc
0x1800388d3  mov     cs:?_tlsIndex@TabThreadMinidumpState@@0KA, eax; ulong TabThreadMinidumpState::_tlsIndex
0x1800388d9  call    cs:__imp_GetProcessHeap
0x1800388df  mov     edx, 8; dwFlags
0x1800388e4  mov     r8d, 18h; dwBytes
0x1800388ea  mov     rcx, rax; hHeap
0x1800388ed  call    cs:__imp_HeapAlloc
0x1800388f3  mov     r14, rax
0x1800388f6  test    rax, rax
0x1800388f9  jz      loc_180038A1D
0x1800388ff  mov     dword ptr [rax+4], 0FFFFFFFFh
0x180038906  mov     [rsp+2A8h+arg_8], rbp
0x18003890e  xor     ebp, ebp
0x180038910  mov     [rax+10h], rbp
0x180038914  mov     eax, cs:dword_18065AA30
0x18003891a  shl     rax, 3
0x18003891e  mov     [r14+8], rax
0x180038922  mov     [rsp+2A8h+arg_10], rdi
0x18003892a  mov     edi, cs:dword_18065AA30
0x180038930  call    cs:__imp_GetProcessHeap
0x180038936  mov     rcx, rax; hHeap
0x180038939  mov     [r14+10h], rbp
0x18003893d  mov     eax, 8
0x180038942  mov     qword ptr [rsp+2A8h+ProviderId.Data1], rbp
0x180038947  mul     rdi
0x18003894a  test    rdx, rdx
0x18003894d  jz      loc_180038A23
0x180038953  mov     eax, cs:dword_18065AA18
0x180038959  mov     [r14], eax
0x18003895c  jmp     loc_180038A47
0x180038961  xor     r8d, r8d; Flags
0x180038964  lea     rcx, ?g_csThreadHooks@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003896b  xor     edx, edx; dwSpinCount
0x18003896d  call    cs:__imp_InitializeCriticalSectionEx
0x180038973  mov     ebx, eax
0x180038975  test    eax, eax
0x180038977  jz      loc_18003889F
0x18003897d  xor     r8d, r8d; Flags
0x180038980  lea     rcx, ?g_csThumbnail@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180038987  xor     edx, edx; dwSpinCount
0x180038989  call    cs:__imp_InitializeCriticalSectionEx
0x18003898f  mov     ebx, eax
0x180038991  test    eax, eax
0x180038993  jz      loc_18003889F
0x180038999  xor     r8d, r8d; Flags
0x18003899c  lea     rcx, ?g_csDownloadManager@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800389a3  xor     edx, edx; dwSpinCount
0x1800389a5  call    cs:__imp_InitializeCriticalSectionEx
0x1800389ab  mov     ebx, eax
0x1800389ad  test    eax, eax
0x1800389af  jz      loc_18003889F
0x1800389b5  xor     r8d, r8d; Flags
0x1800389b8  lea     rcx, ?g_csNewTabPageData@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800389bf  xor     edx, edx; dwSpinCount
0x1800389c1  call    cs:__imp_InitializeCriticalSectionEx
0x1800389c7  mov     ebx, eax
0x1800389c9  test    eax, eax
0x1800389cb  jz      loc_18003889F
0x1800389d1  xor     r8d, r8d; Flags
0x1800389d4  lea     rcx, ?g_csLocalRoamedTabTimer@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800389db  xor     edx, edx; dwSpinCount
0x1800389dd  call    cs:__imp_InitializeCriticalSectionEx
0x1800389e3  mov     ebx, eax
0x1800389e5  test    eax, eax
0x1800389e7  jz      loc_18003889F
0x1800389ed  xor     edx, edx; dwSpinCount
0x1800389ef  lea     rcx, ?s_csInCallback@CAsyncStorage@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800389f6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800389fc  mov     ebx, eax
0x1800389fe  test    eax, eax
0x180038a00  jz      loc_18003889F
0x180038a06  xor     r8d, r8d; Flags
0x180038a09  lea     rcx, ?g_csNamedWindowList@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180038a10  xor     edx, edx; dwSpinCount
0x180038a12  call    cs:__imp_InitializeCriticalSectionEx
0x180038a18  jmp     loc_18003889F
0x180038a1d  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180038a23  mov     r8, rax; dwBytes
0x180038a26  mov     edx, 8; dwFlags
0x180038a2b  call    cs:__imp_HeapAlloc
0x180038a31  mov     [r14+10h], rax
0x180038a35  mov     ecx, cs:dword_18065AA18
0x180038a3b  mov     [r14], ecx
0x180038a3e  test    rax, rax
0x180038a41  jnz     loc_18003902B
0x180038a47  mov     rcx, r14; this
0x180038a4a  call    ??_GCPolicyCache@@QEAAPEAXI@Z; CPolicyCache::`scalar deleting destructor'(uint)
0x180038a4f  mov     cs:qword_18065AA38, rbp
0x180038a56  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x180038a5e  jnz     short loc_180038AD9
0x180038a60  xorps   xmm0, xmm0
0x180038a63  xor     eax, eax
0x180038a65  mov     [rsp+2A8h+pActCtx.hModule], rax
0x180038a6a  movups  xmmword ptr [rsp+2A8h+pActCtx.cbSize], xmm0
0x180038a6f  movups  xmmword ptr [rsp+2A8h+pActCtx.wProcessorArchitecture], xmm0
0x180038a74  movups  xmmword ptr [rsp+2A8h+pActCtx.lpResourceName], xmm0
0x180038a79  test    rsi, rsi
0x180038a7c  jz      loc_180039043
0x180038a82  mov     rdi, rsi
0x180038a85  mov     r8d, 104h; nSize
0x180038a8b  lea     rdx, [rsp+2A8h+Filename]; lpFilename
0x180038a90  mov     rcx, rdi; hModule
0x180038a93  call    cs:__imp_GetModuleFileNameW
0x180038a99  lea     rcx, [rsp+2A8h+Filename]
0x180038a9e  mov     [rsp+2A8h+pActCtx.cbSize], 38h ; '8'
0x180038aa6  mov     [rsp+2A8h+pActCtx.lpSource], rcx
0x180038aab  lea     rcx, [rsp+2A8h+pActCtx]; pActCtx
0x180038ab0  mov     [rsp+2A8h+pActCtx.dwFlags], 88h
0x180038ab8  mov     [rsp+2A8h+pActCtx.lpResourceName], 7Bh ; '{'
0x180038ac1  mov     [rsp+2A8h+pActCtx.hModule], rdi
0x180038ac6  call    cs:__imp_CreateActCtxW
0x180038acc  mov     rcx, rax; struct ATL::_ATL_MODULE *
0x180038acf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180038ad3  jnz     loc_180038FB9
0x180038ad9  lea     rax, ?GUID_ATLVer30@ATL@@3U_GUID@@A; _GUID ATL::GUID_ATLVer30
0x180038ae0  mov     cs:?_Module@@3VCComModule@ATL@@A, 0F8h; ATL::CComModule _Module
0x180038aea  mov     r8, rsi; HINSTANCE
0x180038aed  mov     cs:qword_180660AA8, rax
0x180038af4  mov     cs:dword_180660A90, 301h
0x180038afe  call    ?AtlModuleInit@ATL@@YAJPEAU_ATL_MODULE@1@PEAU_ATL_OBJMAP_ENTRY@1@PEAUHINSTANCE__@@@Z; ATL::AtlModuleInit(ATL::_ATL_MODULE *,ATL::_ATL_OBJMAP_ENTRY *,HINSTANCE__ *)
0x180038b03  mov     rdi, [rsp+2A8h+arg_10]
0x180038b0b  test    eax, eax
0x180038b0d  jns     loc_180039086
0x180038b13  call    cs:__imp_GetACP
0x180038b19  lea     rcx, [rsp+2A8h+ProviderId]; picce
0x180038b1e  mov     [rsp+2A8h+ProviderId.Data1], 8
0x180038b26  mov     dword ptr [rsp+2A8h+ProviderId.Data2], 2000h
0x180038b2e  call    InitCommonControlsEx
0x180038b33  xor     ecx, ecx; hdc
0x180038b35  call    cs:__imp_SHCreateShellPalette
0x180038b3b  lea     rcx, aMswheelRollmsg; "MSWHEEL_ROLLMSG"
0x180038b42  mov     cs:?s_iSearchNameTemplateId@CSearchActivityProvider@@2IA, 7856h; uint CSearchActivityProvider::s_iSearchNameTemplateId
0x180038b4c  mov     cs:g_hpalHalftone, rax
0x180038b53  mov     rax, cs:g_hinstMUI
0x180038b5a  mov     cs:?s_hInstMUI@CSearchActivityProvider@@2PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * CSearchActivityProvider::s_hInstMUI
0x180038b61  lea     rax, ?IEFrameGetFaviconBaseImage@@YAPEAUHBITMAP__@@W4tagBASE_ICON_STYLE@@I@Z; IEFrameGetFaviconBaseImage(tagBASE_ICON_STYLE,uint)
0x180038b68  mov     cs:?g_pfnGetFavIconBaseResource@@3P6APEAUHBITMAP__@@W4tagBASE_ICON_STYLE@@I@ZEA, rax; HBITMAP__ * (*g_pfnGetFavIconBaseResource)(tagBASE_ICON_STYLE,uint)
0x180038b6f  lea     rax, CURLSearchHook_CreateInstance2
0x180038b76  mov     cs:?g_pfnURLHookCreateInstance@@3P6AJAEBU_GUID@@PEAPEAX@ZEA, rax; long (*g_pfnURLHookCreateInstance)(_GUID const &,void * *)
0x180038b7d  call    cs:__imp_RegisterWindowMessageW
0x180038b83  lea     rcx, aShellgetdragim; "ShellGetDragImage"
0x180038b8a  mov     cs:g_msgMSWheel, eax
0x180038b90  call    cs:__imp_RegisterWindowMessageW
0x180038b96  mov     ecx, 2Ah ; '*'; nIndex
0x180038b9b  call    cs:__imp_GetSystemMetrics
0x180038ba1  movups  xmm0, xmmword ptr cs:PKEY_Title.fmtid.Data1
0x180038ba8  mov     eax, cs:PKEY_Title.pid
0x180038bae  lea     rcx, stru_180662540; lpCriticalSection
0x180038bb5  mov     cs:?pkeyIE_DisplayName@@3U_tagpropertykey@@A.pid, eax; _tagpropertykey pkeyIE_DisplayName ...
0x180038bbb  mov     eax, cs:PKEY_Link_TargetUrl.pid
0x180038bc1  movups  xmmword ptr cs:?pkeyIE_DisplayName@@3U_tagpropertykey@@A.fmtid.Data1, xmm0; _tagpropertykey pkeyIE_DisplayName ...
0x180038bc8  mov     cs:?pkeyIE_NavigationUrl@@3U_tagpropertykey@@A.pid, eax; _tagpropertykey pkeyIE_NavigationUrl ...
0x180038bce  movups  xmm0, xmmword ptr cs:PKEY_Link_TargetUrl.fmtid.Data1
0x180038bd5  mov     eax, cs:PKEY_History_VisitCount.pid
0x180038bdb  mov     cs:?pkeyIE_VisitCount@@3U_tagpropertykey@@A.pid, eax; _tagpropertykey pkeyIE_VisitCount ...
0x180038be1  mov     eax, cs:PKEY_History_SelectionCount.pid
0x180038be7  movups  xmmword ptr cs:?pkeyIE_NavigationUrl@@3U_tagpropertykey@@A.fmtid.Data1, xmm0; _tagpropertykey pkeyIE_NavigationUrl ...
0x180038bee  mov     cs:?pkeyIE_SelectionCount@@3U_tagpropertykey@@A.pid, eax; _tagpropertykey pkeyIE_SelectionCount ...
0x180038bf4  movups  xmm0, xmmword ptr cs:PKEY_History_VisitCount.fmtid.Data1
0x180038bfb  mov     eax, cs:PKEY_Link_TargetUrlHostName.pid
0x180038c01  mov     cs:?pkeyIE_UrlHost@@3U_tagpropertykey@@A.pid, eax; _tagpropertykey pkeyIE_UrlHost ...
0x180038c07  mov     eax, cs:PKEY_Link_TargetUrlPath.pid
0x180038c0d  movups  xmmword ptr cs:?pkeyIE_VisitCount@@3U_tagpropertykey@@A.fmtid.Data1, xmm0; _tagpropertykey pkeyIE_VisitCount ...
0x180038c14  mov     dword ptr cs:?pkeyIE_UrlPath@@3U_tagpropertykey@@A+10h, eax; _tagpropertykey pkeyIE_UrlPath
0x180038c1a  movups  xmm0, xmmword ptr cs:PKEY_History_SelectionCount.fmtid.Data1
0x180038c21  mov     eax, cs:PKEY_Link_FeedItemLocalId.pid
0x180038c27  mov     dword ptr cs:?pkeyIE_FeedItem@@3U_tagpropertykey@@A+10h, eax; _tagpropertykey pkeyIE_FeedItem
0x180038c2d  mov     eax, cs:PKEY_Link_DateVisited.pid
0x180038c33  movups  xmmword ptr cs:?pkeyIE_SelectionCount@@3U_tagpropertykey@@A.fmtid.Data1, xmm0; _tagpropertykey pkeyIE_SelectionCount ...
0x180038c3a  mov     cs:?pkeyIE_DateVisited@@3U_tagpropertykey@@A.pid, eax; _tagpropertykey pkeyIE_DateVisited ...
0x180038c40  movups  xmm0, xmmword ptr cs:PKEY_Link_TargetUrlHostName.fmtid.Data1
0x180038c47  mov     eax, cs:PKEY_ItemPathDisplay.pid
0x180038c4d  mov     cs:?pkeyIE_DisplayUrl@@3U_tagpropertykey@@A.pid, eax; _tagpropertykey pkeyIE_DisplayUrl ...
0x180038c53  mov     eax, cs:PKEY_ItemFolderNameDisplay.pid
0x180038c59  movups  xmmword ptr cs:?pkeyIE_UrlHost@@3U_tagpropertykey@@A.fmtid.Data1, xmm0; _tagpropertykey pkeyIE_UrlHost ...
0x180038c60  mov     dword ptr cs:?pkeyIE_FolderName@@3U_tagpropertykey@@A+10h, eax; _tagpropertykey pkeyIE_FolderName
0x180038c66  mov     eax, cs:PKEY_ItemFolderPathDisplay.pid
0x180038c6c  movups  xmm0, xmmword ptr cs:PKEY_Link_TargetUrlPath.fmtid.Data1
0x180038c73  mov     dword ptr cs:?pkeyIE_FolderPath@@3U_tagpropertykey@@A+10h, eax; _tagpropertykey pkeyIE_FolderPath
0x180038c79  mov     eax, cs:PKEY_ItemNameDisplay.pid
0x180038c7f  movups  xmmword ptr cs:?pkeyIE_UrlPath@@3U_tagpropertykey@@A, xmm0; _tagpropertykey pkeyIE_UrlPath
0x180038c86  mov     cs:?pkeyIE_Filename@@3U_tagpropertykey@@A.pid, eax; _tagpropertykey pkeyIE_Filename ...
0x180038c8c  movups  xmm0, xmmword ptr cs:PKEY_Link_FeedItemLocalId.fmtid.Data1
0x180038c93  mov     eax, cs:PKEY_Author.pid
0x180038c99  mov     dword ptr cs:?pkeyIE_Author@@3U_tagpropertykey@@A+10h, eax; _tagpropertykey pkeyIE_Author
0x180038c9f  lea     rax, ?_UpdateAllFavoritesTimestamp@@YAXXZ; _UpdateAllFavoritesTimestamp(void)
0x180038ca6  movups  xmmword ptr cs:?pkeyIE_FeedItem@@3U_tagpropertykey@@A, xmm0; _tagpropertykey pkeyIE_FeedItem
0x180038cad  mov     cs:?g_pfnUpdateFavoritesTimeStamps@@3P6AXXZEA, rax; void (*g_pfnUpdateFavoritesTimeStamps)(void)
0x180038cb4  movups  xmm0, xmmword ptr cs:PKEY_Link_DateVisited.fmtid.Data1
0x180038cbb  movups  xmmword ptr cs:?pkeyIE_DateVisited@@3U_tagpropertykey@@A.fmtid.Data1, xmm0; _tagpropertykey pkeyIE_DateVisited ...
0x180038cc2  movups  xmm0, xmmword ptr cs:PKEY_ItemPathDisplay.fmtid.Data1
0x180038cc9  movups  xmmword ptr cs:?pkeyIE_DisplayUrl@@3U_tagpropertykey@@A.fmtid.Data1, xmm0; _tagpropertykey pkeyIE_DisplayUrl ...
0x180038cd0  movups  xmm0, xmmword ptr cs:PKEY_ItemFolderNameDisplay.fmtid.Data1
0x180038cd7  movups  xmmword ptr cs:?pkeyIE_FolderName@@3U_tagpropertykey@@A, xmm0; _tagpropertykey pkeyIE_FolderName
0x180038cde  movups  xmm0, xmmword ptr cs:PKEY_ItemFolderPathDisplay.fmtid.Data1
0x180038ce5  movups  xmmword ptr cs:?pkeyIE_FolderPath@@3U_tagpropertykey@@A, xmm0; _tagpropertykey pkeyIE_FolderPath
0x180038cec  movups  xmm0, xmmword ptr cs:PKEY_ItemNameDisplay.fmtid.Data1
0x180038cf3  movups  xmmword ptr cs:?pkeyIE_Filename@@3U_tagpropertykey@@A.fmtid.Data1, xmm0; _tagpropertykey pkeyIE_Filename ...
0x180038cfa  movups  xmm0, xmmword ptr cs:PKEY_Author.fmtid.Data1
0x180038d01  movups  xmmword ptr cs:?pkeyIE_Author@@3U_tagpropertykey@@A, xmm0; _tagpropertykey pkeyIE_Author
0x180038d08  call    cs:__imp_InitializeCriticalSection
0x180038d0e  mov     cs:qword_180662140, rbp
0x180038d15  mov     cs:dword_180662150, ebp
0x180038d1b  mov     cs:qword_180662158, rbp
0x180038d22  mov     cs:qword_180662160, rbp
0x180038d29  mov     cs:dword_180662170, ebp
0x180038d2f  mov     cs:qword_180662178, rbp
0x180038d36  mov     cs:qword_180662180, rbp
0x180038d3d  mov     cs:dword_180662190, ebp
0x180038d43  mov     cs:qword_180662198, rbp
0x180038d4a  mov     cs:qword_1806621A0, rbp
0x180038d51  mov     cs:dword_1806621B0, ebp
0x180038d57  mov     cs:qword_1806621B8, rbp
0x180038d5e  mov     cs:qword_1806621C0, rbp
0x180038d65  mov     cs:dword_1806621D0, ebp
0x180038d6b  mov     cs:qword_1806621D8, rbp
0x180038d72  mov     cs:qword_1806621E0, rbp
0x180038d79  mov     cs:dword_1806621F0, ebp
0x180038d7f  mov     cs:qword_1806621F8, rbp
0x180038d86  mov     cs:qword_180662200, rbp
0x180038d8d  mov     cs:dword_180662210, ebp
0x180038d93  mov     cs:qword_180662218, rbp
0x180038d9a  mov     cs:qword_180662220, rbp
0x180038da1  mov     cs:dword_180662230, ebp
0x180038da7  mov     cs:qword_180662238, rbp
0x180038dae  mov     cs:qword_180662240, rbp
0x180038db5  mov     cs:dword_180662250, ebp
0x180038dbb  mov     cs:qword_180662258, rbp
0x180038dc2  mov     cs:qword_180662260, rbp
0x180038dc9  mov     cs:dword_180662270, ebp
0x180038dcf  mov     cs:qword_180662278, rbp
0x180038dd6  mov     cs:qword_180662280, rbp
0x180038ddd  mov     cs:dword_180662290, ebp
0x180038de3  mov     cs:qword_180662298, rbp
0x180038dea  mov     cs:qword_1806622A0, rbp
0x180038df1  mov     cs:dword_1806622B0, ebp
0x180038df7  mov     cs:qword_1806622B8, rbp
0x180038dfe  mov     cs:qword_1806622C0, rbp
0x180038e05  mov     cs:dword_1806622D0, ebp
  ... truncated ...
```
