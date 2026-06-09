# InitializeHttpClient

- ea: `0x180061c4c`
- end: `0x180061d4b`
- name: `InitializeHttpClient`
- size: `255`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003ce4`

## callees

- `0x18000d7b0`
- `0x180061c4c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180061c95`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180061c95`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180061c76`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180061c76`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180061cd4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180061cd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061cad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061d07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061cad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061d07`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061d2e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061d2e`
- `webio!__imp_WebInitialize` at `0x180061cf7`
- `webio!__imp_WebInitialize` at `0x180061cf7`

## string_xrefs

- `0x180061cb9`: `InitializeHttpClient CreateEvent failed: %d`

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
0x180061c4c  sub     rsp, 28h
0x180061c50  lea     rax, qword_1800CC340
0x180061c57  mov     cs:dword_1800CC330, 0
0x180061c61  lea     rcx, stru_1800CC350; lpCriticalSection
0x180061c68  mov     cs:qword_1800CC348, rax
0x180061c6f  mov     cs:qword_1800CC340, rax
0x180061c76  call    cs:__imp_InitializeCriticalSection
0x180061c7d  nop     dword ptr [rax+rax+00h]
0x180061c82  xor     r9d, r9d; lpName
0x180061c85  mov     cs:byte_1800CC378, 0
0x180061c8c  xor     ecx, ecx; lpEventAttributes
0x180061c8e  lea     edx, [r9+1]; bManualReset
0x180061c92  mov     r8d, edx; bInitialState
0x180061c95  call    cs:__imp_CreateEventW
0x180061c9c  nop     dword ptr [rax+rax+00h]
0x180061ca1  mov     cs:qword_1800CC338, rax
0x180061ca8  test    rax, rax
0x180061cab  jnz     short loc_180061CE4
0x180061cad  call    cs:__imp_GetLastError
0x180061cb4  nop     dword ptr [rax+rax+00h]
0x180061cb9  lea     rdx, aInitializehttp; "InitializeHttpClient CreateEvent failed"...
0x180061cc0  mov     ecx, 10000000h
0x180061cc5  mov     r8d, eax
0x180061cc8  call    EventWrite0
0x180061ccd  lea     rcx, stru_1800CC350; lpCriticalSection
0x180061cd4  call    cs:__imp_DeleteCriticalSection
0x180061cdb  nop     dword ptr [rax+rax+00h]
0x180061ce0  xor     al, al
0x180061ce2  jmp     short loc_180061D45
0x180061ce4  lea     r8, qword_1800CC328
0x180061ceb  xor     edx, edx
0x180061ced  mov     rcx, 1000000010000h
0x180061cf7  call    cs:__imp_WebInitialize
0x180061cfe  nop     dword ptr [rax+rax+00h]
0x180061d03  test    eax, eax
0x180061d05  jz      short loc_180061D3C
0x180061d07  call    cs:__imp_GetLastError
0x180061d0e  nop     dword ptr [rax+rax+00h]
0x180061d13  lea     rdx, aWebinitializeF; "WebInitialize failed: %d"
0x180061d1a  mov     ecx, 10000000h
0x180061d1f  mov     r8d, eax
0x180061d22  call    EventWrite0
0x180061d27  mov     rcx, cs:qword_1800CC338; hObject
0x180061d2e  call    cs:__imp_CloseHandle
0x180061d35  nop     dword ptr [rax+rax+00h]
0x180061d3a  jmp     short loc_180061CCD
0x180061d3c  mov     cs:byte_1800CC379, 1
0x180061d43  mov     al, 1
0x180061d45  add     rsp, 28h
0x180061d49  retn
```
