# LsaDbpFixupTrustedDomainListEntry(void *,_LSAPR_UNICODE_STRING *,_LSAPR_UNICODE_STRING *,_LSAPR_TRUSTED_DOMAIN_INFORMATION_EX2 *,ulong *)

- ea: `0x18000b7c8`
- end: `0x18000b989`
- name: `?LsaDbpFixupTrustedDomainListEntry@@YAJPEAXPEAU_LSAPR_UNICODE_STRING@@1PEAU_LSAPR_TRUSTED_DOMAIN_INFORMATION_EX2@@PEAK@Z`
- size: `449`
- prototype: `__int64 __fastcall(void *, struct _LSAPR_UNICODE_STRING *, struct _LSAPR_UNICODE_STRING *, struct _LSAPR_TRUSTED_DOMAIN_INFORMATION_EX2 *, unsigned int *)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18000e9f0`
- `0x180013cbc`
- `0x180014358`

## callees

- `0x180001670`
- `0x180001fb8`
- `0x18000b7c8`
- `0x18000b990`
- `0x18000beb4`
- `0x18002a7f8`

## import_xrefs

- `LSASRV!_fgu__LSAPR_TRUSTED_DOMAIN_INFO` at `0x18000b910`
- `LSASRV!_fgu__LSAPR_TRUSTED_DOMAIN_INFO` at `0x18000b910`
- `LSASRV!LsapDbExpAcquireWriteLockTrustedDomainList` at `0x18000b81a`
- `LSASRV!LsapDbExpAcquireWriteLockTrustedDomainList` at `0x18000b81a`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x18000b967`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x18000b967`
- `LSASRV!LsapDbExpMakeCacheInvalid` at `0x18000b961`
- `LSASRV!LsapDbExpMakeCacheInvalid` at `0x18000b961`
- `LSASRV!LsapDbExpIsCacheValid` at `0x18000b82d`
- `LSASRV!LsapDbExpIsCacheValid` at `0x18000b843`
- `LSASRV!LsapDbExpIsCacheValid` at `0x18000b82d`
- `LSASRV!LsapDbExpIsCacheValid` at `0x18000b843`

## pseudocode

```c
__int64 __fastcall LsaDbpFixupTrustedDomainListEntry(
        void *a1,
        struct _LSAPR_UNICODE_STRING *a2,
        struct _LSAPR_UNICODE_STRING *a3,
        struct _LSAPR_TRUSTED_DOMAIN_INFORMATION_EX2 *a4,
        unsigned int *a5)
{
  __int64 v9; // rcx
  __int64 result; // rax
  FTCache *v11; // rcx
  int v12; // edi
  struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *v13; // rsi
  struct _UNICODE_STRING *v14; // rbx
  struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *v15; // [rsp+20h] [rbp-81h] BYREF
  __int128 v16; // [rsp+28h] [rbp-79h] BYREF
  void *v17; // [rsp+38h] [rbp-69h]
  _BYTE v18[16]; // [rsp+40h] [rbp-61h] BYREF
  __int128 v19; // [rsp+50h] [rbp-51h]
  __int128 v20; // [rsp+60h] [rbp-41h]
  __int128 v21; // [rsp+70h] [rbp-31h]
  __int64 v22; // [rsp+80h] [rbp-21h]
  __int128 v23; // [rsp+88h] [rbp-19h]
  __int64 v24; // [rsp+98h] [rbp-9h]

  v15 = 0;
  memset_0(v18, 0, 0x78u);
  v16 = 0;
  v17 = 0;
  result = LsapDbExpAcquireWriteLockTrustedDomainList(v9);
  if ( (int)result >= 0 )
  {
    if ( !(unsigned __int8)LsapDbExpIsCacheValid(2) || !(unsigned __int8)LsapDbExpIsCacheValid(2) )
    {
      v12 = 0;
LABEL_27:
      LsapDbExpReleaseLockTrustedDomainList(v11);
      return (unsigned int)v12;
    }
    if ( !a1 && !a2 && !a3 )
    {
      v12 = -1073741811;
LABEL_26:
      LsapDbExpMakeCacheInvalid(2);
      goto LABEL_27;
    }
    v16 = 0u;
    v17 = a1;
    if ( a2 )
      v16 = *(_OWORD *)a2;
    v12 = LsaDbpLookupEntryTrustedDomainList((struct _LSAPR_TRUST_INFORMATION *)&v16, &v15);
    if ( v12 == -1073741601 )
    {
      if ( !a3 )
        goto LABEL_26;
      v16 = *(_OWORD *)a3;
      v12 = LsaDbpLookupEntryTrustedDomainList((struct _LSAPR_TRUST_INFORMATION *)&v16, &v15);
    }
    if ( v12 >= 0 )
    {
      v13 = v15;
      if ( a4 )
      {
        v14 = 0;
        if ( !*((_QWORD *)a4 + 7) && DcInRootDomain )
          v14 = (struct _UNICODE_STRING *)((char *)v15 + 16);
        v12 = LsaDbpInitializeTrustedDomainListEntry((struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *)v18, a4, 0);
        if ( v12 >= 0 )
        {
          if ( v14 )
            FTCache::Remove(v11, v14);
          _fgu__LSAPR_TRUSTED_DOMAIN_INFO((char *)v13 + 16, 6);
          *((_OWORD *)v13 + 1) = v19;
          *((_OWORD *)v13 + 2) = v20;
          *((_OWORD *)v13 + 3) = v21;
          *((_QWORD *)v13 + 8) = v22;
          *(_OWORD *)((char *)v13 + 72) = v23;
          *((_QWORD *)v13 + 11) = v24;
        }
      }
      if ( a5 )
        *((_DWORD *)v13 + 25) = *a5;
      if ( v12 >= 0 )
        goto LABEL_27;
    }
    goto LABEL_26;
  }
  return result;
}

```

## disassembly

```asm
0x18000b7c8  push    rbp
0x18000b7ca  push    rbx
0x18000b7cb  push    rsi
0x18000b7cc  push    rdi
0x18000b7cd  push    r14
0x18000b7cf  lea     rbp, [rsp-2Fh]
0x18000b7d4  sub     rsp, 0D0h
0x18000b7db  mov     rax, cs:__security_cookie
0x18000b7e2  xor     rax, rsp
0x18000b7e5  mov     [rbp+4Fh+var_30], rax
0x18000b7e9  mov     rbx, rdx
0x18000b7ec  mov     [rsp+0F0h+var_D0], 0
0x18000b7f5  xor     edx, edx; Val
0x18000b7f7  mov     rsi, r8
0x18000b7fa  mov     rdi, rcx
0x18000b7fd  mov     r14, r9
0x18000b800  lea     rcx, [rbp+4Fh+var_B0]; void *
0x18000b804  lea     r8d, [rdx+78h]; Size
0x18000b808  call    memset_0
0x18000b80d  xorps   xmm0, xmm0
0x18000b810  xor     eax, eax
0x18000b812  movups  [rbp+4Fh+var_C8], xmm0
0x18000b816  mov     [rbp+4Fh+var_B8], rax
0x18000b81a  call    cs:__imp_LsapDbExpAcquireWriteLockTrustedDomainList
0x18000b820  test    eax, eax
0x18000b822  js      loc_18000B96F
0x18000b828  mov     ecx, 2
0x18000b82d  call    cs:__imp_LsapDbExpIsCacheValid
0x18000b833  test    al, al
0x18000b835  jnz     short loc_18000B83E
0x18000b837  xor     edi, edi
0x18000b839  jmp     loc_18000B967
0x18000b83e  mov     ecx, 2
0x18000b843  call    cs:__imp_LsapDbExpIsCacheValid
0x18000b849  test    al, al
0x18000b84b  jz      short loc_18000B837
0x18000b84d  test    rdi, rdi
0x18000b850  jnz     short loc_18000B866
0x18000b852  test    rbx, rbx
0x18000b855  jnz     short loc_18000B866
0x18000b857  test    rsi, rsi
0x18000b85a  jnz     short loc_18000B866
0x18000b85c  mov     edi, 0C000000Dh
0x18000b861  jmp     loc_18000B95C
0x18000b866  mov     qword ptr [rbp+4Fh+var_C8], 0
0x18000b86e  mov     qword ptr [rbp+4Fh+var_C8+8], 0
0x18000b876  mov     [rbp+4Fh+var_B8], rdi
0x18000b87a  test    rbx, rbx
0x18000b87d  jz      short loc_18000B887
0x18000b87f  movups  xmm0, xmmword ptr [rbx]
0x18000b882  movdqu  [rbp+4Fh+var_C8], xmm0
0x18000b887  lea     rdx, [rsp+0F0h+var_D0]; struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY **
0x18000b88c  lea     rcx, [rbp+4Fh+var_C8]; struct _LSAPR_TRUST_INFORMATION *
0x18000b890  call    ?LsaDbpLookupEntryTrustedDomainList@@YAJPEAU_LSAPR_TRUST_INFORMATION@@PEAPEAU_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY@@@Z; LsaDbpLookupEntryTrustedDomainList(_LSAPR_TRUST_INFORMATION *,_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY * *)
0x18000b895  mov     edi, eax
0x18000b897  cmp     eax, 0C00000DFh
0x18000b89c  jnz     short loc_18000B8BF
0x18000b89e  test    rsi, rsi
0x18000b8a1  jz      loc_18000B95C
0x18000b8a7  movups  xmm0, xmmword ptr [rsi]
0x18000b8aa  lea     rdx, [rsp+0F0h+var_D0]; struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY **
0x18000b8af  lea     rcx, [rbp+4Fh+var_C8]; struct _LSAPR_TRUST_INFORMATION *
0x18000b8b3  movdqu  [rbp+4Fh+var_C8], xmm0
0x18000b8b8  call    ?LsaDbpLookupEntryTrustedDomainList@@YAJPEAU_LSAPR_TRUST_INFORMATION@@PEAPEAU_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY@@@Z; LsaDbpLookupEntryTrustedDomainList(_LSAPR_TRUST_INFORMATION *,_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY * *)
0x18000b8bd  mov     edi, eax
0x18000b8bf  test    edi, edi
0x18000b8c1  js      loc_18000B95C
0x18000b8c7  mov     rsi, [rsp+0F0h+var_D0]
0x18000b8cc  test    r14, r14
0x18000b8cf  jz      short loc_18000B94A
0x18000b8d1  xor     ebx, ebx
0x18000b8d3  cmp     [r14+38h], rbx
0x18000b8d7  jnz     short loc_18000B8E5
0x18000b8d9  cmp     cs:?DcInRootDomain@@3EA, bl; uchar DcInRootDomain
0x18000b8df  jz      short loc_18000B8E5
0x18000b8e1  lea     rbx, [rsi+10h]
0x18000b8e5  xor     r8d, r8d; unsigned int
0x18000b8e8  lea     rcx, [rbp+4Fh+var_B0]; struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *
0x18000b8ec  mov     rdx, r14; struct _LSAPR_TRUSTED_DOMAIN_INFORMATION_EX2 *
0x18000b8ef  call    ?LsaDbpInitializeTrustedDomainListEntry@@YAJPEAU_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY@@PEAU_LSAPR_TRUSTED_DOMAIN_INFORMATION_EX2@@K@Z; LsaDbpInitializeTrustedDomainListEntry(_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *,_LSAPR_TRUSTED_DOMAIN_INFORMATION_EX2 *,ulong)
0x18000b8f4  mov     edi, eax
0x18000b8f6  test    eax, eax
0x18000b8f8  js      short loc_18000B94A
0x18000b8fa  test    rbx, rbx
0x18000b8fd  jz      short loc_18000B907
0x18000b8ff  mov     rdx, rbx; struct _UNICODE_STRING *
0x18000b902  call    ?Remove@FTCache@@QEAAJPEAU_UNICODE_STRING@@@Z; FTCache::Remove(_UNICODE_STRING *)
0x18000b907  mov     edx, 6
0x18000b90c  lea     rcx, [rsi+10h]
0x18000b910  call    cs:__imp__fgu__LSAPR_TRUSTED_DOMAIN_INFO
0x18000b916  movaps  xmm0, [rbp+4Fh+var_A0]
0x18000b91a  movups  xmmword ptr [rsi+10h], xmm0
0x18000b91e  movaps  xmm1, [rbp+4Fh+var_90]
0x18000b922  movups  xmmword ptr [rsi+20h], xmm1
0x18000b926  movaps  xmm0, [rbp+4Fh+var_80]
0x18000b92a  movups  xmmword ptr [rsi+30h], xmm0
0x18000b92e  movsd   xmm1, [rbp+4Fh+var_70]
0x18000b933  movsd   qword ptr [rsi+40h], xmm1
0x18000b938  movups  xmm0, [rbp+4Fh+var_68]
0x18000b93c  movups  xmmword ptr [rsi+48h], xmm0
0x18000b940  movsd   xmm1, [rbp+4Fh+var_58]
0x18000b945  movsd   qword ptr [rsi+58h], xmm1
0x18000b94a  mov     rax, [rbp+4Fh+arg_20]
0x18000b94e  test    rax, rax
0x18000b951  jz      short loc_18000B958
0x18000b953  mov     eax, [rax]
0x18000b955  mov     [rsi+64h], eax
0x18000b958  test    edi, edi
0x18000b95a  jns     short loc_18000B967
0x18000b95c  mov     ecx, 2
0x18000b961  call    cs:__imp_LsapDbExpMakeCacheInvalid
0x18000b967  call    cs:__imp_LsapDbExpReleaseLockTrustedDomainList
0x18000b96d  mov     eax, edi
0x18000b96f  mov     rcx, [rbp+4Fh+var_30]
0x18000b973  xor     rcx, rsp; StackCookie
0x18000b976  call    __security_check_cookie
0x18000b97b  add     rsp, 0D0h
0x18000b982  pop     r14
0x18000b984  pop     rdi
0x18000b985  pop     rsi
0x18000b986  pop     rbx
0x18000b987  pop     rbp
0x18000b988  retn
```
