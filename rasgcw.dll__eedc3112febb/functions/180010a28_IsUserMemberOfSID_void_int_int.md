# IsUserMemberOfSID(void *,int *,int *)

- ea: `0x180010a28`
- end: `0x180010c31`
- name: `?IsUserMemberOfSID@@YAJPEAXPEAH1@Z`
- size: `521`
- prototype: `__int64 __fastcall(PSID pSid1, int *, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010928`

## callees

- `0x180010a28`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010a99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010ac4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010afa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010b4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010bb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010a99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010ac4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010afa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010b4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010bb8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010c04`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010c04`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010b80`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010b80`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010b72`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010bf6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010b72`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010bf6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180010a69`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180010a69`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180010aaa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180010aaa`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180010aba`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180010aba`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180010a7e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180010a7e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010b10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010c13`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010b10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010c13`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180010be1`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180010be1`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180010ae8`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180010ae8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010b44`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010bae`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010b44`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010bae`

## pseudocode

```c
__int64 __fastcall IsUserMemberOfSID(PSID pSid1, int *a2, int *a3)
{
  signed int v5; // edi
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  HANDLE CurrentProcess; // rax
  signed int v9; // eax
  signed int v10; // eax
  signed int v11; // eax
  DWORD v12; // ebx
  HANDLE ProcessHeap; // rax
  unsigned int *v14; // rsi
  signed int v15; // eax
  unsigned int i; // ebx
  HANDLE v17; // rax
  void *TokenHandle; // [rsp+70h] [rbp+40h] BYREF
  DWORD TokenInformationLength; // [rsp+80h] [rbp+50h] BYREF
  int v21; // [rsp+84h] [rbp+54h]
  HANDLE ExistingTokenHandle; // [rsp+88h] [rbp+58h] BYREF

  v21 = HIDWORD(a3);
  TokenHandle = 0;
  TokenInformationLength = 0;
  if ( !pSid1 || !a2 )
    return 2147942487LL;
  v5 = 0;
  *a2 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
    goto LABEL_17;
  TokenHandle = 0;
  LastError = GetLastError();
  if ( LastError == 1008 )
  {
    ExistingTokenHandle = 0;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0xAu, &ExistingTokenHandle) )
    {
      v9 = GetLastError();
      v5 = v9;
      if ( v9 > 0 )
        v5 = (unsigned __int16)v9 | 0x80070000;
      if ( v5 < 0 )
        goto LABEL_35;
    }
    if ( !DuplicateToken(ExistingTokenHandle, SecurityImpersonation, &TokenHandle) )
    {
      TokenHandle = 0;
      v10 = GetLastError();
      v5 = v10;
      if ( v10 > 0 )
        v5 = (unsigned __int16)v10 | 0x80070000;
    }
    CloseHandle(ExistingTokenHandle);
  }
  else if ( LastError > 0 )
  {
    v5 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    v5 = LastError;
  }
  if ( v5 >= 0 )
  {
LABEL_17:
    if ( GetTokenInformation(TokenHandle, TokenGroups, 0, TokenInformationLength, &TokenInformationLength) )
      goto LABEL_23;
    v11 = GetLastError();
    if ( v11 != 122 )
    {
      if ( v11 > 0 )
        v5 = (unsigned __int16)v11 | 0x80070000;
      else
        v5 = v11;
    }
    if ( v5 >= 0 )
    {
LABEL_23:
      v12 = TokenInformationLength;
      ProcessHeap = GetProcessHeap();
      v14 = (unsigned int *)HeapAlloc(ProcessHeap, 8u, v12);
      if ( v14 )
      {
        if ( GetTokenInformation(TokenHandle, TokenGroups, v14, TokenInformationLength, &TokenInformationLength) )
          goto LABEL_29;
        v15 = GetLastError();
        v5 = v15;
        if ( v15 > 0 )
          v5 = (unsigned __int16)v15 | 0x80070000;
        if ( v5 >= 0 )
        {
LABEL_29:
          for ( i = 0; i < *v14; ++i )
          {
            if ( EqualSid(pSid1, *(PSID *)&v14[4 * i + 2]) )
            {
              *a2 = 1;
              break;
            }
          }
        }
        v17 = GetProcessHeap();
        HeapFree(v17, 0, v14);
      }
      else
      {
        v5 = -2147024882;
      }
    }
  }
LABEL_35:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180010a28  mov     qword ptr [rsp-38h+TokenInformationLength], r8
0x180010a2d  push    rbp
0x180010a2e  push    rbx
0x180010a2f  push    rsi
0x180010a30  push    rdi
0x180010a31  push    r13
0x180010a33  push    r14
0x180010a35  push    r15
0x180010a37  mov     rbp, rsp
0x180010a3a  sub     rsp, 30h
0x180010a3e  mov     [rbp+TokenHandle], 0
0x180010a46  mov     r14, rdx
0x180010a49  mov     [rbp+TokenInformationLength], 0
0x180010a50  mov     r15, rcx
0x180010a53  test    rcx, rcx
0x180010a56  jz      loc_180010C1D
0x180010a5c  test    rdx, rdx
0x180010a5f  jz      loc_180010C1D
0x180010a65  xor     edi, edi
0x180010a67  mov     [rdx], edi
0x180010a69  call    cs:__imp_GetCurrentThread
0x180010a6f  lea     esi, [rdi+8]
0x180010a72  xor     r8d, r8d; OpenAsSelf
0x180010a75  mov     rcx, rax; ThreadHandle
0x180010a78  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180010a7c  mov     edx, esi; DesiredAccess
0x180010a7e  call    cs:__imp_OpenThreadToken
0x180010a84  lea     ebx, [rdi+2]
0x180010a87  mov     r13d, 80070000h
0x180010a8d  test    eax, eax
0x180010a8f  jnz     loc_180010B2E
0x180010a95  mov     [rbp+TokenHandle], rdi
0x180010a99  call    cs:__imp_GetLastError
0x180010a9f  cmp     eax, 3F0h
0x180010aa4  jnz     short loc_180010B18
0x180010aa6  mov     [rbp+ExistingTokenHandle], rdi
0x180010aaa  call    cs:__imp_GetCurrentProcess
0x180010ab0  mov     rcx, rax; ProcessHandle
0x180010ab3  lea     r8, [rbp+ExistingTokenHandle]; TokenHandle
0x180010ab7  lea     edx, [rdi+0Ah]; DesiredAccess
0x180010aba  call    cs:__imp_OpenProcessToken
0x180010ac0  test    eax, eax
0x180010ac2  jnz     short loc_180010ADE
0x180010ac4  call    cs:__imp_GetLastError
0x180010aca  mov     edi, eax
0x180010acc  test    eax, eax
0x180010ace  jle     short loc_180010AD6
0x180010ad0  movzx   edi, ax
0x180010ad3  or      edi, r13d
0x180010ad6  test    edi, edi
0x180010ad8  js      loc_180010C0A
0x180010ade  mov     rcx, [rbp+ExistingTokenHandle]; ExistingTokenHandle
0x180010ae2  lea     r8, [rbp+TokenHandle]; DuplicateTokenHandle
0x180010ae6  mov     edx, ebx; ImpersonationLevel
0x180010ae8  call    cs:__imp_DuplicateToken
0x180010aee  test    eax, eax
0x180010af0  jnz     short loc_180010B0C
0x180010af2  mov     [rbp+TokenHandle], 0
0x180010afa  call    cs:__imp_GetLastError
0x180010b00  mov     edi, eax
0x180010b02  test    eax, eax
0x180010b04  jle     short loc_180010B0C
0x180010b06  movzx   edi, ax
0x180010b09  or      edi, r13d
0x180010b0c  mov     rcx, [rbp+ExistingTokenHandle]; hObject
0x180010b10  call    cs:__imp_CloseHandle
0x180010b16  jmp     short loc_180010B26
0x180010b18  test    eax, eax
0x180010b1a  jg      short loc_180010B20
0x180010b1c  mov     edi, eax
0x180010b1e  jmp     short loc_180010B26
0x180010b20  movzx   edi, ax
0x180010b23  or      edi, r13d
0x180010b26  test    edi, edi
0x180010b28  js      loc_180010C0A
0x180010b2e  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180010b32  lea     rax, [rbp+TokenInformationLength]
0x180010b36  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180010b3a  xor     r8d, r8d; TokenInformation
0x180010b3d  mov     edx, ebx; TokenInformationClass
0x180010b3f  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180010b44  call    cs:__imp_GetTokenInformation
0x180010b4a  test    eax, eax
0x180010b4c  jnz     short loc_180010B6F
0x180010b4e  call    cs:__imp_GetLastError
0x180010b54  cmp     eax, 7Ah ; 'z'
0x180010b57  jz      short loc_180010B67
0x180010b59  test    eax, eax
0x180010b5b  jg      short loc_180010B61
0x180010b5d  mov     edi, eax
0x180010b5f  jmp     short loc_180010B67
0x180010b61  movzx   edi, ax
0x180010b64  or      edi, r13d
0x180010b67  test    edi, edi
0x180010b69  js      loc_180010C0A
0x180010b6f  mov     ebx, [rbp+TokenInformationLength]
0x180010b72  call    cs:__imp_GetProcessHeap
0x180010b78  mov     r8d, ebx; dwBytes
0x180010b7b  mov     edx, esi; dwFlags
0x180010b7d  mov     rcx, rax; hHeap
0x180010b80  call    cs:__imp_HeapAlloc
0x180010b86  mov     rsi, rax
0x180010b89  test    rax, rax
0x180010b8c  jnz     short loc_180010B95
0x180010b8e  mov     edi, 8007000Eh
0x180010b93  jmp     short loc_180010C0A
0x180010b95  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180010b99  lea     rax, [rbp+TokenInformationLength]
0x180010b9d  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180010ba1  mov     r8, rsi; TokenInformation
0x180010ba4  mov     edx, 2; TokenInformationClass
0x180010ba9  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180010bae  call    cs:__imp_GetTokenInformation
0x180010bb4  test    eax, eax
0x180010bb6  jnz     short loc_180010BCE
0x180010bb8  call    cs:__imp_GetLastError
0x180010bbe  mov     edi, eax
0x180010bc0  test    eax, eax
0x180010bc2  jle     short loc_180010BCA
0x180010bc4  movzx   edi, ax
0x180010bc7  or      edi, r13d
0x180010bca  test    edi, edi
0x180010bcc  js      short loc_180010BF6
0x180010bce  xor     ebx, ebx
0x180010bd0  cmp     ebx, [rsi]
0x180010bd2  jnb     short loc_180010BF6
0x180010bd4  mov     edx, ebx
0x180010bd6  mov     rcx, r15; pSid1
0x180010bd9  add     rdx, rdx
0x180010bdc  mov     rdx, [rsi+rdx*8+8]; pSid2
0x180010be1  call    cs:__imp_EqualSid
0x180010be7  test    eax, eax
0x180010be9  jnz     short loc_180010BEF
0x180010beb  inc     ebx
0x180010bed  jmp     short loc_180010BD0
0x180010bef  mov     dword ptr [r14], 1
0x180010bf6  call    cs:__imp_GetProcessHeap
0x180010bfc  mov     r8, rsi; lpMem
0x180010bff  xor     edx, edx; dwFlags
0x180010c01  mov     rcx, rax; hHeap
0x180010c04  call    cs:__imp_HeapFree
0x180010c0a  mov     rcx, [rbp+TokenHandle]; hObject
0x180010c0e  test    rcx, rcx
0x180010c11  jz      short loc_180010C19
0x180010c13  call    cs:__imp_CloseHandle
0x180010c19  mov     eax, edi
0x180010c1b  jmp     short loc_180010C22
0x180010c1d  mov     eax, 80070057h
0x180010c22  add     rsp, 30h
0x180010c26  pop     r15
0x180010c28  pop     r14
0x180010c2a  pop     r13
0x180010c2c  pop     rdi
0x180010c2d  pop     rsi
0x180010c2e  pop     rbx
0x180010c2f  pop     rbp
0x180010c30  retn
```
