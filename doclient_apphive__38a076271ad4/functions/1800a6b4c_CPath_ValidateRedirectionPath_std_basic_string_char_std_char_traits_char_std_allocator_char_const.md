# CPath::ValidateRedirectionPath(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x1800a6b4c`
- end: `0x1800a6d72`
- name: `?ValidateRedirectionPath@CPath@@SAJAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `550`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `reparse_path`

## callers

- `0x18009adfc`
- `0x1800e8100`

## callees

- `0x180008a54`
- `0x18000933c`
- `0x18000ecf0`
- `0x18000ef98`
- `0x1800a6b4c`
- `0x1800a7618`
- `0x1800a979c`
- `0x1800f82f0`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x1800a6c73`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x1800a6c73`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800a6bbf`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800a6bbf`
- `api-ms-win-core-path-l1-1-0!PathCchStripPrefix` at `0x1800a6c12`
- `api-ms-win-core-path-l1-1-0!PathCchStripPrefix` at `0x1800a6c12`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1800a6d08`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1800a6d08`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall CPath::ValidateRedirectionPath(_QWORD *a1)
{
  __int64 v1; // r8
  const WCHAR *v3; // rcx
  DWORD v4; // ebx
  unsigned int v5; // edi
  HRESULT v6; // eax
  unsigned int v7; // ebx
  unsigned __int64 v8; // rbx
  __int64 v9; // r8
  __int64 first_of; // rax
  const WCHAR *v11; // rcx
  wil::details *v12; // rcx
  unsigned int LastErrorFailHr; // ebx
  int v14; // [rsp+20h] [rbp-278h]
  LPCWSTR lpSrc[4]; // [rsp+28h] [rbp-270h] BYREF
  LPCWSTR lpszFileName[2]; // [rsp+48h] [rbp-250h] BYREF
  __int128 v17; // [rsp+58h] [rbp-240h]
  WCHAR Dst[264]; // [rsp+70h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+0h]

  v1 = a1[2];
  if ( !v1 )
    return 2147942487LL;
  if ( a1[3] > 0xFu )
    a1 = (_QWORD *)*a1;
  UTF8toWstr(lpSrc, a1, v1);
  v3 = (const WCHAR *)lpSrc;
  if ( lpSrc[3] > (LPCWSTR)7 )
    v3 = lpSrc[0];
  v4 = ExpandEnvironmentStringsW(v3, Dst, 0x104u) - 1;
  v5 = v4 > 0x103 ? 0x8007007A : 0;
  std::wstring::~wstring(lpSrc);
  if ( v4 <= 0x103 )
  {
    v6 = PathCchStripPrefix(Dst, 0x104u);
    v7 = v6;
    if ( v6 >= 0 )
    {
      v8 = -1;
      do
        ++v8;
      while ( Dst[v8] );
      if ( v8 < 2 || v8 > 0x96 )
      {
        return 2147942487LL;
      }
      else if ( PathGetDriveNumberW(Dst) == -1 )
      {
        return 2147942487LL;
      }
      else if ( v8 < 3 || Dst[2] == 92 )
      {
        *(_OWORD *)lpszFileName = 0;
        v17 = 0;
        v9 = -1;
        do
          ++v9;
        while ( Dst[v9] );
        std::wstring::_Construct<1,wchar_t const *>(lpszFileName);
        first_of = std::wstring::find_first_of(lpszFileName);
        v11 = (const WCHAR *)lpszFileName;
        if ( first_of == -1 )
        {
          if ( *((_QWORD *)&v17 + 1) > 7u )
            v11 = lpszFileName[0];
          if ( GetVolumePathNameW(v11, Dst, 0x104u) )
          {
            std::wstring::~wstring(lpszFileName);
            return 0;
          }
          else
          {
            LastErrorFailHr = wil::details::GetLastErrorFailHr(v12);
            std::wstring::~wstring(lpszFileName);
            return LastErrorFailHr;
          }
        }
        else
        {
          std::wstring::~wstring(lpszFileName);
          return 2147942487LL;
        }
      }
      else
      {
        return 2147942487LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x27D,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\FileSystem.cpp",
        (const char *)(unsigned int)v6,
        v14);
      return v7;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x27C,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\FileSystem.cpp",
      (const char *)v5,
      v14);
    return v5;
  }
}

```

## disassembly

```asm
0x1800a6b4c  mov     [rsp+arg_8], rbx
0x1800a6b51  mov     [rsp+arg_10], rsi
0x1800a6b56  mov     [rsp+arg_18], rdi
0x1800a6b5b  push    r14
0x1800a6b5d  sub     rsp, 290h
0x1800a6b64  mov     rax, cs:__security_cookie
0x1800a6b6b  xor     rax, rsp
0x1800a6b6e  mov     [rsp+298h+var_18], rax
0x1800a6b76  xor     r14d, r14d
0x1800a6b79  mov     r8, [rcx+10h]
0x1800a6b7d  test    r8, r8
0x1800a6b80  jnz     short loc_1800A6B8C
0x1800a6b82  mov     eax, 80070057h
0x1800a6b87  jmp     loc_1800A6D47
0x1800a6b8c  cmp     qword ptr [rcx+18h], 0Fh
0x1800a6b91  jbe     short loc_1800A6B96
0x1800a6b93  mov     rcx, [rcx]
0x1800a6b96  mov     rdx, rcx
0x1800a6b99  lea     rcx, [rsp+298h+lpSrc]
0x1800a6b9e  call    ?UTF8toWstr@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBD_K@Z; UTF8toWstr(char const *,unsigned __int64)
0x1800a6ba3  lea     rcx, [rsp+298h+lpSrc]
0x1800a6ba8  cmp     [rsp+298h+var_258], 7
0x1800a6bae  cmova   rcx, [rsp+298h+lpSrc]; lpSrc
0x1800a6bb4  mov     r8d, 104h; nSize
0x1800a6bba  lea     rdx, [rsp+298h+Dst]; lpDst
0x1800a6bbf  call    cs:__imp_ExpandEnvironmentStringsW
0x1800a6bc5  lea     ebx, [rax-1]
0x1800a6bc8  mov     esi, 103h
0x1800a6bcd  cmp     esi, ebx
0x1800a6bcf  sbb     edi, edi
0x1800a6bd1  and     edi, 8007007Ah
0x1800a6bd7  lea     rcx, [rsp+298h+lpSrc]
0x1800a6bdc  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a6be1  cmp     ebx, esi
0x1800a6be3  jbe     short loc_1800A6C08
0x1800a6be5  mov     rcx, [rsp+298h]; this
0x1800a6bed  mov     r9d, edi; char *
0x1800a6bf0  lea     r8, aCW1SSrcDeliver_85; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800a6bf7  mov     edx, 27Ch; void *
0x1800a6bfc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6c01  mov     eax, edi
0x1800a6c03  jmp     loc_1800A6D47
0x1800a6c08  mov     edx, 104h; cchPath
0x1800a6c0d  lea     rcx, [rsp+298h+Dst]; pszPath
0x1800a6c12  call    cs:__imp_PathCchStripPrefix
0x1800a6c18  mov     ebx, eax
0x1800a6c1a  test    eax, eax
0x1800a6c1c  jns     short loc_1800A6C41
0x1800a6c1e  mov     rcx, [rsp+298h]; this
0x1800a6c26  mov     r9d, eax; char *
0x1800a6c29  lea     r8, aCW1SSrcDeliver_85; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800a6c30  mov     edx, 27Dh; void *
0x1800a6c35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6c3a  mov     eax, ebx
0x1800a6c3c  jmp     loc_1800A6D47
0x1800a6c41  lea     rax, [rsp+298h+Dst]
0x1800a6c46  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800a6c4a  mov     rbx, rdi
0x1800a6c4d  inc     rbx
0x1800a6c50  cmp     [rax+rbx*2], r14w
0x1800a6c55  jnz     short loc_1800A6C4D
0x1800a6c57  cmp     rbx, 2
0x1800a6c5b  jb      loc_1800A6D35
0x1800a6c61  cmp     rbx, 96h
0x1800a6c68  ja      loc_1800A6D35
0x1800a6c6e  lea     rcx, [rsp+298h+Dst]; pszPath
0x1800a6c73  call    cs:__imp_PathGetDriveNumberW
0x1800a6c79  cmp     eax, edi
0x1800a6c7b  jnz     short loc_1800A6C87
0x1800a6c7d  mov     eax, 80070057h
0x1800a6c82  jmp     loc_1800A6D47
0x1800a6c87  cmp     rbx, 3
0x1800a6c8b  jb      short loc_1800A6C9F
0x1800a6c8d  cmp     [rsp+298h+var_224], 5Ch ; '\'
0x1800a6c93  jz      short loc_1800A6C9F
0x1800a6c95  mov     eax, 80070057h
0x1800a6c9a  jmp     loc_1800A6D47
0x1800a6c9f  xorps   xmm0, xmm0
0x1800a6ca2  movups  xmmword ptr [rsp+298h+lpszFileName], xmm0
0x1800a6ca7  xorps   xmm1, xmm1
0x1800a6caa  movdqu  [rsp+298h+var_240], xmm1
0x1800a6cb0  lea     rax, [rsp+298h+Dst]
0x1800a6cb5  mov     r8, rdi
0x1800a6cb8  inc     r8
0x1800a6cbb  cmp     [rax+r8*2], r14w
0x1800a6cc0  jnz     short loc_1800A6CB8
0x1800a6cc2  lea     rdx, [rsp+298h+Dst]
0x1800a6cc7  lea     rcx, [rsp+298h+lpszFileName]
0x1800a6ccc  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800a6cd1  lea     rcx, [rsp+298h+lpszFileName]; Src
0x1800a6cd6  call    ?find_first_of@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA_KQEB_W_K@Z; std::wstring::find_first_of(wchar_t const * const,unsigned __int64)
0x1800a6cdb  lea     rcx, [rsp+298h+lpszFileName]
0x1800a6ce0  cmp     rax, rdi
0x1800a6ce3  jz      short loc_1800A6CF1
0x1800a6ce5  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a6cea  mov     eax, 80070057h
0x1800a6cef  jmp     short loc_1800A6D47
0x1800a6cf1  cmp     qword ptr [rsp+298h+var_240+8], 7
0x1800a6cf7  cmova   rcx, [rsp+298h+lpszFileName]; lpszFileName
0x1800a6cfd  mov     r8d, 104h; cchBufferLength
0x1800a6d03  lea     rdx, [rsp+298h+Dst]; lpszVolumePathName
0x1800a6d08  call    cs:__imp_GetVolumePathNameW
0x1800a6d0e  test    eax, eax
0x1800a6d10  jnz     short loc_1800A6D27
0x1800a6d12  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800a6d17  mov     ebx, eax
0x1800a6d19  lea     rcx, [rsp+298h+lpszFileName]
0x1800a6d1e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a6d23  mov     eax, ebx
0x1800a6d25  jmp     short loc_1800A6D47
0x1800a6d27  lea     rcx, [rsp+298h+lpszFileName]
0x1800a6d2c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a6d31  xor     eax, eax
0x1800a6d33  jmp     short loc_1800A6D47
0x1800a6d35  mov     eax, 80070057h
0x1800a6d3a  jmp     short loc_1800A6D47
0x1800a6d3c  mov     eax, 8007000Eh
0x1800a6d41  jmp     short loc_1800A6D47
0x1800a6d43  mov     eax, [rsp+298h+var_278]
0x1800a6d47  mov     rcx, [rsp+298h+var_18]
0x1800a6d4f  xor     rcx, rsp; StackCookie
0x1800a6d52  call    __security_check_cookie
0x1800a6d57  lea     r11, [rsp+298h+var_8]
0x1800a6d5f  mov     rbx, [r11+18h]
0x1800a6d63  mov     rsi, [r11+20h]
0x1800a6d67  mov     rdi, [r11+28h]
0x1800a6d6b  mov     rsp, r11
0x1800a6d6e  pop     r14
0x1800a6d70  retn
```
