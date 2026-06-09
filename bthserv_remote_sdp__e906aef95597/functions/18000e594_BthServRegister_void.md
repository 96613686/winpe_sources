# BthServRegister(void)

- ea: `0x18000e594`
- end: `0x18000e65b`
- name: `?BthServRegister@@YAXXZ`
- size: `199`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180010f60`

## callees

- `0x18000e594`
- `0x180012384`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000e5e3`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000e5e3`

## pseudocode

```c
void BthServRegister(void)
{
  _UNKNOWN **v0; // rdx
  _UNKNOWN **v1; // r8

  ServiceStatus.dwWin32ExitCode = 0;
  ServiceStatus.dwServiceSpecificExitCode = 0;
  ServiceStatus.dwCheckPoint = 0;
  ServiceStatus.dwWaitHint = 0;
  ServiceStatus.dwServiceType = 32;
  ServiceStatus.dwCurrentState = 2;
  ServiceStatus.dwControlsAccepted = 133;
  hServiceStatus = RegisterServiceCtrlHandlerExW(L"BthServ", (LPHANDLER_FUNCTION_EX)ServiceHandlerEx, 0);
  v0 = &WPP_GLOBAL_Control;
  LOBYTE(v0) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  v1 = &WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)v0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v1) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)v0,
      (_DWORD)v1,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  }
}

```

## disassembly

```asm
0x18000e594  sub     rsp, 58h
0x18000e598  and     cs:ServiceStatus.dwWin32ExitCode, 0
0x18000e59f  lea     rdx, ?ServiceHandlerEx@@YAKKKPEAX0@Z; lpHandlerProc
0x18000e5a6  and     cs:ServiceStatus.dwServiceSpecificExitCode, 0
0x18000e5ad  lea     rcx, ServiceName; "BthServ"
0x18000e5b4  and     cs:ServiceStatus.dwCheckPoint, 0
0x18000e5bb  xor     r8d, r8d; lpContext
0x18000e5be  and     cs:ServiceStatus.dwWaitHint, 0
0x18000e5c5  mov     cs:ServiceStatus.dwServiceType, 20h ; ' '
0x18000e5cf  mov     cs:ServiceStatus.dwCurrentState, 2
0x18000e5d9  mov     cs:ServiceStatus.dwControlsAccepted, 85h
0x18000e5e3  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18000e5ea  nop     dword ptr [rax+rax+00h]
0x18000e5ef  mov     cs:hServiceStatus, rax
0x18000e5f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e5fd  lea     rdx, WPP_GLOBAL_Control
0x18000e604  cmp     rcx, rdx
0x18000e607  jz      short loc_18000E613
0x18000e609  cmp     byte ptr [rcx+19h], 5
0x18000e60d  jb      short loc_18000E613
0x18000e60f  mov     dl, 1
0x18000e611  jmp     short loc_18000E615
0x18000e613  xor     dl, dl
0x18000e615  lea     r8, WPP_RECORDER_INITIALIZED
0x18000e61c  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x18000e623  setnz   r8b
0x18000e627  test    dl, dl
0x18000e629  jnz     short loc_18000E630
0x18000e62b  test    r8b, r8b
0x18000e62e  jz      short loc_18000E655
0x18000e630  mov     r9, [rcx+28h]
0x18000e634  mov     rcx, [rcx+10h]
0x18000e638  mov     [rsp+58h+var_10], rax
0x18000e63d  lea     rax, WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids
0x18000e644  mov     [rsp+58h+var_20], rax
0x18000e649  mov     [rsp+58h+var_28], 26h ; '&'
0x18000e650  call    WPP_RECORDER_AND_TRACE_SF_si
0x18000e655  add     rsp, 58h
0x18000e659  retn
```
