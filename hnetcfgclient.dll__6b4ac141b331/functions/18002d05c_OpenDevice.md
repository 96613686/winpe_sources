# OpenDevice

- ea: `0x18002d05c`
- end: `0x18002d0da`
- name: `OpenDevice`
- size: `126`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002cdcc`

## callees

- `0x18002d05c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d0ca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d0ca`
- `ntdll!RtlNtStatusToDosError` at `0x18002d0c2`
- `ntdll!RtlNtStatusToDosError` at `0x18002d0c2`
- `ntdll!NtOpenFile` at `0x18002d0b6`
- `ntdll!NtOpenFile` at `0x18002d0b6`

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
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  FileHandle = 0;
  IoStatusBlock = 0;
  v1 = NtOpenFile(&FileHandle, 0x12019Fu, &ObjectAttributes, &IoStatusBlock, 7u, 0x20u);
  if ( v1 )
  {
    v2 = RtlNtStatusToDosError(v1);
    SetLastError(v2);
  }
  return FileHandle;
}

```

## disassembly

```asm
0x18002d05c  push    rbp
0x18002d05e  mov     rbp, rsp
0x18002d061  sub     rsp, 70h
0x18002d065  xorps   xmm0, xmm0
0x18002d068  mov     [rbp+ObjectAttributes.ObjectName], rcx
0x18002d06c  lea     rcx, [rbp+FileHandle]; FileHandle
0x18002d070  mov     [rsp+70h+OpenOptions], 20h ; ' '; OpenOptions
0x18002d078  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x18002d07c  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x18002d084  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18002d088  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18002d090  mov     edx, 12019Fh; DesiredAccess
0x18002d095  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18002d09d  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18002d0a2  mov     [rbp+FileHandle], 0
0x18002d0aa  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x18002d0ae  mov     [rsp+70h+ShareAccess], 7; ShareAccess
0x18002d0b6  call    cs:__imp_NtOpenFile
0x18002d0bc  test    eax, eax
0x18002d0be  jz      short loc_18002D0D0
0x18002d0c0  mov     ecx, eax; Status
0x18002d0c2  call    cs:__imp_RtlNtStatusToDosError
0x18002d0c8  mov     ecx, eax; dwErrCode
0x18002d0ca  call    cs:__imp_SetLastError
0x18002d0d0  mov     rax, [rbp+FileHandle]
0x18002d0d4  add     rsp, 70h
0x18002d0d8  pop     rbp
0x18002d0d9  retn
```
