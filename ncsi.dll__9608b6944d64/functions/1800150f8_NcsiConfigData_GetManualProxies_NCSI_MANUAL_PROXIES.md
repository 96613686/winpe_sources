# NcsiConfigData::GetManualProxies(NCSI_MANUAL_PROXIES *)

- ea: `0x1800150f8`
- end: `0x18001560b`
- name: `?GetManualProxies@NcsiConfigData@@QEAA_NPEAUNCSI_MANUAL_PROXIES@@@Z`
- size: `1299`
- prototype: `bool __fastcall(NcsiConfigData *__hidden this, struct NCSI_MANUAL_PROXIES *)`
- caller_count: `6`
- callee_count: `15`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001450c`
- `0x1800156ac`
- `0x18004debc`
- `0x180053270`
- `0x180053b08`
- `0x180076430`

## callees

- `0x18000175c`
- `0x180003c20`
- `0x1800150f8`
- `0x18002283c`
- `0x1800257b8`
- `0x180029cf4`
- `0x18002a048`
- `0x18002bb64`
- `0x18002d6a0`
- `0x18003e9e8`
- `0x180047240`
- `0x180047f78`
- `0x1800510d4`
- `0x180051858`
- `0x180051b7c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800152f3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800152f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001534a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015553`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001557f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800155dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001534a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015553`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001557f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800155dd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800151a4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800151a4`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180015277`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001528a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001529d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180015277`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001528a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001529d`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x1800151ca`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x1800151ca`

## string_xrefs

- `0x180015414`: `Overwrite the old IE proxy with the new one`
- `0x1800154f1`: `AutoConfigURL`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
char __fastcall NcsiConfigData::GetManualProxies(NcsiConfigData *this, struct NCSI_MANUAL_PROXIES *a2)
{
  struct NCSI_MANUAL_PROXIES *v3; // rax
  int *v4; // rcx
  __int64 v5; // rdx
  NcsiConfigData *v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  const WCHAR *v9; // rdx
  LSTATUS v10; // eax
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  const unsigned __int16 *v20; // rcx
  const unsigned __int16 *v21; // rdx
  char v22; // bl
  int v23; // eax
  __int64 v24; // r8
  __int64 v25; // r9
  int v26; // r14d
  const char *v27; // rax
  const char *lpszAutoConfigUrl; // [rsp+40h] [rbp-2C8h] BYREF
  BOOL fAutoDetect; // [rsp+48h] [rbp-2C0h] BYREF
  const char *lpszProxy; // [rsp+50h] [rbp-2B8h] BYREF
  const size_t *v31[3]; // [rsp+58h] [rbp-2B0h] BYREF
  int v32; // [rsp+70h] [rbp-298h] BYREF
  _BYTE v33[524]; // [rsp+74h] [rbp-294h] BYREF
  WINHTTP_CURRENT_USER_IE_PROXY_CONFIG pProxyConfig; // [rsp+280h] [rbp-88h] BYREF
  HKEY phkResult; // [rsp+2A0h] [rbp-68h] BYREF
  __int128 v36; // [rsp+2A8h] [rbp-60h] BYREF
  __int64 v37; // [rsp+2B8h] [rbp-50h]

  v32 = 0;
  memset_0(v33, 0, 0x208u);
  v3 = a2;
  v4 = &v32;
  v5 = 4;
  do
  {
    *(_OWORD *)v3 = *(_OWORD *)v4;
    *((_OWORD *)v3 + 1) = *((_OWORD *)v4 + 1);
    *((_OWORD *)v3 + 2) = *((_OWORD *)v4 + 2);
    *((_OWORD *)v3 + 3) = *((_OWORD *)v4 + 3);
    *((_OWORD *)v3 + 4) = *((_OWORD *)v4 + 4);
    *((_OWORD *)v3 + 5) = *((_OWORD *)v4 + 5);
    *((_OWORD *)v3 + 6) = *((_OWORD *)v4 + 6);
    *((_OWORD *)v3 + 7) = *((_OWORD *)v4 + 7);
    v3 = (struct NCSI_MANUAL_PROXIES *)((char *)v3 + 128);
    v4 += 32;
    --v5;
  }
  while ( v5 );
  *(_OWORD *)((char *)v3 - 4) = *(_OWORD *)(v4 - 1);
  EnterCriticalSection(&stru_18009D378);
  v31[1] = (const size_t *)&stru_18009D378;
  memset(&pProxyConfig, 0, sizeof(pProxyConfig));
  if ( WinHttpGetIEProxyConfigForCurrentUser(&pProxyConfig) )
  {
    if ( (unsigned int)dword_18009A048 > 5 )
    {
      v31[0] = (const size_t *)pProxyConfig.lpszProxyBypass;
      lpszProxy = (const char *)pProxyConfig.lpszProxy;
      lpszAutoConfigUrl = (const char *)pProxyConfig.lpszAutoConfigUrl;
      fAutoDetect = pProxyConfig.fAutoDetect;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (__int64)v6,
        (int)&word_1800868B6,
        v7,
        v8,
        (__int64)&fAutoDetect,
        (const size_t **)&lpszAutoConfigUrl,
        (const size_t **)&lpszProxy,
        v31);
    }
    if ( pProxyConfig.lpszProxy || pProxyConfig.lpszAutoConfigUrl )
    {
      NcsiConfigData::HandleWinInetProxyConfigForCurrentUser(
        v6,
        (const struct _WINHTTP_CURRENT_USER_IE_PROXY_CONFIG *)&pProxyConfig);
      if ( pProxyConfig.lpszAutoConfigUrl )
        GlobalFree(pProxyConfig.lpszAutoConfigUrl);
      if ( pProxyConfig.lpszProxy )
        GlobalFree(pProxyConfig.lpszProxy);
    }
    if ( pProxyConfig.lpszProxyBypass )
      GlobalFree(pProxyConfig.lpszProxyBypass);
  }
  else if ( (unsigned int)dword_18009A048 > 5 )
  {
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)v6,
      (unsigned __int8 *)byte_18008687B);
  }
  phkResult = 0;
  v9 = (const WCHAR *)&g_ncsiRegistry;
  if ( (unsigned __int64)qword_18009AA78 > 7 )
    v9 = g_ncsiRegistry;
  v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v9, 0, 0x20019u, &phkResult);
  if ( v10 )
  {
    if ( (unsigned int)dword_18009A048 > 5 )
    {
      fAutoDetect = v10;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)dword_18009A048,
        (unsigned __int8 *)&unk_180086840,
        v12,
        v13,
        (__int64)&fAutoDetect);
    }
    if ( qword_18009D358 != qword_18009D360 )
      qword_18009D360 = qword_18009D358;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    LeaveCriticalSection(&stru_18009D378);
    return 0;
  }
  v36 = 0;
  v37 = 0;
  if ( !(unsigned __int8)NcsiConfigData::LoadManualProxies(v11, phkResult, &v36) )
  {
    if ( (unsigned int)dword_18009A048 > 5 )
    {
      lpszAutoConfigUrl = "Unable to load manual proxies";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (__int64)&dword_18009A048,
        (unsigned __int8 *)word_18008676A,
        v15,
        v16,
        (const unsigned __int16 **)&lpszAutoConfigUrl);
    }
    goto LABEL_54;
  }
  if ( (unsigned __int8)std::operator==<unsigned short,std::allocator<unsigned short>>(&v36, &qword_18009D358) )
  {
    if ( (unsigned int)dword_18009A048 > 5 )
    {
      v20 = (const unsigned __int16 *)v36;
      if ( (_QWORD)v36 == *((_QWORD *)&v36 + 1) )
        v20 = 0;
      lpszAutoConfigUrl = (const char *)v20;
      lpszProxy = "IE proxy settings found to be the same as the old ones";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        (__int64)v20,
        (int)byte_1800867F5,
        v18,
        v19,
        (const unsigned __int16 **)&lpszProxy,
        (const size_t **)&lpszAutoConfigUrl);
    }
  }
  else
  {
    if ( (unsigned int)dword_18009A048 > 5 )
    {
      v21 = (const unsigned __int16 *)v36;
      if ( (_QWORD)v36 == *((_QWORD *)&v36 + 1) )
        v21 = 0;
      lpszAutoConfigUrl = (const char *)v21;
      lpszProxy = "Overwrite the old IE proxy with the new one";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v17,
        (int)word_1800867AA,
        v18,
        v19,
        (const unsigned __int16 **)&lpszProxy,
        (const size_t **)&lpszAutoConfigUrl);
    }
    std::vector<unsigned short>::operator=(&qword_18009D358, &v36);
  }
  if ( !((qword_18009D360 - qword_18009D358) >> 1)
    || (unsigned __int64)(((qword_18009D360 - qword_18009D358) >> 1) - 1) >= 0x104 )
  {
LABEL_54:
    std::vector<unsigned short>::_Tidy(&v36);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    LeaveCriticalSection(&stru_18009D378);
    return 0;
  }
  v22 = 1;
  if ( *(_WORD *)qword_18009D358 == 49 )
  {
    v23 = 1;
  }
  else
  {
    v23 = 0;
    if ( *(_WORD *)qword_18009D358 == 48 )
      v23 = 2;
  }
  *(_DWORD *)a2 = v23;
  memset_0((char *)a2 + 4, 0, 0x104u);
  v26 = StringCchCopyW((unsigned __int16 *)a2 + 2, 0x104u, (const unsigned __int16 *)(qword_18009D358 + 2));
  if ( (unsigned int)dword_18009A048 > 5 )
  {
    lpszAutoConfigUrl = (char *)a2 + 4;
    if ( *(_DWORD *)a2 == 1 )
    {
      v27 = "NamedProxy";
    }
    else if ( *(_DWORD *)a2 == 2 )
    {
      v27 = "AutoConfigURL";
    }
    else
    {
      v27 = "Unknown";
    }
    lpszProxy = v27;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
      (unsigned int)dword_18009A048,
      (int)&word_18008672E,
      v24,
      v25,
      (const unsigned __int16 **)&lpszProxy,
      (const size_t **)&lpszAutoConfigUrl);
  }
  if ( v26 < 0 || !*((_WORD *)a2 + 2) )
    v22 = 0;
  std::vector<unsigned short>::_Tidy(&v36);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  LeaveCriticalSection(&stru_18009D378);
  return v22;
}

```

## disassembly

```asm
0x1800150f8  push    rbx
0x1800150fa  push    rsi
0x1800150fb  push    rdi
0x1800150fc  push    r12
0x1800150fe  push    r14
0x180015100  push    r15
0x180015102  sub     rsp, 2D8h
0x180015109  mov     rax, cs:__security_cookie
0x180015110  xor     rax, rsp
0x180015113  mov     [rsp+308h+var_48], rax
0x18001511b  mov     rsi, rdx
0x18001511e  xor     r15d, r15d
0x180015121  mov     [rsp+308h+var_298], r15d
0x180015126  xor     edx, edx; Val
0x180015128  mov     r8d, 208h; Size
0x18001512e  lea     rcx, [rsp+308h+var_294]; void *
0x180015133  call    memset_0
0x180015138  mov     rax, rsi
0x18001513b  lea     rcx, [rsp+308h+var_298]
0x180015140  lea     edx, [r15+4]
0x180015144  lea     r8d, [rdx+7Ch]
0x180015148  movups  xmm0, xmmword ptr [rcx]
0x18001514b  movups  xmmword ptr [rax], xmm0
0x18001514e  movups  xmm1, xmmword ptr [rcx+10h]
0x180015152  movups  xmmword ptr [rax+10h], xmm1
0x180015156  movups  xmm0, xmmword ptr [rcx+20h]
0x18001515a  movups  xmmword ptr [rax+20h], xmm0
0x18001515e  movups  xmm1, xmmword ptr [rcx+30h]
0x180015162  movups  xmmword ptr [rax+30h], xmm1
0x180015166  movups  xmm0, xmmword ptr [rcx+40h]
0x18001516a  movups  xmmword ptr [rax+40h], xmm0
0x18001516e  movups  xmm1, xmmword ptr [rcx+50h]
0x180015172  movups  xmmword ptr [rax+50h], xmm1
0x180015176  movups  xmm0, xmmword ptr [rcx+60h]
0x18001517a  movups  xmmword ptr [rax+60h], xmm0
0x18001517e  movups  xmm1, xmmword ptr [rcx+70h]
0x180015182  movups  xmmword ptr [rax+70h], xmm1
0x180015186  add     rax, r8
0x180015189  add     rcx, r8
0x18001518c  sub     rdx, 1
0x180015190  jnz     short loc_180015148
0x180015192  movups  xmm0, xmmword ptr [rcx-4]
0x180015196  movups  xmmword ptr [rax-4], xmm0
0x18001519a  lea     r12, stru_18009D378
0x1800151a1  mov     rcx, r12; lpCriticalSection
0x1800151a4  call    cs:__imp_EnterCriticalSection
0x1800151aa  mov     [rsp+308h+var_2A8], r12
0x1800151af  xorps   xmm0, xmm0
0x1800151b2  movups  xmmword ptr [rsp+308h+pProxyConfig.fAutoDetect], xmm0
0x1800151ba  movups  xmmword ptr [rsp+308h+pProxyConfig.lpszProxy], xmm0
0x1800151c2  lea     rcx, [rsp+308h+pProxyConfig]; pProxyConfig
0x1800151ca  call    cs:__imp_WinHttpGetIEProxyConfigForCurrentUser
0x1800151d0  test    eax, eax
0x1800151d2  mov     eax, cs:dword_18009A048
0x1800151d8  jz      loc_1800152A5
0x1800151de  cmp     eax, 5
0x1800151e1  jbe     short loc_180015249
0x1800151e3  mov     rax, [rsp+308h+pProxyConfig.lpszProxyBypass]
0x1800151eb  mov     [rsp+308h+var_2B0], rax
0x1800151f0  mov     rax, [rsp+308h+pProxyConfig.lpszProxy]
0x1800151f8  mov     [rsp+308h+var_2B8], rax
0x1800151fd  mov     rax, [rsp+308h+pProxyConfig.lpszAutoConfigUrl]
0x180015205  mov     [rsp+308h+var_2C8], rax
0x18001520a  mov     eax, [rsp+308h+pProxyConfig.fAutoDetect]
0x180015211  mov     [rsp+308h+var_2C0], eax
0x180015215  lea     rax, [rsp+308h+var_2B0]
0x18001521a  mov     [rsp+308h+var_2D0], rax
0x18001521f  lea     rax, [rsp+308h+var_2B8]
0x180015224  mov     [rsp+308h+var_2D8], rax
0x180015229  lea     rax, [rsp+308h+var_2C8]
0x18001522e  mov     [rsp+308h+var_2E0], rax
0x180015233  lea     rax, [rsp+308h+var_2C0]
0x180015238  mov     [rsp+308h+phkResult], rax
0x18001523d  lea     rdx, word_1800868B6
0x180015244  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180015249  cmp     [rsp+308h+pProxyConfig.lpszProxy], r15
0x180015251  jnz     short loc_18001525D
0x180015253  cmp     [rsp+308h+pProxyConfig.lpszAutoConfigUrl], r15
0x18001525b  jz      short loc_180015290
0x18001525d  lea     rdx, [rsp+308h+pProxyConfig]; struct _WINHTTP_CURRENT_USER_IE_PROXY_CONFIG *
0x180015265  call    ?HandleWinInetProxyConfigForCurrentUser@NcsiConfigData@@QEAAXAEBU_WINHTTP_CURRENT_USER_IE_PROXY_CONFIG@@@Z; NcsiConfigData::HandleWinInetProxyConfigForCurrentUser(_WINHTTP_CURRENT_USER_IE_PROXY_CONFIG const &)
0x18001526a  mov     rcx, [rsp+308h+pProxyConfig.lpszAutoConfigUrl]; hMem
0x180015272  test    rcx, rcx
0x180015275  jz      short loc_18001527D
0x180015277  call    cs:__imp_GlobalFree
0x18001527d  mov     rcx, [rsp+308h+pProxyConfig.lpszProxy]; hMem
0x180015285  test    rcx, rcx
0x180015288  jz      short loc_180015290
0x18001528a  call    cs:__imp_GlobalFree
0x180015290  mov     rcx, [rsp+308h+pProxyConfig.lpszProxyBypass]; hMem
0x180015298  test    rcx, rcx
0x18001529b  jz      short loc_1800152B7
0x18001529d  call    cs:__imp_GlobalFree
0x1800152a3  jmp     short loc_1800152B7
0x1800152a5  cmp     eax, 5
0x1800152a8  jbe     short loc_1800152B7
0x1800152aa  lea     rdx, byte_18008687B
0x1800152b1  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800152b6  nop
0x1800152b7  mov     [rsp+308h+var_68], r15
0x1800152bf  lea     rdx, ?g_ncsiRegistry@@3VNcsiRegistry@@A; NcsiRegistry g_ncsiRegistry
0x1800152c6  cmp     cs:qword_18009AA78, 7
0x1800152ce  cmova   rdx, cs:?g_ncsiRegistry@@3VNcsiRegistry@@A; lpSubKey
0x1800152d6  lea     rax, [rsp+308h+var_68]
0x1800152de  mov     [rsp+308h+phkResult], rax; phkResult
0x1800152e3  mov     r9d, 20019h; samDesired
0x1800152e9  xor     r8d, r8d; ulOptions
0x1800152ec  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800152f3  call    cs:__imp_RegOpenKeyExW
0x1800152f9  test    eax, eax
0x1800152fb  jz      short loc_180015357
0x1800152fd  mov     ecx, cs:dword_18009A048
0x180015303  cmp     ecx, 5
0x180015306  jbe     short loc_180015322
0x180015308  mov     [rsp+308h+var_2C0], eax
0x18001530c  lea     rax, [rsp+308h+var_2C0]
0x180015311  mov     [rsp+308h+phkResult], rax
0x180015316  lea     rdx, unk_180086840
0x18001531d  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180015322  mov     rax, cs:qword_18009D358
0x180015329  cmp     rax, cs:qword_18009D360
0x180015330  jz      short loc_180015339
0x180015332  mov     cs:qword_18009D360, rax
0x180015339  lea     rcx, [rsp+308h+var_68]
0x180015341  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180015346  nop
0x180015347  mov     rcx, r12; lpCriticalSection
0x18001534a  call    cs:__imp_LeaveCriticalSection
0x180015350  xor     al, al
0x180015352  jmp     loc_1800155E9
0x180015357  xorps   xmm1, xmm1
0x18001535a  movdqu  [rsp+308h+var_60], xmm1
0x180015363  mov     [rsp+308h+var_50], r15
0x18001536b  lea     r8, [rsp+308h+var_60]
0x180015373  mov     rdx, [rsp+308h+var_68]
0x18001537b  call    ?LoadManualProxies@NcsiConfigData@@AEAA_NPEAUHKEY__@@AEAV?$vector@GV?$allocator@G@std@@@std@@@Z; NcsiConfigData::LoadManualProxies(HKEY__ *,std::vector<ushort> &)
0x180015380  test    al, al
0x180015382  jz      loc_180015589
0x180015388  lea     rdx, qword_18009D358
0x18001538f  lea     rcx, [rsp+308h+var_60]
0x180015397  call    ??$?8GV?$allocator@G@std@@@std@@YA_NAEBV?$vector@GV?$allocator@G@std@@@0@0@Z; std::operator==<ushort,std::allocator<ushort>>(std::vector<ushort> const &,std::vector<ushort> const &)
0x18001539c  test    al, al
0x18001539e  mov     eax, cs:dword_18009A048
0x1800153a4  jz      short loc_1800153F6
0x1800153a6  cmp     eax, 5
0x1800153a9  jbe     loc_180015454
0x1800153af  mov     rcx, qword ptr [rsp+308h+var_60]
0x1800153b7  cmp     rcx, qword ptr [rsp+308h+var_60+8]
0x1800153bf  cmovz   rcx, r15
0x1800153c3  mov     [rsp+308h+var_2C8], rcx
0x1800153c8  lea     rax, aIeProxySetting; "IE proxy settings found to be the same "...
0x1800153cf  mov     [rsp+308h+var_2B8], rax
0x1800153d4  lea     rax, [rsp+308h+var_2C8]
0x1800153d9  mov     [rsp+308h+var_2E0], rax
0x1800153de  lea     rax, [rsp+308h+var_2B8]
0x1800153e3  mov     [rsp+308h+phkResult], rax
0x1800153e8  lea     rdx, byte_1800867F5
0x1800153ef  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800153f4  jmp     short loc_180015454
0x1800153f6  cmp     eax, 5
0x1800153f9  jbe     short loc_180015440
0x1800153fb  mov     rdx, qword ptr [rsp+308h+var_60]
0x180015403  cmp     rdx, qword ptr [rsp+308h+var_60+8]
0x18001540b  cmovz   rdx, r15
0x18001540f  mov     [rsp+308h+var_2C8], rdx
0x180015414  lea     rax, aOverwriteTheOl; "Overwrite the old IE proxy with the new"...
0x18001541b  mov     [rsp+308h+var_2B8], rax
0x180015420  lea     rax, [rsp+308h+var_2C8]
0x180015425  mov     [rsp+308h+var_2E0], rax
0x18001542a  lea     rax, [rsp+308h+var_2B8]
0x18001542f  mov     [rsp+308h+phkResult], rax
0x180015434  lea     rdx, word_1800867AA
0x18001543b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180015440  lea     rdx, [rsp+308h+var_60]
0x180015448  lea     rcx, qword_18009D358
0x18001544f  call    ??4?$vector@GV?$allocator@G@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<ushort>::operator=(std::vector<ushort> &&)
0x180015454  mov     rcx, cs:qword_18009D358
0x18001545b  mov     rax, cs:qword_18009D360
0x180015462  sub     rax, rcx
0x180015465  sar     rax, 1
0x180015468  jz      loc_180015560
0x18001546e  dec     rax
0x180015471  mov     r14d, 104h
0x180015477  cmp     rax, r14
0x18001547a  jnb     loc_180015560
0x180015480  mov     ebx, 1
0x180015485  cmp     word ptr [rcx], 31h ; '1'
0x180015489  jnz     short loc_18001548F
0x18001548b  mov     eax, ebx
0x18001548d  jmp     short loc_1800154A0
0x18001548f  mov     eax, r15d
0x180015492  mov     r8d, 2
0x180015498  cmp     word ptr [rcx], 30h ; '0'
0x18001549c  cmovz   eax, r8d
0x1800154a0  mov     [rsi], eax
0x1800154a2  lea     rdi, [rsi+4]
0x1800154a6  mov     r8, r14; Size
0x1800154a9  xor     edx, edx; Val
0x1800154ab  mov     rcx, rdi; void *
0x1800154ae  call    memset_0
0x1800154b3  mov     r8, cs:qword_18009D358
0x1800154ba  add     r8, 2; unsigned __int16 *
0x1800154be  mov     rdx, r14; unsigned __int64
0x1800154c1  mov     rcx, rdi; unsigned __int16 *
0x1800154c4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800154c9  mov     r14d, eax
0x1800154cc  mov     ecx, cs:dword_18009A048
0x1800154d2  cmp     ecx, 5
0x1800154d5  jbe     short loc_180015526
0x1800154d7  mov     [rsp+308h+var_2C8], rdi
0x1800154dc  mov     edx, [rsi]
0x1800154de  sub     edx, 1
0x1800154e1  jz      short loc_1800154FA
0x1800154e3  cmp     edx, 1
0x1800154e6  jz      short loc_1800154F1
0x1800154e8  lea     rax, aUnknown_0; "Unknown"
0x1800154ef  jmp     short loc_180015501
0x1800154f1  lea     rax, aAutoconfigurl; "AutoConfigURL"
0x1800154f8  jmp     short loc_180015501
0x1800154fa  lea     rax, aNamedproxy; "NamedProxy"
0x180015501  mov     [rsp+308h+var_2B8], rax
0x180015506  lea     rax, [rsp+308h+var_2C8]
0x18001550b  mov     [rsp+308h+var_2E0], rax
0x180015510  lea     rax, [rsp+308h+var_2B8]
0x180015515  mov     [rsp+308h+phkResult], rax
0x18001551a  lea     rdx, word_18008672E
0x180015521  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180015526  test    r14d, r14d
0x180015529  js      short loc_180015531
0x18001552b  cmp     [rdi], r15w
0x18001552f  jnz     short loc_180015534
0x180015531  mov     bl, r15b
0x180015534  lea     rcx, [rsp+308h+var_60]
0x18001553c  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180015541  nop
0x180015542  lea     rcx, [rsp+308h+var_68]
0x18001554a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001554f  nop
0x180015550  mov     rcx, r12; lpCriticalSection
0x180015553  call    cs:__imp_LeaveCriticalSection
0x180015559  mov     al, bl
0x18001555b  jmp     loc_1800155E9
0x180015560  lea     rcx, [rsp+308h+var_60]
0x180015568  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18001556d  nop
0x18001556e  lea     rcx, [rsp+308h+var_68]
0x180015576  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001557b  nop
0x18001557c  mov     rcx, r12; lpCriticalSection
0x18001557f  call    cs:__imp_LeaveCriticalSection
0x180015585  xor     al, al
0x180015587  jmp     short loc_1800155E9
0x180015589  mov     eax, cs:dword_18009A048
0x18001558f  cmp     eax, 5
0x180015592  jbe     short loc_1800155BE
0x180015594  lea     rax, aUnableToLoadMa; "Unable to load manual proxies"
0x18001559b  mov     [rsp+308h+var_2C8], rax
0x1800155a0  lea     rax, [rsp+308h+var_2C8]
0x1800155a5  mov     [rsp+308h+phkResult], rax
0x1800155aa  lea     rdx, word_18008676A
0x1800155b1  lea     rcx, dword_18009A048
0x1800155b8  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800155bd  nop
0x1800155be  lea     rcx, [rsp+308h+var_60]
0x1800155c6  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800155cb  nop
0x1800155cc  lea     rcx, [rsp+308h+var_68]
0x1800155d4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800155d9  nop
0x1800155da  mov     rcx, r12; lpCriticalSection
0x1800155dd  call    cs:__imp_LeaveCriticalSection
0x1800155e3  xor     al, al
0x1800155e5  jmp     short loc_1800155E9
0x1800155e7  xor     al, al
0x1800155e9  mov     rcx, [rsp+308h+var_48]
0x1800155f1  xor     rcx, rsp; StackCookie
0x1800155f4  call    __security_check_cookie
0x1800155f9  add     rsp, 2D8h
0x180015600  pop     r15
0x180015602  pop     r14
0x180015604  pop     r12
0x180015606  pop     rdi
0x180015607  pop     rsi
0x180015608  pop     rbx
0x180015609  retn
```
