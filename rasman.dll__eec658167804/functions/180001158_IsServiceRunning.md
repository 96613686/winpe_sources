# IsServiceRunning

- ea: `0x180001158`
- end: `0x18000120e`
- name: `IsServiceRunning`
- size: `182`
- prototype: `_BOOL8()`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180002504`

## callees

- `0x180001158`
- `0x180026400`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001197`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800011bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001197`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800011bd`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x1800011af`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x1800011af`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x180001189`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x180001189`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800011cd`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800011cd`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800011e2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800011f0`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800011e2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800011f0`

## pseudocode

```c
_BOOL8 IsServiceRunning()
{
  BOOL v0; // ebx
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rsi
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rdi
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-58h] BYREF

  v0 = 0;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v1 = OpenSCManagerA(0, 0, 1u);
  v2 = v1;
  if ( v1 )
  {
    v3 = OpenServiceA(v1, "rasman", 4u);
    v4 = v3;
    if ( v3 && QueryServiceStatus(v3, &ServiceStatus) )
      v0 = ServiceStatus.dwCurrentState == 4;
    else
      GetLastError();
    CloseServiceHandle(v2);
    if ( v4 )
      CloseServiceHandle(v4);
  }
  else
  {
    GetLastError();
  }
  return v0;
}

```

## disassembly

```asm
0x180001158  push    rbx
0x18000115a  push    rbp
0x18000115b  push    rsi
0x18000115c  push    rdi
0x18000115d  sub     rsp, 58h
0x180001161  mov     rax, cs:__security_cookie
0x180001168  xor     rax, rsp
0x18000116b  mov     [rsp+78h+var_38], rax
0x180001170  xorps   xmm0, xmm0
0x180001173  xor     ebx, ebx
0x180001175  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x18000117a  xor     edx, edx; lpDatabaseName
0x18000117c  xor     ecx, ecx; lpMachineName
0x18000117e  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x180001183  lea     ebp, [rbx+1]
0x180001186  mov     r8d, ebp; dwDesiredAccess
0x180001189  call    cs:__imp_OpenSCManagerA
0x18000118f  mov     rsi, rax
0x180001192  test    rax, rax
0x180001195  jnz     short loc_18000119F
0x180001197  call    cs:__imp_GetLastError
0x18000119d  jmp     short loc_1800011F6
0x18000119f  mov     r8d, 4; dwDesiredAccess
0x1800011a5  lea     rdx, ServiceName; "rasman"
0x1800011ac  mov     rcx, rsi; hSCManager
0x1800011af  call    cs:__imp_OpenServiceA
0x1800011b5  mov     rdi, rax
0x1800011b8  test    rax, rax
0x1800011bb  jnz     short loc_1800011C5
0x1800011bd  call    cs:__imp_GetLastError
0x1800011c3  jmp     short loc_1800011DF
0x1800011c5  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x1800011ca  mov     rcx, rdi; hService
0x1800011cd  call    cs:__imp_QueryServiceStatus
0x1800011d3  test    eax, eax
0x1800011d5  jz      short loc_1800011BD
0x1800011d7  cmp     [rsp+78h+ServiceStatus.dwCurrentState], 4
0x1800011dc  cmovz   ebx, ebp
0x1800011df  mov     rcx, rsi; hSCObject
0x1800011e2  call    cs:__imp_CloseServiceHandle
0x1800011e8  test    rdi, rdi
0x1800011eb  jz      short loc_1800011F6
0x1800011ed  mov     rcx, rdi; hSCObject
0x1800011f0  call    cs:__imp_CloseServiceHandle
0x1800011f6  mov     eax, ebx
0x1800011f8  mov     rcx, [rsp+78h+var_38]
0x1800011fd  xor     rcx, rsp; StackCookie
0x180001200  call    __security_check_cookie
0x180001205  add     rsp, 58h
0x180001209  pop     rdi
0x18000120a  pop     rsi
0x18000120b  pop     rbp
0x18000120c  pop     rbx
0x18000120d  retn
```
