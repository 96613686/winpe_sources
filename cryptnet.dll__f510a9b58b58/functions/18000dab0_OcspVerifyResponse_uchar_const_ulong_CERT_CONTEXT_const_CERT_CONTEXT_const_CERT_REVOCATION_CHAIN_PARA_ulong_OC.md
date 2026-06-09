# OcspVerifyResponse(uchar const *,ulong,_CERT_CONTEXT const *,_CERT_CONTEXT const *,_CERT_REVOCATION_CHAIN_PARA *,ulong,_OCSP_BASIC_RESPONSE_INFO * *,_CERT_CONTEXT const * *,_OCSP_STRONG_SIGN_PROP_INFO *,ulong)

- ea: `0x18000dab0`
- end: `0x18000dda4`
- name: `?OcspVerifyResponse@@YAHPEBEKPEBU_CERT_CONTEXT@@1PEAU_CERT_REVOCATION_CHAIN_PARA@@KPEAPEAU_OCSP_BASIC_RESPONSE_INFO@@PEAPEBU1@PEAU_OCSP_STRONG_SIGN_PROP_INFO@@K@Z`
- size: `756`
- prototype: `__int64 __fastcall(BYTE *pbEncoded, DWORD cbEncoded, const struct _CERT_CONTEXT *, const struct _CERT_CONTEXT *pvIssuer, struct _CERT_REVOCATION_CHAIN_PARA *, unsigned int, struct _OCSP_BASIC_RESPONSE_INFO **, const struct _CERT_CONTEXT **, struct _OCSP_STRONG_SIGN_PROP_INFO *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x18000ca20`
- `0x1800101e0`

## callees

- `0x18000a990`
- `0x18000dab0`
- `0x18000ddb0`
- `0x18000f004`
- `0x180026576`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dd8b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dd8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dca9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dd47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dd63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dca9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dd47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dd63`
- `CRYPT32!I_CertDiagControl` at `0x18000dce1`
- `CRYPT32!I_CertDiagControl` at `0x18000dce1`
- `CRYPT32!CryptDecodeObjectEx` at `0x18000db29`
- `CRYPT32!CryptDecodeObjectEx` at `0x18000db99`
- `CRYPT32!CryptDecodeObjectEx` at `0x18000dbdb`
- `CRYPT32!CryptDecodeObjectEx` at `0x18000db29`
- `CRYPT32!CryptDecodeObjectEx` at `0x18000db99`
- `CRYPT32!CryptDecodeObjectEx` at `0x18000dbdb`

## string_xrefs

- `0x18000dd78`: `IsResponseCriticalExtensionSupported`
- `0x18000dd7f`: `UnsupportedOcspResponseCriticalExtension`

## pseudocode

```c
__int64 __fastcall OcspVerifyResponse(
        BYTE *pbEncoded,
        DWORD cbEncoded,
        const struct _CERT_CONTEXT *a3,
        struct _CERT_CONTEXT *pvIssuer,
        struct _CERT_REVOCATION_CHAIN_PARA *a5,
        unsigned int a6,
        struct _OCSP_BASIC_RESPONSE_INFO **a7,
        const struct _CERT_CONTEXT **a8,
        struct _OCSP_STRONG_SIGN_PROP_INFO *a9,
        unsigned int a10)
{
  HLOCAL v12; // rbx
  DWORD LastError; // r14d
  const char *v14; // rcx
  int v15; // eax
  __int64 v16; // rcx
  const struct _CERT_CONTEXT *OcspSignerCert; // rdi
  unsigned int v18; // ebx
  __int64 result; // rax
  const wchar_t *v20; // r15
  const char *v21; // rbx
  HLOCAL hMem; // [rsp+50h] [rbp-39h] BYREF
  HLOCAL pvStructInfo; // [rsp+58h] [rbp-31h] BYREF
  __int64 v24[2]; // [rsp+60h] [rbp-29h] BYREF
  _QWORD v25[2]; // [rsp+70h] [rbp-19h] BYREF
  DWORD v26; // [rsp+80h] [rbp-9h]
  int v27; // [rsp+84h] [rbp-5h]
  __int64 v28; // [rsp+88h] [rbp-1h]
  HLOCAL v29; // [rsp+C0h] [rbp+37h] BYREF
  DWORD pcbStructInfo; // [rsp+C8h] [rbp+3Fh] BYREF

  v24[0] = cbEncoded;
  v24[1] = (__int64)pbEncoded;
  pvStructInfo = 0;
  pcbStructInfo = 0;
  hMem = 0;
  v29 = 0;
  if ( !CryptDecodeObjectEx(
          0x10001u,
          (LPCSTR)0x43,
          pbEncoded,
          cbEncoded,
          0x8005u,
          &PkiDecodePara,
          &pvStructInfo,
          &pcbStructInfo) )
  {
    v20 = L"Call_CryptDecodeObject_OCSP_RESPONSE";
    LastError = GetLastError();
    v21 = "DecodeResponse";
LABEL_15:
    v25[1] = v20;
    v25[0] = v24;
    v26 = LastError;
    v27 = 0;
    v28 = 0;
    OcspSignerCert = 0;
    I_CertDiagControl(6, v25, 0);
    goto LABEL_16;
  }
  v12 = pvStructInfo;
  LastError = 0;
  if ( *(_DWORD *)pvStructInfo )
  {
    v20 = L"CheckResponseStatus";
    v21 = "InvalidResponseStatus";
LABEL_26:
    SetLastError(0x80092013);
    goto LABEL_15;
  }
  v14 = (const char *)*((_QWORD *)pvStructInfo + 1);
  if ( !v14 )
  {
    v20 = L"IsMissingResponseOID";
    v21 = "MissingResponseOID";
    goto LABEL_26;
  }
  if ( strcmp_0(v14, "1.3.6.1.5.5.7.48.1.1") )
  {
    v20 = L"IsUnsupportedResponseOID";
    v21 = "UnsupportedResponseOID";
    goto LABEL_26;
  }
  if ( !CryptDecodeObjectEx(
          0x10001u,
          (LPCSTR)0x44,
          *((const BYTE **)v12 + 3),
          *((_DWORD *)v12 + 4),
          0x8005u,
          &PkiDecodePara,
          &hMem,
          &pcbStructInfo) )
  {
    v20 = L"Call_CryptDecodeObject_OCSP_BASIC_SIGNED_RESPONSE";
    LastError = GetLastError();
    v21 = "DecodeBasicSignedResponse";
    goto LABEL_15;
  }
  if ( !CryptDecodeObjectEx(
          0x10001u,
          (LPCSTR)0x45,
          *((const BYTE **)hMem + 1),
          *(_DWORD *)hMem,
          0x8005u,
          &PkiDecodePara,
          &v29,
          &pcbStructInfo) )
  {
    v20 = L"Call_CryptDecodeObject_OCSP_BASIC_RESPONSE";
    LastError = GetLastError();
    v21 = "DecodeBasicResponse";
    goto LABEL_15;
  }
  v15 = *((_DWORD *)v29 + 12);
  v16 = *((_QWORD *)v29 + 7);
  while ( v15 )
  {
    if ( *(_DWORD *)(v16 + 8) )
    {
      v20 = L"IsResponseCriticalExtensionSupported";
      v21 = "UnsupportedOcspResponseCriticalExtension";
      goto LABEL_26;
    }
    --v15;
    v16 += 32;
  }
  OcspSignerCert = (const struct _CERT_CONTEXT *)I_GetOcspSignerCert(
                                                   pvIssuer,
                                                   hMem,
                                                   (__int64)v24,
                                                   (__int64)a5,
                                                   a6,
                                                   a9,
                                                   a10);
  if ( OcspSignerCert )
  {
    v18 = 1;
    goto LABEL_11;
  }
  v21 = "GetSignerCert";
LABEL_16:
  I_OcspDebugErrorPrintfA(v21, a3);
  if ( v29 )
  {
    operator delete(v29);
    v29 = 0;
  }
  v18 = 0;
LABEL_11:
  operator delete(hMem);
  operator delete(pvStructInfo);
  result = v18;
  *a7 = (struct _OCSP_BASIC_RESPONSE_INFO *)v29;
  *a8 = OcspSignerCert;
  return result;
}

```

## disassembly

```asm
0x18000dab0  mov     [rsp-8+arg_10], rbx
0x18000dab5  mov     [rsp-8+arg_18], rsi
0x18000daba  push    rbp
0x18000dabb  push    rdi
0x18000dabc  push    r12
0x18000dabe  push    r14
0x18000dac0  push    r15
0x18000dac2  lea     rbp, [rsp-7]
0x18000dac7  sub     rsp, 90h
0x18000dace  xor     eax, eax
0x18000dad0  mov     dword ptr [rbp+27h+var_50], edx
0x18000dad3  xor     r12d, r12d
0x18000dad6  mov     dword ptr [rbp+27h+var_50+4], eax
0x18000dad9  lea     rax, [rbp+27h+arg_8]
0x18000dadd  mov     [rbp+27h+var_48], rcx
0x18000dae1  mov     [rsp+0B0h+pcbStructInfo], rax; pcbStructInfo
0x18000dae6  lea     r15, PkiDecodePara
0x18000daed  lea     rax, [rbp+27h+var_58]
0x18000daf1  mov     [rbp+27h+var_58], r12
0x18000daf5  mov     [rsp+0B0h+pvStructInfo], rax; pvStructInfo
0x18000dafa  mov     rdi, r9
0x18000dafd  mov     rsi, r8
0x18000db00  mov     [rsp+0B0h+pDecodePara], r15; pDecodePara
0x18000db05  mov     r9d, edx; cbEncoded
0x18000db08  mov     [rsp+0B0h+dwFlags], 8005h; dwFlags
0x18000db10  mov     r8, rcx; pbEncoded
0x18000db13  mov     [rbp+27h+arg_8], r12d
0x18000db17  mov     edx, 43h ; 'C'; lpszStructType
0x18000db1c  mov     [rbp+27h+hMem], r12
0x18000db20  mov     ecx, 10001h; dwCertEncodingType
0x18000db25  mov     [rbp+27h+arg_0], r12
0x18000db29  call    cs:__imp_CryptDecodeObjectEx
0x18000db2f  test    eax, eax
0x18000db31  jz      loc_18000DCA2
0x18000db37  mov     rbx, [rbp+27h+var_58]
0x18000db3b  mov     r14d, r12d
0x18000db3e  cmp     [rbx], r12d
0x18000db41  jnz     loc_18000DD10
0x18000db47  mov     rcx, [rbx+8]; Str1
0x18000db4b  test    rcx, rcx
0x18000db4e  jz      loc_18000DD20
0x18000db54  lea     rdx, Str2; "1.3.6.1.5.5.7.48.1.1"
0x18000db5b  call    strcmp_0
0x18000db60  test    eax, eax
0x18000db62  jnz     loc_18000DD30
0x18000db68  mov     r9d, [rbx+10h]; cbEncoded
0x18000db6c  lea     rax, [rbp+27h+arg_8]
0x18000db70  mov     r8, [rbx+18h]; pbEncoded
0x18000db74  mov     edx, 44h ; 'D'; lpszStructType
0x18000db79  mov     [rsp+0B0h+pcbStructInfo], rax; pcbStructInfo
0x18000db7e  mov     ecx, 10001h; dwCertEncodingType
0x18000db83  lea     rax, [rbp+27h+hMem]
0x18000db87  mov     [rsp+0B0h+pvStructInfo], rax; pvStructInfo
0x18000db8c  mov     [rsp+0B0h+pDecodePara], r15; pDecodePara
0x18000db91  mov     [rsp+0B0h+dwFlags], 8005h; dwFlags
0x18000db99  call    cs:__imp_CryptDecodeObjectEx
0x18000db9f  test    eax, eax
0x18000dba1  jz      loc_18000DD40
0x18000dba7  mov     r8, [rbp+27h+hMem]
0x18000dbab  lea     rax, [rbp+27h+arg_8]
0x18000dbaf  mov     [rsp+0B0h+pcbStructInfo], rax; pcbStructInfo
0x18000dbb4  mov     edx, 45h ; 'E'; lpszStructType
0x18000dbb9  lea     rax, [rbp+27h+arg_0]
0x18000dbbd  mov     ecx, 10001h; dwCertEncodingType
0x18000dbc2  mov     [rsp+0B0h+pvStructInfo], rax; pvStructInfo
0x18000dbc7  mov     r9d, [r8]; cbEncoded
0x18000dbca  mov     r8, [r8+8]; pbEncoded
0x18000dbce  mov     [rsp+0B0h+pDecodePara], r15; pDecodePara
0x18000dbd3  mov     [rsp+0B0h+dwFlags], 8005h; dwFlags
0x18000dbdb  call    cs:__imp_CryptDecodeObjectEx
0x18000dbe1  test    eax, eax
0x18000dbe3  jz      loc_18000DD5C
0x18000dbe9  mov     r8, [rbp+27h+arg_0]
0x18000dbed  mov     eax, [r8+30h]
0x18000dbf1  mov     rcx, [r8+38h]
0x18000dbf5  test    eax, eax
0x18000dbf7  jnz     loc_18000DC8D
0x18000dbfd  mov     eax, [rbp+27h+arg_48]
0x18000dc00  lea     r9, [r8+8]
0x18000dc04  mov     r8d, [r8+4]
0x18000dc08  mov     rcx, rdi; pvIssuer
0x18000dc0b  mov     rdx, [rbp+27h+hMem]; pvSubject
0x18000dc0f  mov     [rsp+0B0h+var_70], eax; int
0x18000dc13  mov     rax, [rbp+27h+arg_40]
0x18000dc17  mov     [rsp+0B0h+pcbStructInfo], rax; void *
0x18000dc1c  mov     eax, [rbp+27h+arg_28]
0x18000dc1f  mov     dword ptr [rsp+0B0h+pvStructInfo], eax; unsigned int
0x18000dc23  mov     rax, [rbp+27h+arg_20]
0x18000dc27  mov     [rsp+0B0h+pDecodePara], rax; __int64
0x18000dc2c  lea     rax, [rbp+27h+var_50]
0x18000dc30  mov     qword ptr [rsp+0B0h+dwFlags], rax; __int64
0x18000dc35  call    I_GetOcspSignerCert
0x18000dc3a  mov     rdi, rax
0x18000dc3d  test    rax, rax
0x18000dc40  jz      loc_18000DD07
0x18000dc46  mov     ebx, 1
0x18000dc4b  mov     rcx, [rbp+27h+hMem]; hMem
0x18000dc4f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000dc54  mov     rcx, [rbp+27h+var_58]; hMem
0x18000dc58  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000dc5d  mov     rcx, [rbp+27h+arg_30]
0x18000dc61  lea     r11, [rsp+0B0h+var_20]
0x18000dc69  mov     rdx, [rbp+27h+arg_0]
0x18000dc6d  mov     eax, ebx
0x18000dc6f  mov     rbx, [r11+40h]
0x18000dc73  mov     rsi, [r11+48h]
0x18000dc77  mov     [rcx], rdx
0x18000dc7a  mov     rcx, [rbp+27h+arg_38]
0x18000dc7e  mov     [rcx], rdi
0x18000dc81  mov     rsp, r11
0x18000dc84  pop     r15
0x18000dc86  pop     r14
0x18000dc88  pop     r12
0x18000dc8a  pop     rdi
0x18000dc8b  pop     rbp
0x18000dc8c  retn
0x18000dc8d  cmp     [rcx+8], r12d
0x18000dc91  jnz     loc_18000DD78
0x18000dc97  dec     eax
0x18000dc99  add     rcx, 20h ; ' '
0x18000dc9d  jmp     loc_18000DBF5
0x18000dca2  lea     r15, aCallCryptdecod_1; "Call_CryptDecodeObject_OCSP_RESPONSE"
0x18000dca9  call    cs:__imp_GetLastError
0x18000dcaf  mov     r14d, eax
0x18000dcb2  lea     rbx, aDecoderesponse; "DecodeResponse"
0x18000dcb9  lea     rax, [rbp+27h+var_50]
0x18000dcbd  mov     [rbp+27h+var_38], r15
0x18000dcc1  mov     [rbp+27h+var_40], rax
0x18000dcc5  lea     rdx, [rbp+27h+var_40]
0x18000dcc9  xor     eax, eax
0x18000dccb  mov     [rbp+27h+var_30], r14d
0x18000dccf  xor     r8d, r8d
0x18000dcd2  mov     [rbp+27h+var_2C], eax
0x18000dcd5  mov     ecx, 6
0x18000dcda  mov     [rbp+27h+var_28], r12
0x18000dcde  mov     rdi, r12
0x18000dce1  call    cs:__imp_I_CertDiagControl
0x18000dce7  mov     rdx, rsi; struct _CERT_CONTEXT *
0x18000dcea  mov     rcx, rbx; char *
0x18000dced  call    ?I_OcspDebugErrorPrintfA@@YAXPEBDPEBU_CERT_CONTEXT@@@Z; I_OcspDebugErrorPrintfA(char const *,_CERT_CONTEXT const *)
0x18000dcf2  mov     rcx, [rbp+27h+arg_0]; hMem
0x18000dcf6  test    rcx, rcx
0x18000dcf9  jnz     loc_18000DD96
0x18000dcff  mov     ebx, r12d
0x18000dd02  jmp     loc_18000DC4B
0x18000dd07  lea     rbx, aGetsignercert; "GetSignerCert"
0x18000dd0e  jmp     short loc_18000DCE7
0x18000dd10  lea     r15, aCheckresponses; "CheckResponseStatus"
0x18000dd17  lea     rbx, aInvalidrespons; "InvalidResponseStatus"
0x18000dd1e  jmp     short loc_18000DD86
0x18000dd20  lea     r15, aIsmissingrespo; "IsMissingResponseOID"
0x18000dd27  lea     rbx, aMissingrespons; "MissingResponseOID"
0x18000dd2e  jmp     short loc_18000DD86
0x18000dd30  lea     r15, aIsunsupportedr; "IsUnsupportedResponseOID"
0x18000dd37  lea     rbx, aUnsupportedres; "UnsupportedResponseOID"
0x18000dd3e  jmp     short loc_18000DD86
0x18000dd40  lea     r15, aCallCryptdecod_0; "Call_CryptDecodeObject_OCSP_BASIC_SIGNE"...
0x18000dd47  call    cs:__imp_GetLastError
0x18000dd4d  mov     r14d, eax
0x18000dd50  lea     rbx, aDecodebasicsig; "DecodeBasicSignedResponse"
0x18000dd57  jmp     loc_18000DCB9
0x18000dd5c  lea     r15, aCallCryptdecod; "Call_CryptDecodeObject_OCSP_BASIC_RESPO"...
0x18000dd63  call    cs:__imp_GetLastError
0x18000dd69  mov     r14d, eax
0x18000dd6c  lea     rbx, aDecodebasicres; "DecodeBasicResponse"
0x18000dd73  jmp     loc_18000DCB9
0x18000dd78  lea     r15, aIsresponsecrit; "IsResponseCriticalExtensionSupported"
0x18000dd7f  lea     rbx, aUnsupportedocs; "UnsupportedOcspResponseCriticalExtensio"...
0x18000dd86  mov     ecx, 80092013h; dwErrCode
0x18000dd8b  call    cs:__imp_SetLastError
0x18000dd91  jmp     loc_18000DCB9
0x18000dd96  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000dd9b  mov     [rbp+27h+arg_0], r12
0x18000dd9f  jmp     loc_18000DCFF
```
