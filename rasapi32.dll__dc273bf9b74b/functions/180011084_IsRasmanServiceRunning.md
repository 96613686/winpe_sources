# IsRasmanServiceRunning

- ea: `0x180011084`
- end: `0x1800111ed`
- name: `IsRasmanServiceRunning`
- size: `361`
- prototype: `__int64(void)`
- caller_count: `23`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180007b98`
- `0x180010180`
- `0x1800103d0`
- `0x1800111f4`
- `0x180012bd0`
- `0x180027b00`
- `0x180028050`
- `0x180030890`
- `0x18003d3d0`
- `0x180043890`
- `0x18006b750`
- `0x18006b980`
- `0x18006bd14`
- `0x18006e830`
- `0x180072b10`
- `0x180072e70`
- `0x1800730a0`
- `0x1800739a0`
- `0x180074290`
- `0x180074cc0`
- `0x1800754f0`
- `0x180075e60`
- `0x18007d7c0`

## callees

- `0x180011084`
- `0x1800ded50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011168`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011194`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800111c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011168`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011194`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800111c7`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800110dc`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800110dc`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180011110`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180011119`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180011110`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180011119`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800110bc`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800110bc`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800110f6`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800110f6`
- `rtutils!TracePrintfExA` at `0x180011139`
- `rtutils!TracePrintfExA` at `0x180011183`
- `rtutils!TracePrintfExA` at `0x1800111af`
- `rtutils!TracePrintfExA` at `0x1800111e2`
- `rtutils!TracePrintfExA` at `0x180011139`
- `rtutils!TracePrintfExA` at `0x180011183`
- `rtutils!TracePrintfExA` at `0x1800111af`
- `rtutils!TracePrintfExA` at `0x1800111e2`

## string_xrefs

- `0x18001112d`: `IsRasmanServiceRunning=%d`
- `0x1800111a0`: `IsRasmanServiceRunning: OpenService failed with %d`
- `0x1800111d3`: `IsRasmanServiceRunning: QueryServiceStatus failed with %d`
- `0x180011174`: `IsRasmanServiceRunning: OpenSCManager failed with %d`

## pseudocode

```c
__int64 IsRasmanServiceRunning()
{
  unsigned int v0; // edi
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rbp
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // r14
  DWORD v6; // eax
  DWORD v7; // eax
  DWORD LastError; // eax
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v0 = 0;
  v1 = OpenSCManagerW(0, 0, 0x80000000);
  v2 = v1;
  if ( v1 )
  {
    v3 = OpenServiceW(v1, L"RASMAN", 4u);
    v4 = v3;
    if ( v3 )
    {
      if ( QueryServiceStatus(v3, &ServiceStatus) )
      {
        LOBYTE(v0) = ServiceStatus.dwCurrentState == 4;
      }
      else if ( g_dwTraceId != -1 )
      {
        LastError = GetLastError();
        TracePrintfExA(g_dwTraceId, 0xCu, "IsRasmanServiceRunning: QueryServiceStatus failed with %d", LastError);
      }
      CloseServiceHandle(v4);
    }
    else if ( g_dwTraceId != -1 )
    {
      v7 = GetLastError();
      TracePrintfExA(g_dwTraceId, 0xCu, "IsRasmanServiceRunning: OpenService failed with %d", v7);
    }
    CloseServiceHandle(v2);
  }
  else
  {
    if ( g_dwTraceId == -1 )
      return v0;
    v6 = GetLastError();
    TracePrintfExA(g_dwTraceId, 0xCu, "IsRasmanServiceRunning: OpenSCManager failed with %d", v6);
  }
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "IsRasmanServiceRunning=%d", v0);
  return v0;
}

```

## disassembly

```asm
0x180011084  mov     [rsp+arg_0], rbp
0x180011089  mov     [rsp+arg_8], rdi
0x18001108e  push    r14
0x180011090  sub     rsp, 50h
0x180011094  mov     rax, cs:__security_cookie
0x18001109b  xor     rax, rsp
0x18001109e  mov     [rsp+58h+var_18], rax
0x1800110a3  xorps   xmm0, xmm0
0x1800110a6  xor     edx, edx; lpDatabaseName
0x1800110a8  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x1800110ad  xor     ecx, ecx; lpMachineName
0x1800110af  mov     r8d, 80000000h; dwDesiredAccess
0x1800110b5  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800110ba  xor     edi, edi
0x1800110bc  call    cs:__imp_OpenSCManagerW
0x1800110c2  mov     rbp, rax
0x1800110c5  test    rax, rax
0x1800110c8  jz      loc_18001115F
0x1800110ce  lea     r8d, [rdi+4]; dwDesiredAccess
0x1800110d2  mov     rcx, rax; hSCManager
0x1800110d5  lea     rdx, ServiceName; "RASMAN"
0x1800110dc  call    cs:__imp_OpenServiceW
0x1800110e2  mov     r14, rax
0x1800110e5  test    rax, rax
0x1800110e8  jz      loc_18001118B
0x1800110ee  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x1800110f3  mov     rcx, rax; hService
0x1800110f6  call    cs:__imp_QueryServiceStatus
0x1800110fc  test    eax, eax
0x1800110fe  jz      loc_1800111BA
0x180011104  cmp     [rsp+58h+ServiceStatus.dwCurrentState], 4
0x180011109  setz    dil
0x18001110d  mov     rcx, r14; hSCObject
0x180011110  call    cs:__imp_CloseServiceHandle
0x180011116  mov     rcx, rbp; hSCObject
0x180011119  call    cs:__imp_CloseServiceHandle
0x18001111f  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180011125  cmp     ecx, 0FFFFFFFFh
0x180011128  jz      short loc_18001113F
0x18001112a  mov     r9d, edi
0x18001112d  lea     r8, aIsrasmanservic_2; "IsRasmanServiceRunning=%d"
0x180011134  mov     edx, 0Ch; dwFlags
0x180011139  call    cs:__imp_TracePrintfExA
0x18001113f  mov     eax, edi
0x180011141  mov     rcx, [rsp+58h+var_18]
0x180011146  xor     rcx, rsp; StackCookie
0x180011149  call    __security_check_cookie
0x18001114e  mov     rbp, [rsp+58h+arg_0]
0x180011153  mov     rdi, [rsp+58h+arg_8]
0x180011158  add     rsp, 50h
0x18001115c  pop     r14
0x18001115e  retn
0x18001115f  cmp     cs:g_dwTraceId, 0FFFFFFFFh
0x180011166  jz      short loc_18001113F
0x180011168  call    cs:__imp_GetLastError
0x18001116e  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180011174  lea     r8, aIsrasmanservic_0; "IsRasmanServiceRunning: OpenSCManager f"...
0x18001117b  mov     r9d, eax
0x18001117e  mov     edx, 0Ch; dwFlags
0x180011183  call    cs:__imp_TracePrintfExA
0x180011189  jmp     short loc_18001111F
0x18001118b  cmp     cs:g_dwTraceId, 0FFFFFFFFh
0x180011192  jz      short loc_180011116
0x180011194  call    cs:__imp_GetLastError
0x18001119a  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800111a0  lea     r8, aIsrasmanservic_1; "IsRasmanServiceRunning: OpenService fai"...
0x1800111a7  mov     r9d, eax
0x1800111aa  mov     edx, 0Ch; dwFlags
0x1800111af  call    cs:__imp_TracePrintfExA
0x1800111b5  jmp     loc_180011116
0x1800111ba  cmp     cs:g_dwTraceId, 0FFFFFFFFh
0x1800111c1  jz      loc_18001110D
0x1800111c7  call    cs:__imp_GetLastError
0x1800111cd  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800111d3  lea     r8, aIsrasmanservic; "IsRasmanServiceRunning: QueryServiceSta"...
0x1800111da  mov     r9d, eax
0x1800111dd  mov     edx, 0Ch; dwFlags
0x1800111e2  call    cs:__imp_TracePrintfExA
0x1800111e8  jmp     loc_18001110D
```
