# LsaDbpLookupNamesAsDomainNames(ulong,ulong,_LSAPR_UNICODE_STRING *,_LSAPR_UNICODE_STRING *,_LSAPR_UNICODE_STRING *,_LSAPR_REFERENCED_DOMAIN_LIST *,_LSAPR_TRANSLATED_SIDS_EX2 *,ulong *)

- ea: `0x18001c938`
- end: `0x18001cc02`
- name: `?LsaDbpLookupNamesAsDomainNames@@YAJKKPEAU_LSAPR_UNICODE_STRING@@00PEAU_LSAPR_REFERENCED_DOMAIN_LIST@@PEAU_LSAPR_TRANSLATED_SIDS_EX2@@PEAK@Z`
- size: `714`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, struct _LSAPR_UNICODE_STRING *, struct _LSAPR_UNICODE_STRING *, struct _LSAPR_UNICODE_STRING *, struct _LSAPR_REFERENCED_DOMAIN_LIST *, struct _LSAPR_TRANSLATED_SIDS_EX2 *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18001c670`

## callees

- `0x18001a6d8`
- `0x18001a894`
- `0x18001c938`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cb8b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cb9d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cbd8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cbe6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cb8b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cb9d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cbd8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cbe6`
- `LSASRV!LsapDbLookupListReferencedDomains` at `0x18001cad3`
- `LSASRV!LsapDbLookupListReferencedDomains` at `0x18001cad3`
- `LSASRV!LsapDbLookupAddListReferencedDomains` at `0x18001cb06`
- `LSASRV!LsapDbLookupAddListReferencedDomains` at `0x18001cb06`
- `LSASRV!LsapRpcCopySid` at `0x18001cb49`
- `LSASRV!LsapRpcCopySid` at `0x18001cb49`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x18001cb78`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x18001cbc9`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x18001cb78`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x18001cbc9`

## pseudocode

```c
__int64 __fastcall LsaDbpLookupNamesAsDomainNames(
        __int64 a1,
        unsigned int a2,
        struct _LSAPR_UNICODE_STRING *a3,
        struct _LSAPR_UNICODE_STRING *a4,
        struct _LSAPR_UNICODE_STRING *a5,
        struct _LSAPR_REFERENCED_DOMAIN_LIST *a6,
        struct _LSAPR_TRANSLATED_SIDS_EX2 *a7,
        unsigned int *a8)
{
  PSID Sid; // rdi
  int v9; // ebx
  unsigned int v10; // r12d
  __int64 v11; // rax
  bool v12; // zf
  __int64 v13; // rax
  struct _UNICODE_STRING *v14; // r14
  int HasTransitiveTrust; // eax
  int HasDomainTrust; // eax
  int v17; // eax
  __int64 v18; // r14
  __int64 v19; // r9
  struct _LSAPR_TRANSLATED_SIDS_EX2 *v20; // r8
  struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *v22; // [rsp+38h] [rbp-71h] BYREF
  struct _LSA_TRUST_INFORMATION hMem; // [rsp+40h] [rbp-69h] BYREF
  __int128 v24; // [rsp+58h] [rbp-51h]
  LSA_UNICODE_STRING Name; // [rsp+68h] [rbp-41h]
  __int128 v26; // [rsp+78h] [rbp-31h]
  LSA_UNICODE_STRING v27; // [rsp+88h] [rbp-21h] BYREF
  __int64 v28; // [rsp+98h] [rbp-11h]
  unsigned int v29; // [rsp+F8h] [rbp+4Fh]
  struct _LSAPR_UNICODE_STRING *v31; // [rsp+108h] [rbp+5Fh] BYREF
  struct _LSAPR_UNICODE_STRING *v32; // [rsp+110h] [rbp+67h]

  v32 = a4;
  v31 = a3;
  v29 = a1;
  Sid = 0;
  LOBYTE(v31) = 0;
  v9 = 0;
  v10 = 0;
  hMem.Name = 0;
  if ( !a2 )
    goto LABEL_33;
  while ( 1 )
  {
    Sid = 0;
    v22 = 0;
    memset(&hMem, 0, sizeof(hMem));
    v11 = *((_QWORD *)a7 + 1);
    v24 = 0;
    v12 = *(_DWORD *)(v11 + 24LL * v10 + 16) == -1;
    Name = 0;
    v26 = 0;
    if ( v12 && *(_DWORD *)(v11 + 24LL * v10) == 8 )
    {
      v13 = 16LL * v10;
      if ( !*(_WORD *)((char *)a4 + v13) )
        break;
    }
LABEL_30:
    if ( ++v10 >= a2 )
      goto LABEL_31;
  }
  v14 = (struct _UNICODE_STRING *)((char *)a5 + v13);
  if ( (a1 & 2) != 0 )
  {
    HasTransitiveTrust = LsaDbpDomainHasTransitiveTrust((struct _UNICODE_STRING *)((char *)a5 + v13), 0, &hMem);
    Sid = hMem.Sid;
    v9 = HasTransitiveTrust;
    if ( HasTransitiveTrust >= 0 )
    {
      Name = hMem.Name;
      *(_QWORD *)&v26 = hMem.Sid;
      goto LABEL_17;
    }
    if ( HasTransitiveTrust != -1073741601 )
      goto LABEL_31;
    a1 = v29;
    v9 = 0;
  }
  if ( (a1 & 1) == 0 )
    goto LABEL_14;
  HasDomainTrust = LsaDbpDomainHasDomainTrust(3u, v14, 0, (unsigned __int8 *)&v31, &v22);
  v9 = HasDomainTrust;
  if ( HasDomainTrust < 0 )
  {
    if ( HasDomainTrust != -1073741601 )
      goto LABEL_31;
    v9 = 0;
    a1 = v29;
LABEL_14:
    if ( (a1 & 8) == 0 )
    {
LABEL_23:
      if ( (_BYTE)v31 )
      {
        LsapDbExpReleaseLockTrustedDomainList(a1);
        LOBYTE(v31) = 0;
      }
      if ( hMem.Name.Buffer )
      {
        LocalFree(hMem.Name.Buffer);
        hMem.Name.Buffer = 0;
      }
      if ( Sid )
      {
        LocalFree(Sid);
        Sid = 0;
      }
      a1 = v29;
      a4 = v32;
      goto LABEL_30;
    }
    v17 = LsaDbpDomainHasDomainTrust(4u, v14, 0, (unsigned __int8 *)&v31, &v22);
    v9 = v17;
    if ( v17 < 0 )
    {
      if ( v17 != -1073741601 )
        goto LABEL_31;
      v9 = 0;
      goto LABEL_23;
    }
  }
  Name = (LSA_UNICODE_STRING)*((_OWORD *)v22 + 2);
  *(_QWORD *)&v26 = *((_QWORD *)v22 + 6);
LABEL_17:
  LODWORD(v22) = 0;
  v18 = v26;
  if ( (unsigned __int8)LsapDbLookupListReferencedDomains(a6, v26, &v22)
    || (v27 = Name, v28 = v18, v9 = LsapDbLookupAddListReferencedDomains(a6, &v27, &v22), v9 >= 0) )
  {
    v20 = a7;
    *(_DWORD *)(*((_QWORD *)a7 + 1) + 24LL * v10) = 3;
    *(_DWORD *)(*((_QWORD *)v20 + 1) + 24LL * v10 + 16) = (_DWORD)v22;
    v9 = LsapRpcCopySid(0, *((_QWORD *)v20 + 1) + 8LL + 24LL * v10, v18, v19);
    if ( v9 >= 0 )
    {
      ++*a8;
      goto LABEL_23;
    }
  }
LABEL_31:
  if ( (_BYTE)v31 )
    LsapDbExpReleaseLockTrustedDomainList(a1);
LABEL_33:
  if ( hMem.Name.Buffer )
    LocalFree(hMem.Name.Buffer);
  if ( Sid )
    LocalFree(Sid);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001c938  mov     rax, rsp
0x18001c93b  mov     [rax+20h], r9
0x18001c93f  mov     [rax+18h], r8
0x18001c943  mov     [rax+10h], edx
0x18001c946  mov     [rax+8], ecx
0x18001c949  push    rbp
0x18001c94a  push    rbx
0x18001c94b  push    rsi
0x18001c94c  push    rdi
0x18001c94d  push    r12
0x18001c94f  push    r13
0x18001c951  push    r14
0x18001c953  push    r15
0x18001c955  lea     rbp, [rax-47h]
0x18001c959  sub     rsp, 0A8h
0x18001c960  xor     r14d, r14d
0x18001c963  xor     edi, edi
0x18001c965  mov     byte ptr [rbp+3Fh+arg_10], r14b
0x18001c969  xorps   xmm0, xmm0
0x18001c96c  mov     ebx, r14d
0x18001c96f  mov     r12d, r14d
0x18001c972  movups  xmmword ptr [rbp+3Fh+hMem], xmm0
0x18001c976  test    edx, edx
0x18001c978  jz      loc_18001CBCF
0x18001c97e  mov     rax, [rbp+3Fh+arg_30]
0x18001c982  xorps   xmm0, xmm0
0x18001c985  xor     edi, edi
0x18001c987  mov     r15d, r12d
0x18001c98a  mov     [rbp+3Fh+var_B0], r14
0x18001c98e  movups  xmmword ptr [rbp+3Fh+hMem], xmm0
0x18001c992  mov     rax, [rax+8]
0x18001c996  lea     r13, [r15+r15*2]
0x18001c99a  mov     [rbp+3Fh+var_98], rdi
0x18001c99e  movups  [rbp+3Fh+var_90], xmm0
0x18001c9a2  cmp     dword ptr [rax+r13*8+10h], 0FFFFFFFFh
0x18001c9a8  movups  [rbp+3Fh+var_80], xmm0
0x18001c9ac  movups  [rbp+3Fh+var_70], xmm0
0x18001c9b0  jnz     loc_18001CBB1
0x18001c9b6  cmp     dword ptr [rax+r13*8], 8
0x18001c9bb  jnz     loc_18001CBB1
0x18001c9c1  mov     eax, r15d
0x18001c9c4  shl     rax, 4
0x18001c9c8  cmp     [rax+r9], r14w
0x18001c9cd  jnz     loc_18001CBB1
0x18001c9d3  mov     rsi, r14
0x18001c9d6  mov     r14, [rbp+3Fh+arg_20]
0x18001c9da  add     r14, rax
0x18001c9dd  test    cl, 2
0x18001c9e0  jz      short loc_18001CA28
0x18001c9e2  lea     r8, [rbp+3Fh+hMem]; struct _LSA_TRUST_INFORMATION *
0x18001c9e6  xor     edx, edx; void *
0x18001c9e8  mov     rcx, r14; struct _UNICODE_STRING *
0x18001c9eb  call    ?LsaDbpDomainHasTransitiveTrust@@YAJPEAU_UNICODE_STRING@@PEAXPEAU_LSA_TRUST_INFORMATION@@@Z; LsaDbpDomainHasTransitiveTrust(_UNICODE_STRING *,void *,_LSA_TRUST_INFORMATION *)
0x18001c9f0  mov     rdi, [rbp+3Fh+var_98]
0x18001c9f4  mov     ebx, eax
0x18001c9f6  test    eax, eax
0x18001c9f8  js      short loc_18001CA16
0x18001c9fa  mov     rax, [rbp+3Fh+hMem]
0x18001c9fe  xor     r14d, r14d
0x18001ca01  mov     qword ptr [rbp+3Fh+var_80], rax
0x18001ca05  mov     rax, [rbp+3Fh+hMem+8]
0x18001ca09  mov     qword ptr [rbp+3Fh+var_80+8], rax
0x18001ca0d  mov     qword ptr [rbp+3Fh+var_70], rdi
0x18001ca11  jmp     loc_18001CABC
0x18001ca16  cmp     eax, 0C00000DFh
0x18001ca1b  jnz     loc_18001CBC0
0x18001ca21  mov     ecx, [rbp+3Fh+arg_0]
0x18001ca24  xor     ebx, ebx
0x18001ca26  xor     esi, esi
0x18001ca28  test    cl, 1
0x18001ca2b  jz      short loc_18001CA6E
0x18001ca2d  xor     r8d, r8d; void *
0x18001ca30  lea     rax, [rbp+3Fh+var_B0]
0x18001ca34  lea     r9, [rbp+3Fh+arg_10]; unsigned __int8 *
0x18001ca38  mov     [rsp+20h], rax; struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY **
0x18001ca3d  mov     rdx, r14; struct _UNICODE_STRING *
0x18001ca40  lea     ecx, [r8+3]; unsigned int
0x18001ca44  call    ?LsaDbpDomainHasDomainTrust@@YAJKPEAU_UNICODE_STRING@@PEAXPEAEPEAPEAU_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY@@@Z; LsaDbpDomainHasDomainTrust(ulong,_UNICODE_STRING *,void *,uchar *,_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY * *)
0x18001ca49  mov     ebx, eax
0x18001ca4b  test    eax, eax
0x18001ca4d  js      short loc_18001CA54
0x18001ca4f  xor     r14d, r14d
0x18001ca52  jmp     short loc_18001CAA0
0x18001ca54  cmp     eax, 0C00000DFh
0x18001ca59  jnz     loc_18001CBC0
0x18001ca5f  xor     ebx, ebx
0x18001ca61  test    rsi, rsi
0x18001ca64  jz      short loc_18001CA6B
0x18001ca66  xor     r14d, r14d
0x18001ca69  jmp     short loc_18001CAC0
0x18001ca6b  mov     ecx, [rbp+3Fh+arg_0]
0x18001ca6e  test    cl, 8
0x18001ca71  jz      loc_18001CB6F
0x18001ca77  xor     r8d, r8d; void *
0x18001ca7a  lea     rax, [rbp+3Fh+var_B0]
0x18001ca7e  lea     r9, [rbp+3Fh+arg_10]; unsigned __int8 *
0x18001ca82  mov     [rsp+20h], rax; struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY **
0x18001ca87  mov     rdx, r14; struct _UNICODE_STRING *
0x18001ca8a  lea     ecx, [r8+4]; unsigned int
0x18001ca8e  call    ?LsaDbpDomainHasDomainTrust@@YAJKPEAU_UNICODE_STRING@@PEAXPEAEPEAPEAU_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY@@@Z; LsaDbpDomainHasDomainTrust(ulong,_UNICODE_STRING *,void *,uchar *,_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY * *)
0x18001ca93  xor     r14d, r14d
0x18001ca96  mov     ebx, eax
0x18001ca98  test    eax, eax
0x18001ca9a  js      loc_18001CB63
0x18001caa0  mov     rcx, [rbp+3Fh+var_B0]
0x18001caa4  mov     rax, [rcx+20h]
0x18001caa8  mov     qword ptr [rbp+3Fh+var_80], rax
0x18001caac  mov     rax, [rcx+28h]
0x18001cab0  mov     qword ptr [rbp+3Fh+var_80+8], rax
0x18001cab4  mov     rax, [rcx+30h]
0x18001cab8  mov     qword ptr [rbp+3Fh+var_70], rax
0x18001cabc  lea     rsi, [rbp+3Fh+var_90]
0x18001cac0  mov     rcx, [rbp+3Fh+arg_28]
0x18001cac4  lea     r8, [rbp+3Fh+var_B0]
0x18001cac8  mov     dword ptr [rbp+3Fh+var_B0], r14d
0x18001cacc  mov     r14, [rsi+20h]
0x18001cad0  mov     rdx, r14
0x18001cad3  call    cs:__imp_LsapDbLookupListReferencedDomains
0x18001cad9  test    al, al
0x18001cadb  jnz     short loc_18001CB16
0x18001cadd  movups  xmm0, xmmword ptr [rsi+10h]
0x18001cae1  mov     rcx, [rbp+3Fh+arg_28]
0x18001cae5  lea     r8, [rbp+3Fh+var_B0]
0x18001cae9  mov     qword ptr [rbp+3Fh+var_60], 0
0x18001caf1  lea     rdx, [rbp+3Fh+var_60]
0x18001caf5  mov     qword ptr [rbp+3Fh+var_60+8], 0
0x18001cafd  movdqu  [rbp+3Fh+var_60], xmm0
0x18001cb02  mov     [rbp+3Fh+var_50], r14
0x18001cb06  call    cs:__imp_LsapDbLookupAddListReferencedDomains
0x18001cb0c  mov     ebx, eax
0x18001cb0e  test    eax, eax
0x18001cb10  js      loc_18001CBC0
0x18001cb16  mov     r8, [rbp+3Fh+arg_30]
0x18001cb1a  lea     rcx, [r15+r15*2]
0x18001cb1e  lea     rdx, [r15+r15*2]
0x18001cb22  mov     rax, [r8+8]
0x18001cb26  mov     dword ptr [rax+rcx*8], 3
0x18001cb2d  mov     rcx, [r8+8]
0x18001cb31  mov     eax, dword ptr [rbp+3Fh+var_B0]
0x18001cb34  mov     [rcx+rdx*8+10h], eax
0x18001cb38  xor     ecx, ecx
0x18001cb3a  mov     rdx, [r8+8]
0x18001cb3e  mov     r8, r14
0x18001cb41  add     rdx, 8
0x18001cb45  lea     rdx, [rdx+r13*8]
0x18001cb49  call    cs:__imp_LsapRpcCopySid
0x18001cb4f  xor     r14d, r14d
0x18001cb52  mov     ebx, eax
0x18001cb54  test    eax, eax
0x18001cb56  js      short loc_18001CBC3
0x18001cb58  mov     rax, [rbp+3Fh+arg_38]
0x18001cb5f  inc     dword ptr [rax]
0x18001cb61  jmp     short loc_18001CB72
0x18001cb63  cmp     eax, 0C00000DFh
0x18001cb68  jnz     short loc_18001CBC3
0x18001cb6a  mov     ebx, r14d
0x18001cb6d  jmp     short loc_18001CB72
0x18001cb6f  xor     r14d, r14d
0x18001cb72  cmp     byte ptr [rbp+3Fh+arg_10], r14b
0x18001cb76  jz      short loc_18001CB82
0x18001cb78  call    cs:__imp_LsapDbExpReleaseLockTrustedDomainList
0x18001cb7e  mov     byte ptr [rbp+3Fh+arg_10], r14b
0x18001cb82  mov     rcx, [rbp+3Fh+hMem+8]; hMem
0x18001cb86  test    rcx, rcx
0x18001cb89  jz      short loc_18001CB95
0x18001cb8b  call    cs:__imp_LocalFree
0x18001cb91  mov     [rbp+3Fh+hMem+8], r14
0x18001cb95  test    rdi, rdi
0x18001cb98  jz      short loc_18001CBA6
0x18001cb9a  mov     rcx, rdi; hMem
0x18001cb9d  call    cs:__imp_LocalFree
0x18001cba3  mov     rdi, r14
0x18001cba6  test    ebx, ebx
0x18001cba8  js      short loc_18001CBC3
0x18001cbaa  mov     ecx, [rbp+3Fh+arg_0]
0x18001cbad  mov     r9, [rbp+3Fh+arg_18]
0x18001cbb1  inc     r12d
0x18001cbb4  cmp     r12d, [rbp+3Fh+arg_8]
0x18001cbb8  jb      loc_18001C97E
0x18001cbbe  jmp     short loc_18001CBC3
0x18001cbc0  xor     r14d, r14d
0x18001cbc3  cmp     byte ptr [rbp+3Fh+arg_10], r14b
0x18001cbc7  jz      short loc_18001CBCF
0x18001cbc9  call    cs:__imp_LsapDbExpReleaseLockTrustedDomainList
0x18001cbcf  mov     rcx, [rbp+3Fh+hMem+8]; hMem
0x18001cbd3  test    rcx, rcx
0x18001cbd6  jz      short loc_18001CBDE
0x18001cbd8  call    cs:__imp_LocalFree
0x18001cbde  test    rdi, rdi
0x18001cbe1  jz      short loc_18001CBEC
0x18001cbe3  mov     rcx, rdi; hMem
0x18001cbe6  call    cs:__imp_LocalFree
0x18001cbec  mov     eax, ebx
0x18001cbee  add     rsp, 0A8h
0x18001cbf5  pop     r15
0x18001cbf7  pop     r14
0x18001cbf9  pop     r13
0x18001cbfb  pop     r12
0x18001cbfd  pop     rdi
0x18001cbfe  pop     rsi
0x18001cbff  pop     rbx
0x18001cc00  pop     rbp
0x18001cc01  retn
```
