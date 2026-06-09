# LsapOpenKsec

- ea: `0x140003094`
- end: `0x1400031b6`
- name: `LsapOpenKsec`
- size: `290`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400031bc`

## callees

- `0x140003094`
- `0x14000508c`

## import_xrefs

- `ntdll!NtDeviceIoControlFile` at `0x14000316c`
- `ntdll!NtDeviceIoControlFile` at `0x14000316c`
- `ntdll!NtSetInformationFile` at `0x14000319a`
- `ntdll!NtSetInformationFile` at `0x14000319a`
- `ntdll!NtOpenFile` at `0x140003119`
- `ntdll!NtOpenFile` at `0x140003119`
- `ntdll!RtlInitUnicodeString` at `0x1400030c9`
- `ntdll!RtlInitUnicodeString` at `0x1400030c9`

## pseudocode

```c
int LsapOpenKsec()
{
  int result; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp+7h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+60h] [rbp+17h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp+27h] BYREF
  int FileInformation; // [rsp+B0h] [rbp+67h] BYREF

  FileInformation = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\KsecDD");
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = NtOpenFile(&KsecDevice, 0xC0000000, &ObjectAttributes, &IoStatusBlock, 3u, 0);
  if ( result >= 0 )
  {
    result = NtDeviceIoControlFile(KsecDevice, 0, 0, 0, &IoStatusBlock, 0x398000u, 0, 0, &LsapSystemProcessId, 4u);
    if ( result >= 0 )
    {
      FileInformation = 6;
      result = NtSetInformationFile(
                 KsecDevice,
                 &IoStatusBlock,
                 &FileInformation,
                 4u,
                 FileIoCompletionNotificationInformation);
      if ( result >= 0 )
        return InitializeAsyncKsec(&ObjectAttributes);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140003094  push    rbp
0x140003096  lea     rbp, [rsp-57h]
0x14000309b  sub     rsp, 0A0h
0x1400030a2  xorps   xmm0, xmm0
0x1400030a5  lea     rdx, SourceString; "\\Device\\KsecDD"
0x1400030ac  xor     eax, eax
0x1400030ae  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400030b2  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1400030b6  mov     [rbp+57h+FileInformation], eax
0x1400030b9  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1400030bd  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400030c1  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1400030c5  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1400030c9  call    cs:__imp_RtlInitUnicodeString
0x1400030cf  lea     rax, [rbp+57h+DestinationString]
0x1400030d3  mov     [rsp+0A0h+OpenOptions], 0; OpenOptions
0x1400030db  xorps   xmm0, xmm0
0x1400030de  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400030e2  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1400030e6  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400030ed  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400030f1  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1400030f9  mov     edx, 0C0000000h; DesiredAccess
0x1400030fe  mov     [rbp+57h+ObjectAttributes.Attributes], 0
0x140003105  lea     rcx, KsecDevice; FileHandle
0x14000310c  mov     [rsp+0A0h+ShareAccess], 3; ShareAccess
0x140003114  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140003119  call    cs:__imp_NtOpenFile
0x14000311f  test    eax, eax
0x140003121  js      loc_1400031AD
0x140003127  mov     rcx, cs:KsecDevice; FileHandle
0x14000312e  lea     rax, LsapSystemProcessId
0x140003135  mov     [rsp+0A0h+OutputBufferLength], 4; OutputBufferLength
0x14000313d  xor     r9d, r9d; ApcContext
0x140003140  mov     [rsp+0A0h+OutputBuffer], rax; OutputBuffer
0x140003145  xor     r8d, r8d; ApcRoutine
0x140003148  mov     [rsp+0A0h+InputBufferLength], 0; InputBufferLength
0x140003150  lea     rax, [rbp+57h+IoStatusBlock]
0x140003154  mov     [rsp+0A0h+InputBuffer], 0; InputBuffer
0x14000315d  xor     edx, edx; Event
0x14000315f  mov     [rsp+0A0h+OpenOptions], 398000h; IoControlCode
0x140003167  mov     qword ptr [rsp+0A0h+ShareAccess], rax; IoStatusBlock
0x14000316c  call    cs:__imp_NtDeviceIoControlFile
0x140003172  test    eax, eax
0x140003174  js      short loc_1400031AD
0x140003176  mov     rcx, cs:KsecDevice; FileHandle
0x14000317d  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x140003181  mov     r9d, 4; Length
0x140003187  mov     [rbp+57h+FileInformation], 6
0x14000318e  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140003192  mov     [rsp+0A0h+ShareAccess], 29h ; ')'; FileInformationClass
0x14000319a  call    cs:__imp_NtSetInformationFile
0x1400031a0  test    eax, eax
0x1400031a2  js      short loc_1400031AD
0x1400031a4  lea     rcx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400031a8  call    InitializeAsyncKsec
0x1400031ad  add     rsp, 0A0h
0x1400031b4  pop     rbp
0x1400031b5  retn
```
