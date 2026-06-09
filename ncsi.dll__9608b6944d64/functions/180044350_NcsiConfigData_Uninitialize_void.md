# NcsiConfigData::Uninitialize(void)

- ea: `0x180044350`
- end: `0x180044459`
- name: `?Uninitialize@NcsiConfigData@@QEAAXXZ`
- size: `265`
- prototype: `void __fastcall(NcsiConfigData *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180050300`

## callees

- `0x18000e59c`
- `0x180010200`
- `0x180044350`
- `0x180044460`
- `0x180044900`
- `0x180047240`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1800443a3`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1800443a3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800443f4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800443f4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180044404`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180044404`

## pseudocode

```c
void __fastcall NcsiConfigData::Uninitialize(NcsiConfigData *this)
{
  HANDLE v1; // rcx
  DWORD ExitCode; // [rsp+20h] [rbp-18h] BYREF

  v1 = g_registryMonitorThread;
  ExitCode = 0;
  if ( (char *)g_registryMonitorThread - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    if ( (((unsigned __int64)g_registryNotificationEvent + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(g_registryMonitorThread);
      v1 = g_registryMonitorThread;
    }
    if ( !GetExitCodeThread(v1, &ExitCode) || ExitCode == 259 )
    {
      SetEvent(g_registryNotificationEvent);
      WaitForSingleObject(g_registryMonitorThread, 0xFFFFFFFF);
    }
    else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
           && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 35, &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids);
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &g_registryMonitorThread,
      0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &g_registryMonitorEvent,
      0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &g_gpRegistryMonitorEvent,
      0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &g_registryNotificationEvent,
      0);
  }
  NcsiConfigData::SaveCache((NcsiConfigData *)v1);
}

```

## disassembly

```asm
0x180044350  sub     rsp, 38h
0x180044354  mov     rax, cs:__security_cookie
0x18004435b  xor     rax, rsp
0x18004435e  mov     [rsp+38h+var_10], rax
0x180044363  mov     rcx, cs:?g_registryMonitorThread@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> g_registryMonitorThread
0x18004436a  mov     [rsp+38h+ExitCode], 0
0x180044372  lea     rax, [rcx-1]
0x180044376  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004437a  ja      loc_180044442
0x180044380  mov     rax, cs:?g_registryNotificationEvent@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> g_registryNotificationEvent
0x180044387  inc     rax
0x18004438a  test    rax, 0FFFFFFFFFFFFFFFEh
0x180044390  jnz     short loc_18004439E
0x180044392  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180044397  mov     rcx, cs:?g_registryMonitorThread@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; hThread
0x18004439e  lea     rdx, [rsp+38h+ExitCode]; lpExitCode
0x1800443a3  call    cs:__imp_GetExitCodeThread
0x1800443a9  test    eax, eax
0x1800443ab  jz      short loc_1800443ED
0x1800443ad  cmp     [rsp+38h+ExitCode], 103h
0x1800443b5  jz      short loc_1800443ED
0x1800443b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800443be  lea     rax, WPP_GLOBAL_Control
0x1800443c5  cmp     rcx, rax
0x1800443c8  jz      short loc_18004440A
0x1800443ca  test    byte ptr [rcx+1Ch], 10h
0x1800443ce  jz      short loc_18004440A
0x1800443d0  cmp     byte ptr [rcx+19h], 5
0x1800443d4  jb      short loc_18004440A
0x1800443d6  mov     rcx, [rcx+10h]
0x1800443da  lea     r8, WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids
0x1800443e1  mov     edx, 23h ; '#'
0x1800443e6  call    WPP_SF_
0x1800443eb  jmp     short loc_18004440A
0x1800443ed  mov     rcx, cs:?g_registryNotificationEvent@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; hEvent
0x1800443f4  call    cs:__imp_SetEvent
0x1800443fa  mov     rcx, cs:?g_registryMonitorThread@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; hHandle
0x180044401  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180044404  call    cs:__imp_WaitForSingleObject
0x18004440a  xor     edx, edx
0x18004440c  lea     rcx, ?g_registryMonitorThread@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> g_registryMonitorThread
0x180044413  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180044418  xor     edx, edx
0x18004441a  lea     rcx, ?g_registryMonitorEvent@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> g_registryMonitorEvent
0x180044421  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180044426  xor     edx, edx
0x180044428  lea     rcx, ?g_gpRegistryMonitorEvent@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> g_gpRegistryMonitorEvent
0x18004442f  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180044434  xor     edx, edx
0x180044436  lea     rcx, ?g_registryNotificationEvent@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> g_registryNotificationEvent
0x18004443d  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180044442  call    ?SaveCache@NcsiConfigData@@QEAAXXZ; NcsiConfigData::SaveCache(void)
0x180044447  mov     rcx, [rsp+38h+var_10]
0x18004444c  xor     rcx, rsp; StackCookie
0x18004444f  call    __security_check_cookie
0x180044454  add     rsp, 38h
0x180044458  retn
```
