# Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CThreadPoolIo<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&Rdp::Utils::TP::details::DestroyThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>>>>::InternalDeviceIoControl(void *,ulong,void *,ulong,void *,ulong,ulong *)

- ea: `0x18001b970`
- end: `0x18001baa8`
- name: `?InternalDeviceIoControl@?$CFileChannel@V?$CThreadPoolIo@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_IO@@P6AXPEAU1@@Z$1?DestroyThreadpoolIo@details@TP@Utils@Rdp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@TP@Utils@Rdp@@@Driver@Stack@Rdp@@CAHPEAXK0K0KPEAK@Z`
- size: `312`
- prototype: `__int64 __usercall@<rax>(HANDLE FileHandle@<rcx>, HANDLE Event)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x18001b510`

## callees

- `0x18001b970`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ba83`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ba83`
- `ntdll!NtWaitForSingleObject` at `0x18001ba48`
- `ntdll!NtWaitForSingleObject` at `0x18001ba48`
- `ntdll!NtClose` at `0x18001ba6f`
- `ntdll!NtClose` at `0x18001ba6f`
- `ntdll!RtlNtStatusToDosError` at `0x18001ba7b`
- `ntdll!RtlNtStatusToDosError` at `0x18001ba7b`
- `ntdll!NtDeviceIoControlFile` at `0x18001ba28`
- `ntdll!NtDeviceIoControlFile` at `0x18001ba28`
- `ntdll!NtCreateEvent` at `0x18001b9cf`
- `ntdll!NtCreateEvent` at `0x18001b9cf`

## pseudocode

```c
__int64 __fastcall Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CThreadPoolIo<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&void Rdp::Utils::TP::details::DestroyThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>>>>::InternalDeviceIoControl(
        HANDLE FileHandle,
        __int64 a2,
        void *a3,
        __int64 a4,
        HANDLE Event)
{
  int Status; // ebx
  DWORD v8; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp-50h] BYREF
  struct _OBJECT_ATTRIBUTES v11; // [rsp+68h] [rbp-40h] BYREF

  *(_QWORD *)&v11.Length = 48;
  Event = 0;
  memset(&v11.RootDirectory, 0, 40);
  Status = NtCreateEvent(&Event, 0x1F0003u, &v11, NotificationEvent, 0);
  if ( Status >= 0 )
  {
    IoStatusBlock = 0;
    Status = NtDeviceIoControlFile(FileHandle, Event, 0, 0, &IoStatusBlock, 0x80000040, a3, 0x40u, 0, 0);
    if ( Status == 259 )
    {
      Status = NtWaitForSingleObject(Event, 0, 0);
      if ( Status >= 0 )
        Status = IoStatusBlock.Status;
    }
    NtClose(Event);
  }
  if ( Status >= 0 )
    return 1;
  v8 = RtlNtStatusToDosError(Status);
  SetLastError(v8);
  return 0;
}

```

## disassembly

```asm
0x18001b970  mov     rax, rsp
0x18001b973  mov     [rax+8], rbx
0x18001b977  mov     [rax+10h], rsi
0x18001b97b  push    r14
0x18001b97d  sub     rsp, 0A0h
0x18001b984  mov     rsi, r8
0x18001b987  mov     r14, rcx
0x18001b98a  mov     qword ptr [rax-40h], 30h ; '0'
0x18001b992  mov     qword ptr [rax-28h], 0
0x18001b99a  mov     qword ptr [rax+28h], 0
0x18001b9a2  mov     qword ptr [rax-38h], 0
0x18001b9aa  mov     qword ptr [rax-30h], 0
0x18001b9b2  xorps   xmm0, xmm0
0x18001b9b5  movdqu  xmmword ptr [rax-20h], xmm0
0x18001b9ba  mov     [rsp+0A8h+InitialState], 0; InitialState
0x18001b9bf  xor     r9d, r9d; EventType
0x18001b9c2  lea     r8, [rax-40h]; ObjectAttributes
0x18001b9c6  mov     edx, 1F0003h; DesiredAccess
0x18001b9cb  lea     rcx, [rax+28h]; EventHandle
0x18001b9cf  call    cs:__imp_NtCreateEvent
0x18001b9d5  mov     ebx, eax
0x18001b9d7  test    eax, eax
0x18001b9d9  js      loc_18001BA75
0x18001b9df  xorps   xmm0, xmm0
0x18001b9e2  movups  xmmword ptr [rsp+0A8h+IoStatusBlock], xmm0
0x18001b9e7  mov     [rsp+0A8h+OutputBufferLength], 0; OutputBufferLength
0x18001b9ef  mov     [rsp+0A8h+OutputBuffer], 0; OutputBuffer
0x18001b9f8  mov     [rsp+0A8h+InputBufferLength], 40h ; '@'; InputBufferLength
0x18001ba00  mov     [rsp+0A8h+InputBuffer], rsi; InputBuffer
0x18001ba05  mov     [rsp+0A8h+IoControlCode], 80000040h; IoControlCode
0x18001ba0d  lea     rax, [rsp+0A8h+IoStatusBlock]
0x18001ba12  mov     qword ptr [rsp+0A8h+InitialState], rax; IoStatusBlock
0x18001ba17  xor     r9d, r9d; ApcContext
0x18001ba1a  xor     r8d, r8d; ApcRoutine
0x18001ba1d  mov     rdx, [rsp+0A8h+Event]; Event
0x18001ba25  mov     rcx, r14; FileHandle
0x18001ba28  call    cs:__imp_NtDeviceIoControlFile
0x18001ba2e  mov     ebx, eax
0x18001ba30  mov     [rsp+0A8h+var_58], eax
0x18001ba34  cmp     eax, 103h
0x18001ba39  jnz     short loc_18001BA5F
0x18001ba3b  xor     r8d, r8d; Timeout
0x18001ba3e  xor     edx, edx; Alertable
0x18001ba40  mov     rcx, [rsp+0A8h+Event]; Handle
0x18001ba48  call    cs:__imp_NtWaitForSingleObject
0x18001ba4e  mov     ebx, eax
0x18001ba50  mov     [rsp+0A8h+var_58], eax
0x18001ba54  test    eax, eax
0x18001ba56  cmovns  ebx, dword ptr [rsp+0A8h+IoStatusBlock]
0x18001ba5b  mov     [rsp+0A8h+var_58], ebx
0x18001ba5f  jmp     short loc_18001BA67
0x18001ba61  mov     ebx, eax
0x18001ba63  mov     [rsp+0A8h+var_58], eax
0x18001ba67  mov     rcx, [rsp+0A8h+Event]; Handle
0x18001ba6f  call    cs:__imp_NtClose
0x18001ba75  test    ebx, ebx
0x18001ba77  jns     short loc_18001BA8D
0x18001ba79  mov     ecx, ebx; Status
0x18001ba7b  call    cs:__imp_RtlNtStatusToDosError
0x18001ba81  mov     ecx, eax; dwErrCode
0x18001ba83  call    cs:__imp_SetLastError
0x18001ba89  xor     eax, eax
0x18001ba8b  jmp     short loc_18001BA92
0x18001ba8d  mov     eax, 1
0x18001ba92  lea     r11, [rsp+0A8h+var_8]
0x18001ba9a  mov     rbx, [r11+10h]
0x18001ba9e  mov     rsi, [r11+18h]
0x18001baa2  mov     rsp, r11
0x18001baa5  pop     r14
0x18001baa7  retn
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
