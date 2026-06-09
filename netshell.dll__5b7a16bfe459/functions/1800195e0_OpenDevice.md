# OpenDevice

- ea: `0x1800195e0`
- end: `0x18001965e`
- name: `OpenDevice`
- size: `126`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000a2ec`
- `0x1800601a0`

## callees

- `0x1800195e0`

## import_xrefs

- `ntdll!NtOpenFile` at `0x18001963a`
- `ntdll!NtOpenFile` at `0x18001963a`
- `ntdll!RtlNtStatusToDosError` at `0x180019646`
- `ntdll!RtlNtStatusToDosError` at `0x180019646`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001964e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001964e`

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
0x1800195e0  push    rbp
0x1800195e2  mov     rbp, rsp
0x1800195e5  sub     rsp, 70h
0x1800195e9  xorps   xmm0, xmm0
0x1800195ec  mov     [rbp+ObjectAttributes.ObjectName], rcx
0x1800195f0  lea     rcx, [rbp+FileHandle]; FileHandle
0x1800195f4  mov     [rsp+70h+OpenOptions], 20h ; ' '; OpenOptions
0x1800195fc  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x180019600  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x180019608  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18001960c  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180019614  mov     edx, 12019Fh; DesiredAccess
0x180019619  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180019621  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180019626  mov     [rbp+FileHandle], 0
0x18001962e  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x180019632  mov     [rsp+70h+ShareAccess], 7; ShareAccess
0x18001963a  call    cs:__imp_NtOpenFile
0x180019640  test    eax, eax
0x180019642  jz      short loc_180019654
0x180019644  mov     ecx, eax; Status
0x180019646  call    cs:__imp_RtlNtStatusToDosError
0x18001964c  mov     ecx, eax; dwErrCode
0x18001964e  call    cs:__imp_SetLastError
0x180019654  mov     rax, [rbp+FileHandle]
0x180019658  add     rsp, 70h
0x18001965c  pop     rbp
0x18001965d  retn
```
