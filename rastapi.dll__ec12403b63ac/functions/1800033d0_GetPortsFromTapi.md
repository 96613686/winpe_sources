# GetPortsFromTapi

- ea: `0x1800033d0`
- end: `0x1800034fc`
- name: `GetPortsFromTapi`
- size: `300`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800138b0`
- `0x1800154f0`
- `0x1800158c0`

## callees

- `0x1800033d0`
- `0x18000d92c`
- `0x1800292b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000340b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003471`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000340b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003471`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800033fd`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800033fd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180003485`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000349d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180003485`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000349d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000346b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800034aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800034b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800034dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000346b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800034aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800034b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800034dc`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180003456`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180003456`

## string_xrefs

- `0x180003411`: `GetPortsFromTapi: CreateEvent failed with error 0x%x`
- `0x180003477`: `GetPortsFromTapi: CreateThread failed with error 0x%x`

## pseudocode

```c
__int64 __fastcall GetPortsFromTapi(int a1)
{
  HANDLE EventA; // rdi
  DWORD LastError; // eax
  const CHAR *v4; // rcx
  DWORD v5; // ebx
  __int128 Parameter; // [rsp+30h] [rbp-28h] BYREF

  Parameter = 0;
  EventA = CreateEventA(0, 0, 0, 0);
  if ( !EventA )
  {
    LastError = GetLastError();
    v4 = "GetPortsFromTapi: CreateEvent failed with error 0x%x";
LABEL_3:
    v5 = LastError;
    RasTapiTrace(v4);
    return v5;
  }
  *(_QWORD *)&Parameter = EventA;
  DWORD2(Parameter) = a1;
  TapiThreadHandle = CreateThread(0, 0x1388u, (LPTHREAD_START_ROUTINE)EnumerateTapiPorts, &Parameter, 0, &TapiThreadId);
  if ( !TapiThreadHandle )
  {
    CloseHandle(EventA);
    LastError = GetLastError();
    v4 = "GetPortsFromTapi: CreateThread failed with error 0x%x";
    goto LABEL_3;
  }
  WaitForSingleObject(EventA, 0xFFFFFFFF);
  if ( RasLine )
  {
    v5 = 0;
    CloseHandle(EventA);
  }
  else
  {
    WaitForSingleObject(TapiThreadHandle, 0xFFFFFFFF);
    CloseHandle(TapiThreadHandle);
    CloseHandle(EventA);
    TapiThreadHandle = 0;
    RasTapiTrace("GetPortsFromTapi: RasLine == 0, returning ERROR_PORT_NOT_FOUND");
    return 615;
  }
  return v5;
}

```

## disassembly

```asm
0x1800033d0  mov     [rsp+arg_8], rbx
0x1800033d5  push    rdi
0x1800033d6  sub     rsp, 50h
0x1800033da  mov     rax, cs:__security_cookie
0x1800033e1  xor     rax, rsp
0x1800033e4  mov     [rsp+58h+var_18], rax
0x1800033e9  mov     ebx, ecx
0x1800033eb  xorps   xmm0, xmm0
0x1800033ee  xor     ecx, ecx; lpEventAttributes
0x1800033f0  xor     r9d, r9d; lpName
0x1800033f3  xor     r8d, r8d; bInitialState
0x1800033f6  xor     edx, edx; bManualReset
0x1800033f8  movups  [rsp+58h+Parameter], xmm0
0x1800033fd  call    cs:__imp_CreateEventA
0x180003403  mov     rdi, rax
0x180003406  test    rax, rax
0x180003409  jnz     short loc_180003426
0x18000340b  call    cs:__imp_GetLastError
0x180003411  lea     rcx, aGetportsfromta_0; "GetPortsFromTapi: CreateEvent failed wi"...
0x180003418  mov     edx, eax
0x18000341a  mov     ebx, eax
0x18000341c  call    RasTapiTrace
0x180003421  jmp     loc_1800034E2
0x180003426  lea     rax, TapiThreadId
0x18000342d  mov     qword ptr [rsp+58h+Parameter], rdi
0x180003432  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x180003437  lea     r9, [rsp+58h+Parameter]; lpParameter
0x18000343c  lea     r8, EnumerateTapiPorts; lpStartAddress
0x180003443  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x18000344b  mov     edx, 1388h; dwStackSize
0x180003450  mov     dword ptr [rsp+58h+Parameter+8], ebx
0x180003454  xor     ecx, ecx; lpThreadAttributes
0x180003456  call    cs:__imp_CreateThread
0x18000345c  mov     cs:TapiThreadHandle, rax
0x180003463  mov     rcx, rdi; hHandle
0x180003466  test    rax, rax
0x180003469  jnz     short loc_180003480
0x18000346b  call    cs:__imp_CloseHandle
0x180003471  call    cs:__imp_GetLastError
0x180003477  lea     rcx, aGetportsfromta; "GetPortsFromTapi: CreateThread failed w"...
0x18000347e  jmp     short loc_180003418
0x180003480  or      ebx, 0FFFFFFFFh
0x180003483  mov     edx, ebx; dwMilliseconds
0x180003485  call    cs:__imp_WaitForSingleObject
0x18000348b  cmp     cs:RasLine, 0
0x180003492  jnz     short loc_1800034D7
0x180003494  mov     rcx, cs:TapiThreadHandle; hHandle
0x18000349b  mov     edx, ebx; dwMilliseconds
0x18000349d  call    cs:__imp_WaitForSingleObject
0x1800034a3  mov     rcx, cs:TapiThreadHandle; hObject
0x1800034aa  call    cs:__imp_CloseHandle
0x1800034b0  mov     rcx, rdi; hObject
0x1800034b3  call    cs:__imp_CloseHandle
0x1800034b9  lea     rcx, aGetportsfromta_1; "GetPortsFromTapi: RasLine == 0, returni"...
0x1800034c0  mov     cs:TapiThreadHandle, 0
0x1800034cb  call    RasTapiTrace
0x1800034d0  mov     ebx, 267h
0x1800034d5  jmp     short loc_1800034E2
0x1800034d7  xor     ebx, ebx
0x1800034d9  mov     rcx, rdi; hObject
0x1800034dc  call    cs:__imp_CloseHandle
0x1800034e2  mov     eax, ebx
0x1800034e4  mov     rcx, [rsp+58h+var_18]
0x1800034e9  xor     rcx, rsp; StackCookie
0x1800034ec  call    __security_check_cookie
0x1800034f1  mov     rbx, [rsp+58h+arg_8]
0x1800034f6  add     rsp, 50h
0x1800034fa  pop     rdi
0x1800034fb  retn
```
