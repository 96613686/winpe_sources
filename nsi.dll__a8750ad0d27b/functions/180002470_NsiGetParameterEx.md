# NsiGetParameterEx

- ea: `0x180002470`
- end: `0x1800025f1`
- name: `NsiGetParameterEx`
- size: `385`
- prototype: `__int64 __fastcall(PVOID OutputBuffer)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180002470`

## import_xrefs

- `ntdll!NtDeviceIoControlFile` at `0x1800024f3`
- `ntdll!NtDeviceIoControlFile` at `0x1800024f3`
- `ntdll!NtWaitForSingleObject` at `0x1800025dd`
- `ntdll!NtWaitForSingleObject` at `0x1800025dd`
- `ntdll!RtlNtStatusToDosError` at `0x18000254b`
- `ntdll!RtlNtStatusToDosError` at `0x18000254b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000257e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000257e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800025b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800025ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800025b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800025ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002509`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800025a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002509`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800025a3`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800024a9`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800024a9`

## pseudocode

```c
DWORD __fastcall NsiGetParameterEx(_DWORD *OutputBuffer)
{
  ULONG OutputBufferLength; // ebx
  HANDLE EventA; // rsi
  int Status; // ebx
  DWORD result; // eax
  HANDLE FileW; // rax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-18h] BYREF

  IoStatusBlock = 0;
  if ( g_NsiAsyncDeviceHandle != (HANDLE)-1LL )
    goto LABEL_2;
  FileW = CreateFileW(L"\\\\.\\Nsi", 0, 3u, 0, 3u, 0x40000000u, 0);
  if ( FileW != (HANDLE)-1LL )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_NsiAsyncDeviceHandle, (signed __int64)FileW, -1) != -1 )
      CloseHandle(FileW);
LABEL_2:
    OutputBufferLength = OutputBuffer[18];
    EventA = CreateEventA(0, 0, 0, 0);
    if ( !EventA )
      return GetLastError();
    Status = NtDeviceIoControlFile(
               g_NsiAsyncDeviceHandle,
               EventA,
               0,
               0,
               &IoStatusBlock,
               0x120007u,
               OutputBuffer,
               0x50u,
               OutputBuffer,
               OutputBufferLength);
    if ( Status == 259 )
    {
      Status = NtWaitForSingleObject(EventA, 0, 0);
      if ( Status >= 0 )
        Status = IoStatusBlock.Status;
    }
    CloseHandle(EventA);
    if ( Status < 0 )
    {
      if ( (Status & 0xC0000000) == 0xC0000000 )
        return RtlNtStatusToDosError(Status);
    }
    else if ( Status != 261 )
    {
      OutputBuffer[18] = IoStatusBlock.Information;
      return 0;
    }
    OutputBuffer[18] = IoStatusBlock.Information;
    return RtlNtStatusToDosError(Status);
  }
  result = GetLastError();
  if ( !result )
    goto LABEL_2;
  return result;
}

```

## disassembly

```asm
0x180002470  push    rdi
0x180002472  sub     rsp, 60h
0x180002476  cmp     cs:g_NsiAsyncDeviceHandle, 0FFFFFFFFFFFFFFFFh
0x18000247e  xorps   xmm0, xmm0
0x180002481  movups  xmmword ptr [rsp+68h+var_18], xmm0
0x180002486  mov     rdi, rcx
0x180002489  jz      loc_180002553
0x18000248f  mov     [rsp+68h+arg_8], rbx
0x180002494  xor     r9d, r9d; lpName
0x180002497  mov     ebx, [rdi+48h]
0x18000249a  xor     r8d, r8d; bInitialState
0x18000249d  xor     edx, edx; bManualReset
0x18000249f  mov     [rsp+68h+arg_10], rsi
0x1800024a7  xor     ecx, ecx; lpEventAttributes
0x1800024a9  call    cs:__imp_CreateEventA
0x1800024af  mov     rsi, rax
0x1800024b2  test    rax, rax
0x1800024b5  jz      loc_1800025CA
0x1800024bb  mov     rcx, cs:g_NsiAsyncDeviceHandle; FileHandle
0x1800024c2  lea     rax, [rsp+68h+var_18]
0x1800024c7  mov     [rsp+68h+OutputBufferLength], ebx; OutputBufferLength
0x1800024cb  xor     r9d, r9d; ApcContext
0x1800024ce  mov     [rsp+68h+OutputBuffer], rdi; OutputBuffer
0x1800024d3  xor     r8d, r8d; ApcRoutine
0x1800024d6  mov     [rsp+68h+InputBufferLength], 50h ; 'P'; InputBufferLength
0x1800024de  mov     rdx, rsi; Event
0x1800024e1  mov     [rsp+68h+InputBuffer], rdi; InputBuffer
0x1800024e6  mov     [rsp+68h+IoControlCode], 120007h; IoControlCode
0x1800024ee  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x1800024f3  call    cs:__imp_NtDeviceIoControlFile
0x1800024f9  mov     ebx, eax
0x1800024fb  cmp     eax, 103h
0x180002500  jz      loc_1800025D5
0x180002506  mov     rcx, rsi; hObject
0x180002509  call    cs:__imp_CloseHandle
0x18000250f  test    ebx, ebx
0x180002511  js      short loc_18000253B
0x180002513  cmp     ebx, 105h
0x180002519  jz      loc_1800025AE
0x18000251f  mov     eax, dword ptr [rsp+68h+var_18.Information]
0x180002523  mov     [rdi+48h], eax
0x180002526  xor     eax, eax
0x180002528  mov     rbx, [rsp+68h+arg_8]
0x18000252d  mov     rsi, [rsp+68h+arg_10]
0x180002535  add     rsp, 60h
0x180002539  pop     rdi
0x18000253a  retn
0x18000253b  mov     eax, ebx
0x18000253d  and     eax, 0C0000000h
0x180002542  cmp     eax, 0C0000000h
0x180002547  jnz     short loc_1800025AE
0x180002549  mov     ecx, ebx; Status
0x18000254b  call    cs:__imp_RtlNtStatusToDosError
0x180002551  jmp     short loc_180002528
0x180002553  mov     [rsp+68h+InputBuffer], 0; hTemplateFile
0x18000255c  lea     rcx, FileName; "\\\\.\\Nsi"
0x180002563  mov     [rsp+68h+IoControlCode], 40000000h; dwFlagsAndAttributes
0x18000256b  xor     r9d, r9d; lpSecurityAttributes
0x18000256e  xor     edx, edx; dwDesiredAccess
0x180002570  mov     dword ptr [rsp+68h+IoStatusBlock], 3; dwCreationDisposition
0x180002578  mov     r8d, 3; dwShareMode
0x18000257e  call    cs:__imp_CreateFileW
0x180002584  mov     rcx, rax; hObject
0x180002587  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000258b  jz      short loc_1800025B7
0x18000258d  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180002594  lock cmpxchg cs:g_NsiAsyncDeviceHandle, rcx
0x18000259d  jz      loc_18000248F
0x1800025a3  call    cs:__imp_CloseHandle
0x1800025a9  jmp     loc_18000248F
0x1800025ae  mov     eax, dword ptr [rsp+68h+var_18.Information]
0x1800025b2  mov     [rdi+48h], eax
0x1800025b5  jmp     short loc_180002549
0x1800025b7  call    cs:__imp_GetLastError
0x1800025bd  test    eax, eax
0x1800025bf  jz      loc_18000248F
0x1800025c5  jmp     loc_180002535
0x1800025ca  call    cs:__imp_GetLastError
0x1800025d0  jmp     loc_180002528
0x1800025d5  xor     r8d, r8d; Timeout
0x1800025d8  xor     edx, edx; Alertable
0x1800025da  mov     rcx, rsi; Handle
0x1800025dd  call    cs:__imp_NtWaitForSingleObject
0x1800025e3  test    eax, eax
0x1800025e5  mov     ebx, eax
0x1800025e7  cmovns  ebx, dword ptr [rsp+68h+var_18]
0x1800025ec  jmp     loc_180002506
```
