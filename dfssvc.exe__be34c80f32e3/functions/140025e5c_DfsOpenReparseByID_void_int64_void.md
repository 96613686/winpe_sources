# DfsOpenReparseByID(void *,__int64,void * *)

- ea: `0x140025e5c`
- end: `0x140025f12`
- name: `?DfsOpenReparseByID@@YAKPEAX_JPEAPEAX@Z`
- size: `182`
- prototype: `unsigned int(void *, __int64, void **)`
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14002634c`

## import_xrefs

- `ntdll!NtCreateFile` at `0x140025eee`
- `ntdll!NtCreateFile` at `0x140025eee`
- `ntdll!RtlNtStatusToDosError` at `0x140025efc`
- `ntdll!RtlNtStatusToDosError` at `0x140025efc`

## pseudocode

```c
ULONG __fastcall DfsOpenReparseByID(void *a1, __int64 a2, void **a3)
{
  NTSTATUS v3; // eax
  _QWORD v5[2]; // [rsp+68h] [rbp+7h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp+17h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp+27h] BYREF
  __int64 v8; // [rsp+D0h] [rbp+6Fh] BYREF

  v8 = a2;
  ObjectAttributes.RootDirectory = a1;
  v5[0] = 524296;
  *a3 = (void *)-1LL;
  v5[1] = &v8;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v5;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  IoStatusBlock = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v3 = NtCreateFile(a3, 0x100080u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 1u, 0x202001u, 0, 0);
  return RtlNtStatusToDosError(v3);
}

```

## disassembly

```asm
0x140025e5c  mov     r11, rsp
0x140025e5f  mov     [r11+10h], rdx
0x140025e63  push    rbp
0x140025e64  lea     rbp, [r11-5Fh]
0x140025e68  sub     rsp, 0B0h
0x140025e6f  mov     rax, r8
0x140025e72  mov     [rbp+57h+ObjectAttributes.RootDirectory], rcx
0x140025e76  xor     r8d, r8d
0x140025e79  mov     [rbp+57h+var_50], 80008h
0x140025e81  mov     [r11-68h], r8d
0x140025e85  lea     rdx, [rbp+57h+arg_8]
0x140025e89  mov     [r11-70h], r8
0x140025e8d  lea     rcx, [rbp+57h+var_50]
0x140025e91  or      qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x140025e95  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140025e99  mov     dword ptr [rsp+40h], 202001h; CreateOptions
0x140025ea1  xorps   xmm0, xmm0
0x140025ea4  mov     [rsp+0B0h+CreateDisposition], 1; CreateDisposition
0x140025eac  mov     [rsp+0B0h+ShareAccess], 7; ShareAccess
0x140025eb4  mov     [rbp+57h+var_48], rdx
0x140025eb8  mov     edx, 100080h; DesiredAccess
0x140025ebd  mov     [rbp+57h+ObjectAttributes.ObjectName], rcx
0x140025ec1  mov     rcx, rax; FileHandle
0x140025ec4  mov     [rsp+0B0h+FileAttributes], 80h; FileAttributes
0x140025ecc  mov     [rsp+0B0h+AllocationSize], r8; AllocationSize
0x140025ed1  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140025ed5  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140025edd  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x140025ee5  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140025ee9  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140025eee  call    cs:__imp_NtCreateFile
0x140025ef5  nop     dword ptr [rax+rax+00h]
0x140025efa  mov     ecx, eax; Status
0x140025efc  call    cs:__imp_RtlNtStatusToDosError
0x140025f03  nop     dword ptr [rax+rax+00h]
0x140025f08  add     rsp, 0B0h
0x140025f0f  pop     rbp
0x140025f10  retn
```
