# shared::ComObjectCreator::DesktopGetHandlerInternal(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,bool,_GUID const &,void * *)

- ea: `0x1800a02d8`
- end: `0x1800a0698`
- name: `?DesktopGetHandlerInternal@ComObjectCreator@shared@@CAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_NAEBU_GUID@@PEAPEAX@Z`
- size: `960`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800a02c0`

## callees

- `0x18000d02c`
- `0x18000f8d0`
- `0x180010fb4`
- `0x180011058`
- `0x1800113bc`
- `0x180030190`
- `0x1800624cc`
- `0x1800a02d8`
- `0x1800a06a0`
- `0x1800a0784`
- `0x1800a09b0`
- `0x1800a0c7c`
- `0x1800a11bc`
- `0x1800a124c`
- `0x1800a1328`
- `0x1801eacec`
- `0x1801f6fb0`
- `0x180209148`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800a0442`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800a0442`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800a0450`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800a0501`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800a0450`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800a0501`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a042b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a042b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a050c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a050c`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x1800a0397`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x1800a0397`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800a064a`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800a064a`
- `ext-ms-win-ole32-bindctx-l1-1-0!CoGetObject` at `0x1800a0481`
- `ext-ms-win-ole32-bindctx-l1-1-0!CoGetObject` at `0x1800a0481`

## string_xrefs

- `0x1800a05b0`: `{"text":"Retrieved COM instance from moniker %ws"}`
- `0x1800a0320`: `.\comobjectcreator.cpp`
- `0x1800a048e`: `.\comobjectcreator.cpp`
- `0x1800a0532`: `.\comobjectcreator.cpp`
- `0x1800a0570`: `Failed to create COM object from class factory for %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall shared::ComObjectCreator::DesktopGetHandlerInternal(__int64 a1, char a2, __int64 a3, __int64 a4)
{
  unsigned int SessionId; // ebx
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  _QWORD *v12; // rdx
  HANDLE CurrentThread; // rax
  const WCHAR *v14; // rcx
  HRESULT Object; // r8d
  LPCWSTR *v16; // rcx
  __int64 v17; // rax
  int v18; // r8d
  LPCWSTR *v19; // rcx
  __int64 v20; // rax
  LPCWSTR *v21; // r8
  void *v22; // rcx
  __int64 result; // rax
  void *ppv; // [rsp+30h] [rbp-D0h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-C8h] BYREF
  const char *v26; // [rsp+40h] [rbp-C0h] BYREF
  int v27; // [rsp+48h] [rbp-B8h]
  _BYTE v28[64]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v29[8]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v30[128]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v31[104]; // [rsp+118h] [rbp+18h] BYREF
  LPCWSTR pszName[2]; // [rsp+180h] [rbp+80h] BYREF
  __m128i si128; // [rsp+190h] [rbp+90h]
  _QWORD v34[3]; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned __int64 v35; // [rsp+1B8h] [rbp+B8h]
  const char *v36; // [rsp+1C0h] [rbp+C0h] BYREF
  int v37; // [rsp+1C8h] [rbp+C8h]
  _BYTE pBindOptions[20]; // [rsp+1F8h] [rbp+F8h] BYREF
  int v39; // [rsp+20Ch] [rbp+10Ch]
  __int128 v40; // [rsp+210h] [rbp+110h]

  SessionId = shared::ComObjectCreator::GetSessionId();
  if ( !(unsigned __int8)IsCoGetObjectPresent() )
  {
    v26 = ".\\comobjectcreator.cpp";
    v27 = 68;
    v9 = cdp::MakeException<cdp::HResultException<-2147418113>,>(&v36, &v26, "CoGetObject function not found");
    cdp::CdpThrow<cdp::HResultException<-2147418113>>(&v26, v9);
  }
  cdp::ToWstring(v34, a1);
  std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>(v29);
  if ( a2 && SessionId - 1 <= 0xFFFFFFFD )
  {
    v10 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v29, L"Session:");
    v11 = std::basic_ostream<unsigned short>::operator<<(v10, SessionId);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v11, L"!");
  }
  v12 = v34;
  if ( v35 > 7 )
    v12 = (_QWORD *)v34[0];
  std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(v29, v12, v34[2]);
  std::basic_stringbuf<unsigned short>::str(v30, pszName);
  *(_QWORD *)pBindOptions = 40;
  *(_QWORD *)&pBindOptions[12] = 0;
  v40 = 0;
  *(_DWORD *)&pBindOptions[8] = 2;
  v39 = 1048599;
  ppv = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle) )
    SetThreadToken(0, 0);
  v14 = (const WCHAR *)pszName;
  if ( si128.m128i_i64[1] > 7uLL )
    v14 = pszName[0];
  Object = CoGetObject(v14, (BIND_OPTS *)pBindOptions, &GUID_00000001_0000_0000_c000_000000000046, &ppv);
  if ( Object < 0 )
  {
    v36 = ".\\comobjectcreator.cpp";
    v37 = 105;
    v16 = pszName;
    if ( si128.m128i_i64[1] > 7uLL )
      v16 = (LPCWSTR *)pszName[0];
    v26 = (const char *)v16;
    v17 = cdp::MakeException<cdp::hresult_exception,unsigned short const *>(
            (unsigned int)v28,
            (unsigned int)&v36,
            Object,
            (unsigned int)"Failed to CoGetObject the system handler class factory for %ws",
            (__int64)&v26);
    cdp::CdpThrow<cdp::hresult_exception>(&v36, v17);
  }
  if ( TokenHandle )
  {
    SetThreadToken(0, TokenHandle);
    CloseHandle(TokenHandle);
  }
  v18 = (*(__int64 (__fastcall **)(void *, _QWORD, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 0, a3, a4);
  if ( v18 < 0 )
  {
    v36 = ".\\comobjectcreator.cpp";
    v37 = 110;
    v19 = pszName;
    if ( si128.m128i_i64[1] > 7uLL )
      v19 = (LPCWSTR *)pszName[0];
    v26 = (const char *)v19;
    v20 = cdp::MakeException<cdp::hresult_exception,unsigned short const *>(
            (unsigned int)v28,
            (unsigned int)&v36,
            v18,
            (unsigned int)"Failed to create COM object from class factory for %ws",
            (__int64)&v26);
    cdp::CdpThrow<cdp::hresult_exception>(&v36, v20);
  }
  v21 = pszName;
  if ( si128.m128i_i64[1] > 7uLL )
    v21 = (LPCWSTR *)pszName[0];
  cdp::detail::StringFormat(&v36, "{\"text\":\"Retrieved COM instance from moniker %ws\"}", v21);
  shared::LogMessage(3, &v36);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v36);
  v22 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v22 + 16LL))(v22);
  }
  if ( si128.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(pszName[0], 2 * si128.m128i_i64[1] + 2);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(pszName[0]) = 0;
  std::basic_ostringstream<unsigned short>::~basic_ostringstream<unsigned short>(v31);
  result = std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v31);
  if ( v35 > 7 )
    return std::_Deallocate<16>(v34[0], 2 * v35 + 2);
  return result;
}

```

## disassembly

```asm
0x1800a02d8  mov     [rsp-8+arg_8], rbx
0x1800a02dd  push    rbp
0x1800a02de  push    rsi
0x1800a02df  push    rdi
0x1800a02e0  push    r14
0x1800a02e2  push    r15
0x1800a02e4  lea     rbp, [rsp-130h]
0x1800a02ec  sub     rsp, 230h
0x1800a02f3  mov     rax, cs:__security_cookie
0x1800a02fa  xor     rax, rsp
0x1800a02fd  mov     [rbp+150h+var_30], rax
0x1800a0304  mov     r15, r9
0x1800a0307  mov     r14, r8
0x1800a030a  mov     dil, dl
0x1800a030d  mov     rsi, rcx
0x1800a0310  call    ?GetSessionId@ComObjectCreator@shared@@CAKXZ; shared::ComObjectCreator::GetSessionId(void)
0x1800a0315  mov     ebx, eax
0x1800a0317  call    IsCoGetObjectPresent
0x1800a031c  test    al, al
0x1800a031e  jnz     short loc_1800A035B
0x1800a0320  lea     rax, aComobjectcreat; ".\\comobjectcreator.cpp"
0x1800a0327  mov     [rsp+250h+var_210], rax
0x1800a032c  mov     [rsp+250h+var_208], 44h ; 'D'
0x1800a0334  lea     r8, aCogetobjectFun; "CoGetObject function not found"
0x1800a033b  lea     rdx, [rsp+250h+var_210]
0x1800a0340  lea     rcx, [rbp+150h+var_90]
0x1800a0347  call    ??$MakeException@V?$HResultException@$0?HPPPAAAB@@cdp@@$$V@cdp@@YA?AV?$HResultException@$0?HPPPAAAB@@0@AEBUCDPSourceLocationInfo@0@PEBD@Z; cdp::MakeException<cdp::HResultException<-2147418113>,>(cdp::CDPSourceLocationInfo const &,char const *)
0x1800a034c  nop
0x1800a034d  mov     rdx, rax
0x1800a0350  lea     rcx, [rsp+250h+var_210]
0x1800a0355  call    ??$CdpThrow@V?$HResultException@$0?HPPPAAAB@@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAV?$HResultException@$0?HPPPAAAB@@0@@Z; cdp::CdpThrow<cdp::HResultException<-2147418113>>(cdp::CDPSourceLocationInfo const &,cdp::HResultException<-2147418113> &&)
0x1800a035b  mov     rdx, rsi
0x1800a035e  lea     rcx, [rbp+150h+var_B0]
0x1800a0365  call    ?ToWstring@cdp@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z; cdp::ToWstring(std::string const &)
0x1800a036a  nop
0x1800a036b  lea     rcx, [rbp+150h+var_1C0]
0x1800a036f  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x1800a0374  nop
0x1800a0375  test    dil, dil
0x1800a0378  jz      short loc_1800A03AC
0x1800a037a  lea     eax, [rbx-1]
0x1800a037d  cmp     eax, 0FFFFFFFDh
0x1800a0380  ja      short loc_1800A03AC
0x1800a0382  lea     rdx, aSession; "Session:"
0x1800a0389  lea     rcx, [rbp+150h+var_1C0]
0x1800a038d  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1800a0392  mov     edx, ebx
0x1800a0394  mov     rcx, rax
0x1800a0397  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x1800a039d  mov     rcx, rax
0x1800a03a0  lea     rdx, asc_1803A4168; "!"
0x1800a03a7  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1800a03ac  lea     rdx, [rbp+150h+var_B0]
0x1800a03b3  cmp     [rbp+150h+var_98], 7
0x1800a03bb  cmova   rdx, [rbp+150h+var_B0]
0x1800a03c3  mov     r8, [rbp+150h+var_A0]
0x1800a03ca  lea     rcx, [rbp+150h+var_1C0]
0x1800a03ce  call    ??$_Insert_string@GU?$char_traits@G@std@@_K@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@QEBG_K@Z; std::_Insert_string<ushort,std::char_traits<ushort>,unsigned __int64>(std::basic_ostream<ushort> &,ushort const * const,unsigned __int64)
0x1800a03d3  lea     rdx, [rbp+150h+pszName]
0x1800a03da  lea     rcx, [rbp+150h+var_1B8]
0x1800a03de  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x1800a03e3  nop
0x1800a03e4  mov     qword ptr [rbp+150h+pBindOptions], 28h ; '('
0x1800a03ef  mov     qword ptr [rbp+150h+pBindOptions+0Ch], 0
0x1800a03fa  xorps   xmm0, xmm0
0x1800a03fd  movdqu  [rbp+150h+var_40], xmm0
0x1800a0405  mov     dword ptr [rbp+150h+pBindOptions+8], 2
0x1800a040f  mov     [rbp+150h+var_44], 100017h
0x1800a0419  mov     [rsp+250h+ppv], 0
0x1800a0422  mov     [rsp+250h+TokenHandle], 0
0x1800a042b  call    cs:__imp_GetCurrentThread
0x1800a0431  mov     rcx, rax; ThreadHandle
0x1800a0434  lea     r9, [rsp+250h+TokenHandle]; TokenHandle
0x1800a0439  mov     edx, 4; DesiredAccess
0x1800a043e  lea     r8d, [rdx-3]; OpenAsSelf
0x1800a0442  call    cs:__imp_OpenThreadToken
0x1800a0448  test    eax, eax
0x1800a044a  jz      short loc_1800A0457
0x1800a044c  xor     edx, edx; Token
0x1800a044e  xor     ecx, ecx; Thread
0x1800a0450  call    cs:__imp_SetThreadToken
0x1800a0456  nop
0x1800a0457  lea     rcx, [rbp+150h+pszName]
0x1800a045e  cmp     [rbp+150h+var_B8], 7
0x1800a0466  cmova   rcx, [rbp+150h+pszName]; pszName
0x1800a046e  lea     r9, [rsp+250h+ppv]; ppv
0x1800a0473  lea     r8, _GUID_00000001_0000_0000_c000_000000000046; riid
0x1800a047a  lea     rdx, [rbp+150h+pBindOptions]; pBindOptions
0x1800a0481  call    cs:__imp_CoGetObject
0x1800a0487  mov     r8d, eax
0x1800a048a  test    eax, eax
0x1800a048c  jns     short loc_1800A04F5
0x1800a048e  lea     rax, aComobjectcreat; ".\\comobjectcreator.cpp"
0x1800a0495  mov     [rbp+150h+var_90], rax
0x1800a049c  mov     [rbp+150h+var_88], 69h ; 'i'
0x1800a04a6  lea     rcx, [rbp+150h+pszName]
0x1800a04ad  cmp     [rbp+150h+var_B8], 7
0x1800a04b5  cmova   rcx, [rbp+150h+pszName]
0x1800a04bd  mov     [rsp+250h+var_210], rcx
0x1800a04c2  lea     rax, [rsp+250h+var_210]
0x1800a04c7  mov     [rsp+250h+var_230], rax
0x1800a04cc  lea     r9, aFailedToCogeto; "Failed to CoGetObject the system handle"...
0x1800a04d3  lea     rdx, [rbp+150h+var_90]
0x1800a04da  lea     rcx, [rsp+250h+var_200]
0x1800a04df  call    ??$MakeException@Vhresult_exception@cdp@@PEBG@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD$$QEAPEBG@Z; cdp::MakeException<cdp::hresult_exception,ushort const *>(cdp::CDPSourceLocationInfo const &,int,char const *,ushort const * &&)
0x1800a04e4  nop
0x1800a04e5  mov     rdx, rax
0x1800a04e8  lea     rcx, [rbp+150h+var_90]
0x1800a04ef  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1800a04f5  mov     rdx, [rsp+250h+TokenHandle]; Token
0x1800a04fa  test    rdx, rdx
0x1800a04fd  jz      short loc_1800A0512
0x1800a04ff  xor     ecx, ecx; Thread
0x1800a0501  call    cs:__imp_SetThreadToken
0x1800a0507  mov     rcx, [rsp+250h+TokenHandle]; hObject
0x1800a050c  call    cs:__imp_CloseHandle
0x1800a0512  mov     rcx, [rsp+250h+ppv]
0x1800a0517  mov     rax, [rcx]
0x1800a051a  mov     r9, r15
0x1800a051d  mov     r8, r14
0x1800a0520  xor     edx, edx
0x1800a0522  mov     rax, [rax+18h]
0x1800a0526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a052b  mov     r8d, eax
0x1800a052e  test    eax, eax
0x1800a0530  jns     short loc_1800A0599
0x1800a0532  lea     rax, aComobjectcreat; ".\\comobjectcreator.cpp"
0x1800a0539  mov     [rbp+150h+var_90], rax
0x1800a0540  mov     [rbp+150h+var_88], 6Eh ; 'n'
0x1800a054a  lea     rcx, [rbp+150h+pszName]
0x1800a0551  cmp     [rbp+150h+var_B8], 7
0x1800a0559  cmova   rcx, [rbp+150h+pszName]
0x1800a0561  mov     [rsp+250h+var_210], rcx
0x1800a0566  lea     rax, [rsp+250h+var_210]
0x1800a056b  mov     [rsp+250h+var_230], rax
0x1800a0570  lea     r9, aFailedToCreate_10; "Failed to create COM object from class "...
0x1800a0577  lea     rdx, [rbp+150h+var_90]
0x1800a057e  lea     rcx, [rsp+250h+var_200]
0x1800a0583  call    ??$MakeException@Vhresult_exception@cdp@@PEBG@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD$$QEAPEBG@Z; cdp::MakeException<cdp::hresult_exception,ushort const *>(cdp::CDPSourceLocationInfo const &,int,char const *,ushort const * &&)
0x1800a0588  nop
0x1800a0589  mov     rdx, rax
0x1800a058c  lea     rcx, [rbp+150h+var_90]
0x1800a0593  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1800a0599  lea     r8, [rbp+150h+pszName]
0x1800a05a0  cmp     [rbp+150h+var_B8], 7
0x1800a05a8  cmova   r8, [rbp+150h+pszName]
0x1800a05b0  lea     rdx, aTextRetrievedC; "{\"text\":\"Retrieved COM instance from"...
0x1800a05b7  lea     rcx, [rbp+150h+var_90]
0x1800a05be  call    ?StringFormat@detail@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDZZ; cdp::detail::StringFormat(char const *,...)
0x1800a05c3  nop
0x1800a05c4  lea     rdx, [rbp+150h+var_90]
0x1800a05cb  mov     ecx, 3
0x1800a05d0  call    ?LogMessage@shared@@YAXW4CDPLogLevel@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; shared::LogMessage(CDPLogLevel,std::string &)
0x1800a05d5  nop
0x1800a05d6  lea     rcx, [rbp+150h+var_90]; void *
0x1800a05dd  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800a05e2  nop
0x1800a05e3  mov     rcx, [rsp+250h+ppv]
0x1800a05e8  test    rcx, rcx
0x1800a05eb  jz      short loc_1800A0603
0x1800a05ed  mov     [rsp+250h+ppv], 0
0x1800a05f6  mov     rax, [rcx]
0x1800a05f9  mov     rax, [rax+10h]
0x1800a05fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0602  nop
0x1800a0603  mov     rdx, [rbp+150h+var_B8]
0x1800a060a  cmp     rdx, 7
0x1800a060e  jbe     short loc_1800A0624
0x1800a0610  lea     rdx, ds:2[rdx*2]
0x1800a0618  mov     rcx, [rbp+150h+pszName]
0x1800a061f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800a0624  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1800a062c  movdqu  xmmword ptr [rbp+90h], xmm0
0x1800a0634  xor     eax, eax
0x1800a0636  mov     word ptr [rbp+150h+pszName], ax
0x1800a063d  lea     rcx, [rbp+150h+var_138]
0x1800a0641  call    ??1?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEAA@XZ; std::basic_ostringstream<ushort>::~basic_ostringstream<ushort>(void)
0x1800a0646  lea     rcx, [rbp+150h+var_138]
0x1800a064a  call    cs:__imp_??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ios<ushort>::~basic_ios<ushort,std::char_traits<ushort>>(void)
0x1800a0650  nop
0x1800a0651  mov     rdx, [rbp+150h+var_98]
0x1800a0658  cmp     rdx, 7
0x1800a065c  jbe     short loc_1800A0672
0x1800a065e  lea     rdx, ds:2[rdx*2]
0x1800a0666  mov     rcx, [rbp+150h+var_B0]
0x1800a066d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800a0672  mov     rcx, [rbp+150h+var_30]
0x1800a0679  xor     rcx, rsp; StackCookie
0x1800a067c  call    __security_check_cookie
0x1800a0681  mov     rbx, [rsp+250h+arg_8]
0x1800a0689  add     rsp, 230h
0x1800a0690  pop     r15
0x1800a0692  pop     r14
0x1800a0694  pop     rdi
0x1800a0695  pop     rsi
0x1800a0696  pop     rbp
0x1800a0697  retn
```
