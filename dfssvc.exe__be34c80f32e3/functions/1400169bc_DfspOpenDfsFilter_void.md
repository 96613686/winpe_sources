# DfspOpenDfsFilter(void * *)

- ea: `0x1400169bc`
- end: `0x140016a7d`
- name: `?DfspOpenDfsFilter@@YAKPEAPEAX@Z`
- size: `193`
- prototype: `unsigned int __fastcall(void **)`
- caller_count: `6`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400160c0`
- `0x140016204`
- `0x1400162c8`
- `0x14001648c`
- `0x14001668c`
- `0x140016c40`

## callees

- `0x1400169bc`

## import_xrefs

- `ntdll!NtOpenFile` at `0x140016a42`
- `ntdll!NtOpenFile` at `0x140016a42`
- `ntdll!RtlInitUnicodeString` at `0x1400169f2`
- `ntdll!RtlInitUnicodeString` at `0x1400169f2`
- `ntdll!RtlNtStatusToDosError` at `0x140016a54`
- `ntdll!RtlNtStatusToDosError` at `0x140016a54`

## pseudocode

```c
__int64 __fastcall DfspOpenDfsFilter(void **a1)
{
  unsigned int v2; // ecx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-50h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  void *FileHandle; // [rsp+90h] [rbp+10h] BYREF

  FileHandle = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  IoStatusBlock = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\DfsServer");
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v2 = NtOpenFile(&FileHandle, 0x100002u, &ObjectAttributes, &IoStatusBlock, 7u, 0x20u);
  if ( v2 )
    v2 = RtlNtStatusToDosError(v2);
  *a1 = FileHandle;
  return v2;
}

```

## disassembly

```asm
0x1400169bc  mov     [rsp-8+arg_8], rbx
0x1400169c1  push    rbp
0x1400169c2  mov     rbp, rsp
0x1400169c5  sub     rsp, 80h
0x1400169cc  and     [rbp+FileHandle], 0
0x1400169d1  lea     rdx, Source; "\\DfsServer"
0x1400169d8  and     dword ptr [rbp+ObjectAttributes+4], 0
0x1400169dc  xorps   xmm0, xmm0
0x1400169df  and     dword ptr [rbp+ObjectAttributes+1Ch], 0
0x1400169e3  mov     rbx, rcx
0x1400169e6  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400169ea  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x1400169ee  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400169f2  call    cs:__imp_RtlInitUnicodeString
0x1400169f9  nop     dword ptr [rax+rax+00h]
0x1400169fe  and     [rbp+ObjectAttributes.RootDirectory], 0
0x140016a03  lea     rax, [rbp+DestinationString]
0x140016a07  xorps   xmm0, xmm0
0x140016a0a  mov     [rsp+80h+OpenOptions], 20h ; ' '; OpenOptions
0x140016a12  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x140016a16  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140016a1a  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140016a1e  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140016a25  mov     edx, 100002h; DesiredAccess
0x140016a2a  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x140016a31  lea     rcx, [rbp+FileHandle]; FileHandle
0x140016a35  mov     [rsp+80h+ShareAccess], 7; ShareAccess
0x140016a3d  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140016a42  call    cs:__imp_NtOpenFile
0x140016a49  nop     dword ptr [rax+rax+00h]
0x140016a4e  mov     ecx, eax; Status
0x140016a50  test    eax, eax
0x140016a52  jz      short loc_140016A62
0x140016a54  call    cs:__imp_RtlNtStatusToDosError
0x140016a5b  nop     dword ptr [rax+rax+00h]
0x140016a60  mov     ecx, eax
0x140016a62  mov     rax, [rbp+FileHandle]
0x140016a66  mov     [rbx], rax
0x140016a69  mov     eax, ecx
0x140016a6b  mov     rbx, [rsp+80h+arg_8]
0x140016a73  add     rsp, 80h
0x140016a7a  pop     rbp
0x140016a7b  retn
```
