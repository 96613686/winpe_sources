# LsaApLogonUserEx2(void * *,_SECURITY_LOGON_TYPE,void *,void *,ulong,void * *,ulong *,_LUID *,long *,_LSA_TOKEN_INFORMATION_TYPE *,void * *,_UNICODE_STRING * *,_UNICODE_STRING * *,_UNICODE_STRING * *,_SECPKG_PRIMARY_CRED *,_SECPKG_SUPPLEMENTAL_CRED_ARRAY * *)

- ea: `0x180008880`
- end: `0x180008c50`
- name: `?LsaApLogonUserEx2@@YAJPEAPEAXW4_SECURITY_LOGON_TYPE@@PEAX2K0PEAKPEAU_LUID@@PEAJPEAW4_LSA_TOKEN_INFORMATION_TYPE@@0PEAPEAU_UNICODE_STRING@@77PEAU_SECPKG_PRIMARY_CRED@@PEAPEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@@Z`
- size: `976`
- prototype: `int(void **, enum _SECURITY_LOGON_TYPE, void *, void *, unsigned int, void **, unsigned int *, struct _LUID *, int *, enum _LSA_TOKEN_INFORMATION_TYPE *, void **, struct _UNICODE_STRING **, struct _UNICODE_STRING **, struct _UNICODE_STRING **, struct _SECPKG_PRIMARY_CRED *, struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800087d0`
- `0x180008880`
- `0x180008c58`
- `0x180008e2c`
- `0x18001ecee`
- `0x180020010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180008953`
- `ntdll!RtlReleaseResource` at `0x180008953`
- `ntdll!RtlAcquireResourceShared` at `0x18000891d`
- `ntdll!RtlAcquireResourceShared` at `0x18000891d`
- `SspiCli!SspiValidateAuthIdentity` at `0x1800088ea`
- `SspiCli!SspiValidateAuthIdentity` at `0x1800088ea`

## pseudocode

```c
__int64 __fastcall LsaApLogonUserEx2(
        void **a1,
        unsigned int a2,
        _DWORD *a3,
        void *a4,
        unsigned int a5,
        void **a6,
        unsigned int *a7,
        struct _LUID *a8,
        int *a9,
        enum _LSA_TOKEN_INFORMATION_TYPE *a10,
        void **a11,
        struct _UNICODE_STRING **a12,
        struct _UNICODE_STRING **a13,
        struct _UNICODE_STRING **a14,
        struct _SECPKG_PRIMARY_CRED *a15,
        struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **a16)
{
  unsigned int v16; // ebx
  unsigned int v20; // ecx
  unsigned int v21; // esi
  size_t v22; // rbp
  struct _WST_SSP_PACKAGE **v23; // r15
  unsigned int v24; // ebp
  __int64 j; // rax
  struct _WST_SSP_PACKAGE *v26; // rcx
  __int64 (__fastcall *v27)(void **, _QWORD, _DWORD *, void *, unsigned int, void **, unsigned int *, struct _LUID *, int *, enum _LSA_TOKEN_INFORMATION_TYPE *, void **, struct _UNICODE_STRING **, struct _UNICODE_STRING **, struct _UNICODE_STRING **, struct _SECPKG_PRIMARY_CRED *, struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **); // rax
  unsigned int v28; // eax
  unsigned int k; // ebx
  struct _WST_SSP_PACKAGE *v30; // rcx
  struct _WST_SSP_PACKAGE *v32; // r14
  __int64 i; // rbp
  struct _WST_SSP_PACKAGE **v34; // rax

  v16 = a5;
  if ( a5 < 4 )
    return (unsigned int)-1073741811;
  if ( *a3 != 513 )
  {
    if ( ((*a3 - 13) & 0xFFFFFFFD) == 0 )
      goto LABEL_7;
    return (unsigned int)-1073741811;
  }
  if ( a5 < 0x30 )
    return (unsigned int)-2146893039;
  v20 = a3[2];
  if ( (a3[9] & 0x10000) != 0 )
  {
    if ( v20 <= a5 - 8 )
      goto LABEL_6;
    return (unsigned int)-1073741811;
  }
  if ( v20 > a5 )
    return (unsigned int)-1073741811;
LABEL_6:
  if ( SspiValidateAuthIdentity(a3) < 0 )
    return (unsigned int)-1073741811;
LABEL_7:
  if ( !WSTGlobalPkgCount )
  {
    v24 = -2146893042;
LABEL_54:
    if ( v24 == -2146893042 )
      return (unsigned int)-2146893039;
    return v24;
  }
  RtlAcquireResourceShared(&WSTGlobalLoaderLock, 1u);
  v21 = WSTGlobalPkgCount;
  a5 = WSTGlobalPkgCount;
  v22 = 8LL * WSTGlobalPkgCount;
  if ( v22 > 0xFFFFFFFF )
  {
    v23 = 0;
LABEL_10:
    v24 = -1073741801;
    goto LABEL_11;
  }
  if ( *((_DWORD *)WSTGlobalBaseSSP + 52) == 1 )
  {
    v23 = (struct _WST_SSP_PACKAGE **)(*(__int64 (__fastcall **)(_QWORD))(*((_QWORD *)WSTGlobalBaseSSP + 30) + 384LL))((unsigned int)v22);
  }
  else
  {
    v34 = (struct _WST_SSP_PACKAGE **)(**((__int64 (__fastcall ***)(_QWORD))WSTGlobalBaseSSP + 31))((unsigned int)v22);
    v23 = v34;
    if ( v34 )
      memset_0(v34, 0, v22);
  }
  if ( !v23 )
    goto LABEL_10;
  v32 = WSTGlobalPkgList;
  for ( i = 0; v32 != (struct _WST_SSP_PACKAGE *)&WSTGlobalPkgList; v32 = *(struct _WST_SSP_PACKAGE **)v32 )
  {
    if ( (unsigned int)i < v21 )
    {
      v23[i] = v32;
      WSTReferencePackage(v32);
      i = (unsigned int)(i + 1);
    }
  }
  v24 = (unsigned int)i < WSTGlobalPkgCount ? 0x8009030E : 0;
LABEL_11:
  RtlReleaseResource(&WSTGlobalLoaderLock);
  if ( !v21 )
  {
    v24 = -1073741275;
LABEL_52:
    if ( v23 )
      WSTFreePackages(&a5, v23);
    goto LABEL_54;
  }
  if ( (v24 & 0x80000000) != 0 )
    goto LABEL_52;
  for ( j = 0; ; j = a5 + 1 )
  {
    a5 = j;
    if ( (unsigned int)j >= v21 )
      break;
    v26 = v23[j];
    if ( (*((_DWORD *)v26 + 103) & 0x2000) != 0 )
    {
      v27 = (__int64 (__fastcall *)(void **, _QWORD, _DWORD *, void *, unsigned int, void **, unsigned int *, struct _LUID *, int *, enum _LSA_TOKEN_INFORMATION_TYPE *, void **, struct _UNICODE_STRING **, struct _UNICODE_STRING **, struct _UNICODE_STRING **, struct _SECPKG_PRIMARY_CRED *, struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **))*((_QWORD *)v26 + 11);
      if ( v27 )
      {
        v28 = v27(a1, a2, a3, a4, v16, a6, a7, a8, a9, a10, a11, a12, a13, a14, a15, a16);
        v24 = v28;
        if ( v28 != -1073741557 && v28 != -1073741657 && v28 != -2146893039 && v28 != -1073741811 )
          goto LABEL_23;
      }
    }
  }
  v24 = -2146893039;
LABEL_23:
  if ( v23 )
  {
    for ( k = 0; k < v21; ++k )
    {
      v30 = v23[k];
      if ( v30 )
      {
        WSTDereferencePackage(v30);
        v23[k] = 0;
      }
    }
    if ( *((_DWORD *)WSTGlobalBaseSSP + 52) == 1 )
      (*(void (__fastcall **)(struct _WST_SSP_PACKAGE **))(*((_QWORD *)WSTGlobalBaseSSP + 30) + 392LL))(v23);
    else
      (*(void (__fastcall **)(struct _WST_SSP_PACKAGE **))(*((_QWORD *)WSTGlobalBaseSSP + 31) + 8LL))(v23);
  }
  return v24;
}

```

## disassembly

```asm
0x180008880  mov     [rsp+arg_18], rbx
0x180008885  mov     [rsp+arg_0], rcx
0x18000888a  push    rbp
0x18000888b  push    rsi
0x18000888c  push    rdi
0x18000888d  push    r12
0x18000888f  push    r13
0x180008891  sub     rsp, 90h
0x180008898  mov     ebx, [rsp+0B8h+arg_20]
0x18000889f  xor     esi, esi
0x1800088a1  mov     r12, r9
0x1800088a4  mov     rdi, r8
0x1800088a7  mov     r13d, edx
0x1800088aa  cmp     ebx, 4
0x1800088ad  jb      loc_180008B2A
0x1800088b3  mov     eax, [r8]
0x1800088b6  cmp     eax, 201h
0x1800088bb  jnz     loc_180008B1C
0x1800088c1  cmp     ebx, 30h ; '0'
0x1800088c4  jb      loc_180008A6F
0x1800088ca  test    dword ptr [r8+24h], 10000h
0x1800088d2  mov     ecx, [r8+8]
0x1800088d6  jz      loc_180008A62
0x1800088dc  lea     eax, [rbx-8]
0x1800088df  cmp     ecx, eax
0x1800088e1  ja      loc_180008B2A
0x1800088e7  mov     rcx, rdi; AuthData
0x1800088ea  call    cs:__imp_SspiValidateAuthIdentity
0x1800088f0  test    eax, eax
0x1800088f2  js      loc_180008BA3
0x1800088f8  cmp     cs:?WSTGlobalPkgCount@@3KA, esi; ulong WSTGlobalPkgCount
0x1800088fe  mov     [rsp+0B8h+arg_8], r14
0x180008906  mov     [rsp+0B8h+arg_10], r15
0x18000890e  jz      loc_180008BAD
0x180008914  mov     dl, 1; Wait
0x180008916  lea     rcx, ?WSTGlobalLoaderLock@@3U_RTL_RESOURCE@@A; Resource
0x18000891d  call    cs:__imp_RtlAcquireResourceShared
0x180008923  mov     esi, cs:?WSTGlobalPkgCount@@3KA; ulong WSTGlobalPkgCount
0x180008929  mov     ebp, esi
0x18000892b  mov     [rsp+0B8h+arg_20], esi
0x180008932  shl     rbp, 3
0x180008936  mov     eax, 0FFFFFFFFh
0x18000893b  cmp     rbp, rax
0x18000893e  jbe     loc_180008BB4
0x180008944  xor     r15d, r15d
0x180008947  mov     ebp, 0C0000017h
0x18000894c  lea     rcx, ?WSTGlobalLoaderLock@@3U_RTL_RESOURCE@@A; Resource
0x180008953  call    cs:__imp_RtlReleaseResource
0x180008959  test    esi, esi
0x18000895b  jz      loc_180008C10
0x180008961  test    ebp, ebp
0x180008963  js      loc_180008C15
0x180008969  mov     r14, r15
0x18000896c  xor     eax, eax
0x18000896e  mov     [rsp+0B8h+arg_20], eax
0x180008975  cmp     eax, esi
0x180008977  jnb     loc_180008A76
0x18000897d  mov     rcx, [r14+rax*8]
0x180008981  test    dword ptr [rcx+19Ch], 2000h
0x18000898b  jz      loc_180008A54
0x180008991  mov     rax, [rcx+58h]
0x180008995  test    rax, rax
0x180008998  jz      loc_180008A54
0x18000899e  mov     rcx, [rsp+0B8h+arg_78]
0x1800089a6  mov     r9, r12
0x1800089a9  mov     [rsp+0B8h+var_40], rcx
0x1800089ae  mov     r8, rdi
0x1800089b1  mov     rcx, [rsp+0B8h+arg_70]
0x1800089b9  mov     edx, r13d
0x1800089bc  mov     [rsp+0B8h+var_48], rcx
0x1800089c1  mov     rcx, [rsp+0B8h+arg_68]
0x1800089c9  mov     [rsp+0B8h+var_50], rcx
0x1800089ce  mov     rcx, [rsp+0B8h+arg_60]
0x1800089d6  mov     [rsp+0B8h+var_58], rcx
0x1800089db  mov     rcx, [rsp+0B8h+arg_58]
0x1800089e3  mov     [rsp+0B8h+var_60], rcx
0x1800089e8  mov     rcx, [rsp+0B8h+arg_50]
0x1800089f0  mov     [rsp+0B8h+var_68], rcx
0x1800089f5  mov     rcx, [rsp+0B8h+arg_48]
0x1800089fd  mov     [rsp+0B8h+var_70], rcx
0x180008a02  mov     rcx, [rsp+0B8h+arg_40]
0x180008a0a  mov     [rsp+0B8h+var_78], rcx
0x180008a0f  mov     rcx, [rsp+0B8h+arg_38]
0x180008a17  mov     [rsp+0B8h+var_80], rcx
0x180008a1c  mov     rcx, [rsp+0B8h+arg_30]
0x180008a24  mov     [rsp+0B8h+var_88], rcx
0x180008a29  mov     rcx, [rsp+0B8h+arg_28]
0x180008a31  mov     [rsp+0B8h+var_90], rcx
0x180008a36  mov     rcx, [rsp+0B8h+arg_0]
0x180008a3e  mov     [rsp+0B8h+var_98], ebx
0x180008a42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a47  mov     ebp, eax
0x180008a49  cmp     eax, 0C000010Bh
0x180008a4e  jnz     loc_180008AF6
0x180008a54  mov     eax, [rsp+0B8h+arg_20]
0x180008a5b  inc     eax
0x180008a5d  jmp     loc_18000896E
0x180008a62  cmp     ecx, ebx
0x180008a64  jbe     loc_1800088E7
0x180008a6a  jmp     loc_180008B2A
0x180008a6f  mov     ebp, 80090311h
0x180008a74  jmp     short loc_180008ADD
0x180008a76  mov     ebp, 80090311h
0x180008a7b  test    r15, r15
0x180008a7e  jz      short loc_180008ACD
0x180008a80  xor     r12d, r12d
0x180008a83  mov     ebx, r12d
0x180008a86  test    esi, esi
0x180008a88  jz      short loc_180008AA7
0x180008a8a  mov     eax, ebx
0x180008a8c  mov     rcx, [r14+rax*8]; struct _WST_SSP_PACKAGE *
0x180008a90  lea     rdi, [r14+rax*8]
0x180008a94  test    rcx, rcx
0x180008a97  jz      short loc_180008AA1
0x180008a99  call    ?WSTDereferencePackage@@YAXPEAU_WST_SSP_PACKAGE@@@Z; WSTDereferencePackage(_WST_SSP_PACKAGE *)
0x180008a9e  mov     [rdi], r12
0x180008aa1  inc     ebx
0x180008aa3  cmp     ebx, esi
0x180008aa5  jb      short loc_180008A8A
0x180008aa7  mov     rax, cs:?WSTGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; basessp::BaseSSP * WSTGlobalBaseSSP
0x180008aae  mov     rcx, r15
0x180008ab1  cmp     dword ptr [rax+0D0h], 1
0x180008ab8  jnz     short loc_180008B31
0x180008aba  mov     rax, [rax+0F0h]
0x180008ac1  mov     rax, [rax+188h]
0x180008ac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008acd  mov     r14, [rsp+0B8h+arg_8]
0x180008ad5  mov     r15, [rsp+0B8h+arg_10]
0x180008add  mov     rbx, [rsp+0B8h+arg_18]
0x180008ae5  mov     eax, ebp
0x180008ae7  add     rsp, 90h
0x180008aee  pop     r13
0x180008af0  pop     r12
0x180008af2  pop     rdi
0x180008af3  pop     rsi
0x180008af4  pop     rbp
0x180008af5  retn
0x180008af6  cmp     eax, 0C00000A7h
0x180008afb  jz      loc_180008A54
0x180008b01  cmp     eax, 80090311h
0x180008b06  jz      loc_180008A54
0x180008b0c  cmp     eax, 0C000000Dh
0x180008b11  jnz     loc_180008A7B
0x180008b17  jmp     loc_180008A54
0x180008b1c  add     eax, 0FFFFFFF3h
0x180008b1f  test    eax, 0FFFFFFFDh
0x180008b24  jz      loc_1800088F8
0x180008b2a  mov     ebp, 0C000000Dh
0x180008b2f  jmp     short loc_180008ADD
0x180008b31  mov     rax, [rax+0F8h]
0x180008b38  mov     rax, [rax+8]
0x180008b3c  jmp     short loc_180008AC8
0x180008b3e  test    r15, r15
0x180008b41  jz      loc_180008947
0x180008b47  mov     r14, cs:?WSTGlobalPkgList@@3U_LIST_ENTRY@@A; _LIST_ENTRY WSTGlobalPkgList
0x180008b4e  lea     rax, ?WSTGlobalPkgList@@3U_LIST_ENTRY@@A; _LIST_ENTRY WSTGlobalPkgList
0x180008b55  xor     ebp, ebp
0x180008b57  cmp     r14, rax
0x180008b5a  jz      short loc_180008B7D
0x180008b5c  cmp     ebp, esi
0x180008b5e  jnb     short loc_180008B75
0x180008b60  mov     rcx, r14; struct _WST_SSP_PACKAGE *
0x180008b63  mov     [r15+rbp*8], r14
0x180008b67  call    ?WSTReferencePackage@@YAXPEAU_WST_SSP_PACKAGE@@@Z; WSTReferencePackage(_WST_SSP_PACKAGE *)
0x180008b6c  inc     ebp
0x180008b6e  lea     rax, ?WSTGlobalPkgList@@3U_LIST_ENTRY@@A; _LIST_ENTRY WSTGlobalPkgList
0x180008b75  mov     r14, [r14]
0x180008b78  cmp     r14, rax
0x180008b7b  jnz     short loc_180008B5C
0x180008b7d  cmp     ebp, cs:?WSTGlobalPkgCount@@3KA; ulong WSTGlobalPkgCount
0x180008b83  sbb     ebp, ebp
0x180008b85  and     ebp, 8009030Eh
0x180008b8b  jmp     loc_18000894C
0x180008b90  test    ebp, ebp
0x180008b92  js      loc_180008C3A
0x180008b98  xor     r15d, r15d
0x180008b9b  xor     r14d, r14d
0x180008b9e  jmp     loc_18000896C
0x180008ba3  mov     ebp, 0C000000Dh
0x180008ba8  jmp     loc_180008ADD
0x180008bad  mov     ebp, 8009030Eh
0x180008bb2  jmp     short loc_180008B90
0x180008bb4  mov     rax, cs:?WSTGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; basessp::BaseSSP * WSTGlobalBaseSSP
0x180008bbb  cmp     dword ptr [rax+0D0h], 1
0x180008bc2  jnz     short loc_180008BE1
0x180008bc4  mov     rax, [rax+0F0h]
0x180008bcb  mov     ecx, ebp
0x180008bcd  mov     rax, [rax+180h]
0x180008bd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bd9  mov     r15, rax
0x180008bdc  jmp     loc_180008B3E
0x180008be1  mov     rax, [rax+0F8h]
0x180008be8  mov     ecx, ebp
0x180008bea  mov     rax, [rax]
0x180008bed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bf2  mov     r15, rax
0x180008bf5  test    rax, rax
0x180008bf8  jz      loc_180008B3E
0x180008bfe  mov     r8, rbp; Size
0x180008c01  xor     edx, edx; Val
0x180008c03  mov     rcx, rax; void *
0x180008c06  call    memset_0
0x180008c0b  jmp     loc_180008B3E
0x180008c10  mov     ebp, 0C0000225h
0x180008c15  test    r15, r15
0x180008c18  jz      loc_180008B90
0x180008c1e  mov     rdx, r15; struct _WST_SSP_PACKAGE **
0x180008c21  lea     rcx, [rsp+0B8h+arg_20]; unsigned int *
0x180008c29  call    ?WSTFreePackages@@YAXPEAKPEAPEAU_WST_SSP_PACKAGE@@@Z; WSTFreePackages(ulong *,_WST_SSP_PACKAGE * *)
0x180008c2e  mov     esi, [rsp+0B8h+arg_20]
0x180008c35  jmp     loc_180008B90
0x180008c3a  cmp     ebp, 8009030Eh
0x180008c40  jnz     loc_180008ACD
0x180008c46  mov     ebp, 80090311h
0x180008c4b  jmp     loc_180008ACD
```
