# ClusterADLdap::s_GetSidOfCallingThread(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x1800a6fe8`
- end: `0x1800a71af`
- name: `?s_GetSidOfCallingThread@ClusterADLdap@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `455`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180071ce4`

## callees

- `0x180029978`
- `0x180038494`
- `0x1800a6fe8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7027`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a708f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a70eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a711b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7027`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a708f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a70eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a711b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a7005`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a7005`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800a7043`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800a7043`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800a701d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800a701d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800a7034`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800a7034`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a70ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a7158`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a7195`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a70ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a7158`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a7195`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a7076`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a7076`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800a706b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800a70e1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800a706b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800a70e1`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800a7111`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800a7111`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ClusterADLdap::s_GetSidOfCallingThread(__int64 a1)
{
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  void *v4; // rcx
  PSID *v5; // rdi
  signed int v6; // eax
  unsigned int v7; // ebx
  void *v8; // rcx
  bool v9; // cc
  PSID *v10; // rcx
  signed int v11; // eax
  __int64 v12; // r8
  signed int LastError; // eax
  LPWSTR v14; // rcx
  char *v15; // rcx
  LPWSTR v16; // rcx
  char *v17; // rcx
  DWORD TokenInformationLength; // [rsp+68h] [rbp+28h] BYREF
  void *TokenHandle; // [rsp+70h] [rbp+30h] BYREF
  LPWSTR StringSid; // [rsp+78h] [rbp+38h] BYREF

  TokenInformationLength = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    v4 = TokenHandle;
  }
  else
  {
    if ( GetLastError() == 1008 )
    {
      CurrentProcess = GetCurrentProcess();
      OpenProcessToken(CurrentProcess, 8u, &TokenHandle);
    }
    v4 = TokenHandle;
    if ( !TokenHandle )
      goto LABEL_8;
  }
  GetTokenInformation(v4, TokenUser, 0, 0, &TokenInformationLength);
  v5 = (PSID *)LocalAlloc(0, TokenInformationLength);
  CTSmartPtr_PolicyLocalMem::DestroyMem(0);
  if ( v5 )
  {
    if ( GetTokenInformation(TokenHandle, TokenUser, v5, TokenInformationLength, &TokenInformationLength) )
    {
      StringSid = 0;
      if ( ConvertSidToStringSidW(*v5, &StringSid) )
      {
        std::wstring::assign(a1, StringSid, v12);
        v16 = StringSid;
        StringSid = 0;
        CTSmartPtr_PolicyLocalMem::DestroyMem(v16);
        v17 = (char *)TokenHandle;
        TokenHandle = 0;
        if ( (unsigned __int64)(v17 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(v17);
        v7 = 0;
        goto LABEL_25;
      }
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      v14 = StringSid;
      StringSid = 0;
      CTSmartPtr_PolicyLocalMem::DestroyMem(v14);
    }
    else
    {
      v11 = GetLastError();
      v7 = v11;
      if ( v11 > 0 )
        v7 = (unsigned __int16)v11 | 0x80070000;
    }
    v15 = (char *)TokenHandle;
    TokenHandle = 0;
    if ( (unsigned __int64)(v15 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v15);
LABEL_25:
    v10 = v5;
    goto LABEL_26;
  }
LABEL_8:
  v6 = GetLastError();
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  v8 = TokenHandle;
  v9 = (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
  TokenHandle = 0;
  if ( v9 )
    CloseHandle(v8);
  v10 = 0;
LABEL_26:
  CTSmartPtr_PolicyLocalMem::DestroyMem(v10);
  return v7;
}

```

## disassembly

```asm
0x1800a6fe8  push    rbp
0x1800a6fea  push    rbx
0x1800a6feb  push    rdi
0x1800a6fec  mov     rbp, rsp
0x1800a6fef  sub     rsp, 40h
0x1800a6ff3  mov     rbx, rcx
0x1800a6ff6  mov     [rbp+TokenInformationLength], 0
0x1800a6ffd  mov     [rbp+TokenHandle], 0
0x1800a7005  call    cs:__imp_GetCurrentThread
0x1800a700b  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800a700f  mov     edi, 8
0x1800a7014  lea     r8d, [rdi-7]; OpenAsSelf
0x1800a7018  mov     edx, edi; DesiredAccess
0x1800a701a  mov     rcx, rax; ThreadHandle
0x1800a701d  call    cs:__imp_OpenThreadToken
0x1800a7023  test    eax, eax
0x1800a7025  jnz     short loc_1800A7054
0x1800a7027  call    cs:__imp_GetLastError
0x1800a702d  cmp     eax, 3F0h
0x1800a7032  jnz     short loc_1800A7049
0x1800a7034  call    cs:__imp_GetCurrentProcess
0x1800a703a  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800a703e  mov     edx, edi; DesiredAccess
0x1800a7040  mov     rcx, rax; ProcessHandle
0x1800a7043  call    cs:__imp_OpenProcessToken
0x1800a7049  mov     rcx, [rbp+TokenHandle]
0x1800a704d  test    rcx, rcx
0x1800a7050  jnz     short loc_1800A7058
0x1800a7052  jmp     short loc_1800A708F
0x1800a7054  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800a7058  lea     rax, [rbp+TokenInformationLength]
0x1800a705c  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x1800a7061  xor     r9d, r9d; TokenInformationLength
0x1800a7064  xor     r8d, r8d; TokenInformation
0x1800a7067  lea     edx, [r9+1]; TokenInformationClass
0x1800a706b  call    cs:__imp_GetTokenInformation
0x1800a7071  mov     edx, [rbp+TokenInformationLength]; uBytes
0x1800a7074  xor     ecx, ecx; uFlags
0x1800a7076  call    cs:__imp_LocalAlloc
0x1800a707c  mov     rdi, rax
0x1800a707f  xor     ecx, ecx; void *
0x1800a7081  call    ?DestroyMem@CTSmartPtr_PolicyLocalMem@@SAHPEAX@Z; CTSmartPtr_PolicyLocalMem::DestroyMem(void *)
0x1800a7086  mov     [rbp+var_10], rdi
0x1800a708a  test    rdi, rdi
0x1800a708d  jnz     short loc_1800A70C8
0x1800a708f  call    cs:__imp_GetLastError
0x1800a7095  test    eax, eax
0x1800a7097  mov     ebx, eax
0x1800a7099  jle     short loc_1800A70A4
0x1800a709b  movzx   ebx, ax
0x1800a709e  or      ebx, 80070000h
0x1800a70a4  mov     rcx, [rbp+TokenHandle]; hObject
0x1800a70a8  lea     rax, [rcx-1]
0x1800a70ac  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800a70b0  mov     [rbp+TokenHandle], 0
0x1800a70b8  ja      short loc_1800A70C1
0x1800a70ba  call    cs:__imp_CloseHandle
0x1800a70c0  nop
0x1800a70c1  xor     ecx, ecx
0x1800a70c3  jmp     loc_1800A71A0
0x1800a70c8  lea     rax, [rbp+TokenInformationLength]
0x1800a70cc  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x1800a70d1  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800a70d5  mov     r8, rdi; TokenInformation
0x1800a70d8  mov     edx, 1; TokenInformationClass
0x1800a70dd  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800a70e1  call    cs:__imp_GetTokenInformation
0x1800a70e7  test    eax, eax
0x1800a70e9  jnz     short loc_1800A7102
0x1800a70eb  call    cs:__imp_GetLastError
0x1800a70f1  mov     ebx, eax
0x1800a70f3  test    eax, eax
0x1800a70f5  jle     short loc_1800A7142
0x1800a70f7  movzx   ebx, ax
0x1800a70fa  or      ebx, 80070000h
0x1800a7100  jmp     short loc_1800A7142
0x1800a7102  mov     [rbp+StringSid], 0
0x1800a710a  lea     rdx, [rbp+StringSid]; StringSid
0x1800a710e  mov     rcx, [rdi]; Sid
0x1800a7111  call    cs:__imp_ConvertSidToStringSidW
0x1800a7117  test    eax, eax
0x1800a7119  jnz     short loc_1800A7160
0x1800a711b  call    cs:__imp_GetLastError
0x1800a7121  mov     ebx, eax
0x1800a7123  test    eax, eax
0x1800a7125  jle     short loc_1800A7130
0x1800a7127  movzx   ebx, ax
0x1800a712a  or      ebx, 80070000h
0x1800a7130  mov     rcx, [rbp+StringSid]; void *
0x1800a7134  mov     [rbp+StringSid], 0
0x1800a713c  call    ?DestroyMem@CTSmartPtr_PolicyLocalMem@@SAHPEAX@Z; CTSmartPtr_PolicyLocalMem::DestroyMem(void *)
0x1800a7141  nop
0x1800a7142  mov     rcx, [rbp+TokenHandle]; hObject
0x1800a7146  mov     [rbp+TokenHandle], 0
0x1800a714e  lea     rax, [rcx-1]
0x1800a7152  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800a7156  ja      short loc_1800A719D
0x1800a7158  call    cs:__imp_CloseHandle
0x1800a715e  jmp     short loc_1800A719D
0x1800a7160  mov     rdx, [rbp+StringSid]
0x1800a7164  mov     rcx, rbx
0x1800a7167  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x1800a716c  nop
0x1800a716d  mov     rcx, [rbp+StringSid]; void *
0x1800a7171  mov     [rbp+StringSid], 0
0x1800a7179  call    ?DestroyMem@CTSmartPtr_PolicyLocalMem@@SAHPEAX@Z; CTSmartPtr_PolicyLocalMem::DestroyMem(void *)
0x1800a717e  nop
0x1800a717f  mov     rcx, [rbp+TokenHandle]; hObject
0x1800a7183  mov     [rbp+TokenHandle], 0
0x1800a718b  lea     rax, [rcx-1]
0x1800a718f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800a7193  ja      short loc_1800A719B
0x1800a7195  call    cs:__imp_CloseHandle
0x1800a719b  xor     ebx, ebx
0x1800a719d  mov     rcx, rdi; void *
0x1800a71a0  call    ?DestroyMem@CTSmartPtr_PolicyLocalMem@@SAHPEAX@Z; CTSmartPtr_PolicyLocalMem::DestroyMem(void *)
0x1800a71a5  mov     eax, ebx
0x1800a71a7  add     rsp, 40h
0x1800a71ab  pop     rdi
0x1800a71ac  pop     rbx
0x1800a71ad  pop     rbp
0x1800a71ae  retn
```
