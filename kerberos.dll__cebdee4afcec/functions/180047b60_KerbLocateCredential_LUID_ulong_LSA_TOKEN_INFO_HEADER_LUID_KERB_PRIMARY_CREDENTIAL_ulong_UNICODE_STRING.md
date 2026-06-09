# KerbLocateCredential(_LUID *,ulong,_LSA_TOKEN_INFO_HEADER *,_LUID *,_KERB_PRIMARY_CREDENTIAL *,ulong,_UNICODE_STRING *)

- ea: `0x180047b60`
- end: `0x180047f23`
- name: `?KerbLocateCredential@@YAPEAU_KERB_CREDENTIAL@@PEAU_LUID@@KPEAU_LSA_TOKEN_INFO_HEADER@@0PEAU_KERB_PRIMARY_CREDENTIAL@@KPEAU_UNICODE_STRING@@@Z`
- size: `963`
- prototype: `struct _KERB_CREDENTIAL *__fastcall(struct _LUID *, unsigned int, struct _LSA_TOKEN_INFO_HEADER *, struct _LUID *, PCUNICODE_STRING, unsigned int, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800474d8`

## callees

- `0x180011690`
- `0x18002cb68`
- `0x180047b60`
- `0x180070680`
- `0x18008b70c`
- `0x1800f5010`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x180047ca3`
- `ntdll!RtlEqualUnicodeString` at `0x180047cf4`
- `ntdll!RtlEqualUnicodeString` at `0x180047d0c`
- `ntdll!RtlEqualUnicodeString` at `0x180047dc2`
- `ntdll!RtlEqualUnicodeString` at `0x180047ddb`
- `ntdll!RtlEqualUnicodeString` at `0x180047e04`
- `ntdll!RtlEqualUnicodeString` at `0x180047ca3`
- `ntdll!RtlEqualUnicodeString` at `0x180047cf4`
- `ntdll!RtlEqualUnicodeString` at `0x180047d0c`
- `ntdll!RtlEqualUnicodeString` at `0x180047dc2`
- `ntdll!RtlEqualUnicodeString` at `0x180047ddb`
- `ntdll!RtlEqualUnicodeString` at `0x180047e04`
- `ntdll!RtlEnterCriticalSection` at `0x180047c33`
- `ntdll!RtlEnterCriticalSection` at `0x180047c33`
- `ntdll!RtlLeaveCriticalSection` at `0x180047e73`
- `ntdll!RtlLeaveCriticalSection` at `0x180047e73`
- `CRYPT32!CertCompareCertificate` at `0x180047e35`
- `CRYPT32!CertCompareCertificate` at `0x180047e35`
- `LSASRV!LsaIEqualSupplementalTokenInfo` at `0x180047cb9`
- `LSASRV!LsaIEqualSupplementalTokenInfo` at `0x180047cb9`

## pseudocode

```c
struct _KERB_CREDENTIAL *__fastcall KerbLocateCredential(
        struct _LUID *a1,
        int a2,
        struct _LSA_TOKEN_INFO_HEADER *a3,
        struct _LUID *a4,
        PCUNICODE_STRING a5,
        unsigned int a6,
        struct _UNICODE_STRING *a7)
{
  __int64 *v7; // rsi
  char v8; // r15
  __int64 v11; // r14
  unsigned int v12; // r12d
  __int64 *v13; // rbx
  __int64 v14; // rax
  __int64 v15; // rdx
  int v16; // eax
  __int64 v17; // rcx
  const UNICODE_STRING *Buffer; // rcx
  const UNICODE_STRING *v19; // rdx
  _LM_OWF_PASSWORD *v20; // rcx
  struct _KERB_CREDENTIAL *result; // rax
  __int64 v22; // r8
  const void *v23; // rcx
  _BYTE v24[8]; // [rsp+40h] [rbp-61h] BYREF
  __int64 *v25; // [rsp+48h] [rbp-59h]
  PCUNICODE_STRING String1; // [rsp+50h] [rbp-51h]
  struct _LSA_TOKEN_INFO_HEADER *v27; // [rsp+58h] [rbp-49h]
  struct _LUID *v28; // [rsp+60h] [rbp-41h]
  __int128 v29; // [rsp+68h] [rbp-39h] BYREF
  __int64 v30; // [rsp+78h] [rbp-29h]
  _LM_OWF_PASSWORD v31; // [rsp+80h] [rbp-21h] BYREF

  v7 = 0;
  v8 = 0;
  String1 = a7;
  v28 = a4;
  v27 = a3;
  v30 = 0;
  v29 = 0;
  v31 = 0;
  if ( a5 && ((__int64)a5[25].Buffer & 1) == 0 )
  {
    if ( a5[3].Buffer )
      KerbCalculatePasswordComparisonHash((const struct _KERB_PLAINTEXT_PASSWORD *)&a5[2], &v31);
    else
      v31 = 0;
  }
  v11 = 16;
  if ( !((unsigned __int8 (__fastcall *)(__int128 *))LsaFunctions->GetCallInfo)(&v29) )
  {
    KerbTracerT::Log(1, "KerbLocateCredential", 1450, "Failed to get client info:.");
    goto LABEL_46;
  }
  v12 = a6 | a2;
  RtlEnterCriticalSection(&stru_180144A70);
  v13 = (__int64 *)KerbCredentialList;
  if ( (_UNKNOWN *)KerbCredentialList == &KerbCredentialList )
    goto LABEL_45;
  while ( 1 )
  {
    v7 = v13;
    v25 = v13;
    if ( *((_DWORD *)v13 + 17) != (_DWORD)v29
      || (v13[8] & 0x70000013) != v12
      || (v13[8] & 0x40) != 0
      || *((_DWORD *)v13 + 7) != a1->LowPart
      || *((_DWORD *)v13 + 8) != a1->HighPart
      || !RtlEqualUnicodeString(String1, (PCUNICODE_STRING)v13 + 3, 0)
      || !(unsigned int)LsaIEqualSupplementalTokenInfo(v13[12], v27) )
    {
      goto LABEL_43;
    }
    v14 = v13[9];
    if ( !a5 )
      break;
    if ( !v14
      || v13[17]
      || !RtlEqualUnicodeString(a5, (PCUNICODE_STRING)v13[9], 0)
      && !RtlEqualUnicodeString(a5, (PCUNICODE_STRING)(v13[9] + 96), 0) )
    {
      goto LABEL_43;
    }
    v15 = v13[9];
    v16 = *(_DWORD *)(v15 + 408) & 1;
    if ( ((__int64)a5[25].Buffer & 1) != 0 )
    {
      if ( v16 )
        goto LABEL_34;
    }
    else if ( !v16 )
    {
      if ( *(_DWORD *)(v15 + 40) == 1 && *(_QWORD *)(v15 + 56) && LODWORD(a5[2].Buffer) == 1 && a5[3].Buffer )
      {
        v17 = *(_QWORD *)&a5[2].Length;
        v24[0] = 0;
        if ( (*(int (__fastcall **)(__int64, PCUNICODE_STRING, __int64, _BYTE *))(*(_QWORD *)v17 + 256LL))(
               v17,
               a5 + 3,
               v15 + 48,
               v24) < 0
          || !v24[0] )
        {
          goto LABEL_43;
        }
      }
      else if ( *(_QWORD *)v31.data != *(_QWORD *)(v15 + 128) || *(_QWORD *)&v31.data[1] != *(_QWORD *)(v15 + 136) )
      {
        goto LABEL_43;
      }
LABEL_34:
      if ( !RtlEqualUnicodeString(a5 + 1, (PCUNICODE_STRING)(v13[9] + 16), 0)
        && !RtlEqualUnicodeString(a5 + 1, (PCUNICODE_STRING)(v13[9] + 112), 0) )
      {
        goto LABEL_43;
      }
      Buffer = (const UNICODE_STRING *)a5[17].Buffer;
      if ( Buffer )
      {
        v19 = *(const UNICODE_STRING **)(v13[9] + 280);
        if ( v19 )
        {
          if ( !RtlEqualUnicodeString(Buffer, v19, 0)
            || !CertCompareCertificate(
                  1u,
                  *(PCERT_INFO *)(*((_QWORD *)a5[17].Buffer + 4) + 24LL),
                  *(PCERT_INFO *)(*(_QWORD *)(*(_QWORD *)(v13[9] + 280) + 32LL) + 24LL)) )
          {
            goto LABEL_43;
          }
        }
      }
      v7 = v13;
      goto LABEL_41;
    }
LABEL_43:
    v13 = (__int64 *)*v13;
    if ( v13 == (__int64 *)&KerbCredentialList )
    {
      v7 = v25;
      goto LABEL_45;
    }
  }
  if ( v14 || v13[17] )
    goto LABEL_43;
LABEL_41:
  if ( v28->LowPart != *((_DWORD *)v13 + 28) || v28->HighPart != *((_DWORD *)v13 + 29) )
    goto LABEL_43;
  KerbReferenceListEntryNoLock2((struct _KERBEROS_LIST2 *)&KerbCredentialList, (struct _KERBEROS_LIST_ENTRY *)v13, 0);
  ++*((_DWORD *)v13 + 6);
  v8 = 1;
  if ( v13[9] == v22 )
    v23 = 0;
  else
    v23 = (const void *)*((unsigned __int16 *)v13 + 37);
  KerbTracerT::Log(
    8,
    "KerbLocateCredential",
    1659,
    "KerbLocateCredential found credential %p, supplied creds %p, HandleCount %d\n",
    (const void *)WORD1(v13),
    v23,
    *((_DWORD *)v13 + 6));
LABEL_45:
  RtlLeaveCriticalSection(&stru_180144A70);
LABEL_46:
  v20 = &v31;
  result = (struct _KERB_CREDENTIAL *)((unsigned __int64)v7 & -(__int64)(v8 != 0));
  do
  {
    v20->data[0].data[0] = 0;
    v20 = (_LM_OWF_PASSWORD *)((char *)v20 + 1);
    --v11;
  }
  while ( v11 );
  return result;
}

```

## disassembly

```asm
0x180047b60  push    rbp
0x180047b62  push    rbx
0x180047b63  push    rsi
0x180047b64  push    rdi
0x180047b65  push    r12
0x180047b67  push    r13
0x180047b69  push    r14
0x180047b6b  push    r15
0x180047b6d  lea     rbp, [rsp-7]
0x180047b72  sub     rsp, 0A8h
0x180047b79  mov     rax, cs:__security_cookie
0x180047b80  xor     rax, rsp
0x180047b83  mov     [rbp+3Fh+var_50], rax
0x180047b87  mov     rax, [rbp+3Fh+arg_30]
0x180047b8b  xor     esi, esi
0x180047b8d  mov     rdi, [rbp+3Fh+arg_20]
0x180047b91  xor     r15b, r15b
0x180047b94  mov     [rbp+3Fh+String1], rax
0x180047b98  xorps   xmm0, xmm0
0x180047b9b  xor     eax, eax
0x180047b9d  mov     [rbp+3Fh+var_80], r9
0x180047ba1  mov     [rbp+3Fh+var_88], r8
0x180047ba5  xorps   xmm1, xmm1
0x180047ba8  mov     [rbp+3Fh+var_68], rax
0x180047bac  mov     r12d, edx
0x180047baf  mov     r13, rcx
0x180047bb2  movups  [rbp+3Fh+var_78], xmm0
0x180047bb6  movdqu  xmmword ptr [rbp+3Fh+var_60.data.data], xmm1
0x180047bbb  test    rdi, rdi
0x180047bbe  jz      short loc_180047BE5
0x180047bc0  test    byte ptr [rdi+198h], 1
0x180047bc7  jnz     short loc_180047BE5
0x180047bc9  lea     rcx, [rdi+20h]; struct _KERB_PLAINTEXT_PASSWORD *
0x180047bcd  mov     rax, [rcx+18h]
0x180047bd1  test    rax, rax
0x180047bd4  jnz     short loc_180047BDC
0x180047bd6  movups  xmmword ptr [rbp+3Fh+var_60.data.data], xmm0
0x180047bda  jmp     short loc_180047BE5
0x180047bdc  lea     rdx, [rbp+3Fh+var_60]; struct _LM_OWF_PASSWORD *
0x180047be0  call    ?KerbCalculatePasswordComparisonHash@@YAXPEBU_KERB_PLAINTEXT_PASSWORD@@PEAU_LM_OWF_PASSWORD@@@Z; KerbCalculatePasswordComparisonHash(_KERB_PLAINTEXT_PASSWORD const *,_LM_OWF_PASSWORD *)
0x180047be5  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x180047bec  lea     rcx, [rbp+3Fh+var_78]
0x180047bf0  mov     rax, [rax+0C0h]
0x180047bf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047bfc  mov     r14d, 10h
0x180047c02  test    al, al
0x180047c04  jnz     short loc_180047C28
0x180047c06  lea     r9, aFailedToGetCli_0; "Failed to get client info:."
0x180047c0d  mov     r8d, 5AAh
0x180047c13  lea     rdx, aKerblocatecred_0; "KerbLocateCredential"
0x180047c1a  lea     ecx, [r14-0Fh]
0x180047c1e  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180047c23  jmp     loc_180047E79
0x180047c28  or      r12d, [rbp+3Fh+arg_28]
0x180047c2c  lea     rcx, stru_180144A70; CriticalSection
0x180047c33  call    cs:__imp_RtlEnterCriticalSection
0x180047c39  mov     rbx, cs:?KerbCredentialList@@3U_KERBEROS_LIST2@@A; _KERBEROS_LIST2 KerbCredentialList
0x180047c40  lea     rax, ?KerbCredentialList@@3U_KERBEROS_LIST2@@A; _KERBEROS_LIST2 KerbCredentialList
0x180047c47  cmp     rbx, rax
0x180047c4a  jz      loc_180047E6C
0x180047c50  mov     eax, dword ptr [rbp+3Fh+var_78]
0x180047c53  mov     rsi, rbx
0x180047c56  mov     [rbp+3Fh+var_98], rbx
0x180047c5a  cmp     [rbx+44h], eax
0x180047c5d  jnz     loc_180047E55
0x180047c63  mov     eax, [rbx+40h]
0x180047c66  and     eax, 70000013h
0x180047c6b  cmp     eax, r12d
0x180047c6e  jnz     loc_180047E55
0x180047c74  test    byte ptr [rbx+40h], 40h
0x180047c78  jnz     loc_180047E55
0x180047c7e  mov     eax, [r13+0]
0x180047c82  cmp     [rbx+1Ch], eax
0x180047c85  jnz     loc_180047E55
0x180047c8b  mov     eax, [r13+4]
0x180047c8f  cmp     [rbx+20h], eax
0x180047c92  jnz     loc_180047E55
0x180047c98  mov     rcx, [rbp+3Fh+String1]; String1
0x180047c9c  lea     rdx, [rbx+30h]; String2
0x180047ca0  xor     r8d, r8d; CaseInsensitive
0x180047ca3  call    cs:__imp_RtlEqualUnicodeString
0x180047ca9  test    al, al
0x180047cab  jz      loc_180047E55
0x180047cb1  mov     rdx, [rbp+3Fh+var_88]
0x180047cb5  mov     rcx, [rbx+60h]
0x180047cb9  call    cs:__imp_LsaIEqualSupplementalTokenInfo
0x180047cbf  test    eax, eax
0x180047cc1  jz      loc_180047E55
0x180047cc7  mov     rax, [rbx+48h]
0x180047ccb  test    rdi, rdi
0x180047cce  jz      loc_180047EB2
0x180047cd4  test    rax, rax
0x180047cd7  jz      loc_180047E55
0x180047cdd  cmp     qword ptr [rbx+88h], 0
0x180047ce5  jnz     loc_180047E55
0x180047ceb  xor     r8d, r8d; CaseInsensitive
0x180047cee  mov     rdx, rax; String2
0x180047cf1  mov     rcx, rdi; String1
0x180047cf4  call    cs:__imp_RtlEqualUnicodeString
0x180047cfa  test    al, al
0x180047cfc  jnz     short loc_180047D1A
0x180047cfe  mov     rdx, [rbx+48h]
0x180047d02  xor     r8d, r8d; CaseInsensitive
0x180047d05  add     rdx, 60h ; '`'; String2
0x180047d09  mov     rcx, rdi; String1
0x180047d0c  call    cs:__imp_RtlEqualUnicodeString
0x180047d12  test    al, al
0x180047d14  jz      loc_180047E55
0x180047d1a  mov     rdx, [rbx+48h]
0x180047d1e  mov     eax, [rdx+198h]
0x180047d24  and     eax, 1
0x180047d27  test    byte ptr [rdi+198h], 1
0x180047d2e  jz      short loc_180047D3A
0x180047d30  test    eax, eax
0x180047d32  jz      loc_180047E55
0x180047d38  jmp     short loc_180047DB4
0x180047d3a  test    eax, eax
0x180047d3c  jnz     loc_180047E55
0x180047d42  cmp     dword ptr [rdx+28h], 1
0x180047d46  jnz     short loc_180047D92
0x180047d48  cmp     qword ptr [rdx+38h], 0
0x180047d4d  jz      short loc_180047D92
0x180047d4f  cmp     dword ptr [rdi+28h], 1
0x180047d53  jnz     short loc_180047D92
0x180047d55  cmp     qword ptr [rdi+38h], 0
0x180047d5a  jz      short loc_180047D92
0x180047d5c  mov     rcx, [rdi+20h]
0x180047d60  lea     r8, [rdx+30h]
0x180047d64  mov     [rbp+3Fh+var_A0], r15b
0x180047d68  lea     rdx, [rdi+30h]
0x180047d6c  lea     r9, [rbp+3Fh+var_A0]
0x180047d70  mov     rax, [rcx]
0x180047d73  mov     rax, [rax+100h]
0x180047d7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047d7f  test    eax, eax
0x180047d81  js      loc_180047E55
0x180047d87  cmp     [rbp+3Fh+var_A0], r15b
0x180047d8b  jnz     short loc_180047DB4
0x180047d8d  jmp     loc_180047E55
0x180047d92  mov     rax, qword ptr [rbp+3Fh+var_60.data.data]
0x180047d96  cmp     rax, [rdx+80h]
0x180047d9d  jnz     loc_180047E55
0x180047da3  mov     rax, qword ptr [rbp+3Fh+var_60.data.data+8]
0x180047da7  cmp     rax, [rdx+88h]
0x180047dae  jnz     loc_180047E55
0x180047db4  mov     rdx, [rbx+48h]
0x180047db8  lea     rcx, [rdi+10h]; String1
0x180047dbc  add     rdx, r14; String2
0x180047dbf  xor     r8d, r8d; CaseInsensitive
0x180047dc2  call    cs:__imp_RtlEqualUnicodeString
0x180047dc8  test    al, al
0x180047dca  jnz     short loc_180047DE5
0x180047dcc  mov     rdx, [rbx+48h]
0x180047dd0  lea     rcx, [rdi+10h]; String1
0x180047dd4  add     rdx, 70h ; 'p'; String2
0x180047dd8  xor     r8d, r8d; CaseInsensitive
0x180047ddb  call    cs:__imp_RtlEqualUnicodeString
0x180047de1  test    al, al
0x180047de3  jz      short loc_180047E55
0x180047de5  mov     rcx, [rdi+118h]; String1
0x180047dec  test    rcx, rcx
0x180047def  jz      short loc_180047E3F
0x180047df1  mov     rax, [rbx+48h]
0x180047df5  mov     rdx, [rax+118h]; String2
0x180047dfc  test    rdx, rdx
0x180047dff  jz      short loc_180047E3F
0x180047e01  xor     r8d, r8d; CaseInsensitive
0x180047e04  call    cs:__imp_RtlEqualUnicodeString
0x180047e0a  test    al, al
0x180047e0c  jz      short loc_180047E55
0x180047e0e  mov     rax, [rbx+48h]
0x180047e12  mov     rcx, [rax+118h]
0x180047e19  mov     rax, [rdi+118h]
0x180047e20  mov     r8, [rcx+20h]
0x180047e24  mov     ecx, 1; dwCertEncodingType
0x180047e29  mov     rdx, [rax+20h]
0x180047e2d  mov     r8, [r8+18h]; pCertId2
0x180047e31  mov     rdx, [rdx+18h]; pCertId1
0x180047e35  call    cs:__imp_CertCompareCertificate
0x180047e3b  test    eax, eax
0x180047e3d  jz      short loc_180047E55
0x180047e3f  mov     rsi, rbx
0x180047e42  mov     rcx, [rbp+3Fh+var_80]
0x180047e46  mov     eax, [rbx+70h]
0x180047e49  cmp     [rcx], eax
0x180047e4b  jnz     short loc_180047E55
0x180047e4d  mov     eax, [rbx+74h]
0x180047e50  cmp     [rcx+4], eax
0x180047e53  jz      short loc_180047EC2
0x180047e55  mov     rbx, [rbx]
0x180047e58  lea     rax, ?KerbCredentialList@@3U_KERBEROS_LIST2@@A; _KERBEROS_LIST2 KerbCredentialList
0x180047e5f  cmp     rbx, rax
0x180047e62  jnz     loc_180047C50
0x180047e68  mov     rsi, [rbp+3Fh+var_98]
0x180047e6c  lea     rcx, stru_180144A70; CriticalSection
0x180047e73  call    cs:__imp_RtlLeaveCriticalSection
0x180047e79  neg     r15b
0x180047e7c  lea     rcx, [rbp+3Fh+var_60]
0x180047e80  sbb     rax, rax
0x180047e83  and     rax, rsi
0x180047e86  mov     byte ptr [rcx], 0
0x180047e89  inc     rcx
0x180047e8c  sub     r14, 1
0x180047e90  jnz     short loc_180047E86
0x180047e92  mov     rcx, [rbp+3Fh+var_50]
0x180047e96  xor     rcx, rsp; StackCookie
0x180047e99  call    __security_check_cookie
0x180047e9e  add     rsp, 0A8h
0x180047ea5  pop     r15
0x180047ea7  pop     r14
0x180047ea9  pop     r13
0x180047eab  pop     r12
0x180047ead  pop     rdi
0x180047eae  pop     rsi
0x180047eaf  pop     rbx
0x180047eb0  pop     rbp
0x180047eb1  retn
0x180047eb2  test    rax, rax
0x180047eb5  jnz     short loc_180047E55
0x180047eb7  cmp     [rbx+88h], rax
0x180047ebe  jnz     short loc_180047E55
0x180047ec0  jmp     short loc_180047E42
0x180047ec2  xor     r8d, r8d; unsigned __int8
0x180047ec5  lea     rcx, ?KerbCredentialList@@3U_KERBEROS_LIST2@@A; struct _KERBEROS_LIST2 *
0x180047ecc  mov     rdx, rbx; struct _KERBEROS_LIST_ENTRY *
0x180047ecf  call    ?KerbReferenceListEntryNoLock2@@YAXPEAU_KERBEROS_LIST2@@PEAU_KERBEROS_LIST_ENTRY@@E@Z; KerbReferenceListEntryNoLock2(_KERBEROS_LIST2 *,_KERBEROS_LIST_ENTRY *,uchar)
0x180047ed4  inc     dword ptr [rbx+18h]
0x180047ed7  mov     r15b, 1
0x180047eda  mov     edx, [rbx+18h]
0x180047edd  cmp     [rbx+48h], r8
0x180047ee1  jz      short loc_180047EE9
0x180047ee3  movzx   ecx, word ptr [rbx+4Ah]
0x180047ee7  jmp     short loc_180047EEB
0x180047ee9  xor     ecx, ecx
0x180047eeb  mov     [rsp+0E0h+var_B0], edx
0x180047eef  lea     r9, aKerblocatecred; "KerbLocateCredential found credential %"...
0x180047ef6  mov     [rsp+0E0h+var_B8], rcx
0x180047efb  lea     rdx, aKerblocatecred_0; "KerbLocateCredential"
0x180047f02  shr     rbx, 10h
0x180047f06  mov     r8d, 67Bh
0x180047f0c  movzx   eax, bx
0x180047f0f  mov     ecx, 8
0x180047f14  mov     [rsp+0E0h+var_C0], rax
0x180047f19  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180047f1e  jmp     loc_180047E6C
```
