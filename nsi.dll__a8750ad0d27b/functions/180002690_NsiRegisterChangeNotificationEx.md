# NsiRegisterChangeNotificationEx

- ea: `0x180002690`
- end: `0x1800027f2`
- name: `NsiRegisterChangeNotificationEx`
- size: `354`
- prototype: `ULONG __fastcall(_QWORD *OutputBuffer)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180002fd0`

## callees

- `0x180002690`

## import_xrefs

- `ntdll!NtDeviceIoControlFile` at `0x180002717`
- `ntdll!NtDeviceIoControlFile` at `0x180002717`
- `ntdll!NtWaitForSingleObject` at `0x1800027de`
- `ntdll!NtWaitForSingleObject` at `0x1800027de`
- `ntdll!RtlNtStatusToDosError` at `0x18000274e`
- `ntdll!RtlNtStatusToDosError` at `0x18000274e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180002781`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180002781`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800027b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800027cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800027b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800027cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000272d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800027a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000272d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800027a6`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800026c9`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800026c9`

## pseudocode

```c
ULONG __fastcall NsiRegisterChangeNotificationEx(_QWORD *OutputBuffer)
{
  HANDLE EventA; // rdi
  int Status; // ebx
  ULONG result; // eax
  HANDLE FileW; // rax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-18h] BYREF

  if ( OutputBuffer[3] )
    return 87;
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
  EventA = CreateEventA(0, 0, 0, 0);
  if ( !EventA )
    return GetLastError();
  Status = NtDeviceIoControlFile(
             g_NsiAsyncDeviceHandle,
             EventA,
             0,
             0,
             &IoStatusBlock,
             0x12001Fu,
             OutputBuffer,
             0x48u,
             OutputBuffer,
             0x48u);
  if ( Status == 259 )
  {
    Status = NtWaitForSingleObject(EventA, 0, 0);
    if ( Status >= 0 )
      Status = IoStatusBlock.Status;
  }
  CloseHandle(EventA);
  if ( Status < 0 || Status == 261 )
    return RtlNtStatusToDosError(Status);
  else
    return 0;
}

```

## disassembly

```asm
0x180002690  push    rbx
0x180002692  sub     rsp, 60h
0x180002696  cmp     qword ptr [rcx+18h], 0
0x18000269b  mov     rbx, rcx
0x18000269e  jnz     loc_1800027C1
0x1800026a4  cmp     cs:g_NsiAsyncDeviceHandle, 0FFFFFFFFFFFFFFFFh
0x1800026ac  xorps   xmm0, xmm0
0x1800026af  movups  xmmword ptr [rsp+68h+var_18], xmm0
0x1800026b4  jz      loc_180002756
0x1800026ba  xor     r9d, r9d; lpName
0x1800026bd  mov     [rsp+68h+arg_8], rdi
0x1800026c2  xor     r8d, r8d; bInitialState
0x1800026c5  xor     edx, edx; bManualReset
0x1800026c7  xor     ecx, ecx; lpEventAttributes
0x1800026c9  call    cs:__imp_CreateEventA
0x1800026cf  mov     rdi, rax
0x1800026d2  test    rax, rax
0x1800026d5  jz      loc_1800027CB
0x1800026db  mov     rcx, cs:g_NsiAsyncDeviceHandle; FileHandle
0x1800026e2  lea     rax, [rsp+68h+var_18]
0x1800026e7  mov     [rsp+68h+OutputBufferLength], 48h ; 'H'; OutputBufferLength
0x1800026ef  xor     r9d, r9d; ApcContext
0x1800026f2  mov     [rsp+68h+OutputBuffer], rbx; OutputBuffer
0x1800026f7  xor     r8d, r8d; ApcRoutine
0x1800026fa  mov     [rsp+68h+InputBufferLength], 48h ; 'H'; InputBufferLength
0x180002702  mov     rdx, rdi; Event
0x180002705  mov     [rsp+68h+InputBuffer], rbx; InputBuffer
0x18000270a  mov     [rsp+68h+IoControlCode], 12001Fh; IoControlCode
0x180002712  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x180002717  call    cs:__imp_NtDeviceIoControlFile
0x18000271d  mov     ebx, eax
0x18000271f  cmp     eax, 103h
0x180002724  jz      loc_1800027D6
0x18000272a  mov     rcx, rdi; hObject
0x18000272d  call    cs:__imp_CloseHandle
0x180002733  test    ebx, ebx
0x180002735  js      short loc_18000274C
0x180002737  cmp     ebx, 105h
0x18000273d  jz      short loc_18000274C
0x18000273f  xor     eax, eax
0x180002741  mov     rdi, [rsp+68h+arg_8]
0x180002746  add     rsp, 60h
0x18000274a  pop     rbx
0x18000274b  retn
0x18000274c  mov     ecx, ebx; Status
0x18000274e  call    cs:__imp_RtlNtStatusToDosError
0x180002754  jmp     short loc_180002741
0x180002756  mov     [rsp+68h+InputBuffer], 0; hTemplateFile
0x18000275f  lea     rcx, FileName; "\\\\.\\Nsi"
0x180002766  mov     [rsp+68h+IoControlCode], 40000000h; dwFlagsAndAttributes
0x18000276e  xor     r9d, r9d; lpSecurityAttributes
0x180002771  xor     edx, edx; dwDesiredAccess
0x180002773  mov     dword ptr [rsp+68h+IoStatusBlock], 3; dwCreationDisposition
0x18000277b  mov     r8d, 3; dwShareMode
0x180002781  call    cs:__imp_CreateFileW
0x180002787  mov     rcx, rax; hObject
0x18000278a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000278e  jz      short loc_1800027B1
0x180002790  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180002797  lock cmpxchg cs:g_NsiAsyncDeviceHandle, rcx
0x1800027a0  jz      loc_1800026BA
0x1800027a6  call    cs:__imp_CloseHandle
0x1800027ac  jmp     loc_1800026BA
0x1800027b1  call    cs:__imp_GetLastError
0x1800027b7  test    eax, eax
0x1800027b9  jz      loc_1800026BA
0x1800027bf  jmp     short loc_180002746
0x1800027c1  mov     eax, 57h ; 'W'
0x1800027c6  jmp     loc_180002746
0x1800027cb  call    cs:__imp_GetLastError
0x1800027d1  jmp     loc_180002741
0x1800027d6  xor     r8d, r8d; Timeout
0x1800027d9  xor     edx, edx; Alertable
0x1800027db  mov     rcx, rdi; Handle
0x1800027de  call    cs:__imp_NtWaitForSingleObject
0x1800027e4  test    eax, eax
0x1800027e6  mov     ebx, eax
0x1800027e8  cmovns  ebx, dword ptr [rsp+68h+var_18]
0x1800027ed  jmp     loc_18000272A
```
