# MrxSmbGetSrvHandle

- ea: `0x14001eaf0`
- end: `0x14001ed85`
- name: `MrxSmbGetSrvHandle`
- size: `661`
- prototype: `void __fastcall(struct _KEVENT *Context)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, reparse_path`

## callees

- `0x14001eaf0`
- `0x140029764`
- `0x140037120`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14001ec6c`
- `ntoskrnl!KeSetEvent` at `0x14001ec6c`
- `ntoskrnl!IoSetFileOrigin` at `0x14001ece8`
- `ntoskrnl!IoSetFileOrigin` at `0x14001ece8`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14001ecd3`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14001ecd3`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001ecba`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001ecba`
- `ntoskrnl!ZwClose` at `0x14001ec37`
- `ntoskrnl!ZwClose` at `0x14001ec37`
- `ntoskrnl!ZwWaitForSingleObject` at `0x14001ed71`
- `ntoskrnl!ZwWaitForSingleObject` at `0x14001ed71`
- `ntoskrnl!ZwFsControlFile` at `0x14001ec1a`
- `ntoskrnl!ZwFsControlFile` at `0x14001ec1a`
- `ntoskrnl!ZwOpenFile` at `0x14001eba7`
- `ntoskrnl!ZwOpenFile` at `0x14001eba7`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001eb58`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001eb58`

## pseudocode

```c
void __fastcall MrxSmbGetSrvHandle(struct _KEVENT *Context)
{
  struct _LIST_ENTRY *Blink; // rsi
  NTSTATUS Status; // edi
  struct _LIST_ENTRY *Flink; // rcx
  PDEVICE_OBJECT RelatedDeviceObject; // rax
  struct _FILE_OBJECT *v6; // rcx
  struct _LIST_ENTRY *v7; // rdx
  void *FileHandle; // [rsp+50h] [rbp-39h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp-31h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-21h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp+Fh] BYREF
  struct _LIST_ENTRY InputBuffer; // [rsp+A8h] [rbp+1Fh] BYREF
  __int128 v13; // [rsp+B8h] [rbp+2Fh]

  Blink = Context[8].Header.WaitListHead.Blink;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  FileHandle = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  IoStatusBlock = 0;
  DestinationString = 0;
  InputBuffer = 0;
  v13 = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\Srv2");
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  Status = ZwOpenFile(&FileHandle, 0xC0100000, &ObjectAttributes, &IoStatusBlock, 3u, 0x60u);
  if ( Status < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        11,
        WPP_f3cc199661c03597963a8c8eae40d83a_Traceguids,
        (unsigned int)Status);
    }
  }
  else
  {
    DWORD2(v13) = 0;
    InputBuffer = Blink[4];
    *(_QWORD *)&v13 = Blink[5].Flink;
    Status = ZwFsControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x14807Cu, &InputBuffer, 0x20u, &Blink[3], 0x10u);
    if ( Status == 259 )
    {
      ZwWaitForSingleObject(FileHandle, 0, 0);
      Status = IoStatusBlock.Status;
    }
    ZwClose(FileHandle);
    if ( !Status )
    {
      Flink = Blink[3].Flink;
      LODWORD(Blink[1].Flink) = Blink[3].Blink;
      Status = ObReferenceObjectByHandle(Flink, 0, 0, 0, (PVOID *)&Blink->Flink, 0);
      if ( Status >= 0 )
      {
        RelatedDeviceObject = IoGetRelatedDeviceObject((PFILE_OBJECT)Blink->Flink);
        v6 = (struct _FILE_OBJECT *)Blink->Flink;
        Blink->Blink = (struct _LIST_ENTRY *)RelatedDeviceObject;
        IoSetFileOrigin(v6, 1u);
        v7 = Blink->Blink->Blink[5].Flink;
        if ( v7 )
        {
          Blink[1].Blink = v7[1].Flink;
          Blink[2].Flink = v7[1].Blink;
        }
      }
    }
  }
  Context[5].Header.LockNV &= ~0x100000u;
  Context[8].Header.WaitListHead.Blink = (struct _LIST_ENTRY *)Status;
  KeSetEvent(Context + 16, 0, 0);
}

```

## disassembly

```asm
0x14001eaf0  mov     [rsp-8+arg_10], rbx
0x14001eaf5  mov     [rsp-8+arg_18], rsi
0x14001eafa  push    rbp
0x14001eafb  push    rdi
0x14001eafc  push    r15
0x14001eafe  lea     rbp, [rsp-47h]
0x14001eb03  sub     rsp, 0D0h
0x14001eb0a  mov     rax, cs:__security_cookie
0x14001eb11  xor     rax, rsp
0x14001eb14  mov     [rbp+57h+var_18], rax
0x14001eb18  mov     rsi, [rcx+0D0h]
0x14001eb1f  lea     rdx, SourceString; "\\Device\\Srv2"
0x14001eb26  xorps   xmm0, xmm0
0x14001eb29  mov     rbx, rcx
0x14001eb2c  xorps   xmm1, xmm1
0x14001eb2f  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14001eb33  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14001eb37  xor     r15d, r15d
0x14001eb3a  xor     eax, eax
0x14001eb3c  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x14001eb40  mov     [rbp+57h+FileHandle], r15
0x14001eb44  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14001eb48  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x14001eb4c  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x14001eb50  movups  [rbp+57h+var_38], xmm0
0x14001eb54  movups  [rbp+57h+var_28], xmm0
0x14001eb58  call    cs:__imp_RtlInitUnicodeString
0x14001eb5f  nop     dword ptr [rax+rax+00h]
0x14001eb64  lea     rax, [rbp+57h+DestinationString]
0x14001eb68  mov     [rsp+0E0h+OpenOptions], 60h ; '`'; OpenOptions
0x14001eb70  xorps   xmm0, xmm0
0x14001eb73  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14001eb77  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14001eb7b  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14001eb82  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14001eb86  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x14001eb8a  mov     edx, 0C0100000h; DesiredAccess
0x14001eb8f  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14001eb96  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x14001eb9a  mov     [rsp+0E0h+ShareAccess], 3; ShareAccess
0x14001eba2  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001eba7  call    cs:__imp_ZwOpenFile
0x14001ebae  nop     dword ptr [rax+rax+00h]
0x14001ebb3  mov     edi, eax
0x14001ebb5  test    eax, eax
0x14001ebb7  js      loc_14001ED1E
0x14001ebbd  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x14001ebc1  lea     rax, [rbp+57h+var_38]
0x14001ebc5  mov     [rsp+0E0h+OutputBufferLength], 10h; OutputBufferLength
0x14001ebcd  xor     r9d, r9d; ApcContext
0x14001ebd0  mov     dword ptr [rbp+57h+var_28+8], r15d
0x14001ebd4  xor     r8d, r8d; ApcRoutine
0x14001ebd7  movups  xmm0, xmmword ptr [rsi+40h]
0x14001ebdb  mov     [rsp+0E0h+arg_8], r14
0x14001ebe3  xor     edx, edx; Event
0x14001ebe5  lea     r14, [rsi+30h]
0x14001ebe9  mov     [rsp+0E0h+OutputBuffer], r14; OutputBuffer
0x14001ebee  mov     [rsp+0E0h+InputBufferLength], 20h ; ' '; InputBufferLength
0x14001ebf6  mov     [rsp+0E0h+InputBuffer], rax; InputBuffer
0x14001ebfb  lea     rax, [rbp+57h+IoStatusBlock]
0x14001ebff  movups  [rbp+57h+var_38], xmm0
0x14001ec03  mov     [rsp+0E0h+OpenOptions], 14807Ch; FsControlCode
0x14001ec0b  movsd   xmm1, qword ptr [rsi+50h]
0x14001ec10  movsd   qword ptr [rbp+57h+var_28], xmm1
0x14001ec15  mov     qword ptr [rsp+0E0h+ShareAccess], rax; IoStatusBlock
0x14001ec1a  call    cs:__imp_ZwFsControlFile
0x14001ec21  nop     dword ptr [rax+rax+00h]
0x14001ec26  mov     edi, eax
0x14001ec28  cmp     eax, 103h
0x14001ec2d  jz      loc_14001ED68
0x14001ec33  mov     rcx, [rbp+57h+FileHandle]; Handle
0x14001ec37  call    cs:__imp_ZwClose
0x14001ec3e  nop     dword ptr [rax+rax+00h]
0x14001ec43  test    edi, edi
0x14001ec45  jz      short loc_14001EC9F
0x14001ec47  mov     r14, [rsp+0E0h+arg_8]
0x14001ec4f  and     dword ptr [rbx+78h], 0FFEFFFFFh
0x14001ec56  lea     rcx, [rbx+180h]; Event
0x14001ec5d  movsxd  rax, edi
0x14001ec60  xor     r8d, r8d; Wait
0x14001ec63  xor     edx, edx; Increment
0x14001ec65  mov     [rbx+0D0h], rax
0x14001ec6c  call    cs:__imp_KeSetEvent
0x14001ec73  nop     dword ptr [rax+rax+00h]
0x14001ec78  xor     eax, eax
0x14001ec7a  mov     rcx, [rbp+57h+var_18]
0x14001ec7e  xor     rcx, rsp; StackCookie
0x14001ec81  call    __security_check_cookie
0x14001ec86  lea     r11, [rsp+0E0h+var_10]
0x14001ec8e  mov     rbx, [r11+30h]
0x14001ec92  mov     rsi, [r11+38h]
0x14001ec96  mov     rsp, r11
0x14001ec99  pop     r15
0x14001ec9b  pop     rdi
0x14001ec9c  pop     rbp
0x14001ec9d  retn
0x14001ec9f  mov     eax, [rsi+38h]
0x14001eca2  xor     r9d, r9d; AccessMode
0x14001eca5  mov     rcx, [r14]; Handle
0x14001eca8  xor     r8d, r8d; ObjectType
0x14001ecab  mov     qword ptr [rsp+0E0h+OpenOptions], r15; HandleInformation
0x14001ecb0  xor     edx, edx; DesiredAccess
0x14001ecb2  mov     [rsi+10h], eax
0x14001ecb5  mov     qword ptr [rsp+0E0h+ShareAccess], rsi; Object
0x14001ecba  call    cs:__imp_ObReferenceObjectByHandle
0x14001ecc1  nop     dword ptr [rax+rax+00h]
0x14001ecc6  mov     edi, eax
0x14001ecc8  test    eax, eax
0x14001ecca  js      loc_14001EC47
0x14001ecd0  mov     rcx, [rsi]; FileObject
0x14001ecd3  call    cs:__imp_IoGetRelatedDeviceObject
0x14001ecda  nop     dword ptr [rax+rax+00h]
0x14001ecdf  mov     rcx, [rsi]; FileObject
0x14001ece2  mov     dl, 1; Remote
0x14001ece4  mov     [rsi+8], rax
0x14001ece8  call    cs:__imp_IoSetFileOrigin
0x14001ecef  nop     dword ptr [rax+rax+00h]
0x14001ecf4  mov     rax, [rsi+8]
0x14001ecf8  mov     rcx, [rax+8]
0x14001ecfc  mov     rdx, [rcx+50h]
0x14001ed00  test    rdx, rdx
0x14001ed03  jz      loc_14001EC47
0x14001ed09  mov     rax, [rdx+10h]
0x14001ed0d  mov     [rsi+18h], rax
0x14001ed11  mov     rax, [rdx+18h]
0x14001ed15  mov     [rsi+20h], rax
0x14001ed19  jmp     loc_14001EC47
0x14001ed1e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001ed25  lea     rax, WPP_GLOBAL_Control
0x14001ed2c  cmp     rcx, rax
0x14001ed2f  jz      loc_14001EC4F
0x14001ed35  mov     edx, [rcx+2Ch]
0x14001ed38  test    dl, 1
0x14001ed3b  jz      loc_14001EC4F
0x14001ed41  cmp     byte ptr [rcx+29h], 1
0x14001ed45  jb      loc_14001EC4F
0x14001ed4b  mov     rcx, [rcx+18h]
0x14001ed4f  lea     r8, WPP_f3cc199661c03597963a8c8eae40d83a_Traceguids
0x14001ed56  mov     edx, 0Bh
0x14001ed5b  mov     r9d, edi
0x14001ed5e  call    WPP_SF_d
0x14001ed63  jmp     loc_14001EC4F
0x14001ed68  mov     rcx, [rbp+57h+FileHandle]; Handle
0x14001ed6c  xor     r8d, r8d; Timeout
0x14001ed6f  xor     edx, edx; Alertable
0x14001ed71  call    cs:__imp_ZwWaitForSingleObject
0x14001ed78  nop     dword ptr [rax+rax+00h]
0x14001ed7d  mov     edi, dword ptr [rbp+57h+IoStatusBlock]
0x14001ed80  jmp     loc_14001EC33
```
