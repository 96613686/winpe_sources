# Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CCompletionPortIo>::InternalDeviceIoControl(void *,ulong,void *,ulong,void *,ulong,ulong *)

- ea: `0x1800107bc`
- end: `0x1800108f9`
- name: `?InternalDeviceIoControl@?$CFileChannel@VCCompletionPortIo@details@TP@Utils@Rdp@@@Driver@Stack@Rdp@@CAHPEAXK0K0KPEAK@Z`
- size: `317`
- prototype: `__int64 __usercall@<rax>(HANDLE FileHandle@<rcx>, PVOID, ULONG, __int64)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e45c`
- `0x18000e5fc`
- `0x18000e794`
- `0x180011634`

## callees

- `0x1800107bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800108dc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800108dc`
- `ntdll!NtWaitForSingleObject` at `0x180010890`
- `ntdll!NtWaitForSingleObject` at `0x180010890`
- `ntdll!NtClose` at `0x1800108c8`
- `ntdll!NtClose` at `0x1800108c8`
- `ntdll!RtlNtStatusToDosError` at `0x1800108d4`
- `ntdll!RtlNtStatusToDosError` at `0x1800108d4`
- `ntdll!NtDeviceIoControlFile` at `0x180010873`
- `ntdll!NtDeviceIoControlFile` at `0x180010873`
- `ntdll!NtCreateEvent` at `0x18001081a`
- `ntdll!NtCreateEvent` at `0x18001081a`

## pseudocode

```c
__int64 __fastcall Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CCompletionPortIo>::InternalDeviceIoControl(
        HANDLE FileHandle,
        __int64 a2,
        void *a3,
        ULONG a4,
        PVOID OutputBuffer,
        ULONG OutputBufferLength,
        _DWORD *a7)
{
  int Status; // ebx
  DWORD v11; // eax
  HANDLE Event; // [rsp+58h] [rbp-70h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-68h] BYREF
  struct _OBJECT_ATTRIBUTES v15; // [rsp+70h] [rbp-58h] BYREF

  *(_QWORD *)&v15.Length = 48;
  Event = 0;
  memset(&v15.RootDirectory, 0, 40);
  Status = NtCreateEvent(&Event, 0x1F0003u, &v15, NotificationEvent, 0);
  if ( Status >= 0 )
  {
    IoStatusBlock = 0;
    Status = NtDeviceIoControlFile(
               FileHandle,
               Event,
               0,
               0,
               &IoStatusBlock,
               0x80000040,
               a3,
               a4,
               OutputBuffer,
               OutputBufferLength);
    if ( Status == 259 )
    {
      Status = NtWaitForSingleObject(Event, 0, 0);
      if ( Status >= 0 )
      {
        Status = IoStatusBlock.Status;
        if ( a7 )
          *a7 = IoStatusBlock.Information;
      }
    }
    NtClose(Event);
  }
  if ( Status >= 0 )
    return 1;
  v11 = RtlNtStatusToDosError(Status);
  SetLastError(v11);
  return 0;
}

```

## disassembly

```asm
0x1800107bc  mov     rax, rsp
0x1800107bf  push    rbx
0x1800107c0  push    rsi
0x1800107c1  push    r14
0x1800107c3  push    r15
0x1800107c5  sub     rsp, 0A8h
0x1800107cc  mov     esi, r9d
0x1800107cf  mov     r14, r8
0x1800107d2  mov     r15, rcx
0x1800107d5  mov     qword ptr [rax-58h], 30h ; '0'
0x1800107dd  mov     qword ptr [rax-40h], 0
0x1800107e5  mov     qword ptr [rax-70h], 0
0x1800107ed  mov     qword ptr [rax-50h], 0
0x1800107f5  mov     qword ptr [rax-48h], 0
0x1800107fd  xorps   xmm0, xmm0
0x180010800  movdqu  xmmword ptr [rax-38h], xmm0
0x180010805  mov     [rsp+0C8h+InitialState], 0; InitialState
0x18001080a  xor     r9d, r9d; EventType
0x18001080d  lea     r8, [rax-58h]; ObjectAttributes
0x180010811  mov     edx, 1F0003h; DesiredAccess
0x180010816  lea     rcx, [rax-70h]; EventHandle
0x18001081a  call    cs:__imp_NtCreateEvent
0x180010820  mov     ebx, eax
0x180010822  test    eax, eax
0x180010824  js      loc_1800108CE
0x18001082a  xorps   xmm0, xmm0
0x18001082d  movups  xmmword ptr [rsp+0C8h+IoStatusBlock], xmm0
0x180010832  mov     eax, [rsp+0C8h+arg_28]
0x180010839  mov     [rsp+0C8h+OutputBufferLength], eax; OutputBufferLength
0x18001083d  mov     rax, [rsp+0C8h+arg_20]
0x180010845  mov     [rsp+0C8h+OutputBuffer], rax; OutputBuffer
0x18001084a  mov     [rsp+0C8h+InputBufferLength], esi; InputBufferLength
0x18001084e  mov     [rsp+0C8h+InputBuffer], r14; InputBuffer
0x180010853  mov     [rsp+0C8h+IoControlCode], 80000040h; IoControlCode
0x18001085b  lea     rax, [rsp+0C8h+IoStatusBlock]
0x180010860  mov     qword ptr [rsp+0C8h+InitialState], rax; IoStatusBlock
0x180010865  xor     r9d, r9d; ApcContext
0x180010868  xor     r8d, r8d; ApcRoutine
0x18001086b  mov     rdx, [rsp+0C8h+Event]; Event
0x180010870  mov     rcx, r15; FileHandle
0x180010873  call    cs:__imp_NtDeviceIoControlFile
0x180010879  mov     ebx, eax
0x18001087b  mov     [rsp+0C8h+var_78], eax
0x18001087f  cmp     eax, 103h
0x180010884  jnz     short loc_1800108BB
0x180010886  xor     r8d, r8d; Timeout
0x180010889  xor     edx, edx; Alertable
0x18001088b  mov     rcx, [rsp+0C8h+Event]; Handle
0x180010890  call    cs:__imp_NtWaitForSingleObject
0x180010896  mov     ebx, eax
0x180010898  mov     [rsp+0C8h+var_78], eax
0x18001089c  test    eax, eax
0x18001089e  js      short loc_1800108BB
0x1800108a0  mov     ebx, dword ptr [rsp+0C8h+IoStatusBlock]
0x1800108a4  mov     [rsp+0C8h+var_78], ebx
0x1800108a8  mov     rcx, [rsp+0C8h+arg_30]
0x1800108b0  test    rcx, rcx
0x1800108b3  jz      short loc_1800108BB
0x1800108b5  mov     eax, dword ptr [rsp+0C8h+IoStatusBlock.Information]
0x1800108b9  mov     [rcx], eax
0x1800108bb  jmp     short loc_1800108C3
0x1800108bd  mov     ebx, eax
0x1800108bf  mov     [rsp+0C8h+var_78], eax
0x1800108c3  mov     rcx, [rsp+0C8h+Event]; Handle
0x1800108c8  call    cs:__imp_NtClose
0x1800108ce  test    ebx, ebx
0x1800108d0  jns     short loc_1800108E6
0x1800108d2  mov     ecx, ebx; Status
0x1800108d4  call    cs:__imp_RtlNtStatusToDosError
0x1800108da  mov     ecx, eax; dwErrCode
0x1800108dc  call    cs:__imp_SetLastError
0x1800108e2  xor     eax, eax
0x1800108e4  jmp     short loc_1800108EB
0x1800108e6  mov     eax, 1
0x1800108eb  add     rsp, 0A8h
0x1800108f2  pop     r15
0x1800108f4  pop     r14
0x1800108f6  pop     rsi
0x1800108f7  pop     rbx
0x1800108f8  retn
0x180028ea0  push    rbp
0x180028ea2  sub     rsp, 50h
0x180028ea6  mov     rbp, rdx
0x180028ea9  mov     rax, [rcx]
0x180028eac  xor     ecx, ecx
0x180028eae  cmp     dword ptr [rax], 0C00000FDh
0x180028eb4  setnz   cl
0x180028eb7  mov     eax, ecx
0x180028eb9  add     rsp, 50h
0x180028ebd  pop     rbp
0x180028ebe  retn
```
