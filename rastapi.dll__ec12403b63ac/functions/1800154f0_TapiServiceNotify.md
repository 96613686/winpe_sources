# TapiServiceNotify

- ea: `0x1800154f0`
- end: `0x180015578`
- name: `TapiServiceNotify`
- size: `136`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update`

## callees

- `0x1800033d0`
- `0x18000d92c`
- `0x180012340`
- `0x1800154f0`
- `0x180015768`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001556d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001556d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015563`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015563`

## string_xrefs

- `0x18001550e`: `TapiServiceNotify: Tapi service has started`
- `0x180015550`: `TapiServiceNotify: GetPortsFromTapi failed (0x%x)`

## pseudocode

```c
void __fastcall TapiServiceNotify(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  if ( !*(_DWORD *)(a1 + 24) && *(_DWORD *)(a1 + 64) == 8 )
  {
    GetMutex(a1, a2, a3, a4);
    if ( !g_fTapiSrvRunning )
    {
      g_fTapiSrvRunning = 1;
      RasTapiTrace("TapiServiceNotify: Tapi service has started");
      UpdateRasmanDependency(1);
      if ( !TapiThreadId && !RasLine && (unsigned int)GetPortsFromTapi(1) )
        RasTapiTrace("TapiServiceNotify: GetPortsFromTapi failed (0x%x)");
    }
    if ( !ReleaseMutex(RasTapiMutex) )
      GetLastError();
  }
}

```

## disassembly

```asm
0x1800154f0  sub     rsp, 28h
0x1800154f4  cmp     dword ptr [rcx+18h], 0
0x1800154f8  jnz     short loc_180015573
0x1800154fa  cmp     dword ptr [rcx+40h], 8
0x1800154fe  jnz     short loc_180015573
0x180015500  call    GetMutex
0x180015505  cmp     cs:g_fTapiSrvRunning, 0
0x18001550c  jnz     short loc_18001555C
0x18001550e  lea     rcx, aTapiservicenot_0; "TapiServiceNotify: Tapi service has sta"...
0x180015515  mov     cs:g_fTapiSrvRunning, 1
0x18001551f  call    RasTapiTrace
0x180015524  mov     ecx, 1
0x180015529  call    UpdateRasmanDependency
0x18001552e  cmp     cs:TapiThreadId, 0
0x180015535  jnz     short loc_18001555C
0x180015537  cmp     cs:RasLine, 0
0x18001553e  jnz     short loc_18001555C
0x180015540  mov     ecx, 1
0x180015545  call    GetPortsFromTapi
0x18001554a  test    eax, eax
0x18001554c  jz      short loc_18001555C
0x18001554e  mov     edx, eax
0x180015550  lea     rcx, aTapiservicenot; "TapiServiceNotify: GetPortsFromTapi fai"...
0x180015557  call    RasTapiTrace
0x18001555c  mov     rcx, cs:RasTapiMutex; hMutex
0x180015563  call    cs:__imp_ReleaseMutex
0x180015569  test    eax, eax
0x18001556b  jnz     short loc_180015573
0x18001556d  call    cs:__imp_GetLastError
0x180015573  add     rsp, 28h
0x180015577  retn
```
