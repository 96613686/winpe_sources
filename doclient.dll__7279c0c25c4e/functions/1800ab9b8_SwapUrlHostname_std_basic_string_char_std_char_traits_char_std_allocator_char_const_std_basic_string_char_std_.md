# SwapUrlHostname(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,ushort)

- ea: `0x1800ab9b8`
- end: `0x1800abc58`
- name: `?SwapUrlHostname@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV12@0G@Z`
- size: `672`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18006f744`
- `0x1800757d0`
- `0x1800bcd00`

## callees

- `0x1800095a0`
- `0x18000ecf0`
- `0x18000ef98`
- `0x180039b68`
- `0x1800a5978`
- `0x1800a979c`
- `0x1800a98f8`
- `0x1800ab9b8`
- `0x1800abee0`
- `0x1800f82f0`
- `0x180108ed0`

## import_xrefs

- `WINHTTP!WinHttpCrackUrl` at `0x1800aba72`
- `WINHTTP!WinHttpCrackUrl` at `0x1800aba72`
- `WINHTTP!WinHttpCreateUrl` at `0x1800abaf1`
- `WINHTTP!WinHttpCreateUrl` at `0x1800abb35`
- `WINHTTP!WinHttpCreateUrl` at `0x1800abaf1`
- `WINHTTP!WinHttpCreateUrl` at `0x1800abb35`

## string_xrefs

- `0x1800abbc6`: `cacheHostOrigin`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall SwapUrlHostname(__int64 a1, _QWORD *a2, _QWORD *a3, INTERNET_PORT a4)
{
  __int64 v7; // r8
  __int64 v8; // r8
  const WCHAR *v9; // rcx
  const char *v10; // r9
  CHAR *v11; // rax
  INTERNET_PORT nPort; // ax
  WCHAR *v13; // r8
  const char *v14; // r9
  LPWSTR *v15; // rax
  __int64 v16; // rdx
  LPWSTR *v17; // rdx
  __int128 *v18; // rdx
  _QWORD *v19; // rdx
  _QWORD v21[5]; // [rsp+28h] [rbp-D8h] BYREF
  $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pdwUrlLength; // [rsp+C0h] [rbp-40h] BYREF
  LPWSTR Src[2]; // [rsp+C8h] [rbp-38h] BYREF
  __m128i si128; // [rsp+D8h] [rbp-28h]
  __int128 v26; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v27; // [rsp+F8h] [rbp-8h]
  _QWORD v28[2]; // [rsp+108h] [rbp+8h] BYREF
  DWORD v29; // [rsp+118h] [rbp+18h]
  unsigned __int64 v30; // [rsp+120h] [rbp+20h]
  LPCWSTR pwszUrl[4]; // [rsp+128h] [rbp+28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  v21[4] = a1;
  v7 = a2[2];
  if ( a2[3] > 0xFu )
    a2 = (_QWORD *)*a2;
  UTF8toWstr(pwszUrl, a2, v7);
  v8 = a3[2];
  if ( a3[3] > 0xFu )
    a3 = (_QWORD *)*a3;
  UTF8toWstr(v28, a3, v8);
  memset(&UrlComponents, 0, sizeof(UrlComponents));
  UrlComponents.dwStructSize = 104;
  UrlComponents.dwSchemeLength = 1;
  UrlComponents.dwHostNameLength = 1;
  UrlComponents.dwUrlPathLength = 1;
  UrlComponents.dwExtraInfoLength = 1;
  v9 = (const WCHAR *)pwszUrl;
  if ( pwszUrl[3] > (LPCWSTR)7 )
    v9 = pwszUrl[0];
  if ( !WinHttpCrackUrl(v9, 0, 0, &UrlComponents) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x1F1,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\GeneralUtils.cpp",
      v10);
  if ( !UrlComponents.lpszHostName )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x1F2,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\GeneralUtils.cpp",
      v10);
  v26 = 0;
  v27 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v26, UrlComponents.lpszHostName);
  v11 = (CHAR *)v28;
  if ( v30 > 7 )
    v11 = (CHAR *)v28[0];
  UrlComponents.lpszHostName = v11;
  UrlComponents.dwHostNameLength = v29;
  nPort = UrlComponents.nPort;
  if ( a4 )
    nPort = a4;
  UrlComponents.nPort = nPort;
  pdwUrlLength = 0;
  WinHttpCreateUrl(&UrlComponents, 0, 0, &pdwUrlLength);
  *(_OWORD *)Src = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(Src[0]) = 0;
  std::wstring::resize(Src);
  v13 = (WCHAR *)Src;
  if ( si128.m128i_i64[1] > 7uLL )
    v13 = Src[0];
  if ( !WinHttpCreateUrl(&UrlComponents, 0, v13, &pdwUrlLength) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x204,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\GeneralUtils.cpp",
      v14);
  v15 = Src;
  if ( si128.m128i_i64[1] > 7uLL )
    v15 = (LPWSTR *)Src[0];
  v16 = -1;
  do
    ++v16;
  while ( *((_WORD *)v15 + v16) );
  std::wstring::resize(Src);
  v17 = Src;
  if ( si128.m128i_i64[1] > 7uLL )
    v17 = (LPWSTR *)Src[0];
  WstrToUTF8(a1, v17, si128.m128i_i64[0]);
  v18 = &v26;
  if ( *((_QWORD *)&v27 + 1) > 7u )
    v18 = (__int128 *)v26;
  WstrToUTF8(v21, v18, v27);
  v19 = v21;
  if ( v21[3] > 0xFu )
    v19 = (_QWORD *)v21[0];
  AddQueryParamToUrl("cacheHostOrigin", v19, a1);
  std::string::~string(v21);
  std::wstring::~wstring((__int64)Src);
  std::wstring::~wstring((__int64)&v26);
  std::wstring::~wstring((__int64)v28);
  std::wstring::~wstring((__int64)pwszUrl);
  return a1;
}

```

## disassembly

```asm
0x1800ab9b8  push    rbp
0x1800ab9ba  push    rbx
0x1800ab9bb  push    rsi
0x1800ab9bc  push    rdi
0x1800ab9bd  push    r14
0x1800ab9bf  lea     rbp, [rsp-50h]
0x1800ab9c4  sub     rsp, 150h
0x1800ab9cb  mov     rax, cs:__security_cookie
0x1800ab9d2  xor     rax, rsp
0x1800ab9d5  mov     [rbp+70h+var_28], rax
0x1800ab9d9  movzx   esi, r9w
0x1800ab9dd  mov     rbx, r8
0x1800ab9e0  mov     rdi, rcx
0x1800ab9e3  mov     [rsp+170h+var_128], rcx
0x1800ab9e8  xor     r14d, r14d
0x1800ab9eb  mov     [rsp+170h+var_150], r14d
0x1800ab9f0  mov     r8, [rdx+10h]
0x1800ab9f4  cmp     qword ptr [rdx+18h], 0Fh
0x1800ab9f9  jbe     short loc_1800AB9FE
0x1800ab9fb  mov     rdx, [rdx]
0x1800ab9fe  lea     rcx, [rbp+70h+pwszUrl]
0x1800aba02  call    ?UTF8toWstr@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBD_K@Z; UTF8toWstr(char const *,unsigned __int64)
0x1800aba07  mov     [rsp+170h+var_150], 2
0x1800aba0f  mov     r8, [rbx+10h]
0x1800aba13  cmp     qword ptr [rbx+18h], 0Fh
0x1800aba18  jbe     short loc_1800ABA1D
0x1800aba1a  mov     rbx, [rbx]
0x1800aba1d  mov     rdx, rbx
0x1800aba20  lea     rcx, [rbp+70h+var_68]
0x1800aba24  call    ?UTF8toWstr@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBD_K@Z; UTF8toWstr(char const *,unsigned __int64)
0x1800aba29  mov     [rsp+170h+var_150], 6
0x1800aba31  mov     ebx, 68h ; 'h'
0x1800aba36  mov     r8d, ebx; Size
0x1800aba39  xor     edx, edx; Val
0x1800aba3b  lea     rcx, [rsp+170h+UrlComponents]; void *
0x1800aba40  call    memset
0x1800aba45  mov     [rsp+170h+UrlComponents.dwStructSize], ebx
0x1800aba49  lea     eax, [rbx-67h]
0x1800aba4c  mov     [rsp+170h+UrlComponents.dwSchemeLength], eax
0x1800aba50  mov     [rsp+170h+UrlComponents.dwHostNameLength], eax
0x1800aba54  mov     [rbp+70h+UrlComponents.dwUrlPathLength], eax
0x1800aba57  mov     [rbp+70h+UrlComponents.dwExtraInfoLength], eax
0x1800aba5a  lea     rcx, [rbp+70h+pwszUrl]
0x1800aba5e  cmp     [rbp+70h+var_30], 7
0x1800aba63  cmova   rcx, [rbp+70h+pwszUrl]; pwszUrl
0x1800aba68  lea     r9, [rsp+170h+UrlComponents]; lpUrlComponents
0x1800aba6d  xor     r8d, r8d; dwFlags
0x1800aba70  xor     edx, edx; dwUrlLength
0x1800aba72  call    cs:__imp_WinHttpCrackUrl
0x1800aba78  mov     rcx, [rbp+78h]; this
0x1800aba7c  test    eax, eax
0x1800aba7e  jz      loc_1800ABC34
0x1800aba84  mov     rcx, [rbp+78h]; this
0x1800aba88  mov     rdx, [rsp+170h+UrlComponents.lpszHostName]
0x1800aba8d  test    rdx, rdx
0x1800aba90  jz      loc_1800ABC46
0x1800aba96  xorps   xmm0, xmm0
0x1800aba99  movups  [rbp+70h+var_88], xmm0
0x1800aba9d  xorps   xmm1, xmm1
0x1800abaa0  movdqu  [rbp+70h+var_78], xmm1
0x1800abaa5  mov     r8d, [rsp+170h+UrlComponents.dwHostNameLength]
0x1800abaaa  lea     rcx, [rbp+70h+var_88]
0x1800abaae  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800abab3  nop
0x1800abab4  lea     rax, [rbp+70h+var_68]
0x1800abab8  cmp     [rbp+70h+var_50], 7
0x1800ababd  cmova   rax, [rbp+70h+var_68]
0x1800abac2  mov     [rsp+170h+UrlComponents.lpszHostName], rax
0x1800abac7  mov     eax, [rbp+70h+var_58]
0x1800abaca  mov     [rsp+170h+UrlComponents.dwHostNameLength], eax
0x1800abace  movzx   eax, [rsp+170h+UrlComponents.nPort]
0x1800abad3  test    si, si
0x1800abad6  cmovnz  ax, si
0x1800abada  mov     [rsp+170h+UrlComponents.nPort], ax
0x1800abadf  mov     [rbp+70h+pdwUrlLength], r14d
0x1800abae3  lea     r9, [rbp+70h+pdwUrlLength]; pdwUrlLength
0x1800abae7  xor     r8d, r8d; pwszUrl
0x1800abaea  xor     edx, edx; dwFlags
0x1800abaec  lea     rcx, [rsp+170h+UrlComponents]; lpUrlComponents
0x1800abaf1  call    cs:__imp_WinHttpCreateUrl
0x1800abaf7  xorps   xmm0, xmm0
0x1800abafa  movups  xmmword ptr [rbp+70h+Src], xmm0
0x1800abafe  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800abb06  movdqu  [rbp+70h+var_98], xmm1
0x1800abb0b  mov     word ptr [rbp+70h+Src], r14w
0x1800abb10  mov     edx, [rbp+70h+pdwUrlLength]
0x1800abb13  lea     rcx, [rbp+70h+Src]; Src
0x1800abb17  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x1800abb1c  lea     r8, [rbp+70h+Src]
0x1800abb20  cmp     qword ptr [rbp+70h+var_98+8], 7
0x1800abb25  cmova   r8, [rbp+70h+Src]; pwszUrl
0x1800abb2a  lea     r9, [rbp+70h+pdwUrlLength]; pdwUrlLength
0x1800abb2e  xor     edx, edx; dwFlags
0x1800abb30  lea     rcx, [rsp+170h+UrlComponents]; lpUrlComponents
0x1800abb35  call    cs:__imp_WinHttpCreateUrl
0x1800abb3b  mov     rcx, [rbp+78h]; this
0x1800abb3f  test    eax, eax
0x1800abb41  jz      loc_1800ABC22
0x1800abb47  lea     rax, [rbp+70h+Src]
0x1800abb4b  cmp     qword ptr [rbp+70h+var_98+8], 7
0x1800abb50  cmova   rax, [rbp+70h+Src]
0x1800abb55  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800abb59  inc     rdx
0x1800abb5c  cmp     [rax+rdx*2], r14w
0x1800abb61  jnz     short loc_1800ABB59
0x1800abb63  lea     rcx, [rbp+70h+Src]; Src
0x1800abb67  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x1800abb6c  lea     rdx, [rbp+70h+Src]
0x1800abb70  cmp     qword ptr [rbp+70h+var_98+8], 7
0x1800abb75  cmova   rdx, [rbp+70h+Src]
0x1800abb7a  mov     r8, qword ptr [rbp+70h+var_98]
0x1800abb7e  mov     rcx, rdi
0x1800abb81  call    ?WstrToUTF8@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEB_W_K@Z; WstrToUTF8(wchar_t const *,unsigned __int64)
0x1800abb86  mov     [rsp+170h+var_150], 0Fh
0x1800abb8e  lea     rdx, [rbp+70h+var_88]
0x1800abb92  cmp     qword ptr [rbp+70h+var_78+8], 7
0x1800abb97  cmova   rdx, qword ptr [rbp+70h+var_88]
0x1800abb9c  mov     r8, qword ptr [rbp+70h+var_78]
0x1800abba0  lea     rcx, [rsp+170h+var_148]
0x1800abba5  call    ?WstrToUTF8@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEB_W_K@Z; WstrToUTF8(wchar_t const *,unsigned __int64)
0x1800abbaa  mov     [rsp+170h+var_150], 1Fh
0x1800abbb2  lea     rdx, [rsp+170h+var_148]
0x1800abbb7  cmp     [rsp+170h+var_130], 0Fh
0x1800abbbd  cmova   rdx, [rsp+170h+var_148]
0x1800abbc3  mov     r8, rdi
0x1800abbc6  lea     rcx, aCachehostorigi; "cacheHostOrigin"
0x1800abbcd  call    ?AddQueryParamToUrl@@YAXPEBD0AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; AddQueryParamToUrl(char const *,char const *,std::string &)
0x1800abbd2  nop
0x1800abbd3  lea     rcx, [rsp+170h+var_148]; void *
0x1800abbd8  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800abbdd  nop
0x1800abbde  lea     rcx, [rbp+70h+Src]
0x1800abbe2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800abbe7  nop
0x1800abbe8  lea     rcx, [rbp+70h+var_88]
0x1800abbec  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800abbf1  nop
0x1800abbf2  lea     rcx, [rbp+70h+var_68]
0x1800abbf6  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800abbfb  nop
0x1800abbfc  lea     rcx, [rbp+70h+pwszUrl]
0x1800abc00  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800abc05  mov     rax, rdi
0x1800abc08  mov     rcx, [rbp+70h+var_28]
0x1800abc0c  xor     rcx, rsp; StackCookie
0x1800abc0f  call    __security_check_cookie
0x1800abc14  add     rsp, 150h
0x1800abc1b  pop     r14
0x1800abc1d  pop     rdi
0x1800abc1e  pop     rsi
0x1800abc1f  pop     rbx
0x1800abc20  pop     rbp
0x1800abc21  retn
0x1800abc22  lea     r8, aCW1SSrcDeliver_8; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800abc29  mov     edx, 204h; void *
0x1800abc2e  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800abc34  lea     r8, aCW1SSrcDeliver_8; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800abc3b  mov     edx, 1F1h; void *
0x1800abc40  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800abc46  lea     r8, aCW1SSrcDeliver_8; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800abc4d  mov     edx, 1F2h; void *
0x1800abc52  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
