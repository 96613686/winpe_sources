# LsaDbpLookupXForestSidsBuildWorkList(ulong,_LSAPR_SID * *,_LSAPR_REFERENCED_DOMAIN_LIST *,_LSAPR_TRANSLATED_NAMES_EX *,_LSAP_LOOKUP_LEVEL,ulong *,ulong *,_LSAP_DB_LOOKUP_WORK_LIST * *)

- ea: `0x18001be28`
- end: `0x18001c082`
- name: `?LsaDbpLookupXForestSidsBuildWorkList@@YAJKPEAPEAU_LSAPR_SID@@PEAU_LSAPR_REFERENCED_DOMAIN_LIST@@PEAU_LSAPR_TRANSLATED_NAMES_EX@@W4_LSAP_LOOKUP_LEVEL@@PEAK4PEAPEAU_LSAP_DB_LOOKUP_WORK_LIST@@@Z`
- size: `602`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001edf4`

## callees

- `0x180001670`
- `0x18001a658`
- `0x18001b020`
- `0x18001b0dc`
- `0x18001b214`
- `0x18001be28`
- `0x18001c088`
- `0x180032de4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetWindowsAccountDomainSid` at `0x18001bef4`
- `api-ms-win-security-base-l1-1-0!GetWindowsAccountDomainSid` at `0x18001bef4`
- `LSASRV!LsaIForestTrustFindMatch` at `0x18001bf0d`
- `LSASRV!LsaIForestTrustFindMatch` at `0x18001bf0d`
- `LSASRV!LsaIFree_LSAPR_UNICODE_STRING_BUFFER` at `0x18001bfb2`
- `LSASRV!LsaIFree_LSAPR_UNICODE_STRING_BUFFER` at `0x18001c015`
- `LSASRV!LsaIFree_LSAPR_UNICODE_STRING_BUFFER` at `0x18001bfb2`
- `LSASRV!LsaIFree_LSAPR_UNICODE_STRING_BUFFER` at `0x18001c015`
- `LSASRV!LsapCompareDomainNames` at `0x18001bf3b`
- `LSASRV!LsapCompareDomainNames` at `0x18001bf3b`

## pseudocode

```c
__int64 __fastcall LsaDbpLookupXForestSidsBuildWorkList(
        unsigned int a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        _QWORD *a8)
{
  int WorkList; // eax
  __int64 v13; // rbx
  int v14; // esi
  unsigned int v15; // r14d
  __int64 v16; // rax
  void *v17; // rcx
  __int64 v18; // r8
  struct _LSAP_DB_LOOKUP_WORK_ITEM **v19; // rsi
  struct _LSAP_DB_LOOKUP_WORK_ITEM *i; // rdi
  unsigned int v22; // [rsp+20h] [rbp-91h] BYREF
  __int64 v23; // [rsp+28h] [rbp-89h] BYREF
  WCHAR *v24; // [rsp+30h] [rbp-81h]
  DWORD cbDomainSid[2]; // [rsp+38h] [rbp-79h] BYREF
  struct _LSAP_DB_LOOKUP_WORK_ITEM *v26; // [rsp+40h] [rbp-71h] BYREF
  UNICODE_STRING SourceString; // [rsp+48h] [rbp-69h] BYREF
  __int64 v28; // [rsp+58h] [rbp-59h]
  _BYTE pDomainSid[72]; // [rsp+60h] [rbp-51h] BYREF

  v28 = 0;
  v23 = 0;
  v24 = 0;
  SourceString = 0;
  *(_QWORD *)cbDomainSid = 0;
  WorkList = LsaDbpLookupCreateWorkList((struct _LSAP_DB_LOOKUP_WORK_LIST **)cbDomainSid);
  v13 = *(_QWORD *)cbDomainSid;
  v14 = WorkList;
  if ( WorkList < 0 )
    goto LABEL_24;
  *(_DWORD *)(*(_QWORD *)cbDomainSid + 40LL) = 1;
  *(_DWORD *)(v13 + 64) = a1;
  *(_DWORD *)(v13 + 68) = 6;
  *(_QWORD *)(v13 + 72) = a3;
  v15 = 0;
  *(_QWORD *)(v13 + 80) = a6;
  *(_QWORD *)(v13 + 88) = a7;
  *(_QWORD *)(v13 + 112) = a2;
  *(_QWORD *)(v13 + 120) = a4;
  v22 = 0;
  if ( a1 )
  {
    v16 = 0;
    do
    {
      cbDomainSid[0] = 0;
      v17 = *(void **)(a2 + 8 * v16);
      cbDomainSid[0] = 68;
      if ( GetWindowsAccountDomainSid(v17, pDomainSid, cbDomainSid) )
      {
        if ( (int)LsaIForestTrustFindMatch(0, pDomainSid, &v23) >= 0 )
        {
          v19 = *(struct _LSAP_DB_LOOKUP_WORK_ITEM ***)(v13 + 16);
          v26 = 0;
          for ( i = *v19; i != (struct _LSAP_DB_LOOKUP_WORK_ITEM *)v19; i = *(struct _LSAP_DB_LOOKUP_WORK_ITEM **)i )
          {
            if ( (unsigned __int8)LsapCompareDomainNames((char *)i + 24, &v23, 0) )
            {
              if ( i )
                goto LABEL_16;
              break;
            }
          }
          *(_DWORD *)&SourceString.Length = v23;
          SourceString.Buffer = v24;
          *(_DWORD *)(&SourceString.MaximumLength + 1) = 0;
          v28 = 0;
          v14 = LsaDbpLookupCreateWorkItem(&SourceString, -1, v18, &v26);
          if ( v14 < 0 )
            break;
          i = v26;
          v14 = LsaDbpAddWorkItemToWorkList((struct _LSAP_DB_LOOKUP_WORK_LIST *)v13, v26);
          if ( v14 < 0 )
            break;
          *((_DWORD *)i + 5) |= 2u;
LABEL_16:
          LsaIFree_LSAPR_UNICODE_STRING_BUFFER(&v23);
          v24 = 0;
          v14 = LsaDbpLookupAddIndicesToWorkItem(i, 1u, &v22);
          if ( v14 < 0 )
            break;
          v15 = v22;
          *(_DWORD *)(32LL * v22 + *(_QWORD *)(*(_QWORD *)(v13 + 120) + 8LL) + 24) = *((_DWORD *)i + 12);
        }
        else
        {
          v14 = 0;
        }
      }
      v22 = ++v15;
      v16 = v15;
    }
    while ( v15 < a1 );
  }
  if ( v24 )
  {
    LsaIFree_LSAPR_UNICODE_STRING_BUFFER(&v23);
    v24 = 0;
  }
  if ( v14 >= 0 && (v14 = -1073741709, *(_DWORD *)(v13 + 56)) )
  {
    v14 = 0;
    *(_DWORD *)(v13 + 96) = *(_DWORD *)(v13 + 56) - 1;
    LsaDbpUpdateMappedCountsWorkList((struct _LSAP_DB_LOOKUP_WORK_LIST *)v13);
    *a8 = v13;
  }
  else
  {
LABEL_24:
    if ( v13 )
      LsaDbpLookupDeleteWorkList((HLOCAL)v13);
    *a8 = 0;
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18001be28  push    rbp
0x18001be2a  push    rbx
0x18001be2b  push    rsi
0x18001be2c  push    rdi
0x18001be2d  push    r12
0x18001be2f  push    r13
0x18001be31  push    r14
0x18001be33  push    r15
0x18001be35  lea     rbp, [rsp-7]
0x18001be3a  sub     rsp, 0B8h
0x18001be41  mov     rax, cs:__security_cookie
0x18001be48  xor     rax, rsp
0x18001be4b  mov     [rbp+3Fh+var_48], rax
0x18001be4f  mov     r12, [rbp+3Fh+arg_38]
0x18001be56  xor     eax, eax
0x18001be58  mov     r15d, ecx
0x18001be5b  mov     [rbp+3Fh+var_98], rax
0x18001be5f  xorps   xmm0, xmm0
0x18001be62  mov     [rsp+0F0h+var_C8], rax
0x18001be67  lea     rcx, [rbp+3Fh+cbDomainSid]; struct _LSAP_DB_LOOKUP_WORK_LIST **
0x18001be6b  mov     [rsp+0F0h+var_C0], rax
0x18001be70  movups  xmmword ptr [rbp+3Fh+SourceString.Length], xmm0
0x18001be74  mov     rdi, r9
0x18001be77  mov     qword ptr [rbp+3Fh+cbDomainSid], 0
0x18001be7f  mov     r14, r8
0x18001be82  mov     r13, rdx
0x18001be85  call    ?LsaDbpLookupCreateWorkList@@YAJPEAPEAU_LSAP_DB_LOOKUP_WORK_LIST@@@Z; LsaDbpLookupCreateWorkList(_LSAP_DB_LOOKUP_WORK_LIST * *)
0x18001be8a  mov     rbx, qword ptr [rbp+3Fh+cbDomainSid]
0x18001be8e  mov     esi, eax
0x18001be90  test    eax, eax
0x18001be92  js      loc_18001C04B
0x18001be98  mov     rcx, [rbp+3Fh+arg_28]
0x18001be9c  mov     dword ptr [rbx+28h], 1
0x18001bea3  mov     [rbx+40h], r15d
0x18001bea7  mov     dword ptr [rbx+44h], 6
0x18001beae  mov     [rbx+48h], r14
0x18001beb2  xor     r14d, r14d
0x18001beb5  mov     [rbx+50h], rcx
0x18001beb9  mov     rcx, [rbp+3Fh+arg_30]
0x18001bebd  mov     [rbx+58h], rcx
0x18001bec1  mov     [rbx+70h], r13
0x18001bec5  mov     [rbx+78h], rdi
0x18001bec9  mov     [rsp+0F0h+var_D0], r14d
0x18001bece  test    r15d, r15d
0x18001bed1  jz      loc_18001C008
0x18001bed7  xor     eax, eax
0x18001bed9  mov     [rbp+3Fh+cbDomainSid], 0
0x18001bee0  lea     r8, [rbp+3Fh+cbDomainSid]; cbDomainSid
0x18001bee4  mov     rcx, [r13+rax*8+0]; pSid
0x18001bee9  lea     rdx, [rbp+3Fh+pDomainSid]; pDomainSid
0x18001beed  mov     [rbp+3Fh+cbDomainSid], 44h ; 'D'
0x18001bef4  call    cs:__imp_GetWindowsAccountDomainSid
0x18001befa  test    eax, eax
0x18001befc  jz      loc_18001BFF4
0x18001bf02  lea     r8, [rsp+0F0h+var_C8]
0x18001bf07  xor     ecx, ecx
0x18001bf09  lea     rdx, [rbp+3Fh+pDomainSid]
0x18001bf0d  call    cs:__imp_LsaIForestTrustFindMatch
0x18001bf13  test    eax, eax
0x18001bf15  jns     short loc_18001BF1E
0x18001bf17  xor     esi, esi
0x18001bf19  jmp     loc_18001BFF4
0x18001bf1e  mov     rsi, [rbx+10h]
0x18001bf22  mov     [rbp+3Fh+var_B0], 0
0x18001bf2a  mov     rdi, [rsi]
0x18001bf2d  jmp     short loc_18001BF48
0x18001bf2f  lea     rcx, [rdi+18h]
0x18001bf33  xor     r8d, r8d
0x18001bf36  lea     rdx, [rsp+0F0h+var_C8]
0x18001bf3b  call    cs:__imp_LsapCompareDomainNames
0x18001bf41  test    al, al
0x18001bf43  jnz     short loc_18001BF4F
0x18001bf45  mov     rdi, [rdi]
0x18001bf48  cmp     rdi, rsi
0x18001bf4b  jnz     short loc_18001BF2F
0x18001bf4d  jmp     short loc_18001BF54
0x18001bf4f  test    rdi, rdi
0x18001bf52  jnz     short loc_18001BFAD
0x18001bf54  movzx   eax, word ptr [rsp+0F0h+var_C8]
0x18001bf59  lea     r9, [rbp+3Fh+var_B0]; struct _LSAP_DB_LOOKUP_WORK_ITEM **
0x18001bf5d  mov     [rbp+3Fh+SourceString.Length], ax
0x18001bf61  lea     rcx, [rbp+3Fh+SourceString]; SourceString
0x18001bf65  movzx   eax, word ptr [rsp+0F0h+var_C8+2]
0x18001bf6a  or      edx, 0FFFFFFFFh; int
0x18001bf6d  mov     [rbp+3Fh+SourceString.MaximumLength], ax
0x18001bf71  mov     rax, [rsp+0F0h+var_C0]
0x18001bf76  mov     [rbp+3Fh+SourceString.Buffer], rax
0x18001bf7a  mov     dword ptr [rbp+3Fh+SourceString+4], 0
0x18001bf81  mov     [rbp+3Fh+var_98], 0
0x18001bf89  call    ?LsaDbpLookupCreateWorkItem@@YAJPEAU_LSAPR_TRUST_INFORMATION@@JKPEAPEAU_LSAP_DB_LOOKUP_WORK_ITEM@@@Z; LsaDbpLookupCreateWorkItem(_LSAPR_TRUST_INFORMATION *,long,ulong,_LSAP_DB_LOOKUP_WORK_ITEM * *)
0x18001bf8e  mov     esi, eax
0x18001bf90  test    eax, eax
0x18001bf92  js      short loc_18001C008
0x18001bf94  mov     rdi, [rbp+3Fh+var_B0]
0x18001bf98  mov     rcx, rbx; struct _LSAP_DB_LOOKUP_WORK_LIST *
0x18001bf9b  mov     rdx, rdi; struct _LSAP_DB_LOOKUP_WORK_ITEM *
0x18001bf9e  call    ?LsaDbpAddWorkItemToWorkList@@YAJPEAU_LSAP_DB_LOOKUP_WORK_LIST@@PEAU_LSAP_DB_LOOKUP_WORK_ITEM@@@Z; LsaDbpAddWorkItemToWorkList(_LSAP_DB_LOOKUP_WORK_LIST *,_LSAP_DB_LOOKUP_WORK_ITEM *)
0x18001bfa3  mov     esi, eax
0x18001bfa5  test    eax, eax
0x18001bfa7  js      short loc_18001C008
0x18001bfa9  or      dword ptr [rdi+14h], 2
0x18001bfad  lea     rcx, [rsp+0F0h+var_C8]
0x18001bfb2  call    cs:__imp_LsaIFree_LSAPR_UNICODE_STRING_BUFFER
0x18001bfb8  lea     r8, [rsp+0F0h+var_D0]; unsigned int *
0x18001bfbd  mov     [rsp+0F0h+var_C0], 0
0x18001bfc6  mov     edx, 1; unsigned int
0x18001bfcb  mov     rcx, rdi; struct _LSAP_DB_LOOKUP_WORK_ITEM *
0x18001bfce  call    ?LsaDbpLookupAddIndicesToWorkItem@@YAJPEAU_LSAP_DB_LOOKUP_WORK_ITEM@@KPEAK@Z; LsaDbpLookupAddIndicesToWorkItem(_LSAP_DB_LOOKUP_WORK_ITEM *,ulong,ulong *)
0x18001bfd3  mov     esi, eax
0x18001bfd5  test    eax, eax
0x18001bfd7  js      short loc_18001C008
0x18001bfd9  mov     rax, [rbx+78h]
0x18001bfdd  mov     r14d, [rsp+0F0h+var_D0]
0x18001bfe2  mov     edx, r14d
0x18001bfe5  shl     rdx, 5
0x18001bfe9  mov     rcx, [rax+8]
0x18001bfed  mov     eax, [rdi+30h]
0x18001bff0  mov     [rdx+rcx+18h], eax
0x18001bff4  inc     r14d
0x18001bff7  mov     [rsp+0F0h+var_D0], r14d
0x18001bffc  mov     eax, r14d
0x18001bfff  cmp     r14d, r15d
0x18001c002  jb      loc_18001BED9
0x18001c008  cmp     [rsp+0F0h+var_C0], 0
0x18001c00e  jz      short loc_18001C024
0x18001c010  lea     rcx, [rsp+0F0h+var_C8]
0x18001c015  call    cs:__imp_LsaIFree_LSAPR_UNICODE_STRING_BUFFER
0x18001c01b  mov     [rsp+0F0h+var_C0], 0
0x18001c024  test    esi, esi
0x18001c026  js      short loc_18001C04B
0x18001c028  cmp     dword ptr [rbx+38h], 0
0x18001c02c  mov     esi, 0C0000073h
0x18001c031  jz      short loc_18001C04B
0x18001c033  mov     eax, [rbx+38h]
0x18001c036  xor     esi, esi
0x18001c038  dec     eax
0x18001c03a  mov     rcx, rbx; struct _LSAP_DB_LOOKUP_WORK_LIST *
0x18001c03d  mov     [rbx+60h], eax
0x18001c040  call    ?LsaDbpUpdateMappedCountsWorkList@@YAXPEAU_LSAP_DB_LOOKUP_WORK_LIST@@@Z; LsaDbpUpdateMappedCountsWorkList(_LSAP_DB_LOOKUP_WORK_LIST *)
0x18001c045  mov     [r12], rbx
0x18001c049  jmp     short loc_18001C060
0x18001c04b  test    rbx, rbx
0x18001c04e  jz      short loc_18001C058
0x18001c050  mov     rcx, rbx; hMem
0x18001c053  call    ?LsaDbpLookupDeleteWorkList@@YAJPEAU_LSAP_DB_LOOKUP_WORK_LIST@@@Z; LsaDbpLookupDeleteWorkList(_LSAP_DB_LOOKUP_WORK_LIST *)
0x18001c058  mov     qword ptr [r12], 0
0x18001c060  mov     eax, esi
0x18001c062  mov     rcx, [rbp+3Fh+var_48]
0x18001c066  xor     rcx, rsp; StackCookie
0x18001c069  call    __security_check_cookie
0x18001c06e  add     rsp, 0B8h
0x18001c075  pop     r15
0x18001c077  pop     r14
0x18001c079  pop     r13
0x18001c07b  pop     r12
0x18001c07d  pop     rdi
0x18001c07e  pop     rsi
0x18001c07f  pop     rbx
0x18001c080  pop     rbp
0x18001c081  retn
```
