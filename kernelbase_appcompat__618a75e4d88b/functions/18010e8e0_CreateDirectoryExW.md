# CreateDirectoryExW

- ea: `0x18010e8e0`
- end: `0x18010fa11`
- name: `CreateDirectoryExW`
- size: `4401`
- prototype: `BOOL __stdcall(LPCWSTR lpTemplateDirectory, LPCWSTR lpNewDirectory, LPSECURITY_ATTRIBUTES lpSecurityAttributes)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800395b0`
- `0x18004b9d0`
- `0x180053c30`
- `0x1800d6a90`
- `0x1800d770c`
- `0x18010e8e0`
- `0x180136610`
- `0x1801373a0`
- `0x180194eb9`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x18010e9b5`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x18010ec46`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x18010e9b5`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x18010ec46`
- `ntdll!RtlReleaseRelativeName` at `0x18010eaaf`
- `ntdll!RtlReleaseRelativeName` at `0x18010eb22`
- `ntdll!RtlReleaseRelativeName` at `0x18010ec5a`
- `ntdll!RtlReleaseRelativeName` at `0x18010ecce`
- `ntdll!RtlReleaseRelativeName` at `0x18010ecde`
- `ntdll!RtlReleaseRelativeName` at `0x18010ed40`
- `ntdll!RtlReleaseRelativeName` at `0x18010edfc`
- `ntdll!RtlReleaseRelativeName` at `0x18010ee92`
- `ntdll!RtlReleaseRelativeName` at `0x18010ef78`
- `ntdll!RtlReleaseRelativeName` at `0x18010f08f`
- `ntdll!RtlReleaseRelativeName` at `0x18010f157`
- `ntdll!RtlReleaseRelativeName` at `0x18010f1ef`
- `ntdll!RtlReleaseRelativeName` at `0x18010eaaf`
- `ntdll!RtlReleaseRelativeName` at `0x18010eb22`
- `ntdll!RtlReleaseRelativeName` at `0x18010ec5a`
- `ntdll!RtlReleaseRelativeName` at `0x18010ecce`
- `ntdll!RtlReleaseRelativeName` at `0x18010ecde`
- `ntdll!RtlReleaseRelativeName` at `0x18010ed40`
- `ntdll!RtlReleaseRelativeName` at `0x18010edfc`
- `ntdll!RtlReleaseRelativeName` at `0x18010ee92`
- `ntdll!RtlReleaseRelativeName` at `0x18010ef78`
- `ntdll!RtlReleaseRelativeName` at `0x18010f08f`
- `ntdll!RtlReleaseRelativeName` at `0x18010f157`
- `ntdll!RtlReleaseRelativeName` at `0x18010f1ef`
- `ntdll!NtQueryInformationFile` at `0x18010eb0c`
- `ntdll!NtQueryInformationFile` at `0x18010eb81`
- `ntdll!NtQueryInformationFile` at `0x18010ec0f`
- `ntdll!NtQueryInformationFile` at `0x18010ee7c`
- `ntdll!NtQueryInformationFile` at `0x18010f74c`
- `ntdll!NtQueryInformationFile` at `0x18010eb0c`
- `ntdll!NtQueryInformationFile` at `0x18010eb81`
- `ntdll!NtQueryInformationFile` at `0x18010ec0f`
- `ntdll!NtQueryInformationFile` at `0x18010ee7c`
- `ntdll!NtQueryInformationFile` at `0x18010f74c`
- `ntdll!NtOpenFile` at `0x18010ea61`
- `ntdll!NtOpenFile` at `0x18010ea95`
- `ntdll!NtOpenFile` at `0x18010ebda`
- `ntdll!NtOpenFile` at `0x18010ea61`
- `ntdll!NtOpenFile` at `0x18010ea95`
- `ntdll!NtOpenFile` at `0x18010ebda`
- `ntdll!NtSetInformationFile` at `0x18010f6b9`
- `ntdll!NtSetInformationFile` at `0x18010f6ee`
- `ntdll!NtSetInformationFile` at `0x18010f6b9`
- `ntdll!NtSetInformationFile` at `0x18010f6ee`
- `ntdll!NtFsControlFile` at `0x18010f2fb`
- `ntdll!NtFsControlFile` at `0x18010f40f`
- `ntdll!NtFsControlFile` at `0x18010f2fb`
- `ntdll!NtFsControlFile` at `0x18010f40f`
- `ntdll!NtCreateFile` at `0x18010f10c`
- `ntdll!NtCreateFile` at `0x18010f1d4`
- `ntdll!NtCreateFile` at `0x18010f848`
- `ntdll!NtCreateFile` at `0x18010f10c`
- `ntdll!NtCreateFile` at `0x18010f1d4`
- `ntdll!NtCreateFile` at `0x18010f848`
- `ntdll!RtlSetLastWin32Error` at `0x18010e9ca`
- `ntdll!RtlSetLastWin32Error` at `0x18010f671`
- `ntdll!RtlSetLastWin32Error` at `0x18010e9ca`
- `ntdll!RtlSetLastWin32Error` at `0x18010f671`
- `ntdll!RtlEqualUnicodeString` at `0x18010ecba`
- `ntdll!RtlEqualUnicodeString` at `0x18010ecba`
- `ntdll!RtlReleasePrivilege` at `0x18010f12a`
- `ntdll!RtlReleasePrivilege` at `0x18010f12a`
- `ntdll!NtQueryEaFile` at `0x18010f031`
- `ntdll!NtQueryEaFile` at `0x18010f031`
- `ntdll!RtlAcquirePrivilege` at `0x18010ef5d`
- `ntdll!RtlAcquirePrivilege` at `0x18010ef5d`
- `ntdll!RtlIsDosDeviceName_U` at `0x18010f257`
- `ntdll!RtlIsDosDeviceName_U` at `0x18010f257`
- `ntdll!RtlInitUnicodeStringEx` at `0x18010f55b`
- `ntdll!RtlInitUnicodeStringEx` at `0x18010f55b`
- `ntdll!NtClose` at `0x18010ec88`
- `ntdll!NtClose` at `0x18010ed2a`
- `ntdll!NtClose` at `0x18010f244`
- `ntdll!NtClose` at `0x18010f2ae`
- `ntdll!NtClose` at `0x18010f2be`
- `ntdll!NtClose` at `0x18010f32f`
- `ntdll!NtClose` at `0x18010f33f`
- `ntdll!NtClose` at `0x18010f382`
- `ntdll!NtClose` at `0x18010f392`
- `ntdll!NtClose` at `0x18010f440`
- `ntdll!NtClose` at `0x18010f450`
- `ntdll!NtClose` at `0x18010f962`
- `ntdll!NtClose` at `0x18010f978`
- `ntdll!NtClose` at `0x18010f9c0`
- `ntdll!NtClose` at `0x18010f9d5`
- `ntdll!NtClose` at `0x18010ec88`
- `ntdll!NtClose` at `0x18010ed2a`
- `ntdll!NtClose` at `0x18010f244`
- `ntdll!NtClose` at `0x18010f2ae`
- `ntdll!NtClose` at `0x18010f2be`
- `ntdll!NtClose` at `0x18010f32f`
- `ntdll!NtClose` at `0x18010f33f`
- `ntdll!NtClose` at `0x18010f382`
- `ntdll!NtClose` at `0x18010f392`
- `ntdll!NtClose` at `0x18010f440`
- `ntdll!NtClose` at `0x18010f450`
- `ntdll!NtClose` at `0x18010f962`
- `ntdll!NtClose` at `0x18010f978`
- `ntdll!NtClose` at `0x18010f9c0`
- `ntdll!NtClose` at `0x18010f9d5`
- `ntdll!RtlFreeHeap` at `0x18010eacd`
- `ntdll!RtlFreeHeap` at `0x18010eb40`
- `ntdll!RtlFreeHeap` at `0x18010ec78`
- `ntdll!RtlFreeHeap` at `0x18010ecfc`
- `ntdll!RtlFreeHeap` at `0x18010ed1a`
- `ntdll!RtlFreeHeap` at `0x18010ed5e`
- `ntdll!RtlFreeHeap` at `0x18010ee1a`
- `ntdll!RtlFreeHeap` at `0x18010eeb0`
- `ntdll!RtlFreeHeap` at `0x18010ef96`
- `ntdll!RtlFreeHeap` at `0x18010efb9`
- `ntdll!RtlFreeHeap` at `0x18010f055`
- `ntdll!RtlFreeHeap` at `0x18010f0ad`
- `ntdll!RtlFreeHeap` at `0x18010f175`
- `ntdll!RtlFreeHeap` at `0x18010f20d`
- `ntdll!RtlFreeHeap` at `0x18010f230`
- `ntdll!RtlFreeHeap` at `0x18010f31f`
- `ntdll!RtlFreeHeap` at `0x18010f372`
- `ntdll!RtlFreeHeap` at `0x18010f430`
- `ntdll!RtlFreeHeap` at `0x18010f62e`
- `ntdll!RtlFreeHeap` at `0x18010f656`
- `ntdll!RtlFreeHeap` at `0x18010f770`
- `ntdll!RtlFreeHeap` at `0x18010f9b0`
- `ntdll!RtlFreeHeap` at `0x18010eacd`
- `ntdll!RtlFreeHeap` at `0x18010eb40`
- `ntdll!RtlFreeHeap` at `0x18010ec78`
- `ntdll!RtlFreeHeap` at `0x18010ecfc`
- `ntdll!RtlFreeHeap` at `0x18010ed1a`
- `ntdll!RtlFreeHeap` at `0x18010ed5e`
- `ntdll!RtlFreeHeap` at `0x18010ee1a`
- `ntdll!RtlFreeHeap` at `0x18010eeb0`
- `ntdll!RtlFreeHeap` at `0x18010ef96`
- `ntdll!RtlFreeHeap` at `0x18010efb9`
- `ntdll!RtlFreeHeap` at `0x18010f055`
- `ntdll!RtlFreeHeap` at `0x18010f0ad`
- `ntdll!RtlFreeHeap` at `0x18010f175`
- `ntdll!RtlFreeHeap` at `0x18010f20d`
- `ntdll!RtlFreeHeap` at `0x18010f230`
- `ntdll!RtlFreeHeap` at `0x18010f31f`
- `ntdll!RtlFreeHeap` at `0x18010f372`
- `ntdll!RtlFreeHeap` at `0x18010f430`
- `ntdll!RtlFreeHeap` at `0x18010f62e`
- `ntdll!RtlFreeHeap` at `0x18010f656`
- `ntdll!RtlFreeHeap` at `0x18010f770`
- `ntdll!RtlFreeHeap` at `0x18010f9b0`
- `ntdll!RtlGetFullPathName_UEx` at `0x18010edd0`
- `ntdll!RtlGetFullPathName_UEx` at `0x18010edd0`
- `ntdll!RtlAllocateHeap` at `0x18010eff2`
- `ntdll!RtlAllocateHeap` at `0x18010f296`
- `ntdll!RtlAllocateHeap` at `0x18010f586`
- `ntdll!RtlAllocateHeap` at `0x18010f722`
- `ntdll!RtlAllocateHeap` at `0x18010eff2`
- `ntdll!RtlAllocateHeap` at `0x18010f296`
- `ntdll!RtlAllocateHeap` at `0x18010f586`
- `ntdll!RtlAllocateHeap` at `0x18010f722`
- `ext-ms-win-kernel32-file-l1-1-0!SetVolumeMountPointWStub` at `0x18010f5fe`
- `ext-ms-win-kernel32-file-l1-1-0!SetVolumeMountPointWStub` at `0x18010f5fe`

## pseudocode

```c
BOOL __stdcall CreateDirectoryExW(
        LPCWSTR lpTemplateDirectory,
        LPCWSTR lpNewDirectory,
        LPSECURITY_ATTRIBUTES lpSecurityAttributes)
{
  ULONG EaLength; // r12d
  ULONG v5; // ecx
  PWSTR Buffer; // rbx
  char v8; // r13
  HANDLE ContainingDirectory; // rax
  NTSTATUS v10; // eax
  NTSTATUS v11; // edi
  __int64 v12; // rcx
  int v13; // eax
  NTSTATUS v14; // eax
  PWSTR v15; // rsi
  NTSTATUS FullPathName_UEx; // eax
  NTSTATUS v17; // ebx
  PWSTR v18; // r8
  ULONG v19; // r14d
  void *EaBuffer; // rdi
  ULONG v21; // eax
  unsigned int v22; // ebx
  ACCESS_MASK v23; // ebx
  NTSTATUS inited; // r14d
  PVOID Heap; // rax
  NTSTATUS v26; // ebx
  char v27; // r14
  unsigned __int16 *v28; // rax
  unsigned __int16 *v29; // rdi
  _WORD *v30; // rbx
  int v31; // r15d
  _WORD *v32; // rax
  _WORD *v33; // rsi
  unsigned __int64 v34; // rcx
  ULONG v35; // esi
  unsigned int *v36; // rax
  unsigned int *v37; // rdi
  unsigned int *i; // rbx
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // r9
  __int64 v42; // rcx
  unsigned __int64 v43; // rcx
  char v44; // [rsp+B0h] [rbp-80h]
  HANDLE FileHandle; // [rsp+B8h] [rbp-78h] BYREF
  HANDLE Handle; // [rsp+C0h] [rbp-70h] BYREF
  RTL_PATH_TYPE InputPathType; // [rsp+C8h] [rbp-68h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+D0h] [rbp-60h] BYREF
  int v49; // [rsp+E0h] [rbp-50h] BYREF
  ULONG v50; // [rsp+E4h] [rbp-4Ch] BYREF
  __int64 v51; // [rsp+E8h] [rbp-48h] BYREF
  __int64 v52; // [rsp+F0h] [rbp-40h] BYREF
  UNICODE_STRING String2; // [rsp+F8h] [rbp-38h] BYREF
  struct _UNICODE_STRING NtName; // [rsp+108h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+118h] [rbp-18h] BYREF
  struct _RTL_RELATIVE_NAME_U RelativeName; // [rsp+128h] [rbp-8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+148h] [rbp+18h] BYREF
  __int64 v58; // [rsp+178h] [rbp+48h] BYREF
  HANDLE v59; // [rsp+180h] [rbp+50h] BYREF
  HANDLE v60; // [rsp+188h] [rbp+58h] BYREF
  struct _RTL_RELATIVE_NAME_U v61; // [rsp+190h] [rbp+60h] BYREF
  __int128 v62; // [rsp+1B0h] [rbp+80h] BYREF
  PVOID ReturnedState; // [rsp+1C0h] [rbp+90h] BYREF
  PCWSTR Name; // [rsp+1C8h] [rbp+98h]
  PWSTR FilePart; // [rsp+1D0h] [rbp+A0h] BYREF
  LPSECURITY_ATTRIBUTES v66; // [rsp+1D8h] [rbp+A8h]
  __int64 v67; // [rsp+1E0h] [rbp+B0h] BYREF
  _OWORD FileInformation[2]; // [rsp+1E8h] [rbp+B8h] BYREF
  ULONG FileAttributes[2]; // [rsp+208h] [rbp+D8h]
  WCHAR v70[264]; // [rsp+210h] [rbp+E0h] BYREF

  EaLength = 0;
  v66 = lpSecurityAttributes;
  Name = lpNewDirectory;
  FileHandle = 0;
  Handle = 0;
  v59 = 0;
  v60 = 0;
  v52 = 0;
  v50 = 0;
  *(_QWORD *)FileAttributes = 0;
  memset(&ObjectAttributes, 0, 44);
  v49 = 0;
  NtName = 0;
  v51 = 0;
  String2 = 0;
  IoStatusBlock = 0;
  v67 = 0;
  DestinationString = 0;
  ReturnedState = 0;
  memset(&RelativeName, 0, sizeof(RelativeName));
  LODWORD(v58) = 0;
  memset(&v61, 0, sizeof(v61));
  v62 = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  if ( !RtlDosPathNameToRelativeNtPathName_U(lpTemplateDirectory, &NtName, 0, &RelativeName) )
  {
    v5 = 3;
LABEL_3:
    RtlSetLastWin32Error(v5);
    return 0;
  }
  Buffer = NtName.Buffer;
  v44 = 0;
  v8 = 0;
  if ( RelativeName.RelativeName.Length )
  {
    NtName = RelativeName.RelativeName;
    ContainingDirectory = RelativeName.ContainingDirectory;
  }
  else
  {
    ContainingDirectory = 0;
    RelativeName.ContainingDirectory = 0;
  }
  ObjectAttributes.RootDirectory = ContainingDirectory;
  ObjectAttributes.ObjectName = &NtName;
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v10 = NtOpenFile(&FileHandle, 0x100089u, &ObjectAttributes, &IoStatusBlock, 3u, 0x204021u);
  v11 = v10;
  if ( v10 >= 0 )
  {
    FileAttributes[0] = 128;
    v11 = NtQueryInformationFile(FileHandle, &IoStatusBlock, FileInformation, 0x28u, FileBasicInformation);
    if ( v11 >= 0 )
    {
      if ( (FileAttributes[0] & 0x400) != 0 )
      {
        v11 = NtQueryInformationFile(FileHandle, &IoStatusBlock, &v52, 8u, FileAttributeTagInformation);
        if ( v11 < 0 )
          goto LABEL_15;
        if ( (unsigned int)(HIDWORD(v52) + 2147483613) <= 3
          || (unsigned int)(HIDWORD(v52) + 1610612733) <= 0x1A
          && (v13 = 67109377, _bittest(&v13, HIDWORD(v52) + 1610612733)) )
        {
          v44 = 1;
        }
        else
        {
          CloseHandle(FileHandle);
          v11 = NtOpenFile(&FileHandle, 0x100089u, &ObjectAttributes, &IoStatusBlock, 3u, 0x4021u);
          if ( v11 < 0 )
          {
LABEL_11:
            RtlReleaseRelativeName(&RelativeName);
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
LABEL_12:
            v12 = (unsigned int)v11;
LABEL_13:
            BaseSetLastNTError(v12);
            return 0;
          }
        }
      }
      v14 = NtQueryInformationFile(FileHandle, &IoStatusBlock, &v49, 4u, FileEaInformation|0x40);
      v11 = v14;
      if ( v14 >= 0 )
      {
        if ( (v49 & 1) != 0 )
          v8 = 1;
        goto LABEL_27;
      }
      if ( v14 == -1073741811 || v14 == -1073741637 )
        goto LABEL_27;
    }
LABEL_15:
    RtlReleaseRelativeName(&RelativeName);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
    CloseHandle(FileHandle);
    goto LABEL_12;
  }
  if ( v10 != -1073741811 )
    goto LABEL_11;
  v11 = NtOpenFile(&FileHandle, 0x100089u, &ObjectAttributes, &IoStatusBlock, 3u, 0x4021u);
  if ( v11 < 0 )
    goto LABEL_11;
LABEL_27:
  if ( !RtlDosPathNameToRelativeNtPathName_U(lpNewDirectory, &String2, 0, &v61) )
  {
    RtlReleaseRelativeName(&RelativeName);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
    NtClose(FileHandle);
    v5 = 3;
    goto LABEL_3;
  }
  v15 = String2.Buffer;
  if ( RtlEqualUnicodeString(&NtName, &String2, 1u) )
  {
    RtlReleaseRelativeName(&RelativeName);
    RtlReleaseRelativeName(&v61);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
    NtClose(FileHandle);
    v5 = 123;
    goto LABEL_3;
  }
  RtlReleaseRelativeName(&RelativeName);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
  if ( !(unsigned __int8)RtlAreLongPathsEnabled() && String2.Length > 0x1F0u )
  {
    FilePart = 0;
    if ( *lpNewDirectory != 92 || lpNewDirectory[1] != 92 || lpNewDirectory[2] != 63 || lpNewDirectory[3] != 92 )
    {
      InputPathType = RtlPathTypeUnknown;
      FullPathName_UEx = RtlGetFullPathName_UEx((PWSTR)lpNewDirectory, 0, 0, &FilePart, &InputPathType);
      if ( FullPathName_UEx < 0 )
        BaseSetLastNTError((unsigned int)FullPathName_UEx);
      if ( !((unsigned int)InputPathType >> 1) || ((unsigned int)InputPathType >> 1) + 12 > 0x104 )
      {
        RtlReleaseRelativeName(&v61);
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
        CloseHandle(FileHandle);
        v5 = 206;
        goto LABEL_3;
      }
    }
  }
  if ( v61.RelativeName.Length )
    String2 = v61.RelativeName;
  else
    v61.ContainingDirectory = 0;
  v17 = NtQueryInformationFile(FileHandle, &IoStatusBlock, &v50, 4u, FileEaInformation);
  if ( v17 < 0 )
  {
    RtlReleaseRelativeName(&v61);
    v18 = v15;
    goto LABEL_50;
  }
  v19 = v50;
  if ( v50 )
  {
    while ( 1 )
    {
      v19 *= 2;
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, v19);
      EaBuffer = Heap;
      if ( !Heap )
        break;
      v26 = NtQueryEaFile(FileHandle, &IoStatusBlock, Heap, v19, 0, 0, 0, 0, 1u);
      if ( v26 >= 0 )
      {
        EaLength = IoStatusBlock.Information;
      }
      else
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, EaBuffer);
        EaBuffer = 0;
        IoStatusBlock.Information = 0;
      }
      if ( v26 != -2147483643 && v26 != -1073741789 )
        goto LABEL_55;
      EaLength = 0;
    }
    RtlReleaseRelativeName(&v61);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
    CloseHandle(FileHandle);
    goto LABEL_72;
  }
  EaBuffer = 0;
LABEL_55:
  ObjectAttributes.RootDirectory = v61.ContainingDirectory;
  ObjectAttributes.ObjectName = &String2;
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( v66 )
    ObjectAttributes.SecurityDescriptor = v66->lpSecurityDescriptor;
  v21 = FileAttributes[0] & 0xFFFFFBFF;
  v22 = FileAttributes[0] & 0x400 | 0x20030200;
  FileAttributes[0] &= ~0x400u;
  v23 = v22 >> 9;
  if ( HIDWORD(v52) == -1610612724 )
  {
    InputPathType = RtlPathTypeDriveRelative|0x20;
    inited = RtlAcquirePrivilege((PULONG)&InputPathType, 1u, 0, &ReturnedState);
    if ( inited < 0 )
    {
      RtlReleaseRelativeName(&v61);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
      if ( EaBuffer )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, EaBuffer);
      CloseHandle(FileHandle);
LABEL_62:
      v12 = (unsigned int)inited;
      goto LABEL_13;
    }
    v21 = FileAttributes[0];
  }
  v17 = NtCreateFile(&Handle, v23, &ObjectAttributes, &IoStatusBlock, 0, v21, 3u, 2u, 0x204021u, EaBuffer, EaLength);
  if ( HIDWORD(v52) == -1610612724 )
    RtlReleasePrivilege(ReturnedState);
  if ( v17 == -1073741811 || v17 == -1073741790 )
  {
    v27 = v44;
    if ( v44 )
    {
      RtlReleaseRelativeName(&v61);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
      if ( !EaBuffer )
        goto LABEL_51;
      v18 = (PWSTR)EaBuffer;
LABEL_50:
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v18);
LABEL_51:
      CloseHandle(FileHandle);
LABEL_52:
      v12 = (unsigned int)v17;
      goto LABEL_13;
    }
    v17 = NtCreateFile(
            &Handle,
            0x100181u,
            &ObjectAttributes,
            &IoStatusBlock,
            0,
            FileAttributes[0],
            3u,
            2u,
            0x4021u,
            EaBuffer,
            EaLength);
  }
  else
  {
    v27 = v44;
  }
  RtlReleaseRelativeName(&v61);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
  if ( EaBuffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, EaBuffer);
  if ( v17 < 0 )
  {
    NtClose(FileHandle);
    if ( RtlIsDosDeviceName_U(Name) )
      v17 = -1073741565;
    goto LABEL_52;
  }
  if ( v27 )
  {
    v28 = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, 0x4000u);
    v29 = v28;
    if ( !v28 )
    {
      NtClose(FileHandle);
      NtClose(Handle);
LABEL_72:
      v12 = 3221225495LL;
      goto LABEL_13;
    }
    v17 = NtFsControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x900A8u, 0, 0, v28, 0x4000u);
    if ( v17 < 0 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v29);
LABEL_94:
      NtClose(FileHandle);
      NtClose(Handle);
      goto LABEL_52;
    }
    if ( *(_DWORD *)v29 != -1610612733 )
    {
      if ( *(_DWORD *)v29 != -1610612724 )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v29);
        NtClose(FileHandle);
        NtClose(Handle);
        v12 = 3221225523LL;
        goto LABEL_13;
      }
      goto LABEL_101;
    }
    v30 = (unsigned __int16 *)((char *)v29 + v29[4]);
    if ( v29[5] != 96 && (v29[5] != 98 || v30[56] != 92)
      || v30[8] != 92
      || v30[9] != 63 && v30[9] != 92
      || v30[10] != 63
      || v30[11] != 92
      || v30[12] != 86
      || v30[13] != 111
      || v30[14] != 108
      || v30[15] != 117
      || v30[16] != 109
      || v30[17] != 101
      || v30[18] != 123
      || v30[27] != 45
      || v30[32] != 45
      || v30[37] != 45
      || v30[42] != 45
      || v30[55] != 125
      || v29[5] != 98
      || v30[9] != 63 )
    {
LABEL_101:
      v31 = 1;
      inited = NtFsControlFile(Handle, 0, 0, 0, &IoStatusBlock, 0x900A4u, v29, v29[2] + 8, 0, 0);
      goto LABEL_102;
    }
    inited = RtlInitUnicodeStringEx(&DestinationString, Name);
    v32 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, DestinationString.Length + 4LL);
    v33 = v32;
    if ( v32 )
    {
      if ( inited >= 0 )
      {
        memcpy_0(v32, DestinationString.Buffer, DestinationString.Length);
        v33[(unsigned __int64)DestinationString.Length >> 1] = 0;
        v34 = (unsigned __int64)DestinationString.Length >> 1;
        if ( DestinationString.Buffer[v34 - 1] != 92 )
        {
          v33[v34] = 92;
          v33[((unsigned __int64)DestinationString.Length >> 1) + 1] = 0;
        }
        v30[9] = 92;
        if ( (unsigned __int8)IsBasepGetComputerNameFromNtPathPresent() )
        {
          v31 = SetVolumeMountPointWStub(v33, v30 + 8);
        }
        else
        {
          v31 = 0;
          BaseSetLastNTError(3221225659LL);
        }
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v33);
        v30[9] = 63;
LABEL_102:
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v29);
        NtClose(FileHandle);
        NtClose(Handle);
        if ( !v31 )
          return 0;
        if ( inited < 0 )
          goto LABEL_62;
        return 1;
      }
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v32);
      BaseSetLastNTError((unsigned int)inited);
    }
    else
    {
      RtlSetLastWin32Error(8u);
    }
    v31 = 0;
    goto LABEL_102;
  }
  if ( (FileAttributes[0] & 0x180000) != 0 )
  {
    FileAttributes[0] &= 0x180000u;
    v17 = NtSetInformationFile(Handle, &IoStatusBlock, FileInformation, 0x28u, FileBasicInformation);
    if ( v17 < 0 )
      goto LABEL_94;
  }
  if ( v8 )
  {
    v17 = NtSetInformationFile(Handle, &IoStatusBlock, &v49, 4u, FileEaInformation|0x40);
    if ( v17 < 0 )
      goto LABEL_94;
  }
  v35 = 4096;
  LODWORD(v51) = 4096;
  while ( 1 )
  {
    v36 = (unsigned int *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, v35);
    v37 = v36;
    if ( !v36 )
      break;
    v17 = NtQueryInformationFile(FileHandle, &IoStatusBlock, v36, v35, FileStreamInformation);
    if ( v17 < 0 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v37);
      v35 *= 2;
      v37 = 0;
    }
    if ( v17 != -2147483643 && v17 != -1073741789 )
      goto LABEL_147;
  }
  BaseMarkFileForDelete(Handle);
  BaseSetLastNTError(3221225495LL);
LABEL_147:
  if ( v17 >= 0 && IoStatusBlock.Information )
  {
    for ( i = v37; ; i = (unsigned int *)((char *)i + *i) )
    {
      *((_QWORD *)&v62 + 1) = i + 6;
      InputPathType = RtlPathTypeUnknown;
      LOWORD(v62) = *((_WORD *)i + 2);
      WORD1(v62) = v62;
      ObjectAttributes.RootDirectory = FileHandle;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)&v62;
      ObjectAttributes.Length = 48;
      ObjectAttributes.Attributes = 0;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( NtCreateFile(&v59, 0x80100000, &ObjectAttributes, &IoStatusBlock, 0, 0, 1u, 1u, 0x20u, 0, 0) >= 0 )
      {
        v39 = 0;
        v40 = (unsigned __int16)v62 >> 1;
        if ( (unsigned __int16)v62 >> 1 )
        {
          v41 = *((_QWORD *)&v62 + 1);
          do
          {
            if ( (unsigned int)v39 >= 0x100 )
              break;
            v42 = (unsigned int)v39;
            v39 = (unsigned int)(v39 + 1);
            v70[v42] = *(_WORD *)(v41 + 2 * v42);
          }
          while ( (unsigned int)v39 < (unsigned int)v40 );
        }
        v43 = 2LL * (unsigned int)v39;
        if ( v43 >= 0x202 )
          _report_rangecheckfailure(v43, v39, v40);
        v70[(unsigned int)v39] = 0;
        v60 = (HANDLE)-1LL;
        HIDWORD(v51) = 0;
        BaseCopyStream(
          0,
          &v59,
          0x80100000,
          v70,
          Handle,
          0,
          (__int64 *)i + 1,
          (int *)&v51 + 1,
          &v60,
          0,
          &v51,
          &v67,
          0,
          0,
          0,
          0,
          (__int64)&InputPathType,
          0,
          0,
          0,
          0,
          &v58);
        NtClose(v59);
        if ( v60 != (HANDLE)-1LL )
          NtClose(v60);
      }
      if ( !*i )
        break;
    }
  }
  if ( v37 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v37);
  NtClose(FileHandle);
  if ( Handle )
    NtClose(Handle);
  return 1;
}

```

## disassembly

```asm
0x18010e8e0  mov     [rsp-8+arg_18], rbx
0x18010e8e5  push    rbp
0x18010e8e6  push    rsi
0x18010e8e7  push    rdi
0x18010e8e8  push    r12
0x18010e8ea  push    r13
0x18010e8ec  push    r14
0x18010e8ee  push    r15
0x18010e8f0  lea     rbp, [rsp-300h]
0x18010e8f8  sub     rsp, 430h
0x18010e8ff  mov     rax, cs:__security_cookie
0x18010e906  xor     rax, rsp
0x18010e909  mov     [rbp+330h+var_40], rax
0x18010e910  xor     r12d, r12d
0x18010e913  mov     [rbp+330h+var_288], r8
0x18010e91a  xorps   xmm0, xmm0
0x18010e91d  mov     [rbp+330h+Name], rdx
0x18010e924  xorps   xmm1, xmm1
0x18010e927  mov     [rbp+330h+FileHandle], r12
0x18010e92b  mov     r14, rdx
0x18010e92e  mov     [rbp+330h+Handle], r12
0x18010e932  xor     eax, eax
0x18010e934  mov     [rbp+330h+var_2E0], r12
0x18010e938  movups  xmmword ptr [rbp+330h+ObjectAttributes.ObjectName], xmm0
0x18010e93c  lea     r9, [rbp+330h+RelativeName]; RelativeName
0x18010e940  mov     [rbp+330h+var_2D8], r12
0x18010e944  xor     r8d, r8d; PartName
0x18010e947  mov     [rbp+330h+var_370], r12
0x18010e94b  lea     rdx, [rbp+330h+NtName]; NtName
0x18010e94f  mov     [rbp+330h+var_37C], r12d
0x18010e953  movups  xmmword ptr [rbp+330h+ObjectAttributes+1Ch], xmm0
0x18010e957  mov     qword ptr [rbp+330h+FileAttributes], rax
0x18010e95e  movups  xmmword ptr [rbp+330h+ObjectAttributes.Length], xmm0
0x18010e962  mov     [rbp+330h+var_380], r12d
0x18010e966  movups  xmmword ptr [rbp+330h+NtName.Length], xmm0
0x18010e96a  mov     dword ptr [rbp+330h+var_378], r12d
0x18010e96e  movups  xmmword ptr [rbp+330h+String2.Length], xmm1
0x18010e972  mov     dword ptr [rbp+330h+var_378+4], r12d
0x18010e976  movups  xmmword ptr [rbp+330h+IoStatusBlock], xmm0
0x18010e97a  mov     [rbp+330h+var_280], r12
0x18010e981  movups  xmmword ptr [rbp+330h+DestinationString.Length], xmm1
0x18010e985  mov     [rbp+330h+ReturnedState], r12
0x18010e98c  movups  xmmword ptr [rbp+330h+RelativeName.RelativeName.Length], xmm0
0x18010e990  mov     dword ptr [rbp+330h+var_2E8], r12d
0x18010e994  movups  xmmword ptr [rbp+330h+RelativeName.ContainingDirectory], xmm0
0x18010e998  movups  xmmword ptr [rbp+330h+var_2D0.RelativeName.Length], xmm1
0x18010e99c  movups  xmmword ptr [rbp+330h+var_2D0.ContainingDirectory], xmm1
0x18010e9a0  movups  [rbp+330h+var_2B0], xmm0
0x18010e9a7  movups  [rbp+330h+FileInformation], xmm0
0x18010e9ae  movups  [rbp+330h+var_268], xmm0
0x18010e9b5  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x18010e9bc  nop     dword ptr [rax+rax+00h]
0x18010e9c1  test    al, al
0x18010e9c3  jnz     short loc_18010E9DD
0x18010e9c5  lea     ecx, [r12+3]; LastError
0x18010e9ca  call    cs:__imp_RtlSetLastWin32Error
0x18010e9d1  nop     dword ptr [rax+rax+00h]
0x18010e9d6  xor     eax, eax
0x18010e9d8  jmp     loc_18010F9E6
0x18010e9dd  movzx   eax, [rbp+330h+RelativeName.RelativeName.Length]
0x18010e9e1  mov     rbx, [rbp+330h+NtName.Buffer]
0x18010e9e5  mov     [rbp+330h+var_3B0], r12b
0x18010e9e9  movzx   r13d, r12b
0x18010e9ed  test    ax, ax
0x18010e9f0  jz      short loc_18010EA12
0x18010e9f2  mov     [rbp+330h+NtName.Length], ax
0x18010e9f6  mov     eax, dword ptr [rbp+330h+RelativeName.RelativeName.MaximumLength]
0x18010e9f9  mov     dword ptr [rbp+330h+NtName.MaximumLength], eax
0x18010e9fc  movzx   eax, word ptr [rbp+330h+RelativeName.RelativeName+6]
0x18010ea00  mov     word ptr [rbp+330h+NtName+6], ax
0x18010ea04  mov     rax, [rbp+330h+RelativeName.RelativeName.Buffer]
0x18010ea08  mov     [rbp+330h+NtName.Buffer], rax
0x18010ea0c  mov     rax, [rbp+330h+RelativeName.ContainingDirectory]
0x18010ea10  jmp     short loc_18010EA19
0x18010ea12  mov     rax, r12
0x18010ea15  mov     [rbp+330h+RelativeName.ContainingDirectory], rax
0x18010ea19  mov     [rbp+330h+ObjectAttributes.RootDirectory], rax
0x18010ea1d  lea     r9, [rbp+330h+IoStatusBlock]; IoStatusBlock
0x18010ea21  lea     rax, [rbp+330h+NtName]
0x18010ea25  mov     [rsp+460h+OpenOptions], 204021h; OpenOptions
0x18010ea2d  xorps   xmm0, xmm0
0x18010ea30  mov     [rbp+330h+ObjectAttributes.ObjectName], rax
0x18010ea34  mov     esi, 100089h
0x18010ea39  mov     [rbp+330h+ObjectAttributes.Length], 30h ; '0'
0x18010ea40  mov     r15d, 3
0x18010ea46  mov     [rbp+330h+ObjectAttributes.Attributes], 40h ; '@'
0x18010ea4d  mov     edx, esi; DesiredAccess
0x18010ea4f  mov     [rsp+460h+ShareAccess], r15d; ShareAccess
0x18010ea54  lea     r8, [rbp+330h+ObjectAttributes]; ObjectAttributes
0x18010ea58  lea     rcx, [rbp+330h+FileHandle]; FileHandle
0x18010ea5c  movdqu  xmmword ptr [rbp+330h+ObjectAttributes.SecurityDescriptor], xmm0
0x18010ea61  call    cs:__imp_NtOpenFile
0x18010ea68  nop     dword ptr [rax+rax+00h]
0x18010ea6d  mov     edi, eax
0x18010ea6f  test    eax, eax
0x18010ea71  jns     short loc_18010EAE5
0x18010ea73  cmp     eax, 0C000000Dh
0x18010ea78  jnz     short loc_18010EAAB
0x18010ea7a  mov     [rsp+460h+OpenOptions], 4021h; OpenOptions
0x18010ea82  lea     r9, [rbp+330h+IoStatusBlock]; IoStatusBlock
0x18010ea86  lea     r8, [rbp+330h+ObjectAttributes]; ObjectAttributes
0x18010ea8a  mov     [rsp+460h+ShareAccess], r15d; ShareAccess
0x18010ea8f  mov     edx, esi; DesiredAccess
0x18010ea91  lea     rcx, [rbp+330h+FileHandle]; FileHandle
0x18010ea95  call    cs:__imp_NtOpenFile
0x18010ea9c  nop     dword ptr [rax+rax+00h]
0x18010eaa1  mov     edi, eax
0x18010eaa3  test    eax, eax
0x18010eaa5  jns     loc_18010EC33
0x18010eaab  lea     rcx, [rbp+330h+RelativeName]; RelativeName
0x18010eaaf  call    cs:__imp_RtlReleaseRelativeName
0x18010eab6  nop     dword ptr [rax+rax+00h]
0x18010eabb  mov     rcx, gs:60h
0x18010eac4  mov     r8, rbx; P
0x18010eac7  xor     edx, edx; Flags
0x18010eac9  mov     rcx, [rcx+30h]; HeapHandle
0x18010eacd  call    cs:__imp_RtlFreeHeap
0x18010ead4  nop     dword ptr [rax+rax+00h]
0x18010ead9  mov     ecx, edi
0x18010eadb  call    BaseSetLastNTError
0x18010eae0  jmp     loc_18010E9D6
0x18010eae5  mov     rcx, [rbp+330h+FileHandle]; FileHandle
0x18010eae9  lea     r8, [rbp+330h+FileInformation]; FileInformation
0x18010eaf0  mov     r9d, 28h ; '('; Length
0x18010eaf6  mov     [rbp+330h+FileAttributes], 80h
0x18010eb00  lea     rdx, [rbp+330h+IoStatusBlock]; IoStatusBlock
0x18010eb04  mov     [rsp+460h+ShareAccess], 4; FileInformationClass
0x18010eb0c  call    cs:__imp_NtQueryInformationFile
0x18010eb13  nop     dword ptr [rax+rax+00h]
0x18010eb18  mov     edi, eax
0x18010eb1a  test    eax, eax
0x18010eb1c  jns     short loc_18010EB57
0x18010eb1e  lea     rcx, [rbp+330h+RelativeName]; RelativeName
0x18010eb22  call    cs:__imp_RtlReleaseRelativeName
0x18010eb29  nop     dword ptr [rax+rax+00h]
0x18010eb2e  mov     rcx, gs:60h
0x18010eb37  mov     r8, rbx; P
0x18010eb3a  xor     edx, edx; Flags
0x18010eb3c  mov     rcx, [rcx+30h]; HeapHandle
0x18010eb40  call    cs:__imp_RtlFreeHeap
0x18010eb47  nop     dword ptr [rax+rax+00h]
0x18010eb4c  mov     rcx, [rbp+330h+FileHandle]; hObject
0x18010eb50  call    CloseHandle
0x18010eb55  jmp     short loc_18010EAD9
0x18010eb57  test    [rbp+330h+FileAttributes], 400h
0x18010eb61  jz      loc_18010EBF5
0x18010eb67  mov     rcx, [rbp+330h+FileHandle]; FileHandle
0x18010eb6b  lea     r8, [rbp+330h+var_370]; FileInformation
0x18010eb6f  mov     r9d, 8; Length
0x18010eb75  mov     [rsp+460h+ShareAccess], 23h ; '#'; FileInformationClass
0x18010eb7d  lea     rdx, [rbp+330h+IoStatusBlock]; IoStatusBlock
0x18010eb81  call    cs:__imp_NtQueryInformationFile
0x18010eb88  nop     dword ptr [rax+rax+00h]
0x18010eb8d  mov     edi, eax
0x18010eb8f  test    eax, eax
0x18010eb91  js      short loc_18010EB1E
0x18010eb93  mov     ecx, dword ptr [rbp+330h+var_370+4]
0x18010eb96  lea     eax, [rcx+7FFFFFDDh]
0x18010eb9c  cmp     eax, r15d
0x18010eb9f  jbe     short loc_18010EBF1
0x18010eba1  add     ecx, 5FFFFFFDh
0x18010eba7  cmp     ecx, 1Ah
0x18010ebaa  ja      short loc_18010EBB6
0x18010ebac  mov     eax, 4000201h
0x18010ebb1  bt      eax, ecx
0x18010ebb4  jb      short loc_18010EBF1
0x18010ebb6  mov     rcx, [rbp+330h+FileHandle]; hObject
0x18010ebba  call    CloseHandle
0x18010ebbf  lea     r9, [rbp+330h+IoStatusBlock]; IoStatusBlock
0x18010ebc3  mov     [rsp+460h+OpenOptions], 4021h; OpenOptions
0x18010ebcb  lea     r8, [rbp+330h+ObjectAttributes]; ObjectAttributes
0x18010ebcf  mov     [rsp+460h+ShareAccess], r15d; ShareAccess
0x18010ebd4  mov     edx, esi; DesiredAccess
0x18010ebd6  lea     rcx, [rbp+330h+FileHandle]; FileHandle
0x18010ebda  call    cs:__imp_NtOpenFile
0x18010ebe1  nop     dword ptr [rax+rax+00h]
0x18010ebe6  mov     edi, eax
0x18010ebe8  test    eax, eax
0x18010ebea  jns     short loc_18010EBF5
0x18010ebec  jmp     loc_18010EAAB
0x18010ebf1  mov     [rbp+330h+var_3B0], 1
0x18010ebf5  mov     rcx, [rbp+330h+FileHandle]; FileHandle
0x18010ebf9  lea     r8, [rbp+330h+var_380]; FileInformation
0x18010ebfd  mov     r9d, 4; Length
0x18010ec03  mov     [rsp+460h+ShareAccess], 47h ; 'G'; FileInformationClass
0x18010ec0b  lea     rdx, [rbp+330h+IoStatusBlock]; IoStatusBlock
0x18010ec0f  call    cs:__imp_NtQueryInformationFile
0x18010ec16  nop     dword ptr [rax+rax+00h]
0x18010ec1b  mov     edi, eax
0x18010ec1d  test    eax, eax
0x18010ec1f  jns     short loc_18010EC9C
0x18010ec21  cmp     eax, 0C000000Dh
0x18010ec26  jz      short loc_18010EC33
0x18010ec28  cmp     eax, 0C00000BBh
0x18010ec2d  jnz     loc_18010EB1E
0x18010ec33  mov     edi, 1
0x18010ec38  lea     r9, [rbp+330h+var_2D0]; RelativeName
0x18010ec3c  xor     r8d, r8d; PartName
0x18010ec3f  lea     rdx, [rbp+330h+String2]; NtName
0x18010ec43  mov     rcx, r14; DosName
0x18010ec46  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x18010ec4d  nop     dword ptr [rax+rax+00h]
0x18010ec52  test    al, al
0x18010ec54  jnz     short loc_18010ECAB
0x18010ec56  lea     rcx, [rbp+330h+RelativeName]; RelativeName
0x18010ec5a  call    cs:__imp_RtlReleaseRelativeName
0x18010ec61  nop     dword ptr [rax+rax+00h]
0x18010ec66  mov     rcx, gs:60h
0x18010ec6f  mov     r8, rbx; P
0x18010ec72  xor     edx, edx; Flags
0x18010ec74  mov     rcx, [rcx+30h]; HeapHandle
0x18010ec78  call    cs:__imp_RtlFreeHeap
0x18010ec7f  nop     dword ptr [rax+rax+00h]
0x18010ec84  mov     rcx, [rbp+330h+FileHandle]; Handle
0x18010ec88  call    cs:__imp_NtClose
0x18010ec8f  nop     dword ptr [rax+rax+00h]
0x18010ec94  mov     ecx, r15d
0x18010ec97  jmp     loc_18010E9CA
0x18010ec9c  mov     edi, 1
0x18010eca1  test    byte ptr [rbp+330h+var_380], dil
0x18010eca5  cmovnz  r13d, edi
0x18010eca9  jmp     short loc_18010EC38
0x18010ecab  mov     rsi, [rbp+330h+String2.Buffer]
0x18010ecaf  lea     rdx, [rbp+330h+String2]; String2
0x18010ecb3  mov     r8b, dil; CaseInsensitive
0x18010ecb6  lea     rcx, [rbp+330h+NtName]; String1
0x18010ecba  call    cs:__imp_RtlEqualUnicodeString
0x18010ecc1  nop     dword ptr [rax+rax+00h]
0x18010ecc6  lea     rcx, [rbp+330h+RelativeName]; RelativeName
0x18010ecca  test    al, al
0x18010eccc  jz      short loc_18010ED40
0x18010ecce  call    cs:__imp_RtlReleaseRelativeName
0x18010ecd5  nop     dword ptr [rax+rax+00h]
0x18010ecda  lea     rcx, [rbp+330h+var_2D0]; RelativeName
0x18010ecde  call    cs:__imp_RtlReleaseRelativeName
0x18010ece5  nop     dword ptr [rax+rax+00h]
0x18010ecea  mov     rcx, gs:60h
0x18010ecf3  mov     r8, rbx; P
0x18010ecf6  xor     edx, edx; Flags
0x18010ecf8  mov     rcx, [rcx+30h]; HeapHandle
0x18010ecfc  call    cs:__imp_RtlFreeHeap
0x18010ed03  nop     dword ptr [rax+rax+00h]
0x18010ed08  mov     rcx, gs:60h
0x18010ed11  mov     r8, rsi; P
0x18010ed14  xor     edx, edx; Flags
0x18010ed16  mov     rcx, [rcx+30h]; HeapHandle
0x18010ed1a  call    cs:__imp_RtlFreeHeap
0x18010ed21  nop     dword ptr [rax+rax+00h]
0x18010ed26  mov     rcx, [rbp+330h+FileHandle]; Handle
0x18010ed2a  call    cs:__imp_NtClose
0x18010ed31  nop     dword ptr [rax+rax+00h]
0x18010ed36  mov     ecx, 7Bh ; '{'
0x18010ed3b  jmp     loc_18010E9CA
0x18010ed40  call    cs:__imp_RtlReleaseRelativeName
0x18010ed47  nop     dword ptr [rax+rax+00h]
0x18010ed4c  mov     rcx, gs:60h
0x18010ed55  mov     r8, rbx; P
0x18010ed58  xor     edx, edx; Flags
0x18010ed5a  mov     rcx, [rcx+30h]; HeapHandle
0x18010ed5e  call    cs:__imp_RtlFreeHeap
0x18010ed65  nop     dword ptr [rax+rax+00h]
0x18010ed6a  call    RtlAreLongPathsEnabled
0x18010ed6f  mov     ecx, 5Ch ; '\'
0x18010ed74  lea     edx, [rcx-1Dh]
0x18010ed77  test    al, al
0x18010ed79  jnz     loc_18010EE39
0x18010ed7f  mov     eax, 1F0h
0x18010ed84  cmp     [rbp+330h+String2.Length], ax
0x18010ed88  jbe     loc_18010EE39
0x18010ed8e  mov     [rbp+330h+FilePart], r12
0x18010ed95  cmp     [r14], cx
0x18010ed99  jnz     short loc_18010EDB4
0x18010ed9b  cmp     [r14+2], cx
0x18010eda0  jnz     short loc_18010EDB4
0x18010eda2  cmp     [r14+4], dx
0x18010eda7  jnz     short loc_18010EDB4
0x18010eda9  cmp     [r14+6], cx
0x18010edae  jz      loc_18010EE39
0x18010edb4  lea     rax, [rbp+330h+InputPathType]
0x18010edb8  mov     [rbp+330h+InputPathType], r12d
0x18010edbc  lea     r9, [rbp+330h+FilePart]; FilePart
0x18010edc3  mov     qword ptr [rsp+460h+ShareAccess], rax; InputPathType
0x18010edc8  xor     r8d, r8d; Buffer
0x18010edcb  xor     edx, edx; BufferLength
0x18010edcd  mov     rcx, r14; FileName
0x18010edd0  call    cs:__imp_RtlGetFullPathName_UEx
0x18010edd7  nop     dword ptr [rax+rax+00h]
0x18010eddc  test    eax, eax
0x18010edde  jns     short loc_18010EDE7
0x18010ede0  mov     ecx, eax
0x18010ede2  call    BaseSetLastNTError
0x18010ede7  mov     eax, [rbp+330h+InputPathType]
0x18010edea  shr     eax, 1
0x18010edec  jz      short loc_18010EDF8
0x18010edee  add     eax, 0Ch
0x18010edf1  cmp     eax, 104h
0x18010edf6  jbe     short loc_18010EE39
0x18010edf8  lea     rcx, [rbp+330h+var_2D0]; RelativeName
0x18010edfc  call    cs:__imp_RtlReleaseRelativeName
0x18010ee03  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
