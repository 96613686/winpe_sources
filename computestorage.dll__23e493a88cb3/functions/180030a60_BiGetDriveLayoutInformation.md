# BiGetDriveLayoutInformation

- ea: `0x180030a60`
- end: `0x180030b43`
- name: `BiGetDriveLayoutInformation`
- size: `227`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003008c`
- `0x18003095c`

## callees

- `0x180030a60`
- `0x180031a98`

## import_xrefs

- `ntdll!ZwClose` at `0x180030b1f`
- `ntdll!ZwClose` at `0x180030b1f`
- `ntdll!ZwOpenFile` at `0x180030af6`
- `ntdll!ZwOpenFile` at `0x180030af6`
- `ntdll!RtlInitUnicodeString` at `0x180030a9f`
- `ntdll!RtlInitUnicodeString` at `0x180030a9f`

## pseudocode

```c
__int64 __fastcall BiGetDriveLayoutInformation(PCWSTR SourceString)
{
  NTSTATUS DriveLayoutIoctl; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-50h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  void *FileHandle; // [rsp+A0h] [rbp+20h] BYREF

  FileHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  IoStatusBlock = 0;
  DriveLayoutIoctl = ZwOpenFile(&FileHandle, 0x80100000, &ObjectAttributes, &IoStatusBlock, 3u, 0x20u);
  if ( DriveLayoutIoctl >= 0 )
    DriveLayoutIoctl = BiIssueGetDriveLayoutIoctl(FileHandle);
  if ( FileHandle )
    ZwClose(FileHandle);
  return (unsigned int)DriveLayoutIoctl;
}

```

## disassembly

```asm
0x180030a60  mov     [rsp-8+arg_0], rbx
0x180030a65  mov     [rsp-8+arg_8], rdi
0x180030a6a  push    rbp
0x180030a6b  mov     rbp, rsp
0x180030a6e  sub     rsp, 80h
0x180030a75  xorps   xmm0, xmm0
0x180030a78  mov     rdi, rdx
0x180030a7b  mov     rdx, rcx; SourceString
0x180030a7e  xor     eax, eax
0x180030a80  xorps   xmm1, xmm1
0x180030a83  mov     [rbp+FileHandle], rax
0x180030a87  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180030a8b  lea     rcx, [rbp+DestinationString]; DestinationString
0x180030a8f  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180030a93  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180030a97  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x180030a9b  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x180030a9f  call    cs:__imp_RtlInitUnicodeString
0x180030aa6  nop     dword ptr [rax+rax+00h]
0x180030aab  xorps   xmm0, xmm0
0x180030aae  mov     [rsp+80h+OpenOptions], 20h ; ' '; OpenOptions
0x180030ab6  lea     rax, [rbp+DestinationString]
0x180030aba  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180030ac1  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x180030ac5  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180030ac9  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180030acd  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180030ad5  mov     edx, 80100000h; DesiredAccess
0x180030ada  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180030ae1  lea     rcx, [rbp+FileHandle]; FileHandle
0x180030ae5  mov     [rsp+80h+ShareAccess], 3; ShareAccess
0x180030aed  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180030af2  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x180030af6  call    cs:__imp_ZwOpenFile
0x180030afd  nop     dword ptr [rax+rax+00h]
0x180030b02  mov     ebx, eax
0x180030b04  test    eax, eax
0x180030b06  js      short loc_180030B16
0x180030b08  mov     rcx, [rbp+FileHandle]; FileHandle
0x180030b0c  mov     rdx, rdi
0x180030b0f  call    BiIssueGetDriveLayoutIoctl
0x180030b14  mov     ebx, eax
0x180030b16  mov     rcx, [rbp+FileHandle]; Handle
0x180030b1a  test    rcx, rcx
0x180030b1d  jz      short loc_180030B2B
0x180030b1f  call    cs:__imp_ZwClose
0x180030b26  nop     dword ptr [rax+rax+00h]
0x180030b2b  lea     r11, [rsp+80h+var_s0]
0x180030b33  mov     eax, ebx
0x180030b35  mov     rbx, [r11+10h]
0x180030b39  mov     rdi, [r11+18h]
0x180030b3d  mov     rsp, r11
0x180030b40  pop     rbp
0x180030b41  retn
```
