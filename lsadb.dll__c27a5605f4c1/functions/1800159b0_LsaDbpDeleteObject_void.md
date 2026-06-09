# LsaDbpDeleteObject(void * *)

- ea: `0x1800159b0`
- end: `0x180015be5`
- name: `?LsaDbpDeleteObject@@YAJPEAPEAX@Z`
- size: `565`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002234`
- `0x180009ec4`
- `0x18000beb4`
- `0x18000bff4`
- `0x18000c140`
- `0x18000d680`
- `0x18000fd40`
- `0x1800159b0`
- `0x1800345c0`

## import_xrefs

- `LSASRV!_fgs__LSAPR_TRUST_INFORMATION` at `0x180015bb0`
- `LSASRV!_fgs__LSAPR_TRUST_INFORMATION` at `0x180015bb0`
- `LSASRV!LsapDbDeleteObject` at `0x180015b54`
- `LSASRV!LsapDbDeleteObject` at `0x180015b54`
- `LSASRV!LsapRpcCopySid` at `0x180015b2a`
- `LSASRV!LsapRpcCopySid` at `0x180015b2a`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x180015bc4`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x180015bc4`
- `LSASRV!LsapDbDereferenceHandle` at `0x180015b65`
- `LSASRV!LsapDbDereferenceHandle` at `0x180015b65`
- `LSASRV!LsapDbExpAcquireReadLockTrustedDomainList` at `0x180015a8f`
- `LSASRV!LsapDbExpAcquireReadLockTrustedDomainList` at `0x180015a8f`
- `LSASRV!LsapRpcCopyUnicodeString` at `0x180015b16`
- `LSASRV!LsapRpcCopyUnicodeString` at `0x180015b16`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x180015b37`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x180015b37`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledHint` at `0x180015a81`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledHint` at `0x180015b83`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledHint` at `0x180015a81`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledHint` at `0x180015b83`

## pseudocode

```c
__int64 __fastcall LsaDbpDeleteObject(void **a1, __int64 a2, __int64 a3)
{
  char *v3; // rsi
  char v4; // r14
  int v5; // edi
  void **v6; // r15
  int v7; // r12d
  char v8; // bl
  int v9; // eax
  __int64 v10; // rcx
  unsigned int v11; // eax
  __int64 v12; // rcx
  int v13; // eax
  __int128 v14; // xmm0
  int v15; // eax
  struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *v16; // rbx
  __int64 v17; // r9
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8
  unsigned __int16 v22; // cx
  struct _UNICODE_STRING v24; // [rsp+30h] [rbp-30h] BYREF
  __int64 v25; // [rsp+40h] [rbp-20h] BYREF
  __int128 v26; // [rsp+48h] [rbp-18h] BYREF
  __int64 v27; // [rsp+58h] [rbp-8h]
  union _LSAPR_TRUSTED_DOMAIN_INFO *v28; // [rsp+90h] [rbp+30h] BYREF
  struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *v29; // [rsp+98h] [rbp+38h] BYREF

  v3 = (char *)*a1;
  v4 = 0;
  v29 = 0;
  v5 = 0;
  v6 = a1;
  v7 = *((_DWORD *)v3 + 26);
  v28 = 0;
  v24 = 0;
  v25 = 0;
  if ( HIBYTE(word_18004706B) && !*((_QWORD *)v3 + 11) )
  {
    v8 = v3[133];
    v3[133] = 1;
    v9 = LsaDbrQueryInfoTrustedDomain(*a1, TrustedDomainInformationEx, &v28);
    v3[133] = v8;
    v5 = v9;
    if ( v9 < 0 )
    {
      a1 = (void **)WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, "dh$\t", (unsigned int)v9);
    }
    else
    {
      a2 = *((_QWORD *)v28 + 4);
      *((_QWORD *)v3 + 11) = a2;
      a1 = (void **)v28;
      *((_QWORD *)v28 + 4) = 0;
    }
  }
  if ( (unsigned __int8)IsLsapAdtAuditingEnabledByLogonIdPresent(a1, a2, a3)
    && (unsigned __int8)LsapAdtAuditingEnabledHint(141, 8) )
  {
    if ( (int)LsapDbExpAcquireReadLockTrustedDomainList(v10) >= 0 )
    {
      v11 = LsaDbpLookupSidTrustedDomainList(*((struct _LSAPR_SID **)v3 + 11), &v29);
      v12 = v11;
      if ( v11 == -1073741601 )
      {
        v27 = 0;
        LOBYTE(v12) = 1;
        v29 = 0;
        v26 = 0;
        v13 = LsaDbpBuildTrustedDomainCacheIfNecessary(v12, 0);
        v12 = (unsigned int)v13;
        if ( v13 < 0
          || (v14 = *(_OWORD *)(v3 + 56),
              v27 = 0,
              v26 = v14,
              v15 = LsaDbpLookupEntryTrustedDomainList((struct _LSAPR_TRUST_INFORMATION *)&v26, &v29),
              v12 = (unsigned int)v15,
              v15 < 0) )
        {
          v16 = 0;
        }
        else
        {
          v16 = (struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *)((char *)v29 + 72);
        }
      }
      else
      {
        v16 = v29;
      }
      if ( (int)v12 >= 0
        && (int)LsapRpcCopyUnicodeString(0, &v24, v16) >= 0
        && (int)LsapRpcCopySid(0, &v25, *((_QWORD *)v16 + 2), v17) >= 0 )
      {
        v4 = 1;
      }
      LsapDbExpReleaseLockTrustedDomainList(v12);
    }
  }
  else if ( v5 < 0 )
  {
    goto LABEL_28;
  }
  LsaDbpNotifyNetlogonOfTrustChange(*((_QWORD *)v3 + 11), 3);
  v5 = LsapDbDeleteObject(*v6);
  if ( v5 >= 0 )
  {
    LOBYTE(v18) = 1;
    LsapDbDereferenceHandle(*v6, v18);
    if ( (unsigned __int8)IsLsapAdtAuditingEnabledByLogonIdPresent(v20, v19, v21) )
    {
      if ( v4 && (unsigned __int8)LsapAdtAuditingEnabledHint(141, 8) && v7 == 2 )
      {
        LsaDbpAdtTrustedDomainRem(v22, &v24, *((void **)v3 + 11), 0, 0);
        _fgs__LSAPR_TRUST_INFORMATION(&v24);
      }
    }
  }
LABEL_28:
  if ( v28 )
    LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO(6, v28);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800159b0  mov     [rsp-28h+arg_10], rbx
0x1800159b5  mov     [rsp-28h+arg_18], rsi
0x1800159ba  push    rbp
0x1800159bb  push    rdi
0x1800159bc  push    r12
0x1800159be  push    r14
0x1800159c0  push    r15
0x1800159c2  mov     rbp, rsp
0x1800159c5  sub     rsp, 60h
0x1800159c9  mov     rsi, [rcx]
0x1800159cc  xor     eax, eax
0x1800159ce  xor     r14b, r14b
0x1800159d1  mov     [rbp+arg_8], 0
0x1800159d9  xor     edi, edi
0x1800159db  xorps   xmm0, xmm0
0x1800159de  cmp     byte ptr cs:word_18004706B+1, al
0x1800159e4  mov     r15, rcx
0x1800159e7  mov     r12d, [rsi+68h]
0x1800159eb  mov     [rbp+arg_0], 0
0x1800159f3  movups  xmmword ptr [rbp+var_30.Length], xmm0
0x1800159f7  mov     [rbp+var_20], rax
0x1800159fb  jz      short loc_180015A6A
0x1800159fd  cmp     [rsi+58h], rax
0x180015a01  jnz     short loc_180015A6A
0x180015a03  mov     bl, [rsi+85h]
0x180015a09  lea     r8, [rbp+arg_0]; union _LSAPR_TRUSTED_DOMAIN_INFO **
0x180015a0d  mov     byte ptr [rsi+85h], 1
0x180015a14  lea     edx, [rax+6]; enum _TRUSTED_INFORMATION_CLASS
0x180015a17  mov     rcx, [rcx]; void *
0x180015a1a  call    ?LsaDbrQueryInfoTrustedDomain@@YAJPEAXW4_TRUSTED_INFORMATION_CLASS@@PEAPEAT_LSAPR_TRUSTED_DOMAIN_INFO@@@Z; LsaDbrQueryInfoTrustedDomain(void *,_TRUSTED_INFORMATION_CLASS,_LSAPR_TRUSTED_DOMAIN_INFO * *)
0x180015a1f  mov     [rsi+85h], bl
0x180015a25  mov     edi, eax
0x180015a27  test    eax, eax
0x180015a29  js      short loc_180015A45
0x180015a2b  mov     rcx, [rbp+arg_0]
0x180015a2f  mov     rdx, [rcx+20h]
0x180015a33  mov     [rsi+58h], rdx
0x180015a37  mov     rcx, [rbp+arg_0]
0x180015a3b  mov     qword ptr [rcx+20h], 0
0x180015a43  jmp     short loc_180015A6A
0x180015a45  mov     rcx, cs:WPP_GLOBAL_Control
0x180015a4c  test    byte ptr [rcx+1Ch], 1
0x180015a50  jz      short loc_180015A6A
0x180015a52  mov     rcx, [rcx+10h]
0x180015a56  lea     r8, WPP_09246864d60035b807e8ba7c719c23ee_Traceguids; "dh$\t"
0x180015a5d  mov     edx, 0Ah
0x180015a62  mov     r9d, eax
0x180015a65  call    WPP_SF_d
0x180015a6a  call    IsLsapAdtAuditingEnabledByLogonIdPresent
0x180015a6f  test    al, al
0x180015a71  jz      loc_180015B3F
0x180015a77  mov     edx, 8
0x180015a7c  mov     ecx, 8Dh
0x180015a81  call    cs:__imp_LsapAdtAuditingEnabledHint
0x180015a87  test    al, al
0x180015a89  jz      loc_180015B3F
0x180015a8f  call    cs:__imp_LsapDbExpAcquireReadLockTrustedDomainList
0x180015a95  test    eax, eax
0x180015a97  js      loc_180015B43
0x180015a9d  mov     rcx, [rsi+58h]; struct _LSAPR_SID *
0x180015aa1  lea     rdx, [rbp+arg_8]; struct _LSAPR_TRUST_INFORMATION **
0x180015aa5  call    ?LsaDbpLookupSidTrustedDomainList@@YAJPEAU_LSAPR_SID@@PEAPEAU_LSAPR_TRUST_INFORMATION@@@Z; LsaDbpLookupSidTrustedDomainList(_LSAPR_SID *,_LSAPR_TRUST_INFORMATION * *)
0x180015aaa  mov     ecx, eax
0x180015aac  cmp     eax, 0C00000DFh
0x180015ab1  jnz     short loc_180015B05
0x180015ab3  xor     eax, eax
0x180015ab5  xorps   xmm0, xmm0
0x180015ab8  xor     edx, edx; unsigned __int8
0x180015aba  mov     [rbp+var_8], rax
0x180015abe  mov     cl, 1; unsigned __int8
0x180015ac0  mov     [rbp+arg_8], rax
0x180015ac4  movups  [rbp+var_18], xmm0
0x180015ac8  call    ?LsaDbpBuildTrustedDomainCacheIfNecessary@@YAJEE@Z; LsaDbpBuildTrustedDomainCacheIfNecessary(uchar,uchar)
0x180015acd  mov     ecx, eax
0x180015acf  test    eax, eax
0x180015ad1  js      short loc_180015B01
0x180015ad3  movups  xmm0, xmmword ptr [rsi+38h]
0x180015ad7  lea     rdx, [rbp+arg_8]; struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY **
0x180015adb  mov     [rbp+var_8], 0
0x180015ae3  lea     rcx, [rbp+var_18]; struct _LSAPR_TRUST_INFORMATION *
0x180015ae7  movdqu  [rbp+var_18], xmm0
0x180015aec  call    ?LsaDbpLookupEntryTrustedDomainList@@YAJPEAU_LSAPR_TRUST_INFORMATION@@PEAPEAU_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY@@@Z; LsaDbpLookupEntryTrustedDomainList(_LSAPR_TRUST_INFORMATION *,_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY * *)
0x180015af1  mov     ecx, eax
0x180015af3  test    eax, eax
0x180015af5  js      short loc_180015B01
0x180015af7  mov     rbx, [rbp+arg_8]
0x180015afb  add     rbx, 48h ; 'H'
0x180015aff  jmp     short loc_180015B09
0x180015b01  xor     ebx, ebx
0x180015b03  jmp     short loc_180015B09
0x180015b05  mov     rbx, [rbp+arg_8]
0x180015b09  test    ecx, ecx
0x180015b0b  js      short loc_180015B37
0x180015b0d  mov     r8, rbx
0x180015b10  lea     rdx, [rbp+var_30]
0x180015b14  xor     ecx, ecx
0x180015b16  call    cs:__imp_LsapRpcCopyUnicodeString
0x180015b1c  test    eax, eax
0x180015b1e  js      short loc_180015B37
0x180015b20  mov     r8, [rbx+10h]
0x180015b24  lea     rdx, [rbp+var_20]
0x180015b28  xor     ecx, ecx
0x180015b2a  call    cs:__imp_LsapRpcCopySid
0x180015b30  test    eax, eax
0x180015b32  js      short loc_180015B37
0x180015b34  mov     r14b, 1
0x180015b37  call    cs:__imp_LsapDbExpReleaseLockTrustedDomainList
0x180015b3d  jmp     short loc_180015B43
0x180015b3f  test    edi, edi
0x180015b41  js      short loc_180015BB6
0x180015b43  mov     rcx, [rsi+58h]
0x180015b47  mov     edx, 3
0x180015b4c  call    ?LsaDbpNotifyNetlogonOfTrustChange@@YAJPEAXW4_SECURITY_DB_DELTA_TYPE@@@Z; LsaDbpNotifyNetlogonOfTrustChange(void *,_SECURITY_DB_DELTA_TYPE)
0x180015b51  mov     rcx, [r15]
0x180015b54  call    cs:__imp_LsapDbDeleteObject
0x180015b5a  mov     edi, eax
0x180015b5c  test    eax, eax
0x180015b5e  js      short loc_180015BB6
0x180015b60  mov     rcx, [r15]
0x180015b63  mov     dl, 1
0x180015b65  call    cs:__imp_LsapDbDereferenceHandle
0x180015b6b  call    IsLsapAdtAuditingEnabledByLogonIdPresent
0x180015b70  test    al, al
0x180015b72  jz      short loc_180015BB6
0x180015b74  test    r14b, r14b
0x180015b77  jz      short loc_180015BB6
0x180015b79  mov     edx, 8
0x180015b7e  mov     ecx, 8Dh
0x180015b83  call    cs:__imp_LsapAdtAuditingEnabledHint
0x180015b89  test    al, al
0x180015b8b  jz      short loc_180015BB6
0x180015b8d  cmp     r12d, 2
0x180015b91  jnz     short loc_180015BB6
0x180015b93  mov     r8, [rsi+58h]; void *
0x180015b97  lea     rdx, [rbp+var_30]; struct _UNICODE_STRING *
0x180015b9b  xor     r9d, r9d; void *
0x180015b9e  mov     [rsp+60h+var_40], 0; struct _LUID *
0x180015ba7  call    ?LsaDbpAdtTrustedDomainRem@@YAJGPEAU_UNICODE_STRING@@PEAX1PEAU_LUID@@@Z; LsaDbpAdtTrustedDomainRem(ushort,_UNICODE_STRING *,void *,void *,_LUID *)
0x180015bac  lea     rcx, [rbp+var_30]
0x180015bb0  call    cs:__imp__fgs__LSAPR_TRUST_INFORMATION
0x180015bb6  mov     rdx, [rbp+arg_0]
0x180015bba  test    rdx, rdx
0x180015bbd  jz      short loc_180015BCA
0x180015bbf  mov     ecx, 6
0x180015bc4  call    cs:__imp_LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO
0x180015bca  lea     r11, [rsp+60h+var_s0]
0x180015bcf  mov     eax, edi
0x180015bd1  mov     rbx, [r11+40h]
0x180015bd5  mov     rsi, [r11+48h]
0x180015bd9  mov     rsp, r11
0x180015bdc  pop     r15
0x180015bde  pop     r14
0x180015be0  pop     r12
0x180015be2  pop     rdi
0x180015be3  pop     rbp
0x180015be4  retn
```
