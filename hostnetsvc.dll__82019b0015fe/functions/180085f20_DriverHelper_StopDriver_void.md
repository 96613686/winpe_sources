# DriverHelper::StopDriver(void)

- ea: `0x180085f20`
- end: `0x1800860c7`
- name: `?StopDriver@DriverHelper@@UEAAXXZ`
- size: `423`
- prototype: `void __fastcall(DriverHelper *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180080dd0`
- `0x180085608`

## callees

- `0x18005f0c0`
- `0x1800759d8`
- `0x180075aac`
- `0x180085eac`
- `0x180085f20`
- `0x1800860d0`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180085fb9`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180085fb9`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180085f7b`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180085f7b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18008604e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18008605d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18008604e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18008605d`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18008600b`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18008600b`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18008602a`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18008602a`

## string_xrefs

- `0x180085f8c`: `Failed to connect to service control manager`
- `0x180085fd3`: `Failed to open service: %ws.`
- `0x180085f9b`: `onecore\vm\dv\net\hns\service\common\helperlib\src\driverhelper.cpp`
- `0x180085fe2`: `onecore\vm\dv\net\hns\service\common\helperlib\src\driverhelper.cpp`
- `0x18008608f`: `onecore\vm\dv\net\hns\service\common\helperlib\src\driverhelper.cpp`
- `0x1800860b5`: `onecore\vm\dv\net\hns\service\common\helperlib\src\driverhelper.cpp`
- `0x180086088`: `Failed to stop service: %ws`
- `0x1800860ae`: `Failed to query service status: %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall DriverHelper::StopDriver(LPCWSTR *this)
{
  SC_HANDLE v2; // rdi
  SC_HANDLE v3; // rbx
  char v4; // [rsp+28h] [rbp-41h]
  DWORD pcbBytesNeeded; // [rsp+30h] [rbp-39h] BYREF
  SC_HANDLE v6; // [rsp+38h] [rbp-31h]
  SC_HANDLE v7; // [rsp+40h] [rbp-29h]
  BYTE Buffer[16]; // [rsp+48h] [rbp-21h] BYREF
  __int128 v9; // [rsp+58h] [rbp-11h]
  int v10; // [rsp+68h] [rbp-1h]
  struct _SERVICE_STATUS ServiceStatus; // [rsp+70h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  HNSTraceProvider::TraceEnter("DriverHelper::StopDriver", 0x19u);
  *(_OWORD *)Buffer = 0;
  v9 = 0;
  v10 = 0;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  pcbBytesNeeded = 0;
  v2 = OpenSCManagerW(0, 0, 0xF003Fu);
  v6 = v2;
  wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<SC_HANDLE__ *,0>(
    (int)retaddr,
    32,
    (int)"onecore\\vm\\dv\\net\\hns\\service\\common\\helperlib\\src\\driverhelper.cpp",
    (int)v2,
    (void *)"Failed to connect to service control manager",
    v4);
  v3 = OpenServiceW(v2, this[1], 0x24u);
  v7 = v3;
  wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<SC_HANDLE__ *,0>(
    (int)retaddr,
    35,
    (int)"onecore\\vm\\dv\\net\\hns\\service\\common\\helperlib\\src\\driverhelper.cpp",
    (int)v3,
    "Failed to open service: %ws.",
    (char)this[1]);
  if ( !QueryServiceStatusEx(v3, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
    wil::details::in1diag3::Throw_GetLastErrorMsg(
      retaddr,
      (void *)0x27,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\helperlib\\src\\driverhelper.cpp",
      "Failed to query service status: %ws",
      (const char *)this[1]);
  if ( *(_DWORD *)&Buffer[4] != 1 && !ControlService(v3, 1u, &ServiceStatus) )
    wil::details::in1diag3::Throw_GetLastErrorMsg(
      retaddr,
      (void *)0x2E,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\helperlib\\src\\driverhelper.cpp",
      "Failed to stop service: %ws",
      (const char *)this[1]);
  HNSTraceProvider::TraceSuccess("DriverHelper::StopDriver", 0x31u);
  if ( v3 )
    CloseServiceHandle(v3);
  if ( v2 )
    CloseServiceHandle(v2);
}

```

## disassembly

```asm
0x180085f20  push    rbp
0x180085f22  push    rbx
0x180085f23  push    rsi
0x180085f24  push    rdi
0x180085f25  lea     rbp, [rsp-3Fh]
0x180085f2a  sub     rsp, 0A8h
0x180085f31  mov     rax, cs:__security_cookie
0x180085f38  xor     rax, rsp
0x180085f3b  mov     [rbp+57h+var_30], rax
0x180085f3f  mov     rsi, rcx
0x180085f42  mov     edx, 19h; unsigned int
0x180085f47  lea     rcx, aDriverhelperSt; "DriverHelper::StopDriver"
0x180085f4e  call    ?TraceEnter@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceEnter(char const *,uint)
0x180085f53  xorps   xmm0, xmm0
0x180085f56  xor     eax, eax
0x180085f58  movups  xmmword ptr [rbp+57h+Buffer], xmm0
0x180085f5c  movups  [rbp+57h+var_68], xmm0
0x180085f60  mov     [rbp+57h+var_58], eax
0x180085f63  xorps   xmm1, xmm1
0x180085f66  movups  xmmword ptr [rbp+57h+ServiceStatus.dwServiceType], xmm1
0x180085f6a  movups  xmmword ptr [rbp+57h+ServiceStatus.dwWin32ExitCode], xmm1
0x180085f6e  mov     [rbp+57h+var_90], eax
0x180085f71  xor     edx, edx; lpDatabaseName
0x180085f73  mov     r8d, 0F003Fh; dwDesiredAccess
0x180085f79  xor     ecx, ecx; lpMachineName
0x180085f7b  call    cs:__imp_OpenSCManagerW
0x180085f81  mov     rdi, rax
0x180085f84  mov     [rbp+57h+var_88], rax
0x180085f88  mov     rcx, [rbp+5Fh]; int
0x180085f8c  lea     rax, aFailedToConnec; "Failed to connect to service control ma"...
0x180085f93  mov     [rsp+0C0h+pcbBytesNeeded], rax; void *
0x180085f98  mov     r9, rdi; int
0x180085f9b  lea     r8, aOnecoreVmDvNet_34; "onecore\\vm\\dv\\net\\hns\\service\\com"...
0x180085fa2  mov     edx, 20h ; ' '; int
0x180085fa7  call    ??$Throw_GetLastErrorIfNullMsg@PEAUSC_HANDLE__@@$0A@@in1diag3@details@wil@@YAPEAUSC_HANDLE__@@PEAXIPEBDPEAU3@1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<SC_HANDLE__ *,0>(void *,uint,char const *,SC_HANDLE__ *,char const *,...)
0x180085fac  mov     r8d, 24h ; '$'; dwDesiredAccess
0x180085fb2  mov     rdx, [rsi+8]; lpServiceName
0x180085fb6  mov     rcx, rdi; hSCManager
0x180085fb9  call    cs:__imp_OpenServiceW
0x180085fbf  mov     rbx, rax
0x180085fc2  mov     [rbp+57h+var_80], rax
0x180085fc6  mov     rcx, [rbp+5Fh]; int
0x180085fca  mov     rax, [rsi+8]
0x180085fce  mov     qword ptr [rsp+0C0h+var_98], rax; char
0x180085fd3  lea     rax, aFailedToOpenSe; "Failed to open service: %ws."
0x180085fda  mov     [rsp+0C0h+pcbBytesNeeded], rax; void *
0x180085fdf  mov     r9, rbx; int
0x180085fe2  lea     r8, aOnecoreVmDvNet_34; "onecore\\vm\\dv\\net\\hns\\service\\com"...
0x180085fe9  mov     edx, 23h ; '#'; int
0x180085fee  call    ??$Throw_GetLastErrorIfNullMsg@PEAUSC_HANDLE__@@$0A@@in1diag3@details@wil@@YAPEAUSC_HANDLE__@@PEAXIPEBDPEAU3@1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<SC_HANDLE__ *,0>(void *,uint,char const *,SC_HANDLE__ *,char const *,...)
0x180085ff3  lea     rax, [rbp+57h+var_90]
0x180085ff7  mov     [rsp+0C0h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180085ffc  mov     r9d, 24h ; '$'; cbBufSize
0x180086002  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x180086006  xor     edx, edx; InfoLevel
0x180086008  mov     rcx, rbx; hService
0x18008600b  call    cs:__imp_QueryServiceStatusEx
0x180086011  test    eax, eax
0x180086013  jz      loc_1800860A1
0x180086019  mov     edx, 1; dwControl
0x18008601e  cmp     dword ptr [rbp+57h+Buffer+4], edx
0x180086021  jz      short loc_180086034
0x180086023  lea     r8, [rbp+57h+ServiceStatus]; lpServiceStatus
0x180086027  mov     rcx, rbx; hService
0x18008602a  call    cs:__imp_ControlService
0x180086030  test    eax, eax
0x180086032  jz      short loc_18008607B
0x180086034  mov     edx, 31h ; '1'; unsigned int
0x180086039  lea     rcx, aDriverhelperSt; "DriverHelper::StopDriver"
0x180086040  call    ?TraceSuccess@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceSuccess(char const *,uint)
0x180086045  nop
0x180086046  test    rbx, rbx
0x180086049  jz      short loc_180086055
0x18008604b  mov     rcx, rbx; hSCObject
0x18008604e  call    cs:__imp_CloseServiceHandle
0x180086054  nop
0x180086055  test    rdi, rdi
0x180086058  jz      short loc_180086063
0x18008605a  mov     rcx, rdi; hSCObject
0x18008605d  call    cs:__imp_CloseServiceHandle
0x180086063  mov     rcx, [rbp+57h+var_30]
0x180086067  xor     rcx, rsp; StackCookie
0x18008606a  call    __security_check_cookie
0x18008606f  add     rsp, 0A8h
0x180086076  pop     rdi
0x180086077  pop     rsi
0x180086078  pop     rbx
0x180086079  pop     rbp
0x18008607a  retn
0x18008607b  mov     rcx, [rbp+5Fh]; this
0x18008607f  mov     rax, [rsi+8]
0x180086083  mov     [rsp+0C0h+pcbBytesNeeded], rax; char *
0x180086088  lea     r9, aFailedToStopSe; "Failed to stop service: %ws"
0x18008608f  lea     r8, aOnecoreVmDvNet_34; "onecore\\vm\\dv\\net\\hns\\service\\com"...
0x180086096  mov     edx, 2Eh ; '.'; void *
0x18008609b  call    ?Throw_GetLastErrorMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::Throw_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x1800860a1  mov     rcx, [rbp+5Fh]; this
0x1800860a5  mov     rax, [rsi+8]
0x1800860a9  mov     [rsp+0C0h+pcbBytesNeeded], rax; char *
0x1800860ae  lea     r9, aFailedToQueryS; "Failed to query service status: %ws"
0x1800860b5  lea     r8, aOnecoreVmDvNet_34; "onecore\\vm\\dv\\net\\hns\\service\\com"...
0x1800860bc  mov     edx, 27h ; '''; void *
0x1800860c1  call    ?Throw_GetLastErrorMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::Throw_GetLastErrorMsg(void *,uint,char const *,char const *,...)
```
