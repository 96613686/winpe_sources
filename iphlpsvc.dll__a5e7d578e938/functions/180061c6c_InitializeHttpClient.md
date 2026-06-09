# InitializeHttpClient

- ea: `0x180061c6c`
- end: `0x180061d6b`
- name: `InitializeHttpClient`
- size: `255`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003cf4`

## callees

- `0x18000d7c0`
- `0x180061c6c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180061cb5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180061cb5`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180061c96`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180061c96`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180061cf4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180061cf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061ccd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061d27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061ccd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061d27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061d4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061d4e`
- `webio!__imp_WebInitialize` at `0x180061d17`
- `webio!__imp_WebInitialize` at `0x180061d17`

## string_xrefs

- `0x180061cd9`: `InitializeHttpClient CreateEvent failed: %d`

## pseudocode

```c
char InitializeHttpClient()
{
  DWORD LastError; // eax
  DWORD v2; // eax

  dword_1800CC330 = 0;
  qword_1800CC348 = (__int64)&qword_1800CC340;
  qword_1800CC340 = (__int64)&qword_1800CC340;
  InitializeCriticalSection(&stru_1800CC350);
  byte_1800CC378 = 0;
  qword_1800CC338 = CreateEventW(0, 1, 1, 0);
  if ( !qword_1800CC338 )
  {
    LastError = GetLastError();
    EventWrite0(0x10000000, L"InitializeHttpClient CreateEvent failed: %d", LastError);
LABEL_3:
    DeleteCriticalSection(&stru_1800CC350);
    return 0;
  }
  if ( (unsigned int)WebInitialize(0x1000000010000LL, 0, &qword_1800CC328) )
  {
    v2 = GetLastError();
    EventWrite0(0x10000000, L"WebInitialize failed: %d", v2);
    CloseHandle(qword_1800CC338);
    goto LABEL_3;
  }
  byte_1800CC379 = 1;
  return 1;
}

```

## disassembly

```asm
0x180061c6c  sub     rsp, 28h
0x180061c70  lea     rax, qword_1800CC340
0x180061c77  mov     cs:dword_1800CC330, 0
0x180061c81  lea     rcx, stru_1800CC350; lpCriticalSection
0x180061c88  mov     cs:qword_1800CC348, rax
0x180061c8f  mov     cs:qword_1800CC340, rax
0x180061c96  call    cs:__imp_InitializeCriticalSection
0x180061c9d  nop     dword ptr [rax+rax+00h]
0x180061ca2  xor     r9d, r9d; lpName
0x180061ca5  mov     cs:byte_1800CC378, 0
0x180061cac  xor     ecx, ecx; lpEventAttributes
0x180061cae  lea     edx, [r9+1]; bManualReset
0x180061cb2  mov     r8d, edx; bInitialState
0x180061cb5  call    cs:__imp_CreateEventW
0x180061cbc  nop     dword ptr [rax+rax+00h]
0x180061cc1  mov     cs:qword_1800CC338, rax
0x180061cc8  test    rax, rax
0x180061ccb  jnz     short loc_180061D04
0x180061ccd  call    cs:__imp_GetLastError
0x180061cd4  nop     dword ptr [rax+rax+00h]
0x180061cd9  lea     rdx, aInitializehttp; "InitializeHttpClient CreateEvent failed"...
0x180061ce0  mov     ecx, 10000000h
0x180061ce5  mov     r8d, eax
0x180061ce8  call    EventWrite0
0x180061ced  lea     rcx, stru_1800CC350; lpCriticalSection
0x180061cf4  call    cs:__imp_DeleteCriticalSection
0x180061cfb  nop     dword ptr [rax+rax+00h]
0x180061d00  xor     al, al
0x180061d02  jmp     short loc_180061D65
0x180061d04  lea     r8, qword_1800CC328
0x180061d0b  xor     edx, edx
0x180061d0d  mov     rcx, 1000000010000h
0x180061d17  call    cs:__imp_WebInitialize
0x180061d1e  nop     dword ptr [rax+rax+00h]
0x180061d23  test    eax, eax
0x180061d25  jz      short loc_180061D5C
0x180061d27  call    cs:__imp_GetLastError
0x180061d2e  nop     dword ptr [rax+rax+00h]
0x180061d33  lea     rdx, aWebinitializeF; "WebInitialize failed: %d"
0x180061d3a  mov     ecx, 10000000h
0x180061d3f  mov     r8d, eax
0x180061d42  call    EventWrite0
0x180061d47  mov     rcx, cs:qword_1800CC338; hObject
0x180061d4e  call    cs:__imp_CloseHandle
0x180061d55  nop     dword ptr [rax+rax+00h]
0x180061d5a  jmp     short loc_180061CED
0x180061d5c  mov     cs:byte_1800CC379, 1
0x180061d63  mov     al, 1
0x180061d65  add     rsp, 28h
0x180061d69  retn
```
