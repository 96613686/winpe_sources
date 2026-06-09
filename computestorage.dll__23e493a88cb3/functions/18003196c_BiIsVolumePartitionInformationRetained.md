# BiIsVolumePartitionInformationRetained

- ea: `0x18003196c`
- end: `0x180031a91`
- name: `BiIsVolumePartitionInformationRetained`
- size: `293`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002f564`

## callees

- `0x18003196c`

## import_xrefs

- `ntdll!ZwDeviceIoControlFile` at `0x180031a54`
- `ntdll!ZwDeviceIoControlFile` at `0x180031a54`
- `ntdll!ZwClose` at `0x180031a71`
- `ntdll!ZwClose` at `0x180031a71`
- `ntdll!ZwOpenFile` at `0x1800319fc`
- `ntdll!ZwOpenFile` at `0x1800319fc`
- `ntdll!RtlInitUnicodeString` at `0x1800319a5`
- `ntdll!RtlInitUnicodeString` at `0x1800319a5`

## pseudocode

```c
bool __fastcall BiIsVolumePartitionInformationRetained(PCWSTR SourceString)
{
  NTSTATUS v1; // ebx
  bool v2; // bl
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp+7h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp+17h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp+27h] BYREF
  void *FileHandle; // [rsp+B8h] [rbp+6Fh] BYREF

  FileHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  IoStatusBlock = 0;
  v1 = ZwOpenFile(&FileHandle, 0x80100000, &ObjectAttributes, &IoStatusBlock, 3u, 0x20u);
  if ( v1 >= 0 )
  {
    IoStatusBlock = 0;
    v1 = ZwDeviceIoControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x560028u, 0, 0, 0, 0);
  }
  v2 = v1 >= 0;
  if ( FileHandle )
    ZwClose(FileHandle);
  return v2;
}

```

## disassembly

```asm
0x18003196c  mov     [rsp-8+arg_0], rbx
0x180031971  push    rbp
0x180031972  lea     rbp, [rsp-57h]
0x180031977  sub     rsp, 0A0h
0x18003197e  xorps   xmm0, xmm0
0x180031981  xor     eax, eax
0x180031983  xorps   xmm1, xmm1
0x180031986  mov     [rbp+57h+FileHandle], rax
0x18003198a  mov     rdx, rcx; SourceString
0x18003198d  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180031991  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180031995  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180031999  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18003199d  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1800319a1  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x1800319a5  call    cs:__imp_RtlInitUnicodeString
0x1800319ac  nop     dword ptr [rax+rax+00h]
0x1800319b1  xorps   xmm0, xmm0
0x1800319b4  mov     [rsp+0A0h+OpenOptions], 20h ; ' '; OpenOptions
0x1800319bc  lea     rax, [rbp+57h+DestinationString]
0x1800319c0  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800319c7  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800319cb  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800319cf  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800319d3  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1800319db  mov     edx, 80100000h; DesiredAccess
0x1800319e0  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800319e7  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800319eb  mov     [rsp+0A0h+ShareAccess], 3; ShareAccess
0x1800319f3  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800319f8  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1800319fc  call    cs:__imp_ZwOpenFile
0x180031a03  nop     dword ptr [rax+rax+00h]
0x180031a08  mov     ebx, eax
0x180031a0a  test    eax, eax
0x180031a0c  js      short loc_180031A62
0x180031a0e  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x180031a12  lea     rax, [rbp+57h+IoStatusBlock]
0x180031a16  mov     [rsp+0A0h+OutputBufferLength], 0; OutputBufferLength
0x180031a1e  xorps   xmm0, xmm0
0x180031a21  mov     [rsp+0A0h+OutputBuffer], 0; OutputBuffer
0x180031a2a  xor     r9d, r9d; ApcContext
0x180031a2d  mov     [rsp+0A0h+InputBufferLength], 0; InputBufferLength
0x180031a35  xor     r8d, r8d; ApcRoutine
0x180031a38  mov     [rsp+0A0h+InputBuffer], 0; InputBuffer
0x180031a41  xor     edx, edx; Event
0x180031a43  mov     [rsp+0A0h+OpenOptions], 560028h; IoControlCode
0x180031a4b  mov     qword ptr [rsp+0A0h+ShareAccess], rax; IoStatusBlock
0x180031a50  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180031a54  call    cs:__imp_ZwDeviceIoControlFile
0x180031a5b  nop     dword ptr [rax+rax+00h]
0x180031a60  mov     ebx, eax
0x180031a62  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180031a66  shr     ebx, 1Fh
0x180031a69  xor     bl, 1
0x180031a6c  test    rcx, rcx
0x180031a6f  jz      short loc_180031A7D
0x180031a71  call    cs:__imp_ZwClose
0x180031a78  nop     dword ptr [rax+rax+00h]
0x180031a7d  mov     al, bl
0x180031a7f  mov     rbx, [rsp+0A0h+arg_0]
0x180031a87  add     rsp, 0A0h
0x180031a8e  pop     rbp
0x180031a8f  retn
```
