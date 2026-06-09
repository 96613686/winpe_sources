# LsapDbLookupSimpleNames(ulong,ulong,_LSAPR_UNICODE_STRING *,_LSAPR_UNICODE_STRING *,_LSAPR_UNICODE_STRING *,_LSAPR_TRUST_INFORMATION *,_LSAPR_TRUST_INFORMATION_EX *,_LSAPR_TRUST_INFORMATION_EX *,_LSAPR_TRUST_INFORMATION *,_LSAPR_REFERENCED_DOMAIN_LIST *,_LSAPR_TRANSLATED_SIDS_EX2 *,ulong *,ulong *)

- ea: `0x1800388a0`
- end: `0x180038e0e`
- name: `?LsapDbLookupSimpleNames@@YAJKKPEAU_LSAPR_UNICODE_STRING@@00PEAU_LSAPR_TRUST_INFORMATION@@PEAU_LSAPR_TRUST_INFORMATION_EX@@21PEAU_LSAPR_REFERENCED_DOMAIN_LIST@@PEAU_LSAPR_TRANSLATED_SIDS_EX2@@PEAK5@Z`
- size: `1390`
- prototype: `__int64 __usercall@<rax>(unsigned int@<ecx>, unsigned int@<edx>, struct _LSAPR_UNICODE_STRING *@<r8>, struct _LSAPR_UNICODE_STRING *@<r9>, struct _LSAPR_UNICODE_STRING *, struct _LSAPR_TRUST_INFORMATION *, struct _LSAPR_TRUST_INFORMATION_EX *, struct _LSAPR_TRUST_INFORMATION_EX *, struct _LSAPR_TRUST_INFORMATION *, struct _LSAPR_REFERENCED_DOMAIN_LIST *, struct _LSAPR_TRANSLATED_SIDS_EX2 *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180012da4`

## callees

- `0x180038618`
- `0x1800388a0`
- `0x180038e14`
- `0x18003915c`
- `0x180039400`
- `0x180039660`
- `0x1800bd6e0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038b71`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038b89`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038b71`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038b89`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180038a50`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180038ad2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180038c01`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180038a50`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180038ad2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180038c01`
- `ntdll!RtlEqualDomainName` at `0x180038b29`
- `ntdll!RtlEqualDomainName` at `0x180038d6a`
- `ntdll!RtlEqualDomainName` at `0x180038b29`
- `ntdll!RtlEqualDomainName` at `0x180038d6a`
- `ntdll!RtlCopySid` at `0x180038c3f`
- `ntdll!RtlCopySid` at `0x180038c3f`
- `ntdll!RtlLengthSid` at `0x180038be7`
- `ntdll!RtlLengthSid` at `0x180038be7`
- `DNSAPI!DnsNameCompare_W` at `0x180038b47`
- `DNSAPI!DnsNameCompare_W` at `0x180038b47`

## pseudocode

```c
__int64 __fastcall LsapDbLookupSimpleNames(
        unsigned int a1,
        struct _LSAPR_UNICODE_STRING *a2,
        struct _LSAPR_UNICODE_STRING *a3,
        struct _LSAPR_UNICODE_STRING *a4,
        struct _LSAPR_UNICODE_STRING *a5,
        struct _LSAPR_TRUST_INFORMATION *a6,
        struct _LSAPR_TRUST_INFORMATION_EX *a7,
        struct _LSAPR_TRUST_INFORMATION_EX *a8,
        struct _LSAPR_TRUST_INFORMATION *a9,
        struct _LSAPR_REFERENCED_DOMAIN_LIST *a10,
        struct _LSAPR_TRANSLATED_SIDS_EX2 *a11,
        unsigned int *a12,
        unsigned int *a13)
{
  unsigned int *v15; // r15
  unsigned int *v16; // rsi
  struct _LSAPR_TRANSLATED_SIDS_EX2 *v17; // rbp
  struct _LSAPR_REFERENCED_DOMAIN_LIST *v18; // r13
  __int64 result; // rax
  struct _LSAPR_UNICODE_STRING *v20; // rdx
  int v21; // ebx
  unsigned int i; // r12d
  __int64 v23; // rdx
  __int64 v24; // rax
  __int64 v25; // rax
  struct _UNICODE_STRING *v26; // r10
  __int64 v27; // rax
  void *v28; // rcx
  unsigned __int64 Length; // rdx
  WCHAR **p_Buffer; // rax
  WCHAR *v31; // rax
  int v32; // eax
  void *v33; // rdx
  struct _UNICODE_STRING *v34; // rax
  int v35; // eax
  char v36; // [rsp+40h] [rbp-B8h]
  const void **pName2; // [rsp+48h] [rbp-B0h]
  WCHAR *pName2a; // [rsp+48h] [rbp-B0h]
  struct _UNICODE_STRING *DomainName1; // [rsp+50h] [rbp-A8h]
  WCHAR *pName1; // [rsp+60h] [rbp-98h]
  void *Src[2]; // [rsp+70h] [rbp-88h] BYREF
  __int64 v42; // [rsp+80h] [rbp-78h]
  void *v43; // [rsp+88h] [rbp-70h]
  __int64 v44; // [rsp+90h] [rbp-68h]
  __int64 v45; // [rsp+98h] [rbp-60h]
  _QWORD v46[2]; // [rsp+A0h] [rbp-58h] BYREF
  PSID Sid; // [rsp+B0h] [rbp-48h]
  bool DestinationSidLength; // [rsp+108h] [rbp+10h]
  ULONG DestinationSidLengtha; // [rsp+108h] [rbp+10h]
  char v50; // [rsp+110h] [rbp+18h]

  if ( (_DWORD)a2 == 1 )
  {
    v15 = a13;
    v16 = a12;
    v17 = a11;
    v18 = a10;
    result = LsapDbLookupWellKnownNames(a1, a2, a4, a5, a10, a11, a12, a13);
    v21 = result;
    if ( (int)result < 0 )
      return (unsigned int)v21;
    if ( *a12 == a1 )
      return result;
    result = LsapDbLookupNamesUsingSidNameMappingCache(a1, v20, a4, a5, a10, a11, a12, a13);
    v21 = result;
    if ( (int)result < 0 )
      return (unsigned int)v21;
    if ( *a12 == a1 )
      return result;
  }
  else
  {
    if ( (_DWORD)a2 != 2 )
      return 0;
    v15 = a13;
    v16 = a12;
    v17 = a11;
    v18 = a10;
  }
  v21 = 0;
  for ( i = 0; i < a1; ++i )
  {
    v23 = 24LL * i;
    v24 = *((_QWORD *)v17 + 1);
    v45 = v23;
    if ( *(_DWORD *)(v23 + v24 + 16) != -1 )
      continue;
    if ( *(_DWORD *)(v23 + v24) != 8 )
      continue;
    v25 = 16LL * i;
    if ( *(_WORD *)((char *)a4 + v25) )
      continue;
    v26 = (struct _UNICODE_STRING *)((char *)a5 + v25);
    *(_OWORD *)Src = 0;
    v21 = -1073741709;
    v27 = *((_QWORD *)a6 + 1);
    v28 = (void *)*((_QWORD *)a6 + 2);
    Src[1] = *(void **)a6;
    v46[0] = Src[1];
    Length = v26->Length;
    v42 = v27;
    v46[1] = v27;
    p_Buffer = &v26->Buffer;
    DomainName1 = v26;
    v44 = 0;
    v43 = v28;
    Sid = v28;
    pName2 = (const void **)&v26->Buffer;
    if ( v26->MaximumLength > (unsigned __int16)Length )
    {
      pName1 = *p_Buffer;
      if ( !(*p_Buffer)[Length >> 1] )
      {
        v50 = 0;
        goto LABEL_17;
      }
    }
    else
    {
      pName2 = (const void **)&v26->Buffer;
    }
    v31 = (WCHAR *)LocalAlloc(0x40u, Length + 2);
    pName1 = v31;
    if ( !v31 )
      goto LABEL_36;
    v50 = 1;
    memcpy_0(v31, *pName2, DomainName1->Length);
    pName1[(unsigned __int64)DomainName1->Length >> 1] = 0;
LABEL_17:
    DestinationSidLength = 0;
    v36 = 0;
    pName2a = (WCHAR *)LocalAlloc(0x40u, 2u);
    if ( pName2a )
    {
      v36 = 1;
      memcpy_0(pName2a, Src[0], 0);
      *pName2a = 0;
      v32 = 0;
    }
    else
    {
      v32 = -1073741801;
    }
    if ( v32 >= 0 )
      DestinationSidLength = RtlEqualDomainName(DomainName1, (PUNICODE_STRING)&Src[1])
                          || DnsNameCompare_W(pName1, pName2a);
    if ( v50 )
      LocalFree(pName1);
    if ( v36 )
      LocalFree(pName2a);
    if ( DestinationSidLength )
    {
      v21 = LsapDbLookupAddListReferencedDomains(v18, v46, *((_QWORD *)v17 + 1) + v45 + 16);
      if ( v21 >= 0 )
      {
        *(_DWORD *)(*((_QWORD *)v17 + 1) + 24LL * i) = 3;
        DestinationSidLengtha = RtlLengthSid(Sid);
        *(_QWORD *)(*((_QWORD *)v17 + 1) + 24LL * i + 8) = LocalAlloc(0x40u, DestinationSidLengtha);
        v33 = *(void **)(*((_QWORD *)v17 + 1) + 24LL * i + 8);
        if ( v33 )
        {
          RtlCopySid(DestinationSidLengtha, v33, Sid);
          ++*v16;
          --*v15;
          v21 = 0;
          continue;
        }
        v21 = -1073741801;
      }
    }
LABEL_36:
    if ( v21 != -1073741709 )
      return (unsigned int)v21;
    v21 = LsapDbLookupIsolatedDomainNameEx(i, DomainName1, a7, v18, v17, v16, v15);
    if ( v21 < 0 )
    {
      v34 = (struct _UNICODE_STRING *)a8;
      v21 = 0;
      if ( *((_QWORD *)a8 + 4) )
      {
        if ( LsapProductType == NtProductLanManNt )
        {
          v21 = LsapDbLookupIsolatedDomainName(i, (struct _LSAPR_UNICODE_STRING *)DomainName1, a9, v18, v17, v16, v15);
          if ( v21 >= 0 )
            continue;
          v34 = (struct _UNICODE_STRING *)a8;
        }
        v21 = 0;
        if ( !RtlEqualDomainName(v34 + 1, (PUNICODE_STRING)a7 + 1) )
        {
          v35 = LsapDbLookupIsolatedDomainNameEx(i, DomainName1, a8, v18, v17, v16, v15);
          v21 = v35;
          if ( v35 < 0 )
          {
            if ( v35 != -1073741709 )
              return (unsigned int)v21;
            v21 = 0;
          }
        }
      }
    }
  }
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x1800388a0  mov     [rsp+arg_0], rbx
0x1800388a5  mov     [rsp+arg_10], r8
0x1800388aa  push    rbp
0x1800388ab  push    rsi
0x1800388ac  push    rdi
0x1800388ad  push    r12
0x1800388af  push    r13
0x1800388b1  push    r14
0x1800388b3  push    r15
0x1800388b5  sub     rsp, 0C0h
0x1800388bc  mov     r14, r9
0x1800388bf  mov     edi, ecx
0x1800388c1  cmp     edx, 1
0x1800388c4  jnz     loc_180038DCF
0x1800388ca  mov     r15, [rsp+0F8h+arg_60]
0x1800388d2  mov     r8, r14; struct _LSAPR_UNICODE_STRING *
0x1800388d5  mov     rsi, [rsp+0F8h+arg_58]
0x1800388dd  mov     rbp, [rsp+0F8h+arg_50]
0x1800388e5  mov     r12, [rsp+0F8h+arg_20]
0x1800388ed  mov     r13, [rsp+0F8h+arg_48]
0x1800388f5  mov     r9, r12; struct _LSAPR_UNICODE_STRING *
0x1800388f8  mov     [rsp+0F8h+var_C0], r15; unsigned int *
0x1800388fd  mov     [rsp+0F8h+var_C8], rsi; unsigned int *
0x180038902  mov     [rsp+0F8h+var_D0], rbp; struct _LSAPR_TRANSLATED_SIDS_EX2 *
0x180038907  mov     [rsp+0F8h+var_D8], r13; struct _LSAPR_REFERENCED_DOMAIN_LIST *
0x18003890c  call    ?LsapDbLookupWellKnownNames@@YAJKPEAU_LSAPR_UNICODE_STRING@@00PEAU_LSAPR_REFERENCED_DOMAIN_LIST@@PEAU_LSAPR_TRANSLATED_SIDS_EX2@@PEAK3@Z; LsapDbLookupWellKnownNames(ulong,_LSAPR_UNICODE_STRING *,_LSAPR_UNICODE_STRING *,_LSAPR_UNICODE_STRING *,_LSAPR_REFERENCED_DOMAIN_LIST *,_LSAPR_TRANSLATED_SIDS_EX2 *,ulong *,ulong *)
0x180038911  mov     ebx, eax
0x180038913  test    eax, eax
0x180038915  js      loc_18003899E
0x18003891b  cmp     [rsi], edi
0x18003891d  jz      loc_1800389A0
0x180038923  mov     [rsp+0F8h+var_C0], r15; unsigned int *
0x180038928  mov     r9, r12; struct _LSAPR_UNICODE_STRING *
0x18003892b  mov     [rsp+0F8h+var_C8], rsi; unsigned int *
0x180038930  mov     r8, r14; struct _LSAPR_UNICODE_STRING *
0x180038933  mov     [rsp+0F8h+var_D0], rbp; struct _LSAPR_TRANSLATED_SIDS_EX2 *
0x180038938  mov     ecx, edi; unsigned int
0x18003893a  mov     [rsp+0F8h+var_D8], r13; struct _LSAPR_REFERENCED_DOMAIN_LIST *
0x18003893f  call    ?LsapDbLookupNamesUsingSidNameMappingCache@@YAJKPEAU_LSAPR_UNICODE_STRING@@00PEAU_LSAPR_REFERENCED_DOMAIN_LIST@@PEAU_LSAPR_TRANSLATED_SIDS_EX2@@PEAK3@Z; LsapDbLookupNamesUsingSidNameMappingCache(ulong,_LSAPR_UNICODE_STRING *,_LSAPR_UNICODE_STRING *,_LSAPR_UNICODE_STRING *,_LSAPR_REFERENCED_DOMAIN_LIST *,_LSAPR_TRANSLATED_SIDS_EX2 *,ulong *,ulong *)
0x180038944  mov     ebx, eax
0x180038946  test    eax, eax
0x180038948  js      short loc_18003899E
0x18003894a  cmp     [rsi], edi
0x18003894c  jz      short loc_1800389A0
0x18003894e  xor     r8d, r8d
0x180038951  mov     ebx, r8d
0x180038954  mov     r12d, r8d
0x180038957  test    edi, edi
0x180038959  jz      short loc_18003899E
0x18003895b  nop     dword ptr [rax+rax+00h]
0x180038960  mov     ecx, r12d
0x180038963  lea     rax, [rcx+rcx*2]
0x180038967  lea     rdx, ds:0[rax*8]
0x18003896f  mov     rax, [rbp+8]
0x180038973  mov     [rsp+0F8h+var_60], rdx
0x18003897b  cmp     dword ptr [rdx+rax+10h], 0FFFFFFFFh
0x180038980  jnz     short loc_180038996
0x180038982  cmp     dword ptr [rdx+rax], 8
0x180038986  jnz     short loc_180038996
0x180038988  mov     eax, ecx
0x18003898a  shl     rax, 4
0x18003898e  cmp     word ptr [rax+r14], 0
0x180038994  jz      short loc_1800389BC
0x180038996  inc     r12d
0x180038999  cmp     r12d, edi
0x18003899c  jb      short loc_180038960
0x18003899e  mov     eax, ebx
0x1800389a0  mov     rbx, [rsp+0F8h+arg_0]
0x1800389a8  add     rsp, 0C0h
0x1800389af  pop     r15
0x1800389b1  pop     r14
0x1800389b3  pop     r13
0x1800389b5  pop     r12
0x1800389b7  pop     rdi
0x1800389b8  pop     rsi
0x1800389b9  pop     rbp
0x1800389ba  retn
0x1800389bc  mov     rcx, [rsp+0F8h+arg_28]
0x1800389c4  xorps   xmm0, xmm0
0x1800389c7  mov     r10, [rsp+0F8h+arg_20]
0x1800389cf  mov     r9, r8
0x1800389d2  add     r10, rax
0x1800389d5  mov     [rsp+0F8h+var_90], r8
0x1800389da  movdqu  xmmword ptr [rsp+0F8h+Src], xmm0
0x1800389e0  mov     rdx, [rcx]
0x1800389e3  mov     ebx, 0C0000073h
0x1800389e8  mov     rax, [rcx+8]
0x1800389ec  mov     rcx, [rcx+10h]
0x1800389f0  mov     [rsp+0F8h+Src+8], rdx
0x1800389f5  mov     [rsp+0F8h+var_58], rdx
0x1800389fd  movzx   edx, word ptr [r10]
0x180038a01  mov     [rsp+0F8h+var_78], rax
0x180038a09  mov     [rsp+0F8h+var_50], rax
0x180038a11  lea     rax, [r10+8]
0x180038a15  mov     [rsp+0F8h+DomainName1], r10
0x180038a1a  mov     [rsp+0F8h+var_68], r8
0x180038a22  mov     [rsp+0F8h+var_70], rcx
0x180038a2a  mov     [rsp+0F8h+Sid], rcx
0x180038a32  mov     [rsp+0F8h+pName2], rax
0x180038a37  cmp     [r10+2], dx
0x180038a3c  ja      loc_180038C5B
0x180038a42  mov     [rsp+0F8h+pName2], rax
0x180038a47  add     rdx, 2; uBytes
0x180038a4b  mov     ecx, 40h ; '@'; uFlags
0x180038a50  call    cs:__imp_LocalAlloc
0x180038a57  nop     dword ptr [rax+rax+00h]
0x180038a5c  mov     [rsp+0F8h+pName1], rax
0x180038a61  test    rax, rax
0x180038a64  jz      loc_180038CB1
0x180038a6a  mov     rcx, [rsp+0F8h+DomainName1]
0x180038a6f  mov     rdx, [rsp+0F8h+pName2]
0x180038a74  mov     byte ptr [rsp+0F8h+arg_10], 1
0x180038a7c  movzx   r8d, word ptr [rcx]; Size
0x180038a80  mov     rcx, rax; void *
0x180038a83  mov     rdx, [rdx]; Src
0x180038a86  call    memcpy_0
0x180038a8b  mov     rax, [rsp+0F8h+DomainName1]
0x180038a90  movzx   ecx, word ptr [rax]
0x180038a93  mov     rax, [rsp+0F8h+pName1]
0x180038a98  shr     rcx, 1
0x180038a9b  xor     r8d, r8d
0x180038a9e  mov     [rax+rcx*2], r8w
0x180038aa3  mov     r9, [rsp+0F8h+var_90]
0x180038aa8  movzx   edx, r9w
0x180038aac  mov     byte ptr [rsp+0F8h+DestinationSidLength], 0
0x180038ab4  mov     [rsp+0F8h+var_A0], r8d
0x180038ab9  mov     [rsp+0F8h+var_B8], 0
0x180038abe  cmp     word ptr [rsp+0F8h+var_90+2], dx
0x180038ac3  ja      loc_180038C81
0x180038ac9  add     rdx, 2; uBytes
0x180038acd  mov     ecx, 40h ; '@'; uFlags
0x180038ad2  call    cs:__imp_LocalAlloc
0x180038ad9  nop     dword ptr [rax+rax+00h]
0x180038ade  mov     [rsp+0F8h+pName2], rax
0x180038ae3  mov     rcx, rax; void *
0x180038ae6  test    rax, rax
0x180038ae9  jz      loc_180038DC5
0x180038aef  movzx   r8d, word ptr [rsp+0F8h+var_90]; Size
0x180038af5  mov     rdx, [rsp+0F8h+Src]; Src
0x180038afa  mov     [rsp+0F8h+var_B8], 1
0x180038aff  call    memcpy_0
0x180038b04  movzx   eax, word ptr [rsp+0F8h+var_90]
0x180038b09  mov     rcx, [rsp+0F8h+pName2]
0x180038b0e  shr     rax, 1
0x180038b11  xor     edx, edx
0x180038b13  mov     [rcx+rax*2], dx
0x180038b17  mov     eax, [rsp+0F8h+var_A0]
0x180038b1b  test    eax, eax
0x180038b1d  js      short loc_180038B62
0x180038b1f  mov     rcx, [rsp+0F8h+DomainName1]; DomainName1
0x180038b24  lea     rdx, [rsp+0F8h+Src+8]; DomainName2
0x180038b29  call    cs:__imp_RtlEqualDomainName
0x180038b30  nop     dword ptr [rax+rax+00h]
0x180038b35  test    al, al
0x180038b37  jnz     loc_180038CA4
0x180038b3d  mov     rdx, [rsp+0F8h+pName2]; pName2
0x180038b42  mov     rcx, [rsp+0F8h+pName1]; pName1
0x180038b47  call    cs:__imp_DnsNameCompare_W
0x180038b4e  nop     dword ptr [rax+rax+00h]
0x180038b53  test    eax, eax
0x180038b55  jnz     loc_180038CA4
0x180038b5b  mov     byte ptr [rsp+0F8h+DestinationSidLength], al
0x180038b62  cmp     byte ptr [rsp+0F8h+arg_10], 0
0x180038b6a  jz      short loc_180038B7D
0x180038b6c  mov     rcx, [rsp+0F8h+pName1]; hMem
0x180038b71  call    cs:__imp_LocalFree
0x180038b78  nop     dword ptr [rax+rax+00h]
0x180038b7d  cmp     [rsp+0F8h+var_B8], 0
0x180038b82  jz      short loc_180038B95
0x180038b84  mov     rcx, [rsp+0F8h+pName2]; hMem
0x180038b89  call    cs:__imp_LocalFree
0x180038b90  nop     dword ptr [rax+rax+00h]
0x180038b95  cmp     byte ptr [rsp+0F8h+DestinationSidLength], 0
0x180038b9d  jz      loc_180038CB1
0x180038ba3  mov     r8, [rsp+0F8h+var_60]
0x180038bab  lea     rdx, [rsp+0F8h+var_58]
0x180038bb3  add     r8, 10h
0x180038bb7  mov     rcx, r13
0x180038bba  add     r8, [rbp+8]
0x180038bbe  call    LsapDbLookupAddListReferencedDomains
0x180038bc3  mov     ebx, eax
0x180038bc5  test    eax, eax
0x180038bc7  js      loc_180038CB1
0x180038bcd  mov     rax, [rbp+8]
0x180038bd1  mov     ebx, r12d
0x180038bd4  lea     rcx, [rbx+rbx*2]
0x180038bd8  mov     dword ptr [rax+rcx*8], 3
0x180038bdf  mov     rcx, [rsp+0F8h+Sid]; Sid
0x180038be7  call    cs:__imp_RtlLengthSid
0x180038bee  nop     dword ptr [rax+rax+00h]
0x180038bf3  mov     edx, eax; uBytes
0x180038bf5  mov     ecx, 40h ; '@'; uFlags
0x180038bfa  mov     [rsp+0F8h+DestinationSidLength], eax
0x180038c01  call    cs:__imp_LocalAlloc
0x180038c08  nop     dword ptr [rax+rax+00h]
0x180038c0d  mov     rcx, [rbp+8]
0x180038c11  lea     rdx, [rbx+rbx*2]
0x180038c15  mov     [rcx+rdx*8+8], rax
0x180038c1a  lea     rdx, [rbx+rbx*2]
0x180038c1e  mov     rcx, [rbp+8]
0x180038c22  mov     rdx, [rcx+rdx*8+8]; DestinationSid
0x180038c27  test    rdx, rdx
0x180038c2a  jz      loc_180038DFC
0x180038c30  mov     r8, [rsp+0F8h+Sid]; SourceSid
0x180038c38  mov     ecx, [rsp+0F8h+DestinationSidLength]; DestinationSidLength
0x180038c3f  call    cs:__imp_RtlCopySid
0x180038c46  nop     dword ptr [rax+rax+00h]
0x180038c4b  inc     dword ptr [rsi]
0x180038c4d  dec     dword ptr [r15]
0x180038c50  xor     r8d, r8d
0x180038c53  mov     ebx, r8d
0x180038c56  jmp     loc_180038996
0x180038c5b  mov     rcx, [rax]
0x180038c5e  mov     rax, rdx
0x180038c61  shr     rax, 1
0x180038c64  mov     [rsp+0F8h+pName1], rcx
0x180038c69  cmp     word ptr [rcx+rax*2], 0
0x180038c6e  jnz     loc_180038A47
0x180038c74  mov     byte ptr [rsp+0F8h+arg_10], 0
0x180038c7c  jmp     loc_180038AA8
0x180038c81  mov     rcx, [rsp+0F8h+Src]
0x180038c86  mov     rax, rdx
0x180038c89  shr     rax, 1
0x180038c8c  mov     [rsp+0F8h+pName2], rcx
0x180038c91  cmp     word ptr [rcx+rax*2], 0
0x180038c96  jnz     loc_180038AC9
0x180038c9c  mov     eax, r8d
0x180038c9f  jmp     loc_180038B1B
0x180038ca4  mov     byte ptr [rsp+0F8h+DestinationSidLength], 1
0x180038cac  jmp     loc_180038B62
0x180038cb1  test    ebx, ebx
0x180038cb3  js      short loc_180038CBD
0x180038cb5  xor     r8d, r8d
0x180038cb8  jmp     loc_180038996
0x180038cbd  cmp     ebx, 0C0000073h
0x180038cc3  jnz     loc_18003899E
0x180038cc9  mov     r8, [rsp+0F8h+arg_30]; struct _LSAPR_TRUST_INFORMATION_EX *
0x180038cd1  mov     r9, r13; struct _LSAPR_REFERENCED_DOMAIN_LIST *
0x180038cd4  mov     rdx, [rsp+0F8h+DomainName1]; struct _LSAPR_UNICODE_STRING *
0x180038cd9  mov     ecx, r12d; unsigned int
0x180038cdc  mov     [rsp+0F8h+var_C8], r15; unsigned int *
0x180038ce1  mov     [rsp+0F8h+var_D0], rsi; unsigned int *
0x180038ce6  mov     [rsp+0F8h+var_D8], rbp; struct _LSAPR_TRANSLATED_SIDS_EX2 *
0x180038ceb  call    ?LsapDbLookupIsolatedDomainNameEx@@YAJKPEAU_LSAPR_UNICODE_STRING@@PEAU_LSAPR_TRUST_INFORMATION_EX@@PEAU_LSAPR_REFERENCED_DOMAIN_LIST@@PEAU_LSAPR_TRANSLATED_SIDS_EX2@@PEAK4@Z; LsapDbLookupIsolatedDomainNameEx(ulong,_LSAPR_UNICODE_STRING *,_LSAPR_TRUST_INFORMATION_EX *,_LSAPR_REFERENCED_DOMAIN_LIST *,_LSAPR_TRANSLATED_SIDS_EX2 *,ulong *,ulong *)
0x180038cf0  xor     r8d, r8d
0x180038cf3  mov     ebx, eax
0x180038cf5  test    eax, eax
0x180038cf7  jns     loc_180038996
0x180038cfd  mov     rax, [rsp+0F8h+arg_38]
0x180038d05  mov     ebx, r8d
0x180038d08  cmp     [rax+20h], rbx
0x180038d0c  jz      loc_180038996
0x180038d12  cmp     cs:LsapProductType, 2
0x180038d19  jnz     short loc_180038D57
0x180038d1b  mov     r8, [rsp+0F8h+arg_40]; struct _LSAPR_TRUST_INFORMATION *
0x180038d23  mov     r9, r13; struct _LSAPR_REFERENCED_DOMAIN_LIST *
0x180038d26  mov     rdx, [rsp+0F8h+DomainName1]; struct _LSAPR_UNICODE_STRING *
0x180038d2b  mov     ecx, r12d; unsigned int
0x180038d2e  mov     [rsp+0F8h+var_C8], r15; unsigned int *
0x180038d33  mov     [rsp+0F8h+var_D0], rsi; unsigned int *
0x180038d38  mov     [rsp+0F8h+var_D8], rbp; struct _LSAPR_TRANSLATED_SIDS_EX2 *
0x180038d3d  call    ?LsapDbLookupIsolatedDomainName@@YAJKPEAU_LSAPR_UNICODE_STRING@@PEAU_LSAPR_TRUST_INFORMATION@@PEAU_LSAPR_REFERENCED_DOMAIN_LIST@@PEAU_LSAPR_TRANSLATED_SIDS_EX2@@PEAK4@Z; LsapDbLookupIsolatedDomainName(ulong,_LSAPR_UNICODE_STRING *,_LSAPR_TRUST_INFORMATION *,_LSAPR_REFERENCED_DOMAIN_LIST *,_LSAPR_TRANSLATED_SIDS_EX2 *,ulong *,ulong *)
0x180038d42  xor     r8d, r8d
0x180038d45  mov     ebx, eax
0x180038d47  test    eax, eax
0x180038d49  jns     loc_180038996
0x180038d4f  mov     rax, [rsp+0F8h+arg_38]
0x180038d57  mov     rdx, [rsp+0F8h+arg_30]
0x180038d5f  lea     rcx, [rax+10h]; DomainName1
0x180038d63  add     rdx, 10h; DomainName2
0x180038d67  mov     ebx, r8d
0x180038d6a  call    cs:__imp_RtlEqualDomainName
0x180038d71  nop     dword ptr [rax+rax+00h]
0x180038d76  test    al, al
0x180038d78  jnz     loc_180038CB5
0x180038d7e  mov     r8, [rsp+0F8h+arg_38]; struct _LSAPR_TRUST_INFORMATION_EX *
0x180038d86  mov     r9, r13; struct _LSAPR_REFERENCED_DOMAIN_LIST *
0x180038d89  mov     rdx, [rsp+0F8h+DomainName1]; struct _LSAPR_UNICODE_STRING *
0x180038d8e  mov     ecx, r12d; unsigned int
0x180038d91  mov     [rsp+0F8h+var_C8], r15; unsigned int *
0x180038d96  mov     [rsp+0F8h+var_D0], rsi; unsigned int *
0x180038d9b  mov     [rsp+0F8h+var_D8], rbp; struct _LSAPR_TRANSLATED_SIDS_EX2 *
0x180038da0  call    ?LsapDbLookupIsolatedDomainNameEx@@YAJKPEAU_LSAPR_UNICODE_STRING@@PEAU_LSAPR_TRUST_INFORMATION_EX@@PEAU_LSAPR_REFERENCED_DOMAIN_LIST@@PEAU_LSAPR_TRANSLATED_SIDS_EX2@@PEAK4@Z; LsapDbLookupIsolatedDomainNameEx(ulong,_LSAPR_UNICODE_STRING *,_LSAPR_TRUST_INFORMATION_EX *,_LSAPR_REFERENCED_DOMAIN_LIST *,_LSAPR_TRANSLATED_SIDS_EX2 *,ulong *,ulong *)
0x180038da5  mov     ebx, eax
0x180038da7  test    eax, eax
0x180038da9  jns     loc_180038CB5
0x180038daf  cmp     eax, 0C0000073h
0x180038db4  jnz     loc_18003899E
0x180038dba  xor     r8d, r8d
0x180038dbd  mov     ebx, r8d
0x180038dc0  jmp     loc_180038996
0x180038dc5  mov     eax, 0C0000017h
0x180038dca  jmp     loc_180038B1B
0x180038dcf  xor     r8d, r8d
0x180038dd2  cmp     edx, 2
0x180038dd5  jnz     short loc_180038E06
0x180038dd7  mov     r15, [rsp+0F8h+arg_60]
0x180038ddf  mov     rsi, [rsp+0F8h+arg_58]
0x180038de7  mov     rbp, [rsp+0F8h+arg_50]
0x180038def  mov     r13, [rsp+0F8h+arg_48]
  ... truncated ...
```
