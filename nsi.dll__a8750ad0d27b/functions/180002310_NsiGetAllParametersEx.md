# NsiGetAllParametersEx

- ea: `0x180002310`
- end: `0x18000245d`
- name: `NsiGetAllParametersEx`
- size: `333`
- prototype: `__int64 __fastcall(PVOID OutputBuffer)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180002310`

## import_xrefs

- `ntdll!NtDeviceIoControlFile` at `0x18000238c`
- `ntdll!NtDeviceIoControlFile` at `0x18000238c`
- `ntdll!NtWaitForSingleObject` at `0x180002449`
- `ntdll!NtWaitForSingleObject` at `0x180002449`
- `ntdll!RtlNtStatusToDosError` at `0x1800023c3`
- `ntdll!RtlNtStatusToDosError` at `0x1800023c3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800023f6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800023f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002426`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002436`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002426`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002436`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800023a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000241b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800023a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000241b`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000233e`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000233e`

## pseudocode

```c
ULONG __fastcall NsiGetAllParametersEx(PVOID OutputBuffer)
{
  HANDLE EventA; // rbx
  int Status; // edi
  ULONG result; // eax
  HANDLE FileW; // rax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-18h] BYREF

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
             0x12000Fu,
             OutputBuffer,
             0x68u,
             OutputBuffer,
             0x68u);
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
0x180002310  push    rdi
0x180002312  sub     rsp, 60h
0x180002316  cmp     cs:g_NsiAsyncDeviceHandle, 0FFFFFFFFFFFFFFFFh
0x18000231e  xorps   xmm0, xmm0
0x180002321  movups  xmmword ptr [rsp+68h+var_18], xmm0
0x180002326  mov     rdi, rcx
0x180002329  jz      loc_1800023CB
0x18000232f  xor     r9d, r9d; lpName
0x180002332  mov     [rsp+68h+arg_0], rbx
0x180002337  xor     r8d, r8d; bInitialState
0x18000233a  xor     edx, edx; bManualReset
0x18000233c  xor     ecx, ecx; lpEventAttributes
0x18000233e  call    cs:__imp_CreateEventA
0x180002344  mov     rbx, rax
0x180002347  test    rax, rax
0x18000234a  jz      loc_180002436
0x180002350  mov     rcx, cs:g_NsiAsyncDeviceHandle; FileHandle
0x180002357  lea     rax, [rsp+68h+var_18]
0x18000235c  mov     [rsp+68h+OutputBufferLength], 68h ; 'h'; OutputBufferLength
0x180002364  xor     r9d, r9d; ApcContext
0x180002367  mov     [rsp+68h+OutputBuffer], rdi; OutputBuffer
0x18000236c  xor     r8d, r8d; ApcRoutine
0x18000236f  mov     [rsp+68h+InputBufferLength], 68h ; 'h'; InputBufferLength
0x180002377  mov     rdx, rbx; Event
0x18000237a  mov     [rsp+68h+InputBuffer], rdi; InputBuffer
0x18000237f  mov     [rsp+68h+IoControlCode], 12000Fh; IoControlCode
0x180002387  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x18000238c  call    cs:__imp_NtDeviceIoControlFile
0x180002392  mov     edi, eax
0x180002394  cmp     eax, 103h
0x180002399  jz      loc_180002441
0x18000239f  mov     rcx, rbx; hObject
0x1800023a2  call    cs:__imp_CloseHandle
0x1800023a8  test    edi, edi
0x1800023aa  js      short loc_1800023C1
0x1800023ac  cmp     edi, 105h
0x1800023b2  jz      short loc_1800023C1
0x1800023b4  xor     eax, eax
0x1800023b6  mov     rbx, [rsp+68h+arg_0]
0x1800023bb  add     rsp, 60h
0x1800023bf  pop     rdi
0x1800023c0  retn
0x1800023c1  mov     ecx, edi; Status
0x1800023c3  call    cs:__imp_RtlNtStatusToDosError
0x1800023c9  jmp     short loc_1800023B6
0x1800023cb  mov     [rsp+68h+InputBuffer], 0; hTemplateFile
0x1800023d4  lea     rcx, FileName; "\\\\.\\Nsi"
0x1800023db  mov     [rsp+68h+IoControlCode], 40000000h; dwFlagsAndAttributes
0x1800023e3  xor     r9d, r9d; lpSecurityAttributes
0x1800023e6  xor     edx, edx; dwDesiredAccess
0x1800023e8  mov     dword ptr [rsp+68h+IoStatusBlock], 3; dwCreationDisposition
0x1800023f0  mov     r8d, 3; dwShareMode
0x1800023f6  call    cs:__imp_CreateFileW
0x1800023fc  mov     rcx, rax; hObject
0x1800023ff  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180002403  jz      short loc_180002426
0x180002405  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000240c  lock cmpxchg cs:g_NsiAsyncDeviceHandle, rcx
0x180002415  jz      loc_18000232F
0x18000241b  call    cs:__imp_CloseHandle
0x180002421  jmp     loc_18000232F
0x180002426  call    cs:__imp_GetLastError
0x18000242c  test    eax, eax
0x18000242e  jz      loc_18000232F
0x180002434  jmp     short loc_1800023BB
0x180002436  call    cs:__imp_GetLastError
0x18000243c  jmp     loc_1800023B6
0x180002441  xor     r8d, r8d; Timeout
0x180002444  xor     edx, edx; Alertable
0x180002446  mov     rcx, rbx; Handle
0x180002449  call    cs:__imp_NtWaitForSingleObject
0x18000244f  test    eax, eax
0x180002451  mov     edi, eax
0x180002453  cmovns  edi, dword ptr [rsp+68h+var_18]
0x180002458  jmp     loc_18000239F
```
