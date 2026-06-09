# LsaDbpInsertTrustedDomainList(_LSAPR_TRUSTED_DOMAIN_INFORMATION_EX2 *,ulong)

- ea: `0x18000bae8`
- end: `0x18000bd78`
- name: `?LsaDbpInsertTrustedDomainList@@YAJPEAU_LSAPR_TRUSTED_DOMAIN_INFORMATION_EX2@@K@Z`
- size: `656`
- prototype: `__int64 __fastcall(struct _LSAPR_TRUSTED_DOMAIN_INFORMATION_EX2 *, unsigned int)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x180009b24`
- `0x18000a2bc`
- `0x180013cbc`

## callees

- `0x18000988c`
- `0x180009ec4`
- `0x18000b990`
- `0x18000bae8`
- `0x18000bf70`
- `0x18000c4f0`
- `0x18000fd18`
- `0x18000fd40`
- `0x18000fde0`
- `0x18002a7f8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000bb99`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000bb99`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bbe2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bc75`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bbe2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bc75`
- `LSASRV!_fgu__LSAPR_TRUSTED_DOMAIN_INFO` at `0x18000bbd9`
- `LSASRV!_fgu__LSAPR_TRUSTED_DOMAIN_INFO` at `0x18000bc6c`
- `LSASRV!_fgu__LSAPR_TRUSTED_DOMAIN_INFO` at `0x18000bbd9`
- `LSASRV!_fgu__LSAPR_TRUSTED_DOMAIN_INFO` at `0x18000bc6c`
- `LSASRV!LsapDbExpMakeCacheInvalid` at `0x18000bbb3`
- `LSASRV!LsapDbExpMakeCacheInvalid` at `0x18000bbb3`
- `LSASRV!__imp_?SpmpEventWrite@@YAKPEBU_EVENT_DESCRIPTOR@@PEAGZZ` at `0x18000bc5d`
- `LSASRV!__imp_?SpmpEventWrite@@YAKPEBU_EVENT_DESCRIPTOR@@PEAGZZ` at `0x18000bc5d`

## pseudocode

```c
__int64 __fastcall LsaDbpInsertTrustedDomainList(struct _LSAPR_TRUSTED_DOMAIN_INFORMATION_EX2 *a1, int a2)
{
  struct _UNICODE_STRING *v5; // rbx
  __int64 v6; // rcx
  int v7; // eax
  struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *v8; // rax
  struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *v9; // rdi
  struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *v10; // rcx
  int v11; // eax
  struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY **v12; // rcx
  __int64 v13; // rcx
  struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY **v14; // rdx
  int v15; // eax
  struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY **v16; // rdx
  int v17; // [rsp+60h] [rbp+30h] BYREF
  struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *v18; // [rsp+70h] [rbp+40h] BYREF
  struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *v19; // [rsp+78h] [rbp+48h] BYREF

  v17 = 0;
  v18 = 0;
  if ( !a1 )
    return 0;
  v5 = 0;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_d732922acb273e81328a1f77e1e7700c_Traceguids);
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_d732922acb273e81328a1f77e1e7700c_Traceguids, a1);
  }
  LsaDbLogInfoTrustedDomainList();
  LOBYTE(v6) = 1;
  v17 = LsaDbpBuildTrustedDomainCacheIfNecessary(v6, 0);
  if ( v17 < 0 )
    goto LABEL_10;
  v7 = LsaDbpLookupNameTrustedDomainListEx(a1, &v18);
  v17 = v7;
  if ( v7 != -1073741601 )
  {
    if ( v7 )
      goto LABEL_15;
    v19 = 0;
    v17 = LsaDbpReconcileDuplicateTrusts((struct _UNICODE_STRING *)a1, &v19);
    if ( v17 < 0 )
      goto LABEL_10;
    v13 = *(_QWORD *)v18;
    if ( *(struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY **)(*(_QWORD *)v18 + 8LL) == v18 )
    {
      v14 = (struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY **)*((_QWORD *)v18 + 1);
      if ( *v14 == v18 )
      {
        *v14 = (struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *)v13;
        *(_QWORD *)(v13 + 8) = v14;
        v10 = v19;
        v15 = LsaDbpTrustedDomainList - 1;
        v5 = (struct _UNICODE_STRING *)v18;
        --LsaDbpTrustedDomainList;
        if ( v19 )
        {
          LsaDbpTrustedDomainList = v15 + 1;
          *((_DWORD *)v19 + 24) = ++*(&LsaDbpTrustedDomainList + 1);
          v16 = (struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY **)qword_1800480C0;
          if ( *(HLOCAL **)qword_1800480C0 != &hMem )
            goto LABEL_32;
          *(_QWORD *)v10 = &hMem;
          *((_QWORD *)v10 + 1) = v16;
          *v16 = v10;
          qword_1800480C0 = (__int64)v10;
        }
LABEL_11:
        if ( v5 )
        {
          if ( DcInRootDomain )
            FTCache::Remove(v10, v5 + 1);
          _fgu__LSAPR_TRUSTED_DOMAIN_INFO(&v5[1], 6);
          LocalFree(v5);
        }
        goto LABEL_15;
      }
    }
LABEL_32:
    __fastfail(3u);
  }
  v8 = (struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *)LocalAlloc(0x40u, 0x78u);
  v9 = v8;
  if ( !v8 )
  {
    v17 = -1073741670;
LABEL_10:
    LsapDbExpMakeCacheInvalid(2);
    goto LABEL_11;
  }
  v11 = LsaDbpInitializeTrustedDomainListEntry(v8, a1, a2);
  v17 = v11;
  if ( v11 != -1073741811 )
  {
    if ( v11 < 0 )
    {
      v5 = (struct _UNICODE_STRING *)v9;
      goto LABEL_10;
    }
    ++LsaDbpTrustedDomainList;
    *((_DWORD *)v9 + 24) = ++*(&LsaDbpTrustedDomainList + 1);
    v12 = (struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY **)qword_1800480C0;
    if ( *(HLOCAL **)qword_1800480C0 == &hMem )
    {
      *(_QWORD *)v9 = &hMem;
      *((_QWORD *)v9 + 1) = v12;
      *v12 = v9;
      qword_1800480C0 = (__int64)v9;
      goto LABEL_24;
    }
    goto LABEL_32;
  }
  SpmpEventWrite((const struct _EVENT_DESCRIPTOR *)LSA_TRUST_INSERT_ERROR, L"ub", (char *)v9 + 16, 4, &v17);
  _fgu__LSAPR_TRUSTED_DOMAIN_INFO((char *)v9 + 16, 6);
  LocalFree(v9);
LABEL_24:
  v17 = 0;
LABEL_15:
  LsaDbLogInfoTrustedDomainList();
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      33,
      &WPP_d732922acb273e81328a1f77e1e7700c_Traceguids,
      (unsigned int)v17);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x18000bae8  push    rbp
0x18000baea  push    rbx
0x18000baeb  push    rsi
0x18000baec  push    rdi
0x18000baed  push    r14
0x18000baef  mov     rbp, rsp
0x18000baf2  sub     rsp, 30h
0x18000baf6  mov     [rbp+arg_0], 0
0x18000bafd  mov     r14d, edx
0x18000bb00  mov     [rbp+arg_10], 0
0x18000bb08  mov     rsi, rcx
0x18000bb0b  test    rcx, rcx
0x18000bb0e  jnz     short loc_18000BB17
0x18000bb10  xor     eax, eax
0x18000bb12  jmp     loc_18000BC19
0x18000bb17  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bb1e  xor     ebx, ebx
0x18000bb20  test    dword ptr [rcx+1Ch], 100h
0x18000bb27  jz      short loc_18000BB62
0x18000bb29  mov     rcx, [rcx+10h]
0x18000bb2d  lea     edx, [rbx+1Fh]
0x18000bb30  lea     r8, WPP_d732922acb273e81328a1f77e1e7700c_Traceguids
0x18000bb37  call    WPP_SF_
0x18000bb3c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bb43  test    dword ptr [rcx+1Ch], 100h
0x18000bb4a  jz      short loc_18000BB62
0x18000bb4c  mov     rcx, [rcx+10h]
0x18000bb50  lea     edx, [rbx+20h]
0x18000bb53  mov     r9, rsi
0x18000bb56  lea     r8, WPP_d732922acb273e81328a1f77e1e7700c_Traceguids
0x18000bb5d  call    WPP_SF_Z
0x18000bb62  call    ?LsaDbLogInfoTrustedDomainList@@YAXXZ; LsaDbLogInfoTrustedDomainList(void)
0x18000bb67  xor     edx, edx; unsigned __int8
0x18000bb69  mov     cl, 1; unsigned __int8
0x18000bb6b  call    ?LsaDbpBuildTrustedDomainCacheIfNecessary@@YAJEE@Z; LsaDbpBuildTrustedDomainCacheIfNecessary(uchar,uchar)
0x18000bb70  mov     [rbp+arg_0], eax
0x18000bb73  test    eax, eax
0x18000bb75  js      short loc_18000BBAE
0x18000bb77  lea     rdx, [rbp+arg_10]; struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY **
0x18000bb7b  mov     rcx, rsi; struct _LSAPR_UNICODE_STRING *
0x18000bb7e  call    ?LsaDbpLookupNameTrustedDomainListEx@@YAJPEAU_LSAPR_UNICODE_STRING@@PEAPEAU_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY@@@Z; LsaDbpLookupNameTrustedDomainListEx(_LSAPR_UNICODE_STRING *,_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY * *)
0x18000bb83  mov     [rbp+arg_0], eax
0x18000bb86  cmp     eax, 0C00000DFh
0x18000bb8b  jnz     loc_18000BCD0
0x18000bb91  mov     edx, 78h ; 'x'; uBytes
0x18000bb96  lea     ecx, [rdx-38h]; uFlags
0x18000bb99  call    cs:__imp_LocalAlloc
0x18000bb9f  mov     rdi, rax
0x18000bba2  test    rax, rax
0x18000bba5  jnz     short loc_18000BC24
0x18000bba7  mov     [rbp+arg_0], 0C000009Ah
0x18000bbae  mov     ecx, 2
0x18000bbb3  call    cs:__imp_LsapDbExpMakeCacheInvalid
0x18000bbb9  test    rbx, rbx
0x18000bbbc  jz      short loc_18000BBE8
0x18000bbbe  cmp     cs:?DcInRootDomain@@3EA, 0; uchar DcInRootDomain
0x18000bbc5  jz      short loc_18000BBD0
0x18000bbc7  lea     rdx, [rbx+10h]; struct _UNICODE_STRING *
0x18000bbcb  call    ?Remove@FTCache@@QEAAJPEAU_UNICODE_STRING@@@Z; FTCache::Remove(_UNICODE_STRING *)
0x18000bbd0  mov     edx, 6
0x18000bbd5  lea     rcx, [rbx+10h]
0x18000bbd9  call    cs:__imp__fgu__LSAPR_TRUSTED_DOMAIN_INFO
0x18000bbdf  mov     rcx, rbx; hMem
0x18000bbe2  call    cs:__imp_LocalFree
0x18000bbe8  call    ?LsaDbLogInfoTrustedDomainList@@YAXXZ; LsaDbLogInfoTrustedDomainList(void)
0x18000bbed  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bbf4  test    dword ptr [rcx+1Ch], 100h
0x18000bbfb  jz      short loc_18000BC16
0x18000bbfd  mov     r9d, [rbp+arg_0]
0x18000bc01  lea     r8, WPP_d732922acb273e81328a1f77e1e7700c_Traceguids
0x18000bc08  mov     rcx, [rcx+10h]
0x18000bc0c  mov     edx, 21h ; '!'
0x18000bc11  call    WPP_SF_d
0x18000bc16  mov     eax, [rbp+arg_0]
0x18000bc19  add     rsp, 30h
0x18000bc1d  pop     r14
0x18000bc1f  pop     rdi
0x18000bc20  pop     rsi
0x18000bc21  pop     rbx
0x18000bc22  pop     rbp
0x18000bc23  retn
0x18000bc24  mov     r8d, r14d; unsigned int
0x18000bc27  mov     rdx, rsi; struct _LSAPR_TRUSTED_DOMAIN_INFORMATION_EX2 *
0x18000bc2a  mov     rcx, rdi; struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *
0x18000bc2d  call    ?LsaDbpInitializeTrustedDomainListEntry@@YAJPEAU_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY@@PEAU_LSAPR_TRUSTED_DOMAIN_INFORMATION_EX2@@K@Z; LsaDbpInitializeTrustedDomainListEntry(_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *,_LSAPR_TRUSTED_DOMAIN_INFORMATION_EX2 *,ulong)
0x18000bc32  mov     [rbp+arg_0], eax
0x18000bc35  cmp     eax, 0C000000Dh
0x18000bc3a  jnz     short loc_18000BC7D
0x18000bc3c  lea     rax, [rbp+arg_0]
0x18000bc40  mov     r9d, 4
0x18000bc46  lea     r8, [rdi+10h]
0x18000bc4a  mov     [rsp+30h+var_10], rax
0x18000bc4f  lea     rdx, aUb; "ub"
0x18000bc56  lea     rcx, LSA_TRUST_INSERT_ERROR
0x18000bc5d  call    cs:__imp_?SpmpEventWrite@@YAKPEBU_EVENT_DESCRIPTOR@@PEAGZZ; SpmpEventWrite(_EVENT_DESCRIPTOR const *,ushort *,...)
0x18000bc63  mov     edx, 6
0x18000bc68  lea     rcx, [rdi+10h]
0x18000bc6c  call    cs:__imp__fgu__LSAPR_TRUSTED_DOMAIN_INFO
0x18000bc72  mov     rcx, rdi; hMem
0x18000bc75  call    cs:__imp_LocalFree
0x18000bc7b  jmp     short loc_18000BCC8
0x18000bc7d  test    eax, eax
0x18000bc7f  jns     short loc_18000BC89
0x18000bc81  mov     rbx, rdi
0x18000bc84  jmp     loc_18000BBAE
0x18000bc89  mov     eax, dword ptr cs:?LsaDbpTrustedDomainList@@3U_LSAP_DB_TRUSTED_DOMAIN_LIST@@A+4; _LSAP_DB_TRUSTED_DOMAIN_LIST LsaDbpTrustedDomainList
0x18000bc8f  inc     dword ptr cs:?LsaDbpTrustedDomainList@@3U_LSAP_DB_TRUSTED_DOMAIN_LIST@@A; _LSAP_DB_TRUSTED_DOMAIN_LIST LsaDbpTrustedDomainList
0x18000bc95  inc     eax
0x18000bc97  mov     dword ptr cs:?LsaDbpTrustedDomainList@@3U_LSAP_DB_TRUSTED_DOMAIN_LIST@@A+4, eax; _LSAP_DB_TRUSTED_DOMAIN_LIST LsaDbpTrustedDomainList
0x18000bc9d  mov     [rdi+60h], eax
0x18000bca0  lea     rax, hMem
0x18000bca7  mov     rcx, cs:qword_1800480C0
0x18000bcae  cmp     [rcx], rax
0x18000bcb1  jnz     loc_18000BD71
0x18000bcb7  mov     [rdi], rax
0x18000bcba  mov     [rdi+8], rcx
0x18000bcbe  mov     [rcx], rdi
0x18000bcc1  mov     cs:qword_1800480C0, rdi
0x18000bcc8  mov     [rbp+arg_0], ebx
0x18000bccb  jmp     loc_18000BBE8
0x18000bcd0  test    eax, eax
0x18000bcd2  jnz     loc_18000BBE8
0x18000bcd8  lea     rdx, [rbp+arg_18]; struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY **
0x18000bcdc  mov     [rbp+arg_18], rbx
0x18000bce0  mov     rcx, rsi; struct _UNICODE_STRING *
0x18000bce3  call    ?LsaDbpReconcileDuplicateTrusts@@YAJPEAU_UNICODE_STRING@@PEAPEAU_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY@@@Z; LsaDbpReconcileDuplicateTrusts(_UNICODE_STRING *,_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY * *)
0x18000bce8  mov     [rbp+arg_0], eax
0x18000bceb  test    eax, eax
0x18000bced  js      loc_18000BBAE
0x18000bcf3  mov     rax, [rbp+arg_10]
0x18000bcf7  mov     rcx, [rax]
0x18000bcfa  cmp     [rcx+8], rax
0x18000bcfe  jnz     short loc_18000BD71
0x18000bd00  mov     rdx, [rax+8]
0x18000bd04  cmp     [rdx], rax
0x18000bd07  jnz     short loc_18000BD71
0x18000bd09  mov     [rdx], rcx
0x18000bd0c  mov     [rcx+8], rdx
0x18000bd10  mov     eax, dword ptr cs:?LsaDbpTrustedDomainList@@3U_LSAP_DB_TRUSTED_DOMAIN_LIST@@A; _LSAP_DB_TRUSTED_DOMAIN_LIST LsaDbpTrustedDomainList
0x18000bd16  mov     rcx, [rbp+arg_18]
0x18000bd1a  dec     eax
0x18000bd1c  mov     rbx, [rbp+arg_10]
0x18000bd20  mov     dword ptr cs:?LsaDbpTrustedDomainList@@3U_LSAP_DB_TRUSTED_DOMAIN_LIST@@A, eax; _LSAP_DB_TRUSTED_DOMAIN_LIST LsaDbpTrustedDomainList
0x18000bd26  test    rcx, rcx
0x18000bd29  jz      loc_18000BBB9
0x18000bd2f  inc     eax
0x18000bd31  mov     dword ptr cs:?LsaDbpTrustedDomainList@@3U_LSAP_DB_TRUSTED_DOMAIN_LIST@@A, eax; _LSAP_DB_TRUSTED_DOMAIN_LIST LsaDbpTrustedDomainList
0x18000bd37  mov     eax, dword ptr cs:?LsaDbpTrustedDomainList@@3U_LSAP_DB_TRUSTED_DOMAIN_LIST@@A+4; _LSAP_DB_TRUSTED_DOMAIN_LIST LsaDbpTrustedDomainList
0x18000bd3d  inc     eax
0x18000bd3f  mov     dword ptr cs:?LsaDbpTrustedDomainList@@3U_LSAP_DB_TRUSTED_DOMAIN_LIST@@A+4, eax; _LSAP_DB_TRUSTED_DOMAIN_LIST LsaDbpTrustedDomainList
0x18000bd45  mov     [rcx+60h], eax
0x18000bd48  lea     rax, hMem
0x18000bd4f  mov     rdx, cs:qword_1800480C0
0x18000bd56  cmp     [rdx], rax
0x18000bd59  jnz     short loc_18000BD71
0x18000bd5b  mov     [rcx], rax
0x18000bd5e  mov     [rcx+8], rdx
0x18000bd62  mov     [rdx], rcx
0x18000bd65  mov     cs:qword_1800480C0, rcx
0x18000bd6c  jmp     loc_18000BBB9
0x18000bd71  mov     ecx, 3
0x18000bd76  int     29h; Win8: RtlFailFast(ecx)
```
