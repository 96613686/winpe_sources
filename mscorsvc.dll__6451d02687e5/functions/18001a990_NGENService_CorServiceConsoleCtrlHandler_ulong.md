# NGENService::CorServiceConsoleCtrlHandler(ulong)

- ea: `0x18001a990`
- end: `0x18001a9d8`
- name: `?CorServiceConsoleCtrlHandler@NGENService@@YAHK@Z`
- size: `72`
- prototype: `__int64 __fastcall(DWORD CtrlType, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x18001a790`
- `0x18001a990`
- `0x18002e1d0`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18001a9c4`
- `KERNEL32!SetEvent` at `0x18001a9c4`

## string_xrefs

- `0x18001a999`: `Console shutdown notification. Will stop the service.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NGENService::CorServiceConsoleCtrlHandler(DWORD CtrlType, const unsigned __int16 *a2)
{
  unsigned int v2; // edx

  if ( CtrlType != 6 )
    return 0;
  NGENService::g_bIsShutdownInProgress = 1;
  NGENService::DebugLog((NGENService *)L"Console shutdown notification. Will stop the service.\n", a2);
  NGENService::ServiceUpdateState((NGENService *)3, v2);
  NGENService::g_bStopRequested = 1;
  SetEvent(NGENService::g_hSCMRequestEvent);
  return 1;
}

```

## disassembly

```asm
0x18001a990  sub     rsp, 28h
0x18001a994  cmp     ecx, 6
0x18001a997  jnz     short loc_18001A9D1
0x18001a999  lea     rcx, aConsoleShutdow; "Console shutdown notification. Will sto"...
0x18001a9a0  mov     cs:?g_bIsShutdownInProgress@NGENService@@3V?$Volatile@_N@@A, 1; Volatile<bool> NGENService::g_bIsShutdownInProgress
0x18001a9a7  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x18001a9ac  mov     ecx, 3; this
0x18001a9b1  call    ?ServiceUpdateState@NGENService@@YAXK@Z; NGENService::ServiceUpdateState(ulong)
0x18001a9b6  mov     rcx, cs:?g_hSCMRequestEvent@NGENService@@3PEAXEA; hEvent
0x18001a9bd  mov     cs:?g_bStopRequested@NGENService@@3V?$Volatile@_N@@A, 1; Volatile<bool> NGENService::g_bStopRequested
0x18001a9c4  call    cs:__imp_SetEvent
0x18001a9ca  mov     eax, 1
0x18001a9cf  jmp     short loc_18001A9D3
0x18001a9d1  xor     eax, eax
0x18001a9d3  add     rsp, 28h
0x18001a9d7  retn
```
