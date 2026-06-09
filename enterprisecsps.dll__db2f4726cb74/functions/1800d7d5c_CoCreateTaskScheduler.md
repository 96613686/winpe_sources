# CoCreateTaskScheduler

- ea: `0x1800d7d5c`
- end: `0x1800d7e4f`
- name: `CoCreateTaskScheduler`
- size: `243`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800d820c`
- `0x1800d935c`
- `0x1800da5e4`
- `0x1800dbe9c`
- `0x1800dd734`

## callees

- `0x18004568c`
- `0x1800d11a4`
- `0x1800d14ec`
- `0x1800d7d5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800d7dec`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800d7dec`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800d7dc9`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800d7dc9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d7d87`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d7e11`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d7d87`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d7e11`

## string_xrefs

- `0x1800d7dbb`: `Global\SC_AutoStartComplete`
- `0x1800d7d9e`: `CoCreateTaskScheduler`
- `0x1800d7e24`: `CoCreateTaskScheduler Retry`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CoCreateTaskScheduler(__int64 a1, char *a2, LPVOID *ppv)
{
  HRESULT Instance; // ebx
  CEnrollmentLogger *Logger; // rax
  char *v6; // rax
  CEnrollmentLogger *v7; // rax
  char *v9; // [rsp+48h] [rbp+10h] BYREF

  v9 = a2;
  Instance = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, ppv);
  if ( Instance < 0 )
  {
    Logger = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(Logger, Instance, "CoCreateTaskScheduler");
  }
  if ( Instance == -2147221164 )
  {
    v6 = (char *)OpenEventW(0x100000u, 0, L"Global\\SC_AutoStartComplete");
    v9 = v6;
    if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      WaitForSingleObject(v6, 0x3A98u);
    Instance = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, ppv);
    v7 = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(v7, Instance, "CoCreateTaskScheduler Retry");
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v9);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800d7d5c  mov     [rsp+arg_0], rbx
0x1800d7d61  mov     [rsp+arg_8], rdx
0x1800d7d66  push    rdi
0x1800d7d67  sub     rsp, 30h
0x1800d7d6b  mov     rdi, r8
0x1800d7d6e  mov     [rsp+38h+ppv], r8; ppv
0x1800d7d73  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x1800d7d7a  xor     edx, edx; pUnkOuter
0x1800d7d7c  lea     r8d, [rdx+1]; dwClsContext
0x1800d7d80  lea     rcx, CLSID_TaskScheduler; rclsid
0x1800d7d87  call    cs:__imp_CoCreateInstance
0x1800d7d8e  nop     dword ptr [rax+rax+00h]
0x1800d7d93  mov     ebx, eax
0x1800d7d95  test    eax, eax
0x1800d7d97  jns     short loc_1800D7DAF
0x1800d7d99  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x1800d7d9e  lea     r8, aCocreatetasksc_0; "CoCreateTaskScheduler"
0x1800d7da5  mov     edx, ebx; int
0x1800d7da7  mov     rcx, rax; this
0x1800d7daa  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x1800d7daf  cmp     ebx, 80040154h
0x1800d7db5  jnz     loc_1800D7E41
0x1800d7dbb  lea     r8, aGlobalScAutost; "Global\\SC_AutoStartComplete"
0x1800d7dc2  xor     edx, edx; bInheritHandle
0x1800d7dc4  mov     ecx, 100000h; dwDesiredAccess
0x1800d7dc9  call    cs:__imp_OpenEventW
0x1800d7dd0  nop     dword ptr [rax+rax+00h]
0x1800d7dd5  mov     [rsp+38h+arg_8], rax
0x1800d7dda  lea     rdx, [rax-1]
0x1800d7dde  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800d7de2  ja      short loc_1800D7DF8
0x1800d7de4  mov     edx, 3A98h; dwMilliseconds
0x1800d7de9  mov     rcx, rax; hHandle
0x1800d7dec  call    cs:__imp_WaitForSingleObject
0x1800d7df3  nop     dword ptr [rax+rax+00h]
0x1800d7df8  mov     [rsp+38h+ppv], rdi; ppv
0x1800d7dfd  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x1800d7e04  xor     edx, edx; pUnkOuter
0x1800d7e06  lea     r8d, [rdx+1]; dwClsContext
0x1800d7e0a  lea     rcx, CLSID_TaskScheduler; rclsid
0x1800d7e11  call    cs:__imp_CoCreateInstance
0x1800d7e18  nop     dword ptr [rax+rax+00h]
0x1800d7e1d  mov     ebx, eax
0x1800d7e1f  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x1800d7e24  lea     r8, aCocreatetasksc; "CoCreateTaskScheduler Retry"
0x1800d7e2b  mov     edx, ebx; int
0x1800d7e2d  mov     rcx, rax; this
0x1800d7e30  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x1800d7e35  nop
0x1800d7e36  lea     rcx, [rsp+38h+arg_8]
0x1800d7e3b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800d7e40  nop
0x1800d7e41  mov     eax, ebx
0x1800d7e43  mov     rbx, [rsp+38h+arg_0]
0x1800d7e48  add     rsp, 30h
0x1800d7e4c  pop     rdi
0x1800d7e4d  retn
```
