# _DllProcessDetach

- ea: `0x18002f954`
- end: `0x18002fa5f`
- name: `_DllProcessDetach`
- size: `267`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x180045b04`

## callees

- `0x18002f954`
- `0x18002fa68`
- `0x18002fa8c`
- `0x18002fabc`
- `0x18002fb20`
- `0x18002fb7c`
- `0x180078ecc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002f998`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002f998`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18002fa07`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18002fa1d`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18002fa07`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18002fa1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002fa57`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002fa57`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002fa4f`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002fa4f`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x18002fa2f`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x18002fa2f`

## pseudocode

```c
void __fastcall DllProcessDetach(__int64 a1)
{
  unsigned int v2; // edx

  if ( hEventLog )
  {
    DeregisterEventSource(hEventLog);
    hEventLog = 0;
  }
  IERegReleaseKeys();
  McGenEventUnregister_EventUnregister();
  TraceLoggingUnregister_EventUnregister(&dword_180293010);
  FreeBrowsingEnvironment();
  if ( byte_180298C88 )
  {
    DeleteCriticalSection(&g_csInit);
    byte_180298C88 = 0;
  }
  if ( g_pScriptProcessor )
    CScriptProcessor::`scalar deleting destructor'(g_pScriptProcessor, v2);
  g_pScriptProcessor = 0;
  if ( !a1 )
    CleanupHashMapCaches();
  if ( !g_fGCountRundown )
  {
    g_fGCountRundown = 1;
    if ( !a1 )
    {
      if ( g_prgSessionWide )
        UnmapViewOfFile(g_prgSessionWide);
      if ( g_hSessionWideFileMapping )
        CloseHandle(g_hSessionWideFileMapping);
    }
  }
  if ( ThreadFreeLibrary::TLS != -1 )
  {
    TlsFree(ThreadFreeLibrary::TLS);
    ThreadFreeLibrary::TLS = -1;
  }
  if ( g_tlsIEConfiguration != -1 )
  {
    TlsFree(g_tlsIEConfiguration);
    g_tlsIEConfiguration = -1;
  }
}

```

## disassembly

```asm
0x18002f954  push    rbx
0x18002f956  sub     rsp, 20h
0x18002f95a  mov     rbx, rcx
0x18002f95d  mov     rcx, cs:hEventLog; hEventLog
0x18002f964  test    rcx, rcx
0x18002f967  jnz     loc_18002FA2F
0x18002f96d  call    IERegReleaseKeys
0x18002f972  call    McGenEventUnregister_EventUnregister
0x18002f977  lea     rcx, dword_180293010
0x18002f97e  call    TraceLoggingUnregister_EventUnregister
0x18002f983  call    ?FreeBrowsingEnvironment@@YAXXZ; FreeBrowsingEnvironment(void)
0x18002f988  cmp     cs:byte_180298C88, 0
0x18002f98f  jz      short loc_18002F9A5
0x18002f991  lea     rcx, ?g_csInit@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002f998  call    cs:__imp_DeleteCriticalSection
0x18002f99e  mov     cs:byte_180298C88, 0
0x18002f9a5  mov     rcx, cs:?g_pScriptProcessor@@3PEAVCScriptProcessor@@EA; this
0x18002f9ac  test    rcx, rcx
0x18002f9af  jnz     loc_18002FA45
0x18002f9b5  mov     cs:?g_pScriptProcessor@@3PEAVCScriptProcessor@@EA, 0; CScriptProcessor * g_pScriptProcessor
0x18002f9c0  test    rbx, rbx
0x18002f9c3  jnz     short loc_18002F9CA
0x18002f9c5  call    ?CleanupHashMapCaches@@YAXXZ; CleanupHashMapCaches(void)
0x18002f9ca  cmp     cs:g_fGCountRundown, 0
0x18002f9d1  jnz     short loc_18002F9FA
0x18002f9d3  mov     cs:g_fGCountRundown, 1
0x18002f9dd  test    rbx, rbx
0x18002f9e0  jnz     short loc_18002F9FA
0x18002f9e2  mov     rcx, cs:g_prgSessionWide; lpBaseAddress
0x18002f9e9  test    rcx, rcx
0x18002f9ec  jnz     short loc_18002FA4F
0x18002f9ee  mov     rcx, cs:g_hSessionWideFileMapping; hObject
0x18002f9f5  test    rcx, rcx
0x18002f9f8  jnz     short loc_18002FA57
0x18002f9fa  mov     ecx, cs:?TLS@ThreadFreeLibrary@@0KA; dwTlsIndex
0x18002fa00  or      ebx, 0FFFFFFFFh
0x18002fa03  cmp     ecx, ebx
0x18002fa05  jz      short loc_18002FA13
0x18002fa07  call    cs:__imp_TlsFree
0x18002fa0d  mov     cs:?TLS@ThreadFreeLibrary@@0KA, ebx; ulong ThreadFreeLibrary::TLS
0x18002fa13  mov     ecx, cs:?g_tlsIEConfiguration@@3KA; dwTlsIndex
0x18002fa19  cmp     ecx, ebx
0x18002fa1b  jz      short loc_18002FA29
0x18002fa1d  call    cs:__imp_TlsFree
0x18002fa23  mov     cs:?g_tlsIEConfiguration@@3KA, ebx; ulong g_tlsIEConfiguration
0x18002fa29  add     rsp, 20h
0x18002fa2d  pop     rbx
0x18002fa2e  retn
0x18002fa2f  call    cs:__imp_DeregisterEventSource
0x18002fa35  mov     cs:hEventLog, 0
0x18002fa40  jmp     loc_18002F96D
0x18002fa45  call    ??_GCScriptProcessor@@IEAAPEAXI@Z; CScriptProcessor::`scalar deleting destructor'(uint)
0x18002fa4a  jmp     loc_18002F9B5
0x18002fa4f  call    cs:__imp_UnmapViewOfFile
0x18002fa55  jmp     short loc_18002F9EE
0x18002fa57  call    cs:__imp_CloseHandle
0x18002fa5d  jmp     short loc_18002F9FA
```
