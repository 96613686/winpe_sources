# CertificateUtil::DoesExtensionWithValueExist(char const *,ushort const *,_CERT_OID_VALUE_TYPE,_CERT_CONTEXT const *,int *)

- ea: `0x1800086b0`
- end: `0x180008a53`
- name: `?DoesExtensionWithValueExist@CertificateUtil@@SAJPEBDPEBGW4_CERT_OID_VALUE_TYPE@@PEBU_CERT_CONTEXT@@PEAH@Z`
- size: `931`
- prototype: `static int __high(const char *, const unsigned __int16 *, enum _CERT_OID_VALUE_TYPE, const struct _CERT_CONTEXT *, int *)`
- caller_count: `4`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000d4f4`
- `0x18005c95c`
- `0x18005d424`
- `0x18009434c`

## callees

- `0x1800084f4`
- `0x1800086b0`
- `0x180008a5c`
- `0x18000bac0`
- `0x18000cbd8`
- `0x18000d110`
- `0x1800307c4`
- `0x180043ef8`
- `0x180044300`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000896b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000896b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008917`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008917`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008812`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008812`
- `CRYPT32!CertFindExtension` at `0x18000889b`
- `CRYPT32!CertFindExtension` at `0x18000889b`
- `CRYPT32!CryptDecodeObjectEx` at `0x1800088e0`
- `CRYPT32!CryptDecodeObjectEx` at `0x1800088e0`

## string_xrefs

- `0x18000872d`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x18000877e`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x180008837`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x180008936`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x180008995`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x1800089cb`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x180008a38`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x1800088a1`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x1800089eb`: `%s: Extension was not found in the certificate. OID: %hs.`
- `0x1800087ec`: `Logger::WriteNullOrEmptyParameterFailureEvent`
- `0x1800087e5`: `EventWriteNullOrEmptyParameterFailureEvent`

## pseudocode

```c
__int64 __fastcall CertificateUtil::DoesExtensionWithValueExist(
        const CHAR *a1,
        const WCHAR *a2,
        int a3,
        const struct _CERT_CONTEXT *a4,
        _DWORD *a5)
{
  WCHAR *v5; // rdi
  unsigned int ExtensionStrValueByOid; // eax
  const unsigned __int16 *v10; // r12
  unsigned int v11; // ebx
  const wchar_t *v13; // r14
  __int64 v14; // r8
  unsigned int v15; // eax
  PCERT_INFO pCertInfo; // rdx
  unsigned __int16 *v17; // r13
  CERT_EXTENSION *rgExtension; // r8
  PCERT_EXTENSION Extension; // rax
  int v20; // eax
  __int64 LastError; // r14
  void *Block; // [rsp+40h] [rbp-41h] BYREF
  DWORD pcbStructInfo; // [rsp+48h] [rbp-39h] BYREF
  unsigned __int16 *v24; // [rsp+50h] [rbp-31h] BYREF
  _BYTE v25[16]; // [rsp+58h] [rbp-29h] BYREF
  const unsigned __int16 *v26; // [rsp+68h] [rbp-19h]
  __int64 v27; // [rsp+70h] [rbp-11h]
  const wchar_t *v28; // [rsp+78h] [rbp-9h]
  __int64 v29; // [rsp+80h] [rbp-1h]

  v5 = 0;
  Block = 0;
  if ( !a1 )
  {
    v13 = L"pcszOid";
    v11 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"CertificateUtil::DoesExtensionWithValueExist", L"pcszOid");
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) == 0 )
      goto LABEL_9;
    v29 = 16;
    goto LABEL_12;
  }
  if ( !a2 )
  {
    v11 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::DoesExtensionWithValueExist",
      L"pcszOidValue");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"CertificateUtil::DoesExtensionWithValueExist", L"pcszOidValue");
    goto LABEL_9;
  }
  if ( !a4 )
  {
    v13 = L"pCertContext";
    v11 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::DoesExtensionWithValueExist",
      L"pCertContext");
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) == 0 )
      goto LABEL_9;
    v29 = 26;
    goto LABEL_12;
  }
  if ( !a5 )
  {
    v13 = L"pbResult";
    v11 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"CertificateUtil::DoesExtensionWithValueExist", L"pbResult");
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) == 0 )
      goto LABEL_9;
    v29 = 18;
LABEL_12:
    v26 = L"CertificateUtil::DoesExtensionWithValueExist";
    v27 = 90;
    v28 = v13;
    v15 = McGenEventWrite_EventWriteTransfer(
            &UserDeviceRegistrationEventProvider_Context,
            NullOrEmptyParameterFailureEvent,
            v14,
            3,
            v25);
    if ( v15 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"Logger::WriteNullOrEmptyParameterFailureEvent",
        L"EventWriteNullOrEmptyParameterFailureEvent",
        v15);
    goto LABEL_9;
  }
  *a5 = 0;
  if ( a3 )
  {
    if ( a3 != 1 )
    {
      Logger::TraceError(L"%s: Unknown CERT_OID_VALUE_TYPE: %d.", L"CertificateUtil::DoesExtensionWithValueExist");
      v11 = -2147024809;
      goto LABEL_9;
    }
    pCertInfo = a4->pCertInfo;
    Block = 0;
    pcbStructInfo = 0;
    v17 = 0;
    rgExtension = pCertInfo->rgExtension;
    LODWORD(pCertInfo) = pCertInfo->cExtension;
    v24 = 0;
    Extension = CertFindExtension(a1, (DWORD)pCertInfo, rgExtension);
    v10 = L"CertificateUtil::FindExtensionGuidValueByOid";
    if ( Extension )
    {
      if ( CryptDecodeObjectEx(
             a4->dwCertEncodingType,
             (LPCSTR)0x19,
             Extension->Value.pbData,
             Extension->Value.cbData,
             0x8000u,
             0,
             &Block,
             &pcbStructInfo) )
      {
        v20 = CertificateUtil::GuidStringFromByteArray(*((const unsigned __int8 **)Block + 1), *(_DWORD *)Block, &v24);
        v11 = v20;
        if ( v20 < 0 )
        {
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"CertificateUtil::FindExtensionGuidValueByOid",
            L"CertificateUtil::GuidStringFromByteArray",
            (unsigned int)v20);
          v17 = v24;
        }
        else
        {
          v5 = v24;
        }
      }
      else
      {
        v11 = 0;
        LastError = GetLastError();
        Logger::TraceError(
          L"%s: CryptDecodeObjectEx failed with error code: 0x%08x",
          L"CertificateUtil::FindExtensionGuidValueByOid",
          LastError);
        if ( (_DWORD)LastError )
        {
          if ( (int)LastError > 0 )
            v11 = (unsigned __int16)LastError | 0x80070000;
          else
            v11 = LastError;
        }
      }
    }
    else
    {
      Logger::TraceVerbose(
        (wchar_t *)L"%s: Extension was not found in the certificate. OID: %hs.",
        L"CertificateUtil::FindExtensionGuidValueByOid",
        a1);
      v11 = -2146885628;
    }
    operator delete(v17);
    LocalFree(Block);
  }
  else
  {
    ExtensionStrValueByOid = CertificateUtil::FindExtensionStrValueByOid(a1, a4, (unsigned __int16 **)&Block);
    v5 = (WCHAR *)Block;
    v10 = L"CertificateUtil::FindExtensionStrValueByOid";
    v11 = ExtensionStrValueByOid;
  }
  if ( v11 == -2146885628 )
  {
    v11 = 0;
  }
  else if ( (v11 & 0x80000000) != 0 )
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x",
      L"CertificateUtil::DoesExtensionWithValueExist",
      v10,
      v11);
  }
  else if ( !lstrcmpiW(v5, a2) )
  {
    *a5 = 1;
  }
LABEL_9:
  operator delete(v5);
  return v11;
}

```

## disassembly

```asm
0x1800086b0  push    rbp
0x1800086b2  push    rbx
0x1800086b3  push    rsi
0x1800086b4  push    rdi
0x1800086b5  push    r14
0x1800086b7  push    r15
0x1800086b9  lea     rbp, [rsp-27h]
0x1800086be  sub     rsp, 0A8h
0x1800086c5  mov     rax, cs:__security_cookie
0x1800086cc  xor     rax, rsp
0x1800086cf  mov     [rbp+4Fh+var_48], rax
0x1800086d3  mov     rsi, [rbp+4Fh+arg_20]
0x1800086d7  xor     edi, edi
0x1800086d9  mov     [rbp+4Fh+Block], rdi
0x1800086dd  mov     r14, r9
0x1800086e0  mov     r15, rdx
0x1800086e3  mov     rbx, rcx
0x1800086e6  test    rcx, rcx
0x1800086e9  jz      loc_180008772
0x1800086ef  test    rdx, rdx
0x1800086f2  jz      loc_180008995
0x1800086f8  test    r9, r9
0x1800086fb  jz      loc_18000882B
0x180008701  test    rsi, rsi
0x180008704  jz      loc_18000892A
0x18000870a  mov     [rsp+0D0h+var_30], r12
0x180008712  mov     [rsi], edi
0x180008714  test    r8d, r8d
0x180008717  jnz     loc_18000886A
0x18000871d  lea     r8, [rbp+4Fh+Block]; unsigned __int16 **
0x180008721  mov     rdx, r9; struct _CERT_CONTEXT *
0x180008724  call    ?FindExtensionStrValueByOid@CertificateUtil@@SAJPEBDPEBU_CERT_CONTEXT@@PEAPEAG@Z; CertificateUtil::FindExtensionStrValueByOid(char const *,_CERT_CONTEXT const *,ushort * *)
0x180008729  mov     rdi, [rbp+4Fh+Block]
0x18000872d  lea     r12, aCertificateuti_6; "CertificateUtil::FindExtensionStrValueB"...
0x180008734  mov     ebx, eax
0x180008736  cmp     ebx, 80092004h
0x18000873c  jnz     loc_180008804
0x180008742  xor     ebx, ebx
0x180008744  mov     r12, [rsp+0D0h+var_30]
0x18000874c  mov     rcx, rdi; Block
0x18000874f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008754  mov     eax, ebx
0x180008756  mov     rcx, [rbp+4Fh+var_48]
0x18000875a  xor     rcx, rsp; StackCookie
0x18000875d  call    __security_check_cookie
0x180008762  add     rsp, 0A8h
0x180008769  pop     r15
0x18000876b  pop     r14
0x18000876d  pop     rdi
0x18000876e  pop     rsi
0x18000876f  pop     rbx
0x180008770  pop     rbp
0x180008771  retn
0x180008772  lea     r14, aPcszoid; "pcszOid"
0x180008779  mov     ebx, 80070057h
0x18000877e  lea     rsi, aCertificateuti_8; "CertificateUtil::DoesExtensionWithValue"...
0x180008785  mov     r8, r14
0x180008788  mov     rdx, rsi
0x18000878b  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180008792  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180008797  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x18000879e  jz      short loc_18000874C
0x1800087a0  mov     [rbp+4Fh+var_50], 10h
0x1800087a8  lea     rax, [rbp+4Fh+var_78]
0x1800087ac  mov     [rbp+4Fh+var_68], rsi
0x1800087b0  mov     r9d, 3
0x1800087b6  mov     qword ptr [rsp+0D0h+dwFlags], rax
0x1800087bb  lea     rdx, NullOrEmptyParameterFailureEvent
0x1800087c2  mov     [rbp+4Fh+var_60], 5Ah ; 'Z'
0x1800087ca  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x1800087d1  mov     [rbp+4Fh+var_58], r14
0x1800087d5  call    McGenEventWrite_EventWriteTransfer
0x1800087da  test    eax, eax
0x1800087dc  jz      loc_18000874C
0x1800087e2  mov     r9d, eax
0x1800087e5  lea     r8, aEventwritenull; "EventWriteNullOrEmptyParameterFailureEv"...
0x1800087ec  lea     rdx, aLoggerWritenul; "Logger::WriteNullOrEmptyParameterFailur"...
0x1800087f3  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x1800087fa  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800087ff  jmp     loc_18000874C
0x180008804  test    ebx, ebx
0x180008806  js      loc_180008A35
0x18000880c  mov     rdx, r15; lpString2
0x18000880f  mov     rcx, rdi; lpString1
0x180008812  call    cs:__imp_lstrcmpiW
0x180008818  test    eax, eax
0x18000881a  jnz     loc_180008744
0x180008820  mov     dword ptr [rsi], 1
0x180008826  jmp     loc_180008744
0x18000882b  lea     r14, aPcertcontext; "pCertContext"
0x180008832  mov     ebx, 80070057h
0x180008837  lea     rsi, aCertificateuti_8; "CertificateUtil::DoesExtensionWithValue"...
0x18000883e  mov     r8, r14
0x180008841  mov     rdx, rsi
0x180008844  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18000884b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180008850  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x180008857  jz      loc_18000874C
0x18000885d  mov     [rbp+4Fh+var_50], 1Ah
0x180008865  jmp     loc_1800087A8
0x18000886a  cmp     r8d, 1
0x18000886e  jnz     loc_1800089CB
0x180008874  mov     rdx, [r9+18h]
0x180008878  mov     [rbp+4Fh+Block], rdi
0x18000887c  mov     [rbp+4Fh+var_88], edi
0x18000887f  mov     [rsp+0D0h+var_38], r13
0x180008887  xor     r13d, r13d
0x18000888a  mov     r8, [rdx+0C8h]; rgExtensions
0x180008891  mov     edx, [rdx+0C0h]; cExtensions
0x180008897  mov     [rbp+4Fh+var_80], r13
0x18000889b  call    cs:__imp_CertFindExtension
0x1800088a1  lea     r12, aCertificateuti_5; "CertificateUtil::FindExtensionGuidValue"...
0x1800088a8  test    rax, rax
0x1800088ab  jz      loc_1800089E8
0x1800088b1  mov     r9d, [rax+10h]; cbEncoded
0x1800088b5  lea     rcx, [rbp+4Fh+var_88]
0x1800088b9  mov     r8, [rax+18h]; pbEncoded
0x1800088bd  mov     edx, 19h; lpszStructType
0x1800088c2  mov     [rsp+0D0h+pcbStructInfo], rcx; pcbStructInfo
0x1800088c7  lea     rcx, [rbp+4Fh+Block]
0x1800088cb  mov     [rsp+0D0h+pvStructInfo], rcx; pvStructInfo
0x1800088d0  mov     ecx, [r14]; dwCertEncodingType
0x1800088d3  mov     [rsp+0D0h+pDecodePara], rdi; pDecodePara
0x1800088d8  mov     [rsp+0D0h+dwFlags], 8000h; dwFlags
0x1800088e0  call    cs:__imp_CryptDecodeObjectEx
0x1800088e6  test    eax, eax
0x1800088e8  jz      short loc_180008969
0x1800088ea  mov     rcx, [rbp+4Fh+Block]
0x1800088ee  lea     r8, [rbp+4Fh+var_80]; unsigned __int16 **
0x1800088f2  mov     edx, [rcx]; unsigned int
0x1800088f4  mov     rcx, [rcx+8]; unsigned __int8 *
0x1800088f8  call    ?GuidStringFromByteArray@CertificateUtil@@CAJPEBEKPEAPEAG@Z; CertificateUtil::GuidStringFromByteArray(uchar const *,ulong,ushort * *)
0x1800088fd  mov     ebx, eax
0x1800088ff  test    eax, eax
0x180008901  js      loc_180008A13
0x180008907  mov     rdi, [rbp+4Fh+var_80]
0x18000890b  mov     rcx, r13; Block
0x18000890e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008913  mov     rcx, [rbp+4Fh+Block]; hMem
0x180008917  call    cs:__imp_LocalFree
0x18000891d  mov     r13, [rsp+0D0h+var_38]
0x180008925  jmp     loc_180008736
0x18000892a  lea     r14, aPbresult; "pbResult"
0x180008931  mov     ebx, 80070057h
0x180008936  lea     rsi, aCertificateuti_8; "CertificateUtil::DoesExtensionWithValue"...
0x18000893d  mov     r8, r14
0x180008940  mov     rdx, rsi
0x180008943  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18000894a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000894f  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x180008956  jz      loc_18000874C
0x18000895c  mov     [rbp+4Fh+var_50], 12h
0x180008964  jmp     loc_1800087A8
0x180008969  xor     ebx, ebx
0x18000896b  call    cs:__imp_GetLastError
0x180008971  mov     rdx, r12
0x180008974  lea     rcx, aSCryptdecodeob_0; "%s: CryptDecodeObjectEx failed with err"...
0x18000897b  mov     r8d, eax
0x18000897e  mov     r14d, eax
0x180008981  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180008986  test    r14d, r14d
0x180008989  jz      short loc_18000890B
0x18000898b  jg      short loc_180008A04
0x18000898d  mov     ebx, r14d
0x180008990  jmp     loc_18000890B
0x180008995  lea     rsi, aCertificateuti_8; "CertificateUtil::DoesExtensionWithValue"...
0x18000899c  mov     ebx, 80070057h
0x1800089a1  mov     rdx, rsi
0x1800089a4  lea     r8, aPcszoidvalue; "pcszOidValue"
0x1800089ab  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x1800089b2  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800089b7  lea     rdx, aPcszoidvalue; "pcszOidValue"
0x1800089be  mov     rcx, rsi; unsigned __int16 *
0x1800089c1  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x1800089c6  jmp     loc_18000874C
0x1800089cb  lea     rdx, aCertificateuti_8; "CertificateUtil::DoesExtensionWithValue"...
0x1800089d2  lea     rcx, aSUnknownCertOi; "%s: Unknown CERT_OID_VALUE_TYPE: %d."
0x1800089d9  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800089de  mov     ebx, 80070057h
0x1800089e3  jmp     loc_180008744
0x1800089e8  mov     r8, rbx
0x1800089eb  lea     rcx, aSExtensionWasN; "%s: Extension was not found in the cert"...
0x1800089f2  mov     rdx, r12
0x1800089f5  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800089fa  mov     ebx, 80092004h
0x1800089ff  jmp     loc_18000890B
0x180008a04  movzx   ebx, r14w
0x180008a08  or      ebx, 80070000h
0x180008a0e  jmp     loc_18000890B
0x180008a13  mov     r9d, eax
0x180008a16  lea     r8, aCertificateuti_4; "CertificateUtil::GuidStringFromByteArra"...
0x180008a1d  mov     rdx, r12
0x180008a20  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180008a27  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180008a2c  mov     r13, [rbp+4Fh+var_80]
0x180008a30  jmp     loc_18000890B
0x180008a35  mov     r9d, ebx
0x180008a38  lea     rdx, aCertificateuti_8; "CertificateUtil::DoesExtensionWithValue"...
0x180008a3f  mov     r8, r12
0x180008a42  lea     rcx, aSSFailedWithEr; "%s: %s failed with error code: 0x%08x"
0x180008a49  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180008a4e  jmp     loc_180008744
```
