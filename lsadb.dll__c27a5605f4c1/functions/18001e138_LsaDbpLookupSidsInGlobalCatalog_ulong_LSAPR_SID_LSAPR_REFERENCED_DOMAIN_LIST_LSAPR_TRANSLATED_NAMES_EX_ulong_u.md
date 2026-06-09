# LsaDbpLookupSidsInGlobalCatalog(ulong,_LSAPR_SID * *,_LSAPR_REFERENCED_DOMAIN_LIST *,_LSAPR_TRANSLATED_NAMES_EX *,ulong *,ulong *,uchar,long *)

- ea: `0x18001e138`
- end: `0x18001e80e`
- name: `?LsaDbpLookupSidsInGlobalCatalog@@YAJKPEAPEAU_LSAPR_SID@@PEAU_LSAPR_REFERENCED_DOMAIN_LIST@@PEAU_LSAPR_TRANSLATED_NAMES_EX@@PEAK3EPEAJ@Z`
- size: `1750`
- prototype: `__int64 __usercall@<rax>(size_t Size@<rcx>, struct _LSAPR_SID **@<rdx>, struct _LSAPR_REFERENCED_DOMAIN_LIST *@<r8>, struct _LSAPR_TRANSLATED_NAMES_EX *@<r9>, unsigned int *, unsigned int *, unsigned __int8, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001db90`

## callees

- `0x180001fb8`
- `0x18000fd18`
- `0x18000fd40`
- `0x18001abec`
- `0x18001ae84`
- `0x18001e138`
- `0x180037140`
- `0x18003ad30`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e1b7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e263`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e29c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e30c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e32e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e69b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e1b7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e263`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e29c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e30c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e32e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e69b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e237`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e2ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e734`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e746`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e761`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e7b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e7c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e7cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e7dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e7eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e237`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e2ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e734`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e746`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e761`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e7b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e7c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e7cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e7dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e7eb`
- `LSASRV!LsapDbLookupListReferencedDomains` at `0x18001e5f7`
- `LSASRV!LsapDbLookupListReferencedDomains` at `0x18001e5f7`
- `LSASRV!LsapDbLookupAddListReferencedDomains` at `0x18001e636`
- `LSASRV!LsapDbLookupAddListReferencedDomains` at `0x18001e636`
- `LSASRV!__imp_?SpmpEventWrite@@YAKPEBU_EVENT_DESCRIPTOR@@PEAGZZ` at `0x18001e450`
- `LSASRV!__imp_?SpmpEventWrite@@YAKPEBU_EVENT_DESCRIPTOR@@PEAGZZ` at `0x18001e450`
- `ntdll!RtlInitUnicodeString` at `0x18001e1a9`
- `ntdll!RtlInitUnicodeString` at `0x18001e1a9`
- `SAMSRV!SamIFree_SAMPR_RETURNED_USTRING_ARRAY` at `0x18001e7a1`
- `SAMSRV!SamIFree_SAMPR_RETURNED_USTRING_ARRAY` at `0x18001e7a1`
- `SAMSRV!SampDsIsRunning` at `0x18001e179`
- `SAMSRV!SampDsIsRunning` at `0x18001e179`
- `NTDSA!SamIGCLookupSids` at `0x18001e3ff`
- `NTDSA!SamIGCLookupSids` at `0x18001e3ff`

## pseudocode

```c
__int64 __fastcall LsaDbpLookupSidsInGlobalCatalog(
        size_t Size,
        struct _LSAPR_SID **a2,
        struct _LSAPR_REFERENCED_DOMAIN_LIST *a3,
        struct _LSAPR_TRANSLATED_NAMES_EX *a4,
        unsigned int *a5,
        unsigned int *a6,
        ULONG a7,
        int *a8)
{
  SIZE_T v8; // r14
  int v9; // ebx
  unsigned __int64 v12; // rsi
  char *v13; // r13
  char *v14; // r15
  _BYTE *v15; // rax
  void *v16; // r14
  unsigned int v17; // edi
  HLOCAL v18; // rcx
  size_t v19; // rbx
  __int64 v20; // rdi
  _QWORD *v21; // rax
  SIZE_T v22; // rdi
  HLOCAL v23; // rax
  _DWORD *v24; // rbx
  _BYTE *v25; // rcx
  unsigned int v26; // edx
  unsigned int v27; // esi
  __int64 v28; // rcx
  char *v29; // rax
  unsigned int v30; // ecx
  unsigned int v31; // eax
  unsigned int v32; // ebx
  char *v33; // rdi
  unsigned __int64 i; // rcx
  __int64 v35; // rax
  _QWORD *v36; // r14
  int v37; // eax
  unsigned int v38; // r12d
  __int64 v39; // rdx
  HLOCAL v40; // rdi
  bool v41; // zf
  __int64 v42; // rcx
  int v43; // edx
  __int64 v44; // r9
  unsigned __int16 v45; // r8
  unsigned __int16 v46; // r15
  unsigned __int16 v47; // r12
  unsigned __int64 v48; // r14
  unsigned __int64 v49; // rdi
  const unsigned __int16 *v50; // rcx
  int DomainSidByNetbiosName; // eax
  void *v52; // rcx
  int DomainNameBySid; // eax
  __int64 v54; // r14
  void *v55; // rcx
  _QWORD *v56; // [rsp+38h] [rbp-89h]
  _BYTE *v57; // [rsp+40h] [rbp-81h]
  char *v58; // [rsp+48h] [rbp-79h]
  __int64 v59; // [rsp+50h] [rbp-71h]
  int v60; // [rsp+58h] [rbp-69h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp-61h] BYREF
  HLOCAL v62; // [rsp+68h] [rbp-59h]
  __int128 v63; // [rsp+70h] [rbp-51h]
  void *Src[2]; // [rsp+80h] [rbp-41h]
  __int128 v65; // [rsp+90h] [rbp-31h] BYREF
  HLOCAL v66[2]; // [rsp+A0h] [rbp-21h] BYREF
  HLOCAL v67; // [rsp+B0h] [rbp-11h]
  struct _UNICODE_STRING DestinationString; // [rsp+B8h] [rbp-9h] BYREF

  v8 = (unsigned int)Size;
  v9 = 0;
  v65 = 0;
  *a8 = 0;
  DestinationString = 0;
  if ( !(unsigned __int8)SampDsIsRunning() )
    return 0;
  v62 = 0;
  v12 = 0;
  v13 = 0;
  v65 = 0;
  v14 = 0;
  RtlInitUnicodeString(&DestinationString, L"\\");
  v15 = LocalAlloc(0x40u, v8);
  v57 = v15;
  if ( !v15 )
  {
    v9 = -1073741670;
    v16 = 0;
    goto LABEL_86;
  }
  memset_0(v15, 0, v8);
  v17 = 0;
  if ( !(_DWORD)v8 )
    goto LABEL_83;
  do
  {
    hMem = 0;
    a7 = 0;
    if ( *(_DWORD *)(32LL * v17 + *((_QWORD *)a4 + 1)) == 8 )
    {
      v9 = LsapSplitSid(a2[v17], &hMem, &a7);
      if ( v9 < 0 )
      {
        v14 = 0;
        v12 = 0;
        goto LABEL_85;
      }
      v12 = (unsigned int)(v12 + 1);
      v18 = hMem;
      v57[v17] = 1;
      LocalFree(v18);
    }
    ++v17;
  }
  while ( v17 < (unsigned int)v8 );
  v14 = 0;
  if ( !(_DWORD)v12 )
  {
    v14 = 0;
LABEL_83:
    v12 = 0;
    goto LABEL_85;
  }
  v19 = 8 * v12;
  v20 = (unsigned int)v12;
  v21 = LocalAlloc(0x40u, 8 * v12);
  v56 = v21;
  v12 = (unsigned __int64)v21;
  if ( !v21 || (memset_0(v21, 0, v19), v22 = 4 * v20, v23 = LocalAlloc(0x40u, v22), v62 = v23, (v24 = v23) == 0) )
  {
    v9 = -1073741670;
    v14 = 0;
    goto LABEL_85;
  }
  memset_0(v23, 0, v22);
  v25 = v57;
  v26 = 0;
  v27 = 0;
  do
  {
    if ( v25[v26] )
    {
      v28 = v27++;
      v56[v28] = a2[v26];
      v24[v28] = v26;
      v25 = v57;
    }
    ++v26;
  }
  while ( v26 < (unsigned int)v8 );
  LocalFree(v25);
  v57 = 0;
  v16 = 0;
  v13 = (char *)LocalAlloc(0x40u, 4LL * v27);
  if ( !v13 || (v29 = (char *)LocalAlloc(0x40u, 4LL * v27), v58 = v29, (v14 = v29) == 0) )
  {
    v12 = (unsigned __int64)v56;
    v9 = -1073741670;
    goto LABEL_86;
  }
  if ( v27 )
  {
    v30 = 0;
    if ( v27 < 4 || v29 <= &v13[4 * v27 - 4] && &v29[4 * v27 - 4] >= v13 )
      goto LABEL_99;
    v31 = v27 & 0xFFFFFFFC;
    do
    {
      v30 += 4;
      v32 = v30;
    }
    while ( v30 < v31 );
    v33 = v13;
    for ( i = (4 * (unsigned __int64)v31) >> 2; i; --i )
    {
      *(_DWORD *)v33 = 8;
      v33 += 4;
    }
    memset_0(v14, 0, 4LL * v31);
    v30 = v32;
    if ( v32 < v27 )
    {
LABEL_99:
      do
      {
        v35 = v30++;
        *(_DWORD *)&v13[4 * v35] = 8;
        *(_DWORD *)&v14[4 * v35] = 0;
      }
      while ( v30 < v27 );
    }
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_fba679e325d0357b28993121764167cc_Traceguids);
  v36 = v56;
  v37 = SamIGCLookupSids(v27, v56, 1, v14, v13, &v65);
  v9 = v37;
  if ( v37 < 0 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      WPP_fba679e325d0357b28993121764167cc_Traceguids,
      (unsigned int)v37);
  if ( v9 != -1073741136 )
  {
    if ( v9 >= 0 )
    {
      LODWORD(a8) = 0;
      v38 = 0;
      if ( v27 )
      {
        while ( 1 )
        {
          v39 = v38;
          hMem = 0;
          v40 = 0;
          v60 = -1;
          *(_OWORD *)v66 = 0;
          v41 = (v14[4 * v38] & 4) == 0;
          v67 = 0;
          v63 = 0;
          v59 = v38;
          if ( !v41 )
          {
            v42 = 32LL * *((unsigned int *)v62 + v38);
            *(_DWORD *)(v42 + *((_QWORD *)a4 + 1) + 28) |= 2u;
          }
          if ( *(_DWORD *)&v13[4 * v38] == 8 )
            goto LABEL_70;
          if ( *(_DWORD *)&v13[4 * v38] == 3 )
            break;
          *(_OWORD *)Src = *(_OWORD *)(*((_QWORD *)&v65 + 1) + 16LL * v38);
          v63 = *(_OWORD *)Src;
          if ( !LOWORD(Src[0]) )
            goto LABEL_51;
          v43 = 0;
          while ( *DestinationString.Buffer != *(_WORD *)(*(_QWORD *)(*((_QWORD *)&v65 + 1) + 16LL * v38 + 8)
                                                        + 2 * ((unsigned __int64)(unsigned int)v43 >> 1)) )
          {
            v43 += 2;
            if ( v43 >= (unsigned int)LOWORD(Src[0]) )
              goto LABEL_51;
          }
          if ( v43 >= 0 )
          {
            v45 = v43;
            v44 = *((_QWORD *)&v63 + 1) + 2LL * (int)(((unsigned __int64)v43 >> 1) + 1);
            v46 = -2 - v43 + v63;
          }
          else
          {
LABEL_51:
            v44 = *((_QWORD *)&v63 + 1);
            v45 = 0;
            v46 = v63;
          }
          LOWORD(a7) = v46;
          v47 = v46;
          v48 = (unsigned __int64)Src[1] & -(__int64)(v45 != 0);
          Src[0] = (void *)(v44 & -(__int64)(v46 != 0));
          if ( !v45
            || (v49 = (unsigned __int64)v45 >> 1,
                v50 = (const unsigned __int16 *)((unsigned __int64)Src[1] & -(__int64)(v45 != 0)),
                *(_WORD *)(v48 + 2 * v49) = 0,
                DomainSidByNetbiosName = LsaDbpGetDomainSidByNetbiosName(v50, &hMem),
                *(_WORD *)(v48 + 2 * v49) = 92,
                v40 = hMem,
                v9 = DomainSidByNetbiosName,
                DomainSidByNetbiosName == -1073741601) )
          {
LABEL_58:
            v9 = 0;
            goto LABEL_55;
          }
          if ( DomainSidByNetbiosName >= 0 )
            goto LABEL_60;
LABEL_55:
          v39 = v59;
LABEL_69:
          v38 = (unsigned int)a8;
          v14 = v58;
LABEL_70:
          v36 = v56;
          if ( v67 && v67 != (HLOCAL)v56[v39] )
            LocalFree(v67);
          if ( v66[1] )
            LocalFree(v66[1]);
          if ( v40 && v40 != (HLOCAL)v56[v59] )
            LocalFree(v40);
          if ( v9 >= 0 )
          {
            LODWORD(a8) = ++v38;
            if ( v38 < v27 )
              continue;
          }
          v12 = (unsigned __int64)v56;
          goto LABEL_85;
        }
        v47 = WORD1(v63);
        v40 = (HLOCAL)v36[v39];
        v46 = v63;
        Src[0] = *((void **)&v63 + 1);
        LOWORD(a7) = WORD1(v63);
LABEL_60:
        if ( !(unsigned __int8)LsapDbLookupListReferencedDomains(a3, v40, &v60) )
        {
          v52 = v40;
          v67 = v40;
          v40 = 0;
          DomainNameBySid = LsaDbpGetDomainNameBySid(v52, (PUNICODE_STRING)v66);
          v9 = DomainNameBySid;
          if ( DomainNameBySid == -1073741601 )
            goto LABEL_58;
          if ( DomainNameBySid < 0 )
            goto LABEL_55;
          v9 = LsapDbLookupAddListReferencedDomains(a3, v66, &v60);
          if ( v9 < 0 )
            goto LABEL_55;
        }
        v39 = v59;
        v54 = 32LL * *((unsigned int *)v62 + v59);
        *(_DWORD *)(*((_QWORD *)a4 + 1) + v54 + 28) = *(_DWORD *)&v58[4 * v59] & 1;
        *(_DWORD *)(v54 + *((_QWORD *)a4 + 1)) = *(_DWORD *)&v13[4 * v59];
        *(_DWORD *)(*((_QWORD *)a4 + 1) + v54 + 24) = v60;
        if ( !v47 )
          goto LABEL_68;
        *(_QWORD *)(*((_QWORD *)a4 + 1) + v54 + 16) = LocalAlloc(0x40u, v47);
        v55 = *(void **)(*((_QWORD *)a4 + 1) + v54 + 16);
        if ( v55 )
        {
          memset_0(v55, 0, v47);
          *(_WORD *)(*((_QWORD *)a4 + 1) + v54 + 10) = a7;
          *(_WORD *)(*((_QWORD *)a4 + 1) + v54 + 8) = v46;
          memcpy_0(*(void **)(*((_QWORD *)a4 + 1) + v54 + 16), Src[0], v46);
          v39 = v59;
LABEL_68:
          ++*a5;
          --*a6;
          goto LABEL_69;
        }
        v9 = -1073741670;
        goto LABEL_55;
      }
    }
    v12 = (unsigned __int64)v56;
LABEL_85:
    v16 = v57;
    goto LABEL_86;
  }
  if ( LsapLookupLogLevel )
    SpmpEventWrite((const struct _EVENT_DESCRIPTOR *)LSAEVENT_LOOKUP_GC_FAILED, 0);
  v9 = 0;
  v12 = (unsigned __int64)v56;
  v16 = 0;
  *a8 = -1073741136;
LABEL_86:
  SamIFree_SAMPR_RETURNED_USTRING_ARRAY(&v65);
  if ( v62 )
    LocalFree(v62);
  if ( v16 )
    LocalFree(v16);
  if ( v12 )
    LocalFree((HLOCAL)v12);
  if ( v13 )
    LocalFree(v13);
  if ( v14 )
    LocalFree(v14);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001e138  mov     rax, rsp
0x18001e13b  mov     [rax+8], rbx
0x18001e13f  mov     [rax+20h], r9
0x18001e143  mov     [rax+18h], r8
0x18001e147  push    rbp
0x18001e148  push    rsi
0x18001e149  push    rdi
0x18001e14a  push    r12
0x18001e14c  push    r13
0x18001e14e  push    r14
0x18001e150  push    r15
0x18001e152  lea     rbp, [rax-3Fh]
0x18001e156  sub     rsp, 0C0h
0x18001e15d  mov     rax, [rbp+37h+arg_38]
0x18001e161  xorps   xmm0, xmm0
0x18001e164  xorps   xmm1, xmm1
0x18001e167  mov     r14d, ecx
0x18001e16a  xor     ebx, ebx
0x18001e16c  mov     r12, rdx
0x18001e16f  movups  [rbp+37h+var_68], xmm0
0x18001e173  mov     [rax], ebx
0x18001e175  movups  xmmword ptr [rbp+37h+DestinationString.Length], xmm1
0x18001e179  call    cs:__imp_SampDsIsRunning
0x18001e17f  test    al, al
0x18001e181  jnz     short loc_18001E18A
0x18001e183  xor     eax, eax
0x18001e185  jmp     loc_18001E7F3
0x18001e18a  xorps   xmm0, xmm0
0x18001e18d  mov     [rbp+37h+var_90], rbx
0x18001e191  lea     rdx, asc_18003D82C; "\\"
0x18001e198  mov     rsi, rbx
0x18001e19b  lea     rcx, [rbp+37h+DestinationString]; DestinationString
0x18001e19f  mov     r13, rbx
0x18001e1a2  movups  [rbp+37h+var_68], xmm0
0x18001e1a6  mov     r15, rbx
0x18001e1a9  call    cs:__imp_RtlInitUnicodeString
0x18001e1af  mov     rdx, r14; uBytes
0x18001e1b2  mov     ecx, 40h ; '@'; uFlags
0x18001e1b7  call    cs:__imp_LocalAlloc
0x18001e1bd  mov     [rsp+38h], rax
0x18001e1c2  test    rax, rax
0x18001e1c5  jnz     short loc_18001E1D4
0x18001e1c7  mov     ebx, 0C000009Ah
0x18001e1cc  mov     r14, rax
0x18001e1cf  jmp     loc_18001E79D
0x18001e1d4  mov     r8, r14; Size
0x18001e1d7  xor     edx, edx; Val
0x18001e1d9  mov     rcx, rax; void *
0x18001e1dc  call    memset_0
0x18001e1e1  xor     eax, eax
0x18001e1e3  mov     edi, eax
0x18001e1e5  test    r14d, r14d
0x18001e1e8  jz      loc_18001E790
0x18001e1ee  mov     [rbp+37h+hMem], rax
0x18001e1f2  mov     [rbp+37h+arg_30], eax
0x18001e1f5  mov     rax, [rbp+37h+arg_18]
0x18001e1f9  mov     ecx, edi
0x18001e1fb  shl     rcx, 5
0x18001e1ff  mov     r15d, edi
0x18001e202  mov     rax, [rax+8]
0x18001e206  cmp     dword ptr [rcx+rax], 8
0x18001e20a  jnz     short loc_18001E23D
0x18001e20c  mov     rcx, [r12+r15*8]; Src
0x18001e210  lea     r8, [rbp+37h+arg_30]
0x18001e214  lea     rdx, [rbp+37h+hMem]
0x18001e218  call    LsapSplitSid
0x18001e21d  mov     ebx, eax
0x18001e21f  test    eax, eax
0x18001e221  js      loc_18001E785
0x18001e227  mov     rax, [rsp+38h]
0x18001e22c  inc     esi
0x18001e22e  mov     rcx, [rbp+37h+hMem]; hMem
0x18001e232  mov     byte ptr [r15+rax], 1
0x18001e237  call    cs:__imp_LocalFree
0x18001e23d  inc     edi
0x18001e23f  mov     rax, r13
0x18001e242  cmp     edi, r14d
0x18001e245  jb      short loc_18001E1EE
0x18001e247  xor     r15d, r15d
0x18001e24a  test    esi, esi
0x18001e24c  jz      loc_18001E78D
0x18001e252  lea     rbx, ds:0[rsi*8]
0x18001e25a  mov     edi, esi
0x18001e25c  mov     rdx, rbx; uBytes
0x18001e25f  lea     ecx, [r15+40h]; uFlags
0x18001e263  call    cs:__imp_LocalAlloc
0x18001e269  mov     [rsp+0F0h+var_C0], rax
0x18001e26e  mov     rsi, rax
0x18001e271  test    rax, rax
0x18001e274  jnz     short loc_18001E283
0x18001e276  mov     ebx, 0C000009Ah
0x18001e27b  mov     r15, r13
0x18001e27e  jmp     loc_18001E798
0x18001e283  mov     r8, rbx; Size
0x18001e286  xor     edx, edx; Val
0x18001e288  mov     rcx, rax; void *
0x18001e28b  call    memset_0
0x18001e290  shl     rdi, 2
0x18001e294  mov     ecx, 40h ; '@'; uFlags
0x18001e299  mov     rdx, rdi; uBytes
0x18001e29c  call    cs:__imp_LocalAlloc
0x18001e2a2  mov     [rbp+37h+var_90], rax
0x18001e2a6  mov     rbx, rax
0x18001e2a9  test    rax, rax
0x18001e2ac  jz      short loc_18001E276
0x18001e2ae  mov     r8, rdi; Size
0x18001e2b1  xor     edx, edx; Val
0x18001e2b3  mov     rcx, rax; void *
0x18001e2b6  call    memset_0
0x18001e2bb  mov     rcx, [rsp+38h]
0x18001e2c0  mov     edx, r15d
0x18001e2c3  mov     rdi, [rsp+0F0h+var_C0]
0x18001e2c8  mov     esi, r15d
0x18001e2cb  mov     eax, edx
0x18001e2cd  cmp     [rax+rcx], r15b
0x18001e2d1  jz      short loc_18001E2E7
0x18001e2d3  mov     rax, [r12+rax*8]
0x18001e2d7  mov     ecx, esi
0x18001e2d9  inc     esi
0x18001e2db  mov     [rdi+rcx*8], rax
0x18001e2df  mov     [rbx+rcx*4], edx
0x18001e2e2  mov     rcx, [rsp+38h]; hMem
0x18001e2e7  inc     edx
0x18001e2e9  cmp     edx, r14d
0x18001e2ec  jb      short loc_18001E2CB
0x18001e2ee  call    cs:__imp_LocalFree
0x18001e2f4  mov     edi, esi
0x18001e2f6  mov     ebx, 40h ; '@'
0x18001e2fb  shl     rdi, 2
0x18001e2ff  mov     ecx, ebx; uFlags
0x18001e301  mov     rdx, rdi; uBytes
0x18001e304  mov     [rsp+38h], r15
0x18001e309  mov     r14, r15
0x18001e30c  call    cs:__imp_LocalAlloc
0x18001e312  mov     r13, rax
0x18001e315  test    rax, rax
0x18001e318  jnz     short loc_18001E329
0x18001e31a  mov     rsi, [rsp+0F0h+var_C0]
0x18001e31f  mov     ebx, 0C000009Ah
0x18001e324  jmp     loc_18001E79D
0x18001e329  mov     rdx, rdi; uBytes
0x18001e32c  mov     ecx, ebx; uFlags
0x18001e32e  call    cs:__imp_LocalAlloc
0x18001e334  xor     edx, edx
0x18001e336  mov     [rbp+37h+var_B0], rax
0x18001e33a  mov     r15, rax
0x18001e33d  test    rax, rax
0x18001e340  jz      short loc_18001E31A
0x18001e342  test    esi, esi
0x18001e344  jz      short loc_18001E3BC
0x18001e346  mov     ecx, edx
0x18001e348  cmp     esi, 4
0x18001e34b  jb      short loc_18001E3A7
0x18001e34d  lea     eax, [rsi-1]
0x18001e350  mov     edx, eax
0x18001e352  lea     rax, ds:0[rax*4]
0x18001e35a  add     rax, r13
0x18001e35d  cmp     r15, rax
0x18001e360  ja      short loc_18001E36B
0x18001e362  lea     rax, [r15+rdx*4]
0x18001e366  cmp     rax, r13
0x18001e369  jnb     short loc_18001E3A5
0x18001e36b  mov     eax, esi
0x18001e36d  and     eax, 0FFFFFFFCh
0x18001e370  add     ecx, 4
0x18001e373  mov     ebx, ecx
0x18001e375  cmp     ecx, eax
0x18001e377  jb      short loc_18001E370
0x18001e379  mov     r8d, eax
0x18001e37c  mov     rdi, r13
0x18001e37f  shl     r8, 2
0x18001e383  mov     eax, 8
0x18001e388  mov     rcx, r8
0x18001e38b  xor     edx, edx; Val
0x18001e38d  shr     rcx, 2
0x18001e391  and     r8, 0FFFFFFFFFFFFFFFCh; Size
0x18001e395  rep stosd
0x18001e397  mov     rcx, r15; void *
0x18001e39a  call    memset_0
0x18001e39f  mov     ecx, ebx
0x18001e3a1  cmp     ebx, esi
0x18001e3a3  jnb     short loc_18001E3BC
0x18001e3a5  xor     edx, edx
0x18001e3a7  mov     eax, ecx
0x18001e3a9  inc     ecx
0x18001e3ab  mov     dword ptr [r13+rax*4+0], 8
0x18001e3b4  mov     [r15+rax*4], edx
0x18001e3b8  cmp     ecx, esi
0x18001e3ba  jb      short loc_18001E3A7
0x18001e3bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e3c3  test    byte ptr [rcx+1Ch], 20h
0x18001e3c7  jz      short loc_18001E3DE
0x18001e3c9  mov     rcx, [rcx+10h]
0x18001e3cd  lea     r8, WPP_fba679e325d0357b28993121764167cc_Traceguids
0x18001e3d4  mov     edx, 0Ah
0x18001e3d9  call    WPP_SF_
0x18001e3de  mov     r14, [rsp+0F0h+var_C0]
0x18001e3e3  lea     rax, [rbp+37h+var_68]
0x18001e3e7  mov     [rsp+0F0h+var_C8], rax
0x18001e3ec  mov     rdx, r14
0x18001e3ef  mov     r9, r15
0x18001e3f2  mov     [rsp+0F0h+var_D0], r13
0x18001e3f7  mov     r8d, 1
0x18001e3fd  mov     ecx, esi
0x18001e3ff  call    cs:__imp_SamIGCLookupSids
0x18001e405  xor     r10d, r10d
0x18001e408  mov     ebx, eax
0x18001e40a  test    eax, eax
0x18001e40c  jns     short loc_18001E435
0x18001e40e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e415  test    byte ptr [rcx+1Ch], 20h
0x18001e419  jz      short loc_18001E435
0x18001e41b  mov     rcx, [rcx+10h]
0x18001e41f  lea     edx, [r10+0Bh]
0x18001e423  mov     r9d, eax
0x18001e426  lea     r8, WPP_fba679e325d0357b28993121764167cc_Traceguids
0x18001e42d  call    WPP_SF_d
0x18001e432  xor     r10d, r10d
0x18001e435  mov     edi, 0C00002B0h
0x18001e43a  cmp     ebx, edi
0x18001e43c  jnz     short loc_18001E469
0x18001e43e  cmp     cs:?LsapLookupLogLevel@@3KA, 1; ulong LsapLookupLogLevel
0x18001e445  jb      short loc_18001E456
0x18001e447  xor     edx, edx
0x18001e449  lea     rcx, LSAEVENT_LOOKUP_GC_FAILED
0x18001e450  call    cs:__imp_?SpmpEventWrite@@YAKPEBU_EVENT_DESCRIPTOR@@PEAGZZ; SpmpEventWrite(_EVENT_DESCRIPTOR const *,ushort *,...)
0x18001e456  mov     rax, [rbp+37h+arg_38]
0x18001e45a  xor     ebx, ebx
0x18001e45c  mov     rsi, r14
0x18001e45f  mov     r14d, ebx
0x18001e462  mov     [rax], edi
0x18001e464  jmp     loc_18001E79D
0x18001e469  test    ebx, ebx
0x18001e46b  js      loc_18001E795
0x18001e471  mov     dword ptr [rbp+37h+arg_38], r10d
0x18001e475  mov     r12d, r10d
0x18001e478  test    esi, esi
0x18001e47a  jz      loc_18001E795
0x18001e480  mov     edx, r12d
0x18001e483  xor     eax, eax
0x18001e485  xorps   xmm0, xmm0
0x18001e488  mov     [rbp+37h+hMem], r10
0x18001e48c  mov     rdi, r10
0x18001e48f  mov     [rbp+37h+var_A0], 0FFFFFFFFh
0x18001e496  movups  xmmword ptr [rbp+37h+var_58], xmm0
0x18001e49a  test    byte ptr [r15+rdx*4], 4
0x18001e49f  mov     [rbp+37h+var_48], rax
0x18001e4a3  movups  [rbp+37h+var_88], xmm0
0x18001e4a7  mov     [rbp+37h+var_A8], rdx
0x18001e4ab  jz      short loc_18001E4C5
0x18001e4ad  mov     rax, [rbp+37h+var_90]
0x18001e4b1  mov     ecx, [rax+rdx*4]
0x18001e4b4  mov     rax, [rbp+37h+arg_18]
0x18001e4b8  shl     rcx, 5
0x18001e4bc  mov     rax, [rax+8]
0x18001e4c0  or      dword ptr [rcx+rax+1Ch], 2
0x18001e4c5  cmp     dword ptr [r13+rdx*4+0], 8
0x18001e4cb  jz      loc_18001E720
0x18001e4d1  cmp     dword ptr [r13+rdx*4+0], 3
0x18001e4d7  jz      loc_18001E5CE
0x18001e4dd  mov     rcx, qword ptr [rbp+37h+var_68+8]
0x18001e4e1  mov     rax, rdx
0x18001e4e4  add     rax, rax
0x18001e4e7  movups  xmm0, xmmword ptr [rcx+rax*8]
0x18001e4eb  movzx   r8d, word ptr [rcx+rax*8]
0x18001e4f0  movdqu  xmmword ptr [rbp+37h+Src], xmm0
0x18001e4f5  movdqu  [rbp+37h+var_88], xmm0
0x18001e4fa  test    r8d, r8d
0x18001e4fd  jz      short loc_18001E522
0x18001e4ff  mov     r9, [rcx+rax*8+8]
0x18001e504  mov     edx, r10d
0x18001e507  mov     rax, [rbp+37h+DestinationString.Buffer]
0x18001e50b  movzx   ecx, word ptr [rax]
0x18001e50e  mov     eax, edx
0x18001e510  shr     rax, 1
0x18001e513  cmp     cx, [r9+rax*2]
0x18001e518  jz      short loc_18001E598
0x18001e51a  add     edx, 2
0x18001e51d  cmp     edx, r8d
0x18001e520  jb      short loc_18001E50E
0x18001e522  mov     r9, qword ptr [rbp+37h+var_88+8]
0x18001e526  mov     r8d, r10d
0x18001e529  movzx   r15d, word ptr [rbp+37h+var_88]
0x18001e52e  movzx   eax, r8w
0x18001e532  mov     word ptr [rbp+37h+arg_30], r15w
0x18001e537  neg     ax
0x18001e53a  movzx   r12d, r15w
0x18001e53e  movzx   eax, r15w
0x18001e542  sbb     r14, r14
0x18001e545  and     r14, [rbp+37h+Src+8]
0x18001e549  neg     ax
0x18001e54c  sbb     rax, rax
0x18001e54f  and     rax, r9
0x18001e552  mov     [rbp+37h+Src], rax
0x18001e556  test    r8w, r8w
0x18001e55a  jz      short loc_18001E5C9
0x18001e55c  movzx   edi, r8w
0x18001e560  lea     rdx, [rbp+37h+hMem]; void **
0x18001e564  shr     rdi, 1
0x18001e567  mov     rcx, r14; unsigned __int16 *
  ... truncated ...
```
