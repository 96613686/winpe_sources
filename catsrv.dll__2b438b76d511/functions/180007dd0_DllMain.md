# DllMain

- ea: `0x180007dd0`
- end: `0x180007e9c`
- name: `DllMain`
- size: `204`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180013214`

## callees

- `0x180007dd0`
- `0x18002f758`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180007e19`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180007e35`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180007e19`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180007e35`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007e6f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007e81`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007e6f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007e81`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180007e09`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180007e09`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  if ( fdwReason == 1 )
  {
    if ( DllMainHelper::s_fFailLoad )
      return 0;
    qword_1800721B0 = hinstDLL;
    qword_1800721A8 = (struct ATL::_ATL_OBJMAP_ENTRY *)&off_180072000;
    DisableThreadLibraryCalls(hinstDLL);
    g_ThreadStartEvent = CreateEventW(0, 0, 0, 0);
    if ( !g_ThreadStartEvent )
      return 0;
    g_ThreadStopEvent = CreateEventW(0, 0, 0, 0);
    if ( !g_ThreadStopEvent )
      return 0;
    DllMainHelper::s_fOutOfDllMain = 1;
  }
  else if ( !fdwReason )
  {
    if ( g_bThreadRunning )
      RegSrvrStop(0);
    if ( g_ThreadStartEvent )
      CloseHandle(g_ThreadStartEvent);
    if ( g_ThreadStopEvent )
      CloseHandle(g_ThreadStopEvent);
    g_ThreadStartEvent = 0;
    g_ThreadStopEvent = 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180007dd0  sub     rsp, 28h
0x180007dd4  cmp     edx, 1
0x180007dd7  jnz     short loc_180007DE9
0x180007dd9  cmp     cs:?s_fFailLoad@DllMainHelper@@0HA, 0; int DllMainHelper::s_fFailLoad
0x180007de0  jz      short loc_180007DF4
0x180007de2  xor     eax, eax
0x180007de4  add     rsp, 28h
0x180007de8  retn
0x180007de9  test    edx, edx
0x180007deb  jz      short loc_180007E53
0x180007ded  mov     eax, 1
0x180007df2  jmp     short loc_180007DE4
0x180007df4  lea     rax, off_180072000
0x180007dfb  mov     cs:qword_1800721B0, rcx
0x180007e02  mov     cs:qword_1800721A8, rax
0x180007e09  call    cs:__imp_DisableThreadLibraryCalls
0x180007e0f  xor     r9d, r9d; lpName
0x180007e12  xor     r8d, r8d; bInitialState
0x180007e15  xor     edx, edx; bManualReset
0x180007e17  xor     ecx, ecx; lpEventAttributes
0x180007e19  call    cs:__imp_CreateEventW
0x180007e1f  mov     cs:?g_ThreadStartEvent@@3PEAXEA, rax; void * g_ThreadStartEvent
0x180007e26  test    rax, rax
0x180007e29  jz      short loc_180007DE2
0x180007e2b  xor     r9d, r9d; lpName
0x180007e2e  xor     r8d, r8d; bInitialState
0x180007e31  xor     edx, edx; bManualReset
0x180007e33  xor     ecx, ecx; lpEventAttributes
0x180007e35  call    cs:__imp_CreateEventW
0x180007e3b  mov     cs:?g_ThreadStopEvent@@3PEAXEA, rax; void * g_ThreadStopEvent
0x180007e42  test    rax, rax
0x180007e45  jz      short loc_180007DE2
0x180007e47  mov     cs:?s_fOutOfDllMain@DllMainHelper@@0HA, 1; int DllMainHelper::s_fOutOfDllMain
0x180007e51  jmp     short loc_180007DED
0x180007e53  cmp     cs:?g_bThreadRunning@@3HA, 0; int g_bThreadRunning
0x180007e5a  jz      short loc_180007E63
0x180007e5c  xor     ecx, ecx; dwMilliseconds
0x180007e5e  call    ?RegSrvrStop@@YAJK@Z; RegSrvrStop(ulong)
0x180007e63  mov     rcx, cs:?g_ThreadStartEvent@@3PEAXEA; hObject
0x180007e6a  test    rcx, rcx
0x180007e6d  jz      short loc_180007E75
0x180007e6f  call    cs:__imp_CloseHandle
0x180007e75  mov     rcx, cs:?g_ThreadStopEvent@@3PEAXEA; hObject
0x180007e7c  test    rcx, rcx
0x180007e7f  jz      short loc_180007E87
0x180007e81  call    cs:__imp_CloseHandle
0x180007e87  xor     eax, eax
0x180007e89  mov     cs:?g_ThreadStartEvent@@3PEAXEA, rax; void * g_ThreadStartEvent
0x180007e90  mov     cs:?g_ThreadStopEvent@@3PEAXEA, rax; void * g_ThreadStopEvent
0x180007e97  jmp     loc_180007DED
```
