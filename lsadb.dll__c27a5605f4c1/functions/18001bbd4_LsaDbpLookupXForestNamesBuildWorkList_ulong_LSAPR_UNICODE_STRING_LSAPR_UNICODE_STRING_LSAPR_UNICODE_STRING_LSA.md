# LsaDbpLookupXForestNamesBuildWorkList(ulong,_LSAPR_UNICODE_STRING *,_LSAPR_UNICODE_STRING *,_LSAPR_UNICODE_STRING *,_LSAPR_REFERENCED_DOMAIN_LIST *,_LSAPR_TRANSLATED_SIDS_EX2 *,_LSAP_LOOKUP_LEVEL,ulong *,ulong *,_LSAP_DB_LOOKUP_WORK_LIST * *)

- ea: `0x18001bbd4`
- end: `0x18001be20`
- name: `?LsaDbpLookupXForestNamesBuildWorkList@@YAJKPEAU_LSAPR_UNICODE_STRING@@00PEAU_LSAPR_REFERENCED_DOMAIN_LIST@@PEAU_LSAPR_TRANSLATED_SIDS_EX2@@W4_LSAP_LOOKUP_LEVEL@@PEAK4PEAPEAU_LSAP_DB_LOOKUP_WORK_LIST@@@Z`
- size: `588`
- prototype: `__int64(unsigned int, __int64, __int64, __int64, __int64, __int64, ...)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001d7f4`

## callees

- `0x18001a658`
- `0x18001b020`
- `0x18001b0dc`
- `0x18001b214`
- `0x18001bbd4`
- `0x18001c088`
- `0x180032de4`

## import_xrefs

- `LSASRV!LsaIForestTrustFindMatch` at `0x18001bcbd`
- `LSASRV!LsaIForestTrustFindMatch` at `0x18001bcd5`
- `LSASRV!LsaIForestTrustFindMatch` at `0x18001bcbd`
- `LSASRV!LsaIForestTrustFindMatch` at `0x18001bcd5`
- `LSASRV!LsaIFree_LSAPR_UNICODE_STRING_BUFFER` at `0x18001bd63`
- `LSASRV!LsaIFree_LSAPR_UNICODE_STRING_BUFFER` at `0x18001bdad`
- `LSASRV!LsaIFree_LSAPR_UNICODE_STRING_BUFFER` at `0x18001bd63`
- `LSASRV!LsaIFree_LSAPR_UNICODE_STRING_BUFFER` at `0x18001bdad`
- `LSASRV!LsapCompareDomainNames` at `0x18001bcf7`
- `LSASRV!LsapCompareDomainNames` at `0x18001bcf7`

## pseudocode

```c
__int64 LsaDbpLookupXForestNamesBuildWorkList(
        unsigned int a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        ...)
{
  __int64 v7; // r12
  int WorkList; // eax
  HLOCAL v10; // rbx
  int v11; // edi
  unsigned int v12; // r14d
  __int64 v13; // rax
  unsigned int v14; // eax
  HLOCAL *v15; // r15
  __int64 v16; // rcx
  HLOCAL *v17; // rsi
  __int64 v18; // rdx
  __int64 v19; // r12
  __int64 v20; // r8
  HLOCAL hMem; // [rsp+20h] [rbp-30h] BYREF
  __int64 v23; // [rsp+28h] [rbp-28h] BYREF
  WCHAR *v24; // [rsp+30h] [rbp-20h]
  UNICODE_STRING SourceString; // [rsp+38h] [rbp-18h] BYREF
  __int64 v26; // [rsp+48h] [rbp-8h]
  __int64 v29; // [rsp+C0h] [rbp+70h] BYREF
  va_list va; // [rsp+C0h] [rbp+70h]
  __int64 v31; // [rsp+C8h] [rbp+78h]
  __int64 v32; // [rsp+D0h] [rbp+80h]
  _QWORD *v33; // [rsp+D8h] [rbp+88h]
  va_list va1; // [rsp+E0h] [rbp+90h] BYREF

  va_start(va1, a6);
  va_start(va, a6);
  v29 = va_arg(va1, _QWORD);
  v31 = va_arg(va1, _QWORD);
  v32 = va_arg(va1, _QWORD);
  v33 = va_arg(va1, _QWORD *);
  hMem = 0;
  v23 = 0;
  v26 = 0;
  SourceString = 0;
  v24 = 0;
  v7 = a3;
  WorkList = LsaDbpLookupCreateWorkList((struct _LSAP_DB_LOOKUP_WORK_LIST **)&hMem);
  v10 = hMem;
  v11 = WorkList;
  if ( WorkList >= 0 )
  {
    v12 = 0;
    v13 = v32;
    *((_DWORD *)hMem + 8) = 0;
    *((_DWORD *)v10 + 9) = 1;
    *((_DWORD *)v10 + 10) = 2;
    *((_DWORD *)v10 + 16) = a1;
    *((_DWORD *)v10 + 17) = 6;
    *((_QWORD *)v10 + 9) = a5;
    *((_QWORD *)v10 + 10) = v31;
    *((_QWORD *)v10 + 11) = v13;
    *((_QWORD *)v10 + 14) = a2;
    *((_QWORD *)v10 + 15) = a6;
    LODWORD(v29) = 0;
    if ( a1 )
    {
      v14 = 0;
      while ( 1 )
      {
        v15 = (HLOCAL *)*((_QWORD *)v10 + 2);
        v16 = 16LL * v14;
        hMem = 0;
        v17 = (HLOCAL *)*v15;
        v18 = v16 + v7;
        if ( !*(_WORD *)(v16 + v7) )
        {
          v19 = v16 + a4;
          if ( (int)LsaIForestTrustFindMatch(2, v16 + a4, &v23) >= 0 )
            break;
          v18 = v19;
        }
        if ( (int)LsaIForestTrustFindMatch(1, v18, &v23) >= 0 )
          break;
        v11 = 0;
LABEL_18:
        v7 = a3;
        LODWORD(v29) = ++v12;
        v14 = v12;
        if ( v12 >= a1 )
          goto LABEL_19;
      }
      while ( v17 != v15 )
      {
        if ( (unsigned __int8)LsapCompareDomainNames(v17 + 3, &v23, 0) )
        {
          if ( v17 )
            goto LABEL_15;
          break;
        }
        v17 = (HLOCAL *)*v17;
      }
      *(_DWORD *)&SourceString.Length = v23;
      SourceString.Buffer = v24;
      *(_DWORD *)(&SourceString.MaximumLength + 1) = 0;
      v26 = 0;
      v11 = LsaDbpLookupCreateWorkItem(&SourceString, -1, v20, (struct _LSAP_DB_LOOKUP_WORK_ITEM **)&hMem);
      if ( v11 < 0 )
        goto LABEL_19;
      v17 = (HLOCAL *)hMem;
      v11 = LsaDbpAddWorkItemToWorkList(
              (struct _LSAP_DB_LOOKUP_WORK_LIST *)v10,
              (struct _LSAP_DB_LOOKUP_WORK_ITEM *)hMem);
      if ( v11 < 0 )
        goto LABEL_19;
      *((_DWORD *)v17 + 5) |= 2u;
LABEL_15:
      LsaIFree_LSAPR_UNICODE_STRING_BUFFER(&v23);
      v24 = 0;
      v11 = LsaDbpLookupAddIndicesToWorkItem((struct _LSAP_DB_LOOKUP_WORK_ITEM *)v17, 1u, (unsigned int *)va);
      if ( v11 >= 0 )
      {
        v12 = v29;
        goto LABEL_18;
      }
    }
LABEL_19:
    if ( v24 )
    {
      LsaIFree_LSAPR_UNICODE_STRING_BUFFER(&v23);
      v24 = 0;
    }
    if ( v11 >= 0 )
    {
      if ( *((_DWORD *)v10 + 14) )
      {
        v11 = 0;
        *((_DWORD *)v10 + 24) = *((_DWORD *)v10 + 14) - 1;
        LsaDbpUpdateMappedCountsWorkList((struct _LSAP_DB_LOOKUP_WORK_LIST *)v10);
        goto LABEL_26;
      }
      v11 = -1073741709;
    }
  }
  if ( v10 )
  {
    LsaDbpLookupDeleteWorkList(v10);
    v10 = 0;
  }
LABEL_26:
  *v33 = v10;
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18001bbd4  mov     [rsp-38h+arg_0], rbx
0x18001bbd9  mov     [rsp-38h+arg_18], r9
0x18001bbde  mov     [rsp-38h+arg_10], r8
0x18001bbe3  push    rbp
0x18001bbe4  push    rsi
0x18001bbe5  push    rdi
0x18001bbe6  push    r12
0x18001bbe8  push    r13
0x18001bbea  push    r14
0x18001bbec  push    r15
0x18001bbee  mov     rbp, rsp
0x18001bbf1  sub     rsp, 50h
0x18001bbf5  xor     r15d, r15d
0x18001bbf8  mov     r13d, ecx
0x18001bbfb  xorps   xmm0, xmm0
0x18001bbfe  mov     [rbp+hMem], r15
0x18001bc02  xor     eax, eax
0x18001bc04  mov     [rbp+var_28], r15
0x18001bc08  lea     rcx, [rbp+hMem]; struct _LSAP_DB_LOOKUP_WORK_LIST **
0x18001bc0c  mov     [rbp+var_8], rax
0x18001bc10  movups  xmmword ptr [rbp+SourceString.Length], xmm0
0x18001bc14  mov     [rbp+var_20], r15
0x18001bc18  mov     r12, r8
0x18001bc1b  mov     rsi, rdx
0x18001bc1e  call    ?LsaDbpLookupCreateWorkList@@YAJPEAPEAU_LSAP_DB_LOOKUP_WORK_LIST@@@Z; LsaDbpLookupCreateWorkList(_LSAP_DB_LOOKUP_WORK_LIST * *)
0x18001bc23  mov     rbx, [rbp+hMem]
0x18001bc27  mov     edi, eax
0x18001bc29  test    eax, eax
0x18001bc2b  js      loc_18001BDC6
0x18001bc31  mov     rcx, [rbp+arg_20]
0x18001bc35  mov     r14d, r15d
0x18001bc38  mov     rax, [rbp+arg_40]
0x18001bc3f  mov     [rbx+20h], r15d
0x18001bc43  mov     dword ptr [rbx+24h], 1
0x18001bc4a  mov     dword ptr [rbx+28h], 2
0x18001bc51  mov     [rbx+40h], r13d
0x18001bc55  mov     dword ptr [rbx+44h], 6
0x18001bc5c  mov     [rbx+48h], rcx
0x18001bc60  mov     rcx, [rbp+arg_38]
0x18001bc64  mov     [rbx+50h], rcx
0x18001bc68  mov     [rbx+58h], rax
0x18001bc6c  mov     rax, [rbp+arg_28]
0x18001bc70  mov     [rbx+70h], rsi
0x18001bc74  mov     [rbx+78h], rax
0x18001bc78  mov     dword ptr [rbp+arg_30], r15d
0x18001bc7c  test    r13d, r13d
0x18001bc7f  jz      loc_18001BDA3
0x18001bc85  mov     eax, r15d
0x18001bc88  mov     r15, [rbx+10h]
0x18001bc8c  lea     r8, [rbp+var_28]
0x18001bc90  mov     ecx, eax
0x18001bc92  shl     rcx, 4
0x18001bc96  mov     [rbp+hMem], 0
0x18001bc9e  mov     rsi, [r15]
0x18001bca1  lea     rdx, [rcx+r12]
0x18001bca5  xor     r12d, r12d
0x18001bca8  cmp     [rdx], r12w
0x18001bcac  jnz     short loc_18001BCD0
0x18001bcae  mov     r12, [rbp+arg_18]
0x18001bcb2  add     r12, rcx
0x18001bcb5  mov     ecx, 2
0x18001bcba  mov     rdx, r12
0x18001bcbd  call    cs:__imp_LsaIForestTrustFindMatch
0x18001bcc3  mov     edi, eax
0x18001bcc5  test    eax, eax
0x18001bcc7  jns     short loc_18001BD08
0x18001bcc9  lea     r8, [rbp+var_28]
0x18001bccd  mov     rdx, r12
0x18001bcd0  mov     ecx, 1
0x18001bcd5  call    cs:__imp_LsaIForestTrustFindMatch
0x18001bcdb  mov     edi, eax
0x18001bcdd  test    eax, eax
0x18001bcdf  jns     short loc_18001BD08
0x18001bce1  xor     r15d, r15d
0x18001bce4  mov     edi, r15d
0x18001bce7  jmp     loc_18001BD8C
0x18001bcec  lea     rcx, [rsi+18h]
0x18001bcf0  xor     r8d, r8d
0x18001bcf3  lea     rdx, [rbp+var_28]
0x18001bcf7  call    cs:__imp_LsapCompareDomainNames
0x18001bcfd  test    al, al
0x18001bcff  jnz     loc_18001BDFA
0x18001bd05  mov     rsi, [rsi]
0x18001bd08  cmp     rsi, r15
0x18001bd0b  jnz     short loc_18001BCEC
0x18001bd0d  xor     r15d, r15d
0x18001bd10  movzx   eax, word ptr [rbp+var_28]
0x18001bd14  lea     r9, [rbp+hMem]; struct _LSAP_DB_LOOKUP_WORK_ITEM **
0x18001bd18  mov     [rbp+SourceString.Length], ax
0x18001bd1c  lea     rcx, [rbp+SourceString]; SourceString
0x18001bd20  movzx   eax, word ptr [rbp+var_28+2]
0x18001bd24  or      edx, 0FFFFFFFFh; int
0x18001bd27  mov     [rbp+SourceString.MaximumLength], ax
0x18001bd2b  mov     rax, [rbp+var_20]
0x18001bd2f  mov     [rbp+SourceString.Buffer], rax
0x18001bd33  mov     dword ptr [rbp+SourceString+4], r15d
0x18001bd37  mov     [rbp+var_8], r15
0x18001bd3b  call    ?LsaDbpLookupCreateWorkItem@@YAJPEAU_LSAPR_TRUST_INFORMATION@@JKPEAPEAU_LSAP_DB_LOOKUP_WORK_ITEM@@@Z; LsaDbpLookupCreateWorkItem(_LSAPR_TRUST_INFORMATION *,long,ulong,_LSAP_DB_LOOKUP_WORK_ITEM * *)
0x18001bd40  mov     edi, eax
0x18001bd42  test    eax, eax
0x18001bd44  js      short loc_18001BDA3
0x18001bd46  mov     rsi, [rbp+hMem]
0x18001bd4a  mov     rcx, rbx; struct _LSAP_DB_LOOKUP_WORK_LIST *
0x18001bd4d  mov     rdx, rsi; struct _LSAP_DB_LOOKUP_WORK_ITEM *
0x18001bd50  call    ?LsaDbpAddWorkItemToWorkList@@YAJPEAU_LSAP_DB_LOOKUP_WORK_LIST@@PEAU_LSAP_DB_LOOKUP_WORK_ITEM@@@Z; LsaDbpAddWorkItemToWorkList(_LSAP_DB_LOOKUP_WORK_LIST *,_LSAP_DB_LOOKUP_WORK_ITEM *)
0x18001bd55  mov     edi, eax
0x18001bd57  test    eax, eax
0x18001bd59  js      short loc_18001BDA3
0x18001bd5b  or      dword ptr [rsi+14h], 2
0x18001bd5f  lea     rcx, [rbp+var_28]
0x18001bd63  call    cs:__imp_LsaIFree_LSAPR_UNICODE_STRING_BUFFER
0x18001bd69  mov     [rbp+var_20], r15
0x18001bd6d  test    edi, edi
0x18001bd6f  js      short loc_18001BDC6
0x18001bd71  lea     r8, [rbp+arg_30]; unsigned int *
0x18001bd75  mov     edx, 1; unsigned int
0x18001bd7a  mov     rcx, rsi; struct _LSAP_DB_LOOKUP_WORK_ITEM *
0x18001bd7d  call    ?LsaDbpLookupAddIndicesToWorkItem@@YAJPEAU_LSAP_DB_LOOKUP_WORK_ITEM@@KPEAK@Z; LsaDbpLookupAddIndicesToWorkItem(_LSAP_DB_LOOKUP_WORK_ITEM *,ulong,ulong *)
0x18001bd82  mov     edi, eax
0x18001bd84  test    eax, eax
0x18001bd86  js      short loc_18001BDA3
0x18001bd88  mov     r14d, dword ptr [rbp+arg_30]
0x18001bd8c  mov     r12, [rbp+arg_10]
0x18001bd90  inc     r14d
0x18001bd93  mov     dword ptr [rbp+arg_30], r14d
0x18001bd97  mov     eax, r14d
0x18001bd9a  cmp     r14d, r13d
0x18001bd9d  jb      loc_18001BC88
0x18001bda3  cmp     [rbp+var_20], r15
0x18001bda7  jz      short loc_18001BDB7
0x18001bda9  lea     rcx, [rbp+var_28]
0x18001bdad  call    cs:__imp_LsaIFree_LSAPR_UNICODE_STRING_BUFFER
0x18001bdb3  mov     [rbp+var_20], r15
0x18001bdb7  test    edi, edi
0x18001bdb9  js      short loc_18001BDC6
0x18001bdbb  cmp     [rbx+38h], r15d
0x18001bdbf  jnz     short loc_18001BE0B
0x18001bdc1  mov     edi, 0C0000073h
0x18001bdc6  test    rbx, rbx
0x18001bdc9  jz      short loc_18001BDD6
0x18001bdcb  mov     rcx, rbx; hMem
0x18001bdce  call    ?LsaDbpLookupDeleteWorkList@@YAJPEAU_LSAP_DB_LOOKUP_WORK_LIST@@@Z; LsaDbpLookupDeleteWorkList(_LSAP_DB_LOOKUP_WORK_LIST *)
0x18001bdd3  mov     rbx, r15
0x18001bdd6  mov     rax, [rbp+arg_48]
0x18001bddd  mov     [rax], rbx
0x18001bde0  mov     eax, edi
0x18001bde2  mov     rbx, [rsp+50h+arg_0]
0x18001bdea  add     rsp, 50h
0x18001bdee  pop     r15
0x18001bdf0  pop     r14
0x18001bdf2  pop     r13
0x18001bdf4  pop     r12
0x18001bdf6  pop     rdi
0x18001bdf7  pop     rsi
0x18001bdf8  pop     rbp
0x18001bdf9  retn
0x18001bdfa  xor     r15d, r15d
0x18001bdfd  test    rsi, rsi
0x18001be00  jz      loc_18001BD10
0x18001be06  jmp     loc_18001BD5F
0x18001be0b  mov     eax, [rbx+38h]
0x18001be0e  mov     rcx, rbx; struct _LSAP_DB_LOOKUP_WORK_LIST *
0x18001be11  dec     eax
0x18001be13  mov     edi, r15d
0x18001be16  mov     [rbx+60h], eax
0x18001be19  call    ?LsaDbpUpdateMappedCountsWorkList@@YAXPEAU_LSAP_DB_LOOKUP_WORK_LIST@@@Z; LsaDbpUpdateMappedCountsWorkList(_LSAP_DB_LOOKUP_WORK_LIST *)
0x18001be1e  jmp     short loc_18001BDD6
```
