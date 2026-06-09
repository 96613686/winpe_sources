# EfsSsoObtainSmartcardCredsFromLSA

- ea: `0x180027934`
- end: `0x180027eb2`
- name: `EfsSsoObtainSmartcardCredsFromLSA`
- size: `1406`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003d348`
- `0x18003e5a4`
- `0x18003f030`

## callees

- `0x180004f86`
- `0x18000505d`
- `0x1800102f0`
- `0x180010bf0`
- `0x18001efb8`
- `0x180027934`
- `0x180063698`
- `0x1800dca3c`
- `0x1800dddf0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027a02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027a66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027ac2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027b05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027b34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027c65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027cc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027d12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027dab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027a02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027a66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027ac2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027b05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027b34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027c65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027cc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027d12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027dab`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800279f8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800279f8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800279e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800279e3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180027c5b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180027da1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180027c5b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180027da1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027ddf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027df2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027ddf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027df2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027e47`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027e70`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027e47`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027e70`
- `CRYPT32!CertCreateCertificateContext` at `0x180027cb7`
- `CRYPT32!CertCreateCertificateContext` at `0x180027cb7`
- `CRYPT32!CertFreeCertificateContext` at `0x180027e24`
- `CRYPT32!CertFreeCertificateContext` at `0x180027e37`
- `CRYPT32!CertFreeCertificateContext` at `0x180027e24`
- `CRYPT32!CertFreeCertificateContext` at `0x180027e37`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180027b2a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180027b2a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180027a5c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180027ab8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180027afb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180027a5c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180027ab8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180027afb`
- `ntdll!RtlNtStatusToDosError` at `0x180027ba9`
- `ntdll!RtlNtStatusToDosError` at `0x180027c3f`
- `ntdll!RtlNtStatusToDosError` at `0x180027ba9`
- `ntdll!RtlNtStatusToDosError` at `0x180027c3f`
- `CRYPTBASE!SystemFunction041` at `0x180027c33`
- `CRYPTBASE!SystemFunction041` at `0x180027c33`
- `RPCRT4!NdrClientCall3` at `0x180027b95`
- `RPCRT4!NdrClientCall3` at `0x180027b95`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800de61f`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800de61f`
- `EFSUTIL!EfsUtilGetCertContextFromCertHash` at `0x180027d3c`
- `EFSUTIL!EfsUtilGetCertContextFromCertHash` at `0x180027d3c`

## pseudocode

```c
__int64 __fastcall EfsSsoObtainSmartcardCredsFromLSA(_QWORD *a1, PCCERT_CONTEXT *a2)
{
  void *v3; // rsi
  PCCERT_CONTEXT CertificateContext; // r14
  void *v5; // r15
  int v6; // r12d
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  char v9; // r13
  ULONG CertContextFromCertHash; // edi
  DWORD v11; // eax
  DWORD v12; // r8d
  void *v13; // rcx
  CLIENT_CALL_RETURN v14; // rax
  void *v15; // rax
  int v16; // eax
  DWORD v17; // eax
  BYTE *v18; // rdx
  __int64 CertHashFromCertContext; // rax
  DWORD v20; // eax
  char ReturnLength; // [rsp+20h] [rbp-128h]
  void *TokenHandle; // [rsp+58h] [rbp-F0h] BYREF
  DWORD v24; // [rsp+60h] [rbp-E8h] BYREF
  DWORD cbCertEncoded; // [rsp+64h] [rbp-E4h]
  int TokenInformation; // [rsp+68h] [rbp-E0h] BYREF
  DWORD pcbData; // [rsp+6Ch] [rbp-DCh] BYREF
  BYTE *pbCertEncoded; // [rsp+70h] [rbp-D8h]
  void *Src; // [rsp+78h] [rbp-D0h]
  PCCERT_CONTEXT pCertContext; // [rsp+80h] [rbp-C8h] BYREF
  ULONG v31; // [rsp+88h] [rbp-C0h]
  HANDLE hObject; // [rsp+90h] [rbp-B8h] BYREF
  __int64 v33; // [rsp+98h] [rbp-B0h]
  _QWORD *v34; // [rsp+A0h] [rbp-A8h]
  CLIENT_CALL_RETURN v35; // [rsp+A8h] [rbp-A0h]
  _QWORD *v36; // [rsp+C8h] [rbp-80h]
  PCCERT_CONTEXT *v37; // [rsp+D0h] [rbp-78h]
  int v38; // [rsp+D8h] [rbp-70h] BYREF
  __int128 v39; // [rsp+DCh] [rbp-6Ch]
  __int128 v40; // [rsp+ECh] [rbp-5Ch]
  __int128 v41; // [rsp+FCh] [rbp-4Ch]
  int v42; // [rsp+10Ch] [rbp-3Ch]

  v34 = a1;
  v36 = a1;
  v37 = a2;
  TokenHandle = 0;
  v24 = 0;
  TokenInformation = 0;
  hObject = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  v33 = 0;
  pbCertEncoded = 0;
  cbCertEncoded = 0;
  Src = 0;
  v3 = 0;
  CertificateContext = 0;
  pCertContext = 0;
  pcbData = 0;
  v5 = 0;
  v6 = 0;
  *a2 = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    v9 = -7;
LABEL_3:
    CertContextFromCertHash = LastError;
    v11 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, LastError, 7, v9);
    ReturnLength = v9;
LABEL_4:
    v12 = v11;
LABEL_41:
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v12, 7, ReturnLength);
    goto LABEL_42;
  }
  if ( !GetTokenInformation(TokenHandle, TokenElevationType, &TokenInformation, 4u, &v24) )
  {
    v11 = GetLastError();
    CertContextFromCertHash = v11;
    ReturnLength = 7;
    goto LABEL_4;
  }
  if ( TokenInformation == 2 || TokenInformation == 1 )
  {
    v13 = TokenHandle;
  }
  else
  {
    if ( TokenInformation != 3 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( !GetTokenInformation(TokenHandle, TokenLinkedToken, &hObject, 8u, &v24) )
    {
      v11 = GetLastError();
      CertContextFromCertHash = v11;
      ReturnLength = 42;
      goto LABEL_4;
    }
    v13 = hObject;
  }
  if ( !GetTokenInformation(v13, TokenStatistics, &v38, 0x38u, &v24) )
  {
    v11 = GetLastError();
    CertContextFromCertHash = v11;
    ReturnLength = 54;
    goto LABEL_4;
  }
  v33 = *(_QWORD *)((char *)&v39 + 4);
  if ( !RevertToSelf() )
  {
    LastError = GetLastError();
    v9 = 67;
    goto LABEL_3;
  }
  CertContextFromCertHash = 0;
  v35.Simple = 0;
  v14.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x66u, 0).Pointer;
  v35.Pointer = v14.Pointer;
  if ( LODWORD(v14.Pointer) )
  {
    CertContextFromCertHash = RtlNtStatusToDosError(v14.Simple);
    v31 = CertContextFromCertHash;
  }
  v6 = 1;
  if ( !CertContextFromCertHash )
  {
    v15 = wil::details::heap_allocator::allocate(0);
    v3 = v15;
    if ( !v15 )
    {
      CertContextFromCertHash = 8;
      ReturnLength = 94;
LABEL_40:
      v12 = CertContextFromCertHash;
      goto LABEL_41;
    }
    memcpy_0(v15, Src, 0);
    v16 = SystemFunction041(v3, 0, 2u);
    if ( v16 < 0 )
    {
      v11 = RtlNtStatusToDosError(v16);
      CertContextFromCertHash = v11;
      ReturnLength = 102;
      goto LABEL_4;
    }
    if ( !SetThreadToken(0, TokenHandle) )
    {
      v17 = GetLastError();
      fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v17, 7, 111);
    }
    v6 = 0;
    v18 = pbCertEncoded;
    if ( !pbCertEncoded || !Src )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      v18 = pbCertEncoded;
    }
    CertificateContext = CertCreateCertificateContext(1u, v18, cbCertEncoded);
    if ( !CertificateContext )
    {
      v11 = GetLastError();
      CertContextFromCertHash = v11;
      ReturnLength = 120;
      goto LABEL_4;
    }
    if ( CertificateContext->cbCertEncoded != cbCertEncoded
      || memcmp_0(pbCertEncoded, CertificateContext->pbCertEncoded, cbCertEncoded) )
    {
      CertContextFromCertHash = 13;
      ReturnLength = -125;
      goto LABEL_40;
    }
    CertHashFromCertContext = GetCertHashFromCertContext(CertificateContext, &pcbData);
    v5 = (void *)CertHashFromCertContext;
    if ( !CertHashFromCertContext )
    {
      v11 = GetLastError();
      CertContextFromCertHash = v11;
      ReturnLength = -113;
      goto LABEL_4;
    }
    CertContextFromCertHash = EfsUtilGetCertContextFromCertHash(
                                CertHashFromCertContext,
                                pcbData,
                                0x10000,
                                &pCertContext);
    if ( !CertContextFromCertHash )
    {
      *a2 = pCertContext;
      pCertContext = 0;
      *v34 = v3;
      v3 = 0;
    }
  }
LABEL_42:
  if ( v6 && !SetThreadToken(0, TokenHandle) )
  {
    v20 = GetLastError();
    fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v20, 7, 164);
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( hObject )
    CloseHandle(hObject);
  if ( v3 )
    EfsFreeHeap(v3);
  if ( CertificateContext )
    CertFreeCertificateContext(CertificateContext);
  if ( pCertContext )
    CertFreeCertificateContext(pCertContext);
  if ( pbCertEncoded )
    LocalFree(pbCertEncoded);
  if ( Src )
    LocalFree(Src);
  if ( v5 )
    EfsFreeHeap(v5);
  return CertContextFromCertHash;
}

```

## disassembly

```asm
0x180027934  mov     r11, rsp
0x180027937  mov     [r11+18h], rbx
0x18002793b  mov     [r11+20h], rsi
0x18002793f  push    rdi
0x180027940  push    r12
0x180027942  push    r13
0x180027944  push    r14
0x180027946  push    r15
0x180027948  sub     rsp, 120h
0x18002794f  mov     rax, cs:__security_cookie
0x180027956  xor     rax, rsp
0x180027959  mov     [rsp+148h+var_38], rax
0x180027961  mov     r13, rdx
0x180027964  mov     rax, rcx
0x180027967  mov     [rsp+148h+var_A8], rcx
0x18002796f  mov     [rsp+148h+var_80], rcx
0x180027977  mov     [rsp+148h+var_78], rdx
0x18002797f  xor     ebx, ebx
0x180027981  mov     [rsp+148h+TokenHandle], rbx
0x180027986  mov     [rsp+148h+var_E8], ebx
0x18002798a  mov     [rsp+148h+TokenInformation], ebx
0x18002798e  mov     [r11-0B8h], rbx
0x180027995  mov     [r11-70h], ebx
0x180027999  xorps   xmm0, xmm0
0x18002799c  xor     eax, eax
0x18002799e  movups  xmmword ptr [r11-6Ch], xmm0
0x1800279a3  movups  xmmword ptr [r11-5Ch], xmm0
0x1800279a8  movups  xmmword ptr [r11-4Ch], xmm0
0x1800279ad  mov     [r11-3Ch], eax
0x1800279b1  mov     [r11-0B0h], rbx
0x1800279b8  mov     [rsp+148h+pbCertEncoded], rbx
0x1800279bd  mov     [rsp+148h+cbCertEncoded], ebx
0x1800279c1  mov     [rsp+148h+Src], rbx
0x1800279c6  mov     dword ptr [rsp+148h+Size], ebx
0x1800279ca  mov     esi, ebx
0x1800279cc  mov     r14d, ebx
0x1800279cf  mov     [r11-0C8h], rbx
0x1800279d6  mov     [rsp+148h+pcbData], ebx
0x1800279da  mov     r15d, ebx
0x1800279dd  mov     r12d, ebx
0x1800279e0  mov     [rdx], rbx
0x1800279e3  call    cs:__imp_GetCurrentThread
0x1800279e9  mov     rcx, rax; ThreadHandle
0x1800279ec  lea     r9, [rsp+148h+TokenHandle]; TokenHandle
0x1800279f1  lea     edx, [rbx+0Ch]; DesiredAccess
0x1800279f4  lea     r8d, [rbx+1]; OpenAsSelf
0x1800279f8  call    cs:__imp_OpenThreadToken
0x1800279fe  test    eax, eax
0x180027a00  jnz     short loc_180027A3E
0x180027a02  call    cs:__imp_GetLastError
0x180027a08  mov     r13d, 2F9h
0x180027a0e  mov     edi, eax
0x180027a10  mov     dword ptr [rsp+148h+ReturnLength], r13d
0x180027a15  mov     r9d, 7
0x180027a1b  mov     r8d, eax
0x180027a1e  lea     rdx, EFS_API_ERROR
0x180027a25  mov     rcx, cs:g_hPublisher
0x180027a2c  call    fnEfsLogTrace1
0x180027a31  mov     dword ptr [rsp+148h+ReturnLength], r13d
0x180027a36  mov     r8d, eax
0x180027a39  jmp     loc_180027D7C
0x180027a3e  lea     rax, [rsp+148h+var_E8]
0x180027a43  mov     [rsp+148h+ReturnLength], rax; ReturnLength
0x180027a48  mov     r9d, 4; TokenInformationLength
0x180027a4e  lea     r8, [rsp+148h+TokenInformation]; TokenInformation
0x180027a53  lea     edx, [r9+0Eh]; TokenInformationClass
0x180027a57  mov     rcx, [rsp+148h+TokenHandle]; TokenHandle
0x180027a5c  call    cs:__imp_GetTokenInformation
0x180027a62  test    eax, eax
0x180027a64  jnz     short loc_180027A78
0x180027a66  call    cs:__imp_GetLastError
0x180027a6c  mov     edi, eax
0x180027a6e  mov     dword ptr [rsp+148h+ReturnLength], 307h
0x180027a76  jmp     short loc_180027A36
0x180027a78  mov     eax, [rsp+148h+TokenInformation]
0x180027a7c  cmp     eax, 2
0x180027a7f  jz      short loc_180027A86
0x180027a81  cmp     eax, 1
0x180027a84  jnz     short loc_180027A8D
0x180027a86  mov     rcx, [rsp+148h+TokenHandle]
0x180027a8b  jmp     short loc_180027ADF
0x180027a8d  cmp     eax, 3
0x180027a90  jz      short loc_180027A97
0x180027a92  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "ElevationType == TokenElevationTypeLimited")
0x180027a97  lea     rax, [rsp+148h+var_E8]
0x180027a9c  mov     [rsp+148h+ReturnLength], rax; ReturnLength
0x180027aa1  mov     r9d, 8; TokenInformationLength
0x180027aa7  lea     r8, [rsp+148h+hObject]; TokenInformation
0x180027aaf  lea     edx, [r9+0Bh]; TokenInformationClass
0x180027ab3  mov     rcx, [rsp+148h+TokenHandle]; TokenHandle
0x180027ab8  call    cs:__imp_GetTokenInformation
0x180027abe  test    eax, eax
0x180027ac0  jnz     short loc_180027AD7
0x180027ac2  call    cs:__imp_GetLastError
0x180027ac8  mov     edi, eax
0x180027aca  mov     dword ptr [rsp+148h+ReturnLength], 32Ah
0x180027ad2  jmp     loc_180027A36
0x180027ad7  mov     rcx, [rsp+148h+hObject]; TokenHandle
0x180027adf  lea     rax, [rsp+148h+var_E8]
0x180027ae4  mov     [rsp+148h+ReturnLength], rax; ReturnLength
0x180027ae9  mov     r9d, 38h ; '8'; TokenInformationLength
0x180027aef  lea     r8, [rsp+148h+var_70]; TokenInformation
0x180027af7  lea     edx, [r9-2Eh]; TokenInformationClass
0x180027afb  call    cs:__imp_GetTokenInformation
0x180027b01  test    eax, eax
0x180027b03  jnz     short loc_180027B1A
0x180027b05  call    cs:__imp_GetLastError
0x180027b0b  mov     edi, eax
0x180027b0d  mov     dword ptr [rsp+148h+ReturnLength], 336h
0x180027b15  jmp     loc_180027A36
0x180027b1a  mov     rax, [rsp+148h+var_68]
0x180027b22  mov     [rsp+148h+var_B0], rax
0x180027b2a  call    cs:__imp_RevertToSelf
0x180027b30  test    eax, eax
0x180027b32  jnz     short loc_180027B45
0x180027b34  call    cs:__imp_GetLastError
0x180027b3a  mov     r13d, 343h
0x180027b40  jmp     loc_180027A0E
0x180027b45  mov     edi, ebx
0x180027b47  mov     [rsp+148h+var_A0], rbx
0x180027b4f  lea     rax, [rsp+148h+Size]
0x180027b54  mov     [rsp+148h+var_108], rax
0x180027b59  lea     rax, [rsp+148h+Src]
0x180027b5e  mov     [rsp+148h+var_110], rax
0x180027b63  lea     rax, [rsp+148h+cbCertEncoded]
0x180027b68  mov     [rsp+148h+var_118], rax
0x180027b6d  lea     rax, [rsp+148h+pbCertEncoded]
0x180027b72  mov     [rsp+148h+var_120], rax
0x180027b77  lea     rax, [rsp+148h+var_B0]
0x180027b7f  mov     [rsp+148h+ReturnLength], rax
0x180027b84  xor     r9d, r9d
0x180027b87  xor     r8d, r8d; pReturnValue
0x180027b8a  lea     edx, [r9+66h]; nProcNum
0x180027b8e  lea     rcx, pProxyInfo; pProxyInfo
0x180027b95  call    cs:__imp_NdrClientCall3
0x180027b9b  mov     [rsp+148h+var_A0], rax
0x180027ba3  test    eax, eax
0x180027ba5  jz      short loc_180027BB8
0x180027ba7  mov     ecx, eax; Status
0x180027ba9  call    cs:__imp_RtlNtStatusToDosError
0x180027baf  mov     edi, eax
0x180027bb1  mov     [rsp+148h+var_C0], eax
0x180027bb8  jmp     short loc_180027BE5
0x180027bba  mov     edi, eax
0x180027bbc  mov     [rsp+148h+var_C0], eax
0x180027bc3  xor     ebx, ebx
0x180027bc5  mov     esi, ebx
0x180027bc7  mov     r14d, ebx
0x180027bca  mov     r15d, ebx
0x180027bcd  mov     rax, [rsp+148h+var_80]
0x180027bd5  mov     [rsp+148h+var_A8], rax
0x180027bdd  mov     r13, [rsp+148h+var_78]
0x180027be5  mov     r12d, 1
0x180027beb  test    edi, edi
0x180027bed  jnz     loc_180027D95
0x180027bf3  mov     ecx, dword ptr [rsp+148h+Size]; unsigned __int64
0x180027bf7  call    ?allocate@heap_allocator@details@wil@@SAPEAX_K@Z; wil::details::heap_allocator::allocate(unsigned __int64)
0x180027bfc  mov     rsi, rax
0x180027bff  test    rax, rax
0x180027c02  jnz     short loc_180027C14
0x180027c04  lea     edi, [rax+8]
0x180027c07  mov     dword ptr [rsp+148h+ReturnLength], 35Eh
0x180027c0f  jmp     loc_180027D79
0x180027c14  mov     r8d, dword ptr [rsp+148h+Size]; Size
0x180027c19  mov     rdx, [rsp+148h+Src]; Src
0x180027c1e  mov     rcx, rsi; void *
0x180027c21  call    memcpy_0
0x180027c26  mov     r8d, 2; OptionFlags
0x180027c2c  mov     edx, dword ptr [rsp+148h+Size]; MemorySize
0x180027c30  mov     rcx, rsi; Memory
0x180027c33  call    cs:__imp_SystemFunction041
0x180027c39  test    eax, eax
0x180027c3b  jns     short loc_180027C54
0x180027c3d  mov     ecx, eax; Status
0x180027c3f  call    cs:__imp_RtlNtStatusToDosError
0x180027c45  mov     edi, eax
0x180027c47  mov     dword ptr [rsp+148h+ReturnLength], 366h
0x180027c4f  jmp     loc_180027A36
0x180027c54  mov     rdx, [rsp+148h+TokenHandle]; Token
0x180027c59  xor     ecx, ecx; Thread
0x180027c5b  call    cs:__imp_SetThreadToken
0x180027c61  test    eax, eax
0x180027c63  jnz     short loc_180027C8F
0x180027c65  call    cs:__imp_GetLastError
0x180027c6b  mov     dword ptr [rsp+148h+ReturnLength], 36Fh
0x180027c73  mov     r9d, 7
0x180027c79  mov     r8d, eax
0x180027c7c  lea     rdx, EFS_API_ERROR
0x180027c83  mov     rcx, cs:g_hPublisher
0x180027c8a  call    fnEfsLogTrace1
0x180027c8f  mov     r12d, ebx
0x180027c92  mov     rdx, [rsp+148h+pbCertEncoded]
0x180027c97  test    rdx, rdx
0x180027c9a  jz      short loc_180027CA3
0x180027c9c  cmp     [rsp+148h+Src], rbx
0x180027ca1  jnz     short loc_180027CAD
0x180027ca3  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "pbEncodedCert != NULL && pbEncryptedPIN != NULL")
0x180027ca8  mov     rdx, [rsp+148h+pbCertEncoded]; pbCertEncoded
0x180027cad  mov     r8d, [rsp+148h+cbCertEncoded]; cbCertEncoded
0x180027cb2  mov     ecx, 1; dwCertEncodingType
0x180027cb7  call    cs:__imp_CertCreateCertificateContext
0x180027cbd  mov     r14, rax
0x180027cc0  test    rax, rax
0x180027cc3  jnz     short loc_180027CDA
0x180027cc5  call    cs:__imp_GetLastError
0x180027ccb  mov     edi, eax
0x180027ccd  mov     dword ptr [rsp+148h+ReturnLength], 378h
0x180027cd5  jmp     loc_180027A36
0x180027cda  mov     eax, [rsp+148h+cbCertEncoded]
0x180027cde  cmp     [r14+10h], eax
0x180027ce2  jnz     loc_180027D6C
0x180027ce8  mov     r8d, eax; Size
0x180027ceb  mov     rdx, [r14+8]; Buf2
0x180027cef  mov     rcx, [rsp+148h+pbCertEncoded]; Buf1
0x180027cf4  call    memcmp_0
0x180027cf9  test    eax, eax
0x180027cfb  jnz     short loc_180027D6C
0x180027cfd  lea     rdx, [rsp+148h+pcbData]; pcbData
0x180027d02  mov     rcx, r14; pCertContext
0x180027d05  call    GetCertHashFromCertContext
0x180027d0a  mov     r15, rax
0x180027d0d  test    rax, rax
0x180027d10  jnz     short loc_180027D27
0x180027d12  call    cs:__imp_GetLastError
0x180027d18  mov     edi, eax
0x180027d1a  mov     dword ptr [rsp+148h+ReturnLength], 38Fh
0x180027d22  jmp     loc_180027A36
0x180027d27  lea     r9, [rsp+148h+pCertContext]
0x180027d2f  mov     r8d, 10000h
0x180027d35  mov     edx, [rsp+148h+pcbData]
0x180027d39  mov     rcx, rax
0x180027d3c  call    cs:__imp_EfsUtilGetCertContextFromCertHash
0x180027d42  mov     edi, eax
0x180027d44  test    eax, eax
0x180027d46  jnz     short loc_180027D95
0x180027d48  mov     rax, [rsp+148h+pCertContext]
0x180027d50  mov     [r13+0], rax
0x180027d54  mov     [rsp+148h+pCertContext], rbx
0x180027d5c  mov     rax, [rsp+148h+var_A8]
0x180027d64  mov     [rax], rsi
0x180027d67  mov     rsi, rbx
0x180027d6a  jmp     short loc_180027D95
0x180027d6c  mov     edi, 0Dh
0x180027d71  mov     dword ptr [rsp+148h+ReturnLength], 383h
0x180027d79  mov     r8d, edi
0x180027d7c  mov     r9d, 7
0x180027d82  lea     rdx, EFS_TRACE_ERROR
0x180027d89  mov     rcx, cs:g_hPublisher
0x180027d90  call    fnEfsLogTrace1
0x180027d95  test    r12d, r12d
0x180027d98  jz      short loc_180027DD5
0x180027d9a  mov     rdx, [rsp+148h+TokenHandle]; Token
0x180027d9f  xor     ecx, ecx; Thread
0x180027da1  call    cs:__imp_SetThreadToken
0x180027da7  test    eax, eax
0x180027da9  jnz     short loc_180027DD5
0x180027dab  call    cs:__imp_GetLastError
0x180027db1  mov     dword ptr [rsp+148h+ReturnLength], 3A4h
0x180027db9  mov     r9d, 7
0x180027dbf  mov     r8d, eax
0x180027dc2  lea     rdx, EFS_API_ERROR
0x180027dc9  mov     rcx, cs:g_hPublisher
0x180027dd0  call    fnEfsLogTrace1
0x180027dd5  mov     rcx, [rsp+148h+TokenHandle]; hObject
0x180027dda  test    rcx, rcx
0x180027ddd  jz      short loc_180027DE5
0x180027ddf  call    cs:__imp_CloseHandle
0x180027de5  mov     rcx, [rsp+148h+hObject]; hObject
0x180027ded  test    rcx, rcx
0x180027df0  jz      short loc_180027DF8
0x180027df2  call    cs:__imp_CloseHandle
0x180027df8  test    rsi, rsi
0x180027dfb  jz      short loc_180027E1C
0x180027dfd  mov     ecx, dword ptr [rsp+148h+Size]
0x180027e01  mov     rax, rsi
0x180027e04  test    rcx, rcx
0x180027e07  jz      short loc_180027E14
0x180027e09  mov     [rax], bl
0x180027e0b  inc     rax
0x180027e0e  sub     rcx, 1
0x180027e12  jnz     short loc_180027E09
0x180027e14  mov     rcx, rsi; lpMem
0x180027e17  call    EfsFreeHeap
0x180027e1c  test    r14, r14
0x180027e1f  jz      short loc_180027E2A
0x180027e21  mov     rcx, r14; pCertContext
0x180027e24  call    cs:__imp_CertFreeCertificateContext
0x180027e2a  mov     rcx, [rsp+148h+pCertContext]; pCertContext
0x180027e32  test    rcx, rcx
0x180027e35  jz      short loc_180027E3D
0x180027e37  call    cs:__imp_CertFreeCertificateContext
0x180027e3d  mov     rcx, [rsp+148h+pbCertEncoded]; hMem
0x180027e42  test    rcx, rcx
0x180027e45  jz      short loc_180027E4D
0x180027e47  call    cs:__imp_LocalFree
0x180027e4d  mov     rcx, [rsp+148h+Src]
0x180027e52  test    rcx, rcx
0x180027e55  jz      short loc_180027E76
0x180027e57  mov     eax, dword ptr [rsp+148h+Size]
0x180027e5b  test    rax, rax
  ... truncated ...
```
