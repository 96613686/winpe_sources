# DsRolepRemoveDirectoryOrLink

- ea: `0x18000d8fc`
- end: `0x18000da46`
- name: `DsRolepRemoveDirectoryOrLink`
- size: `330`
- prototype: `ULONG __fastcall(PCWSTR DosPathName)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000d304`

## callees

- `0x18000d8fc`
- `0x180020dbc`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000d935`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000d935`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000d943`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000d943`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d94d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d94d`
- `ntdll!NtOpenFile` at `0x18000d9c5`
- `ntdll!NtOpenFile` at `0x18000d9c5`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18000d96d`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18000d96d`
- `ntdll!NtSetInformationFile` at `0x18000d9eb`
- `ntdll!NtSetInformationFile` at `0x18000d9eb`
- `ntdll!RtlFreeUnicodeString` at `0x18000da08`
- `ntdll!RtlFreeUnicodeString` at `0x18000da08`
- `ntdll!RtlNtStatusToDosError` at `0x18000da2b`
- `ntdll!RtlNtStatusToDosError` at `0x18000da2b`
- `ntdll!NtClose` at `0x18000d9f7`
- `ntdll!NtClose` at `0x18000d9f7`

## string_xrefs

- `0x18000da15`: `Failed to delete %ws: 0x%lx\n`

## pseudocode

```c
ULONG __fastcall DsRolepRemoveDirectoryOrLink(PCWSTR DosPathName)
{
  DWORD FileAttributesW; // eax
  int v4; // ebx
  struct _UNICODE_STRING NtPathName; // [rsp+30h] [rbp-50h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  char FileInformation; // [rsp+98h] [rbp+18h] BYREF
  void *FileHandle; // [rsp+A0h] [rbp+20h] BYREF

  FileInformation = 1;
  FileHandle = 0;
  NtPathName = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  FileAttributesW = GetFileAttributesW(DosPathName);
  if ( !SetFileAttributesW(DosPathName, FileAttributesW & 0xFFFFFFF8) )
    return GetLastError();
  NtPathName.Buffer = 0;
  if ( RtlDosPathNameToNtPathName_U(DosPathName, &NtPathName, 0, 0) )
  {
    ObjectAttributes.ObjectName = &NtPathName;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v4 = NtOpenFile(&FileHandle, 0x110001u, &ObjectAttributes, &IoStatusBlock, 7u, 0x204020u);
    if ( v4 >= 0 )
    {
      v4 = NtSetInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 1u, FileDispositionInformation);
      NtClose(FileHandle);
    }
  }
  else
  {
    v4 = -1073741670;
  }
  if ( NtPathName.Buffer )
    RtlFreeUnicodeString(&NtPathName);
  if ( v4 < 0 )
    DsRolepLogPrintRoutine(1, "Failed to delete %ws: 0x%lx\n", DosPathName, (unsigned int)v4);
  return RtlNtStatusToDosError(v4);
}

```

## disassembly

```asm
0x18000d8fc  mov     [rsp-8+arg_0], rbx
0x18000d901  mov     [rsp-8+arg_18], rdi
0x18000d906  push    rbp
0x18000d907  mov     rbp, rsp
0x18000d90a  sub     rsp, 80h
0x18000d911  xorps   xmm0, xmm0
0x18000d914  mov     [rbp+FileInformation], 1
0x18000d918  xor     eax, eax
0x18000d91a  mov     rdi, rcx
0x18000d91d  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18000d921  mov     [rbp+FileHandle], rax
0x18000d925  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x18000d929  movups  xmmword ptr [rbp+NtPathName.Length], xmm0
0x18000d92d  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18000d931  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x18000d935  call    cs:__imp_GetFileAttributesW
0x18000d93b  and     eax, 0FFFFFFF8h
0x18000d93e  mov     rcx, rdi; lpFileName
0x18000d941  mov     edx, eax; dwFileAttributes
0x18000d943  call    cs:__imp_SetFileAttributesW
0x18000d949  test    eax, eax
0x18000d94b  jnz     short loc_18000D958
0x18000d94d  call    cs:__imp_GetLastError
0x18000d953  jmp     loc_18000DA31
0x18000d958  xor     r9d, r9d; DirectoryInfo
0x18000d95b  mov     [rbp+NtPathName.Buffer], 0
0x18000d963  xor     r8d, r8d; NtFileNamePart
0x18000d966  lea     rdx, [rbp+NtPathName]; NtPathName
0x18000d96a  mov     rcx, rdi; DosPathName
0x18000d96d  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x18000d973  test    al, al
0x18000d975  jnz     short loc_18000D97E
0x18000d977  mov     ebx, 0C000009Ah
0x18000d97c  jmp     short loc_18000D9FD
0x18000d97e  lea     rax, [rbp+NtPathName]
0x18000d982  mov     [rsp+80h+OpenOptions], 204020h; OpenOptions
0x18000d98a  xorps   xmm0, xmm0
0x18000d98d  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18000d991  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x18000d995  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18000d99c  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18000d9a0  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18000d9a8  mov     edx, 110001h; DesiredAccess
0x18000d9ad  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18000d9b4  lea     rcx, [rbp+FileHandle]; FileHandle
0x18000d9b8  mov     [rsp+80h+ShareAccess], 7; ShareAccess
0x18000d9c0  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18000d9c5  call    cs:__imp_NtOpenFile
0x18000d9cb  mov     ebx, eax
0x18000d9cd  test    eax, eax
0x18000d9cf  js      short loc_18000D9FD
0x18000d9d1  mov     rcx, [rbp+FileHandle]; FileHandle
0x18000d9d5  lea     r8, [rbp+FileInformation]; FileInformation
0x18000d9d9  mov     r9d, 1; Length
0x18000d9df  mov     [rsp+80h+ShareAccess], 0Dh; FileInformationClass
0x18000d9e7  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x18000d9eb  call    cs:__imp_NtSetInformationFile
0x18000d9f1  mov     rcx, [rbp+FileHandle]; Handle
0x18000d9f5  mov     ebx, eax
0x18000d9f7  call    cs:__imp_NtClose
0x18000d9fd  cmp     [rbp+NtPathName.Buffer], 0
0x18000da02  jz      short loc_18000DA0E
0x18000da04  lea     rcx, [rbp+NtPathName]; UnicodeString
0x18000da08  call    cs:__imp_RtlFreeUnicodeString
0x18000da0e  test    ebx, ebx
0x18000da10  jns     short loc_18000DA29
0x18000da12  mov     r9d, ebx
0x18000da15  lea     rdx, aFailedToDelete_4; "Failed to delete %ws: 0x%lx\n"
0x18000da1c  mov     r8, rdi
0x18000da1f  mov     ecx, 1
0x18000da24  call    DsRolepLogPrintRoutine
0x18000da29  mov     ecx, ebx; Status
0x18000da2b  call    cs:__imp_RtlNtStatusToDosError
0x18000da31  lea     r11, [rsp+80h+var_s0]
0x18000da39  mov     rbx, [r11+10h]
0x18000da3d  mov     rdi, [r11+28h]
0x18000da41  mov     rsp, r11
0x18000da44  pop     rbp
0x18000da45  retn
```
