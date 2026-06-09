# WcpRemoveFile

- ea: `0x14000ecc4`
- end: `0x14000efca`
- name: `WcpRemoveFile`
- size: `774`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000aca8`
- `0x14000e5a8`

## callees

- `0x14000df1c`
- `0x14000df78`
- `0x14000ea6c`
- `0x14000eb48`
- `0x14000ecc4`
- `0x14000efd0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000ef87`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000ef87`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14000ef02`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14000ef02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ef29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ef29`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x14000ed4a`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x14000ed4a`
- `ntdll!RtlFreeUnicodeString` at `0x14000ef9e`
- `ntdll!RtlFreeUnicodeString` at `0x14000ef9e`
- `ntdll!NtSetInformationFile` at `0x14000ee1e`
- `ntdll!NtSetInformationFile` at `0x14000ee1e`
- `ntdll!NtClose` at `0x14000ee46`
- `ntdll!NtClose` at `0x14000ef6c`
- `ntdll!NtClose` at `0x14000ee46`
- `ntdll!NtClose` at `0x14000ef6c`
- `ntdll!RtlNtStatusToDosError` at `0x14000ed5c`
- `ntdll!RtlNtStatusToDosError` at `0x14000ee34`
- `ntdll!RtlNtStatusToDosError` at `0x14000ee64`
- `ntdll!RtlNtStatusToDosError` at `0x14000ed5c`
- `ntdll!RtlNtStatusToDosError` at `0x14000ee34`
- `ntdll!RtlNtStatusToDosError` at `0x14000ee64`
- `ntdll!NtOpenFile` at `0x14000edc6`
- `ntdll!NtOpenFile` at `0x14000edc6`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14000eec6`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14000eec6`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x14000eee4`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x14000eee4`

## pseudocode

```c
__int64 __fastcall WcpRemoveFile(__int64 a1, __int64 a2, __int64 a3, __int64 a4, char a5)
{
  __int64 v6; // rdi
  signed int v7; // ebx
  NTSTATUS v8; // eax
  signed int LastError; // eax
  int v10; // ebx
  DWORD v11; // r15d
  char v12; // r14
  int v13; // r12d
  int v14; // eax
  int v15; // eax
  signed int v16; // edi
  DWORD FileAttributesW; // eax
  DWORD v18; // eax
  LPCWSTR lpFileName; // [rsp+38h] [rbp-41h] BYREF
  void *FileHandle; // [rsp+40h] [rbp-39h] BYREF
  void *Block; // [rsp+48h] [rbp-31h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+50h] [rbp-29h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-19h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-9h] BYREF
  int FileInformation; // [rsp+F0h] [rbp+77h] BYREF

  FileInformation = 0;
  lpFileName = 0;
  *(_QWORD *)&UnicodeString.Length = 0;
  v6 = a2;
  FileHandle = 0;
  Block = 0;
  UnicodeString.Buffer = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  v7 = WcpConstructLongPath(a1, &Block, &lpFileName);
  if ( v7 < 0 )
    goto LABEL_39;
  v8 = RtlDosPathNameToNtPathName_U_WithStatus(lpFileName, &UnicodeString, 0, 0);
  if ( v8 < 0 )
  {
    LastError = RtlNtStatusToDosError(v8);
LABEL_4:
    v7 = LastError;
    if ( LastError > 0 )
    {
      v10 = (unsigned __int16)LastError;
      goto LABEL_38;
    }
    goto LABEL_39;
  }
  v11 = 0;
  ObjectAttributes.Length = 48;
  v12 = 0;
  ObjectAttributes.Attributes = 64;
  v13 = 0;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = &UnicodeString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  while ( 1 )
  {
    v14 = NtOpenFile(&FileHandle, 0x110000u, &ObjectAttributes, &IoStatusBlock, 7u, 0x204020u);
    if ( v14 < 0 )
    {
      v16 = RtlNtStatusToDosError(v14);
    }
    else
    {
      if ( !a5 )
      {
        v7 = EnsurePathNotRedirected(FileHandle, lpFileName, v6, a3);
        if ( v7 < 0 )
          goto LABEL_39;
      }
      FileInformation = 1;
      v15 = NtSetInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 4u, (FILE_INFORMATION_CLASS)64);
      if ( v15 >= 0 )
        goto LABEL_39;
      v16 = RtlNtStatusToDosError(v15);
      if ( NtClose(FileHandle) < 0 )
        __int2c();
      FileHandle = 0;
    }
    if ( !v16 )
      goto LABEL_39;
    if ( FileHandle )
      __int2c();
    if ( v16 == 32 || v16 == 145 )
      break;
    if ( v16 != 5 )
      goto LABEL_35;
    if ( v12 )
      goto LABEL_37;
    if ( (unsigned int)Feature_WcRemoveFileOwnershipTOCTOU__private_IsEnabledDeviceUsageNoInline() )
    {
      v7 = WcpPrivilegedRemoveFile(&ObjectAttributes);
      goto LABEL_39;
    }
    v7 = WcpTakeOwnership((LPWSTR)lpFileName);
    if ( v7 < 0 )
      goto LABEL_39;
    FileAttributesW = GetFileAttributesW(lpFileName);
    if ( FileAttributesW == -1
      || (FileAttributesW & 1) != 0 && !SetFileAttributesW(lpFileName, FileAttributesW & 0xFFFFFFFE) )
    {
      LastError = GetLastError();
      goto LABEL_4;
    }
    v12 = 1;
LABEL_32:
    v6 = a2;
  }
  if ( v13 != 25 )
  {
    Sleep(v11);
    v18 = v11 + 5;
    ++v13;
    if ( v11 >= 0x32 )
      v18 = v11;
    v11 = v18;
    goto LABEL_32;
  }
LABEL_35:
  if ( v16 <= 0 )
  {
    v7 = v16;
    goto LABEL_39;
  }
LABEL_37:
  v10 = (unsigned __int16)v16;
LABEL_38:
  v7 = v10 | 0x80070000;
LABEL_39:
  if ( FileHandle && NtClose(FileHandle) < 0 )
    __int2c();
  if ( Block )
    free(Block);
  if ( UnicodeString.Buffer )
    RtlFreeUnicodeString(&UnicodeString);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14000ecc4  mov     rax, rsp
0x14000ecc7  mov     [rax+8], rbx
0x14000eccb  mov     [rax+18h], rdi
0x14000eccf  mov     [rax+20h], r9b
0x14000ecd3  mov     [rax+10h], rdx
0x14000ecd7  push    rbp
0x14000ecd8  push    r12
0x14000ecda  push    r13
0x14000ecdc  push    r14
0x14000ecde  push    r15
0x14000ece0  lea     rbp, [rax-57h]
0x14000ece4  sub     rsp, 0A0h
0x14000eceb  xorps   xmm0, xmm0
0x14000ecee  mov     [rbp+4Fh+FileInformation], 0
0x14000ecf5  xor     eax, eax
0x14000ecf7  mov     [rbp+4Fh+lpFileName], 0
0x14000ecff  mov     r13, r8
0x14000ed02  mov     qword ptr [rbp+4Fh+UnicodeString.Length], rax
0x14000ed06  mov     rdi, rdx
0x14000ed09  mov     [rbp+4Fh+FileHandle], rax
0x14000ed0d  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x14000ed11  lea     r8, [rbp+4Fh+lpFileName]
0x14000ed15  mov     [rbp+4Fh+Block], rax
0x14000ed19  lea     rdx, [rbp+4Fh+Block]
0x14000ed1d  mov     [rbp+4Fh+UnicodeString.Buffer], rax
0x14000ed21  movups  xmmword ptr [rbp+4Fh+ObjectAttributes+1Ch], xmm0
0x14000ed25  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x14000ed29  movups  xmmword ptr [rbp+4Fh+IoStatusBlock], xmm0
0x14000ed2d  call    WcpConstructLongPath
0x14000ed32  mov     ebx, eax
0x14000ed34  test    eax, eax
0x14000ed36  js      loc_14000EF63
0x14000ed3c  mov     rcx, [rbp+4Fh+lpFileName]
0x14000ed40  lea     rdx, [rbp+4Fh+UnicodeString]
0x14000ed44  xor     r9d, r9d
0x14000ed47  xor     r8d, r8d
0x14000ed4a  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x14000ed51  nop     dword ptr [rax+rax+00h]
0x14000ed56  test    eax, eax
0x14000ed58  jns     short loc_14000ED7A
0x14000ed5a  mov     ecx, eax; Status
0x14000ed5c  call    cs:__imp_RtlNtStatusToDosError
0x14000ed63  nop     dword ptr [rax+rax+00h]
0x14000ed68  mov     ebx, eax
0x14000ed6a  test    eax, eax
0x14000ed6c  jle     loc_14000EF63
0x14000ed72  movzx   ebx, ax
0x14000ed75  jmp     loc_14000EF5D
0x14000ed7a  xor     r15d, r15d
0x14000ed7d  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x14000ed84  xor     r14b, r14b
0x14000ed87  mov     [rbp+4Fh+ObjectAttributes.Attributes], 40h ; '@'
0x14000ed8e  xor     r12d, r12d
0x14000ed91  lea     rax, [rbp+4Fh+UnicodeString]
0x14000ed95  xorps   xmm0, xmm0
0x14000ed98  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], r12
0x14000ed9c  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x14000eda0  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x14000eda5  mov     [rsp+0C0h+OpenOptions], 204020h; OpenOptions
0x14000edad  lea     r9, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x14000edb1  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x14000edb5  mov     [rsp+0C0h+ShareAccess], 7; ShareAccess
0x14000edbd  mov     edx, 110000h; DesiredAccess
0x14000edc2  lea     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x14000edc6  call    cs:__imp_NtOpenFile
0x14000edcd  nop     dword ptr [rax+rax+00h]
0x14000edd2  test    eax, eax
0x14000edd4  js      loc_14000EE62
0x14000edda  cmp     [rbp+4Fh+arg_20], 0
0x14000edde  jnz     short loc_14000EDFD
0x14000ede0  mov     rdx, [rbp+4Fh+lpFileName]
0x14000ede4  mov     r9, r13
0x14000ede7  mov     rcx, [rbp+4Fh+FileHandle]
0x14000edeb  mov     r8, rdi
0x14000edee  call    EnsurePathNotRedirected
0x14000edf3  mov     ebx, eax
0x14000edf5  test    eax, eax
0x14000edf7  js      loc_14000EF63
0x14000edfd  mov     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x14000ee01  lea     r8, [rbp+4Fh+FileInformation]; FileInformation
0x14000ee05  mov     r9d, 4; Length
0x14000ee0b  mov     [rbp+4Fh+FileInformation], 1
0x14000ee12  lea     rdx, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x14000ee16  mov     [rsp+0C0h+ShareAccess], 40h ; '@'; FileInformationClass
0x14000ee1e  call    cs:__imp_NtSetInformationFile
0x14000ee25  nop     dword ptr [rax+rax+00h]
0x14000ee2a  test    eax, eax
0x14000ee2c  jns     loc_14000EF63
0x14000ee32  mov     ecx, eax; Status
0x14000ee34  call    cs:__imp_RtlNtStatusToDosError
0x14000ee3b  nop     dword ptr [rax+rax+00h]
0x14000ee40  mov     rcx, [rbp+4Fh+FileHandle]; Handle
0x14000ee44  mov     edi, eax
0x14000ee46  call    cs:__imp_NtClose
0x14000ee4d  nop     dword ptr [rax+rax+00h]
0x14000ee52  test    eax, eax
0x14000ee54  jns     short loc_14000EE58
0x14000ee56  int     2Ch; Windows NT - assertion failure
0x14000ee58  mov     [rbp+4Fh+FileHandle], 0
0x14000ee60  jmp     short loc_14000EE72
0x14000ee62  mov     ecx, eax; Status
0x14000ee64  call    cs:__imp_RtlNtStatusToDosError
0x14000ee6b  nop     dword ptr [rax+rax+00h]
0x14000ee70  mov     edi, eax
0x14000ee72  test    edi, edi
0x14000ee74  jz      loc_14000EF63
0x14000ee7a  cmp     [rbp+4Fh+FileHandle], 0
0x14000ee7f  jz      short loc_14000EE83
0x14000ee81  int     2Ch; Windows NT - assertion failure
0x14000ee83  cmp     edi, 20h ; ' '
0x14000ee86  jz      short loc_14000EEF9
0x14000ee88  cmp     edi, 91h
0x14000ee8e  jz      short loc_14000EEF9
0x14000ee90  cmp     edi, 5
0x14000ee93  jnz     loc_14000EF52
0x14000ee99  test    r14b, r14b
0x14000ee9c  jnz     loc_14000EF5A
0x14000eea2  call    Feature_WcRemoveFileOwnershipTOCTOU__private_IsEnabledDeviceUsageNoInline
0x14000eea7  test    eax, eax
0x14000eea9  jnz     loc_14000EF3A
0x14000eeaf  mov     rcx, [rbp+4Fh+lpFileName]; pObjectName
0x14000eeb3  call    WcpTakeOwnership
0x14000eeb8  mov     ebx, eax
0x14000eeba  test    eax, eax
0x14000eebc  js      loc_14000EF63
0x14000eec2  mov     rcx, [rbp+4Fh+lpFileName]; lpFileName
0x14000eec6  call    cs:__imp_GetFileAttributesW
0x14000eecd  nop     dword ptr [rax+rax+00h]
0x14000eed2  cmp     eax, 0FFFFFFFFh
0x14000eed5  jz      short loc_14000EF29
0x14000eed7  test    al, 1
0x14000eed9  jz      short loc_14000EEF4
0x14000eedb  mov     rcx, [rbp+4Fh+lpFileName]; lpFileName
0x14000eedf  and     eax, 0FFFFFFFEh
0x14000eee2  mov     edx, eax; dwFileAttributes
0x14000eee4  call    cs:__imp_SetFileAttributesW
0x14000eeeb  nop     dword ptr [rax+rax+00h]
0x14000eef0  test    eax, eax
0x14000eef2  jz      short loc_14000EF29
0x14000eef4  mov     r14b, 1
0x14000eef7  jmp     short loc_14000EF20
0x14000eef9  cmp     r12d, 19h
0x14000eefd  jz      short loc_14000EF52
0x14000eeff  mov     ecx, r15d; dwMilliseconds
0x14000ef02  call    cs:__imp_Sleep
0x14000ef09  nop     dword ptr [rax+rax+00h]
0x14000ef0e  lea     eax, [r15+5]
0x14000ef12  inc     r12d
0x14000ef15  cmp     r15d, 32h ; '2'
0x14000ef19  cmovnb  eax, r15d
0x14000ef1d  mov     r15d, eax
0x14000ef20  mov     rdi, [rbp+4Fh+arg_8]
0x14000ef24  jmp     loc_14000EDA5
0x14000ef29  call    cs:__imp_GetLastError
0x14000ef30  nop     dword ptr [rax+rax+00h]
0x14000ef35  jmp     loc_14000ED68
0x14000ef3a  mov     r8, [rbp+4Fh+arg_8]
0x14000ef3e  lea     rcx, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x14000ef42  mov     rdx, [rbp+4Fh+lpFileName]
0x14000ef46  mov     r9, r13
0x14000ef49  call    WcpPrivilegedRemoveFile
0x14000ef4e  mov     ebx, eax
0x14000ef50  jmp     short loc_14000EF63
0x14000ef52  test    edi, edi
0x14000ef54  jg      short loc_14000EF5A
0x14000ef56  mov     ebx, edi
0x14000ef58  jmp     short loc_14000EF63
0x14000ef5a  movzx   ebx, di
0x14000ef5d  or      ebx, 80070000h
0x14000ef63  mov     rcx, [rbp+4Fh+FileHandle]; Handle
0x14000ef67  test    rcx, rcx
0x14000ef6a  jz      short loc_14000EF7E
0x14000ef6c  call    cs:__imp_NtClose
0x14000ef73  nop     dword ptr [rax+rax+00h]
0x14000ef78  test    eax, eax
0x14000ef7a  jns     short loc_14000EF7E
0x14000ef7c  int     2Ch; Windows NT - assertion failure
0x14000ef7e  mov     rcx, [rbp+4Fh+Block]; Block
0x14000ef82  test    rcx, rcx
0x14000ef85  jz      short loc_14000EF93
0x14000ef87  call    cs:__imp_free
0x14000ef8e  nop     dword ptr [rax+rax+00h]
0x14000ef93  cmp     [rbp+4Fh+UnicodeString.Buffer], 0
0x14000ef98  jz      short loc_14000EFAA
0x14000ef9a  lea     rcx, [rbp+4Fh+UnicodeString]; UnicodeString
0x14000ef9e  call    cs:__imp_RtlFreeUnicodeString
0x14000efa5  nop     dword ptr [rax+rax+00h]
0x14000efaa  lea     r11, [rsp+0C0h+var_20]
0x14000efb2  mov     eax, ebx
0x14000efb4  mov     rbx, [r11+30h]
0x14000efb8  mov     rdi, [r11+40h]
0x14000efbc  mov     rsp, r11
0x14000efbf  pop     r15
0x14000efc1  pop     r14
0x14000efc3  pop     r13
0x14000efc5  pop     r12
0x14000efc7  pop     rbp
0x14000efc8  retn
```
