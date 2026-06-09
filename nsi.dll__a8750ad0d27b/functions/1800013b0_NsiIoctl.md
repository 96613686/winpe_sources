# NsiIoctl

- ea: `0x1800013b0`
- end: `0x1800015bc`
- name: `NsiIoctl`
- size: `524`
- prototype: `__int64 __fastcall(DWORD dwIoControlCode, LPVOID lpInBuffer, DWORD nInBufferSize, LPVOID lpOutBuffer, LPDWORD lpBytesReturned, LPOVERLAPPED lpOverlapped)`
- caller_count: `13`
- callee_count: `1`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180001010`
- `0x1800010a0`
- `0x180001140`
- `0x1800011a0`
- `0x1800011e0`
- `0x180001280`
- `0x180001330`
- `0x180001370`
- `0x180002b50`
- `0x180002b90`
- `0x180002e40`
- `0x180002ea0`
- `0x180003040`

## callees

- `0x1800013b0`

## import_xrefs

- `ntdll!NtDeviceIoControlFile` at `0x180001462`
- `ntdll!NtDeviceIoControlFile` at `0x180001462`
- `ntdll!NtWaitForSingleObject` at `0x1800015a8`
- `ntdll!NtWaitForSingleObject` at `0x1800015a8`
- `ntdll!RtlNtStatusToDosError` at `0x1800014d5`
- `ntdll!RtlNtStatusToDosError` at `0x1800014d5`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000155b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000155b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180001508`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180001508`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001565`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001582`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001595`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001565`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001582`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001595`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001478`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000152d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001478`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000152d`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000141e`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000141e`

## pseudocode

```c
DWORD __fastcall NsiIoctl(
        DWORD dwIoControlCode,
        LPVOID lpInBuffer,
        DWORD nInBufferSize,
        LPVOID lpOutBuffer,
        LPDWORD lpBytesReturned,
        LPOVERLAPPED lpOverlapped)
{
  ULONG OutputBufferLength; // ebx
  HANDLE EventA; // rdi
  int Status; // ebx
  DWORD result; // eax
  HANDLE FileW; // rax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp-30h] BYREF

  IoStatusBlock = 0;
  if ( g_NsiAsyncDeviceHandle == (HANDLE)-1LL )
  {
    FileW = CreateFileW(L"\\\\.\\Nsi", 0, 3u, 0, 3u, 0x40000000u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      result = GetLastError();
      if ( result )
        return result;
    }
    else if ( _InterlockedCompareExchange64(
                (volatile signed __int64 *)&g_NsiAsyncDeviceHandle,
                (signed __int64)FileW,
                -1) != -1 )
    {
      CloseHandle(FileW);
    }
  }
  OutputBufferLength = *lpBytesReturned;
  if ( !lpOverlapped )
  {
    EventA = CreateEventA(0, 0, 0, 0);
    if ( EventA )
    {
      Status = NtDeviceIoControlFile(
                 g_NsiAsyncDeviceHandle,
                 EventA,
                 0,
                 0,
                 &IoStatusBlock,
                 dwIoControlCode,
                 lpInBuffer,
                 nInBufferSize,
                 lpOutBuffer,
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
        *lpBytesReturned = IoStatusBlock.Information;
        return 0;
      }
      *lpBytesReturned = IoStatusBlock.Information;
      return RtlNtStatusToDosError(Status);
    }
    return GetLastError();
  }
  if ( !DeviceIoControl(
          g_NsiAsyncDeviceHandle,
          dwIoControlCode,
          lpInBuffer,
          nInBufferSize,
          lpOutBuffer,
          OutputBufferLength,
          lpBytesReturned,
          lpOverlapped) )
    return GetLastError();
  return 0;
}

```

## disassembly

```asm
0x1800013b0  mov     [rsp+arg_18], rbp
0x1800013b5  push    r12
0x1800013b7  push    r14
0x1800013b9  push    r15
0x1800013bb  sub     rsp, 70h
0x1800013bf  cmp     cs:g_NsiAsyncDeviceHandle, 0FFFFFFFFFFFFFFFFh
0x1800013c7  xorps   xmm0, xmm0
0x1800013ca  movups  xmmword ptr [rsp+88h+var_30], xmm0
0x1800013cf  mov     rbp, r9
0x1800013d2  mov     r14d, r8d
0x1800013d5  mov     r15, rdx
0x1800013d8  mov     r12d, ecx
0x1800013db  jz      loc_1800014DD
0x1800013e1  mov     rax, [rsp+88h+lpOverlapped]
0x1800013e9  mov     [rsp+88h+arg_0], rbx
0x1800013f1  mov     [rsp+88h+arg_8], rsi
0x1800013f9  mov     rsi, [rsp+88h+lpBytesReturned]
0x180001401  mov     ebx, [rsi]
0x180001403  test    rax, rax
0x180001406  jnz     loc_180001538
0x18000140c  xor     r9d, r9d; lpName
0x18000140f  mov     [rsp+88h+arg_10], rdi
0x180001417  xor     r8d, r8d; bInitialState
0x18000141a  xor     edx, edx; bManualReset
0x18000141c  xor     ecx, ecx; lpEventAttributes
0x18000141e  call    cs:__imp_CreateEventA
0x180001424  mov     rdi, rax
0x180001427  test    rax, rax
0x18000142a  jz      loc_180001595
0x180001430  mov     rcx, cs:g_NsiAsyncDeviceHandle; FileHandle
0x180001437  lea     rax, [rsp+88h+var_30]
0x18000143c  mov     [rsp+88h+OutputBufferLength], ebx; OutputBufferLength
0x180001440  xor     r9d, r9d; ApcContext
0x180001443  mov     [rsp+88h+OutputBuffer], rbp; OutputBuffer
0x180001448  xor     r8d, r8d; ApcRoutine
0x18000144b  mov     [rsp+88h+InputBufferLength], r14d; InputBufferLength
0x180001450  mov     rdx, rdi; Event
0x180001453  mov     [rsp+88h+InputBuffer], r15; InputBuffer
0x180001458  mov     [rsp+88h+IoControlCode], r12d; IoControlCode
0x18000145d  mov     [rsp+88h+IoStatusBlock], rax; IoStatusBlock
0x180001462  call    cs:__imp_NtDeviceIoControlFile
0x180001468  mov     ebx, eax
0x18000146a  cmp     eax, 103h
0x18000146f  jz      loc_1800015A0
0x180001475  mov     rcx, rdi; hObject
0x180001478  call    cs:__imp_CloseHandle
0x18000147e  test    ebx, ebx
0x180001480  js      short loc_1800014C1
0x180001482  cmp     ebx, 105h
0x180001488  jz      loc_180001577
0x18000148e  mov     eax, dword ptr [rsp+88h+var_30.Information]
0x180001492  mov     [rsi], eax
0x180001494  xor     eax, eax
0x180001496  mov     rdi, [rsp+88h+arg_10]
0x18000149e  mov     rbx, [rsp+88h+arg_0]
0x1800014a6  mov     rsi, [rsp+88h+arg_8]
0x1800014ae  mov     rbp, [rsp+88h+arg_18]
0x1800014b6  add     rsp, 70h
0x1800014ba  pop     r15
0x1800014bc  pop     r14
0x1800014be  pop     r12
0x1800014c0  retn
0x1800014c1  mov     eax, ebx
0x1800014c3  and     eax, 0C0000000h
0x1800014c8  cmp     eax, 0C0000000h
0x1800014cd  jnz     loc_180001577
0x1800014d3  mov     ecx, ebx; Status
0x1800014d5  call    cs:__imp_RtlNtStatusToDosError
0x1800014db  jmp     short loc_180001496
0x1800014dd  mov     [rsp+88h+InputBuffer], 0; hTemplateFile
0x1800014e6  lea     rcx, FileName; "\\\\.\\Nsi"
0x1800014ed  mov     [rsp+88h+IoControlCode], 40000000h; dwFlagsAndAttributes
0x1800014f5  xor     r9d, r9d; lpSecurityAttributes
0x1800014f8  xor     edx, edx; dwDesiredAccess
0x1800014fa  mov     dword ptr [rsp+88h+IoStatusBlock], 3; dwCreationDisposition
0x180001502  mov     r8d, 3; dwShareMode
0x180001508  call    cs:__imp_CreateFileW
0x18000150e  mov     rcx, rax; hObject
0x180001511  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180001515  jz      short loc_180001582
0x180001517  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000151e  lock cmpxchg cs:g_NsiAsyncDeviceHandle, rcx
0x180001527  jz      loc_1800013E1
0x18000152d  call    cs:__imp_CloseHandle
0x180001533  jmp     loc_1800013E1
0x180001538  mov     rcx, cs:g_NsiAsyncDeviceHandle; hDevice
0x18000153f  mov     r9d, r14d; nInBufferSize
0x180001542  mov     qword ptr [rsp+88h+InputBufferLength], rax; lpOverlapped
0x180001547  mov     r8, r15; lpInBuffer
0x18000154a  mov     [rsp+88h+InputBuffer], rsi; lpBytesReturned
0x18000154f  mov     edx, r12d; dwIoControlCode
0x180001552  mov     [rsp+88h+IoControlCode], ebx; nOutBufferSize
0x180001556  mov     [rsp+88h+IoStatusBlock], rbp; lpOutBuffer
0x18000155b  call    cs:__imp_DeviceIoControl
0x180001561  test    eax, eax
0x180001563  jnz     short loc_180001570
0x180001565  call    cs:__imp_GetLastError
0x18000156b  jmp     loc_18000149E
0x180001570  xor     eax, eax
0x180001572  jmp     loc_18000149E
0x180001577  mov     eax, dword ptr [rsp+88h+var_30.Information]
0x18000157b  mov     [rsi], eax
0x18000157d  jmp     loc_1800014D3
0x180001582  call    cs:__imp_GetLastError
0x180001588  test    eax, eax
0x18000158a  jz      loc_1800013E1
0x180001590  jmp     loc_1800014AE
0x180001595  call    cs:__imp_GetLastError
0x18000159b  jmp     loc_180001496
0x1800015a0  xor     r8d, r8d; Timeout
0x1800015a3  xor     edx, edx; Alertable
0x1800015a5  mov     rcx, rdi; Handle
0x1800015a8  call    cs:__imp_NtWaitForSingleObject
0x1800015ae  test    eax, eax
0x1800015b0  mov     ebx, eax
0x1800015b2  cmovns  ebx, dword ptr [rsp+88h+var_30]
0x1800015b7  jmp     loc_180001475
```
