# Pku2uS4UToSelfLogon(void *,void *,ulong,_LSA_TOKEN_INFORMATION_TYPE *,void * *,_SECPKG_PRIMARY_CRED *,_NETLOGON_VALIDATION_SAM_INFO4 * *)

- ea: `0x18002d5f8`
- end: `0x18002db46`
- name: `?Pku2uS4UToSelfLogon@@YAJPEAX0KPEAW4_LSA_TOKEN_INFORMATION_TYPE@@PEAPEAXPEAU_SECPKG_PRIMARY_CRED@@PEAPEAU_NETLOGON_VALIDATION_SAM_INFO4@@@Z`
- size: `1358`
- prototype: `__int64 __fastcall(void *, void *, unsigned int, enum _LSA_TOKEN_INFORMATION_TYPE *, void **, LUID *LocallyUniqueId, struct _NETLOGON_VALIDATION_SAM_INFO4 **)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002cf50`

## callees

- `0x180003bc0`
- `0x1800044f0`
- `0x180004830`
- `0x1800057f0`
- `0x180016860`
- `0x18001a0b0`
- `0x18001a524`
- `0x180023cb8`
- `0x180023d9c`
- `0x18002b744`
- `0x18002d5f8`
- `0x18003b1f8`
- `0x180044f8c`
- `0x180046010`

## import_xrefs

- `ntdll!RtlValidSid` at `0x18002da2a`
- `ntdll!RtlValidSid` at `0x18002da2a`
- `ntdll!RtlLengthSid` at `0x18002da3b`
- `ntdll!RtlLengthSid` at `0x18002da3b`
- `ntdll!NtAllocateLocallyUniqueId` at `0x18002d989`
- `ntdll!NtAllocateLocallyUniqueId` at `0x18002d989`
- `ntdll!NtQuerySystemTime` at `0x18002d80c`
- `ntdll!NtQuerySystemTime` at `0x18002d80c`
- `CRYPT32!CertFreeCertificateContext` at `0x18002db3b`
- `CRYPT32!CertFreeCertificateContext` at `0x18002db3b`

## string_xrefs

- `0x18002d7db`: `onecore\ds\security\protocols\pku2u\logonapi.cxx`
- `0x18002d867`: `onecore\ds\security\protocols\pku2u\logonapi.cxx`
- `0x18002d8bc`: `onecore\ds\security\protocols\pku2u\logonapi.cxx`

## pseudocode

```c
__int64 __fastcall Pku2uS4UToSelfLogon(
        _QWORD *a1,
        unsigned __int64 a2,
        unsigned int a3,
        enum _LSA_TOKEN_INFORMATION_TYPE *a4,
        void **a5,
        LUID *LocallyUniqueId,
        struct _NETLOGON_VALIDATION_SAM_INFO4 **a7)
{
  unsigned __int64 v7; // r10
  unsigned __int64 v10; // rdx
  __int64 v11; // r8
  int TokenInformationV2; // ebx
  struct _UNICODE_STRING *v14; // rdi
  unsigned __int64 v15; // rdx
  __int64 v16; // r8
  unsigned __int64 v17; // rdx
  DWORD v18; // r9d
  BYTE *v19; // rax
  struct _PAC_INFO_BUFFER *v20; // r8
  struct _PAC_INFO_BUFFER *v21; // rax
  struct _UNICODE_STRING *v22; // rdx
  struct _UNICODE_STRING *v23; // r8
  LUID *v24; // rdi
  unsigned __int8 v25; // r8
  unsigned __int8 v26; // r8
  unsigned __int8 v27; // r8
  PSID Sid; // rbx
  size_t v29; // r14
  void *v30; // rax
  struct _LSA_SECPKG_FUNCTION_TABLE *v31; // rax
  struct _LSA_TOKEN_INFORMATION_V1 *v32; // rax
  struct _NETLOGON_VALIDATION_SAM_INFO4 *v33; // rax
  struct _NETLOGON_VALIDATION_SAM_INFO4 **v34; // rdx
  struct _LSA_TOKEN_INFORMATION_V1 *v35; // [rsp+30h] [rbp-50h] BYREF
  struct _PACTYPE *v36; // [rsp+38h] [rbp-48h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+40h] [rbp-40h] BYREF
  union _LARGE_INTEGER SystemTime; // [rsp+48h] [rbp-38h] BYREF
  struct _UNICODE_STRING v39; // [rsp+50h] [rbp-30h] BYREF
  __int128 v40; // [rsp+60h] [rbp-20h] BYREF
  __int128 v41; // [rsp+70h] [rbp-10h]
  struct _NETLOGON_VALIDATION_SAM_INFO4 *v42; // [rsp+B0h] [rbp+30h] BYREF
  unsigned int v43; // [rsp+C0h] [rbp+40h] BYREF

  v7 = a3;
  SystemTime.QuadPart = 0;
  v36 = 0;
  pCertContext = 0;
  v42 = 0;
  v35 = 0;
  v43 = 0;
  v40 = 0;
  v41 = 0;
  v39 = 0;
  if ( a3 < 0x38 )
    goto LABEL_4;
  v10 = a1[4];
  v11 = *((unsigned __int16 *)a1 + 12);
  if ( v10 )
  {
    if ( (_WORD)v11 )
    {
      if ( v10 >= a2 )
        v10 -= a2;
      if ( !v10 )
        goto LABEL_4;
      if ( v10 > v7 )
        goto LABEL_4;
      if ( v10 + v11 > v7 )
        goto LABEL_4;
      if ( v10 < 0x38 )
        goto LABEL_4;
      if ( (v10 & 1) != 0 )
        goto LABEL_4;
      *((_WORD *)a1 + 13) = v11;
      a1[4] = (char *)a1 + v10;
      if ( (v11 & 1) != 0 )
        goto LABEL_4;
    }
    else
    {
      a1[4] = 0;
    }
  }
  else if ( (_WORD)v11 )
  {
LABEL_4:
    TokenInformationV2 = -1073741811;
    goto LABEL_5;
  }
  v14 = (struct _UNICODE_STRING *)(a1 + 1);
  v15 = a1[2];
  v16 = *((unsigned __int16 *)a1 + 4);
  if ( v15 )
  {
    if ( (_WORD)v16 )
    {
      if ( v15 >= a2 )
        v15 -= a2;
      if ( !v15 )
        goto LABEL_4;
      if ( v15 > v7 )
        goto LABEL_4;
      if ( v15 + v16 > v7 )
        goto LABEL_4;
      if ( v15 < 0x38 )
        goto LABEL_4;
      if ( (v15 & 1) != 0 )
        goto LABEL_4;
      *((_WORD *)a1 + 5) = v16;
      a1[2] = (char *)a1 + v15;
      if ( (v16 & 1) != 0 )
        goto LABEL_4;
    }
    else
    {
      a1[2] = 0;
    }
  }
  else if ( (_WORD)v16 )
  {
    goto LABEL_4;
  }
  v17 = a1[6];
  v18 = *((_DWORD *)a1 + 10);
  if ( !v17 )
  {
    if ( v18 )
      goto LABEL_4;
    goto LABEL_34;
  }
  if ( !v18 )
  {
    a1[6] = 0;
LABEL_34:
    v19 = 0;
    goto LABEL_40;
  }
  if ( v17 >= a2 )
    v17 -= a2;
  if ( v18 > (unsigned int)v7 || v17 > (unsigned int)v7 - v18 )
    goto LABEL_4;
  v19 = (BYTE *)a1 + v17;
  a1[6] = (char *)a1 + v17;
LABEL_40:
  TokenInformationV2 = ScHelperBuildCertContext(v19, v18, &pCertContext);
  if ( TokenInformationV2 >= 0 )
  {
    NtQuerySystemTime(&SystemTime);
    TokenInformationV2 = Pku2uCreatePac(&SystemTime, v14, pCertContext, &v39, &v36);
    if ( TokenInformationV2 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_dsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          (unsigned int)WPP_7e7e3542d015350663d795ca61e34c82_Traceguids,
          TokenInformationV2,
          (__int64)"onecore\\ds\\security\\protocols\\pku2u\\logonapi.cxx",
          94);
      goto LABEL_78;
    }
    v21 = PAC_Find(v36, 1u, v20);
    if ( v21 )
    {
      TokenInformationV2 = PAC_UnmarshallAndConvertValidationInfo(
                             &v42,
                             v22,
                             v23,
                             *((unsigned __int8 **)v21 + 1),
                             *((_DWORD *)v21 + 1));
      if ( TokenInformationV2 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_dsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            (unsigned int)WPP_7e7e3542d015350663d795ca61e34c82_Traceguids,
            TokenInformationV2,
            (__int64)"onecore\\ds\\security\\protocols\\pku2u\\logonapi.cxx",
            126);
        goto LABEL_78;
      }
      TokenInformationV2 = Pku2uMakeTokenInformationV2(v42, 0, 0, &v35, &v43);
      if ( TokenInformationV2 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_dsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            (unsigned int)WPP_7e7e3542d015350663d795ca61e34c82_Traceguids,
            TokenInformationV2,
            (__int64)"onecore\\ds\\security\\protocols\\pku2u\\logonapi.cxx",
            146);
        goto LABEL_78;
      }
      v24 = LocallyUniqueId;
      TokenInformationV2 = NtAllocateLocallyUniqueId(LocallyUniqueId);
      if ( TokenInformationV2 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_dsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            (unsigned int)WPP_7e7e3542d015350663d795ca61e34c82_Traceguids,
            TokenInformationV2,
            (__int64)"onecore\\ds\\security\\protocols\\pku2u\\logonapi.cxx",
            159);
        goto LABEL_78;
      }
      TokenInformationV2 = KerbDuplicateStringEx2(
                             (struct _UNICODE_STRING *)&v24[1],
                             (const struct _UNICODE_STRING *)v42 + 3,
                             v25);
      if ( TokenInformationV2 < 0
        || (TokenInformationV2 = KerbDuplicateStringEx2(
                                   (struct _UNICODE_STRING *)&v24[3],
                                   (const struct _UNICODE_STRING *)v42 + 13,
                                   v26),
            TokenInformationV2 < 0)
        || (TokenInformationV2 = KerbDuplicateStringEx2(
                                   (struct _UNICODE_STRING *)&v24[15],
                                   (const struct _UNICODE_STRING *)v42 + 12,
                                   v27),
            TokenInformationV2 < 0) )
      {
LABEL_78:
        if ( v36 )
          Pku2uFree(v36);
        goto LABEL_80;
      }
      Sid = v35->User.User.Sid;
      if ( RtlValidSid(Sid) )
      {
        v29 = RtlLengthSid(Sid);
        v30 = (void *)((__int64 (__fastcall *)(size_t))Pku2uGlobalLsaFunctions->AllocateLsaHeap)(v29);
        v24[9] = (LUID)v30;
        if ( v30 )
        {
          memcpy_0(v30, Sid, v29);
          v31 = Pku2uGlobalLsaFunctions;
          v24[10].LowPart = 0;
          TokenInformationV2 = ((__int64 (__fastcall *)(__int128 *))v31->GetClientInfo)(&v40);
          if ( TokenInformationV2 >= 0 )
          {
            if ( !(_BYTE)v41 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_7e7e3542d015350663d795ca61e34c82_Traceguids);
              v24[10].LowPart |= 0x10u;
            }
            v32 = v35;
            v35 = 0;
            *a5 = v32;
            v33 = v42;
            v34 = a7;
            *a4 = LsaTokenInformationV2;
            v42 = 0;
            *v34 = v33;
          }
        }
        else
        {
          TokenInformationV2 = -1073741801;
        }
        goto LABEL_78;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        (unsigned int)WPP_7e7e3542d015350663d795ca61e34c82_Traceguids,
        (unsigned int)"onecore\\ds\\security\\protocols\\pku2u\\logonapi.cxx",
        106);
    }
    TokenInformationV2 = -1073741811;
    goto LABEL_78;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_dsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      (unsigned int)WPP_7e7e3542d015350663d795ca61e34c82_Traceguids,
      TokenInformationV2,
      (__int64)"onecore\\ds\\security\\protocols\\pku2u\\logonapi.cxx",
      77);
LABEL_80:
  if ( v42 )
    Pku2uFree(v42);
  if ( v35 )
    ((void (*)(void))Pku2uGlobalLsaFunctions->FreeLsaHeap)();
  if ( pCertContext )
    CertFreeCertificateContext(pCertContext);
LABEL_5:
  KerbFreeString2(&v39);
  return (unsigned int)TokenInformationV2;
}

```

## disassembly

```asm
0x18002d5f8  mov     [rsp-28h+arg_8], rbx
0x18002d5fd  push    rbp
0x18002d5fe  push    rdi
0x18002d5ff  push    r12
0x18002d601  push    r13
0x18002d603  push    r14
0x18002d605  mov     rbp, rsp
0x18002d608  sub     rsp, 80h
0x18002d60f  xor     r13d, r13d
0x18002d612  mov     r10d, r8d
0x18002d615  mov     qword ptr [rbp+SystemTime], r13
0x18002d619  xorps   xmm0, xmm0
0x18002d61c  mov     [rbp+var_48], r13
0x18002d620  mov     r12, r9
0x18002d623  mov     [rbp+pCertContext], r13
0x18002d627  mov     r11, rdx
0x18002d62a  mov     [rbp+arg_0], r13
0x18002d62e  mov     [rbp+var_50], r13
0x18002d632  mov     [rbp+arg_10], r13d
0x18002d636  movups  [rbp+var_20], xmm0
0x18002d63a  movups  [rbp+var_10], xmm0
0x18002d63e  movups  xmmword ptr [rbp+var_30.Length], xmm0
0x18002d642  cmp     r8d, 38h ; '8'
0x18002d646  jb      short loc_18002D660
0x18002d648  mov     rdx, [rcx+20h]
0x18002d64c  lea     r14d, [r13+1]
0x18002d650  movzx   r8d, word ptr [rcx+18h]
0x18002d655  test    rdx, rdx
0x18002d658  jnz     short loc_18002D688
0x18002d65a  test    r8w, r8w
0x18002d65e  jz      short loc_18002D6D1
0x18002d660  mov     ebx, 0C000000Dh
0x18002d665  lea     rcx, [rbp+var_30]; struct _UNICODE_STRING *
0x18002d669  call    ?KerbFreeString2@@YAXPEAU_UNICODE_STRING@@@Z; KerbFreeString2(_UNICODE_STRING *)
0x18002d66e  mov     eax, ebx
0x18002d670  mov     rbx, [rsp+80h+arg_8]
0x18002d678  add     rsp, 80h
0x18002d67f  pop     r14
0x18002d681  pop     r13
0x18002d683  pop     r12
0x18002d685  pop     rdi
0x18002d686  pop     rbp
0x18002d687  retn
0x18002d688  test    r8w, r8w
0x18002d68c  jnz     short loc_18002D694
0x18002d68e  mov     [rcx+20h], r13
0x18002d692  jmp     short loc_18002D6D1
0x18002d694  mov     rax, rdx
0x18002d697  sub     rax, r11
0x18002d69a  cmp     rdx, r11
0x18002d69d  cmovnb  rdx, rax
0x18002d6a1  test    rdx, rdx
0x18002d6a4  jz      short loc_18002D660
0x18002d6a6  cmp     rdx, r10
0x18002d6a9  ja      short loc_18002D660
0x18002d6ab  lea     rax, [rdx+r8]
0x18002d6af  cmp     rax, r10
0x18002d6b2  ja      short loc_18002D660
0x18002d6b4  cmp     rdx, 38h ; '8'
0x18002d6b8  jb      short loc_18002D660
0x18002d6ba  test    r14b, dl
0x18002d6bd  jnz     short loc_18002D660
0x18002d6bf  mov     [rcx+1Ah], r8w
0x18002d6c4  lea     rax, [rdx+rcx]
0x18002d6c8  mov     [rcx+20h], rax
0x18002d6cc  test    r14b, r8b
0x18002d6cf  jnz     short loc_18002D660
0x18002d6d1  lea     rdi, [rcx+8]
0x18002d6d5  mov     rdx, [rdi+8]
0x18002d6d9  movzx   r8d, word ptr [rdi]
0x18002d6dd  test    rdx, rdx
0x18002d6e0  jnz     short loc_18002D6ED
0x18002d6e2  test    r8w, r8w
0x18002d6e6  jz      short loc_18002D74E
0x18002d6e8  jmp     loc_18002D660
0x18002d6ed  test    r8w, r8w
0x18002d6f1  jnz     short loc_18002D6F9
0x18002d6f3  mov     [rcx+10h], r13
0x18002d6f7  jmp     short loc_18002D74E
0x18002d6f9  mov     rax, rdx
0x18002d6fc  sub     rax, r11
0x18002d6ff  cmp     rdx, r11
0x18002d702  cmovnb  rdx, rax
0x18002d706  test    rdx, rdx
0x18002d709  jz      loc_18002D660
0x18002d70f  cmp     rdx, r10
0x18002d712  ja      loc_18002D660
0x18002d718  lea     rax, [rdx+r8]
0x18002d71c  cmp     rax, r10
0x18002d71f  ja      loc_18002D660
0x18002d725  cmp     rdx, 38h ; '8'
0x18002d729  jb      loc_18002D660
0x18002d72f  test    r14b, dl
0x18002d732  jnz     loc_18002D660
0x18002d738  mov     [rcx+0Ah], r8w
0x18002d73d  lea     rax, [rcx+rdx]
0x18002d741  mov     [rcx+10h], rax
0x18002d745  test    r14b, r8b
0x18002d748  jnz     loc_18002D660
0x18002d74e  mov     rdx, [rcx+30h]
0x18002d752  mov     r9d, [rcx+28h]
0x18002d756  test    rdx, rdx
0x18002d759  jnz     short loc_18002D766
0x18002d75b  test    r9d, r9d
0x18002d75e  jnz     loc_18002D660
0x18002d764  jmp     short loc_18002D76F
0x18002d766  test    r9d, r9d
0x18002d769  jnz     short loc_18002D774
0x18002d76b  mov     [rcx+30h], r13
0x18002d76f  mov     rax, r13
0x18002d772  jmp     short loc_18002D7A1
0x18002d774  mov     rax, rdx
0x18002d777  sub     rax, r11
0x18002d77a  cmp     rdx, r11
0x18002d77d  cmovnb  rdx, rax
0x18002d781  cmp     r9d, r10d
0x18002d784  ja      loc_18002D660
0x18002d78a  sub     r10d, r9d
0x18002d78d  mov     eax, r10d
0x18002d790  cmp     rdx, rax
0x18002d793  ja      loc_18002D660
0x18002d799  lea     rax, [rdx+rcx]
0x18002d79d  mov     [rcx+30h], rax
0x18002d7a1  lea     r8, [rbp+pCertContext]; struct _CERT_CONTEXT **
0x18002d7a5  mov     edx, r9d; cbCertEncoded
0x18002d7a8  mov     rcx, rax; pbCertEncoded
0x18002d7ab  call    ?ScHelperBuildCertContext@@YAJPEAEKPEAPEBU_CERT_CONTEXT@@@Z; ScHelperBuildCertContext(uchar *,ulong,_CERT_CONTEXT const * *)
0x18002d7b0  mov     ebx, eax
0x18002d7b2  test    eax, eax
0x18002d7b4  jns     short loc_18002D808
0x18002d7b6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d7bd  lea     rax, WPP_GLOBAL_Control
0x18002d7c4  cmp     rcx, rax
0x18002d7c7  jz      loc_18002DB06
0x18002d7cd  test    [rcx+1Ch], r14b
0x18002d7d1  jz      loc_18002DB06
0x18002d7d7  mov     rcx, [rcx+10h]
0x18002d7db  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\protocols\\pku2u"...
0x18002d7e2  mov     edx, 0Ah
0x18002d7e7  mov     [rsp+80h+var_58], 4Dh ; 'M'
0x18002d7ef  mov     r9d, ebx
0x18002d7f2  mov     [rsp+80h+var_60], rax
0x18002d7f7  lea     r8, WPP_7e7e3542d015350663d795ca61e34c82_Traceguids
0x18002d7fe  call    WPP_SF_dsd
0x18002d803  jmp     loc_18002DB06
0x18002d808  lea     rcx, [rbp+SystemTime]; SystemTime
0x18002d80c  call    cs:__imp_NtQuerySystemTime
0x18002d812  mov     r8, [rbp+pCertContext]; struct _CERT_CONTEXT *
0x18002d816  lea     rax, [rbp+var_48]
0x18002d81a  lea     r9, [rbp+var_30]; struct _UNICODE_STRING *
0x18002d81e  mov     [rsp+80h+var_60], rax; struct _PACTYPE **
0x18002d823  mov     rdx, rdi; struct _UNICODE_STRING *
0x18002d826  lea     rcx, [rbp+SystemTime]; union _LARGE_INTEGER *
0x18002d82a  call    ?Pku2uCreatePac@@YAJPEAT_LARGE_INTEGER@@PEAU_UNICODE_STRING@@PEBU_CERT_CONTEXT@@1PEAPEAU_PACTYPE@@@Z; Pku2uCreatePac(_LARGE_INTEGER *,_UNICODE_STRING *,_CERT_CONTEXT const *,_UNICODE_STRING *,_PACTYPE * *)
0x18002d82f  mov     ebx, eax
0x18002d831  test    eax, eax
0x18002d833  jns     short loc_18002D887
0x18002d835  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d83c  lea     rax, WPP_GLOBAL_Control
0x18002d843  cmp     rcx, rax
0x18002d846  jz      loc_18002DAF7
0x18002d84c  test    [rcx+1Ch], r14b
0x18002d850  jz      loc_18002DAF7
0x18002d856  mov     edx, 0Bh
0x18002d85b  mov     [rsp+80h+var_58], 5Eh ; '^'
0x18002d863  mov     rcx, [rcx+10h]
0x18002d867  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\protocols\\pku2u"...
0x18002d86e  mov     r9d, ebx
0x18002d871  mov     [rsp+80h+var_60], rax
0x18002d876  lea     r8, WPP_7e7e3542d015350663d795ca61e34c82_Traceguids
0x18002d87d  call    WPP_SF_dsd
0x18002d882  jmp     loc_18002DAF7
0x18002d887  mov     rcx, [rbp+var_48]; struct _PACTYPE *
0x18002d88b  mov     edx, r14d; unsigned int
0x18002d88e  call    ?PAC_Find@@YAPEAU_PAC_INFO_BUFFER@@PEAU_PACTYPE@@KPEAU1@@Z; PAC_Find(_PACTYPE *,ulong,_PAC_INFO_BUFFER *)
0x18002d893  mov     r9, rax
0x18002d896  test    rax, rax
0x18002d899  jnz     short loc_18002D8E1
0x18002d89b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d8a2  lea     rax, WPP_GLOBAL_Control
0x18002d8a9  cmp     rcx, rax
0x18002d8ac  jz      short loc_18002D8D7
0x18002d8ae  test    [rcx+1Ch], r14b
0x18002d8b2  jz      short loc_18002D8D7
0x18002d8b4  mov     rcx, [rcx+10h]
0x18002d8b8  lea     edx, [r9+0Ch]
0x18002d8bc  lea     r9, aOnecoreDsSecur_7; "onecore\\ds\\security\\protocols\\pku2u"...
0x18002d8c3  mov     dword ptr [rsp+80h+var_60], 6Ah ; 'j'
0x18002d8cb  lea     r8, WPP_7e7e3542d015350663d795ca61e34c82_Traceguids
0x18002d8d2  call    WPP_SF_sd
0x18002d8d7  mov     ebx, 0C000000Dh
0x18002d8dc  jmp     loc_18002DAF7
0x18002d8e1  mov     eax, [rax+4]
0x18002d8e4  lea     rcx, [rbp+arg_0]; struct _NETLOGON_VALIDATION_SAM_INFO4 **
0x18002d8e8  mov     r9, [r9+8]; unsigned __int8 *
0x18002d8ec  mov     dword ptr [rsp+80h+var_60], eax; unsigned int
0x18002d8f0  call    ?PAC_UnmarshallAndConvertValidationInfo@@YAJPEAPEAU_NETLOGON_VALIDATION_SAM_INFO4@@PEAU_UNICODE_STRING@@1PEAEK@Z; PAC_UnmarshallAndConvertValidationInfo(_NETLOGON_VALIDATION_SAM_INFO4 * *,_UNICODE_STRING *,_UNICODE_STRING *,uchar *,ulong)
0x18002d8f5  mov     ebx, eax
0x18002d8f7  test    eax, eax
0x18002d8f9  jns     short loc_18002D92E
0x18002d8fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d902  lea     rax, WPP_GLOBAL_Control
0x18002d909  cmp     rcx, rax
0x18002d90c  jz      loc_18002DAF7
0x18002d912  test    [rcx+1Ch], r14b
0x18002d916  jz      loc_18002DAF7
0x18002d91c  mov     edx, 0Dh
0x18002d921  mov     [rsp+80h+var_58], 7Eh ; '~'
0x18002d929  jmp     loc_18002D863
0x18002d92e  mov     rcx, [rbp+arg_0]; struct _NETLOGON_VALIDATION_SAM_INFO4 *
0x18002d932  lea     rax, [rbp+arg_10]
0x18002d936  lea     r9, [rbp+var_50]; struct _LSA_TOKEN_INFORMATION_V1 **
0x18002d93a  mov     [rsp+80h+var_60], rax; unsigned int *
0x18002d93f  xor     r8d, r8d; unsigned __int8
0x18002d942  xor     edx, edx; unsigned __int8
0x18002d944  call    ?Pku2uMakeTokenInformationV2@@YAJPEAU_NETLOGON_VALIDATION_SAM_INFO4@@EEPEAPEAU_LSA_TOKEN_INFORMATION_V1@@PEAK@Z; Pku2uMakeTokenInformationV2(_NETLOGON_VALIDATION_SAM_INFO4 *,uchar,uchar,_LSA_TOKEN_INFORMATION_V1 * *,ulong *)
0x18002d949  mov     ebx, eax
0x18002d94b  test    eax, eax
0x18002d94d  jns     short loc_18002D982
0x18002d94f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d956  lea     rax, WPP_GLOBAL_Control
0x18002d95d  cmp     rcx, rax
0x18002d960  jz      loc_18002DAF7
0x18002d966  test    [rcx+1Ch], r14b
0x18002d96a  jz      loc_18002DAF7
0x18002d970  mov     edx, 0Eh
0x18002d975  mov     [rsp+80h+var_58], 92h
0x18002d97d  jmp     loc_18002D863
0x18002d982  mov     rdi, [rbp+LocallyUniqueId]
0x18002d986  mov     rcx, rdi; LocallyUniqueId
0x18002d989  call    cs:__imp_NtAllocateLocallyUniqueId
0x18002d98f  mov     ebx, eax
0x18002d991  test    eax, eax
0x18002d993  jns     short loc_18002D9C8
0x18002d995  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d99c  lea     rax, WPP_GLOBAL_Control
0x18002d9a3  cmp     rcx, rax
0x18002d9a6  jz      loc_18002DAF7
0x18002d9ac  test    [rcx+1Ch], r14b
0x18002d9b0  jz      loc_18002DAF7
0x18002d9b6  mov     edx, 0Fh
0x18002d9bb  mov     [rsp+80h+var_58], 9Fh
0x18002d9c3  jmp     loc_18002D863
0x18002d9c8  mov     rdx, [rbp+arg_0]
0x18002d9cc  lea     rcx, [rdi+8]; struct _UNICODE_STRING *
0x18002d9d0  add     rdx, 30h ; '0'; struct _UNICODE_STRING *
0x18002d9d4  call    ?KerbDuplicateStringEx2@@YAJPEAU_UNICODE_STRING@@PEBU1@E@Z; KerbDuplicateStringEx2(_UNICODE_STRING *,_UNICODE_STRING const *,uchar)
0x18002d9d9  mov     ebx, eax
0x18002d9db  test    eax, eax
0x18002d9dd  js      loc_18002DAF7
0x18002d9e3  mov     rdx, [rbp+arg_0]
0x18002d9e7  lea     rcx, [rdi+18h]; struct _UNICODE_STRING *
0x18002d9eb  add     rdx, 0D0h; struct _UNICODE_STRING *
0x18002d9f2  call    ?KerbDuplicateStringEx2@@YAJPEAU_UNICODE_STRING@@PEBU1@E@Z; KerbDuplicateStringEx2(_UNICODE_STRING *,_UNICODE_STRING const *,uchar)
0x18002d9f7  mov     ebx, eax
0x18002d9f9  test    eax, eax
0x18002d9fb  js      loc_18002DAF7
0x18002da01  mov     rdx, [rbp+arg_0]
0x18002da05  lea     rcx, [rdi+78h]; struct _UNICODE_STRING *
0x18002da09  add     rdx, 0C0h; struct _UNICODE_STRING *
0x18002da10  call    ?KerbDuplicateStringEx2@@YAJPEAU_UNICODE_STRING@@PEBU1@E@Z; KerbDuplicateStringEx2(_UNICODE_STRING *,_UNICODE_STRING const *,uchar)
0x18002da15  mov     ebx, eax
0x18002da17  test    eax, eax
0x18002da19  js      loc_18002DAF7
0x18002da1f  mov     rax, [rbp+var_50]
0x18002da23  mov     rbx, [rax+8]
0x18002da27  mov     rcx, rbx; Sid
0x18002da2a  call    cs:__imp_RtlValidSid
0x18002da30  test    al, al
0x18002da32  jz      loc_18002D8D7
0x18002da38  mov     rcx, rbx; Sid
0x18002da3b  call    cs:__imp_RtlLengthSid
0x18002da41  mov     rcx, cs:?Pku2uGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * Pku2uGlobalLsaFunctions
0x18002da48  mov     r14d, eax
0x18002da4b  mov     rax, [rcx+28h]
0x18002da4f  mov     ecx, r14d
0x18002da52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002da57  mov     [rdi+48h], rax
0x18002da5b  test    rax, rax
0x18002da5e  jnz     short loc_18002DA6A
0x18002da60  mov     ebx, 0C0000017h
0x18002da65  jmp     loc_18002DAF7
0x18002da6a  mov     r8, r14; Size
0x18002da6d  mov     rdx, rbx; Src
0x18002da70  mov     rcx, rax; void *
0x18002da73  call    memcpy_0
0x18002da78  mov     rax, cs:?Pku2uGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * Pku2uGlobalLsaFunctions
0x18002da7f  lea     rcx, [rbp+var_20]
0x18002da83  mov     [rdi+50h], r13d
0x18002da87  mov     rax, [rax+80h]
0x18002da8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002da93  mov     ebx, eax
0x18002da95  test    eax, eax
0x18002da97  js      short loc_18002DAF7
0x18002da99  cmp     byte ptr [rbp+var_10], r13b
0x18002da9d  jnz     short loc_18002DAD1
0x18002da9f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002daa6  lea     rax, WPP_GLOBAL_Control
0x18002daad  cmp     rcx, rax
0x18002dab0  jz      short loc_18002DACD
  ... truncated ...
```
