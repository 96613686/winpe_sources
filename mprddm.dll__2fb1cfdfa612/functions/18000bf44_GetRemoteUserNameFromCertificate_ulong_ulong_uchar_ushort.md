# GetRemoteUserNameFromCertificate(ulong,ulong,uchar *,ushort *)

- ea: `0x18000bf44`
- end: `0x18000c0f3`
- name: `?GetRemoteUserNameFromCertificate@@YAKKKPEAEPEAG@Z`
- size: `431`
- prototype: `unsigned int __fastcall(DWORD dwCertEncodingType, DWORD cbCertEncoded, BYTE *pbCertEncoded, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800342d0`

## callees

- `0x180007b7c`
- `0x18000bdc8`
- `0x18000bf44`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000bfab`
- `KERNEL32!GetLastError` at `0x18000bfab`
- `CRYPT32!CertFreeCertificateContext` at `0x18000c0cc`
- `CRYPT32!CertFreeCertificateContext` at `0x18000c0cc`
- `CRYPT32!CertCreateCertificateContext` at `0x18000bf99`
- `CRYPT32!CertCreateCertificateContext` at `0x18000bf99`

## pseudocode

```c
__int64 __fastcall GetRemoteUserNameFromCertificate(
        DWORD dwCertEncodingType,
        DWORD cbCertEncoded,
        BYTE *pbCertEncoded,
        unsigned __int16 *a4)
{
  const CERT_CONTEXT *CertificateContext; // rax
  unsigned int v9; // edx
  unsigned int v10; // r8d
  const CERT_CONTEXT *v11; // rdi
  DWORD LastError; // eax
  unsigned int v13; // ebx
  __int64 v14; // r8
  __int64 v15; // rax
  unsigned int CertSubjectName; // eax
  __int64 v17; // r8
  __int64 v18; // rax
  struct _EVENT_DATA_DESCRIPTOR v20; // [rsp+30h] [rbp-D0h] BYREF
  int *v21; // [rsp+40h] [rbp-C0h]
  int v22; // [rsp+48h] [rbp-B8h]
  int v23; // [rsp+4Ch] [rbp-B4h]
  int v24; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v25[2044]; // [rsp+54h] [rbp-ACh] BYREF

  v24 = 0;
  memset_0(v25, 0, sizeof(v25));
  CertificateContext = CertCreateCertificateContext(dwCertEncodingType, pbCertEncoded, cbCertEncoded);
  v11 = CertificateContext;
  if ( CertificateContext )
  {
    CertSubjectName = GetCertSubjectName(CertificateContext, v9, v10, a4);
    v13 = CertSubjectName;
    if ( CertSubjectName )
    {
      if ( (byte_1800C8404 & 8) != 0 )
      {
        LOWORD(v24) = 0;
        FormatRRASErrorString(
          &v24,
          L"GetRemoteUserNameFromCertificate: GetCertFriendlyName failed. Error:%d",
          CertSubjectName);
        if ( (byte_1800C8404 & 8) != 0 )
        {
          v18 = -1;
          do
            ++v18;
          while ( *(_WORD *)&v25[2 * v18 - 4] );
          v23 = 0;
          v22 = 2 * v18 + 2;
          v21 = &v24;
          McGenEventWrite_EventWriteTransfer(
            (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (const EVENT_DESCRIPTOR *)RasDdmTraceError,
            v17,
            2u,
            &v20);
        }
      }
    }
    CertFreeCertificateContext(v11);
  }
  else
  {
    LastError = GetLastError();
    v13 = LastError;
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      LOWORD(v24) = 0;
      FormatRRASErrorString(
        &v24,
        L"GetRemoteUserNameFromCertificate: Cannot get the certiificate context. Error:%d",
        LastError);
      if ( (byte_1800C8404 & 0x10) != 0 )
      {
        v15 = -1;
        do
          ++v15;
        while ( *(_WORD *)&v25[2 * v15 - 4] );
        v23 = 0;
        v22 = 2 * v15 + 2;
        v21 = &v24;
        McGenEventWrite_EventWriteTransfer(
          (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (const EVENT_DESCRIPTOR *)RasDdmTraceInfo,
          v14,
          2u,
          &v20);
      }
    }
  }
  return v13;
}

```

## disassembly

```asm
0x18000bf44  push    rbp
0x18000bf46  push    rbx
0x18000bf47  push    rsi
0x18000bf48  push    rdi
0x18000bf49  push    r14
0x18000bf4b  push    r15
0x18000bf4d  lea     rbp, [rsp-768h]
0x18000bf55  sub     rsp, 868h
0x18000bf5c  mov     rax, cs:__security_cookie
0x18000bf63  xor     rax, rsp
0x18000bf66  mov     [rbp+790h+var_40], rax
0x18000bf6d  mov     rsi, r8
0x18000bf70  mov     ebx, edx
0x18000bf72  mov     edi, ecx
0x18000bf74  xor     r15d, r15d
0x18000bf77  xor     edx, edx; Val
0x18000bf79  mov     [rsp+890h+var_840], r15d
0x18000bf7e  mov     r8d, 7FCh; Size
0x18000bf84  lea     rcx, [rsp+890h+var_83C]; void *
0x18000bf89  mov     r14, r9
0x18000bf8c  call    memset_0
0x18000bf91  mov     r8d, ebx; cbCertEncoded
0x18000bf94  mov     rdx, rsi; pbCertEncoded
0x18000bf97  mov     ecx, edi; dwCertEncodingType
0x18000bf99  call    cs:__imp_CertCreateCertificateContext
0x18000bf9f  mov     rdi, rax
0x18000bfa2  test    rax, rax
0x18000bfa5  jnz     loc_18000C03C
0x18000bfab  call    cs:__imp_GetLastError
0x18000bfb1  test    cs:byte_1800C8404, 10h
0x18000bfb8  mov     ebx, eax
0x18000bfba  jz      loc_18000C0D2
0x18000bfc0  mov     r8d, eax
0x18000bfc3  mov     word ptr [rsp+890h+var_840], r15w
0x18000bfc9  lea     rdx, aGetremoteusern_1; "GetRemoteUserNameFromCertificate: Canno"...
0x18000bfd0  lea     rcx, [rsp+890h+var_840]
0x18000bfd5  call    FormatRRASErrorString
0x18000bfda  test    cs:byte_1800C8404, 10h
0x18000bfe1  jz      loc_18000C0D2
0x18000bfe7  lea     rcx, [rsp+890h+var_840]
0x18000bfec  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000bff0  inc     rax
0x18000bff3  cmp     [rcx+rax*2], r15w
0x18000bff8  jnz     short loc_18000BFF0
0x18000bffa  lea     eax, ds:2[rax*2]
0x18000c001  mov     [rsp+890h+var_844], r15d
0x18000c006  lea     rcx, [rsp+890h+var_840]
0x18000c00b  mov     [rsp+890h+var_848], eax
0x18000c00f  lea     rax, [rsp+890h+var_860]
0x18000c014  mov     [rsp+890h+var_850], rcx
0x18000c019  mov     r9d, 2
0x18000c01f  mov     [rsp+890h+var_870], rax
0x18000c024  lea     rdx, RasDdmTraceInfo
0x18000c02b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000c032  call    McGenEventWrite_EventWriteTransfer
0x18000c037  jmp     loc_18000C0D2
0x18000c03c  mov     r9, r14; unsigned __int16 *
0x18000c03f  mov     rcx, rdi; pCertContext
0x18000c042  call    ?GetCertSubjectName@@YAKPEBU_CERT_CONTEXT@@KKPEAG@Z; GetCertSubjectName(_CERT_CONTEXT const *,ulong,ulong,ushort *)
0x18000c047  mov     ebx, eax
0x18000c049  test    eax, eax
0x18000c04b  jz      short loc_18000C0C9
0x18000c04d  test    cs:byte_1800C8404, 8
0x18000c054  jz      short loc_18000C0C9
0x18000c056  mov     r8d, eax
0x18000c059  mov     word ptr [rsp+890h+var_840], r15w
0x18000c05f  lea     rdx, aGetremoteusern; "GetRemoteUserNameFromCertificate: GetCe"...
0x18000c066  lea     rcx, [rsp+890h+var_840]
0x18000c06b  call    FormatRRASErrorString
0x18000c070  test    cs:byte_1800C8404, 8
0x18000c077  jz      short loc_18000C0C9
0x18000c079  lea     rcx, [rsp+890h+var_840]
0x18000c07e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c082  inc     rax
0x18000c085  cmp     [rcx+rax*2], r15w
0x18000c08a  jnz     short loc_18000C082
0x18000c08c  lea     eax, ds:2[rax*2]
0x18000c093  mov     [rsp+890h+var_844], r15d
0x18000c098  lea     rcx, [rsp+890h+var_840]
0x18000c09d  mov     [rsp+890h+var_848], eax
0x18000c0a1  lea     rax, [rsp+890h+var_860]
0x18000c0a6  mov     [rsp+890h+var_850], rcx
0x18000c0ab  mov     r9d, 2
0x18000c0b1  mov     [rsp+890h+var_870], rax
0x18000c0b6  lea     rdx, RasDdmTraceError
0x18000c0bd  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000c0c4  call    McGenEventWrite_EventWriteTransfer
0x18000c0c9  mov     rcx, rdi; pCertContext
0x18000c0cc  call    cs:__imp_CertFreeCertificateContext
0x18000c0d2  mov     eax, ebx
0x18000c0d4  mov     rcx, [rbp+790h+var_40]
0x18000c0db  xor     rcx, rsp; StackCookie
0x18000c0de  call    __security_check_cookie
0x18000c0e3  add     rsp, 868h
0x18000c0ea  pop     r15
0x18000c0ec  pop     r14
0x18000c0ee  pop     rdi
0x18000c0ef  pop     rsi
0x18000c0f0  pop     rbx
0x18000c0f1  pop     rbp
0x18000c0f2  retn
```
