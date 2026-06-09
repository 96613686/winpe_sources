# GetRemoteUserNameFromCertificate(ulong,ulong,uchar *,ushort *)

- ea: `0x18000c240`
- end: `0x18000c402`
- name: `?GetRemoteUserNameFromCertificate@@YAKKKPEAEPEAG@Z`
- size: `450`
- prototype: `unsigned int __fastcall(DWORD dwCertEncodingType, DWORD cbCertEncoded, BYTE *pbCertEncoded, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180036080`

## callees

- `0x180007c0c`
- `0x18000c0b0`
- `0x18000c240`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000c2ad`
- `KERNEL32!GetLastError` at `0x18000c2ad`
- `CRYPT32!CertFreeCertificateContext` at `0x18000c3d4`
- `CRYPT32!CertFreeCertificateContext` at `0x18000c3d4`
- `CRYPT32!CertCreateCertificateContext` at `0x18000c295`
- `CRYPT32!CertCreateCertificateContext` at `0x18000c295`

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
      if ( (byte_1800CF404 & 8) != 0 )
      {
        LOWORD(v24) = 0;
        FormatRRASErrorString(
          &v24,
          L"GetRemoteUserNameFromCertificate: GetCertFriendlyName failed. Error:%d",
          CertSubjectName);
        if ( (byte_1800CF404 & 8) != 0 )
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
    if ( (byte_1800CF404 & 0x10) != 0 )
    {
      LOWORD(v24) = 0;
      FormatRRASErrorString(
        &v24,
        L"GetRemoteUserNameFromCertificate: Cannot get the certiificate context. Error:%d",
        LastError);
      if ( (byte_1800CF404 & 0x10) != 0 )
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
0x18000c240  push    rbp
0x18000c242  push    rbx
0x18000c243  push    rsi
0x18000c244  push    rdi
0x18000c245  push    r14
0x18000c247  push    r15
0x18000c249  lea     rbp, [rsp-768h]
0x18000c251  sub     rsp, 868h
0x18000c258  mov     rax, cs:__security_cookie
0x18000c25f  xor     rax, rsp
0x18000c262  mov     [rbp+790h+var_40], rax
0x18000c269  mov     rsi, r8
0x18000c26c  mov     ebx, edx
0x18000c26e  mov     edi, ecx
0x18000c270  xor     r15d, r15d
0x18000c273  xor     edx, edx; Val
0x18000c275  mov     [rsp+890h+var_840], r15d
0x18000c27a  mov     r8d, 7FCh; Size
0x18000c280  lea     rcx, [rsp+890h+var_83C]; void *
0x18000c285  mov     r14, r9
0x18000c288  call    memset_0
0x18000c28d  mov     r8d, ebx; cbCertEncoded
0x18000c290  mov     rdx, rsi; pbCertEncoded
0x18000c293  mov     ecx, edi; dwCertEncodingType
0x18000c295  call    cs:__imp_CertCreateCertificateContext
0x18000c29c  nop     dword ptr [rax+rax+00h]
0x18000c2a1  mov     rdi, rax
0x18000c2a4  test    rax, rax
0x18000c2a7  jnz     loc_18000C344
0x18000c2ad  call    cs:__imp_GetLastError
0x18000c2b4  nop     dword ptr [rax+rax+00h]
0x18000c2b9  test    cs:byte_1800CF404, 10h
0x18000c2c0  mov     ebx, eax
0x18000c2c2  jz      loc_18000C3E0
0x18000c2c8  mov     r8d, eax
0x18000c2cb  mov     word ptr [rsp+890h+var_840], r15w
0x18000c2d1  lea     rdx, aGetremoteusern_1; "GetRemoteUserNameFromCertificate: Canno"...
0x18000c2d8  lea     rcx, [rsp+890h+var_840]
0x18000c2dd  call    FormatRRASErrorString
0x18000c2e2  test    cs:byte_1800CF404, 10h
0x18000c2e9  jz      loc_18000C3E0
0x18000c2ef  lea     rcx, [rsp+890h+var_840]
0x18000c2f4  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c2f8  inc     rax
0x18000c2fb  cmp     [rcx+rax*2], r15w
0x18000c300  jnz     short loc_18000C2F8
0x18000c302  lea     eax, ds:2[rax*2]
0x18000c309  mov     [rsp+890h+var_844], r15d
0x18000c30e  lea     rcx, [rsp+890h+var_840]
0x18000c313  mov     [rsp+890h+var_848], eax
0x18000c317  lea     rax, [rsp+890h+var_860]
0x18000c31c  mov     [rsp+890h+var_850], rcx
0x18000c321  mov     r9d, 2
0x18000c327  mov     [rsp+890h+var_870], rax
0x18000c32c  lea     rdx, RasDdmTraceInfo
0x18000c333  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000c33a  call    McGenEventWrite_EventWriteTransfer
0x18000c33f  jmp     loc_18000C3E0
0x18000c344  mov     r9, r14; unsigned __int16 *
0x18000c347  mov     rcx, rdi; pCertContext
0x18000c34a  call    ?GetCertSubjectName@@YAKPEBU_CERT_CONTEXT@@KKPEAG@Z; GetCertSubjectName(_CERT_CONTEXT const *,ulong,ulong,ushort *)
0x18000c34f  mov     ebx, eax
0x18000c351  test    eax, eax
0x18000c353  jz      short loc_18000C3D1
0x18000c355  test    cs:byte_1800CF404, 8
0x18000c35c  jz      short loc_18000C3D1
0x18000c35e  mov     r8d, eax
0x18000c361  mov     word ptr [rsp+890h+var_840], r15w
0x18000c367  lea     rdx, aGetremoteusern; "GetRemoteUserNameFromCertificate: GetCe"...
0x18000c36e  lea     rcx, [rsp+890h+var_840]
0x18000c373  call    FormatRRASErrorString
0x18000c378  test    cs:byte_1800CF404, 8
0x18000c37f  jz      short loc_18000C3D1
0x18000c381  lea     rcx, [rsp+890h+var_840]
0x18000c386  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c38a  inc     rax
0x18000c38d  cmp     [rcx+rax*2], r15w
0x18000c392  jnz     short loc_18000C38A
0x18000c394  lea     eax, ds:2[rax*2]
0x18000c39b  mov     [rsp+890h+var_844], r15d
0x18000c3a0  lea     rcx, [rsp+890h+var_840]
0x18000c3a5  mov     [rsp+890h+var_848], eax
0x18000c3a9  lea     rax, [rsp+890h+var_860]
0x18000c3ae  mov     [rsp+890h+var_850], rcx
0x18000c3b3  mov     r9d, 2
0x18000c3b9  mov     [rsp+890h+var_870], rax
0x18000c3be  lea     rdx, RasDdmTraceError
0x18000c3c5  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000c3cc  call    McGenEventWrite_EventWriteTransfer
0x18000c3d1  mov     rcx, rdi; pCertContext
0x18000c3d4  call    cs:__imp_CertFreeCertificateContext
0x18000c3db  nop     dword ptr [rax+rax+00h]
0x18000c3e0  mov     eax, ebx
0x18000c3e2  mov     rcx, [rbp+790h+var_40]
0x18000c3e9  xor     rcx, rsp; StackCookie
0x18000c3ec  call    __security_check_cookie
0x18000c3f1  add     rsp, 868h
0x18000c3f8  pop     r15
0x18000c3fa  pop     r14
0x18000c3fc  pop     rdi
0x18000c3fd  pop     rsi
0x18000c3fe  pop     rbx
0x18000c3ff  pop     rbp
0x18000c400  retn
```
