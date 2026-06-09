# BfsOpenPolicyRootDirectory

- ea: `0x140003e44`
- end: `0x140003f68`
- name: `BfsOpenPolicyRootDirectory`
- size: `292`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14001f078`

## callees

- `0x140001008`
- `0x140003e44`
- `0x140013860`

## import_xrefs

- `ntoskrnl!ZwCreateFile` at `0x140003ef6`
- `ntoskrnl!ZwCreateFile` at `0x140003ef6`

## pseudocode

```c
__int64 __fastcall BfsOpenPolicyRootDirectory(struct _UNICODE_STRING *a1, void **a2)
{
  NTSTATUS v3; // eax
  __int64 v4; // r8
  __int64 v5; // r9
  unsigned int v6; // ebx
  int AllocationSize; // [rsp+20h] [rbp-79h]
  NTSTATUS v9; // [rsp+60h] [rbp-39h] BYREF
  void *FileHandle; // [rsp+68h] [rbp-31h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-29h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A0h] [rbp+7h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v13; // [rsp+B0h] [rbp+17h] BYREF
  NTSTATUS *v14; // [rsp+D0h] [rbp+37h]
  __int64 v15; // [rsp+D8h] [rbp+3Fh]

  *a2 = 0;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = a1;
  FileHandle = 0;
  IoStatusBlock = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  ObjectAttributes.SecurityDescriptor = gBfsPolicyStorageDirectoryDescriptor;
  ObjectAttributes.SecurityQualityOfService = 0;
  v3 = ZwCreateFile(&FileHandle, 0x100047u, &ObjectAttributes, &IoStatusBlock, 0, 0x10u, 3u, 3u, 0x21u, 0, 0);
  v6 = v3;
  if ( v3 >= 0 )
  {
    *a2 = FileHandle;
  }
  else if ( (unsigned int)dword_140019000 > 3 )
  {
    v9 = v3;
    v15 = 4;
    v14 = &v9;
    tlgWriteTransfer_EtwWriteTransfer(
      (unsigned int)dword_140019000,
      (unsigned __int8 *)&byte_140016D91,
      v4,
      v5,
      AllocationSize,
      &v13);
  }
  return v6;
}

```

## disassembly

```asm
0x140003e44  mov     [rsp-8+arg_10], rbx
0x140003e49  mov     [rsp-8+arg_18], rdi
0x140003e4e  push    rbp
0x140003e4f  lea     rbp, [rsp-57h]
0x140003e54  sub     rsp, 0F0h
0x140003e5b  mov     rax, cs:__security_cookie
0x140003e62  xor     rax, rsp
0x140003e65  mov     [rbp+57h+var_10], rax
0x140003e69  mov     [rsp+0F0h+EaLength], 0; EaLength
0x140003e71  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140003e75  mov     [rsp+0F0h+EaBuffer], 0; EaBuffer
0x140003e7e  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140003e82  xor     eax, eax
0x140003e84  mov     [rsp+0F0h+CreateOptions], 21h ; '!'; CreateOptions
0x140003e8c  mov     [rsp+0F0h+CreateDisposition], 3; CreateDisposition
0x140003e94  mov     rdi, rdx
0x140003e97  mov     [rdx], rax
0x140003e9a  xorps   xmm0, xmm0
0x140003e9d  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x140003ea1  mov     edx, 100047h; DesiredAccess
0x140003ea6  mov     [rsp+0F0h+ShareAccess], 3; ShareAccess
0x140003eae  lea     rax, gBfsPolicyStorageDirectoryDescriptor
0x140003eb5  mov     [rbp+57h+ObjectAttributes.ObjectName], rcx
0x140003eb9  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x140003ebd  mov     [rsp+0F0h+FileAttributes], 10h; FileAttributes
0x140003ec5  mov     [rsp+0F0h+AllocationSize], 0; int
0x140003ece  mov     [rbp+57h+FileHandle], 0
0x140003ed6  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140003eda  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140003ee2  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x140003eea  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], rax
0x140003eee  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], 0
0x140003ef6  call    cs:__imp_ZwCreateFile
0x140003efd  nop     dword ptr [rax+rax+00h]
0x140003f02  mov     ebx, eax
0x140003f04  test    eax, eax
0x140003f06  jns     short loc_140003F3D
0x140003f08  mov     ecx, cs:dword_140019000; int
0x140003f0e  cmp     ecx, 3
0x140003f11  jbe     short loc_140003F44
0x140003f13  mov     [rbp+57h+var_90], eax
0x140003f16  lea     rdx, byte_140016D91; int
0x140003f1d  lea     rax, [rbp+57h+var_90]
0x140003f21  mov     [rbp+57h+var_18], 4
0x140003f29  mov     [rbp+57h+var_20], rax
0x140003f2d  lea     rax, [rbp+57h+var_40]
0x140003f31  mov     qword ptr [rsp+0F0h+FileAttributes], rax; PEVENT_DATA_DESCRIPTOR
0x140003f36  call    _tlgWriteTransfer_EtwWriteTransfer
0x140003f3b  jmp     short loc_140003F44
0x140003f3d  mov     rax, [rbp+57h+FileHandle]
0x140003f41  mov     [rdi], rax
0x140003f44  mov     eax, ebx
0x140003f46  mov     rcx, [rbp+57h+var_10]
0x140003f4a  xor     rcx, rsp; StackCookie
0x140003f4d  call    __security_check_cookie
0x140003f52  lea     r11, [rsp+0F0h+var_s0]
0x140003f5a  mov     rbx, [r11+20h]
0x140003f5e  mov     rdi, [r11+28h]
0x140003f62  mov     rsp, r11
0x140003f65  pop     rbp
0x140003f66  retn
```
