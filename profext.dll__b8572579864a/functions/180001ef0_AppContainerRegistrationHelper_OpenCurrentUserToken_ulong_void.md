# AppContainerRegistrationHelper::OpenCurrentUserToken(ulong,void * *)

- ea: `0x180001ef0`
- end: `0x180002021`
- name: `?OpenCurrentUserToken@AppContainerRegistrationHelper@@SAJKPEAPEAX@Z`
- size: `305`
- prototype: `__int64 __fastcall(char *, void **)`
- caller_count: `6`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800020d0`
- `0x180002a80`
- `0x1800045bc`
- `0x18000ca58`
- `0x180013de4`
- `0x18001fed0`

## callees

- `0x180001854`
- `0x180001ef0`
- `0x18000c6c0`
- `0x18000f440`
- `0x18000f6cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001f38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001f38`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180001fcc`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180001fcc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180001f08`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180001f08`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001fb6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001fb6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180001f24`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180001f24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001f89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001f89`

## string_xrefs

- `0x180001f5f`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180001fe8`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180001f54`: `access %x`
- `0x180001fe1`: `access %x`

## pseudocode

```c
__int64 __fastcall AppContainerRegistrationHelper::OpenCurrentUserToken(char *a1, void **a2)
{
  DWORD v3; // ebx
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  unsigned int LastErrorMsg; // ebx
  HANDLE CurrentProcess; // rax
  char *v9; // [rsp+20h] [rbp-18h]
  char *v10; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  TokenHandle = 0;
  v3 = (unsigned int)a1;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, v3, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    if ( LastError != 1008 && LastError )
    {
      LODWORD(v10) = v3;
      LastErrorMsg = wil::details::in1diag3::Return_Win32Msg(
                       retaddr,
                       (void *)0x152,
                       (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
                       (const char *)LastError,
                       (unsigned int)"access %x",
                       v10);
      if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(TokenHandle);
      return LastErrorMsg;
    }
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(TokenHandle);
    TokenHandle = 0;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, v3, &TokenHandle) )
    {
      LODWORD(v9) = v3;
      LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                       retaddr,
                       (void *)0x156,
                       (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
                       "access %x",
                       v9);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      return LastErrorMsg;
    }
  }
  *a2 = TokenHandle;
  return 0;
}

```

## disassembly

```asm
0x180001ef0  mov     [rsp+arg_0], rbx
0x180001ef5  push    rdi
0x180001ef6  sub     rsp, 30h
0x180001efa  mov     rdi, rdx
0x180001efd  mov     [rsp+38h+TokenHandle], 0
0x180001f06  mov     ebx, ecx
0x180001f08  call    cs:__imp_GetCurrentThread
0x180001f0f  nop     dword ptr [rax+rax+00h]
0x180001f14  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x180001f19  mov     r8d, 1; OpenAsSelf
0x180001f1f  mov     rcx, rax; ThreadHandle
0x180001f22  mov     edx, ebx; DesiredAccess
0x180001f24  call    cs:__imp_OpenThreadToken
0x180001f2b  nop     dword ptr [rax+rax+00h]
0x180001f30  test    eax, eax
0x180001f32  jnz     loc_18000200B
0x180001f38  call    cs:__imp_GetLastError
0x180001f3f  nop     dword ptr [rax+rax+00h]
0x180001f44  cmp     eax, 3F0h
0x180001f49  jz      short loc_180001F99
0x180001f4b  test    eax, eax
0x180001f4d  jz      short loc_180001F99
0x180001f4f  mov     rcx, [rsp+38h]; this
0x180001f54  lea     r9, aAccessX_0; "access %x"
0x180001f5b  mov     dword ptr [rsp+38h+var_10], ebx; char *
0x180001f5f  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180001f66  mov     [rsp+38h+var_18], r9; unsigned int
0x180001f6b  mov     edx, 152h; void *
0x180001f70  mov     r9d, eax; char *
0x180001f73  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180001f78  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180001f7d  mov     ebx, eax
0x180001f7f  lea     rdx, [rcx-1]
0x180001f83  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180001f87  ja      short loc_180001F95
0x180001f89  call    cs:__imp_CloseHandle
0x180001f90  nop     dword ptr [rax+rax+00h]
0x180001f95  mov     eax, ebx
0x180001f97  jmp     short loc_180002015
0x180001f99  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180001f9e  lea     rax, [rcx-1]
0x180001fa2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180001fa6  ja      short loc_180001FAD
0x180001fa8  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x180001fad  mov     [rsp+38h+TokenHandle], 0
0x180001fb6  call    cs:__imp_GetCurrentProcess
0x180001fbd  nop     dword ptr [rax+rax+00h]
0x180001fc2  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x180001fc7  mov     edx, ebx; DesiredAccess
0x180001fc9  mov     rcx, rax; ProcessHandle
0x180001fcc  call    cs:__imp_OpenProcessToken
0x180001fd3  nop     dword ptr [rax+rax+00h]
0x180001fd8  test    eax, eax
0x180001fda  jnz     short loc_18000200B
0x180001fdc  mov     rcx, [rsp+38h]; this
0x180001fe1  lea     r9, aAccessX_0; "access %x"
0x180001fe8  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180001fef  mov     dword ptr [rsp+38h+var_18], ebx; char *
0x180001ff3  mov     edx, 156h; void *
0x180001ff8  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x180001ffd  lea     rcx, [rsp+38h+TokenHandle]
0x180002002  mov     ebx, eax
0x180002004  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180002009  jmp     short loc_180001F95
0x18000200b  mov     rax, [rsp+38h+TokenHandle]
0x180002010  mov     [rdi], rax
0x180002013  xor     eax, eax
0x180002015  mov     rbx, [rsp+38h+arg_0]
0x18000201a  add     rsp, 30h
0x18000201e  pop     rdi
0x18000201f  retn
```
