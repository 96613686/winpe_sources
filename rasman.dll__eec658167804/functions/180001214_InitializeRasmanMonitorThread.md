# InitializeRasmanMonitorThread

- ea: `0x180001214`
- end: `0x180001311`
- name: `InitializeRasmanMonitorThread`
- size: `253`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callers

- `0x180002504`

## callees

- `0x180001214`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180001233`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180001233`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180001278`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180001278`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180001255`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180001255`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800012fe`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800012fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800012e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800012e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000128a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000128a`
- `rtutils!TracePrintfExA` at `0x1800012b0`
- `rtutils!TracePrintfExA` at `0x1800012ca`
- `rtutils!TracePrintfExA` at `0x1800012b0`
- `rtutils!TracePrintfExA` at `0x1800012ca`

## string_xrefs

- `0x1800012a4`: `InitializeRasmanMonitorThread exiting ... %d`
- `0x18000124e`: `rasman.dll`
- `0x1800012be`: `InitializeRasmanMonitorThread Entered ...`

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
    || (LastError = 0, (g_hRasmanServiceMonitorThread = CreateThread(0, 0, RasmanServiceMonitorThread, 0, 0, 0)) == 0) )
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
0x180001214  push    rbx
0x180001216  sub     rsp, 30h
0x18000121a  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180001220  cmp     ecx, 0FFFFFFFFh
0x180001223  jnz     loc_1800012BE
0x180001229  xor     r9d, r9d; lpName
0x18000122c  xor     r8d, r8d; bInitialState
0x18000122f  xor     edx, edx; bManualReset
0x180001231  xor     ecx, ecx; lpEventAttributes
0x180001233  call    cs:__imp_CreateEventA
0x180001239  mov     cs:g_hEventServiceMonitorTerminate, rax
0x180001240  test    rax, rax
0x180001243  jz      short loc_18000128A
0x180001245  lea     r8, g_hModule; phModule
0x18000124c  xor     ecx, ecx; dwFlags
0x18000124e  lea     rdx, ModuleName; "rasman.dll"
0x180001255  call    cs:__imp_GetModuleHandleExA
0x18000125b  test    eax, eax
0x18000125d  jz      short loc_18000128A
0x18000125f  xor     ebx, ebx
0x180001261  lea     r8, RasmanServiceMonitorThread; lpStartAddress
0x180001268  mov     [rsp+38h+lpThreadId], rbx; lpThreadId
0x18000126d  xor     r9d, r9d; lpParameter
0x180001270  xor     edx, edx; dwStackSize
0x180001272  mov     [rsp+38h+dwCreationFlags], ebx; dwCreationFlags
0x180001276  xor     ecx, ecx; lpThreadAttributes
0x180001278  call    cs:__imp_CreateThread
0x18000127e  mov     cs:g_hRasmanServiceMonitorThread, rax
0x180001285  test    rax, rax
0x180001288  jnz     short loc_180001296
0x18000128a  call    cs:__imp_GetLastError
0x180001290  mov     ebx, eax
0x180001292  test    eax, eax
0x180001294  jnz     short loc_1800012D5
0x180001296  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000129c  cmp     ecx, 0FFFFFFFFh
0x18000129f  jz      short loc_1800012B6
0x1800012a1  mov     r9d, ebx
0x1800012a4  lea     r8, szFormat; "InitializeRasmanMonitorThread exiting ."...
0x1800012ab  mov     edx, 0Ch; dwFlags
0x1800012b0  call    cs:__imp_TracePrintfExA
0x1800012b6  mov     eax, ebx
0x1800012b8  add     rsp, 30h
0x1800012bc  pop     rbx
0x1800012bd  retn
0x1800012be  lea     r8, aInitializerasm; "InitializeRasmanMonitorThread Entered ."...
0x1800012c5  mov     edx, 0Ch; dwFlags
0x1800012ca  call    cs:__imp_TracePrintfExA
0x1800012d0  jmp     loc_180001229
0x1800012d5  mov     rcx, cs:g_hEventServiceMonitorTerminate; hObject
0x1800012dc  test    rcx, rcx
0x1800012df  jz      short loc_1800012F2
0x1800012e1  call    cs:__imp_CloseHandle
0x1800012e7  mov     cs:g_hEventServiceMonitorTerminate, 0
0x1800012f2  mov     rcx, cs:g_hModule; hLibModule
0x1800012f9  test    rcx, rcx
0x1800012fc  jz      short loc_180001296
0x1800012fe  call    cs:__imp_FreeLibrary
0x180001304  mov     cs:g_hModule, 0
0x18000130f  jmp     short loc_180001296
```
