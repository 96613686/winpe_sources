# FCheckGroupMembershipInternal(uchar,ulong,ulong,int)

- ea: `0x180034cc8`
- end: `0x180034f78`
- name: `?FCheckGroupMembershipInternal@@YAHEKKH@Z`
- size: `688`
- prototype: `int(unsigned __int8, unsigned int, unsigned int, int)`
- caller_count: `9`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007000`
- `0x180018970`
- `0x18001c34c`
- `0x18002a9e0`
- `0x18002e498`
- `0x18003f844`
- `0x180044cd0`
- `0x180045340`
- `0x18004e670`

## callees

- `0x18001e1e0`
- `0x180034cc8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180034e78`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180034e78`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034f19`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034f19`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034e67`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034f0b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034e67`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034f0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034d85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034db0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034de8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034e44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034eb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034d85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034db0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034de8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034e44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034eb2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180034d96`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180034d96`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180034d73`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180034d73`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180034d60`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180034d60`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180034da6`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180034da6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034e01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034f28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034e01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034f28`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180034f4f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180034f4f`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180034d36`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180034d36`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180034ee6`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180034ee6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180034e3a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180034ea8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180034e3a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180034ea8`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180034dda`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180034dda`

## pseudocode

```c
__int64 __fastcall FCheckGroupMembershipInternal(__int64 a1, __int64 a2, DWORD a3, int a4)
{
  int v4; // ebx
  int v5; // esi
  unsigned int v6; // r14d
  PSID v7; // r13
  signed int v8; // edi
  unsigned int *v9; // r15
  int v10; // r12d
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  HANDLE CurrentProcess; // rax
  signed int v14; // eax
  signed int v15; // eax
  signed int v16; // eax
  DWORD v17; // ebx
  HANDLE ProcessHeap; // rax
  unsigned int *v19; // rax
  signed int v20; // eax
  unsigned int i; // esi
  HANDLE v22; // rax
  DWORD ReturnLength; // [rsp+60h] [rbp-29h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp-21h] BYREF
  int v26; // [rsp+70h] [rbp-19h]
  HANDLE ExistingTokenHandle; // [rsp+78h] [rbp-11h] BYREF
  PSID pSid1; // [rsp+80h] [rbp-9h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+88h] [rbp-1h] BYREF

  v4 = 0;
  v26 = a4;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  v5 = a4;
  v6 = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  pSid1 = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, a3, 0, 0, 0, 0, 0, 0, &pSid1) )
  {
    v7 = pSid1;
    TokenHandle = 0;
    ReturnLength = 0;
    if ( !pSid1 )
    {
LABEL_46:
      FreeSid(pSid1);
      return v6;
    }
    v8 = 0;
    v9 = 0;
    v10 = 0;
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
          v14 = GetLastError();
          v8 = v14;
          if ( v14 > 0 )
            v8 = (unsigned __int16)v14 | 0x80070000;
          if ( v8 < 0 )
            goto LABEL_29;
        }
        if ( !DuplicateToken(ExistingTokenHandle, SecurityImpersonation, &TokenHandle) )
        {
          TokenHandle = 0;
          v15 = GetLastError();
          v8 = v15;
          if ( v15 > 0 )
            v8 = (unsigned __int16)v15 | 0x80070000;
        }
        CloseHandle(ExistingTokenHandle);
      }
      else if ( LastError > 0 )
      {
        v8 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v8 = LastError;
      }
      if ( v8 < 0 )
        goto LABEL_29;
    }
    if ( GetTokenInformation(TokenHandle, TokenGroups, 0, ReturnLength, &ReturnLength) )
      goto LABEL_23;
    v16 = GetLastError();
    if ( v16 != 122 )
    {
      if ( v16 > 0 )
        v8 = (unsigned __int16)v16 | 0x80070000;
      else
        v8 = v16;
    }
    if ( v8 >= 0 )
    {
LABEL_23:
      v17 = ReturnLength;
      ProcessHeap = GetProcessHeap();
      v19 = (unsigned int *)HeapAlloc(ProcessHeap, 8u, v17);
      v4 = 0;
      v9 = v19;
      if ( v19 )
      {
        if ( GetTokenInformation(TokenHandle, TokenGroups, v19, ReturnLength, &ReturnLength) )
          goto LABEL_31;
        v20 = GetLastError();
        v8 = v20;
        if ( v20 > 0 )
          v8 = (unsigned __int16)v20 | 0x80070000;
        if ( v8 >= 0 )
        {
LABEL_31:
          for ( i = 0; i < *v9; ++i )
          {
            if ( EqualSid(v7, *(PSID *)&v9[4 * i + 2]) )
            {
              v10 = 1;
              v4 = (v9[4 * i + 4] >> 4) & 1;
              break;
            }
            v4 = 0;
          }
          v5 = v26;
          goto LABEL_37;
        }
      }
      else
      {
        v8 = -2147024882;
      }
    }
LABEL_29:
    if ( !v9 )
    {
LABEL_38:
      if ( TokenHandle )
        CloseHandle(TokenHandle);
      if ( v8 >= 0 )
      {
        if ( v5 )
        {
          v6 = v10;
        }
        else if ( v10 && !v4 )
        {
          v6 = 1;
        }
      }
      goto LABEL_46;
    }
LABEL_37:
    v22 = GetProcessHeap();
    HeapFree(v22, 0, v9);
    goto LABEL_38;
  }
  return v6;
}

```

## disassembly

```asm
0x180034cc8  push    rbp
0x180034cca  push    rbx
0x180034ccb  push    rsi
0x180034ccc  push    rdi
0x180034ccd  push    r12
0x180034ccf  push    r13
0x180034cd1  push    r14
0x180034cd3  push    r15
0x180034cd5  lea     rbp, [rsp-1Fh]
0x180034cda  sub     rsp, 0A8h
0x180034ce1  mov     rax, cs:__security_cookie
0x180034ce8  xor     rax, rsp
0x180034ceb  mov     [rbp+57h+var_50], rax
0x180034cef  xor     ebx, ebx
0x180034cf1  mov     [rbp+57h+var_70], r9d
0x180034cf5  lea     rax, [rbp+57h+pSid1]
0x180034cf9  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], ebx
0x180034cfc  mov     [rsp+0E0h+pSid], rax; pSid
0x180034d01  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180034d05  mov     [rsp+0E0h+nSubAuthority7], ebx; nSubAuthority7
0x180034d09  mov     esi, r9d
0x180034d0c  mov     [rsp+0E0h+nSubAuthority6], ebx; nSubAuthority6
0x180034d10  mov     r9d, r8d; nSubAuthority1
0x180034d13  mov     [rsp+0E0h+nSubAuthority5], ebx; nSubAuthority5
0x180034d17  lea     r8d, [rbx+20h]; nSubAuthority0
0x180034d1b  mov     [rsp+0E0h+nSubAuthority4], ebx; nSubAuthority4
0x180034d1f  mov     dl, 2; nSubAuthorityCount
0x180034d21  mov     [rsp+0E0h+nSubAuthority3], ebx; nSubAuthority3
0x180034d25  mov     r14d, ebx
0x180034d28  mov     [rsp+0E0h+nSubAuthority2], ebx; nSubAuthority2
0x180034d2c  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180034d32  mov     [rbp+57h+pSid1], rbx
0x180034d36  call    cs:__imp_AllocateAndInitializeSid
0x180034d3c  test    eax, eax
0x180034d3e  jz      loc_180034F55
0x180034d44  mov     r13, [rbp+57h+pSid1]
0x180034d48  mov     [rbp+57h+TokenHandle], rbx
0x180034d4c  mov     [rbp+57h+ReturnLength], ebx
0x180034d4f  test    r13, r13
0x180034d52  jz      loc_180034F4B
0x180034d58  mov     edi, ebx
0x180034d5a  mov     r15d, ebx
0x180034d5d  mov     r12d, ebx
0x180034d60  call    cs:__imp_GetCurrentThread
0x180034d66  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180034d6a  xor     r8d, r8d; OpenAsSelf
0x180034d6d  mov     rcx, rax; ThreadHandle
0x180034d70  lea     edx, [rbx+8]; DesiredAccess
0x180034d73  call    cs:__imp_OpenThreadToken
0x180034d79  test    eax, eax
0x180034d7b  jnz     loc_180034E22
0x180034d81  mov     [rbp+57h+TokenHandle], rbx
0x180034d85  call    cs:__imp_GetLastError
0x180034d8b  cmp     eax, 3F0h
0x180034d90  jnz     short loc_180034E09
0x180034d92  mov     [rbp+57h+ExistingTokenHandle], rbx
0x180034d96  call    cs:__imp_GetCurrentProcess
0x180034d9c  mov     rcx, rax; ProcessHandle
0x180034d9f  lea     r8, [rbp+57h+ExistingTokenHandle]; TokenHandle
0x180034da3  lea     edx, [rbx+0Ah]; DesiredAccess
0x180034da6  call    cs:__imp_OpenProcessToken
0x180034dac  test    eax, eax
0x180034dae  jnz     short loc_180034DCD
0x180034db0  call    cs:__imp_GetLastError
0x180034db6  mov     edi, eax
0x180034db8  test    eax, eax
0x180034dba  jle     short loc_180034DC5
0x180034dbc  movzx   edi, ax
0x180034dbf  or      edi, 80070000h
0x180034dc5  test    edi, edi
0x180034dc7  js      loc_180034ECB
0x180034dcd  mov     rcx, [rbp+57h+ExistingTokenHandle]; ExistingTokenHandle
0x180034dd1  lea     r8, [rbp+57h+TokenHandle]; DuplicateTokenHandle
0x180034dd5  mov     edx, 2; ImpersonationLevel
0x180034dda  call    cs:__imp_DuplicateToken
0x180034de0  test    eax, eax
0x180034de2  jnz     short loc_180034DFD
0x180034de4  mov     [rbp+57h+TokenHandle], rbx
0x180034de8  call    cs:__imp_GetLastError
0x180034dee  mov     edi, eax
0x180034df0  test    eax, eax
0x180034df2  jle     short loc_180034DFD
0x180034df4  movzx   edi, ax
0x180034df7  or      edi, 80070000h
0x180034dfd  mov     rcx, [rbp+57h+ExistingTokenHandle]; hObject
0x180034e01  call    cs:__imp_CloseHandle
0x180034e07  jmp     short loc_180034E1A
0x180034e09  test    eax, eax
0x180034e0b  jg      short loc_180034E11
0x180034e0d  mov     edi, eax
0x180034e0f  jmp     short loc_180034E1A
0x180034e11  movzx   edi, ax
0x180034e14  or      edi, 80070000h
0x180034e1a  test    edi, edi
0x180034e1c  js      loc_180034ECB
0x180034e22  mov     r9d, [rbp+57h+ReturnLength]; TokenInformationLength
0x180034e26  lea     rax, [rbp+57h+ReturnLength]
0x180034e2a  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180034e2e  xor     r8d, r8d; TokenInformation
0x180034e31  mov     qword ptr [rsp+0E0h+nSubAuthority2], rax; ReturnLength
0x180034e36  lea     edx, [r8+2]; TokenInformationClass
0x180034e3a  call    cs:__imp_GetTokenInformation
0x180034e40  test    eax, eax
0x180034e42  jnz     short loc_180034E64
0x180034e44  call    cs:__imp_GetLastError
0x180034e4a  cmp     eax, 7Ah ; 'z'
0x180034e4d  jz      short loc_180034E60
0x180034e4f  test    eax, eax
0x180034e51  jg      short loc_180034E57
0x180034e53  mov     edi, eax
0x180034e55  jmp     short loc_180034E60
0x180034e57  movzx   edi, ax
0x180034e5a  or      edi, 80070000h
0x180034e60  test    edi, edi
0x180034e62  js      short loc_180034ECB
0x180034e64  mov     ebx, [rbp+57h+ReturnLength]
0x180034e67  call    cs:__imp_GetProcessHeap
0x180034e6d  mov     r8d, ebx; dwBytes
0x180034e70  mov     edx, 8; dwFlags
0x180034e75  mov     rcx, rax; hHeap
0x180034e78  call    cs:__imp_HeapAlloc
0x180034e7e  xor     ebx, ebx
0x180034e80  mov     r15, rax
0x180034e83  test    rax, rax
0x180034e86  jnz     short loc_180034E8F
0x180034e88  mov     edi, 8007000Eh
0x180034e8d  jmp     short loc_180034ECB
0x180034e8f  mov     r9d, [rbp+57h+ReturnLength]; TokenInformationLength
0x180034e93  lea     rax, [rbp+57h+ReturnLength]
0x180034e97  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180034e9b  mov     r8, r15; TokenInformation
0x180034e9e  mov     edx, 2; TokenInformationClass
0x180034ea3  mov     qword ptr [rsp+0E0h+nSubAuthority2], rax; ReturnLength
0x180034ea8  call    cs:__imp_GetTokenInformation
0x180034eae  test    eax, eax
0x180034eb0  jnz     short loc_180034ED2
0x180034eb2  call    cs:__imp_GetLastError
0x180034eb8  mov     edi, eax
0x180034eba  test    eax, eax
0x180034ebc  jle     short loc_180034EC7
0x180034ebe  movzx   edi, ax
0x180034ec1  or      edi, 80070000h
0x180034ec7  test    edi, edi
0x180034ec9  jns     short loc_180034ED2
0x180034ecb  test    r15, r15
0x180034ece  jz      short loc_180034F1F
0x180034ed0  jmp     short loc_180034F0B
0x180034ed2  mov     esi, ebx
0x180034ed4  cmp     esi, [r15]
0x180034ed7  jnb     short loc_180034F08
0x180034ed9  mov     ebx, esi
0x180034edb  mov     rcx, r13; pSid1
0x180034ede  add     rbx, rbx
0x180034ee1  mov     rdx, [r15+rbx*8+8]; pSid2
0x180034ee6  call    cs:__imp_EqualSid
0x180034eec  test    eax, eax
0x180034eee  jnz     short loc_180034EF6
0x180034ef0  inc     esi
0x180034ef2  xor     ebx, ebx
0x180034ef4  jmp     short loc_180034ED4
0x180034ef6  mov     ebx, [r15+rbx*8+10h]
0x180034efb  mov     eax, 1
0x180034f00  shr     ebx, 4
0x180034f03  mov     r12d, eax
0x180034f06  and     ebx, eax
0x180034f08  mov     esi, [rbp+57h+var_70]
0x180034f0b  call    cs:__imp_GetProcessHeap
0x180034f11  mov     r8, r15; lpMem
0x180034f14  xor     edx, edx; dwFlags
0x180034f16  mov     rcx, rax; hHeap
0x180034f19  call    cs:__imp_HeapFree
0x180034f1f  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180034f23  test    rcx, rcx
0x180034f26  jz      short loc_180034F2E
0x180034f28  call    cs:__imp_CloseHandle
0x180034f2e  test    edi, edi
0x180034f30  js      short loc_180034F4B
0x180034f32  test    esi, esi
0x180034f34  jz      short loc_180034F3B
0x180034f36  mov     r14d, r12d
0x180034f39  jmp     short loc_180034F4B
0x180034f3b  test    r12d, r12d
0x180034f3e  jz      short loc_180034F4B
0x180034f40  test    ebx, ebx
0x180034f42  mov     eax, 1
0x180034f47  cmovz   r14d, eax
0x180034f4b  mov     rcx, [rbp+57h+pSid1]; pSid
0x180034f4f  call    cs:__imp_FreeSid
0x180034f55  mov     eax, r14d
0x180034f58  mov     rcx, [rbp+57h+var_50]
0x180034f5c  xor     rcx, rsp; StackCookie
0x180034f5f  call    __security_check_cookie
0x180034f64  add     rsp, 0A8h
0x180034f6b  pop     r15
0x180034f6d  pop     r14
0x180034f6f  pop     r13
0x180034f71  pop     r12
0x180034f73  pop     rdi
0x180034f74  pop     rsi
0x180034f75  pop     rbx
0x180034f76  pop     rbp
0x180034f77  retn
```
