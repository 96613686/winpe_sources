# CLogonTaskFramework::s_ActiveSetupMethod(CLogonTaskFramework *,LogonFrameworkTelemetry::LogonTask *)

- ea: `0x140089f10`
- end: `0x140089f89`
- name: `?s_ActiveSetupMethod@CLogonTaskFramework@@CAJPEAV1@PEAVLogonTask@LogonFrameworkTelemetry@@@Z`
- size: `121`
- prototype: `__int64 __fastcall(struct CLogonTaskFramework *, struct LogonFrameworkTelemetry::LogonTask *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update`

## callees

- `0x140089f10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140089f3a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140089f3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140089f74`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140089f74`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x140089f1b`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x140089f4e`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x140089f1b`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x140089f4e`
- `SHELL32!__imp_RunInstallUninstallStubs` at `0x140089f60`
- `SHELL32!__imp_RunInstallUninstallStubs` at `0x140089f60`

## string_xrefs

- `0x140089f33`: `Local\_fCanRegisterWithShellService`

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
0x140089f10  push    rbx
0x140089f12  sub     rsp, 20h
0x140089f16  mov     ecx, 43h ; 'C'; nIndex
0x140089f1b  call    cs:__imp_GetSystemMetrics
0x140089f22  nop     dword ptr [rax+rax+00h]
0x140089f27  test    eax, eax
0x140089f29  jnz     short loc_140089F80
0x140089f2b  lea     edx, [rax+1]; bManualReset
0x140089f2e  xor     ecx, ecx; lpEventAttributes
0x140089f30  mov     r8d, edx; bInitialState
0x140089f33  lea     r9, aLocalFcanregis; "Local\\_fCanRegisterWithShellService"
0x140089f3a  call    cs:__imp_CreateEventW
0x140089f41  nop     dword ptr [rax+rax+00h]
0x140089f46  mov     ecx, 43h ; 'C'; nIndex
0x140089f4b  mov     rbx, rax
0x140089f4e  call    cs:__imp_GetSystemMetrics
0x140089f55  nop     dword ptr [rax+rax+00h]
0x140089f5a  test    eax, eax
0x140089f5c  jnz     short loc_140089F6C
0x140089f5e  xor     ecx, ecx
0x140089f60  call    cs:__imp_RunInstallUninstallStubs
0x140089f67  nop     dword ptr [rax+rax+00h]
0x140089f6c  test    rbx, rbx
0x140089f6f  jz      short loc_140089F80
0x140089f71  mov     rcx, rbx; hObject
0x140089f74  call    cs:__imp_CloseHandle
0x140089f7b  nop     dword ptr [rax+rax+00h]
0x140089f80  xor     eax, eax
0x140089f82  add     rsp, 20h
0x140089f86  pop     rbx
0x140089f87  retn
```
