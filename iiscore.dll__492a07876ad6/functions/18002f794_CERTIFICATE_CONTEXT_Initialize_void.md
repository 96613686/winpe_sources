# CERTIFICATE_CONTEXT::Initialize(void)

- ea: `0x18002f794`
- end: `0x18002f8ba`
- name: `?Initialize@CERTIFICATE_CONTEXT@@SAJXZ`
- size: `294`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1800147d0`

## callees

- `0x18001ab30`
- `0x18001c238`
- `0x18002f794`
- `0x180037790`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f7da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f7da`
- `CRYPTSP!CryptAcquireContextW` at `0x18002f7ca`
- `CRYPTSP!CryptAcquireContextW` at `0x18002f7ca`
- `CRYPTSP!CryptReleaseContext` at `0x18002f88b`
- `CRYPTSP!CryptReleaseContext` at `0x18002f88b`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x18002f837`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x18002f837`
- `iisutil!?IsValid@ALLOC_CACHE_HANDLER@@QEBAHXZ` at `0x18002f852`
- `iisutil!?IsValid@ALLOC_CACHE_HANDLER@@QEBAHXZ` at `0x18002f852`

## pseudocode

```c
signed int CERTIFICATE_CONTEXT::Initialize(void)
{
  signed int result; // eax
  ALLOC_CACHE_HANDLER *v1; // rax
  ALLOC_CACHE_HANDLER *v2; // rax
  unsigned int v3; // edx
  __int64 v4; // [rsp+30h] [rbp-28h] BYREF
  int v5; // [rsp+38h] [rbp-20h]

  v4 = 0;
  v5 = 0;
  if ( CryptAcquireContextW(&CERTIFICATE_CONTEXT::sm_CryptProvider, 0, 0, 0x18u, 0xF0000000) )
  {
    v4 = 0x6400000001LL;
    v5 = 280;
    v1 = (ALLOC_CACHE_HANDLER *)operator new(0x100u);
    if ( v1 )
    {
      v2 = ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(
             v1,
             "CERTIFICATE_CONTEXT",
             (const struct ALLOC_CACHE_CONFIGURATION *)&v4,
             1);
      CERTIFICATE_CONTEXT::sm_pachCertContexts = v2;
      if ( !v2 )
        goto LABEL_11;
      if ( ALLOC_CACHE_HANDLER::IsValid(v2) )
        return 0;
      if ( !CERTIFICATE_CONTEXT::sm_pachCertContexts )
        goto LABEL_11;
      ALLOC_CACHE_HANDLER::`scalar deleting destructor'(CERTIFICATE_CONTEXT::sm_pachCertContexts, v3);
    }
    CERTIFICATE_CONTEXT::sm_pachCertContexts = 0;
LABEL_11:
    CryptReleaseContext(CERTIFICATE_CONTEXT::sm_CryptProvider, 0);
    result = -2147024888;
    CERTIFICATE_CONTEXT::sm_CryptProvider = 0;
    return result;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18002f794  sub     rsp, 58h
0x18002f798  mov     rax, cs:__security_cookie
0x18002f79f  xor     rax, rsp
0x18002f7a2  mov     [rsp+58h+var_18], rax
0x18002f7a7  xor     eax, eax
0x18002f7a9  mov     [rsp+58h+dwFlags], 0F0000000h; dwFlags
0x18002f7b1  xor     r8d, r8d; szProvider
0x18002f7b4  mov     [rsp+58h+var_28], rax
0x18002f7b9  xor     edx, edx; szContainer
0x18002f7bb  mov     [rsp+58h+var_20], eax
0x18002f7bf  lea     rcx, ?sm_CryptProvider@CERTIFICATE_CONTEXT@@0_KA; phProv
0x18002f7c6  lea     r9d, [rax+18h]; dwProvType
0x18002f7ca  call    cs:__imp_CryptAcquireContextW
0x18002f7d1  nop     dword ptr [rax+rax+00h]
0x18002f7d6  test    eax, eax
0x18002f7d8  jnz     short loc_18002F7FB
0x18002f7da  call    cs:__imp_GetLastError
0x18002f7e1  nop     dword ptr [rax+rax+00h]
0x18002f7e6  test    eax, eax
0x18002f7e8  jle     loc_18002F8A7
0x18002f7ee  movzx   eax, ax
0x18002f7f1  or      eax, 80070000h
0x18002f7f6  jmp     loc_18002F8A7
0x18002f7fb  mov     ecx, 100h; Size
0x18002f800  mov     dword ptr [rsp+58h+var_28], 1
0x18002f808  mov     dword ptr [rsp+58h+var_28+4], 64h ; 'd'
0x18002f810  mov     [rsp+58h+var_20], 118h
0x18002f818  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002f81d  test    rax, rax
0x18002f820  jz      short loc_18002F877
0x18002f822  mov     r9d, 1
0x18002f828  lea     r8, [rsp+58h+var_28]
0x18002f82d  lea     rdx, aCertificateCon; "CERTIFICATE_CONTEXT"
0x18002f834  mov     rcx, rax
0x18002f837  call    cs:__imp_??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z; ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(char const *,ALLOC_CACHE_CONFIGURATION const *,int)
0x18002f83e  nop     dword ptr [rax+rax+00h]
0x18002f843  mov     cs:?sm_pachCertContexts@CERTIFICATE_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA, rax; ALLOC_CACHE_HANDLER * CERTIFICATE_CONTEXT::sm_pachCertContexts
0x18002f84a  test    rax, rax
0x18002f84d  jz      short loc_18002F882
0x18002f84f  mov     rcx, rax
0x18002f852  call    cs:__imp_?IsValid@ALLOC_CACHE_HANDLER@@QEBAHXZ; ALLOC_CACHE_HANDLER::IsValid(void)
0x18002f859  nop     dword ptr [rax+rax+00h]
0x18002f85e  test    eax, eax
0x18002f860  jz      short loc_18002F866
0x18002f862  xor     eax, eax
0x18002f864  jmp     short loc_18002F8A7
0x18002f866  mov     rcx, cs:?sm_pachCertContexts@CERTIFICATE_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA; this
0x18002f86d  test    rcx, rcx
0x18002f870  jz      short loc_18002F882
0x18002f872  call    ??_GALLOC_CACHE_HANDLER@@QEAAPEAXI@Z; ALLOC_CACHE_HANDLER::`scalar deleting destructor'(uint)
0x18002f877  mov     cs:?sm_pachCertContexts@CERTIFICATE_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * CERTIFICATE_CONTEXT::sm_pachCertContexts
0x18002f882  mov     rcx, cs:?sm_CryptProvider@CERTIFICATE_CONTEXT@@0_KA; hProv
0x18002f889  xor     edx, edx; dwFlags
0x18002f88b  call    cs:__imp_CryptReleaseContext
0x18002f892  nop     dword ptr [rax+rax+00h]
0x18002f897  mov     eax, 80070008h
0x18002f89c  mov     cs:?sm_CryptProvider@CERTIFICATE_CONTEXT@@0_KA, 0; unsigned __int64 CERTIFICATE_CONTEXT::sm_CryptProvider
0x18002f8a7  mov     rcx, [rsp+58h+var_18]
0x18002f8ac  xor     rcx, rsp; StackCookie
0x18002f8af  call    __security_check_cookie
0x18002f8b4  add     rsp, 58h
0x18002f8b8  retn
```
