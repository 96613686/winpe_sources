# BfsOpenPolicyDirectory

- ea: `0x140008ecc`
- end: `0x14000900d`
- name: `BfsOpenPolicyDirectory`
- size: `321`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140007fec`
- `0x140008728`
- `0x140009014`
- `0x1400092a4`
- `0x14000a64c`
- `0x14000ceb4`

## callees

- `0x140001008`
- `0x140008ecc`
- `0x140013860`
- `0x14001e008`

## import_xrefs

- `FLTMGR!FltCreateFileEx2` at `0x140008fa5`
- `FLTMGR!FltCreateFileEx2` at `0x140008fa5`

## pseudocode

```c
__int64 __fastcall BfsOpenPolicyDirectory(__int64 a1, __int64 a2, __int64 a3, __int64 a4, void **a5)
{
  char v5; // r9
  struct _UNICODE_STRING *v6; // r8
  PFLT_INSTANCE v7; // rdx
  PFLT_FILTER v8; // rcx
  NTSTATUS v9; // eax
  __int64 v10; // r8
  __int64 v11; // r9
  unsigned int v12; // ebx
  ACCESS_MASK DesiredAccess; // [rsp+20h] [rbp-E0h]
  NTSTATUS v15; // [rsp+80h] [rbp-80h] BYREF
  void *FileHandle; // [rsp+88h] [rbp-78h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-70h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C0h] [rbp-40h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v19; // [rsp+D0h] [rbp-30h] BYREF
  NTSTATUS *v20; // [rsp+F0h] [rbp-10h]
  __int64 v21; // [rsp+F8h] [rbp-8h]

  FileHandle = 0;
  IoStatusBlock = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *a5 = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  ObjectAttributes.RootDirectory = (HANDLE)BfsGetRootDirectory();
  ObjectAttributes.SecurityDescriptor = gBfsPolicyStorageDirectoryDescriptor;
  ObjectAttributes.ObjectName = v6;
  ObjectAttributes.SecurityQualityOfService = 0;
  v9 = FltCreateFileEx2(
         v8,
         v7,
         &FileHandle,
         0,
         0x100047u,
         &ObjectAttributes,
         &IoStatusBlock,
         0,
         0x10u,
         3u,
         v5 != 0 ? 1 : 3,
         0x21u,
         0,
         0,
         0x100u,
         0);
  v12 = v9;
  if ( v9 >= 0 )
  {
    *a5 = FileHandle;
  }
  else if ( (unsigned int)dword_140019000 > 3 )
  {
    v15 = v9;
    v21 = 4;
    v20 = &v15;
    tlgWriteTransfer_EtwWriteTransfer(
      (unsigned int)dword_140019000,
      (unsigned __int8 *)&byte_140016D91,
      v10,
      v11,
      DesiredAccess,
      &v19);
  }
  return v12;
}

```

## disassembly

```asm
0x140008ecc  push    rbp
0x140008ece  push    rbx
0x140008ecf  push    rdi
0x140008ed0  lea     rbp, [rsp-10h]
0x140008ed5  sub     rsp, 110h
0x140008edc  mov     rax, cs:__security_cookie
0x140008ee3  xor     rax, rsp
0x140008ee6  mov     [rbp+20h+var_20], rax
0x140008eea  mov     rdi, [rbp+20h+arg_20]
0x140008eee  xor     eax, eax
0x140008ef0  xorps   xmm0, xmm0
0x140008ef3  mov     [rbp+20h+FileHandle], 0
0x140008efb  movups  xmmword ptr [rbp+20h+var_60], xmm0
0x140008eff  mov     qword ptr [rbp+20h+var_90.Length], 30h ; '0'
0x140008f07  mov     [rdi], rax
0x140008f0a  mov     qword ptr [rbp+20h+var_90.Attributes], 240h
0x140008f12  call    BfsGetRootDirectory
0x140008f17  mov     [rsp+120h+DriverContext], 0; DriverContext
0x140008f20  neg     r9b
0x140008f23  mov     [rsp+120h+Flags], 100h; Flags
0x140008f2b  mov     [rsp+120h+EaLength], 0; EaLength
0x140008f33  mov     [rsp+120h+EaBuffer], 0; EaBuffer
0x140008f3c  mov     [rbp+20h+var_90.RootDirectory], rax
0x140008f40  lea     rax, gBfsPolicyStorageDirectoryDescriptor
0x140008f47  mov     [rsp+120h+CreateOptions], 21h ; '!'; CreateOptions
0x140008f4f  mov     [rbp+20h+var_90.SecurityDescriptor], rax
0x140008f53  sbb     eax, eax
0x140008f55  and     eax, 0FFFFFFFEh
0x140008f58  mov     [rbp+20h+var_90.ObjectName], r8
0x140008f5c  add     eax, 3
0x140008f5f  mov     [rbp+20h+var_90.SecurityQualityOfService], 0
0x140008f67  mov     [rsp+120h+CreateDisposition], eax; CreateDisposition
0x140008f6b  lea     r8, [rbp+20h+FileHandle]; FileHandle
0x140008f6f  mov     [rsp+120h+ShareAccess], 3; ShareAccess
0x140008f77  lea     rax, [rbp+20h+var_60]
0x140008f7b  mov     [rsp+120h+FileAttributes], 10h; FileAttributes
0x140008f83  xor     r9d, r9d; FileObject
0x140008f86  mov     [rsp+120h+AllocationSize], 0; AllocationSize
0x140008f8f  mov     [rsp+120h+IoStatusBlock], rax; IoStatusBlock
0x140008f94  lea     rax, [rbp+20h+var_90]
0x140008f98  mov     [rsp+120h+ObjectAttributes], rax; ObjectAttributes
0x140008f9d  mov     [rsp+120h+DesiredAccess], 100047h; int
0x140008fa5  call    cs:__imp_FltCreateFileEx2
0x140008fac  nop     dword ptr [rax+rax+00h]
0x140008fb1  mov     ebx, eax
0x140008fb3  test    eax, eax
0x140008fb5  jns     short loc_140008FEC
0x140008fb7  mov     ecx, cs:dword_140019000; int
0x140008fbd  cmp     ecx, 3
0x140008fc0  jbe     short loc_140008FF3
0x140008fc2  mov     [rbp+20h+var_A0], eax
0x140008fc5  lea     rdx, byte_140016D91; int
0x140008fcc  lea     rax, [rbp+20h+var_A0]
0x140008fd0  mov     [rbp+20h+var_28], 4
0x140008fd8  mov     [rbp+20h+var_30], rax
0x140008fdc  lea     rax, [rbp+20h+var_50]
0x140008fe0  mov     [rsp+120h+ObjectAttributes], rax; PEVENT_DATA_DESCRIPTOR
0x140008fe5  call    _tlgWriteTransfer_EtwWriteTransfer
0x140008fea  jmp     short loc_140008FF3
0x140008fec  mov     rax, [rbp+20h+FileHandle]
0x140008ff0  mov     [rdi], rax
0x140008ff3  mov     eax, ebx
0x140008ff5  mov     rcx, [rbp+20h+var_20]
0x140008ff9  xor     rcx, rsp; StackCookie
0x140008ffc  call    __security_check_cookie
0x140009001  add     rsp, 110h
0x140009008  pop     rdi
0x140009009  pop     rbx
0x14000900a  pop     rbp
0x14000900b  retn
```
