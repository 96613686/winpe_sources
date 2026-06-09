# CertificateUtil::GetCertificateThumbprint(_CERT_CONTEXT const *,ushort * *)

- ea: `0x180010a60`
- end: `0x180010dc6`
- name: `?GetCertificateThumbprint@CertificateUtil@@SAJPEBU_CERT_CONTEXT@@PEAPEAG@Z`
- size: `870`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800461d8`

## callees

- `0x180010a60`
- `0x180027448`
- `0x1800274cc`
- `0x18002bc58`
- `0x18002e664`
- `0x18002f710`
- `0x180046ce0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010cce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010d3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010cce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010d3f`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180010bb3`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180010d31`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180010bb3`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180010d31`

## string_xrefs

- `0x180010c6f`: `Logger::WriteNullOrEmptyParameterFailureEvent`
- `0x180010c68`: `EventWriteNullOrEmptyParameterFailureEvent`

## pseudocode

```c
__int64 __fastcall CertificateUtil::GetCertificateThumbprint(PCCERT_CONTEXT pCertContext, unsigned __int16 **a2)
{
  void *v2; // rdi
  HCERTSTORE *p_hCertStore; // rbp
  unsigned int v6; // esi
  __int64 v7; // r8
  ULONG v8; // eax
  unsigned __int8 *v10; // rax
  unsigned __int8 *v11; // r14
  DWORD v12; // r15d
  signed int v13; // ebp
  unsigned __int64 v14; // rax
  unsigned __int16 *v15; // rax
  unsigned __int16 *v16; // r8
  signed int LastError; // r12d
  unsigned __int8 *v18; // rax
  __int64 i; // rdx
  unsigned __int8 v20; // al
  DWORD pcbData; // [rsp+30h] [rbp-68h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v22; // [rsp+38h] [rbp-60h] BYREF
  const wchar_t *v23; // [rsp+48h] [rbp-50h]
  __int64 v24; // [rsp+50h] [rbp-48h]
  HCERTSTORE *v25; // [rsp+58h] [rbp-40h]
  __int64 v26; // [rsp+60h] [rbp-38h]

  v2 = 0;
  if ( !a2 )
  {
    p_hCertStore = &stru_1800542A8.hCertStore;
    v6 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::GetCertificateThumbprint",
      &stru_1800542A8.hCertStore);
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) == 0 )
      goto LABEL_7;
    v26 = 28;
LABEL_5:
    v25 = p_hCertStore;
    v24 = 84;
    v23 = L"CertificateUtil::GetCertificateThumbprint";
    v8 = McGenEventWrite_EventWriteTransfer(
           (REGHANDLE *)&UserDeviceRegistrationEventProvider_Context,
           (const EVENT_DESCRIPTOR *)NullOrEmptyParameterFailureEvent,
           v7,
           3u,
           &v22);
    if ( v8 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"Logger::WriteNullOrEmptyParameterFailureEvent",
        L"EventWriteNullOrEmptyParameterFailureEvent",
        v8);
    goto LABEL_7;
  }
  *a2 = 0;
  if ( !pCertContext )
  {
    p_hCertStore = (HCERTSTORE *)&stru_1800542A8;
    v6 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"CertificateUtil::GetCertificateThumbprint", &stru_1800542A8);
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) == 0 )
      goto LABEL_7;
    v26 = 26;
    goto LABEL_5;
  }
  pcbData = 20;
  v10 = (unsigned __int8 *)operator new[](0x14u, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v10;
  if ( !v10 )
  {
    v6 = -2147024882;
    v13 = -2147024882;
    Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"CertificateUtil::GetCertificateThumbprintBytes");
    operator delete(0);
    goto LABEL_22;
  }
  if ( CertGetCertificateContextProperty(pCertContext, 3u, v10, &pcbData) )
    goto LABEL_12;
  v12 = 0;
  LastError = GetLastError();
  if ( LastError == 234 )
  {
    operator delete(v11);
    v18 = (unsigned __int8 *)operator new[](pcbData, (const struct std::nothrow_t *)&std::nothrow);
    v11 = v18;
    if ( !v18 )
    {
      Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"CertificateUtil::GetCertificateThumbprintBytes");
      operator delete(0);
      goto LABEL_18;
    }
    if ( CertGetCertificateContextProperty(pCertContext, 3u, v18, &pcbData) )
    {
LABEL_12:
      v12 = pcbData;
      operator delete(0);
      v13 = 0;
      v2 = v11;
      goto LABEL_13;
    }
    LastError = GetLastError();
  }
  if ( !LastError )
    goto LABEL_12;
  Logger::TraceError(
    L"%s: %s failed with win32 error code: 0x%08x.",
    L"CertificateUtil::GetCertificateThumbprintBytes",
    L"CertGetCertificateContextProperty",
    (unsigned int)LastError);
  operator delete(v11);
  v11 = 0;
LABEL_18:
  if ( LastError > 0 )
    v13 = (unsigned __int16)LastError | 0x80070000;
  else
    v13 = LastError;
LABEL_13:
  v6 = v13;
  if ( v13 < 0 )
  {
LABEL_22:
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"CertificateUtil::GetCertificateThumbprint",
      L"CertificateUtil::GetCertificateThumbprintBytes",
      (unsigned int)v13);
    goto LABEL_7;
  }
  v14 = 2LL * (2 * v12 + 1);
  if ( !is_mul_ok(2 * v12 + 1, 2u) )
    v14 = -1;
  v15 = (unsigned __int16 *)operator new[](v14, (const struct std::nothrow_t *)&std::nothrow);
  *a2 = v15;
  v16 = v15;
  if ( v15 )
  {
    for ( i = 0; (unsigned int)i < v12; v16 += 2 )
    {
      *v16 = a0123456789abcd_0[(unsigned __int64)v11[i] >> 4];
      v20 = v11[i];
      i = (unsigned int)(i + 1);
      v16[1] = a0123456789abcd_0[v20 & 0xF];
    }
    *v16 = 0;
  }
  else
  {
    v6 = -2147024882;
    Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"CertificateUtil::GetCertificateThumbprint");
  }
LABEL_7:
  operator delete(v2);
  return v6;
}

```

## disassembly

```asm
0x180010a60  push    rbx
0x180010a62  push    rbp
0x180010a63  push    rsi
0x180010a64  push    rdi
0x180010a65  sub     rsp, 78h
0x180010a69  mov     rax, cs:__security_cookie
0x180010a70  xor     rax, rsp
0x180010a73  mov     [rsp+98h+var_30], rax
0x180010a78  xor     edi, edi
0x180010a7a  mov     rbx, rdx
0x180010a7d  mov     rsi, rcx
0x180010a80  test    rdx, rdx
0x180010a83  jz      loc_180010B2A
0x180010a89  mov     [rdx], rdi
0x180010a8c  test    rcx, rcx
0x180010a8f  jnz     loc_180010B66
0x180010a95  lea     rbp, stru_1800542A8
0x180010a9c  mov     esi, 80070057h
0x180010aa1  lea     rbx, aCertificateuti_0; "CertificateUtil::GetCertificateThumbpri"...
0x180010aa8  mov     r8, rbp
0x180010aab  mov     rdx, rbx
0x180010aae  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x180010ab5  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180010aba  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x180010ac1  jz      short loc_180010B0A
0x180010ac3  mov     [rsp+98h+var_38], 1Ah
0x180010acc  lea     rax, [rsp+98h+var_60]
0x180010ad1  mov     [rsp+98h+var_40], rbp
0x180010ad6  mov     r9d, 3
0x180010adc  mov     [rsp+98h+var_78], rax
0x180010ae1  lea     rdx, NullOrEmptyParameterFailureEvent
0x180010ae8  mov     [rsp+98h+var_48], 54h ; 'T'
0x180010af1  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x180010af8  mov     [rsp+98h+var_50], rbx
0x180010afd  call    McGenEventWrite_EventWriteTransfer
0x180010b02  test    eax, eax
0x180010b04  jnz     loc_180010C65
0x180010b0a  mov     rcx, rdi; Block
0x180010b0d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010b12  mov     eax, esi
0x180010b14  mov     rcx, [rsp+98h+var_30]
0x180010b19  xor     rcx, rsp; StackCookie
0x180010b1c  call    __security_check_cookie
0x180010b21  add     rsp, 78h
0x180010b25  pop     rdi
0x180010b26  pop     rsi
0x180010b27  pop     rbp
0x180010b28  pop     rbx
0x180010b29  retn
0x180010b2a  lea     rbp, stru_1800542A8.hCertStore
0x180010b31  mov     esi, 80070057h
0x180010b36  lea     rbx, aCertificateuti_0; "CertificateUtil::GetCertificateThumbpri"...
0x180010b3d  mov     r8, rbp
0x180010b40  mov     rdx, rbx
0x180010b43  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x180010b4a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180010b4f  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x180010b56  jz      short loc_180010B0A
0x180010b58  mov     [rsp+98h+var_38], 1Ch
0x180010b61  jmp     loc_180010ACC
0x180010b66  mov     [rsp+98h+arg_18], r14
0x180010b6e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180010b75  mov     ecx, 14h; unsigned __int64
0x180010b7a  mov     [rsp+98h+var_28], r15
0x180010b7f  mov     [rsp+98h+pcbData], 14h
0x180010b87  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180010b8c  mov     r14, rax
0x180010b8f  test    rax, rax
0x180010b92  jz      loc_180010C87
0x180010b98  mov     [rsp+98h+arg_10], r12
0x180010ba0  lea     r9, [rsp+98h+pcbData]; pcbData
0x180010ba5  mov     r8, rax; pvData
0x180010ba8  mov     edx, 3; dwPropId
0x180010bad  mov     rcx, rsi; pCertContext
0x180010bb0  xor     r12d, r12d
0x180010bb3  call    cs:__imp_CertGetCertificateContextProperty
0x180010bb9  test    eax, eax
0x180010bbb  jz      loc_180010CCB
0x180010bc1  mov     r15d, [rsp+98h+pcbData]
0x180010bc6  xor     ecx, ecx; Block
0x180010bc8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010bcd  xor     ebp, ebp
0x180010bcf  mov     rdi, r14
0x180010bd2  test    r12d, r12d
0x180010bd5  jnz     short loc_180010C4C
0x180010bd7  mov     r12, [rsp+98h+arg_10]
0x180010bdf  mov     esi, ebp
0x180010be1  test    ebp, ebp
0x180010be3  js      loc_180010CA9
0x180010be9  lea     ecx, ds:1[r15*2]
0x180010bf1  mov     eax, 2
0x180010bf6  mul     rcx
0x180010bf9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180010c00  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180010c07  cmovb   rax, rcx
0x180010c0b  mov     rcx, rax; unsigned __int64
0x180010c0e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180010c13  mov     [rbx], rax
0x180010c16  mov     r8, rax
0x180010c19  test    rax, rax
0x180010c1c  jnz     loc_180010D7E
0x180010c22  lea     rdx, aCertificateuti_0; "CertificateUtil::GetCertificateThumbpri"...
0x180010c29  mov     esi, 8007000Eh
0x180010c2e  lea     rcx, aSOutOfMemoryAl; "%s: Out of memory. Allocation failed."
0x180010c35  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x180010c3a  mov     r14, [rsp+98h+arg_18]
0x180010c42  mov     r15, [rsp+98h+var_28]
0x180010c47  jmp     loc_180010B0A
0x180010c4c  test    r12d, r12d
0x180010c4f  jg      short loc_180010C56
0x180010c51  mov     ebp, r12d
0x180010c54  jmp     short loc_180010BD7
0x180010c56  movzx   ebp, r12w
0x180010c5a  or      ebp, 80070000h
0x180010c60  jmp     loc_180010BD7
0x180010c65  mov     r9d, eax
0x180010c68  lea     r8, aEventwritenull; "EventWriteNullOrEmptyParameterFailureEv"...
0x180010c6f  lea     rdx, aLoggerWritenul; "Logger::WriteNullOrEmptyParameterFailur"...
0x180010c76  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x180010c7d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180010c82  jmp     loc_180010B0A
0x180010c87  mov     esi, 8007000Eh
0x180010c8c  lea     rdx, aCertificateuti_2; "CertificateUtil::GetCertificateThumbpri"...
0x180010c93  lea     rcx, aSOutOfMemoryAl; "%s: Out of memory. Allocation failed."
0x180010c9a  mov     ebp, esi
0x180010c9c  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x180010ca1  mov     rcx, r14; Block
0x180010ca4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010ca9  mov     r9d, ebp
0x180010cac  lea     r8, aCertificateuti_2; "CertificateUtil::GetCertificateThumbpri"...
0x180010cb3  lea     rdx, aCertificateuti_0; "CertificateUtil::GetCertificateThumbpri"...
0x180010cba  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x180010cc1  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180010cc6  jmp     loc_180010C3A
0x180010ccb  xor     r15d, r15d
0x180010cce  call    cs:__imp_GetLastError
0x180010cd4  mov     r12d, eax
0x180010cd7  cmp     eax, 0EAh
0x180010cdc  jnz     short loc_180010D48
0x180010cde  mov     rcx, r14; Block
0x180010ce1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010ce6  mov     ecx, [rsp+98h+pcbData]; unsigned __int64
0x180010cea  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180010cf1  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180010cf6  mov     r14, rax
0x180010cf9  test    rax, rax
0x180010cfc  jnz     short loc_180010D1E
0x180010cfe  lea     rdx, aCertificateuti_2; "CertificateUtil::GetCertificateThumbpri"...
0x180010d05  lea     rcx, aSOutOfMemoryAl; "%s: Out of memory. Allocation failed."
0x180010d0c  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x180010d11  mov     rcx, r14; Block
0x180010d14  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010d19  jmp     loc_180010C4C
0x180010d1e  lea     r9, [rsp+98h+pcbData]; pcbData
0x180010d23  mov     r8, r14; pvData
0x180010d26  mov     edx, 3; dwPropId
0x180010d2b  mov     rcx, rsi; pCertContext
0x180010d2e  xor     r12d, r12d
0x180010d31  call    cs:__imp_CertGetCertificateContextProperty
0x180010d37  test    eax, eax
0x180010d39  jnz     loc_180010BC1
0x180010d3f  call    cs:__imp_GetLastError
0x180010d45  mov     r12d, eax
0x180010d48  test    r12d, r12d
0x180010d4b  jz      loc_180010BC1
0x180010d51  mov     r9d, r12d
0x180010d54  lea     r8, aCertgetcertifi_0; "CertGetCertificateContextProperty"
0x180010d5b  lea     rdx, aCertificateuti_2; "CertificateUtil::GetCertificateThumbpri"...
0x180010d62  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x180010d69  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180010d6e  mov     rcx, r14; Block
0x180010d71  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010d76  xor     r14d, r14d
0x180010d79  jmp     loc_180010C4C
0x180010d7e  xor     edx, edx
0x180010d80  test    r15d, r15d
0x180010d83  jz      short loc_180010DBB
0x180010d85  lea     r9, a0123456789abcd_0; "0123456789ABCDEF"
0x180010d8c  movzx   eax, byte ptr [rdx+r14]
0x180010d91  shr     rax, 4
0x180010d95  movzx   eax, word ptr [r9+rax*2]
0x180010d9a  mov     [r8], ax
0x180010d9e  movzx   eax, byte ptr [rdx+r14]
0x180010da3  inc     edx
0x180010da5  and     eax, 0Fh
0x180010da8  movzx   eax, word ptr [r9+rax*2]
0x180010dad  mov     [r8+2], ax
0x180010db2  add     r8, 4
0x180010db6  cmp     edx, r15d
0x180010db9  jb      short loc_180010D8C
0x180010dbb  xor     edx, edx
0x180010dbd  mov     [r8], dx
0x180010dc1  jmp     loc_180010C3A
```
