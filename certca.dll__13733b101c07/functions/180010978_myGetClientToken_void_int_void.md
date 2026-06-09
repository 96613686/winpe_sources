# myGetClientToken(void *,int,void * *)

- ea: `0x180010978`
- end: `0x180010d2a`
- name: `?myGetClientToken@@YAJPEAXHPEAPEAX@Z`
- size: `946`
- prototype: `__int64 __fastcall(void *, int, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010600`

## callees

- `0x180008400`
- `0x180008610`
- `0x18000fb00`
- `0x180010978`
- `0x180012450`
- `0x1800382c0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010b45`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010b45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010cd7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010cd7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800109f8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800109f8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180010a4c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180010a4c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180010a21`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180010a21`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180010a92`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180010a92`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180010bcc`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180010c21`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180010bcc`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180010c21`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010b02`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010b7b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010b02`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010b7b`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180010c49`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180010c5a`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180010c49`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180010c5a`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180010ab9`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180010ab9`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180010cba`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180010cc9`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180010cba`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180010cc9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010c72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010ce6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010cfa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010c72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010ce6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010cfa`

## pseudocode

```c
__int64 __fastcall myGetClientToken(void *a1, int a2, void **a3)
{
  PSID *v6; // rdi
  unsigned int v7; // ebx
  unsigned int v8; // ecx
  int v9; // edx
  HANDLE CurrentThread; // rax
  int v11; // eax
  void *v12; // rax
  HANDLE CurrentProcess; // rax
  unsigned int v14; // eax
  void *TokenHandle; // [rsp+60h] [rbp-9h] BYREF
  DWORD TokenInformationLength; // [rsp+68h] [rbp-1h] BYREF
  PSID pSid1; // [rsp+70h] [rbp+7h] BYREF
  PSID pSid; // [rsp+78h] [rbp+Fh] BYREF
  HANDLE ExistingTokenHandle; // [rsp+80h] [rbp+17h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+88h] [rbp+1Fh] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  TokenInformationLength = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  TokenHandle = 0;
  ExistingTokenHandle = 0;
  v6 = 0;
  pSid1 = 0;
  pSid = 0;
  if ( !a3 )
  {
    v7 = -2147467261;
    v8 = 17367499;
LABEL_3:
    v9 = v7;
LABEL_4:
    CSPrintErrorLineFile(v8, v9);
    goto LABEL_43;
  }
  *a3 = 0;
  if ( a1 )
  {
    v12 = a1;
    TokenHandle = a1;
  }
  else
  {
    CurrentThread = GetCurrentThread();
    if ( CurrentThread )
    {
      if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
      {
        v7 = myHLastError();
        CSPrintErrorLineFileData2(0, 0x11E01CBu, v7, -2147023888);
        if ( v7 != -2147023888 )
        {
          v8 = 19005899;
          goto LABEL_3;
        }
      }
    }
    else
    {
      v11 = myHLastError();
      CSPrintErrorLineFile(0x11401CBu, v11);
    }
    v12 = TokenHandle;
    if ( !TokenHandle )
    {
      CurrentProcess = GetCurrentProcess();
      if ( !CurrentProcess )
      {
        v7 = myHLastError();
        v9 = v7;
        v8 = 19661259;
        goto LABEL_4;
      }
      if ( !OpenProcessToken(CurrentProcess, 2u, &ExistingTokenHandle) )
      {
        v7 = myHLastError();
        v9 = v7;
        v8 = 20120011;
        goto LABEL_4;
      }
      if ( !DuplicateToken(ExistingTokenHandle, SecurityImpersonation, &TokenHandle) )
      {
        v7 = myHLastError();
        v9 = v7;
        v8 = 20578763;
        goto LABEL_4;
      }
      v12 = TokenHandle;
    }
  }
  if ( a2 )
  {
    if ( !GetTokenInformation(v12, TokenUser, 0, 0, &TokenInformationLength) )
    {
      v14 = myHLastError();
      v7 = v14;
      if ( v14 != -2147024774 )
      {
        v9 = v14;
        v8 = 22086091;
        goto LABEL_4;
      }
    }
    if ( !TokenInformationLength )
    {
      v7 = myHLastError();
      v9 = v7;
      v8 = 22479307;
      goto LABEL_4;
    }
    v6 = (PSID *)LocalAlloc(0, TokenInformationLength);
    if ( !v6 )
    {
      v7 = -2147024882;
      v8 = 22872523;
      goto LABEL_3;
    }
    if ( !GetTokenInformation(TokenHandle, TokenUser, v6, TokenInformationLength, &TokenInformationLength) )
    {
      v7 = myHLastError();
      v9 = v7;
      v8 = 23200203;
      goto LABEL_4;
    }
    if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid1) )
    {
      pSid1 = 0;
      v7 = myHLastError();
      v9 = v7;
      v8 = 23724491;
      goto LABEL_4;
    }
    if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x14u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
    {
      pSid = 0;
      v7 = myHLastError();
      v9 = v7;
      v8 = 24183243;
      goto LABEL_4;
    }
    if ( EqualSid(pSid1, *v6) || EqualSid(pSid, *v6) )
    {
      if ( a1 != TokenHandle && TokenHandle )
      {
        CloseHandle(TokenHandle);
        TokenHandle = 0;
      }
      if ( !(unsigned int)myNetLogonUser(0, 0, 0) )
      {
        v7 = myHLastError();
        v9 = v7;
        v8 = 25362891;
        goto LABEL_4;
      }
    }
    v12 = TokenHandle;
  }
  *a3 = v12;
  v7 = 0;
  TokenHandle = 0;
LABEL_43:
  if ( pSid1 )
    FreeSid(pSid1);
  if ( pSid )
    FreeSid(pSid);
  if ( v6 )
    LocalFree(v6);
  if ( ExistingTokenHandle )
    CloseHandle(ExistingTokenHandle);
  if ( TokenHandle != a1 && TokenHandle )
    CloseHandle(TokenHandle);
  return v7;
}

```

## disassembly

```asm
0x180010978  mov     [rsp-8+arg_8], rbx
0x18001097d  mov     [rsp-8+arg_18], rsi
0x180010982  push    rbp
0x180010983  push    rdi
0x180010984  push    r13
0x180010986  push    r14
0x180010988  push    r15
0x18001098a  lea     rbp, [rsp-37h]
0x18001098f  sub     rsp, 0A0h
0x180010996  mov     rax, cs:__security_cookie
0x18001099d  xor     rax, rsp
0x1800109a0  mov     [rbp+57h+var_30], rax
0x1800109a4  xor     r13d, r13d
0x1800109a7  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1800109ad  mov     [rbp+57h+TokenInformationLength], r13d
0x1800109b1  mov     r14, r8
0x1800109b4  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r13d
0x1800109b8  mov     r15d, edx
0x1800109bb  mov     [rbp+57h+TokenHandle], r13
0x1800109bf  mov     rsi, rcx
0x1800109c2  mov     [rbp+57h+ExistingTokenHandle], r13
0x1800109c6  mov     edi, r13d
0x1800109c9  mov     [rbp+57h+pSid1], r13
0x1800109cd  mov     [rbp+57h+var_48], r13
0x1800109d1  test    r8, r8
0x1800109d4  jnz     short loc_1800109EC
0x1800109d6  mov     ebx, 80004003h
0x1800109db  mov     ecx, 10901CBh; unsigned int
0x1800109e0  mov     edx, ebx; int
0x1800109e2  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800109e7  jmp     loc_180010CB1
0x1800109ec  mov     [r8], r13
0x1800109ef  test    rsi, rsi
0x1800109f2  jnz     loc_180010ADC
0x1800109f8  call    cs:__imp_GetCurrentThread
0x1800109fe  test    rax, rax
0x180010a01  jnz     short loc_180010A3C
0x180010a03  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180010a08  mov     edx, eax; int
0x180010a0a  mov     ecx, 11401CBh; unsigned int
0x180010a0f  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180010a14  mov     rax, [rbp+57h+TokenHandle]
0x180010a18  test    rax, rax
0x180010a1b  jnz     loc_180010AE3
0x180010a21  call    cs:__imp_GetCurrentProcess
0x180010a27  test    rax, rax
0x180010a2a  jnz     short loc_180010A84
0x180010a2c  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180010a31  mov     ebx, eax
0x180010a33  mov     edx, eax
0x180010a35  mov     ecx, 12C01CBh
0x180010a3a  jmp     short loc_1800109E2
0x180010a3c  mov     edx, 8; DesiredAccess
0x180010a41  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180010a45  mov     rcx, rax; ThreadHandle
0x180010a48  lea     r8d, [rdx-7]; OpenAsSelf
0x180010a4c  call    cs:__imp_OpenThreadToken
0x180010a52  test    eax, eax
0x180010a54  jnz     short loc_180010A14
0x180010a56  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180010a5b  mov     r9d, 800703F0h; int
0x180010a61  mov     r8d, eax; int
0x180010a64  mov     edx, 11E01CBh; unsigned int
0x180010a69  xor     ecx, ecx; unsigned __int16 *
0x180010a6b  mov     ebx, eax
0x180010a6d  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x180010a72  cmp     ebx, 800703F0h
0x180010a78  jz      short loc_180010A14
0x180010a7a  mov     ecx, 12201CBh
0x180010a7f  jmp     loc_1800109E0
0x180010a84  mov     ebx, 2
0x180010a89  lea     r8, [rbp+57h+ExistingTokenHandle]; TokenHandle
0x180010a8d  mov     edx, ebx; DesiredAccess
0x180010a8f  mov     rcx, rax; ProcessHandle
0x180010a92  call    cs:__imp_OpenProcessToken
0x180010a98  test    eax, eax
0x180010a9a  jnz     short loc_180010AAF
0x180010a9c  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180010aa1  mov     ebx, eax
0x180010aa3  mov     edx, eax
0x180010aa5  mov     ecx, 13301CBh
0x180010aaa  jmp     loc_1800109E2
0x180010aaf  mov     rcx, [rbp+57h+ExistingTokenHandle]; ExistingTokenHandle
0x180010ab3  lea     r8, [rbp+57h+TokenHandle]; DuplicateTokenHandle
0x180010ab7  mov     edx, ebx; ImpersonationLevel
0x180010ab9  call    cs:__imp_DuplicateToken
0x180010abf  test    eax, eax
0x180010ac1  jnz     short loc_180010AD6
0x180010ac3  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180010ac8  mov     ebx, eax
0x180010aca  mov     edx, eax
0x180010acc  mov     ecx, 13A01CBh
0x180010ad1  jmp     loc_1800109E2
0x180010ad6  mov     rax, [rbp+57h+TokenHandle]
0x180010ada  jmp     short loc_180010AE3
0x180010adc  mov     rax, rsi
0x180010adf  mov     [rbp+57h+TokenHandle], rax
0x180010ae3  test    r15d, r15d
0x180010ae6  jz      loc_180010CA7
0x180010aec  xor     r9d, r9d; TokenInformationLength
0x180010aef  lea     rcx, [rbp+57h+TokenInformationLength]
0x180010af3  mov     [rsp+0C0h+ReturnLength], rcx; ReturnLength
0x180010af8  xor     r8d, r8d; TokenInformation
0x180010afb  mov     rcx, rax; TokenHandle
0x180010afe  lea     edx, [r9+1]; TokenInformationClass
0x180010b02  call    cs:__imp_GetTokenInformation
0x180010b08  test    eax, eax
0x180010b0a  jnz     short loc_180010B26
0x180010b0c  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180010b11  mov     ebx, eax
0x180010b13  cmp     eax, 8007007Ah
0x180010b18  jz      short loc_180010B26
0x180010b1a  mov     edx, eax
0x180010b1c  mov     ecx, 15101CBh
0x180010b21  jmp     loc_1800109E2
0x180010b26  mov     eax, [rbp+57h+TokenInformationLength]
0x180010b29  test    eax, eax
0x180010b2b  jnz     short loc_180010B40
0x180010b2d  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180010b32  mov     ebx, eax
0x180010b34  mov     edx, eax
0x180010b36  mov     ecx, 15701CBh
0x180010b3b  jmp     loc_1800109E2
0x180010b40  mov     rdx, rax; uBytes
0x180010b43  xor     ecx, ecx; uFlags
0x180010b45  call    cs:__imp_LocalAlloc
0x180010b4b  mov     rdi, rax
0x180010b4e  test    rax, rax
0x180010b51  jnz     short loc_180010B62
0x180010b53  mov     ebx, 8007000Eh
0x180010b58  mov     ecx, 15D01CBh
0x180010b5d  jmp     loc_1800109E0
0x180010b62  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x180010b66  lea     rax, [rbp+57h+TokenInformationLength]
0x180010b6a  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180010b6e  mov     r8, rdi; TokenInformation
0x180010b71  mov     edx, 1; TokenInformationClass
0x180010b76  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x180010b7b  call    cs:__imp_GetTokenInformation
0x180010b81  test    eax, eax
0x180010b83  jnz     short loc_180010B98
0x180010b85  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180010b8a  mov     ebx, eax
0x180010b8c  mov     edx, eax
0x180010b8e  mov     ecx, 16201CBh
0x180010b93  jmp     loc_1800109E2
0x180010b98  lea     rax, [rbp+57h+pSid1]
0x180010b9c  xor     r9d, r9d; nSubAuthority1
0x180010b9f  mov     [rsp+0C0h+pSid], rax; pSid
0x180010ba4  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180010ba8  mov     [rsp+0C0h+nSubAuthority7], r13d; nSubAuthority7
0x180010bad  mov     dl, 1; nSubAuthorityCount
0x180010baf  mov     [rsp+0C0h+nSubAuthority6], r13d; nSubAuthority6
0x180010bb4  mov     [rsp+0C0h+nSubAuthority5], r13d; nSubAuthority5
0x180010bb9  lea     r8d, [r9+12h]; nSubAuthority0
0x180010bbd  mov     [rsp+0C0h+nSubAuthority4], r13d; nSubAuthority4
0x180010bc2  mov     [rsp+0C0h+nSubAuthority3], r13d; nSubAuthority3
0x180010bc7  mov     dword ptr [rsp+0C0h+ReturnLength], r13d; nSubAuthority2
0x180010bcc  call    cs:__imp_AllocateAndInitializeSid
0x180010bd2  test    eax, eax
0x180010bd4  jnz     short loc_180010BED
0x180010bd6  mov     [rbp+57h+pSid1], r13
0x180010bda  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180010bdf  mov     ebx, eax
0x180010be1  mov     edx, eax
0x180010be3  mov     ecx, 16A01CBh
0x180010be8  jmp     loc_1800109E2
0x180010bed  lea     rax, [rbp+57h+var_48]
0x180010bf1  xor     r9d, r9d; nSubAuthority1
0x180010bf4  mov     [rsp+0C0h+pSid], rax; pSid
0x180010bf9  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180010bfd  mov     [rsp+0C0h+nSubAuthority7], r13d; nSubAuthority7
0x180010c02  mov     dl, 1; nSubAuthorityCount
0x180010c04  mov     [rsp+0C0h+nSubAuthority6], r13d; nSubAuthority6
0x180010c09  mov     [rsp+0C0h+nSubAuthority5], r13d; nSubAuthority5
0x180010c0e  lea     r8d, [r9+14h]; nSubAuthority0
0x180010c12  mov     [rsp+0C0h+nSubAuthority4], r13d; nSubAuthority4
0x180010c17  mov     [rsp+0C0h+nSubAuthority3], r13d; nSubAuthority3
0x180010c1c  mov     dword ptr [rsp+0C0h+ReturnLength], r13d; nSubAuthority2
0x180010c21  call    cs:__imp_AllocateAndInitializeSid
0x180010c27  test    eax, eax
0x180010c29  jnz     short loc_180010C42
0x180010c2b  mov     [rbp+57h+var_48], r13
0x180010c2f  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180010c34  mov     ebx, eax
0x180010c36  mov     edx, eax
0x180010c38  mov     ecx, 17101CBh
0x180010c3d  jmp     loc_1800109E2
0x180010c42  mov     rdx, [rdi]; pSid2
0x180010c45  mov     rcx, [rbp+57h+pSid1]; pSid1
0x180010c49  call    cs:__imp_EqualSid
0x180010c4f  test    eax, eax
0x180010c51  jnz     short loc_180010C64
0x180010c53  mov     rdx, [rdi]; pSid2
0x180010c56  mov     rcx, [rbp+57h+var_48]; pSid1
0x180010c5a  call    cs:__imp_EqualSid
0x180010c60  test    eax, eax
0x180010c62  jz      short loc_180010CA3
0x180010c64  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180010c68  cmp     rsi, rcx
0x180010c6b  jz      short loc_180010C7C
0x180010c6d  test    rcx, rcx
0x180010c70  jz      short loc_180010C7C
0x180010c72  call    cs:__imp_CloseHandle
0x180010c78  mov     [rbp+57h+TokenHandle], r13
0x180010c7c  lea     r9, [rbp+57h+TokenHandle]
0x180010c80  xor     r8d, r8d; LPCWSTR
0x180010c83  xor     edx, edx; LPCWSTR
0x180010c85  xor     ecx, ecx; lpString
0x180010c87  call    myNetLogonUser
0x180010c8c  test    eax, eax
0x180010c8e  jnz     short loc_180010CA3
0x180010c90  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180010c95  mov     ebx, eax
0x180010c97  mov     edx, eax
0x180010c99  mov     ecx, 18301CBh
0x180010c9e  jmp     loc_1800109E2
0x180010ca3  mov     rax, [rbp+57h+TokenHandle]
0x180010ca7  mov     [r14], rax
0x180010caa  mov     ebx, r13d
0x180010cad  mov     [rbp+57h+TokenHandle], r13
0x180010cb1  mov     rcx, [rbp+57h+pSid1]; pSid
0x180010cb5  test    rcx, rcx
0x180010cb8  jz      short loc_180010CC0
0x180010cba  call    cs:__imp_FreeSid
0x180010cc0  mov     rcx, [rbp+57h+var_48]; pSid
0x180010cc4  test    rcx, rcx
0x180010cc7  jz      short loc_180010CCF
0x180010cc9  call    cs:__imp_FreeSid
0x180010ccf  test    rdi, rdi
0x180010cd2  jz      short loc_180010CDD
0x180010cd4  mov     rcx, rdi; hMem
0x180010cd7  call    cs:__imp_LocalFree
0x180010cdd  mov     rcx, [rbp+57h+ExistingTokenHandle]; hObject
0x180010ce1  test    rcx, rcx
0x180010ce4  jz      short loc_180010CEC
0x180010ce6  call    cs:__imp_CloseHandle
0x180010cec  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180010cf0  cmp     rcx, rsi
0x180010cf3  jz      short loc_180010D00
0x180010cf5  test    rcx, rcx
0x180010cf8  jz      short loc_180010D00
0x180010cfa  call    cs:__imp_CloseHandle
0x180010d00  mov     eax, ebx
0x180010d02  mov     rcx, [rbp+57h+var_30]
0x180010d06  xor     rcx, rsp; StackCookie
0x180010d09  call    __security_check_cookie
0x180010d0e  lea     r11, [rsp+0C0h+var_20]
0x180010d16  mov     rbx, [r11+38h]
0x180010d1a  mov     rsi, [r11+48h]
0x180010d1e  mov     rsp, r11
0x180010d21  pop     r15
0x180010d23  pop     r14
0x180010d25  pop     r13
0x180010d27  pop     rdi
0x180010d28  pop     rbp
0x180010d29  retn
```
