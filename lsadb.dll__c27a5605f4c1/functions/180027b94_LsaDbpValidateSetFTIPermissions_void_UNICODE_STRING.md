# LsaDbpValidateSetFTIPermissions(void *,_UNICODE_STRING *)

- ea: `0x180027b94`
- end: `0x180027d52`
- name: `?LsaDbpValidateSetFTIPermissions@@YAJPEAXPEAU_UNICODE_STRING@@@Z`
- size: `446`
- prototype: `__int64 __fastcall(void *, struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180028290`
- `0x1800283d0`

## callees

- `0x180001fb8`
- `0x18000bf70`
- `0x18000fd40`
- `0x180012fa4`
- `0x180027b94`

## import_xrefs

- `LSASRV!LsapDbCloseObject` at `0x180027d05`
- `LSASRV!LsapDbCloseObject` at `0x180027d05`
- `LSASRV!LsapDbOpenObject` at `0x180027cc1`
- `LSASRV!LsapDbOpenObject` at `0x180027cc1`
- `LSASRV!LsapDbDereferenceObject` at `0x180027d36`
- `LSASRV!LsapDbDereferenceObject` at `0x180027d36`
- `LSASRV!LsapDbExpAcquireReadLockTrustedDomainList` at `0x180027c25`
- `LSASRV!LsapDbExpAcquireReadLockTrustedDomainList` at `0x180027c25`
- `LSASRV!LsapDbReferenceObject` at `0x180027be5`
- `LSASRV!LsapDbReferenceObject` at `0x180027be5`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x180027d10`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x180027d10`

## pseudocode

```c
__int64 __fastcall LsaDbpValidateSetFTIPermissions(void *a1, struct _UNICODE_STRING *a2)
{
  int v4; // r14d
  int LockTrustedDomainList; // eax
  __int64 v6; // rcx
  unsigned int v7; // ebx
  int v8; // edi
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  int v11; // eax
  int v12; // edx
  _QWORD v14[8]; // [rsp+30h] [rbp-50h] BYREF
  int v15; // [rsp+70h] [rbp-10h]
  int v16; // [rsp+74h] [rbp-Ch]
  void *v17; // [rsp+C0h] [rbp+40h] BYREF
  __int64 v18; // [rsp+D0h] [rbp+50h] BYREF
  struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *v19; // [rsp+D8h] [rbp+58h] BYREF

  v17 = a1;
  v18 = 0;
  v4 = 0;
  memset_0(v14, 0, 0x48u);
  v19 = 0;
  LockTrustedDomainList = LsapDbReferenceObject(a1, 0, 1, 2);
  v7 = LockTrustedDomainList;
  if ( LockTrustedDomainList < 0 )
  {
    v8 = 0;
    v9 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_15;
    v10 = 320;
    goto LABEL_4;
  }
  v8 = 1;
  LockTrustedDomainList = LsapDbExpAcquireReadLockTrustedDomainList(v6);
  v7 = LockTrustedDomainList;
  if ( LockTrustedDomainList >= 0 )
  {
    v4 = 1;
    v11 = LsaDbpLookupNameTrustedDomainListEx((struct _LSAPR_UNICODE_STRING *)a2, &v19);
    v7 = v11;
    if ( v11 >= 0 )
    {
      v14[1] = 48;
      LODWORD(a2) = (_DWORD)v19 + 16;
      memset(&v14[4], 0, 32);
      v14[3] = (char *)v19 + 16;
      v15 = 0;
      v14[0] = 2;
      v16 = 32;
      v14[2] = v17;
      v11 = LsapDbOpenObject(v14, 32, 0, &v18, 1);
      v7 = v11;
      if ( v11 >= 0 )
        goto LABEL_15;
      v9 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_15;
      v12 = 323;
    }
    else
    {
      v9 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_15;
      v12 = 322;
    }
    WPP_SF_ZD(v9[2], v12, (unsigned int)&WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids, (_DWORD)a2, v11);
    goto LABEL_15;
  }
  v9 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    v10 = 321;
LABEL_4:
    WPP_SF_d(v9[2], v10, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids, (unsigned int)LockTrustedDomainList);
  }
LABEL_15:
  if ( v18 )
    LsapDbCloseObject(&v18, 0, v7);
  if ( v4 )
    LsapDbExpReleaseLockTrustedDomainList(v9);
  if ( v8 )
    return (unsigned int)LsapDbDereferenceObject(&v17, 1, 2, 16385, 0, v7);
  return v7;
}

```

## disassembly

```asm
0x180027b94  mov     [rsp-38h+arg_0], rcx
0x180027b99  push    rbp
0x180027b9a  push    rbx
0x180027b9b  push    rsi
0x180027b9c  push    rdi
0x180027b9d  push    r12
0x180027b9f  push    r14
0x180027ba1  push    r15
0x180027ba3  mov     rbp, rsp
0x180027ba6  sub     rsp, 80h
0x180027bad  xor     r15d, r15d
0x180027bb0  mov     rsi, rdx
0x180027bb3  mov     rbx, rcx
0x180027bb6  mov     [rbp+arg_10], r15
0x180027bba  xor     edx, edx; Val
0x180027bbc  lea     rcx, [rbp+var_50]; void *
0x180027bc0  mov     r14d, r15d
0x180027bc3  lea     r8d, [r15+48h]; Size
0x180027bc7  call    memset_0
0x180027bcc  lea     r12d, [r15+1]
0x180027bd0  mov     [rbp+arg_18], r15
0x180027bd4  mov     r8d, r12d
0x180027bd7  mov     [rsp+80h+var_60], r12d
0x180027bdc  lea     r9d, [r15+2]
0x180027be0  xor     edx, edx
0x180027be2  mov     rcx, rbx
0x180027be5  call    cs:__imp_LsapDbReferenceObject
0x180027beb  mov     ebx, eax
0x180027bed  test    eax, eax
0x180027bef  jns     short loc_180027C22
0x180027bf1  mov     edi, r15d
0x180027bf4  mov     rcx, cs:WPP_GLOBAL_Control
0x180027bfb  test    byte ptr [rcx+1Ch], 8
0x180027bff  jz      loc_180027CF6
0x180027c05  mov     edx, 140h
0x180027c0a  mov     rcx, [rcx+10h]
0x180027c0e  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x180027c15  mov     r9d, eax
0x180027c18  call    WPP_SF_d
0x180027c1d  jmp     loc_180027CF6
0x180027c22  mov     edi, r12d
0x180027c25  call    cs:__imp_LsapDbExpAcquireReadLockTrustedDomainList
0x180027c2b  mov     ebx, eax
0x180027c2d  test    eax, eax
0x180027c2f  jns     short loc_180027C49
0x180027c31  mov     rcx, cs:WPP_GLOBAL_Control
0x180027c38  test    byte ptr [rcx+1Ch], 8
0x180027c3c  jz      loc_180027CF6
0x180027c42  mov     edx, 141h
0x180027c47  jmp     short loc_180027C0A
0x180027c49  lea     rdx, [rbp+arg_18]; struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY **
0x180027c4d  mov     rcx, rsi; struct _LSAPR_UNICODE_STRING *
0x180027c50  mov     r14d, r12d
0x180027c53  call    ?LsaDbpLookupNameTrustedDomainListEx@@YAJPEAU_LSAPR_UNICODE_STRING@@PEAPEAU_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY@@@Z; LsaDbpLookupNameTrustedDomainListEx(_LSAPR_UNICODE_STRING *,_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY * *)
0x180027c58  mov     ebx, eax
0x180027c5a  test    eax, eax
0x180027c5c  jns     short loc_180027C76
0x180027c5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180027c65  test    byte ptr [rcx+1Ch], 8
0x180027c69  jz      loc_180027CF6
0x180027c6f  mov     edx, 142h
0x180027c74  jmp     short loc_180027CDF
0x180027c76  mov     rax, [rbp+arg_0]
0x180027c7a  lea     r9, [rbp+arg_10]
0x180027c7e  mov     rsi, [rbp+arg_18]
0x180027c82  lea     rcx, [rbp+var_50]
0x180027c86  mov     edx, 20h ; ' '
0x180027c8b  mov     [rbp+var_48], 30h ; '0'
0x180027c93  add     rsi, 10h
0x180027c97  mov     [rbp+var_30], r15
0x180027c9b  xor     r8d, r8d
0x180027c9e  mov     [rbp+var_38], rsi
0x180027ca2  mov     [rbp+var_10], r15d
0x180027ca6  mov     [rbp+var_50], 2
0x180027cae  mov     [rbp+var_18], r15
0x180027cb2  mov     [rbp+var_C], edx
0x180027cb5  mov     [rbp+var_40], rax
0x180027cb9  mov     [rbp+var_28], r15
0x180027cbd  mov     [rbp+var_20], r15
0x180027cc1  call    cs:__imp_LsapDbOpenObject
0x180027cc7  mov     ebx, eax
0x180027cc9  test    eax, eax
0x180027ccb  jns     short loc_180027CF6
0x180027ccd  mov     rcx, cs:WPP_GLOBAL_Control
0x180027cd4  test    byte ptr [rcx+1Ch], 8
0x180027cd8  jz      short loc_180027CF6
0x180027cda  mov     edx, 143h
0x180027cdf  mov     rcx, [rcx+10h]
0x180027ce3  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x180027cea  mov     r9, rsi
0x180027ced  mov     [rsp+80h+var_60], eax
0x180027cf1  call    WPP_SF_ZD
0x180027cf6  cmp     [rbp+arg_10], r15
0x180027cfa  jz      short loc_180027D0B
0x180027cfc  mov     r8d, ebx
0x180027cff  lea     rcx, [rbp+arg_10]
0x180027d03  xor     edx, edx
0x180027d05  call    cs:__imp_LsapDbCloseObject
0x180027d0b  test    r14d, r14d
0x180027d0e  jz      short loc_180027D16
0x180027d10  call    cs:__imp_LsapDbExpReleaseLockTrustedDomainList
0x180027d16  test    edi, edi
0x180027d18  jz      short loc_180027D3E
0x180027d1a  mov     [rsp+80h+var_58], ebx
0x180027d1e  lea     rcx, [rbp+arg_0]
0x180027d22  mov     r9d, 4001h
0x180027d28  mov     [rsp+80h+var_60], r15d
0x180027d2d  mov     r8d, 2
0x180027d33  mov     edx, r12d
0x180027d36  call    cs:__imp_LsapDbDereferenceObject
0x180027d3c  mov     ebx, eax
0x180027d3e  mov     eax, ebx
0x180027d40  add     rsp, 80h
0x180027d47  pop     r15
0x180027d49  pop     r14
0x180027d4b  pop     r12
0x180027d4d  pop     rdi
0x180027d4e  pop     rsi
0x180027d4f  pop     rbx
0x180027d50  pop     rbp
0x180027d51  retn
```
