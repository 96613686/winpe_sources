# LsaDbpDsTrustedDomainObjectNameForDomain(_UNICODE_STRING *,uchar,_DSNAME * *)

- ea: `0x180019db4`
- end: `0x180019f2d`
- name: `?LsaDbpDsTrustedDomainObjectNameForDomain@@YAJPEAU_UNICODE_STRING@@EPEAPEAU_DSNAME@@@Z`
- size: `377`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, unsigned __int8, struct _DSNAME **)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path`

## callers

- `0x18001f890`

## callees

- `0x180001670`
- `0x18000beb4`
- `0x18000fd18`
- `0x18000fd40`
- `0x1800113cc`
- `0x180019db4`

## import_xrefs

- `LSASRV!LsapDbExpAcquireReadLockTrustedDomainList` at `0x180019e1b`
- `LSASRV!LsapDbExpAcquireReadLockTrustedDomainList` at `0x180019e1b`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x180019e8d`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x180019ea2`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x180019e8d`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x180019ea2`

## pseudocode

```c
__int64 __fastcall LsaDbpDsTrustedDomainObjectNameForDomain(struct _UNICODE_STRING *a1, char a2, struct _DSNAME **a3)
{
  void *v6; // rcx
  int LockTrustedDomainList; // ebx
  __int128 v8; // xmm0
  __int128 *v9; // rcx
  __int128 v10; // xmm1
  __int64 v11; // rcx
  int Unique; // eax
  __int64 v13; // rcx
  int v14; // eax
  _DWORD v16[2]; // [rsp+30h] [rbp-40h] BYREF
  void *Buffer; // [rsp+38h] [rbp-38h]
  __int128 v18; // [rsp+40h] [rbp-30h] BYREF
  __int64 v19; // [rsp+50h] [rbp-20h]
  struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *v20[2]; // [rsp+58h] [rbp-18h] BYREF

  v16[1] = 0;
  v19 = 0;
  v18 = 0;
  v20[0] = 0;
  v6 = WPP_GLOBAL_Control;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, &WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids);
  LockTrustedDomainList = LsapDbExpAcquireReadLockTrustedDomainList(v6);
  if ( LockTrustedDomainList >= 0 )
  {
    v8 = (__int128)*a1;
    v19 = 0;
    v18 = v8;
    if ( (unsigned int)LsaDbpLookupEntryTrustedDomainList((struct _LSAPR_TRUST_INFORMATION *)&v18, v20)
      || (v9 = (__int128 *)((char *)v20[0] + 104), v20[0] == (struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *)-104LL)
      || *(_QWORD *)v9 == *(_QWORD *)&LsapNullUuidValue.Data1
      && *((_QWORD *)v20[0] + 14) == *(_QWORD *)LsapNullUuidValue.Data4 )
    {
      LsapDbExpReleaseLockTrustedDomainList(v9);
      v16[0] = a1->Length;
      Buffer = a1->Buffer;
      v14 = dword_180047EA8;
      if ( a2 )
        v14 = dword_180047EAC;
      Unique = LsaDbpDsFindUnique(v13, 0, 2, v16, v14, a3);
    }
    else
    {
      v16[0] = 16;
      *(_OWORD *)v20 = 0;
      v10 = *v9;
      Buffer = v20;
      *(_OWORD *)v20 = v10;
      LsapDbExpReleaseLockTrustedDomainList(v9);
      Unique = LsaDbpDsFindUnique(v11, 0, 2, v16, 589826, a3);
    }
    LockTrustedDomainList = Unique;
  }
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      72,
      &WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids,
      (unsigned int)LockTrustedDomainList);
  return (unsigned int)LockTrustedDomainList;
}

```

## disassembly

```asm
0x180019db4  mov     [rsp-18h+arg_8], rbx
0x180019db9  mov     [rsp-18h+arg_18], rsi
0x180019dbe  push    rbp
0x180019dbf  push    rdi
0x180019dc0  push    r14
0x180019dc2  mov     rbp, rsp
0x180019dc5  sub     rsp, 70h
0x180019dc9  mov     rax, cs:__security_cookie
0x180019dd0  xor     rax, rsp
0x180019dd3  mov     [rbp+var_8], rax
0x180019dd7  xor     eax, eax
0x180019dd9  mov     [rbp+var_3C], 0
0x180019de0  xorps   xmm0, xmm0
0x180019de3  mov     [rbp+var_20], rax
0x180019de7  movups  [rbp+var_30], xmm0
0x180019deb  mov     [rbp+var_18], rax
0x180019def  mov     rsi, r8
0x180019df2  mov     r14b, dl
0x180019df5  mov     rdi, rcx
0x180019df8  mov     rcx, cs:WPP_GLOBAL_Control
0x180019dff  test    dword ptr [rcx+1Ch], 100h
0x180019e06  jz      short loc_180019E1B
0x180019e08  mov     rcx, [rcx+10h]
0x180019e0c  lea     edx, [rax+47h]
0x180019e0f  lea     r8, WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids
0x180019e16  call    WPP_SF_
0x180019e1b  call    cs:__imp_LsapDbExpAcquireReadLockTrustedDomainList
0x180019e21  mov     ebx, eax
0x180019e23  test    eax, eax
0x180019e25  js      loc_180019EE2
0x180019e2b  movups  xmm0, xmmword ptr [rdi]
0x180019e2e  lea     rdx, [rbp+var_18]; struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY **
0x180019e32  mov     [rbp+var_20], 0
0x180019e3a  lea     rcx, [rbp+var_30]; struct _LSAPR_TRUST_INFORMATION *
0x180019e3e  movdqu  [rbp+var_30], xmm0
0x180019e43  call    ?LsaDbpLookupEntryTrustedDomainList@@YAJPEAU_LSAPR_TRUST_INFORMATION@@PEAPEAU_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY@@@Z; LsaDbpLookupEntryTrustedDomainList(_LSAPR_TRUST_INFORMATION *,_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY * *)
0x180019e48  test    eax, eax
0x180019e4a  jnz     short loc_180019EA2
0x180019e4c  mov     rcx, [rbp+var_18]
0x180019e50  add     rcx, 68h ; 'h'
0x180019e54  jz      short loc_180019EA2
0x180019e56  mov     rax, [rcx]
0x180019e59  cmp     rax, qword ptr cs:?LsapNullUuidValue@@3U_GUID@@A.Data1; _GUID LsapNullUuidValue ...
0x180019e60  jnz     short loc_180019E6F
0x180019e62  mov     rax, [rcx+8]
0x180019e66  cmp     rax, qword ptr cs:?LsapNullUuidValue@@3U_GUID@@A.Data4; _GUID LsapNullUuidValue ...
0x180019e6d  jz      short loc_180019EA2
0x180019e6f  xorps   xmm0, xmm0
0x180019e72  mov     [rbp+var_40], 10h
0x180019e79  movups  xmmword ptr [rbp+var_18], xmm0
0x180019e7d  lea     rax, [rbp+var_18]
0x180019e81  movups  xmm1, xmmword ptr [rcx]
0x180019e84  mov     [rbp+var_38], rax
0x180019e88  movdqu  xmmword ptr [rbp+var_18], xmm1
0x180019e8d  call    cs:__imp_LsapDbExpReleaseLockTrustedDomainList
0x180019e93  mov     [rsp+70h+var_48], rsi
0x180019e98  mov     [rsp+70h+var_50], 90002h
0x180019ea0  jmp     short loc_180019ECF
0x180019ea2  call    cs:__imp_LsapDbExpReleaseLockTrustedDomainList
0x180019ea8  movzx   eax, word ptr [rdi]
0x180019eab  test    r14b, r14b
0x180019eae  mov     [rbp+var_40], eax
0x180019eb1  mov     rax, [rdi+8]
0x180019eb5  mov     [rbp+var_38], rax
0x180019eb9  mov     eax, cs:dword_180047EA8
0x180019ebf  cmovnz  eax, cs:dword_180047EAC
0x180019ec6  mov     [rsp+70h+var_48], rsi
0x180019ecb  mov     [rsp+70h+var_50], eax
0x180019ecf  lea     r9, [rbp+var_40]
0x180019ed3  mov     r8d, 2
0x180019ed9  xor     edx, edx
0x180019edb  call    ?LsaDbpDsFindUnique@@YAJKPEAU_DSNAME@@W4_LSAP_DB_OBJECT_TYPE_ID@@PEAU_ATTRVAL@@KPEAPEAU1@@Z; LsaDbpDsFindUnique(ulong,_DSNAME *,_LSAP_DB_OBJECT_TYPE_ID,_ATTRVAL *,ulong,_DSNAME * *)
0x180019ee0  mov     ebx, eax
0x180019ee2  mov     rcx, cs:WPP_GLOBAL_Control
0x180019ee9  test    dword ptr [rcx+1Ch], 100h
0x180019ef0  jz      short loc_180019F0A
0x180019ef2  mov     rcx, [rcx+10h]
0x180019ef6  lea     r8, WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids
0x180019efd  mov     edx, 48h ; 'H'
0x180019f02  mov     r9d, ebx
0x180019f05  call    WPP_SF_d
0x180019f0a  mov     eax, ebx
0x180019f0c  mov     rcx, [rbp+var_8]
0x180019f10  xor     rcx, rsp; StackCookie
0x180019f13  call    __security_check_cookie
0x180019f18  lea     r11, [rsp+70h+var_s0]
0x180019f1d  mov     rbx, [r11+28h]
0x180019f21  mov     rsi, [r11+38h]
0x180019f25  mov     rsp, r11
0x180019f28  pop     r14
0x180019f2a  pop     rdi
0x180019f2b  pop     rbp
0x180019f2c  retn
```
