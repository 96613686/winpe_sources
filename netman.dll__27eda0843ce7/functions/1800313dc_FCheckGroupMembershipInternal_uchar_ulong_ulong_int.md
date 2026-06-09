# FCheckGroupMembershipInternal(uchar,ulong,ulong,int)

- ea: `0x1800313dc`
- end: `0x18003166c`
- name: `?FCheckGroupMembershipInternal@@YAHEKKH@Z`
- size: `656`
- prototype: `int(unsigned __int8, unsigned int, unsigned int, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180031674`
- `0x1800316e8`
- `0x1800317f4`

## callees

- `0x180001710`
- `0x1800313dc`

## import_xrefs

- `ADVAPI32!OpenThreadToken` at `0x180031480`
- `ADVAPI32!OpenThreadToken` at `0x180031480`
- `ADVAPI32!OpenProcessToken` at `0x1800314b8`
- `ADVAPI32!OpenProcessToken` at `0x1800314b8`
- `ADVAPI32!DuplicateToken` at `0x1800314e8`
- `ADVAPI32!DuplicateToken` at `0x1800314e8`
- `ADVAPI32!GetTokenInformation` at `0x180031540`
- `ADVAPI32!GetTokenInformation` at `0x1800315a8`
- `ADVAPI32!GetTokenInformation` at `0x180031540`
- `ADVAPI32!GetTokenInformation` at `0x1800315a8`
- `ADVAPI32!EqualSid` at `0x1800315e8`
- `ADVAPI32!EqualSid` at `0x1800315e8`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180031443`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180031443`
- `ADVAPI32!FreeSid` at `0x180031643`
- `ADVAPI32!FreeSid` at `0x180031643`
- `KERNEL32!GetLastError` at `0x180031497`
- `KERNEL32!GetLastError` at `0x1800314c2`
- `KERNEL32!GetLastError` at `0x1800314f6`
- `KERNEL32!GetLastError` at `0x18003154a`
- `KERNEL32!GetLastError` at `0x1800315b2`
- `KERNEL32!GetLastError` at `0x180031497`
- `KERNEL32!GetLastError` at `0x1800314c2`
- `KERNEL32!GetLastError` at `0x1800314f6`
- `KERNEL32!GetLastError` at `0x18003154a`
- `KERNEL32!GetLastError` at `0x1800315b2`
- `KERNEL32!CloseHandle` at `0x18003150b`
- `KERNEL32!CloseHandle` at `0x180031625`
- `KERNEL32!CloseHandle` at `0x18003150b`
- `KERNEL32!CloseHandle` at `0x180031625`
- `KERNEL32!GetProcessHeap` at `0x180031569`
- `KERNEL32!GetProcessHeap` at `0x180031608`
- `KERNEL32!GetProcessHeap` at `0x180031569`
- `KERNEL32!GetProcessHeap` at `0x180031608`
- `KERNEL32!HeapAlloc` at `0x18003157a`
- `KERNEL32!HeapAlloc` at `0x18003157a`
- `KERNEL32!HeapFree` at `0x180031616`
- `KERNEL32!HeapFree` at `0x180031616`
- `KERNEL32!GetCurrentProcess` at `0x1800314a8`
- `KERNEL32!GetCurrentProcess` at `0x1800314a8`
- `KERNEL32!GetCurrentThread` at `0x18003146d`
- `KERNEL32!GetCurrentThread` at `0x18003146d`

## pseudocode

```c
__int64 __fastcall FCheckGroupMembershipInternal(__int64 a1, __int64 a2, DWORD a3)
{
  unsigned int v3; // esi
  unsigned int v4; // r15d
  PSID v5; // r12
  signed int v6; // edi
  unsigned int *v7; // r14
  int v8; // r13d
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  HANDLE CurrentProcess; // rax
  signed int v12; // eax
  signed int v13; // eax
  signed int v14; // eax
  DWORD v15; // ebx
  HANDLE ProcessHeap; // rax
  signed int v17; // eax
  int v18; // ebx
  HANDLE v19; // rax
  DWORD ReturnLength; // [rsp+60h] [rbp-19h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp-11h] BYREF
  HANDLE ExistingTokenHandle; // [rsp+70h] [rbp-9h] BYREF
  PSID pSid1; // [rsp+78h] [rbp-1h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+80h] [rbp+7h] BYREF

  v3 = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  v4 = 0;
  pSid1 = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, a3, 0, 0, 0, 0, 0, 0, &pSid1) )
  {
    v5 = pSid1;
    TokenHandle = 0;
    ReturnLength = 0;
    if ( !pSid1 )
    {
LABEL_42:
      FreeSid(pSid1);
      return v4;
    }
    v6 = 0;
    v7 = 0;
    v8 = 0;
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
    {
      TokenHandle = 0;
      LastError = GetLastError();
      if ( LastError == 1008 )
      {
        ExistingTokenHandle = 0;
        CurrentProcess = GetCurrentProcess();
        if ( !OpenProcessToken(CurrentProcess, 0xAu, &ExistingTokenHandle) )
        {
          v12 = GetLastError();
          v6 = v12;
          if ( v12 > 0 )
            v6 = (unsigned __int16)v12 | 0x80070000;
          if ( v6 < 0 )
            goto LABEL_29;
        }
        if ( !DuplicateToken(ExistingTokenHandle, SecurityImpersonation, &TokenHandle) )
        {
          TokenHandle = 0;
          v13 = GetLastError();
          v6 = v13;
          if ( v13 > 0 )
            v6 = (unsigned __int16)v13 | 0x80070000;
        }
        CloseHandle(ExistingTokenHandle);
      }
      else if ( LastError > 0 )
      {
        v6 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v6 = LastError;
      }
      if ( v6 < 0 )
        goto LABEL_29;
    }
    if ( GetTokenInformation(TokenHandle, TokenGroups, 0, ReturnLength, &ReturnLength) )
      goto LABEL_23;
    v14 = GetLastError();
    if ( v14 != 122 )
    {
      if ( v14 > 0 )
        v6 = (unsigned __int16)v14 | 0x80070000;
      else
        v6 = v14;
    }
    if ( v6 >= 0 )
    {
LABEL_23:
      v15 = ReturnLength;
      ProcessHeap = GetProcessHeap();
      v7 = (unsigned int *)HeapAlloc(ProcessHeap, 8u, v15);
      if ( v7 )
      {
        if ( GetTokenInformation(TokenHandle, TokenGroups, v7, ReturnLength, &ReturnLength) )
          goto LABEL_46;
        v17 = GetLastError();
        v6 = v17;
        if ( v17 > 0 )
          v6 = (unsigned __int16)v17 | 0x80070000;
        if ( v6 >= 0 )
        {
LABEL_46:
          while ( 1 )
          {
            v18 = 0;
            if ( v3 >= *v7 )
              goto LABEL_35;
            if ( EqualSid(v5, *(PSID *)&v7[4 * v3 + 2]) )
            {
              v8 = 1;
              v18 = (v7[4 * v3 + 4] >> 4) & 1;
              goto LABEL_35;
            }
            ++v3;
          }
        }
      }
      else
      {
        v6 = -2147024882;
      }
    }
LABEL_29:
    v18 = 0;
    if ( !v7 )
    {
LABEL_36:
      if ( TokenHandle )
        CloseHandle(TokenHandle);
      if ( v6 >= 0 && v8 && !v18 )
        v4 = 1;
      goto LABEL_42;
    }
LABEL_35:
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v7);
    goto LABEL_36;
  }
  return v4;
}

```

## disassembly

```asm
0x1800313dc  push    rbp
0x1800313de  push    rbx
0x1800313df  push    rsi
0x1800313e0  push    rdi
0x1800313e1  push    r12
0x1800313e3  push    r13
0x1800313e5  push    r14
0x1800313e7  push    r15
0x1800313e9  lea     rbp, [rsp-1Fh]
0x1800313ee  sub     rsp, 98h
0x1800313f5  mov     rax, cs:__security_cookie
0x1800313fc  xor     rax, rsp
0x1800313ff  mov     [rbp+57h+var_48], rax
0x180031403  xor     esi, esi
0x180031405  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18003140b  lea     rax, [rbp+57h+pSid1]
0x18003140f  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x180031412  mov     [rsp+0D0h+pSid], rax; pSid
0x180031417  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18003141b  mov     [rsp+0D0h+nSubAuthority7], esi; nSubAuthority7
0x18003141f  mov     r9d, r8d; nSubAuthority1
0x180031422  mov     [rsp+0D0h+nSubAuthority6], esi; nSubAuthority6
0x180031426  lea     r8d, [rsi+20h]; nSubAuthority0
0x18003142a  mov     [rsp+0D0h+nSubAuthority5], esi; nSubAuthority5
0x18003142e  mov     dl, 2; nSubAuthorityCount
0x180031430  mov     [rsp+0D0h+nSubAuthority4], esi; nSubAuthority4
0x180031434  mov     r15d, esi
0x180031437  mov     [rsp+0D0h+nSubAuthority3], esi; nSubAuthority3
0x18003143b  mov     [rsp+0D0h+nSubAuthority2], esi; nSubAuthority2
0x18003143f  mov     [rbp+57h+pSid1], rsi
0x180031443  call    cs:__imp_AllocateAndInitializeSid
0x180031449  test    eax, eax
0x18003144b  jz      loc_180031649
0x180031451  mov     r12, [rbp+57h+pSid1]
0x180031455  mov     [rbp+57h+TokenHandle], rsi
0x180031459  mov     [rbp+57h+ReturnLength], esi
0x18003145c  test    r12, r12
0x18003145f  jz      loc_18003163F
0x180031465  mov     edi, esi
0x180031467  mov     r14d, esi
0x18003146a  mov     r13d, esi
0x18003146d  call    cs:__imp_GetCurrentThread
0x180031473  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180031477  xor     r8d, r8d; OpenAsSelf
0x18003147a  mov     rcx, rax; ThreadHandle
0x18003147d  lea     edx, [rsi+8]; DesiredAccess
0x180031480  call    cs:__imp_OpenThreadToken
0x180031486  mov     ebx, 80070000h
0x18003148b  test    eax, eax
0x18003148d  jnz     loc_180031528
0x180031493  mov     [rbp+57h+TokenHandle], rsi
0x180031497  call    cs:__imp_GetLastError
0x18003149d  cmp     eax, 3F0h
0x1800314a2  jnz     short loc_180031513
0x1800314a4  mov     [rbp+57h+ExistingTokenHandle], rsi
0x1800314a8  call    cs:__imp_GetCurrentProcess
0x1800314ae  mov     rcx, rax; ProcessHandle
0x1800314b1  lea     r8, [rbp+57h+ExistingTokenHandle]; TokenHandle
0x1800314b5  lea     edx, [rsi+0Ah]; DesiredAccess
0x1800314b8  call    cs:__imp_OpenProcessToken
0x1800314be  test    eax, eax
0x1800314c0  jnz     short loc_1800314DB
0x1800314c2  call    cs:__imp_GetLastError
0x1800314c8  mov     edi, eax
0x1800314ca  test    eax, eax
0x1800314cc  jle     short loc_1800314D3
0x1800314ce  movzx   edi, ax
0x1800314d1  or      edi, ebx
0x1800314d3  test    edi, edi
0x1800314d5  js      loc_1800315CB
0x1800314db  mov     rcx, [rbp+57h+ExistingTokenHandle]; ExistingTokenHandle
0x1800314df  lea     r8, [rbp+57h+TokenHandle]; DuplicateTokenHandle
0x1800314e3  mov     edx, 2; ImpersonationLevel
0x1800314e8  call    cs:__imp_DuplicateToken
0x1800314ee  test    eax, eax
0x1800314f0  jnz     short loc_180031507
0x1800314f2  mov     [rbp+57h+TokenHandle], rsi
0x1800314f6  call    cs:__imp_GetLastError
0x1800314fc  mov     edi, eax
0x1800314fe  test    eax, eax
0x180031500  jle     short loc_180031507
0x180031502  movzx   edi, ax
0x180031505  or      edi, ebx
0x180031507  mov     rcx, [rbp+57h+ExistingTokenHandle]; hObject
0x18003150b  call    cs:__imp_CloseHandle
0x180031511  jmp     short loc_180031520
0x180031513  test    eax, eax
0x180031515  jg      short loc_18003151B
0x180031517  mov     edi, eax
0x180031519  jmp     short loc_180031520
0x18003151b  movzx   edi, ax
0x18003151e  or      edi, ebx
0x180031520  test    edi, edi
0x180031522  js      loc_1800315CB
0x180031528  mov     r9d, [rbp+57h+ReturnLength]; TokenInformationLength
0x18003152c  lea     rax, [rbp+57h+ReturnLength]
0x180031530  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180031534  xor     r8d, r8d; TokenInformation
0x180031537  mov     qword ptr [rsp+0D0h+nSubAuthority2], rax; ReturnLength
0x18003153c  lea     edx, [r8+2]; TokenInformationClass
0x180031540  call    cs:__imp_GetTokenInformation
0x180031546  test    eax, eax
0x180031548  jnz     short loc_180031566
0x18003154a  call    cs:__imp_GetLastError
0x180031550  cmp     eax, 7Ah ; 'z'
0x180031553  jz      short loc_180031562
0x180031555  test    eax, eax
0x180031557  jg      short loc_18003155D
0x180031559  mov     edi, eax
0x18003155b  jmp     short loc_180031562
0x18003155d  movzx   edi, ax
0x180031560  or      edi, ebx
0x180031562  test    edi, edi
0x180031564  js      short loc_1800315CB
0x180031566  mov     ebx, [rbp+57h+ReturnLength]
0x180031569  call    cs:__imp_GetProcessHeap
0x18003156f  mov     r8d, ebx; dwBytes
0x180031572  mov     edx, 8; dwFlags
0x180031577  mov     rcx, rax; hHeap
0x18003157a  call    cs:__imp_HeapAlloc
0x180031580  mov     r14, rax
0x180031583  test    rax, rax
0x180031586  jnz     short loc_18003158F
0x180031588  mov     edi, 8007000Eh
0x18003158d  jmp     short loc_1800315CB
0x18003158f  mov     r9d, [rbp+57h+ReturnLength]; TokenInformationLength
0x180031593  lea     rax, [rbp+57h+ReturnLength]
0x180031597  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18003159b  mov     r8, r14; TokenInformation
0x18003159e  mov     edx, 2; TokenInformationClass
0x1800315a3  mov     qword ptr [rsp+0D0h+nSubAuthority2], rax; ReturnLength
0x1800315a8  call    cs:__imp_GetTokenInformation
0x1800315ae  test    eax, eax
0x1800315b0  jnz     short loc_1800315D4
0x1800315b2  call    cs:__imp_GetLastError
0x1800315b8  mov     edi, eax
0x1800315ba  test    eax, eax
0x1800315bc  jle     short loc_1800315C7
0x1800315be  movzx   edi, ax
0x1800315c1  or      edi, 80070000h
0x1800315c7  test    edi, edi
0x1800315c9  jns     short loc_1800315D4
0x1800315cb  mov     ebx, esi
0x1800315cd  test    r14, r14
0x1800315d0  jz      short loc_18003161C
0x1800315d2  jmp     short loc_180031608
0x1800315d4  xor     ebx, ebx
0x1800315d6  cmp     esi, [r14]
0x1800315d9  jnb     short loc_180031608
0x1800315db  mov     ebx, esi
0x1800315dd  mov     rcx, r12; pSid1
0x1800315e0  add     rbx, rbx
0x1800315e3  mov     rdx, [r14+rbx*8+8]; pSid2
0x1800315e8  call    cs:__imp_EqualSid
0x1800315ee  test    eax, eax
0x1800315f0  jnz     short loc_1800315F6
0x1800315f2  inc     esi
0x1800315f4  jmp     short loc_1800315D4
0x1800315f6  mov     ebx, [r14+rbx*8+10h]
0x1800315fb  mov     eax, 1
0x180031600  shr     ebx, 4
0x180031603  mov     r13d, eax
0x180031606  and     ebx, eax
0x180031608  call    cs:__imp_GetProcessHeap
0x18003160e  mov     r8, r14; lpMem
0x180031611  xor     edx, edx; dwFlags
0x180031613  mov     rcx, rax; hHeap
0x180031616  call    cs:__imp_HeapFree
0x18003161c  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180031620  test    rcx, rcx
0x180031623  jz      short loc_18003162B
0x180031625  call    cs:__imp_CloseHandle
0x18003162b  test    edi, edi
0x18003162d  js      short loc_18003163F
0x18003162f  test    r13d, r13d
0x180031632  jz      short loc_18003163F
0x180031634  test    ebx, ebx
0x180031636  mov     eax, 1
0x18003163b  cmovz   r15d, eax
0x18003163f  mov     rcx, [rbp+57h+pSid1]; pSid
0x180031643  call    cs:__imp_FreeSid
0x180031649  mov     eax, r15d
0x18003164c  mov     rcx, [rbp+57h+var_48]
0x180031650  xor     rcx, rsp; StackCookie
0x180031653  call    __security_check_cookie
0x180031658  add     rsp, 98h
0x18003165f  pop     r15
0x180031661  pop     r14
0x180031663  pop     r13
0x180031665  pop     r12
0x180031667  pop     rdi
0x180031668  pop     rsi
0x180031669  pop     rbx
0x18003166a  pop     rbp
0x18003166b  retn
```
