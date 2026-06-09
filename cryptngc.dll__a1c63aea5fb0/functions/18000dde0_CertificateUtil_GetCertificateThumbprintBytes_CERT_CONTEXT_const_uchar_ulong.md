# CertificateUtil::GetCertificateThumbprintBytes(_CERT_CONTEXT const *,uchar * *,ulong *)

- ea: `0x18000dde0`
- end: `0x18000e0ec`
- name: `?GetCertificateThumbprintBytes@CertificateUtil@@SAJPEBU_CERT_CONTEXT@@PEAPEAEPEAK@Z`
- size: `780`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000d770`

## callees

- `0x18000dde0`
- `0x180027278`
- `0x180027448`
- `0x1800274cc`
- `0x18002bc58`
- `0x18002e664`
- `0x18002f710`
- `0x180046ce0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e03f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e0b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e03f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e0b0`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18000dee3`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18000e0a2`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18000dee3`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18000e0a2`

## string_xrefs

- `0x18000dfad`: `Logger::WriteNullOrEmptyParameterFailureEvent`
- `0x18000dfa6`: `EventWriteNullOrEmptyParameterFailureEvent`

## pseudocode

```c
__int64 __fastcall CertificateUtil::GetCertificateThumbprintBytes(
        PCCERT_CONTEXT pCertContext,
        unsigned __int8 **a2,
        unsigned int *a3)
{
  __int64 v6; // r8
  ULONG v7; // eax
  void *v9; // rax
  void *v10; // r14
  DWORD v11; // eax
  __int64 v12; // r8
  DWORD LastError; // r15d
  void *v14; // rax
  DWORD pcbData; // [rsp+30h] [rbp-68h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v16; // [rsp+38h] [rbp-60h] BYREF
  const unsigned __int16 *v17; // [rsp+48h] [rbp-50h]
  __int64 v18; // [rsp+50h] [rbp-48h]
  const wchar_t *v19; // [rsp+58h] [rbp-40h]
  __int64 v20; // [rsp+60h] [rbp-38h]

  pcbData = 20;
  if ( !a2 )
  {
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::GetCertificateThumbprintBytes",
      L"ppbBuffer");
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) == 0 )
      goto LABEL_6;
    v17 = L"CertificateUtil::GetCertificateThumbprintBytes";
    v18 = 94;
    v19 = L"ppbBuffer";
    v20 = 20;
    v7 = McGenEventWrite_EventWriteTransfer(
           (REGHANDLE *)&UserDeviceRegistrationEventProvider_Context,
           (const EVENT_DESCRIPTOR *)NullOrEmptyParameterFailureEvent,
           v12,
           3u,
           &v16);
    if ( !v7 )
      goto LABEL_6;
LABEL_14:
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"Logger::WriteNullOrEmptyParameterFailureEvent",
      L"EventWriteNullOrEmptyParameterFailureEvent",
      v7);
LABEL_6:
    operator delete(0);
    return 2147942487LL;
  }
  *a2 = 0;
  if ( !a3 )
  {
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::GetCertificateThumbprintBytes",
      L"pdwBufferSize");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"CertificateUtil::GetCertificateThumbprintBytes", L"pdwBufferSize");
    operator delete(0);
    return 2147942487LL;
  }
  *a3 = 0;
  if ( !pCertContext )
  {
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::GetCertificateThumbprintBytes",
      &stru_1800542A8);
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) == 0 )
      goto LABEL_6;
    v17 = L"CertificateUtil::GetCertificateThumbprintBytes";
    v18 = 94;
    v19 = (const wchar_t *)&stru_1800542A8;
    v20 = 26;
    v7 = McGenEventWrite_EventWriteTransfer(
           (REGHANDLE *)&UserDeviceRegistrationEventProvider_Context,
           (const EVENT_DESCRIPTOR *)NullOrEmptyParameterFailureEvent,
           v6,
           3u,
           &v16);
    if ( !v7 )
      goto LABEL_6;
    goto LABEL_14;
  }
  v9 = operator new[](0x14u, (const struct std::nothrow_t *)&std::nothrow);
  v10 = v9;
  if ( !v9 )
  {
    Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"CertificateUtil::GetCertificateThumbprintBytes");
    operator delete(0);
    return 2147942414LL;
  }
  if ( CertGetCertificateContextProperty(pCertContext, 3u, v9, &pcbData) )
    goto LABEL_9;
  LastError = GetLastError();
  if ( LastError != 234 )
    goto LABEL_25;
  operator delete(v10);
  v14 = operator new[](pcbData, (const struct std::nothrow_t *)&std::nothrow);
  v10 = v14;
  if ( v14 )
  {
    if ( CertGetCertificateContextProperty(pCertContext, 3u, v14, &pcbData) )
      goto LABEL_9;
    LastError = GetLastError();
LABEL_25:
    if ( LastError )
    {
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"CertificateUtil::GetCertificateThumbprintBytes",
        L"CertGetCertificateContextProperty",
        LastError);
      operator delete(v10);
      goto LABEL_15;
    }
LABEL_9:
    v11 = pcbData;
    *a2 = (unsigned __int8 *)v10;
    *a3 = v11;
    operator delete(0);
    return 0;
  }
  Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"CertificateUtil::GetCertificateThumbprintBytes");
  operator delete(0);
LABEL_15:
  if ( (int)LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return LastError;
}

```

## disassembly

```asm
0x18000dde0  push    rbx
0x18000dde2  push    rbp
0x18000dde3  push    rsi
0x18000dde4  push    rdi
0x18000dde5  sub     rsp, 78h
0x18000dde9  mov     rax, cs:__security_cookie
0x18000ddf0  xor     rax, rsp
0x18000ddf3  mov     [rsp+98h+var_30], rax
0x18000ddf8  mov     [rsp+98h+pcbData], 14h
0x18000de00  mov     rdi, r8
0x18000de03  mov     rsi, rdx
0x18000de06  mov     rbp, rcx
0x18000de09  test    rdx, rdx
0x18000de0c  jz      loc_18000DF2F
0x18000de12  xor     ebx, ebx
0x18000de14  mov     [rdx], rbx
0x18000de17  test    r8, r8
0x18000de1a  jz      loc_18000DFDD
0x18000de20  mov     [r8], ebx
0x18000de23  test    rcx, rcx
0x18000de26  jnz     short loc_18000DEA6
0x18000de28  lea     rsi, stru_1800542A8
0x18000de2f  lea     rdi, aCertificateuti_2; "CertificateUtil::GetCertificateThumbpri"...
0x18000de36  mov     r8, rsi
0x18000de39  mov     rdx, rdi
0x18000de3c  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18000de43  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000de48  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x18000de4f  jz      short loc_18000DE98
0x18000de51  lea     rax, [rsp+98h+var_60]
0x18000de56  mov     [rsp+98h+var_50], rdi
0x18000de5b  mov     r9d, 3
0x18000de61  mov     [rsp+98h+var_78], rax
0x18000de66  lea     rdx, NullOrEmptyParameterFailureEvent
0x18000de6d  mov     [rsp+98h+var_48], 5Eh ; '^'
0x18000de76  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x18000de7d  mov     [rsp+98h+var_40], rsi
0x18000de82  mov     [rsp+98h+var_38], 1Ah
0x18000de8b  call    McGenEventWrite_EventWriteTransfer
0x18000de90  test    eax, eax
0x18000de92  jnz     loc_18000DFA3
0x18000de98  xor     ecx, ecx; Block
0x18000de9a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000de9f  mov     eax, 80070057h
0x18000dea4  jmp     short loc_18000DF19
0x18000dea6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000dead  mov     [rsp+98h+arg_18], r14
0x18000deb5  mov     ecx, 14h; unsigned __int64
0x18000deba  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000debf  mov     r14, rax
0x18000dec2  test    rax, rax
0x18000dec5  jz      loc_18000E01A
0x18000decb  mov     [rsp+98h+var_28], r15
0x18000ded0  lea     r9, [rsp+98h+pcbData]; pcbData
0x18000ded5  mov     r8, rax; pvData
0x18000ded8  mov     edx, 3; dwPropId
0x18000dedd  mov     rcx, rbp; pCertContext
0x18000dee0  mov     r15d, ebx
0x18000dee3  call    cs:__imp_CertGetCertificateContextProperty
0x18000dee9  test    eax, eax
0x18000deeb  jz      loc_18000E03F
0x18000def1  mov     eax, [rsp+98h+pcbData]
0x18000def5  mov     [rsi], r14
0x18000def8  mov     [rdi], eax
0x18000defa  xor     ecx, ecx; Block
0x18000defc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000df01  test    r15d, r15d
0x18000df04  jnz     loc_18000DFC5
0x18000df0a  mov     eax, ebx
0x18000df0c  mov     r15, [rsp+98h+var_28]
0x18000df11  mov     r14, [rsp+98h+arg_18]
0x18000df19  mov     rcx, [rsp+98h+var_30]
0x18000df1e  xor     rcx, rsp; StackCookie
0x18000df21  call    __security_check_cookie
0x18000df26  add     rsp, 78h
0x18000df2a  pop     rdi
0x18000df2b  pop     rsi
0x18000df2c  pop     rbp
0x18000df2d  pop     rbx
0x18000df2e  retn
0x18000df2f  lea     rsi, aPpbbuffer; "ppbBuffer"
0x18000df36  lea     rdi, aCertificateuti_2; "CertificateUtil::GetCertificateThumbpri"...
0x18000df3d  mov     r8, rsi
0x18000df40  mov     rdx, rdi
0x18000df43  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18000df4a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000df4f  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x18000df56  jz      loc_18000DE98
0x18000df5c  lea     rax, [rsp+98h+var_60]
0x18000df61  mov     [rsp+98h+var_50], rdi
0x18000df66  mov     r9d, 3
0x18000df6c  mov     [rsp+98h+var_78], rax
0x18000df71  lea     rdx, NullOrEmptyParameterFailureEvent
0x18000df78  mov     [rsp+98h+var_48], 5Eh ; '^'
0x18000df81  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x18000df88  mov     [rsp+98h+var_40], rsi
0x18000df8d  mov     [rsp+98h+var_38], 14h
0x18000df96  call    McGenEventWrite_EventWriteTransfer
0x18000df9b  test    eax, eax
0x18000df9d  jz      loc_18000DE98
0x18000dfa3  mov     r9d, eax
0x18000dfa6  lea     r8, aEventwritenull; "EventWriteNullOrEmptyParameterFailureEv"...
0x18000dfad  lea     rdx, aLoggerWritenul; "Logger::WriteNullOrEmptyParameterFailur"...
0x18000dfb4  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18000dfbb  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000dfc0  jmp     loc_18000DE98
0x18000dfc5  test    r15d, r15d
0x18000dfc8  jle     short loc_18000DFD5
0x18000dfca  movzx   r15d, r15w
0x18000dfce  or      r15d, 80070000h
0x18000dfd5  mov     eax, r15d
0x18000dfd8  jmp     loc_18000DF0C
0x18000dfdd  lea     rdi, aCertificateuti_2; "CertificateUtil::GetCertificateThumbpri"...
0x18000dfe4  mov     rdx, rdi
0x18000dfe7  lea     r8, aPdwbuffersize; "pdwBufferSize"
0x18000dfee  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18000dff5  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000dffa  lea     rdx, aPdwbuffersize; "pdwBufferSize"
0x18000e001  mov     rcx, rdi; unsigned __int16 *
0x18000e004  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18000e009  xor     ecx, ecx; Block
0x18000e00b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e010  mov     eax, 80070057h
0x18000e015  jmp     loc_18000DF19
0x18000e01a  lea     rdx, aCertificateuti_2; "CertificateUtil::GetCertificateThumbpri"...
0x18000e021  lea     rcx, aSOutOfMemoryAl; "%s: Out of memory. Allocation failed."
0x18000e028  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x18000e02d  mov     rcx, r14; Block
0x18000e030  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e035  mov     eax, 8007000Eh
0x18000e03a  jmp     loc_18000DF11
0x18000e03f  call    cs:__imp_GetLastError
0x18000e045  mov     r15d, eax
0x18000e048  cmp     eax, 0EAh
0x18000e04d  jnz     short loc_18000E0B9
0x18000e04f  mov     rcx, r14; Block
0x18000e052  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e057  mov     ecx, [rsp+98h+pcbData]; unsigned __int64
0x18000e05b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000e062  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000e067  mov     r14, rax
0x18000e06a  test    rax, rax
0x18000e06d  jnz     short loc_18000E08F
0x18000e06f  lea     rdx, aCertificateuti_2; "CertificateUtil::GetCertificateThumbpri"...
0x18000e076  lea     rcx, aSOutOfMemoryAl; "%s: Out of memory. Allocation failed."
0x18000e07d  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x18000e082  mov     rcx, r14; Block
0x18000e085  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e08a  jmp     loc_18000DFC5
0x18000e08f  lea     r9, [rsp+98h+pcbData]; pcbData
0x18000e094  mov     r8, r14; pvData
0x18000e097  mov     edx, 3; dwPropId
0x18000e09c  mov     rcx, rbp; pCertContext
0x18000e09f  mov     r15d, ebx
0x18000e0a2  call    cs:__imp_CertGetCertificateContextProperty
0x18000e0a8  test    eax, eax
0x18000e0aa  jnz     loc_18000DEF1
0x18000e0b0  call    cs:__imp_GetLastError
0x18000e0b6  mov     r15d, eax
0x18000e0b9  test    r15d, r15d
0x18000e0bc  jz      loc_18000DEF1
0x18000e0c2  mov     r9d, r15d
0x18000e0c5  lea     r8, aCertgetcertifi_0; "CertGetCertificateContextProperty"
0x18000e0cc  lea     rdx, aCertificateuti_2; "CertificateUtil::GetCertificateThumbpri"...
0x18000e0d3  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18000e0da  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000e0df  mov     rcx, r14; Block
0x18000e0e2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e0e7  jmp     loc_18000DFC5
```
