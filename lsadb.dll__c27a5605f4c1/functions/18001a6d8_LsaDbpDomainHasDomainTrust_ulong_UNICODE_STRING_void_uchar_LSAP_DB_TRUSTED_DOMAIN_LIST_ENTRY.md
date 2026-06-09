# LsaDbpDomainHasDomainTrust(ulong,_UNICODE_STRING *,void *,uchar *,_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY * *)

- ea: `0x18001a6d8`
- end: `0x18001a88c`
- name: `?LsaDbpDomainHasDomainTrust@@YAJKPEAU_UNICODE_STRING@@PEAXPEAEPEAPEAU_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY@@@Z`
- size: `436`
- prototype: `int(unsigned int, struct _UNICODE_STRING *, void *, unsigned __int8 *, struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY **)`
- caller_count: `6`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001b2d4`
- `0x18001b94c`
- `0x18001c938`
- `0x18001cc08`
- `0x18001de20`
- `0x18001e968`

## callees

- `0x180009ec4`
- `0x18000beb4`
- `0x18000bf70`
- `0x18001a6d8`
- `0x18001abec`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a86c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a86c`
- `LSASRV!LsapDbExpAcquireReadLockTrustedDomainList` at `0x18001a72f`
- `LSASRV!LsapDbExpAcquireReadLockTrustedDomainList` at `0x18001a72f`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x18001a857`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x18001a857`
- `ntdll!RtlInitUnicodeString` at `0x18001a71b`
- `ntdll!RtlInitUnicodeString` at `0x18001a786`
- `ntdll!RtlInitUnicodeString` at `0x18001a71b`
- `ntdll!RtlInitUnicodeString` at `0x18001a786`

## pseudocode

```c
__int64 __fastcall LsaDbpDomainHasDomainTrust(
        char a1,
        struct _UNICODE_STRING *a2,
        void *a3,
        unsigned __int8 *a4,
        struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY **a5)
{
  struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY **v5; // r15
  struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *v6; // rdi
  __int64 v10; // rcx
  int LockTrustedDomainList; // ebx
  int v12; // eax
  void *v13; // rcx
  bool v14; // r13
  char v15; // r12
  char v16; // si
  int DomainNameBySid; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-30h] BYREF
  struct _UNICODE_STRING v20; // [rsp+30h] [rbp-20h] BYREF
  void *v21; // [rsp+40h] [rbp-10h]
  struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *v23; // [rsp+A8h] [rbp+58h] BYREF

  v5 = a5;
  v6 = 0;
  v23 = 0;
  DestinationString = 0;
  if ( a5 )
    *a5 = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  if ( !a4 || (LOBYTE(a5) = 0, !*a4) )
  {
    LockTrustedDomainList = LsapDbExpAcquireReadLockTrustedDomainList(v10);
    if ( LockTrustedDomainList < 0 )
      goto LABEL_39;
    LOBYTE(a5) = 1;
  }
  if ( a2 )
  {
    v12 = LsaDbpLookupNameTrustedDomainListEx((struct _LSAPR_UNICODE_STRING *)a2, &v23);
    v6 = v23;
  }
  else
  {
    v21 = 0;
    LOBYTE(v10) = 1;
    v23 = 0;
    v20 = 0;
    if ( (int)LsaDbpBuildTrustedDomainCacheIfNecessary(v10, 0) < 0 )
      goto LABEL_34;
    v21 = a3;
    RtlInitUnicodeString(&v20, 0);
    v12 = LsaDbpLookupEntryTrustedDomainList((struct _LSAPR_TRUST_INFORMATION *)&v20, &v23);
    if ( v12 >= 0 )
      v6 = v23;
  }
  if ( v12 >= 0 && (*((_BYTE *)v6 + 56) & 2) != 0 )
  {
    v13 = (void *)*((unsigned int *)v6 + 15);
    if ( (unsigned int)((_DWORD)v13 - 1) <= 1 )
    {
      v14 = 0;
      v15 = 0;
      v16 = 0;
      if ( (_DWORD)v13 == 2 )
      {
        if ( *((_QWORD *)v6 + 6) )
          v14 = (*((_BYTE *)v6 + 64) & 8) != 0;
      }
      else if ( (_DWORD)v13 != 1 )
      {
LABEL_24:
        if ( (a1 & 4) != 0 && v14 || (a1 & 1) != 0 && v15 && !v16 || (a1 & 2) != 0 && v15 && v16 )
        {
          LockTrustedDomainList = 0;
          if ( v5 )
            *v5 = v6;
          goto LABEL_35;
        }
        goto LABEL_34;
      }
      v13 = (void *)*((_QWORD *)v6 + 6);
      if ( v13 && (*((_BYTE *)v6 + 64) & 8) == 0 )
      {
        v15 = 1;
        DomainNameBySid = LsaDbpGetDomainNameBySid(v13, &DestinationString);
        LockTrustedDomainList = DomainNameBySid;
        if ( DomainNameBySid < 0 )
        {
          if ( DomainNameBySid != -1073741601 )
            goto LABEL_35;
        }
        else
        {
          v16 = 1;
        }
      }
      goto LABEL_24;
    }
  }
LABEL_34:
  LockTrustedDomainList = -1073741601;
LABEL_35:
  if ( (_BYTE)a5 )
  {
    if ( a4 )
      *a4 = 1;
    else
      LsapDbExpReleaseLockTrustedDomainList(v13);
  }
LABEL_39:
  if ( DestinationString.Buffer )
    LocalFree(DestinationString.Buffer);
  return (unsigned int)LockTrustedDomainList;
}

```

## disassembly

```asm
0x18001a6d8  mov     [rsp-38h+arg_8], rbx
0x18001a6dd  mov     [rsp-38h+arg_0], ecx
0x18001a6e1  push    rbp
0x18001a6e2  push    rsi
0x18001a6e3  push    rdi
0x18001a6e4  push    r12
0x18001a6e6  push    r13
0x18001a6e8  push    r14
0x18001a6ea  push    r15
0x18001a6ec  mov     rbp, rsp
0x18001a6ef  sub     rsp, 50h
0x18001a6f3  mov     r15, [rbp+arg_20]
0x18001a6f7  xor     edi, edi
0x18001a6f9  mov     [rbp+arg_18], rdi
0x18001a6fd  xorps   xmm0, xmm0
0x18001a700  mov     r14, r9
0x18001a703  mov     r12, r8
0x18001a706  mov     rsi, rdx
0x18001a709  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18001a70d  test    r15, r15
0x18001a710  jz      short loc_18001A715
0x18001a712  mov     [r15], rdi
0x18001a715  xor     edx, edx; SourceString
0x18001a717  lea     rcx, [rbp+DestinationString]; DestinationString
0x18001a71b  call    cs:__imp_RtlInitUnicodeString
0x18001a721  test    r14, r14
0x18001a724  jz      short loc_18001A72F
0x18001a726  mov     byte ptr [rbp+arg_20], dil
0x18001a72a  cmp     [r14], dil
0x18001a72d  jnz     short loc_18001A743
0x18001a72f  call    cs:__imp_LsapDbExpAcquireReadLockTrustedDomainList
0x18001a735  mov     ebx, eax
0x18001a737  test    eax, eax
0x18001a739  js      loc_18001A863
0x18001a73f  mov     byte ptr [rbp+arg_20], 1
0x18001a743  test    rsi, rsi
0x18001a746  jz      short loc_18001A75A
0x18001a748  lea     rdx, [rbp+arg_18]; struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY **
0x18001a74c  mov     rcx, rsi; struct _LSAPR_UNICODE_STRING *
0x18001a74f  call    ?LsaDbpLookupNameTrustedDomainListEx@@YAJPEAU_LSAPR_UNICODE_STRING@@PEAPEAU_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY@@@Z; LsaDbpLookupNameTrustedDomainListEx(_LSAPR_UNICODE_STRING *,_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY * *)
0x18001a754  mov     rdi, [rbp+arg_18]
0x18001a758  jmp     short loc_18001A7A0
0x18001a75a  xor     eax, eax
0x18001a75c  xorps   xmm0, xmm0
0x18001a75f  xor     edx, edx; unsigned __int8
0x18001a761  mov     [rbp+var_10], rax
0x18001a765  mov     cl, 1; unsigned __int8
0x18001a767  mov     [rbp+arg_18], rax
0x18001a76b  movups  xmmword ptr [rbp+var_20.Length], xmm0
0x18001a76f  call    ?LsaDbpBuildTrustedDomainCacheIfNecessary@@YAJEE@Z; LsaDbpBuildTrustedDomainCacheIfNecessary(uchar,uchar)
0x18001a774  test    eax, eax
0x18001a776  js      loc_18001A847
0x18001a77c  xor     edx, edx; SourceString
0x18001a77e  mov     [rbp+var_10], r12
0x18001a782  lea     rcx, [rbp+var_20]; DestinationString
0x18001a786  call    cs:__imp_RtlInitUnicodeString
0x18001a78c  lea     rdx, [rbp+arg_18]; struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY **
0x18001a790  lea     rcx, [rbp+var_20]; struct _LSAPR_TRUST_INFORMATION *
0x18001a794  call    ?LsaDbpLookupEntryTrustedDomainList@@YAJPEAU_LSAPR_TRUST_INFORMATION@@PEAPEAU_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY@@@Z; LsaDbpLookupEntryTrustedDomainList(_LSAPR_TRUST_INFORMATION *,_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY * *)
0x18001a799  test    eax, eax
0x18001a79b  cmovns  rdi, [rbp+arg_18]
0x18001a7a0  test    eax, eax
0x18001a7a2  js      loc_18001A847
0x18001a7a8  test    byte ptr [rdi+38h], 2
0x18001a7ac  jz      loc_18001A847
0x18001a7b2  mov     ecx, [rdi+3Ch]
0x18001a7b5  lea     eax, [rcx-1]
0x18001a7b8  cmp     eax, 1
0x18001a7bb  ja      loc_18001A847
0x18001a7c1  xor     r13b, r13b
0x18001a7c4  xor     r12b, r12b
0x18001a7c7  xor     sil, sil
0x18001a7ca  cmp     ecx, 2
0x18001a7cd  jnz     short loc_18001A7E1
0x18001a7cf  cmp     qword ptr [rdi+30h], 0
0x18001a7d4  jz      short loc_18001A7E6
0x18001a7d6  test    byte ptr [rdi+40h], 8
0x18001a7da  jz      short loc_18001A7E6
0x18001a7dc  mov     r13b, 1
0x18001a7df  jmp     short loc_18001A7E6
0x18001a7e1  cmp     ecx, 1
0x18001a7e4  jnz     short loc_18001A813
0x18001a7e6  mov     rcx, [rdi+30h]; Src
0x18001a7ea  test    rcx, rcx
0x18001a7ed  jz      short loc_18001A813
0x18001a7ef  test    byte ptr [rdi+40h], 8
0x18001a7f3  jnz     short loc_18001A813
0x18001a7f5  lea     rdx, [rbp+DestinationString]; DestinationString
0x18001a7f9  mov     r12b, 1
0x18001a7fc  call    ?LsaDbpGetDomainNameBySid@@YAJPEAXPEAU_UNICODE_STRING@@@Z; LsaDbpGetDomainNameBySid(void *,_UNICODE_STRING *)
0x18001a801  mov     ebx, eax
0x18001a803  test    eax, eax
0x18001a805  js      short loc_18001A80C
0x18001a807  mov     sil, r12b
0x18001a80a  jmp     short loc_18001A813
0x18001a80c  cmp     eax, 0C00000DFh
0x18001a811  jnz     short loc_18001A84C
0x18001a813  mov     eax, [rbp+arg_0]
0x18001a816  test    al, 4
0x18001a818  jz      short loc_18001A81F
0x18001a81a  test    r13b, r13b
0x18001a81d  jnz     short loc_18001A83B
0x18001a81f  test    al, 1
0x18001a821  jz      short loc_18001A82D
0x18001a823  test    r12b, r12b
0x18001a826  jz      short loc_18001A82D
0x18001a828  test    sil, sil
0x18001a82b  jz      short loc_18001A83B
0x18001a82d  test    al, 2
0x18001a82f  jz      short loc_18001A847
0x18001a831  test    r12b, r12b
0x18001a834  jz      short loc_18001A847
0x18001a836  test    sil, sil
0x18001a839  jz      short loc_18001A847
0x18001a83b  xor     ebx, ebx
0x18001a83d  test    r15, r15
0x18001a840  jz      short loc_18001A84C
0x18001a842  mov     [r15], rdi
0x18001a845  jmp     short loc_18001A84C
0x18001a847  mov     ebx, 0C00000DFh
0x18001a84c  cmp     byte ptr [rbp+arg_20], 0
0x18001a850  jz      short loc_18001A863
0x18001a852  test    r14, r14
0x18001a855  jnz     short loc_18001A85F
0x18001a857  call    cs:__imp_LsapDbExpReleaseLockTrustedDomainList
0x18001a85d  jmp     short loc_18001A863
0x18001a85f  mov     byte ptr [r14], 1
0x18001a863  mov     rcx, [rbp+DestinationString.Buffer]; hMem
0x18001a867  test    rcx, rcx
0x18001a86a  jz      short loc_18001A872
0x18001a86c  call    cs:__imp_LocalFree
0x18001a872  mov     eax, ebx
0x18001a874  mov     rbx, [rsp+50h+arg_8]
0x18001a87c  add     rsp, 50h
0x18001a880  pop     r15
0x18001a882  pop     r14
0x18001a884  pop     r13
0x18001a886  pop     r12
0x18001a888  pop     rdi
0x18001a889  pop     rsi
0x18001a88a  pop     rbp
0x18001a88b  retn
```
