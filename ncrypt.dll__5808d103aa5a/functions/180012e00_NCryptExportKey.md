# NCryptExportKey

- ea: `0x180012e00`
- end: `0x1800130b0`
- name: `NCryptExportKey`
- size: `688`
- prototype: `SECURITY_STATUS __stdcall(NCRYPT_KEY_HANDLE hKey, NCRYPT_KEY_HANDLE hExportKey, LPCWSTR pszBlobType, NCryptBufferDesc *pParameterList, PBYTE pbOutput, DWORD cbOutput, DWORD *pcbResult, DWORD dwFlags)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x18001bbe8`

## callees

- `0x18000a650`
- `0x18000c8e0`
- `0x18000d02c`
- `0x18000e120`
- `0x180010684`
- `0x180012e00`
- `0x1800130c0`
- `0x1800159ec`
- `0x180016878`
- `0x180020010`

## string_xrefs

- `0x180012f36`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x180012ff9`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x180013079`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`

## pseudocode

```c
SECURITY_STATUS __stdcall NCryptExportKey(
        NCRYPT_KEY_HANDLE hKey,
        NCRYPT_KEY_HANDLE hExportKey,
        LPCWSTR pszBlobType,
        NCryptBufferDesc *pParameterList,
        PBYTE pbOutput,
        DWORD cbOutput,
        DWORD *pcbResult,
        DWORD dwFlags)
{
  NCryptBufferDesc *v8; // rbx
  PVOID *v12; // rcx
  _QWORD *v13; // rsi
  __int64 v14; // rbp
  __int64 v15; // r8
  unsigned int v16; // eax
  unsigned int v17; // ebx
  __int64 v19; // r9
  __int64 v20; // rcx
  int v21; // r9d
  __int64 v22; // [rsp+A0h] [rbp+18h]

  v8 = pParameterList;
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_PPSD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      hExportKey,
      (_DWORD)pszBlobType,
      hKey,
      hExportKey,
      (__int64)pszBlobType,
      dwFlags);
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !pszBlobType )
  {
    v17 = -2146893785;
    if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 )
      WPP_SF_sDsd(
        (unsigned int)v12[2],
        hExportKey,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
        (unsigned int)"Status",
        39,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
        67);
    return NormalizeNteStatus(
             v17,
             (NCRYPT_KEY_HANDLE *)hExportKey,
             (NCryptKeyName **)pszBlobType,
             pParameterList,
             pbOutput,
             cbOutput,
             pcbResult,
             dwFlags);
  }
  v13 = (_QWORD *)ValidateClientKeyHandle(hKey);
  if ( !v13 )
  {
    v19 = 3404;
    goto LABEL_22;
  }
  v14 = 0;
  if ( hExportKey )
  {
    v14 = ValidateClientKeyHandle(hExportKey);
    if ( !v14 )
    {
      v19 = 3415;
LABEL_22:
      v17 = -2146893786;
      v20 = 2148073510LL;
LABEL_24:
      DebugTraceError(v20, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c", v19);
      return NormalizeNteStatus(
               v17,
               (NCRYPT_KEY_HANDLE *)hExportKey,
               (NCryptKeyName **)pszBlobType,
               pParameterList,
               pbOutput,
               cbOutput,
               pcbResult,
               dwFlags);
    }
  }
  v22 = (unsigned int)Feature_PKCS11_NCryptExportKey__private_featureState;
  if ( (Feature_PKCS11_NCryptExportKey__private_featureState & 0x10) == 0 )
  {
    LODWORD(v22) = Feature_PKCS11_NCryptExportKey__private_featureState | 1;
    wil_details_FeatureReporting_ReportUsageToService(Feature_PKCS11_NCryptExportKey__private_descriptor, v22, 3);
    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(
      v22,
      3,
      Feature_PKCS11_NCryptExportKey__private_descriptor);
  }
  while ( 1 )
  {
    v15 = hExportKey ? *(_QWORD *)(v14 + 16) : 0LL;
    v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, LPCWSTR, NCryptBufferDesc *, PBYTE, DWORD, DWORD *, DWORD))(v13[1] + 168LL))(
            *(_QWORD *)(v13[1] + 272LL),
            v13[2],
            v15,
            pszBlobType,
            v8,
            pbOutput,
            cbOutput,
            pcbResult,
            dwFlags);
    v17 = v16;
    if ( v16 != -2146893778 )
      break;
    if ( (dwFlags & 0x40) != 0 )
    {
      v17 = -2146893790;
      v19 = 3453;
      v20 = 2148073506LL;
      goto LABEL_24;
    }
    v17 = (*(__int64 (__fastcall **)(_QWORD, NCRYPT_KEY_HANDLE, const wchar_t *, _QWORD))(v13[1] + 192LL))(
            *(_QWORD *)(v13[1] + 272LL),
            hKey,
            L"NCryptExportKey",
            0);
    if ( v17 )
      goto LABEL_27;
    v8 = pParameterList;
  }
  if ( !v16 )
    return NormalizeNteStatus(
             v17,
             (NCRYPT_KEY_HANDLE *)hExportKey,
             (NCryptKeyName **)pszBlobType,
             pParameterList,
             pbOutput,
             cbOutput,
             pcbResult,
             dwFlags);
LABEL_27:
  DebugTraceError(v17, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c", 3471);
  EtwLogNCryptOperationFailed(12, *(_QWORD *)(v13[1] + 280LL), v13[3], v21, v17);
  return NormalizeNteStatus(
           v17,
           (NCRYPT_KEY_HANDLE *)hExportKey,
           (NCryptKeyName **)pszBlobType,
           pParameterList,
           pbOutput,
           cbOutput,
           pcbResult,
           dwFlags);
}

```

## disassembly

```asm
0x180012e00  mov     [rsp+arg_0], rbx
0x180012e05  mov     [rsp+arg_18], r9
0x180012e0a  push    rbp
0x180012e0b  push    rsi
0x180012e0c  push    rdi
0x180012e0d  push    r12
0x180012e0f  push    r13
0x180012e11  push    r14
0x180012e13  push    r15
0x180012e15  sub     rsp, 50h
0x180012e19  mov     rbx, r9
0x180012e1c  mov     r14, r8
0x180012e1f  mov     rdi, rdx
0x180012e22  mov     r15, rcx
0x180012e25  mov     rcx, cs:WPP_GLOBAL_Control
0x180012e2c  lea     rsi, WPP_GLOBAL_Control
0x180012e33  mov     r12d, [rsp+88h+dwFlags]
0x180012e3b  cmp     rcx, rsi
0x180012e3e  jz      short loc_180012E4A
0x180012e40  test    byte ptr [rcx+1Ch], 4
0x180012e44  jnz     loc_180012F60
0x180012e4a  test    r14, r14
0x180012e4d  jz      loc_180012F22
0x180012e53  mov     rcx, r15
0x180012e56  call    ValidateClientKeyHandle
0x180012e5b  mov     rsi, rax
0x180012e5e  test    rax, rax
0x180012e61  jz      loc_180012FC8
0x180012e67  xor     ebp, ebp
0x180012e69  test    rdi, rdi
0x180012e6c  jnz     loc_18001300A
0x180012e72  mov     ecx, cs:Feature_PKCS11_NCryptExportKey__private_featureState
0x180012e78  mov     [rsp+88h+arg_10], 0
0x180012e84  mov     dword ptr [rsp+88h+arg_10], ecx
0x180012e8b  test    cl, 10h
0x180012e8e  jz      loc_180013020
0x180012e94  mov     r13, [rsp+88h+pcbResult]
0x180012e9c  test    rdi, rdi
0x180012e9f  jz      short loc_180012F1D
0x180012ea1  mov     r8, [rbp+10h]
0x180012ea5  mov     rcx, [rsi+8]
0x180012ea9  mov     r9, r14
0x180012eac  mov     edx, [rsp+88h+cbOutput]
0x180012eb3  mov     [rsp+88h+var_48], r12d
0x180012eb8  mov     [rsp+88h+var_50], r13
0x180012ebd  mov     rax, [rcx+0A8h]
0x180012ec4  mov     rcx, [rcx+110h]
0x180012ecb  mov     [rsp+88h+var_58], edx
0x180012ecf  mov     rdx, [rsp+88h+pbOutput]
0x180012ed7  mov     [rsp+88h+var_60], rdx
0x180012edc  mov     rdx, [rsi+10h]
0x180012ee0  mov     [rsp+88h+var_68], rbx
0x180012ee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012eea  mov     ebx, eax
0x180012eec  cmp     eax, 8009002Eh
0x180012ef1  jz      loc_180012F87
0x180012ef7  test    eax, eax
0x180012ef9  jnz     loc_180013073
0x180012eff  mov     ecx, ebx
0x180012f01  mov     rbx, [rsp+88h+arg_0]
0x180012f09  add     rsp, 50h
0x180012f0d  pop     r15
0x180012f0f  pop     r14
0x180012f11  pop     r13
0x180012f13  pop     r12
0x180012f15  pop     rdi
0x180012f16  pop     rsi
0x180012f17  pop     rbp
0x180012f18  jmp     NormalizeNteStatus
0x180012f1d  xor     r8d, r8d
0x180012f20  jmp     short loc_180012EA5
0x180012f22  mov     ebx, 80090027h
0x180012f27  cmp     rcx, rsi
0x180012f2a  jz      short loc_180012EFF
0x180012f2c  test    byte ptr [rcx+1Ch], 1
0x180012f30  jz      short loc_180012EFF
0x180012f32  mov     rcx, [rcx+10h]
0x180012f36  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180012f3d  mov     [rsp+88h+var_58], 0D43h
0x180012f45  lea     r9, aStatus; "Status"
0x180012f4c  mov     [rsp+88h+var_60], r8
0x180012f51  mov     dword ptr [rsp+88h+var_68], 80090027h
0x180012f59  call    WPP_SF_sDsd
0x180012f5e  jmp     short loc_180012EFF
0x180012f60  mov     rcx, [rcx+10h]
0x180012f64  mov     r9, r15
0x180012f67  mov     [rsp+88h+var_58], r12d
0x180012f6c  mov     [rsp+88h+var_60], r14
0x180012f71  mov     [rsp+88h+var_68], rdi
0x180012f76  call    WPP_SF_PPSD
0x180012f7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180012f82  jmp     loc_180012E4A
0x180012f87  test    r12b, 40h
0x180012f8b  jnz     short loc_180012FE2
0x180012f8d  mov     rcx, [rsi+8]
0x180012f91  lea     r8, aNcryptexportke_0; "NCryptExportKey"
0x180012f98  xor     r9d, r9d
0x180012f9b  mov     rdx, r15
0x180012f9e  mov     rax, [rcx+0C0h]
0x180012fa5  mov     rcx, [rcx+110h]
0x180012fac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012fb1  mov     ebx, eax
0x180012fb3  test    eax, eax
0x180012fb5  jnz     loc_180013073
0x180012fbb  mov     rbx, [rsp+88h+arg_18]
0x180012fc3  jmp     loc_180012E9C
0x180012fc8  mov     r9d, 0D4Ch
0x180012fce  jmp     short loc_180012FD6
0x180012fd0  mov     r9d, 0D57h
0x180012fd6  mov     ebx, 80090026h
0x180012fdb  mov     ecx, 80090026h
0x180012fe0  jmp     short loc_180012FF2
0x180012fe2  mov     ebx, 80090022h
0x180012fe7  mov     r9d, 0D7Dh
0x180012fed  mov     ecx, 80090022h
0x180012ff2  lea     rdx, aStatus; "Status"
0x180012ff9  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180013000  call    DebugTraceError
0x180013005  jmp     loc_180012EFF
0x18001300a  mov     rcx, rdi
0x18001300d  call    ValidateClientKeyHandle
0x180013012  mov     rbp, rax
0x180013015  test    rax, rax
0x180013018  jnz     loc_180012E72
0x18001301e  jmp     short loc_180012FD0
0x180013020  mov     rax, [rsp+88h+arg_10]
0x180013028  or      ecx, 1
0x18001302b  mov     [rsp+88h+arg_10], rax
0x180013033  mov     r13d, 3
0x180013039  mov     dword ptr [rsp+88h+arg_10], ecx
0x180013040  mov     r8d, r13d
0x180013043  mov     rdx, [rsp+88h+arg_10]
0x18001304b  lea     rcx, Feature_PKCS11_NCryptExportKey__private_descriptor
0x180013052  call    wil_details_FeatureReporting_ReportUsageToService
0x180013057  mov     rcx, [rsp+88h+arg_10]
0x18001305f  lea     r8, Feature_PKCS11_NCryptExportKey__private_descriptor
0x180013066  mov     edx, r13d
0x180013069  call    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath
0x18001306e  jmp     loc_180012E94
0x180013073  mov     r9d, 0D8Fh
0x180013079  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180013080  lea     rdx, aStatus; "Status"
0x180013087  mov     ecx, ebx
0x180013089  call    DebugTraceError
0x18001308e  mov     rdx, [rsi+8]
0x180013092  mov     ecx, 0Ch
0x180013097  mov     r8, [rsi+18h]
0x18001309b  mov     dword ptr [rsp+88h+var_68], ebx
0x18001309f  mov     rdx, [rdx+118h]
0x1800130a6  call    EtwLogNCryptOperationFailed
0x1800130ab  jmp     loc_180012EFF
```
