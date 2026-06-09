# RxVmbusRecvTransportNegotiateMessage

- ea: `0x1400559e4`
- end: `0x140055c5d`
- name: `RxVmbusRecvTransportNegotiateMessage`
- size: `633`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400554d0`

## callees

- `0x14003838c`
- `0x140055924`
- `0x1400559e4`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140055b4e`
- `ntoskrnl!ExAllocatePool2` at `0x140055b4e`
- `ntoskrnl!ZwCreateEvent` at `0x140055a4f`
- `ntoskrnl!ZwCreateEvent` at `0x140055a4f`
- `ntoskrnl!ZwClose` at `0x140055c09`
- `ntoskrnl!ZwClose` at `0x140055c09`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055bec`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055bec`
- `ntoskrnl!ZwWaitForSingleObject` at `0x140055acd`
- `ntoskrnl!ZwWaitForSingleObject` at `0x140055bc1`
- `ntoskrnl!ZwWaitForSingleObject` at `0x140055acd`
- `ntoskrnl!ZwWaitForSingleObject` at `0x140055bc1`
- `ntoskrnl!ZwReadFile` at `0x140055aae`
- `ntoskrnl!ZwReadFile` at `0x140055ba6`
- `ntoskrnl!ZwReadFile` at `0x140055aae`
- `ntoskrnl!ZwReadFile` at `0x140055ba6`

## pseudocode

```c
__int64 __fastcall RxVmbusRecvTransportNegotiateMessage(__int64 a1)
{
  NTSTATUS Status; // ebx
  void *v3; // rcx
  unsigned __int32 v4; // eax
  __int64 v5; // r9
  __int64 Length; // rsi
  void *Pool2; // rdi
  void *v8; // rcx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+7h] BYREF
  unsigned int Buffer; // [rsp+C8h] [rbp+6Fh] BYREF
  void *EventHandle; // [rsp+D0h] [rbp+77h] BYREF
  LARGE_INTEGER ByteOffset; // [rsp+D8h] [rbp+7Fh] BYREF

  Buffer = 0;
  ByteOffset.QuadPart = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 512;
  EventHandle = (void *)-1LL;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = 0;
  IoStatusBlock = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  Status = ZwCreateEvent(&EventHandle, 0x1F0003u, &ObjectAttributes, SynchronizationEvent, 0);
  if ( Status >= 0 )
  {
    v3 = *(void **)(a1 + 120);
    ByteOffset.QuadPart = 0;
    Status = ZwReadFile(v3, EventHandle, 0, 0, &IoStatusBlock, &Buffer, 4u, &ByteOffset, 0);
    if ( Status >= 0 )
    {
      ZwWaitForSingleObject(EventHandle, 0, 0);
      Status = IoStatusBlock.Status;
      if ( IoStatusBlock.Status >= 0 )
      {
        v4 = _byteswap_ulong(Buffer);
        Buffer = v4;
        v5 = v4 & 0xFF000000;
        if ( (_DWORD)v5 != 0x1000000 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
          {
            if ( BYTE1(WPP_GLOBAL_Control->Timer) )
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_1aa408cf43a53df084d1ad3a10e953fa_Traceguids, v5);
          }
          __debugbreak();
        }
        Length = v4 & 0xFFFFFF;
        Pool2 = (void *)ExAllocatePool2(66, Length, 1665366098);
        if ( Pool2 )
        {
          v8 = *(void **)(a1 + 120);
          ByteOffset.QuadPart = 0;
          Status = ZwReadFile(v8, EventHandle, 0, 0, &IoStatusBlock, Pool2, Length, &ByteOffset, 0);
          if ( Status >= 0 )
          {
            ZwWaitForSingleObject(EventHandle, 0, 0);
            Status = IoStatusBlock.Status;
            if ( IoStatusBlock.Status >= 0 )
              Status = RxVmbusProcessTransportNegotiateMessage(a1, Pool2, (unsigned int)Length);
          }
          ExFreePoolWithTag(Pool2, 0x63437852u);
        }
        else
        {
          Status = -1073741670;
        }
      }
    }
  }
  if ( EventHandle != (void *)-1LL )
    ZwClose(EventHandle);
  if ( Status < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      14,
      WPP_1aa408cf43a53df084d1ad3a10e953fa_Traceguids,
      (unsigned int)Status);
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x1400559e4  mov     [rsp-8+arg_8], edx
0x1400559e8  push    rbp
0x1400559e9  push    rbx
0x1400559ea  push    rsi
0x1400559eb  push    rdi
0x1400559ec  push    r14
0x1400559ee  lea     rbp, [rsp-37h]
0x1400559f3  sub     rsp, 90h
0x1400559fa  xor     eax, eax
0x1400559fc  mov     [rbp+57h+arg_8], 0
0x140055a03  xorps   xmm0, xmm0
0x140055a06  mov     qword ptr [rbp+57h+arg_18], 0
0x140055a0e  mov     r14, rcx
0x140055a11  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140055a19  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140055a1d  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 200h
0x140055a25  lea     r9d, [rax+1]; EventType
0x140055a29  mov     [rbp+57h+EventHandle], 0FFFFFFFFFFFFFFFFh
0x140055a31  mov     edx, 1F0003h; DesiredAccess
0x140055a36  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x140055a3a  lea     rcx, [rbp+57h+EventHandle]; EventHandle
0x140055a3e  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140055a42  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140055a46  mov     [rsp+0B0h+InitialState], al; InitialState
0x140055a4a  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140055a4f  call    cs:__imp_ZwCreateEvent
0x140055a56  nop     dword ptr [rax+rax+00h]
0x140055a5b  lea     rdi, WPP_GLOBAL_Control
0x140055a62  mov     ebx, eax
0x140055a64  test    eax, eax
0x140055a66  js      loc_140055BFF
0x140055a6c  mov     rdx, [rbp+57h+EventHandle]; Event
0x140055a70  lea     rax, [rbp+57h+arg_18]
0x140055a74  mov     rcx, [r14+78h]; FileHandle
0x140055a78  xor     r9d, r9d; ApcContext
0x140055a7b  mov     [rsp+0B0h+Key], 0; Key
0x140055a84  xor     r8d, r8d; ApcRoutine
0x140055a87  mov     [rsp+0B0h+ByteOffset], rax; ByteOffset
0x140055a8c  lea     rax, [rbp+57h+arg_8]
0x140055a90  mov     [rsp+0B0h+Length], 4; Length
0x140055a98  mov     [rsp+0B0h+Buffer], rax; Buffer
0x140055a9d  lea     rax, [rbp+57h+IoStatusBlock]
0x140055aa1  mov     qword ptr [rsp+0B0h+InitialState], rax; IoStatusBlock
0x140055aa6  mov     qword ptr [rbp+57h+arg_18], 0
0x140055aae  call    cs:__imp_ZwReadFile
0x140055ab5  nop     dword ptr [rax+rax+00h]
0x140055aba  mov     ebx, eax
0x140055abc  test    eax, eax
0x140055abe  js      loc_140055BFF
0x140055ac4  mov     rcx, [rbp+57h+EventHandle]; Handle
0x140055ac8  xor     r8d, r8d; Timeout
0x140055acb  xor     edx, edx; Alertable
0x140055acd  call    cs:__imp_ZwWaitForSingleObject
0x140055ad4  nop     dword ptr [rax+rax+00h]
0x140055ad9  mov     ebx, dword ptr [rbp+57h+IoStatusBlock]
0x140055adc  test    ebx, ebx
0x140055ade  js      loc_140055BFF
0x140055ae4  mov     eax, [rbp+57h+arg_8]
0x140055ae7  bswap   eax
0x140055ae9  mov     r9d, eax
0x140055aec  mov     [rbp+57h+arg_8], eax
0x140055aef  and     r9d, 0FF000000h
0x140055af6  cmp     r9d, 1000000h
0x140055afd  jz      short loc_140055B3A
0x140055aff  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140055b06  cmp     rcx, rdi
0x140055b09  jz      short loc_140055B2F
0x140055b0b  test    dword ptr [rcx+2Ch], 200h
0x140055b12  jz      short loc_140055B2F
0x140055b14  cmp     byte ptr [rcx+29h], 1
0x140055b18  jb      short loc_140055B2F
0x140055b1a  mov     rcx, [rcx+18h]
0x140055b1e  lea     r8, WPP_1aa408cf43a53df084d1ad3a10e953fa_Traceguids
0x140055b25  mov     edx, 0Dh
0x140055b2a  call    WPP_SF_d
0x140055b2f  int     3; Trap to Debugger
0x140055b30  mov     ebx, 0C00000C4h
0x140055b35  jmp     loc_140055BFF
0x140055b3a  and     eax, 0FFFFFFh
0x140055b3f  mov     ecx, 42h ; 'B'
0x140055b44  mov     edx, eax
0x140055b46  mov     r8d, 63437852h
0x140055b4c  mov     esi, eax
0x140055b4e  call    cs:__imp_ExAllocatePool2
0x140055b55  nop     dword ptr [rax+rax+00h]
0x140055b5a  mov     rdi, rax
0x140055b5d  test    rax, rax
0x140055b60  jnz     short loc_140055B6C
0x140055b62  mov     ebx, 0C000009Ah
0x140055b67  jmp     loc_140055BF8
0x140055b6c  mov     rdx, [rbp+57h+EventHandle]; Event
0x140055b70  lea     rax, [rbp+57h+arg_18]
0x140055b74  mov     rcx, [r14+78h]; FileHandle
0x140055b78  xor     r9d, r9d; ApcContext
0x140055b7b  mov     [rsp+0B0h+Key], 0; Key
0x140055b84  xor     r8d, r8d; ApcRoutine
0x140055b87  mov     [rsp+0B0h+ByteOffset], rax; ByteOffset
0x140055b8c  lea     rax, [rbp+57h+IoStatusBlock]
0x140055b90  mov     [rsp+0B0h+Length], esi; Length
0x140055b94  mov     [rsp+0B0h+Buffer], rdi; Buffer
0x140055b99  mov     qword ptr [rsp+0B0h+InitialState], rax; IoStatusBlock
0x140055b9e  mov     qword ptr [rbp+57h+arg_18], 0
0x140055ba6  call    cs:__imp_ZwReadFile
0x140055bad  nop     dword ptr [rax+rax+00h]
0x140055bb2  mov     ebx, eax
0x140055bb4  test    eax, eax
0x140055bb6  js      short loc_140055BE4
0x140055bb8  mov     rcx, [rbp+57h+EventHandle]; Handle
0x140055bbc  xor     r8d, r8d; Timeout
0x140055bbf  xor     edx, edx; Alertable
0x140055bc1  call    cs:__imp_ZwWaitForSingleObject
0x140055bc8  nop     dword ptr [rax+rax+00h]
0x140055bcd  mov     ebx, dword ptr [rbp+57h+IoStatusBlock]
0x140055bd0  test    ebx, ebx
0x140055bd2  js      short loc_140055BE4
0x140055bd4  mov     r8d, esi
0x140055bd7  mov     rdx, rdi
0x140055bda  mov     rcx, r14
0x140055bdd  call    RxVmbusProcessTransportNegotiateMessage
0x140055be2  mov     ebx, eax
0x140055be4  mov     edx, 63437852h; Tag
0x140055be9  mov     rcx, rdi; P
0x140055bec  call    cs:__imp_ExFreePoolWithTag
0x140055bf3  nop     dword ptr [rax+rax+00h]
0x140055bf8  lea     rdi, WPP_GLOBAL_Control
0x140055bff  mov     rcx, [rbp+57h+EventHandle]; Handle
0x140055c03  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140055c07  jz      short loc_140055C15
0x140055c09  call    cs:__imp_ZwClose
0x140055c10  nop     dword ptr [rax+rax+00h]
0x140055c15  test    ebx, ebx
0x140055c17  jns     short loc_140055C4C
0x140055c19  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140055c20  cmp     rcx, rdi
0x140055c23  jz      short loc_140055C4C
0x140055c25  test    dword ptr [rcx+2Ch], 200h
0x140055c2c  jz      short loc_140055C4C
0x140055c2e  cmp     byte ptr [rcx+29h], 1
0x140055c32  jb      short loc_140055C4C
0x140055c34  mov     rcx, [rcx+18h]
0x140055c38  lea     r8, WPP_1aa408cf43a53df084d1ad3a10e953fa_Traceguids
0x140055c3f  mov     edx, 0Eh
0x140055c44  mov     r9d, ebx
0x140055c47  call    WPP_SF_d
0x140055c4c  mov     eax, ebx
0x140055c4e  add     rsp, 90h
0x140055c55  pop     r14
0x140055c57  pop     rdi
0x140055c58  pop     rsi
0x140055c59  pop     rbx
0x140055c5a  pop     rbp
0x140055c5b  retn
```
