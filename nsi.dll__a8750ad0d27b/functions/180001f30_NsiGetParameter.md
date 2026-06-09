# NsiGetParameter

- ea: `0x180001f30`
- end: `0x180002109`
- name: `NsiGetParameter`
- size: `473`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180001f30`

## import_xrefs

- `ntdll!NtDeviceIoControlFile` at `0x18000200a`
- `ntdll!NtDeviceIoControlFile` at `0x18000200a`
- `ntdll!NtWaitForSingleObject` at `0x1800020f6`
- `ntdll!NtWaitForSingleObject` at `0x1800020f6`
- `ntdll!RtlNtStatusToDosError` at `0x180002069`
- `ntdll!RtlNtStatusToDosError` at `0x180002069`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180002098`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180002098`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800020d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800020e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800020d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800020e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002020`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800020bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002020`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800020bd`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180001fb9`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180001fb9`

## pseudocode

```c
DWORD __fastcall NsiGetParameter(int a1, __int64 a2, int a3, __int64 a4, int a5, int a6, __int64 a7, ULONG a8, int a9)
{
  HANDLE EventA; // rax
  void *v10; // rbx
  int Status; // edi
  DWORD result; // eax
  HANDLE FileW; // rax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-31h] BYREF
  _QWORD InputBuffer[3]; // [rsp+60h] [rbp-21h] BYREF
  int v16; // [rsp+78h] [rbp-9h]
  int v17; // [rsp+7Ch] [rbp-5h]
  int v18; // [rsp+80h] [rbp-1h]
  int v19; // [rsp+84h] [rbp+3h]
  __int64 v20; // [rsp+88h] [rbp+7h]
  int v21; // [rsp+90h] [rbp+Fh]
  int v22; // [rsp+94h] [rbp+13h]
  int v23; // [rsp+98h] [rbp+17h]
  int v24; // [rsp+9Ch] [rbp+1Bh]
  __int64 v25; // [rsp+A0h] [rbp+1Fh]
  ULONG OutputBufferLength; // [rsp+A8h] [rbp+27h]
  int v27; // [rsp+ACh] [rbp+2Bh]

  v21 = a5;
  v23 = a6;
  v25 = a7;
  OutputBufferLength = a8;
  v27 = a9;
  InputBuffer[0] = 0;
  InputBuffer[1] = 0;
  v17 = 0;
  v22 = 0;
  v24 = 0;
  InputBuffer[2] = a2;
  v16 = a3;
  v20 = a4;
  v18 = a1;
  v19 = 0;
  IoStatusBlock = 0;
  if ( g_NsiAsyncDeviceHandle != (HANDLE)-1LL )
    goto LABEL_2;
  FileW = CreateFileW(L"\\\\.\\Nsi", 0, 3u, 0, 3u, 0x40000000u, 0);
  if ( FileW != (HANDLE)-1LL )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_NsiAsyncDeviceHandle, (signed __int64)FileW, -1) != -1 )
      CloseHandle(FileW);
LABEL_2:
    EventA = CreateEventA(0, 0, 0, 0);
    v10 = EventA;
    if ( !EventA )
      return GetLastError();
    Status = NtDeviceIoControlFile(
               g_NsiAsyncDeviceHandle,
               EventA,
               0,
               0,
               &IoStatusBlock,
               0x120007u,
               InputBuffer,
               0x50u,
               InputBuffer,
               OutputBufferLength);
    if ( Status == 259 )
    {
      Status = NtWaitForSingleObject(v10, 0, 0);
      if ( Status >= 0 )
        Status = IoStatusBlock.Status;
    }
    CloseHandle(v10);
    if ( Status < 0 )
    {
      if ( (Status & 0xC0000000) == 0xC0000000 )
        return RtlNtStatusToDosError(Status);
    }
    else if ( Status != 261 )
    {
      return 0;
    }
    OutputBufferLength = IoStatusBlock.Information;
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
0x180001f30  mov     [rsp-8+arg_10], rsi
0x180001f35  push    rbp
0x180001f36  lea     rbp, [rsp-2Fh]
0x180001f3b  sub     rsp, 0B0h
0x180001f42  mov     eax, [rbp+2Fh+arg_20]
0x180001f45  xor     esi, esi
0x180001f47  cmp     cs:g_NsiAsyncDeviceHandle, 0FFFFFFFFFFFFFFFFh
0x180001f4f  xorps   xmm0, xmm0
0x180001f52  mov     [rbp+2Fh+var_20], eax
0x180001f55  mov     eax, [rbp+2Fh+arg_28]
0x180001f58  mov     [rbp+2Fh+var_18], eax
0x180001f5b  mov     rax, [rbp+2Fh+arg_30]
0x180001f5f  mov     [rbp+2Fh+var_10], rax
0x180001f63  mov     eax, [rbp+2Fh+arg_38]
0x180001f66  mov     [rbp+2Fh+var_8], eax
0x180001f69  mov     eax, [rbp+2Fh+arg_40]
0x180001f6c  mov     [rbp+2Fh+var_4], eax
0x180001f6f  mov     [rbp+2Fh+var_50], rsi
0x180001f73  mov     [rbp+2Fh+var_48], rsi
0x180001f77  mov     [rbp+2Fh+var_34], esi
0x180001f7a  mov     [rbp+2Fh+var_1C], esi
0x180001f7d  mov     [rbp+2Fh+var_14], esi
0x180001f80  mov     [rbp+2Fh+var_40], rdx
0x180001f84  mov     [rbp+2Fh+var_38], r8d
0x180001f88  mov     [rbp+2Fh+var_28], r9
0x180001f8c  mov     [rbp+2Fh+var_30], ecx
0x180001f8f  mov     [rbp+2Fh+var_2C], esi
0x180001f92  movups  xmmword ptr [rbp+2Fh+var_60], xmm0
0x180001f96  jz      loc_180002071
0x180001f9c  mov     [rsp+0B0h+arg_0], rbx
0x180001fa4  xor     r9d, r9d; lpName
0x180001fa7  mov     [rsp+0B0h+arg_8], rdi
0x180001faf  xor     r8d, r8d; bInitialState
0x180001fb2  mov     edi, [rbp+2Fh+var_8]
0x180001fb5  xor     edx, edx; bManualReset
0x180001fb7  xor     ecx, ecx; lpEventAttributes
0x180001fb9  call    cs:__imp_CreateEventA
0x180001fbf  mov     rbx, rax
0x180001fc2  test    rax, rax
0x180001fc5  jz      loc_1800020E3
0x180001fcb  mov     rcx, cs:g_NsiAsyncDeviceHandle; FileHandle
0x180001fd2  lea     rax, [rbp+2Fh+var_50]
0x180001fd6  mov     [rsp+0B0h+OutputBufferLength], edi; OutputBufferLength
0x180001fda  xor     r9d, r9d; ApcContext
0x180001fdd  mov     [rsp+0B0h+OutputBuffer], rax; OutputBuffer
0x180001fe2  xor     r8d, r8d; ApcRoutine
0x180001fe5  mov     [rsp+0B0h+InputBufferLength], 50h ; 'P'; InputBufferLength
0x180001fed  lea     rax, [rbp+2Fh+var_50]
0x180001ff1  mov     [rsp+0B0h+InputBuffer], rax; InputBuffer
0x180001ff6  mov     rdx, rbx; Event
0x180001ff9  lea     rax, [rbp+2Fh+var_60]
0x180001ffd  mov     [rsp+0B0h+IoControlCode], 120007h; IoControlCode
0x180002005  mov     [rsp+0B0h+IoStatusBlock], rax; IoStatusBlock
0x18000200a  call    cs:__imp_NtDeviceIoControlFile
0x180002010  mov     edi, eax
0x180002012  cmp     eax, 103h
0x180002017  jz      loc_1800020EE
0x18000201d  mov     rcx, rbx; hObject
0x180002020  call    cs:__imp_CloseHandle
0x180002026  test    edi, edi
0x180002028  js      short loc_180002059
0x18000202a  cmp     edi, 105h
0x180002030  jz      loc_1800020C8
0x180002036  mov     eax, esi
0x180002038  mov     rbx, [rsp+0B0h+arg_0]
0x180002040  mov     rdi, [rsp+0B0h+arg_8]
0x180002048  mov     rsi, [rsp+0B0h+arg_10]
0x180002050  add     rsp, 0B0h
0x180002057  pop     rbp
0x180002058  retn
0x180002059  mov     eax, edi
0x18000205b  and     eax, 0C0000000h
0x180002060  cmp     eax, 0C0000000h
0x180002065  jnz     short loc_1800020C8
0x180002067  mov     ecx, edi; Status
0x180002069  call    cs:__imp_RtlNtStatusToDosError
0x18000206f  jmp     short loc_180002038
0x180002071  mov     [rsp+0B0h+InputBuffer], rsi; hTemplateFile
0x180002076  lea     rcx, FileName; "\\\\.\\Nsi"
0x18000207d  mov     [rsp+0B0h+IoControlCode], 40000000h; dwFlagsAndAttributes
0x180002085  xor     r9d, r9d; lpSecurityAttributes
0x180002088  xor     edx, edx; dwDesiredAccess
0x18000208a  mov     dword ptr [rsp+0B0h+IoStatusBlock], 3; dwCreationDisposition
0x180002092  mov     r8d, 3; dwShareMode
0x180002098  call    cs:__imp_CreateFileW
0x18000209e  mov     rcx, rax; hObject
0x1800020a1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800020a5  jz      short loc_1800020D0
0x1800020a7  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800020ae  lock cmpxchg cs:g_NsiAsyncDeviceHandle, rcx
0x1800020b7  jz      loc_180001F9C
0x1800020bd  call    cs:__imp_CloseHandle
0x1800020c3  jmp     loc_180001F9C
0x1800020c8  mov     eax, dword ptr [rbp+2Fh+var_60.Information]
0x1800020cb  mov     [rbp+2Fh+var_8], eax
0x1800020ce  jmp     short loc_180002067
0x1800020d0  call    cs:__imp_GetLastError
0x1800020d6  test    eax, eax
0x1800020d8  jz      loc_180001F9C
0x1800020de  jmp     loc_180002048
0x1800020e3  call    cs:__imp_GetLastError
0x1800020e9  jmp     loc_180002038
0x1800020ee  xor     r8d, r8d; Timeout
0x1800020f1  xor     edx, edx; Alertable
0x1800020f3  mov     rcx, rbx; Handle
0x1800020f6  call    cs:__imp_NtWaitForSingleObject
0x1800020fc  test    eax, eax
0x1800020fe  mov     edi, eax
0x180002100  cmovns  edi, dword ptr [rbp+2Fh+var_60]
0x180002104  jmp     loc_18000201D
```
