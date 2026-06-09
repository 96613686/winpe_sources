# CertificateUtil::FindExtensionGuidValueByOid(char const *,_CERT_CONTEXT const *,ushort * *)

- ea: `0x180009a70`
- end: `0x180009f55`
- name: `?FindExtensionGuidValueByOid@CertificateUtil@@SAJPEBDPEBU_CERT_CONTEXT@@PEAPEAG@Z`
- size: `1253`
- prototype: `__int64 __fastcall(const char *, const struct _CERT_CONTEXT *, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180008ad0`
- `0x180009f5c`
- `0x180015b10`
- `0x18002aee4`

## callees

- `0x1800073c0`
- `0x180009a70`
- `0x180027278`
- `0x180027448`
- `0x1800274cc`
- `0x18002bc58`
- `0x18002e664`
- `0x18002f710`
- `0x180046ce0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c3f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009f2f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009f2f`
- `CRYPT32!CertFindExtension` at `0x180009bd7`
- `CRYPT32!CertFindExtension` at `0x180009bd7`
- `CRYPT32!CryptDecodeObjectEx` at `0x180009c32`
- `CRYPT32!CryptDecodeObjectEx` at `0x180009c32`

## string_xrefs

- `0x180009abe`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x180009b52`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x180009b8d`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x180009be5`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x180009c48`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x180009cef`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x180009b35`: `Logger::WriteNullOrEmptyParameterFailureEvent`
- `0x180009b2e`: `EventWriteNullOrEmptyParameterFailureEvent`
- `0x180009bec`: `%s: Extension was not found in the certificate. OID: %hs.`

## pseudocode

```c
__int64 __fastcall CertificateUtil::FindExtensionGuidValueByOid(
        const char *a1,
        const struct _CERT_CONTEXT *a2,
        unsigned __int16 **a3)
{
  unsigned int v6; // ebx
  __int64 v7; // r8
  unsigned int v8; // eax
  PCERT_EXTENSION Extension; // rax
  __int64 LastError; // rsi
  unsigned int v11; // edi
  unsigned __int8 *v12; // rsi
  unsigned __int16 *v13; // rax
  unsigned __int16 *v14; // rbx
  DWORD pcbStructInfo; // [rsp+40h] [rbp-78h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-70h] BYREF
  _BYTE v18[16]; // [rsp+50h] [rbp-68h] BYREF
  const unsigned __int16 *v19; // [rsp+60h] [rbp-58h]
  __int64 v20; // [rsp+68h] [rbp-50h]
  const wchar_t *v21; // [rsp+70h] [rbp-48h]
  __int64 v22; // [rsp+78h] [rbp-40h]

  hMem = 0;
  pcbStructInfo = 0;
  if ( a1 )
  {
    if ( a3 )
    {
      if ( a2 )
      {
        *a3 = 0;
        Extension = CertFindExtension(a1, a2->pCertInfo->cExtension, a2->pCertInfo->rgExtension);
        if ( Extension )
        {
          if ( CryptDecodeObjectEx(
                 a2->dwCertEncodingType,
                 (LPCSTR)0x19,
                 Extension->Value.pbData,
                 Extension->Value.cbData,
                 0x8000u,
                 0,
                 &hMem,
                 &pcbStructInfo) )
          {
            if ( *(_DWORD *)hMem == 16 )
            {
              v12 = (unsigned __int8 *)*((_QWORD *)hMem + 1);
              v13 = (unsigned __int16 *)operator new[](0x4Au, (const struct std::nothrow_t *)&std::nothrow);
              v14 = v13;
              if ( v13 )
              {
                *v13 = a0123456789abcd[(unsigned __int64)v12[3] >> 4];
                v13[1] = a0123456789abcd[v12[3] & 0xF];
                v13[2] = a0123456789abcd[(unsigned __int64)v12[2] >> 4];
                v13[3] = a0123456789abcd[v12[2] & 0xF];
                v13[4] = a0123456789abcd[(unsigned __int64)v12[1] >> 4];
                v13[5] = a0123456789abcd[v12[1] & 0xF];
                v13[6] = a0123456789abcd[(unsigned __int64)*v12 >> 4];
                v13[7] = a0123456789abcd[*v12 & 0xF];
                v13[8] = 45;
                v13[9] = a0123456789abcd[(unsigned __int64)v12[5] >> 4];
                v13[10] = a0123456789abcd[v12[5] & 0xF];
                v13[11] = a0123456789abcd[(unsigned __int64)v12[4] >> 4];
                v13[12] = a0123456789abcd[v12[4] & 0xF];
                v13[13] = 45;
                v13[14] = a0123456789abcd[(unsigned __int64)v12[7] >> 4];
                v13[15] = a0123456789abcd[v12[7] & 0xF];
                v13[16] = a0123456789abcd[(unsigned __int64)v12[6] >> 4];
                v13[17] = a0123456789abcd[v12[6] & 0xF];
                v13[18] = 45;
                v13[19] = a0123456789abcd[(unsigned __int64)v12[8] >> 4];
                v13[20] = a0123456789abcd[v12[8] & 0xF];
                v13[21] = a0123456789abcd[(unsigned __int64)v12[9] >> 4];
                v13[22] = a0123456789abcd[v12[9] & 0xF];
                v13[23] = 45;
                v13[24] = a0123456789abcd[(unsigned __int64)v12[10] >> 4];
                v13[25] = a0123456789abcd[v12[10] & 0xF];
                v13[26] = a0123456789abcd[(unsigned __int64)v12[11] >> 4];
                v13[27] = a0123456789abcd[v12[11] & 0xF];
                v13[28] = a0123456789abcd[(unsigned __int64)v12[12] >> 4];
                v13[29] = a0123456789abcd[v12[12] & 0xF];
                v13[30] = a0123456789abcd[(unsigned __int64)v12[13] >> 4];
                v13[31] = a0123456789abcd[v12[13] & 0xF];
                v13[32] = a0123456789abcd[(unsigned __int64)v12[14] >> 4];
                v13[33] = a0123456789abcd[v12[14] & 0xF];
                v13[34] = a0123456789abcd[(unsigned __int64)v12[15] >> 4];
                v13[35] = a0123456789abcd[v12[15] & 0xF];
                v13[36] = 0;
                operator delete(0);
                *a3 = v14;
                v6 = 0;
                goto LABEL_22;
              }
              v6 = -2147024882;
              v11 = -2147024882;
              Logger::TraceCritical(
                L"%s: Out of memory. Allocation failed.",
                L"CertificateUtil::GuidStringFromByteArray");
            }
            else
            {
              Logger::TraceError(
                L"%s: cbInputCount size is not the size of Guid: %d.",
                L"CertificateUtil::GuidStringFromByteArray");
              v6 = -2147024809;
              v11 = -2147024809;
            }
            operator delete(0);
            Logger::TraceError(
              L"%s: %s failed with error code: 0x%08x.",
              L"CertificateUtil::FindExtensionGuidValueByOid",
              L"CertificateUtil::GuidStringFromByteArray",
              v11);
          }
          else
          {
            v6 = 0;
            LastError = GetLastError();
            Logger::TraceError(
              L"%s: CryptDecodeObjectEx failed with error code: 0x%08x",
              L"CertificateUtil::FindExtensionGuidValueByOid",
              LastError);
            if ( (_DWORD)LastError )
            {
              if ( (int)LastError > 0 )
                v6 = (unsigned __int16)LastError | 0x80070000;
              else
                v6 = LastError;
            }
          }
        }
        else
        {
          Logger::TraceVerbose(
            L"%s: Extension was not found in the certificate. OID: %hs.",
            L"CertificateUtil::FindExtensionGuidValueByOid",
            a1);
          v6 = -2146885628;
        }
      }
      else
      {
        v6 = -2147024809;
        Logger::TraceError(
          L"%s: \"%s\" should not be null.",
          L"CertificateUtil::FindExtensionGuidValueByOid",
          &stru_1800542A8);
        Logger::WriteNullOrEmptyParameterFailureEvent(
          L"CertificateUtil::FindExtensionGuidValueByOid",
          (const unsigned __int16 *)&stru_1800542A8);
      }
    }
    else
    {
      v6 = -2147024809;
      Logger::TraceError(
        L"%s: \"%s\" should not be null.",
        L"CertificateUtil::FindExtensionGuidValueByOid",
        &stru_1800542A8.hCertStore);
      Logger::WriteNullOrEmptyParameterFailureEvent(
        L"CertificateUtil::FindExtensionGuidValueByOid",
        (const unsigned __int16 *)&stru_1800542A8.hCertStore);
    }
  }
  else
  {
    v6 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"CertificateUtil::FindExtensionGuidValueByOid", L"pcszOid");
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
    {
      v19 = L"CertificateUtil::FindExtensionGuidValueByOid";
      v20 = 90;
      v21 = L"pcszOid";
      v22 = 16;
      v8 = McGenEventWrite_EventWriteTransfer(
             &UserDeviceRegistrationEventProvider_Context,
             NullOrEmptyParameterFailureEvent,
             v7,
             3,
             v18);
      if ( v8 )
        Logger::TraceError(
          L"%s: %s failed with win32 error code: 0x%08x.",
          L"Logger::WriteNullOrEmptyParameterFailureEvent",
          L"EventWriteNullOrEmptyParameterFailureEvent",
          v8);
    }
  }
LABEL_22:
  operator delete(0);
  LocalFree(hMem);
  return v6;
}

```

## disassembly

```asm
0x180009a70  push    rbx
0x180009a72  push    rbp
0x180009a73  push    rsi
0x180009a74  push    rdi
0x180009a75  push    r14
0x180009a77  sub     rsp, 90h
0x180009a7e  mov     rax, cs:__security_cookie
0x180009a85  xor     rax, rsp
0x180009a88  mov     [rsp+0B8h+var_38], rax
0x180009a90  xor     r14d, r14d
0x180009a93  mov     rdi, r8
0x180009a96  mov     [rsp+0B8h+hMem], r14
0x180009a9b  mov     rbx, rdx
0x180009a9e  mov     [rsp+0B8h+var_78], r14d
0x180009aa3  mov     rsi, rcx
0x180009aa6  mov     ebp, r14d
0x180009aa9  test    rcx, rcx
0x180009aac  jnz     loc_180009B4D
0x180009ab2  lea     rsi, aPcszoid; "pcszOid"
0x180009ab9  mov     ebx, 80070057h
0x180009abe  lea     rdi, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x180009ac5  mov     r8, rsi
0x180009ac8  mov     rdx, rdi
0x180009acb  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x180009ad2  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180009ad7  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x180009ade  jz      loc_180009F22
0x180009ae4  lea     rax, [rsp+0B8h+var_68]
0x180009ae9  mov     [rsp+0B8h+var_58], rdi
0x180009aee  mov     r9d, 3
0x180009af4  mov     qword ptr [rsp+0B8h+dwFlags], rax
0x180009af9  lea     rdx, NullOrEmptyParameterFailureEvent
0x180009b00  mov     [rsp+0B8h+var_50], 5Ah ; 'Z'
0x180009b09  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x180009b10  mov     [rsp+0B8h+var_48], rsi
0x180009b15  mov     [rsp+0B8h+var_40], 10h
0x180009b1e  call    McGenEventWrite_EventWriteTransfer
0x180009b23  test    eax, eax
0x180009b25  jz      loc_180009F22
0x180009b2b  mov     r9d, eax
0x180009b2e  lea     r8, aEventwritenull; "EventWriteNullOrEmptyParameterFailureEv"...
0x180009b35  lea     rdx, aLoggerWritenul; "Logger::WriteNullOrEmptyParameterFailur"...
0x180009b3c  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x180009b43  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180009b48  jmp     loc_180009F22
0x180009b4d  test    rdi, rdi
0x180009b50  jnz     short loc_180009B88
0x180009b52  lea     rdi, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x180009b59  mov     ebx, 80070057h
0x180009b5e  mov     rdx, rdi
0x180009b61  lea     r8, stru_1800542A8.hCertStore
0x180009b68  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x180009b6f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180009b74  lea     rdx, stru_1800542A8.hCertStore; unsigned __int16 *
0x180009b7b  mov     rcx, rdi; unsigned __int16 *
0x180009b7e  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180009b83  jmp     loc_180009F22
0x180009b88  test    rbx, rbx
0x180009b8b  jnz     short loc_180009BC3
0x180009b8d  lea     rdi, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x180009b94  mov     ebx, 80070057h
0x180009b99  mov     rdx, rdi
0x180009b9c  lea     r8, stru_1800542A8
0x180009ba3  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x180009baa  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180009baf  lea     rdx, stru_1800542A8; unsigned __int16 *
0x180009bb6  mov     rcx, rdi; unsigned __int16 *
0x180009bb9  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180009bbe  jmp     loc_180009F22
0x180009bc3  mov     [r8], r14
0x180009bc6  mov     rdx, [rdx+18h]
0x180009bca  mov     r8, [rdx+0C8h]; rgExtensions
0x180009bd1  mov     edx, [rdx+0C0h]; cExtensions
0x180009bd7  call    cs:__imp_CertFindExtension
0x180009bdd  test    rax, rax
0x180009be0  jnz     short loc_180009C02
0x180009be2  mov     r8, rsi
0x180009be5  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x180009bec  lea     rcx, aSExtensionWasN; "%s: Extension was not found in the cert"...
0x180009bf3  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180009bf8  mov     ebx, 80092004h
0x180009bfd  jmp     loc_180009F22
0x180009c02  mov     r9d, [rax+10h]; cbEncoded
0x180009c06  lea     rcx, [rsp+0B8h+var_78]
0x180009c0b  mov     r8, [rax+18h]; pbEncoded
0x180009c0f  mov     edx, 19h; lpszStructType
0x180009c14  mov     [rsp+0B8h+pcbStructInfo], rcx; pcbStructInfo
0x180009c19  lea     rcx, [rsp+0B8h+hMem]
0x180009c1e  mov     [rsp+0B8h+pvStructInfo], rcx; pvStructInfo
0x180009c23  mov     ecx, [rbx]; dwCertEncodingType
0x180009c25  mov     [rsp+0B8h+pDecodePara], r14; pDecodePara
0x180009c2a  mov     [rsp+0B8h+dwFlags], 8000h; dwFlags
0x180009c32  call    cs:__imp_CryptDecodeObjectEx
0x180009c38  test    eax, eax
0x180009c3a  jnz     short loc_180009C7C
0x180009c3c  mov     ebx, r14d
0x180009c3f  call    cs:__imp_GetLastError
0x180009c45  mov     r8d, eax
0x180009c48  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x180009c4f  lea     rcx, aSCryptdecodeob_0; "%s: CryptDecodeObjectEx failed with err"...
0x180009c56  mov     esi, eax
0x180009c58  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180009c5d  test    esi, esi
0x180009c5f  jz      loc_180009F22
0x180009c65  jg      short loc_180009C6E
0x180009c67  mov     ebx, esi
0x180009c69  jmp     loc_180009F22
0x180009c6e  movzx   ebx, si
0x180009c71  or      ebx, 80070000h
0x180009c77  jmp     loc_180009F22
0x180009c7c  mov     rax, [rsp+0B8h+hMem]
0x180009c81  mov     r8d, [rax]
0x180009c84  cmp     r8d, 10h
0x180009c88  jz      short loc_180009CA6
0x180009c8a  lea     rdx, aCertificateuti_3; "CertificateUtil::GuidStringFromByteArra"...
0x180009c91  lea     rcx, aSCbinputcountS; "%s: cbInputCount size is not the size o"...
0x180009c98  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180009c9d  mov     ebx, 80070057h
0x180009ca2  mov     edi, ebx
0x180009ca4  jmp     short loc_180009CDD
0x180009ca6  mov     rsi, [rax+8]
0x180009caa  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009cb1  mov     ecx, 4Ah ; 'J'; unsigned __int64
0x180009cb6  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180009cbb  mov     rbx, rax
0x180009cbe  test    rax, rax
0x180009cc1  jnz     short loc_180009D07
0x180009cc3  mov     ebx, 8007000Eh
0x180009cc8  lea     rdx, aCertificateuti_3; "CertificateUtil::GuidStringFromByteArra"...
0x180009ccf  lea     rcx, aSOutOfMemoryAl; "%s: Out of memory. Allocation failed."
0x180009cd6  mov     edi, ebx
0x180009cd8  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x180009cdd  mov     rcx, r14; Block
0x180009ce0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009ce5  mov     r9d, edi
0x180009ce8  lea     r8, aCertificateuti_3; "CertificateUtil::GuidStringFromByteArra"...
0x180009cef  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x180009cf6  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x180009cfd  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180009d02  jmp     loc_180009F22
0x180009d07  movzx   eax, byte ptr [rsi+3]
0x180009d0b  lea     rdx, a0123456789abcd; "0123456789abcdef"
0x180009d12  shr     rax, 4
0x180009d16  mov     ecx, 2Dh ; '-'
0x180009d1b  movzx   eax, word ptr [rdx+rax*2]
0x180009d1f  mov     [rbx], ax
0x180009d22  movzx   eax, byte ptr [rsi+3]
0x180009d26  and     eax, 0Fh
0x180009d29  movzx   eax, word ptr [rdx+rax*2]
0x180009d2d  mov     [rbx+2], ax
0x180009d31  movzx   eax, byte ptr [rsi+2]
0x180009d35  shr     rax, 4
0x180009d39  movzx   eax, word ptr [rdx+rax*2]
0x180009d3d  mov     [rbx+4], ax
0x180009d41  movzx   eax, byte ptr [rsi+2]
0x180009d45  and     eax, 0Fh
0x180009d48  movzx   eax, word ptr [rdx+rax*2]
0x180009d4c  mov     [rbx+6], ax
0x180009d50  movzx   eax, byte ptr [rsi+1]
0x180009d54  shr     rax, 4
0x180009d58  movzx   eax, word ptr [rdx+rax*2]
0x180009d5c  mov     [rbx+8], ax
0x180009d60  movzx   eax, byte ptr [rsi+1]
0x180009d64  and     eax, 0Fh
0x180009d67  movzx   eax, word ptr [rdx+rax*2]
0x180009d6b  mov     [rbx+0Ah], ax
0x180009d6f  movzx   eax, byte ptr [rsi]
0x180009d72  shr     rax, 4
0x180009d76  movzx   eax, word ptr [rdx+rax*2]
0x180009d7a  mov     [rbx+0Ch], ax
0x180009d7e  movzx   eax, byte ptr [rsi]
0x180009d81  and     eax, 0Fh
0x180009d84  movzx   eax, word ptr [rdx+rax*2]
0x180009d88  mov     [rbx+0Eh], ax
0x180009d8c  mov     [rbx+10h], cx
0x180009d90  movzx   eax, byte ptr [rsi+5]
0x180009d94  shr     rax, 4
0x180009d98  movzx   eax, word ptr [rdx+rax*2]
0x180009d9c  mov     [rbx+12h], ax
0x180009da0  movzx   eax, byte ptr [rsi+5]
0x180009da4  and     eax, 0Fh
0x180009da7  movzx   eax, word ptr [rdx+rax*2]
0x180009dab  mov     [rbx+14h], ax
0x180009daf  movzx   eax, byte ptr [rsi+4]
0x180009db3  shr     rax, 4
0x180009db7  movzx   eax, word ptr [rdx+rax*2]
0x180009dbb  mov     [rbx+16h], ax
0x180009dbf  movzx   eax, byte ptr [rsi+4]
0x180009dc3  and     eax, 0Fh
0x180009dc6  movzx   eax, word ptr [rdx+rax*2]
0x180009dca  mov     [rbx+18h], ax
0x180009dce  mov     [rbx+1Ah], cx
0x180009dd2  movzx   eax, byte ptr [rsi+7]
0x180009dd6  shr     rax, 4
0x180009dda  movzx   eax, word ptr [rdx+rax*2]
0x180009dde  mov     [rbx+1Ch], ax
0x180009de2  movzx   eax, byte ptr [rsi+7]
0x180009de6  and     eax, 0Fh
0x180009de9  movzx   eax, word ptr [rdx+rax*2]
0x180009ded  mov     [rbx+1Eh], ax
0x180009df1  movzx   eax, byte ptr [rsi+6]
0x180009df5  shr     rax, 4
0x180009df9  movzx   eax, word ptr [rdx+rax*2]
0x180009dfd  mov     [rbx+20h], ax
0x180009e01  movzx   eax, byte ptr [rsi+6]
0x180009e05  and     eax, 0Fh
0x180009e08  movzx   eax, word ptr [rdx+rax*2]
0x180009e0c  mov     [rbx+22h], ax
0x180009e10  mov     [rbx+24h], cx
0x180009e14  movzx   eax, byte ptr [rsi+8]
0x180009e18  shr     rax, 4
0x180009e1c  movzx   eax, word ptr [rdx+rax*2]
0x180009e20  mov     [rbx+26h], ax
0x180009e24  movzx   eax, byte ptr [rsi+8]
0x180009e28  and     eax, 0Fh
0x180009e2b  movzx   eax, word ptr [rdx+rax*2]
0x180009e2f  mov     [rbx+28h], ax
0x180009e33  movzx   eax, byte ptr [rsi+9]
0x180009e37  shr     rax, 4
0x180009e3b  movzx   eax, word ptr [rdx+rax*2]
0x180009e3f  mov     [rbx+2Ah], ax
0x180009e43  movzx   eax, byte ptr [rsi+9]
0x180009e47  and     eax, 0Fh
0x180009e4a  movzx   eax, word ptr [rdx+rax*2]
0x180009e4e  mov     [rbx+2Ch], ax
0x180009e52  mov     [rbx+2Eh], cx
0x180009e56  xor     ecx, ecx; Block
0x180009e58  movzx   eax, byte ptr [rsi+0Ah]
0x180009e5c  shr     rax, 4
0x180009e60  movzx   eax, word ptr [rdx+rax*2]
0x180009e64  mov     [rbx+30h], ax
0x180009e68  movzx   eax, byte ptr [rsi+0Ah]
0x180009e6c  and     eax, 0Fh
0x180009e6f  movzx   eax, word ptr [rdx+rax*2]
0x180009e73  mov     [rbx+32h], ax
0x180009e77  movzx   eax, byte ptr [rsi+0Bh]
0x180009e7b  shr     rax, 4
0x180009e7f  movzx   eax, word ptr [rdx+rax*2]
0x180009e83  mov     [rbx+34h], ax
0x180009e87  movzx   eax, byte ptr [rsi+0Bh]
0x180009e8b  and     eax, 0Fh
0x180009e8e  movzx   eax, word ptr [rdx+rax*2]
0x180009e92  mov     [rbx+36h], ax
0x180009e96  movzx   eax, byte ptr [rsi+0Ch]
0x180009e9a  shr     rax, 4
0x180009e9e  movzx   eax, word ptr [rdx+rax*2]
0x180009ea2  mov     [rbx+38h], ax
0x180009ea6  movzx   eax, byte ptr [rsi+0Ch]
0x180009eaa  and     eax, 0Fh
0x180009ead  movzx   eax, word ptr [rdx+rax*2]
0x180009eb1  mov     [rbx+3Ah], ax
0x180009eb5  movzx   eax, byte ptr [rsi+0Dh]
0x180009eb9  shr     rax, 4
0x180009ebd  movzx   eax, word ptr [rdx+rax*2]
0x180009ec1  mov     [rbx+3Ch], ax
0x180009ec5  movzx   eax, byte ptr [rsi+0Dh]
0x180009ec9  and     eax, 0Fh
0x180009ecc  movzx   eax, word ptr [rdx+rax*2]
0x180009ed0  mov     [rbx+3Eh], ax
0x180009ed4  movzx   eax, byte ptr [rsi+0Eh]
0x180009ed8  shr     rax, 4
0x180009edc  movzx   eax, word ptr [rdx+rax*2]
0x180009ee0  mov     [rbx+40h], ax
0x180009ee4  movzx   eax, byte ptr [rsi+0Eh]
0x180009ee8  and     eax, 0Fh
0x180009eeb  movzx   eax, word ptr [rdx+rax*2]
0x180009eef  mov     [rbx+42h], ax
0x180009ef3  movzx   eax, byte ptr [rsi+0Fh]
0x180009ef7  shr     rax, 4
0x180009efb  movzx   eax, word ptr [rdx+rax*2]
0x180009eff  mov     [rbx+44h], ax
0x180009f03  movzx   eax, byte ptr [rsi+0Fh]
0x180009f07  and     eax, 0Fh
0x180009f0a  movzx   eax, word ptr [rdx+rax*2]
0x180009f0e  mov     [rbx+46h], ax
0x180009f12  mov     [rbx+48h], r14w
0x180009f17  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009f1c  mov     [rdi], rbx
0x180009f1f  mov     ebx, r14d
0x180009f22  mov     rcx, rbp; Block
0x180009f25  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009f2a  mov     rcx, [rsp+0B8h+hMem]; hMem
0x180009f2f  call    cs:__imp_LocalFree
0x180009f35  mov     eax, ebx
0x180009f37  mov     rcx, [rsp+0B8h+var_38]
0x180009f3f  xor     rcx, rsp; StackCookie
0x180009f42  call    __security_check_cookie
0x180009f47  add     rsp, 90h
0x180009f4e  pop     r14
0x180009f50  pop     rdi
0x180009f51  pop     rsi
0x180009f52  pop     rbp
0x180009f53  pop     rbx
0x180009f54  retn
```
