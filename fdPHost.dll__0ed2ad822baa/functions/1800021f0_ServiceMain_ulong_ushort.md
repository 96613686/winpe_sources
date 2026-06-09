# ServiceMain(ulong,ushort * *)

- ea: `0x1800021f0`
- end: `0x180002280`
- name: `?ServiceMain@@YAXKPEAPEAG@Z`
- size: `144`
- prototype: `void __fastcall(__int64, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callees

- `0x1800021f0`
- `0x180002288`
- `0x180002510`
- `0x18000284c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000224d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000224d`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000223b`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000223b`

## pseudocode

```c
void __fastcall ServiceMain(__int64 a1, unsigned __int16 **a2)
{
  int LastError; // eax
  bool v3; // zf

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_fe2b77c2a50e30d09de66304557b9354_Traceguids);
  _InterlockedExchange(&g_ServiceControlFlags, 0);
  hServiceStatus = RegisterServiceCtrlHandlerExW(L"fdPHost", ServiceCtrlHandler, 0);
  if ( !hServiceStatus )
  {
    LastError = GetLastError();
    v3 = LastError == 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v3 = LastError == 0;
    }
    if ( !v3 )
      goto LABEL_9;
  }
  LastError = ServiceStartup();
  if ( LastError )
  {
LABEL_9:
    ServiceStatus.dwWin32ExitCode = LastError;
    ServiceStopCallback(0, 0);
  }
}

```

## disassembly

```asm
0x1800021f0  sub     rsp, 28h
0x1800021f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800021fb  lea     rax, WPP_GLOBAL_Control
0x180002202  cmp     rcx, rax
0x180002205  jz      short loc_180002222
0x180002207  cmp     byte ptr [rcx+19h], 4
0x18000220b  jb      short loc_180002222
0x18000220d  mov     rcx, [rcx+10h]
0x180002211  lea     r8, WPP_fe2b77c2a50e30d09de66304557b9354_Traceguids
0x180002218  mov     edx, 16h
0x18000221d  call    WPP_SF_s
0x180002222  xor     eax, eax
0x180002224  lea     rdx, ?ServiceCtrlHandler@@YAKKKPEAX0@Z; lpHandlerProc
0x18000222b  xchg    eax, cs:?g_ServiceControlFlags@@3JC; long volatile g_ServiceControlFlags
0x180002231  xor     r8d, r8d; lpContext
0x180002234  lea     rcx, ServiceName; "fdPHost"
0x18000223b  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180002241  mov     cs:hServiceStatus, rax
0x180002248  test    rax, rax
0x18000224b  jnz     short loc_180002263
0x18000224d  call    cs:__imp_GetLastError
0x180002253  test    eax, eax
0x180002255  jle     short loc_180002261
0x180002257  movzx   eax, ax
0x18000225a  or      eax, 80070000h
0x18000225f  test    eax, eax
0x180002261  jnz     short loc_18000226C
0x180002263  call    ?ServiceStartup@@YAJXZ; ServiceStartup(void)
0x180002268  test    eax, eax
0x18000226a  jz      short loc_18000227B
0x18000226c  xor     edx, edx; unsigned __int8
0x18000226e  mov     cs:ServiceStatus.dwWin32ExitCode, eax
0x180002274  xor     ecx, ecx; void *
0x180002276  call    ?ServiceStopCallback@@YAXPEAXE@Z; ServiceStopCallback(void *,uchar)
0x18000227b  add     rsp, 28h
0x18000227f  retn
```
