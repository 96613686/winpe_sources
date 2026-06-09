# GetProcessToken(ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)

- ea: `0x140032a64`
- end: `0x140032aed`
- name: `?GetProcessToken@@YAJKAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z`
- size: `137`
- prototype: `__int64 __fastcall(DWORD dwProcessId, PHANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14002dd30`

## callees

- `0x140008168`
- `0x14002e5b8`
- `0x140032690`
- `0x140032a64`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140032ab2`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140032ab2`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140032a7b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140032a7b`

## string_xrefs

- `0x140032ac4`: `clientcore\termsrv\rdpplatform\common\rdpsid\rdpsid.cpp`

## pseudocode

```c
__int64 __fastcall GetProcessToken(DWORD dwProcessId, PHANDLE TokenHandle)
{
  const char *v3; // r9
  void *v4; // rbx
  __int64 v5; // rdx
  unsigned int LastError; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HANDLE v9; // [rsp+40h] [rbp+18h] BYREF

  v9 = OpenProcess(0x1000u, 0, dwProcessId);
  v4 = v9;
  if ( v9 )
  {
    if ( *TokenHandle )
      wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(*TokenHandle);
    *TokenHandle = 0;
    if ( OpenProcessToken(v4, 8u, TokenHandle) )
    {
      LastError = 0;
      goto LABEL_9;
    }
    v5 = 21;
  }
  else
  {
    v5 = 20;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v5,
                (unsigned int)"clientcore\\termsrv\\rdpplatform\\common\\rdpsid\\rdpsid.cpp",
                v3);
LABEL_9:
  wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v9);
  return LastError;
}

```

## disassembly

```asm
0x140032a64  mov     [rsp+arg_0], rbx
0x140032a69  push    rdi
0x140032a6a  sub     rsp, 20h
0x140032a6e  mov     rdi, rdx
0x140032a71  mov     r8d, ecx; dwProcessId
0x140032a74  xor     edx, edx; bInheritHandle
0x140032a76  mov     ecx, 1000h; dwDesiredAccess
0x140032a7b  call    cs:__imp_OpenProcess
0x140032a81  mov     [rsp+28h+arg_10], rax
0x140032a86  mov     rbx, rax
0x140032a89  test    rax, rax
0x140032a8c  jnz     short loc_140032A93
0x140032a8e  lea     edx, [rax+14h]
0x140032a91  jmp     short loc_140032ABF
0x140032a93  mov     rcx, [rdi]; hObject
0x140032a96  test    rcx, rcx
0x140032a99  jz      short loc_140032AA0
0x140032a9b  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x140032aa0  mov     r8, rdi; TokenHandle
0x140032aa3  mov     qword ptr [rdi], 0
0x140032aaa  mov     edx, 8; DesiredAccess
0x140032aaf  mov     rcx, rbx; ProcessHandle
0x140032ab2  call    cs:__imp_OpenProcessToken
0x140032ab8  test    eax, eax
0x140032aba  jnz     short loc_140032AD4
0x140032abc  lea     edx, [rax+15h]; void *
0x140032abf  mov     rcx, [rsp+28h]; this
0x140032ac4  lea     r8, aClientcoreTerm_1; "clientcore\\termsrv\\rdpplatform\\commo"...
0x140032acb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140032ad0  mov     ebx, eax
0x140032ad2  jmp     short loc_140032AD6
0x140032ad4  xor     ebx, ebx
0x140032ad6  lea     rcx, [rsp+28h+arg_10]
0x140032adb  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140032ae0  mov     eax, ebx
0x140032ae2  mov     rbx, [rsp+28h+arg_0]
0x140032ae7  add     rsp, 20h
0x140032aeb  pop     rdi
0x140032aec  retn
```
