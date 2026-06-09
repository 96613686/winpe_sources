# StartTapiService

- ea: `0x180015280`
- end: `0x180015362`
- name: `StartTapiService`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800158c0`

## callees

- `0x18000d92c`
- `0x180015280`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800152a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800152de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015311`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800152a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800152de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015311`
- `api-ms-win-service-winsvc-l1-1-0!StartServiceA` at `0x1800152fe`
- `api-ms-win-service-winsvc-l1-1-0!StartServiceA` at `0x1800152fe`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x1800152d0`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x1800152d0`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x180015297`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x180015297`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180015341`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001534a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180015341`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001534a`

## string_xrefs

- `0x1800152ad`: `StartTapiService: OpenSCManager failed (0x%x)`
- `0x1800152e6`: `StartTapiService: OpenService failed (0x%x)`
- `0x180015308`: `StartTapiService: TapiSrv started successfully`
- `0x180015320`: `StartTapiService: TapiSrv already running`
- `0x180015332`: `StartTapiService: TapiSrv could not be started. Error 0x%x`

## pseudocode

```c
__int64 StartTapiService()
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rdi
  DWORD LastError; // ebx
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rsi
  const CHAR *v5; // rcx

  v0 = OpenSCManagerA(0, 0, 1u);
  v1 = v0;
  if ( v0 )
  {
    v3 = OpenServiceA(v0, "TapiSrv", 0x10u);
    v4 = v3;
    if ( !v3 )
    {
      LastError = GetLastError();
      RasTapiTrace("StartTapiService: OpenService failed (0x%x)");
LABEL_12:
      CloseServiceHandle(v1);
      return LastError;
    }
    if ( StartServiceA(v3, 0, 0) )
    {
      v5 = "StartTapiService: TapiSrv started successfully";
    }
    else
    {
      LastError = GetLastError();
      if ( LastError != 1056 )
      {
        RasTapiTrace("StartTapiService: TapiSrv could not be started. Error 0x%x");
        goto LABEL_11;
      }
      v5 = "StartTapiService: TapiSrv already running";
    }
    LastError = 0;
    RasTapiTrace(v5);
LABEL_11:
    CloseServiceHandle(v4);
    goto LABEL_12;
  }
  LastError = GetLastError();
  RasTapiTrace("StartTapiService: OpenSCManager failed (0x%x)");
  return LastError;
}

```

## disassembly

```asm
0x180015280  mov     [rsp+arg_0], rbx
0x180015285  mov     [rsp+arg_8], rsi
0x18001528a  push    rdi
0x18001528b  sub     rsp, 20h
0x18001528f  xor     edx, edx; lpDatabaseName
0x180015291  xor     ecx, ecx; lpMachineName
0x180015293  lea     r8d, [rdx+1]; dwDesiredAccess
0x180015297  call    cs:__imp_OpenSCManagerA
0x18001529d  mov     rdi, rax
0x1800152a0  test    rax, rax
0x1800152a3  jnz     short loc_1800152C0
0x1800152a5  call    cs:__imp_GetLastError
0x1800152ab  mov     edx, eax
0x1800152ad  lea     rcx, aStarttapiservi_3; "StartTapiService: OpenSCManager failed "...
0x1800152b4  mov     ebx, eax
0x1800152b6  call    RasTapiTrace
0x1800152bb  jmp     loc_180015350
0x1800152c0  mov     r8d, 10h; dwDesiredAccess
0x1800152c6  lea     rdx, ServiceName; "TapiSrv"
0x1800152cd  mov     rcx, rdi; hSCManager
0x1800152d0  call    cs:__imp_OpenServiceA
0x1800152d6  mov     rsi, rax
0x1800152d9  test    rax, rax
0x1800152dc  jnz     short loc_1800152F6
0x1800152de  call    cs:__imp_GetLastError
0x1800152e4  mov     edx, eax
0x1800152e6  lea     rcx, aStarttapiservi_1; "StartTapiService: OpenService failed (0"...
0x1800152ed  mov     ebx, eax
0x1800152ef  call    RasTapiTrace
0x1800152f4  jmp     short loc_180015347
0x1800152f6  xor     r8d, r8d; lpServiceArgVectors
0x1800152f9  xor     edx, edx; dwNumServiceArgs
0x1800152fb  mov     rcx, rsi; hService
0x1800152fe  call    cs:__imp_StartServiceA
0x180015304  test    eax, eax
0x180015306  jz      short loc_180015311
0x180015308  lea     rcx, aStarttapiservi_2; "StartTapiService: TapiSrv started succe"...
0x18001530f  jmp     short loc_180015327
0x180015311  call    cs:__imp_GetLastError
0x180015317  mov     ebx, eax
0x180015319  cmp     eax, 420h
0x18001531e  jnz     short loc_180015330
0x180015320  lea     rcx, aStarttapiservi_0; "StartTapiService: TapiSrv already runni"...
0x180015327  xor     ebx, ebx
0x180015329  call    RasTapiTrace
0x18001532e  jmp     short loc_18001533E
0x180015330  mov     edx, eax
0x180015332  lea     rcx, aStarttapiservi; "StartTapiService: TapiSrv could not be "...
0x180015339  call    RasTapiTrace
0x18001533e  mov     rcx, rsi; hSCObject
0x180015341  call    cs:__imp_CloseServiceHandle
0x180015347  mov     rcx, rdi; hSCObject
0x18001534a  call    cs:__imp_CloseServiceHandle
0x180015350  mov     rsi, [rsp+28h+arg_8]
0x180015355  mov     eax, ebx
0x180015357  mov     rbx, [rsp+28h+arg_0]
0x18001535c  add     rsp, 20h
0x180015360  pop     rdi
0x180015361  retn
```
