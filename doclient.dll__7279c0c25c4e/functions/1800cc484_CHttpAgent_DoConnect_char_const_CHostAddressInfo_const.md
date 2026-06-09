# CHttpAgent::_DoConnect(char const *,CHostAddressInfo const *)

- ea: `0x1800cc484`
- end: `0x1800ccb1d`
- name: `?_DoConnect@CHttpAgent@@AEAAJPEBDPEBVCHostAddressInfo@@@Z`
- size: `1689`
- prototype: `int(CHttpAgent *__hidden this, const char *, const struct CHostAddressInfo *)`
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800cb870`
- `0x1800cb8e0`

## callees

- `0x180007c24`
- `0x180008618`
- `0x1800095a0`
- `0x180009ab4`
- `0x18000ecf0`
- `0x18000ef98`
- `0x1800179a4`
- `0x1800199b4`
- `0x180019c5c`
- `0x1800a1ea4`
- `0x1800a1f08`
- `0x1800a979c`
- `0x1800c3e5c`
- `0x1800c3f2c`
- `0x1800cc484`
- `0x1800cf144`
- `0x1800f82f0`
- `0x180108ed0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cca14`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cca89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cca14`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cca89`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800cc9fe`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800cca73`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800cc9fe`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800cca73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cc7f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cc8bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cc99f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cc7f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cc8bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cc99f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800cc9b2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800cc9b2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cc51f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cc60d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cc661`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cc6b2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cca48`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ccabd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cc51f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cc60d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cc661`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cc6b2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cca48`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ccabd`
- `WINHTTP!WinHttpSetOption` at `0x1800cc7e6`
- `WINHTTP!WinHttpSetOption` at `0x1800cc8b0`
- `WINHTTP!WinHttpSetOption` at `0x1800cc7e6`
- `WINHTTP!WinHttpSetOption` at `0x1800cc8b0`
- `WINHTTP!WinHttpCrackUrl` at `0x1800cc5c9`
- `WINHTTP!WinHttpCrackUrl` at `0x1800cc5c9`
- `WINHTTP!WinHttpConnect` at `0x1800cc98d`
- `WINHTTP!WinHttpConnect` at `0x1800cc98d`
- `WINHTTP!WinHttpCloseHandle` at `0x1800cc9aa`
- `WINHTTP!WinHttpCloseHandle` at `0x1800cc9aa`

## string_xrefs

- `0x1800cc5db`: `C:\__w\1\s\src\DeliveryOptimization\Util\win10\HttpAgent.cpp`
- `0x1800cc62f`: `C:\__w\1\s\src\DeliveryOptimization\Util\win10\HttpAgent.cpp`
- `0x1800cc680`: `C:\__w\1\s\src\DeliveryOptimization\Util\win10\HttpAgent.cpp`
- `0x1800cc9cd`: `C:\__w\1\s\src\DeliveryOptimization\Util\win10\HttpAgent.cpp`
- `0x1800cc54b`: `CHttpAgent::_DoConnect`
- `0x1800cc868`: `CHttpAgent::_DoConnect`
- `0x1800cc8f7`: `CHttpAgent::_DoConnect`
- `0x1800cc959`: `CHttpAgent::_DoConnect`
- `0x1800cc85b`: `Failed to associate the URL cache entry with an address info; hr = %x, host: %ls, IP: %s)`
- `0x1800cc8e2`: `Attempted to enable rLEDBAT, background? %u`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CHttpAgent::_DoConnect(CHttpAgent *this, const char *a2, INTERNET_PORT *a3)
{
  char *v6; // rdi
  int v7; // eax
  const char *v8; // r9
  int v9; // eax
  int v10; // eax
  __int64 result; // rax
  const WCHAR *v12; // rcx
  const char *v13; // r9
  unsigned int LastError; // ebx
  bool v15; // zf
  LPSTR lpszUrlPath; // rdx
  unsigned int v17; // ebx
  unsigned int v18; // ebx
  INTERNET_PORT nPort; // r14
  INTERNET_PORT v20; // r12
  __int64 v21; // rax
  LPCWSTR *v22; // rax
  signed int v23; // eax
  unsigned int v24; // ebx
  unsigned int v25; // edx
  const char *v26; // rcx
  const wchar_t *v27; // rax
  signed int v28; // eax
  const char *v29; // r8
  const wchar_t *v30; // rcx
  const WCHAR *v31; // rdx
  const char *v32; // r9
  HINTERNET v33; // r14
  void *v34; // r15
  DWORD v35; // ebx
  unsigned int v36; // esi
  _QWORD v37[4]; // [rsp+58h] [rbp-150h] BYREF
  _QWORD Buffer[3]; // [rsp+78h] [rbp-130h] BYREF
  struct $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+90h] [rbp-118h] BYREF
  int v40; // [rsp+100h] [rbp-A8h] BYREF
  LPCWSTR pswzServerName[2]; // [rsp+108h] [rbp-A0h] BYREF
  __int128 v42; // [rsp+118h] [rbp-90h]
  __int128 v43; // [rsp+128h] [rbp-80h] BYREF
  __m128i si128; // [rsp+138h] [rbp-70h]
  LPCWSTR pwszUrl[4]; // [rsp+148h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  v6 = (char *)this + 280;
  v7 = mtx_do_lock((char *)this + 280);
  try
  {
    if ( v7 )
      std::_Throw_Cpp_error(5);
    v9 = *((_DWORD *)this + 89);
    if ( v9 == 0x7FFFFFFF )
    {
      *((_DWORD *)this + 89) = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    if ( *((_BYTE *)this + 387) )
    {
      v10 = v9 - 1;
      *((_DWORD *)this + 89) = v10;
      if ( !v10 )
      {
        *((_DWORD *)this + 88) = -1;
        ReleaseSRWLockExclusive((PSRWLOCK)this + 37);
      }
      return 2147500036LL;
    }
    if ( !*((_QWORD *)this + 2) )
    {
      LogMessage(5u, "CHttpAgent::_DoConnect", 0x215u, "Establishing HTTP Connection to %s", a2);
      UTF8toWstr(pwszUrl, a2, 0);
      memset(&UrlComponents, 0, sizeof(UrlComponents));
      UrlComponents.dwStructSize = 104;
      UrlComponents.dwUrlPathLength = 1;
      UrlComponents.dwHostNameLength = 1;
      v12 = (const WCHAR *)pwszUrl;
      if ( pwszUrl[3] > (LPCWSTR)7 )
        v12 = pwszUrl[0];
      if ( !WinHttpCrackUrl(v12, 0, 0, &UrlComponents) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x21C,
                      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\HttpAgent.cpp",
                      v13);
        std::wstring::~wstring((__int64)pwszUrl);
        v15 = (*((_DWORD *)v6 + 19))-- == 1;
        if ( v15 )
        {
          *((_DWORD *)v6 + 18) = -1;
          ReleaseSRWLockExclusive((PSRWLOCK)v6 + 2);
        }
        return LastError;
      }
      lpszUrlPath = UrlComponents.lpszUrlPath;
      if ( !UrlComponents.lpszUrlPath )
      {
        v17 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x21D,
                (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\HttpAgent.cpp",
                v13);
        std::wstring::~wstring((__int64)pwszUrl);
        v15 = (*((_DWORD *)v6 + 19))-- == 1;
        if ( v15 )
        {
          *((_DWORD *)v6 + 18) = -1;
          ReleaseSRWLockExclusive((PSRWLOCK)v6 + 2);
        }
        return v17;
      }
      if ( !UrlComponents.lpszHostName )
      {
        v18 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x21E,
                (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\HttpAgent.cpp",
                v13);
        std::wstring::~wstring((__int64)pwszUrl);
        v15 = (*((_DWORD *)v6 + 19))-- == 1;
        if ( v15 )
        {
          *((_DWORD *)v6 + 18) = -1;
          ReleaseSRWLockExclusive((PSRWLOCK)v6 + 2);
        }
        return v18;
      }
      *((_DWORD *)this + 39) = UrlComponents.nScheme;
      std::wstring::operator=((char *)this + 160, lpszUrlPath);
      *(_OWORD *)pswzServerName = 0;
      v42 = 0;
      std::wstring::_Construct<1,wchar_t const *>(pswzServerName, UrlComponents.lpszHostName);
      CHttpAgent::_ImpersonateUserToken((__int64)this);
      v43 = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOBYTE(v43) = 0;
      nPort = UrlComponents.nPort;
      v20 = UrlComponents.nPort;
      if ( !a3 )
        goto LABEL_40;
      *((_BYTE *)this + 389) = CHostAddressInfo::IsLocalHost((CHostAddressInfo *)a3);
      if ( !*(_QWORD *)a3 )
        goto LABEL_40;
      v21 = CHostAddressInfo::SockAddressOrHostName(a3, v37);
      std::string::operator=(&v43, v21);
      std::string::~string(v37);
      nPort = a3[12];
      if ( !nPort )
        nPort = v20;
      v22 = pswzServerName;
      if ( *((_QWORD *)&v42 + 1) > 7u )
        v22 = (LPCWSTR *)pswzServerName[0];
      Buffer[0] = v22;
      Buffer[1] = *(_QWORD *)a3;
      if ( !WinHttpSetOption(*((HINTERNET *)this + 1), 0x7Fu, Buffer, 0x10u) )
      {
        v23 = GetLastError();
        v24 = -2147467259;
        if ( v23 )
        {
          v25 = (unsigned __int16)v23 | 0x80070000;
          if ( v23 <= 0 )
            v25 = v23;
        }
        else
        {
          v25 = -2147467259;
        }
        v26 = (const char *)&v43;
        if ( si128.m128i_i64[1] > 0xFuLL )
          v26 = (const char *)v43;
        v27 = (const wchar_t *)pswzServerName;
        if ( *((_QWORD *)&v42 + 1) > 7u )
          v27 = pswzServerName[0];
        LogMessage(
          3u,
          "CHttpAgent::_DoConnect",
          0x243u,
          "Failed to associate the URL cache entry with an address info; hr = %x, host: %ls, IP: %s)",
          v25,
          v27,
          v26);
      }
      else
      {
LABEL_40:
        v24 = -2147467259;
      }
      if ( !*((_BYTE *)this + 389) && *((_BYTE *)this + 386) )
      {
        v40 = 0;
        if ( WinHttpSetOption(*((HINTERNET *)this + 1), 0x80u, &v40, 4u) )
        {
          v24 = 0;
        }
        else
        {
          v28 = GetLastError();
          if ( v28 )
          {
            v24 = (unsigned __int16)v28 | 0x80070000;
            if ( v28 <= 0 )
              v24 = v28;
          }
        }
        LogResult(
          5u,
          "CHttpAgent::_DoConnect",
          0x24Du,
          v24,
          "Attempted to enable rLEDBAT, background? %u",
          *((unsigned __int8 *)this + 388));
      }
      v29 = (const char *)&v43;
      if ( si128.m128i_i64[1] > 0xFuLL )
        v29 = (const char *)v43;
      v30 = (const wchar_t *)pswzServerName;
      if ( *((_QWORD *)&v42 + 1) > 7u )
        v30 = pswzServerName[0];
      LogMessage(
        5u,
        "CHttpAgent::_DoConnect",
        0x252u,
        "Connecting to the following host: %ls, IP: [%s]:%u",
        v30,
        v29,
        nPort);
      v31 = (const WCHAR *)pswzServerName;
      if ( *((_QWORD *)&v42 + 1) > 7u )
        v31 = pswzServerName[0];
      v33 = WinHttpConnect(*((HINTERNET *)this + 1), v31, nPort, 0);
      v34 = (void *)*((_QWORD *)this + 2);
      if ( v34 )
      {
        v35 = GetLastError();
        WinHttpCloseHandle(v34);
        SetLastError(v35);
      }
      *((_QWORD *)this + 2) = v33;
      if ( !v33 )
      {
        v36 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x254,
                (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\HttpAgent.cpp",
                v32);
        std::string::~string(&v43);
        std::wstring::~wstring((__int64)pswzServerName);
        std::wstring::~wstring((__int64)pwszUrl);
        v15 = (*((_DWORD *)v6 + 19))-- == 1;
        if ( v15 )
        {
          *((_DWORD *)v6 + 18) = -1;
          ReleaseSRWLockExclusive((PSRWLOCK)v6 + 2);
        }
        return v36;
      }
      std::string::~string(&v43);
      std::wstring::~wstring((__int64)pswzServerName);
      std::wstring::~wstring((__int64)pwszUrl);
    }
    v15 = (*((_DWORD *)v6 + 19))-- == 1;
    if ( v15 )
    {
      *((_DWORD *)v6 + 18) = -1;
      ReleaseSRWLockExclusive((PSRWLOCK)v6 + 2);
    }
    result = 0;
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x258,
                           (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\HttpAgent.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x1800cc484  push    rbx
0x1800cc486  push    rsi
0x1800cc487  push    rdi
0x1800cc488  push    r12
0x1800cc48a  push    r13
0x1800cc48c  push    r14
0x1800cc48e  push    r15
0x1800cc490  sub     rsp, 170h
0x1800cc497  mov     rax, cs:__security_cookie
0x1800cc49e  xor     rax, rsp
0x1800cc4a1  mov     [rsp+1A8h+var_40], rax
0x1800cc4a9  mov     rbx, r8
0x1800cc4ac  mov     r14, rdx
0x1800cc4af  mov     rsi, rcx
0x1800cc4b2  xorps   xmm0, xmm0
0x1800cc4b5  movups  [rsp+1A8h+var_160], xmm0
0x1800cc4ba  lea     rdi, [rcx+118h]
0x1800cc4c1  mov     qword ptr [rsp+1A8h+var_160], rdi
0x1800cc4c6  xor     r13d, r13d
0x1800cc4c9  mov     byte ptr [rsp+1A8h+var_160+8], r13b
0x1800cc4ce  mov     rcx, rdi
0x1800cc4d1  call    mtx_do_lock
0x1800cc4d6  test    eax, eax
0x1800cc4d8  jnz     loc_1800CCAF8
0x1800cc4de  mov     eax, [rsi+164h]
0x1800cc4e4  cmp     eax, 7FFFFFFFh
0x1800cc4e9  jz      loc_1800CCB01
0x1800cc4ef  mov     r12d, 1
0x1800cc4f5  mov     byte ptr [rsp+1A8h+var_160+8], r12b
0x1800cc4fa  cmp     [rsi+183h], r13b
0x1800cc501  jz      short loc_1800CC52F
0x1800cc503  sub     eax, r12d
0x1800cc506  mov     [rsi+164h], eax
0x1800cc50c  jnz     short loc_1800CC525
0x1800cc50e  mov     dword ptr [rsi+160h], 0FFFFFFFFh
0x1800cc518  lea     rcx, [rsi+128h]; SRWLock
0x1800cc51f  call    cs:__imp_ReleaseSRWLockExclusive
0x1800cc525  mov     eax, 80004004h
0x1800cc52a  jmp     loc_1800CCAD5
0x1800cc52f  cmp     [rsi+10h], r13
0x1800cc533  jnz     loc_1800CCAAC
0x1800cc539  mov     [rsp+1A8h+var_188], r14
0x1800cc53e  lea     r9, aEstablishingHt; "Establishing HTTP Connection to %s"
0x1800cc545  mov     r8d, 215h; unsigned int
0x1800cc54b  lea     rdx, aChttpagentDoco; "CHttpAgent::_DoConnect"
0x1800cc552  mov     r15d, 5
0x1800cc558  mov     ecx, r15d; unsigned __int8
0x1800cc55b  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x1800cc560  xor     r8d, r8d
0x1800cc563  mov     rdx, r14
0x1800cc566  lea     rcx, [rsp+1A8h+pwszUrl]
0x1800cc56e  call    ?UTF8toWstr@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBD_K@Z; UTF8toWstr(char const *,unsigned __int64)
0x1800cc573  nop
0x1800cc574  lea     r14d, [r15+63h]
0x1800cc578  mov     r8d, r14d; Size
0x1800cc57b  xor     edx, edx; Val
0x1800cc57d  lea     rcx, [rsp+1A8h+UrlComponents]; void *
0x1800cc585  call    memset
0x1800cc58a  mov     [rsp+1A8h+UrlComponents.dwStructSize], r14d
0x1800cc592  mov     [rsp+1A8h+UrlComponents.dwUrlPathLength], r12d
0x1800cc59a  mov     [rsp+1A8h+UrlComponents.dwHostNameLength], r12d
0x1800cc5a2  lea     rcx, [rsp+1A8h+pwszUrl]
0x1800cc5aa  cmp     [rsp+1A8h+var_48], 7
0x1800cc5b3  cmova   rcx, [rsp+1A8h+pwszUrl]; pwszUrl
0x1800cc5bc  lea     r9, [rsp+1A8h+UrlComponents]; lpUrlComponents
0x1800cc5c4  xor     r8d, r8d; dwFlags
0x1800cc5c7  xor     edx, edx; dwUrlLength
0x1800cc5c9  call    cs:__imp_WinHttpCrackUrl
0x1800cc5cf  test    eax, eax
0x1800cc5d1  jnz     short loc_1800CC61A
0x1800cc5d3  mov     rcx, [rsp+1A8h]; this
0x1800cc5db  lea     r8, aCW1SSrcDeliver_73; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800cc5e2  mov     edx, 21Ch; void *
0x1800cc5e7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800cc5ec  mov     ebx, eax
0x1800cc5ee  lea     rcx, [rsp+1A8h+pwszUrl]
0x1800cc5f6  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800cc5fb  nop
0x1800cc5fc  sub     dword ptr [rdi+4Ch], 1
0x1800cc600  jnz     short loc_1800CC613
0x1800cc602  mov     dword ptr [rdi+48h], 0FFFFFFFFh
0x1800cc609  lea     rcx, [rdi+10h]; SRWLock
0x1800cc60d  call    cs:__imp_ReleaseSRWLockExclusive
0x1800cc613  mov     eax, ebx
0x1800cc615  jmp     loc_1800CCAD5
0x1800cc61a  mov     rdx, [rsp+1A8h+UrlComponents.lpszUrlPath]; Src
0x1800cc622  test    rdx, rdx
0x1800cc625  jnz     short loc_1800CC66E
0x1800cc627  mov     rcx, [rsp+1A8h]; this
0x1800cc62f  lea     r8, aCW1SSrcDeliver_73; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800cc636  mov     edx, 21Dh; void *
0x1800cc63b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800cc640  mov     ebx, eax
0x1800cc642  lea     rcx, [rsp+1A8h+pwszUrl]
0x1800cc64a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800cc64f  nop
0x1800cc650  sub     dword ptr [rdi+4Ch], 1
0x1800cc654  jnz     short loc_1800CC667
0x1800cc656  mov     dword ptr [rdi+48h], 0FFFFFFFFh
0x1800cc65d  lea     rcx, [rdi+10h]; SRWLock
0x1800cc661  call    cs:__imp_ReleaseSRWLockExclusive
0x1800cc667  mov     eax, ebx
0x1800cc669  jmp     loc_1800CCAD5
0x1800cc66e  cmp     [rsp+1A8h+UrlComponents.lpszHostName], r13
0x1800cc676  jnz     short loc_1800CC6BF
0x1800cc678  mov     rcx, [rsp+1A8h]; this
0x1800cc680  lea     r8, aCW1SSrcDeliver_73; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800cc687  mov     edx, 21Eh; void *
0x1800cc68c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800cc691  mov     ebx, eax
0x1800cc693  lea     rcx, [rsp+1A8h+pwszUrl]
0x1800cc69b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800cc6a0  nop
0x1800cc6a1  sub     dword ptr [rdi+4Ch], 1
0x1800cc6a5  jnz     short loc_1800CC6B8
0x1800cc6a7  mov     dword ptr [rdi+48h], 0FFFFFFFFh
0x1800cc6ae  lea     rcx, [rdi+10h]; SRWLock
0x1800cc6b2  call    cs:__imp_ReleaseSRWLockExclusive
0x1800cc6b8  mov     eax, ebx
0x1800cc6ba  jmp     loc_1800CCAD5
0x1800cc6bf  mov     eax, [rsp+1A8h+UrlComponents.nScheme]
0x1800cc6c6  mov     [rsi+9Ch], eax
0x1800cc6cc  lea     rcx, [rsi+0A0h]; void *
0x1800cc6d3  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@QEB_W@Z; std::wstring::operator=(wchar_t const * const)
0x1800cc6d8  xorps   xmm0, xmm0
0x1800cc6db  movups  xmmword ptr [rsp+1A8h+pswzServerName], xmm0
0x1800cc6e3  xorps   xmm1, xmm1
0x1800cc6e6  movdqu  [rsp+1A8h+var_90], xmm1
0x1800cc6ef  mov     r8d, [rsp+1A8h+UrlComponents.dwHostNameLength]
0x1800cc6f7  mov     rdx, [rsp+1A8h+UrlComponents.lpszHostName]
0x1800cc6ff  lea     rcx, [rsp+1A8h+pswzServerName]
0x1800cc707  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800cc70c  nop
0x1800cc70d  mov     [rsp+1A8h+Token], 0FFFFFFFFFFFFFFFFh
0x1800cc716  lea     rdx, [rsp+1A8h+Token]
0x1800cc71b  mov     rcx, rsi
0x1800cc71e  call    ?_ImpersonateUserToken@CHttpAgent@@AEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@wil@@@Z; CHttpAgent::_ImpersonateUserToken(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)
0x1800cc723  xorps   xmm0, xmm0
0x1800cc726  movups  [rsp+1A8h+var_80], xmm0
0x1800cc72e  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x1800cc736  movdqu  [rsp+1A8h+var_70], xmm1
0x1800cc73f  mov     byte ptr [rsp+1A8h+var_80], r13b
0x1800cc747  movzx   r14d, [rsp+1A8h+UrlComponents.nPort]
0x1800cc750  movzx   r12d, r14w
0x1800cc754  test    rbx, rbx
0x1800cc757  jz      loc_1800CC87B
0x1800cc75d  mov     rcx, rbx; this
0x1800cc760  call    ?IsLocalHost@CHostAddressInfo@@QEBA_NXZ; CHostAddressInfo::IsLocalHost(void)
0x1800cc765  mov     [rsi+185h], al
0x1800cc76b  cmp     [rbx], r13
0x1800cc76e  jz      loc_1800CC87B
0x1800cc774  lea     rdx, [rsp+1A8h+var_150]
0x1800cc779  mov     rcx, rbx
0x1800cc77c  call    ?SockAddressOrHostName@CHostAddressInfo@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; CHostAddressInfo::SockAddressOrHostName(void)
0x1800cc781  mov     rdx, rax
0x1800cc784  lea     rcx, [rsp+1A8h+var_80]
0x1800cc78c  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x1800cc791  lea     rcx, [rsp+1A8h+var_150]; void *
0x1800cc796  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800cc79b  movzx   r14d, word ptr [rbx+18h]
0x1800cc7a0  test    r14w, r14w
0x1800cc7a4  cmovz   r14w, r12w
0x1800cc7a9  lea     rax, [rsp+1A8h+pswzServerName]
0x1800cc7b1  cmp     qword ptr [rsp+1A8h+var_90+8], 7
0x1800cc7ba  cmova   rax, [rsp+1A8h+pswzServerName]
0x1800cc7c3  mov     [rsp+1A8h+Buffer], rax
0x1800cc7c8  mov     rax, [rbx]
0x1800cc7cb  mov     [rsp+1A8h+var_128], rax
0x1800cc7d3  mov     r9d, 10h; dwBufferLength
0x1800cc7d9  lea     r8, [rsp+1A8h+Buffer]; lpBuffer
0x1800cc7de  lea     edx, [r9+6Fh]; dwOption
0x1800cc7e2  mov     rcx, [rsi+8]; hInternet
0x1800cc7e6  call    cs:__imp_WinHttpSetOption
0x1800cc7ec  test    eax, eax
0x1800cc7ee  jnz     loc_1800CC87B
0x1800cc7f4  call    cs:__imp_GetLastError
0x1800cc7fa  mov     ebx, 80004005h
0x1800cc7ff  test    eax, eax
0x1800cc801  jz      short loc_1800CC817
0x1800cc803  movzx   edx, ax
0x1800cc806  or      edx, 80070000h
0x1800cc80c  test    eax, eax
0x1800cc80e  cmovle  edx, eax
0x1800cc811  test    edx, edx
0x1800cc813  js      short loc_1800CC819
0x1800cc815  jmp     short loc_1800CC880
0x1800cc817  mov     edx, ebx
0x1800cc819  lea     rcx, [rsp+1A8h+var_80]
0x1800cc821  cmp     qword ptr [rsp+1A8h+var_70+8], 0Fh
0x1800cc82a  cmova   rcx, qword ptr [rsp+1A8h+var_80]
0x1800cc833  lea     rax, [rsp+1A8h+pswzServerName]
0x1800cc83b  cmp     qword ptr [rsp+1A8h+var_90+8], 7
0x1800cc844  cmova   rax, [rsp+1A8h+pswzServerName]
0x1800cc84d  mov     [rsp+1A8h+var_178], rcx
0x1800cc852  mov     [rsp+1A8h+var_180], rax
0x1800cc857  mov     dword ptr [rsp+1A8h+var_188], edx
0x1800cc85b  lea     r9, aFailedToAssoci; "Failed to associate the URL cache entry"...
0x1800cc862  mov     r8d, 243h; unsigned int
0x1800cc868  lea     rdx, aChttpagentDoco; "CHttpAgent::_DoConnect"
0x1800cc86f  mov     ecx, 3; unsigned __int8
0x1800cc874  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x1800cc879  jmp     short loc_1800CC880
0x1800cc87b  mov     ebx, 80004005h
0x1800cc880  cmp     [rsi+185h], r13b
0x1800cc887  jnz     short loc_1800CC906
0x1800cc889  cmp     [rsi+182h], r13b
0x1800cc890  jz      short loc_1800CC906
0x1800cc892  mov     [rsp+1A8h+var_A8], r13d
0x1800cc89a  mov     r9d, 4; dwBufferLength
0x1800cc8a0  lea     r8, [rsp+1A8h+var_A8]; lpBuffer
0x1800cc8a8  lea     edx, [r9+7Ch]; dwOption
0x1800cc8ac  mov     rcx, [rsi+8]; hInternet
0x1800cc8b0  call    cs:__imp_WinHttpSetOption
0x1800cc8b6  test    eax, eax
0x1800cc8b8  jz      short loc_1800CC8BF
0x1800cc8ba  mov     ebx, r13d
0x1800cc8bd  jmp     short loc_1800CC8D7
0x1800cc8bf  call    cs:__imp_GetLastError
0x1800cc8c5  test    eax, eax
0x1800cc8c7  jz      short loc_1800CC8D7
0x1800cc8c9  movzx   ebx, ax
0x1800cc8cc  or      ebx, 80070000h
0x1800cc8d2  test    eax, eax
0x1800cc8d4  cmovle  ebx, eax
0x1800cc8d7  movzx   eax, byte ptr [rsi+184h]
0x1800cc8de  mov     dword ptr [rsp+1A8h+var_180], eax
0x1800cc8e2  lea     rax, aAttemptedToEna; "Attempted to enable rLEDBAT, background"...
0x1800cc8e9  mov     [rsp+1A8h+var_188], rax; char *
0x1800cc8ee  mov     r9d, ebx; int
0x1800cc8f1  mov     r8d, 24Dh; unsigned int
0x1800cc8f7  lea     rdx, aChttpagentDoco; "CHttpAgent::_DoConnect"
0x1800cc8fe  mov     ecx, r15d; unsigned __int8
0x1800cc901  call    ?LogResult@@YAXEPEBDIJ0ZZ; LogResult(uchar,char const *,uint,long,char const *,...)
0x1800cc906  lea     r8, [rsp+1A8h+var_80]
0x1800cc90e  cmp     qword ptr [rsp+1A8h+var_70+8], 0Fh
0x1800cc917  cmova   r8, qword ptr [rsp+1A8h+var_80]
0x1800cc920  lea     rcx, [rsp+1A8h+pswzServerName]
0x1800cc928  cmp     qword ptr [rsp+1A8h+var_90+8], 7
0x1800cc931  cmova   rcx, [rsp+1A8h+pswzServerName]
0x1800cc93a  movzx   eax, r14w
0x1800cc93e  mov     dword ptr [rsp+1A8h+var_178], eax
0x1800cc942  mov     [rsp+1A8h+var_180], r8
0x1800cc947  mov     [rsp+1A8h+var_188], rcx
0x1800cc94c  lea     r9, aConnectingToTh; "Connecting to the following host: %ls, "...
0x1800cc953  mov     r8d, 252h; unsigned int
0x1800cc959  lea     rdx, aChttpagentDoco; "CHttpAgent::_DoConnect"
0x1800cc960  mov     ecx, r15d; unsigned __int8
0x1800cc963  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x1800cc968  lea     rdx, [rsp+1A8h+pswzServerName]
0x1800cc970  cmp     qword ptr [rsp+1A8h+var_90+8], 7
0x1800cc979  cmova   rdx, [rsp+1A8h+pswzServerName]; pswzServerName
0x1800cc982  xor     r9d, r9d; dwReserved
0x1800cc985  movzx   r8d, r14w; nServerPort
0x1800cc989  mov     rcx, [rsi+8]; hSession
0x1800cc98d  call    cs:__imp_WinHttpConnect
0x1800cc993  mov     r14, rax
0x1800cc996  mov     r15, [rsi+10h]
0x1800cc99a  test    r15, r15
0x1800cc99d  jz      short loc_1800CC9B8
0x1800cc99f  call    cs:__imp_GetLastError
0x1800cc9a5  mov     ebx, eax
0x1800cc9a7  mov     rcx, r15; hInternet
0x1800cc9aa  call    cs:__imp_WinHttpCloseHandle
0x1800cc9b0  mov     ecx, ebx; dwErrCode
0x1800cc9b2  call    cs:__imp_SetLastError
0x1800cc9b8  mov     [rsi+10h], r14
0x1800cc9bc  test    r14, r14
0x1800cc9bf  jnz     loc_1800CCA55
0x1800cc9c5  mov     rcx, [rsp+1A8h]; this
0x1800cc9cd  lea     r8, aCW1SSrcDeliver_73; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800cc9d4  mov     edx, 254h; void *
0x1800cc9d9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800cc9de  mov     esi, eax
0x1800cc9e0  lea     rcx, [rsp+1A8h+var_80]; void *
0x1800cc9e8  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800cc9ed  nop
0x1800cc9ee  mov     rbx, [rsp+1A8h+Token]
0x1800cc9f3  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800cc9f7  jz      short loc_1800CCA1B
0x1800cc9f9  mov     rdx, rbx; Token
0x1800cc9fc  xor     ecx, ecx; Thread
0x1800cc9fe  call    cs:__imp_SetThreadToken
0x1800cca04  test    eax, eax
0x1800cca06  jz      loc_1800CCB16
0x1800cca0c  test    rbx, rbx
0x1800cca0f  jz      short loc_1800CCA1B
0x1800cca11  mov     rcx, rbx; hObject
0x1800cca14  call    cs:__imp_CloseHandle
0x1800cca1a  nop
0x1800cca1b  lea     rcx, [rsp+1A8h+pswzServerName]
0x1800cca23  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800cca28  nop
0x1800cca29  lea     rcx, [rsp+1A8h+pwszUrl]
0x1800cca31  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800cca36  nop
0x1800cca37  sub     dword ptr [rdi+4Ch], 1
0x1800cca3b  jnz     short loc_1800CCA4E
0x1800cca3d  mov     dword ptr [rdi+48h], 0FFFFFFFFh
0x1800cca44  lea     rcx, [rdi+10h]; SRWLock
0x1800cca48  call    cs:__imp_ReleaseSRWLockExclusive
  ... truncated ...
```
