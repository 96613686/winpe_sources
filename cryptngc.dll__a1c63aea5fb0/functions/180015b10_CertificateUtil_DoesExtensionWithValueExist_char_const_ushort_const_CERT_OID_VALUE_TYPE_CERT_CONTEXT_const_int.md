# CertificateUtil::DoesExtensionWithValueExist(char const *,ushort const *,_CERT_OID_VALUE_TYPE,_CERT_CONTEXT const *,int *)

- ea: `0x180015b10`
- end: `0x180015d4b`
- name: `?DoesExtensionWithValueExist@CertificateUtil@@SAJPEBDPEBGW4_CERT_OID_VALUE_TYPE@@PEBU_CERT_CONTEXT@@PEAH@Z`
- size: `571`
- prototype: `static int __high(const char *, const unsigned __int16 *, enum _CERT_OID_VALUE_TYPE, const struct _CERT_CONTEXT *, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18002bcdc`

## callees

- `0x180009a70`
- `0x180015b10`
- `0x180015d54`
- `0x180027278`
- `0x180027448`
- `0x1800274cc`
- `0x18002e664`
- `0x180046ce0`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180015d19`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180015d19`

## string_xrefs

- `0x180015ccd`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x180015ce3`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x180015b4f`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x180015be3`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x180015c1e`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x180015c65`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x180015ca6`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x180015cfe`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x180015bc6`: `Logger::WriteNullOrEmptyParameterFailureEvent`
- `0x180015bbf`: `EventWriteNullOrEmptyParameterFailureEvent`

## pseudocode

```c
__int64 __fastcall CertificateUtil::DoesExtensionWithValueExist(
        const char *a1,
        const WCHAR *a2,
        int a3,
        const struct _CERT_CONTEXT *a4,
        _DWORD *a5)
{
  const wchar_t *v6; // rsi
  unsigned int v7; // ebx
  __int64 v8; // r8
  unsigned int v9; // eax
  int ExtensionGuidValueByOid; // eax
  const unsigned __int16 *v11; // r8
  LPCWSTR lpString1; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v14[16]; // [rsp+38h] [rbp-60h] BYREF
  const unsigned __int16 *v15; // [rsp+48h] [rbp-50h]
  __int64 v16; // [rsp+50h] [rbp-48h]
  const wchar_t *v17; // [rsp+58h] [rbp-40h]
  __int64 v18; // [rsp+60h] [rbp-38h]

  lpString1 = 0;
  if ( !a1 )
  {
    v6 = L"pcszOid";
    v7 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"CertificateUtil::DoesExtensionWithValueExist", L"pcszOid");
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) == 0 )
      goto LABEL_25;
    v18 = 16;
    goto LABEL_4;
  }
  if ( !a2 )
  {
    v7 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::DoesExtensionWithValueExist",
      L"pcszOidValue");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"CertificateUtil::DoesExtensionWithValueExist", L"pcszOidValue");
    goto LABEL_25;
  }
  if ( !a4 )
  {
    v7 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::DoesExtensionWithValueExist",
      &stru_1800542A8);
    Logger::WriteNullOrEmptyParameterFailureEvent(
      L"CertificateUtil::DoesExtensionWithValueExist",
      (const unsigned __int16 *)&stru_1800542A8);
    goto LABEL_25;
  }
  if ( !a5 )
  {
    v6 = L"pbResult";
    v7 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"CertificateUtil::DoesExtensionWithValueExist", L"pbResult");
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) == 0 )
      goto LABEL_25;
    v18 = 18;
LABEL_4:
    v17 = v6;
    v16 = 90;
    v15 = L"CertificateUtil::DoesExtensionWithValueExist";
    v9 = McGenEventWrite_EventWriteTransfer(
           &UserDeviceRegistrationEventProvider_Context,
           NullOrEmptyParameterFailureEvent,
           v8,
           3,
           v14);
    if ( v9 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"Logger::WriteNullOrEmptyParameterFailureEvent",
        L"EventWriteNullOrEmptyParameterFailureEvent",
        v9);
    goto LABEL_25;
  }
  *a5 = 0;
  if ( a3 )
  {
    if ( a3 != 1 )
    {
      Logger::TraceError(L"%s: Unknown CERT_OID_VALUE_TYPE: %d.", L"CertificateUtil::DoesExtensionWithValueExist");
      v7 = -2147024809;
      goto LABEL_25;
    }
    ExtensionGuidValueByOid = CertificateUtil::FindExtensionGuidValueByOid(a1, a4, (unsigned __int16 **)&lpString1);
    v11 = L"CertificateUtil::FindExtensionGuidValueByOid";
  }
  else
  {
    ExtensionGuidValueByOid = CertificateUtil::FindExtensionStrValueByOid(a1, a4, (unsigned __int16 **)&lpString1);
    v11 = L"CertificateUtil::FindExtensionStrValueByOid";
  }
  v7 = ExtensionGuidValueByOid;
  if ( ExtensionGuidValueByOid == -2146885628 )
  {
    v7 = 0;
  }
  else if ( ExtensionGuidValueByOid >= 0 )
  {
    if ( !lstrcmpiW(lpString1, a2) )
      *a5 = 1;
  }
  else
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x",
      L"CertificateUtil::DoesExtensionWithValueExist",
      v11,
      (unsigned int)ExtensionGuidValueByOid);
  }
LABEL_25:
  operator delete((void *)lpString1);
  return v7;
}

```

## disassembly

```asm
0x180015b10  push    rbx
0x180015b12  push    rbp
0x180015b13  push    rsi
0x180015b14  push    rdi
0x180015b15  sub     rsp, 78h
0x180015b19  mov     rax, cs:__security_cookie
0x180015b20  xor     rax, rsp
0x180015b23  mov     [rsp+98h+var_30], rax
0x180015b28  mov     rdi, [rsp+98h+arg_20]
0x180015b30  xor     ebp, ebp
0x180015b32  mov     [rsp+98h+lpString1], rbp
0x180015b37  mov     rsi, rdx
0x180015b3a  test    rcx, rcx
0x180015b3d  jnz     loc_180015BDE
0x180015b43  lea     rsi, aPcszoid; "pcszOid"
0x180015b4a  mov     ebx, 80070057h
0x180015b4f  lea     rdi, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x180015b56  mov     r8, rsi
0x180015b59  mov     rdx, rdi
0x180015b5c  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x180015b63  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180015b68  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x180015b6f  jz      loc_180015D29
0x180015b75  mov     [rsp+98h+var_38], 10h
0x180015b7e  lea     rax, [rsp+98h+var_60]
0x180015b83  mov     [rsp+98h+var_40], rsi
0x180015b88  mov     r9d, 3
0x180015b8e  mov     [rsp+98h+var_78], rax
0x180015b93  lea     rdx, NullOrEmptyParameterFailureEvent
0x180015b9a  mov     [rsp+98h+var_48], 5Ah ; 'Z'
0x180015ba3  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x180015baa  mov     [rsp+98h+var_50], rdi
0x180015baf  call    McGenEventWrite_EventWriteTransfer
0x180015bb4  test    eax, eax
0x180015bb6  jz      loc_180015D29
0x180015bbc  mov     r9d, eax
0x180015bbf  lea     r8, aEventwritenull; "EventWriteNullOrEmptyParameterFailureEv"...
0x180015bc6  lea     rdx, aLoggerWritenul; "Logger::WriteNullOrEmptyParameterFailur"...
0x180015bcd  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x180015bd4  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180015bd9  jmp     loc_180015D29
0x180015bde  test    rsi, rsi
0x180015be1  jnz     short loc_180015C19
0x180015be3  lea     rdi, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x180015bea  mov     ebx, 80070057h
0x180015bef  mov     rdx, rdi
0x180015bf2  lea     r8, aPcszoidvalue; "pcszOidValue"
0x180015bf9  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x180015c00  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180015c05  lea     rdx, aPcszoidvalue; "pcszOidValue"
0x180015c0c  mov     rcx, rdi; unsigned __int16 *
0x180015c0f  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180015c14  jmp     loc_180015D29
0x180015c19  test    r9, r9
0x180015c1c  jnz     short loc_180015C54
0x180015c1e  lea     rdi, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x180015c25  mov     ebx, 80070057h
0x180015c2a  mov     rdx, rdi
0x180015c2d  lea     r8, stru_1800542A8
0x180015c34  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x180015c3b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180015c40  lea     rdx, stru_1800542A8; unsigned __int16 *
0x180015c47  mov     rcx, rdi; unsigned __int16 *
0x180015c4a  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180015c4f  jmp     loc_180015D29
0x180015c54  test    rdi, rdi
0x180015c57  jnz     short loc_180015C99
0x180015c59  lea     rsi, aPbresult; "pbResult"
0x180015c60  mov     ebx, 80070057h
0x180015c65  lea     rdi, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x180015c6c  mov     r8, rsi
0x180015c6f  mov     rdx, rdi
0x180015c72  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x180015c79  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180015c7e  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x180015c85  jz      loc_180015D29
0x180015c8b  mov     [rsp+98h+var_38], 12h
0x180015c94  jmp     loc_180015B7E
0x180015c99  mov     [rdi], ebp
0x180015c9b  test    r8d, r8d
0x180015c9e  jz      short loc_180015CD6
0x180015ca0  cmp     r8d, 1
0x180015ca4  jz      short loc_180015CC0
0x180015ca6  lea     rdx, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x180015cad  lea     rcx, aSUnknownCertOi; "%s: Unknown CERT_OID_VALUE_TYPE: %d."
0x180015cb4  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180015cb9  mov     ebx, 80070057h
0x180015cbe  jmp     short loc_180015D29
0x180015cc0  lea     r8, [rsp+98h+lpString1]; unsigned __int16 **
0x180015cc5  mov     rdx, r9; struct _CERT_CONTEXT *
0x180015cc8  call    ?FindExtensionGuidValueByOid@CertificateUtil@@SAJPEBDPEBU_CERT_CONTEXT@@PEAPEAG@Z; CertificateUtil::FindExtensionGuidValueByOid(char const *,_CERT_CONTEXT const *,ushort * *)
0x180015ccd  lea     r8, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x180015cd4  jmp     short loc_180015CEA
0x180015cd6  lea     r8, [rsp+98h+lpString1]; unsigned __int16 **
0x180015cdb  mov     rdx, r9; struct _CERT_CONTEXT *
0x180015cde  call    ?FindExtensionStrValueByOid@CertificateUtil@@SAJPEBDPEBU_CERT_CONTEXT@@PEAPEAG@Z; CertificateUtil::FindExtensionStrValueByOid(char const *,_CERT_CONTEXT const *,ushort * *)
0x180015ce3  lea     r8, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x180015cea  mov     ebx, eax
0x180015cec  cmp     eax, 80092004h
0x180015cf1  jnz     short loc_180015CF7
0x180015cf3  mov     ebx, ebp
0x180015cf5  jmp     short loc_180015D29
0x180015cf7  test    ebx, ebx
0x180015cf9  jns     short loc_180015D11
0x180015cfb  mov     r9d, ebx
0x180015cfe  lea     rdx, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x180015d05  lea     rcx, aSSFailedWithEr; "%s: %s failed with error code: 0x%08x"
0x180015d0c  jmp     loc_180015BD4
0x180015d11  mov     rcx, [rsp+98h+lpString1]; lpString1
0x180015d16  mov     rdx, rsi; lpString2
0x180015d19  call    cs:__imp_lstrcmpiW
0x180015d1f  test    eax, eax
0x180015d21  jnz     short loc_180015D29
0x180015d23  mov     dword ptr [rdi], 1
0x180015d29  mov     rcx, [rsp+98h+lpString1]; Block
0x180015d2e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015d33  mov     eax, ebx
0x180015d35  mov     rcx, [rsp+98h+var_30]
0x180015d3a  xor     rcx, rsp; StackCookie
0x180015d3d  call    __security_check_cookie
0x180015d42  add     rsp, 78h
0x180015d46  pop     rdi
0x180015d47  pop     rsi
0x180015d48  pop     rbp
0x180015d49  pop     rbx
0x180015d4a  retn
```
