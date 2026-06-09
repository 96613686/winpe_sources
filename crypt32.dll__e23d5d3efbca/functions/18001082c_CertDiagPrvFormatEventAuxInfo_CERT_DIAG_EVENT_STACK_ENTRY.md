# CertDiagPrvFormatEventAuxInfo(_CERT_DIAG_EVENT_STACK_ENTRY *)

- ea: `0x18001082c`
- end: `0x180010aed`
- name: `?CertDiagPrvFormatEventAuxInfo@@YAXPEAU_CERT_DIAG_EVENT_STACK_ENTRY@@@Z`
- size: `705`
- prototype: `void __fastcall(struct _CERT_DIAG_EVENT_STACK_ENTRY *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800101d0`

## callees

- `0x18000bae0`
- `0x18000f190`
- `0x18001082c`
- `0x180058768`
- `0x180058b08`
- `0x180058b60`
- `0x180058c64`
- `0x18005d484`
- `0x1800bec20`
- `0x1800bec60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010917`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010a04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010917`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010a04`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010a17`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010a17`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010a0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010a0f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180010aa2`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180010aa2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180010900`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180010944`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180010900`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180010944`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800108e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180010931`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800108e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180010931`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800109f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800109f4`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180010927`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180010927`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180010957`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180010957`

## pseudocode

```c
void __fastcall CertDiagPrvFormatEventAuxInfo(struct _CERT_DIAG_EVENT_STACK_ENTRY *a1)
{
  __int64 v1; // r8
  unsigned __int64 v2; // r12
  int v3; // edx
  __int64 v4; // r13
  __int64 v5; // rdi
  void **v6; // r15
  void *v7; // rsi
  __int64 v8; // rdx
  unsigned __int64 v9; // rbx
  unsigned __int64 v10; // r14
  LARGE_INTEGER v11; // rcx
  unsigned __int64 v12; // rbx
  HANDLE CurrentThread; // rax
  HANDLE v14; // rax
  void *v15; // rcx
  HLOCAL v16; // rdi
  DWORD LastError; // ebx
  void *TokenHandle; // [rsp+40h] [rbp-C0h] BYREF
  int HasAppContainerPackageAttribute; // [rsp+48h] [rbp-B8h] BYREF
  int HasAppContainerPackageCertificatesCapability; // [rsp+4Ch] [rbp-B4h] BYREF
  void *v21; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v23; // [rsp+60h] [rbp-A0h] BYREF
  void *v24; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *v25; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v26; // [rsp+78h] [rbp-88h]
  void **v27; // [rsp+80h] [rbp-80h]
  void **v28; // [rsp+88h] [rbp-78h]
  HLOCAL *p_hMem; // [rsp+90h] [rbp-70h]
  int *p_HasAppContainerPackageAttribute; // [rsp+98h] [rbp-68h]
  int *p_HasAppContainerPackageCertificatesCapability; // [rsp+A0h] [rbp-60h]
  wchar_t pszDest[32]; // [rsp+B0h] [rbp-50h] BYREF

  v1 = *(_QWORD *)a1;
  v2 = *(_QWORD *)(*(_QWORD *)a1 + 1048LL);
  if ( *(_BYTE *)(v2 + 4) >= 5u )
  {
    v4 = *((_QWORD *)a1 + 11);
    v6 = (void **)((char *)a1 + 80);
    v5 = *((_QWORD *)a1 + 12);
    v3 = 1;
  }
  else
  {
    v3 = 0;
    v4 = 0;
    v5 = 0;
    v6 = 0;
  }
  v7 = *(void **)(v1 + 1064);
  v8 = (unsigned int)-v3;
  TokenHandle = 0;
  v24 = 0;
  v9 = 0;
  v21 = 0;
  v10 = ((unsigned __int64)a1 + 72) & -(__int64)((_DWORD)v8 != 0);
  hMem = 0;
  v25 = pszDest;
  HasAppContainerPackageAttribute = 0;
  HasAppContainerPackageCertificatesCapability = 0;
  if ( dword_18015D510 )
  {
    v11 = Frequency;
  }
  else
  {
    if ( QueryPerformanceFrequency(&Frequency) )
    {
      v11 = Frequency;
    }
    else
    {
      v11.QuadPart = 0;
      Frequency.QuadPart = 0;
    }
    dword_18015D510 = 1;
  }
  if ( v5 )
  {
    if ( v11.QuadPart )
    {
      v23 = 0;
      if ( (int)StringCchPrintfExW(
                  pszDest,
                  0x20u,
                  0,
                  &v23,
                  0,
                  L"PT%u.%06uS",
                  (int)(1000000 * (v5 - v4) / v11.QuadPart) / 1000000,
                  (int)(1000000 * (v5 - v4) / v11.QuadPart) % 1000000) >= 0 )
        v9 = 32 - v23;
    }
  }
  v12 = v9;
  if ( v12 >= 32 )
    ((void (__fastcall __noreturn *)(_QWORD, _QWORD, _QWORD, _QWORD))_report_rangecheckfailure)(
      (LARGE_INTEGER)v11.QuadPart,
      v8,
      v1,
      0);
  pszDest[v12] = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    v15 = TokenHandle;
    v24 = TokenHandle;
  }
  else
  {
    TokenHandle = 0;
    if ( GetLastError() == 1008 && ImpersonateSelf(SecurityImpersonation) )
    {
      v14 = GetCurrentThread();
      if ( !OpenThreadToken(v14, 8u, 1, &TokenHandle) )
        TokenHandle = 0;
      RevertToSelf();
    }
    v15 = TokenHandle;
  }
  if ( v15 && (unsigned int)I_CryptIsAppContainerToken(v15) )
  {
    v21 = TokenHandle;
    hMem = (HLOCAL)CertDiagGetAppContainerMoniker();
    HasAppContainerPackageAttribute = I_CryptHasAppContainerPackageAttribute(v21);
    HasAppContainerPackageCertificatesCapability = I_CryptHasAppContainerPackageCertificatesCapability(v21);
  }
  v26 = v2;
  v27 = &v24;
  v28 = &v21;
  p_hMem = &hMem;
  p_HasAppContainerPackageAttribute = &HasAppContainerPackageAttribute;
  p_HasAppContainerPackageCertificatesCapability = &HasAppContainerPackageCertificatesCapability;
  CertDiagXmlFormatElement(v7);
  if ( v21 )
    CertDiagPrvXmlFormatAppContainerCapabilities(v7, v21);
  v26 = v10;
  v28 = (void **)&v25;
  v27 = v6;
  CertDiagXmlFormatElement(v7);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  v16 = hMem;
  if ( hMem )
  {
    LastError = GetLastError();
    LocalFree(v16);
    SetLastError(LastError);
  }
}

```

## disassembly

```asm
0x18001082c  push    rbp
0x18001082e  push    rbx
0x18001082f  push    rsi
0x180010830  push    rdi
0x180010831  push    r12
0x180010833  push    r13
0x180010835  push    r14
0x180010837  push    r15
0x180010839  lea     rbp, [rsp-8]
0x18001083e  sub     rsp, 108h
0x180010845  mov     rax, cs:__security_cookie
0x18001084c  xor     rax, rsp
0x18001084f  mov     [rbp+40h+var_50], rax
0x180010853  mov     r8, [rcx]
0x180010856  xor     r9d, r9d
0x180010859  mov     r12, [r8+418h]
0x180010860  cmp     byte ptr [r12+4], 5
0x180010866  jnb     loc_180010AD1
0x18001086c  mov     edx, r9d
0x18001086f  mov     r13d, r9d
0x180010872  mov     edi, r9d
0x180010875  mov     r15d, r9d
0x180010878  mov     rsi, [r8+428h]
0x18001087f  lea     rax, [rcx+48h]
0x180010883  neg     edx
0x180010885  mov     [rsp+140h+TokenHandle], r9
0x18001088a  mov     [rsp+140h+var_D8], r9
0x18001088f  mov     rbx, r9
0x180010892  sbb     r14, r14
0x180010895  mov     [rsp+140h+var_F0], r9
0x18001089a  and     r14, rax
0x18001089d  mov     [rsp+140h+hMem], r9
0x1800108a2  cmp     cs:dword_18015D510, r9d
0x1800108a9  lea     rax, [rbp+40h+pszDest]
0x1800108ad  mov     [rsp+140h+var_D0], rax
0x1800108b2  mov     [rsp+140h+var_F8], r9d
0x1800108b7  mov     [rsp+140h+var_F4], r9d
0x1800108bc  jz      loc_180010A9B
0x1800108c2  mov     rcx, qword ptr cs:Frequency
0x1800108c9  test    rdi, rdi
0x1800108cc  jnz     loc_1801155D0
0x1800108d2  add     rbx, rbx
0x1800108d5  cmp     rbx, 40h ; '@'
0x1800108d9  jnb     loc_180010AE7
0x1800108df  mov     [rbp+rbx+40h+pszDest], r9w
0x1800108e5  call    cs:__imp_GetCurrentThread
0x1800108eb  mov     ebx, 1
0x1800108f0  lea     r9, [rsp+140h+TokenHandle]; TokenHandle
0x1800108f5  mov     rcx, rax; ThreadHandle
0x1800108f8  mov     r8d, ebx; OpenAsSelf
0x1800108fb  lea     edi, [rbx+7]
0x1800108fe  mov     edx, edi; DesiredAccess
0x180010900  call    cs:__imp_OpenThreadToken
0x180010906  test    eax, eax
0x180010908  jnz     loc_180010A8C
0x18001090e  mov     [rsp+140h+TokenHandle], 0
0x180010917  call    cs:__imp_GetLastError
0x18001091d  cmp     eax, 3F0h
0x180010922  jnz     short loc_18001095D
0x180010924  lea     ecx, [rbx+1]; ImpersonationLevel
0x180010927  call    cs:__imp_ImpersonateSelf
0x18001092d  test    eax, eax
0x18001092f  jz      short loc_18001095D
0x180010931  call    cs:__imp_GetCurrentThread
0x180010937  lea     r9, [rsp+140h+TokenHandle]; TokenHandle
0x18001093c  mov     r8d, ebx; OpenAsSelf
0x18001093f  mov     rcx, rax; ThreadHandle
0x180010942  mov     edx, edi; DesiredAccess
0x180010944  call    cs:__imp_OpenThreadToken
0x18001094a  test    eax, eax
0x18001094c  jnz     short loc_180010957
0x18001094e  mov     [rsp+140h+TokenHandle], 0
0x180010957  call    cs:__imp_RevertToSelf
0x18001095d  mov     rcx, [rsp+140h+TokenHandle]
0x180010962  test    rcx, rcx
0x180010965  jnz     loc_180010A4A
0x18001096b  lea     rax, [rsp+140h+var_D8]
0x180010970  mov     [rsp+140h+var_C8], r12
0x180010975  mov     [rbp+40h+var_C0], rax
0x180010979  lea     r9, [rsp+140h+var_C8]
0x18001097e  lea     rax, [rsp+140h+var_F0]
0x180010983  mov     rcx, rsi; void *
0x180010986  mov     [rbp+40h+var_B8], rax
0x18001098a  lea     r8, off_180123370; "ProcessName"
0x180010991  lea     rax, [rsp+140h+hMem]
0x180010996  mov     [rbp+40h+var_B0], rax
0x18001099a  lea     rdx, aEventauxinfo; "EventAuxInfo"
0x1800109a1  lea     rax, [rsp+140h+var_F8]
0x1800109a6  mov     [rbp+40h+var_A8], rax
0x1800109aa  lea     rax, [rsp+140h+var_F4]
0x1800109af  mov     [rbp+40h+var_A0], rax
0x1800109b3  call    CertDiagXmlFormatElement
0x1800109b8  mov     rdx, [rsp+140h+var_F0]; void *
0x1800109bd  test    rdx, rdx
0x1800109c0  jnz     short loc_180010A3D
0x1800109c2  lea     rax, [rsp+140h+var_D0]
0x1800109c7  mov     [rsp+140h+var_C8], r14
0x1800109cc  lea     r9, [rsp+140h+var_C8]
0x1800109d1  mov     [rbp+40h+var_B8], rax
0x1800109d5  lea     r8, off_180123430; "startTime"
0x1800109dc  mov     [rbp+40h+var_C0], r15
0x1800109e0  xor     edx, edx
0x1800109e2  mov     rcx, rsi; void *
0x1800109e5  call    CertDiagXmlFormatElement
0x1800109ea  mov     rcx, [rsp+140h+TokenHandle]; hObject
0x1800109ef  test    rcx, rcx
0x1800109f2  jz      short loc_1800109FA
0x1800109f4  call    cs:__imp_CloseHandle
0x1800109fa  mov     rdi, [rsp+140h+hMem]
0x1800109ff  test    rdi, rdi
0x180010a02  jz      short loc_180010A1D
0x180010a04  call    cs:__imp_GetLastError
0x180010a0a  mov     rcx, rdi; hMem
0x180010a0d  mov     ebx, eax
0x180010a0f  call    cs:__imp_LocalFree
0x180010a15  mov     ecx, ebx; dwErrCode
0x180010a17  call    cs:__imp_SetLastError
0x180010a1d  mov     rcx, [rbp+40h+var_50]
0x180010a21  xor     rcx, rsp; StackCookie
0x180010a24  call    __security_check_cookie
0x180010a29  add     rsp, 108h
0x180010a30  pop     r15
0x180010a32  pop     r14
0x180010a34  pop     r13
0x180010a36  pop     r12
0x180010a38  pop     rdi
0x180010a39  pop     rsi
0x180010a3a  pop     rbx
0x180010a3b  pop     rbp
0x180010a3c  retn
0x180010a3d  mov     rcx, rsi; void *
0x180010a40  call    ?CertDiagPrvXmlFormatAppContainerCapabilities@@YAXPEAX0@Z; CertDiagPrvXmlFormatAppContainerCapabilities(void *,void *)
0x180010a45  jmp     loc_1800109C2
0x180010a4a  call    I_CryptIsAppContainerToken
0x180010a4f  test    eax, eax
0x180010a51  jz      loc_18001096B
0x180010a57  mov     rcx, [rsp+140h+TokenHandle]
0x180010a5c  mov     [rsp+140h+var_F0], rcx
0x180010a61  call    CertDiagGetAppContainerMoniker
0x180010a66  mov     rcx, [rsp+140h+var_F0]
0x180010a6b  mov     [rsp+140h+hMem], rax
0x180010a70  call    I_CryptHasAppContainerPackageAttribute
0x180010a75  mov     rcx, [rsp+140h+var_F0]
0x180010a7a  mov     [rsp+140h+var_F8], eax
0x180010a7e  call    I_CryptHasAppContainerPackageCertificatesCapability
0x180010a83  mov     [rsp+140h+var_F4], eax
0x180010a87  jmp     loc_18001096B
0x180010a8c  mov     rcx, [rsp+140h+TokenHandle]
0x180010a91  mov     [rsp+140h+var_D8], rcx
0x180010a96  jmp     loc_180010962
0x180010a9b  lea     rcx, Frequency; lpFrequency
0x180010aa2  call    cs:__imp_QueryPerformanceFrequency
0x180010aa8  xor     r9d, r9d
0x180010aab  test    eax, eax
0x180010aad  jnz     short loc_180010AC8
0x180010aaf  mov     ecx, r9d
0x180010ab2  mov     qword ptr cs:Frequency, rcx
0x180010ab9  mov     cs:dword_18015D510, 1
0x180010ac3  jmp     loc_1800108C9
0x180010ac8  mov     rcx, qword ptr cs:Frequency
0x180010acf  jmp     short loc_180010AB9
0x180010ad1  mov     r13, [rcx+58h]
0x180010ad5  lea     r15, [rcx+50h]
0x180010ad9  mov     rdi, [rcx+60h]
0x180010add  mov     edx, 1
0x180010ae2  jmp     loc_180010878
0x180010ae7  call    __report_rangecheckfailure
0x1801155d0  test    rcx, rcx
0x1801155d3  jz      loc_1800108D2
0x1801155d9  sub     rdi, r13
0x1801155dc  mov     [rsp+140h+var_E0], r9
0x1801155e1  imul    rax, rdi, 0F4240h
0x1801155e8  cqo
0x1801155ea  idiv    rcx
0x1801155ed  mov     r8, rax
0x1801155f0  mov     rax, 431BDE82D7B634DBh
0x1801155fa  imul    r8
0x1801155fd  lea     rax, aPtU06us; "PT%u.%06uS"
0x180115604  sar     rdx, 12h
0x180115608  mov     rcx, rdx
0x18011560b  shr     rcx, 3Fh
0x18011560f  add     rdx, rcx
0x180115612  imul    ecx, edx, 0F4240h
0x180115618  sub     r8d, ecx
0x18011561b  lea     rcx, [rbp+40h+pszDest]; pszDest
0x18011561f  mov     [rsp+140h+var_108], r8d
0x180115624  xor     r8d, r8d; unsigned __int16 **
0x180115627  mov     [rsp+140h+var_110], edx
0x18011562b  mov     [rsp+140h+var_118], rax; unsigned __int16 *
0x180115630  mov     qword ptr [rsp+140h+var_120], r9; unsigned int
0x180115635  lea     r9, [rsp+140h+var_E0]; unsigned __int64 *
0x18011563a  lea     edi, [r8+20h]
0x18011563e  mov     edx, edi; unsigned __int64
0x180115640  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180115645  xor     r9d, r9d
0x180115648  test    eax, eax
0x18011564a  js      loc_1800108D2
0x180115650  mov     ebx, edi
0x180115652  sub     rbx, [rsp+140h+var_E0]
0x180115657  jmp     loc_1800108D2
```
