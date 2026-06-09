# _IsRunningInAppContainer(int *,void * *)

- ea: `0x180003e20`
- end: `0x180003fd6`
- name: `?_IsRunningInAppContainer@@YAJPEAHPEAPEAX@Z`
- size: `438`
- prototype: `__int64 __fastcall(int *, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180003914`
- `0x180008910`

## callees

- `0x180003e20`
- `0x180003fdc`
- `0x18000608c`
- `0x18000d5fc`
- `0x18000dc34`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f6c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003f7f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003f7f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180003e53`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180003e53`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180003e8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180003e8b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180003e9e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180003e9e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003e3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003e3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f64`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003fc9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f64`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003fc9`
- `ntdll!NtQueryInformationToken` at `0x180003ed8`
- `ntdll!NtQueryInformationToken` at `0x180003ed8`

## pseudocode

```c
__int64 __fastcall _IsRunningInAppContainer(int *a1, void **a2)
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  void *v6; // rdi
  HANDLE CurrentProcess; // rax
  const char *v8; // r9
  NTSTATUS v9; // eax
  unsigned int v10; // r8d
  unsigned int v12; // ebx
  DWORD v13; // ebx
  unsigned int v14; // ebx
  unsigned int ReturnLength; // [rsp+20h] [rbp-38h]
  int ReturnLengtha; // [rsp+20h] [rbp-38h]
  void *TokenHandle[5]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int TokenInformation; // [rsp+70h] [rbp+18h] BYREF
  ULONG v20; // [rsp+78h] [rbp+20h] BYREF

  TokenHandle[0] = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, TokenHandle) )
  {
    LastError = GetLastError();
    if ( LastError != 1008 )
    {
      if ( !LastError )
      {
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(TokenHandle);
        return 0;
      }
      v14 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x23,
              (unsigned int)"minio\\profapi\\appcontainer.cpp",
              (const char *)LastError,
              ReturnLength);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(TokenHandle);
      return v14;
    }
    v6 = TokenHandle[0];
    if ( (unsigned __int64)TokenHandle[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v13 = GetLastError();
      CloseHandle(v6);
      SetLastError(v13);
    }
    TokenHandle[0] = 0;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, TokenHandle) )
    {
      v12 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x1F,
              (unsigned int)"minio\\profapi\\appcontainer.cpp",
              v8);
      if ( (unsigned __int64)TokenHandle[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(TokenHandle[0]);
      return v12;
    }
  }
  TokenInformation = 0;
  v20 = 0;
  v9 = NtQueryInformationToken(TokenHandle[0], TokenIsAppContainer, &TokenInformation, 4u, &v20);
  if ( v9 >= 0 )
  {
    *a1 = TokenInformation != 0;
    *a2 = TokenHandle[0];
    return 0;
  }
  v12 = wil::details::in1diag3::Return_NtStatus(
          retaddr,
          (void *)0x2E,
          v10,
          (const char *)(unsigned int)v9,
          ReturnLengtha);
  if ( (unsigned __int64)TokenHandle[0] - 1 > 0xFFFFFFFFFFFFFFFDuLL )
    return v12;
  CloseHandle(TokenHandle[0]);
  return v12;
}

```

## disassembly

```asm
0x180003e20  mov     [rsp+arg_8], rbx
0x180003e25  push    rbp
0x180003e26  push    rsi
0x180003e27  push    r14
0x180003e29  sub     rsp, 40h
0x180003e2d  xor     ebp, ebp
0x180003e2f  mov     rsi, rdx
0x180003e32  mov     [rsp+58h+TokenHandle], rbp
0x180003e37  mov     r14, rcx
0x180003e3a  call    cs:__imp_GetCurrentThread
0x180003e40  lea     r9, [rsp+58h+TokenHandle]; TokenHandle
0x180003e45  mov     edx, 8; DesiredAccess
0x180003e4a  mov     rcx, rax; ThreadHandle
0x180003e4d  mov     r8d, 1; OpenAsSelf
0x180003e53  call    cs:__imp_OpenThreadToken
0x180003e59  test    eax, eax
0x180003e5b  jnz     short loc_180003EB1
0x180003e5d  call    cs:__imp_GetLastError
0x180003e63  cmp     eax, 3F0h
0x180003e68  jnz     loc_180003F8A
0x180003e6e  mov     [rsp+58h+arg_0], rdi
0x180003e73  mov     rdi, [rsp+58h+TokenHandle]
0x180003e78  lea     rax, [rdi-1]
0x180003e7c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180003e80  jbe     loc_180003F6C
0x180003e86  mov     [rsp+58h+TokenHandle], rbp
0x180003e8b  call    cs:__imp_GetCurrentProcess
0x180003e91  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x180003e96  mov     edx, 8; DesiredAccess
0x180003e9b  mov     rcx, rax; ProcessHandle
0x180003e9e  call    cs:__imp_OpenProcessToken
0x180003ea4  mov     rdi, [rsp+58h+arg_0]
0x180003ea9  test    eax, eax
0x180003eab  jz      loc_180003F3D
0x180003eb1  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x180003eb6  lea     rax, [rsp+58h+arg_18]
0x180003ebb  mov     r9d, 4; TokenInformationLength
0x180003ec1  mov     qword ptr [rsp+58h+ReturnLength], rax; int
0x180003ec6  lea     r8, [rsp+58h+TokenInformation]; TokenInformation
0x180003ecb  mov     [rsp+58h+TokenInformation], ebp
0x180003ecf  mov     edx, 1Dh; TokenInformationClass
0x180003ed4  mov     [rsp+58h+arg_18], ebp
0x180003ed8  call    cs:__imp_NtQueryInformationToken
0x180003ede  test    eax, eax
0x180003ee0  js      short loc_180003F06
0x180003ee2  mov     eax, ebp
0x180003ee4  cmp     [rsp+58h+TokenInformation], eax
0x180003ee8  setnz   al
0x180003eeb  mov     [r14], eax
0x180003eee  mov     rax, [rsp+58h+TokenHandle]
0x180003ef3  mov     [rsi], rax
0x180003ef6  xor     eax, eax
0x180003ef8  mov     rbx, [rsp+58h+arg_8]
0x180003efd  add     rsp, 40h
0x180003f01  pop     r14
0x180003f03  pop     rsi
0x180003f04  pop     rbp
0x180003f05  retn
0x180003f06  mov     rcx, [rsp+58h]; this
0x180003f0b  mov     r9d, eax; char *
0x180003f0e  mov     edx, 2Eh ; '.'; void *
0x180003f13  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180003f18  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x180003f1d  mov     ebx, eax
0x180003f1f  lea     rdx, [rcx-1]
0x180003f23  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180003f27  jbe     loc_180003FC9
0x180003f2d  mov     eax, ebx
0x180003f2f  mov     rbx, [rsp+58h+arg_8]
0x180003f34  add     rsp, 40h
0x180003f38  pop     r14
0x180003f3a  pop     rsi
0x180003f3b  pop     rbp
0x180003f3c  retn
0x180003f3d  mov     rcx, [rsp+58h]; this
0x180003f42  lea     r8, aMinioProfapiAp; "minio\\profapi\\appcontainer.cpp"
0x180003f49  mov     edx, 1Fh; void *
0x180003f4e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180003f53  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x180003f58  mov     ebx, eax
0x180003f5a  lea     rdx, [rcx-1]
0x180003f5e  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180003f62  ja      short loc_180003F2D
0x180003f64  call    cs:__imp_CloseHandle
0x180003f6a  jmp     short loc_180003F2D
0x180003f6c  call    cs:__imp_GetLastError
0x180003f72  mov     rcx, rdi; hObject
0x180003f75  mov     ebx, eax
0x180003f77  call    cs:__imp_CloseHandle
0x180003f7d  mov     ecx, ebx; dwErrCode
0x180003f7f  call    cs:__imp_SetLastError
0x180003f85  jmp     loc_180003E86
0x180003f8a  test    eax, eax
0x180003f8c  jz      short loc_180003FBA
0x180003f8e  mov     rcx, [rsp+58h]; this
0x180003f93  lea     r8, aMinioProfapiAp; "minio\\profapi\\appcontainer.cpp"
0x180003f9a  mov     r9d, eax; char *
0x180003f9d  mov     edx, 23h ; '#'; void *
0x180003fa2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180003fa7  lea     rcx, [rsp+58h+TokenHandle]
0x180003fac  mov     ebx, eax
0x180003fae  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180003fb3  mov     eax, ebx
0x180003fb5  jmp     loc_180003EF8
0x180003fba  lea     rcx, [rsp+58h+TokenHandle]
0x180003fbf  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180003fc4  jmp     loc_180003EF6
0x180003fc9  call    cs:__imp_CloseHandle
0x180003fcf  mov     eax, ebx
0x180003fd1  jmp     loc_180003EF8
```
