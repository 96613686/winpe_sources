# IsUserMemberOfSID(void *,int *,int *)

- ea: `0x18003f604`
- end: `0x18003f83b`
- name: `?IsUserMemberOfSID@@YAJPEAXPEAH1@Z`
- size: `567`
- prototype: `__int64 __fastcall(PSID pSid1, int *, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180046544`

## callees

- `0x18003f604`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003f769`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003f769`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003f805`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003f805`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003f75b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003f7f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003f75b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003f7f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f682`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f6ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f6e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f737`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f7a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f682`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f6ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f6e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f737`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f7a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003f693`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003f693`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003f667`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003f667`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003f651`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003f651`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003f6a3`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003f6a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f6f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f814`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f6f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f814`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003f7ce`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003f7ce`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003f72d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003f79a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003f72d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003f79a`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18003f6d1`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18003f6d1`

## pseudocode

```c
__int64 __fastcall IsUserMemberOfSID(PSID pSid1, int *a2, unsigned int *a3)
{
  signed int v6; // edi
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  HANDLE CurrentProcess; // rax
  signed int v10; // eax
  signed int v11; // eax
  signed int v12; // eax
  DWORD v13; // ebx
  HANDLE ProcessHeap; // rax
  unsigned int *v15; // rsi
  signed int v16; // eax
  unsigned int i; // ebx
  HANDLE v18; // rax
  HANDLE ExistingTokenHandle; // [rsp+30h] [rbp-10h] BYREF
  DWORD TokenInformationLength; // [rsp+80h] [rbp+40h] BYREF
  void *TokenHandle; // [rsp+98h] [rbp+58h] BYREF

  TokenHandle = 0;
  TokenInformationLength = 0;
  if ( !pSid1 || !a2 )
    return 2147942487LL;
  v6 = 0;
  *a2 = 0;
  if ( a3 )
    *a3 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
    goto LABEL_19;
  TokenHandle = 0;
  LastError = GetLastError();
  if ( LastError == 1008 )
  {
    ExistingTokenHandle = 0;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0xAu, &ExistingTokenHandle) )
    {
      v10 = GetLastError();
      v6 = v10;
      if ( v10 > 0 )
        v6 = (unsigned __int16)v10 | 0x80070000;
      if ( v6 < 0 )
        goto LABEL_38;
    }
    if ( !DuplicateToken(ExistingTokenHandle, SecurityImpersonation, &TokenHandle) )
    {
      TokenHandle = 0;
      v11 = GetLastError();
      v6 = v11;
      if ( v11 > 0 )
        v6 = (unsigned __int16)v11 | 0x80070000;
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
  if ( v6 >= 0 )
  {
LABEL_19:
    if ( GetTokenInformation(TokenHandle, TokenGroups, 0, TokenInformationLength, &TokenInformationLength) )
      goto LABEL_25;
    v12 = GetLastError();
    if ( v12 != 122 )
    {
      if ( v12 > 0 )
        v6 = (unsigned __int16)v12 | 0x80070000;
      else
        v6 = v12;
    }
    if ( v6 >= 0 )
    {
LABEL_25:
      v13 = TokenInformationLength;
      ProcessHeap = GetProcessHeap();
      v15 = (unsigned int *)HeapAlloc(ProcessHeap, 8u, v13);
      if ( v15 )
      {
        if ( GetTokenInformation(TokenHandle, TokenGroups, v15, TokenInformationLength, &TokenInformationLength) )
          goto LABEL_31;
        v16 = GetLastError();
        v6 = v16;
        if ( v16 > 0 )
          v6 = (unsigned __int16)v16 | 0x80070000;
        if ( v6 >= 0 )
        {
LABEL_31:
          for ( i = 0; i < *v15; ++i )
          {
            if ( EqualSid(pSid1, *(PSID *)&v15[4 * i + 2]) )
            {
              *a2 = 1;
              if ( a3 )
                *a3 = (v15[4 * i + 4] >> 4) & 1;
              break;
            }
          }
        }
        v18 = GetProcessHeap();
        HeapFree(v18, 0, v15);
      }
      else
      {
        v6 = -2147024882;
      }
    }
  }
LABEL_38:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003f604  mov     [rsp-38h+arg_8], rbx
0x18003f609  push    rbp
0x18003f60a  push    rsi
0x18003f60b  push    rdi
0x18003f60c  push    r12
0x18003f60e  push    r13
0x18003f610  push    r14
0x18003f612  push    r15
0x18003f614  mov     rbp, rsp
0x18003f617  sub     rsp, 40h
0x18003f61b  mov     [rbp+TokenHandle], 0
0x18003f623  mov     r15, r8
0x18003f626  mov     [rbp+TokenInformationLength], 0
0x18003f62d  mov     r12, rdx
0x18003f630  mov     r13, rcx
0x18003f633  test    rcx, rcx
0x18003f636  jz      loc_18003F81E
0x18003f63c  test    rdx, rdx
0x18003f63f  jz      loc_18003F81E
0x18003f645  xor     edi, edi
0x18003f647  mov     [rdx], edi
0x18003f649  test    r8, r8
0x18003f64c  jz      short loc_18003F651
0x18003f64e  mov     [r8], edi
0x18003f651  call    cs:__imp_GetCurrentThread
0x18003f657  xor     r8d, r8d; OpenAsSelf
0x18003f65a  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18003f65e  mov     rcx, rax; ThreadHandle
0x18003f661  lea     esi, [r8+8]
0x18003f665  mov     edx, esi; DesiredAccess
0x18003f667  call    cs:__imp_OpenThreadToken
0x18003f66d  lea     ebx, [rsi-6]
0x18003f670  mov     r14d, 80070000h
0x18003f676  test    eax, eax
0x18003f678  jnz     loc_18003F717
0x18003f67e  mov     [rbp+TokenHandle], rdi
0x18003f682  call    cs:__imp_GetLastError
0x18003f688  cmp     eax, 3F0h
0x18003f68d  jnz     short loc_18003F701
0x18003f68f  mov     [rbp+ExistingTokenHandle], rdi
0x18003f693  call    cs:__imp_GetCurrentProcess
0x18003f699  mov     rcx, rax; ProcessHandle
0x18003f69c  lea     r8, [rbp+ExistingTokenHandle]; TokenHandle
0x18003f6a0  lea     edx, [rsi+2]; DesiredAccess
0x18003f6a3  call    cs:__imp_OpenProcessToken
0x18003f6a9  test    eax, eax
0x18003f6ab  jnz     short loc_18003F6C7
0x18003f6ad  call    cs:__imp_GetLastError
0x18003f6b3  mov     edi, eax
0x18003f6b5  test    eax, eax
0x18003f6b7  jle     short loc_18003F6BF
0x18003f6b9  movzx   edi, ax
0x18003f6bc  or      edi, r14d
0x18003f6bf  test    edi, edi
0x18003f6c1  js      loc_18003F80B
0x18003f6c7  mov     rcx, [rbp+ExistingTokenHandle]; ExistingTokenHandle
0x18003f6cb  lea     r8, [rbp+TokenHandle]; DuplicateTokenHandle
0x18003f6cf  mov     edx, ebx; ImpersonationLevel
0x18003f6d1  call    cs:__imp_DuplicateToken
0x18003f6d7  test    eax, eax
0x18003f6d9  jnz     short loc_18003F6F5
0x18003f6db  mov     [rbp+TokenHandle], 0
0x18003f6e3  call    cs:__imp_GetLastError
0x18003f6e9  mov     edi, eax
0x18003f6eb  test    eax, eax
0x18003f6ed  jle     short loc_18003F6F5
0x18003f6ef  movzx   edi, ax
0x18003f6f2  or      edi, r14d
0x18003f6f5  mov     rcx, [rbp+ExistingTokenHandle]; hObject
0x18003f6f9  call    cs:__imp_CloseHandle
0x18003f6ff  jmp     short loc_18003F70F
0x18003f701  test    eax, eax
0x18003f703  jg      short loc_18003F709
0x18003f705  mov     edi, eax
0x18003f707  jmp     short loc_18003F70F
0x18003f709  movzx   edi, ax
0x18003f70c  or      edi, r14d
0x18003f70f  test    edi, edi
0x18003f711  js      loc_18003F80B
0x18003f717  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18003f71b  lea     rax, [rbp+TokenInformationLength]
0x18003f71f  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18003f723  xor     r8d, r8d; TokenInformation
0x18003f726  mov     edx, ebx; TokenInformationClass
0x18003f728  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x18003f72d  call    cs:__imp_GetTokenInformation
0x18003f733  test    eax, eax
0x18003f735  jnz     short loc_18003F758
0x18003f737  call    cs:__imp_GetLastError
0x18003f73d  cmp     eax, 7Ah ; 'z'
0x18003f740  jz      short loc_18003F750
0x18003f742  test    eax, eax
0x18003f744  jg      short loc_18003F74A
0x18003f746  mov     edi, eax
0x18003f748  jmp     short loc_18003F750
0x18003f74a  movzx   edi, ax
0x18003f74d  or      edi, r14d
0x18003f750  test    edi, edi
0x18003f752  js      loc_18003F80B
0x18003f758  mov     ebx, [rbp+TokenInformationLength]
0x18003f75b  call    cs:__imp_GetProcessHeap
0x18003f761  mov     r8d, ebx; dwBytes
0x18003f764  mov     edx, esi; dwFlags
0x18003f766  mov     rcx, rax; hHeap
0x18003f769  call    cs:__imp_HeapAlloc
0x18003f76f  mov     rsi, rax
0x18003f772  test    rax, rax
0x18003f775  jnz     short loc_18003F781
0x18003f777  mov     edi, 8007000Eh
0x18003f77c  jmp     loc_18003F80B
0x18003f781  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18003f785  lea     rax, [rbp+TokenInformationLength]
0x18003f789  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18003f78d  mov     r8, rsi; TokenInformation
0x18003f790  mov     edx, 2; TokenInformationClass
0x18003f795  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x18003f79a  call    cs:__imp_GetTokenInformation
0x18003f7a0  test    eax, eax
0x18003f7a2  jnz     short loc_18003F7BA
0x18003f7a4  call    cs:__imp_GetLastError
0x18003f7aa  mov     edi, eax
0x18003f7ac  test    eax, eax
0x18003f7ae  jle     short loc_18003F7B6
0x18003f7b0  movzx   edi, ax
0x18003f7b3  or      edi, r14d
0x18003f7b6  test    edi, edi
0x18003f7b8  js      short loc_18003F7F7
0x18003f7ba  xor     ebx, ebx
0x18003f7bc  cmp     ebx, [rsi]
0x18003f7be  jnb     short loc_18003F7F7
0x18003f7c0  mov     r14d, ebx
0x18003f7c3  mov     rcx, r13; pSid1
0x18003f7c6  add     r14, r14
0x18003f7c9  mov     rdx, [rsi+r14*8+8]; pSid2
0x18003f7ce  call    cs:__imp_EqualSid
0x18003f7d4  test    eax, eax
0x18003f7d6  jnz     short loc_18003F7DC
0x18003f7d8  inc     ebx
0x18003f7da  jmp     short loc_18003F7BC
0x18003f7dc  mov     dword ptr [r12], 1
0x18003f7e4  test    r15, r15
0x18003f7e7  jz      short loc_18003F7F7
0x18003f7e9  mov     eax, [rsi+r14*8+10h]
0x18003f7ee  shr     eax, 4
0x18003f7f1  and     eax, 1
0x18003f7f4  mov     [r15], eax
0x18003f7f7  call    cs:__imp_GetProcessHeap
0x18003f7fd  mov     r8, rsi; lpMem
0x18003f800  xor     edx, edx; dwFlags
0x18003f802  mov     rcx, rax; hHeap
0x18003f805  call    cs:__imp_HeapFree
0x18003f80b  mov     rcx, [rbp+TokenHandle]; hObject
0x18003f80f  test    rcx, rcx
0x18003f812  jz      short loc_18003F81A
0x18003f814  call    cs:__imp_CloseHandle
0x18003f81a  mov     eax, edi
0x18003f81c  jmp     short loc_18003F823
0x18003f81e  mov     eax, 80070057h
0x18003f823  mov     rbx, [rsp+40h+arg_8]
0x18003f82b  add     rsp, 40h
0x18003f82f  pop     r15
0x18003f831  pop     r14
0x18003f833  pop     r13
0x18003f835  pop     r12
0x18003f837  pop     rdi
0x18003f838  pop     rsi
0x18003f839  pop     rbp
0x18003f83a  retn
```
