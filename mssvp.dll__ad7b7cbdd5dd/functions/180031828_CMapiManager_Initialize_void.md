# CMapiManager::Initialize(void)

- ea: `0x180031828`
- end: `0x18003194b`
- name: `?Initialize@CMapiManager@@AEAAJXZ`
- size: `291`
- prototype: `__int64 __fastcall(CMapiManager *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800314c0`

## callees

- `0x180004850`
- `0x1800048c0`
- `0x180018758`
- `0x18002d33c`
- `0x18002d37c`
- `0x18002ef70`
- `0x18002f7f8`
- `0x180030dbc`
- `0x180031828`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180031878`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180031878`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031890`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800318a7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800318fd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031914`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031890`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800318a7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800318fd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031914`

## string_xrefs

- `0x18003189d`: `GetDefCachedModeDownloadPubFoldFavs@4`
- `0x1800318f3`: `HrOpenOfflineObj@20`
- `0x18003186f`: `msmapi32.dll`
- `0x180031886`: `GetDefCachedMode@4`
- `0x18003190a`: `WrapCompressedRTFStreamEx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMapiManager::Initialize(HMODULE *this)
{
  DWORD MapiIdleThread; // edi
  HMODULE *v3; // rsi
  _QWORD *v4; // rax
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF
  __int64 v7; // [rsp+38h] [rbp+10h] BYREF

  CLogger::Info(L"CMapiManager::Initialize() Enter");
  MapiIdleThread = 0;
  if ( *((_DWORD *)this + 38) )
  {
    MapiIdleThread = CMapiManager::CreateMapiIdleThread((CMapiManager *)this);
    *((_DWORD *)this + 40) = (MapiIdleThread & 0x80000000) == 0;
  }
  v3 = this + 28;
  if ( GetModuleHandleExW(0, L"msmapi32.dll", this + 28) )
  {
    this[29] = (HMODULE)GetProcAddress(*v3, "GetDefCachedMode@4");
    this[30] = (HMODULE)GetProcAddress(*v3, "GetDefCachedModeDownloadPubFoldFavs@4");
    ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(&v6);
    if ( !(unsigned int)CMapiSupport::GetInstalledOutlookVersion(&v6) )
    {
      v4 = ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
             &v7,
             &v6);
      if ( CMapiSupport::ConvertToIntVersion(v4) >= 0xB000000000000LL )
      {
        this[31] = (HMODULE)GetProcAddress(*v3, "HrOpenOfflineObj@20");
        this[32] = (HMODULE)GetProcAddress(*v3, "WrapCompressedRTFStreamEx");
      }
    }
    ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&v6);
  }
  CLogger::Info(MapiIdleThread, L"CMapiManager::Initialize() Exit");
  return MapiIdleThread;
}

```

## disassembly

```asm
0x180031828  mov     [rsp+arg_10], rbx
0x18003182d  mov     [rsp+arg_18], rsi
0x180031832  push    rdi
0x180031833  sub     rsp, 20h
0x180031837  mov     rbx, rcx
0x18003183a  lea     rcx, aCmapimanagerIn_2; "CMapiManager::Initialize() Enter"
0x180031841  call    ?Info@CLogger@@SAXPEB_WZZ; CLogger::Info(wchar_t const *,...)
0x180031846  xor     edi, edi
0x180031848  cmp     [rbx+98h], edi
0x18003184e  jz      short loc_180031865
0x180031850  mov     rcx, rbx; this
0x180031853  call    ?CreateMapiIdleThread@CMapiManager@@AEAAJXZ; CMapiManager::CreateMapiIdleThread(void)
0x180031858  mov     edi, eax
0x18003185a  not     eax
0x18003185c  shr     eax, 1Fh
0x18003185f  mov     [rbx+0A0h], eax
0x180031865  lea     rsi, [rbx+0E0h]
0x18003186c  mov     r8, rsi; phModule
0x18003186f  lea     rdx, aMsmapi32Dll; "msmapi32.dll"
0x180031876  xor     ecx, ecx; dwFlags
0x180031878  call    cs:__imp_GetModuleHandleExW
0x18003187e  test    eax, eax
0x180031880  jz      loc_18003192B
0x180031886  lea     rdx, aGetdefcachedmo; "GetDefCachedMode@4"
0x18003188d  mov     rcx, [rsi]; hModule
0x180031890  call    cs:__imp_GetProcAddress
0x180031896  mov     [rbx+0E8h], rax
0x18003189d  lea     rdx, aGetdefcachedmo_0; "GetDefCachedModeDownloadPubFoldFavs@4"
0x1800318a4  mov     rcx, [rsi]; hModule
0x1800318a7  call    cs:__imp_GetProcAddress
0x1800318ad  mov     [rbx+0F0h], rax
0x1800318b4  lea     rcx, [rsp+28h+arg_0]
0x1800318b9  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x1800318be  nop
0x1800318bf  lea     rcx, [rsp+28h+arg_0]
0x1800318c4  call    ?GetInstalledOutlookVersion@CMapiSupport@@SAJAEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z; CMapiSupport::GetInstalledOutlookVersion(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)
0x1800318c9  test    eax, eax
0x1800318cb  jnz     short loc_180031921
0x1800318cd  lea     rdx, [rsp+28h+arg_0]
0x1800318d2  lea     rcx, [rsp+28h+arg_8]
0x1800318d7  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x1800318dc  mov     rcx, rax
0x1800318df  call    ?ConvertToIntVersion@CMapiSupport@@SA_JV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z; CMapiSupport::ConvertToIntVersion(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>)
0x1800318e4  mov     rcx, 0B000000000000h
0x1800318ee  cmp     rax, rcx
0x1800318f1  jl      short loc_180031921
0x1800318f3  lea     rdx, aHropenofflineo; "HrOpenOfflineObj@20"
0x1800318fa  mov     rcx, [rsi]; hModule
0x1800318fd  call    cs:__imp_GetProcAddress
0x180031903  mov     [rbx+0F8h], rax
0x18003190a  lea     rdx, aWrapcompressed; "WrapCompressedRTFStreamEx"
0x180031911  mov     rcx, [rsi]; hModule
0x180031914  call    cs:__imp_GetProcAddress
0x18003191a  mov     [rbx+100h], rax
0x180031921  lea     rcx, [rsp+28h+arg_0]
0x180031926  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x18003192b  lea     rdx, aCmapimanagerIn_1; "CMapiManager::Initialize() Exit"
0x180031932  mov     ecx, edi; int
0x180031934  call    ?Info@CLogger@@SAXJPEB_WZZ; CLogger::Info(long,wchar_t const *,...)
0x180031939  mov     eax, edi
0x18003193b  mov     rbx, [rsp+28h+arg_10]
0x180031940  mov     rsi, [rsp+28h+arg_18]
0x180031945  add     rsp, 20h
0x180031949  pop     rdi
0x18003194a  retn
```
