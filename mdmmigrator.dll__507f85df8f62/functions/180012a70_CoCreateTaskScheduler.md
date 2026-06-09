# CoCreateTaskScheduler

- ea: `0x180012a70`
- end: `0x180012b4f`
- name: `CoCreateTaskScheduler`
- size: `223`
- prototype: `__int64 __fastcall(__int64, __int64, LPVOID *ppv)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180012ed4`
- `0x180016ca8`
- `0x180019904`

## callees

- `0x180012a70`
- `0x18001dce8`
- `0x18001e264`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180012aed`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180012aed`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180012ad3`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180012ad3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012b37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012b37`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012a9b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012b0c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012a9b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012b0c`

## string_xrefs

- `0x180012ac5`: `Global\SC_AutoStartComplete`
- `0x180012aac`: `CoCreateTaskScheduler`
- `0x180012b19`: `CoCreateTaskScheduler Retry`

## pseudocode

```c
__int64 __fastcall CoCreateTaskScheduler(__int64 a1, __int64 a2, LPVOID *ppv)
{
  HRESULT Instance; // edi
  CEnrollmentLogger *Logger; // rax
  char *v6; // rbx
  CEnrollmentLogger *v7; // rax

  Instance = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, ppv);
  if ( Instance < 0 )
  {
    Logger = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(Logger, Instance, "CoCreateTaskScheduler");
  }
  if ( Instance == -2147221164 )
  {
    v6 = (char *)OpenEventW(0x100000u, 0, L"Global\\SC_AutoStartComplete");
    if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      WaitForSingleObject(v6, 0x3A98u);
    Instance = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, ppv);
    v7 = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(v7, Instance, "CoCreateTaskScheduler Retry");
    if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v6);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180012a70  mov     [rsp+arg_0], rbx
0x180012a75  mov     [rsp+arg_8], rsi
0x180012a7a  push    rdi
0x180012a7b  sub     rsp, 30h
0x180012a7f  xor     edx, edx; pUnkOuter
0x180012a81  mov     [rsp+38h+ppv], r8; ppv
0x180012a86  mov     rsi, r8
0x180012a89  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x180012a90  lea     rcx, CLSID_TaskScheduler; rclsid
0x180012a97  lea     r8d, [rdx+1]; dwClsContext
0x180012a9b  call    cs:__imp_CoCreateInstance
0x180012aa1  mov     edi, eax
0x180012aa3  test    eax, eax
0x180012aa5  jns     short loc_180012ABD
0x180012aa7  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180012aac  lea     r8, aCocreatetasksc_0; "CoCreateTaskScheduler"
0x180012ab3  mov     edx, edi; int
0x180012ab5  mov     rcx, rax; this
0x180012ab8  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x180012abd  cmp     edi, 80040154h
0x180012ac3  jnz     short loc_180012B3D
0x180012ac5  lea     r8, Name; "Global\\SC_AutoStartComplete"
0x180012acc  xor     edx, edx; bInheritHandle
0x180012ace  mov     ecx, 100000h; dwDesiredAccess
0x180012ad3  call    cs:__imp_OpenEventW
0x180012ad9  mov     rbx, rax
0x180012adc  dec     rax
0x180012adf  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180012ae3  ja      short loc_180012AF3
0x180012ae5  mov     edx, 3A98h; dwMilliseconds
0x180012aea  mov     rcx, rbx; hHandle
0x180012aed  call    cs:__imp_WaitForSingleObject
0x180012af3  xor     edx, edx; pUnkOuter
0x180012af5  mov     [rsp+38h+ppv], rsi; ppv
0x180012afa  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x180012b01  lea     rcx, CLSID_TaskScheduler; rclsid
0x180012b08  lea     r8d, [rdx+1]; dwClsContext
0x180012b0c  call    cs:__imp_CoCreateInstance
0x180012b12  mov     edi, eax
0x180012b14  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180012b19  lea     r8, aCocreatetasksc; "CoCreateTaskScheduler Retry"
0x180012b20  mov     edx, edi; int
0x180012b22  mov     rcx, rax; this
0x180012b25  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x180012b2a  lea     rax, [rbx-1]
0x180012b2e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180012b32  ja      short loc_180012B3D
0x180012b34  mov     rcx, rbx; hObject
0x180012b37  call    cs:__imp_CloseHandle
0x180012b3d  mov     rbx, [rsp+38h+arg_0]
0x180012b42  mov     eax, edi
0x180012b44  mov     rsi, [rsp+38h+arg_8]
0x180012b49  add     rsp, 30h
0x180012b4d  pop     rdi
0x180012b4e  retn
```
