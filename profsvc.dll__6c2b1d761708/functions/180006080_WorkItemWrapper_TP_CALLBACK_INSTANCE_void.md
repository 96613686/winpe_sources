# _WorkItemWrapper(_TP_CALLBACK_INSTANCE *,void *)

- ea: `0x180006080`
- end: `0x1800061bf`
- name: `?_WorkItemWrapper@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z`
- size: `319`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180006080`
- `0x1800061c8`
- `0x1800073c0`
- `0x1800084bc`
- `0x18002df48`
- `0x180030ad0`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000610e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000610e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800060fe`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800060fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800060df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800060df`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180006128`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180006128`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x180006098`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x180006098`

## string_xrefs

- `0x18000616c`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x18000619c`: `onecore\ds\security\gina\profile\proflib\sid.cpp`

## pseudocode

```c
void __fastcall _WorkItemWrapper(PTP_CALLBACK_INSTANCE Instance, _BYTE *Context)
{
  void *v3; // rbx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  const char *v6; // r9
  int v7; // ebx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF
  void *v11; // [rsp+40h] [rbp+18h] BYREF

  if ( Context )
  {
    if ( (Context[24] & 0x10) != 0 )
      CallbackMayRunLong(Instance);
    v3 = (void *)*((_QWORD *)Context + 2);
    if ( v3 )
    {
      v11 = 0;
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
            v8);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
          goto LABEL_6;
        }
      }
      if ( ImpersonateLoggedOnUser(v3) )
      {
        v11 = TokenHandle;
      }
      else
      {
        v7 = wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x2D,
               (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
               v6);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        if ( v7 < 0 )
          goto LABEL_6;
      }
      (*(void (__fastcall **)(_QWORD))Context)(*((_QWORD *)Context + 1));
      RevertToUser(&v11);
    }
    else
    {
      (*(void (__fastcall **)(_QWORD))Context)(*((_QWORD *)Context + 1));
    }
LABEL_6:
    _DestroyWorkItemInfo((struct WorkItemInfo *)Context);
  }
}

```

## disassembly

```asm
0x180006080  test    rdx, rdx
0x180006083  jz      short locret_1800060CB
0x180006085  mov     [rsp+arg_0], rbx
0x18000608a  push    rdi; int
0x18000608b  sub     rsp, 20h
0x18000608f  test    byte ptr [rdx+18h], 10h
0x180006093  mov     rdi, rdx
0x180006096  jz      short loc_1800060A4
0x180006098  call    cs:__imp_CallbackMayRunLong
0x18000609f  nop     dword ptr [rax+rax+00h]
0x1800060a4  mov     rbx, [rdi+10h]
0x1800060a8  test    rbx, rbx
0x1800060ab  jnz     short loc_1800060CD
0x1800060ad  mov     rcx, [rdi+8]
0x1800060b1  mov     rax, [rdi]
0x1800060b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060b9  mov     rcx, rdi; lpMem
0x1800060bc  call    ?_DestroyWorkItemInfo@@YAXPEAUWorkItemInfo@@@Z; _DestroyWorkItemInfo(WorkItemInfo *)
0x1800060c1  mov     rbx, [rsp+28h+arg_0]
0x1800060c6  add     rsp, 20h
0x1800060ca  pop     rdi
0x1800060cb  retn
0x1800060cd  mov     [rsp+28h+arg_10], 0
0x1800060d6  mov     [rsp+28h+TokenHandle], 0
0x1800060df  call    cs:__imp_GetCurrentThread
0x1800060e6  nop     dword ptr [rax+rax+00h]
0x1800060eb  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x1800060f0  mov     edx, 2000Ch; DesiredAccess
0x1800060f5  mov     rcx, rax; ThreadHandle
0x1800060f8  mov     r8d, 1; OpenAsSelf
0x1800060fe  call    cs:__imp_OpenThreadToken
0x180006105  nop     dword ptr [rax+rax+00h]
0x18000610a  test    eax, eax
0x18000610c  jnz     short loc_180006125
0x18000610e  call    cs:__imp_GetLastError
0x180006115  nop     dword ptr [rax+rax+00h]
0x18000611a  test    eax, eax
0x18000611c  jg      short loc_18000615D
0x18000611e  cmp     eax, 800703F0h
0x180006123  jnz     short loc_180006193
0x180006125  mov     rcx, rbx; hToken
0x180006128  call    cs:__imp_ImpersonateLoggedOnUser
0x18000612f  nop     dword ptr [rax+rax+00h]
0x180006134  test    eax, eax
0x180006136  jz      short loc_180006167
0x180006138  mov     rax, [rsp+28h+TokenHandle]
0x18000613d  mov     [rsp+28h+arg_10], rax
0x180006142  mov     rcx, [rdi+8]
0x180006146  mov     rax, [rdi]
0x180006149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000614e  lea     rcx, [rsp+28h+arg_10]; void **
0x180006153  call    ?RevertToUser@@YAJPEAPEAX@Z; RevertToUser(void * *)
0x180006158  jmp     loc_1800060B9
0x18000615d  movzx   eax, ax
0x180006160  or      eax, 80070000h
0x180006165  jmp     short loc_18000611E
0x180006167  mov     rcx, [rsp+28h]; this
0x18000616c  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x180006173  mov     edx, 2Dh ; '-'; void *
0x180006178  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000617d  lea     rcx, [rsp+28h+TokenHandle]
0x180006182  mov     ebx, eax
0x180006184  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180006189  test    ebx, ebx
0x18000618b  js      loc_1800060B9
0x180006191  jmp     short loc_180006142
0x180006193  test    eax, eax
0x180006195  jns     short loc_180006125
0x180006197  mov     rcx, [rsp+28h]; this
0x18000619c  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800061a3  mov     r9d, eax; char *
0x1800061a6  mov     edx, 2Ah ; '*'; void *
0x1800061ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800061b0  lea     rcx, [rsp+28h+TokenHandle]
0x1800061b5  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800061ba  jmp     loc_1800060B9
```
