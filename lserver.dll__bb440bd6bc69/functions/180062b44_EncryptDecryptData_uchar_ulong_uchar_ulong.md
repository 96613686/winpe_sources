# EncryptDecryptData(uchar *,ulong,uchar *,ulong)

- ea: `0x180062b44`
- end: `0x180062dfe`
- name: `?EncryptDecryptData@@YAKPEAEK0K@Z`
- size: `698`
- prototype: `unsigned int(unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180062e90`

## callees

- `0x180002d26`
- `0x180005665`
- `0x180062ab8`
- `0x180062adc`
- `0x180062afc`
- `0x180062b44`
- `0x18006d9dc`
- `0x18006da28`
- `0x18006dad4`
- `0x1800a0fb0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180062bfa`
- `ntdll!RtlNtStatusToDosError` at `0x180062c5f`
- `ntdll!RtlNtStatusToDosError` at `0x180062ce7`
- `ntdll!RtlNtStatusToDosError` at `0x180062bfa`
- `ntdll!RtlNtStatusToDosError` at `0x180062c5f`
- `ntdll!RtlNtStatusToDosError` at `0x180062ce7`
- `KERNEL32!LocalSize` at `0x180062d2c`
- `KERNEL32!LocalSize` at `0x180062d81`
- `KERNEL32!LocalSize` at `0x180062d2c`
- `KERNEL32!LocalSize` at `0x180062d81`
- `KERNEL32!LocalAlloc` at `0x180062c79`
- `KERNEL32!LocalAlloc` at `0x180062c79`
- `KERNEL32!LocalFree` at `0x180062d45`
- `KERNEL32!LocalFree` at `0x180062d9a`
- `KERNEL32!LocalFree` at `0x180062d45`
- `KERNEL32!LocalFree` at `0x180062d9a`
- `KERNEL32!SetLastError` at `0x180062c0a`
- `KERNEL32!SetLastError` at `0x180062d03`
- `KERNEL32!SetLastError` at `0x180062d1d`
- `KERNEL32!SetLastError` at `0x180062dcc`
- `KERNEL32!SetLastError` at `0x180062c0a`
- `KERNEL32!SetLastError` at `0x180062d03`
- `KERNEL32!SetLastError` at `0x180062d1d`
- `KERNEL32!SetLastError` at `0x180062dcc`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180062c4d`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180062c4d`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180062be8`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180062be8`
- `bcrypt!BCryptEncrypt` at `0x180062cd5`
- `bcrypt!BCryptEncrypt` at `0x180062cd5`

## pseudocode

```c
__int64 __fastcall EncryptDecryptData(unsigned __int8 *a1, unsigned int a2, unsigned __int8 *a3, unsigned int a4)
{
  SIZE_T cbOutput; // rbx
  int v8; // eax
  DWORD v9; // edi
  int v10; // eax
  ULONG v11; // ebx
  DWORD v12; // ecx
  UCHAR *v13; // rax
  UCHAR *pbOutput; // rsi
  int v15; // eax
  DWORD v16; // ecx
  ULONG pcbResult; // [rsp+50h] [rbp-29h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+58h] [rbp-21h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+60h] [rbp-19h] BYREF
  _QWORD v21[2]; // [rsp+68h] [rbp-11h] BYREF
  BCRYPT_HASH_HANDLE phHash[2]; // [rsp+78h] [rbp-1h] BYREF
  __int64 v23; // [rsp+88h] [rbp+Fh]
  UCHAR pbIV[16]; // [rsp+90h] [rbp+17h] BYREF

  cbOutput = a4;
  v23 = 0;
  v21[0] = pbIV;
  v21[1] = 16;
  *(_OWORD *)phHash = 0;
  if ( !a1 || !a2 )
  {
    v9 = 87;
    SetLastError(0x57u);
    goto LABEL_21;
  }
  RDP_MD5Init(phHash);
  RDP_MD5Update(phHash, a1, a2);
  RDP_MD5Final(phHash);
  phAlgorithm = 0;
  *(_OWORD *)pbIV = 0;
  *(_DWORD *)pbIV = phHash[1];
  pbIV[4] = BYTE4(phHash[1]);
  v8 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"RC4", 0, 0);
  if ( v8 >= 0 )
  {
    phKey = 0;
    v10 = BCryptGenerateSymmetricKey(phAlgorithm, &phKey, 0, 0, pbIV, 0x10u, 0);
    if ( v10 < 0 )
    {
      v11 = RtlNtStatusToDosError(v10);
      v12 = v11;
LABEL_14:
      SetLastError(v12);
      goto LABEL_18;
    }
    v13 = (UCHAR *)LocalAlloc(0, cbOutput);
    pbOutput = v13;
    if ( !v13 || v13 == &v13[cbOutput] )
    {
      if ( !v13 )
      {
        v11 = 14;
        v12 = 14;
        goto LABEL_14;
      }
    }
    else
    {
      memset_0(v13, 0, cbOutput);
    }
    pcbResult = 0;
    v15 = BCryptEncrypt(phKey, a3, cbOutput, 0, 0, 0, pbOutput, cbOutput, &pcbResult, 0);
    if ( v15 >= 0 )
    {
      if ( (_DWORD)cbOutput == pcbResult )
      {
        memcpy_0(a3, pbOutput, cbOutput);
        memset(pbOutput, 0, LocalSize(pbOutput));
        LocalFree(pbOutput);
        wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
        __1__unique_storage_U__resource_policy_PEAXP6AXUSecureZeroData_details_wil____E_1_Close_123_SAX0_ZU__integral_constant__K_0A__wistd__U123_PEAX_0A___T_details_wil___details_wil__QEAA_XZ(v21);
        return 0;
      }
      v11 = 1;
      v16 = 1;
    }
    else
    {
      v11 = RtlNtStatusToDosError(v15);
      v16 = v11;
    }
    SetLastError(v16);
    memset(pbOutput, 0, LocalSize(pbOutput));
    LocalFree(pbOutput);
LABEL_18:
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
    __1__unique_storage_U__resource_policy_PEAXP6AXUSecureZeroData_details_wil____E_1_Close_123_SAX0_ZU__integral_constant__K_0A__wistd__U123_PEAX_0A___T_details_wil___details_wil__QEAA_XZ(v21);
    return v11;
  }
  v9 = RtlNtStatusToDosError(v8);
  SetLastError(v9);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
LABEL_21:
  __1__unique_storage_U__resource_policy_PEAXP6AXUSecureZeroData_details_wil____E_1_Close_123_SAX0_ZU__integral_constant__K_0A__wistd__U123_PEAX_0A___T_details_wil___details_wil__QEAA_XZ(v21);
  return v9;
}

```

## disassembly

```asm
0x180062b44  push    rbp
0x180062b46  push    rbx
0x180062b47  push    rsi
0x180062b48  push    rdi
0x180062b49  push    r14
0x180062b4b  lea     rbp, [rsp-37h]
0x180062b50  sub     rsp, 0B0h
0x180062b57  mov     rax, cs:__security_cookie
0x180062b5e  xor     rax, rsp
0x180062b61  mov     [rbp+57h+var_30], rax
0x180062b65  xor     eax, eax
0x180062b67  mov     ebx, r9d
0x180062b6a  mov     [rbp+57h+var_48], rax
0x180062b6e  lea     rax, [rbp+57h+pbIV]
0x180062b72  mov     [rbp+57h+var_68], rax
0x180062b76  xorps   xmm0, xmm0
0x180062b79  mov     [rbp+57h+var_60], 10h
0x180062b81  mov     r14, r8
0x180062b84  mov     edi, edx
0x180062b86  mov     rsi, rcx
0x180062b89  movups  xmmword ptr [rbp+57h+phHash], xmm0
0x180062b8d  test    rcx, rcx
0x180062b90  jz      loc_180062DC5
0x180062b96  test    edx, edx
0x180062b98  jz      loc_180062DC5
0x180062b9e  lea     rcx, [rbp+57h+phHash]; phHash
0x180062ba2  call    RDP_MD5Init
0x180062ba7  mov     r8d, edi
0x180062baa  lea     rcx, [rbp+57h+phHash]
0x180062bae  mov     rdx, rsi
0x180062bb1  call    RDP_MD5Update
0x180062bb6  lea     rcx, [rbp+57h+phHash]
0x180062bba  call    RDP_MD5Final
0x180062bbf  mov     eax, dword ptr [rbp+57h+phHash+8]
0x180062bc2  lea     rdx, pszAlgId; "RC4"
0x180062bc9  and     [rbp+57h+phAlgorithm], 0
0x180062bce  lea     rcx, [rbp+57h+phAlgorithm]; phAlgorithm
0x180062bd2  xorps   xmm0, xmm0
0x180062bd5  xor     r9d, r9d; dwFlags
0x180062bd8  movups  xmmword ptr [rbp+57h+pbIV], xmm0
0x180062bdc  mov     dword ptr [rbp+57h+pbIV], eax
0x180062bdf  xor     r8d, r8d; pszImplementation
0x180062be2  mov     al, byte ptr [rbp+57h+phHash+0Ch]
0x180062be5  mov     [rbp+57h+pbIV+4], al
0x180062be8  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180062bef  nop     dword ptr [rax+rax+00h]
0x180062bf4  test    eax, eax
0x180062bf6  jns     short loc_180062C24
0x180062bf8  mov     ecx, eax; Status
0x180062bfa  call    cs:__imp_RtlNtStatusToDosError
0x180062c01  nop     dword ptr [rax+rax+00h]
0x180062c06  mov     ecx, eax; dwErrCode
0x180062c08  mov     edi, eax
0x180062c0a  call    cs:__imp_SetLastError
0x180062c11  nop     dword ptr [rax+rax+00h]
0x180062c16  lea     rcx, [rbp+57h+phAlgorithm]
0x180062c1a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180062c1f  jmp     loc_180062DD8
0x180062c24  and     dword ptr [rsp+0D0h+pbOutput], 0
0x180062c29  lea     rax, [rbp+57h+pbIV]
0x180062c2d  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x180062c31  lea     rdx, [rbp+57h+phKey]; phKey
0x180062c35  and     [rbp+57h+phKey], 0
0x180062c3a  xor     r9d, r9d; cbKeyObject
0x180062c3d  mov     [rsp+0D0h+cbSecret], 10h; cbIV
0x180062c45  xor     r8d, r8d; pbKeyObject
0x180062c48  mov     [rsp+0D0h+pbSecret], rax; pbIV
0x180062c4d  call    cs:__imp_BCryptGenerateSymmetricKey
0x180062c54  nop     dword ptr [rax+rax+00h]
0x180062c59  test    eax, eax
0x180062c5b  jns     short loc_180062C74
0x180062c5d  mov     ecx, eax; Status
0x180062c5f  call    cs:__imp_RtlNtStatusToDosError
0x180062c66  nop     dword ptr [rax+rax+00h]
0x180062c6b  mov     ebx, eax
0x180062c6d  mov     ecx, eax
0x180062c6f  jmp     loc_180062D03
0x180062c74  mov     rdx, rbx; uBytes
0x180062c77  xor     ecx, ecx; uFlags
0x180062c79  call    cs:__imp_LocalAlloc
0x180062c80  nop     dword ptr [rax+rax+00h]
0x180062c85  mov     rsi, rax
0x180062c88  test    rax, rax
0x180062c8b  jz      short loc_180062CF9
0x180062c8d  add     rax, rbx
0x180062c90  cmp     rsi, rax
0x180062c93  jz      short loc_180062CF9
0x180062c95  mov     r8, rbx; Size
0x180062c98  xor     edx, edx; Val
0x180062c9a  mov     rcx, rsi; void *
0x180062c9d  call    memset_0
0x180062ca2  and     [rsp+0D0h+var_88], 0
0x180062ca7  lea     rax, [rbp+57h+var_80]
0x180062cab  mov     rcx, [rbp+57h+phKey]; hKey
0x180062caf  xor     r9d, r9d; pPaddingInfo
0x180062cb2  and     [rbp+57h+var_80], 0
0x180062cb6  mov     r8d, ebx; cbInput
0x180062cb9  mov     [rsp+0D0h+pcbResult], rax; pcbResult
0x180062cbe  mov     rdx, r14; pbInput
0x180062cc1  mov     [rsp+0D0h+cbOutput], ebx; cbOutput
0x180062cc5  mov     [rsp+0D0h+pbOutput], rsi; pbOutput
0x180062cca  and     [rsp+0D0h+cbSecret], 0
0x180062ccf  and     [rsp+0D0h+pbSecret], 0
0x180062cd5  call    cs:__imp_BCryptEncrypt
0x180062cdc  nop     dword ptr [rax+rax+00h]
0x180062ce1  test    eax, eax
0x180062ce3  jns     short loc_180062D11
0x180062ce5  mov     ecx, eax; Status
0x180062ce7  call    cs:__imp_RtlNtStatusToDosError
0x180062cee  nop     dword ptr [rax+rax+00h]
0x180062cf3  mov     ebx, eax
0x180062cf5  mov     ecx, eax
0x180062cf7  jmp     short loc_180062D1D
0x180062cf9  test    rsi, rsi
0x180062cfc  jnz     short loc_180062CA2
0x180062cfe  lea     ebx, [rsi+0Eh]
0x180062d01  mov     ecx, ebx; dwErrCode
0x180062d03  call    cs:__imp_SetLastError
0x180062d0a  nop     dword ptr [rax+rax+00h]
0x180062d0f  jmp     short loc_180062D51
0x180062d11  cmp     ebx, [rbp+57h+var_80]
0x180062d14  jz      short loc_180062D70
0x180062d16  mov     ebx, 1
0x180062d1b  mov     ecx, ebx; dwErrCode
0x180062d1d  call    cs:__imp_SetLastError
0x180062d24  nop     dword ptr [rax+rax+00h]
0x180062d29  mov     rcx, rsi; hMem
0x180062d2c  call    cs:__imp_LocalSize
0x180062d33  nop     dword ptr [rax+rax+00h]
0x180062d38  mov     rcx, rax
0x180062d3b  mov     rdi, rsi
0x180062d3e  xor     eax, eax
0x180062d40  rep stosb
0x180062d42  mov     rcx, rsi; hMem
0x180062d45  call    cs:__imp_LocalFree
0x180062d4c  nop     dword ptr [rax+rax+00h]
0x180062d51  lea     rcx, [rbp+57h+phKey]
0x180062d55  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180062d5a  lea     rcx, [rbp+57h+phAlgorithm]
0x180062d5e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180062d63  lea     rcx, [rbp+57h+var_68]
0x180062d67  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXUSecureZeroData@details@wil@@@_E$1?Close@123@SAX0@ZU?$integral_constant@_K$0A@@wistd@@U123@PEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180062d6c  mov     eax, ebx
0x180062d6e  jmp     short loc_180062DE3
0x180062d70  mov     r8, rbx; Size
0x180062d73  mov     rdx, rsi; Src
0x180062d76  mov     rcx, r14; void *
0x180062d79  call    memcpy_0
0x180062d7e  mov     rcx, rsi; hMem
0x180062d81  call    cs:__imp_LocalSize
0x180062d88  nop     dword ptr [rax+rax+00h]
0x180062d8d  mov     rcx, rax
0x180062d90  mov     rdi, rsi
0x180062d93  xor     eax, eax
0x180062d95  rep stosb
0x180062d97  mov     rcx, rsi; hMem
0x180062d9a  call    cs:__imp_LocalFree
0x180062da1  nop     dword ptr [rax+rax+00h]
0x180062da6  lea     rcx, [rbp+57h+phKey]
0x180062daa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180062daf  lea     rcx, [rbp+57h+phAlgorithm]
0x180062db3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180062db8  lea     rcx, [rbp+57h+var_68]
0x180062dbc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXUSecureZeroData@details@wil@@@_E$1?Close@123@SAX0@ZU?$integral_constant@_K$0A@@wistd@@U123@PEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180062dc1  xor     eax, eax
0x180062dc3  jmp     short loc_180062DE3
0x180062dc5  mov     edi, 57h ; 'W'
0x180062dca  mov     ecx, edi; dwErrCode
0x180062dcc  call    cs:__imp_SetLastError
0x180062dd3  nop     dword ptr [rax+rax+00h]
0x180062dd8  lea     rcx, [rbp+57h+var_68]
0x180062ddc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXUSecureZeroData@details@wil@@@_E$1?Close@123@SAX0@ZU?$integral_constant@_K$0A@@wistd@@U123@PEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180062de1  mov     eax, edi
0x180062de3  mov     rcx, [rbp+57h+var_30]
0x180062de7  xor     rcx, rsp; StackCookie
0x180062dea  call    __security_check_cookie
0x180062def  add     rsp, 0B0h
0x180062df6  pop     r14
0x180062df8  pop     rdi
0x180062df9  pop     rsi
0x180062dfa  pop     rbx
0x180062dfb  pop     rbp
0x180062dfc  retn
```
