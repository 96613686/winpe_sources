# IsRasmanServiceRunning

- ea: `0x180041f48`
- end: `0x1800420a1`
- name: `IsRasmanServiceRunning`
- size: `345`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800490c4`

## callees

- `0x180041f48`
- `0x18004d110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041f9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041fe6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042023`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041f9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041fe6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042023`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180041fcf`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180041fcf`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180042052`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004205b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180042052`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004205b`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180041f80`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180041f80`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180042010`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180042010`
- `rtutils!TracePrintfExA` at `0x180041fb4`
- `rtutils!TracePrintfExA` at `0x180042000`
- `rtutils!TracePrintfExA` at `0x18004203e`
- `rtutils!TracePrintfExA` at `0x18004207b`
- `rtutils!TracePrintfExA` at `0x180041fb4`
- `rtutils!TracePrintfExA` at `0x180042000`
- `rtutils!TracePrintfExA` at `0x18004203e`
- `rtutils!TracePrintfExA` at `0x18004207b`

## string_xrefs

- `0x180041fa7`: `IsRasmanServiceRunning: OpenSCManager failed with %d`
- `0x180041ff2`: `IsRasmanServiceRunning: OpenService failed with %d`
- `0x18004202f`: `IsRasmanServiceRunning: QueryServiceStatus failed with %d`
- `0x18004206f`: `IsRasmanServiceRunning=%d`

## pseudocode

```c
__int64 IsRasmanServiceRunning()
{
  unsigned int v0; // edi
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rbp
  DWORD v3; // eax
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // r14
  DWORD v6; // eax
  DWORD LastError; // eax
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v0 = 0;
  v1 = OpenSCManagerW(0, 0, 0x80000000);
  v2 = v1;
  if ( v1 )
  {
    v4 = OpenServiceW(v1, L"RASMAN", 4u);
    v5 = v4;
    if ( v4 )
    {
      if ( QueryServiceStatus(v4, &ServiceStatus) )
      {
        LOBYTE(v0) = ServiceStatus.dwCurrentState == 4;
      }
      else if ( g_dwTraceId != -1 )
      {
        LastError = GetLastError();
        TracePrintfExA(g_dwTraceId, 0xCu, "IsRasmanServiceRunning: QueryServiceStatus failed with %d", LastError);
      }
      CloseServiceHandle(v5);
    }
    else if ( g_dwTraceId != -1 )
    {
      v6 = GetLastError();
      TracePrintfExA(g_dwTraceId, 0xCu, "IsRasmanServiceRunning: OpenService failed with %d", v6);
    }
    CloseServiceHandle(v2);
  }
  else
  {
    if ( g_dwTraceId == -1 )
      return v0;
    v3 = GetLastError();
    TracePrintfExA(g_dwTraceId, 0xCu, "IsRasmanServiceRunning: OpenSCManager failed with %d", v3);
  }
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "IsRasmanServiceRunning=%d", v0);
  return v0;
}

```

## disassembly

```asm
0x180041f48  mov     [rsp+arg_0], rbp
0x180041f4d  mov     [rsp+arg_8], rdi
0x180041f52  push    r14
0x180041f54  sub     rsp, 50h
0x180041f58  mov     rax, cs:__security_cookie
0x180041f5f  xor     rax, rsp
0x180041f62  mov     [rsp+58h+var_18], rax
0x180041f67  xorps   xmm0, xmm0
0x180041f6a  xor     edx, edx; lpDatabaseName
0x180041f6c  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x180041f71  xor     ecx, ecx; lpMachineName
0x180041f73  mov     r8d, 80000000h; dwDesiredAccess
0x180041f79  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x180041f7e  xor     edi, edi
0x180041f80  call    cs:__imp_OpenSCManagerW
0x180041f86  mov     rbp, rax
0x180041f89  test    rax, rax
0x180041f8c  jnz     short loc_180041FBF
0x180041f8e  cmp     cs:g_dwTraceId, 0FFFFFFFFh
0x180041f95  jz      loc_180042081
0x180041f9b  call    cs:__imp_GetLastError
0x180041fa1  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180041fa7  lea     r8, aIsrasmanservic_0; "IsRasmanServiceRunning: OpenSCManager f"...
0x180041fae  mov     r9d, eax
0x180041fb1  lea     edx, [rdi+0Ch]; dwFlags
0x180041fb4  call    cs:__imp_TracePrintfExA
0x180041fba  jmp     loc_180042061
0x180041fbf  mov     r8d, 4; dwDesiredAccess
0x180041fc5  lea     rdx, aRasman; "RASMAN"
0x180041fcc  mov     rcx, rbp; hSCManager
0x180041fcf  call    cs:__imp_OpenServiceW
0x180041fd5  mov     r14, rax
0x180041fd8  test    rax, rax
0x180041fdb  jnz     short loc_180042008
0x180041fdd  cmp     cs:g_dwTraceId, 0FFFFFFFFh
0x180041fe4  jz      short loc_180042058
0x180041fe6  call    cs:__imp_GetLastError
0x180041fec  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180041ff2  lea     r8, aIsrasmanservic_1; "IsRasmanServiceRunning: OpenService fai"...
0x180041ff9  mov     r9d, eax
0x180041ffc  lea     edx, [r14+0Ch]; dwFlags
0x180042000  call    cs:__imp_TracePrintfExA
0x180042006  jmp     short loc_180042058
0x180042008  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x18004200d  mov     rcx, r14; hService
0x180042010  call    cs:__imp_QueryServiceStatus
0x180042016  test    eax, eax
0x180042018  jnz     short loc_180042046
0x18004201a  cmp     cs:g_dwTraceId, 0FFFFFFFFh
0x180042021  jz      short loc_18004204F
0x180042023  call    cs:__imp_GetLastError
0x180042029  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18004202f  lea     r8, aIsrasmanservic; "IsRasmanServiceRunning: QueryServiceSta"...
0x180042036  mov     r9d, eax
0x180042039  mov     edx, 0Ch; dwFlags
0x18004203e  call    cs:__imp_TracePrintfExA
0x180042044  jmp     short loc_18004204F
0x180042046  cmp     [rsp+58h+ServiceStatus.dwCurrentState], 4
0x18004204b  setz    dil
0x18004204f  mov     rcx, r14; hSCObject
0x180042052  call    cs:__imp_CloseServiceHandle
0x180042058  mov     rcx, rbp; hSCObject
0x18004205b  call    cs:__imp_CloseServiceHandle
0x180042061  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180042067  cmp     ecx, 0FFFFFFFFh
0x18004206a  jz      short loc_180042081
0x18004206c  mov     r9d, edi
0x18004206f  lea     r8, aIsrasmanservic_2; "IsRasmanServiceRunning=%d"
0x180042076  mov     edx, 0Ch; dwFlags
0x18004207b  call    cs:__imp_TracePrintfExA
0x180042081  mov     eax, edi
0x180042083  mov     rcx, [rsp+58h+var_18]
0x180042088  xor     rcx, rsp; StackCookie
0x18004208b  call    __security_check_cookie
0x180042090  mov     rbp, [rsp+58h+arg_0]
0x180042095  mov     rdi, [rsp+58h+arg_8]
0x18004209a  add     rsp, 50h
0x18004209e  pop     r14
0x1800420a0  retn
```
