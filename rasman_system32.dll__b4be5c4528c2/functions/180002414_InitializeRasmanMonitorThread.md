# InitializeRasmanMonitorThread

- ea: `0x180002414`
- end: `0x180002545`
- name: `InitializeRasmanMonitorThread`
- size: `305`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callers

- `0x1800022c4`

## callees

- `0x180002414`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180002433`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180002433`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180002484`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180002484`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18000245b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18000245b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002529`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002529`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002506`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002506`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000249c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000249c`
- `rtutils!TracePrintfExA` at `0x1800024c8`
- `rtutils!TracePrintfExA` at `0x1800024e9`
- `rtutils!TracePrintfExA` at `0x1800024c8`
- `rtutils!TracePrintfExA` at `0x1800024e9`

## string_xrefs

- `0x1800024bc`: `InitializeRasmanMonitorThread exiting ... %d`
- `0x180002454`: `rasman.dll`
- `0x1800024dd`: `InitializeRasmanMonitorThread Entered ...`

## pseudocode

```c
__int64 InitializeRasmanMonitorThread()
{
  DWORD LastError; // ebx

  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "InitializeRasmanMonitorThread Entered ...");
  g_hEventServiceMonitorTerminate = CreateEventA(0, 0, 0, 0);
  if ( !g_hEventServiceMonitorTerminate
    || !GetModuleHandleExA(0, "rasman.dll", &g_hModule)
    || (LastError = 0,
        (g_hRasmanServiceMonitorThread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)RasmanServiceMonitorThread, 0, 0, 0)) == 0) )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( g_hEventServiceMonitorTerminate )
      {
        CloseHandle(g_hEventServiceMonitorTerminate);
        g_hEventServiceMonitorTerminate = 0;
      }
      if ( g_hModule )
      {
        FreeLibrary(g_hModule);
        g_hModule = 0;
      }
    }
  }
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "InitializeRasmanMonitorThread exiting ... %d", LastError);
  return LastError;
}

```

## disassembly

```asm
0x180002414  push    rbx
0x180002416  sub     rsp, 30h
0x18000241a  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180002420  cmp     ecx, 0FFFFFFFFh
0x180002423  jnz     loc_1800024DD
0x180002429  xor     r9d, r9d; lpName
0x18000242c  xor     r8d, r8d; bInitialState
0x18000242f  xor     edx, edx; bManualReset
0x180002431  xor     ecx, ecx; lpEventAttributes
0x180002433  call    cs:__imp_CreateEventA
0x18000243a  nop     dword ptr [rax+rax+00h]
0x18000243f  mov     cs:g_hEventServiceMonitorTerminate, rax
0x180002446  test    rax, rax
0x180002449  jz      short loc_18000249C
0x18000244b  lea     r8, g_hModule; phModule
0x180002452  xor     ecx, ecx; dwFlags
0x180002454  lea     rdx, ModuleName; "rasman.dll"
0x18000245b  call    cs:__imp_GetModuleHandleExA
0x180002462  nop     dword ptr [rax+rax+00h]
0x180002467  test    eax, eax
0x180002469  jz      short loc_18000249C
0x18000246b  xor     ebx, ebx
0x18000246d  lea     r8, RasmanServiceMonitorThread; lpStartAddress
0x180002474  mov     [rsp+38h+lpThreadId], rbx; lpThreadId
0x180002479  xor     r9d, r9d; lpParameter
0x18000247c  xor     edx, edx; dwStackSize
0x18000247e  mov     [rsp+38h+dwCreationFlags], ebx; dwCreationFlags
0x180002482  xor     ecx, ecx; lpThreadAttributes
0x180002484  call    cs:__imp_CreateThread
0x18000248b  nop     dword ptr [rax+rax+00h]
0x180002490  mov     cs:g_hRasmanServiceMonitorThread, rax
0x180002497  test    rax, rax
0x18000249a  jnz     short loc_1800024AE
0x18000249c  call    cs:__imp_GetLastError
0x1800024a3  nop     dword ptr [rax+rax+00h]
0x1800024a8  mov     ebx, eax
0x1800024aa  test    eax, eax
0x1800024ac  jnz     short loc_1800024FA
0x1800024ae  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800024b4  cmp     ecx, 0FFFFFFFFh
0x1800024b7  jz      short loc_1800024D4
0x1800024b9  mov     r9d, ebx
0x1800024bc  lea     r8, aInitializerasm_0; "InitializeRasmanMonitorThread exiting ."...
0x1800024c3  mov     edx, 0Ch; dwFlags
0x1800024c8  call    cs:__imp_TracePrintfExA
0x1800024cf  nop     dword ptr [rax+rax+00h]
0x1800024d4  mov     eax, ebx
0x1800024d6  add     rsp, 30h
0x1800024da  pop     rbx
0x1800024db  retn
0x1800024dd  lea     r8, aInitializerasm; "InitializeRasmanMonitorThread Entered ."...
0x1800024e4  mov     edx, 0Ch; dwFlags
0x1800024e9  call    cs:__imp_TracePrintfExA
0x1800024f0  nop     dword ptr [rax+rax+00h]
0x1800024f5  jmp     loc_180002429
0x1800024fa  mov     rcx, cs:g_hEventServiceMonitorTerminate; hObject
0x180002501  test    rcx, rcx
0x180002504  jz      short loc_18000251D
0x180002506  call    cs:__imp_CloseHandle
0x18000250d  nop     dword ptr [rax+rax+00h]
0x180002512  mov     cs:g_hEventServiceMonitorTerminate, 0
0x18000251d  mov     rcx, cs:g_hModule; hLibModule
0x180002524  test    rcx, rcx
0x180002527  jz      short loc_1800024AE
0x180002529  call    cs:__imp_FreeLibrary
0x180002530  nop     dword ptr [rax+rax+00h]
0x180002535  mov     cs:g_hModule, 0
0x180002540  jmp     loc_1800024AE
```
