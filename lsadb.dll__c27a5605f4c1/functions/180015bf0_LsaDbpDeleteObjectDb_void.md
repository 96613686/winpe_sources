# LsaDbpDeleteObjectDb(void *)

- ea: `0x180015bf0`
- end: `0x180015d6e`
- name: `?LsaDbpDeleteObjectDb@@YAJPEAX@Z`
- size: `382`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000af18`
- `0x180015bf0`
- `0x18001863c`
- `0x18001f600`
- `0x18001f740`
- `0x1800360f8`

## import_xrefs

- `LSASRV!LsapDbInitializeAttribute` at `0x180015c52`
- `LSASRV!LsapDbInitializeAttribute` at `0x180015c84`
- `LSASRV!LsapDbInitializeAttribute` at `0x180015c52`
- `LSASRV!LsapDbInitializeAttribute` at `0x180015c84`
- `LSASRV!LsapDbExpAcquireWriteLockTrustedDomainList` at `0x180015cd8`
- `LSASRV!LsapDbExpAcquireWriteLockTrustedDomainList` at `0x180015d43`
- `LSASRV!LsapDbExpAcquireWriteLockTrustedDomainList` at `0x180015cd8`
- `LSASRV!LsapDbExpAcquireWriteLockTrustedDomainList` at `0x180015d43`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x180015cee`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x180015d58`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x180015cee`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x180015d58`
- `LSASRV!LsapDbExpMakeCacheInvalid` at `0x180015d52`
- `LSASRV!LsapDbExpMakeCacheInvalid` at `0x180015d52`

## pseudocode

```c
__int64 __fastcall LsaDbpDeleteObjectDb(char *a1)
{
  bool v1; // zf
  char v3; // si
  int v4; // edi
  __int128 v5; // xmm0
  __int64 v6; // rcx
  __int64 v7; // rcx
  int v8; // eax
  __int64 v9; // rcx
  __int128 v11; // [rsp+30h] [rbp-39h] BYREF
  __int64 v12; // [rsp+40h] [rbp-29h]
  _BYTE v13[32]; // [rsp+50h] [rbp-19h] BYREF
  int v14; // [rsp+70h] [rbp+7h]
  int v15; // [rsp+74h] [rbp+Bh]
  _BYTE v16[32]; // [rsp+78h] [rbp+Fh] BYREF
  int v17; // [rsp+98h] [rbp+2Fh]
  int v18; // [rsp+9Ch] [rbp+33h]

  v1 = *((_DWORD *)a1 + 26) == 2;
  v12 = 0;
  v11 = 0;
  v3 = 1;
  if ( v1 )
  {
    if ( (*((_DWORD *)a1 + 34) & 0x400000) != 0 )
    {
      LsapDbInitializeAttribute(v13, 43, 0);
      v14 = *((_DWORD *)LsaDbpDsAttInfo + 129);
      v15 = *((_DWORD *)LsaDbpDsAttInfo + 130);
      LsapDbInitializeAttribute(v16, 44, 0);
      v17 = *((_DWORD *)LsaDbpDsAttInfo + 132);
      v18 = *((_DWORD *)LsaDbpDsAttInfo + 133);
    }
    else
    {
      if ( HIBYTE(word_18004706B) )
      {
        if ( *((_WORD *)a1 + 72) )
        {
          v4 = LsaDbpCheckTDODeletionQuotas((struct _LSAP_DB_HANDLE *)a1);
          if ( v4 < 0 )
            return (unsigned int)v4;
        }
      }
      v5 = *(_OWORD *)(a1 + 56);
      v12 = *((_QWORD *)a1 + 11);
      v11 = v5;
      if ( (int)LsapDbExpAcquireWriteLockTrustedDomainList(a1) >= 0 )
      {
        LsaDbpDeleteTrustedDomainList((struct _LSAPR_TRUST_INFORMATION *)&v11);
        v3 = 0;
        LsapDbExpReleaseLockTrustedDomainList(v6);
      }
      v4 = LsaDbpDsDeleteInterdomainTrustAccount(a1);
      if ( v4 < 0 )
        goto LABEL_17;
    }
  }
  else if ( *((_DWORD *)a1 + 26) != 4 )
  {
    return (unsigned int)-1073741811;
  }
  if ( (*((_DWORD *)a1 + 34) & 0x400000) != 0 && *((_DWORD *)a1 + 26) == 2 )
    v8 = LsaDbpDsDeleteAttributes((struct _UNICODE_STRING *)a1 + 9, (struct _LSAP_DB_ATTRIBUTE *)v13, 2u);
  else
    v8 = LsaDbpDsDeleteObject((struct _UNICODE_STRING *)a1 + 9);
  v4 = v8;
  if ( v8 < 0 )
  {
LABEL_17:
    if ( !v3 && (int)LsapDbExpAcquireWriteLockTrustedDomainList(v7) >= 0 )
    {
      LsapDbExpMakeCacheInvalid(2);
      LsapDbExpReleaseLockTrustedDomainList(v9);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180015bf0  push    rbp
0x180015bf2  push    rbx
0x180015bf3  push    rsi
0x180015bf4  push    rdi
0x180015bf5  push    r14
0x180015bf7  lea     rbp, [rsp-37h]
0x180015bfc  sub     rsp, 0A0h
0x180015c03  xor     eax, eax
0x180015c05  xor     r14d, r14d
0x180015c08  cmp     dword ptr [rcx+68h], 2
0x180015c0c  xorps   xmm0, xmm0
0x180015c0f  mov     rbx, rcx
0x180015c12  mov     [rbp+57h+var_80], rax
0x180015c16  movups  [rbp+57h+var_90], xmm0
0x180015c1a  mov     sil, 1
0x180015c1d  jz      short loc_180015C33
0x180015c1f  cmp     dword ptr [rcx+68h], 4
0x180015c23  jz      loc_180015D02
0x180015c29  mov     edi, 0C000000Dh
0x180015c2e  jmp     loc_180015D5E
0x180015c33  test    dword ptr [rcx+88h], 400000h
0x180015c3d  jz      short loc_180015CA5
0x180015c3f  xor     r9d, r9d
0x180015c42  mov     [rsp+0C0h+var_A0], r14b
0x180015c47  xor     r8d, r8d
0x180015c4a  lea     rcx, [rbp+57h+var_70]
0x180015c4e  lea     edx, [r9+2Bh]
0x180015c52  call    cs:__imp_LsapDbInitializeAttribute
0x180015c58  mov     rcx, cs:?LsaDbpDsAttInfo@@3PEAU_LSAP_DB_DS_INFO@@EA; _LSAP_DB_DS_INFO * LsaDbpDsAttInfo
0x180015c5f  xor     r9d, r9d
0x180015c62  xor     r8d, r8d
0x180015c65  mov     [rsp+0C0h+var_A0], r14b
0x180015c6a  mov     eax, [rcx+204h]
0x180015c70  lea     edx, [r9+2Ch]
0x180015c74  mov     [rbp+57h+var_50], eax
0x180015c77  mov     eax, [rcx+208h]
0x180015c7d  lea     rcx, [rbp+57h+var_48]
0x180015c81  mov     [rbp+57h+var_4C], eax
0x180015c84  call    cs:__imp_LsapDbInitializeAttribute
0x180015c8a  mov     rcx, cs:?LsaDbpDsAttInfo@@3PEAU_LSAP_DB_DS_INFO@@EA; struct _LSAP_DB_HANDLE *
0x180015c91  mov     eax, [rcx+210h]
0x180015c97  mov     [rbp+57h+var_28], eax
0x180015c9a  mov     eax, [rcx+214h]
0x180015ca0  mov     [rbp+57h+var_24], eax
0x180015ca3  jmp     short loc_180015D02
0x180015ca5  cmp     byte ptr cs:word_18004706B+1, r14b
0x180015cac  jz      short loc_180015CC7
0x180015cae  cmp     [rcx+90h], r14w
0x180015cb6  jz      short loc_180015CC7
0x180015cb8  call    ?LsaDbpCheckTDODeletionQuotas@@YAJPEAU_LSAP_DB_HANDLE@@@Z; LsaDbpCheckTDODeletionQuotas(_LSAP_DB_HANDLE *)
0x180015cbd  mov     edi, eax
0x180015cbf  test    eax, eax
0x180015cc1  js      loc_180015D5E
0x180015cc7  movups  xmm0, xmmword ptr [rbx+38h]
0x180015ccb  mov     rax, [rbx+58h]
0x180015ccf  mov     [rbp+57h+var_80], rax
0x180015cd3  movdqu  [rbp+57h+var_90], xmm0
0x180015cd8  call    cs:__imp_LsapDbExpAcquireWriteLockTrustedDomainList
0x180015cde  test    eax, eax
0x180015ce0  js      short loc_180015CF4
0x180015ce2  lea     rcx, [rbp+57h+var_90]; struct _LSAPR_TRUST_INFORMATION *
0x180015ce6  call    ?LsaDbpDeleteTrustedDomainList@@YAJPEAU_LSAPR_TRUST_INFORMATION@@@Z; LsaDbpDeleteTrustedDomainList(_LSAPR_TRUST_INFORMATION *)
0x180015ceb  mov     sil, r14b
0x180015cee  call    cs:__imp_LsapDbExpReleaseLockTrustedDomainList
0x180015cf4  mov     rcx, rbx; void *
0x180015cf7  call    ?LsaDbpDsDeleteInterdomainTrustAccount@@YAJPEAX@Z; LsaDbpDsDeleteInterdomainTrustAccount(void *)
0x180015cfc  mov     edi, eax
0x180015cfe  test    eax, eax
0x180015d00  js      short loc_180015D3E
0x180015d02  test    dword ptr [rbx+88h], 400000h
0x180015d0c  jz      short loc_180015D2C
0x180015d0e  cmp     dword ptr [rbx+68h], 2
0x180015d12  jnz     short loc_180015D2C
0x180015d14  lea     rcx, [rbx+90h]; struct _UNICODE_STRING *
0x180015d1b  mov     r8d, 2; unsigned int
0x180015d21  lea     rdx, [rbp+57h+var_70]; struct _LSAP_DB_ATTRIBUTE *
0x180015d25  call    ?LsaDbpDsDeleteAttributes@@YAJPEAU_UNICODE_STRING@@PEAU_LSAP_DB_ATTRIBUTE@@K@Z; LsaDbpDsDeleteAttributes(_UNICODE_STRING *,_LSAP_DB_ATTRIBUTE *,ulong)
0x180015d2a  jmp     short loc_180015D38
0x180015d2c  lea     rcx, [rbx+90h]; struct _UNICODE_STRING *
0x180015d33  call    ?LsaDbpDsDeleteObject@@YAJPEAU_UNICODE_STRING@@@Z; LsaDbpDsDeleteObject(_UNICODE_STRING *)
0x180015d38  mov     edi, eax
0x180015d3a  test    eax, eax
0x180015d3c  jns     short loc_180015D5E
0x180015d3e  test    sil, sil
0x180015d41  jnz     short loc_180015D5E
0x180015d43  call    cs:__imp_LsapDbExpAcquireWriteLockTrustedDomainList
0x180015d49  test    eax, eax
0x180015d4b  js      short loc_180015D5E
0x180015d4d  mov     ecx, 2
0x180015d52  call    cs:__imp_LsapDbExpMakeCacheInvalid
0x180015d58  call    cs:__imp_LsapDbExpReleaseLockTrustedDomainList
0x180015d5e  mov     eax, edi
0x180015d60  add     rsp, 0A0h
0x180015d67  pop     r14
0x180015d69  pop     rdi
0x180015d6a  pop     rsi
0x180015d6b  pop     rbx
0x180015d6c  pop     rbp
0x180015d6d  retn
```
