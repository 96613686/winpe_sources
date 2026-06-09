# NGENService::InitService(void)

- ea: `0x18001a9d8`
- end: `0x18001ac2e`
- name: `?InitService@NGENService@@YAJXZ`
- size: `598`
- prototype: `__int64 __fastcall(NGENService *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x18001b340`

## callees

- `0x180001e8c`
- `0x1800020f0`
- `0x1800046c4`
- `0x180004af4`
- `0x18001a9d8`
- `0x18002dca8`
- `0x18002e1d0`
- `0x180030d84`
- `0x180036fd0`
- `0x18003dc30`
- `0x18003f280`

## import_xrefs

- `KERNEL32!SetConsoleCtrlHandler` at `0x18001ab47`
- `KERNEL32!SetConsoleCtrlHandler` at `0x18001ab47`
- `KERNEL32!SetProcessShutdownParameters` at `0x18001ab61`
- `KERNEL32!SetProcessShutdownParameters` at `0x18001ab61`
- `KERNEL32!LoadLibraryExW` at `0x18001aab3`
- `KERNEL32!LoadLibraryExW` at `0x18001aab3`
- `KERNEL32!CloseHandle` at `0x18001abf5`
- `KERNEL32!CloseHandle` at `0x18001abf5`
- `KERNEL32!CreateEventW` at `0x18001ab11`
- `KERNEL32!CreateEventW` at `0x18001ab11`
- `KERNEL32!GetLastError` at `0x18001ab77`
- `KERNEL32!GetLastError` at `0x18001ab77`
- `KERNEL32!GetProcAddress` at `0x18001aac8`
- `KERNEL32!GetProcAddress` at `0x18001aac8`
- `KERNEL32!HeapFree` at `0x18001abe2`
- `KERNEL32!HeapFree` at `0x18001abe2`
- `KERNEL32!GetProcessHeap` at `0x18001abcd`
- `KERNEL32!GetProcessHeap` at `0x18001abcd`

## string_xrefs

- `0x18001aa54`: `\ngen_service`
- `0x18001aa81`: `InitService()\n`
- `0x18001aabe`: `InstallDetours`
- `0x18001aadb`: `Installed test hook library\n`
- `0x18001aae4`: `Failed to install test hooks\n`
- `0x18001ab8b`: `InitService() failed\n`
- `0x18001aa9a`: `NGENServiceTestHookDll`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall NGENService::InitService(NGENService *this)
{
  int v1; // esi
  unsigned int v2; // r9d
  const unsigned __int16 *v3; // rdx
  const WCHAR *ConfigString_DontUse; // rax
  HMODULE Library; // rax
  const unsigned __int16 *v6; // rdx
  __int64 (*ProcAddress)(void); // rax
  int v8; // eax
  wchar_t *v9; // rcx
  HANDLE EventW; // rax
  NGENService *v11; // rcx
  void *v12; // rdi
  const unsigned __int16 *v13; // rdx
  signed int v14; // ebx
  const unsigned __int16 *v15; // rdx
  wchar_t *v16; // rcx
  signed int LastError; // eax
  NGENService *v18; // rcx
  void *v19; // r14
  HANDLE ProcessHeap; // rax
  int v22; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v23; // [rsp+3Ch] [rbp-CCh]
  LPVOID lpMem; // [rsp+48h] [rbp-C0h]
  __int16 v25; // [rsp+50h] [rbp-B8h] BYREF

  v1 = 0;
  v23 = 512;
  lpMem = &v25;
  v22 = 2;
  v25 = 0;
  Helpers::GetVersionDirectoryPathFromCurrentModulePath((struct SString *)&v22);
  SString::Append((SString *)&v22, L"\\ngen_service");
  SString::ConvertToUnicode((SString *)&v22);
  NGENService::InitServiceLogging((NGENService *)lpMem, 0, (const unsigned __int16 *)0xA00000, v2);
  NGENService::DebugLog((NGENService *)L"InitService()\n", v3);
  ConfigString_DontUse = (const WCHAR *)REGUTIL::GetConfigString_DontUse_(L"NGENServiceTestHookDll", 0, 7, 1, -1, 0);
  if ( ConfigString_DontUse )
  {
    Library = LoadLibraryExW(ConfigString_DontUse, 0, 0);
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "InstallDetours");
      if ( !ProcAddress || (v8 = ProcAddress(), v9 = L"Installed test hook library\n", !v8) )
        v9 = L"Failed to install test hooks\n";
    }
    else
    {
      v9 = L"Failed to load test hook library()\n";
    }
    NGENService::DebugLog((NGENService *)v9, v6);
  }
  NGENService::g_bPauseRequested = 0;
  NGENService::g_bStopRequested = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  v12 = EventW;
  if ( EventW != (HANDLE)-1LL )
  {
    v1 = 1;
    if ( !EventW )
    {
LABEL_16:
      LastError = GetLastError();
      v14 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v14 = LastError;
      goto LABEL_18;
    }
  }
  v14 = NGENService::ControllerInit(v11);
  if ( v14 >= 0 )
  {
    if ( SetConsoleCtrlHandler(NGENService::CorServiceConsoleCtrlHandler, 1) )
    {
      if ( SetProcessShutdownParameters(0x380u, 0) )
      {
        v1 = 0;
        NGENService::g_hRestartEvent = v12;
        v14 = 0;
        goto LABEL_20;
      }
      v16 = L"SetProcessShutdownParameters() failed\n";
    }
    else
    {
      v16 = L"SetConsoleCtrlHandler() failed\n";
    }
    NGENService::DebugLog((NGENService *)v16, v15);
    goto LABEL_16;
  }
LABEL_18:
  NGENService::DebugLog((NGENService *)L"InitService() failed\n", v13);
  NGENService::ControllerShutdown(v18);
LABEL_20:
  if ( (v23 & 0x800000000LL) != 0 )
  {
    v19 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        ProcessHeap = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
      }
      HeapFree(ProcessHeap, 0, v19);
    }
  }
  if ( v1 && v12 )
    CloseHandle(v12);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18001a9d8  mov     rax, rsp
0x18001a9db  mov     [rax+8], rbx
0x18001a9df  mov     [rax+10h], rsi
0x18001a9e3  mov     [rax+18h], rdi
0x18001a9e7  push    rbp
0x18001a9e8  push    r14
0x18001a9ea  push    r15
0x18001a9ec  lea     rbp, [rax-178h]
0x18001a9f3  sub     rsp, 260h
0x18001a9fa  mov     rax, cs:__security_cookie
0x18001aa01  xor     rax, rsp
0x18001aa04  mov     [rbp+170h+var_20], rax
0x18001aa0b  or      qword ptr [rsp+270h+var_250], 0FFFFFFFFFFFFFFFFh
0x18001aa11  xor     r15d, r15d
0x18001aa14  mov     esi, r15d
0x18001aa17  mov     dword ptr [rsp+270h+var_248], r15d
0x18001aa1c  mov     qword ptr [rsp+270h+var_240], r15
0x18001aa21  mov     qword ptr [rsp+34h], 200h
0x18001aa2a  mov     [rsp+270h+lpMem], r15
0x18001aa2f  lea     rax, [rsp+270h+var_228]
0x18001aa34  mov     [rsp+270h+lpMem], rax
0x18001aa39  mov     [rsp+270h+var_240], 2
0x18001aa41  mov     rax, [rsp+270h+lpMem]
0x18001aa46  mov     [rax], r15w
0x18001aa4a  lea     rcx, [rsp+270h+var_240]; this
0x18001aa4f  call    ?GetVersionDirectoryPathFromCurrentModulePath@Helpers@@SAXAEAVSString@@@Z; Helpers::GetVersionDirectoryPathFromCurrentModulePath(SString &)
0x18001aa54  lea     rdx, aNgenService; "\\ngen_service"
0x18001aa5b  lea     rcx, [rsp+270h+var_240]; this
0x18001aa60  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x18001aa65  lea     rcx, [rsp+270h+var_240]; this
0x18001aa6a  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18001aa6f  xor     edx, edx; unsigned __int16 *
0x18001aa71  mov     r8d, 0A00000h; unsigned __int16 *
0x18001aa77  mov     rcx, [rsp+270h+lpMem]; this
0x18001aa7c  call    ?InitServiceLogging@NGENService@@YAJPEBG0K@Z; NGENService::InitServiceLogging(ushort const *,ushort const *,ulong)
0x18001aa81  lea     rcx, aInitservice; "InitService()\n"
0x18001aa88  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x18001aa8d  lea     r14d, [r15+1]
0x18001aa91  mov     r9d, r14d
0x18001aa94  xor     edx, edx
0x18001aa96  lea     r8d, [r15+7]
0x18001aa9a  lea     rcx, aNgenservicetes; "NGENServiceTestHookDll"
0x18001aaa1  call    ?GetConfigString_DontUse_@REGUTIL@@SAPEAGPEBGHW4CORConfigLevel@1@H@Z; REGUTIL::GetConfigString_DontUse_(ushort const *,int,REGUTIL::CORConfigLevel,int)
0x18001aaa6  test    rax, rax
0x18001aaa9  jz      short loc_18001AAF9
0x18001aaab  xor     r8d, r8d; dwFlags
0x18001aaae  xor     edx, edx; hFile
0x18001aab0  mov     rcx, rax; lpLibFileName
0x18001aab3  call    cs:__imp_LoadLibraryExW
0x18001aab9  test    rax, rax
0x18001aabc  jz      short loc_18001AAED
0x18001aabe  lea     rdx, aInstalldetours; "InstallDetours"
0x18001aac5  mov     rcx, rax; hModule
0x18001aac8  call    cs:__imp_GetProcAddress
0x18001aace  test    rax, rax
0x18001aad1  jz      short loc_18001AAE4
0x18001aad3  call    cs:__guard_dispatch_icall_fptr
0x18001aad9  test    eax, eax
0x18001aadb  lea     rcx, aInstalledTestH; "Installed test hook library\n"
0x18001aae2  jnz     short loc_18001AAF4
0x18001aae4  lea     rcx, aFailedToInstal; "Failed to install test hooks\n"
0x18001aaeb  jmp     short loc_18001AAF4
0x18001aaed  lea     rcx, aFailedToLoadTe; "Failed to load test hook library()\n"
0x18001aaf4  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x18001aaf9  mov     cs:?g_bPauseRequested@NGENService@@3V?$Volatile@_N@@A, r15b; Volatile<bool> NGENService::g_bPauseRequested
0x18001ab00  mov     cs:?g_bStopRequested@NGENService@@3V?$Volatile@_N@@A, r15b; Volatile<bool> NGENService::g_bStopRequested
0x18001ab07  xor     r9d, r9d; lpName
0x18001ab0a  xor     r8d, r8d; bInitialState
0x18001ab0d  xor     edx, edx; bManualReset
0x18001ab0f  xor     ecx, ecx; lpEventAttributes
0x18001ab11  call    cs:__imp_CreateEventW
0x18001ab17  mov     rdi, rax
0x18001ab1a  mov     qword ptr [rsp+270h+var_250], rax
0x18001ab1f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001ab23  jz      short loc_18001AB32
0x18001ab25  mov     esi, r14d
0x18001ab28  mov     dword ptr [rsp+270h+var_248], r14d
0x18001ab2d  test    rax, rax
0x18001ab30  jz      short loc_18001AB77
0x18001ab32  call    ?ControllerInit@NGENService@@YAJXZ; NGENService::ControllerInit(void)
0x18001ab37  mov     ebx, eax
0x18001ab39  test    eax, eax
0x18001ab3b  js      short loc_18001AB8B
0x18001ab3d  mov     edx, r14d; Add
0x18001ab40  lea     rcx, ?CorServiceConsoleCtrlHandler@NGENService@@YAHK@Z; HandlerRoutine
0x18001ab47  call    cs:__imp_SetConsoleCtrlHandler
0x18001ab4d  test    eax, eax
0x18001ab4f  jnz     short loc_18001AB5A
0x18001ab51  lea     rcx, aSetconsolectrl; "SetConsoleCtrlHandler() failed\n"
0x18001ab58  jmp     short loc_18001AB72
0x18001ab5a  xor     edx, edx; dwFlags
0x18001ab5c  mov     ecx, 380h; dwLevel
0x18001ab61  call    cs:__imp_SetProcessShutdownParameters
0x18001ab67  test    eax, eax
0x18001ab69  jnz     short loc_18001AB9E
0x18001ab6b  lea     rcx, aSetprocessshut; "SetProcessShutdownParameters() failed\n"
0x18001ab72  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x18001ab77  call    cs:__imp_GetLastError
0x18001ab7d  movzx   ebx, ax
0x18001ab80  or      ebx, 80070000h
0x18001ab86  test    eax, eax
0x18001ab88  cmovle  ebx, eax
0x18001ab8b  lea     rcx, aInitserviceFai; "InitService() failed\n"
0x18001ab92  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x18001ab97  call    ?ControllerShutdown@NGENService@@YAXXZ; NGENService::ControllerShutdown(void)
0x18001ab9c  jmp     short loc_18001ABB0
0x18001ab9e  mov     esi, r15d
0x18001aba1  mov     dword ptr [rsp+270h+var_248], r15d
0x18001aba6  mov     cs:?g_hRestartEvent@NGENService@@3PEAXEA, rdi; void * NGENService::g_hRestartEvent
0x18001abad  mov     ebx, r15d
0x18001abb0  test    byte ptr [rsp+270h+var_238], 8
0x18001abb5  jz      short loc_18001ABE9
0x18001abb7  mov     r14, [rsp+270h+lpMem]
0x18001abbc  test    r14, r14
0x18001abbf  jz      short loc_18001ABE9
0x18001abc1  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18001abc8  test    rax, rax
0x18001abcb  jnz     short loc_18001ABDA
0x18001abcd  call    cs:__imp_GetProcessHeap
0x18001abd3  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18001abda  mov     r8, r14; lpMem
0x18001abdd  xor     edx, edx; dwFlags
0x18001abdf  mov     rcx, rax; hHeap
0x18001abe2  call    cs:__imp_HeapFree
0x18001abe8  nop
0x18001abe9  test    esi, esi
0x18001abeb  jz      short loc_18001AC00
0x18001abed  test    rdi, rdi
0x18001abf0  jz      short loc_18001ABFB
0x18001abf2  mov     rcx, rdi; hObject
0x18001abf5  call    cs:__imp_CloseHandle
0x18001abfb  mov     dword ptr [rsp+270h+var_248], r15d
0x18001ac00  mov     eax, ebx
0x18001ac02  mov     rcx, [rbp+170h+var_20]
0x18001ac09  xor     rcx, rsp; StackCookie
0x18001ac0c  call    __security_check_cookie
0x18001ac11  lea     r11, [rsp+270h+var_10]
0x18001ac19  mov     rbx, [r11+20h]
0x18001ac1d  mov     rsi, [r11+28h]
0x18001ac21  mov     rdi, [r11+30h]
0x18001ac25  mov     rsp, r11
0x18001ac28  pop     r15
0x18001ac2a  pop     r14
0x18001ac2c  pop     rbp
0x18001ac2d  retn
```
