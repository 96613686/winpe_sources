# NlpGetCacheEntry

- ea: `0x1800448cc`
- end: `0x180044b6d`
- name: `NlpGetCacheEntry`
- size: `673`
- prototype: `__int64 __usercall@<rax>(struct _UNICODE_STRING *@<rcx>, unsigned int@<edx>, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18001a470`
- `0x18003d6a0`

## callees

- `0x180030844`
- `0x180042378`
- `0x180042dac`
- `0x180043968`
- `0x1800448cc`
- `0x18004542c`
- `0x18006bd74`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044b1f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044b45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044b1f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044b45`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800449fc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800449fc`
- `ntdll!RtlReleaseResource` at `0x1800449c7`
- `ntdll!RtlReleaseResource` at `0x1800449db`
- `ntdll!RtlReleaseResource` at `0x1800449c7`
- `ntdll!RtlReleaseResource` at `0x1800449db`
- `ntdll!RtlAcquireResourceShared` at `0x18004497e`
- `ntdll!RtlAcquireResourceShared` at `0x18004497e`

## pseudocode

```c
__int64 __fastcall NlpGetCacheEntry(
        struct _UNICODE_STRING *a1,
        unsigned int a2,
        struct _UNICODE_STRING *a3,
        struct _UNICODE_STRING *a4,
        struct _NETLOGON_VALIDATION_SAM_INFO4 **a5,
        __int64 a6,
        _DWORD *a7,
        void **a8,
        _DWORD *a9)
{
  __int64 v9; // r13
  void **v10; // r15
  struct _NETLOGON_VALIDATION_SAM_INFO4 *v13; // rdi
  _DWORD *v14; // rsi
  int v16; // ebx
  struct _LOGON_CACHE_ENTRY *v17; // rbx
  SIZE_T v18; // rdx
  HLOCAL v19; // rax
  int CredentialNamesFromCacheEntry; // r14d
  int v21; // eax
  int v22; // eax
  _DWORD *v23; // rcx
  __int128 v24; // xmm1
  unsigned int v25; // [rsp+50h] [rbp-20h] BYREF
  struct _NETLOGON_VALIDATION_SAM_INFO4 *v26; // [rsp+58h] [rbp-18h] BYREF
  struct _LOGON_CACHE_ENTRY *v27; // [rsp+60h] [rbp-10h] BYREF
  size_t Size; // [rsp+B0h] [rbp+40h] BYREF
  struct _UNICODE_STRING *v29; // [rsp+C0h] [rbp+50h]
  struct _UNICODE_STRING *v30; // [rsp+C8h] [rbp+58h]

  v30 = a4;
  v29 = a3;
  v9 = a6;
  v10 = a8;
  v26 = 0;
  v13 = 0;
  v27 = 0;
  *a5 = 0;
  LODWORD(Size) = 0;
  v25 = 0;
  *(_OWORD *)v9 = 0;
  *(_OWORD *)(v9 + 16) = 0;
  *(_DWORD *)(v9 + 31) = 0;
  *a7 = 0;
  if ( v10 )
    *v10 = 0;
  v14 = a9;
  if ( a9 )
    *a9 = 0;
  if ( a1->Length == 2 && *a1->Buffer == 46 )
    return 3221225659LL;
  if ( !NlpCacheInitialized )
    return 3221225581LL;
  RtlAcquireResourceShared(&NlpLogonCacheCritSec, 1u);
  if ( !HIDWORD(NlpCacheControl) )
  {
    v16 = -1073741715;
LABEL_13:
    RtlReleaseResource(&NlpLogonCacheCritSec);
    return (unsigned int)v16;
  }
  v16 = NlpReadCacheEntry(a1, a1 + 2, a2, &v25, &v27, (unsigned int *)&Size);
  if ( v16 < 0 )
    goto LABEL_13;
  RtlReleaseResource(&NlpLogonCacheCritSec);
  v17 = v27;
  if ( v10 && v14 )
  {
    v18 = *((unsigned int *)v27 + 33);
    *v14 = v18;
    v19 = LocalAlloc(0x40u, v18);
    *v10 = v19;
    if ( !v19 )
    {
      CredentialNamesFromCacheEntry = -1073741801;
      goto LABEL_27;
    }
    memcpy_0(v19, (char *)v17 + *((unsigned int *)v17 + 34), (unsigned int)*v14);
  }
  v21 = NlpBuildAccountInfo((unsigned __int16 *)v17, &v26);
  v13 = v26;
  CredentialNamesFromCacheEntry = v21;
  if ( v21 >= 0 )
  {
    if ( v29 && v30 )
    {
      CredentialNamesFromCacheEntry = NlpGetCredentialNamesFromCacheEntry(v17, v26, v29, v30);
      if ( CredentialNamesFromCacheEntry < 0 )
        goto LABEL_27;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0 )
        WPP_SF_ZZZZZZ(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (_DWORD)v13 + 208,
          (_DWORD)a1 + 32,
          (_DWORD)v29,
          (__int64)v30,
          (__int64)v13 + 208,
          (__int64)v13 + 48,
          (__int64)a1,
          (__int64)&a1[2]);
    }
    v22 = *((unsigned __int16 *)v17 + 25);
    v23 = a7;
    *(_OWORD *)v9 = *((_OWORD *)v17 + 6);
    v24 = *((_OWORD *)v17 + 7);
    *v23 = v22;
    *(_OWORD *)(v9 + 16) = v24;
    *(_DWORD *)(v9 + 31) = *(_DWORD *)((char *)v17 + 127);
  }
LABEL_27:
  if ( v17 )
  {
    memset_0(v17, 0, (unsigned int)Size);
    ((void (__fastcall *)(struct _LOGON_CACHE_ENTRY *))qword_180088398)(v17);
  }
  if ( CredentialNamesFromCacheEntry < 0 )
  {
    if ( v13 )
      LocalFree(v13);
    if ( v10 && *v10 )
    {
      if ( v14 )
        memset_0(*v10, 0, (unsigned int)*v14);
      LocalFree(*v10);
      *v10 = 0;
    }
  }
  else
  {
    *a5 = v13;
  }
  return (unsigned int)CredentialNamesFromCacheEntry;
}

```

## disassembly

```asm
0x1800448cc  mov     [rsp-38h+arg_8], rbx
0x1800448d1  mov     [rsp-38h+arg_18], r9
0x1800448d6  mov     [rsp-38h+arg_10], r8
0x1800448db  push    rbp
0x1800448dc  push    rsi
0x1800448dd  push    rdi
0x1800448de  push    r12
0x1800448e0  push    r13
0x1800448e2  push    r14
0x1800448e4  push    r15
0x1800448e6  mov     rbp, rsp
0x1800448e9  sub     rsp, 70h
0x1800448ed  mov     r13, [rbp+arg_28]
0x1800448f1  xor     r14d, r14d
0x1800448f4  mov     rax, [rbp+arg_20]
0x1800448f8  xorps   xmm0, xmm0
0x1800448fb  mov     r15, [rbp+arg_38]
0x1800448ff  mov     ebx, edx
0x180044901  mov     r12, rcx
0x180044904  mov     [rbp+var_18], r14
0x180044908  mov     edi, r14d
0x18004490b  mov     [rbp+var_10], r14
0x18004490f  mov     [rax], r14
0x180044912  xor     eax, eax
0x180044914  mov     dword ptr [rbp+Size], r14d
0x180044918  mov     [rbp+var_20], r14d
0x18004491c  movups  xmmword ptr [r13+0], xmm0
0x180044921  movups  xmmword ptr [r13+10h], xmm0
0x180044926  mov     [r13+1Fh], eax
0x18004492a  mov     rax, [rbp+arg_30]
0x18004492e  mov     [rax], r14d
0x180044931  test    r15, r15
0x180044934  jz      short loc_180044939
0x180044936  mov     [r15], r14
0x180044939  mov     rsi, [rbp+arg_40]
0x180044940  test    rsi, rsi
0x180044943  jz      short loc_180044948
0x180044945  mov     [rsi], r14d
0x180044948  cmp     word ptr [rcx], 2
0x18004494c  jnz     short loc_180044962
0x18004494e  mov     rax, [rcx+8]
0x180044952  cmp     word ptr [rax], 2Eh ; '.'
0x180044956  jnz     short loc_180044962
0x180044958  mov     eax, 0C00000BBh
0x18004495d  jmp     loc_180044B55
0x180044962  cmp     cs:NlpCacheInitialized, r14b
0x180044969  jnz     short loc_180044975
0x18004496b  mov     eax, 0C000006Dh
0x180044970  jmp     loc_180044B55
0x180044975  mov     dl, 1; Wait
0x180044977  lea     rcx, NlpLogonCacheCritSec; Resource
0x18004497e  call    cs:__imp_RtlAcquireResourceShared
0x180044984  cmp     dword ptr cs:NlpCacheControl+4, r14d
0x18004498b  jnz     short loc_180044994
0x18004498d  mov     ebx, 0C000006Dh
0x180044992  jmp     short loc_1800449C0
0x180044994  lea     rcx, [rbp+Size]
0x180044998  mov     r8d, ebx; unsigned int
0x18004499b  mov     [rsp+70h+var_48], rcx; unsigned int *
0x1800449a0  lea     rdx, [rbp+var_10]
0x1800449a4  mov     [rsp+70h+var_50], rdx; struct _LOGON_CACHE_ENTRY **
0x1800449a9  lea     r9, [rbp+var_20]; unsigned int *
0x1800449ad  lea     rdx, [r12+20h]; struct _UNICODE_STRING *
0x1800449b2  mov     rcx, r12; struct _UNICODE_STRING *
0x1800449b5  call    ?NlpReadCacheEntry@@YAJPEAU_UNICODE_STRING@@0KPEAKPEAPEAU_LOGON_CACHE_ENTRY@@1@Z; NlpReadCacheEntry(_UNICODE_STRING *,_UNICODE_STRING *,ulong,ulong *,_LOGON_CACHE_ENTRY * *,ulong *)
0x1800449ba  mov     ebx, eax
0x1800449bc  test    eax, eax
0x1800449be  jns     short loc_1800449D4
0x1800449c0  lea     rcx, NlpLogonCacheCritSec; Resource
0x1800449c7  call    cs:__imp_RtlReleaseResource
0x1800449cd  mov     eax, ebx
0x1800449cf  jmp     loc_180044B55
0x1800449d4  lea     rcx, NlpLogonCacheCritSec; Resource
0x1800449db  call    cs:__imp_RtlReleaseResource
0x1800449e1  mov     rbx, [rbp+var_10]
0x1800449e5  test    r15, r15
0x1800449e8  jz      short loc_180044A29
0x1800449ea  test    rsi, rsi
0x1800449ed  jz      short loc_180044A29
0x1800449ef  mov     edx, [rbx+84h]; uBytes
0x1800449f5  mov     ecx, 40h ; '@'; uFlags
0x1800449fa  mov     [rsi], edx
0x1800449fc  call    cs:__imp_LocalAlloc
0x180044a02  mov     [r15], rax
0x180044a05  test    rax, rax
0x180044a08  jnz     short loc_180044A15
0x180044a0a  mov     r14d, 0C0000017h
0x180044a10  jmp     loc_180044AE7
0x180044a15  mov     edx, [rbx+88h]
0x180044a1b  mov     rcx, rax; void *
0x180044a1e  mov     r8d, [rsi]; Size
0x180044a21  add     rdx, rbx; Src
0x180044a24  call    memcpy_0
0x180044a29  lea     rdx, [rbp+var_18]
0x180044a2d  mov     rcx, rbx
0x180044a30  call    NlpBuildAccountInfo
0x180044a35  mov     rdi, [rbp+var_18]
0x180044a39  mov     r14d, eax
0x180044a3c  test    eax, eax
0x180044a3e  js      loc_180044AE7
0x180044a44  mov     rcx, [rbp+arg_10]
0x180044a48  test    rcx, rcx
0x180044a4b  jz      short loc_180044AC4
0x180044a4d  mov     rax, [rbp+arg_18]
0x180044a51  test    rax, rax
0x180044a54  jz      short loc_180044AC4
0x180044a56  mov     r8, rcx; struct _UNICODE_STRING *
0x180044a59  mov     r9, rax; struct _UNICODE_STRING *
0x180044a5c  mov     rcx, rbx; struct _LOGON_CACHE_ENTRY *
0x180044a5f  mov     rdx, rdi; struct _NETLOGON_VALIDATION_SAM_INFO4 *
0x180044a62  call    ?NlpGetCredentialNamesFromCacheEntry@@YAJPEAU_LOGON_CACHE_ENTRY@@PEAU_NETLOGON_VALIDATION_SAM_INFO4@@PEAU_UNICODE_STRING@@2@Z; NlpGetCredentialNamesFromCacheEntry(_LOGON_CACHE_ENTRY *,_NETLOGON_VALIDATION_SAM_INFO4 *,_UNICODE_STRING *,_UNICODE_STRING *)
0x180044a67  mov     r14d, eax
0x180044a6a  test    eax, eax
0x180044a6c  js      short loc_180044AE7
0x180044a6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180044a75  lea     rax, WPP_GLOBAL_Control
0x180044a7c  cmp     rcx, rax
0x180044a7f  jz      short loc_180044AC4
0x180044a81  test    dword ptr [rcx+1Ch], 4000h
0x180044a88  jz      short loc_180044AC4
0x180044a8a  mov     r9, [rbp+arg_18]
0x180044a8e  lea     r8, [r12+20h]
0x180044a93  mov     rcx, [rcx+10h]
0x180044a97  lea     rax, [rdi+30h]
0x180044a9b  mov     [rsp+70h+var_30], r8
0x180044aa0  lea     rdx, [rdi+0D0h]
0x180044aa7  mov     [rsp+70h+var_38], r12
0x180044aac  mov     [rsp+70h+var_40], rax
0x180044ab1  mov     [rsp+70h+var_48], rdx
0x180044ab6  mov     [rsp+70h+var_50], r9
0x180044abb  mov     r9, [rbp+arg_10]
0x180044abf  call    WPP_SF_ZZZZZZ
0x180044ac4  movzx   eax, word ptr [rbx+32h]
0x180044ac8  movups  xmm0, xmmword ptr [rbx+60h]
0x180044acc  mov     rcx, [rbp+arg_30]
0x180044ad0  movups  xmmword ptr [r13+0], xmm0
0x180044ad5  movups  xmm1, xmmword ptr [rbx+70h]
0x180044ad9  mov     [rcx], eax
0x180044adb  movups  xmmword ptr [r13+10h], xmm1
0x180044ae0  mov     eax, [rbx+7Fh]
0x180044ae3  mov     [r13+1Fh], eax
0x180044ae7  test    rbx, rbx
0x180044aea  jz      short loc_180044B09
0x180044aec  mov     r8d, dword ptr [rbp+Size]; Size
0x180044af0  xor     edx, edx; Val
0x180044af2  mov     rcx, rbx; void *
0x180044af5  call    memset_0
0x180044afa  mov     rax, cs:qword_180088398
0x180044b01  mov     rcx, rbx
0x180044b04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044b09  test    r14d, r14d
0x180044b0c  js      short loc_180044B17
0x180044b0e  mov     rax, [rbp+arg_20]
0x180044b12  mov     [rax], rdi
0x180044b15  jmp     short loc_180044B52
0x180044b17  test    rdi, rdi
0x180044b1a  jz      short loc_180044B25
0x180044b1c  mov     rcx, rdi; hMem
0x180044b1f  call    cs:__imp_LocalFree
0x180044b25  test    r15, r15
0x180044b28  jz      short loc_180044B52
0x180044b2a  cmp     qword ptr [r15], 0
0x180044b2e  jz      short loc_180044B52
0x180044b30  test    rsi, rsi
0x180044b33  jz      short loc_180044B42
0x180044b35  mov     r8d, [rsi]; Size
0x180044b38  xor     edx, edx; Val
0x180044b3a  mov     rcx, [r15]; void *
0x180044b3d  call    memset_0
0x180044b42  mov     rcx, [r15]; hMem
0x180044b45  call    cs:__imp_LocalFree
0x180044b4b  mov     qword ptr [r15], 0
0x180044b52  mov     eax, r14d
0x180044b55  mov     rbx, [rsp+70h+arg_8]
0x180044b5d  add     rsp, 70h
0x180044b61  pop     r15
0x180044b63  pop     r14
0x180044b65  pop     r13
0x180044b67  pop     r12
0x180044b69  pop     rdi
0x180044b6a  pop     rsi
0x180044b6b  pop     rbp
0x180044b6c  retn
```
