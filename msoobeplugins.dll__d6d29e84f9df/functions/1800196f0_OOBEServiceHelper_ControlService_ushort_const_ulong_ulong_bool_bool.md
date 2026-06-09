# OOBEServiceHelper::_ControlService(ushort const *,ulong,ulong,bool,bool)

- ea: `0x1800196f0`
- end: `0x180019906`
- name: `?_ControlService@OOBEServiceHelper@@CAJPEBGKK_N1@Z`
- size: `534`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, DWORD dwControl@<edx>, unsigned int@<r8d>, bool@<r9b>, bool)`
- caller_count: `3`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180018a04`
- `0x180050d5c`
- `0x180050df0`

## callees

- `0x180003470`
- `0x18000ac48`
- `0x1800196f0`
- `0x180019c7c`
- `0x180019ce8`
- `0x1800b8834`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001973e`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001973e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001989a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800198c0`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001989a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800198c0`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180019815`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180019815`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180019720`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180019720`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180019765`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180019765`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1800197ab`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1800197ab`

## string_xrefs

- `0x18001977d`: `QueryServiceStatusEx failed [0x%08X]`
- `0x18001982d`: `StartService returned that Service %ls is already running`
- `0x18001983a`: `StartService for %ls failed [0x%08X]`
- `0x180019848`: `Service %ls is already running without invoking StartService()`
- `0x1800197c8`: `ControlService call to %ls failed [hr=0x%08X]`
- `0x1800197ec`: `Service %ls is already in final state %ls`
- `0x18001987c`: `Failed to wait for service %ls to enter state %ls [0x%08X]`
- `0x1800198aa`: `OpenService failed [0x%08X]`
- `0x1800198d0`: `OpenSCManager failed [0x%08X]`

## pseudocode

```c
__int64 __fastcall OOBEServiceHelper::_ControlService(
        const unsigned __int16 *a1,
        DWORD dwControl,
        unsigned int a3,
        __int64 a4,
        bool a5)
{
  SC_HANDLE v8; // rax
  SC_HANDLE v9; // r14
  SC_HANDLE v10; // rax
  struct SC_HANDLE__ *v11; // rsi
  int v12; // eax
  __int64 Error; // rbx
  int v14; // eax
  const unsigned __int16 *v15; // rax
  int v16; // eax
  const unsigned __int16 *v17; // rax
  _SERVICE_STATUS ServiceStatus; // [rsp+30h] [rbp-58h] BYREF

  v8 = OpenSCManagerW(0, 0, 4u);
  v9 = v8;
  if ( !v8 )
  {
    Error = (unsigned int)ResultFromKnownLastError();
    UnattendLogW(1, L"OpenSCManager failed [0x%08X]", Error);
    return (unsigned int)Error;
  }
  v10 = OpenServiceW(v8, a1, 0x34u);
  v11 = v10;
  if ( !v10 )
  {
    Error = (unsigned int)ResultFromKnownLastError();
    UnattendLogW(1, L"OpenService failed [0x%08X]", Error);
    goto LABEL_24;
  }
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  if ( QueryServiceStatus(v10, &ServiceStatus) || (v12 = ResultFromKnownLastError(), LODWORD(Error) = v12, v12 >= 0) )
  {
    if ( a3 == 4 )
    {
      if ( ((ServiceStatus.dwCurrentState - 2) & 0xFFFFFFFD) != 0 )
      {
        if ( !StartServiceW(v11, 0, 0) )
        {
          v16 = ResultFromKnownLastError();
          LODWORD(Error) = v16;
          if ( v16 == -2147023840 )
          {
            UnattendLogW(0, L"StartService returned that Service %ls is already running", a1);
          }
          else if ( v16 < 0 )
          {
            UnattendLogW(1, L"StartService for %ls failed [0x%08X]", a1, (unsigned int)v16);
            goto LABEL_22;
          }
        }
      }
      else
      {
        UnattendLogW(0, L"Service %ls is already running without invoking StartService()", a1);
      }
    }
    else if ( ServiceStatus.dwCurrentState == a3 )
    {
      v15 = OOBEServiceHelper::_ServiceStateToString(ServiceStatus.dwCurrentState);
      UnattendLogW(0, L"Service %ls is already in final state %ls", a1, v15);
    }
    else if ( !ControlService(v11, dwControl, &ServiceStatus) )
    {
      v14 = ResultFromKnownLastError();
      LODWORD(Error) = v14;
      if ( v14 < 0 )
      {
        UnattendLogW(2, L"ControlService call to %ls failed [hr=0x%08X]", a1, (unsigned int)v14);
        goto LABEL_22;
      }
    }
    LODWORD(Error) = OOBEServiceHelper::_WaitForServiceState(a1, v11, a3);
    if ( (int)Error < 0 )
    {
      v17 = OOBEServiceHelper::_ServiceStateToString(a3);
      UnattendLogW(!a5 + 1, L"Failed to wait for service %ls to enter state %ls [0x%08X]", a1, v17, Error);
    }
    goto LABEL_22;
  }
  UnattendLogW(1, L"QueryServiceStatusEx failed [0x%08X]", (unsigned int)v12);
LABEL_22:
  CloseServiceHandle(v11);
LABEL_24:
  CloseServiceHandle(v9);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800196f0  mov     [rsp+arg_18], rbx
0x1800196f5  push    rbp
0x1800196f6  push    rsi
0x1800196f7  push    rdi
0x1800196f8  push    r14
0x1800196fa  push    r15
0x1800196fc  sub     rsp, 60h
0x180019700  mov     rax, cs:__security_cookie
0x180019707  xor     rax, rsp
0x18001970a  mov     [rsp+88h+var_38], rax
0x18001970f  mov     r15d, edx
0x180019712  mov     ebp, r8d
0x180019715  xor     edx, edx; lpDatabaseName
0x180019717  mov     rdi, rcx
0x18001971a  xor     ecx, ecx; lpMachineName
0x18001971c  lea     r8d, [rdx+4]; dwDesiredAccess
0x180019720  call    cs:__imp_OpenSCManagerW
0x180019726  mov     r14, rax
0x180019729  test    rax, rax
0x18001972c  jz      loc_1800198C8
0x180019732  mov     r8d, 34h ; '4'; dwDesiredAccess
0x180019738  mov     rdx, rdi; lpServiceName
0x18001973b  mov     rcx, rax; hSCManager
0x18001973e  call    cs:__imp_OpenServiceW
0x180019744  mov     rsi, rax
0x180019747  test    rax, rax
0x18001974a  jz      loc_1800198A2
0x180019750  xorps   xmm0, xmm0
0x180019753  lea     rdx, [rsp+88h+ServiceStatus]; lpServiceStatus
0x180019758  movups  xmmword ptr [rsp+88h+ServiceStatus.dwServiceType], xmm0
0x18001975d  mov     rcx, rax; hService
0x180019760  movups  xmmword ptr [rsp+88h+ServiceStatus.dwWin32ExitCode], xmm0
0x180019765  call    cs:__imp_QueryServiceStatus
0x18001976b  test    eax, eax
0x18001976d  jnz     short loc_180019793
0x18001976f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180019774  mov     ebx, eax
0x180019776  test    eax, eax
0x180019778  jns     short loc_180019793
0x18001977a  mov     r8d, eax
0x18001977d  lea     rdx, aQueryservicest; "QueryServiceStatusEx failed [0x%08X]"
0x180019784  mov     ecx, 1
0x180019789  call    UnattendLogW
0x18001978e  jmp     loc_180019897
0x180019793  cmp     ebp, 4
0x180019796  jz      short loc_1800197FF
0x180019798  mov     ecx, [rsp+88h+ServiceStatus.dwCurrentState]; unsigned int
0x18001979c  cmp     ecx, ebp
0x18001979e  jz      short loc_1800197E4
0x1800197a0  lea     r8, [rsp+88h+ServiceStatus]; lpServiceStatus
0x1800197a5  mov     edx, r15d; dwControl
0x1800197a8  mov     rcx, rsi; hService
0x1800197ab  call    cs:__imp_ControlService
0x1800197b1  test    eax, eax
0x1800197b3  jnz     loc_180019859
0x1800197b9  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800197be  mov     ebx, eax
0x1800197c0  test    eax, eax
0x1800197c2  jns     loc_180019859
0x1800197c8  lea     rdx, aControlservice; "ControlService call to %ls failed [hr=0"...
0x1800197cf  mov     ecx, 2
0x1800197d4  mov     r8, rdi
0x1800197d7  mov     r9d, eax
0x1800197da  call    UnattendLogW
0x1800197df  jmp     loc_180019897
0x1800197e4  call    ?_ServiceStateToString@OOBEServiceHelper@@CAPEBGK@Z; OOBEServiceHelper::_ServiceStateToString(ulong)
0x1800197e9  mov     r9, rax
0x1800197ec  lea     rdx, aServiceLsIsAlr_0; "Service %ls is already in final state %"...
0x1800197f3  xor     ecx, ecx
0x1800197f5  mov     r8, rdi
0x1800197f8  call    UnattendLogW
0x1800197fd  jmp     short loc_180019859
0x1800197ff  mov     eax, [rsp+88h+ServiceStatus.dwCurrentState]
0x180019803  add     eax, 0FFFFFFFEh
0x180019806  test    eax, 0FFFFFFFDh
0x18001980b  jz      short loc_180019848
0x18001980d  xor     r8d, r8d; lpServiceArgVectors
0x180019810  xor     edx, edx; dwNumServiceArgs
0x180019812  mov     rcx, rsi; hService
0x180019815  call    cs:__imp_StartServiceW
0x18001981b  test    eax, eax
0x18001981d  jnz     short loc_180019859
0x18001981f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180019824  mov     ebx, eax
0x180019826  cmp     eax, 80070420h
0x18001982b  jnz     short loc_180019836
0x18001982d  lea     rdx, aStartserviceRe; "StartService returned that Service %ls "...
0x180019834  jmp     short loc_18001984F
0x180019836  test    eax, eax
0x180019838  jns     short loc_180019859
0x18001983a  lea     rdx, aStartserviceFo; "StartService for %ls failed [0x%08X]"
0x180019841  mov     ecx, 1
0x180019846  jmp     short loc_1800197D4
0x180019848  lea     rdx, aServiceLsIsAlr; "Service %ls is already running without "...
0x18001984f  mov     r8, rdi
0x180019852  xor     ecx, ecx
0x180019854  call    UnattendLogW
0x180019859  mov     r8d, ebp; unsigned int
0x18001985c  mov     rdx, rsi; struct SC_HANDLE__ *
0x18001985f  mov     rcx, rdi; unsigned __int16 *
0x180019862  call    ?_WaitForServiceState@OOBEServiceHelper@@CAJPEBGPEAUSC_HANDLE__@@K@Z; OOBEServiceHelper::_WaitForServiceState(ushort const *,SC_HANDLE__ *,ulong)
0x180019867  mov     ebx, eax
0x180019869  test    eax, eax
0x18001986b  jns     short loc_180019897
0x18001986d  mov     ecx, ebp; unsigned int
0x18001986f  call    ?_ServiceStateToString@OOBEServiceHelper@@CAPEBGK@Z; OOBEServiceHelper::_ServiceStateToString(ulong)
0x180019874  movzx   ecx, [rsp+88h+arg_20]
0x18001987c  lea     rdx, aFailedToWaitFo; "Failed to wait for service %ls to enter"...
0x180019883  xor     ecx, 1
0x180019886  mov     [rsp+88h+var_68], ebx
0x18001988a  inc     ecx
0x18001988c  mov     r9, rax
0x18001988f  mov     r8, rdi
0x180019892  call    UnattendLogW
0x180019897  mov     rcx, rsi; hSCObject
0x18001989a  call    cs:__imp_CloseServiceHandle
0x1800198a0  jmp     short loc_1800198BD
0x1800198a2  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800198a7  mov     r8d, eax
0x1800198aa  lea     rdx, aOpenserviceFai; "OpenService failed [0x%08X]"
0x1800198b1  mov     ecx, 1
0x1800198b6  mov     ebx, eax
0x1800198b8  call    UnattendLogW
0x1800198bd  mov     rcx, r14; hSCObject
0x1800198c0  call    cs:__imp_CloseServiceHandle
0x1800198c6  jmp     short loc_1800198E3
0x1800198c8  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800198cd  mov     r8d, eax
0x1800198d0  lea     rdx, aOpenscmanagerF; "OpenSCManager failed [0x%08X]"
0x1800198d7  mov     ecx, 1
0x1800198dc  mov     ebx, eax
0x1800198de  call    UnattendLogW
0x1800198e3  mov     eax, ebx
0x1800198e5  mov     rcx, [rsp+88h+var_38]
0x1800198ea  xor     rcx, rsp; StackCookie
0x1800198ed  call    __security_check_cookie
0x1800198f2  mov     rbx, [rsp+88h+arg_18]
0x1800198fa  add     rsp, 60h
0x1800198fe  pop     r15
0x180019900  pop     r14
0x180019902  pop     rdi
0x180019903  pop     rsi
0x180019904  pop     rbp
0x180019905  retn
```
