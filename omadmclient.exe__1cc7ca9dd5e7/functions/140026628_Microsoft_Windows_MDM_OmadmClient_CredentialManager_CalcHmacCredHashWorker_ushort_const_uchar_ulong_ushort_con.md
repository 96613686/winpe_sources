# Microsoft::Windows::MDM::OmadmClient::CredentialManager::CalcHmacCredHashWorker(ushort const *,uchar *,ulong,ushort const *,ushort const *,uchar const * const,ulong,ushort * *)

- ea: `0x140026628`
- end: `0x140026ea6`
- name: `?CalcHmacCredHashWorker@CredentialManager@OmadmClient@MDM@Windows@Microsoft@@IEAAJPEBGPEAEK00QEBEKPEAPEAG@Z`
- size: `2174`
- prototype: `int(Microsoft::Windows::MDM::OmadmClient::CredentialManager *__hidden this, const unsigned __int16 *, unsigned __int8 *, unsigned int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int8 *const, unsigned int, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140027e10`
- `0x140028940`

## callees

- `0x140003450`
- `0x1400036e4`
- `0x140005864`
- `0x14000b0f4`
- `0x14000d71c`
- `0x14000d778`
- `0x14000e610`
- `0x140013404`
- `0x140026628`
- `0x140028328`
- `0x1400552f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400267f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026858`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400268da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026946`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400269ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026b9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026d18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400267f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026858`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400268da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026946`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400269ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026b9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026d18`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002681f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002681f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140026ce5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140026dd4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140026ce5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140026dd4`
- `CRYPTSP!CryptHashData` at `0x140026a2b`
- `CRYPTSP!CryptHashData` at `0x140026b8f`
- `CRYPTSP!CryptHashData` at `0x140026bd9`
- `CRYPTSP!CryptHashData` at `0x140026bfc`
- `CRYPTSP!CryptHashData` at `0x140026c38`
- `CRYPTSP!CryptHashData` at `0x140026d08`
- `CRYPTSP!CryptHashData` at `0x140026a2b`
- `CRYPTSP!CryptHashData` at `0x140026b8f`
- `CRYPTSP!CryptHashData` at `0x140026bd9`
- `CRYPTSP!CryptHashData` at `0x140026bfc`
- `CRYPTSP!CryptHashData` at `0x140026c38`
- `CRYPTSP!CryptHashData` at `0x140026d08`
- `CRYPTSP!CryptCreateHash` at `0x1400268ca`
- `CRYPTSP!CryptCreateHash` at `0x140026936`
- `CRYPTSP!CryptCreateHash` at `0x14002699c`
- `CRYPTSP!CryptCreateHash` at `0x1400268ca`
- `CRYPTSP!CryptCreateHash` at `0x140026936`
- `CRYPTSP!CryptCreateHash` at `0x14002699c`
- `CRYPTSP!CryptGetHashParam` at `0x140026a8f`
- `CRYPTSP!CryptGetHashParam` at `0x140026c7a`
- `CRYPTSP!CryptGetHashParam` at `0x140026d78`
- `CRYPTSP!CryptGetHashParam` at `0x140026a8f`
- `CRYPTSP!CryptGetHashParam` at `0x140026c7a`
- `CRYPTSP!CryptGetHashParam` at `0x140026d78`
- `CRYPTSP!CryptDestroyHash` at `0x140026903`
- `CRYPTSP!CryptDestroyHash` at `0x14002696f`
- `CRYPTSP!CryptDestroyHash` at `0x1400269d5`
- `CRYPTSP!CryptDestroyHash` at `0x140026df4`
- `CRYPTSP!CryptDestroyHash` at `0x140026e0b`
- `CRYPTSP!CryptDestroyHash` at `0x140026e22`
- `CRYPTSP!CryptDestroyHash` at `0x140026903`
- `CRYPTSP!CryptDestroyHash` at `0x14002696f`
- `CRYPTSP!CryptDestroyHash` at `0x1400269d5`
- `CRYPTSP!CryptDestroyHash` at `0x140026df4`
- `CRYPTSP!CryptDestroyHash` at `0x140026e0b`
- `CRYPTSP!CryptDestroyHash` at `0x140026e22`
- `CRYPTSP!CryptReleaseContext` at `0x140026811`
- `CRYPTSP!CryptReleaseContext` at `0x140026886`
- `CRYPTSP!CryptReleaseContext` at `0x140026e40`
- `CRYPTSP!CryptReleaseContext` at `0x140026811`
- `CRYPTSP!CryptReleaseContext` at `0x140026886`
- `CRYPTSP!CryptReleaseContext` at `0x140026e40`
- `CRYPTSP!CryptAcquireContextW` at `0x1400267db`
- `CRYPTSP!CryptAcquireContextW` at `0x140026848`
- `CRYPTSP!CryptAcquireContextW` at `0x1400267db`
- `CRYPTSP!CryptAcquireContextW` at `0x140026848`
- `DMCmnUtils!EncodeBase64W` at `0x140026ca4`
- `DMCmnUtils!EncodeBase64W` at `0x140026daa`
- `DMCmnUtils!EncodeBase64W` at `0x140026ca4`
- `DMCmnUtils!EncodeBase64W` at `0x140026daa`
- `DMCmnUtils!EncodeBase64` at `0x140026b5f`
- `DMCmnUtils!EncodeBase64` at `0x140026b5f`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::CredentialManager::CalcHmacCredHashWorker(
        Microsoft::Windows::MDM::OmadmClient::CredentialManager *this,
        const unsigned __int16 *a2,
        unsigned __int8 *a3,
        DWORD a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        BYTE *a7,
        DWORD a8,
        unsigned __int16 **a9)
{
  char v10; // al
  unsigned int *v11; // rcx
  unsigned int v12; // edi
  __int64 v13; // r9
  HCRYPTPROV v14; // rbx
  DWORD LastError; // edi
  signed int v16; // eax
  signed int v17; // eax
  signed int v18; // eax
  Microsoft::Windows::MDM::OmadmClient::CredentialManager *v19; // rcx
  signed int v20; // eax
  int v21; // eax
  __int64 v22; // rdx
  Microsoft::Windows::MDM::OmadmClient::CredentialManager *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  DWORD v28; // eax
  unsigned int v29; // esi
  void *v30; // rbx
  DWORD v31; // eax
  __int64 v32; // rdx
  unsigned __int64 v33; // r9
  int v34; // eax
  signed int v35; // eax
  Microsoft::Windows::MDM::OmadmClient::CredentialManager *v36; // rcx
  int v37; // eax
  __int64 v38; // rdx
  Microsoft::Windows::MDM::OmadmClient::CredentialManager *v39; // rcx
  signed int v40; // eax
  __int64 v41; // rcx
  __int64 v42; // r8
  __int64 v43; // r9
  DWORD v44; // edx
  int dwFlags; // [rsp+20h] [rbp-F8h]
  DWORD dwFlagsa[2]; // [rsp+20h] [rbp-F8h]
  DWORD dwFlagsb[2]; // [rsp+20h] [rbp-F8h]
  unsigned int v49; // [rsp+30h] [rbp-E8h] BYREF
  HCRYPTPROV phProv; // [rsp+38h] [rbp-E0h] BYREF
  HCRYPTHASH hHash; // [rsp+40h] [rbp-D8h] BYREF
  HCRYPTHASH phHash; // [rsp+48h] [rbp-D0h] BYREF
  HCRYPTHASH v53; // [rsp+50h] [rbp-C8h] BYREF
  DWORD pdwDataLen; // [rsp+58h] [rbp-C0h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp-B8h] BYREF
  DWORD dwDataLen; // [rsp+68h] [rbp-B0h] BYREF
  DWORD v57; // [rsp+6Ch] [rbp-ACh]
  void *v58; // [rsp+70h] [rbp-A8h] BYREF
  BYTE *v59; // [rsp+78h] [rbp-A0h]
  unsigned __int16 **v60; // [rsp+80h] [rbp-98h]
  _QWORD v61[3]; // [rsp+88h] [rbp-90h] BYREF
  int v62; // [rsp+A0h] [rbp-78h]
  unsigned int *v63; // [rsp+A8h] [rbp-70h]
  unsigned int *v64; // [rsp+B0h] [rbp-68h]
  char v65; // [rsp+B8h] [rbp-60h]
  void **v66; // [rsp+C0h] [rbp-58h]
  __int64 v67; // [rsp+C8h] [rbp-50h]
  BYTE pbData[16]; // [rsp+D0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  v57 = a4;
  v59 = a3;
  v60 = a9;
  v49 = 0;
  v61[0] = 0;
  v61[1] = "CalcHmacCredHashWorker";
  v61[2] = COmaDmLogger::GetLogger();
  v62 = 2;
  v63 = &v49;
  v10 = Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits;
  if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
  {
    LODWORD(v58) = 69;
    v66 = &v58;
    v67 = 4;
    McGenEventWrite_EventWriteTransfer(WP_OMADM_CLIENT_PROVIDER_Context, OmaDmClientFunctionEntryPointEvent, 69, 2);
    v10 = Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits;
  }
  v11 = &v49;
  v64 = &v49;
  v65 = 1;
  if ( !a5 )
  {
    v12 = -805306126;
    v49 = -805306126;
    if ( (v10 & 8) != 0 )
    {
      v13 = 3489661170LL;
LABEL_106:
      McTemplateU0qq_EventWriteTransfer(v11, OmaDmClientFunctionReturnValueEvent, 69, v13);
      goto LABEL_107;
    }
    goto LABEL_107;
  }
  if ( a6 )
  {
    if ( !a7 )
    {
      v12 = -805306124;
      v49 = -805306124;
      if ( (v10 & 8) != 0 )
      {
        v13 = 3489661172LL;
        goto LABEL_106;
      }
      goto LABEL_107;
    }
    if ( !a8 )
    {
      v12 = -805306123;
      v49 = -805306123;
      if ( (v10 & 8) != 0 )
      {
        v13 = 3489661173LL;
        goto LABEL_106;
      }
      goto LABEL_107;
    }
    phProv = 0;
    if ( !CryptAcquireContextW(&phProv, 0, 0, 1u, 0xF0000000) )
    {
      v14 = phProv;
      if ( phProv )
      {
        LastError = GetLastError();
        CryptReleaseContext(v14, 0);
        SetLastError(LastError);
      }
      phProv = 0;
      if ( !CryptAcquireContextW(&phProv, 0, 0, 1u, 0xF0000008) )
      {
        v16 = GetLastError();
        v12 = v16;
        if ( v16 > 0 )
          v12 = (unsigned __int16)v16 | 0x80070000;
        v13 = v12;
        v49 = v12;
        v11 = (unsigned int *)phProv;
        if ( phProv )
        {
          CryptReleaseContext(phProv, 0);
          v13 = v49;
        }
        if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
          goto LABEL_106;
        goto LABEL_107;
      }
    }
    phHash = 0;
    if ( !CryptCreateHash(phProv, 0x8003u, 0, 0, &phHash) )
    {
      v17 = GetLastError();
      v12 = v17;
      if ( v17 > 0 )
        v12 = (unsigned __int16)v17 | 0x80070000;
      v49 = v12;
LABEL_29:
      if ( phHash )
        CryptDestroyHash(phHash);
      v11 = (unsigned int *)phProv;
      goto LABEL_102;
    }
    hHash = 0;
    if ( !CryptCreateHash(phProv, 0x8003u, 0, 0, &hHash) )
    {
      v18 = GetLastError();
      v12 = v18;
      if ( v18 > 0 )
        v12 = (unsigned __int16)v18 | 0x80070000;
      v49 = v12;
LABEL_36:
      if ( hHash )
        CryptDestroyHash(hHash);
      goto LABEL_29;
    }
    v53 = 0;
    if ( !CryptCreateHash(phProv, 0x8003u, 0, 0, &v53) )
      goto LABEL_39;
    v21 = Microsoft::Windows::MDM::OmadmClient::CredentialManager::HashFromUnicode(v19, a5, phHash);
    v12 = v21;
    v49 = v21;
    if ( v21 < 0 )
    {
      v22 = 608;
LABEL_46:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v22,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\credentialmanager.cpp",
        (const char *)(unsigned int)v21,
        dwFlags);
      goto LABEL_42;
    }
    if ( !CryptHashData(phHash, ":", 1u, 0) )
      goto LABEL_39;
    v21 = Microsoft::Windows::MDM::OmadmClient::CredentialManager::HashFromUnicode(v23, a6, phHash);
    v12 = v21;
    v49 = v21;
    if ( v21 < 0 )
    {
      v22 = 620;
      goto LABEL_46;
    }
    pdwDataLen = 16;
    *(_OWORD *)pbData = 0;
    if ( !CryptGetHashParam(phHash, 2u, pbData, &pdwDataLen, 0) )
    {
LABEL_39:
      v20 = GetLastError();
      v12 = v20;
      if ( v20 > 0 )
        v12 = (unsigned __int16)v20 | 0x80070000;
      v49 = v12;
      goto LABEL_42;
    }
    v28 = pdwDataLen;
    if ( pdwDataLen != 16 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v25, v24, v26, v27, *(_QWORD *)dwFlagsa);
      v28 = pdwDataLen;
    }
    v29 = 2 * v28;
    v30 = operator new[](2 * v28, (const struct std::nothrow_t *)std::nothrow);
    v58 = v30;
    if ( !v30 )
    {
      v12 = -2147024882;
      v49 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x281,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\credentialmanager.cpp",
        (const char *)0x8007000ELL,
        dwFlagsa[0]);
      goto LABEL_42;
    }
    v31 = -1;
    if ( v29 <= 0x7FFFFFFF )
      v31 = v29;
    v12 = v29 > 0x7FFFFFFF ? 0x80070216 : 0;
    dwDataLen = v31;
    v49 = v12;
    if ( v29 > 0x7FFFFFFF )
    {
      v32 = 646;
LABEL_59:
      v33 = v12;
LABEL_60:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v32,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\credentialmanager.cpp",
        (const char *)v33,
        dwFlagsa[0]);
LABEL_61:
      operator delete(v30);
LABEL_42:
      if ( v53 )
        CryptDestroyHash(v53);
      goto LABEL_36;
    }
    v34 = EncodeBase64(pbData, pdwDataLen, (unsigned __int8 *)v30, (int *)&dwDataLen);
    v12 = v34;
    v49 = v34;
    if ( v34 < 0 )
    {
      v33 = (unsigned int)v34;
      v32 = 649;
      goto LABEL_60;
    }
    if ( CryptHashData(hHash, (const BYTE *)v30, dwDataLen, 0)
      && CryptHashData(hHash, ":", 1u, 0)
      && CryptHashData(hHash, a7, a8, 0) )
    {
      if ( a2 )
      {
        v12 = Microsoft::Windows::MDM::OmadmClient::CredentialManager::HashFromUnicode(v36, a2, v53);
        v49 = v12;
      }
      else
      {
        if ( !CryptHashData(v53, v59, v57, 0) )
          goto LABEL_65;
        v12 = v49;
      }
      if ( (v12 & 0x80000000) != 0 )
      {
        v32 = 690;
        goto LABEL_59;
      }
      if ( CryptGetHashParam(v53, 2u, pbData, &pdwDataLen, 0) )
      {
        hMem = 0;
        v37 = EncodeBase64W(pbData, pdwDataLen, (unsigned __int16 **)&hMem);
        v12 = v37;
        v49 = v37;
        if ( v37 < 0 )
        {
          v38 = 703;
LABEL_79:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v38,
            (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\credentialmanager.cpp",
            (const char *)(unsigned int)v37,
            dwFlagsb[0]);
LABEL_80:
          if ( hMem )
            LocalFree(hMem);
          goto LABEL_61;
        }
        if ( CryptHashData(hHash, ":", 1u, 0) )
        {
          v37 = Microsoft::Windows::MDM::OmadmClient::CredentialManager::HashFromUnicode(
                  v39,
                  (const unsigned __int16 *)hMem,
                  hHash);
          v12 = v37;
          v49 = v37;
          if ( v37 < 0 )
          {
            v38 = 715;
            goto LABEL_79;
          }
          if ( CryptGetHashParam(hHash, 2u, pbData, &pdwDataLen, 0) )
          {
            v44 = pdwDataLen;
            if ( pdwDataLen != 16 )
            {
              MicrosoftTelemetryAssertTriggeredNoArgs(v41, pdwDataLen, v42, v43, *(_QWORD *)dwFlagsb);
              v44 = pdwDataLen;
            }
            v37 = EncodeBase64W(pbData, v44, v60);
            v12 = v37;
            v49 = v37;
            if ( v37 >= 0 )
            {
              if ( hMem )
                LocalFree(hMem);
              operator delete(v30);
              if ( v53 )
                CryptDestroyHash(v53);
              if ( hHash )
                CryptDestroyHash(hHash);
              if ( phHash )
                CryptDestroyHash(phHash);
              v11 = (unsigned int *)phProv;
              if ( !phProv )
              {
LABEL_104:
                if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
                {
                  v13 = v49;
                  goto LABEL_106;
                }
                goto LABEL_107;
              }
LABEL_102:
              if ( v11 )
                CryptReleaseContext((HCRYPTPROV)v11, 0);
              goto LABEL_104;
            }
            v38 = 728;
            goto LABEL_79;
          }
        }
        v40 = GetLastError();
        v12 = v40;
        if ( v40 > 0 )
          v12 = (unsigned __int16)v40 | 0x80070000;
        v49 = v12;
        goto LABEL_80;
      }
    }
LABEL_65:
    v35 = GetLastError();
    v12 = v35;
    if ( v35 > 0 )
      v12 = (unsigned __int16)v35 | 0x80070000;
    v49 = v12;
    goto LABEL_61;
  }
  v12 = -805306125;
  v49 = -805306125;
  if ( (v10 & 8) != 0 )
  {
    v13 = 3489661171LL;
    goto LABEL_106;
  }
LABEL_107:
  Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v61);
  return v12;
}

```

## disassembly

```asm
0x140026628  mov     [rsp+arg_0], rbx
0x14002662d  push    rsi
0x14002662e  push    rdi
0x14002662f  push    r12
0x140026631  push    r13
0x140026633  push    r14
0x140026635  sub     rsp, 0F0h
0x14002663c  mov     rax, cs:__security_cookie
0x140026643  xor     rax, rsp
0x140026646  mov     [rsp+118h+var_38], rax
0x14002664e  mov     [rsp+118h+var_AC], r9d
0x140026653  mov     [rsp+118h+var_A0], r8
0x140026658  mov     r12, rdx
0x14002665b  mov     rsi, [rsp+118h+arg_20]
0x140026663  mov     r14, [rsp+118h+arg_28]
0x14002666b  mov     r13, [rsp+118h+arg_30]
0x140026673  mov     rax, [rsp+118h+arg_40]
0x14002667b  mov     [rsp+118h+var_98], rax
0x140026683  xor     ebx, ebx
0x140026685  mov     [rsp+118h+var_E8], ebx
0x140026689  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x14002668e  mov     [rsp+118h+var_90], rbx
0x140026696  lea     rcx, aCalchmaccredha; "CalcHmacCredHashWorker"
0x14002669d  mov     [rsp+118h+var_88], rcx
0x1400266a5  mov     [rsp+118h+var_80], rax
0x1400266ad  lea     ecx, [rbx+2]
0x1400266b0  mov     [rsp+118h+var_78], ecx
0x1400266b7  lea     rax, [rsp+118h+var_E8]
0x1400266bc  mov     [rsp+118h+var_70], rax
0x1400266c4  mov     eax, cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits
0x1400266ca  lea     r8d, [rbx+45h]
0x1400266ce  mov     dl, 8
0x1400266d0  test    dl, al
0x1400266d2  jz      short loc_140026721
0x1400266d4  mov     dword ptr [rsp+118h+var_A8], r8d
0x1400266d9  lea     rax, [rsp+118h+var_A8]
0x1400266de  mov     [rsp+118h+var_58], rax
0x1400266e6  mov     [rsp+118h+var_50], 4
0x1400266f2  lea     rax, [rsp+118h+var_68]
0x1400266fa  mov     qword ptr [rsp+118h+dwFlags], rax
0x1400266ff  mov     r9d, ecx
0x140026702  lea     rdx, OmaDmClientFunctionEntryPointEvent
0x140026709  lea     rcx, WP_OMADM_CLIENT_PROVIDER_Context
0x140026710  call    McGenEventWrite_EventWriteTransfer
0x140026715  mov     eax, cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits
0x14002671b  mov     dl, 8
0x14002671d  lea     r8d, [rbx+45h]
0x140026721  lea     rcx, [rsp+118h+var_E8]
0x140026726  mov     [rsp+118h+var_68], rcx
0x14002672e  mov     [rsp+118h+var_60], 1
0x140026736  test    rsi, rsi
0x140026739  jnz     short loc_140026757
0x14002673b  mov     edi, 0D00000F2h
0x140026740  mov     [rsp+118h+var_E8], edi
0x140026744  test    dl, al
0x140026746  jz      loc_140026E6E
0x14002674c  mov     r9d, 0D00000F2h
0x140026752  jmp     loc_140026E61
0x140026757  test    r14, r14
0x14002675a  jnz     short loc_140026778
0x14002675c  mov     edi, 0D00000F3h
0x140026761  mov     [rsp+118h+var_E8], edi
0x140026765  test    dl, al
0x140026767  jz      loc_140026E6E
0x14002676d  mov     r9d, 0D00000F3h
0x140026773  jmp     loc_140026E61
0x140026778  test    r13, r13
0x14002677b  jnz     short loc_140026799
0x14002677d  mov     edi, 0D00000F4h
0x140026782  mov     [rsp+118h+var_E8], edi
0x140026786  test    dl, al
0x140026788  jz      loc_140026E6E
0x14002678e  mov     r9d, 0D00000F4h
0x140026794  jmp     loc_140026E61
0x140026799  cmp     [rsp+118h+arg_38], ebx
0x1400267a0  jnz     short loc_1400267BE
0x1400267a2  mov     edi, 0D00000F5h
0x1400267a7  mov     [rsp+118h+var_E8], edi
0x1400267ab  test    dl, al
0x1400267ad  jz      loc_140026E6E
0x1400267b3  mov     r9d, 0D00000F5h
0x1400267b9  jmp     loc_140026E61
0x1400267be  mov     [rsp+118h+phProv], rbx
0x1400267c3  mov     [rsp+118h+dwFlags], 0F0000000h; dwFlags
0x1400267cb  mov     r9d, 1; dwProvType
0x1400267d1  xor     r8d, r8d; szProvider
0x1400267d4  xor     edx, edx; szContainer
0x1400267d6  lea     rcx, [rsp+118h+phProv]; phProv
0x1400267db  call    cs:__imp_CryptAcquireContextW
0x1400267e2  nop     dword ptr [rax+rax+00h]
0x1400267e7  test    eax, eax
0x1400267e9  jnz     loc_1400268A9
0x1400267ef  mov     rbx, [rsp+118h+phProv]
0x1400267f4  test    rbx, rbx
0x1400267f7  jz      short loc_14002682B
0x1400267f9  call    cs:__imp_GetLastError
0x140026800  nop     dword ptr [rax+rax+00h]
0x140026805  mov     edi, eax
0x140026807  test    rbx, rbx
0x14002680a  jz      short loc_14002681D
0x14002680c  xor     edx, edx; dwFlags
0x14002680e  mov     rcx, rbx; hProv
0x140026811  call    cs:__imp_CryptReleaseContext
0x140026818  nop     dword ptr [rax+rax+00h]
0x14002681d  mov     ecx, edi; dwErrCode
0x14002681f  call    cs:__imp_SetLastError
0x140026826  nop     dword ptr [rax+rax+00h]
0x14002682b  xor     ebx, ebx
0x14002682d  mov     [rsp+118h+phProv], rbx
0x140026832  mov     [rsp+118h+dwFlags], 0F0000008h; dwFlags
0x14002683a  lea     r9d, [rbx+1]; dwProvType
0x14002683e  xor     r8d, r8d; szProvider
0x140026841  xor     edx, edx; szContainer
0x140026843  lea     rcx, [rsp+118h+phProv]; phProv
0x140026848  call    cs:__imp_CryptAcquireContextW
0x14002684f  nop     dword ptr [rax+rax+00h]
0x140026854  test    eax, eax
0x140026856  jnz     short loc_1400268A9
0x140026858  call    cs:__imp_GetLastError
0x14002685f  nop     dword ptr [rax+rax+00h]
0x140026864  mov     edi, eax
0x140026866  test    eax, eax
0x140026868  jle     short loc_140026873
0x14002686a  movzx   edi, ax
0x14002686d  or      edi, 80070000h
0x140026873  mov     r9d, edi
0x140026876  mov     [rsp+118h+var_E8], edi
0x14002687a  mov     rcx, [rsp+118h+phProv]; hProv
0x14002687f  test    rcx, rcx
0x140026882  jz      short loc_140026897
0x140026884  xor     edx, edx; dwFlags
0x140026886  call    cs:__imp_CryptReleaseContext
0x14002688d  nop     dword ptr [rax+rax+00h]
0x140026892  mov     r9d, [rsp+118h+var_E8]
0x140026897  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x14002689e  jz      loc_140026E6E
0x1400268a4  jmp     loc_140026E5B
0x1400268a9  mov     [rsp+118h+phHash], rbx
0x1400268ae  lea     rax, [rsp+118h+phHash]
0x1400268b3  mov     qword ptr [rsp+118h+dwFlags], rax; phHash
0x1400268b8  xor     r9d, r9d; dwFlags
0x1400268bb  xor     r8d, r8d; hKey
0x1400268be  mov     edi, 8003h
0x1400268c3  mov     edx, edi; Algid
0x1400268c5  mov     rcx, [rsp+118h+phProv]; hProv
0x1400268ca  call    cs:__imp_CryptCreateHash
0x1400268d1  nop     dword ptr [rax+rax+00h]
0x1400268d6  test    eax, eax
0x1400268d8  jnz     short loc_14002691A
0x1400268da  call    cs:__imp_GetLastError
0x1400268e1  nop     dword ptr [rax+rax+00h]
0x1400268e6  mov     edi, eax
0x1400268e8  test    eax, eax
0x1400268ea  jle     short loc_1400268F5
0x1400268ec  movzx   edi, ax
0x1400268ef  or      edi, 80070000h
0x1400268f5  mov     [rsp+118h+var_E8], edi
0x1400268f9  mov     rcx, [rsp+118h+phHash]; hHash
0x1400268fe  test    rcx, rcx
0x140026901  jz      short loc_140026910
0x140026903  call    cs:__imp_CryptDestroyHash
0x14002690a  nop     dword ptr [rax+rax+00h]
0x14002690f  nop
0x140026910  mov     rcx, [rsp+118h+phProv]
0x140026915  jmp     loc_140026E39
0x14002691a  mov     [rsp+118h+hHash], rbx
0x14002691f  lea     rax, [rsp+118h+hHash]
0x140026924  mov     qword ptr [rsp+118h+dwFlags], rax; phHash
0x140026929  xor     r9d, r9d; dwFlags
0x14002692c  xor     r8d, r8d; hKey
0x14002692f  mov     edx, edi; Algid
0x140026931  mov     rcx, [rsp+118h+phProv]; hProv
0x140026936  call    cs:__imp_CryptCreateHash
0x14002693d  nop     dword ptr [rax+rax+00h]
0x140026942  test    eax, eax
0x140026944  jnz     short loc_140026980
0x140026946  call    cs:__imp_GetLastError
0x14002694d  nop     dword ptr [rax+rax+00h]
0x140026952  mov     edi, eax
0x140026954  test    eax, eax
0x140026956  jle     short loc_140026961
0x140026958  movzx   edi, ax
0x14002695b  or      edi, 80070000h
0x140026961  mov     [rsp+118h+var_E8], edi
0x140026965  mov     rcx, [rsp+118h+hHash]; hHash
0x14002696a  test    rcx, rcx
0x14002696d  jz      short loc_1400268F9
0x14002696f  call    cs:__imp_CryptDestroyHash
0x140026976  nop     dword ptr [rax+rax+00h]
0x14002697b  jmp     loc_1400268F9
0x140026980  mov     [rsp+118h+var_C8], rbx
0x140026985  lea     rax, [rsp+118h+var_C8]
0x14002698a  mov     qword ptr [rsp+118h+dwFlags], rax; int
0x14002698f  xor     r9d, r9d; dwFlags
0x140026992  xor     r8d, r8d; hKey
0x140026995  mov     edx, edi; Algid
0x140026997  mov     rcx, [rsp+118h+phProv]; hProv
0x14002699c  call    cs:__imp_CryptCreateHash
0x1400269a3  nop     dword ptr [rax+rax+00h]
0x1400269a8  test    eax, eax
0x1400269aa  jnz     short loc_1400269E3
0x1400269ac  call    cs:__imp_GetLastError
0x1400269b3  nop     dword ptr [rax+rax+00h]
0x1400269b8  test    eax, eax
0x1400269ba  mov     edi, eax
0x1400269bc  jle     short loc_1400269C7
0x1400269be  movzx   edi, ax
0x1400269c1  or      edi, 80070000h
0x1400269c7  mov     [rsp+118h+var_E8], edi
0x1400269cb  mov     rcx, [rsp+118h+var_C8]; hHash
0x1400269d0  test    rcx, rcx
0x1400269d3  jz      short loc_140026965
0x1400269d5  call    cs:__imp_CryptDestroyHash
0x1400269dc  nop     dword ptr [rax+rax+00h]
0x1400269e1  jmp     short loc_140026965
0x1400269e3  mov     r8, [rsp+118h+phHash]; unsigned __int64
0x1400269e8  mov     rdx, rsi; unsigned __int16 *
0x1400269eb  call    ?HashFromUnicode@CredentialManager@OmadmClient@MDM@Windows@Microsoft@@IEAAJPEBG_K@Z; Microsoft::Windows::MDM::OmadmClient::CredentialManager::HashFromUnicode(ushort const *,unsigned __int64)
0x1400269f0  mov     edi, eax
0x1400269f2  mov     [rsp+118h+var_E8], eax
0x1400269f6  test    eax, eax
0x1400269f8  jns     short loc_140026A18
0x1400269fa  mov     edx, 260h; void *
0x1400269ff  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x140026a06  mov     r9d, eax; char *
0x140026a09  mov     rcx, [rsp+118h]; this
0x140026a11  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140026a16  jmp     short loc_1400269CB
0x140026a18  xor     r9d, r9d; dwFlags
0x140026a1b  lea     r8d, [r9+1]; dwDataLen
0x140026a1f  lea     rdx, pbData; ":"
0x140026a26  mov     rcx, [rsp+118h+phHash]; hHash
0x140026a2b  call    cs:__imp_CryptHashData
0x140026a32  nop     dword ptr [rax+rax+00h]
0x140026a37  test    eax, eax
0x140026a39  jz      loc_1400269AC
0x140026a3f  mov     r8, [rsp+118h+phHash]; unsigned __int64
0x140026a44  mov     rdx, r14; unsigned __int16 *
0x140026a47  call    ?HashFromUnicode@CredentialManager@OmadmClient@MDM@Windows@Microsoft@@IEAAJPEBG_K@Z; Microsoft::Windows::MDM::OmadmClient::CredentialManager::HashFromUnicode(ushort const *,unsigned __int64)
0x140026a4c  mov     edi, eax
0x140026a4e  mov     [rsp+118h+var_E8], eax
0x140026a52  xor     r14d, r14d
0x140026a55  test    eax, eax
0x140026a57  jns     short loc_140026A60
0x140026a59  mov     edx, 26Ch
0x140026a5e  jmp     short loc_1400269FF
0x140026a60  mov     [rsp+118h+pdwDataLen], 10h
0x140026a68  xorps   xmm0, xmm0
0x140026a6b  movups  xmmword ptr [rsp+118h+pbData], xmm0
0x140026a73  mov     [rsp+118h+dwFlags], r14d; int
0x140026a78  lea     r9, [rsp+118h+pdwDataLen]; pdwDataLen
0x140026a7d  lea     r8, [rsp+118h+pbData]; pbData
0x140026a85  mov     edx, 2; dwParam
0x140026a8a  mov     rcx, [rsp+118h+phHash]; hHash
0x140026a8f  call    cs:__imp_CryptGetHashParam
0x140026a96  nop     dword ptr [rax+rax+00h]
0x140026a9b  test    eax, eax
0x140026a9d  jz      loc_1400269AC
0x140026aa3  mov     eax, [rsp+118h+pdwDataLen]
0x140026aa7  cmp     eax, 10h
0x140026aaa  jz      short loc_140026AB5
0x140026aac  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "gc_dwMD5DigestSize == cbCalcDigest")
0x140026ab1  mov     eax, [rsp+118h+pdwDataLen]
0x140026ab5  lea     esi, [rax+rax]
0x140026ab8  mov     ecx, esi; unsigned __int64
0x140026aba  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140026ac1  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140026ac6  mov     rbx, rax
0x140026ac9  mov     [rsp+118h+var_A8], rax
0x140026ace  test    rax, rax
0x140026ad1  jnz     short loc_140026AFE
0x140026ad3  mov     edi, 8007000Eh
0x140026ad8  mov     [rsp+118h+var_E8], edi
0x140026adc  mov     rcx, [rsp+118h]; this
0x140026ae4  mov     r9d, edi; char *
0x140026ae7  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x140026aee  mov     edx, 281h; void *
0x140026af3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140026af8  nop
0x140026af9  jmp     loc_1400269CB
0x140026afe  or      eax, 0FFFFFFFFh
0x140026b01  mov     ecx, 7FFFFFFFh
0x140026b06  cmp     esi, ecx
0x140026b08  cmovbe  eax, esi
0x140026b0b  cmp     ecx, esi
0x140026b0d  sbb     edi, edi
0x140026b0f  and     edi, 80070216h
0x140026b15  mov     [rsp+118h+dwDataLen], eax
0x140026b19  mov     [rsp+118h+var_E8], edi
0x140026b1d  cmp     esi, ecx
0x140026b1f  jbe     short loc_140026B4B
0x140026b21  mov     edx, 286h; void *
0x140026b26  mov     r9d, edi; char *
0x140026b29  mov     rcx, [rsp+118h]; this
0x140026b31  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x140026b38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140026b3d  nop
0x140026b3e  mov     rcx, rbx; Block
0x140026b41  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140026b46  jmp     loc_1400269CB
  ... truncated ...
```
