# Microsoft::Windows::MDM::OmadmClient::CredentialManager::CalcMd5CredHash(ushort const *,ushort const *,uchar const * const,ulong,ushort * *)

- ea: `0x140026eac`
- end: `0x140027509`
- name: `?CalcMd5CredHash@CredentialManager@OmadmClient@MDM@Windows@Microsoft@@IEAAJPEBG0QEBEKPEAPEAG@Z`
- size: `1629`
- prototype: `int(Microsoft::Windows::MDM::OmadmClient::CredentialManager *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int8 *const, unsigned int, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400280f0`
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
- `0x140026eac`
- `0x140028328`
- `0x1400552f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002704d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400270ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002712e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002719a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140027394`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002704d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400270ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002712e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002719a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140027394`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140027073`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140027073`
- `CRYPTSP!CryptHashData` at `0x14002721c`
- `CRYPTSP!CryptHashData` at `0x140027384`
- `CRYPTSP!CryptHashData` at `0x1400273cb`
- `CRYPTSP!CryptHashData` at `0x1400273ee`
- `CRYPTSP!CryptHashData` at `0x14002721c`
- `CRYPTSP!CryptHashData` at `0x140027384`
- `CRYPTSP!CryptHashData` at `0x1400273cb`
- `CRYPTSP!CryptHashData` at `0x1400273ee`
- `CRYPTSP!CryptCreateHash` at `0x14002711e`
- `CRYPTSP!CryptCreateHash` at `0x14002718a`
- `CRYPTSP!CryptCreateHash` at `0x14002711e`
- `CRYPTSP!CryptCreateHash` at `0x14002718a`
- `CRYPTSP!CryptGetHashParam` at `0x140027284`
- `CRYPTSP!CryptGetHashParam` at `0x14002741b`
- `CRYPTSP!CryptGetHashParam` at `0x140027284`
- `CRYPTSP!CryptGetHashParam` at `0x14002741b`
- `CRYPTSP!CryptDestroyHash` at `0x140027157`
- `CRYPTSP!CryptDestroyHash` at `0x1400271c3`
- `CRYPTSP!CryptDestroyHash` at `0x140027471`
- `CRYPTSP!CryptDestroyHash` at `0x140027488`
- `CRYPTSP!CryptDestroyHash` at `0x140027157`
- `CRYPTSP!CryptDestroyHash` at `0x1400271c3`
- `CRYPTSP!CryptDestroyHash` at `0x140027471`
- `CRYPTSP!CryptDestroyHash` at `0x140027488`
- `CRYPTSP!CryptReleaseContext` at `0x140027065`
- `CRYPTSP!CryptReleaseContext` at `0x1400270da`
- `CRYPTSP!CryptReleaseContext` at `0x1400274a6`
- `CRYPTSP!CryptReleaseContext` at `0x140027065`
- `CRYPTSP!CryptReleaseContext` at `0x1400270da`
- `CRYPTSP!CryptReleaseContext` at `0x1400274a6`
- `CRYPTSP!CryptAcquireContextW` at `0x14002702f`
- `CRYPTSP!CryptAcquireContextW` at `0x14002709c`
- `CRYPTSP!CryptAcquireContextW` at `0x14002702f`
- `CRYPTSP!CryptAcquireContextW` at `0x14002709c`
- `DMCmnUtils!EncodeBase64W` at `0x14002744c`
- `DMCmnUtils!EncodeBase64W` at `0x14002744c`
- `DMCmnUtils!EncodeBase64` at `0x140027354`
- `DMCmnUtils!EncodeBase64` at `0x140027354`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::CredentialManager::CalcMd5CredHash(
        Microsoft::Windows::MDM::OmadmClient::CredentialManager *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const BYTE *a4,
        DWORD a5,
        unsigned __int16 **a6)
{
  char v9; // al
  unsigned int *v10; // rcx
  unsigned int v11; // edi
  __int64 v12; // r9
  HCRYPTPROV v13; // rbx
  DWORD LastError; // edi
  signed int v15; // eax
  signed int v16; // eax
  Microsoft::Windows::MDM::OmadmClient::CredentialManager *v17; // rcx
  signed int v18; // eax
  int v19; // eax
  __int64 v20; // rdx
  Microsoft::Windows::MDM::OmadmClient::CredentialManager *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // r9
  DWORD v26; // eax
  unsigned int v27; // esi
  unsigned __int8 *v28; // rbx
  DWORD v29; // eax
  unsigned __int64 v30; // r9
  __int64 v31; // rdx
  int v32; // eax
  signed int v33; // eax
  __int64 v34; // rcx
  __int64 v35; // r8
  __int64 v36; // r9
  DWORD v37; // edx
  int dwFlags; // [rsp+20h] [rbp-C8h]
  DWORD dwFlagsa[2]; // [rsp+20h] [rbp-C8h]
  DWORD dwFlagsb[2]; // [rsp+20h] [rbp-C8h]
  unsigned int v42; // [rsp+30h] [rbp-B8h] BYREF
  HCRYPTPROV phProv; // [rsp+38h] [rbp-B0h] BYREF
  HCRYPTHASH phHash; // [rsp+40h] [rbp-A8h] BYREF
  HCRYPTHASH hHash; // [rsp+48h] [rbp-A0h] BYREF
  DWORD pdwDataLen; // [rsp+50h] [rbp-98h] BYREF
  DWORD dwDataLen; // [rsp+54h] [rbp-94h] BYREF
  unsigned __int8 *v48; // [rsp+58h] [rbp-90h] BYREF
  _QWORD v49[3]; // [rsp+60h] [rbp-88h] BYREF
  int v50; // [rsp+78h] [rbp-70h]
  unsigned int *v51; // [rsp+80h] [rbp-68h]
  unsigned int *v52; // [rsp+88h] [rbp-60h]
  char v53; // [rsp+90h] [rbp-58h]
  unsigned __int8 **v54; // [rsp+98h] [rbp-50h]
  __int64 v55; // [rsp+A0h] [rbp-48h]
  BYTE pbData[16]; // [rsp+A8h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  v42 = 0;
  v49[0] = 0;
  v49[1] = "CalcMd5CredHash";
  v49[2] = COmaDmLogger::GetLogger();
  v50 = 2;
  v51 = &v42;
  v9 = Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits;
  if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
  {
    LODWORD(v48) = 70;
    v54 = &v48;
    v55 = 4;
    McGenEventWrite_EventWriteTransfer(WP_OMADM_CLIENT_PROVIDER_Context, OmaDmClientFunctionEntryPointEvent, 70, 2);
    v9 = Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits;
  }
  v10 = &v42;
  v52 = &v42;
  v53 = 1;
  if ( !a2 )
  {
    v11 = -805306129;
    v42 = -805306129;
    if ( (v9 & 8) != 0 )
    {
      v12 = 3489661167LL;
LABEL_75:
      McTemplateU0qq_EventWriteTransfer(v10, OmaDmClientFunctionReturnValueEvent, 70, v12);
      goto LABEL_76;
    }
    goto LABEL_76;
  }
  if ( a3 )
  {
    if ( !a4 )
    {
      v11 = -805306127;
      v42 = -805306127;
      if ( (v9 & 8) != 0 )
      {
        v12 = 3489661169LL;
        goto LABEL_75;
      }
      goto LABEL_76;
    }
    if ( !a5 )
    {
      v11 = -805306126;
      v42 = -805306126;
      if ( (v9 & 8) != 0 )
      {
        v12 = 3489661170LL;
        goto LABEL_75;
      }
      goto LABEL_76;
    }
    phProv = 0;
    if ( !CryptAcquireContextW(&phProv, 0, 0, 1u, 0xF0000000) )
    {
      v13 = phProv;
      if ( phProv )
      {
        LastError = GetLastError();
        CryptReleaseContext(v13, 0);
        SetLastError(LastError);
      }
      phProv = 0;
      if ( !CryptAcquireContextW(&phProv, 0, 0, 1u, 0xF0000008) )
      {
        v15 = GetLastError();
        v11 = v15;
        if ( v15 > 0 )
          v11 = (unsigned __int16)v15 | 0x80070000;
        v12 = v11;
        v42 = v11;
        v10 = (unsigned int *)phProv;
        if ( phProv )
        {
          CryptReleaseContext(phProv, 0);
          v12 = v42;
        }
        if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
          goto LABEL_75;
        goto LABEL_76;
      }
    }
    phHash = 0;
    if ( !CryptCreateHash(phProv, 0x8003u, 0, 0, &phHash) )
    {
      v16 = GetLastError();
      v11 = v16;
      if ( v16 > 0 )
        v11 = (unsigned __int16)v16 | 0x80070000;
      v42 = v11;
LABEL_29:
      if ( phHash )
        CryptDestroyHash(phHash);
      v10 = (unsigned int *)phProv;
      goto LABEL_71;
    }
    hHash = 0;
    if ( !CryptCreateHash(phProv, 0x8003u, 0, 0, &hHash) )
      goto LABEL_33;
    v19 = Microsoft::Windows::MDM::OmadmClient::CredentialManager::HashFromUnicode(v17, a2, phHash);
    v11 = v19;
    v42 = v19;
    if ( v19 < 0 )
    {
      v20 = 809;
LABEL_40:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v20,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\credentialmanager.cpp",
        (const char *)(unsigned int)v19,
        dwFlags);
      goto LABEL_36;
    }
    if ( !CryptHashData(phHash, ":", 1u, 0) )
      goto LABEL_33;
    v19 = Microsoft::Windows::MDM::OmadmClient::CredentialManager::HashFromUnicode(v21, a3, phHash);
    v11 = v19;
    v42 = v19;
    if ( v19 < 0 )
    {
      v20 = 821;
      goto LABEL_40;
    }
    pdwDataLen = 16;
    *(_OWORD *)pbData = 0;
    if ( !CryptGetHashParam(phHash, 2u, pbData, &pdwDataLen, 0) )
    {
LABEL_33:
      v18 = GetLastError();
      v11 = v18;
      if ( v18 > 0 )
        v11 = (unsigned __int16)v18 | 0x80070000;
      v42 = v11;
      goto LABEL_36;
    }
    v26 = pdwDataLen;
    if ( pdwDataLen != 16 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v23, v22, v24, v25, *(_QWORD *)dwFlagsa);
      v26 = pdwDataLen;
    }
    v27 = 2 * v26;
    v28 = (unsigned __int8 *)operator new[](2 * v26, (const struct std::nothrow_t *)std::nothrow);
    v48 = v28;
    if ( !v28 )
    {
      v11 = -2147024882;
      v42 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x349,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\credentialmanager.cpp",
        (const char *)0x8007000ELL,
        dwFlagsa[0]);
      goto LABEL_36;
    }
    v29 = -1;
    if ( v27 <= 0x7FFFFFFF )
      v29 = v27;
    v11 = v27 > 0x7FFFFFFF ? 0x80070216 : 0;
    dwDataLen = v29;
    v42 = v11;
    if ( v27 <= 0x7FFFFFFF )
    {
      v32 = EncodeBase64(pbData, pdwDataLen, v28, (int *)&dwDataLen);
      v11 = v32;
      v42 = v32;
      if ( v32 >= 0 )
      {
        if ( CryptHashData(hHash, v28, dwDataLen, 0)
          && CryptHashData(hHash, ":", 1u, 0)
          && CryptHashData(hHash, a4, a5, 0)
          && CryptGetHashParam(hHash, 2u, pbData, &pdwDataLen, 0) )
        {
          v37 = pdwDataLen;
          if ( pdwDataLen != 16 )
          {
            MicrosoftTelemetryAssertTriggeredNoArgs(v34, pdwDataLen, v35, v36, *(_QWORD *)dwFlagsb);
            v37 = pdwDataLen;
          }
          v11 = EncodeBase64W(pbData, v37, a6);
          v42 = v11;
          operator delete(v28);
          if ( hHash )
            CryptDestroyHash(hHash);
          if ( phHash )
            CryptDestroyHash(phHash);
          v10 = (unsigned int *)phProv;
          if ( !phProv )
          {
LABEL_73:
            if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
            {
              v12 = v42;
              goto LABEL_75;
            }
            goto LABEL_76;
          }
LABEL_71:
          if ( v10 )
            CryptReleaseContext((HCRYPTPROV)v10, 0);
          goto LABEL_73;
        }
        v33 = GetLastError();
        v11 = v33;
        if ( v33 > 0 )
          v11 = (unsigned __int16)v33 | 0x80070000;
        v42 = v11;
        goto LABEL_54;
      }
      v30 = (unsigned int)v32;
      v31 = 849;
    }
    else
    {
      v30 = v11;
      v31 = 846;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v31,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\credentialmanager.cpp",
      (const char *)v30,
      dwFlagsa[0]);
LABEL_54:
    operator delete(v28);
LABEL_36:
    if ( hHash )
      CryptDestroyHash(hHash);
    goto LABEL_29;
  }
  v11 = -805306128;
  v42 = -805306128;
  if ( (v9 & 8) != 0 )
  {
    v12 = 3489661168LL;
    goto LABEL_75;
  }
LABEL_76:
  Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v49);
  return v11;
}

```

## disassembly

```asm
0x140026eac  mov     [rsp+arg_0], rbx
0x140026eb1  push    rsi
0x140026eb2  push    rdi
0x140026eb3  push    r12
0x140026eb5  push    r13
0x140026eb7  push    r14
0x140026eb9  sub     rsp, 0C0h
0x140026ec0  mov     rax, cs:__security_cookie
0x140026ec7  xor     rax, rsp
0x140026eca  mov     [rsp+0E8h+var_30], rax
0x140026ed2  mov     r12, r9
0x140026ed5  mov     r14, r8
0x140026ed8  mov     rsi, rdx
0x140026edb  mov     r13, [rsp+0E8h+arg_28]
0x140026ee3  xor     ebx, ebx
0x140026ee5  mov     [rsp+0E8h+var_B8], ebx
0x140026ee9  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x140026eee  mov     [rsp+0E8h+var_88], rbx
0x140026ef3  lea     rcx, aCalcmd5credhas; "CalcMd5CredHash"
0x140026efa  mov     [rsp+0E8h+var_80], rcx
0x140026eff  mov     [rsp+0E8h+var_78], rax
0x140026f04  lea     ecx, [rbx+2]
0x140026f07  mov     [rsp+0E8h+var_70], ecx
0x140026f0b  lea     rax, [rsp+0E8h+var_B8]
0x140026f10  mov     [rsp+0E8h+var_68], rax
0x140026f18  mov     eax, cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits
0x140026f1e  lea     r8d, [rbx+46h]
0x140026f22  mov     dl, 8
0x140026f24  test    dl, al
0x140026f26  jz      short loc_140026F75
0x140026f28  mov     dword ptr [rsp+0E8h+var_90], r8d
0x140026f2d  lea     rax, [rsp+0E8h+var_90]
0x140026f32  mov     [rsp+0E8h+var_50], rax
0x140026f3a  mov     [rsp+0E8h+var_48], 4
0x140026f46  lea     rax, [rsp+0E8h+var_60]
0x140026f4e  mov     qword ptr [rsp+0E8h+dwFlags], rax
0x140026f53  mov     r9d, ecx
0x140026f56  lea     rdx, OmaDmClientFunctionEntryPointEvent
0x140026f5d  lea     rcx, WP_OMADM_CLIENT_PROVIDER_Context
0x140026f64  call    McGenEventWrite_EventWriteTransfer
0x140026f69  mov     eax, cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits
0x140026f6f  mov     dl, 8
0x140026f71  lea     r8d, [rbx+46h]
0x140026f75  lea     rcx, [rsp+0E8h+var_B8]
0x140026f7a  mov     [rsp+0E8h+var_60], rcx
0x140026f82  mov     [rsp+0E8h+var_58], 1
0x140026f8a  test    rsi, rsi
0x140026f8d  jnz     short loc_140026FAB
0x140026f8f  mov     edi, 0D00000EFh
0x140026f94  mov     [rsp+0E8h+var_B8], edi
0x140026f98  test    dl, al
0x140026f9a  jz      loc_1400274D4
0x140026fa0  mov     r9d, 0D00000EFh
0x140026fa6  jmp     loc_1400274C7
0x140026fab  test    r14, r14
0x140026fae  jnz     short loc_140026FCC
0x140026fb0  mov     edi, 0D00000F0h
0x140026fb5  mov     [rsp+0E8h+var_B8], edi
0x140026fb9  test    dl, al
0x140026fbb  jz      loc_1400274D4
0x140026fc1  mov     r9d, 0D00000F0h
0x140026fc7  jmp     loc_1400274C7
0x140026fcc  test    r12, r12
0x140026fcf  jnz     short loc_140026FED
0x140026fd1  mov     edi, 0D00000F1h
0x140026fd6  mov     [rsp+0E8h+var_B8], edi
0x140026fda  test    dl, al
0x140026fdc  jz      loc_1400274D4
0x140026fe2  mov     r9d, 0D00000F1h
0x140026fe8  jmp     loc_1400274C7
0x140026fed  cmp     [rsp+0E8h+arg_20], ebx
0x140026ff4  jnz     short loc_140027012
0x140026ff6  mov     edi, 0D00000F2h
0x140026ffb  mov     [rsp+0E8h+var_B8], edi
0x140026fff  test    dl, al
0x140027001  jz      loc_1400274D4
0x140027007  mov     r9d, 0D00000F2h
0x14002700d  jmp     loc_1400274C7
0x140027012  mov     [rsp+0E8h+phProv], rbx
0x140027017  mov     [rsp+0E8h+dwFlags], 0F0000000h; dwFlags
0x14002701f  mov     r9d, 1; dwProvType
0x140027025  xor     r8d, r8d; szProvider
0x140027028  xor     edx, edx; szContainer
0x14002702a  lea     rcx, [rsp+0E8h+phProv]; phProv
0x14002702f  call    cs:__imp_CryptAcquireContextW
0x140027036  nop     dword ptr [rax+rax+00h]
0x14002703b  test    eax, eax
0x14002703d  jnz     loc_1400270FD
0x140027043  mov     rbx, [rsp+0E8h+phProv]
0x140027048  test    rbx, rbx
0x14002704b  jz      short loc_14002707F
0x14002704d  call    cs:__imp_GetLastError
0x140027054  nop     dword ptr [rax+rax+00h]
0x140027059  mov     edi, eax
0x14002705b  test    rbx, rbx
0x14002705e  jz      short loc_140027071
0x140027060  xor     edx, edx; dwFlags
0x140027062  mov     rcx, rbx; hProv
0x140027065  call    cs:__imp_CryptReleaseContext
0x14002706c  nop     dword ptr [rax+rax+00h]
0x140027071  mov     ecx, edi; dwErrCode
0x140027073  call    cs:__imp_SetLastError
0x14002707a  nop     dword ptr [rax+rax+00h]
0x14002707f  xor     ebx, ebx
0x140027081  mov     [rsp+0E8h+phProv], rbx
0x140027086  mov     [rsp+0E8h+dwFlags], 0F0000008h; dwFlags
0x14002708e  lea     r9d, [rbx+1]; dwProvType
0x140027092  xor     r8d, r8d; szProvider
0x140027095  xor     edx, edx; szContainer
0x140027097  lea     rcx, [rsp+0E8h+phProv]; phProv
0x14002709c  call    cs:__imp_CryptAcquireContextW
0x1400270a3  nop     dword ptr [rax+rax+00h]
0x1400270a8  test    eax, eax
0x1400270aa  jnz     short loc_1400270FD
0x1400270ac  call    cs:__imp_GetLastError
0x1400270b3  nop     dword ptr [rax+rax+00h]
0x1400270b8  mov     edi, eax
0x1400270ba  test    eax, eax
0x1400270bc  jle     short loc_1400270C7
0x1400270be  movzx   edi, ax
0x1400270c1  or      edi, 80070000h
0x1400270c7  mov     r9d, edi
0x1400270ca  mov     [rsp+0E8h+var_B8], edi
0x1400270ce  mov     rcx, [rsp+0E8h+phProv]; hProv
0x1400270d3  test    rcx, rcx
0x1400270d6  jz      short loc_1400270EB
0x1400270d8  xor     edx, edx; dwFlags
0x1400270da  call    cs:__imp_CryptReleaseContext
0x1400270e1  nop     dword ptr [rax+rax+00h]
0x1400270e6  mov     r9d, [rsp+0E8h+var_B8]
0x1400270eb  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x1400270f2  jz      loc_1400274D4
0x1400270f8  jmp     loc_1400274C1
0x1400270fd  mov     [rsp+0E8h+phHash], rbx
0x140027102  lea     rax, [rsp+0E8h+phHash]
0x140027107  mov     qword ptr [rsp+0E8h+dwFlags], rax; phHash
0x14002710c  xor     r9d, r9d; dwFlags
0x14002710f  xor     r8d, r8d; hKey
0x140027112  mov     edi, 8003h
0x140027117  mov     edx, edi; Algid
0x140027119  mov     rcx, [rsp+0E8h+phProv]; hProv
0x14002711e  call    cs:__imp_CryptCreateHash
0x140027125  nop     dword ptr [rax+rax+00h]
0x14002712a  test    eax, eax
0x14002712c  jnz     short loc_14002716E
0x14002712e  call    cs:__imp_GetLastError
0x140027135  nop     dword ptr [rax+rax+00h]
0x14002713a  mov     edi, eax
0x14002713c  test    eax, eax
0x14002713e  jle     short loc_140027149
0x140027140  movzx   edi, ax
0x140027143  or      edi, 80070000h
0x140027149  mov     [rsp+0E8h+var_B8], edi
0x14002714d  mov     rcx, [rsp+0E8h+phHash]; hHash
0x140027152  test    rcx, rcx
0x140027155  jz      short loc_140027164
0x140027157  call    cs:__imp_CryptDestroyHash
0x14002715e  nop     dword ptr [rax+rax+00h]
0x140027163  nop
0x140027164  mov     rcx, [rsp+0E8h+phProv]
0x140027169  jmp     loc_14002749F
0x14002716e  mov     [rsp+0E8h+hHash], rbx
0x140027173  lea     rax, [rsp+0E8h+hHash]
0x140027178  mov     qword ptr [rsp+0E8h+dwFlags], rax; int
0x14002717d  xor     r9d, r9d; dwFlags
0x140027180  xor     r8d, r8d; hKey
0x140027183  mov     edx, edi; Algid
0x140027185  mov     rcx, [rsp+0E8h+phProv]; hProv
0x14002718a  call    cs:__imp_CryptCreateHash
0x140027191  nop     dword ptr [rax+rax+00h]
0x140027196  test    eax, eax
0x140027198  jnz     short loc_1400271D4
0x14002719a  call    cs:__imp_GetLastError
0x1400271a1  nop     dword ptr [rax+rax+00h]
0x1400271a6  test    eax, eax
0x1400271a8  mov     edi, eax
0x1400271aa  jle     short loc_1400271B5
0x1400271ac  movzx   edi, ax
0x1400271af  or      edi, 80070000h
0x1400271b5  mov     [rsp+0E8h+var_B8], edi
0x1400271b9  mov     rcx, [rsp+0E8h+hHash]; hHash
0x1400271be  test    rcx, rcx
0x1400271c1  jz      short loc_14002714D
0x1400271c3  call    cs:__imp_CryptDestroyHash
0x1400271ca  nop     dword ptr [rax+rax+00h]
0x1400271cf  jmp     loc_14002714D
0x1400271d4  mov     r8, [rsp+0E8h+phHash]; unsigned __int64
0x1400271d9  mov     rdx, rsi; unsigned __int16 *
0x1400271dc  call    ?HashFromUnicode@CredentialManager@OmadmClient@MDM@Windows@Microsoft@@IEAAJPEBG_K@Z; Microsoft::Windows::MDM::OmadmClient::CredentialManager::HashFromUnicode(ushort const *,unsigned __int64)
0x1400271e1  mov     edi, eax
0x1400271e3  mov     [rsp+0E8h+var_B8], eax
0x1400271e7  test    eax, eax
0x1400271e9  jns     short loc_140027209
0x1400271eb  mov     edx, 329h; void *
0x1400271f0  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x1400271f7  mov     r9d, eax; char *
0x1400271fa  mov     rcx, [rsp+0E8h]; this
0x140027202  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140027207  jmp     short loc_1400271B9
0x140027209  xor     r9d, r9d; dwFlags
0x14002720c  lea     r8d, [r9+1]; dwDataLen
0x140027210  lea     rdx, pbData; ":"
0x140027217  mov     rcx, [rsp+0E8h+phHash]; hHash
0x14002721c  call    cs:__imp_CryptHashData
0x140027223  nop     dword ptr [rax+rax+00h]
0x140027228  test    eax, eax
0x14002722a  jz      loc_14002719A
0x140027230  mov     r8, [rsp+0E8h+phHash]; unsigned __int64
0x140027235  mov     rdx, r14; unsigned __int16 *
0x140027238  call    ?HashFromUnicode@CredentialManager@OmadmClient@MDM@Windows@Microsoft@@IEAAJPEBG_K@Z; Microsoft::Windows::MDM::OmadmClient::CredentialManager::HashFromUnicode(ushort const *,unsigned __int64)
0x14002723d  mov     edi, eax
0x14002723f  mov     [rsp+0E8h+var_B8], eax
0x140027243  test    eax, eax
0x140027245  jns     short loc_14002724E
0x140027247  mov     edx, 335h
0x14002724c  jmp     short loc_1400271F0
0x14002724e  mov     [rsp+0E8h+pdwDataLen], 10h
0x140027256  xorps   xmm0, xmm0
0x140027259  movups  xmmword ptr [rsp+0E8h+pbData], xmm0
0x140027261  mov     [rsp+0E8h+dwFlags], 0; int
0x140027269  lea     r9, [rsp+0E8h+pdwDataLen]; pdwDataLen
0x14002726e  lea     r8, [rsp+0E8h+pbData]; pbData
0x140027276  mov     r14d, 2
0x14002727c  mov     edx, r14d; dwParam
0x14002727f  mov     rcx, [rsp+0E8h+phHash]; hHash
0x140027284  call    cs:__imp_CryptGetHashParam
0x14002728b  nop     dword ptr [rax+rax+00h]
0x140027290  test    eax, eax
0x140027292  jz      loc_14002719A
0x140027298  mov     eax, [rsp+0E8h+pdwDataLen]
0x14002729c  cmp     eax, 10h
0x14002729f  jz      short loc_1400272AA
0x1400272a1  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "gc_dwMD5DigestSize == cbCalcDigest")
0x1400272a6  mov     eax, [rsp+0E8h+pdwDataLen]
0x1400272aa  lea     esi, [rax+rax]
0x1400272ad  mov     ecx, esi; unsigned __int64
0x1400272af  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400272b6  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1400272bb  mov     rbx, rax
0x1400272be  mov     [rsp+0E8h+var_90], rax
0x1400272c3  test    rax, rax
0x1400272c6  jnz     short loc_1400272F3
0x1400272c8  mov     edi, 8007000Eh
0x1400272cd  mov     [rsp+0E8h+var_B8], edi
0x1400272d1  mov     rcx, [rsp+0E8h]; this
0x1400272d9  mov     r9d, edi; char *
0x1400272dc  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x1400272e3  mov     edx, 349h; void *
0x1400272e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400272ed  nop
0x1400272ee  jmp     loc_1400271B9
0x1400272f3  or      eax, 0FFFFFFFFh
0x1400272f6  mov     ecx, 7FFFFFFFh
0x1400272fb  cmp     esi, ecx
0x1400272fd  cmovbe  eax, esi
0x140027300  cmp     ecx, esi
0x140027302  sbb     edi, edi
0x140027304  and     edi, 80070216h
0x14002730a  mov     [rsp+0E8h+dwDataLen], eax
0x14002730e  mov     [rsp+0E8h+var_B8], edi
0x140027312  cmp     esi, ecx
0x140027314  jbe     short loc_140027340
0x140027316  mov     r9d, edi; char *
0x140027319  mov     edx, 34Eh; void *
0x14002731e  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x140027325  mov     rcx, [rsp+0E8h]; this
0x14002732d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140027332  nop
0x140027333  mov     rcx, rbx; Block
0x140027336  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002733b  jmp     loc_1400271B9
0x140027340  lea     r9, [rsp+0E8h+dwDataLen]
0x140027345  mov     r8, rbx
0x140027348  mov     edx, [rsp+0E8h+pdwDataLen]
0x14002734c  lea     rcx, [rsp+0E8h+pbData]
0x140027354  call    cs:__imp_?EncodeBase64@@YAJPEBEHPEAEPEAH@Z; EncodeBase64(uchar const *,int,uchar *,int *)
0x14002735b  nop     dword ptr [rax+rax+00h]
0x140027360  mov     edi, eax
0x140027362  mov     [rsp+0E8h+var_B8], eax
0x140027366  test    eax, eax
0x140027368  jns     short loc_140027374
0x14002736a  mov     r9d, eax
0x14002736d  mov     edx, 351h
0x140027372  jmp     short loc_14002731E
0x140027374  xor     r9d, r9d; dwFlags
0x140027377  mov     r8d, [rsp+0E8h+dwDataLen]; dwDataLen
0x14002737c  mov     rdx, rbx; pbData
0x14002737f  mov     rcx, [rsp+0E8h+hHash]; hHash
0x140027384  call    cs:__imp_CryptHashData
0x14002738b  nop     dword ptr [rax+rax+00h]
0x140027390  test    eax, eax
0x140027392  jnz     short loc_1400273B8
0x140027394  call    cs:__imp_GetLastError
0x14002739b  nop     dword ptr [rax+rax+00h]
0x1400273a0  mov     edi, eax
0x1400273a2  test    eax, eax
0x1400273a4  jle     short loc_1400273AF
0x1400273a6  movzx   edi, ax
0x1400273a9  or      edi, 80070000h
0x1400273af  mov     [rsp+0E8h+var_B8], edi
  ... truncated ...
```
