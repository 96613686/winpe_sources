# OpenDevice

- ea: `0x180032f74`
- end: `0x180032ff2`
- name: `OpenDevice`
- size: `126`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180032ce4`

## callees

- `0x180032f74`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180032fe2`
- `KERNEL32!SetLastError` at `0x180032fe2`
- `ntdll!RtlNtStatusToDosError` at `0x180032fda`
- `ntdll!RtlNtStatusToDosError` at `0x180032fda`
- `ntdll!NtOpenFile` at `0x180032fce`
- `ntdll!NtOpenFile` at `0x180032fce`

## pseudocode

```c
void *__fastcall OpenDevice(struct _UNICODE_STRING *a1)
{
  NTSTATUS v1; // eax
  ULONG v2; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
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
0x180032f74  push    rbp
0x180032f76  mov     rbp, rsp
0x180032f79  sub     rsp, 70h
0x180032f7d  xorps   xmm0, xmm0
0x180032f80  mov     [rbp+ObjectAttributes.ObjectName], rcx
0x180032f84  lea     rcx, [rbp+FileHandle]; FileHandle
0x180032f88  mov     [rsp+70h+OpenOptions], 20h ; ' '; OpenOptions
0x180032f90  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x180032f94  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x180032f9c  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180032fa0  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180032fa8  mov     edx, 12019Fh; DesiredAccess
0x180032fad  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180032fb5  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180032fba  mov     [rbp+FileHandle], 0
0x180032fc2  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x180032fc6  mov     [rsp+70h+ShareAccess], 7; ShareAccess
0x180032fce  call    cs:__imp_NtOpenFile
0x180032fd4  test    eax, eax
0x180032fd6  jz      short loc_180032FE8
0x180032fd8  mov     ecx, eax; Status
0x180032fda  call    cs:__imp_RtlNtStatusToDosError
0x180032fe0  mov     ecx, eax; dwErrCode
0x180032fe2  call    cs:__imp_SetLastError
0x180032fe8  mov     rax, [rbp+FileHandle]
0x180032fec  add     rsp, 70h
0x180032ff0  pop     rbp
0x180032ff1  retn
```
