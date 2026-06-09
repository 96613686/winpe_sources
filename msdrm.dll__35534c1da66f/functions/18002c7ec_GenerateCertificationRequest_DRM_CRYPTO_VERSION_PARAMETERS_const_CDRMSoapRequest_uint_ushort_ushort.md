# GenerateCertificationRequest(_DRM_CRYPTO_VERSION_PARAMETERS const *,CDRMSoapRequest *,uint,ushort *,ushort *)

- ea: `0x18002c7ec`
- end: `0x18002ca6c`
- name: `?GenerateCertificationRequest@@YAJPEBU_DRM_CRYPTO_VERSION_PARAMETERS@@PEAVCDRMSoapRequest@@IPEAG2@Z`
- size: `640`
- prototype: `int(const struct _DRM_CRYPTO_VERSION_PARAMETERS *, struct CDRMSoapRequest *, unsigned int, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18002c390`

## callees

- `0x180001284`
- `0x18000420c`
- `0x1800046c8`
- `0x18002c7ec`
- `0x18002ca74`
- `0x180039350`
- `0x180047758`
- `0x180047c38`
- `0x180047c68`
- `0x180048b20`
- `0x180048edc`
- `0x18004ba58`
- `0x18005bd8a`

## string_xrefs

- `0x18002c894`: `http://microsoft.com/DRM/CertificationService`
- `0x18002c907`: `http://microsoft.com/DRM/CertificationService`
- `0x18002c87e`: `CertificationService`
- `0x18002c8f1`: `CertificationService`

## pseudocode

```c
__int64 __fastcall GenerateCertificationRequest(
        const struct _DRM_CRYPTO_VERSION_PARAMETERS *a1,
        struct CDRMSoapRequest *a2,
        char a3,
        unsigned __int16 *a4,
        unsigned __int16 *String1)
{
  unsigned __int16 *v5; // r14
  const unsigned __int16 *v6; // r13
  unsigned int v7; // r15d
  unsigned __int16 **v8; // rsi
  __int64 v11; // r8
  __int64 v12; // r9
  int Header; // edi
  int Request; // eax
  const unsigned __int16 *v15; // rdx
  unsigned int v16; // r8d
  __int64 v17; // rdx
  __int64 v18; // rdx
  int MachineCert; // eax
  int v20; // eax
  __int64 v21; // rdx
  __int64 i; // r14
  unsigned __int16 **v24; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int16 *v25; // [rsp+48h] [rbp-8h] BYREF
  unsigned int v27; // [rsp+A0h] [rbp+50h] BYREF

  v5 = 0;
  v6 = L"false";
  v7 = 0;
  v25 = 0;
  v8 = 0;
  v27 = 0;
  v24 = 0;
  if ( (a3 & 4) == 0 )
    v6 = L"true";
  if ( !String1 || !a2 )
    goto LABEL_21;
  if ( wcscmp_0(String1, L"PassportAuthProvider") )
  {
    Header = CDRMSoapRequest::SetServerMethod(a2, L"CertificationService", L"Certify");
    if ( Header < 0 )
      goto LABEL_22;
    Request = CDRMSoapRequest::CreateRequest(
                a2,
                L"Certify",
                L"requestParams",
                L"http://microsoft.com/DRM/CertificationService",
                2u);
    goto LABEL_12;
  }
  if ( !(unsigned __int8)DRMIsValidStringT<unsigned short>(a4, 0, v11, v12) )
  {
LABEL_21:
    Header = -2147024809;
    goto LABEL_22;
  }
  Header = CDRMSoapRequest::SetServerMethod(a2, L"CertificationService", L"CertifyPassportName");
  if ( Header < 0 )
    goto LABEL_22;
  Header = CDRMSoapRequest::CreateRequest(
             a2,
             L"CertifyPassportName",
             L"requestParams",
             L"http://microsoft.com/DRM/CertificationService",
             4u);
  if ( Header < 0 )
    goto LABEL_22;
  Request = CDRMSoapRequest::AddParam(a2, 1, 0, L"UserName", 3, a4);
LABEL_12:
  Header = Request;
  if ( Request >= 0 )
  {
    Header = CDRMSoapRequest::CreateHeader(a2, v15, v16);
    if ( Header >= 0 )
    {
      Header = CDRMSoapRequest::AddHeaderParameter(a2, v17, L"MinimumVersion");
      if ( Header >= 0 )
      {
        Header = CDRMSoapRequest::AddHeaderParameter(a2, v18, L"MaximumVersion");
        if ( Header >= 0 )
        {
          MachineCert = GetMachineCert(a1, &v25);
          v5 = v25;
          Header = MachineCert;
          if ( MachineCert >= 0 )
          {
            v20 = ExtractConcatenatedChain(v25, &v27, &v24);
            if ( v20 >= 0 )
            {
              v7 = v27;
              v8 = v24;
              Header = CDRMSoapRequest::AddArray(a2, v21, 0, L"MachineCertificateChain");
              if ( Header >= 0 )
                Header = CDRMSoapRequest::AddParam(a2, 1, 0, L"Persistent", 3, v6);
            }
            else
            {
              _RTLTRACE(
                "[msdrm]: GenerateCertificationRequest - ExtractConcatenatedChain function FAILED with hr = %x ",
                v20);
              v7 = v27;
              Header = -2147168451;
              v8 = v24;
            }
          }
        }
      }
    }
  }
LABEL_22:
  operator delete(v5);
  if ( v8 )
  {
    for ( i = 0; (unsigned int)i < v7; i = (unsigned int)(i + 1) )
    {
      operator delete(v8[i]);
      v8[i] = 0;
    }
    operator delete(v8);
  }
  return (unsigned int)Header;
}

```

## disassembly

```asm
0x18002c7ec  mov     [rsp-38h+arg_8], rbx
0x18002c7f1  mov     [rsp-38h+arg_0], rcx
0x18002c7f6  push    rbp
0x18002c7f7  push    rsi
0x18002c7f8  push    rdi
0x18002c7f9  push    r12
0x18002c7fb  push    r13
0x18002c7fd  push    r14
0x18002c7ff  push    r15
0x18002c801  mov     rbp, rsp
0x18002c804  sub     rsp, 50h
0x18002c808  mov     rcx, [rbp+String1]; String1
0x18002c80c  lea     rax, ?g_wszSOAP_TRUE@@3QBGB; "true"
0x18002c813  xor     r14d, r14d
0x18002c816  lea     r13, ?g_wszSOAP_FALSE@@3QBGB; "false"
0x18002c81d  xor     r15d, r15d
0x18002c820  mov     [rbp+var_8], r14
0x18002c824  xor     esi, esi
0x18002c826  mov     [rbp+arg_10], r15d
0x18002c82a  test    r8b, 4
0x18002c82e  mov     [rbp+var_10], rsi
0x18002c832  mov     r12, r9
0x18002c835  mov     rbx, rdx
0x18002c838  cmovz   r13, rax
0x18002c83c  test    rcx, rcx
0x18002c83f  jz      loc_18002CA17
0x18002c845  test    rdx, rdx
0x18002c848  jz      loc_18002CA17
0x18002c84e  lea     rdx, aPassportauthpr; "PassportAuthProvider"
0x18002c855  call    wcscmp_0
0x18002c85a  test    eax, eax
0x18002c85c  jnz     loc_18002C8E7
0x18002c862  xor     edx, edx
0x18002c864  mov     rcx, r12
0x18002c867  call    ??$DRMIsValidStringT@G@@YA_NPEBGPEA_K@Z; DRMIsValidStringT<ushort>(ushort const *,unsigned __int64 *)
0x18002c86c  test    al, al
0x18002c86e  jz      loc_18002CA17
0x18002c874  lea     r8, ?g_wszACT_CertifyPassportName@@3QBGB; "CertifyPassportName"
0x18002c87b  mov     rcx, rbx; this
0x18002c87e  lea     rdx, ?g_wszACT_CertificationService@@3QBGB; "CertificationService"
0x18002c885  call    ?SetServerMethod@CDRMSoapRequest@@QEAAJPEBG0@Z; CDRMSoapRequest::SetServerMethod(ushort const *,ushort const *)
0x18002c88a  mov     edi, eax
0x18002c88c  test    eax, eax
0x18002c88e  js      loc_18002CA1C
0x18002c894  lea     r9, ?g_wszACT_CertifyNamespace@@3QBGB; "http://microsoft.com/DRM/CertificationS"...
0x18002c89b  mov     [rsp+50h+var_30], 4; unsigned int
0x18002c8a3  lea     r8, ?g_wszACT_RequestParams@@3QBGB; "requestParams"
0x18002c8aa  mov     rcx, rbx; this
0x18002c8ad  lea     rdx, ?g_wszACT_CertifyPassportName@@3QBGB; "CertifyPassportName"
0x18002c8b4  call    ?CreateRequest@CDRMSoapRequest@@QEAAJPEBG00I@Z; CDRMSoapRequest::CreateRequest(ushort const *,ushort const *,ushort const *,uint)
0x18002c8b9  mov     edi, eax
0x18002c8bb  test    eax, eax
0x18002c8bd  js      loc_18002CA1C
0x18002c8c3  mov     [rsp+50h+var_28], r12
0x18002c8c8  lea     r9, ?g_wszACT_Identification@@3QBGB; "UserName"
0x18002c8cf  xor     r8d, r8d
0x18002c8d2  mov     [rsp+50h+var_30], 3
0x18002c8da  lea     edx, [rsi+1]
0x18002c8dd  mov     rcx, rbx
0x18002c8e0  call    ?AddParam@CDRMSoapRequest@@IEAAJHPEBG0W4SOAP_DATA_TYPE@@0@Z; CDRMSoapRequest::AddParam(int,ushort const *,ushort const *,SOAP_DATA_TYPE,ushort const *)
0x18002c8e5  jmp     short loc_18002C92C
0x18002c8e7  lea     r8, ?g_wszACT_Certify@@3QBGB; "Certify"
0x18002c8ee  mov     rcx, rbx; this
0x18002c8f1  lea     rdx, ?g_wszACT_CertificationService@@3QBGB; "CertificationService"
0x18002c8f8  call    ?SetServerMethod@CDRMSoapRequest@@QEAAJPEBG0@Z; CDRMSoapRequest::SetServerMethod(ushort const *,ushort const *)
0x18002c8fd  mov     edi, eax
0x18002c8ff  test    eax, eax
0x18002c901  js      loc_18002CA1C
0x18002c907  lea     r9, ?g_wszACT_CertifyNamespace@@3QBGB; "http://microsoft.com/DRM/CertificationS"...
0x18002c90e  mov     [rsp+50h+var_30], 2; unsigned int
0x18002c916  lea     r8, ?g_wszACT_RequestParams@@3QBGB; "requestParams"
0x18002c91d  mov     rcx, rbx; this
0x18002c920  lea     rdx, ?g_wszACT_Certify@@3QBGB; "Certify"
0x18002c927  call    ?CreateRequest@CDRMSoapRequest@@QEAAJPEBG00I@Z; CDRMSoapRequest::CreateRequest(ushort const *,ushort const *,ushort const *,uint)
0x18002c92c  mov     edi, eax
0x18002c92e  test    eax, eax
0x18002c930  js      loc_18002CA1C
0x18002c936  mov     rcx, rbx; this
0x18002c939  call    ?CreateHeader@CDRMSoapRequest@@QEAAJPEBGI@Z; CDRMSoapRequest::CreateHeader(ushort const *,uint)
0x18002c93e  mov     edi, eax
0x18002c940  test    eax, eax
0x18002c942  js      loc_18002CA1C
0x18002c948  lea     r8, ?g_wszACT_MinimumVersion@@3QBGB; "MinimumVersion"
0x18002c94f  mov     rcx, rbx
0x18002c952  call    ?AddHeaderParameter@CDRMSoapRequest@@QEAAJPEBG0W4SOAP_DATA_TYPE@@0@Z; CDRMSoapRequest::AddHeaderParameter(ushort const *,ushort const *,SOAP_DATA_TYPE,ushort const *)
0x18002c957  mov     edi, eax
0x18002c959  test    eax, eax
0x18002c95b  js      loc_18002CA1C
0x18002c961  lea     r8, ?g_wszACT_MaximumVersion@@3QBGB; "MaximumVersion"
0x18002c968  mov     rcx, rbx
0x18002c96b  call    ?AddHeaderParameter@CDRMSoapRequest@@QEAAJPEBG0W4SOAP_DATA_TYPE@@0@Z; CDRMSoapRequest::AddHeaderParameter(ushort const *,ushort const *,SOAP_DATA_TYPE,ushort const *)
0x18002c970  mov     edi, eax
0x18002c972  test    eax, eax
0x18002c974  js      loc_18002CA1C
0x18002c97a  mov     rcx, [rbp+arg_0]; struct _DRM_CRYPTO_VERSION_PARAMETERS *
0x18002c97e  lea     rdx, [rbp+var_8]; unsigned __int16 **
0x18002c982  call    ?GetMachineCert@@YAJPEBU_DRM_CRYPTO_VERSION_PARAMETERS@@PEAPEAG@Z; GetMachineCert(_DRM_CRYPTO_VERSION_PARAMETERS const *,ushort * *)
0x18002c987  mov     r14, [rbp+var_8]
0x18002c98b  mov     edi, eax
0x18002c98d  test    eax, eax
0x18002c98f  js      loc_18002CA1C
0x18002c995  lea     r8, [rbp+var_10]; unsigned __int16 ***
0x18002c999  mov     rcx, r14; unsigned __int16 *
0x18002c99c  lea     rdx, [rbp+arg_10]; unsigned int *
0x18002c9a0  call    ?ExtractConcatenatedChain@@YAJPEBGPEAIPEAPEAPEAG@Z; ExtractConcatenatedChain(ushort const *,uint *,ushort * * *)
0x18002c9a5  test    eax, eax
0x18002c9a7  jns     short loc_18002C9C6
0x18002c9a9  mov     edx, eax
0x18002c9ab  lea     rcx, aMsdrmGeneratec; "[msdrm]: GenerateCertificationRequest -"...
0x18002c9b2  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18002c9b7  mov     r15d, [rbp+arg_10]
0x18002c9bb  mov     edi, 8004CF3Dh
0x18002c9c0  mov     rsi, [rbp+var_10]
0x18002c9c4  jmp     short loc_18002CA1C
0x18002c9c6  mov     r15d, [rbp+arg_10]
0x18002c9ca  lea     r9, ?g_wszACT_MachineCertificate@@3QBGB; "MachineCertificateChain"
0x18002c9d1  mov     rsi, [rbp+var_10]
0x18002c9d5  xor     r8d, r8d
0x18002c9d8  mov     [rsp+50h+var_18], r15d
0x18002c9dd  mov     rcx, rbx
0x18002c9e0  mov     [rsp+50h+var_20], rsi
0x18002c9e5  call    ?AddArray@CDRMSoapRequest@@IEAAJHPEBG00W4SOAP_DATA_TYPE@@PEAPEAGI@Z; CDRMSoapRequest::AddArray(int,ushort const *,ushort const *,ushort const *,SOAP_DATA_TYPE,ushort * *,uint)
0x18002c9ea  mov     edi, eax
0x18002c9ec  test    eax, eax
0x18002c9ee  js      short loc_18002CA1C
0x18002c9f0  xor     r8d, r8d
0x18002c9f3  mov     [rsp+50h+var_28], r13
0x18002c9f8  lea     r9, ?g_wszACT_Persistent@@3QBGB; "Persistent"
0x18002c9ff  mov     [rsp+50h+var_30], 3
0x18002ca07  mov     rcx, rbx
0x18002ca0a  lea     edx, [r8+1]
0x18002ca0e  call    ?AddParam@CDRMSoapRequest@@IEAAJHPEBG0W4SOAP_DATA_TYPE@@0@Z; CDRMSoapRequest::AddParam(int,ushort const *,ushort const *,SOAP_DATA_TYPE,ushort const *)
0x18002ca13  mov     edi, eax
0x18002ca15  jmp     short loc_18002CA1C
0x18002ca17  mov     edi, 80070057h
0x18002ca1c  mov     rcx, r14; Block
0x18002ca1f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002ca24  test    rsi, rsi
0x18002ca27  jz      short loc_18002CA52
0x18002ca29  xor     r14d, r14d
0x18002ca2c  test    r15d, r15d
0x18002ca2f  jz      short loc_18002CA4A
0x18002ca31  mov     rcx, [rsi+r14*8]; Block
0x18002ca35  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002ca3a  mov     qword ptr [rsi+r14*8], 0
0x18002ca42  inc     r14d
0x18002ca45  cmp     r14d, r15d
0x18002ca48  jb      short loc_18002CA31
0x18002ca4a  mov     rcx, rsi; Block
0x18002ca4d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002ca52  mov     rbx, [rsp+50h+arg_8]
0x18002ca5a  mov     eax, edi
0x18002ca5c  add     rsp, 50h
0x18002ca60  pop     r15
0x18002ca62  pop     r14
0x18002ca64  pop     r13
0x18002ca66  pop     r12
0x18002ca68  pop     rdi
0x18002ca69  pop     rsi
0x18002ca6a  pop     rbp
0x18002ca6b  retn
```
