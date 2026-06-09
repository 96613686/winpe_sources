# CoCreateTaskScheduler

- ea: `0x18001788c`
- end: `0x180017963`
- name: `CoCreateTaskScheduler`
- size: `215`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800613ac`
- `0x1800643c0`

## callees

- `0x18001788c`
- `0x180017de4`
- `0x180018074`
- `0x18001aec8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001790d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001790d`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800178ef`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800178ef`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800178b7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001792c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800178b7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001792c`

## string_xrefs

- `0x180017939`: `CoCreateTaskScheduler Retry`
- `0x1800178e1`: `Global\SC_AutoStartComplete`
- `0x1800178c8`: `CoCreateTaskScheduler`

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
0x18001788c  mov     [rsp+arg_0], rbx
0x180017891  mov     [rsp+arg_8], rdx
0x180017896  push    rdi
0x180017897  sub     rsp, 30h
0x18001789b  mov     rdi, r8
0x18001789e  mov     [rsp+38h+ppv], r8; ppv
0x1800178a3  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x1800178aa  xor     edx, edx; pUnkOuter
0x1800178ac  lea     r8d, [rdx+1]; dwClsContext
0x1800178b0  lea     rcx, CLSID_TaskScheduler; rclsid
0x1800178b7  call    cs:__imp_CoCreateInstance
0x1800178bd  mov     ebx, eax
0x1800178bf  test    eax, eax
0x1800178c1  jns     short loc_1800178D9
0x1800178c3  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x1800178c8  lea     r8, aCocreatetasksc_0; "CoCreateTaskScheduler"
0x1800178cf  mov     edx, ebx; int
0x1800178d1  mov     rcx, rax; this
0x1800178d4  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x1800178d9  cmp     ebx, 80040154h
0x1800178df  jnz     short loc_180017956
0x1800178e1  lea     r8, Name; "Global\\SC_AutoStartComplete"
0x1800178e8  xor     edx, edx; bInheritHandle
0x1800178ea  mov     ecx, 100000h; dwDesiredAccess
0x1800178ef  call    cs:__imp_OpenEventW
0x1800178f5  nop
0x1800178f6  mov     [rsp+38h+arg_8], rax
0x1800178fb  lea     rdx, [rax-1]
0x1800178ff  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180017903  ja      short loc_180017913
0x180017905  mov     edx, 3A98h; dwMilliseconds
0x18001790a  mov     rcx, rax; hHandle
0x18001790d  call    cs:__imp_WaitForSingleObject
0x180017913  mov     [rsp+38h+ppv], rdi; ppv
0x180017918  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x18001791f  xor     edx, edx; pUnkOuter
0x180017921  lea     r8d, [rdx+1]; dwClsContext
0x180017925  lea     rcx, CLSID_TaskScheduler; rclsid
0x18001792c  call    cs:__imp_CoCreateInstance
0x180017932  mov     ebx, eax
0x180017934  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180017939  lea     r8, aCocreatetasksc; "CoCreateTaskScheduler Retry"
0x180017940  mov     edx, ebx; int
0x180017942  mov     rcx, rax; this
0x180017945  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x18001794a  nop
0x18001794b  lea     rcx, [rsp+38h+arg_8]
0x180017950  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180017955  nop
0x180017956  mov     eax, ebx
0x180017958  mov     rbx, [rsp+38h+arg_0]
0x18001795d  add     rsp, 30h
0x180017961  pop     rdi
0x180017962  retn
```
