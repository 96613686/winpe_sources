# IsCurrentUserLocalAdmin(int &)

- ea: `0x180098940`
- end: `0x180098b06`
- name: `?IsCurrentUserLocalAdmin@@YAJAEAH@Z`
- size: `454`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18009b940`
- `0x1800a8fe8`
- `0x1800ab4f0`

## callees

- `0x1800084f4`
- `0x180038e44`
- `0x180044300`
- `0x180098940`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180098a48`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180098a48`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180098a36`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180098a36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098a1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098a77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098a1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098a77`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180098abd`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180098abd`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180098a9a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180098a9a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180098a6d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180098a6d`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180098a11`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180098a11`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180098acb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180098ada`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180098acb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180098ada`

## pseudocode

```c
__int64 __fastcall IsCurrentUserLocalAdmin(int *a1)
{
  HANDLE v2; // rdi
  int v3; // eax
  unsigned int v4; // ebx
  signed int LastError; // eax
  HANDLE CurrentProcess; // rax
  WINBOOL v8; // [rsp+60h] [rbp+7h] BYREF
  WINBOOL IsMember; // [rsp+64h] [rbp+Bh] BYREF
  DWORD ReturnLength; // [rsp+68h] [rbp+Fh] BYREF
  PSID SidToCheck; // [rsp+70h] [rbp+17h] BYREF
  void *TokenHandle; // [rsp+78h] [rbp+1Fh] BYREF
  HANDLE TokenInformation; // [rsp+80h] [rbp+27h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+88h] [rbp+2Fh] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *a1 = 0;
  v8 = 0;
  TokenHandle = 0;
  v2 = 0;
  ReturnLength = 0;
  TokenInformation = 0;
  SidToCheck = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  IsMember = 0;
  v3 = IsCurrentUserElevated(&v8);
  v4 = v3;
  if ( v3 < 0 )
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"IsCurrentUserLocalAdmin",
      L"IsCurrentUserElevated",
      (unsigned int)v3);
    goto LABEL_15;
  }
  if ( v8 )
  {
    *a1 = 1;
    goto LABEL_15;
  }
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
      if ( GetTokenInformation(TokenHandle, TokenLinkedToken, &TokenInformation, 8u, &ReturnLength) )
      {
        v2 = TokenInformation;
        if ( !TokenInformation )
          goto LABEL_15;
        if ( CheckTokenMembership(TokenInformation, SidToCheck, &IsMember) )
        {
          *a1 = IsMember == 1;
          goto LABEL_15;
        }
      }
      else if ( GetLastError() == 1312 )
      {
        goto LABEL_15;
      }
    }
  }
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
    v4 = (unsigned __int16)LastError | 0x80070000;
LABEL_15:
  if ( SidToCheck )
    FreeSid(SidToCheck);
  if ( v2 )
    CloseHandle(v2);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v4;
}

```

## disassembly

```asm
0x180098940  mov     [rsp-8+arg_8], rbx
0x180098945  mov     [rsp-8+arg_10], rsi
0x18009894a  push    rbp
0x18009894b  push    rdi
0x18009894c  push    r14
0x18009894e  lea     rbp, [rsp-47h]
0x180098953  sub     rsp, 0A0h
0x18009895a  mov     rax, cs:__security_cookie
0x180098961  xor     rax, rsp
0x180098964  mov     [rbp+57h+var_20], rax
0x180098968  xor     r14d, r14d
0x18009896b  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180098971  mov     [rcx], r14d
0x180098974  mov     rsi, rcx
0x180098977  lea     rcx, [rbp+57h+var_50]; IsMember
0x18009897b  mov     [rbp+57h+var_50], r14d
0x18009897f  mov     [rbp+57h+TokenHandle], r14
0x180098983  mov     edi, r14d
0x180098986  mov     [rbp+57h+ReturnLength], r14d
0x18009898a  mov     [rbp+57h+TokenInformation], r14
0x18009898e  mov     [rbp+57h+SidToCheck], r14
0x180098992  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r14d
0x180098996  mov     [rbp+57h+IsMember], r14d
0x18009899a  call    ?IsCurrentUserElevated@@YAJAEAH@Z; IsCurrentUserElevated(int &)
0x18009899f  mov     ebx, eax
0x1800989a1  test    eax, eax
0x1800989a3  jns     short loc_1800989C7
0x1800989a5  mov     r9d, eax
0x1800989a8  lea     r8, aIscurrentusere; "IsCurrentUserElevated"
0x1800989af  lea     rdx, aIscurrentuserl; "IsCurrentUserLocalAdmin"
0x1800989b6  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x1800989bd  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800989c2  jmp     loc_180098AB4
0x1800989c7  cmp     [rbp+57h+var_50], r14d
0x1800989cb  jz      short loc_1800989D8
0x1800989cd  mov     dword ptr [rsi], 1
0x1800989d3  jmp     loc_180098AB4
0x1800989d8  lea     rax, [rbp+57h+SidToCheck]
0x1800989dc  mov     r9d, 220h; nSubAuthority1
0x1800989e2  mov     [rsp+0B0h+pSid], rax; pSid
0x1800989e7  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1800989eb  mov     [rsp+0B0h+nSubAuthority7], r14d; nSubAuthority7
0x1800989f0  mov     r8d, 20h ; ' '; nSubAuthority0
0x1800989f6  mov     [rsp+0B0h+nSubAuthority6], r14d; nSubAuthority6
0x1800989fb  mov     dl, 2; nSubAuthorityCount
0x1800989fd  mov     [rsp+0B0h+nSubAuthority5], r14d; nSubAuthority5
0x180098a02  mov     [rsp+0B0h+nSubAuthority4], r14d; nSubAuthority4
0x180098a07  mov     [rsp+0B0h+nSubAuthority3], r14d; nSubAuthority3
0x180098a0c  mov     [rsp+0B0h+nSubAuthority2], r14d; nSubAuthority2
0x180098a11  call    cs:__imp_AllocateAndInitializeSid
0x180098a17  test    eax, eax
0x180098a19  jnz     short loc_180098A36
0x180098a1b  call    cs:__imp_GetLastError
0x180098a21  mov     ebx, eax
0x180098a23  test    eax, eax
0x180098a25  jle     loc_180098AB4
0x180098a2b  movzx   ebx, ax
0x180098a2e  or      ebx, 80070000h
0x180098a34  jmp     short loc_180098AB4
0x180098a36  call    cs:__imp_GetCurrentProcess
0x180098a3c  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x180098a40  mov     edx, 8; DesiredAccess
0x180098a45  mov     rcx, rax; ProcessHandle
0x180098a48  call    cs:__imp_OpenProcessToken
0x180098a4e  test    eax, eax
0x180098a50  jz      short loc_180098A1B
0x180098a52  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180098a56  lea     rax, [rbp+57h+ReturnLength]
0x180098a5a  mov     r9d, 8; TokenInformationLength
0x180098a60  mov     qword ptr [rsp+0B0h+nSubAuthority2], rax; ReturnLength
0x180098a65  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180098a69  lea     edx, [r9+0Bh]; TokenInformationClass
0x180098a6d  call    cs:__imp_GetTokenInformation
0x180098a73  test    eax, eax
0x180098a75  jnz     short loc_180098A86
0x180098a77  call    cs:__imp_GetLastError
0x180098a7d  cmp     eax, 520h
0x180098a82  jz      short loc_180098AB4
0x180098a84  jmp     short loc_180098A1B
0x180098a86  mov     rdi, [rbp+57h+TokenInformation]
0x180098a8a  test    rdi, rdi
0x180098a8d  jz      short loc_180098AB4
0x180098a8f  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x180098a93  lea     r8, [rbp+57h+IsMember]; IsMember
0x180098a97  mov     rcx, rdi; TokenHandle
0x180098a9a  call    cs:__imp_CheckTokenMembership
0x180098aa0  test    eax, eax
0x180098aa2  jz      loc_180098A1B
0x180098aa8  cmp     [rbp+57h+IsMember], 1
0x180098aac  mov     eax, r14d
0x180098aaf  setz    al
0x180098ab2  mov     [rsi], eax
0x180098ab4  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x180098ab8  test    rcx, rcx
0x180098abb  jz      short loc_180098AC3
0x180098abd  call    cs:__imp_FreeSid
0x180098ac3  test    rdi, rdi
0x180098ac6  jz      short loc_180098AD1
0x180098ac8  mov     rcx, rdi; hObject
0x180098acb  call    cs:__imp_CloseHandle
0x180098ad1  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180098ad5  test    rcx, rcx
0x180098ad8  jz      short loc_180098AE0
0x180098ada  call    cs:__imp_CloseHandle
0x180098ae0  mov     eax, ebx
0x180098ae2  mov     rcx, [rbp+57h+var_20]
0x180098ae6  xor     rcx, rsp; StackCookie
0x180098ae9  call    __security_check_cookie
0x180098aee  lea     r11, [rsp+0B0h+var_10]
0x180098af6  mov     rbx, [r11+28h]
0x180098afa  mov     rsi, [r11+30h]
0x180098afe  mov     rsp, r11
0x180098b01  pop     r14
0x180098b03  pop     rdi
0x180098b04  pop     rbp
0x180098b05  retn
```
