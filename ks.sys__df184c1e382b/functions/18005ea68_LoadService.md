# LoadService

- ea: `0x18005ea68`
- end: `0x18005ebe6`
- name: `LoadService`
- size: `382`
- prototype: `__int64 __fastcall(const GUID *, PVOID *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18005b230`

## callees

- `0x18005ea68`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18005ead3`
- `ntoskrnl!RtlInitUnicodeString` at `0x18005ead3`
- `ntoskrnl!ZwClose` at `0x18005ebd8`
- `ntoskrnl!ZwClose` at `0x18005ebd8`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18005ebc6`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18005ebc6`
- `ntoskrnl!IoCreateFile` at `0x18005eb66`
- `ntoskrnl!IoCreateFile` at `0x18005eb66`
- `ntoskrnl!IoFileObjectType` at `0x18005eba2`
- `ntoskrnl!IoGetDeviceInterfaces` at `0x18005ea93`
- `ntoskrnl!IoGetDeviceInterfaces` at `0x18005ea93`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005eb7a`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005eb7a`

## pseudocode

```c
__int64 __fastcall LoadService(const GUID *a1, PVOID *a2)
{
  NTSTATUS DeviceInterfaces; // ebx
  UNICODE_STRING DestinationString; // [rsp+70h] [rbp+7h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp+17h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp+27h] BYREF
  PZZWSTR SymbolicLinkList; // [rsp+E0h] [rbp+77h] BYREF
  void *FileHandle; // [rsp+E8h] [rbp+7Fh] BYREF

  SymbolicLinkList = 0;
  DeviceInterfaces = IoGetDeviceInterfaces(a1, 0, 0, &SymbolicLinkList);
  if ( DeviceInterfaces >= 0 )
  {
    FileHandle = 0;
    DestinationString = 0;
    memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
    IoStatusBlock = 0;
    RtlInitUnicodeString(&DestinationString, SymbolicLinkList);
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 1600;
    ObjectAttributes.ObjectName = &DestinationString;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    DeviceInterfaces = IoCreateFile(
                         &FileHandle,
                         0,
                         &ObjectAttributes,
                         &IoStatusBlock,
                         0,
                         0,
                         0,
                         1u,
                         0x100100u,
                         0,
                         0,
                         CreateFileTypeNone,
                         0,
                         0x101u);
    ExFreePoolWithTag(SymbolicLinkList, 0);
    if ( DeviceInterfaces >= 0 )
    {
      DeviceInterfaces = ObReferenceObjectByHandle(FileHandle, 0x120089u, (POBJECT_TYPE)IoFileObjectType, 0, a2, 0);
      ZwClose(FileHandle);
    }
  }
  return (unsigned int)DeviceInterfaces;
}

```

## disassembly

```asm
0x18005ea68  mov     [rsp-8+arg_0], rbx
0x18005ea6d  mov     [rsp-8+arg_8], rdi
0x18005ea72  push    rbp
0x18005ea73  lea     rbp, [rsp-57h]
0x18005ea78  sub     rsp, 0C0h
0x18005ea7f  mov     rdi, rdx
0x18005ea82  mov     [rbp+57h+SymbolicLinkList], 0
0x18005ea8a  xor     edx, edx; PhysicalDeviceObject
0x18005ea8c  lea     r9, [rbp+57h+SymbolicLinkList]; SymbolicLinkList
0x18005ea90  xor     r8d, r8d; Flags
0x18005ea93  call    cs:__imp_IoGetDeviceInterfaces
0x18005ea9a  nop     dword ptr [rax+rax+00h]
0x18005ea9f  mov     ebx, eax
0x18005eaa1  test    eax, eax
0x18005eaa3  js      loc_18005EB8A
0x18005eaa9  mov     rdx, [rbp+57h+SymbolicLinkList]; SourceString
0x18005eaad  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18005eab1  xorps   xmm1, xmm1
0x18005eab4  mov     [rbp+57h+FileHandle], 0
0x18005eabc  xorps   xmm0, xmm0
0x18005eabf  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18005eac3  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x18005eac7  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x18005eacb  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x18005eacf  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18005ead3  call    cs:__imp_RtlInitUnicodeString
0x18005eada  nop     dword ptr [rax+rax+00h]
0x18005eadf  mov     [rsp+0C0h+Options], 101h; Options
0x18005eae7  lea     rax, [rbp+57h+DestinationString]
0x18005eaeb  mov     [rsp+0C0h+InternalParameters], 0; InternalParameters
0x18005eaf4  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18005eaf8  mov     [rsp+0C0h+CreateFileType], 0; CreateFileType
0x18005eb00  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18005eb04  mov     [rsp+0C0h+EaLength], 0; EaLength
0x18005eb0c  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18005eb10  mov     [rsp+0C0h+EaBuffer], 0; EaBuffer
0x18005eb19  xorps   xmm0, xmm0
0x18005eb1c  mov     [rsp+0C0h+CreateOptions], 100100h; CreateOptions
0x18005eb24  xor     edx, edx; DesiredAccess
0x18005eb26  mov     [rsp+0C0h+Disposition], 1; Disposition
0x18005eb2e  mov     [rsp+0C0h+ShareAccess], 0; ShareAccess
0x18005eb36  mov     [rsp+0C0h+FileAttributes], 0; FileAttributes
0x18005eb3e  mov     [rsp+0C0h+AllocationSize], 0; AllocationSize
0x18005eb47  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18005eb4e  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18005eb56  mov     [rbp+57h+ObjectAttributes.Attributes], 640h
0x18005eb5d  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18005eb61  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005eb66  call    cs:__imp_IoCreateFile
0x18005eb6d  nop     dword ptr [rax+rax+00h]
0x18005eb72  mov     rcx, [rbp+57h+SymbolicLinkList]; P
0x18005eb76  xor     edx, edx; Tag
0x18005eb78  mov     ebx, eax
0x18005eb7a  call    cs:__imp_ExFreePoolWithTag
0x18005eb81  nop     dword ptr [rax+rax+00h]
0x18005eb86  test    ebx, ebx
0x18005eb88  jns     short loc_18005EBA2
0x18005eb8a  lea     r11, [rsp+0C0h+var_s0]
0x18005eb92  mov     eax, ebx
0x18005eb94  mov     rbx, [r11+10h]
0x18005eb98  mov     rdi, [r11+18h]
0x18005eb9c  mov     rsp, r11
0x18005eb9f  pop     rbp
0x18005eba0  retn
0x18005eba2  mov     r8, cs:__imp_IoFileObjectType
0x18005eba9  xor     r9d, r9d; AccessMode
0x18005ebac  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18005ebb0  mov     edx, 120089h; DesiredAccess
0x18005ebb5  mov     qword ptr [rsp+0C0h+FileAttributes], 0; HandleInformation
0x18005ebbe  mov     [rsp+0C0h+AllocationSize], rdi; Object
0x18005ebc3  mov     r8, [r8]; ObjectType
0x18005ebc6  call    cs:__imp_ObReferenceObjectByHandle
0x18005ebcd  nop     dword ptr [rax+rax+00h]
0x18005ebd2  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18005ebd6  mov     ebx, eax
0x18005ebd8  call    cs:__imp_ZwClose
0x18005ebdf  nop     dword ptr [rax+rax+00h]
0x18005ebe4  jmp     short loc_18005EB8A
```
