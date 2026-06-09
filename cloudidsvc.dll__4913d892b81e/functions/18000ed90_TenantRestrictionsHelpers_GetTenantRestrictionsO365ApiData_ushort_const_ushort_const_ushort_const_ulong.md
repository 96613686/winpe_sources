# TenantRestrictionsHelpers::GetTenantRestrictionsO365ApiData(ushort const *,ushort const *,ushort const *,ulong)

- ea: `0x18000ed90`
- end: `0x18000f4a5`
- name: `?GetTenantRestrictionsO365ApiData@TenantRestrictionsHelpers@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG00K@Z`
- size: `1813`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, __int64, __int64, int)`
- caller_count: `2`
- callee_count: `27`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000b67c`
- `0x18000e668`

## callees

- `0x180001278`
- `0x180001348`
- `0x180001a50`
- `0x180003e58`
- `0x180003eac`
- `0x180008570`
- `0x180008724`
- `0x180008c18`
- `0x180008d64`
- `0x180009014`
- `0x180009da8`
- `0x18000c338`
- `0x18000c400`
- `0x18000c41c`
- `0x18000c498`
- `0x18000d114`
- `0x18000d2c0`
- `0x18000d824`
- `0x18000dd8c`
- `0x18000de34`
- `0x18000ed90`
- `0x18000fc08`
- `0x18000fc3c`
- `0x18000fc64`
- `0x18000fdc4`
- `0x18000fdd0`
- `0x18000fe24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f13e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f13e`
- `WINHTTP!WinHttpConnect` at `0x18000ef7c`
- `WINHTTP!WinHttpConnect` at `0x18000ef7c`
- `WINHTTP!WinHttpSendRequest` at `0x18000f029`
- `WINHTTP!WinHttpSendRequest` at `0x18000f029`
- `WINHTTP!WinHttpReceiveResponse` at `0x18000f043`
- `WINHTTP!WinHttpReceiveResponse` at `0x18000f043`
- `WINHTTP!WinHttpOpen` at `0x18000ef44`
- `WINHTTP!WinHttpOpen` at `0x18000ef44`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x18000f1d3`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x18000f1d3`
- `WINHTTP!WinHttpQueryHeaders` at `0x18000f081`
- `WINHTTP!WinHttpQueryHeaders` at `0x18000f134`
- `WINHTTP!WinHttpQueryHeaders` at `0x18000f19a`
- `WINHTTP!WinHttpQueryHeaders` at `0x18000f081`
- `WINHTTP!WinHttpQueryHeaders` at `0x18000f134`
- `WINHTTP!WinHttpQueryHeaders` at `0x18000f19a`
- `WINHTTP!WinHttpReadData` at `0x18000f228`
- `WINHTTP!WinHttpReadData` at `0x18000f228`
- `WINHTTP!WinHttpOpenRequest` at `0x18000efe7`
- `WINHTTP!WinHttpOpenRequest` at `0x18000efe7`

## string_xrefs

- `0x18000ee6c`: `endpoints.office.com`
- `0x18000ef75`: `endpoints.office.com`
- `0x18000f393`: `onecoreuap\ds\ext\common\ntservice\lib\utilities.cpp`
- `0x18000f3ac`: `onecoreuap\ds\ext\common\ntservice\lib\utilities.cpp`
- `0x18000f3be`: `onecoreuap\ds\ext\common\ntservice\lib\utilities.cpp`
- `0x18000f3d0`: `onecoreuap\ds\ext\common\ntservice\lib\utilities.cpp`
- `0x18000f3e5`: `onecoreuap\ds\ext\common\ntservice\lib\utilities.cpp`
- `0x18000f3f7`: `onecoreuap\ds\ext\common\ntservice\lib\utilities.cpp`
- `0x18000f409`: `onecoreuap\ds\ext\common\ntservice\lib\utilities.cpp`
- `0x18000f41b`: `onecoreuap\ds\ext\common\ntservice\lib\utilities.cpp`
- `0x18000f42d`: `onecoreuap\ds\ext\common\ntservice\lib\utilities.cpp`
- `0x18000f494`: `onecoreuap\ds\ext\common\ntservice\lib\utilities.cpp`

## pseudocode

```c
_QWORD *__fastcall TenantRestrictionsHelpers::GetTenantRestrictionsO365ApiData(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5)
{
  __int64 v9; // rbx
  __int64 v10; // r8
  __int64 v11; // r8
  __int64 v12; // rax
  __int64 v13; // r14
  HINTERNET v14; // rax
  const char *v15; // r9
  HINTERNET v16; // rax
  const char *v17; // r9
  const WCHAR *v18; // rax
  HINTERNET v19; // r10
  HINTERNET v20; // rax
  const char *v21; // r9
  void *v22; // rbx
  const char *v23; // r9
  const char *v24; // r9
  const char *v25; // r9
  int v26; // ecx
  int v27; // r8d
  int v28; // r9d
  void *v29; // rdx
  unsigned int v30; // r8d
  const char *v31; // r9
  void *v32; // rax
  LPVOID v33; // r9
  unsigned int v34; // eax
  const char *v35; // r9
  const char *v36; // r9
  const char *v37; // r9
  __int64 v38; // r8
  LPVOID v39; // rcx
  __int64 v40; // r9
  __int64 v41; // rdx
  const unsigned __int16 *v43; // rax
  __int64 v44; // rcx
  unsigned int v45; // eax
  void *v46; // rdx
  unsigned int v47; // r8d
  int dwFlags; // [rsp+20h] [rbp-E0h]
  int dwFlagsa; // [rsp+20h] [rbp-E0h]
  signed int Buffer; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v51; // [rsp+44h] [rbp-BCh] BYREF
  DWORD dwNumberOfBytesAvailable; // [rsp+48h] [rbp-B8h] BYREF
  DWORD dwNumberOfBytesRead; // [rsp+4Ch] [rbp-B4h] BYREF
  HINTERNET hRequest; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwBufferLength; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v56; // [rsp+60h] [rbp-A0h] BYREF
  HINTERNET hSession; // [rsp+68h] [rbp-98h] BYREF
  __int128 v58; // [rsp+70h] [rbp-90h] BYREF
  __int64 v59; // [rsp+80h] [rbp-80h]
  __int64 v60; // [rsp+90h] [rbp-70h] BYREF
  __int64 v61; // [rsp+98h] [rbp-68h] BYREF
  LPCWSTR ppwszAcceptTypes[2]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v63[16]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v64; // [rsp+C0h] [rbp-40h]
  _BYTE v65[32]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v66[30]; // [rsp+F0h] [rbp-10h] BYREF
  char v67; // [rsp+1E0h] [rbp+E0h]
  int v68; // [rsp+1E4h] [rbp+E4h]
  int v69; // [rsp+1F8h] [rbp+F8h]
  int v70; // [rsp+1FCh] [rbp+FCh]
  __int128 v71; // [rsp+200h] [rbp+100h] BYREF
  __m128i si128; // [rsp+210h] [rbp+110h]
  __int128 v73; // [rsp+220h] [rbp+120h]
  __m128i v74; // [rsp+230h] [rbp+130h]
  LPVOID lpBuffer[2]; // [rsp+240h] [rbp+140h] BYREF
  __int64 v76; // [rsp+250h] [rbp+150h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  lpBuffer[0] = a1;
  std::wstring::wstring(v63, a2);
  v9 = -1;
  if ( a3 )
  {
    std::wstring::_Append<unsigned short>(v63, L"/", 1);
    v10 = -1;
    do
      ++v10;
    while ( *(_WORD *)(a3 + 2 * v10) );
    std::wstring::_Append<unsigned short>(v63, a3, v10);
  }
  std::wstring::_Append<unsigned short>(v63, L"?", 1);
  std::wstring::_Append<unsigned short>(v63, L"ClientRequestId", 15);
  std::wstring::_Append<unsigned short>(v63, L"=", 1);
  v11 = -1;
  do
    ++v11;
  while ( *(_WORD *)(a4 + 2 * v11) );
  std::wstring::_Append<unsigned short>(v63, a4, v11);
  std::wstring::wstring(v65, L"endpoints.office.com");
  v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v63);
  std::wstring::_Append<unsigned short>(v65, v12, v64);
  v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v65);
  TenantRestrictionsLoggers::BaseLogger::BaseLogger((TenantRestrictionsLoggers::BaseLogger *)v66, 0);
  v66[0] = &TenantRestrictionsLoggers::GetO365APIDataLogger::`vftable';
  v70 = 0;
  v71 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v71) = 0;
  v73 = 0;
  v74 = si128;
  LOWORD(v73) = 0;
  do
    ++v9;
  while ( *(_WORD *)(v13 + 2 * v9) );
  std::wstring::_Assign<unsigned short>(&v71, v13, v9);
  v69 = a5;
  hSession = 0;
  v56 = 0;
  v14 = WinHttpOpen(L"TenantRestrictions", 4u, 0, 0, 0);
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &hSession,
    v14);
  if ( !hSession )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\utilities.cpp",
      v15);
  v16 = WinHttpConnect(hSession, L"endpoints.office.com", 0x1BBu, 0);
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &v56,
    v16);
  if ( !v56 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x2C,
      (unsigned int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\utilities.cpp",
      v17);
  hRequest = 0;
  ppwszAcceptTypes[0] = L"*/*";
  ppwszAcceptTypes[1] = 0;
  v18 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v63);
  v20 = WinHttpOpenRequest(v19, L"GET", v18, 0, 0, ppwszAcceptTypes, 0x800100u);
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &hRequest,
    v20);
  v22 = hRequest;
  if ( !hRequest )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x39,
      (unsigned int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\utilities.cpp",
      v21);
  if ( !WinHttpSendRequest(hRequest, 0, 0, 0, 0, 0, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x41,
      (unsigned int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\utilities.cpp",
      v23);
  if ( !WinHttpReceiveResponse(v22, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x43,
      (unsigned int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\utilities.cpp",
      v24);
  Buffer = 0;
  dwBufferLength = 4;
  if ( !WinHttpQueryHeaders(v22, 0x20000013u, 0, &Buffer, &dwBufferLength, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x4D,
      (unsigned int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\utilities.cpp",
      v25);
  if ( (unsigned int)dword_180019048 > 5 && (unsigned __int8)tlgKeywordOn(retaddr, 0x400000000000LL) )
  {
    v60 = a2;
    v61 = a3;
    v51 = Buffer;
    lpBuffer[0] = (LPVOID)50331648;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v26,
      (unsigned int)&byte_180015367,
      v27,
      v28,
      (__int64)lpBuffer,
      (__int64)&v51,
      (__int64)&v61,
      (__int64)&v60);
  }
  if ( Buffer != 200 )
  {
    v51 = 0;
    if ( WinHttpQueryHeaders(v22, 0x16u, 0, 0, &v51, 0) || GetLastError() == 122 )
    {
      std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>>>(lpBuffer);
      std::vector<unsigned short>::resize(lpBuffer, v51);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::get(lpBuffer);
      v32 = (void *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::get(&hRequest);
      v34 = WinHttpQueryHeaders(v32, 0x16u, 0, v33, &v51, 0);
      if ( (unsigned int)wil::verify_BOOL<int>(v34) )
      {
        v43 = (const unsigned __int16 *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::get(lpBuffer);
        TenantRestrictionsLoggers::GetO365APIDataLogger::RecordHttpError(
          (TenantRestrictionsLoggers::GetO365APIDataLogger *)v66,
          Buffer,
          v43);
        v44 = (unsigned int)Buffer;
        if ( Buffer > 0 )
          v44 = (unsigned __int16)Buffer | 0x80070000;
        v45 = wil::verify_BOOL<int>(v44);
        wil::details::in1diag3::Throw_Hr(retaddr, v46, v47, (const char *)v45, dwFlagsa);
      }
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x71,
        (unsigned int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\utilities.cpp",
        v35);
    }
    wil::details::in1diag3::Throw_GetLastError(retaddr, v29, v30, v31);
  }
  dwNumberOfBytesAvailable = 0;
  dwNumberOfBytesRead = 0;
  v58 = 0;
  v59 = 0;
  do
  {
    if ( !WinHttpQueryDataAvailable(v22, &dwNumberOfBytesAvailable) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x7F,
        (unsigned int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\utilities.cpp",
        v36);
    *(_OWORD *)lpBuffer = 0;
    v76 = 0;
    if ( dwNumberOfBytesAvailable )
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(lpBuffer);
    if ( !WinHttpReadData(v22, lpBuffer[0], LODWORD(lpBuffer[1]) - LODWORD(lpBuffer[0]), &dwNumberOfBytesRead) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x87,
        (unsigned int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\utilities.cpp",
        v37);
    if ( dwNumberOfBytesAvailable != dwNumberOfBytesRead )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x89,
        (unsigned int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\utilities.cpp",
        (const char *)0x1E,
        dwFlags);
    std::vector<unsigned char>::_Insert_counted_range<unsigned char *>(
      &v58,
      *((_QWORD *)&v58 + 1),
      lpBuffer[0],
      (char *)lpBuffer[1] - (char *)lpBuffer[0]);
    v39 = lpBuffer[0];
    if ( lpBuffer[0] )
      std::_Deallocate<16>(lpBuffer[0], v76 - (unsigned __int64)lpBuffer[0]);
  }
  while ( dwNumberOfBytesAvailable );
  v40 = *((_QWORD *)&v58 + 1);
  v41 = v58;
  *(_OWORD *)a1 = 0;
  a1[2] = 0;
  a1[3] = 0;
  if ( v41 == v40 )
  {
    a1[3] = 7;
    *(_WORD *)a1 = 0;
  }
  else
  {
    std::wstring::_Construct_from_iter<unsigned char *,unsigned char *,unsigned __int64>(a1, v41, v38, v40 - v41);
  }
  if ( !a1[2] && (Microsoft_Windows_TenantRestrictionsEnableBits & 0x10) != 0 )
    McGenEventWrite_EventWriteTransfer(v39, EmptyO365APIResponse, v38, 1, lpBuffer);
  v67 = 1;
  v68 = 0;
  if ( (_QWORD)v58 )
  {
    std::_Deallocate<16>(v58, v59 - v58);
    v58 = 0;
    v59 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hRequest);
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v56);
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hSession);
  TenantRestrictionsLoggers::GetO365APIDataLogger::~GetO365APIDataLogger((TenantRestrictionsLoggers::GetO365APIDataLogger *)v66);
  std::wstring::_Tidy_deallocate(v65);
  std::wstring::_Tidy_deallocate(v63);
  return a1;
}

```

## disassembly

```asm
0x18000ed90  push    rbp
0x18000ed92  push    rbx
0x18000ed93  push    rsi
0x18000ed94  push    rdi
0x18000ed95  push    r12
0x18000ed97  push    r13
0x18000ed99  push    r14
0x18000ed9b  push    r15
0x18000ed9d  lea     rbp, [rsp-168h]
0x18000eda5  sub     rsp, 268h
0x18000edac  mov     rax, cs:__security_cookie
0x18000edb3  xor     rax, rsp
0x18000edb6  mov     [rbp+1A0h+var_48], rax
0x18000edbd  mov     r14, r9
0x18000edc0  mov     rsi, r8
0x18000edc3  mov     r15, rdx
0x18000edc6  mov     rdi, rcx
0x18000edc9  mov     [rbp+1A0h+lpBuffer], rcx
0x18000edd0  xor     r12d, r12d
0x18000edd3  lea     rcx, [rbp+1A0h+var_1F0]
0x18000edd7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000eddc  nop
0x18000eddd  lea     r13d, [r12+1]
0x18000ede2  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000ede6  test    rsi, rsi
0x18000ede9  jz      short loc_18000EE17
0x18000edeb  mov     r8d, r13d
0x18000edee  lea     rdx, asc_180013F60; "/"
0x18000edf5  lea     rcx, [rbp+1A0h+var_1F0]
0x18000edf9  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000edfe  mov     r8, rbx
0x18000ee01  inc     r8
0x18000ee04  cmp     [rsi+r8*2], r12w
0x18000ee09  jnz     short loc_18000EE01
0x18000ee0b  mov     rdx, rsi
0x18000ee0e  lea     rcx, [rbp+1A0h+var_1F0]
0x18000ee12  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000ee17  mov     r8, r13
0x18000ee1a  lea     rdx, asc_180014D44; "?"
0x18000ee21  lea     rcx, [rbp+1A0h+var_1F0]
0x18000ee25  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000ee2a  mov     r8d, 0Fh
0x18000ee30  lea     rdx, aClientrequesti; "ClientRequestId"
0x18000ee37  lea     rcx, [rbp+1A0h+var_1F0]
0x18000ee3b  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000ee40  mov     r8, r13
0x18000ee43  lea     rdx, asc_180014D48; "="
0x18000ee4a  lea     rcx, [rbp+1A0h+var_1F0]
0x18000ee4e  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000ee53  mov     r8, rbx
0x18000ee56  inc     r8
0x18000ee59  cmp     [r14+r8*2], r12w
0x18000ee5e  jnz     short loc_18000EE56
0x18000ee60  mov     rdx, r14
0x18000ee63  lea     rcx, [rbp+1A0h+var_1F0]
0x18000ee67  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000ee6c  lea     rdx, pswzServerName; "endpoints.office.com"
0x18000ee73  lea     rcx, [rbp+1A0h+var_1D0]
0x18000ee77  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000ee7c  nop
0x18000ee7d  lea     rcx, [rbp+1A0h+var_1F0]
0x18000ee81  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000ee86  mov     rdx, rax
0x18000ee89  mov     r8, [rbp+1A0h+var_1E0]
0x18000ee8d  lea     rcx, [rbp+1A0h+var_1D0]
0x18000ee91  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000ee96  lea     rcx, [rbp+1A0h+var_1D0]
0x18000ee9a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000ee9f  mov     r14, rax
0x18000eea2  xor     edx, edx; char *
0x18000eea4  lea     rcx, [rbp+1A0h+var_1B0]; this
0x18000eea8  call    ??0BaseLogger@TenantRestrictionsLoggers@@QEAA@PEBD@Z; TenantRestrictionsLoggers::BaseLogger::BaseLogger(char const *)
0x18000eead  nop
0x18000eeae  lea     rax, ??_7GetO365APIDataLogger@TenantRestrictionsLoggers@@6B@; const TenantRestrictionsLoggers::GetO365APIDataLogger::`vftable'
0x18000eeb5  mov     [rbp+1A0h+var_1B0], rax
0x18000eeb9  mov     [rbp+1A0h+var_A4], r12d
0x18000eec0  xorps   xmm0, xmm0
0x18000eec3  movups  [rbp+1A0h+var_A0], xmm0
0x18000eeca  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18000eed2  movdqa  [rbp+1A0h+var_90], xmm1
0x18000eeda  mov     word ptr [rbp+1A0h+var_A0], r12w
0x18000eee2  movups  [rbp+1A0h+var_80], xmm0
0x18000eee9  movdqa  [rbp+1A0h+var_70], xmm1
0x18000eef1  mov     word ptr [rbp+1A0h+var_80], r12w
0x18000eef9  inc     rbx
0x18000eefc  cmp     [r14+rbx*2], r12w
0x18000ef01  jnz     short loc_18000EEF9
0x18000ef03  mov     r8, rbx
0x18000ef06  mov     rdx, r14
0x18000ef09  lea     rcx, [rbp+1A0h+var_A0]
0x18000ef10  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18000ef15  mov     eax, [rbp+1A0h+arg_20]
0x18000ef1b  mov     [rbp+1A0h+var_A8], eax
0x18000ef21  mov     [rsp+2A0h+hSession], r12
0x18000ef26  mov     [rsp+2A0h+var_240], r12
0x18000ef2b  mov     [rsp+2A0h+dwFlags], r12d; dwFlags
0x18000ef30  xor     r9d, r9d; pszProxyBypassW
0x18000ef33  xor     r8d, r8d; pszProxyW
0x18000ef36  lea     r14d, [r9+4]
0x18000ef3a  mov     edx, r14d; dwAccessType
0x18000ef3d  lea     rcx, pszAgentW; "TenantRestrictions"
0x18000ef44  call    cs:__imp_WinHttpOpen
0x18000ef4a  mov     rdx, rax
0x18000ef4d  lea     rcx, [rsp+2A0h+hSession]
0x18000ef52  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?WinHttpCloseHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18000ef57  mov     rax, [rbp+1A8h]
0x18000ef5e  mov     rcx, [rsp+2A0h+hSession]; hSession
0x18000ef63  test    rcx, rcx
0x18000ef66  jz      loc_18000F3D0
0x18000ef6c  mov     r8d, 1BBh; nServerPort
0x18000ef72  xor     r9d, r9d; dwReserved
0x18000ef75  lea     rdx, pswzServerName; "endpoints.office.com"
0x18000ef7c  call    cs:__imp_WinHttpConnect
0x18000ef82  mov     rdx, rax
0x18000ef85  lea     rcx, [rsp+2A0h+var_240]
0x18000ef8a  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?WinHttpCloseHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18000ef8f  mov     rcx, [rbp+1A8h]; this
0x18000ef96  mov     r10, [rsp+2A0h+var_240]
0x18000ef9b  test    r10, r10
0x18000ef9e  jz      loc_18000F3E5
0x18000efa4  mov     [rsp+2A0h+hRequest], r12
0x18000efa9  lea     rax, asc_180014D88; "*/*"
0x18000efb0  mov     [rbp+1A0h+var_200], rax
0x18000efb4  mov     [rbp+1A0h+var_1F8], r12
0x18000efb8  lea     rcx, [rbp+1A0h+var_1F0]
0x18000efbc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000efc1  mov     r8, rax; pwszObjectName
0x18000efc4  mov     [rsp+2A0h+var_270], 800100h; dwFlags
0x18000efcc  lea     rax, [rbp+1A0h+var_200]
0x18000efd0  mov     [rsp+2A0h+ppwszAcceptTypes], rax; ppwszAcceptTypes
0x18000efd5  mov     qword ptr [rsp+2A0h+dwFlags], r12; pwszReferrer
0x18000efda  xor     r9d, r9d; pwszVersion
0x18000efdd  lea     rdx, pwszVerb; "GET"
0x18000efe4  mov     rcx, r10; hConnect
0x18000efe7  call    cs:__imp_WinHttpOpenRequest
0x18000efed  mov     rdx, rax
0x18000eff0  lea     rcx, [rsp+2A0h+hRequest]
0x18000eff5  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?WinHttpCloseHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18000effa  mov     rcx, [rbp+1A8h]; this
0x18000f001  mov     rbx, [rsp+2A0h+hRequest]
0x18000f006  test    rbx, rbx
0x18000f009  jz      loc_18000F3F7
0x18000f00f  mov     qword ptr [rsp+2A0h+var_270], r12; dwContext
0x18000f014  mov     dword ptr [rsp+2A0h+ppwszAcceptTypes], r12d; dwTotalLength
0x18000f019  mov     [rsp+2A0h+dwFlags], r12d; dwOptionalLength
0x18000f01e  xor     r9d, r9d; lpOptional
0x18000f021  xor     r8d, r8d; dwHeadersLength
0x18000f024  xor     edx, edx; lpszHeaders
0x18000f026  mov     rcx, rbx; hRequest
0x18000f029  call    cs:__imp_WinHttpSendRequest
0x18000f02f  mov     rcx, [rbp+1A8h]; this
0x18000f036  test    eax, eax
0x18000f038  jz      loc_18000F409
0x18000f03e  xor     edx, edx; lpReserved
0x18000f040  mov     rcx, rbx; hRequest
0x18000f043  call    cs:__imp_WinHttpReceiveResponse
0x18000f049  mov     rcx, [rbp+1A8h]; this
0x18000f050  test    eax, eax
0x18000f052  jz      loc_18000F41B
0x18000f058  mov     [rsp+2A0h+Buffer], r12d
0x18000f05d  mov     [rsp+2A0h+dwBufferLength], r14d
0x18000f062  mov     [rsp+2A0h+ppwszAcceptTypes], r12; lpdwIndex
0x18000f067  lea     rax, [rsp+2A0h+dwBufferLength]
0x18000f06c  mov     qword ptr [rsp+2A0h+dwFlags], rax; lpdwBufferLength
0x18000f071  lea     r9, [rsp+2A0h+Buffer]; lpBuffer
0x18000f076  xor     r8d, r8d; pwszName
0x18000f079  mov     edx, 20000013h; dwInfoLevel
0x18000f07e  mov     rcx, rbx; hRequest
0x18000f081  call    cs:__imp_WinHttpQueryHeaders
0x18000f087  mov     rcx, [rbp+1A8h]; this
0x18000f08e  test    eax, eax
0x18000f090  jz      loc_18000F42D
0x18000f096  mov     eax, cs:dword_180019048
0x18000f09c  cmp     eax, 5
0x18000f09f  jbe     short loc_18000F103
0x18000f0a1  mov     rdx, 400000000000h
0x18000f0ab  call    _tlgKeywordOn
0x18000f0b0  test    al, al
0x18000f0b2  jz      short loc_18000F103
0x18000f0b4  mov     [rbp+1A0h+var_210], r15
0x18000f0b8  mov     [rbp+1A0h+var_208], rsi
0x18000f0bc  mov     eax, [rsp+2A0h+Buffer]
0x18000f0c0  mov     [rsp+2A0h+var_25C], eax
0x18000f0c4  mov     [rbp+1A0h+lpBuffer], 3000000h
0x18000f0cf  lea     rax, [rbp+1A0h+var_210]
0x18000f0d3  mov     [rsp+2A0h+var_268], rax
0x18000f0d8  lea     rax, [rbp+1A0h+var_208]
0x18000f0dc  mov     qword ptr [rsp+2A0h+var_270], rax
0x18000f0e1  lea     rax, [rsp+2A0h+var_25C]
0x18000f0e6  mov     [rsp+2A0h+ppwszAcceptTypes], rax
0x18000f0eb  lea     rax, [rbp+1A0h+lpBuffer]
0x18000f0f2  mov     qword ptr [rsp+2A0h+dwFlags], rax; int
0x18000f0f7  lea     rdx, byte_180015367
0x18000f0fe  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18000f103  cmp     [rsp+2A0h+Buffer], 0C8h
0x18000f10b  jz      loc_18000F1B4
0x18000f111  mov     [rsp+2A0h+var_25C], r12d
0x18000f116  mov     [rsp+2A0h+ppwszAcceptTypes], r12; lpdwIndex
0x18000f11b  lea     rax, [rsp+2A0h+var_25C]
0x18000f120  mov     qword ptr [rsp+2A0h+dwFlags], rax; lpdwBufferLength
0x18000f125  xor     r9d, r9d; lpBuffer
0x18000f128  xor     r8d, r8d; pwszName
0x18000f12b  lea     edi, [r9+16h]
0x18000f12f  mov     edx, edi; dwInfoLevel
0x18000f131  mov     rcx, rbx; hRequest
0x18000f134  call    cs:__imp_WinHttpQueryHeaders
0x18000f13a  test    eax, eax
0x18000f13c  jnz     short loc_18000F14D
0x18000f13e  call    cs:__imp_GetLastError
0x18000f144  cmp     eax, 7Ah ; 'z'
0x18000f147  jnz     loc_18000F43F
0x18000f14d  lea     rcx, [rbp+1A0h+lpBuffer]
0x18000f154  call    ??$?0AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>>>(std::allocator<std::pair<std::wstring const,std::wstring>> const &)
0x18000f159  nop
0x18000f15a  mov     edx, [rsp+2A0h+var_25C]
0x18000f15e  lea     rcx, [rbp+1A0h+lpBuffer]
0x18000f165  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18000f16a  lea     rcx, [rbp+1A0h+lpBuffer]
0x18000f171  call    ?get@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?WinHttpCloseHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEBAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::get(void)
0x18000f176  mov     r9, rax
0x18000f179  lea     rcx, [rsp+2A0h+hRequest]
0x18000f17e  call    ?get@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?WinHttpCloseHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEBAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::get(void)
0x18000f183  mov     rcx, rax; hRequest
0x18000f186  mov     [rsp+2A0h+ppwszAcceptTypes], r12; lpdwIndex
0x18000f18b  lea     rax, [rsp+2A0h+var_25C]
0x18000f190  mov     qword ptr [rsp+2A0h+dwFlags], rax; int
0x18000f195  xor     r8d, r8d; pwszName
0x18000f198  mov     edx, edi; dwInfoLevel
0x18000f19a  call    cs:__imp_WinHttpQueryHeaders
0x18000f1a0  mov     ecx, eax
0x18000f1a2  call    ??$verify_BOOL@H@wil@@YAHH@Z; wil::verify_BOOL<int>(int)
0x18000f1a7  test    eax, eax
0x18000f1a9  jz      loc_18000F3A5
0x18000f1af  jmp     loc_18000F44C
0x18000f1b4  mov     [rsp+2A0h+dwNumberOfBytesAvailable], r12d
0x18000f1b9  mov     [rsp+2A0h+dwNumberOfBytesRead], r12d
0x18000f1be  xorps   xmm0, xmm0
0x18000f1c1  movdqu  [rsp+2A0h+var_230], xmm0
0x18000f1c7  mov     [rbp+1A0h+var_220], r12
0x18000f1cb  lea     rdx, [rsp+2A0h+dwNumberOfBytesAvailable]; lpdwNumberOfBytesAvailable
0x18000f1d0  mov     rcx, rbx; hRequest
0x18000f1d3  call    cs:__imp_WinHttpQueryDataAvailable
0x18000f1d9  mov     rcx, [rbp+1A8h]; this
0x18000f1e0  test    eax, eax
0x18000f1e2  jz      loc_18000F3BE
0x18000f1e8  xorps   xmm0, xmm0
0x18000f1eb  movdqu  xmmword ptr [rbp+1A0h+lpBuffer], xmm0
0x18000f1f3  mov     [rbp+1A0h+var_50], r12
0x18000f1fa  mov     edx, [rsp+2A0h+dwNumberOfBytesAvailable]
0x18000f1fe  test    rdx, rdx
0x18000f201  jz      short loc_18000F20F
0x18000f203  lea     rcx, [rbp+1A0h+lpBuffer]
0x18000f20a  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18000f20f  mov     rdx, [rbp+1A0h+lpBuffer]; lpBuffer
0x18000f216  mov     r8d, dword ptr [rbp+1A0h+lpBuffer+8]
0x18000f21d  sub     r8d, edx; dwNumberOfBytesToRead
0x18000f220  lea     r9, [rsp+2A0h+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x18000f225  mov     rcx, rbx; hRequest
0x18000f228  call    cs:__imp_WinHttpReadData
0x18000f22e  mov     rcx, [rbp+1A8h]; this
0x18000f235  test    eax, eax
0x18000f237  jz      loc_18000F393
0x18000f23d  mov     eax, [rsp+2A0h+dwNumberOfBytesRead]
0x18000f241  cmp     [rsp+2A0h+dwNumberOfBytesAvailable], eax
0x18000f245  setnz   al
0x18000f248  mov     rcx, [rbp+1A8h]; this
0x18000f24f  test    al, al
0x18000f251  jnz     loc_18000F48E
0x18000f257  mov     r8, [rbp+1A0h+lpBuffer]
0x18000f25e  mov     r9, [rbp+1A0h+lpBuffer+8]
0x18000f265  sub     r9, r8
0x18000f268  mov     rdx, qword ptr [rsp+2A0h+var_230+8]
0x18000f26d  lea     rcx, [rsp+2A0h+var_230]
0x18000f272  call    ??$_Insert_counted_range@PEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEAE_K@Z; std::vector<uchar>::_Insert_counted_range<uchar *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar *,unsigned __int64)
0x18000f277  nop
0x18000f278  mov     rcx, [rbp+1A0h+lpBuffer]
0x18000f27f  test    rcx, rcx
0x18000f282  jz      short loc_18000F293
0x18000f284  mov     rdx, [rbp+1A0h+var_50]
0x18000f28b  sub     rdx, rcx
0x18000f28e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000f293  cmp     [rsp+2A0h+dwNumberOfBytesAvailable], r12d
0x18000f298  ja      loc_18000F1CB
0x18000f29e  mov     r9, qword ptr [rsp+2A0h+var_230+8]
0x18000f2a3  mov     rdx, qword ptr [rsp+2A0h+var_230]
0x18000f2a8  xorps   xmm0, xmm0
0x18000f2ab  movups  xmmword ptr [rdi], xmm0
0x18000f2ae  mov     [rdi+10h], r12
0x18000f2b2  mov     [rdi+18h], r12
0x18000f2b6  cmp     rdx, r9
0x18000f2b9  jnz     short loc_18000F2C9
0x18000f2bb  mov     qword ptr [rdi+18h], 7
0x18000f2c3  mov     [rdi], r12w
0x18000f2c7  jmp     short loc_18000F2D4
0x18000f2c9  sub     r9, rdx
0x18000f2cc  mov     rcx, rdi
0x18000f2cf  call    ??$_Construct_from_iter@PEAEPEAE_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXPEAEQEAE_K@Z; std::wstring::_Construct_from_iter<uchar *,uchar *,unsigned __int64>(uchar *,uchar * const,unsigned __int64)
0x18000f2d4  cmp     [rdi+10h], r12
0x18000f2d8  jnz     short loc_18000F2FE
0x18000f2da  test    cs:Microsoft_Windows_TenantRestrictionsEnableBits, 10h
  ... truncated ...
```
