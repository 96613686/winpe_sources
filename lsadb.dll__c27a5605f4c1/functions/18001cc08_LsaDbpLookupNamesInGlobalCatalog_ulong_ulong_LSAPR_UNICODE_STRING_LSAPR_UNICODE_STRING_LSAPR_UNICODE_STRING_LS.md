# LsaDbpLookupNamesInGlobalCatalog(ulong,ulong,_LSAPR_UNICODE_STRING *,_LSAPR_UNICODE_STRING *,_LSAPR_UNICODE_STRING *,_LSAPR_REFERENCED_DOMAIN_LIST *,_LSAPR_TRANSLATED_SIDS_EX2 *,ulong *,ulong *,long *)

- ea: `0x18001cc08`
- end: `0x18001d1af`
- name: `?LsaDbpLookupNamesInGlobalCatalog@@YAJKKPEAU_LSAPR_UNICODE_STRING@@00PEAU_LSAPR_REFERENCED_DOMAIN_LIST@@PEAU_LSAPR_TRANSLATED_SIDS_EX2@@PEAK3PEAJ@Z`
- size: `1447`
- prototype: `int(unsigned int, unsigned int, struct _LSAPR_UNICODE_STRING *, struct _LSAPR_UNICODE_STRING *, struct _LSAPR_UNICODE_STRING *, struct _LSAPR_REFERENCED_DOMAIN_LIST *, struct _LSAPR_TRANSLATED_SIDS_EX2 *, unsigned int *, unsigned int *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001c670`

## callees

- `0x180001fb8`
- `0x18000fd18`
- `0x18000fd40`
- `0x18001a6d8`
- `0x18001abec`
- `0x18001cc08`
- `0x180037140`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001cc62`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001cd38`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001cd77`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ce66`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ce94`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d0b4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001cc62`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001cd38`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001cd77`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ce66`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ce94`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d0b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cda7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cdb5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cdc3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cdd1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cddf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ce51`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d142`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d151`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d16d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cda7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cdb5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cdc3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cdd1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cddf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ce51`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d142`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d151`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d16d`
- `LSASRV!LsapDbLookupListReferencedDomains` at `0x18001d02b`
- `LSASRV!LsapDbLookupListReferencedDomains` at `0x18001d02b`
- `LSASRV!LsapDbLookupAddListReferencedDomains` at `0x18001d070`
- `LSASRV!LsapDbLookupAddListReferencedDomains` at `0x18001d070`
- `LSASRV!LsapGetWellKnownSid` at `0x18001cffe`
- `LSASRV!LsapGetWellKnownSid` at `0x18001cffe`
- `LSASRV!__imp_?SpmpEventWrite@@YAKPEBU_EVENT_DESCRIPTOR@@PEAGZZ` at `0x18001cf48`
- `LSASRV!__imp_?SpmpEventWrite@@YAKPEBU_EVENT_DESCRIPTOR@@PEAGZZ` at `0x18001cf48`
- `ntdll!RtlCopySid` at `0x18001d0eb`
- `ntdll!RtlCopySid` at `0x18001d0eb`
- `ntdll!RtlLengthSid` at `0x18001d0a4`
- `ntdll!RtlLengthSid` at `0x18001d0a4`
- `ntdll!RtlEqualSid` at `0x18001d00a`
- `ntdll!RtlEqualSid` at `0x18001d00a`
- `SAMSRV!SamIFreeSidArray` at `0x18001cd99`
- `SAMSRV!SamIFreeSidArray` at `0x18001cd99`
- `SAMSRV!SampDsIsRunning` at `0x18001cc40`
- `SAMSRV!SampDsIsRunning` at `0x18001cc40`
- `NTDSA!SamIGCLookupNames` at `0x18001cefd`
- `NTDSA!SamIGCLookupNames` at `0x18001cefd`

## pseudocode

```c
__int64 __fastcall LsaDbpLookupNamesInGlobalCatalog(
        int a1,
        unsigned int a2,
        struct _LSAPR_UNICODE_STRING *a3,
        struct _UNICODE_STRING *a4,
        struct _LSAPR_UNICODE_STRING *a5,
        struct _LSAPR_REFERENCED_DOMAIN_LIST *a6,
        struct _LSAPR_TRANSLATED_SIDS_EX2 *a7,
        unsigned int *a8,
        unsigned int *a9,
        int *a10)
{
  int v10; // ebx
  SIZE_T v11; // rsi
  _DWORD *v13; // r12
  void *v14; // r15
  _BYTE *v15; // r13
  _BYTE *v16; // rax
  _BYTE *v17; // r14
  void *v18; // rdi
  __int64 v19; // rcx
  struct _UNICODE_STRING *v20; // r15
  char *v21; // rax
  char *v22; // r13
  SIZE_T v23; // rbx
  HLOCAL v24; // rax
  unsigned int v25; // edx
  unsigned int v26; // r9d
  __int64 v27; // rax
  __int64 v28; // rcx
  _DWORD *v29; // rax
  _BYTE *v30; // rax
  int v31; // eax
  unsigned int v32; // eax
  unsigned int *v33; // r14
  PSID v34; // rdi
  __int64 v35; // rsi
  __int64 v36; // rcx
  __int64 v37; // rcx
  int v38; // eax
  void *WellKnownSid; // rax
  void *v40; // rcx
  int DomainNameBySid; // eax
  __int64 v42; // r13
  void *v43; // rdx
  HLOCAL v44; // [rsp+30h] [rbp-50h]
  ULONG DestinationSidLength; // [rsp+38h] [rbp-48h]
  _BYTE *v46; // [rsp+40h] [rbp-40h]
  __int64 v47; // [rsp+48h] [rbp-38h] BYREF
  HLOCAL v48; // [rsp+50h] [rbp-30h]
  PSID Sid1; // [rsp+58h] [rbp-28h]
  HLOCAL v50[2]; // [rsp+60h] [rbp-20h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp-10h]
  int v55; // [rsp+E0h] [rbp+60h]
  unsigned int v56; // [rsp+E0h] [rbp+60h]

  v10 = 0;
  v11 = a2;
  v47 = 0;
  *a10 = 0;
  if ( !(unsigned __int8)SampDsIsRunning() )
    return 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  v16 = LocalAlloc(0x40u, v11);
  v17 = v16;
  if ( v16 )
  {
    v55 = 0;
    memset_0(v16, 0, v11);
    v18 = 0;
    if ( !(_DWORD)v11 )
    {
      v15 = 0;
      v14 = 0;
      goto LABEL_21;
    }
    do
    {
      v19 = *((_QWORD *)a7 + 1);
      if ( *(_DWORD *)(v19 + 24LL * (_QWORD)v18 + 16) == -1 && *(_DWORD *)(v19 + 24LL * (_QWORD)v18) == 8 )
      {
        v20 = &a4[(_QWORD)v18];
        if ( v20->Length && LsaDbpDomainHasDomainTrust(1u, &a4[(_QWORD)v18], 0, 0, 0) >= 0 || a1 < 0 && !v20->Length )
        {
          LODWORD(v14) = v55;
        }
        else
        {
          LODWORD(v14) = v55 + 1;
          *((_BYTE *)v18 + (_QWORD)v17) = 1;
          ++v55;
        }
      }
      LODWORD(v15) = (_DWORD)v15 + 1;
      v18 = (char *)v18 + 1;
    }
    while ( (unsigned int)v15 < (unsigned int)v11 );
    v10 = 0;
    v13 = 0;
    if ( !(_DWORD)v14 )
    {
      v15 = 0;
      v18 = 0;
      v14 = 0;
      goto LABEL_21;
    }
    v21 = (char *)LocalAlloc(0x40u, 16LL * (unsigned int)v14);
    v44 = v21;
    v22 = v21;
    if ( !v21 )
    {
      v10 = -1073741670;
      v15 = 0;
      v18 = 0;
      v14 = 0;
      goto LABEL_21;
    }
    memset_0(v21, 0, 16LL * (unsigned int)v14);
    v23 = 4LL * (unsigned int)v14;
    v24 = LocalAlloc(0x40u, v23);
    v48 = v24;
    v18 = v24;
    if ( !v24 )
    {
      v10 = -1073741670;
      v15 = 0;
      goto LABEL_20;
    }
    memset_0(v24, 0, v23);
    v25 = 0;
    v26 = 0;
    do
    {
      if ( v26 >= (unsigned int)v14 )
        break;
      if ( v17[v25] )
      {
        v27 = 2LL * v26;
        v28 = v26++;
        *(_OWORD *)&v22[8 * v27] = *((_OWORD *)a3 + v25);
        *((_DWORD *)v18 + v28) = v25;
      }
      ++v25;
    }
    while ( v25 < (unsigned int)v11 );
    LocalFree(v17);
    v17 = 0;
    v29 = LocalAlloc(0x40u, v23);
    v13 = v29;
    if ( !v29 )
    {
      v10 = -1073741670;
      v15 = 0;
      goto LABEL_20;
    }
    memset_0(v29, 0, v23);
    v30 = LocalAlloc(0x40u, v23);
    v46 = v30;
    v15 = v30;
    if ( !v30 )
    {
      v10 = -1073741670;
      goto LABEL_20;
    }
    memset_0(v30, 0, v23);
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_c0948403788e3f00547c7c2dd7a3b1b0_Traceguids);
    v31 = SamIGCLookupNames((unsigned int)v14, v44, 2, v15, v13, &v47);
    v10 = v31;
    if ( v31 < 0 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_c0948403788e3f00547c7c2dd7a3b1b0_Traceguids,
        (unsigned int)v31);
    if ( v10 == -1073741136 )
    {
      if ( LsapLookupLogLevel )
        SpmpEventWrite((const struct _EVENT_DESCRIPTOR *)LSAEVENT_LOOKUP_GC_FAILED, 0);
      v10 = 0;
      *a10 = -1073741136;
LABEL_20:
      v14 = v44;
      goto LABEL_21;
    }
    if ( v10 < 0 )
      goto LABEL_20;
    v32 = 0;
    v56 = 0;
    v33 = (unsigned int *)v18;
    while ( 1 )
    {
      Sid1 = 0;
      v34 = 0;
      v35 = v32;
      LODWORD(a10) = -1;
      *(_OWORD *)v50 = 0;
      hMem = 0;
      if ( (v15[4 * v32] & 4) != 0 )
      {
        v36 = 3LL * v33[v32];
        *(_DWORD *)(*((_QWORD *)a7 + 1) + 8 * v36 + 20) |= 2u;
      }
      if ( v13[v32] == 8 )
        goto LABEL_72;
      v37 = *(_QWORD *)(v47 + 8);
      if ( v13[v32] == 3 )
      {
        v34 = *(PSID *)(v37 + 8LL * v32);
      }
      else
      {
        v38 = LsapSplitSid(*(void **)(v37 + 8LL * v32));
        v34 = Sid1;
        v10 = v38;
        if ( v38 < 0 )
          goto LABEL_72;
      }
      WellKnownSid = (void *)LsapGetWellKnownSid(14);
      if ( RtlEqualSid(v34, WellKnownSid) )
      {
        v10 = 0;
      }
      else
      {
        if ( (unsigned __int8)LsapDbLookupListReferencedDomains(a6, v34, &a10) )
          goto LABEL_66;
        v40 = v34;
        v34 = 0;
        hMem = v40;
        DomainNameBySid = LsaDbpGetDomainNameBySid(v40, (PUNICODE_STRING)v50);
        v10 = DomainNameBySid;
        if ( DomainNameBySid == -1073741601 )
        {
          v10 = 0;
        }
        else if ( DomainNameBySid >= 0 )
        {
          v10 = LsapDbLookupAddListReferencedDomains(a6, v50, &a10);
          if ( v10 >= 0 )
          {
LABEL_66:
            v42 = 3LL * v33[v35];
            *(_DWORD *)(*((_QWORD *)a7 + 1) + 24LL * v33[v35]) = v13[v35];
            DestinationSidLength = RtlLengthSid(*(PSID *)(*(_QWORD *)(v47 + 8) + 8 * v35));
            *(_QWORD *)(*((_QWORD *)a7 + 1) + 8 * v42 + 8) = LocalAlloc(0x40u, DestinationSidLength);
            v43 = *(void **)(*((_QWORD *)a7 + 1) + 8 * v42 + 8);
            if ( v43 )
            {
              RtlCopySid(DestinationSidLength, v43, *(PSID *)(*(_QWORD *)(v47 + 8) + 8 * v35));
              *(_DWORD *)(*((_QWORD *)a7 + 1) + 8 * v42 + 16) = (_DWORD)a10;
              if ( (v46[4 * v35] & 2) == 0 )
                *(_DWORD *)(*((_QWORD *)a7 + 1) + 8 * v42 + 20) |= 1u;
              ++*a8;
              --*a9;
            }
            else
            {
              v10 = -1073741801;
            }
            v15 = v46;
          }
        }
      }
LABEL_72:
      if ( hMem && hMem != *(HLOCAL *)(*(_QWORD *)(v47 + 8) + 8 * v35) )
        LocalFree(hMem);
      if ( v50[1] )
        LocalFree(v50[1]);
      if ( v34 && v34 != *(PSID *)(*(_QWORD *)(v47 + 8) + 8 * v35) )
        LocalFree(v34);
      if ( v10 >= 0 )
      {
        v32 = v56 + 1;
        v56 = v32;
        if ( v32 < (unsigned int)v14 )
          continue;
      }
      v18 = v48;
      v17 = 0;
      goto LABEL_20;
    }
  }
  v10 = -1073741670;
  v18 = 0;
LABEL_21:
  SamIFreeSidArray(v47);
  if ( v17 )
    LocalFree(v17);
  if ( v13 )
    LocalFree(v13);
  if ( v14 )
    LocalFree(v14);
  if ( v18 )
    LocalFree(v18);
  if ( v15 )
    LocalFree(v15);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001cc08  mov     rax, rsp
0x18001cc0b  mov     [rax+10h], rbx
0x18001cc0f  mov     [rax+20h], r9
0x18001cc13  mov     [rax+18h], r8
0x18001cc17  mov     [rax+8], ecx
0x18001cc1a  push    rbp
0x18001cc1b  push    rsi
0x18001cc1c  push    rdi
0x18001cc1d  push    r12
0x18001cc1f  push    r13
0x18001cc21  push    r14
0x18001cc23  push    r15
0x18001cc25  mov     rbp, rsp
0x18001cc28  sub     rsp, 80h
0x18001cc2f  mov     rax, [rbp+arg_48]
0x18001cc36  xor     ebx, ebx
0x18001cc38  mov     esi, edx
0x18001cc3a  mov     [rbp+var_38], rbx
0x18001cc3e  mov     [rax], ebx
0x18001cc40  call    cs:__imp_SampDsIsRunning
0x18001cc46  test    al, al
0x18001cc48  jnz     short loc_18001CC51
0x18001cc4a  xor     eax, eax
0x18001cc4c  jmp     loc_18001CDE7
0x18001cc51  mov     rdx, rsi; uBytes
0x18001cc54  mov     ecx, 40h ; '@'; uFlags
0x18001cc59  mov     r12, rbx
0x18001cc5c  mov     r15, rbx
0x18001cc5f  mov     r13, rbx
0x18001cc62  call    cs:__imp_LocalAlloc
0x18001cc68  mov     r14, rax
0x18001cc6b  test    rax, rax
0x18001cc6e  jnz     short loc_18001CC7D
0x18001cc70  mov     ebx, 0C000009Ah
0x18001cc75  mov     rdi, r13
0x18001cc78  jmp     loc_18001CD95
0x18001cc7d  mov     r8, rsi; Size
0x18001cc80  mov     [rbp+DestinationSidLength], ebx
0x18001cc83  xor     edx, edx; Val
0x18001cc85  mov     dword ptr [rbp+arg_20], r15d
0x18001cc89  mov     rcx, r14; void *
0x18001cc8c  call    memset_0
0x18001cc91  xor     edx, edx
0x18001cc93  mov     edi, edx
0x18001cc95  test    esi, esi
0x18001cc97  jz      loc_18001D1A4
0x18001cc9d  mov     r12d, [rbp+arg_0]
0x18001cca1  mov     rbx, [rbp+arg_18]
0x18001cca5  mov     rcx, [rbp+arg_30]
0x18001cca9  lea     rax, [rdi+rdi*2]
0x18001ccad  mov     rcx, [rcx+8]
0x18001ccb1  cmp     dword ptr [rcx+rax*8+10h], 0FFFFFFFFh
0x18001ccb6  jnz     short loc_18001CD0C
0x18001ccb8  cmp     dword ptr [rcx+rax*8], 8
0x18001ccbc  jnz     short loc_18001CD0C
0x18001ccbe  mov     r15, rdi
0x18001ccc1  shl     r15, 4
0x18001ccc5  add     r15, rbx
0x18001ccc8  cmp     [r15], dx
0x18001cccc  jz      short loc_18001CCEB
0x18001ccce  xor     r9d, r9d; unsigned __int8 *
0x18001ccd1  mov     [rsp+80h+var_60], rdx; struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY **
0x18001ccd6  xor     r8d, r8d; void *
0x18001ccd9  mov     rdx, r15; struct _UNICODE_STRING *
0x18001ccdc  lea     ecx, [r9+1]; unsigned int
0x18001cce0  call    ?LsaDbpDomainHasDomainTrust@@YAJKPEAU_UNICODE_STRING@@PEAXPEAEPEAPEAU_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY@@@Z; LsaDbpDomainHasDomainTrust(ulong,_UNICODE_STRING *,void *,uchar *,_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY * *)
0x18001cce5  xor     edx, edx
0x18001cce7  test    eax, eax
0x18001cce9  jns     short loc_18001CD08
0x18001cceb  test    r12d, r12d
0x18001ccee  jns     short loc_18001CCF6
0x18001ccf0  cmp     [r15], dx
0x18001ccf4  jz      short loc_18001CD08
0x18001ccf6  mov     r15d, dword ptr [rbp+arg_20]
0x18001ccfa  inc     r15d
0x18001ccfd  mov     byte ptr [r14+rdi], 1
0x18001cd02  mov     dword ptr [rbp+arg_20], r15d
0x18001cd06  jmp     short loc_18001CD0C
0x18001cd08  mov     r15d, dword ptr [rbp+arg_20]
0x18001cd0c  inc     r13d
0x18001cd0f  inc     rdi
0x18001cd12  cmp     r13d, esi
0x18001cd15  jb      short loc_18001CCA5
0x18001cd17  mov     ebx, [rbp+DestinationSidLength]
0x18001cd1a  mov     r12d, ebx
0x18001cd1d  test    r15d, r15d
0x18001cd20  jz      loc_18001D196
0x18001cd26  mov     ebx, r15d
0x18001cd29  mov     ecx, 40h ; '@'; uFlags
0x18001cd2e  shl     rbx, 4
0x18001cd32  mov     rdx, rbx; uBytes
0x18001cd35  mov     edi, r15d
0x18001cd38  call    cs:__imp_LocalAlloc
0x18001cd3e  mov     [rbp+var_50], rax
0x18001cd42  mov     r13, rax
0x18001cd45  test    rax, rax
0x18001cd48  jnz     short loc_18001CD5A
0x18001cd4a  mov     ebx, 0C000009Ah
0x18001cd4f  mov     r13d, r12d
0x18001cd52  mov     edi, r12d
0x18001cd55  mov     r15, rax
0x18001cd58  jmp     short loc_18001CD95
0x18001cd5a  mov     r8, rbx; Size
0x18001cd5d  xor     edx, edx; Val
0x18001cd5f  mov     rcx, r13; void *
0x18001cd62  call    memset_0
0x18001cd67  lea     rbx, ds:0[rdi*4]
0x18001cd6f  mov     ecx, 40h ; '@'; uFlags
0x18001cd74  mov     rdx, rbx; uBytes
0x18001cd77  call    cs:__imp_LocalAlloc
0x18001cd7d  mov     [rbp+var_30], rax
0x18001cd81  mov     rdi, rax
0x18001cd84  test    rax, rax
0x18001cd87  jnz     short loc_18001CE02
0x18001cd89  mov     ebx, 0C000009Ah
0x18001cd8e  mov     r13, r12
0x18001cd91  mov     r15, [rbp+var_50]
0x18001cd95  mov     rcx, [rbp+var_38]
0x18001cd99  call    cs:__imp_SamIFreeSidArray
0x18001cd9f  test    r14, r14
0x18001cda2  jz      short loc_18001CDAD
0x18001cda4  mov     rcx, r14; hMem
0x18001cda7  call    cs:__imp_LocalFree
0x18001cdad  test    r12, r12
0x18001cdb0  jz      short loc_18001CDBB
0x18001cdb2  mov     rcx, r12; hMem
0x18001cdb5  call    cs:__imp_LocalFree
0x18001cdbb  test    r15, r15
0x18001cdbe  jz      short loc_18001CDC9
0x18001cdc0  mov     rcx, r15; hMem
0x18001cdc3  call    cs:__imp_LocalFree
0x18001cdc9  test    rdi, rdi
0x18001cdcc  jz      short loc_18001CDD7
0x18001cdce  mov     rcx, rdi; hMem
0x18001cdd1  call    cs:__imp_LocalFree
0x18001cdd7  test    r13, r13
0x18001cdda  jz      short loc_18001CDE5
0x18001cddc  mov     rcx, r13; hMem
0x18001cddf  call    cs:__imp_LocalFree
0x18001cde5  mov     eax, ebx
0x18001cde7  mov     rbx, [rsp+80h+arg_8]
0x18001cdef  add     rsp, 80h
0x18001cdf6  pop     r15
0x18001cdf8  pop     r14
0x18001cdfa  pop     r13
0x18001cdfc  pop     r12
0x18001cdfe  pop     rdi
0x18001cdff  pop     rsi
0x18001ce00  pop     rbp
0x18001ce01  retn
0x18001ce02  mov     r8, rbx; Size
0x18001ce05  xor     edx, edx; Val
0x18001ce07  mov     rcx, rdi; void *
0x18001ce0a  call    memset_0
0x18001ce0f  mov     r10, [rbp+arg_10]
0x18001ce13  xor     eax, eax
0x18001ce15  mov     edx, eax
0x18001ce17  mov     r9d, eax
0x18001ce1a  cmp     r9d, r15d
0x18001ce1d  jnb     short loc_18001CE4E
0x18001ce1f  mov     r8d, edx
0x18001ce22  cmp     [r8+r14], al
0x18001ce26  jz      short loc_18001CE48
0x18001ce28  add     r8, r8
0x18001ce2b  mov     eax, r9d
0x18001ce2e  add     rax, rax
0x18001ce31  mov     ecx, r9d
0x18001ce34  inc     r9d
0x18001ce37  movups  xmm0, xmmword ptr [r10+r8*8]
0x18001ce3c  movdqu  xmmword ptr [r13+rax*8+0], xmm0
0x18001ce43  mov     [rdi+rcx*4], edx
0x18001ce46  xor     eax, eax
0x18001ce48  inc     edx
0x18001ce4a  cmp     edx, esi
0x18001ce4c  jb      short loc_18001CE1A
0x18001ce4e  mov     rcx, r14; hMem
0x18001ce51  call    cs:__imp_LocalFree
0x18001ce57  xor     esi, esi
0x18001ce59  mov     rdx, rbx; uBytes
0x18001ce5c  mov     r14d, esi
0x18001ce5f  lea     r13d, [rsi+40h]
0x18001ce63  mov     ecx, r13d; uFlags
0x18001ce66  call    cs:__imp_LocalAlloc
0x18001ce6c  mov     r12, rax
0x18001ce6f  test    rax, rax
0x18001ce72  jnz     short loc_18001CE81
0x18001ce74  mov     ebx, 0C000009Ah
0x18001ce79  mov     r13d, esi
0x18001ce7c  jmp     loc_18001CD91
0x18001ce81  mov     r8, rbx; Size
0x18001ce84  xor     edx, edx; Val
0x18001ce86  mov     rcx, r12; void *
0x18001ce89  call    memset_0
0x18001ce8e  mov     rdx, rbx; uBytes
0x18001ce91  mov     ecx, r13d; uFlags
0x18001ce94  call    cs:__imp_LocalAlloc
0x18001ce9a  mov     [rbp+var_40], rax
0x18001ce9e  mov     r13, rax
0x18001cea1  test    rax, rax
0x18001cea4  jnz     short loc_18001CEB0
0x18001cea6  mov     ebx, 0C000009Ah
0x18001ceab  jmp     loc_18001CD91
0x18001ceb0  mov     r8, rbx; Size
0x18001ceb3  xor     edx, edx; Val
0x18001ceb5  mov     rcx, r13; void *
0x18001ceb8  call    memset_0
0x18001cebd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cec4  test    byte ptr [rcx+1Ch], 20h
0x18001cec8  jz      short loc_18001CEDF
0x18001ceca  mov     rcx, [rcx+10h]
0x18001cece  lea     r8, WPP_c0948403788e3f00547c7c2dd7a3b1b0_Traceguids
0x18001ced5  mov     edx, 0Ah
0x18001ceda  call    WPP_SF_
0x18001cedf  mov     rdx, [rbp+var_50]
0x18001cee3  lea     rax, [rbp+var_38]
0x18001cee7  mov     [rsp+80h+var_58], rax
0x18001ceec  mov     r9, r13
0x18001ceef  mov     r8d, 2
0x18001cef5  mov     [rsp+80h+var_60], r12
0x18001cefa  mov     ecx, r15d
0x18001cefd  call    cs:__imp_SamIGCLookupNames
0x18001cf03  mov     ebx, eax
0x18001cf05  test    eax, eax
0x18001cf07  jns     short loc_18001CF2E
0x18001cf09  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cf10  test    byte ptr [rcx+1Ch], 20h
0x18001cf14  jz      short loc_18001CF2E
0x18001cf16  mov     rcx, [rcx+10h]
0x18001cf1a  lea     r8, WPP_c0948403788e3f00547c7c2dd7a3b1b0_Traceguids
0x18001cf21  mov     edx, 0Bh
0x18001cf26  mov     r9d, eax
0x18001cf29  call    WPP_SF_d
0x18001cf2e  cmp     ebx, 0C00002B0h
0x18001cf34  jnz     short loc_18001CF62
0x18001cf36  cmp     cs:?LsapLookupLogLevel@@3KA, 1; ulong LsapLookupLogLevel
0x18001cf3d  jb      short loc_18001CF4E
0x18001cf3f  xor     edx, edx
0x18001cf41  lea     rcx, LSAEVENT_LOOKUP_GC_FAILED
0x18001cf48  call    cs:__imp_?SpmpEventWrite@@YAKPEBU_EVENT_DESCRIPTOR@@PEAGZZ; SpmpEventWrite(_EVENT_DESCRIPTOR const *,ushort *,...)
0x18001cf4e  mov     rax, [rbp+arg_48]
0x18001cf55  mov     ebx, esi
0x18001cf57  mov     dword ptr [rax], 0C00002B0h
0x18001cf5d  jmp     loc_18001CD91
0x18001cf62  test    ebx, ebx
0x18001cf64  js      loc_18001CD91
0x18001cf6a  mov     eax, esi
0x18001cf6c  mov     dword ptr [rbp+arg_20], eax
0x18001cf6f  test    r15d, r15d
0x18001cf72  jz      loc_18001CD91
0x18001cf78  mov     r14, rdi
0x18001cf7b  xor     ecx, ecx
0x18001cf7d  mov     [rbp+Sid1], rsi
0x18001cf81  mov     rdi, rsi
0x18001cf84  mov     [rbp+DestinationSidLength], esi
0x18001cf87  mov     esi, eax
0x18001cf89  xorps   xmm0, xmm0
0x18001cf8c  mov     dword ptr [rbp+arg_48], 0FFFFFFFFh
0x18001cf96  movups  xmmword ptr [rbp+var_20], xmm0
0x18001cf9a  mov     [rbp+hMem], rcx
0x18001cf9e  test    byte ptr [r13+rsi*4+0], 4
0x18001cfa4  jz      short loc_18001CFBB
0x18001cfa6  mov     eax, [r14+rsi*4]
0x18001cfaa  lea     rcx, [rax+rax*2]
0x18001cfae  mov     rax, [rbp+arg_30]
0x18001cfb2  mov     rax, [rax+8]
0x18001cfb6  or      dword ptr [rax+rcx*8+14h], 2
0x18001cfbb  cmp     dword ptr [r12+rsi*4], 8
0x18001cfc0  jz      loc_18001D12B
0x18001cfc6  cmp     dword ptr [r12+rsi*4], 3
0x18001cfcb  mov     rax, [rbp+var_38]
0x18001cfcf  mov     rcx, [rax+8]
0x18001cfd3  jz      short loc_18001CFF5
0x18001cfd5  mov     rcx, [rcx+rsi*8]; Src
0x18001cfd9  lea     r8, [rbp+DestinationSidLength]
0x18001cfdd  lea     rdx, [rbp+Sid1]
0x18001cfe1  call    LsapSplitSid
0x18001cfe6  mov     rdi, [rbp+Sid1]
0x18001cfea  mov     ebx, eax
0x18001cfec  test    eax, eax
0x18001cfee  jns     short loc_18001CFF9
0x18001cff0  jmp     loc_18001D12B
0x18001cff5  mov     rdi, [rcx+rsi*8]
0x18001cff9  mov     ecx, 0Eh
0x18001cffe  call    cs:__imp_LsapGetWellKnownSid
0x18001d004  mov     rdx, rax; Sid2
0x18001d007  mov     rcx, rdi; Sid1
0x18001d00a  call    cs:__imp_RtlEqualSid
0x18001d010  xor     ecx, ecx
0x18001d012  test    al, al
0x18001d014  jz      short loc_18001D01D
0x18001d016  mov     ebx, ecx
0x18001d018  jmp     loc_18001D12B
0x18001d01d  mov     rcx, [rbp+arg_28]
0x18001d021  lea     r8, [rbp+arg_48]
0x18001d028  mov     rdx, rdi
0x18001d02b  call    cs:__imp_LsapDbLookupListReferencedDomains
0x18001d031  xor     edx, edx
0x18001d033  test    al, al
0x18001d035  jnz     short loc_18001D080
0x18001d037  mov     rcx, rdi; Src
  ... truncated ...
```
