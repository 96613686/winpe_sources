# GetDiskFreeSpaceExW

- ea: `0x1800edf90`
- end: `0x1800ee1f4`
- name: `GetDiskFreeSpaceExW`
- size: `612`
- prototype: `BOOL __stdcall(LPCWSTR lpDirectoryName, PULARGE_INTEGER lpFreeBytesAvailableToCaller, PULARGE_INTEGER lpTotalNumberOfBytes, PULARGE_INTEGER lpTotalNumberOfFreeBytes)`
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800edf10`
- `0x18011c918`

## callees

- `0x18004b9d0`
- `0x1800edf90`
- `0x180194f10`

## import_xrefs

- `ntdll!NtOpenFile` at `0x1800ee060`
- `ntdll!NtOpenFile` at `0x1800ee060`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800ee001`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800ee001`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800ee0b1`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800ee11b`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800ee0b1`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800ee11b`
- `ntdll!RtlSetLastWin32Error` at `0x1800ee193`
- `ntdll!RtlSetLastWin32Error` at `0x1800ee1e6`
- `ntdll!RtlSetLastWin32Error` at `0x1800ee193`
- `ntdll!RtlSetLastWin32Error` at `0x1800ee1e6`
- `ntdll!NtClose` at `0x1800ee0c5`
- `ntdll!NtClose` at `0x1800ee12e`
- `ntdll!NtClose` at `0x1800ee0c5`
- `ntdll!NtClose` at `0x1800ee12e`
- `ntdll!RtlFreeHeap` at `0x1800ee086`
- `ntdll!RtlFreeHeap` at `0x1800ee1c9`
- `ntdll!RtlFreeHeap` at `0x1800ee086`
- `ntdll!RtlFreeHeap` at `0x1800ee1c9`

## pseudocode

```c
BOOL __stdcall GetDiskFreeSpaceExW(
        LPCWSTR lpDirectoryName,
        PULARGE_INTEGER lpFreeBytesAvailableToCaller,
        PULARGE_INTEGER lpTotalNumberOfBytes,
        PULARGE_INTEGER lpTotalNumberOfFreeBytes)
{
  bool v5; // zf
  const WCHAR *v7; // rcx
  PWSTR Buffer; // r14
  NTSTATUS v11; // eax
  __int64 v12; // rcx
  NTSTATUS v13; // r14d
  __int64 v14; // rcx
  ULONGLONG v15; // rax
  int v17; // [rsp+30h] [rbp-59h] BYREF
  HANDLE FileHandle; // [rsp+38h] [rbp-51h] BYREF
  struct _UNICODE_STRING NtPathName; // [rsp+40h] [rbp-49h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-39h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-29h] BYREF
  __int128 FsInformation; // [rsp+90h] [rbp+7h] BYREF
  __int128 v23; // [rsp+A0h] [rbp+17h]

  v17 = 92;
  v5 = lpDirectoryName == 0;
  FileHandle = 0;
  v7 = (const WCHAR *)&v17;
  if ( !v5 )
    v7 = lpDirectoryName;
  memset(&ObjectAttributes, 0, 44);
  NtPathName = 0;
  IoStatusBlock = 0;
  FsInformation = 0;
  v23 = 0;
  if ( RtlDosPathNameToNtPathName_U(v7, &NtPathName, 0, 0) )
  {
    Buffer = NtPathName.Buffer;
    ObjectAttributes.ObjectName = &NtPathName;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v11 = NtOpenFile(&FileHandle, 0x100000u, &ObjectAttributes, &IoStatusBlock, 0, 0x800021u);
    if ( v11 < 0 )
    {
      BaseSetLastNTError((unsigned int)v11);
      if ( NtCurrentTeb()->LastErrorValue == 2 )
        RtlSetLastWin32Error(3u);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
    }
    else
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
      if ( lpTotalNumberOfFreeBytes
        && NtQueryVolumeInformationFile(FileHandle, &IoStatusBlock, &FsInformation, 0x20u, FileFsFullSizeInformation) >= 0 )
      {
        NtClose(FileHandle);
        v12 = (unsigned int)(HIDWORD(v23) * DWORD2(v23));
        if ( lpFreeBytesAvailableToCaller )
          lpFreeBytesAvailableToCaller->QuadPart = *((_QWORD *)&FsInformation + 1) * (unsigned int)v12;
        if ( lpTotalNumberOfBytes )
          lpTotalNumberOfBytes->QuadPart = FsInformation * v12;
        lpTotalNumberOfFreeBytes->QuadPart = v23 * v12;
        return 1;
      }
      v13 = NtQueryVolumeInformationFile(FileHandle, &IoStatusBlock, &FsInformation, 0x18u, FileFsSizeInformation);
      NtClose(FileHandle);
      if ( v13 >= 0 )
      {
        v14 = (unsigned int)(DWORD1(v23) * v23);
        v15 = *((_QWORD *)&FsInformation + 1) * v14;
        if ( lpFreeBytesAvailableToCaller )
          lpFreeBytesAvailableToCaller->QuadPart = v15;
        if ( lpTotalNumberOfBytes )
          lpTotalNumberOfBytes->QuadPart = FsInformation * v14;
        if ( lpTotalNumberOfFreeBytes )
          lpTotalNumberOfFreeBytes->QuadPart = v15;
        return 1;
      }
      BaseSetLastNTError((unsigned int)v13);
    }
  }
  else
  {
    RtlSetLastWin32Error(3u);
  }
  return 0;
}

```

## disassembly

```asm
0x1800edf90  push    rbp
0x1800edf92  push    rbx
0x1800edf93  push    rsi
0x1800edf94  push    rdi
0x1800edf95  push    r14
0x1800edf97  lea     rbp, [rsp-37h]
0x1800edf9c  sub     rsp, 0C0h
0x1800edfa3  mov     rax, cs:__security_cookie
0x1800edfaa  xor     rax, rsp
0x1800edfad  mov     [rbp+57h+var_30], rax
0x1800edfb1  xorps   xmm0, xmm0
0x1800edfb4  mov     [rbp+57h+var_B0], 5Ch ; '\'
0x1800edfbb  mov     r10, rcx
0x1800edfbe  xor     eax, eax
0x1800edfc0  test    r10, r10
0x1800edfc3  mov     [rbp+57h+FileHandle], rax
0x1800edfc7  mov     rdi, r9
0x1800edfca  lea     rcx, [rbp+57h+var_B0]
0x1800edfce  cmovnz  rcx, r10; DosPathName
0x1800edfd2  mov     rbx, r8
0x1800edfd5  mov     rsi, rdx
0x1800edfd8  xorps   xmm1, xmm1
0x1800edfdb  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800edfdf  xor     r9d, r9d; DirectoryInfo
0x1800edfe2  lea     rdx, [rbp+57h+NtPathName]; NtPathName
0x1800edfe6  xor     r8d, r8d; NtFileNamePart
0x1800edfe9  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800edfed  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800edff1  movups  xmmword ptr [rbp+57h+NtPathName.Length], xmm0
0x1800edff5  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x1800edff9  movups  [rbp+57h+FsInformation], xmm0
0x1800edffd  movups  [rbp+57h+var_40], xmm0
0x1800ee001  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800ee008  nop     dword ptr [rax+rax+00h]
0x1800ee00d  test    al, al
0x1800ee00f  jz      loc_1800EE18E
0x1800ee015  mov     r14, [rbp+57h+NtPathName.Buffer]
0x1800ee019  lea     rax, [rbp+57h+NtPathName]
0x1800ee01d  xorps   xmm0, xmm0
0x1800ee020  mov     [rsp+0E0h+OpenOptions], 800021h; OpenOptions
0x1800ee028  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800ee02c  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800ee030  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800ee034  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800ee03b  mov     edx, 100000h; DesiredAccess
0x1800ee040  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1800ee048  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800ee04c  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800ee053  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800ee058  mov     [rsp+0E0h+ShareAccess], 0; ShareAccess
0x1800ee060  call    cs:__imp_NtOpenFile
0x1800ee067  nop     dword ptr [rax+rax+00h]
0x1800ee06c  test    eax, eax
0x1800ee06e  js      loc_1800EE1A3
0x1800ee074  mov     rcx, gs:60h
0x1800ee07d  mov     r8, r14; P
0x1800ee080  xor     edx, edx; Flags
0x1800ee082  mov     rcx, [rcx+30h]; HeapHandle
0x1800ee086  call    cs:__imp_RtlFreeHeap
0x1800ee08d  nop     dword ptr [rax+rax+00h]
0x1800ee092  test    rdi, rdi
0x1800ee095  jz      short loc_1800EE101
0x1800ee097  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800ee09b  lea     r8, [rbp+57h+FsInformation]; FsInformation
0x1800ee09f  mov     r9d, 20h ; ' '; Length
0x1800ee0a5  mov     [rsp+0E0h+ShareAccess], 7; FsInformationClass
0x1800ee0ad  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800ee0b1  call    cs:__imp_NtQueryVolumeInformationFile
0x1800ee0b8  nop     dword ptr [rax+rax+00h]
0x1800ee0bd  test    eax, eax
0x1800ee0bf  js      short loc_1800EE101
0x1800ee0c1  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800ee0c5  call    cs:__imp_NtClose
0x1800ee0cc  nop     dword ptr [rax+rax+00h]
0x1800ee0d1  mov     ecx, dword ptr [rbp+57h+var_40+8]
0x1800ee0d4  imul    ecx, dword ptr [rbp+57h+var_40+0Ch]
0x1800ee0d8  test    rsi, rsi
0x1800ee0db  jz      short loc_1800EE0E7
0x1800ee0dd  mov     eax, ecx
0x1800ee0df  imul    rax, qword ptr [rbp+57h+FsInformation+8]
0x1800ee0e4  mov     [rsi], rax
0x1800ee0e7  test    rbx, rbx
0x1800ee0ea  jz      short loc_1800EE0F7
0x1800ee0ec  mov     rax, rcx
0x1800ee0ef  imul    rax, qword ptr [rbp+57h+FsInformation]
0x1800ee0f4  mov     [rbx], rax
0x1800ee0f7  imul    rcx, qword ptr [rbp+57h+var_40]
0x1800ee0fc  mov     [rdi], rcx
0x1800ee0ff  jmp     short loc_1800EE16E
0x1800ee101  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800ee105  lea     r8, [rbp+57h+FsInformation]; FsInformation
0x1800ee109  mov     r9d, 18h; Length
0x1800ee10f  mov     [rsp+0E0h+ShareAccess], 3; FsInformationClass
0x1800ee117  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800ee11b  call    cs:__imp_NtQueryVolumeInformationFile
0x1800ee122  nop     dword ptr [rax+rax+00h]
0x1800ee127  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800ee12b  mov     r14d, eax
0x1800ee12e  call    cs:__imp_NtClose
0x1800ee135  nop     dword ptr [rax+rax+00h]
0x1800ee13a  test    r14d, r14d
0x1800ee13d  js      loc_1800EE1D7
0x1800ee143  mov     eax, dword ptr [rbp+57h+var_40]
0x1800ee146  imul    eax, dword ptr [rbp+57h+var_40+4]
0x1800ee14a  mov     ecx, eax
0x1800ee14c  imul    rax, qword ptr [rbp+57h+FsInformation+8]
0x1800ee151  test    rsi, rsi
0x1800ee154  jz      short loc_1800EE159
0x1800ee156  mov     [rsi], rax
0x1800ee159  test    rbx, rbx
0x1800ee15c  jz      short loc_1800EE166
0x1800ee15e  imul    rcx, qword ptr [rbp+57h+FsInformation]
0x1800ee163  mov     [rbx], rcx
0x1800ee166  test    rdi, rdi
0x1800ee169  jz      short loc_1800EE16E
0x1800ee16b  mov     [rdi], rax
0x1800ee16e  mov     eax, 1
0x1800ee173  mov     rcx, [rbp+57h+var_30]
0x1800ee177  xor     rcx, rsp; StackCookie
0x1800ee17a  call    __security_check_cookie
0x1800ee17f  add     rsp, 0C0h
0x1800ee186  pop     r14
0x1800ee188  pop     rdi
0x1800ee189  pop     rsi
0x1800ee18a  pop     rbx
0x1800ee18b  pop     rbp
0x1800ee18c  retn
0x1800ee18e  mov     ecx, 3; LastError
0x1800ee193  call    cs:__imp_RtlSetLastWin32Error
0x1800ee19a  nop     dword ptr [rax+rax+00h]
0x1800ee19f  xor     eax, eax
0x1800ee1a1  jmp     short loc_1800EE173
0x1800ee1a3  mov     ecx, eax
0x1800ee1a5  call    BaseSetLastNTError
0x1800ee1aa  mov     eax, gs:68h
0x1800ee1b2  cmp     eax, 2
0x1800ee1b5  jz      short loc_1800EE1E1
0x1800ee1b7  mov     rcx, gs:60h
0x1800ee1c0  mov     r8, r14; P
0x1800ee1c3  xor     edx, edx; Flags
0x1800ee1c5  mov     rcx, [rcx+30h]; HeapHandle
0x1800ee1c9  call    cs:__imp_RtlFreeHeap
0x1800ee1d0  nop     dword ptr [rax+rax+00h]
0x1800ee1d5  jmp     short loc_1800EE19F
0x1800ee1d7  mov     ecx, r14d
0x1800ee1da  call    BaseSetLastNTError
0x1800ee1df  jmp     short loc_1800EE19F
0x1800ee1e1  mov     ecx, 3; LastError
0x1800ee1e6  call    cs:__imp_RtlSetLastWin32Error
0x1800ee1ed  nop     dword ptr [rax+rax+00h]
0x1800ee1f2  jmp     short loc_1800EE1B7
```
