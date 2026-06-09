# LsaDbrQueryForestTrustInformationWorker(void *,_UNICODE_STRING *,LSA_FOREST_TRUST_RECORD_TYPE,_LSA_FOREST_TRUST_INFORMATION2 * *)

- ea: `0x180027f28`
- end: `0x180028287`
- name: `?LsaDbrQueryForestTrustInformationWorker@@YAJPEAXPEAU_UNICODE_STRING@@W4LSA_FOREST_TRUST_RECORD_TYPE@@PEAPEAU_LSA_FOREST_TRUST_INFORMATION2@@@Z`
- size: `863`
- prototype: `int(void *, struct _UNICODE_STRING *, enum LSA_FOREST_TRUST_RECORD_TYPE, struct _LSA_FOREST_TRUST_INFORMATION2 **)`
- caller_count: `4`
- callee_count: `9`
- tags: ``

## callers

- `0x180027e30`
- `0x180027e50`
- `0x18002f640`
- `0x180031abc`

## callees

- `0x180001fb8`
- `0x18000bf70`
- `0x18000c0e0`
- `0x18000fd18`
- `0x18000fd40`
- `0x180012fa4`
- `0x180027f28`
- `0x18002aa14`
- `0x180036e6c`

## import_xrefs

- `LSASRV!LsapDbCloseObject` at `0x1800281fc`
- `LSASRV!LsapDbCloseObject` at `0x1800281fc`
- `LSASRV!LsapDbOpenObject` at `0x180028160`
- `LSASRV!LsapDbOpenObject` at `0x180028160`
- `LSASRV!LsapTraceEvent` at `0x180027fa0`
- `LSASRV!LsapTraceEvent` at `0x18002823e`
- `LSASRV!LsapTraceEvent` at `0x180027fa0`
- `LSASRV!LsapTraceEvent` at `0x18002823e`
- `LSASRV!LsapDbDereferenceObject` at `0x18002822e`
- `LSASRV!LsapDbDereferenceObject` at `0x18002822e`
- `LSASRV!LsapDbExpAcquireReadLockTrustedDomainList` at `0x180028091`
- `LSASRV!LsapDbExpAcquireReadLockTrustedDomainList` at `0x180028091`
- `LSASRV!LsapDbReferenceObject` at `0x180028054`
- `LSASRV!LsapDbReferenceObject` at `0x180028054`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x180028207`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x180028207`

## pseudocode

```c
__int64 __fastcall LsaDbrQueryForestTrustInformationWorker(
        void *a1,
        struct _UNICODE_STRING *a2,
        unsigned int a3,
        struct _LSA_FOREST_TRUST_INFORMATION2 **a4)
{
  char v7; // r14
  char v8; // r15
  unsigned __int8 v9; // dl
  unsigned __int8 v10; // r8
  unsigned __int8 v11; // r9
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  unsigned int v14; // ebx
  int LockTrustedDomainList; // eax
  __int64 v16; // rcx
  __int64 v17; // rdx
  int v18; // eax
  struct _UNICODE_STRING *v19; // rdi
  int v20; // ebx
  __int64 v21; // rdx
  unsigned __int16 v23; // [rsp+28h] [rbp-39h]
  unsigned __int16 *v24; // [rsp+30h] [rbp-31h]
  struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *v25; // [rsp+38h] [rbp-29h] BYREF
  _QWORD v26[8]; // [rsp+48h] [rbp-19h] BYREF
  int v27; // [rsp+88h] [rbp+27h]
  int v28; // [rsp+8Ch] [rbp+2Bh]
  void *v29; // [rsp+C8h] [rbp+67h] BYREF
  __int64 v30; // [rsp+E0h] [rbp+7Fh] BYREF

  v29 = a1;
  memset_0(v26, 0, 0x48u);
  v30 = 0;
  v7 = 0;
  v8 = 0;
  v25 = 0;
  *a4 = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 285, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
  LsapTraceEvent(1, 18);
  if ( !LsapValidateUnicodeStringWorker(a2, v9, v10, v11, v23, v24) )
  {
    v12 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v21 = 286;
      goto LABEL_37;
    }
LABEL_38:
    v14 = -1073741811;
    goto LABEL_39;
  }
  *a4 = 0;
  if ( (int)a3 > 4 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 287, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids, a3);
    goto LABEL_38;
  }
  if ( !DcInRootDomain )
  {
    v12 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
    {
LABEL_11:
      v14 = -1073741603;
      goto LABEL_39;
    }
    v13 = 288;
LABEL_10:
    WPP_SF_(v12[2], v13, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
    goto LABEL_11;
  }
  if ( !LsaDbpNoMoreWin2KForest() )
  {
    v12 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_11;
    v13 = 289;
    goto LABEL_10;
  }
  LockTrustedDomainList = LsapDbReferenceObject(v29, 0, 1, 2);
  v14 = LockTrustedDomainList;
  if ( LockTrustedDomainList < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_39;
    v17 = 290;
    goto LABEL_18;
  }
  v7 = 1;
  LockTrustedDomainList = LsapDbExpAcquireReadLockTrustedDomainList(v16);
  v14 = LockTrustedDomainList;
  if ( LockTrustedDomainList < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_39;
    v17 = 291;
    goto LABEL_18;
  }
  v8 = 1;
  v18 = LsaDbpLookupNameTrustedDomainListEx((struct _LSAPR_UNICODE_STRING *)a2, &v25);
  v14 = v18;
  if ( v18 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_ZD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        292,
        (unsigned int)&WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids,
        (_DWORD)a2,
        v18);
    goto LABEL_39;
  }
  v19 = (struct _UNICODE_STRING *)((char *)v25 + 16);
  v20 = *((_DWORD *)v25 + 16);
  if ( !LsaDbpNoMoreWin2KForest() || (v20 & 8) == 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v21 = 293;
LABEL_37:
      WPP_SF_(v12[2], v21, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
      goto LABEL_38;
    }
    goto LABEL_38;
  }
  v26[2] = v29;
  v28 = 64;
  v26[1] = 48;
  memset(&v26[4], 0, 32);
  v27 = 0;
  v26[0] = 2;
  v26[3] = v19;
  LockTrustedDomainList = LsapDbOpenObject(v26, 64, 0, &v30, 50331649);
  v14 = LockTrustedDomainList;
  if ( LockTrustedDomainList < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_39;
    v17 = 294;
LABEL_18:
    WPP_SF_d(v12[2], v17, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids, (unsigned int)LockTrustedDomainList);
    goto LABEL_39;
  }
  LockTrustedDomainList = FTCache::Retrieve(g_FTCache, v19, a4);
  v14 = LockTrustedDomainList;
  if ( LockTrustedDomainList < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v17 = 295;
      goto LABEL_18;
    }
  }
LABEL_39:
  if ( v30 )
    LsapDbCloseObject(&v30, 0, v14);
  if ( v8 )
    LsapDbExpReleaseLockTrustedDomainList(v12);
  if ( v7 )
    v14 = LsapDbDereferenceObject(&v29, 1, 2, 50331649, 0, v14);
  LsapTraceEvent(2, 18);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 296, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids, v14);
  return v14;
}

```

## disassembly

```asm
0x180027f28  mov     rax, rsp
0x180027f2b  mov     [rax+10h], rbx
0x180027f2f  mov     [rax+18h], rsi
0x180027f33  mov     [rax+8], rcx
0x180027f37  push    rbp
0x180027f38  push    rdi
0x180027f39  push    r12
0x180027f3b  push    r14
0x180027f3d  push    r15
0x180027f3f  lea     rbp, [rax-5Fh]
0x180027f43  sub     rsp, 90h
0x180027f4a  mov     rdi, rdx
0x180027f4d  lea     rcx, [rbp+57h+var_70]; void *
0x180027f51  xor     edx, edx; Val
0x180027f53  mov     ebx, r8d
0x180027f56  mov     rsi, r9
0x180027f59  lea     r8d, [rdx+48h]; Size
0x180027f5d  call    memset_0
0x180027f62  xor     r12d, r12d
0x180027f65  mov     [rbp+57h+arg_18], r12
0x180027f69  mov     r14b, r12b
0x180027f6c  mov     r15b, r12b
0x180027f6f  mov     [rbp+57h+var_80], r12
0x180027f73  mov     [rsi], r12
0x180027f76  mov     rcx, cs:WPP_GLOBAL_Control
0x180027f7d  test    byte ptr [rcx+1Ch], 8
0x180027f81  jz      short loc_180027F98
0x180027f83  mov     rcx, [rcx+10h]
0x180027f87  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x180027f8e  mov     edx, 11Dh
0x180027f93  call    WPP_SF_
0x180027f98  mov     edx, 12h
0x180027f9d  lea     ecx, [rdx-11h]
0x180027fa0  call    cs:__imp_LsapTraceEvent
0x180027fa6  mov     rcx, rdi; SearchString
0x180027fa9  call    ?LsapValidateUnicodeStringWorker@@YAEPEAU_UNICODE_STRING@@EEEGPEAG@Z; LsapValidateUnicodeStringWorker(_UNICODE_STRING *,uchar,uchar,uchar,ushort,ushort *)
0x180027fae  test    al, al
0x180027fb0  jz      loc_1800281C6
0x180027fb6  mov     [rsi], r12
0x180027fb9  cmp     ebx, 4
0x180027fbc  jle     short loc_180027FEC
0x180027fbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180027fc5  test    byte ptr [rcx+1Ch], 8
0x180027fc9  jz      loc_1800281E8
0x180027fcf  mov     rcx, [rcx+10h]
0x180027fd3  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x180027fda  mov     edx, 11Fh
0x180027fdf  mov     r9d, ebx
0x180027fe2  call    WPP_SF_d
0x180027fe7  jmp     loc_1800281E8
0x180027fec  cmp     cs:?DcInRootDomain@@3EA, r12b; uchar DcInRootDomain
0x180027ff3  jnz     short loc_180028021
0x180027ff5  mov     rcx, cs:WPP_GLOBAL_Control
0x180027ffc  test    byte ptr [rcx+1Ch], 8
0x180028000  jz      short loc_180028017
0x180028002  mov     edx, 120h
0x180028007  mov     rcx, [rcx+10h]
0x18002800b  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x180028012  call    WPP_SF_
0x180028017  mov     ebx, 0C00000DDh
0x18002801c  jmp     loc_1800281ED
0x180028021  call    ?LsaDbpNoMoreWin2KForest@@YAEXZ; LsaDbpNoMoreWin2KForest(void)
0x180028026  test    al, al
0x180028028  jnz     short loc_18002803E
0x18002802a  mov     rcx, cs:WPP_GLOBAL_Control
0x180028031  test    byte ptr [rcx+1Ch], 8
0x180028035  jz      short loc_180028017
0x180028037  mov     edx, 121h
0x18002803c  jmp     short loc_180028007
0x18002803e  mov     rcx, [rbp+57h+arg_0]
0x180028042  xor     edx, edx
0x180028044  mov     dword ptr [rsp+0B0h+var_90], 3000001h
0x18002804c  lea     r9d, [rdx+2]
0x180028050  lea     r8d, [rdx+1]
0x180028054  call    cs:__imp_LsapDbReferenceObject
0x18002805a  mov     ebx, eax
0x18002805c  test    eax, eax
0x18002805e  jns     short loc_18002808E
0x180028060  mov     rcx, cs:WPP_GLOBAL_Control
0x180028067  test    byte ptr [rcx+1Ch], 8
0x18002806b  jz      loc_1800281ED
0x180028071  mov     edx, 122h
0x180028076  mov     rcx, [rcx+10h]
0x18002807a  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x180028081  mov     r9d, eax
0x180028084  call    WPP_SF_d
0x180028089  jmp     loc_1800281ED
0x18002808e  mov     r14b, 1
0x180028091  call    cs:__imp_LsapDbExpAcquireReadLockTrustedDomainList
0x180028097  mov     ebx, eax
0x180028099  test    eax, eax
0x18002809b  jns     short loc_1800280B5
0x18002809d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800280a4  test    byte ptr [rcx+1Ch], 8
0x1800280a8  jz      loc_1800281ED
0x1800280ae  mov     edx, 123h
0x1800280b3  jmp     short loc_180028076
0x1800280b5  lea     rdx, [rbp+57h+var_80]; struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY **
0x1800280b9  mov     rcx, rdi; struct _LSAPR_UNICODE_STRING *
0x1800280bc  mov     r15b, r14b
0x1800280bf  call    ?LsaDbpLookupNameTrustedDomainListEx@@YAJPEAU_LSAPR_UNICODE_STRING@@PEAPEAU_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY@@@Z; LsaDbpLookupNameTrustedDomainListEx(_LSAPR_UNICODE_STRING *,_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY * *)
0x1800280c4  mov     ebx, eax
0x1800280c6  test    eax, eax
0x1800280c8  jns     short loc_1800280FC
0x1800280ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800280d1  test    byte ptr [rcx+1Ch], 8
0x1800280d5  jz      loc_1800281ED
0x1800280db  mov     rcx, [rcx+10h]
0x1800280df  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x1800280e6  mov     edx, 124h
0x1800280eb  mov     dword ptr [rsp+0B0h+var_90], eax
0x1800280ef  mov     r9, rdi
0x1800280f2  call    WPP_SF_ZD
0x1800280f7  jmp     loc_1800281ED
0x1800280fc  mov     rdi, [rbp+57h+var_80]
0x180028100  add     rdi, 10h
0x180028104  mov     ebx, [rdi+30h]
0x180028107  call    ?LsaDbpNoMoreWin2KForest@@YAEXZ; LsaDbpNoMoreWin2KForest(void)
0x18002810c  test    al, al
0x18002810e  jz      loc_1800281B2
0x180028114  test    bl, 8
0x180028117  jz      loc_1800281B2
0x18002811d  mov     rax, [rbp+57h+arg_0]
0x180028121  lea     r9, [rbp+57h+arg_18]
0x180028125  mov     edx, 40h ; '@'
0x18002812a  mov     [rbp+57h+var_60], rax
0x18002812e  xor     r8d, r8d
0x180028131  mov     [rbp+57h+var_2C], edx
0x180028134  lea     rcx, [rbp+57h+var_70]
0x180028138  mov     [rbp+57h+var_68], 30h ; '0'
0x180028140  mov     [rbp+57h+var_50], r12
0x180028144  mov     [rbp+57h+var_30], r12d
0x180028148  mov     [rbp+57h+var_70], 2
0x180028150  mov     [rbp+57h+var_38], r12
0x180028154  mov     [rbp+57h+var_58], rdi
0x180028158  mov     [rbp+57h+var_48], r12
0x18002815c  mov     [rbp+57h+var_40], r12
0x180028160  call    cs:__imp_LsapDbOpenObject
0x180028166  mov     ebx, eax
0x180028168  test    eax, eax
0x18002816a  jns     short loc_180028183
0x18002816c  mov     rcx, cs:WPP_GLOBAL_Control
0x180028173  test    byte ptr [rcx+1Ch], 8
0x180028177  jz      short loc_1800281ED
0x180028179  mov     edx, 126h
0x18002817e  jmp     loc_180028076
0x180028183  mov     rcx, cs:?g_FTCache@@3PEAVFTCache@@EA; this
0x18002818a  mov     r8, rsi; struct _LSA_FOREST_TRUST_INFORMATION2 **
0x18002818d  mov     rdx, rdi; struct _UNICODE_STRING *
0x180028190  call    ?Retrieve@FTCache@@QEAAJPEAU_UNICODE_STRING@@PEAPEAU_LSA_FOREST_TRUST_INFORMATION2@@@Z; FTCache::Retrieve(_UNICODE_STRING *,_LSA_FOREST_TRUST_INFORMATION2 * *)
0x180028195  mov     ebx, eax
0x180028197  test    eax, eax
0x180028199  jns     short loc_1800281ED
0x18002819b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800281a2  test    byte ptr [rcx+1Ch], 8
0x1800281a6  jz      short loc_1800281ED
0x1800281a8  mov     edx, 127h
0x1800281ad  jmp     loc_180028076
0x1800281b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800281b9  test    byte ptr [rcx+1Ch], 8
0x1800281bd  jz      short loc_1800281E8
0x1800281bf  mov     edx, 125h
0x1800281c4  jmp     short loc_1800281D8
0x1800281c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800281cd  test    byte ptr [rcx+1Ch], 8
0x1800281d1  jz      short loc_1800281E8
0x1800281d3  mov     edx, 11Eh
0x1800281d8  mov     rcx, [rcx+10h]
0x1800281dc  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x1800281e3  call    WPP_SF_
0x1800281e8  mov     ebx, 0C000000Dh
0x1800281ed  cmp     [rbp+57h+arg_18], r12
0x1800281f1  jz      short loc_180028202
0x1800281f3  mov     r8d, ebx
0x1800281f6  lea     rcx, [rbp+57h+arg_18]
0x1800281fa  xor     edx, edx
0x1800281fc  call    cs:__imp_LsapDbCloseObject
0x180028202  test    r15b, r15b
0x180028205  jz      short loc_18002820D
0x180028207  call    cs:__imp_LsapDbExpReleaseLockTrustedDomainList
0x18002820d  test    r14b, r14b
0x180028210  jz      short loc_180028236
0x180028212  mov     edx, 1
0x180028217  mov     dword ptr [rsp+0B0h+var_88], ebx
0x18002821b  mov     r9d, 3000001h
0x180028221  mov     dword ptr [rsp+0B0h+var_90], r12d
0x180028226  lea     rcx, [rbp+57h+arg_0]
0x18002822a  lea     r8d, [rdx+1]
0x18002822e  call    cs:__imp_LsapDbDereferenceObject
0x180028234  mov     ebx, eax
0x180028236  mov     edx, 12h
0x18002823b  lea     ecx, [rdx-10h]
0x18002823e  call    cs:__imp_LsapTraceEvent
0x180028244  mov     rcx, cs:WPP_GLOBAL_Control
0x18002824b  test    byte ptr [rcx+1Ch], 8
0x18002824f  jz      short loc_180028269
0x180028251  mov     rcx, [rcx+10h]
0x180028255  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x18002825c  mov     edx, 128h
0x180028261  mov     r9d, ebx
0x180028264  call    WPP_SF_d
0x180028269  lea     r11, [rsp+0B0h+var_20]
0x180028271  mov     eax, ebx
0x180028273  mov     rbx, [r11+38h]
0x180028277  mov     rsi, [r11+40h]
0x18002827b  mov     rsp, r11
0x18002827e  pop     r15
0x180028280  pop     r14
0x180028282  pop     r12
0x180028284  pop     rdi
0x180028285  pop     rbp
0x180028286  retn
```
