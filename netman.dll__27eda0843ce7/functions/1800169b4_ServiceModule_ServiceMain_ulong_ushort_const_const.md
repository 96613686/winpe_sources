# ServiceModule::ServiceMain(ulong,ushort const * * const)

- ea: `0x1800169b4`
- end: `0x180016a96`
- name: `?ServiceMain@ServiceModule@@QEAAXKQEAPEBG@Z`
- size: `226`
- prototype: `void __fastcall(ServiceModule *__hidden this, unsigned int, const unsigned __int16 **const)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x180005240`

## callees

- `0x18000538c`
- `0x180016688`
- `0x1800169b4`
- `0x1800171b8`
- `0x180019200`
- `0x18003060c`

## import_xrefs

- `ADVAPI32!RegisterServiceCtrlHandlerExW` at `0x180016a34`
- `ADVAPI32!RegisterServiceCtrlHandlerExW` at `0x180016a34`
- `KERNEL32!GetCurrentThreadId` at `0x1800169fc`
- `KERNEL32!GetCurrentThreadId` at `0x1800169fc`

## pseudocode

```c
void __fastcall ServiceModule::ServiceMain(ServiceModule *this, __int64 a2, const unsigned __int16 **const a3)
{
  ServiceModule *v3; // rcx
  ServiceModule *v4; // rcx
  unsigned int Win32Error; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_b4d1654223233927dad0a39c06a0afa5_Traceguids);
  g_lRasEntryModifiedVersionEra = 0;
  dword_180044F2C = 0;
  dword_180044F00 = GetCurrentThreadId();
  *(_OWORD *)&ServiceStatus.dwServiceType = 0;
  ServiceStatus.dwServiceType = 32;
  *(_OWORD *)&ServiceStatus.dwWin32ExitCode = 0;
  hRecipient = RegisterServiceCtrlHandlerExW(L"netman", (LPHANDLER_FUNCTION_EX)ServiceModule::_DwHandler, 0);
  if ( hRecipient )
  {
    ServiceModule::SetServiceStatus(v3, 2u);
    ServiceModule::Run(v4);
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    Win32Error = HrFromLastWin32Error();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_b4d1654223233927dad0a39c06a0afa5_Traceguids, Win32Error);
  }
}

```

## disassembly

```asm
0x1800169b4  push    rbx
0x1800169b6  sub     rsp, 20h
0x1800169ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800169c1  lea     rbx, WPP_GLOBAL_Control
0x1800169c8  cmp     rcx, rbx
0x1800169cb  jz      short loc_1800169E8
0x1800169cd  test    byte ptr [rcx+1Ch], 8
0x1800169d1  jz      short loc_1800169E8
0x1800169d3  mov     rcx, [rcx+10h]
0x1800169d7  lea     r8, WPP_b4d1654223233927dad0a39c06a0afa5_Traceguids
0x1800169de  mov     edx, 1Eh
0x1800169e3  call    WPP_SF_
0x1800169e8  mov     cs:?g_lRasEntryModifiedVersionEra@@3JA, 0; long g_lRasEntryModifiedVersionEra
0x1800169f2  mov     cs:dword_180044F2C, 0
0x1800169fc  call    cs:__imp_GetCurrentThreadId
0x180016a02  xorps   xmm0, xmm0
0x180016a05  lea     rdx, ?_DwHandler@ServiceModule@@CAKKKPEAX0@Z; lpHandlerProc
0x180016a0c  lea     rcx, ServiceName; "netman"
0x180016a13  mov     cs:dword_180044F00, eax
0x180016a19  movups  xmmword ptr cs:ServiceStatus.dwServiceType, xmm0
0x180016a20  xor     r8d, r8d; lpContext
0x180016a23  mov     cs:ServiceStatus.dwServiceType, 20h ; ' '
0x180016a2d  movups  xmmword ptr cs:ServiceStatus.dwWin32ExitCode, xmm0
0x180016a34  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180016a3a  mov     cs:hRecipient, rax
0x180016a41  test    rax, rax
0x180016a44  jz      short loc_180016A5A
0x180016a46  mov     edx, 2; unsigned int
0x180016a4b  call    ?SetServiceStatus@ServiceModule@@QEAAXK@Z; ServiceModule::SetServiceStatus(ulong)
0x180016a50  add     rsp, 20h
0x180016a54  pop     rbx
0x180016a55  jmp     ?Run@ServiceModule@@QEAAXXZ; ServiceModule::Run(void)
0x180016a5a  mov     rax, cs:WPP_GLOBAL_Control
0x180016a61  cmp     rax, rbx
0x180016a64  jz      short loc_180016A90
0x180016a66  test    byte ptr [rax+1Ch], 8
0x180016a6a  jz      short loc_180016A90
0x180016a6c  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180016a71  mov     rcx, cs:WPP_GLOBAL_Control
0x180016a78  lea     r8, WPP_b4d1654223233927dad0a39c06a0afa5_Traceguids
0x180016a7f  mov     edx, 1Fh
0x180016a84  mov     r9d, eax
0x180016a87  mov     rcx, [rcx+10h]
0x180016a8b  call    WPP_SF_d
0x180016a90  add     rsp, 20h
0x180016a94  pop     rbx
0x180016a95  retn
```
