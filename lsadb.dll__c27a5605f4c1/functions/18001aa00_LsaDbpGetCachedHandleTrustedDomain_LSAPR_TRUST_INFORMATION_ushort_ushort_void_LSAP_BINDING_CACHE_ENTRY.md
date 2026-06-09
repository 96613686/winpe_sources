# LsaDbpGetCachedHandleTrustedDomain(_LSAPR_TRUST_INFORMATION *,ushort * *,ushort * *,void * *,_LSAP_BINDING_CACHE_ENTRY * *)

- ea: `0x18001aa00`
- end: `0x18001ab89`
- name: `?LsaDbpGetCachedHandleTrustedDomain@@YAJPEAU_LSAPR_TRUST_INFORMATION@@PEAPEAG1PEAPEAXPEAPEAU_LSAP_BINDING_CACHE_ENTRY@@@Z`
- size: `393`
- prototype: `__int64 __fastcall(struct _LSAPR_TRUST_INFORMATION *String2, PCWSTR *, unsigned __int16 **, void **, struct _LSAP_BINDING_CACHE_ENTRY **)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x18000bff4`
- `0x1800164a8`
- `0x1800165f0`
- `0x1800166a4`
- `0x180016740`
- `0x18001aa00`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ab42`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ab42`
- `LSASRV!LsapRtlValidateControllerTrustedDomain` at `0x18001aaf2`
- `LSASRV!LsapRtlValidateControllerTrustedDomain` at `0x18001aaf2`
- `LSASRV!LsapRtlValidateControllerTrustedDomainByHandle` at `0x18001aa93`
- `LSASRV!LsapRtlValidateControllerTrustedDomainByHandle` at `0x18001aa93`
- `ntdll!RtlInitUnicodeString` at `0x18001aac6`
- `ntdll!RtlInitUnicodeString` at `0x18001aac6`
- `ADVAPI32!LsaClose` at `0x18001ab2f`
- `ADVAPI32!LsaClose` at `0x18001ab2f`
- `NETLOGON!I_NetLogonFree` at `0x18001ab54`
- `NETLOGON!I_NetLogonFree` at `0x18001ab65`
- `NETLOGON!I_NetLogonFree` at `0x18001ab54`
- `NETLOGON!I_NetLogonFree` at `0x18001ab65`

## pseudocode

```c
__int64 __fastcall LsaDbpGetCachedHandleTrustedDomain(
        struct _LSAPR_TRUST_INFORMATION *String2,
        PCWSTR *a2,
        unsigned __int16 **a3,
        void **a4,
        struct _LSAP_BINDING_CACHE_ENTRY **a5)
{
  struct _LSAP_BINDING_CACHE_ENTRY **v5; // r13
  struct _LSAPR_TRUST_INFORMATION *v9; // rdi
  const UNICODE_STRING *v10; // rbp
  struct _LSAPR_SID *v11; // rcx
  int v12; // ebx
  struct _LSAP_BINDING_CACHE_ENTRY *BindingCacheEntry; // rax
  struct _LSAP_BINDING_CACHE_ENTRY *v14; // rsi
  struct _LSAPR_TRUST_INFORMATION *v16; // [rsp+30h] [rbp-68h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-60h] BYREF
  LSA_HANDLE ObjectHandle; // [rsp+A0h] [rbp+8h] BYREF

  v5 = a5;
  v16 = 0;
  ObjectHandle = 0;
  *a5 = 0;
  v9 = String2;
  DestinationString = 0;
  if ( *(_WORD *)String2 && *((_QWORD *)String2 + 1) )
  {
    v10 = (const UNICODE_STRING *)String2;
  }
  else
  {
    v11 = (struct _LSAPR_SID *)*((_QWORD *)String2 + 2);
    v12 = -1073741811;
    if ( !v11 )
      return (unsigned int)v12;
    v12 = LsaDbpLookupSidTrustedDomainList(v11, &v16);
    if ( v12 < 0 )
      goto LABEL_12;
    v10 = (const UNICODE_STRING *)v16;
    v9 = v16;
  }
  BindingCacheEntry = LsaDbpLocateBindingCacheEntry(v10, 0);
  v14 = BindingCacheEntry;
  if ( !BindingCacheEntry )
    goto LABEL_10;
  v12 = LsapRtlValidateControllerTrustedDomainByHandle(*((_QWORD *)BindingCacheEntry + 9), v9);
  if ( v12 < 0 )
  {
    LsaDbpReferenceBindingCacheEntry(v14, 1u);
    LsaDbpDereferenceBindingCacheEntry(v14);
    LsaDbpDereferenceBindingCacheEntry(v14);
LABEL_10:
    RtlInitUnicodeString(&DestinationString, *a2);
    v12 = LsapRtlValidateControllerTrustedDomain(&DestinationString, v9, 2049, *a3, *a4, &ObjectHandle);
    if ( v12 >= 0 )
      v12 = LsaDbpCacheBinding(v10, &ObjectHandle, (unsigned __int16 **)a2, a3, a4, v5);
    goto LABEL_12;
  }
  *v5 = v14;
LABEL_12:
  if ( ObjectHandle )
    LsaClose(ObjectHandle);
  if ( v12 >= 0 )
  {
    if ( *a2 )
    {
      LocalFree((HLOCAL)*a2);
      *a2 = 0;
    }
    if ( *a3 )
    {
      I_NetLogonFree();
      *a3 = 0;
    }
    if ( *a4 )
    {
      I_NetLogonFree();
      *a4 = 0;
    }
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18001aa00  mov     rax, rsp
0x18001aa03  push    rbx
0x18001aa04  push    rbp
0x18001aa05  push    rsi
0x18001aa06  push    rdi
0x18001aa07  push    r12
0x18001aa09  push    r13
0x18001aa0b  push    r14
0x18001aa0d  push    r15
0x18001aa0f  sub     rsp, 58h
0x18001aa13  mov     r13, [rsp+98h+arg_20]
0x18001aa1b  xor     esi, esi
0x18001aa1d  xorps   xmm0, xmm0
0x18001aa20  mov     [rax-68h], rsi
0x18001aa24  mov     r14, r9
0x18001aa27  mov     [rax+8], rsi
0x18001aa2b  mov     r15, r8
0x18001aa2e  mov     r12, rdx
0x18001aa31  mov     [r13+0], rsi
0x18001aa35  mov     rdi, rcx
0x18001aa38  movups  xmmword ptr [rax-60h], xmm0
0x18001aa3c  cmp     [rcx], si
0x18001aa3f  jz      short loc_18001AA4C
0x18001aa41  cmp     [rcx+8], rsi
0x18001aa45  jz      short loc_18001AA4C
0x18001aa47  mov     rbp, rcx
0x18001aa4a  jmp     short loc_18001AA7A
0x18001aa4c  mov     rcx, [rcx+10h]; struct _LSAPR_SID *
0x18001aa50  mov     ebx, 0C000000Dh
0x18001aa55  test    rcx, rcx
0x18001aa58  jz      loc_18001AB6E
0x18001aa5e  lea     rdx, [rsp+98h+var_68]; struct _LSAPR_TRUST_INFORMATION **
0x18001aa63  call    ?LsaDbpLookupSidTrustedDomainList@@YAJPEAU_LSAPR_SID@@PEAPEAU_LSAPR_TRUST_INFORMATION@@@Z; LsaDbpLookupSidTrustedDomainList(_LSAPR_SID *,_LSAPR_TRUST_INFORMATION * *)
0x18001aa68  mov     ebx, eax
0x18001aa6a  test    eax, eax
0x18001aa6c  js      loc_18001AB22
0x18001aa72  mov     rbp, [rsp+98h+var_68]
0x18001aa77  mov     rdi, rbp
0x18001aa7a  xor     edx, edx; unsigned __int8
0x18001aa7c  mov     rcx, rbp; String2
0x18001aa7f  call    ?LsaDbpLocateBindingCacheEntry@@YAPEAU_LSAP_BINDING_CACHE_ENTRY@@PEAU_UNICODE_STRING@@E@Z; LsaDbpLocateBindingCacheEntry(_UNICODE_STRING *,uchar)
0x18001aa84  mov     rsi, rax
0x18001aa87  test    rax, rax
0x18001aa8a  jz      short loc_18001AABD
0x18001aa8c  mov     rcx, [rax+48h]
0x18001aa90  mov     rdx, rdi
0x18001aa93  call    cs:__imp_LsapRtlValidateControllerTrustedDomainByHandle
0x18001aa99  mov     ebx, eax
0x18001aa9b  test    eax, eax
0x18001aa9d  jns     loc_18001AB81
0x18001aaa3  mov     dl, 1; unsigned __int8
0x18001aaa5  mov     rcx, rsi; struct _LSAP_BINDING_CACHE_ENTRY *
0x18001aaa8  call    ?LsaDbpReferenceBindingCacheEntry@@YAXPEAU_LSAP_BINDING_CACHE_ENTRY@@E@Z; LsaDbpReferenceBindingCacheEntry(_LSAP_BINDING_CACHE_ENTRY *,uchar)
0x18001aaad  mov     rcx, rsi; struct _LSAP_BINDING_CACHE_ENTRY *
0x18001aab0  call    ?LsaDbpDereferenceBindingCacheEntry@@YAXPEAU_LSAP_BINDING_CACHE_ENTRY@@@Z; LsaDbpDereferenceBindingCacheEntry(_LSAP_BINDING_CACHE_ENTRY *)
0x18001aab5  mov     rcx, rsi; struct _LSAP_BINDING_CACHE_ENTRY *
0x18001aab8  call    ?LsaDbpDereferenceBindingCacheEntry@@YAXPEAU_LSAP_BINDING_CACHE_ENTRY@@@Z; LsaDbpDereferenceBindingCacheEntry(_LSAP_BINDING_CACHE_ENTRY *)
0x18001aabd  mov     rdx, [r12]; SourceString
0x18001aac1  lea     rcx, [rsp+98h+DestinationString]; DestinationString
0x18001aac6  call    cs:__imp_RtlInitUnicodeString
0x18001aacc  mov     r9, [r15]
0x18001aacf  lea     rax, [rsp+98h+ObjectHandle]
0x18001aad7  mov     [rsp+98h+var_70], rax
0x18001aadc  lea     rcx, [rsp+98h+DestinationString]
0x18001aae1  mov     rax, [r14]
0x18001aae4  mov     r8d, 801h
0x18001aaea  mov     rdx, rdi
0x18001aaed  mov     [rsp+98h+var_78], rax
0x18001aaf2  call    cs:__imp_LsapRtlValidateControllerTrustedDomain
0x18001aaf8  xor     esi, esi
0x18001aafa  mov     ebx, eax
0x18001aafc  test    eax, eax
0x18001aafe  js      short loc_18001AB22
0x18001ab00  mov     [rsp+98h+var_70], r13; struct _LSAP_BINDING_CACHE_ENTRY **
0x18001ab05  lea     rdx, [rsp+98h+ObjectHandle]; void **
0x18001ab0d  mov     r9, r15; unsigned __int16 **
0x18001ab10  mov     [rsp+98h+var_78], r14; void **
0x18001ab15  mov     r8, r12; unsigned __int16 **
0x18001ab18  mov     rcx, rbp; String2
0x18001ab1b  call    ?LsaDbpCacheBinding@@YAJPEAU_UNICODE_STRING@@PEAPEAXPEAPEAG21PEAPEAU_LSAP_BINDING_CACHE_ENTRY@@@Z; LsaDbpCacheBinding(_UNICODE_STRING *,void * *,ushort * *,ushort * *,void * *,_LSAP_BINDING_CACHE_ENTRY * *)
0x18001ab20  mov     ebx, eax
0x18001ab22  mov     rcx, [rsp+98h+ObjectHandle]; ObjectHandle
0x18001ab2a  test    rcx, rcx
0x18001ab2d  jz      short loc_18001AB35
0x18001ab2f  call    cs:__imp_LsaClose
0x18001ab35  test    ebx, ebx
0x18001ab37  js      short loc_18001AB6E
0x18001ab39  mov     rcx, [r12]; hMem
0x18001ab3d  test    rcx, rcx
0x18001ab40  jz      short loc_18001AB4C
0x18001ab42  call    cs:__imp_LocalFree
0x18001ab48  mov     [r12], rsi
0x18001ab4c  mov     rcx, [r15]
0x18001ab4f  test    rcx, rcx
0x18001ab52  jz      short loc_18001AB5D
0x18001ab54  call    cs:__imp_I_NetLogonFree
0x18001ab5a  mov     [r15], rsi
0x18001ab5d  mov     rcx, [r14]
0x18001ab60  test    rcx, rcx
0x18001ab63  jz      short loc_18001AB6E
0x18001ab65  call    cs:__imp_I_NetLogonFree
0x18001ab6b  mov     [r14], rsi
0x18001ab6e  mov     eax, ebx
0x18001ab70  add     rsp, 58h
0x18001ab74  pop     r15
0x18001ab76  pop     r14
0x18001ab78  pop     r13
0x18001ab7a  pop     r12
0x18001ab7c  pop     rdi
0x18001ab7d  pop     rsi
0x18001ab7e  pop     rbp
0x18001ab7f  pop     rbx
0x18001ab80  retn
0x18001ab81  mov     [r13+0], rsi
0x18001ab85  xor     esi, esi
0x18001ab87  jmp     short loc_18001AB22
```
