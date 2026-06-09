# CONFIG_MANAGER::LaunchChangeNotificationListener(void)

- ea: `0x18002f194`
- end: `0x18002f312`
- name: `?LaunchChangeNotificationListener@CONFIG_MANAGER@@AEAAJXZ`
- size: `382`
- prototype: `__int64 __fastcall(CONFIG_MANAGER *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002e84c`

## callees

- `0x18002f194`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002f2dc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002f2dc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002f1ad`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002f1ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f1bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f252`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f2a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f1bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f252`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f2a5`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002f240`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002f240`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18002f298`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18002f298`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f2f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f2f4`
- `iisutil!PuDbgPrintError` at `0x18002f20c`
- `iisutil!PuDbgPrintError` at `0x18002f20c`

## string_xrefs

- `0x18002f201`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\config_manager.cxx`
- `0x18002f1e1`: `Failed to initialize blocking event to wait on config thread starting\n`
- `0x18002f1f5`: `CONFIG_MANAGER::LaunchChangeNotificationListener`
- `0x18002f270`: `Failed to launch the thread to handle change notifications\n`
- `0x18002f2c3`: `Failed to resume the thread to handle change notifications\n`

## pseudocode

```c
__int64 __fastcall CONFIG_MANAGER::LaunchChangeNotificationListener(CONFIG_MANAGER *this)
{
  HANDLE EventW; // rax
  signed int v3; // eax
  unsigned int v4; // ebx
  HANDLE Thread; // rax
  signed int v6; // eax
  signed int LastError; // eax
  void *v8; // rcx

  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 35) = EventW;
  if ( EventW )
  {
    Thread = CreateThread(
               0,
               0x8000u,
               (LPTHREAD_START_ROUTINE)ChangeNotificationLauncher,
               *((LPVOID *)this + 32),
               4u,
               (LPDWORD)this + 66);
    *((_QWORD *)this + 34) = Thread;
    if ( Thread )
    {
      *((_DWORD *)g_pWebAdminService + 393) = *((_DWORD *)this + 66);
      if ( ResumeThread(*((HANDLE *)this + 34)) == -1 )
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_manager.cxx",
            1023,
            "CONFIG_MANAGER::LaunchChangeNotificationListener",
            v4,
            "Failed to resume the thread to handle change notifications\n");
      }
      else
      {
        WaitForSingleObject(*((HANDLE *)this + 35), 0xFFFFFFFF);
        v4 = *((_DWORD *)this + 72);
      }
    }
    else
    {
      v6 = GetLastError();
      v4 = v6;
      if ( v6 > 0 )
        v4 = (unsigned __int16)v6 | 0x80070000;
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_manager.cxx",
          1006,
          "CONFIG_MANAGER::LaunchChangeNotificationListener",
          v4,
          "Failed to launch the thread to handle change notifications\n");
    }
  }
  else
  {
    v3 = GetLastError();
    v4 = v3;
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_manager.cxx",
        985,
        "CONFIG_MANAGER::LaunchChangeNotificationListener",
        v4,
        "Failed to initialize blocking event to wait on config thread starting\n");
  }
  v8 = (void *)*((_QWORD *)this + 35);
  if ( v8 )
  {
    CloseHandle(v8);
    *((_QWORD *)this + 35) = 0;
  }
  return v4;
}

```

## disassembly

```asm
0x18002f194  mov     [rsp+arg_0], rbx
0x18002f199  push    rdi
0x18002f19a  sub     rsp, 30h
0x18002f19e  xor     r9d, r9d; lpName
0x18002f1a1  mov     rdi, rcx
0x18002f1a4  xor     r8d, r8d; bInitialState
0x18002f1a7  xor     ecx, ecx; lpEventAttributes
0x18002f1a9  lea     edx, [r9+1]; bManualReset
0x18002f1ad  call    cs:__imp_CreateEventW
0x18002f1b3  mov     [rdi+118h], rax
0x18002f1ba  test    rax, rax
0x18002f1bd  jnz     short loc_18002F217
0x18002f1bf  call    cs:__imp_GetLastError
0x18002f1c5  mov     ebx, eax
0x18002f1c7  test    eax, eax
0x18002f1c9  jle     short loc_18002F1D4
0x18002f1cb  movzx   ebx, ax
0x18002f1ce  or      ebx, 80070000h
0x18002f1d4  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002f1db  jz      loc_18002F2E8
0x18002f1e1  lea     rax, aFailedToInitia_1; "Failed to initialize blocking event to "...
0x18002f1e8  mov     r8d, 3D9h
0x18002f1ee  mov     rcx, cs:g_pDebug
0x18002f1f5  lea     r9, aConfigManagerL; "CONFIG_MANAGER::LaunchChangeNotificatio"...
0x18002f1fc  mov     [rsp+38h+lpThreadId], rax
0x18002f201  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002f208  mov     [rsp+38h+dwCreationFlags], ebx
0x18002f20c  call    cs:__imp_PuDbgPrintError
0x18002f212  jmp     loc_18002F2E8
0x18002f217  mov     r9, [rdi+100h]; lpParameter
0x18002f21e  lea     rbx, [rdi+108h]
0x18002f225  mov     [rsp+38h+lpThreadId], rbx; lpThreadId
0x18002f22a  lea     r8, ?ChangeNotificationLauncher@@YAKPEAX@Z; lpStartAddress
0x18002f231  mov     edx, 8000h; dwStackSize
0x18002f236  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x18002f23e  xor     ecx, ecx; lpThreadAttributes
0x18002f240  call    cs:__imp_CreateThread
0x18002f246  mov     [rdi+110h], rax
0x18002f24d  test    rax, rax
0x18002f250  jnz     short loc_18002F282
0x18002f252  call    cs:__imp_GetLastError
0x18002f258  mov     ebx, eax
0x18002f25a  test    eax, eax
0x18002f25c  jle     short loc_18002F267
0x18002f25e  movzx   ebx, ax
0x18002f261  or      ebx, 80070000h
0x18002f267  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002f26e  jz      short loc_18002F2E8
0x18002f270  lea     rax, aFailedToLaunch; "Failed to launch the thread to handle c"...
0x18002f277  mov     r8d, 3EEh
0x18002f27d  jmp     loc_18002F1EE
0x18002f282  mov     ecx, [rbx]
0x18002f284  mov     rax, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x18002f28b  mov     [rax+624h], ecx
0x18002f291  mov     rcx, [rdi+110h]; hThread
0x18002f298  call    cs:__imp_ResumeThread
0x18002f29e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002f2a1  cmp     eax, edx
0x18002f2a3  jnz     short loc_18002F2D5
0x18002f2a5  call    cs:__imp_GetLastError
0x18002f2ab  mov     ebx, eax
0x18002f2ad  test    eax, eax
0x18002f2af  jle     short loc_18002F2BA
0x18002f2b1  movzx   ebx, ax
0x18002f2b4  or      ebx, 80070000h
0x18002f2ba  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002f2c1  jz      short loc_18002F2E8
0x18002f2c3  lea     rax, aFailedToResume; "Failed to resume the thread to handle c"...
0x18002f2ca  mov     r8d, 3FFh
0x18002f2d0  jmp     loc_18002F1EE
0x18002f2d5  mov     rcx, [rdi+118h]; hHandle
0x18002f2dc  call    cs:__imp_WaitForSingleObject
0x18002f2e2  mov     ebx, [rdi+120h]
0x18002f2e8  mov     rcx, [rdi+118h]; hObject
0x18002f2ef  test    rcx, rcx
0x18002f2f2  jz      short loc_18002F305
0x18002f2f4  call    cs:__imp_CloseHandle
0x18002f2fa  mov     qword ptr [rdi+118h], 0
0x18002f305  mov     eax, ebx
0x18002f307  mov     rbx, [rsp+38h+arg_0]
0x18002f30c  add     rsp, 30h
0x18002f310  pop     rdi
0x18002f311  retn
```
