# DllProcessAttach(HINSTANCE__ *)

- ea: `0x180014920`
- end: `0x180014a13`
- name: `?DllProcessAttach@@YAHPEAUHINSTANCE__@@@Z`
- size: `243`
- prototype: `__int64 __fastcall(HINSTANCE hLibModule)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x180016504`

## callees

- `0x18000d624`
- `0x180014920`
- `0x180016648`
- `0x1800353e4`

## import_xrefs

- `ntdll!EtwEventRegister` at `0x180014961`
- `ntdll!EtwEventRegister` at `0x180014961`
- `ntdll!RtlGetVersion` at `0x1800149ad`
- `ntdll!RtlGetVersion` at `0x1800149ad`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180014996`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180014996`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800149c0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800149d9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800149f2`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800149c0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800149d9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800149f2`

## string_xrefs

- `0x18001492d`: `DLL_PROCESS_ATTACH`
- `0x180014934`: `DllProcessAttach`

## pseudocode

```c
__int64 __fastcall DllProcessAttach(HINSTANCE hLibModule)
{
  unsigned int v2; // eax

  ClassInstallerTelemetry::WriteDbgTraceInfo("DllProcessAttach", L"DLL_PROCESS_ATTACH");
  if ( !g_bTracingEnabled )
  {
    v2 = EtwEventRegister(SPOOLER_ETW_CONTROL_GUID, 0, 0, &g_splRegistrationHandle);
    if ( !v2 )
      g_bTracingEnabled = 1;
    PerfLibTelemetry::WriteDbgTraceInfo("SplEventLogRegister", L"rc: %d", v2);
  }
  McGenEventRegister_EventRegister();
  ghInst = hLibModule;
  DisableThreadLibraryCalls(hLibModule);
  OsVersionInfo.dwOSVersionInfoSize = 276;
  if ( RtlGetVersion(&OsVersionInfo) < 0 )
    return 0;
  if ( !InitializeCriticalSectionAndSpinCount(&CDMCritSect, 0) )
    return 0;
  gbCDMCritSectInitialized = 1;
  if ( !InitializeCriticalSectionAndSpinCount(&SetupapiGlobalFlagsCritSect, 0) )
    return 0;
  gbSetupapiGlobalFlagsCritSectInitialized = 1;
  if ( !InitializeCriticalSectionAndSpinCount(&SkipCritSect, 0) )
    return 0;
  gbSkipCritSectInitialized = 1;
  return 1;
}

```

## disassembly

```asm
0x180014920  mov     [rsp+arg_0], rbx
0x180014925  push    rdi
0x180014926  sub     rsp, 20h
0x18001492a  mov     rbx, rcx
0x18001492d  lea     rdx, aDllProcessAtta; "DLL_PROCESS_ATTACH"
0x180014934  lea     rcx, aDllprocessatta; "DllProcessAttach"
0x18001493b  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180014940  cmp     cs:?g_bTracingEnabled@@3HA, 0; int g_bTracingEnabled
0x180014947  mov     edi, 1
0x18001494c  jnz     short loc_180014987
0x18001494e  lea     r9, ?g_splRegistrationHandle@@3_KA; unsigned __int64 g_splRegistrationHandle
0x180014955  xor     r8d, r8d
0x180014958  xor     edx, edx
0x18001495a  lea     rcx, SPOOLER_ETW_CONTROL_GUID
0x180014961  call    cs:__imp_EtwEventRegister
0x180014967  test    eax, eax
0x180014969  jnz     short loc_180014971
0x18001496b  mov     cs:?g_bTracingEnabled@@3HA, edi; int g_bTracingEnabled
0x180014971  mov     r8d, eax
0x180014974  lea     rdx, aRcD; "rc: %d"
0x18001497b  lea     rcx, aSpleventlogreg; "SplEventLogRegister"
0x180014982  call    ?WriteDbgTraceInfo@PerfLibTelemetry@@SAXPEADPEAGZZ; PerfLibTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180014987  call    McGenEventRegister_EventRegister
0x18001498c  mov     rcx, rbx; hLibModule
0x18001498f  mov     cs:ghInst, rbx
0x180014996  call    cs:__imp_DisableThreadLibraryCalls
0x18001499c  lea     rcx, OsVersionInfo; lpVersionInformation
0x1800149a3  mov     cs:OsVersionInfo.dwOSVersionInfoSize, 114h
0x1800149ad  call    cs:__imp_RtlGetVersion
0x1800149b3  test    eax, eax
0x1800149b5  js      short loc_180014A06
0x1800149b7  xor     edx, edx; dwSpinCount
0x1800149b9  lea     rcx, CDMCritSect; lpCriticalSection
0x1800149c0  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800149c6  test    eax, eax
0x1800149c8  jz      short loc_180014A06
0x1800149ca  xor     edx, edx; dwSpinCount
0x1800149cc  mov     cs:gbCDMCritSectInitialized, edi
0x1800149d2  lea     rcx, SetupapiGlobalFlagsCritSect; lpCriticalSection
0x1800149d9  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800149df  test    eax, eax
0x1800149e1  jz      short loc_180014A06
0x1800149e3  xor     edx, edx; dwSpinCount
0x1800149e5  mov     cs:gbSetupapiGlobalFlagsCritSectInitialized, edi
0x1800149eb  lea     rcx, SkipCritSect; lpCriticalSection
0x1800149f2  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800149f8  test    eax, eax
0x1800149fa  jz      short loc_180014A06
0x1800149fc  mov     cs:gbSkipCritSectInitialized, edi
0x180014a02  mov     eax, edi
0x180014a04  jmp     short loc_180014A08
0x180014a06  xor     eax, eax
0x180014a08  mov     rbx, [rsp+28h+arg_0]
0x180014a0d  add     rsp, 20h
0x180014a11  pop     rdi
0x180014a12  retn
```
