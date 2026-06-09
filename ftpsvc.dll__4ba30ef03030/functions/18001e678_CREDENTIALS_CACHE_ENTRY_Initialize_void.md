# CREDENTIALS_CACHE_ENTRY::Initialize(void)

- ea: `0x18001e678`
- end: `0x18001e7db`
- name: `?Initialize@CREDENTIALS_CACHE_ENTRY@@SAJXZ`
- size: `355`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x18001e53c`

## callees

- `0x180001210`
- `0x180001250`
- `0x18001e678`
- `0x180047050`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001e712`
- `KERNEL32!GetLastError` at `0x18001e712`
- `ADVAPI32!CryptAcquireContextW` at `0x18001e708`
- `ADVAPI32!CryptAcquireContextW` at `0x18001e708`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x18001e76c`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x18001e76c`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x18001e6cc`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x18001e6cc`
- `iisutil!PuDbgPrintError` at `0x18001e75b`
- `iisutil!PuDbgPrintError` at `0x18001e7bd`
- `iisutil!PuDbgPrintError` at `0x18001e75b`
- `iisutil!PuDbgPrintError` at `0x18001e7bd`

## string_xrefs

- `0x18001e6c2`: `CREDENTIALS_CACHE_ENTRY`
- `0x18001e78e`: `Error initializing sm_pachCredentialCacheEntry\n`
- `0x18001e740`: `CREDENTIALS_CACHE_ENTRY::Initialize`
- `0x18001e7a2`: `CREDENTIALS_CACHE_ENTRY::Initialize`
- `0x18001e74d`: `inetsrv\iis\iisrearc\ftp\server\core\credentials_cache.cxx`
- `0x18001e7af`: `inetsrv\iis\iisrearc\ftp\server\core\credentials_cache.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 CREDENTIALS_CACHE_ENTRY::Initialize(void)
{
  ALLOC_CACHE_HANDLER *v0; // rax
  ALLOC_CACHE_HANDLER *v1; // rbx
  signed int LastError; // eax
  unsigned int v3; // ebx
  ALLOC_CACHE_HANDLER *v5; // [rsp+30h] [rbp-28h]
  __int64 v6; // [rsp+38h] [rbp-20h] BYREF
  __int64 v7; // [rsp+40h] [rbp-18h]

  v6 = 0x6400000001LL;
  LODWORD(v7) = 408;
  v0 = (ALLOC_CACHE_HANDLER *)operator new(0x100u);
  v5 = v0;
  if ( v0 )
    v1 = ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(
           v0,
           "CREDENTIALS_CACHE_ENTRY",
           (const struct ALLOC_CACHE_CONFIGURATION *)&v6,
           1);
  else
    v1 = 0;
  CREDENTIALS_CACHE_ENTRY::sm_pachCredentialCacheEntry = v1;
  if ( v1 )
  {
    if ( *(_DWORD *)v1 )
    {
      if ( CryptAcquireContextW(&CREDENTIALS_CACHE_ENTRY::sm_hCryptProv, 0, 0, 0x18u, 0xF0000000) )
        return 0;
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\credentials_cache.cxx",
          175,
          "CREDENTIALS_CACHE_ENTRY::Initialize",
          v3,
          "CryptAcquireContext() failed\n",
          v5,
          v6,
          v7);
      return v3;
    }
    ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER(v1);
    operator delete(v1);
    CREDENTIALS_CACHE_ENTRY::sm_pachCredentialCacheEntry = 0;
  }
  if ( (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\credentials_cache.cxx",
      157,
      "CREDENTIALS_CACHE_ENTRY::Initialize",
      -2147024888,
      "Error initializing sm_pachCredentialCacheEntry\n",
      v5,
      v6,
      v7);
  return 2147942408LL;
}

```

## disassembly

```asm
0x18001e678  push    rbx
0x18001e67a  sub     rsp, 50h
0x18001e67e  mov     rax, cs:__security_cookie
0x18001e685  xor     rax, rsp
0x18001e688  mov     [rsp+58h+var_10], rax
0x18001e68d  mov     ebx, 1
0x18001e692  mov     [rsp+58h+var_20], ebx
0x18001e696  mov     [rsp+58h+var_1C], 64h ; 'd'
0x18001e69e  mov     dword ptr [rsp+58h+var_18], 198h
0x18001e6a6  mov     ecx, 100h; Size
0x18001e6ab  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e6b0  mov     [rsp+58h+var_28], rax
0x18001e6b5  test    rax, rax
0x18001e6b8  jz      short loc_18001E6D7
0x18001e6ba  mov     r9d, ebx
0x18001e6bd  lea     r8, [rsp+58h+var_20]
0x18001e6c2  lea     rdx, aCredentialsCac_4; "CREDENTIALS_CACHE_ENTRY"
0x18001e6c9  mov     rcx, rax
0x18001e6cc  call    cs:__imp_??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z; ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(char const *,ALLOC_CACHE_CONFIGURATION const *,int)
0x18001e6d2  mov     rbx, rax
0x18001e6d5  jmp     short loc_18001E6D9
0x18001e6d7  xor     ebx, ebx
0x18001e6d9  mov     cs:?sm_pachCredentialCacheEntry@CREDENTIALS_CACHE_ENTRY@@0PEAVALLOC_CACHE_HANDLER@@EA, rbx; ALLOC_CACHE_HANDLER * CREDENTIALS_CACHE_ENTRY::sm_pachCredentialCacheEntry
0x18001e6e0  test    rbx, rbx
0x18001e6e3  jz      loc_18001E785
0x18001e6e9  cmp     dword ptr [rbx], 0
0x18001e6ec  jz      short loc_18001E769
0x18001e6ee  mov     [rsp+58h+dwFlags], 0F0000000h; dwFlags
0x18001e6f6  mov     r9d, 18h; dwProvType
0x18001e6fc  xor     r8d, r8d; szProvider
0x18001e6ff  xor     edx, edx; szContainer
0x18001e701  lea     rcx, ?sm_hCryptProv@CREDENTIALS_CACHE_ENTRY@@0_KA; phProv
0x18001e708  call    cs:__imp_CryptAcquireContextW
0x18001e70e  test    eax, eax
0x18001e710  jnz     short loc_18001E765
0x18001e712  call    cs:__imp_GetLastError
0x18001e718  mov     ebx, eax
0x18001e71a  test    eax, eax
0x18001e71c  jle     short loc_18001E727
0x18001e71e  movzx   ebx, ax
0x18001e721  or      ebx, 80070000h
0x18001e727  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001e72e  jz      short loc_18001E761
0x18001e730  lea     rax, aCryptacquireco; "CryptAcquireContext() failed\n"
0x18001e737  mov     [rsp+58h+var_30], rax
0x18001e73c  mov     [rsp+58h+dwFlags], ebx
0x18001e740  lea     r9, aCredentialsCac_6; "CREDENTIALS_CACHE_ENTRY::Initialize"
0x18001e747  mov     r8d, 0AFh
0x18001e74d  lea     rdx, aInetsrvIisIisr_21; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18001e754  mov     rcx, cs:g_pDebug
0x18001e75b  call    cs:__imp_PuDbgPrintError
0x18001e761  mov     eax, ebx
0x18001e763  jmp     short loc_18001E7C8
0x18001e765  xor     eax, eax
0x18001e767  jmp     short loc_18001E7C8
0x18001e769  mov     rcx, rbx
0x18001e76c  call    cs:__imp_??1ALLOC_CACHE_HANDLER@@QEAA@XZ; ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER(void)
0x18001e772  mov     rcx, rbx; Block
0x18001e775  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001e77a  mov     cs:?sm_pachCredentialCacheEntry@CREDENTIALS_CACHE_ENTRY@@0PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * CREDENTIALS_CACHE_ENTRY::sm_pachCredentialCacheEntry
0x18001e785  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001e78c  jz      short loc_18001E7C3
0x18001e78e  lea     rax, aErrorInitializ_0; "Error initializing sm_pachCredentialCac"...
0x18001e795  mov     [rsp+58h+var_30], rax
0x18001e79a  mov     [rsp+58h+dwFlags], 80070008h
0x18001e7a2  lea     r9, aCredentialsCac_6; "CREDENTIALS_CACHE_ENTRY::Initialize"
0x18001e7a9  mov     r8d, 9Dh
0x18001e7af  lea     rdx, aInetsrvIisIisr_21; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18001e7b6  mov     rcx, cs:g_pDebug
0x18001e7bd  call    cs:__imp_PuDbgPrintError
0x18001e7c3  mov     eax, 80070008h
0x18001e7c8  mov     rcx, [rsp+58h+var_10]
0x18001e7cd  xor     rcx, rsp; StackCookie
0x18001e7d0  call    __security_check_cookie
0x18001e7d5  add     rsp, 50h
0x18001e7d9  pop     rbx
0x18001e7da  retn
```
