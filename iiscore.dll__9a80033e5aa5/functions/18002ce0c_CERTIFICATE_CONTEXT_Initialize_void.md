# CERTIFICATE_CONTEXT::Initialize(void)

- ea: `0x18002ce0c`
- end: `0x18002cf13`
- name: `?Initialize@CERTIFICATE_CONTEXT@@SAJXZ`
- size: `263`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180013690`

## callees

- `0x180019558`
- `0x18001ab40`
- `0x18002ce0c`
- `0x1800343f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ce4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ce4c`
- `CRYPTSP!CryptAcquireContextW` at `0x18002ce42`
- `CRYPTSP!CryptAcquireContextW` at `0x18002ce42`
- `CRYPTSP!CryptReleaseContext` at `0x18002ceeb`
- `CRYPTSP!CryptReleaseContext` at `0x18002ceeb`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x18002cea3`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x18002cea3`
- `iisutil!?IsValid@ALLOC_CACHE_HANDLER@@QEBAHXZ` at `0x18002ceb8`
- `iisutil!?IsValid@ALLOC_CACHE_HANDLER@@QEBAHXZ` at `0x18002ceb8`

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
0x18002ce0c  sub     rsp, 58h
0x18002ce10  mov     rax, cs:__security_cookie
0x18002ce17  xor     rax, rsp
0x18002ce1a  mov     [rsp+58h+var_18], rax
0x18002ce1f  xor     eax, eax
0x18002ce21  mov     [rsp+58h+dwFlags], 0F0000000h; dwFlags
0x18002ce29  xor     r8d, r8d; szProvider
0x18002ce2c  mov     [rsp+58h+var_28], rax
0x18002ce31  xor     edx, edx; szContainer
0x18002ce33  mov     [rsp+58h+var_20], eax
0x18002ce37  lea     rcx, ?sm_CryptProvider@CERTIFICATE_CONTEXT@@0_KA; phProv
0x18002ce3e  lea     r9d, [rax+18h]; dwProvType
0x18002ce42  call    cs:__imp_CryptAcquireContextW
0x18002ce48  test    eax, eax
0x18002ce4a  jnz     short loc_18002CE67
0x18002ce4c  call    cs:__imp_GetLastError
0x18002ce52  test    eax, eax
0x18002ce54  jle     loc_18002CF01
0x18002ce5a  movzx   eax, ax
0x18002ce5d  or      eax, 80070000h
0x18002ce62  jmp     loc_18002CF01
0x18002ce67  mov     ecx, 100h; Size
0x18002ce6c  mov     dword ptr [rsp+58h+var_28], 1
0x18002ce74  mov     dword ptr [rsp+58h+var_28+4], 64h ; 'd'
0x18002ce7c  mov     [rsp+58h+var_20], 118h
0x18002ce84  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002ce89  test    rax, rax
0x18002ce8c  jz      short loc_18002CED7
0x18002ce8e  mov     r9d, 1
0x18002ce94  lea     r8, [rsp+58h+var_28]
0x18002ce99  lea     rdx, aCertificateCon; "CERTIFICATE_CONTEXT"
0x18002cea0  mov     rcx, rax
0x18002cea3  call    cs:__imp_??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z; ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(char const *,ALLOC_CACHE_CONFIGURATION const *,int)
0x18002cea9  mov     cs:?sm_pachCertContexts@CERTIFICATE_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA, rax; ALLOC_CACHE_HANDLER * CERTIFICATE_CONTEXT::sm_pachCertContexts
0x18002ceb0  test    rax, rax
0x18002ceb3  jz      short loc_18002CEE2
0x18002ceb5  mov     rcx, rax
0x18002ceb8  call    cs:__imp_?IsValid@ALLOC_CACHE_HANDLER@@QEBAHXZ; ALLOC_CACHE_HANDLER::IsValid(void)
0x18002cebe  test    eax, eax
0x18002cec0  jz      short loc_18002CEC6
0x18002cec2  xor     eax, eax
0x18002cec4  jmp     short loc_18002CF01
0x18002cec6  mov     rcx, cs:?sm_pachCertContexts@CERTIFICATE_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA; this
0x18002cecd  test    rcx, rcx
0x18002ced0  jz      short loc_18002CEE2
0x18002ced2  call    ??_GALLOC_CACHE_HANDLER@@QEAAPEAXI@Z; ALLOC_CACHE_HANDLER::`scalar deleting destructor'(uint)
0x18002ced7  mov     cs:?sm_pachCertContexts@CERTIFICATE_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * CERTIFICATE_CONTEXT::sm_pachCertContexts
0x18002cee2  mov     rcx, cs:?sm_CryptProvider@CERTIFICATE_CONTEXT@@0_KA; hProv
0x18002cee9  xor     edx, edx; dwFlags
0x18002ceeb  call    cs:__imp_CryptReleaseContext
0x18002cef1  mov     eax, 80070008h
0x18002cef6  mov     cs:?sm_CryptProvider@CERTIFICATE_CONTEXT@@0_KA, 0; unsigned __int64 CERTIFICATE_CONTEXT::sm_CryptProvider
0x18002cf01  mov     rcx, [rsp+58h+var_18]
0x18002cf06  xor     rcx, rsp; StackCookie
0x18002cf09  call    __security_check_cookie
0x18002cf0e  add     rsp, 58h
0x18002cf12  retn
```
