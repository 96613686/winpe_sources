# OpenDevice(_UNICODE_STRING *)

- ea: `0x180032550`
- end: `0x1800325d6`
- name: `?OpenDevice@@YAPEAXPEAU_UNICODE_STRING@@@Z`
- size: `134`
- prototype: `void *__fastcall(struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180032398`

## callees

- `0x180032550`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800325c6`
- `KERNEL32!SetLastError` at `0x1800325c6`
- `ntdll!RtlNtStatusToDosError` at `0x1800325be`
- `ntdll!RtlNtStatusToDosError` at `0x1800325be`
- `ntdll!NtOpenFile` at `0x1800325aa`
- `ntdll!NtOpenFile` at `0x1800325aa`

## pseudocode

```c
void *__fastcall OpenDevice(struct _UNICODE_STRING *a1)
{
  NTSTATUS v1; // eax
  ULONG v2; // eax
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+30h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *FileHandle; // [rsp+80h] [rbp+10h] BYREF

  ObjectAttributes.ObjectName = a1;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  FileHandle = 0;
  IoStatusBlock = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v1 = NtOpenFile(&FileHandle, 0x12019Fu, &ObjectAttributes, &IoStatusBlock, 7u, 0x20u);
  if ( v1 )
  {
    FileHandle = 0;
    v2 = RtlNtStatusToDosError(v1);
    SetLastError(v2);
  }
  return FileHandle;
}

```

## disassembly

```asm
0x180032550  push    rbp
0x180032552  mov     rbp, rsp
0x180032555  sub     rsp, 70h
0x180032559  xorps   xmm0, xmm0
0x18003255c  mov     [rbp+ObjectAttributes.ObjectName], rcx
0x180032560  lea     rcx, [rbp+FileHandle]; FileHandle
0x180032564  mov     [rsp+70h+OpenOptions], 20h ; ' '; OpenOptions
0x18003256c  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x180032570  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x180032578  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18003257c  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180032584  mov     edx, 12019Fh; DesiredAccess
0x180032589  mov     [rbp+FileHandle], 0
0x180032591  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x180032595  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18003259d  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800325a2  mov     [rsp+70h+ShareAccess], 7; ShareAccess
0x1800325aa  call    cs:__imp_NtOpenFile
0x1800325b0  test    eax, eax
0x1800325b2  jz      short loc_1800325CC
0x1800325b4  mov     ecx, eax; Status
0x1800325b6  mov     [rbp+FileHandle], 0
0x1800325be  call    cs:__imp_RtlNtStatusToDosError
0x1800325c4  mov     ecx, eax; dwErrCode
0x1800325c6  call    cs:__imp_SetLastError
0x1800325cc  mov     rax, [rbp+FileHandle]
0x1800325d0  add     rsp, 70h
0x1800325d4  pop     rbp
0x1800325d5  retn
```
