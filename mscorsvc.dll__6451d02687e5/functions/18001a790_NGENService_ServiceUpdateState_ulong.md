# NGENService::ServiceUpdateState(ulong)

- ea: `0x18001a790`
- end: `0x18001a87e`
- name: `?ServiceUpdateState@NGENService@@YAXK@Z`
- size: `238`
- prototype: `void __fastcall(NGENService *__hidden this, unsigned int)`
- caller_count: `5`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x180002f44`
- `0x18001a880`
- `0x18001a990`
- `0x18001b1e4`
- `0x18001b340`

## callees

- `0x180007c7c`
- `0x18001a790`
- `0x18002e308`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x18001a84c`
- `KERNEL32!TerminateProcess` at `0x18001a84c`
- `KERNEL32!GetCurrentProcess` at `0x18001a83e`
- `KERNEL32!GetCurrentProcess` at `0x18001a83e`
- `KERNEL32!EnterCriticalSection` at `0x18001a7b0`
- `KERNEL32!EnterCriticalSection` at `0x18001a7b0`
- `KERNEL32!LeaveCriticalSection` at `0x18001a877`
- `KERNEL32!GetLastError` at `0x18001a81e`
- `KERNEL32!GetLastError` at `0x18001a81e`

## string_xrefs

- `0x18001a832`: `SetServiceStatus() call failed. HR=0x%08x. Will terminate service.\n`
- `0x18001a85d`: `Service state is now %s\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall NGENService::ServiceUpdateState(NGENService *this)
{
  __int64 v1; // rbx
  struct SERVICE_STATUS_HANDLE__ *v2; // rcx
  signed int LastError; // eax
  unsigned __int64 v4; // rdx
  HANDLE CurrentProcess; // rax

  v1 = (unsigned int)this;
  EnterCriticalSection(&NGENService::g_UpdateServiceCS);
  NGENService::g_ServiceStatus.dwCurrentState = v1;
  switch ( (_DWORD)v1 )
  {
    case 1:
    case 2:
    case 3:
      NGENService::g_ServiceStatus.dwControlsAccepted = 0;
      break;
    case 4:
      goto LABEL_8;
    case 5:
    case 6:
      NGENService::g_ServiceStatus.dwControlsAccepted = 5;
      break;
    case 7:
LABEL_8:
      NGENService::g_ServiceStatus.dwControlsAccepted = 7;
      break;
  }
  if ( NGENService::g_Options == 1 && !(unsigned int)CLRSetServiceStatus(v2, &NGENService::g_ServiceStatus) )
  {
    LastError = GetLastError();
    v4 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v4 = (unsigned int)LastError;
    NGENService::Log(
      (NGENService *)L"SetServiceStatus() call failed. HR=0x%08x. Will terminate service.\n",
      (const unsigned __int16 *)v4);
    CurrentProcess = GetCurrentProcess();
    TerminateProcess(CurrentProcess, 1u);
  }
  NGENService::Log(
    (NGENService *)L"Service state is now %s\n",
    (const unsigned __int16 *)(&NGENService::ServiceStatusString)[v1]);
  LeaveCriticalSection(&NGENService::g_UpdateServiceCS);
}

```

## disassembly

```asm
0x18001a790  mov     [rsp+arg_0], rbx
0x18001a795  push    rdi
0x18001a796  sub     rsp, 30h
0x18001a79a  mov     ebx, ecx
0x18001a79c  lea     rdi, ?g_UpdateServiceCS@NGENService@@3VCriticalSection@@A; CriticalSection NGENService::g_UpdateServiceCS
0x18001a7a3  mov     [rsp+38h+var_18], rdi
0x18001a7a8  mov     [rsp+38h+var_10], 0
0x18001a7ad  mov     rcx, rdi; lpCriticalSection
0x18001a7b0  call    cs:__imp_EnterCriticalSection
0x18001a7b6  mov     [rsp+38h+var_10], 1
0x18001a7bb  mov     cs:?g_ServiceStatus@NGENService@@3U_SERVICE_STATUS@@A.dwCurrentState, ebx; _SERVICE_STATUS NGENService::g_ServiceStatus ...
0x18001a7c1  mov     eax, ebx
0x18001a7c3  sub     eax, 1
0x18001a7c6  jz      short loc_18001A7FE
0x18001a7c8  sub     eax, 1
0x18001a7cb  jz      short loc_18001A7FE
0x18001a7cd  sub     eax, 1
0x18001a7d0  jz      short loc_18001A7FE
0x18001a7d2  sub     eax, 1
0x18001a7d5  jz      short loc_18001A7E6
0x18001a7d7  sub     eax, 1
0x18001a7da  jz      short loc_18001A7F2
0x18001a7dc  sub     eax, 1
0x18001a7df  jz      short loc_18001A7F2
0x18001a7e1  cmp     eax, 1
0x18001a7e4  jnz     short loc_18001A805
0x18001a7e6  mov     cs:?g_ServiceStatus@NGENService@@3U_SERVICE_STATUS@@A.dwControlsAccepted, 7; _SERVICE_STATUS NGENService::g_ServiceStatus ...
0x18001a7f0  jmp     short loc_18001A805
0x18001a7f2  mov     cs:?g_ServiceStatus@NGENService@@3U_SERVICE_STATUS@@A.dwControlsAccepted, 5; _SERVICE_STATUS NGENService::g_ServiceStatus ...
0x18001a7fc  jmp     short loc_18001A805
0x18001a7fe  and     cs:?g_ServiceStatus@NGENService@@3U_SERVICE_STATUS@@A.dwControlsAccepted, 0; _SERVICE_STATUS NGENService::g_ServiceStatus ...
0x18001a805  cmp     dword ptr cs:?g_Options@NGENService@@3U_ServiceOptions@@A, 1; _ServiceOptions NGENService::g_Options
0x18001a80c  jnz     short loc_18001A852
0x18001a80e  lea     rdx, ?g_ServiceStatus@NGENService@@3U_SERVICE_STATUS@@A; struct _SERVICE_STATUS *
0x18001a815  call    ?CLRSetServiceStatus@@YAHPEAUSERVICE_STATUS_HANDLE__@@PEAU_SERVICE_STATUS@@@Z; CLRSetServiceStatus(SERVICE_STATUS_HANDLE__ *,_SERVICE_STATUS *)
0x18001a81a  test    eax, eax
0x18001a81c  jnz     short loc_18001A852
0x18001a81e  call    cs:__imp_GetLastError
0x18001a824  movzx   edx, ax
0x18001a827  or      edx, 80070000h
0x18001a82d  test    eax, eax
0x18001a82f  cmovle  edx, eax; unsigned __int16 *
0x18001a832  lea     rcx, aSetservicestat; "SetServiceStatus() call failed. HR=0x%0"...
0x18001a839  call    ?Log@NGENService@@YAXPEBGZZ; NGENService::Log(ushort const *,...)
0x18001a83e  call    cs:__imp_GetCurrentProcess
0x18001a844  mov     rcx, rax; hProcess
0x18001a847  mov     edx, 1; uExitCode
0x18001a84c  call    cs:__imp_TerminateProcess
0x18001a852  lea     rax, ?ServiceStatusString@NGENService@@3PAPEBGA; ushort const * near * NGENService::ServiceStatusString
0x18001a859  mov     rdx, [rax+rbx*8]; unsigned __int16 *
0x18001a85d  lea     rcx, aServiceStateIs; "Service state is now %s\n"
0x18001a864  call    ?Log@NGENService@@YAXPEBGZZ; NGENService::Log(ushort const *,...)
0x18001a869  nop
0x18001a86a  mov     rcx, rdi
0x18001a86d  mov     rbx, [rsp+38h+arg_0]
0x18001a872  add     rsp, 30h
0x18001a876  pop     rdi
0x18001a877  jmp     cs:__imp_LeaveCriticalSection
```
