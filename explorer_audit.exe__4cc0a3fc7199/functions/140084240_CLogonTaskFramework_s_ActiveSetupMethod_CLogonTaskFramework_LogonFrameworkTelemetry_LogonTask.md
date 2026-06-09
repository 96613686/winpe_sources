# CLogonTaskFramework::s_ActiveSetupMethod(CLogonTaskFramework *,LogonFrameworkTelemetry::LogonTask *)

- ea: `0x140084240`
- end: `0x14008429a`
- name: `?s_ActiveSetupMethod@CLogonTaskFramework@@CAJPEAV1@PEAVLogonTask@LogonFrameworkTelemetry@@@Z`
- size: `90`
- prototype: `__int64 __fastcall(struct CLogonTaskFramework *, struct LogonFrameworkTelemetry::LogonTask *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update`

## callees

- `0x140084240`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140084264`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140084264`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14008428c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14008428c`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x14008424b`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x140084272`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x14008424b`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x140084272`
- `SHELL32!__imp_RunInstallUninstallStubs` at `0x14008427e`
- `SHELL32!__imp_RunInstallUninstallStubs` at `0x14008427e`

## string_xrefs

- `0x14008425d`: `Local\_fCanRegisterWithShellService`

## pseudocode

```c
__int64 __fastcall CLogonTaskFramework::s_ActiveSetupMethod(
        struct CLogonTaskFramework *a1,
        struct LogonFrameworkTelemetry::LogonTask *a2)
{
  HANDLE EventW; // rbx

  if ( !GetSystemMetrics(67) )
  {
    EventW = CreateEventW(0, 1, 1, L"Local\\_fCanRegisterWithShellService");
    if ( !GetSystemMetrics(67) )
      RunInstallUninstallStubs(0);
    if ( EventW )
      CloseHandle(EventW);
  }
  return 0;
}

```

## disassembly

```asm
0x140084240  push    rbx
0x140084242  sub     rsp, 20h
0x140084246  mov     ecx, 43h ; 'C'; nIndex
0x14008424b  call    cs:__imp_GetSystemMetrics
0x140084251  test    eax, eax
0x140084253  jnz     short loc_140084292
0x140084255  lea     edx, [rax+1]; bManualReset
0x140084258  xor     ecx, ecx; lpEventAttributes
0x14008425a  mov     r8d, edx; bInitialState
0x14008425d  lea     r9, aLocalFcanregis; "Local\\_fCanRegisterWithShellService"
0x140084264  call    cs:__imp_CreateEventW
0x14008426a  mov     ecx, 43h ; 'C'; nIndex
0x14008426f  mov     rbx, rax
0x140084272  call    cs:__imp_GetSystemMetrics
0x140084278  test    eax, eax
0x14008427a  jnz     short loc_140084284
0x14008427c  xor     ecx, ecx
0x14008427e  call    cs:__imp_RunInstallUninstallStubs
0x140084284  test    rbx, rbx
0x140084287  jz      short loc_140084292
0x140084289  mov     rcx, rbx; hObject
0x14008428c  call    cs:__imp_CloseHandle
0x140084292  xor     eax, eax
0x140084294  add     rsp, 20h
0x140084298  pop     rbx
0x140084299  retn
```
