# CDimInterfaceTable::GetInterfaceByCertificate(_IKEv2_CERT_BLOB *)

- ea: `0x18000a164`
- end: `0x18000a382`
- name: `?GetInterfaceByCertificate@CDimInterfaceTable@@AEAAPEAUIDimInterface@@PEAU_IKEv2_CERT_BLOB@@@Z`
- size: `542`
- prototype: `struct IDimInterface *__fastcall(CDimInterfaceTable *__hidden this, struct _IKEv2_CERT_BLOB *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180025300`

## callees

- `0x180005670`
- `0x18000a164`
- `0x18000a388`
- `0x18000a710`
- `0x18000aaa4`
- `0x18000def0`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`

## import_xrefs

- `CRYPT32!CertFreeCertificateContext` at `0x18000a342`
- `CRYPT32!CertFreeCertificateContext` at `0x18000a342`
- `CRYPT32!CertAddEncodedCertificateToStore` at `0x18000a266`
- `CRYPT32!CertAddEncodedCertificateToStore` at `0x18000a266`
- `CRYPT32!CertOpenStore` at `0x18000a1ed`
- `CRYPT32!CertOpenStore` at `0x18000a1ed`
- `CRYPT32!CertCloseStore` at `0x18000a352`
- `CRYPT32!CertCloseStore` at `0x18000a352`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a1fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a270`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a1fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a270`

## string_xrefs

- `0x18000a1d6`: `RRAS_TEMP_CERT_STORE`
- `0x18000a211`: `GetInterfaceByCertificate CertOpenStore failed with %d`

## pseudocode

```c
struct IDimInterface *__fastcall CDimInterfaceTable::GetInterfaceByCertificate(
        CDimInterfaceTable *this,
        struct _IKEv2_CERT_BLOB *a2)
{
  __int64 v4; // rbx
  HCERTSTORE v5; // rsi
  __int64 LastError; // r8
  const wchar_t *v7; // rdx
  const wchar_t *v8; // r8
  __int64 *v9; // rdx
  PCCERT_CONTEXT pCertContext; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v12[8]; // [rsp+38h] [rbp-C8h] BYREF
  std::tr1::_Ref_count_base *v13; // [rsp+40h] [rbp-C0h]
  int v14; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v15[2044]; // [rsp+54h] [rbp-ACh] BYREF

  pCertContext = 0;
  v4 = 0;
  v14 = 0;
  memset_0(v15, 0, sizeof(v15));
  if ( !a2 || !*(_DWORD *)a2 || !*((_QWORD *)a2 + 1) )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
      return (struct IDimInterface *)v4;
    v5 = 0;
    v8 = L"GetInterfaceByCertificate bailing out with ERROR_INVALID_PARAMETER";
    v9 = RasDimTraceError;
LABEL_24:
    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, v9, v8);
    goto LABEL_25;
  }
  v5 = CertOpenStore((LPCSTR)2, 0, 0, 0, "RRAS_TEMP_CERT_STORE");
  if ( !v5 )
  {
    LastError = GetLastError();
    if ( (Microsoft_Windows_RRASEnableBits & 8) == 0 )
      goto LABEL_25;
    v7 = L"GetInterfaceByCertificate CertOpenStore failed with %d";
    goto LABEL_7;
  }
  if ( CertAddEncodedCertificateToStore(
         v5,
         *((_DWORD *)a2 + 4),
         *((const BYTE **)a2 + 1),
         *(_DWORD *)a2,
         3u,
         &pCertContext) )
  {
    if ( !pCertContext )
    {
LABEL_28:
      CertCloseStore(v5, 0);
      return (struct IDimInterface *)v4;
    }
    v4 = *(_QWORD *)CDimInterfaceTable::GetInterfaceByCertSubjectName(this, v12);
    if ( v13 )
      std::tr1::_Ref_count_base::_Decref(v13);
    if ( !v4 )
    {
      v4 = *(_QWORD *)CDimInterfaceTable::GetInterfaceByCertFriendlyName(this, v12, pCertContext);
      if ( v13 )
        std::tr1::_Ref_count_base::_Decref(v13);
      if ( !v4 )
      {
        v4 = *(_QWORD *)CDimInterfaceTable::GetInterfaceByCertSubjectAltName(this, v12, pCertContext);
        if ( v13 )
          std::tr1::_Ref_count_base::_Decref(v13);
      }
    }
    goto LABEL_25;
  }
  LastError = GetLastError();
  if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
  {
    v7 = L"GetInterfaceByCertificate CertAddEncodedCertificateToStore failed with %d";
LABEL_7:
    LOWORD(v14) = 0;
    FormatRRASErrorString(&v14, v7, LastError);
    if ( (Microsoft_Windows_RRASEnableBits & 8) == 0 )
      goto LABEL_25;
    v8 = (const wchar_t *)&v14;
    v9 = RasDimTraceInfo;
    goto LABEL_24;
  }
LABEL_25:
  if ( pCertContext )
    CertFreeCertificateContext(pCertContext);
  if ( v5 )
    goto LABEL_28;
  return (struct IDimInterface *)v4;
}

```

## disassembly

```asm
0x18000a164  mov     [rsp-8+arg_10], rbx
0x18000a169  mov     [rsp-8+arg_18], rsi
0x18000a16e  push    rbp
0x18000a16f  push    rdi
0x18000a170  push    r14
0x18000a172  lea     rbp, [rsp-760h]
0x18000a17a  sub     rsp, 860h
0x18000a181  mov     rax, cs:__security_cookie
0x18000a188  xor     rax, rsp
0x18000a18b  mov     [rbp+770h+var_20], rax
0x18000a192  mov     rdi, rdx
0x18000a195  mov     r14, rcx
0x18000a198  mov     [rsp+870h+pCertContext], 0
0x18000a1a1  xor     ebx, ebx
0x18000a1a3  xor     eax, eax
0x18000a1a5  mov     [rsp+870h+var_820], eax
0x18000a1a9  xor     edx, edx; Val
0x18000a1ab  mov     r8d, 7FCh; Size
0x18000a1b1  lea     rcx, [rsp+870h+var_81C]; void *
0x18000a1b6  call    memset_0
0x18000a1bb  test    rdi, rdi
0x18000a1be  jz      loc_18000A313
0x18000a1c4  cmp     [rdi], ebx
0x18000a1c6  jz      loc_18000A313
0x18000a1cc  cmp     [rdi+8], rbx
0x18000a1d0  jz      loc_18000A313
0x18000a1d6  lea     rax, aRrasTempCertSt; "RRAS_TEMP_CERT_STORE"
0x18000a1dd  mov     [rsp+870h+pvPara], rax; pvPara
0x18000a1e2  xor     r9d, r9d; dwFlags
0x18000a1e5  xor     r8d, r8d; hCryptProv
0x18000a1e8  xor     edx, edx; dwEncodingType
0x18000a1ea  lea     ecx, [rbx+2]; lpszStoreProvider
0x18000a1ed  call    cs:__imp_CertOpenStore
0x18000a1f3  mov     rsi, rax
0x18000a1f6  test    rax, rax
0x18000a1f9  jnz     short loc_18000A247
0x18000a1fb  call    cs:__imp_GetLastError
0x18000a201  mov     r8d, eax
0x18000a204  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x18000a20b  jz      loc_18000A338
0x18000a211  lea     rdx, aGetinterfaceby_0; "GetInterfaceByCertificate CertOpenStore"...
0x18000a218  xor     eax, eax
0x18000a21a  mov     word ptr [rsp+870h+var_820], ax
0x18000a21f  lea     rcx, [rsp+870h+var_820]
0x18000a224  call    FormatRRASErrorString
0x18000a229  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x18000a230  jz      loc_18000A338
0x18000a236  lea     r8, [rsp+870h+var_820]
0x18000a23b  lea     rdx, RasDimTraceInfo
0x18000a242  jmp     loc_18000A32C
0x18000a247  lea     rax, [rsp+870h+pCertContext]
0x18000a24c  mov     [rsp+870h+ppCertContext], rax; ppCertContext
0x18000a251  mov     dword ptr [rsp+870h+pvPara], 3; dwAddDisposition
0x18000a259  mov     r9d, [rdi]; cbCertEncoded
0x18000a25c  mov     r8, [rdi+8]; pbCertEncoded
0x18000a260  mov     edx, [rdi+10h]; dwCertEncodingType
0x18000a263  mov     rcx, rsi; hCertStore
0x18000a266  call    cs:__imp_CertAddEncodedCertificateToStore
0x18000a26c  test    eax, eax
0x18000a26e  jnz     short loc_18000A28F
0x18000a270  call    cs:__imp_GetLastError
0x18000a276  mov     r8d, eax
0x18000a279  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x18000a280  jz      loc_18000A338
0x18000a286  lea     rdx, aGetinterfaceby_4; "GetInterfaceByCertificate CertAddEncode"...
0x18000a28d  jmp     short loc_18000A218
0x18000a28f  mov     r8, [rsp+870h+pCertContext]
0x18000a294  test    r8, r8
0x18000a297  jz      loc_18000A34D
0x18000a29d  lea     rdx, [rsp+870h+var_838]
0x18000a2a2  mov     rcx, r14
0x18000a2a5  call    ?GetInterfaceByCertSubjectName@CDimInterfaceTable@@AEAA?AV?$shared_ptr@VCDimInterface@@@tr1@std@@PEBU_CERT_CONTEXT@@@Z; CDimInterfaceTable::GetInterfaceByCertSubjectName(_CERT_CONTEXT const *)
0x18000a2aa  mov     rbx, [rax]
0x18000a2ad  mov     rcx, [rsp+870h+var_830]; this
0x18000a2b2  test    rcx, rcx
0x18000a2b5  jz      short loc_18000A2BD
0x18000a2b7  call    ?_Decref@_Ref_count_base@tr1@std@@QEAAXXZ; std::tr1::_Ref_count_base::_Decref(void)
0x18000a2bc  nop
0x18000a2bd  test    rbx, rbx
0x18000a2c0  jnz     short loc_18000A338
0x18000a2c2  mov     r8, [rsp+870h+pCertContext]
0x18000a2c7  lea     rdx, [rsp+870h+var_838]
0x18000a2cc  mov     rcx, r14
0x18000a2cf  call    ?GetInterfaceByCertFriendlyName@CDimInterfaceTable@@AEAA?AV?$shared_ptr@VCDimInterface@@@tr1@std@@PEBU_CERT_CONTEXT@@@Z; CDimInterfaceTable::GetInterfaceByCertFriendlyName(_CERT_CONTEXT const *)
0x18000a2d4  mov     rbx, [rax]
0x18000a2d7  mov     rcx, [rsp+870h+var_830]; this
0x18000a2dc  test    rcx, rcx
0x18000a2df  jz      short loc_18000A2E7
0x18000a2e1  call    ?_Decref@_Ref_count_base@tr1@std@@QEAAXXZ; std::tr1::_Ref_count_base::_Decref(void)
0x18000a2e6  nop
0x18000a2e7  test    rbx, rbx
0x18000a2ea  jnz     short loc_18000A338
0x18000a2ec  mov     r8, [rsp+870h+pCertContext]
0x18000a2f1  lea     rdx, [rsp+870h+var_838]
0x18000a2f6  mov     rcx, r14
0x18000a2f9  call    ?GetInterfaceByCertSubjectAltName@CDimInterfaceTable@@AEAA?AV?$shared_ptr@VCDimInterface@@@tr1@std@@PEBU_CERT_CONTEXT@@@Z; CDimInterfaceTable::GetInterfaceByCertSubjectAltName(_CERT_CONTEXT const *)
0x18000a2fe  mov     rbx, [rax]
0x18000a301  mov     rcx, [rsp+870h+var_830]; this
0x18000a306  test    rcx, rcx
0x18000a309  jz      short loc_18000A311
0x18000a30b  call    ?_Decref@_Ref_count_base@tr1@std@@QEAAXXZ; std::tr1::_Ref_count_base::_Decref(void)
0x18000a310  nop
0x18000a311  jmp     short loc_18000A338
0x18000a313  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x18000a31a  jz      short loc_18000A358
0x18000a31c  xor     esi, esi
0x18000a31e  lea     r8, aGetinterfaceby_2; "GetInterfaceByCertificate bailing out w"...
0x18000a325  lea     rdx, RasDimTraceError
0x18000a32c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000a333  call    McTemplateU0z_EventWriteTransfer
0x18000a338  mov     rcx, [rsp+870h+pCertContext]; pCertContext
0x18000a33d  test    rcx, rcx
0x18000a340  jz      short loc_18000A348
0x18000a342  call    cs:__imp_CertFreeCertificateContext
0x18000a348  test    rsi, rsi
0x18000a34b  jz      short loc_18000A358
0x18000a34d  xor     edx, edx; dwFlags
0x18000a34f  mov     rcx, rsi; hCertStore
0x18000a352  call    cs:__imp_CertCloseStore
0x18000a358  mov     rax, rbx
0x18000a35b  mov     rcx, [rbp+770h+var_20]
0x18000a362  xor     rcx, rsp; StackCookie
0x18000a365  call    __security_check_cookie
0x18000a36a  lea     r11, [rsp+870h+var_10]
0x18000a372  mov     rbx, [r11+30h]
0x18000a376  mov     rsi, [r11+38h]
0x18000a37a  mov     rsp, r11
0x18000a37d  pop     r14
0x18000a37f  pop     rdi
0x18000a380  pop     rbp
0x18000a381  retn
```
