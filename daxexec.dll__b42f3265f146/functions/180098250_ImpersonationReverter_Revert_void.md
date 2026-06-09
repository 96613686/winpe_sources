# ImpersonationReverter::Revert(void)

- ea: `0x180098250`
- end: `0x18009836d`
- name: `?Revert@ImpersonationReverter@@SA?AU1@XZ`
- size: `285`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800249ec`
- `0x180097f68`
- `0x18009815c`

## callees

- `0x180014e74`
- `0x1800210fc`
- `0x180098250`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800982ee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800982ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800982cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098302`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800982cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098302`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180098285`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180098285`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800982a2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800982a2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18009831b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18009831b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800982e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800982e0`

## string_xrefs

- `0x180098341`: `onecore\base\appmodel\execmodel\desktopappx\sharedlib\securityutils.cpp`
- `0x18009835b`: `onecore\base\appmodel\execmodel\desktopappx\sharedlib\securityutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ImpersonationReverter::Revert(__int64 a1)
{
  HANDLE CurrentThread; // rax
  BOOL v3; // r15d
  void *v4; // r14
  void *v5; // rbp
  DWORD LastError; // ebx
  DWORD v7; // eax
  const char *v8; // r9
  unsigned int v10; // [rsp+20h] [rbp-58h]
  void **v11; // [rsp+28h] [rbp-50h]
  void *TokenHandle; // [rsp+30h] [rbp-48h] BYREF
  char v13; // [rsp+38h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  *(_BYTE *)a1 = 1;
  *(_QWORD *)(a1 + 8) = 0;
  v11 = (void **)(a1 + 8);
  TokenHandle = 0;
  v13 = 1;
  CurrentThread = GetCurrentThread();
  v3 = OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle);
  if ( v13 )
  {
    v4 = TokenHandle;
    v5 = *v11;
    if ( (char *)*v11 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      LastError = GetLastError();
      CloseHandle(v5);
      SetLastError(LastError);
    }
    *v11 = v4;
  }
  if ( v3 )
  {
    if ( !SetThreadToken(0, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x3E,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\securityutils.cpp",
        v8);
  }
  else
  {
    v7 = GetLastError();
    if ( v7 != 1008 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x3A,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\securityutils.cpp",
        (const char *)v7,
        v10);
  }
  return a1;
}

```

## disassembly

```asm
0x180098250  mov     [rsp+arg_0], rcx
0x180098255  push    rbx
0x180098256  push    rbp
0x180098257  push    rsi
0x180098258  push    rdi
0x180098259  push    r14
0x18009825b  push    r15
0x18009825d  sub     rsp, 48h
0x180098261  mov     rsi, rcx
0x180098264  mov     byte ptr [rcx], 1
0x180098267  lea     rax, [rcx+8]
0x18009826b  mov     qword ptr [rax], 0
0x180098272  mov     [rsp+78h+var_50], rax
0x180098277  mov     [rsp+78h+TokenHandle], 0
0x180098280  mov     [rsp+78h+var_40], 1
0x180098285  call    cs:__imp_GetCurrentThread
0x18009828c  nop     dword ptr [rax+rax+00h]
0x180098291  lea     r9, [rsp+78h+TokenHandle]; TokenHandle
0x180098296  mov     edx, 0Ch; DesiredAccess
0x18009829b  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x18009829f  mov     rcx, rax; ThreadHandle
0x1800982a2  call    cs:__imp_OpenThreadToken
0x1800982a9  nop     dword ptr [rax+rax+00h]
0x1800982ae  mov     r15d, eax
0x1800982b1  cmp     [rsp+78h+var_40], 0
0x1800982b6  jz      short loc_1800982FD
0x1800982b8  mov     r14, [rsp+78h+TokenHandle]
0x1800982bd  mov     rdi, [rsp+78h+var_50]
0x1800982c2  mov     rbp, [rdi]
0x1800982c5  lea     rdx, [rbp-1]
0x1800982c9  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800982cd  ja      short loc_1800982FA
0x1800982cf  call    cs:__imp_GetLastError
0x1800982d6  nop     dword ptr [rax+rax+00h]
0x1800982db  mov     ebx, eax
0x1800982dd  mov     rcx, rbp; hObject
0x1800982e0  call    cs:__imp_CloseHandle
0x1800982e7  nop     dword ptr [rax+rax+00h]
0x1800982ec  mov     ecx, ebx; dwErrCode
0x1800982ee  call    cs:__imp_SetLastError
0x1800982f5  nop     dword ptr [rax+rax+00h]
0x1800982fa  mov     [rdi], r14
0x1800982fd  test    r15d, r15d
0x180098300  jnz     short loc_180098317
0x180098302  call    cs:__imp_GetLastError
0x180098309  nop     dword ptr [rax+rax+00h]
0x18009830e  cmp     eax, 3F0h
0x180098313  jnz     short loc_180098353
0x180098315  jmp     short loc_180098330
0x180098317  xor     edx, edx; Token
0x180098319  xor     ecx, ecx; Thread
0x18009831b  call    cs:__imp_SetThreadToken
0x180098322  nop     dword ptr [rax+rax+00h]
0x180098327  mov     rcx, [rsp+78h]; this
0x18009832c  test    eax, eax
0x18009832e  jz      short loc_180098341
0x180098330  mov     rax, rsi
0x180098333  add     rsp, 48h
0x180098337  pop     r15
0x180098339  pop     r14
0x18009833b  pop     rdi
0x18009833c  pop     rsi
0x18009833d  pop     rbp
0x18009833e  pop     rbx
0x18009833f  retn
0x180098341  lea     r8, aOnecoreBaseApp_16; "onecore\\base\\appmodel\\execmodel\\des"...
0x180098348  mov     edx, 3Eh ; '>'; void *
0x18009834d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180098353  mov     rcx, [rsp+78h]; this
0x180098358  mov     r9d, eax; char *
0x18009835b  lea     r8, aOnecoreBaseApp_16; "onecore\\base\\appmodel\\execmodel\\des"...
0x180098362  mov     edx, 3Ah ; ':'; void *
0x180098367  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
