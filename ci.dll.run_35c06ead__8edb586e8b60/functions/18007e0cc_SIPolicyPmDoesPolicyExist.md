# SIPolicyPmDoesPolicyExist

- ea: `0x18007e0cc`
- end: `0x18007e188`
- name: `SIPolicyPmDoesPolicyExist`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18007eca0`

## callees

- `0x18007e0cc`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x18007e168`
- `ntoskrnl!ZwClose` at `0x18007e168`
- `ntoskrnl!ZwCreateFile` at `0x18007e14b`
- `ntoskrnl!ZwCreateFile` at `0x18007e14b`

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
0x18007e0cc  mov     [rsp-8+arg_0], rbx
0x18007e0d1  push    rbp
0x18007e0d2  lea     rbp, [rsp-57h]
0x18007e0d7  sub     rsp, 0A0h
0x18007e0de  xor     eax, eax
0x18007e0e0  mov     [rbp+57h+ObjectAttributes.ObjectName], rdx
0x18007e0e4  mov     [rsp+0A0h+EaLength], eax; EaLength
0x18007e0e8  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18007e0ec  mov     [rsp+0A0h+EaBuffer], rax; EaBuffer
0x18007e0f1  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18007e0f5  mov     [rsp+0A0h+CreateOptions], 20h ; ' '; CreateOptions
0x18007e0fd  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18007e101  mov     [rsp+0A0h+CreateDisposition], 1; CreateDisposition
0x18007e109  xorps   xmm0, xmm0
0x18007e10c  mov     [rsp+0A0h+ShareAccess], 3; ShareAccess
0x18007e114  mov     edx, 120089h; DesiredAccess
0x18007e119  mov     [rsp+0A0h+FileAttributes], 80h; FileAttributes
0x18007e121  mov     [rsp+0A0h+AllocationSize], rax; AllocationSize
0x18007e126  mov     [rbp+57h+FileHandle], 0
0x18007e12e  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18007e132  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18007e13a  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x18007e142  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x18007e146  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18007e14b  call    cs:__imp_ZwCreateFile
0x18007e152  nop     dword ptr [rax+rax+00h]
0x18007e157  mov     ebx, eax
0x18007e159  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18007e15d  shr     ebx, 1Fh
0x18007e160  xor     bl, 1
0x18007e163  test    rcx, rcx
0x18007e166  jz      short loc_18007E174
0x18007e168  call    cs:__imp_ZwClose
0x18007e16f  nop     dword ptr [rax+rax+00h]
0x18007e174  mov     al, bl
0x18007e176  mov     rbx, [rsp+0A0h+arg_0]
0x18007e17e  add     rsp, 0A0h
0x18007e185  pop     rbp
0x18007e186  retn
```
