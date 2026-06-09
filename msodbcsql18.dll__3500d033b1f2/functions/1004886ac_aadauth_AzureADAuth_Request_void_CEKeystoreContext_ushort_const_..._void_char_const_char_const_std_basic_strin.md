# aadauth::AzureADAuth::Request(void (*)(CEKeystoreContext *,ushort const *,...),void *,char const *,char const *,std::basic_string<char,std::char_traits<char>,std::allocator<char>> &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> *,char const *,char,std::basic_string<char,std::char_traits<char>,std::allocator<char>> *)

- ea: `0x1004886ac`
- end: `0x100488f94`
- name: `?Request@AzureADAuth@aadauth@@QEBAJP6AXPEAUCEKeystoreContext@@PEBGZZPEAXPEBD4AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAV45@4D6@Z`
- size: `2280`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, void *, __int64, __int64, char, void *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callers

- `0x100470b78`
- `0x100486398`

## callees

- `0x10040128c`
- `0x10042a440`
- `0x1004306f0`
- `0x1004717c4`
- `0x100485f38`
- `0x1004886ac`
- `0x100488f9c`
- `0x100548210`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!Sleep` at `0x100488c0c`
- `KERNEL32!Sleep` at `0x100488c0c`
- `KERNEL32!GetLastError` at `0x10048875e`
- `KERNEL32!GetLastError` at `0x100488cbf`
- `KERNEL32!GetLastError` at `0x100488d4f`
- `KERNEL32!GetLastError` at `0x100488dd6`
- `KERNEL32!GetLastError` at `0x100488ea2`
- `KERNEL32!GetLastError` at `0x10048875e`
- `KERNEL32!GetLastError` at `0x100488cbf`
- `KERNEL32!GetLastError` at `0x100488d4f`
- `KERNEL32!GetLastError` at `0x100488dd6`
- `KERNEL32!GetLastError` at `0x100488ea2`
- `KERNEL32!GetTickCount` at `0x10048878f`
- `KERNEL32!GetTickCount` at `0x100488bf3`
- `KERNEL32!GetTickCount` at `0x10048878f`
- `KERNEL32!GetTickCount` at `0x100488bf3`
- `WININET!InternetOpenUrlA` at `0x100488867`
- `WININET!InternetOpenUrlA` at `0x100488867`
- `WININET!InternetConnectA` at `0x1004888fb`
- `WININET!InternetConnectA` at `0x1004888fb`
- `WININET!HttpOpenRequestA` at `0x100488952`
- `WININET!HttpOpenRequestA` at `0x100488952`
- `WININET!InternetReadFile` at `0x100488b60`
- `WININET!InternetReadFile` at `0x100488b60`
- `WININET!InternetCloseHandle` at `0x100488ba7`
- `WININET!InternetCloseHandle` at `0x100488bb5`
- `WININET!InternetCloseHandle` at `0x100488d73`
- `WININET!InternetCloseHandle` at `0x100488d7c`
- `WININET!InternetCloseHandle` at `0x100488dfa`
- `WININET!InternetCloseHandle` at `0x100488ba7`
- `WININET!InternetCloseHandle` at `0x100488bb5`
- `WININET!InternetCloseHandle` at `0x100488d73`
- `WININET!InternetCloseHandle` at `0x100488d7c`
- `WININET!InternetCloseHandle` at `0x100488dfa`
- `WININET!InternetOpenA` at `0x10048874c`
- `WININET!InternetOpenA` at `0x10048874c`
- `WININET!HttpAddRequestHeadersA` at `0x10048898c`
- `WININET!HttpAddRequestHeadersA` at `0x10048898c`
- `WININET!HttpSendRequestA` at `0x1004889b6`
- `WININET!HttpSendRequestA` at `0x1004889b6`
- `WININET!HttpQueryInfoA` at `0x100488a43`
- `WININET!HttpQueryInfoA` at `0x100488a8c`
- `WININET!HttpQueryInfoA` at `0x100488aec`
- `WININET!HttpQueryInfoA` at `0x100488a43`
- `WININET!HttpQueryInfoA` at `0x100488a8c`
- `WININET!HttpQueryInfoA` at `0x100488aec`
- `VCRUNTIME140!strchr` at `0x100488895`
- `VCRUNTIME140!strchr` at `0x100488895`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100488cef`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100488e4e`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100488f1b`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100488f62`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100488cef`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100488e4e`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100488f1b`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100488f62`

## string_xrefs

- `0x100488745`: `AzureADAuthProvider`
- `0x10048890d`: `application/json`
- `0x100488982`: `Content-Type: application/json\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall aadauth::AzureADAuth::Request(
        unsigned int *a1,
        void (__fastcall *a2)(__int64, __int64, __int64, _QWORD *),
        __int64 a3,
        __int64 a4,
        const CHAR *a5,
        _QWORD *a6,
        __int64 a7,
        __int64 a8,
        char a9,
        _QWORD *a10)
{
  __int64 v12; // r14
  char v13; // r13
  __int64 LastError; // r8
  unsigned int v16; // r15d
  unsigned int v17; // ebx
  const char *v18; // rdx
  __int64 v19; // r8
  void *v20; // r13
  __int64 v21; // r8
  const CHAR *v22; // rdx
  DWORD dwFlags; // eax
  void *v24; // r14
  LPCSTR *v25; // rcx
  char *v26; // rbx
  LPCSTR *v27; // rdx
  const CHAR *v28; // r8
  _BYTE *v29; // rax
  void *v30; // r9
  CHAR *v31; // rcx
  BOOL v32; // eax
  int v33; // ecx
  _BYTE *v34; // r8
  unsigned __int64 v35; // rdx
  unsigned __int64 v36; // rax
  _QWORD *v37; // rax
  void *v38; // r8
  _BYTE *v39; // rax
  unsigned __int64 v40; // rdx
  unsigned __int64 v41; // rax
  _QWORD *v42; // rax
  _QWORD *v43; // rax
  unsigned __int64 v44; // rdx
  unsigned __int64 v45; // rax
  _QWORD *v46; // rax
  unsigned int v47; // ecx
  unsigned int v48; // eax
  unsigned int *v49; // rbx
  DWORD v50; // ebx
  CHAR *v51; // rcx
  _QWORD *v52; // rbx
  __int64 v53; // r8
  _QWORD *v54; // rbx
  __int64 v55; // r8
  _QWORD *v56; // rcx
  _QWORD *v57; // rbx
  __int64 v58; // r8
  CHAR *v59; // rdx
  _QWORD *v60; // rbx
  __int64 v61; // r8
  void *v62; // rcx
  CHAR *v63; // rdx
  DWORD dwIndex; // [rsp+44h] [rbp-BCh] BYREF
  int Buffer; // [rsp+48h] [rbp-B8h] BYREF
  DWORD v66; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v67; // [rsp+50h] [rbp-B0h]
  DWORD dwMilliseconds; // [rsp+54h] [rbp-ACh]
  __int64 v69; // [rsp+58h] [rbp-A8h]
  void (__fastcall *v70)(__int64, __int64, __int64, _QWORD *); // [rsp+60h] [rbp-A0h]
  DWORD dwBufferLength; // [rsp+68h] [rbp-98h] BYREF
  DWORD dwNumberOfBytesRead; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD TickCount; // [rsp+70h] [rbp-90h]
  LPCSTR lpszHeaders; // [rsp+78h] [rbp-88h]
  __int64 v75; // [rsp+80h] [rbp-80h]
  __int64 v76; // [rsp+88h] [rbp-78h]
  unsigned int *v77; // [rsp+90h] [rbp-70h]
  LPCSTR lpszAcceptTypes[3]; // [rsp+98h] [rbp-68h] BYREF
  LPCSTR lpszUrl[3]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v80; // [rsp+C8h] [rbp-38h]
  LPCSTR lpszObjectName[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v82; // [rsp+E0h] [rbp-20h]
  unsigned __int64 v83; // [rsp+E8h] [rbp-18h]
  _QWORD v84[3]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int64 v85; // [rsp+108h] [rbp+8h]
  _QWORD Src[3]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int64 v87; // [rsp+128h] [rbp+28h]
  _QWORD v88[3]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int64 v89; // [rsp+148h] [rbp+48h]
  _QWORD v90[3]; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int64 v91; // [rsp+168h] [rbp+68h]

  lpszAcceptTypes[2] = (LPCSTR)-2LL;
  v76 = a4;
  v69 = a3;
  v70 = a2;
  v77 = a1;
  lpszHeaders = a5;
  v12 = a8;
  v75 = a8;
  v13 = a9;
  if ( !aadauth::AzureADAuth::m_hInternet )
  {
    aadauth::AzureADAuth::m_hInternet = InternetOpenA("AzureADAuthProvider", 0, 0, 0, 0);
    if ( !aadauth::AzureADAuth::m_hInternet )
    {
      LastError = GetLastError();
      ((void (__fastcall *)(__int64, __int64, __int64))a2)(v69, 41351, LastError);
      return 41351;
    }
  }
  v67 = 0;
  dwMilliseconds = a1[2];
  TickCount = GetTickCount();
  v16 = -1;
  while ( 1 )
  {
    v17 = 0;
    lpszUrl[2] = 0;
    v80 = 15;
    LOBYTE(lpszUrl[0]) = 0;
    std::string::assign(lpszUrl);
    if ( v13 >= 0 )
    {
      _mm_lfence();
      v18 = off_1005D0420[v13];
    }
    else
    {
      v18 = qword_100558430;
    }
    v19 = -1;
    do
      ++v19;
    while ( v18[v19] );
    std::string::append(lpszUrl);
    v20 = 0;
    if ( a7 )
      break;
    if ( v12 )
    {
      std::string::append(lpszUrl);
      v21 = -1;
      do
        ++v21;
      while ( *(_BYTE *)(v12 + v21) );
      std::string::append(lpszUrl);
    }
    v22 = (const CHAR *)lpszUrl;
    if ( v80 >= 0x10 )
      v22 = lpszUrl[0];
    dwFlags = -2069101824;
    if ( a9 > 0 )
      dwFlags = -2077490432;
    v24 = InternetOpenUrlA(aadauth::AzureADAuth::m_hInternet, v22, lpszHeaders, 0xFFFFFFFF, dwFlags, 0);
    if ( !v24 )
    {
      Src[2] = 0;
      v87 = 7;
      LOWORD(Src[0]) = 0;
      std::wstring::_Construct<char *>(Src);
      v52 = Src;
      if ( v87 >= 8 )
        v52 = (_QWORD *)Src[0];
      v53 = GetLastError();
      v70(v69, 41352, v53, v52);
      std::basic_string<char16_t>::_Tidy_deallocate(Src);
      goto LABEL_114;
    }
LABEL_43:
    dwBufferLength = 4;
    dwIndex = 0;
    v32 = HttpQueryInfoA(v24, 0x20000013u, &Buffer, &dwBufferLength, &dwIndex);
    v33 = Buffer;
    if ( !v32 )
      v33 = -1;
    Buffer = v33;
    if ( a10 )
    {
      v66 = 0;
      dwIndex = 0;
      v34 = a10;
      if ( a10[3] >= 0x10u )
        v34 = (_BYTE *)*a10;
      HttpQueryInfoA(v24, 0x28u, v34, &v66, &dwIndex);
      v35 = v66 + 1;
      v36 = a10[2];
      if ( v35 > v36 )
      {
        _mm_lfence();
        std::string::append(a10, v35 - v36, 0);
      }
      else
      {
        a10[2] = v35;
        v37 = a10;
        if ( a10[3] >= 0x10u )
          v37 = (_QWORD *)*a10;
        *((_BYTE *)v37 + v35) = 0;
      }
      v38 = a10;
      if ( a10[3] >= 0x10u )
        v38 = (void *)*a10;
      if ( !HttpQueryInfoA(v24, 0x28u, v38, &v66, &dwIndex) )
      {
        a10[2] = 0;
        v39 = a10;
        if ( a10[3] >= 0x10u )
          v39 = (_BYTE *)*a10;
        *v39 = 0;
      }
    }
    do
    {
      v40 = v17 + 1024;
      v41 = a6[2];
      if ( v40 > v41 )
      {
        _mm_lfence();
        std::string::append(a6, v40 - v41, 0);
      }
      else
      {
        a6[2] = v40;
        v42 = a6;
        if ( a6[3] >= 0x10u )
          v42 = (_QWORD *)*a6;
        *((_BYTE *)v42 + v40) = 0;
      }
      v43 = a6;
      if ( a6[3] >= 0x10u )
        v43 = (_QWORD *)*a6;
      InternetReadFile(v24, (char *)v43 + v17, 0x400u, &dwNumberOfBytesRead);
      v17 += dwNumberOfBytesRead;
    }
    while ( dwNumberOfBytesRead );
    v44 = v17 + 1;
    v45 = a6[2];
    if ( v44 > v45 )
    {
      _mm_lfence();
      std::string::append(a6, v44 - v45, 0);
    }
    else
    {
      a6[2] = v44;
      v46 = a6;
      if ( a6[3] >= 0x10u )
        v46 = (_QWORD *)*a6;
      *((_BYTE *)v46 + v44) = 0;
    }
    InternetCloseHandle(v24);
    if ( v20 )
      InternetCloseHandle(v20);
    v47 = Buffer;
    if ( Buffer == 401 )
      goto LABEL_89;
    if ( Buffer == 200 )
      goto LABEL_89;
    v48 = v67++;
    v49 = v77;
    if ( v48 >= *v77 )
      goto LABEL_89;
    if ( GetTickCount() - TickCount >= v49[1] )
    {
      v47 = Buffer;
LABEL_89:
      v16 = v47;
      goto LABEL_114;
    }
    v50 = dwMilliseconds;
    Sleep(dwMilliseconds);
    dwMilliseconds = 2 * v50;
    v12 = v75;
    v13 = a9;
    if ( v80 >= 0x10 )
    {
      v51 = (CHAR *)lpszUrl[0];
      if ( v80 + 1 >= 0x1000 )
      {
        if ( ((__int64)lpszUrl[0] & 0x1F) != 0 )
          goto LABEL_119;
        v51 = (CHAR *)*((_QWORD *)lpszUrl[0] - 1);
        if ( v51 >= lpszUrl[0] || (unsigned __int64)(lpszUrl[0] - (LPCSTR)v51 - 8) > 0x1F )
          goto LABEL_119;
      }
      operator delete(v51);
    }
  }
  v25 = lpszUrl;
  if ( v80 >= 0x10 )
    v25 = (LPCSTR *)lpszUrl[0];
  v26 = strchr((const char *)v25 + 8, 47);
  v82 = 0;
  v83 = 15;
  LOBYTE(lpszObjectName[0]) = 0;
  std::string::assign(lpszObjectName);
  *v26 = 0;
  v27 = lpszUrl;
  if ( v80 >= 0x10 )
    v27 = (LPCSTR *)lpszUrl[0];
  v17 = 0;
  v20 = InternetConnectA(aadauth::AzureADAuth::m_hInternet, (LPCSTR)v27 + 8, 0x1BBu, 0, 0, 3u, 0, 0);
  if ( v20 )
  {
    lpszAcceptTypes[0] = "application/json";
    lpszAcceptTypes[1] = 0;
    v28 = (const CHAR *)lpszObjectName;
    if ( v83 >= 0x10 )
      v28 = lpszObjectName[0];
    v24 = HttpOpenRequestA(v20, "POST", v28, 0, 0, lpszAcceptTypes, 0x84AC0300, 0);
    if ( v24 )
    {
      v29 = (_BYTE *)a7;
      if ( *(_QWORD *)(a7 + 24) >= 0x10u )
        v29 = *(_BYTE **)a7;
      if ( *v29 == 123 )
        HttpAddRequestHeadersA(v24, "Content-Type: application/json\r\n", 0xFFFFFFFF, 0xA0000000);
      v30 = (void *)a7;
      if ( *(_QWORD *)(a7 + 24) >= 0x10u )
        v30 = *(void **)a7;
      if ( HttpSendRequestA(v24, lpszHeaders, 0xFFFFFFFF, v30, *(_DWORD *)(a7 + 16)) )
      {
        if ( v83 >= 0x10 )
        {
          v31 = (CHAR *)lpszObjectName[0];
          if ( v83 + 1 >= 0x1000 )
          {
            if ( ((__int64)lpszObjectName[0] & 0x1F) != 0
              || (v31 = (CHAR *)*((_QWORD *)lpszObjectName[0] - 1), v31 >= lpszObjectName[0])
              || (unsigned __int64)(lpszObjectName[0] - (LPCSTR)v31 - 8) > 0x1F )
            {
              _invalid_parameter_noinfo_noreturn();
            }
          }
          operator delete(v31);
        }
        v82 = 0;
        v83 = 15;
        LOBYTE(lpszObjectName[0]) = 0;
        goto LABEL_43;
      }
      v88[2] = 0;
      v89 = 7;
      LOWORD(v88[0]) = 0;
      std::wstring::_Construct<char *>(v88);
      v54 = v88;
      if ( v89 >= 8 )
        v54 = (_QWORD *)v88[0];
      v55 = GetLastError();
      v70(v69, 41354, v55, v54);
      InternetCloseHandle(v24);
      InternetCloseHandle(v20);
      v56 = v88;
    }
    else
    {
      v90[2] = 0;
      v91 = 7;
      LOWORD(v90[0]) = 0;
      std::wstring::_Construct<char *>(v90);
      v57 = v90;
      if ( v91 >= 8 )
        v57 = (_QWORD *)v90[0];
      v58 = GetLastError();
      v70(v69, 41352, v58, v57);
      InternetCloseHandle(v20);
      v56 = v90;
    }
    std::basic_string<char16_t>::_Tidy_deallocate(v56);
    goto LABEL_97;
  }
  v84[2] = 0;
  v85 = 7;
  LOWORD(v84[0]) = 0;
  std::wstring::_Construct<char *>(v84);
  v60 = v84;
  if ( v85 >= 8 )
    v60 = (_QWORD *)v84[0];
  v61 = GetLastError();
  v70(v69, 41353, v61, v60);
  if ( v85 >= 8 )
  {
    v62 = (void *)v84[0];
    if ( v85 + 1 > 0x7FFFFFFFFFFFFFFFLL
      || 2 * (v85 + 1) >= 0x1000
      && ((v84[0] & 0x1F) != 0
       || (v62 = *(void **)(v84[0] - 8LL), (unsigned __int64)v62 >= v84[0])
       || (unsigned __int64)(v84[0] - (_QWORD)v62 - 8LL) > 0x1F) )
    {
      _invalid_parameter_noinfo_noreturn();
    }
    operator delete(v62);
  }
LABEL_97:
  if ( v83 >= 0x10 )
  {
    v59 = (CHAR *)lpszObjectName[0];
    if ( v83 + 1 >= 0x1000 )
    {
      if ( ((__int64)lpszObjectName[0] & 0x1F) != 0
        || (v59 = (CHAR *)*((_QWORD *)lpszObjectName[0] - 1), v59 >= lpszObjectName[0])
        || (unsigned __int64)(lpszObjectName[0] - (LPCSTR)v59 - 8) > 0x1F )
      {
        _invalid_parameter_noinfo_noreturn();
      }
    }
    operator delete(v59);
  }
LABEL_114:
  if ( v80 >= 0x10 )
  {
    v63 = (CHAR *)lpszUrl[0];
    if ( v80 + 1 >= 0x1000 )
    {
      if ( ((__int64)lpszUrl[0] & 0x1F) != 0
        || (v63 = (CHAR *)*((_QWORD *)lpszUrl[0] - 1), v63 >= lpszUrl[0])
        || (unsigned __int64)(lpszUrl[0] - (LPCSTR)v63 - 8) > 0x1F )
      {
LABEL_119:
        _invalid_parameter_noinfo_noreturn();
      }
    }
    operator delete(v63);
  }
  return v16;
}

```

## disassembly

```asm
0x1004886ac  push    rbp
0x1004886ae  push    rbx
0x1004886af  push    rsi
0x1004886b0  push    rdi
0x1004886b1  push    r12
0x1004886b3  push    r13
0x1004886b5  push    r14
0x1004886b7  push    r15
0x1004886b9  lea     rbp, [rsp-88h]
0x1004886c1  sub     rsp, 188h
0x1004886c8  mov     [rbp+0C0h+var_118], 0FFFFFFFFFFFFFFFEh
0x1004886d0  mov     rax, cs:__security_cookie
0x1004886d7  xor     rax, rsp
0x1004886da  mov     [rbp+0C0h+var_50], rax
0x1004886de  mov     [rbp+0C0h+var_138], r9
0x1004886e2  mov     [rsp+1C0h+var_168], r8
0x1004886e7  mov     r15, rdx
0x1004886ea  mov     [rsp+1C0h+var_160], rdx
0x1004886ef  mov     rbx, rcx
0x1004886f2  mov     [rbp+0C0h+var_130], rcx
0x1004886f6  mov     rax, [rbp+0C0h+arg_20]
0x1004886fd  mov     [rsp+1C0h+lpszHeaders], rax
0x100488702  mov     rsi, [rbp+0C0h+arg_28]
0x100488709  mov     r12, [rbp+0C0h+arg_30]
0x100488710  mov     r14, [rbp+0C0h+arg_38]
0x100488717  mov     [rbp+0C0h+var_140], r14
0x10048871b  mov     r13b, [rbp+0C0h+arg_40]
0x100488722  mov     [rsp+1C0h+var_180], r13b
0x100488727  mov     rdi, [rbp+0C0h+arg_48]
0x10048872e  cmp     cs:?m_hInternet@AzureADAuth@aadauth@@0PEAXEA, 0; void * aadauth::AzureADAuth::m_hInternet
0x100488736  jnz     short loc_100488783
0x100488738  and     [rsp+1C0h+dwFlags], 0
0x10048873d  xor     r9d, r9d; lpszProxyBypass
0x100488740  xor     r8d, r8d; lpszProxy
0x100488743  xor     edx, edx; dwAccessType
0x100488745  lea     rcx, aAzureadauthpro; "AzureADAuthProvider"
0x10048874c  call    cs:__imp_InternetOpenA
0x100488752  mov     cs:?m_hInternet@AzureADAuth@aadauth@@0PEAXEA, rax; void * aadauth::AzureADAuth::m_hInternet
0x100488759  test    rax, rax
0x10048875c  jnz     short loc_100488783
0x10048875e  call    cs:__imp_GetLastError
0x100488764  mov     r8d, eax
0x100488767  mov     ebx, 0A187h
0x10048876c  mov     edx, ebx
0x10048876e  mov     rcx, [rsp+1C0h+var_168]
0x100488773  mov     rax, r15
0x100488776  call    cs:__guard_dispatch_icall_fptr
0x10048877c  mov     eax, ebx
0x10048877e  jmp     loc_100488F74
0x100488783  and     [rsp+1C0h+var_170], 0
0x100488788  mov     eax, [rbx+8]
0x10048878b  mov     [rsp+1C0h+dwMilliseconds], eax
0x10048878f  call    cs:__imp_GetTickCount
0x100488795  mov     [rsp+1C0h+var_150], eax
0x100488799  or      r15, 0FFFFFFFFFFFFFFFFh
0x10048879d  xor     ebx, ebx
0x10048879f  mov     [rbp+0C0h+var_100], rbx
0x1004887a3  mov     [rbp+0C0h+var_F8], 0Fh
0x1004887ab  mov     byte ptr [rbp+0C0h+lpszUrl], bl
0x1004887ae  mov     rdx, [rbp+0C0h+var_138]
0x1004887b2  lea     rcx, [rbp+0C0h+lpszUrl]; void *
0x1004887b6  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD@Z; std::string::assign(char const * const)
0x1004887bb  nop
0x1004887bc  test    r13b, r13b
0x1004887bf  jns     short loc_1004887CA
0x1004887c1  lea     rdx, qword_100558430
0x1004887c8  jmp     short loc_1004887DC
0x1004887ca  lfence
0x1004887cd  movsx   rax, r13b
0x1004887d1  lea     rdx, off_1005D0420; "?api-version=2015-06-01"
0x1004887d8  mov     rdx, [rdx+rax*8]
0x1004887dc  mov     r8, r15
0x1004887df  inc     r8
0x1004887e2  cmp     [rdx+r8], bl
0x1004887e6  jnz     short loc_1004887DF
0x1004887e8  lea     rcx, [rbp+0C0h+lpszUrl]; Src
0x1004887ec  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x1004887f1  mov     r13, rbx
0x1004887f4  test    r12, r12
0x1004887f7  jnz     loc_10048887E
0x1004887fd  test    r14, r14
0x100488800  jz      short loc_10048882F
0x100488802  lea     r8d, [r12+1]
0x100488807  lea     rdx, asc_10059B6DC; "&"
0x10048880e  lea     rcx, [rbp+0C0h+lpszUrl]; Src
0x100488812  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x100488817  mov     r8, r15
0x10048881a  inc     r8
0x10048881d  cmp     [r14+r8], bl
0x100488821  jnz     short loc_10048881A
0x100488823  mov     rdx, r14
0x100488826  lea     rcx, [rbp+0C0h+lpszUrl]; Src
0x10048882a  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x10048882f  lea     rdx, [rbp+0C0h+lpszUrl]
0x100488833  cmp     [rbp+0C0h+var_F8], 10h
0x100488838  cmovnb  rdx, [rbp+0C0h+lpszUrl]; lpszUrl
0x10048883d  mov     eax, 84AC0300h
0x100488842  mov     ecx, 842C0300h
0x100488847  cmp     [rsp+1C0h+var_180], bl
0x10048884b  cmovg   eax, ecx
0x10048884e  mov     [rsp+1C0h+dwContext], rbx; dwContext
0x100488853  mov     [rsp+1C0h+dwFlags], eax; dwFlags
0x100488857  or      r9d, 0FFFFFFFFh; dwHeadersLength
0x10048885b  mov     r8, [rsp+1C0h+lpszHeaders]; lpszHeaders
0x100488860  mov     rcx, cs:?m_hInternet@AzureADAuth@aadauth@@0PEAXEA; hInternet
0x100488867  call    cs:__imp_InternetOpenUrlA
0x10048886d  mov     r14, rax
0x100488870  test    rax, rax
0x100488873  jz      loc_100488C72
0x100488879  jmp     loc_100488A1B
0x10048887e  lea     rcx, [rbp+0C0h+lpszUrl]
0x100488882  cmp     [rbp+0C0h+var_F8], 10h
0x100488887  cmovnb  rcx, [rbp+0C0h+lpszUrl]
0x10048888c  add     rcx, 8; Str
0x100488890  mov     edx, 2Fh ; '/'; Val
0x100488895  call    cs:__imp_strchr
0x10048889b  mov     rbx, rax
0x10048889e  xor     r14d, r14d
0x1004888a1  mov     [rbp+0C0h+var_E0], r14
0x1004888a5  mov     [rbp+0C0h+var_D8], 0Fh
0x1004888ad  mov     byte ptr [rbp+0C0h+lpszObjectName], r14b
0x1004888b1  mov     rdx, rax
0x1004888b4  lea     rcx, [rbp+0C0h+lpszObjectName]; void *
0x1004888b8  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD@Z; std::string::assign(char const * const)
0x1004888bd  nop
0x1004888be  mov     [rbx], r14b
0x1004888c1  lea     rdx, [rbp+0C0h+lpszUrl]
0x1004888c5  cmp     [rbp+0C0h+var_F8], 10h
0x1004888ca  cmovnb  rdx, [rbp+0C0h+lpszUrl]
0x1004888cf  mov     r8d, 1BBh; nServerPort
0x1004888d5  add     rdx, 8; lpszServerName
0x1004888d9  xor     ebx, ebx
0x1004888db  mov     [rsp+1C0h+var_188], rbx; dwContext
0x1004888e0  mov     [rsp+1C0h+var_190], ebx; dwFlags
0x1004888e4  mov     dword ptr [rsp+1C0h+dwContext], 3; dwService
0x1004888ec  mov     qword ptr [rsp+1C0h+dwFlags], rbx; lpszPassword
0x1004888f1  xor     r9d, r9d; lpszUserName
0x1004888f4  mov     rcx, cs:?m_hInternet@AzureADAuth@aadauth@@0PEAXEA; hInternet
0x1004888fb  call    cs:__imp_InternetConnectA
0x100488901  mov     r13, rax
0x100488904  test    rax, rax
0x100488907  jz      loc_100488E55
0x10048890d  lea     rax, aApplicationJso; "application/json"
0x100488914  mov     [rbp+0C0h+lpszAcceptTypes], rax
0x100488918  mov     [rbp+0C0h+var_120], rbx
0x10048891c  lea     r8, [rbp+0C0h+lpszObjectName]
0x100488920  cmp     [rbp+0C0h+var_D8], 10h
0x100488925  cmovnb  r8, [rbp+0C0h+lpszObjectName]; lpszObjectName
0x10048892a  mov     [rsp+1C0h+var_188], rbx; dwContext
0x10048892f  mov     [rsp+1C0h+var_190], 84AC0300h; dwFlags
0x100488937  lea     rax, [rbp+0C0h+lpszAcceptTypes]
0x10048893b  mov     [rsp+1C0h+dwContext], rax; lplpszAcceptTypes
0x100488940  mov     qword ptr [rsp+1C0h+dwFlags], rbx; lpszReferrer
0x100488945  xor     r9d, r9d; lpszVersion
0x100488948  lea     rdx, szVerb; "POST"
0x10048894f  mov     rcx, r13; hConnect
0x100488952  call    cs:__imp_HttpOpenRequestA
0x100488958  mov     r14, rax
0x10048895b  test    rax, rax
0x10048895e  jz      loc_100488D89
0x100488964  mov     rax, r12
0x100488967  cmp     qword ptr [r12+18h], 10h
0x10048896d  jb      short loc_100488973
0x10048896f  mov     rax, [r12]
0x100488973  cmp     byte ptr [rax], 7Bh ; '{'
0x100488976  jnz     short loc_100488992
0x100488978  mov     r9d, 0A0000000h; dwModifiers
0x10048897e  or      r8d, 0FFFFFFFFh; dwHeadersLength
0x100488982  lea     rdx, szHeaders; "Content-Type: application/json\r\n"
0x100488989  mov     rcx, r14; hRequest
0x10048898c  call    cs:__imp_HttpAddRequestHeadersA
0x100488992  mov     r9, r12
0x100488995  cmp     qword ptr [r12+18h], 10h
0x10048899b  jb      short loc_1004889A1
0x10048899d  mov     r9, [r12]; lpOptional
0x1004889a1  mov     eax, [r12+10h]
0x1004889a6  mov     [rsp+1C0h+dwFlags], eax; dwOptionalLength
0x1004889aa  or      r8d, 0FFFFFFFFh; dwHeadersLength
0x1004889ae  mov     rdx, [rsp+1C0h+lpszHeaders]; lpszHeaders
0x1004889b3  mov     rcx, r14; hRequest
0x1004889b6  call    cs:__imp_HttpSendRequestA
0x1004889bc  test    eax, eax
0x1004889be  jz      loc_100488D02
0x1004889c4  mov     rax, [rbp+0C0h+var_D8]
0x1004889c8  cmp     rax, 10h
0x1004889cc  jb      short loc_100488A0C
0x1004889ce  inc     rax
0x1004889d1  mov     rcx, [rbp+0C0h+lpszObjectName]
0x1004889d5  mov     rdx, rcx
0x1004889d8  cmp     rax, 1000h
0x1004889de  jb      short loc_100488A07
0x1004889e0  test    dl, 1Fh
0x1004889e3  jnz     loc_100488CEF
0x1004889e9  mov     rcx, [rcx-8]; void *
0x1004889ed  cmp     rcx, rdx
0x1004889f0  jnb     loc_100488CEF
0x1004889f6  sub     rdx, rcx
0x1004889f9  sub     rdx, 8
0x1004889fd  cmp     rdx, 1Fh
0x100488a01  ja      loc_100488CEF
0x100488a07  call    ??3@YAXPEAX@Z; operator delete(void *)
0x100488a0c  mov     [rbp+0C0h+var_E0], rbx
0x100488a10  mov     [rbp+0C0h+var_D8], 0Fh
0x100488a18  mov     byte ptr [rbp+0C0h+lpszObjectName], bl
0x100488a1b  mov     [rsp+1C0h+dwBufferLength], 4
0x100488a23  mov     [rsp+1C0h+dwIndex], ebx
0x100488a27  lea     rax, [rsp+1C0h+dwIndex]
0x100488a2c  mov     qword ptr [rsp+1C0h+dwFlags], rax; lpdwIndex
0x100488a31  lea     r9, [rsp+1C0h+dwBufferLength]; lpdwBufferLength
0x100488a36  lea     r8, [rsp+1C0h+Buffer]; lpBuffer
0x100488a3b  mov     edx, 20000013h; dwInfoLevel
0x100488a40  mov     rcx, r14; hRequest
0x100488a43  call    cs:__imp_HttpQueryInfoA
0x100488a49  mov     ecx, [rsp+1C0h+Buffer]
0x100488a4d  test    eax, eax
0x100488a4f  cmovz   ecx, r15d
0x100488a53  mov     [rsp+1C0h+Buffer], ecx
0x100488a57  test    rdi, rdi
0x100488a5a  jz      loc_100488B09
0x100488a60  mov     [rsp+1C0h+var_174], ebx
0x100488a64  mov     [rsp+1C0h+dwIndex], ebx
0x100488a68  mov     r8, rdi
0x100488a6b  cmp     qword ptr [rdi+18h], 10h
0x100488a70  jb      short loc_100488A75
0x100488a72  mov     r8, [rdi]; lpBuffer
0x100488a75  lea     rax, [rsp+1C0h+dwIndex]
0x100488a7a  mov     qword ptr [rsp+1C0h+dwFlags], rax; lpdwIndex
0x100488a7f  lea     r9, [rsp+1C0h+var_174]; lpdwBufferLength
0x100488a84  mov     edx, 28h ; '('; dwInfoLevel
0x100488a89  mov     rcx, r14; hRequest
0x100488a8c  call    cs:__imp_HttpQueryInfoA
0x100488a92  mov     edx, [rsp+1C0h+var_174]
0x100488a96  inc     edx
0x100488a98  mov     rax, [rdi+10h]
0x100488a9c  cmp     rdx, rax
0x100488a9f  ja      short loc_100488AB7
0x100488aa1  mov     [rdi+10h], rdx
0x100488aa5  mov     rax, rdi
0x100488aa8  cmp     qword ptr [rdi+18h], 10h
0x100488aad  jb      short loc_100488AB2
0x100488aaf  mov     rax, [rdi]
0x100488ab2  mov     [rax+rdx], bl
0x100488ab5  jmp     short loc_100488AC8
0x100488ab7  lfence
0x100488aba  sub     rdx, rax; Size
0x100488abd  xor     r8d, r8d; char
0x100488ac0  mov     rcx, rdi; Src
0x100488ac3  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@_KD@Z; std::string::append(unsigned __int64,char)
0x100488ac8  mov     r8, rdi
0x100488acb  cmp     qword ptr [rdi+18h], 10h
0x100488ad0  jb      short loc_100488AD5
0x100488ad2  mov     r8, [rdi]; lpBuffer
0x100488ad5  lea     rax, [rsp+1C0h+dwIndex]
0x100488ada  mov     qword ptr [rsp+1C0h+dwFlags], rax; lpdwIndex
0x100488adf  lea     r9, [rsp+1C0h+var_174]; lpdwBufferLength
0x100488ae4  mov     edx, 28h ; '('; dwInfoLevel
0x100488ae9  mov     rcx, r14; hRequest
0x100488aec  call    cs:__imp_HttpQueryInfoA
0x100488af2  test    eax, eax
0x100488af4  jnz     short loc_100488B09
0x100488af6  mov     [rdi+10h], rbx
0x100488afa  mov     rax, rdi
0x100488afd  cmp     qword ptr [rdi+18h], 10h
0x100488b02  jb      short loc_100488B07
0x100488b04  mov     rax, [rdi]
0x100488b07  mov     [rax], bl
0x100488b09  lea     edx, [rbx+400h]
0x100488b0f  mov     rax, [rsi+10h]
0x100488b13  cmp     rdx, rax
0x100488b16  ja      short loc_100488B2F
0x100488b18  mov     [rsi+10h], rdx
0x100488b1c  mov     rax, rsi
0x100488b1f  cmp     qword ptr [rsi+18h], 10h
0x100488b24  jb      short loc_100488B29
0x100488b26  mov     rax, [rsi]
0x100488b29  mov     byte ptr [rax+rdx], 0
0x100488b2d  jmp     short loc_100488B40
0x100488b2f  lfence
0x100488b32  sub     rdx, rax; Size
0x100488b35  xor     r8d, r8d; char
0x100488b38  mov     rcx, rsi; Src
0x100488b3b  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@_KD@Z; std::string::append(unsigned __int64,char)
0x100488b40  mov     rax, rsi
0x100488b43  cmp     qword ptr [rsi+18h], 10h
0x100488b48  jb      short loc_100488B4D
0x100488b4a  mov     rax, [rsi]
0x100488b4d  mov     edx, ebx
0x100488b4f  add     rdx, rax; lpBuffer
0x100488b52  lea     r9, [rsp+1C0h+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x100488b57  mov     r8d, 400h; dwNumberOfBytesToRead
0x100488b5d  mov     rcx, r14; hFile
0x100488b60  call    cs:__imp_InternetReadFile
0x100488b66  mov     eax, [rsp+1C0h+dwNumberOfBytesRead]
0x100488b6a  add     ebx, eax
0x100488b6c  test    eax, eax
0x100488b6e  jnz     short loc_100488B09
0x100488b70  lea     edx, [rbx+1]
0x100488b73  mov     rax, [rsi+10h]
0x100488b77  cmp     rdx, rax
0x100488b7a  ja      short loc_100488B93
  ... truncated ...
```
