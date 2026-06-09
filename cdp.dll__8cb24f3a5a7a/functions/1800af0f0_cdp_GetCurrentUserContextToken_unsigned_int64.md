# cdp::GetCurrentUserContextToken(unsigned __int64 &)

- ea: `0x1800af0f0`
- end: `0x1800af29d`
- name: `?GetCurrentUserContextToken@cdp@@YAJAEA_K@Z`
- size: `429`
- prototype: `__int64 __fastcall(cdp *__hidden this, unsigned __int64 *)`
- caller_count: `6`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1800426fc`
- `0x1800aeb14`
- `0x180222be8`
- `0x180223130`
- `0x1802c0a4c`
- `0x1802d2128`

## callees

- `0x1800a29a0`
- `0x1800af0f0`
- `0x1800b0fec`
- `0x180102d00`
- `0x18012d5cc`
- `0x1802093a8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800af1da`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800af1da`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800af14b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800af14b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800af1c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800af1c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800af135`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800af135`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af159`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af1e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af159`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af1e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800af27f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800af27f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall cdp::GetCurrentUserContextToken(cdp *this, unsigned __int64 *a2)
{
  unsigned __int64 *v3; // r8
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  int v6; // ecx
  signed int v7; // ebx
  HANDLE CurrentProcess; // rax
  signed int v9; // eax
  int v10; // ecx
  int UserManagerForUserContextToken; // eax
  int v13; // ecx
  unsigned int v14; // [rsp+50h] [rbp+20h] BYREF
  int v15; // [rsp+58h] [rbp+28h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp+30h] BYREF

  *(_QWORD *)this = 0;
  if ( !(unsigned __int8)IsUMgrQueryUserContextPresent(this, a2) )
    return 0;
  TokenHandle = 0;
  if ( (NtCurrentPeb()->BitField & 0x20) == 0 )
  {
    TokenHandle = 0;
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      if ( v7 != -2147023888 )
      {
        v14 = v7;
        if ( v7 < 0 )
        {
          v15 = 140;
          Log<long &,char const (&)[36],int>(
            v6,
            (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Error:\"}",
            (unsigned int)&v14,
            (unsigned int)".\\platformutils.cpp",
            (__int64)&v15);
          v7 = v14;
        }
LABEL_17:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        return (unsigned int)v7;
      }
      if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(TokenHandle);
      TokenHandle = 0;
      CurrentProcess = GetCurrentProcess();
      if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
      {
        v9 = GetLastError();
        if ( v9 > 0 )
          v9 = (unsigned __int16)v9 | 0x80070000;
        v14 = v9;
        if ( v9 < 0 )
        {
          v15 = 144;
          Log<long &,char const (&)[36],int>(
            v10,
            (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Error:\"}",
            (unsigned int)&v14,
            (unsigned int)".\\platformutils.cpp",
            (__int64)&v15);
          v9 = v14;
        }
        v7 = v9;
        goto LABEL_17;
      }
    }
  }
  UserManagerForUserContextToken = cdp::QueryUserManagerForUserContextToken((cdp *)TokenHandle, this, v3);
  if ( UserManagerForUserContextToken >= 0 )
  {
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return 0;
  }
  v14 = UserManagerForUserContextToken;
  v15 = 149;
  Log<long &,char const (&)[36],int>(
    v13,
    (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Error:\"}",
    (unsigned int)&v14,
    (unsigned int)".\\platformutils.cpp",
    (__int64)&v15);
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return v14;
}

```

## disassembly

```asm
0x1800af0f0  push    rbp
0x1800af0f2  push    rbx
0x1800af0f3  push    rdi
0x1800af0f4  mov     rbp, rsp
0x1800af0f7  sub     rsp, 30h
0x1800af0fb  mov     rdi, rcx
0x1800af0fe  mov     qword ptr [rcx], 0
0x1800af105  call    IsUMgrQueryUserContextPresent
0x1800af10a  test    al, al
0x1800af10c  jz      loc_1800AF293
0x1800af112  mov     [rbp+TokenHandle], 0
0x1800af11a  mov     rax, gs:60h
0x1800af123  test    byte ptr [rax+3], 20h
0x1800af127  jnz     loc_1800AF236
0x1800af12d  mov     [rbp+TokenHandle], 0
0x1800af135  call    cs:__imp_GetCurrentThread
0x1800af13b  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800af13f  mov     edx, 8; DesiredAccess
0x1800af144  lea     r8d, [rdx-7]; OpenAsSelf
0x1800af148  mov     rcx, rax; ThreadHandle
0x1800af14b  call    cs:__imp_OpenThreadToken
0x1800af151  test    eax, eax
0x1800af153  jnz     loc_1800AF236
0x1800af159  call    cs:__imp_GetLastError
0x1800af15f  mov     ebx, eax
0x1800af161  test    eax, eax
0x1800af163  jle     short loc_1800AF16E
0x1800af165  movzx   ebx, ax
0x1800af168  or      ebx, 80070000h
0x1800af16e  cmp     ebx, 800703F0h
0x1800af174  jz      short loc_1800AF1AD
0x1800af176  mov     [rbp+arg_0], ebx
0x1800af179  test    ebx, ebx
0x1800af17b  jns     loc_1800AF229
0x1800af181  mov     [rbp+arg_8], 8Ch
0x1800af188  lea     rax, [rbp+arg_8]
0x1800af18c  mov     [rsp+30h+var_10], rax
0x1800af191  lea     r9, aPlatformutilsC; ".\\platformutils.cpp"
0x1800af198  lea     r8, [rbp+arg_0]
0x1800af19c  lea     rdx, aHr0x08xFileSLi_93; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800af1a3  call    ??$Log@AEAJAEAY0CE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CE@$$CBD$$QEAH@Z; Log<long &,char const (&)[36],int>(CDPLogLevel,char const *,long &,char const (&)[36],int &&)
0x1800af1a8  mov     ebx, [rbp+arg_0]
0x1800af1ab  jmp     short loc_1800AF229
0x1800af1ad  mov     rcx, [rbp+TokenHandle]; hObject
0x1800af1b1  lea     rax, [rcx-1]
0x1800af1b5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800af1b9  ja      short loc_1800AF1C0
0x1800af1bb  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x1800af1c0  mov     [rbp+TokenHandle], 0
0x1800af1c8  call    cs:__imp_GetCurrentProcess
0x1800af1ce  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800af1d2  mov     edx, 8; DesiredAccess
0x1800af1d7  mov     rcx, rax; ProcessHandle
0x1800af1da  call    cs:__imp_OpenProcessToken
0x1800af1e0  test    eax, eax
0x1800af1e2  jnz     short loc_1800AF236
0x1800af1e4  call    cs:__imp_GetLastError
0x1800af1ea  test    eax, eax
0x1800af1ec  jle     short loc_1800AF1F6
0x1800af1ee  movzx   eax, ax
0x1800af1f1  or      eax, 80070000h
0x1800af1f6  mov     [rbp+arg_0], eax
0x1800af1f9  test    eax, eax
0x1800af1fb  jns     short loc_1800AF227
0x1800af1fd  mov     [rbp+arg_8], 90h
0x1800af204  lea     rax, [rbp+arg_8]
0x1800af208  mov     [rsp+30h+var_10], rax
0x1800af20d  lea     r9, aPlatformutilsC; ".\\platformutils.cpp"
0x1800af214  lea     r8, [rbp+arg_0]
0x1800af218  lea     rdx, aHr0x08xFileSLi_93; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800af21f  call    ??$Log@AEAJAEAY0CE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CE@$$CBD$$QEAH@Z; Log<long &,char const (&)[36],int>(CDPLogLevel,char const *,long &,char const (&)[36],int &&)
0x1800af224  mov     eax, [rbp+arg_0]
0x1800af227  mov     ebx, eax
0x1800af229  lea     rcx, [rbp+TokenHandle]
0x1800af22d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800af232  mov     eax, ebx
0x1800af234  jmp     short loc_1800AF295
0x1800af236  mov     rdx, rdi; void *
0x1800af239  mov     rcx, [rbp+TokenHandle]; this
0x1800af23d  call    ?QueryUserManagerForUserContextToken@cdp@@YAJPEAXAEA_K@Z; cdp::QueryUserManagerForUserContextToken(void *,unsigned __int64 &)
0x1800af242  test    eax, eax
0x1800af244  jns     short loc_1800AF28A
0x1800af246  mov     [rbp+arg_0], eax
0x1800af249  mov     [rbp+arg_8], 95h
0x1800af250  lea     rax, [rbp+arg_8]
0x1800af254  mov     [rsp+30h+var_10], rax
0x1800af259  lea     r9, aPlatformutilsC; ".\\platformutils.cpp"
0x1800af260  lea     r8, [rbp+arg_0]
0x1800af264  lea     rdx, aHr0x08xFileSLi_93; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800af26b  call    ??$Log@AEAJAEAY0CE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CE@$$CBD$$QEAH@Z; Log<long &,char const (&)[36],int>(CDPLogLevel,char const *,long &,char const (&)[36],int &&)
0x1800af270  nop
0x1800af271  mov     rcx, [rbp+TokenHandle]; hObject
0x1800af275  lea     rdx, [rcx-1]
0x1800af279  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800af27d  ja      short loc_1800AF285
0x1800af27f  call    cs:__imp_CloseHandle
0x1800af285  mov     eax, [rbp+arg_0]
0x1800af288  jmp     short loc_1800AF295
0x1800af28a  lea     rcx, [rbp+TokenHandle]
0x1800af28e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800af293  xor     eax, eax
0x1800af295  add     rsp, 30h
0x1800af299  pop     rdi
0x1800af29a  pop     rbx
0x1800af29b  pop     rbp
0x1800af29c  retn
```
