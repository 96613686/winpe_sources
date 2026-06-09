# Windows::Internal::ConfigurationManagement::Flags::FlagConfigurationManager::GetCurrentUserToken(ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)

- ea: `0x180098b74`
- end: `0x180098c12`
- name: `?GetCurrentUserToken@FlagConfigurationManager@Flags@ConfigurationManagement@Internal@Windows@@CAJKAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z`
- size: `158`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180098df0`
- `0x180098f54`

## callees

- `0x18006fcec`
- `0x180098b74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098baa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098be2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098baa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098be2`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180098bd8`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180098bd8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180098ba0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180098ba0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180098bc5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180098bc5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180098b89`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180098b89`

## pseudocode

```c
signed int __fastcall Windows::Internal::ConfigurationManagement::Flags::FlagConfigurationManager::GetCurrentUserToken(
        __int64 a1,
        __int64 a2)
{
  HANDLE CurrentThread; // rax
  signed int result; // eax
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+40h] [rbp+18h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xAu, 1, &TokenHandle) )
    goto LABEL_10;
  result = GetLastError();
  if ( result != 1008 )
  {
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0xAu, &TokenHandle) )
  {
LABEL_10:
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      a2,
      TokenHandle);
    return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180098b74  mov     [rsp+arg_0], ecx
0x180098b78  push    rbx
0x180098b79  sub     rsp, 20h
0x180098b7d  mov     rbx, rdx
0x180098b80  mov     [rsp+28h+TokenHandle], 0
0x180098b89  call    cs:__imp_GetCurrentThread
0x180098b8f  mov     rcx, rax; ThreadHandle
0x180098b92  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180098b97  mov     edx, 0Ah; DesiredAccess
0x180098b9c  lea     r8d, [rdx-9]; OpenAsSelf
0x180098ba0  call    cs:__imp_OpenThreadToken
0x180098ba6  test    eax, eax
0x180098ba8  jnz     short loc_180098BF6
0x180098baa  call    cs:__imp_GetLastError
0x180098bb0  cmp     eax, 3F0h
0x180098bb5  jz      short loc_180098BC5
0x180098bb7  test    eax, eax
0x180098bb9  jle     short loc_180098BC3
0x180098bbb  movzx   eax, ax
0x180098bbe  or      eax, 80070000h
0x180098bc3  jmp     short loc_180098C0B
0x180098bc5  call    cs:__imp_GetCurrentProcess
0x180098bcb  mov     rcx, rax; ProcessHandle
0x180098bce  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x180098bd3  mov     edx, 0Ah; DesiredAccess
0x180098bd8  call    cs:__imp_OpenProcessToken
0x180098bde  test    eax, eax
0x180098be0  jnz     short loc_180098BF6
0x180098be2  call    cs:__imp_GetLastError
0x180098be8  test    eax, eax
0x180098bea  jle     short loc_180098BF4
0x180098bec  movzx   eax, ax
0x180098bef  or      eax, 80070000h
0x180098bf4  jmp     short loc_180098C0B
0x180098bf6  mov     rdx, [rsp+28h+TokenHandle]
0x180098bfb  mov     rcx, rbx
0x180098bfe  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180098c03  xor     eax, eax
0x180098c05  jmp     short loc_180098C0B
0x180098c07  mov     eax, [rsp+28h+arg_0]
0x180098c0b  add     rsp, 20h
0x180098c0f  pop     rbx
0x180098c10  retn
```
