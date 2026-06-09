# RxVmbusSendTransportNegotiateMessage

- ea: `0x140055c64`
- end: `0x140055dec`
- name: `RxVmbusSendTransportNegotiateMessage`
- size: `392`
- prototype: `__int64 __fastcall(HANDLE FileHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400554d0`

## callees

- `0x14003838c`
- `0x140055c64`
- `0x140059dc0`

## import_xrefs

- `ntoskrnl!ZwCreateEvent` at `0x140055cde`
- `ntoskrnl!ZwCreateEvent` at `0x140055cde`
- `ntoskrnl!ZwClose` at `0x140055dbc`
- `ntoskrnl!ZwClose` at `0x140055dbc`
- `ntoskrnl!ZwWaitForSingleObject` at `0x140055d65`
- `ntoskrnl!ZwWaitForSingleObject` at `0x140055d65`
- `ntoskrnl!ZwWriteFile` at `0x140055d4a`
- `ntoskrnl!ZwWriteFile` at `0x140055d4a`

## pseudocode

```c
__int64 __fastcall RxVmbusSendTransportNegotiateMessage(HANDLE FileHandle)
{
  NTSTATUS Status; // ebx
  void *EventHandle; // [rsp+50h] [rbp-19h] BYREF
  LARGE_INTEGER ByteOffset; // [rsp+58h] [rbp-11h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp+7h] BYREF
  __int64 Buffer; // [rsp+A0h] [rbp+37h] BYREF
  int v9; // [rsp+A8h] [rbp+3Fh]

  ByteOffset.QuadPart = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 512;
  EventHandle = (void *)-1LL;
  Buffer = 0;
  v9 = 0;
  ObjectAttributes.RootDirectory = 0;
  IoStatusBlock = 0;
  ObjectAttributes.ObjectName = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  Status = ZwCreateEvent(&EventHandle, 0x1F0003u, &ObjectAttributes, SynchronizationEvent, 0);
  if ( Status < 0
    || (Buffer = 0x108000001LL,
        v9 = 1,
        ByteOffset.QuadPart = 0,
        Status = ZwWriteFile(FileHandle, EventHandle, 0, 0, &IoStatusBlock, &Buffer, 0xCu, &ByteOffset, 0),
        Status < 0)
    || (ZwWaitForSingleObject(EventHandle, 0, 0), Status = IoStatusBlock.Status, IoStatusBlock.Status < 0) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        10,
        &WPP_1aa408cf43a53df084d1ad3a10e953fa_Traceguids,
        (unsigned int)Status);
    }
  }
  if ( EventHandle != (void *)-1LL )
    ZwClose(EventHandle);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x140055c64  mov     [rsp-8+arg_8], rbx
0x140055c69  mov     [rsp-8+arg_10], rdi
0x140055c6e  push    rbp
0x140055c6f  lea     rbp, [rsp-57h]
0x140055c74  sub     rsp, 0C0h
0x140055c7b  mov     rax, cs:__security_cookie
0x140055c82  xor     rax, rsp
0x140055c85  mov     [rbp+57h+var_10], rax
0x140055c89  xor     eax, eax
0x140055c8b  mov     qword ptr [rbp+57h+var_68], 0
0x140055c93  xorps   xmm0, xmm0
0x140055c96  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140055c9e  mov     rdi, rcx
0x140055ca1  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 200h
0x140055ca9  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140055cad  mov     [rbp+57h+EventHandle], 0FFFFFFFFFFFFFFFFh
0x140055cb5  lea     r9d, [rax+1]; EventType
0x140055cb9  mov     [rbp+57h+var_20], rax
0x140055cbd  mov     edx, 1F0003h; DesiredAccess
0x140055cc2  mov     [rbp+57h+var_18], eax
0x140055cc5  lea     rcx, [rbp+57h+EventHandle]; EventHandle
0x140055cc9  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x140055ccd  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140055cd1  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140055cd5  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140055cda  mov     [rsp+0C0h+InitialState], al; InitialState
0x140055cde  call    cs:__imp_ZwCreateEvent
0x140055ce5  nop     dword ptr [rax+rax+00h]
0x140055cea  mov     ebx, eax
0x140055cec  test    eax, eax
0x140055cee  js      loc_140055D78
0x140055cf4  mov     rdx, [rbp+57h+EventHandle]; Event
0x140055cf8  lea     rax, [rbp+57h+var_68]
0x140055cfc  mov     [rsp+0C0h+Key], 0; Key
0x140055d05  xor     r9d, r9d; ApcContext
0x140055d08  mov     [rsp+0C0h+ByteOffset], rax; ByteOffset
0x140055d0d  xor     r8d, r8d; ApcRoutine
0x140055d10  lea     rax, [rbp+57h+var_20]
0x140055d14  mov     [rsp+0C0h+Length], 0Ch; Length
0x140055d1c  mov     [rsp+0C0h+Buffer], rax; Buffer
0x140055d21  mov     rcx, rdi; FileHandle
0x140055d24  lea     rax, [rbp+57h+IoStatusBlock]
0x140055d28  mov     dword ptr [rbp+57h+var_20], 8000001h
0x140055d2f  mov     qword ptr [rsp+0C0h+InitialState], rax; IoStatusBlock
0x140055d34  mov     dword ptr [rbp+57h+var_20+4], 1
0x140055d3b  mov     [rbp+57h+var_18], 1
0x140055d42  mov     qword ptr [rbp+57h+var_68], 0
0x140055d4a  call    cs:__imp_ZwWriteFile
0x140055d51  nop     dword ptr [rax+rax+00h]
0x140055d56  mov     ebx, eax
0x140055d58  test    eax, eax
0x140055d5a  js      short loc_140055D78
0x140055d5c  mov     rcx, [rbp+57h+EventHandle]; Handle
0x140055d60  xor     r8d, r8d; Timeout
0x140055d63  xor     edx, edx; Alertable
0x140055d65  call    cs:__imp_ZwWaitForSingleObject
0x140055d6c  nop     dword ptr [rax+rax+00h]
0x140055d71  mov     ebx, dword ptr [rbp+57h+IoStatusBlock]
0x140055d74  test    ebx, ebx
0x140055d76  jns     short loc_140055DB2
0x140055d78  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140055d7f  lea     rax, WPP_GLOBAL_Control
0x140055d86  cmp     rcx, rax
0x140055d89  jz      short loc_140055DB2
0x140055d8b  test    dword ptr [rcx+2Ch], 200h
0x140055d92  jz      short loc_140055DB2
0x140055d94  cmp     byte ptr [rcx+29h], 1
0x140055d98  jb      short loc_140055DB2
0x140055d9a  mov     rcx, [rcx+18h]
0x140055d9e  lea     r8, WPP_1aa408cf43a53df084d1ad3a10e953fa_Traceguids
0x140055da5  mov     edx, 0Ah
0x140055daa  mov     r9d, ebx
0x140055dad  call    WPP_SF_d
0x140055db2  mov     rcx, [rbp+57h+EventHandle]; Handle
0x140055db6  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140055dba  jz      short loc_140055DC8
0x140055dbc  call    cs:__imp_ZwClose
0x140055dc3  nop     dword ptr [rax+rax+00h]
0x140055dc8  mov     eax, ebx
0x140055dca  mov     rcx, [rbp+57h+var_10]
0x140055dce  xor     rcx, rsp; StackCookie
0x140055dd1  call    __security_check_cookie
0x140055dd6  lea     r11, [rsp+0C0h+var_s0]
0x140055dde  mov     rbx, [r11+18h]
0x140055de2  mov     rdi, [r11+20h]
0x140055de6  mov     rsp, r11
0x140055de9  pop     rbp
0x140055dea  retn
```
