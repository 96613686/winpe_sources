# LsaDbpLookupSidsInTrustedForests(ulong,_LSAPR_SID * *,_LSAPR_REFERENCED_DOMAIN_LIST *,_LSAPR_TRANSLATED_NAMES_EX *,ulong *,ulong *,long *)

- ea: `0x18001e968`
- end: `0x18001edeb`
- name: `?LsaDbpLookupSidsInTrustedForests@@YAJKPEAPEAU_LSAPR_SID@@PEAU_LSAPR_REFERENCED_DOMAIN_LIST@@PEAU_LSAPR_TRANSLATED_NAMES_EX@@PEAK3PEAJ@Z`
- size: `1155`
- prototype: `__int64 __usercall@<rax>(size_t Size@<rcx>, struct _LSAPR_SID **@<rdx>, struct _LSAPR_REFERENCED_DOMAIN_LIST *@<r8>, struct _LSAPR_TRANSLATED_NAMES_EX *@<r9>, unsigned int *, unsigned int *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001db90`

## callees

- `0x180001670`
- `0x180001fb8`
- `0x18001a6d8`
- `0x18001e968`
- `0x18001edf4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetWindowsAccountDomainSid` at `0x18001ea6a`
- `api-ms-win-security-base-l1-1-0!GetWindowsAccountDomainSid` at `0x18001ea6a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ea04`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001eac2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001eaec`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ea04`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001eac2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001eaec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ec8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ecb0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ed12`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ed2d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ed47`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ed52`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ed69`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ed92`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001eda2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001edb5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001edc3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ec8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ecb0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ed12`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ed2d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ed47`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ed52`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ed69`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ed92`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001eda2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001edb5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001edc3`
- `LSASRV!LsapDbLookupMergeDisjointReferencedDomains` at `0x18001ebc0`
- `LSASRV!LsapDbLookupMergeDisjointReferencedDomains` at `0x18001ebc0`
- `LSASRV!LsapRpcCopyUnicodeString` at `0x18001ec30`
- `LSASRV!LsapRpcCopyUnicodeString` at `0x18001ec30`

## pseudocode

```c
__int64 __fastcall LsaDbpLookupSidsInTrustedForests(
        size_t Size,
        struct _LSAPR_SID **a2,
        struct _LSAPR_REFERENCED_DOMAIN_LIST *a3,
        struct _LSAPR_TRANSLATED_NAMES_EX *a4,
        unsigned int *a5,
        unsigned int *a6,
        int *a7)
{
  size_t v8; // r14
  int v9; // ebx
  __int64 v10; // r15
  _QWORD *v11; // r12
  void *v12; // r14
  unsigned int v13; // edi
  int HasDomainTrust; // eax
  _DWORD *v15; // rdi
  struct _LSAPR_SID **v16; // r11
  _BYTE *v17; // r9
  unsigned int v18; // r8d
  struct _LSAPR_SID **v19; // r10
  unsigned int v20; // edx
  __int64 v21; // rcx
  int v22; // eax
  unsigned int v23; // r14d
  int v24; // r13d
  __int64 v25; // rdi
  int v26; // edx
  __int64 v27; // rsi
  struct _LSAPR_TRANSLATED_NAMES_EX *v28; // r9
  __int64 v29; // rcx
  struct _LSAPR_TRANSLATED_NAMES_EX *v30; // rdx
  __int64 v31; // rsi
  struct _LSAPR_REFERENCED_DOMAIN_LIST *v32; // r13
  _QWORD *v33; // rcx
  unsigned int i; // edi
  void *v35; // rcx
  void *v36; // rcx
  unsigned int j; // edi
  void *v38; // rcx
  unsigned __int8 v40[8]; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL v41; // [rsp+48h] [rbp-B8h]
  HLOCAL v42; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v43; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cbDomainSid; // [rsp+5Ch] [rbp-A4h] BYREF
  int v45; // [rsp+60h] [rbp-A0h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp-98h] BYREF
  struct _LSAPR_TRANSLATED_NAMES_EX *v47; // [rsp+70h] [rbp-90h]
  HLOCAL v48; // [rsp+78h] [rbp-88h]
  struct _LSAPR_SID **v49; // [rsp+80h] [rbp-80h]
  int *v50; // [rsp+88h] [rbp-78h]
  HLOCAL v51; // [rsp+90h] [rbp-70h]
  __int128 v52; // [rsp+98h] [rbp-68h] BYREF
  unsigned int *v53; // [rsp+A8h] [rbp-58h]
  struct _LSAPR_REFERENCED_DOMAIN_LIST *v54; // [rsp+B0h] [rbp-50h]
  unsigned int *v55; // [rsp+B8h] [rbp-48h]
  _BYTE pDomainSid[72]; // [rsp+C0h] [rbp-40h] BYREF

  v55 = a5;
  v8 = (unsigned int)Size;
  v9 = 0;
  v10 = 0;
  v47 = a4;
  v11 = 0;
  *a7 = 0;
  v54 = a3;
  v49 = a2;
  v53 = a6;
  v50 = a7;
  v45 = 0;
  v43 = 0;
  v42 = 0;
  hMem = 0;
  v52 = 0;
  v51 = 0;
  v48 = 0;
  v40[0] = 0;
  if ( !*a6 )
  {
    v12 = 0;
    goto LABEL_45;
  }
  v41 = LocalAlloc(0x40u, (unsigned int)Size);
  if ( !v41 )
  {
    v9 = -1073741670;
    v12 = 0;
    goto LABEL_45;
  }
  memset_0(v41, 0, v8);
  v13 = 0;
  if ( !(_DWORD)v8 )
    goto LABEL_27;
  do
  {
    if ( (*(_BYTE *)(32LL * v13 + *((_QWORD *)v47 + 1) + 28) & 2) == 0 )
      goto LABEL_10;
    cbDomainSid = 68;
    if ( GetWindowsAccountDomainSid(v49[v13], pDomainSid, &cbDomainSid) )
    {
      HasDomainTrust = LsaDbpDomainHasDomainTrust(1u, 0, pDomainSid, 0, 0);
      if ( HasDomainTrust >= 0 )
        goto LABEL_10;
      if ( HasDomainTrust != -1073741601 )
        goto LABEL_27;
    }
    v10 = (unsigned int)(v10 + 1);
    *((_BYTE *)v41 + v13) = 1;
LABEL_10:
    ++v13;
  }
  while ( v13 < (unsigned int)v8 );
  if ( !(_DWORD)v10 )
    goto LABEL_27;
  v48 = LocalAlloc(0x40u, 4 * v10);
  v15 = v48;
  if ( !v48 || (v51 = LocalAlloc(0x40u, 8 * v10), (v16 = (struct _LSAPR_SID **)v51) == 0) )
  {
    v9 = -1073741670;
    goto LABEL_27;
  }
  v17 = v41;
  v18 = 0;
  v19 = v49;
  v20 = 0;
  do
  {
    if ( v18 >= (unsigned int)v10 )
      break;
    if ( v17[v20] )
    {
      v21 = v18++;
      v16[v21] = v19[v20];
      v15[v21] = v20;
    }
    ++v20;
  }
  while ( v20 < (unsigned int)v8 );
  v43 = 0;
  LODWORD(v52) = 0;
  *((_QWORD *)&v52 + 1) = 0;
  v22 = LsaDbpLookupSidsInTrustedForestsWorker(
          v10,
          v16,
          (struct _LSAPR_REFERENCED_DOMAIN_LIST **)&v42,
          (struct _LSAPR_TRANSLATED_NAMES_EX *)&v52,
          v40,
          &v43,
          &v45);
  v11 = (_QWORD *)*((_QWORD *)&v52 + 1);
  v9 = v22;
  if ( v22 >= 0 )
  {
    v22 = v45;
    if ( v45 >= 0 )
      goto LABEL_29;
LABEL_26:
    *v50 = v22;
    goto LABEL_27;
  }
  if ( (unsigned int)(v22 + 1073741428) <= 1 || v22 == -1073741136 )
  {
    v9 = 0;
    goto LABEL_26;
  }
  if ( v22 != -1073741709 )
    goto LABEL_27;
LABEL_29:
  v9 = LsapDbLookupMergeDisjointReferencedDomains(a3, v42, &hMem, 1);
  if ( v9 < 0 )
    goto LABEL_27;
  v23 = 0;
  v24 = *(_DWORD *)a3;
  while ( 2 )
  {
    v25 = 4LL * v23;
    if ( LODWORD(v11[v25 + 3]) == -1 && LODWORD(v11[v25]) == 8 )
    {
LABEL_36:
      if ( ++v23 >= (unsigned int)v10 )
        goto LABEL_37;
      continue;
    }
    break;
  }
  v26 = v11[v25];
  v27 = *((unsigned int *)v48 + v23);
  if ( v26 == 8
    || (v28 = v47,
        v29 = 32LL * (unsigned int)v27,
        *(_DWORD *)(v29 + *((_QWORD *)v47 + 1)) = v26,
        v9 = LsapRpcCopyUnicodeString(0, v29 + *((_QWORD *)v28 + 1) + 8LL, &v11[v25 + 1]),
        v9 >= 0) )
  {
    v30 = v47;
    v31 = 32 * v27;
    *(_DWORD *)(*((_QWORD *)v47 + 1) + v31 + 24) = v24 + LODWORD(v11[v25 + 3]);
    *(_DWORD *)(*((_QWORD *)v30 + 1) + v31 + 28) = HIDWORD(v11[v25 + 3]);
    --*v53;
    goto LABEL_36;
  }
LABEL_37:
  v32 = v54;
  v33 = hMem;
  if ( hMem )
  {
    if ( *((_QWORD *)v54 + 1) )
    {
      LocalFree(*((HLOCAL *)v54 + 1));
      v33 = hMem;
      *((_QWORD *)v32 + 1) = 0;
    }
    *(_OWORD *)v32 = *(_OWORD *)v33;
    *((_QWORD *)v32 + 2) = v33[2];
    LocalFree(v33);
    hMem = 0;
  }
  if ( v9 >= 0 )
    *v55 += v43;
LABEL_27:
  v12 = v41;
LABEL_45:
  if ( v42 )
  {
    if ( !v40[0] && *((_QWORD *)v42 + 1) )
    {
      for ( i = 0; i < *(_DWORD *)v42; ++i )
      {
        v35 = *(void **)(*((_QWORD *)v42 + 1) + 24LL * i + 8);
        if ( v35 )
          LocalFree(v35);
        v36 = *(void **)(*((_QWORD *)v42 + 1) + 24LL * i + 16);
        if ( v36 )
          LocalFree(v36);
      }
      LocalFree(*((HLOCAL *)v42 + 1));
    }
    LocalFree(v42);
    v42 = 0;
  }
  if ( v51 )
    LocalFree(v51);
  if ( v11 )
  {
    if ( !v40[0] )
    {
      for ( j = 0; j < (unsigned int)v10; ++j )
      {
        v38 = (void *)v11[4 * j + 2];
        if ( v38 )
          LocalFree(v38);
      }
    }
    LocalFree(v11);
  }
  if ( v48 )
    LocalFree(v48);
  if ( v12 )
    LocalFree(v12);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001e968  push    rbp
0x18001e96a  push    rbx
0x18001e96b  push    rsi
0x18001e96c  push    rdi
0x18001e96d  push    r12
0x18001e96f  push    r13
0x18001e971  push    r14
0x18001e973  push    r15
0x18001e975  lea     rbp, [rsp-18h]
0x18001e97a  sub     rsp, 118h
0x18001e981  mov     rax, cs:__security_cookie
0x18001e988  xor     rax, rsp
0x18001e98b  mov     [rbp+50h+var_48], rax
0x18001e98f  mov     rax, [rbp+50h+arg_20]
0x18001e996  xor     esi, esi
0x18001e998  mov     [rbp+50h+var_98], rax
0x18001e99c  xorps   xmm0, xmm0
0x18001e99f  mov     rax, [rbp+50h+arg_30]
0x18001e9a6  mov     r13, r8
0x18001e9a9  mov     r14d, ecx
0x18001e9ac  mov     ebx, esi
0x18001e9ae  mov     rcx, [rbp+50h+arg_28]
0x18001e9b5  mov     r15d, esi
0x18001e9b8  mov     [rsp+150h+var_E0], r9
0x18001e9bd  mov     r12d, esi
0x18001e9c0  mov     [rax], esi
0x18001e9c2  mov     [rbp+50h+var_A0], r8
0x18001e9c6  mov     [rbp+50h+var_D0], rdx
0x18001e9ca  mov     [rbp+50h+var_A8], rcx
0x18001e9ce  mov     [rbp+50h+var_C8], rax
0x18001e9d2  mov     [rsp+150h+var_F0], esi
0x18001e9d6  mov     [rsp+150h+var_F8], esi
0x18001e9da  mov     [rsp+150h+var_100], rsi
0x18001e9df  mov     [rsp+150h+hMem], rsi
0x18001e9e4  movups  [rbp+50h+var_B8], xmm0
0x18001e9e8  mov     [rbp+50h+var_C0], rsi
0x18001e9ec  mov     [rsp+150h+var_D8], rsi
0x18001e9f1  mov     [rsp+150h+var_110], sil
0x18001e9f6  cmp     [rcx], esi
0x18001e9f8  jz      loc_18001ECD9
0x18001e9fe  mov     edx, r14d; uBytes
0x18001ea01  lea     ecx, [rsi+40h]; uFlags
0x18001ea04  call    cs:__imp_LocalAlloc
0x18001ea0a  mov     [rsp+150h+var_108], rax
0x18001ea0f  mov     rcx, rax; void *
0x18001ea12  test    rax, rax
0x18001ea15  jnz     short loc_18001EA24
0x18001ea17  mov     ebx, 0C000009Ah
0x18001ea1c  mov     r14, rax
0x18001ea1f  jmp     loc_18001ECDC
0x18001ea24  mov     r8, r14; Size
0x18001ea27  xor     edx, edx; Val
0x18001ea29  call    memset_0
0x18001ea2e  mov     edi, esi
0x18001ea30  test    r14d, r14d
0x18001ea33  jz      loc_18001EB9B
0x18001ea39  mov     rax, [rsp+150h+var_E0]
0x18001ea3e  mov     ecx, edi
0x18001ea40  shl     rcx, 5
0x18001ea44  mov     esi, edi
0x18001ea46  mov     rax, [rax+8]
0x18001ea4a  test    byte ptr [rcx+rax+1Ch], 2
0x18001ea4f  jz      short loc_18001EAA5
0x18001ea51  mov     rax, [rbp+50h+var_D0]
0x18001ea55  lea     r8, [rsp+150h+cbDomainSid]; cbDomainSid
0x18001ea5a  lea     rdx, [rbp+50h+pDomainSid]; pDomainSid
0x18001ea5e  mov     [rsp+150h+cbDomainSid], 44h ; 'D'
0x18001ea66  mov     rcx, [rax+rsi*8]; pSid
0x18001ea6a  call    cs:__imp_GetWindowsAccountDomainSid
0x18001ea70  test    eax, eax
0x18001ea72  jz      short loc_18001EA99
0x18001ea74  xor     edx, edx; struct _UNICODE_STRING *
0x18001ea76  mov     [rsp+150h+var_130], rbx; struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY **
0x18001ea7b  xor     r9d, r9d; unsigned __int8 *
0x18001ea7e  lea     r8, [rbp+50h+pDomainSid]; void *
0x18001ea82  lea     ecx, [rdx+1]; unsigned int
0x18001ea85  call    ?LsaDbpDomainHasDomainTrust@@YAJKPEAU_UNICODE_STRING@@PEAXPEAEPEAPEAU_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY@@@Z; LsaDbpDomainHasDomainTrust(ulong,_UNICODE_STRING *,void *,uchar *,_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY * *)
0x18001ea8a  test    eax, eax
0x18001ea8c  jns     short loc_18001EAA5
0x18001ea8e  cmp     eax, 0C00000DFh
0x18001ea93  jnz     loc_18001ECD2
0x18001ea99  mov     rax, [rsp+150h+var_108]
0x18001ea9e  inc     r15d
0x18001eaa1  mov     byte ptr [rsi+rax], 1
0x18001eaa5  inc     edi
0x18001eaa7  cmp     edi, r14d
0x18001eaaa  jb      short loc_18001EA39
0x18001eaac  xor     esi, esi
0x18001eaae  test    r15d, r15d
0x18001eab1  jz      loc_18001EB9B
0x18001eab7  lea     rdx, ds:0[r15*4]; uBytes
0x18001eabf  lea     ecx, [rsi+40h]; uFlags
0x18001eac2  call    cs:__imp_LocalAlloc
0x18001eac8  mov     [rsp+150h+var_D8], rax
0x18001eacd  mov     rdi, rax
0x18001ead0  test    rax, rax
0x18001ead3  jnz     short loc_18001EADF
0x18001ead5  mov     ebx, 0C000009Ah
0x18001eada  jmp     loc_18001EB9B
0x18001eadf  lea     rdx, ds:0[r15*8]; uBytes
0x18001eae7  mov     ecx, 40h ; '@'; uFlags
0x18001eaec  call    cs:__imp_LocalAlloc
0x18001eaf2  mov     [rbp+50h+var_C0], rax
0x18001eaf6  mov     r11, rax
0x18001eaf9  test    rax, rax
0x18001eafc  jz      short loc_18001EAD5
0x18001eafe  mov     r9, [rsp+150h+var_108]
0x18001eb03  mov     r8d, esi
0x18001eb06  mov     r10, [rbp+50h+var_D0]
0x18001eb0a  mov     edx, esi
0x18001eb0c  cmp     r8d, r15d
0x18001eb0f  jnb     short loc_18001EB31
0x18001eb11  mov     eax, edx
0x18001eb13  cmp     [rax+r9], sil
0x18001eb17  jz      short loc_18001EB2A
0x18001eb19  mov     rax, [r10+rax*8]
0x18001eb1d  mov     ecx, r8d
0x18001eb20  inc     r8d
0x18001eb23  mov     [r11+rcx*8], rax
0x18001eb27  mov     [rdi+rcx*4], edx
0x18001eb2a  inc     edx
0x18001eb2c  cmp     edx, r14d
0x18001eb2f  jb      short loc_18001EB0C
0x18001eb31  lea     rax, [rsp+150h+var_F0]
0x18001eb36  mov     [rsp+150h+var_F8], esi
0x18001eb3a  mov     [rsp+150h+var_120], rax; int *
0x18001eb3f  lea     r9, [rbp+50h+var_B8]; struct _LSAPR_TRANSLATED_NAMES_EX *
0x18001eb43  lea     rax, [rsp+150h+var_F8]
0x18001eb48  mov     dword ptr [rbp+50h+var_B8], esi
0x18001eb4b  mov     [rsp+150h+var_128], rax; unsigned int *
0x18001eb50  lea     r8, [rsp+150h+var_100]; struct _LSAPR_REFERENCED_DOMAIN_LIST **
0x18001eb55  lea     rax, [rsp+150h+var_110]
0x18001eb5a  mov     qword ptr [rbp+50h+var_B8+8], rsi
0x18001eb5e  mov     rdx, r11; struct _LSAPR_SID **
0x18001eb61  mov     [rsp+150h+var_130], rax; unsigned __int8 *
0x18001eb66  mov     ecx, r15d; unsigned int
0x18001eb69  call    ?LsaDbpLookupSidsInTrustedForestsWorker@@YAJKPEAPEAU_LSAPR_SID@@PEAPEAU_LSAPR_REFERENCED_DOMAIN_LIST@@PEAU_LSAPR_TRANSLATED_NAMES_EX@@PEAEPEAKPEAJ@Z; LsaDbpLookupSidsInTrustedForestsWorker(ulong,_LSAPR_SID * *,_LSAPR_REFERENCED_DOMAIN_LIST * *,_LSAPR_TRANSLATED_NAMES_EX *,uchar *,ulong *,long *)
0x18001eb6e  mov     r12, qword ptr [rbp+50h+var_B8+8]
0x18001eb72  mov     ebx, eax
0x18001eb74  test    eax, eax
0x18001eb76  jns     short loc_18001EBA5
0x18001eb78  lea     ecx, [rax+3FFFFE74h]
0x18001eb7e  cmp     ecx, 1
0x18001eb81  jbe     short loc_18001EB93
0x18001eb83  cmp     eax, 0C00002B0h
0x18001eb88  jz      short loc_18001EB93
0x18001eb8a  cmp     eax, 0C0000073h
0x18001eb8f  jnz     short loc_18001EB9B
0x18001eb91  jmp     short loc_18001EBAD
0x18001eb93  mov     ebx, esi
0x18001eb95  mov     rcx, [rbp+50h+var_C8]
0x18001eb99  mov     [rcx], eax
0x18001eb9b  mov     r14, [rsp+150h+var_108]
0x18001eba0  jmp     loc_18001ECDC
0x18001eba5  mov     eax, [rsp+150h+var_F0]
0x18001eba9  test    eax, eax
0x18001ebab  js      short loc_18001EB95
0x18001ebad  mov     rdx, [rsp+150h+var_100]
0x18001ebb2  lea     r8, [rsp+150h+hMem]
0x18001ebb7  mov     r9d, 1
0x18001ebbd  mov     rcx, r13
0x18001ebc0  call    cs:__imp_LsapDbLookupMergeDisjointReferencedDomains
0x18001ebc6  mov     ebx, eax
0x18001ebc8  test    eax, eax
0x18001ebca  js      short loc_18001EB9B
0x18001ebcc  mov     eax, [r13+0]
0x18001ebd0  mov     r14d, esi
0x18001ebd3  test    r15d, r15d
0x18001ebd6  jz      loc_18001EC7A
0x18001ebdc  mov     r13d, eax
0x18001ebdf  mov     edi, r14d
0x18001ebe2  shl     rdi, 5
0x18001ebe6  mov     eax, r14d
0x18001ebe9  cmp     dword ptr [rdi+r12+18h], 0FFFFFFFFh
0x18001ebef  jnz     short loc_18001EBF8
0x18001ebf1  cmp     dword ptr [rdi+r12], 8
0x18001ebf6  jz      short loc_18001EC68
0x18001ebf8  mov     rcx, [rsp+150h+var_D8]
0x18001ebfd  mov     edx, [rdi+r12]
0x18001ec01  mov     esi, [rcx+rax*4]
0x18001ec04  cmp     edx, 8
0x18001ec07  jz      short loc_18001EC3C
0x18001ec09  mov     r9, [rsp+150h+var_E0]
0x18001ec0e  lea     r8, [r12+8]
0x18001ec13  mov     ecx, esi
0x18001ec15  add     r8, rdi
0x18001ec18  shl     rcx, 5
0x18001ec1c  mov     rax, [r9+8]
0x18001ec20  mov     [rcx+rax], edx
0x18001ec23  mov     rdx, [r9+8]
0x18001ec27  add     rdx, 8
0x18001ec2b  add     rdx, rcx
0x18001ec2e  xor     ecx, ecx
0x18001ec30  call    cs:__imp_LsapRpcCopyUnicodeString
0x18001ec36  mov     ebx, eax
0x18001ec38  test    eax, eax
0x18001ec3a  js      short loc_18001EC74
0x18001ec3c  mov     ecx, [rdi+r12+18h]
0x18001ec41  mov     rdx, [rsp+150h+var_E0]
0x18001ec46  add     ecx, r13d
0x18001ec49  shl     rsi, 5
0x18001ec4d  mov     rax, [rdx+8]
0x18001ec51  mov     [rax+rsi+18h], ecx
0x18001ec55  mov     eax, [rdi+r12+1Ch]
0x18001ec5a  mov     rcx, [rdx+8]
0x18001ec5e  mov     [rcx+rsi+1Ch], eax
0x18001ec62  mov     rax, [rbp+50h+var_A8]
0x18001ec66  dec     dword ptr [rax]
0x18001ec68  inc     r14d
0x18001ec6b  cmp     r14d, r15d
0x18001ec6e  jb      loc_18001EBDF
0x18001ec74  mov     r13, [rbp+50h+var_A0]
0x18001ec78  xor     esi, esi
0x18001ec7a  mov     rcx, [rsp+150h+hMem]
0x18001ec7f  test    rcx, rcx
0x18001ec82  jz      short loc_18001ECBB
0x18001ec84  cmp     [r13+8], rsi
0x18001ec88  jz      short loc_18001EC9D
0x18001ec8a  mov     rcx, [r13+8]; hMem
0x18001ec8e  call    cs:__imp_LocalFree
0x18001ec94  mov     rcx, [rsp+150h+hMem]; hMem
0x18001ec99  mov     [r13+8], rsi
0x18001ec9d  movups  xmm0, xmmword ptr [rcx]
0x18001eca0  movups  xmmword ptr [r13+0], xmm0
0x18001eca5  movsd   xmm1, qword ptr [rcx+10h]
0x18001ecaa  movsd   qword ptr [r13+10h], xmm1
0x18001ecb0  call    cs:__imp_LocalFree
0x18001ecb6  mov     [rsp+150h+hMem], rsi
0x18001ecbb  test    ebx, ebx
0x18001ecbd  js      loc_18001EB9B
0x18001ecc3  mov     rcx, [rbp+50h+var_98]
0x18001ecc7  mov     eax, [rsp+150h+var_F8]
0x18001eccb  add     [rcx], eax
0x18001eccd  jmp     loc_18001EB9B
0x18001ecd2  xor     esi, esi
0x18001ecd4  jmp     loc_18001EB9B
0x18001ecd9  mov     r14, rsi
0x18001ecdc  mov     rax, [rsp+150h+var_100]
0x18001ece1  test    rax, rax
0x18001ece4  jz      short loc_18001ED5D
0x18001ece6  cmp     [rsp+150h+var_110], sil
0x18001eceb  jnz     short loc_18001ED4D
0x18001eced  cmp     [rax+8], rsi
0x18001ecf1  jz      short loc_18001ED4D
0x18001ecf3  mov     edi, esi
0x18001ecf5  cmp     [rax], esi
0x18001ecf7  jbe     short loc_18001ED3E
0x18001ecf9  mov     eax, edi
0x18001ecfb  lea     rsi, [rax+rax*2]
0x18001ecff  mov     rax, [rsp+150h+var_100]
0x18001ed04  mov     rcx, [rax+8]
0x18001ed08  mov     rcx, [rcx+rsi*8+8]; hMem
0x18001ed0d  test    rcx, rcx
0x18001ed10  jz      short loc_18001ED18
0x18001ed12  call    cs:__imp_LocalFree
0x18001ed18  mov     rax, [rsp+150h+var_100]
0x18001ed1d  mov     rcx, [rax+8]
0x18001ed21  mov     rcx, [rcx+rsi*8+10h]; hMem
0x18001ed26  xor     esi, esi
0x18001ed28  test    rcx, rcx
0x18001ed2b  jz      short loc_18001ED33
0x18001ed2d  call    cs:__imp_LocalFree
0x18001ed33  mov     rax, [rsp+150h+var_100]
0x18001ed38  inc     edi
0x18001ed3a  cmp     edi, [rax]
0x18001ed3c  jb      short loc_18001ECF9
0x18001ed3e  mov     rcx, [rsp+150h+var_100]
0x18001ed43  mov     rcx, [rcx+8]; hMem
0x18001ed47  call    cs:__imp_LocalFree
0x18001ed4d  mov     rcx, [rsp+150h+var_100]; hMem
0x18001ed52  call    cs:__imp_LocalFree
0x18001ed58  mov     [rsp+150h+var_100], rsi
0x18001ed5d  mov     rax, [rbp+50h+var_C0]
0x18001ed61  test    rax, rax
0x18001ed64  jz      short loc_18001ED6F
0x18001ed66  mov     rcx, rax; hMem
0x18001ed69  call    cs:__imp_LocalFree
0x18001ed6f  test    r12, r12
0x18001ed72  jz      short loc_18001EDA8
0x18001ed74  cmp     [rsp+150h+var_110], sil
0x18001ed79  jnz     short loc_18001ED9F
0x18001ed7b  mov     edi, esi
0x18001ed7d  test    r15d, r15d
0x18001ed80  jz      short loc_18001ED9F
0x18001ed82  mov     eax, edi
0x18001ed84  shl     rax, 5
0x18001ed88  mov     rcx, [rax+r12+10h]; hMem
0x18001ed8d  test    rcx, rcx
0x18001ed90  jz      short loc_18001ED98
0x18001ed92  call    cs:__imp_LocalFree
0x18001ed98  inc     edi
0x18001ed9a  cmp     edi, r15d
0x18001ed9d  jb      short loc_18001ED82
0x18001ed9f  mov     rcx, r12; hMem
0x18001eda2  call    cs:__imp_LocalFree
0x18001eda8  mov     rax, [rsp+150h+var_D8]
0x18001edad  test    rax, rax
0x18001edb0  jz      short loc_18001EDBB
0x18001edb2  mov     rcx, rax; hMem
0x18001edb5  call    cs:__imp_LocalFree
  ... truncated ...
```
