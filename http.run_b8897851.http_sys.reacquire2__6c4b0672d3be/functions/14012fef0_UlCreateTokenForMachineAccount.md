# UlCreateTokenForMachineAccount

- ea: `0x14012fef0`
- end: `0x140130304`
- name: `UlCreateTokenForMachineAccount`
- size: `1044`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140149bb0`

## callees

- `0x1400af800`
- `0x14012fef0`
- `0x140130b58`
- `0x140167700`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14013027f`
- `ntoskrnl!ZwClose` at `0x14013027f`
- `ksecdd!InitializeSecurityContextW` at `0x1401300c9`
- `ksecdd!InitializeSecurityContextW` at `0x1401300c9`
- `ksecdd!SspiFreeAuthIdentity` at `0x140130264`
- `ksecdd!SspiFreeAuthIdentity` at `0x140130264`
- `ksecdd!FreeCredentialsHandle` at `0x140130211`
- `ksecdd!FreeCredentialsHandle` at `0x140130235`
- `ksecdd!FreeCredentialsHandle` at `0x140130211`
- `ksecdd!FreeCredentialsHandle` at `0x140130235`
- `ksecdd!AcquireCredentialsHandleW` at `0x14012ffec`
- `ksecdd!AcquireCredentialsHandleW` at `0x140130034`
- `ksecdd!AcquireCredentialsHandleW` at `0x14012ffec`
- `ksecdd!AcquireCredentialsHandleW` at `0x140130034`
- `ksecdd!DeleteSecurityContext` at `0x1401301c9`
- `ksecdd!DeleteSecurityContext` at `0x1401301ed`
- `ksecdd!DeleteSecurityContext` at `0x1401301c9`
- `ksecdd!DeleteSecurityContext` at `0x1401301ed`
- `ksecdd!AcceptSecurityContext` at `0x14013013e`
- `ksecdd!AcceptSecurityContext` at `0x14013013e`
- `ksecdd!QuerySecurityContextToken` at `0x1401302db`
- `ksecdd!QuerySecurityContextToken` at `0x1401302db`
- `ksecdd!SspiZeroAuthIdentity` at `0x140130253`
- `ksecdd!SspiZeroAuthIdentity` at `0x140130253`
- `ksecdd!FreeContextBuffer` at `0x140130057`
- `ksecdd!FreeContextBuffer` at `0x1401300eb`
- `ksecdd!FreeContextBuffer` at `0x140130190`
- `ksecdd!FreeContextBuffer` at `0x1401301a9`
- `ksecdd!FreeContextBuffer` at `0x140130057`
- `ksecdd!FreeContextBuffer` at `0x1401300eb`
- `ksecdd!FreeContextBuffer` at `0x140130190`
- `ksecdd!FreeContextBuffer` at `0x1401301a9`

## pseudocode

```c
__int64 __fastcall UlCreateTokenForMachineAccount(const wchar_t *a1, __int64 a2, HANDLE *a3)
{
  int LocalMachineAuthIdentity; // ebx
  SECURITY_STATUS v5; // eax
  struct _SecHandle *p_phNewContext; // rbx
  struct _SecHandle *p_phContext; // rdi
  unsigned int pfContextAttr; // [rsp+60h] [rbp-A0h] BYREF
  PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthData; // [rsp+68h] [rbp-98h]
  SECURITY_INTEGER ptsExpiry; // [rsp+70h] [rbp-90h] BYREF
  HANDLE Handle; // [rsp+78h] [rbp-88h] BYREF
  PVOID v13[2]; // [rsp+80h] [rbp-80h] BYREF
  PVOID pvContextBuffer[2]; // [rsp+90h] [rbp-70h] BYREF
  UNICODE_STRING pPackage; // [rsp+A0h] [rbp-60h] BYREF
  struct _SecBufferDesc v16; // [rsp+B0h] [rbp-50h] BYREF
  struct _SecBufferDesc pInput; // [rsp+C0h] [rbp-40h] BYREF
  struct _SecHandle phContext; // [rsp+D0h] [rbp-30h] BYREF
  struct _SecHandle phNewContext; // [rsp+E0h] [rbp-20h] BYREF
  struct _SecHandle v20; // [rsp+F0h] [rbp-10h] BYREF
  struct _SecHandle phCredential; // [rsp+100h] [rbp+0h] BYREF

  *(_QWORD *)&pPackage.Length = 655368;
  *a3 = 0;
  pfContextAttr = 0;
  pPackage.Buffer = L"NTLM";
  ptsExpiry.QuadPart = 0;
  pInput.pBuffers = (PSecBuffer)pvContextBuffer;
  AuthData = 0;
  Handle = 0;
  v16.pBuffers = (PSecBuffer)v13;
  phCredential.dwUpper = -1;
  *(_OWORD *)pvContextBuffer = 0;
  phCredential.dwLower = -1;
  *(_OWORD *)v13 = 0;
  v20.dwUpper = -1;
  v20.dwLower = -1;
  phNewContext.dwUpper = -1;
  phNewContext.dwLower = -1;
  phContext.dwUpper = -1;
  phContext.dwLower = -1;
  HIDWORD(pvContextBuffer[0]) = 2;
  HIDWORD(v13[0]) = 2;
  pInput.ulVersion = 0;
  pInput.cBuffers = 1;
  v16.ulVersion = 0;
  v16.cBuffers = 1;
  LocalMachineAuthIdentity = UlpGetLocalMachineAuthIdentity(a1);
  if ( LocalMachineAuthIdentity >= 0 )
  {
    v5 = AcquireCredentialsHandleW(0, &pPackage, 2u, 0, AuthData, 0, 0, &phCredential, &ptsExpiry);
    if ( v5
      || (p_phNewContext = 0,
          p_phContext = 0,
          (v5 = AcquireCredentialsHandleW(0, &pPackage, 1u, 0, 0, 0, 0, &v20, &ptsExpiry)) != 0) )
    {
LABEL_17:
      LocalMachineAuthIdentity = UxSslMapSecurityStatusToErrorNtStatus((unsigned int)v5);
    }
    else
    {
      while ( 1 )
      {
        if ( pvContextBuffer[1] )
        {
          FreeContextBuffer(pvContextBuffer[1]);
          LODWORD(pvContextBuffer[0]) = 0;
          pvContextBuffer[1] = 0;
        }
        v5 = InitializeSecurityContextW(
               &phCredential,
               p_phNewContext,
               0,
               0x100u,
               0,
               0x10u,
               (PSecBufferDesc)((unsigned __int64)&v16 & -(__int64)(v13[1] != 0)),
               0,
               &phNewContext,
               &pInput,
               &pfContextAttr,
               &ptsExpiry);
        if ( v5 && v5 != 590610 )
        {
          if ( v5 < 0 && !p_phNewContext )
          {
            phNewContext.dwUpper = -1;
            phNewContext.dwLower = -1;
          }
          goto LABEL_17;
        }
        if ( v13[1] )
        {
          FreeContextBuffer(v13[1]);
          LODWORD(v13[0]) = 0;
          v13[1] = 0;
        }
        v5 = AcceptSecurityContext(
               &v20,
               p_phContext,
               &pInput,
               0x100u,
               0x10u,
               &phContext,
               &v16,
               &pfContextAttr,
               &ptsExpiry);
        if ( v5 && v5 != 590610 )
        {
          if ( v5 < 0 && !p_phContext )
          {
            phContext.dwUpper = -1;
            phContext.dwLower = -1;
          }
          goto LABEL_17;
        }
        if ( v5 != 590610 )
          break;
        p_phNewContext = &phNewContext;
        p_phContext = &phContext;
      }
      v5 = QuerySecurityContextToken(&phContext, &Handle);
      if ( v5 )
        goto LABEL_17;
      LocalMachineAuthIdentity = 0;
      *a3 = Handle;
      Handle = 0;
    }
  }
  if ( v13[1] )
  {
    FreeContextBuffer(v13[1]);
    v13[1] = 0;
  }
  if ( pvContextBuffer[1] )
  {
    FreeContextBuffer(pvContextBuffer[1]);
    pvContextBuffer[1] = 0;
  }
  if ( phContext.dwLower != -1 && phContext.dwUpper != -1 )
  {
    DeleteSecurityContext(&phContext);
    phContext.dwUpper = -1;
    phContext.dwLower = -1;
  }
  if ( phNewContext.dwLower != -1 && phNewContext.dwUpper != -1 )
  {
    DeleteSecurityContext(&phNewContext);
    phNewContext.dwUpper = -1;
    phNewContext.dwLower = -1;
  }
  if ( v20.dwLower != -1 && v20.dwUpper != -1 )
  {
    FreeCredentialsHandle(&v20);
    v20.dwUpper = -1;
    v20.dwLower = -1;
  }
  if ( phCredential.dwLower != -1 && phCredential.dwUpper != -1 )
  {
    FreeCredentialsHandle(&phCredential);
    phCredential.dwUpper = -1;
    phCredential.dwLower = -1;
  }
  if ( AuthData )
  {
    SspiZeroAuthIdentity(AuthData);
    SspiFreeAuthIdentity(AuthData);
    AuthData = 0;
  }
  if ( Handle )
    ZwClose(Handle);
  return (unsigned int)LocalMachineAuthIdentity;
}

```

## disassembly

```asm
0x14012fef0  push    rbp
0x14012fef2  push    rbx
0x14012fef3  push    rsi
0x14012fef4  push    rdi
0x14012fef5  push    r12
0x14012fef7  push    r14
0x14012fef9  push    r15
0x14012fefb  lea     rbp, [rsp-20h]
0x14012ff00  sub     rsp, 120h
0x14012ff07  mov     rax, cs:__security_cookie
0x14012ff0e  xor     rax, rsp
0x14012ff11  mov     [rbp+50h+var_40], rax
0x14012ff15  xor     r14d, r14d
0x14012ff18  mov     qword ptr [rbp+50h+pPackage.Length], 0A0008h
0x14012ff20  or      r15, 0FFFFFFFFFFFFFFFFh
0x14012ff24  mov     [r8], r14
0x14012ff27  lea     rax, aNtlm_0; "NTLM"
0x14012ff2e  mov     [rsp+150h+var_F0], r14d
0x14012ff33  mov     [rbp+50h+pPackage.Buffer], rax
0x14012ff37  xorps   xmm0, xmm0
0x14012ff3a  lea     rax, [rbp+50h+pvContextBuffer]
0x14012ff3e  mov     qword ptr [rsp+150h+var_E0], r14
0x14012ff43  mov     [rbp+50h+pInput.pBuffers], rax
0x14012ff47  lea     edi, [r14+2]
0x14012ff4b  xorps   xmm1, xmm1
0x14012ff4e  mov     [rsp+150h+AuthData], r14
0x14012ff53  lea     rax, [rbp+50h+var_D0]
0x14012ff57  mov     [rsp+150h+Handle], r14
0x14012ff5c  mov     rsi, r8
0x14012ff5f  mov     [rbp+50h+var_A0.pBuffers], rax
0x14012ff63  lea     r12d, [r14+1]
0x14012ff67  mov     [rbp+50h+var_50.dwUpper], r15
0x14012ff6b  movups  xmmword ptr [rbp+50h+pvContextBuffer], xmm0
0x14012ff6f  lea     r8, [rsp+150h+AuthData]
0x14012ff74  mov     [rbp+50h+var_50.dwLower], r15
0x14012ff78  movups  xmmword ptr [rbp+50h+var_D0], xmm1
0x14012ff7c  mov     [rbp+50h+var_60.dwUpper], r15
0x14012ff80  mov     [rbp+50h+var_60.dwLower], r15
0x14012ff84  mov     [rbp+50h+phNewContext.dwUpper], r15
0x14012ff88  mov     [rbp+50h+phNewContext.dwLower], r15
0x14012ff8c  mov     [rbp+50h+phContext.dwUpper], r15
0x14012ff90  mov     [rbp+50h+phContext.dwLower], r15
0x14012ff94  mov     dword ptr [rbp+50h+pvContextBuffer+4], edi
0x14012ff97  mov     dword ptr [rbp+50h+var_D0+4], edi
0x14012ff9a  mov     [rbp+50h+pInput.ulVersion], r14d
0x14012ff9e  mov     [rbp+50h+pInput.cBuffers], r12d
0x14012ffa2  mov     [rbp+50h+var_A0.ulVersion], r14d
0x14012ffa6  mov     [rbp+50h+var_A0.cBuffers], r12d
0x14012ffaa  call    UlpGetLocalMachineAuthIdentity
0x14012ffaf  mov     ebx, eax
0x14012ffb1  test    eax, eax
0x14012ffb3  js      loc_140130187
0x14012ffb9  lea     rax, [rsp+150h+var_E0]
0x14012ffbe  xor     r9d, r9d; pvLogonId
0x14012ffc1  mov     [rsp+150h+ptsExpiry], rax; ptsExpiry
0x14012ffc6  lea     rdx, [rbp+50h+pPackage]; pPackage
0x14012ffca  lea     rax, [rbp+50h+var_50]
0x14012ffce  mov     r8d, edi; fCredentialUse
0x14012ffd1  mov     [rsp+150h+phCredential], rax; phCredential
0x14012ffd6  xor     ecx, ecx; pPrincipal
0x14012ffd8  mov     rax, [rsp+150h+AuthData]
0x14012ffdd  mov     [rsp+150h+pvGetKeyArgument], r14; pvGetKeyArgument
0x14012ffe2  mov     [rsp+150h+pGetKeyFn], r14; pGetKeyFn
0x14012ffe7  mov     [rsp+150h+pAuthData], rax; pAuthData
0x14012ffec  call    cs:__imp_AcquireCredentialsHandleW
0x14012fff3  nop     dword ptr [rax+rax+00h]
0x14012fff8  test    eax, eax
0x14012fffa  jnz     loc_14013017E
0x140130000  lea     rax, [rsp+150h+var_E0]
0x140130005  xor     r9d, r9d; pvLogonId
0x140130008  mov     [rsp+150h+ptsExpiry], rax; ptsExpiry
0x14013000d  lea     rdx, [rbp+50h+pPackage]; pPackage
0x140130011  lea     rax, [rbp+50h+var_60]
0x140130015  mov     r8d, r12d; fCredentialUse
0x140130018  mov     [rsp+150h+phCredential], rax; phCredential
0x14013001d  xor     ecx, ecx; pPrincipal
0x14013001f  mov     [rsp+150h+pvGetKeyArgument], r14; pvGetKeyArgument
0x140130024  mov     ebx, r14d
0x140130027  mov     [rsp+150h+pGetKeyFn], r14; pGetKeyFn
0x14013002c  mov     edi, r14d
0x14013002f  mov     [rsp+150h+pAuthData], r14; pAuthData
0x140130034  call    cs:__imp_AcquireCredentialsHandleW
0x14013003b  nop     dword ptr [rax+rax+00h]
0x140130040  test    eax, eax
0x140130042  jnz     loc_14013017E
0x140130048  mov     r12d, 90312h
0x14013004e  mov     rcx, [rbp+50h+pvContextBuffer+8]; pvContextBuffer
0x140130052  test    rcx, rcx
0x140130055  jz      short loc_14013006B
0x140130057  call    cs:__imp_FreeContextBuffer
0x14013005e  nop     dword ptr [rax+rax+00h]
0x140130063  mov     dword ptr [rbp+50h+pvContextBuffer], r14d
0x140130067  mov     [rbp+50h+pvContextBuffer+8], r14
0x14013006b  mov     rax, [rbp+50h+var_D0+8]
0x14013006f  mov     r9d, 100h; fContextReq
0x140130075  neg     rax
0x140130078  mov     rdx, rbx; phContext
0x14013007b  lea     rax, [rbp+50h+var_A0]
0x14013007f  sbb     rcx, rcx
0x140130082  xor     r8d, r8d; pTargetName
0x140130085  and     rcx, rax
0x140130088  lea     rax, [rsp+150h+var_E0]
0x14013008d  mov     [rsp+150h+var_F8], rax; ptsExpiry
0x140130092  lea     rax, [rsp+150h+var_F0]
0x140130097  mov     [rsp+150h+pfContextAttr], rax; pfContextAttr
0x14013009c  lea     rax, [rbp+50h+pInput]
0x1401300a0  mov     [rsp+150h+pOutput], rax; pOutput
0x1401300a5  lea     rax, [rbp+50h+phNewContext]
0x1401300a9  mov     [rsp+150h+ptsExpiry], rax; phNewContext
0x1401300ae  mov     dword ptr [rsp+150h+phCredential], r14d; Reserved2
0x1401300b3  mov     [rsp+150h+pvGetKeyArgument], rcx; pInput
0x1401300b8  lea     rcx, [rbp+50h+var_50]; phCredential
0x1401300bc  mov     dword ptr [rsp+150h+pGetKeyFn], 10h; TargetDataRep
0x1401300c4  mov     dword ptr [rsp+150h+pAuthData], r14d; Reserved1
0x1401300c9  call    cs:__imp_InitializeSecurityContextW
0x1401300d0  nop     dword ptr [rax+rax+00h]
0x1401300d5  test    eax, eax
0x1401300d7  jz      short loc_1401300E2
0x1401300d9  cmp     eax, r12d
0x1401300dc  jnz     loc_14013016D
0x1401300e2  mov     rcx, [rbp+50h+var_D0+8]; pvContextBuffer
0x1401300e6  test    rcx, rcx
0x1401300e9  jz      short loc_1401300FF
0x1401300eb  call    cs:__imp_FreeContextBuffer
0x1401300f2  nop     dword ptr [rax+rax+00h]
0x1401300f7  mov     dword ptr [rbp+50h+var_D0], r14d
0x1401300fb  mov     [rbp+50h+var_D0+8], r14
0x1401300ff  lea     rax, [rsp+150h+var_E0]
0x140130104  mov     r9d, 100h; fContextReq
0x14013010a  mov     [rsp+150h+ptsExpiry], rax; ptsExpiry
0x14013010f  lea     r8, [rbp+50h+pInput]; pInput
0x140130113  lea     rax, [rsp+150h+var_F0]
0x140130118  mov     rdx, rdi; phContext
0x14013011b  mov     [rsp+150h+phCredential], rax; pfContextAttr
0x140130120  lea     rcx, [rbp+50h+var_60]; phCredential
0x140130124  lea     rax, [rbp+50h+var_A0]
0x140130128  mov     [rsp+150h+pvGetKeyArgument], rax; pOutput
0x14013012d  lea     rax, [rbp+50h+phContext]
0x140130131  mov     [rsp+150h+pGetKeyFn], rax; phNewContext
0x140130136  mov     dword ptr [rsp+150h+pAuthData], 10h; TargetDataRep
0x14013013e  call    cs:__imp_AcceptSecurityContext
0x140130145  nop     dword ptr [rax+rax+00h]
0x14013014a  test    eax, eax
0x14013014c  jz      short loc_140130157
0x14013014e  cmp     eax, r12d
0x140130151  jnz     loc_1401302AC
0x140130157  cmp     eax, r12d
0x14013015a  jnz     loc_1401302CA
0x140130160  lea     rbx, [rbp+50h+phNewContext]
0x140130164  lea     rdi, [rbp+50h+phContext]
0x140130168  jmp     loc_14013004E
0x14013016d  test    eax, eax
0x14013016f  jns     short loc_14013017E
0x140130171  test    rbx, rbx
0x140130174  jnz     short loc_14013017E
0x140130176  mov     [rbp+50h+phNewContext.dwUpper], r15
0x14013017a  mov     [rbp+50h+phNewContext.dwLower], r15
0x14013017e  mov     ecx, eax
0x140130180  call    UxSslMapSecurityStatusToErrorNtStatus
0x140130185  mov     ebx, eax
0x140130187  mov     rcx, [rbp+50h+var_D0+8]; pvContextBuffer
0x14013018b  test    rcx, rcx
0x14013018e  jz      short loc_1401301A0
0x140130190  call    cs:__imp_FreeContextBuffer
0x140130197  nop     dword ptr [rax+rax+00h]
0x14013019c  mov     [rbp+50h+var_D0+8], r14
0x1401301a0  mov     rcx, [rbp+50h+pvContextBuffer+8]; pvContextBuffer
0x1401301a4  test    rcx, rcx
0x1401301a7  jz      short loc_1401301B9
0x1401301a9  call    cs:__imp_FreeContextBuffer
0x1401301b0  nop     dword ptr [rax+rax+00h]
0x1401301b5  mov     [rbp+50h+pvContextBuffer+8], r14
0x1401301b9  cmp     [rbp+50h+phContext.dwLower], r15
0x1401301bd  jz      short loc_1401301DD
0x1401301bf  cmp     [rbp+50h+phContext.dwUpper], r15
0x1401301c3  jz      short loc_1401301DD
0x1401301c5  lea     rcx, [rbp+50h+phContext]; phContext
0x1401301c9  call    cs:__imp_DeleteSecurityContext
0x1401301d0  nop     dword ptr [rax+rax+00h]
0x1401301d5  mov     [rbp+50h+phContext.dwUpper], r15
0x1401301d9  mov     [rbp+50h+phContext.dwLower], r15
0x1401301dd  cmp     [rbp+50h+phNewContext.dwLower], r15
0x1401301e1  jz      short loc_140130201
0x1401301e3  cmp     [rbp+50h+phNewContext.dwUpper], r15
0x1401301e7  jz      short loc_140130201
0x1401301e9  lea     rcx, [rbp+50h+phNewContext]; phContext
0x1401301ed  call    cs:__imp_DeleteSecurityContext
0x1401301f4  nop     dword ptr [rax+rax+00h]
0x1401301f9  mov     [rbp+50h+phNewContext.dwUpper], r15
0x1401301fd  mov     [rbp+50h+phNewContext.dwLower], r15
0x140130201  cmp     [rbp+50h+var_60.dwLower], r15
0x140130205  jz      short loc_140130225
0x140130207  cmp     [rbp+50h+var_60.dwUpper], r15
0x14013020b  jz      short loc_140130225
0x14013020d  lea     rcx, [rbp+50h+var_60]; phCredential
0x140130211  call    cs:__imp_FreeCredentialsHandle
0x140130218  nop     dword ptr [rax+rax+00h]
0x14013021d  mov     [rbp+50h+var_60.dwUpper], r15
0x140130221  mov     [rbp+50h+var_60.dwLower], r15
0x140130225  cmp     [rbp+50h+var_50.dwLower], r15
0x140130229  jz      short loc_140130249
0x14013022b  cmp     [rbp+50h+var_50.dwUpper], r15
0x14013022f  jz      short loc_140130249
0x140130231  lea     rcx, [rbp+50h+var_50]; phCredential
0x140130235  call    cs:__imp_FreeCredentialsHandle
0x14013023c  nop     dword ptr [rax+rax+00h]
0x140130241  mov     [rbp+50h+var_50.dwUpper], r15
0x140130245  mov     [rbp+50h+var_50.dwLower], r15
0x140130249  mov     rcx, [rsp+150h+AuthData]; AuthData
0x14013024e  test    rcx, rcx
0x140130251  jz      short loc_140130275
0x140130253  call    cs:__imp_SspiZeroAuthIdentity
0x14013025a  nop     dword ptr [rax+rax+00h]
0x14013025f  mov     rcx, [rsp+150h+AuthData]; AuthData
0x140130264  call    cs:__imp_SspiFreeAuthIdentity
0x14013026b  nop     dword ptr [rax+rax+00h]
0x140130270  mov     [rsp+150h+AuthData], r14
0x140130275  mov     rcx, [rsp+150h+Handle]; Handle
0x14013027a  test    rcx, rcx
0x14013027d  jz      short loc_14013028B
0x14013027f  call    cs:__imp_ZwClose
0x140130286  nop     dword ptr [rax+rax+00h]
0x14013028b  mov     eax, ebx
0x14013028d  mov     rcx, [rbp+50h+var_40]
0x140130291  xor     rcx, rsp; StackCookie
0x140130294  call    __security_check_cookie
0x140130299  add     rsp, 120h
0x1401302a0  pop     r15
0x1401302a2  pop     r14
0x1401302a4  pop     r12
0x1401302a6  pop     rdi
0x1401302a7  pop     rsi
0x1401302a8  pop     rbx
0x1401302a9  pop     rbp
0x1401302aa  retn
0x1401302ac  test    eax, eax
0x1401302ae  jns     loc_14013017E
0x1401302b4  test    rdi, rdi
0x1401302b7  jnz     loc_14013017E
0x1401302bd  mov     [rbp+50h+phContext.dwUpper], r15
0x1401302c1  mov     [rbp+50h+phContext.dwLower], r15
0x1401302c5  jmp     loc_14013017E
0x1401302ca  test    eax, eax
0x1401302cc  jnz     loc_14013017E
0x1401302d2  lea     rdx, [rsp+150h+Handle]; Token
0x1401302d7  lea     rcx, [rbp+50h+phContext]; phContext
0x1401302db  call    cs:__imp_QuerySecurityContextToken
0x1401302e2  nop     dword ptr [rax+rax+00h]
0x1401302e7  test    eax, eax
0x1401302e9  jnz     loc_14013017E
0x1401302ef  mov     rax, [rsp+150h+Handle]
0x1401302f4  mov     ebx, r14d
0x1401302f7  mov     [rsi], rax
0x1401302fa  mov     [rsp+150h+Handle], r14
0x1401302ff  jmp     loc_140130187
```
