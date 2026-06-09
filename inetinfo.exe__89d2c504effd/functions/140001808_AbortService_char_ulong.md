# AbortService(char *,ulong)

- ea: `0x140001808`
- end: `0x140001923`
- name: `?AbortService@@YAXPEADK@Z`
- size: `283`
- prototype: `void __fastcall(char *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x140001b40`

## callees

- `0x140001808`
- `0x140002850`

## import_xrefs

- `ADVAPI32!RegisterServiceCtrlHandlerA` at `0x14000185c`
- `ADVAPI32!RegisterServiceCtrlHandlerA` at `0x14000185c`
- `ADVAPI32!SetServiceStatus` at `0x1400018a4`
- `ADVAPI32!SetServiceStatus` at `0x1400018a4`
- `KERNEL32!GetLastError` at `0x140001867`
- `KERNEL32!GetLastError` at `0x1400018ae`
- `KERNEL32!GetLastError` at `0x140001867`
- `KERNEL32!GetLastError` at `0x1400018ae`
- `msvcrt!sprintf_s` at `0x140001885`
- `msvcrt!sprintf_s` at `0x1400018cc`
- `msvcrt!sprintf_s` at `0x140001885`
- `msvcrt!sprintf_s` at `0x1400018cc`
- `iisutil!PuDbgPrint` at `0x140001900`
- `iisutil!PuDbgPrint` at `0x140001900`

## string_xrefs

- `0x140001870`: `[Inetinfo]RegisterServiceCtrlHandler[%s] failed %d\n`
- `0x1400018ed`: `AbortService`
- `0x1400018b7`: `[Inetinfo]SetServiceStatus[%s] error %ld\n`

## pseudocode

```c
void __fastcall AbortService(char *a1, DWORD a2)
{
  SERVICE_STATUS_HANDLE v3; // rax
  DWORD LastError; // eax
  __int64 v5; // r8
  DWORD v6; // eax
  _SERVICE_STATUS ServiceStatus; // [rsp+30h] [rbp-D0h] BYREF
  char Buffer[256]; // [rsp+50h] [rbp-B0h] BYREF

  ServiceStatus.dwWin32ExitCode = a2;
  ServiceStatus.dwCurrentState = 1;
  ServiceStatus.dwControlsAccepted = 1;
  ServiceStatus.dwServiceType = 48;
  *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
  ServiceStatus.dwServiceSpecificExitCode = 0;
  v3 = RegisterServiceCtrlHandlerA(a1, DummyCtrlHandler);
  if ( !v3 )
  {
    LastError = GetLastError();
    sprintf_s(Buffer, 0x100u, "[Inetinfo]RegisterServiceCtrlHandler[%s] failed %d\n", a1, LastError);
    if ( (g_dwDebugFlags & 3) == 0 )
      return;
    v5 = 669;
    goto LABEL_7;
  }
  if ( !SetServiceStatus(v3, &ServiceStatus) )
  {
    v6 = GetLastError();
    sprintf_s(Buffer, 0x100u, "[Inetinfo]SetServiceStatus[%s] error %ld\n", a1, v6);
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      v5 = 676;
LABEL_7:
      PuDbgPrint(g_pDebug, "inetsrv\\iis\\iisrearc\\iisplus\\inetinfo\\main.cxx", v5, "AbortService", Buffer);
    }
  }
}

```

## disassembly

```asm
0x140001808  mov     [rsp-8+arg_10], rbx
0x14000180d  push    rbp
0x14000180e  lea     rbp, [rsp-60h]
0x140001813  sub     rsp, 160h
0x14000181a  mov     rax, cs:__security_cookie
0x140001821  xor     rax, rsp
0x140001824  mov     [rbp+60h+var_10], rax
0x140001828  mov     eax, 1
0x14000182d  mov     [rsp+160h+ServiceStatus.dwWin32ExitCode], edx
0x140001831  lea     rdx, ?DummyCtrlHandler@@YAXK@Z; lpHandlerProc
0x140001838  mov     [rsp+160h+ServiceStatus.dwCurrentState], eax
0x14000183c  mov     [rsp+160h+ServiceStatus.dwControlsAccepted], eax
0x140001840  mov     rbx, rcx
0x140001843  mov     [rsp+160h+ServiceStatus.dwServiceType], 30h ; '0'
0x14000184b  mov     qword ptr [rsp+160h+ServiceStatus.dwCheckPoint], 0
0x140001854  mov     [rsp+160h+ServiceStatus.dwServiceSpecificExitCode], 0
0x14000185c  call    cs:__imp_RegisterServiceCtrlHandlerA
0x140001862  test    rax, rax
0x140001865  jnz     short loc_14000189C
0x140001867  call    cs:__imp_GetLastError
0x14000186d  mov     r9, rbx
0x140001870  lea     r8, Format; "[Inetinfo]RegisterServiceCtrlHandler[%s"...
0x140001877  lea     rcx, [rsp+160h+Buffer]; Buffer
0x14000187c  mov     dword ptr [rsp+160h+var_140], eax
0x140001880  mov     edx, 100h; BufferCount
0x140001885  call    cs:__imp_sprintf_s
0x14000188b  test    cs:g_dwDebugFlags, 3
0x140001892  jz      short loc_140001906
0x140001894  mov     r8d, 29Dh
0x14000189a  jmp     short loc_1400018E1
0x14000189c  lea     rdx, [rsp+160h+ServiceStatus]; lpServiceStatus
0x1400018a1  mov     rcx, rax; hServiceStatus
0x1400018a4  call    cs:__imp_SetServiceStatus
0x1400018aa  test    eax, eax
0x1400018ac  jnz     short loc_140001906
0x1400018ae  call    cs:__imp_GetLastError
0x1400018b4  mov     r9, rbx
0x1400018b7  lea     r8, aInetinfoSetser; "[Inetinfo]SetServiceStatus[%s] error %l"...
0x1400018be  lea     rcx, [rsp+160h+Buffer]; Buffer
0x1400018c3  mov     dword ptr [rsp+160h+var_140], eax
0x1400018c7  mov     edx, 100h; BufferCount
0x1400018cc  call    cs:__imp_sprintf_s
0x1400018d2  test    cs:g_dwDebugFlags, 3
0x1400018d9  jz      short loc_140001906
0x1400018db  mov     r8d, 2A4h
0x1400018e1  mov     rcx, cs:g_pDebug
0x1400018e8  lea     rax, [rsp+160h+Buffer]
0x1400018ed  lea     r9, aAbortservice; "AbortService"
0x1400018f4  mov     [rsp+160h+var_140], rax
0x1400018f9  lea     rdx, aInetsrvIisIisr; "inetsrv\\iis\\iisrearc\\iisplus\\inetin"...
0x140001900  call    cs:__imp_PuDbgPrint
0x140001906  mov     rcx, [rbp+60h+var_10]
0x14000190a  xor     rcx, rsp; StackCookie
0x14000190d  call    __security_check_cookie
0x140001912  mov     rbx, [rsp+160h+arg_10]
0x14000191a  add     rsp, 160h
0x140001921  pop     rbp
0x140001922  retn
```
