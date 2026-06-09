# EncryptRecoveryPassword(void *,_CERT_CONTEXT const *,_UNICODE_STRING *)

- ea: `0x180036dc0`
- end: `0x18003720c`
- name: `?EncryptRecoveryPassword@@YAKPEAXPEBU_CERT_CONTEXT@@PEAU_UNICODE_STRING@@@Z`
- size: `1100`
- prototype: `__int64 __fastcall(__int64, const struct _CERT_CONTEXT *, struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180038234`
- `0x180038a00`

## callees

- `0x180003080`
- `0x180007f10`
- `0x18000c4a0`
- `0x18001c9c0`
- `0x18001d810`
- `0x180029818`
- `0x180036a18`
- `0x180036dc0`
- `0x1800385fc`
- `0x18003c62c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036e6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036feb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800370d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036e6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036feb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800370d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003716d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037196`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800371c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003716d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037196`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800371c1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180036f81`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180036f81`
- `bcrypt!BCryptEncrypt` at `0x18003706b`
- `bcrypt!BCryptEncrypt` at `0x18003706b`
- `bcrypt!BCryptDestroyKey` at `0x1800371d6`
- `bcrypt!BCryptDestroyKey` at `0x1800371d6`
- `bcrypt!BCryptGetProperty` at `0x180036ebb`
- `bcrypt!BCryptGetProperty` at `0x180036ebb`
- `ntdll!RtlNtStatusToDosError` at `0x18003709a`
- `ntdll!RtlNtStatusToDosError` at `0x180037157`
- `ntdll!RtlNtStatusToDosError` at `0x18003709a`
- `ntdll!RtlNtStatusToDosError` at `0x180037157`
- `CRYPT32!CryptImportPublicKeyInfoEx2` at `0x180036e5b`
- `CRYPT32!CryptImportPublicKeyInfoEx2` at `0x180036e5b`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180036fdb`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180036fdb`

## string_xrefs

- `0x180036e88`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\recovery.cpp`
- `0x180036f59`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\recovery.cpp`
- `0x180037083`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\recovery.cpp`
- `0x1800370e8`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\recovery.cpp`
- `0x180037123`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\recovery.cpp`
- `0x180037140`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\recovery.cpp`

## pseudocode

```c
__int64 __fastcall EncryptRecoveryPassword(__int64 a1, const struct _CERT_CONTEXT *a2, struct _UNICODE_STRING *a3)
{
  _DWORD *v3; // rdi
  DWORD v4; // r12d
  void *v5; // r14
  HLOCAL v6; // rsi
  DWORD LastError; // eax
  __int64 v10; // r9
  ULONG v11; // ebx
  __int64 v12; // rcx
  NTSTATUS Property; // eax
  NTSTATUS v14; // ebx
  ULONG Length; // edx
  ULONG Signature; // eax
  __int64 v17; // r9
  __int64 v18; // rcx
  size_t v19; // rbx
  _DWORD *v20; // rax
  DWORD *v21; // rsi
  void *v22; // rdx
  ULONG v23; // r8d
  UCHAR *v24; // rdx
  NTSTATUS v25; // eax
  NTSTATUS v26; // ebx
  ULONG v27; // eax
  UCHAR *v28; // rax
  __int64 v29; // rcx
  __int64 v30; // rcx
  _BYTE *v31; // rax
  UCHAR pbOutput[4]; // [rsp+50h] [rbp-29h] BYREF
  ULONG pcbResult; // [rsp+54h] [rbp-25h] BYREF
  size_t Size; // [rsp+58h] [rbp-21h] BYREF
  void *Src; // [rsp+60h] [rbp-19h] BYREF
  BCRYPT_KEY_HANDLE hObject; // [rsp+68h] [rbp-11h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp-9h] BYREF
  __int64 v39; // [rsp+78h] [rbp-1h]
  UCHAR v40[24]; // [rsp+80h] [rbp+7h] BYREF

  v39 = a1;
  hObject = 0;
  v3 = 0;
  v4 = 0;
  Src = 0;
  v5 = 0;
  LODWORD(Size) = 0;
  pcbResult = 0;
  v6 = 0;
  *(_DWORD *)pbOutput = 0;
  hMem = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 10, WPP_f5cee88f95423c4d1ee5d29d95c63987_Traceguids);
  if ( !CryptImportPublicKeyInfoEx2(a2->dwCertEncodingType, &a2->pCertInfo->SubjectPublicKeyInfo, 0, 0, &hObject) )
  {
    LastError = GetLastError();
    v10 = 197;
LABEL_6:
    v11 = LastError;
    v12 = LastError;
LABEL_7:
    DebugTraceError(v12, "dwError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\recovery.cpp", v10);
    goto LABEL_30;
  }
  Property = BCryptGetProperty(hObject, L"BlockLength", pbOutput, 4u, &pcbResult, 0);
  v14 = Property;
  if ( Property < 0 || pcbResult < 4 )
  {
    DebugTraceError(
      (unsigned int)Property,
      "ntStatus",
      "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\recovery.cpp",
      209);
    v11 = RtlNtStatusToDosError(v14);
  }
  else
  {
    Length = a3->Length;
    if ( Length + 20 > *(_DWORD *)pbOutput )
    {
      v12 = 13;
      v10 = 217;
      v11 = 13;
      goto LABEL_7;
    }
    if ( !(unsigned int)FMyPrimitiveSHA((PUCHAR)a3->Buffer, Length, v40) )
    {
      v12 = 13;
      v10 = 229;
      v11 = 13;
      goto LABEL_7;
    }
    Signature = LogonCredGenerateSignature(
                  v39,
                  a2->pbCertEncoded,
                  a2->cbCertEncoded,
                  v40,
                  (unsigned int **)&Src,
                  (DWORD *)&Size);
    v11 = Signature;
    if ( Signature )
    {
      v17 = 248;
      v18 = Signature;
LABEL_16:
      DebugTraceError(v18, "dwError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\recovery.cpp", v17);
      v5 = Src;
      goto LABEL_30;
    }
    v19 = (unsigned int)Size;
    v4 = Size + *(_DWORD *)pbOutput + 36;
    v20 = LocalAlloc(0, v4);
    v3 = v20;
    if ( !v20 )
    {
      v11 = 8;
      v17 = 268;
      v18 = 8;
      goto LABEL_16;
    }
    v20[3] = 0;
    v21 = v20 + 1;
    v5 = Src;
    v22 = Src;
    *v20 = 1;
    v20[1] = 20;
    v20[2] = v19;
    memcpy_0(v20 + 9, v22, v19);
    if ( !CertGetCertificateContextProperty(a2, 3u, v3 + 4, v21) )
    {
      LastError = GetLastError();
      v10 = 289;
      goto LABEL_6;
    }
    memcpy_0((char *)v3 + *v21 + v3[2] + 16, a3->Buffer, a3->Length);
    v23 = a3->Length;
    v24 = (UCHAR *)v3 + *v21 + v3[2] + 16;
    v3[3] = v23;
    v25 = BCryptEncrypt(hObject, v24, v23, 0, 0, 0, v24, *(ULONG *)pbOutput, v3 + 3, 2u);
    v26 = v25;
    if ( v25 < 0 )
    {
      DebugTraceError(
        (unsigned int)v25,
        "ntStatus",
        "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\recovery.cpp",
        320);
      v11 = RtlNtStatusToDosError(v26);
      goto LABEL_30;
    }
    FMyReverseBytes((unsigned __int8 *)v3 + *v21 + v3[2] + 16, v3[3]);
    if ( (unsigned int)GetTokenUserSid(v39, &hMem) )
    {
      v6 = hMem;
      v27 = RecoverySetSupplementalCredential((__int64)hMem, (const BYTE *)v3, v4);
      v11 = v27;
      if ( v27 )
        DebugTraceError(v27, "dwError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\recovery.cpp", 350);
    }
    else
    {
      v11 = GetLastError();
      DebugTraceError(v11, "dwError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\recovery.cpp", 339);
      v6 = hMem;
    }
  }
  if ( v6 )
    LocalFree(v6);
LABEL_30:
  v28 = v40;
  v29 = 20;
  do
  {
    *v28++ = 0;
    --v29;
  }
  while ( v29 );
  if ( v5 )
    LocalFree(v5);
  if ( v3 )
  {
    v30 = v4;
    v31 = v3;
    if ( v4 )
    {
      do
      {
        *v31++ = 0;
        --v30;
      }
      while ( v30 );
    }
    LocalFree(v3);
  }
  if ( hObject )
    BCryptDestroyKey(hObject);
  return v11;
}

```

## disassembly

```asm
0x180036dc0  mov     [rsp-8+arg_18], rbx
0x180036dc5  push    rbp
0x180036dc6  push    rsi
0x180036dc7  push    rdi
0x180036dc8  push    r12
0x180036dca  push    r13
0x180036dcc  push    r14
0x180036dce  push    r15
0x180036dd0  lea     rbp, [rsp-27h]
0x180036dd5  sub     rsp, 0A0h
0x180036ddc  mov     rax, cs:__security_cookie
0x180036de3  xor     rax, rsp
0x180036de6  mov     [rbp+57h+var_38], rax
0x180036dea  xor     ebx, ebx
0x180036dec  mov     [rbp+57h+var_58], rcx
0x180036df0  mov     [rbp+57h+hObject], rbx
0x180036df4  mov     edi, ebx
0x180036df6  mov     r12d, ebx
0x180036df9  mov     [rbp+57h+Src], rbx
0x180036dfd  mov     r14d, ebx
0x180036e00  mov     dword ptr [rbp+57h+Size], ebx
0x180036e03  mov     [rbp+57h+pcbResult], ebx
0x180036e06  mov     esi, ebx
0x180036e08  mov     dword ptr [rbp+57h+pbOutput], ebx
0x180036e0b  mov     r13, r8
0x180036e0e  mov     [rbp+57h+hMem], rbx
0x180036e12  mov     r15, rdx
0x180036e15  mov     rcx, cs:WPP_GLOBAL_Control
0x180036e1c  lea     rax, WPP_GLOBAL_Control
0x180036e23  cmp     rcx, rax
0x180036e26  jz      short loc_180036E41
0x180036e28  test    byte ptr [rcx+1Ch], 4
0x180036e2c  jz      short loc_180036E41
0x180036e2e  mov     rcx, [rcx+10h]
0x180036e32  lea     edx, [rbx+0Ah]
0x180036e35  lea     r8, WPP_f5cee88f95423c4d1ee5d29d95c63987_Traceguids
0x180036e3c  call    WPP_SF_
0x180036e41  mov     rdx, [r15+18h]
0x180036e45  lea     rax, [rbp+57h+hObject]
0x180036e49  mov     ecx, [r15]; dwCertEncodingType
0x180036e4c  add     rdx, 60h ; '`'; pInfo
0x180036e50  xor     r9d, r9d; pvAuxInfo
0x180036e53  mov     [rsp+0D0h+phKey], rax; phKey
0x180036e58  xor     r8d, r8d; dwFlags
0x180036e5b  call    cs:__imp_CryptImportPublicKeyInfoEx2
0x180036e62  nop     dword ptr [rax+rax+00h]
0x180036e67  test    eax, eax
0x180036e69  jnz     short loc_180036E99
0x180036e6b  call    cs:__imp_GetLastError
0x180036e72  nop     dword ptr [rax+rax+00h]
0x180036e77  mov     r9d, 0C5h
0x180036e7d  mov     ebx, eax
0x180036e7f  mov     ecx, eax
0x180036e81  lea     rdx, aDwerror; "dwError"
0x180036e88  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180036e8f  call    DebugTraceError
0x180036e94  jmp     loc_180037179
0x180036e99  mov     rcx, [rbp+57h+hObject]; hObject
0x180036e9d  lea     rax, [rbp+57h+pcbResult]
0x180036ea1  mov     [rsp+0D0h+dwFlags], ebx; dwFlags
0x180036ea5  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x180036ea9  mov     r9d, 4; cbOutput
0x180036eaf  mov     [rsp+0D0h+phKey], rax; pcbResult
0x180036eb4  lea     rdx, aBlocklength; "BlockLength"
0x180036ebb  call    cs:__imp_BCryptGetProperty
0x180036ec2  nop     dword ptr [rax+rax+00h]
0x180036ec7  mov     ebx, eax
0x180036ec9  test    eax, eax
0x180036ecb  js      loc_18003713A
0x180036ed1  cmp     [rbp+57h+pcbResult], 4
0x180036ed5  jb      loc_18003713A
0x180036edb  movzx   edx, word ptr [r13+0]; cbInput
0x180036ee0  lea     eax, [rdx+14h]
0x180036ee3  cmp     eax, dword ptr [rbp+57h+pbOutput]
0x180036ee6  jbe     short loc_180036EF7
0x180036ee8  mov     ecx, 0Dh
0x180036eed  mov     r9d, 0D9h
0x180036ef3  mov     ebx, ecx
0x180036ef5  jmp     short loc_180036E81
0x180036ef7  mov     rcx, [r13+8]; pbInput
0x180036efb  lea     rax, [rbp+57h+var_50]
0x180036eff  mov     [rsp+0D0h+phKey], rax; PUCHAR
0x180036f04  call    FMyPrimitiveSHA
0x180036f09  test    eax, eax
0x180036f0b  jnz     short loc_180036F1D
0x180036f0d  lea     ecx, [rax+0Dh]
0x180036f10  mov     r9d, 0E5h
0x180036f16  mov     ebx, ecx
0x180036f18  jmp     loc_180036E81
0x180036f1d  mov     r8d, [r15+10h]
0x180036f21  lea     rax, [rbp+57h+Size]
0x180036f25  mov     rdx, [r15+8]
0x180036f29  lea     r9, [rbp+57h+var_50]
0x180036f2d  mov     rcx, [rbp+57h+var_58]
0x180036f31  mov     qword ptr [rsp+0D0h+dwFlags], rax
0x180036f36  lea     rax, [rbp+57h+Src]
0x180036f3a  mov     [rsp+0D0h+phKey], rax
0x180036f3f  call    LogonCredGenerateSignature
0x180036f44  mov     ebx, eax
0x180036f46  test    eax, eax
0x180036f48  jz      short loc_180036F6E
0x180036f4a  mov     r9d, 0F8h
0x180036f50  mov     ecx, eax
0x180036f52  lea     rdx, aDwerror; "dwError"
0x180036f59  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180036f60  call    DebugTraceError
0x180036f65  mov     r14, [rbp+57h+Src]
0x180036f69  jmp     loc_180037179
0x180036f6e  mov     r12d, dword ptr [rbp+57h+pbOutput]
0x180036f72  xor     ecx, ecx; uFlags
0x180036f74  mov     ebx, dword ptr [rbp+57h+Size]
0x180036f77  add     r12d, 24h ; '$'
0x180036f7b  add     r12d, ebx
0x180036f7e  mov     edx, r12d; uBytes
0x180036f81  call    cs:__imp_LocalAlloc
0x180036f88  nop     dword ptr [rax+rax+00h]
0x180036f8d  mov     rdi, rax
0x180036f90  test    rax, rax
0x180036f93  jnz     short loc_180036FA2
0x180036f95  lea     ebx, [rax+8]
0x180036f98  mov     r9d, 10Ch
0x180036f9e  mov     ecx, ebx
0x180036fa0  jmp     short loc_180036F52
0x180036fa2  mov     [rax+0Ch], r14d
0x180036fa6  lea     rsi, [rax+4]
0x180036faa  mov     r14, [rbp+57h+Src]
0x180036fae  lea     rcx, [rax+24h]; void *
0x180036fb2  mov     rdx, r14; Src
0x180036fb5  mov     dword ptr [rax], 1
0x180036fbb  mov     r8, rbx; Size
0x180036fbe  mov     dword ptr [rsi], 14h
0x180036fc4  mov     [rax+8], ebx
0x180036fc7  call    memcpy_0
0x180036fcc  lea     r8, [rdi+10h]; pvData
0x180036fd0  mov     r9, rsi; pcbData
0x180036fd3  mov     edx, 3; dwPropId
0x180036fd8  mov     rcx, r15; pCertContext
0x180036fdb  call    cs:__imp_CertGetCertificateContextProperty
0x180036fe2  nop     dword ptr [rax+rax+00h]
0x180036fe7  test    eax, eax
0x180036fe9  jnz     short loc_180037002
0x180036feb  call    cs:__imp_GetLastError
0x180036ff2  nop     dword ptr [rax+rax+00h]
0x180036ff7  mov     r9d, 121h
0x180036ffd  jmp     loc_180036E7D
0x180037002  mov     eax, [rsi]
0x180037004  mov     ecx, [rdi+8]
0x180037007  add     rax, 10h
0x18003700b  movzx   r8d, word ptr [r13+0]; Size
0x180037010  add     rax, rdi
0x180037013  mov     rdx, [r13+8]; Src
0x180037017  add     rcx, rax; void *
0x18003701a  call    memcpy_0
0x18003701f  mov     edx, [rsi]
0x180037021  lea     r15, [rdi+0Ch]
0x180037025  mov     ecx, [rdi+8]
0x180037028  add     rdx, rdi
0x18003702b  movzx   r8d, word ptr [r13+0]; cbInput
0x180037030  add     rcx, 10h
0x180037034  mov     [rsp+0D0h+var_88], 2; dwFlags
0x18003703c  add     rdx, rcx; pbInput
0x18003703f  mov     [rsp+0D0h+var_90], r15; pcbResult
0x180037044  xor     r9d, r9d; pPaddingInfo
0x180037047  mov     [r15], r8d
0x18003704a  mov     eax, dword ptr [rbp+57h+pbOutput]
0x18003704d  mov     rcx, [rbp+57h+hObject]; hKey
0x180037051  mov     [rsp+0D0h+cbOutput], eax; cbOutput
0x180037055  mov     [rsp+0D0h+var_A0], rdx; pbOutput
0x18003705a  mov     [rsp+0D0h+dwFlags], 0; cbIV
0x180037062  mov     [rsp+0D0h+phKey], 0; pbIV
0x18003706b  call    cs:__imp_BCryptEncrypt
0x180037072  nop     dword ptr [rax+rax+00h]
0x180037077  mov     ebx, eax
0x180037079  test    eax, eax
0x18003707b  jns     short loc_1800370AD
0x18003707d  mov     r9d, 140h
0x180037083  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18003708a  lea     rdx, aNtstatus; "ntStatus"
0x180037091  mov     ecx, eax
0x180037093  call    DebugTraceError
0x180037098  mov     ecx, ebx; Status
0x18003709a  call    cs:__imp_RtlNtStatusToDosError
0x1800370a1  nop     dword ptr [rax+rax+00h]
0x1800370a6  mov     ebx, eax
0x1800370a8  jmp     loc_180037179
0x1800370ad  mov     ecx, [rsi]
0x1800370af  mov     r8d, [rdi+8]
0x1800370b3  add     rcx, rdi
0x1800370b6  mov     edx, [r15]; unsigned int
0x1800370b9  add     r8, 10h
0x1800370bd  add     rcx, r8; unsigned __int8 *
0x1800370c0  call    ?FMyReverseBytes@@YAXPEAEK@Z; FMyReverseBytes(uchar *,ulong)
0x1800370c5  mov     rcx, [rbp+57h+var_58]
0x1800370c9  lea     rdx, [rbp+57h+hMem]
0x1800370cd  call    GetTokenUserSid
0x1800370d2  test    eax, eax
0x1800370d4  jnz     short loc_180037105
0x1800370d6  call    cs:__imp_GetLastError
0x1800370dd  nop     dword ptr [rax+rax+00h]
0x1800370e2  mov     r9d, 153h
0x1800370e8  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800370ef  mov     ecx, eax
0x1800370f1  lea     rdx, aDwerror; "dwError"
0x1800370f8  mov     ebx, eax
0x1800370fa  call    DebugTraceError
0x1800370ff  mov     rsi, [rbp+57h+hMem]
0x180037103  jmp     short loc_180037165
0x180037105  mov     rsi, [rbp+57h+hMem]
0x180037109  mov     r8d, r12d
0x18003710c  mov     rcx, rsi
0x18003710f  mov     rdx, rdi
0x180037112  call    RecoverySetSupplementalCredential
0x180037117  mov     ebx, eax
0x180037119  test    eax, eax
0x18003711b  jz      short loc_180037165
0x18003711d  mov     r9d, 15Eh
0x180037123  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18003712a  lea     rdx, aDwerror; "dwError"
0x180037131  mov     ecx, eax
0x180037133  call    DebugTraceError
0x180037138  jmp     short loc_180037165
0x18003713a  mov     r9d, 0D1h
0x180037140  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180037147  lea     rdx, aNtstatus; "ntStatus"
0x18003714e  mov     ecx, ebx
0x180037150  call    DebugTraceError
0x180037155  mov     ecx, ebx; Status
0x180037157  call    cs:__imp_RtlNtStatusToDosError
0x18003715e  nop     dword ptr [rax+rax+00h]
0x180037163  mov     ebx, eax
0x180037165  test    rsi, rsi
0x180037168  jz      short loc_180037179
0x18003716a  mov     rcx, rsi; hMem
0x18003716d  call    cs:__imp_LocalFree
0x180037174  nop     dword ptr [rax+rax+00h]
0x180037179  lea     rax, [rbp+57h+var_50]
0x18003717d  mov     ecx, 14h
0x180037182  mov     byte ptr [rax], 0
0x180037185  inc     rax
0x180037188  sub     rcx, 1
0x18003718c  jnz     short loc_180037182
0x18003718e  test    r14, r14
0x180037191  jz      short loc_1800371A2
0x180037193  mov     rcx, r14; hMem
0x180037196  call    cs:__imp_LocalFree
0x18003719d  nop     dword ptr [rax+rax+00h]
0x1800371a2  test    rdi, rdi
0x1800371a5  jz      short loc_1800371CD
0x1800371a7  mov     ecx, r12d
0x1800371aa  mov     rax, rdi
0x1800371ad  test    r12d, r12d
0x1800371b0  jz      short loc_1800371BE
0x1800371b2  mov     byte ptr [rax], 0
0x1800371b5  inc     rax
0x1800371b8  sub     rcx, 1
0x1800371bc  jnz     short loc_1800371B2
0x1800371be  mov     rcx, rdi; hMem
0x1800371c1  call    cs:__imp_LocalFree
0x1800371c8  nop     dword ptr [rax+rax+00h]
0x1800371cd  mov     rcx, [rbp+57h+hObject]; hKey
0x1800371d1  test    rcx, rcx
0x1800371d4  jz      short loc_1800371E2
0x1800371d6  call    cs:__imp_BCryptDestroyKey
0x1800371dd  nop     dword ptr [rax+rax+00h]
0x1800371e2  mov     eax, ebx
0x1800371e4  mov     rcx, [rbp+57h+var_38]
0x1800371e8  xor     rcx, rsp; StackCookie
0x1800371eb  call    __security_check_cookie
0x1800371f0  mov     rbx, [rsp+0D0h+arg_18]
0x1800371f8  add     rsp, 0A0h
0x1800371ff  pop     r15
0x180037201  pop     r14
0x180037203  pop     r13
0x180037205  pop     r12
0x180037207  pop     rdi
0x180037208  pop     rsi
0x180037209  pop     rbp
0x18003720a  retn
```
