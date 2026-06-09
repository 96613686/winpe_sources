# LoadService

- ea: `0x18005e8c8`
- end: `0x18005ea46`
- name: `LoadService`
- size: `382`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18005b090`

## callees

- `0x18005e8c8`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18005e933`
- `ntoskrnl!RtlInitUnicodeString` at `0x18005e933`
- `ntoskrnl!ZwClose` at `0x18005ea38`
- `ntoskrnl!ZwClose` at `0x18005ea38`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18005ea26`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18005ea26`
- `ntoskrnl!IoCreateFile` at `0x18005e9c6`
- `ntoskrnl!IoCreateFile` at `0x18005e9c6`
- `ntoskrnl!IoFileObjectType` at `0x18005ea02`
- `ntoskrnl!IoGetDeviceInterfaces` at `0x18005e8f3`
- `ntoskrnl!IoGetDeviceInterfaces` at `0x18005e8f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005e9da`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005e9da`

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
0x18005e8c8  mov     [rsp-8+arg_0], rbx
0x18005e8cd  mov     [rsp-8+arg_8], rdi
0x18005e8d2  push    rbp
0x18005e8d3  lea     rbp, [rsp-57h]
0x18005e8d8  sub     rsp, 0C0h
0x18005e8df  mov     rdi, rdx
0x18005e8e2  mov     [rbp+57h+SymbolicLinkList], 0
0x18005e8ea  xor     edx, edx; PhysicalDeviceObject
0x18005e8ec  lea     r9, [rbp+57h+SymbolicLinkList]; SymbolicLinkList
0x18005e8f0  xor     r8d, r8d; Flags
0x18005e8f3  call    cs:__imp_IoGetDeviceInterfaces
0x18005e8fa  nop     dword ptr [rax+rax+00h]
0x18005e8ff  mov     ebx, eax
0x18005e901  test    eax, eax
0x18005e903  js      loc_18005E9EA
0x18005e909  mov     rdx, [rbp+57h+SymbolicLinkList]; SourceString
0x18005e90d  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18005e911  xorps   xmm1, xmm1
0x18005e914  mov     [rbp+57h+FileHandle], 0
0x18005e91c  xorps   xmm0, xmm0
0x18005e91f  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18005e923  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x18005e927  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x18005e92b  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x18005e92f  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18005e933  call    cs:__imp_RtlInitUnicodeString
0x18005e93a  nop     dword ptr [rax+rax+00h]
0x18005e93f  mov     [rsp+0C0h+Options], 101h; Options
0x18005e947  lea     rax, [rbp+57h+DestinationString]
0x18005e94b  mov     [rsp+0C0h+InternalParameters], 0; InternalParameters
0x18005e954  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18005e958  mov     [rsp+0C0h+CreateFileType], 0; CreateFileType
0x18005e960  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18005e964  mov     [rsp+0C0h+EaLength], 0; EaLength
0x18005e96c  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18005e970  mov     [rsp+0C0h+EaBuffer], 0; EaBuffer
0x18005e979  xorps   xmm0, xmm0
0x18005e97c  mov     [rsp+0C0h+CreateOptions], 100100h; CreateOptions
0x18005e984  xor     edx, edx; DesiredAccess
0x18005e986  mov     [rsp+0C0h+Disposition], 1; Disposition
0x18005e98e  mov     [rsp+0C0h+ShareAccess], 0; ShareAccess
0x18005e996  mov     [rsp+0C0h+FileAttributes], 0; FileAttributes
0x18005e99e  mov     [rsp+0C0h+AllocationSize], 0; AllocationSize
0x18005e9a7  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18005e9ae  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18005e9b6  mov     [rbp+57h+ObjectAttributes.Attributes], 640h
0x18005e9bd  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18005e9c1  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005e9c6  call    cs:__imp_IoCreateFile
0x18005e9cd  nop     dword ptr [rax+rax+00h]
0x18005e9d2  mov     rcx, [rbp+57h+SymbolicLinkList]; P
0x18005e9d6  xor     edx, edx; Tag
0x18005e9d8  mov     ebx, eax
0x18005e9da  call    cs:__imp_ExFreePoolWithTag
0x18005e9e1  nop     dword ptr [rax+rax+00h]
0x18005e9e6  test    ebx, ebx
0x18005e9e8  jns     short loc_18005EA02
0x18005e9ea  lea     r11, [rsp+0C0h+var_s0]
0x18005e9f2  mov     eax, ebx
0x18005e9f4  mov     rbx, [r11+10h]
0x18005e9f8  mov     rdi, [r11+18h]
0x18005e9fc  mov     rsp, r11
0x18005e9ff  pop     rbp
0x18005ea00  retn
0x18005ea02  mov     r8, cs:__imp_IoFileObjectType
0x18005ea09  xor     r9d, r9d; AccessMode
0x18005ea0c  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18005ea10  mov     edx, 120089h; DesiredAccess
0x18005ea15  mov     qword ptr [rsp+0C0h+FileAttributes], 0; HandleInformation
0x18005ea1e  mov     [rsp+0C0h+AllocationSize], rdi; Object
0x18005ea23  mov     r8, [r8]; ObjectType
0x18005ea26  call    cs:__imp_ObReferenceObjectByHandle
0x18005ea2d  nop     dword ptr [rax+rax+00h]
0x18005ea32  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18005ea36  mov     ebx, eax
0x18005ea38  call    cs:__imp_ZwClose
0x18005ea3f  nop     dword ptr [rax+rax+00h]
0x18005ea44  jmp     short loc_18005E9EA
```
