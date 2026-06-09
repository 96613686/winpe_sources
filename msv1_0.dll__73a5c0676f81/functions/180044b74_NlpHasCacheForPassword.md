# NlpHasCacheForPassword

- ea: `0x180044b74`
- end: `0x180044da9`
- name: `NlpHasCacheForPassword`
- size: `565`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180033148`

## callees

- `0x1800186d4`
- `0x18002ee7c`
- `0x18002fb50`
- `0x180030844`
- `0x1800415d8`
- `0x180042dac`
- `0x180044b74`
- `0x18006bd74`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044d49`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044d49`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180044c7a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180044c7a`
- `ntdll!RtlReleaseResource` at `0x180044cf7`
- `ntdll!RtlReleaseResource` at `0x180044cf7`
- `ntdll!RtlAcquireResourceShared` at `0x180044bf4`
- `ntdll!RtlAcquireResourceShared` at `0x180044bf4`

## pseudocode

```c
__int64 __fastcall NlpHasCacheForPassword(
        struct _UNICODE_STRING *a1,
        struct _UNICODE_STRING *a2,
        __int64 a3,
        _BYTE *a4)
{
  struct _LOGON_CACHE_ENTRY *v8; // rbx
  unsigned int v9; // esi
  struct _LOGON_CACHE_ENTRY *v11; // rdi
  int CacheEntry; // r14d
  struct _LOGON_CACHE_ENTRY *v13; // rax
  __int64 v14; // rcx
  _BYTE *v15; // rax
  SIZE_T uBytes; // [rsp+30h] [rbp-D0h] BYREF
  void *Src; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v18[4]; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v19; // [rsp+50h] [rbp-B0h]
  _BYTE v20[30]; // [rsp+52h] [rbp-AEh] BYREF
  _QWORD v21[44]; // [rsp+70h] [rbp-90h] BYREF

  v19 = 0;
  memset_0(v20, 0, 0x17Eu);
  v8 = 0;
  v9 = 0;
  Src = 0;
  v18[0] = 0;
  LODWORD(uBytes) = 0;
  if ( !NlpCacheInitialized )
    return 3221225581LL;
  v11 = 0;
  RtlAcquireResourceShared(&NlpLogonCacheCritSec, 1u);
  if ( a1 && a2 && a3 && a4 )
  {
    CacheEntry = NlpPutOwfsInPrimaryCredential(a3, 0, 0, 0, (__int64)v21);
    if ( CacheEntry >= 0 )
    {
      CacheEntry = NlpReadCacheEntry(a1, a2, 0, v18, (struct _LOGON_CACHE_ENTRY **)&Src, (unsigned int *)&uBytes);
      if ( CacheEntry < 0 )
      {
        v8 = (struct _LOGON_CACHE_ENTRY *)Src;
        v9 = uBytes;
      }
      else
      {
        v9 = uBytes;
        v13 = (struct _LOGON_CACHE_ENTRY *)LocalAlloc(0x40u, (unsigned int)uBytes);
        v8 = (struct _LOGON_CACHE_ENTRY *)Src;
        v11 = v13;
        if ( v13 )
        {
          memcpy_0(v13, Src, v9);
          CacheEntry = (*(__int64 (__fastcall **)(_QWORD, struct _UNICODE_STRING *, _QWORD *, _QWORD, __int64))(*(_QWORD *)v21[0] + 80LL))(
                         v21[0],
                         a2,
                         v21,
                         *((unsigned __int16 *)v8 + 25),
                         (__int64)v11 + 96);
          if ( CacheEntry >= 0 )
            *a4 = NlpCompareCacheEntry(v8, v9, v11, v9);
        }
      }
    }
  }
  else
  {
    CacheEntry = -1073741811;
  }
  RtlReleaseResource(&NlpLogonCacheCritSec);
  v14 = 352;
  v15 = v21;
  do
  {
    *v15++ = 0;
    --v14;
  }
  while ( v14 );
  if ( v8 )
  {
    memset_0(v8, 0, v9);
    ((void (__fastcall *)(struct _LOGON_CACHE_ENTRY *))qword_180088398)(v8);
  }
  if ( v11 )
  {
    memset_0(v11, 0, v9);
    LocalFree(v11);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      63,
      WPP_905305d962583d6f838b30057de84013_Traceguids,
      (unsigned int)CacheEntry);
  return (unsigned int)CacheEntry;
}

```

## disassembly

```asm
0x180044b74  push    rbp
0x180044b76  push    rbx
0x180044b77  push    rsi
0x180044b78  push    rdi
0x180044b79  push    r12
0x180044b7b  push    r13
0x180044b7d  push    r14
0x180044b7f  push    r15
0x180044b81  lea     rbp, [rsp-0E8h]
0x180044b89  sub     rsp, 1E8h
0x180044b90  mov     rax, cs:__security_cookie
0x180044b97  xor     rax, rsp
0x180044b9a  mov     [rbp+120h+var_50], rax
0x180044ba1  mov     r14, r8
0x180044ba4  mov     r15, rdx
0x180044ba7  mov     r12, rcx
0x180044baa  xor     eax, eax
0x180044bac  xor     edx, edx; Val
0x180044bae  mov     [rsp+220h+var_1D0], ax
0x180044bb3  mov     r8d, 17Eh; Size
0x180044bb9  lea     rcx, [rsp+220h+var_1CE]; void *
0x180044bbe  mov     r13, r9
0x180044bc1  call    memset_0
0x180044bc6  xor     ebx, ebx
0x180044bc8  xor     esi, esi
0x180044bca  cmp     cs:NlpCacheInitialized, bl
0x180044bd0  mov     [rsp+220h+Src], rbx
0x180044bd5  mov     [rsp+220h+var_1E0], ebx
0x180044bd9  mov     dword ptr [rsp+220h+uBytes], esi
0x180044bdd  jnz     short loc_180044BE9
0x180044bdf  mov     eax, 0C000006Dh
0x180044be4  jmp     loc_180044D86
0x180044be9  mov     dl, 1; Wait
0x180044beb  lea     rcx, NlpLogonCacheCritSec; Resource
0x180044bf2  xor     edi, edi
0x180044bf4  call    cs:__imp_RtlAcquireResourceShared
0x180044bfa  test    r12, r12
0x180044bfd  jz      loc_180044CEA
0x180044c03  test    r15, r15
0x180044c06  jz      loc_180044CEA
0x180044c0c  test    r14, r14
0x180044c0f  jz      loc_180044CEA
0x180044c15  test    r13, r13
0x180044c18  jz      loc_180044CEA
0x180044c1e  lea     rax, [rsp+220h+var_1B0]
0x180044c23  xor     r9d, r9d
0x180044c26  xor     r8d, r8d
0x180044c29  mov     [rsp+220h+var_200], rax
0x180044c2e  xor     edx, edx
0x180044c30  mov     rcx, r14
0x180044c33  call    NlpPutOwfsInPrimaryCredential
0x180044c38  mov     r14d, eax
0x180044c3b  test    eax, eax
0x180044c3d  js      loc_180044CF0
0x180044c43  lea     rax, [rsp+220h+uBytes]
0x180044c48  xor     r8d, r8d; unsigned int
0x180044c4b  mov     [rsp+220h+var_1F8], rax; unsigned int *
0x180044c50  lea     r9, [rsp+220h+var_1E0]; unsigned int *
0x180044c55  lea     rax, [rsp+220h+Src]
0x180044c5a  mov     rdx, r15; struct _UNICODE_STRING *
0x180044c5d  mov     rcx, r12; struct _UNICODE_STRING *
0x180044c60  mov     [rsp+220h+var_200], rax; struct _LOGON_CACHE_ENTRY **
0x180044c65  call    ?NlpReadCacheEntry@@YAJPEAU_UNICODE_STRING@@0KPEAKPEAPEAU_LOGON_CACHE_ENTRY@@1@Z; NlpReadCacheEntry(_UNICODE_STRING *,_UNICODE_STRING *,ulong,ulong *,_LOGON_CACHE_ENTRY * *,ulong *)
0x180044c6a  mov     r14d, eax
0x180044c6d  test    eax, eax
0x180044c6f  js      short loc_180044CDF
0x180044c71  mov     esi, dword ptr [rsp+220h+uBytes]
0x180044c75  lea     ecx, [rdi+40h]; uFlags
0x180044c78  mov     edx, esi; uBytes
0x180044c7a  call    cs:__imp_LocalAlloc
0x180044c80  mov     rbx, [rsp+220h+Src]
0x180044c85  mov     rdi, rax
0x180044c88  test    rax, rax
0x180044c8b  jz      short loc_180044CF0
0x180044c8d  mov     r8d, esi; Size
0x180044c90  mov     rdx, rbx; Src
0x180044c93  mov     rcx, rax; void *
0x180044c96  call    memcpy_0
0x180044c9b  mov     rcx, [rsp+220h+var_1B0]
0x180044ca0  lea     r10, [rdi+60h]
0x180044ca4  movzx   r9d, word ptr [rbx+32h]
0x180044ca9  mov     rdx, r15
0x180044cac  mov     [rsp+220h+var_200], r10
0x180044cb1  mov     r8, [rcx]
0x180044cb4  mov     rax, [r8+50h]
0x180044cb8  lea     r8, [rsp+220h+var_1B0]
0x180044cbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044cc2  mov     r14d, eax
0x180044cc5  test    eax, eax
0x180044cc7  js      short loc_180044CF0
0x180044cc9  mov     r9d, esi; unsigned int
0x180044ccc  mov     r8, rdi; struct _LOGON_CACHE_ENTRY *
0x180044ccf  mov     edx, esi; unsigned int
0x180044cd1  mov     rcx, rbx; struct _LOGON_CACHE_ENTRY *
0x180044cd4  call    ?NlpCompareCacheEntry@@YAEPEAU_LOGON_CACHE_ENTRY@@K0K@Z; NlpCompareCacheEntry(_LOGON_CACHE_ENTRY *,ulong,_LOGON_CACHE_ENTRY *,ulong)
0x180044cd9  mov     [r13+0], al
0x180044cdd  jmp     short loc_180044CF0
0x180044cdf  mov     rbx, [rsp+220h+Src]
0x180044ce4  mov     esi, dword ptr [rsp+220h+uBytes]
0x180044ce8  jmp     short loc_180044CF0
0x180044cea  mov     r14d, 0C000000Dh
0x180044cf0  lea     rcx, NlpLogonCacheCritSec; Resource
0x180044cf7  call    cs:__imp_RtlReleaseResource
0x180044cfd  mov     ecx, 160h
0x180044d02  lea     rax, [rsp+220h+var_1B0]
0x180044d07  mov     byte ptr [rax], 0
0x180044d0a  inc     rax
0x180044d0d  sub     rcx, 1
0x180044d11  jnz     short loc_180044D07
0x180044d13  test    rbx, rbx
0x180044d16  jz      short loc_180044D34
0x180044d18  mov     r8d, esi; Size
0x180044d1b  xor     edx, edx; Val
0x180044d1d  mov     rcx, rbx; void *
0x180044d20  call    memset_0
0x180044d25  mov     rax, cs:qword_180088398
0x180044d2c  mov     rcx, rbx
0x180044d2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044d34  test    rdi, rdi
0x180044d37  jz      short loc_180044D4F
0x180044d39  mov     r8d, esi; Size
0x180044d3c  xor     edx, edx; Val
0x180044d3e  mov     rcx, rdi; void *
0x180044d41  call    memset_0
0x180044d46  mov     rcx, rdi; hMem
0x180044d49  call    cs:__imp_LocalFree
0x180044d4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180044d56  lea     rax, WPP_GLOBAL_Control
0x180044d5d  cmp     rcx, rax
0x180044d60  jz      short loc_180044D83
0x180044d62  test    dword ptr [rcx+1Ch], 1000h
0x180044d69  jz      short loc_180044D83
0x180044d6b  mov     rcx, [rcx+10h]
0x180044d6f  lea     r8, WPP_905305d962583d6f838b30057de84013_Traceguids
0x180044d76  mov     edx, 3Fh ; '?'
0x180044d7b  mov     r9d, r14d
0x180044d7e  call    WPP_SF_d
0x180044d83  mov     eax, r14d
0x180044d86  mov     rcx, [rbp+120h+var_50]
0x180044d8d  xor     rcx, rsp; StackCookie
0x180044d90  call    __security_check_cookie
0x180044d95  add     rsp, 1E8h
0x180044d9c  pop     r15
0x180044d9e  pop     r14
0x180044da0  pop     r13
0x180044da2  pop     r12
0x180044da4  pop     rdi
0x180044da5  pop     rsi
0x180044da6  pop     rbx
0x180044da7  pop     rbp
0x180044da8  retn
```
