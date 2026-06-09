# SIPolicyPmDoesPolicyExist

- ea: `0x18007c108`
- end: `0x18007c1c4`
- name: `SIPolicyPmDoesPolicyExist`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18007ccdc`

## callees

- `0x18007c108`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x18007c1a4`
- `ntoskrnl!ZwClose` at `0x18007c1a4`
- `ntoskrnl!ZwCreateFile` at `0x18007c187`
- `ntoskrnl!ZwCreateFile` at `0x18007c187`

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
0x18007c108  mov     [rsp-8+arg_0], rbx
0x18007c10d  push    rbp
0x18007c10e  lea     rbp, [rsp-57h]
0x18007c113  sub     rsp, 0A0h
0x18007c11a  xor     eax, eax
0x18007c11c  mov     [rbp+57h+ObjectAttributes.ObjectName], rdx
0x18007c120  mov     [rsp+0A0h+EaLength], eax; EaLength
0x18007c124  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18007c128  mov     [rsp+0A0h+EaBuffer], rax; EaBuffer
0x18007c12d  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18007c131  mov     [rsp+0A0h+CreateOptions], 20h ; ' '; CreateOptions
0x18007c139  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18007c13d  mov     [rsp+0A0h+CreateDisposition], 1; CreateDisposition
0x18007c145  xorps   xmm0, xmm0
0x18007c148  mov     [rsp+0A0h+ShareAccess], 3; ShareAccess
0x18007c150  mov     edx, 120089h; DesiredAccess
0x18007c155  mov     [rsp+0A0h+FileAttributes], 80h; FileAttributes
0x18007c15d  mov     [rsp+0A0h+AllocationSize], rax; AllocationSize
0x18007c162  mov     [rbp+57h+FileHandle], 0
0x18007c16a  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18007c16e  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18007c176  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x18007c17e  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x18007c182  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18007c187  call    cs:__imp_ZwCreateFile
0x18007c18e  nop     dword ptr [rax+rax+00h]
0x18007c193  mov     ebx, eax
0x18007c195  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18007c199  shr     ebx, 1Fh
0x18007c19c  xor     bl, 1
0x18007c19f  test    rcx, rcx
0x18007c1a2  jz      short loc_18007C1B0
0x18007c1a4  call    cs:__imp_ZwClose
0x18007c1ab  nop     dword ptr [rax+rax+00h]
0x18007c1b0  mov     al, bl
0x18007c1b2  mov     rbx, [rsp+0A0h+arg_0]
0x18007c1ba  add     rsp, 0A0h
0x18007c1c1  pop     rbp
0x18007c1c2  retn
```
