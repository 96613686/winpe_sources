# IsUserMemberOfSID(void *,int *,int *)

- ea: `0x18002c88c`
- end: `0x18002ca95`
- name: `?IsUserMemberOfSID@@YAJPEAXPEAH1@Z`
- size: `521`
- prototype: `__int64 __fastcall(PSID pSid1, int *, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002c78c`

## callees

- `0x18002c88c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c8fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c928`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c95e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c9b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ca1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c8fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c928`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c95e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c9b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ca1c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002c8e2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002c8e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002c90e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002c90e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002c8cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002c8cd`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002c91e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002c91e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c974`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ca77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c974`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ca77`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002ca45`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002ca45`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002c9a8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002ca12`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002c9a8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002ca12`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18002c94c`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18002c94c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c9d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ca5a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c9d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ca5a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002ca68`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002ca68`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002c9e4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002c9e4`

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
0x18002c88c  mov     qword ptr [rsp-38h+TokenInformationLength], r8
0x18002c891  push    rbp
0x18002c892  push    rbx
0x18002c893  push    rsi
0x18002c894  push    rdi
0x18002c895  push    r13
0x18002c897  push    r14
0x18002c899  push    r15
0x18002c89b  mov     rbp, rsp
0x18002c89e  sub     rsp, 30h
0x18002c8a2  mov     [rbp+TokenHandle], 0
0x18002c8aa  mov     r14, rdx
0x18002c8ad  mov     [rbp+TokenInformationLength], 0
0x18002c8b4  mov     r15, rcx
0x18002c8b7  test    rcx, rcx
0x18002c8ba  jz      loc_18002CA81
0x18002c8c0  test    rdx, rdx
0x18002c8c3  jz      loc_18002CA81
0x18002c8c9  xor     edi, edi
0x18002c8cb  mov     [rdx], edi
0x18002c8cd  call    cs:__imp_GetCurrentThread
0x18002c8d3  lea     esi, [rdi+8]
0x18002c8d6  xor     r8d, r8d; OpenAsSelf
0x18002c8d9  mov     rcx, rax; ThreadHandle
0x18002c8dc  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18002c8e0  mov     edx, esi; DesiredAccess
0x18002c8e2  call    cs:__imp_OpenThreadToken
0x18002c8e8  lea     ebx, [rdi+2]
0x18002c8eb  mov     r13d, 80070000h
0x18002c8f1  test    eax, eax
0x18002c8f3  jnz     loc_18002C992
0x18002c8f9  mov     [rbp+TokenHandle], rdi
0x18002c8fd  call    cs:__imp_GetLastError
0x18002c903  cmp     eax, 3F0h
0x18002c908  jnz     short loc_18002C97C
0x18002c90a  mov     [rbp+ExistingTokenHandle], rdi
0x18002c90e  call    cs:__imp_GetCurrentProcess
0x18002c914  mov     rcx, rax; ProcessHandle
0x18002c917  lea     r8, [rbp+ExistingTokenHandle]; TokenHandle
0x18002c91b  lea     edx, [rdi+0Ah]; DesiredAccess
0x18002c91e  call    cs:__imp_OpenProcessToken
0x18002c924  test    eax, eax
0x18002c926  jnz     short loc_18002C942
0x18002c928  call    cs:__imp_GetLastError
0x18002c92e  mov     edi, eax
0x18002c930  test    eax, eax
0x18002c932  jle     short loc_18002C93A
0x18002c934  movzx   edi, ax
0x18002c937  or      edi, r13d
0x18002c93a  test    edi, edi
0x18002c93c  js      loc_18002CA6E
0x18002c942  mov     rcx, [rbp+ExistingTokenHandle]; ExistingTokenHandle
0x18002c946  lea     r8, [rbp+TokenHandle]; DuplicateTokenHandle
0x18002c94a  mov     edx, ebx; ImpersonationLevel
0x18002c94c  call    cs:__imp_DuplicateToken
0x18002c952  test    eax, eax
0x18002c954  jnz     short loc_18002C970
0x18002c956  mov     [rbp+TokenHandle], 0
0x18002c95e  call    cs:__imp_GetLastError
0x18002c964  mov     edi, eax
0x18002c966  test    eax, eax
0x18002c968  jle     short loc_18002C970
0x18002c96a  movzx   edi, ax
0x18002c96d  or      edi, r13d
0x18002c970  mov     rcx, [rbp+ExistingTokenHandle]; hObject
0x18002c974  call    cs:__imp_CloseHandle
0x18002c97a  jmp     short loc_18002C98A
0x18002c97c  test    eax, eax
0x18002c97e  jg      short loc_18002C984
0x18002c980  mov     edi, eax
0x18002c982  jmp     short loc_18002C98A
0x18002c984  movzx   edi, ax
0x18002c987  or      edi, r13d
0x18002c98a  test    edi, edi
0x18002c98c  js      loc_18002CA6E
0x18002c992  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18002c996  lea     rax, [rbp+TokenInformationLength]
0x18002c99a  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18002c99e  xor     r8d, r8d; TokenInformation
0x18002c9a1  mov     edx, ebx; TokenInformationClass
0x18002c9a3  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18002c9a8  call    cs:__imp_GetTokenInformation
0x18002c9ae  test    eax, eax
0x18002c9b0  jnz     short loc_18002C9D3
0x18002c9b2  call    cs:__imp_GetLastError
0x18002c9b8  cmp     eax, 7Ah ; 'z'
0x18002c9bb  jz      short loc_18002C9CB
0x18002c9bd  test    eax, eax
0x18002c9bf  jg      short loc_18002C9C5
0x18002c9c1  mov     edi, eax
0x18002c9c3  jmp     short loc_18002C9CB
0x18002c9c5  movzx   edi, ax
0x18002c9c8  or      edi, r13d
0x18002c9cb  test    edi, edi
0x18002c9cd  js      loc_18002CA6E
0x18002c9d3  mov     ebx, [rbp+TokenInformationLength]
0x18002c9d6  call    cs:__imp_GetProcessHeap
0x18002c9dc  mov     r8d, ebx; dwBytes
0x18002c9df  mov     edx, esi; dwFlags
0x18002c9e1  mov     rcx, rax; hHeap
0x18002c9e4  call    cs:__imp_HeapAlloc
0x18002c9ea  mov     rsi, rax
0x18002c9ed  test    rax, rax
0x18002c9f0  jnz     short loc_18002C9F9
0x18002c9f2  mov     edi, 8007000Eh
0x18002c9f7  jmp     short loc_18002CA6E
0x18002c9f9  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18002c9fd  lea     rax, [rbp+TokenInformationLength]
0x18002ca01  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18002ca05  mov     r8, rsi; TokenInformation
0x18002ca08  mov     edx, 2; TokenInformationClass
0x18002ca0d  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18002ca12  call    cs:__imp_GetTokenInformation
0x18002ca18  test    eax, eax
0x18002ca1a  jnz     short loc_18002CA32
0x18002ca1c  call    cs:__imp_GetLastError
0x18002ca22  mov     edi, eax
0x18002ca24  test    eax, eax
0x18002ca26  jle     short loc_18002CA2E
0x18002ca28  movzx   edi, ax
0x18002ca2b  or      edi, r13d
0x18002ca2e  test    edi, edi
0x18002ca30  js      short loc_18002CA5A
0x18002ca32  xor     ebx, ebx
0x18002ca34  cmp     ebx, [rsi]
0x18002ca36  jnb     short loc_18002CA5A
0x18002ca38  mov     edx, ebx
0x18002ca3a  mov     rcx, r15; pSid1
0x18002ca3d  add     rdx, rdx
0x18002ca40  mov     rdx, [rsi+rdx*8+8]; pSid2
0x18002ca45  call    cs:__imp_EqualSid
0x18002ca4b  test    eax, eax
0x18002ca4d  jnz     short loc_18002CA53
0x18002ca4f  inc     ebx
0x18002ca51  jmp     short loc_18002CA34
0x18002ca53  mov     dword ptr [r14], 1
0x18002ca5a  call    cs:__imp_GetProcessHeap
0x18002ca60  mov     r8, rsi; lpMem
0x18002ca63  xor     edx, edx; dwFlags
0x18002ca65  mov     rcx, rax; hHeap
0x18002ca68  call    cs:__imp_HeapFree
0x18002ca6e  mov     rcx, [rbp+TokenHandle]; hObject
0x18002ca72  test    rcx, rcx
0x18002ca75  jz      short loc_18002CA7D
0x18002ca77  call    cs:__imp_CloseHandle
0x18002ca7d  mov     eax, edi
0x18002ca7f  jmp     short loc_18002CA86
0x18002ca81  mov     eax, 80070057h
0x18002ca86  add     rsp, 30h
0x18002ca8a  pop     r15
0x18002ca8c  pop     r14
0x18002ca8e  pop     r13
0x18002ca90  pop     rdi
0x18002ca91  pop     rsi
0x18002ca92  pop     rbx
0x18002ca93  pop     rbp
0x18002ca94  retn
```
