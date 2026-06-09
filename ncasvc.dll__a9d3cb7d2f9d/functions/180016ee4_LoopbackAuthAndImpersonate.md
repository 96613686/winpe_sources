# LoopbackAuthAndImpersonate

- ea: `0x180016ee4`
- end: `0x1800174dc`
- name: `LoopbackAuthAndImpersonate`
- size: `1528`
- prototype: `__int64 __fastcall(__int64, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800131ac`

## callees

- `0x180013610`
- `0x180016e30`
- `0x180016ee4`
- `0x18001cc26`
- `0x18001cc32`
- `0x18001cc3e`
- `0x18001cc70`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001742b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001742b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017024`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800170f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017024`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800170f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180016fff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180016fff`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180017014`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180017014`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180016fef`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180016fef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180016fd0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180016fd0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800173b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800173c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800173b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800173c8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800171c5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800171ed`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800171c5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800171ed`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180017063`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180017063`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800170e4`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800170e4`
- `SspiCli!FreeContextBuffer` at `0x180017416`
- `SspiCli!FreeContextBuffer` at `0x180017416`
- `SspiCli!GetUserNameExW` at `0x1800170b1`
- `SspiCli!GetUserNameExW` at `0x180017468`
- `SspiCli!GetUserNameExW` at `0x1800170b1`
- `SspiCli!GetUserNameExW` at `0x180017468`
- `SspiCli!DeleteSecurityContext` at `0x180017384`
- `SspiCli!DeleteSecurityContext` at `0x1800173a0`
- `SspiCli!DeleteSecurityContext` at `0x180017384`
- `SspiCli!DeleteSecurityContext` at `0x1800173a0`
- `SspiCli!InitializeSecurityContextW` at `0x180017284`
- `SspiCli!InitializeSecurityContextW` at `0x180017284`
- `SspiCli!QuerySecurityPackageInfoW` at `0x180016fba`
- `SspiCli!QuerySecurityPackageInfoW` at `0x180016fba`
- `SspiCli!FreeCredentialsHandle` at `0x1800173e4`
- `SspiCli!FreeCredentialsHandle` at `0x180017400`
- `SspiCli!FreeCredentialsHandle` at `0x1800173e4`
- `SspiCli!FreeCredentialsHandle` at `0x180017400`
- `SspiCli!AcquireCredentialsHandleW` at `0x180017161`
- `SspiCli!AcquireCredentialsHandleW` at `0x1800171a5`
- `SspiCli!AcquireCredentialsHandleW` at `0x180017161`
- `SspiCli!AcquireCredentialsHandleW` at `0x1800171a5`
- `SspiCli!RevertSecurityContext` at `0x180017366`
- `SspiCli!RevertSecurityContext` at `0x180017366`
- `SspiCli!ImpersonateSecurityContext` at `0x180017348`
- `SspiCli!ImpersonateSecurityContext` at `0x180017348`
- `SspiCli!AcceptSecurityContext` at `0x180017312`
- `SspiCli!AcceptSecurityContext` at `0x180017312`

## pseudocode

```c
__int64 __fastcall LoopbackAuthAndImpersonate(__int64 a1, int *a2)
{
  HLOCAL v3; // r14
  HLOCAL v4; // rsi
  int v5; // ebx
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  signed int v8; // eax
  DWORD LastError; // eax
  struct _SecHandle *p_phContext; // rdi
  struct _SecHandle *p_phNewContext; // rdx
  struct _SecBufferDesc *v12; // r8
  SECURITY_STATUS v13; // eax
  SECURITY_STATUS v14; // eax
  ULONG nSize; // [rsp+60h] [rbp-A0h] BYREF
  DWORD v17; // [rsp+64h] [rbp-9Ch] BYREF
  PSecPkgInfoW ppPackageInfo; // [rsp+68h] [rbp-98h] BYREF
  unsigned int pfContextAttr; // [rsp+70h] [rbp-90h] BYREF
  SECURITY_INTEGER ptsExpiry; // [rsp+78h] [rbp-88h] BYREF
  void *TokenHandle; // [rsp+80h] [rbp-80h] BYREF
  DWORD ReturnLength; // [rsp+88h] [rbp-78h] BYREF
  __int64 Buf2; // [rsp+90h] [rbp-70h] BYREF
  __int64 v24; // [rsp+98h] [rbp-68h] BYREF
  __int128 v25; // [rsp+A0h] [rbp-60h] BYREF
  struct _SecBufferDesc pInput; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v27; // [rsp+C0h] [rbp-40h] BYREF
  struct _SecBufferDesc v28; // [rsp+D0h] [rbp-30h] BYREF
  struct _SecHandle phContext; // [rsp+E0h] [rbp-20h] BYREF
  struct _SecHandle phNewContext; // [rsp+F0h] [rbp-10h] BYREF
  struct _SecHandle phCredential; // [rsp+100h] [rbp+0h] BYREF
  struct _SecHandle v32; // [rsp+110h] [rbp+10h] BYREF
  _OWORD TokenInformation[3]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v34; // [rsp+150h] [rbp+50h]
  WCHAR NameBuffer[520]; // [rsp+160h] [rbp+60h] BYREF
  WCHAR Buffer[264]; // [rsp+570h] [rbp+470h] BYREF
  WCHAR v37[520]; // [rsp+780h] [rbp+680h] BYREF

  ptsExpiry.QuadPart = 0;
  v17 = 0;
  memset_0(NameBuffer, 0, sizeof(NameBuffer));
  pfContextAttr = 0;
  ReturnLength = 0;
  TokenHandle = 0;
  Buf2 = 999;
  v34 = 0;
  v24 = 996;
  ppPackageInfo = 0;
  pInput = 0;
  v3 = 0;
  v4 = 0;
  v25 = 0;
  nSize = 0;
  v28 = 0;
  phCredential.dwUpper = -1;
  v27 = 0;
  phCredential.dwLower = -1;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  v32.dwUpper = -1;
  v32.dwLower = -1;
  phNewContext.dwUpper = -1;
  phNewContext.dwLower = -1;
  phContext.dwUpper = -1;
  phContext.dwLower = -1;
  v5 = QuerySecurityPackageInfoW((LPWSTR)L"Kerberos", &ppPackageInfo);
  if ( v5 >= 0 )
  {
    CurrentThread = GetCurrentThread();
    if ( (OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle)
       || (CurrentProcess = GetCurrentProcess(), OpenProcessToken(CurrentProcess, 8u, &TokenHandle)))
      && GetTokenInformation(TokenHandle, TokenStatistics, TokenInformation, 0x38u, &ReturnLength) )
    {
      if ( !memcmp_0((char *)TokenInformation + 8, &Buf2, 8u) || !memcmp_0((char *)TokenInformation + 8, &v24, 8u) )
      {
        v17 = 260;
        if ( !GetComputerNameExW(ComputerNameDnsFullyQualified, Buffer, &v17) )
        {
          LastError = GetLastError();
LABEL_32:
          v5 = LastError;
          goto LABEL_33;
        }
        wcscpy(NameBuffer, L"host/");
        memcpy_0(&NameBuffer[5], Buffer, 2LL * v17);
      }
      else
      {
        nSize = 519;
        if ( !GetUserNameExW(NameSamCompatible, NameBuffer, &nSize) )
        {
          v5 = -2146893056;
          goto LABEL_33;
        }
      }
      v5 = AcquireCredentialsHandleW(0, (LPWSTR)L"Kerberos", 2u, 0, 0, 0, 0, &phCredential, &ptsExpiry);
      if ( v5 >= 0 )
      {
        v5 = AcquireCredentialsHandleW(0, (LPWSTR)L"Kerberos", 1u, 0, 0, 0, 0, &v32, &ptsExpiry);
        if ( v5 >= 0 )
        {
          v3 = LocalAlloc(0, ppPackageInfo->cbMaxToken);
          if ( !v3 || (v4 = LocalAlloc(0, ppPackageInfo->cbMaxToken)) == 0 )
          {
            v5 = -1073741801;
            goto LABEL_33;
          }
          p_phContext = 0;
          p_phNewContext = 0;
          v12 = 0;
          while ( v5 >= 0 )
          {
            pInput.ulVersion = 0;
            pInput.pBuffers = (PSecBuffer)&v25;
            pInput.cBuffers = 1;
            LODWORD(v25) = ppPackageInfo->cbMaxToken;
            DWORD1(v25) = 2;
            *((_QWORD *)&v25 + 1) = v3;
            v13 = InitializeSecurityContextW(
                    &phCredential,
                    p_phNewContext,
                    NameBuffer,
                    2u,
                    0,
                    0x10u,
                    v12,
                    0,
                    &phNewContext,
                    &pInput,
                    &pfContextAttr,
                    &ptsExpiry);
            v5 = v13;
            if ( v13 )
            {
              if ( v13 != 590610 )
                goto LABEL_33;
            }
            else if ( !(_DWORD)v25 )
            {
              break;
            }
            v28.ulVersion = 0;
            v28.pBuffers = (PSecBuffer)&v27;
            v28.cBuffers = 1;
            LODWORD(v27) = ppPackageInfo->cbMaxToken;
            DWORD1(v27) = 2;
            *((_QWORD *)&v27 + 1) = v4;
            v14 = AcceptSecurityContext(
                    &v32,
                    p_phContext,
                    &pInput,
                    0,
                    0x10u,
                    &phContext,
                    &v28,
                    &pfContextAttr,
                    &ptsExpiry);
            v5 = v14;
            if ( v14 )
            {
              if ( v14 != 590610 )
                goto LABEL_33;
            }
            else if ( !(_DWORD)v27 )
            {
              break;
            }
            p_phNewContext = &phNewContext;
            v12 = &v28;
            p_phContext = &phContext;
          }
          v5 = ImpersonateSecurityContext(&phContext);
          if ( v5 >= 0 )
          {
            NcaEvCollStrongAuthLoopbackImpersonateCheck(a2);
            LastError = RevertSecurityContext(&phContext);
            goto LABEL_32;
          }
        }
      }
    }
    else
    {
      v8 = GetLastError();
      v5 = v8;
      if ( v8 > 0 )
        v5 = (unsigned __int16)v8 | 0x80070000;
    }
  }
LABEL_33:
  if ( phNewContext.dwLower != -1 && phNewContext.dwUpper != -1 )
    DeleteSecurityContext(&phNewContext);
  if ( phContext.dwLower != -1 && phContext.dwUpper != -1 )
    DeleteSecurityContext(&phContext);
  if ( v4 )
    LocalFree(v4);
  if ( v3 )
    LocalFree(v3);
  if ( phCredential.dwLower != -1 && phCredential.dwUpper != -1 )
    FreeCredentialsHandle(&phCredential);
  if ( v32.dwLower != -1 && v32.dwUpper != -1 )
    FreeCredentialsHandle(&v32);
  if ( ppPackageInfo )
    FreeContextBuffer(ppPackageInfo);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v5 < 0 )
  {
    memset_0(v37, 0, sizeof(v37));
    nSize = 519;
    if ( GetUserNameExW(NameSamCompatible, v37, &nSize) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          (unsigned int)WPP_cb66f0d556cc3744df2a404706c3aa89_Traceguids,
          (unsigned int)v37,
          (__int64)NameBuffer);
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180016ee4  push    rbp
0x180016ee6  push    rbx
0x180016ee7  push    rsi
0x180016ee8  push    rdi
0x180016ee9  push    r12
0x180016eeb  push    r13
0x180016eed  push    r14
0x180016eef  push    r15
0x180016ef1  lea     rbp, [rsp-0AA8h]
0x180016ef9  sub     rsp, 0BA8h
0x180016f00  mov     rax, cs:__security_cookie
0x180016f07  xor     rax, rsp
0x180016f0a  mov     [rbp+0AE0h+var_50], rax
0x180016f11  mov     r15, rdx
0x180016f14  lea     rcx, [rbp+0AE0h+NameBuffer]; void *
0x180016f18  xor     r12d, r12d
0x180016f1b  xor     edx, edx; Val
0x180016f1d  mov     r8d, 410h; Size
0x180016f23  mov     qword ptr [rsp+0BE0h+var_B68], r12
0x180016f28  mov     [rsp+0BE0h+var_B7C], r12d
0x180016f2d  call    memset_0
0x180016f32  or      r13, 0FFFFFFFFFFFFFFFFh
0x180016f36  mov     [rsp+0BE0h+var_B70], r12d
0x180016f3b  xorps   xmm0, xmm0
0x180016f3e  mov     [rbp+0AE0h+var_B58], r12d
0x180016f42  xorps   xmm1, xmm1
0x180016f45  mov     [rbp+0AE0h+TokenHandle], r12
0x180016f49  xor     eax, eax
0x180016f4b  mov     [rbp+0AE0h+Buf2], 3E7h
0x180016f53  lea     rdi, pszPackage; "Kerberos"
0x180016f5a  mov     [rbp+0AE0h+var_A90], rax
0x180016f5e  mov     rcx, rdi; pszPackageName
0x180016f61  mov     [rbp+0AE0h+var_B48], 3E4h
0x180016f69  lea     rdx, [rsp+0BE0h+ppPackageInfo]; ppPackageInfo
0x180016f6e  mov     [rsp+0BE0h+ppPackageInfo], r12
0x180016f73  movups  xmmword ptr [rbp+0AE0h+pInput.ulVersion], xmm0
0x180016f77  mov     r14d, r12d
0x180016f7a  mov     esi, r12d
0x180016f7d  movups  [rbp+0AE0h+var_B40], xmm1
0x180016f81  mov     [rsp+0BE0h+nSize], r12d
0x180016f86  movups  xmmword ptr [rbp+0AE0h+var_B10.ulVersion], xmm0
0x180016f8a  mov     [rbp+0AE0h+var_AE0.dwUpper], r13
0x180016f8e  movups  [rbp+0AE0h+var_B20], xmm1
0x180016f92  mov     [rbp+0AE0h+var_AE0.dwLower], r13
0x180016f96  movups  [rbp+0AE0h+TokenInformation], xmm0
0x180016f9a  mov     [rbp+0AE0h+var_AD0.dwUpper], r13
0x180016f9e  movups  [rbp+0AE0h+var_AB0], xmm0
0x180016fa2  mov     [rbp+0AE0h+var_AD0.dwLower], r13
0x180016fa6  movups  [rbp+0AE0h+var_AA0], xmm0
0x180016faa  mov     [rbp+0AE0h+phNewContext.dwUpper], r13
0x180016fae  mov     [rbp+0AE0h+phNewContext.dwLower], r13
0x180016fb2  mov     [rbp+0AE0h+phContext.dwUpper], r13
0x180016fb6  mov     [rbp+0AE0h+phContext.dwLower], r13
0x180016fba  call    cs:__imp_QuerySecurityPackageInfoW
0x180016fc1  nop     dword ptr [rax+rax+00h]
0x180016fc6  mov     ebx, eax
0x180016fc8  test    eax, eax
0x180016fca  js      loc_180017374
0x180016fd0  call    cs:__imp_GetCurrentThread
0x180016fd7  nop     dword ptr [rax+rax+00h]
0x180016fdc  lea     ebx, [r12+8]
0x180016fe1  mov     rcx, rax; ThreadHandle
0x180016fe4  mov     edx, ebx; DesiredAccess
0x180016fe6  lea     r9, [rbp+0AE0h+TokenHandle]; TokenHandle
0x180016fea  lea     r8d, [r12+1]; OpenAsSelf
0x180016fef  call    cs:__imp_OpenThreadToken
0x180016ff6  nop     dword ptr [rax+rax+00h]
0x180016ffb  test    eax, eax
0x180016ffd  jnz     short loc_180017048
0x180016fff  call    cs:__imp_GetCurrentProcess
0x180017006  nop     dword ptr [rax+rax+00h]
0x18001700b  lea     r8, [rbp+0AE0h+TokenHandle]; TokenHandle
0x18001700f  mov     edx, ebx; DesiredAccess
0x180017011  mov     rcx, rax; ProcessHandle
0x180017014  call    cs:__imp_OpenProcessToken
0x18001701b  nop     dword ptr [rax+rax+00h]
0x180017020  test    eax, eax
0x180017022  jnz     short loc_180017048
0x180017024  call    cs:__imp_GetLastError
0x18001702b  nop     dword ptr [rax+rax+00h]
0x180017030  mov     ebx, eax
0x180017032  test    eax, eax
0x180017034  jle     loc_180017374
0x18001703a  movzx   ebx, ax
0x18001703d  or      ebx, 80070000h
0x180017043  jmp     loc_180017374
0x180017048  mov     rcx, [rbp+0AE0h+TokenHandle]; TokenHandle
0x18001704c  lea     rax, [rbp+0AE0h+var_B58]
0x180017050  mov     r9d, 38h ; '8'; TokenInformationLength
0x180017056  mov     [rsp+0BE0h+ReturnLength], rax; ReturnLength
0x18001705b  lea     r8, [rbp+0AE0h+TokenInformation]; TokenInformation
0x18001705f  lea     edx, [r9-2Eh]; TokenInformationClass
0x180017063  call    cs:__imp_GetTokenInformation
0x18001706a  nop     dword ptr [rax+rax+00h]
0x18001706f  test    eax, eax
0x180017071  jz      short loc_180017024
0x180017073  mov     r8, rbx; Size
0x180017076  lea     rdx, [rbp+0AE0h+Buf2]; Buf2
0x18001707a  lea     rcx, [rbp+0AE0h+TokenInformation+8]; Buf1
0x18001707e  call    memcmp_0
0x180017083  test    eax, eax
0x180017085  jz      short loc_1800170CB
0x180017087  mov     r8, rbx; Size
0x18001708a  lea     rdx, [rbp+0AE0h+var_B48]; Buf2
0x18001708e  lea     rcx, [rbp+0AE0h+TokenInformation+8]; Buf1
0x180017092  call    memcmp_0
0x180017097  test    eax, eax
0x180017099  jz      short loc_1800170CB
0x18001709b  lea     r8, [rsp+0BE0h+nSize]; nSize
0x1800170a0  mov     [rsp+0BE0h+nSize], 207h
0x1800170a8  lea     rdx, [rbp+0AE0h+NameBuffer]; lpNameBuffer
0x1800170ac  mov     ecx, 2; NameFormat
0x1800170b1  call    cs:__imp_GetUserNameExW
0x1800170b8  nop     dword ptr [rax+rax+00h]
0x1800170bd  test    al, al
0x1800170bf  jnz     short loc_180017133
0x1800170c1  mov     ebx, 80090300h
0x1800170c6  jmp     loc_180017374
0x1800170cb  lea     r8, [rsp+0BE0h+var_B7C]; nSize
0x1800170d0  mov     [rsp+0BE0h+var_B7C], 104h
0x1800170d8  lea     rdx, [rbp+0AE0h+Buffer]; lpBuffer
0x1800170df  mov     ecx, 3; NameType
0x1800170e4  call    cs:__imp_GetComputerNameExW
0x1800170eb  nop     dword ptr [rax+rax+00h]
0x1800170f0  test    eax, eax
0x1800170f2  jnz     short loc_180017105
0x1800170f4  call    cs:__imp_GetLastError
0x1800170fb  nop     dword ptr [rax+rax+00h]
0x180017100  jmp     loc_180017372
0x180017105  movsd   xmm0, qword ptr cs:aHost; "host/"
0x18001710d  lea     rdx, [rbp+0AE0h+Buffer]; Src
0x180017114  mov     eax, dword ptr cs:aHost+8; "/"
0x18001711a  lea     rcx, [rbp+0AE0h+var_A76]; void *
0x18001711e  mov     r8d, [rsp+0BE0h+var_B7C]
0x180017123  add     r8, r8; Size
0x180017126  movsd   qword ptr [rbp+0AE0h+NameBuffer], xmm0
0x18001712b  mov     [rbp+68h], eax
0x18001712e  call    memcpy_0
0x180017133  lea     rax, [rsp+0BE0h+var_B68]
0x180017138  xor     r9d, r9d; pvLogonId
0x18001713b  mov     [rsp+0BE0h+ptsExpiry], rax; ptsExpiry
0x180017140  mov     rdx, rdi; pszPackage
0x180017143  lea     rax, [rbp+0AE0h+var_AE0]
0x180017147  xor     ecx, ecx; pszPrincipal
0x180017149  mov     [rsp+0BE0h+phCredential], rax; phCredential
0x18001714e  mov     [rsp+0BE0h+pvGetKeyArgument], r12; pvGetKeyArgument
0x180017153  lea     r8d, [r9+2]; fCredentialUse
0x180017157  mov     [rsp+0BE0h+pGetKeyFn], r12; pGetKeyFn
0x18001715c  mov     [rsp+0BE0h+ReturnLength], r12; pAuthData
0x180017161  call    cs:__imp_AcquireCredentialsHandleW
0x180017168  nop     dword ptr [rax+rax+00h]
0x18001716d  mov     ebx, eax
0x18001716f  test    eax, eax
0x180017171  js      loc_180017374
0x180017177  lea     rax, [rsp+0BE0h+var_B68]
0x18001717c  xor     r9d, r9d; pvLogonId
0x18001717f  mov     [rsp+0BE0h+ptsExpiry], rax; ptsExpiry
0x180017184  mov     rdx, rdi; pszPackage
0x180017187  lea     rax, [rbp+0AE0h+var_AD0]
0x18001718b  xor     ecx, ecx; pszPrincipal
0x18001718d  mov     [rsp+0BE0h+phCredential], rax; phCredential
0x180017192  mov     [rsp+0BE0h+pvGetKeyArgument], r12; pvGetKeyArgument
0x180017197  lea     r8d, [r9+1]; fCredentialUse
0x18001719b  mov     [rsp+0BE0h+pGetKeyFn], r12; pGetKeyFn
0x1800171a0  mov     [rsp+0BE0h+ReturnLength], r12; pAuthData
0x1800171a5  call    cs:__imp_AcquireCredentialsHandleW
0x1800171ac  nop     dword ptr [rax+rax+00h]
0x1800171b1  mov     ebx, eax
0x1800171b3  test    eax, eax
0x1800171b5  js      loc_180017374
0x1800171bb  mov     rax, [rsp+0BE0h+ppPackageInfo]
0x1800171c0  xor     ecx, ecx; uFlags
0x1800171c2  mov     edx, [rax+8]; uBytes
0x1800171c5  call    cs:__imp_LocalAlloc
0x1800171cc  nop     dword ptr [rax+rax+00h]
0x1800171d1  mov     r14, rax
0x1800171d4  test    rax, rax
0x1800171d7  jnz     short loc_1800171E3
0x1800171d9  mov     ebx, 0C0000017h
0x1800171de  jmp     loc_180017374
0x1800171e3  mov     rax, [rsp+0BE0h+ppPackageInfo]
0x1800171e8  xor     ecx, ecx; uFlags
0x1800171ea  mov     edx, [rax+8]; uBytes
0x1800171ed  call    cs:__imp_LocalAlloc
0x1800171f4  nop     dword ptr [rax+rax+00h]
0x1800171f9  mov     rsi, rax
0x1800171fc  test    rax, rax
0x1800171ff  jz      short loc_1800171D9
0x180017201  mov     rdi, r12
0x180017204  mov     rdx, r12; phContext
0x180017207  mov     r8, r12
0x18001720a  test    ebx, ebx
0x18001720c  js      loc_180017344
0x180017212  lea     rax, [rbp+0AE0h+var_B40]
0x180017216  mov     [rbp+0AE0h+pInput.ulVersion], r12d
0x18001721a  mov     [rbp+0AE0h+pInput.pBuffers], rax
0x18001721e  mov     rax, [rsp+0BE0h+ppPackageInfo]
0x180017223  mov     [rbp+0AE0h+pInput.cBuffers], 1
0x18001722a  mov     ecx, [rax+8]
0x18001722d  lea     rax, [rsp+0BE0h+var_B68]
0x180017232  mov     [rsp+0BE0h+var_B88], rax; ptsExpiry
0x180017237  lea     rax, [rsp+0BE0h+var_B70]
0x18001723c  mov     [rsp+0BE0h+pfContextAttr], rax; pfContextAttr
0x180017241  lea     rax, [rbp+0AE0h+pInput]
0x180017245  mov     [rsp+0BE0h+pOutput], rax; pOutput
0x18001724a  lea     rax, [rbp+0AE0h+phNewContext]
0x18001724e  mov     [rsp+0BE0h+ptsExpiry], rax; phNewContext
0x180017253  mov     dword ptr [rbp+0AE0h+var_B40], ecx
0x180017256  mov     ecx, 2
0x18001725b  mov     dword ptr [rsp+0BE0h+phCredential], r12d; Reserved2
0x180017260  mov     r9d, ecx; fContextReq
0x180017263  mov     [rsp+0BE0h+pvGetKeyArgument], r8; pInput
0x180017268  lea     r8, [rbp+0AE0h+NameBuffer]; pszTargetName
0x18001726c  mov     dword ptr [rbp+0AE0h+var_B40+4], ecx
0x18001726f  lea     rcx, [rbp+0AE0h+var_AE0]; phCredential
0x180017273  mov     dword ptr [rsp+0BE0h+pGetKeyFn], 10h; TargetDataRep
0x18001727b  mov     dword ptr [rsp+0BE0h+ReturnLength], r12d; Reserved1
0x180017280  mov     qword ptr [rbp+0AE0h+var_B40+8], r14
0x180017284  call    cs:__imp_InitializeSecurityContextW
0x18001728b  nop     dword ptr [rax+rax+00h]
0x180017290  mov     ebx, eax
0x180017292  test    eax, eax
0x180017294  jz      short loc_1800172A3
0x180017296  cmp     eax, 90312h
0x18001729b  jnz     loc_180017374
0x1800172a1  jmp     short loc_1800172AD
0x1800172a3  cmp     dword ptr [rbp+0AE0h+var_B40], r12d
0x1800172a7  jz      loc_180017344
0x1800172ad  lea     rax, [rbp+0AE0h+var_B20]
0x1800172b1  mov     [rbp+0AE0h+var_B10.ulVersion], r12d
0x1800172b5  mov     [rbp+0AE0h+var_B10.pBuffers], rax
0x1800172b9  lea     r8, [rbp+0AE0h+pInput]; pInput
0x1800172bd  mov     rax, [rsp+0BE0h+ppPackageInfo]
0x1800172c2  xor     r9d, r9d; fContextReq
0x1800172c5  mov     [rbp+0AE0h+var_B10.cBuffers], 1
0x1800172cc  mov     rdx, rdi; phContext
0x1800172cf  mov     ecx, [rax+8]
0x1800172d2  lea     rax, [rsp+0BE0h+var_B68]
0x1800172d7  mov     [rsp+0BE0h+ptsExpiry], rax; ptsExpiry
0x1800172dc  lea     rax, [rsp+0BE0h+var_B70]
0x1800172e1  mov     [rsp+0BE0h+phCredential], rax; pfContextAttr
0x1800172e6  lea     rax, [rbp+0AE0h+var_B10]
0x1800172ea  mov     [rsp+0BE0h+pvGetKeyArgument], rax; pOutput
0x1800172ef  lea     rax, [rbp+0AE0h+phContext]
0x1800172f3  mov     dword ptr [rbp+0AE0h+var_B20], ecx
0x1800172f6  lea     rcx, [rbp+0AE0h+var_AD0]; phCredential
0x1800172fa  mov     [rsp+0BE0h+pGetKeyFn], rax; phNewContext
0x1800172ff  mov     dword ptr [rsp+0BE0h+ReturnLength], 10h; TargetDataRep
0x180017307  mov     dword ptr [rbp+0AE0h+var_B20+4], 2
0x18001730e  mov     qword ptr [rbp+0AE0h+var_B20+8], rsi
0x180017312  call    cs:__imp_AcceptSecurityContext
0x180017319  nop     dword ptr [rax+rax+00h]
0x18001731e  mov     ebx, eax
0x180017320  test    eax, eax
0x180017322  jz      short loc_18001732D
0x180017324  cmp     eax, 90312h
0x180017329  jnz     short loc_180017374
0x18001732b  jmp     short loc_180017333
0x18001732d  cmp     dword ptr [rbp+0AE0h+var_B20], r12d
0x180017331  jz      short loc_180017344
0x180017333  lea     rdx, [rbp+0AE0h+phNewContext]
0x180017337  lea     r8, [rbp+0AE0h+var_B10]
0x18001733b  lea     rdi, [rbp+0AE0h+phContext]
0x18001733f  jmp     loc_18001720A
0x180017344  lea     rcx, [rbp+0AE0h+phContext]; phContext
0x180017348  call    cs:__imp_ImpersonateSecurityContext
0x18001734f  nop     dword ptr [rax+rax+00h]
0x180017354  mov     ebx, eax
0x180017356  test    eax, eax
0x180017358  js      short loc_180017374
0x18001735a  mov     rcx, r15; int *
0x18001735d  call    ?NcaEvCollStrongAuthLoopbackImpersonateCheck@@YAXPEAH@Z; NcaEvCollStrongAuthLoopbackImpersonateCheck(int *)
0x180017362  lea     rcx, [rbp+0AE0h+phContext]; phContext
0x180017366  call    cs:__imp_RevertSecurityContext
0x18001736d  nop     dword ptr [rax+rax+00h]
0x180017372  mov     ebx, eax
0x180017374  cmp     [rbp+0AE0h+phNewContext.dwLower], r13
0x180017378  jz      short loc_180017390
0x18001737a  cmp     [rbp+0AE0h+phNewContext.dwUpper], r13
0x18001737e  jz      short loc_180017390
0x180017380  lea     rcx, [rbp+0AE0h+phNewContext]; phContext
0x180017384  call    cs:__imp_DeleteSecurityContext
0x18001738b  nop     dword ptr [rax+rax+00h]
0x180017390  cmp     [rbp+0AE0h+phContext.dwLower], r13
0x180017394  jz      short loc_1800173AC
0x180017396  cmp     [rbp+0AE0h+phContext.dwUpper], r13
0x18001739a  jz      short loc_1800173AC
0x18001739c  lea     rcx, [rbp+0AE0h+phContext]; phContext
0x1800173a0  call    cs:__imp_DeleteSecurityContext
0x1800173a7  nop     dword ptr [rax+rax+00h]
0x1800173ac  test    rsi, rsi
0x1800173af  jz      short loc_1800173C0
0x1800173b1  mov     rcx, rsi; hMem
0x1800173b4  call    cs:__imp_LocalFree
0x1800173bb  nop     dword ptr [rax+rax+00h]
0x1800173c0  test    r14, r14
0x1800173c3  jz      short loc_1800173D4
0x1800173c5  mov     rcx, r14; hMem
0x1800173c8  call    cs:__imp_LocalFree
0x1800173cf  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
