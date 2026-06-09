# EfspAddCertToCertStore

- ea: `0x1800265c0`
- end: `0x180026884`
- name: `EfspAddCertToCertStore`
- size: `708`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180025cd0`

## callees

- `0x180010bf0`
- `0x1800265c0`
- `0x180063698`
- `0x1800dca3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002666e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800266aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800267af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002666e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800266aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800267af`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18002675d`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18002675d`
- `CRYPT32!CertOpenStore` at `0x18002669c`
- `CRYPT32!CertOpenStore` at `0x18002669c`
- `CRYPT32!CertFindCertificateInStore` at `0x180026711`
- `CRYPT32!CertFindCertificateInStore` at `0x180026711`
- `CRYPT32!CertCloseStore` at `0x1800267f3`
- `CRYPT32!CertCloseStore` at `0x1800267f3`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x18002676b`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x18002676b`
- `CRYPT32!CertAddEncodedCertificateToStore` at `0x1800267a5`
- `CRYPT32!CertAddEncodedCertificateToStore` at `0x1800267a5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180026664`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180026664`
- `ntdll!NtClose` at `0x180026863`
- `ntdll!NtClose` at `0x180026863`
- `ntdll!NtSetInformationThread` at `0x180026813`
- `ntdll!NtSetInformationThread` at `0x180026813`
- `ntdll!NtOpenThreadToken` at `0x18002661a`
- `ntdll!NtOpenThreadToken` at `0x18002661a`
- `ntdll!RtlNtStatusToDosError` at `0x18002664a`
- `ntdll!RtlNtStatusToDosError` at `0x180026852`
- `ntdll!RtlNtStatusToDosError` at `0x18002664a`
- `ntdll!RtlNtStatusToDosError` at `0x180026852`
- `EFSUTIL!EfsUtilGetCertNameFromCertContext` at `0x1800266cf`
- `EFSUTIL!EfsUtilGetCertNameFromCertContext` at `0x180026726`
- `EFSUTIL!EfsUtilGetCertNameFromCertContext` at `0x1800266cf`
- `EFSUTIL!EfsUtilGetCertNameFromCertContext` at `0x180026726`

## pseudocode

```c
__int64 __fastcall EfspAddCertToCertStore(__int64 a1, const void *a2, _DWORD *a3)
{
  HCERTSTORE v3; // rsi
  int v7; // r15d
  NTSTATUS v8; // eax
  NTSTATUS v9; // ebx
  ULONG LastError; // eax
  __int64 *v11; // rdx
  ULONG CertNameFromCertContext; // eax
  ULONG v13; // ebx
  const CERT_CONTEXT *pPrevCertContext; // rdi
  PCCERT_CONTEXT CertificateInStore; // rax
  void *v16; // rcx
  unsigned __int16 *v17; // rdx
  int v18; // eax
  int v19; // r8d
  const CERT_CONTEXT *v20; // rax
  __int64 v21; // rcx
  int v22; // edi
  int v23; // ecx
  char pvPara; // [rsp+20h] [rbp-30h]
  void *TokenHandle; // [rsp+30h] [rbp-20h] BYREF
  const char *v27; // [rsp+38h] [rbp-18h] BYREF
  __int128 pvFindPara; // [rsp+40h] [rbp-10h] BYREF
  LPVOID lpMem; // [rsp+90h] [rbp+40h] BYREF
  LPVOID v30; // [rsp+98h] [rbp+48h] BYREF

  v3 = 0;
  TokenHandle = 0;
  *a3 = 0;
  v30 = 0;
  lpMem = 0;
  v27 = "1.3.6.1.4.1.311.10.3.4";
  v7 = 0;
  pvFindPara = 0;
  v8 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xCu, 1u, &TokenHandle);
  v9 = v8;
  if ( v8 < 0 )
  {
    fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v8, 9, 116);
    LastError = RtlNtStatusToDosError(v9);
    v11 = EFS_TRACE_ERROR;
    pvPara = 117;
LABEL_23:
    v13 = LastError;
    fnEfsLogTrace1(g_hPublisher, (_DWORD)v11, LastError, 9, pvPara);
    goto LABEL_24;
  }
  if ( !RevertToSelf() )
  {
    LastError = GetLastError();
    pvPara = 123;
LABEL_22:
    v11 = (__int64 *)&EFS_API_ERROR;
    goto LABEL_23;
  }
  v7 = 1;
  v3 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x21000u, a2);
  if ( !v3 )
  {
    LastError = GetLastError();
    pvPara = -117;
    goto LABEL_22;
  }
  LODWORD(pvFindPara) = 1;
  *((_QWORD *)&pvFindPara + 1) = &v27;
  CertNameFromCertContext = EfsUtilGetCertNameFromCertContext(a1, &v30);
  v13 = CertNameFromCertContext;
  if ( !v30 )
  {
    fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, CertNameFromCertContext, 9, 149);
    goto LABEL_24;
  }
  pPrevCertContext = 0;
  while ( 1 )
  {
    CertificateInStore = CertFindCertificateInStore(v3, 1u, 0, 0xA0000u, &pvFindPara, pPrevCertContext);
    pPrevCertContext = CertificateInStore;
    if ( !CertificateInStore )
      break;
    EfsUtilGetCertNameFromCertContext(CertificateInStore, &lpMem);
    v16 = lpMem;
    if ( lpMem )
    {
      v17 = (unsigned __int16 *)lpMem;
      do
      {
        v18 = *(unsigned __int16 *)((char *)v17 + (_BYTE *)v30 - (_BYTE *)lpMem);
        v19 = *v17 - v18;
        if ( v19 )
          break;
        ++v17;
      }
      while ( v18 );
      if ( !v19 )
      {
        v20 = CertDuplicateCertificateContext(pPrevCertContext);
        if ( v20 )
          CertDeleteCertificateFromStore(v20);
        v16 = lpMem;
      }
      EfsFreeHeap(v16);
      lpMem = 0;
    }
  }
  if ( !CertAddEncodedCertificateToStore(v3, 0x10001u, *(const BYTE **)(a1 + 8), *(_DWORD *)(a1 + 16), 1u, 0) )
  {
    LastError = GetLastError();
    pvPara = -56;
    goto LABEL_22;
  }
LABEL_24:
  if ( v30 )
    EfsFreeHeap(v30);
  if ( v3 )
    CertCloseStore(v3, 0);
  if ( v7 )
  {
    v22 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &TokenHandle, 8u);
    if ( v22 < 0 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v21);
      v23 = g_hPublisher;
      *a3 = 1;
      fnEfsLogTrace1(v23, (unsigned int)&EFS_API_ERROR, v22, 9, 223);
      v13 = RtlNtStatusToDosError(v22);
    }
  }
  if ( TokenHandle )
    NtClose(TokenHandle);
  return v13;
}

```

## disassembly

```asm
0x1800265c0  mov     [rsp-28h+arg_0], rbx
0x1800265c5  mov     [rsp-28h+arg_8], rsi
0x1800265ca  push    rbp
0x1800265cb  push    rdi
0x1800265cc  push    r12
0x1800265ce  push    r14
0x1800265d0  push    r15
0x1800265d2  mov     rbp, rsp
0x1800265d5  sub     rsp, 50h
0x1800265d9  xor     esi, esi
0x1800265db  mov     [rbp+TokenHandle], 0
0x1800265e3  mov     r12, r8
0x1800265e6  mov     [r8], esi
0x1800265e9  mov     rdi, rdx
0x1800265ec  mov     [rbp+arg_18], rsi
0x1800265f0  mov     r14, rcx
0x1800265f3  mov     [rbp+lpMem], rsi
0x1800265f7  xorps   xmm0, xmm0
0x1800265fa  lea     rax, a1361413111034; "1.3.6.1.4.1.311.10.3.4"
0x180026601  lea     edx, [rsi+0Ch]; DesiredAccess
0x180026604  mov     [rbp+var_18], rax
0x180026608  lea     rcx, [rsi-2]; ThreadHandle
0x18002660c  mov     r8b, 1; OpenAsSelf
0x18002660f  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180026613  xor     r15d, r15d
0x180026616  movups  [rbp+pvFindPara], xmm0
0x18002661a  call    cs:__imp_NtOpenThreadToken
0x180026620  mov     ebx, eax
0x180026622  test    eax, eax
0x180026624  jns     short loc_180026664
0x180026626  mov     rcx, cs:g_hPublisher
0x18002662d  lea     r9d, [rsi+9]
0x180026631  mov     r8d, eax
0x180026634  mov     dword ptr [rsp+50h+pvPara], 174h
0x18002663c  lea     rdx, EFS_API_ERROR
0x180026643  call    fnEfsLogTrace1
0x180026648  mov     ecx, ebx; Status
0x18002664a  call    cs:__imp_RtlNtStatusToDosError
0x180026650  lea     rdx, EFS_TRACE_ERROR
0x180026657  mov     dword ptr [rsp+50h+pvPara], 175h
0x18002665f  jmp     loc_1800267C4
0x180026664  call    cs:__imp_RevertToSelf
0x18002666a  test    eax, eax
0x18002666c  jnz     short loc_180026681
0x18002666e  call    cs:__imp_GetLastError
0x180026674  mov     dword ptr [rsp+50h+pvPara], 17Bh
0x18002667c  jmp     loc_1800267BD
0x180026681  mov     ebx, 1
0x180026686  mov     [rsp+50h+pvPara], rdi; pvPara
0x18002668b  mov     r9d, 21000h; dwFlags
0x180026691  xor     r8d, r8d; hCryptProv
0x180026694  xor     edx, edx; dwEncodingType
0x180026696  mov     r15d, ebx
0x180026699  lea     ecx, [rbx+9]; lpszStoreProvider
0x18002669c  call    cs:__imp_CertOpenStore
0x1800266a2  mov     rsi, rax
0x1800266a5  test    rax, rax
0x1800266a8  jnz     short loc_1800266BD
0x1800266aa  call    cs:__imp_GetLastError
0x1800266b0  mov     dword ptr [rsp+50h+pvPara], 18Bh
0x1800266b8  jmp     loc_1800267BD
0x1800266bd  lea     rax, [rbp+var_18]
0x1800266c1  mov     dword ptr [rbp+pvFindPara], ebx
0x1800266c4  lea     rdx, [rbp+arg_18]
0x1800266c8  mov     qword ptr [rbp+pvFindPara+8], rax
0x1800266cc  mov     rcx, r14
0x1800266cf  call    cs:__imp_EfsUtilGetCertNameFromCertContext
0x1800266d5  cmp     [rbp+arg_18], 0
0x1800266da  mov     ebx, eax
0x1800266dc  jnz     short loc_1800266F2
0x1800266de  mov     dword ptr [rsp+50h+pvPara], 195h
0x1800266e6  lea     rdx, EFS_API_ERROR
0x1800266ed  jmp     loc_1800267C6
0x1800266f2  xor     edi, edi
0x1800266f4  lea     rax, [rbp+pvFindPara]
0x1800266f8  mov     [rsp+50h+pPrevCertContext], rdi; pPrevCertContext
0x1800266fd  mov     r9d, 0A0000h; dwFindType
0x180026703  mov     [rsp+50h+pvPara], rax; pvFindPara
0x180026708  xor     r8d, r8d; dwFindFlags
0x18002670b  mov     edx, r15d; dwCertEncodingType
0x18002670e  mov     rcx, rsi; hCertStore
0x180026711  call    cs:__imp_CertFindCertificateInStore
0x180026717  mov     rdi, rax
0x18002671a  test    rax, rax
0x18002671d  jz      short loc_180026787
0x18002671f  lea     rdx, [rbp+lpMem]
0x180026723  mov     rcx, rax
0x180026726  call    cs:__imp_EfsUtilGetCertNameFromCertContext
0x18002672c  mov     rcx, [rbp+lpMem]
0x180026730  test    rcx, rcx
0x180026733  jz      short loc_1800266F4
0x180026735  mov     r9, [rbp+arg_18]
0x180026739  mov     rdx, rcx
0x18002673c  sub     r9, rcx
0x18002673f  movzx   r8d, word ptr [rdx]
0x180026743  movzx   eax, word ptr [rdx+r9]
0x180026748  sub     r8d, eax
0x18002674b  jnz     short loc_180026755
0x18002674d  add     rdx, 2
0x180026751  test    eax, eax
0x180026753  jnz     short loc_18002673F
0x180026755  test    r8d, r8d
0x180026758  jnz     short loc_180026775
0x18002675a  mov     rcx, rdi; pCertContext
0x18002675d  call    cs:__imp_CertDuplicateCertificateContext
0x180026763  test    rax, rax
0x180026766  jz      short loc_180026771
0x180026768  mov     rcx, rax; pCertContext
0x18002676b  call    cs:__imp_CertDeleteCertificateFromStore
0x180026771  mov     rcx, [rbp+lpMem]; lpMem
0x180026775  call    EfsFreeHeap
0x18002677a  mov     [rbp+lpMem], 0
0x180026782  jmp     loc_1800266F4
0x180026787  mov     r9d, [r14+10h]; cbCertEncoded
0x18002678b  mov     edx, 10001h; dwCertEncodingType
0x180026790  mov     r8, [r14+8]; pbCertEncoded
0x180026794  mov     rcx, rsi; hCertStore
0x180026797  mov     [rsp+50h+pPrevCertContext], 0; ppCertContext
0x1800267a0  mov     dword ptr [rsp+50h+pvPara], r15d; dwAddDisposition
0x1800267a5  call    cs:__imp_CertAddEncodedCertificateToStore
0x1800267ab  test    eax, eax
0x1800267ad  jnz     short loc_1800267DB
0x1800267af  call    cs:__imp_GetLastError
0x1800267b5  mov     dword ptr [rsp+50h+pvPara], 1C8h
0x1800267bd  lea     rdx, EFS_API_ERROR
0x1800267c4  mov     ebx, eax
0x1800267c6  mov     rcx, cs:g_hPublisher
0x1800267cd  mov     r9d, 9
0x1800267d3  mov     r8d, eax
0x1800267d6  call    fnEfsLogTrace1
0x1800267db  mov     rcx, [rbp+arg_18]; lpMem
0x1800267df  test    rcx, rcx
0x1800267e2  jz      short loc_1800267E9
0x1800267e4  call    EfsFreeHeap
0x1800267e9  test    rsi, rsi
0x1800267ec  jz      short loc_1800267F9
0x1800267ee  xor     edx, edx; dwFlags
0x1800267f0  mov     rcx, rsi; hCertStore
0x1800267f3  call    cs:__imp_CertCloseStore
0x1800267f9  test    r15d, r15d
0x1800267fc  jz      short loc_18002685A
0x1800267fe  mov     r9d, 8; ThreadInformationLength
0x180026804  lea     r8, [rbp+TokenHandle]; ThreadInformation
0x180026808  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18002680f  lea     edx, [r9-3]; ThreadInformationClass
0x180026813  call    cs:__imp_NtSetInformationThread
0x180026819  mov     edi, eax
0x18002681b  test    eax, eax
0x18002681d  jns     short loc_18002685A
0x18002681f  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "FALSE")
0x180026824  mov     rcx, cs:g_hPublisher
0x18002682b  lea     rdx, EFS_API_ERROR
0x180026832  mov     r9d, 9
0x180026838  mov     dword ptr [r12], 1
0x180026840  mov     r8d, edi
0x180026843  mov     dword ptr [rsp+50h+pvPara], 1DFh
0x18002684b  call    fnEfsLogTrace1
0x180026850  mov     ecx, edi; Status
0x180026852  call    cs:__imp_RtlNtStatusToDosError
0x180026858  mov     ebx, eax
0x18002685a  mov     rcx, [rbp+TokenHandle]; Handle
0x18002685e  test    rcx, rcx
0x180026861  jz      short loc_180026869
0x180026863  call    cs:__imp_NtClose
0x180026869  lea     r11, [rsp+50h+var_s0]
0x18002686e  mov     eax, ebx
0x180026870  mov     rbx, [r11+30h]
0x180026874  mov     rsi, [r11+38h]
0x180026878  mov     rsp, r11
0x18002687b  pop     r15
0x18002687d  pop     r14
0x18002687f  pop     r12
0x180026881  pop     rdi
0x180026882  pop     rbp
0x180026883  retn
```
