# _WorkItemWrapper(_TP_CALLBACK_INSTANCE *,void *)

- ea: `0x180008b30`
- end: `0x180008c74`
- name: `?_WorkItemWrapper@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z`
- size: `324`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, _BYTE *Context)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180008b30`
- `0x180009b70`
- `0x18000a9b8`
- `0x18002d2d8`
- `0x18002db38`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008b7e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008b7e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008b70`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008b70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008bc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008bc4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180008bba`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180008bba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008ba1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008ba1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008c69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008c69`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180008bd8`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180008bd8`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x180008b48`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x180008b48`

## string_xrefs

- `0x180008c16`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x180008c46`: `onecore\ds\security\gina\profile\proflib\sid.cpp`

## pseudocode

```c
void __fastcall _WorkItemWrapper(PTP_CALLBACK_INSTANCE Instance, _BYTE *Context)
{
  void *v3; // rbx
  void *v4; // rcx
  HANDLE ProcessHeap; // rax
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  const char *v8; // r9
  int v9; // ebx
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF
  void *v13; // [rsp+40h] [rbp+18h] BYREF

  if ( !Context )
    return;
  if ( (Context[24] & 0x10) != 0 )
    CallbackMayRunLong(Instance);
  v3 = (void *)*((_QWORD *)Context + 2);
  if ( v3 )
  {
    v13 = 0;
    TokenHandle = 0;
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 0x2000Cu, 1, &TokenHandle) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( LastError != -2147023888 && LastError < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2A,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
          (const char *)(unsigned int)LastError,
          v10);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        goto LABEL_6;
      }
    }
    if ( ImpersonateLoggedOnUser(v3) )
    {
      v13 = TokenHandle;
    }
    else
    {
      v9 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x2D,
             (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
             v8);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      if ( v9 < 0 )
        goto LABEL_6;
    }
    (*(void (__fastcall **)(_QWORD))Context)(*((_QWORD *)Context + 1));
    RevertToUser(&v13);
  }
  else
  {
    (*(void (__fastcall **)(_QWORD))Context)(*((_QWORD *)Context + 1));
  }
LABEL_6:
  v4 = (void *)*((_QWORD *)Context + 2);
  if ( v4 )
    CloseHandle(v4);
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, Context);
}

```

## disassembly

```asm
0x180008b30  test    rdx, rdx
0x180008b33  jz      short locret_180008B8E
0x180008b35  mov     [rsp+arg_0], rbx
0x180008b3a  push    rdi; int
0x180008b3b  sub     rsp, 20h
0x180008b3f  test    byte ptr [rdx+18h], 10h
0x180008b43  mov     rdi, rdx
0x180008b46  jz      short loc_180008B4E
0x180008b48  call    cs:__imp_CallbackMayRunLong
0x180008b4e  mov     rbx, [rdi+10h]
0x180008b52  test    rbx, rbx
0x180008b55  jnz     short loc_180008B8F
0x180008b57  mov     rcx, [rdi+8]
0x180008b5b  mov     rax, [rdi]
0x180008b5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b63  mov     rcx, [rdi+10h]; hObject
0x180008b67  test    rcx, rcx
0x180008b6a  jnz     loc_180008C69
0x180008b70  call    cs:__imp_GetProcessHeap
0x180008b76  mov     r8, rdi; lpMem
0x180008b79  xor     edx, edx; dwFlags
0x180008b7b  mov     rcx, rax; hHeap
0x180008b7e  call    cs:__imp_HeapFree
0x180008b84  mov     rbx, [rsp+28h+arg_0]
0x180008b89  add     rsp, 20h
0x180008b8d  pop     rdi
0x180008b8e  retn
0x180008b8f  mov     [rsp+28h+arg_10], 0
0x180008b98  mov     [rsp+28h+TokenHandle], 0
0x180008ba1  call    cs:__imp_GetCurrentThread
0x180008ba7  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180008bac  mov     edx, 2000Ch; DesiredAccess
0x180008bb1  mov     rcx, rax; ThreadHandle
0x180008bb4  mov     r8d, 1; OpenAsSelf
0x180008bba  call    cs:__imp_OpenThreadToken
0x180008bc0  test    eax, eax
0x180008bc2  jnz     short loc_180008BD5
0x180008bc4  call    cs:__imp_GetLastError
0x180008bca  test    eax, eax
0x180008bcc  jg      short loc_180008C07
0x180008bce  cmp     eax, 800703F0h
0x180008bd3  jnz     short loc_180008C3D
0x180008bd5  mov     rcx, rbx; hToken
0x180008bd8  call    cs:__imp_ImpersonateLoggedOnUser
0x180008bde  test    eax, eax
0x180008be0  jz      short loc_180008C11
0x180008be2  mov     rax, [rsp+28h+TokenHandle]
0x180008be7  mov     [rsp+28h+arg_10], rax
0x180008bec  mov     rcx, [rdi+8]
0x180008bf0  mov     rax, [rdi]
0x180008bf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bf8  lea     rcx, [rsp+28h+arg_10]; void **
0x180008bfd  call    ?RevertToUser@@YAJPEAPEAX@Z; RevertToUser(void * *)
0x180008c02  jmp     loc_180008B63
0x180008c07  movzx   eax, ax
0x180008c0a  or      eax, 80070000h
0x180008c0f  jmp     short loc_180008BCE
0x180008c11  mov     rcx, [rsp+28h]; this
0x180008c16  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x180008c1d  mov     edx, 2Dh ; '-'; void *
0x180008c22  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008c27  lea     rcx, [rsp+28h+TokenHandle]
0x180008c2c  mov     ebx, eax
0x180008c2e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180008c33  test    ebx, ebx
0x180008c35  js      loc_180008B63
0x180008c3b  jmp     short loc_180008BEC
0x180008c3d  test    eax, eax
0x180008c3f  jns     short loc_180008BD5
0x180008c41  mov     rcx, [rsp+28h]; this
0x180008c46  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x180008c4d  mov     r9d, eax; char *
0x180008c50  mov     edx, 2Ah ; '*'; void *
0x180008c55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008c5a  lea     rcx, [rsp+28h+TokenHandle]
0x180008c5f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180008c64  jmp     loc_180008B63
0x180008c69  call    cs:__imp_CloseHandle
0x180008c6f  jmp     loc_180008B70
```
