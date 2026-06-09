# Microsoft::IoT::Utility::MTAThreadPool::GetDelayTimer(unsigned __int64)

- ea: `0x18000d6d8`
- end: `0x18000d7c0`
- name: `?GetDelayTimer@MTAThreadPool@Utility@IoT@Microsoft@@CA?AV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@_K@Z`
- size: `232`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f58c`

## callees

- `0x180006af4`
- `0x18000d200`
- `0x18000d6d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetWaitableTimerEx` at `0x18000d77a`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimerEx` at `0x18000d77a`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x18000d6fb`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x18000d6fb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000d730`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000d730`

## string_xrefs

- `0x18000d789`: `onecoreuap\shell\embedded\shell\iotshellhostext\iotshellcbt\mtathreadpool.cpp`
- `0x18000d7ae`: `onecoreuap\shell\embedded\shell\iotshellhostext\iotshellcbt\mtathreadpool.cpp`

## pseudocode

```c
_QWORD *__fastcall Microsoft::IoT::Utility::MTAThreadPool::GetDelayTimer(_QWORD *a1, __int64 a2)
{
  HANDLE WaitableTimer; // rax
  const char *v5; // r9
  _QWORD *v6; // rcx
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+60h] [rbp+8h] BYREF
  LARGE_INTEGER DueTime; // [rsp+70h] [rbp+18h] BYREF

  SystemTimeAsFileTime = (struct _FILETIME)a1;
  WaitableTimer = CreateWaitableTimerExW(0, 0, 1u, 0x1F0003u);
  wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(
    a1,
    WaitableTimer);
  if ( !*a1 || !*(_QWORD *)*a1 )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x11D,
      (unsigned int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\mtathreadpool.cpp",
      v5);
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v6 = (_QWORD *)*a1;
  DueTime.QuadPart = 10000 * a2 + *(_QWORD *)&SystemTimeAsFileTime;
  if ( v6 )
    v6 = (_QWORD *)*v6;
  if ( !SetWaitableTimerEx(v6, &DueTime, 0, 0, 0, 0, 0x64u) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x123,
      (unsigned int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\mtathreadpool.cpp",
      v7);
  return a1;
}

```

## disassembly

```asm
0x18000d6d8  mov     [rsp+arg_8], rbx
0x18000d6dd  mov     qword ptr [rsp+SystemTimeAsFileTime.dwLowDateTime], rcx
0x18000d6e2  push    rdi
0x18000d6e3  sub     rsp, 50h
0x18000d6e7  mov     rdi, rdx
0x18000d6ea  mov     rbx, rcx
0x18000d6ed  xor     edx, edx; lpTimerName
0x18000d6ef  mov     r9d, 1F0003h; dwDesiredAccess
0x18000d6f5  xor     ecx, ecx; lpTimerAttributes
0x18000d6f7  lea     r8d, [rdx+1]; dwFlags
0x18000d6fb  call    cs:__imp_CreateWaitableTimerExW
0x18000d701  mov     rdx, rax
0x18000d704  mov     rcx, rbx
0x18000d707  call    ??0?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@PEAX@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void *)
0x18000d70c  mov     rax, [rbx]
0x18000d70f  test    rax, rax
0x18000d712  jz      loc_18000D7A9
0x18000d718  cmp     qword ptr [rax], 0
0x18000d71c  jz      loc_18000D7A9
0x18000d722  lea     rcx, [rsp+58h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000d727  mov     qword ptr [rsp+58h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18000d730  call    cs:__imp_GetSystemTimeAsFileTime
0x18000d736  mov     rax, qword ptr [rsp+58h+SystemTimeAsFileTime.dwLowDateTime]
0x18000d73b  imul    rcx, rdi, 2710h
0x18000d742  add     rax, rcx
0x18000d745  mov     rcx, [rbx]
0x18000d748  mov     qword ptr [rsp+58h+DueTime], rax
0x18000d74d  test    rcx, rcx
0x18000d750  jz      short loc_18000D755
0x18000d752  mov     rcx, [rcx]; hTimer
0x18000d755  mov     [rsp+58h+TolerableDelay], 64h ; 'd'; TolerableDelay
0x18000d75d  lea     rdx, [rsp+58h+DueTime]; lpDueTime
0x18000d762  mov     [rsp+58h+WakeContext], 0; WakeContext
0x18000d76b  xor     r9d, r9d; pfnCompletionRoutine
0x18000d76e  xor     r8d, r8d; lPeriod
0x18000d771  mov     [rsp+58h+lpArgToCompletionRoutine], 0; lpArgToCompletionRoutine
0x18000d77a  call    cs:__imp_SetWaitableTimerEx
0x18000d780  test    eax, eax
0x18000d782  jnz     short loc_18000D79B
0x18000d784  mov     rcx, [rsp+58h]; this
0x18000d789  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x18000d790  mov     edx, 123h; void *
0x18000d795  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000d79b  mov     rax, rbx
0x18000d79e  mov     rbx, [rsp+58h+arg_8]
0x18000d7a3  add     rsp, 50h
0x18000d7a7  pop     rdi
0x18000d7a8  retn
0x18000d7a9  mov     rcx, [rsp+58h]; this
0x18000d7ae  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x18000d7b5  mov     edx, 11Dh; void *
0x18000d7ba  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
