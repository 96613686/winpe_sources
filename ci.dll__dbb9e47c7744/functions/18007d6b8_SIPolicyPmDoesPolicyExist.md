# SIPolicyPmDoesPolicyExist

- ea: `0x18007d6b8`
- end: `0x18007d774`
- name: `SIPolicyPmDoesPolicyExist`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18007e28c`

## callees

- `0x18007d6b8`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x18007d754`
- `ntoskrnl!ZwClose` at `0x18007d754`
- `ntoskrnl!ZwCreateFile` at `0x18007d737`
- `ntoskrnl!ZwCreateFile` at `0x18007d737`

## pseudocode

```c
bool __fastcall SIPolicyPmDoesPolicyExist(__int64 a1, struct _UNICODE_STRING *a2)
{
  bool v2; // bl
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp+17h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp+27h] BYREF
  void *FileHandle; // [rsp+B8h] [rbp+6Fh] BYREF

  ObjectAttributes.ObjectName = a2;
  FileHandle = 0;
  IoStatusBlock = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v2 = ZwCreateFile(&FileHandle, 0x120089u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 3u, 1u, 0x20u, 0, 0) >= 0;
  if ( FileHandle )
    ZwClose(FileHandle);
  return v2;
}

```

## disassembly

```asm
0x18007d6b8  mov     [rsp-8+arg_0], rbx
0x18007d6bd  push    rbp
0x18007d6be  lea     rbp, [rsp-57h]
0x18007d6c3  sub     rsp, 0A0h
0x18007d6ca  xor     eax, eax
0x18007d6cc  mov     [rbp+57h+ObjectAttributes.ObjectName], rdx
0x18007d6d0  mov     [rsp+0A0h+EaLength], eax; EaLength
0x18007d6d4  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18007d6d8  mov     [rsp+0A0h+EaBuffer], rax; EaBuffer
0x18007d6dd  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18007d6e1  mov     [rsp+0A0h+CreateOptions], 20h ; ' '; CreateOptions
0x18007d6e9  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18007d6ed  mov     [rsp+0A0h+CreateDisposition], 1; CreateDisposition
0x18007d6f5  xorps   xmm0, xmm0
0x18007d6f8  mov     [rsp+0A0h+ShareAccess], 3; ShareAccess
0x18007d700  mov     edx, 120089h; DesiredAccess
0x18007d705  mov     [rsp+0A0h+FileAttributes], 80h; FileAttributes
0x18007d70d  mov     [rsp+0A0h+AllocationSize], rax; AllocationSize
0x18007d712  mov     [rbp+57h+FileHandle], 0
0x18007d71a  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18007d71e  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18007d726  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x18007d72e  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x18007d732  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18007d737  call    cs:__imp_ZwCreateFile
0x18007d73e  nop     dword ptr [rax+rax+00h]
0x18007d743  mov     ebx, eax
0x18007d745  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18007d749  shr     ebx, 1Fh
0x18007d74c  xor     bl, 1
0x18007d74f  test    rcx, rcx
0x18007d752  jz      short loc_18007D760
0x18007d754  call    cs:__imp_ZwClose
0x18007d75b  nop     dword ptr [rax+rax+00h]
0x18007d760  mov     al, bl
0x18007d762  mov     rbx, [rsp+0A0h+arg_0]
0x18007d76a  add     rsp, 0A0h
0x18007d771  pop     rbp
0x18007d772  retn
```
