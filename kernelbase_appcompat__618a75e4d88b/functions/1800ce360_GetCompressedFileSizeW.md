# GetCompressedFileSizeW

- ea: `0x1800ce360`
- end: `0x1800ce563`
- name: `GetCompressedFileSizeW`
- size: `515`
- prototype: `DWORD __stdcall(LPCWSTR lpFileName, LPDWORD lpFileSizeHigh)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800ce300`

## callees

- `0x18004b9d0`
- `0x1800ce360`
- `0x1800ce570`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x1800ce3c5`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x1800ce3c5`
- `ntdll!RtlReleaseRelativeName` at `0x1800ce446`
- `ntdll!RtlReleaseRelativeName` at `0x1800ce446`
- `ntdll!NtQueryInformationFile` at `0x1800ce492`
- `ntdll!NtQueryInformationFile` at `0x1800ce492`
- `ntdll!NtOpenFile` at `0x1800ce434`
- `ntdll!NtOpenFile` at `0x1800ce434`
- `ntdll!RtlSetLastWin32Error` at `0x1800ce53f`
- `ntdll!RtlSetLastWin32Error` at `0x1800ce54f`
- `ntdll!RtlSetLastWin32Error` at `0x1800ce53f`
- `ntdll!RtlSetLastWin32Error` at `0x1800ce54f`
- `ntdll!NtClose` at `0x1800ce4a6`
- `ntdll!NtClose` at `0x1800ce4fb`
- `ntdll!NtClose` at `0x1800ce4a6`
- `ntdll!NtClose` at `0x1800ce4fb`
- `ntdll!RtlFreeHeap` at `0x1800ce464`
- `ntdll!RtlFreeHeap` at `0x1800ce464`

## pseudocode

```c
DWORD __stdcall GetCompressedFileSizeW(LPCWSTR lpFileName, LPDWORD lpFileSizeHigh)
{
  PWSTR Buffer; // rsi
  HANDLE ContainingDirectory; // rax
  NTSTATUS v5; // edi
  DWORD result; // eax
  DWORD FileSize; // ebx
  HANDLE FileHandle; // [rsp+30h] [rbp-49h] BYREF
  struct _UNICODE_STRING NtName; // [rsp+38h] [rbp-41h] BYREF
  struct _RTL_RELATIVE_NAME_U RelativeName; // [rsp+48h] [rbp-31h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-11h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+98h] [rbp+1Fh] BYREF
  __int128 FileInformation; // [rsp+A8h] [rbp+2Fh] BYREF

  FileHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  NtName = 0;
  IoStatusBlock = 0;
  FileInformation = 0;
  memset(&RelativeName, 0, sizeof(RelativeName));
  if ( !RtlDosPathNameToRelativeNtPathName_U(lpFileName, &NtName, 0, &RelativeName) )
  {
    RtlSetLastWin32Error(3u);
    return -1;
  }
  Buffer = NtName.Buffer;
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
  v5 = NtOpenFile(&FileHandle, 0x80u, &ObjectAttributes, &IoStatusBlock, 7u, 0x4000u);
  RtlReleaseRelativeName(&RelativeName);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
  if ( v5 < 0 )
  {
    BaseSetLastNTError((unsigned int)v5);
    return -1;
  }
  if ( NtQueryInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 0x10u, FileCompressionInformation) < 0 )
  {
    FileSize = GetFileSize(FileHandle, lpFileSizeHigh);
    NtClose(FileHandle);
    return FileSize;
  }
  else
  {
    NtClose(FileHandle);
    if ( lpFileSizeHigh )
      *lpFileSizeHigh = DWORD1(FileInformation);
    result = FileInformation;
    if ( (_DWORD)FileInformation == -1 )
    {
      RtlSetLastWin32Error(0);
      return FileInformation;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800ce360  mov     [rsp-8+arg_10], rbx
0x1800ce365  mov     [rsp-8+arg_18], rsi
0x1800ce36a  push    rbp
0x1800ce36b  push    rdi
0x1800ce36c  push    r14
0x1800ce36e  lea     rbp, [rsp-47h]
0x1800ce373  sub     rsp, 0C0h
0x1800ce37a  mov     rax, cs:__security_cookie
0x1800ce381  xor     rax, rsp
0x1800ce384  mov     [rbp+57h+var_18], rax
0x1800ce388  xorps   xmm0, xmm0
0x1800ce38b  lea     r9, [rbp+57h+RelativeName]; RelativeName
0x1800ce38f  xorps   xmm1, xmm1
0x1800ce392  mov     rbx, rdx
0x1800ce395  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800ce399  xor     r14d, r14d
0x1800ce39c  lea     rdx, [rbp+57h+NtName]; NtName
0x1800ce3a0  xor     eax, eax
0x1800ce3a2  mov     [rbp+57h+FileHandle], r14
0x1800ce3a6  xor     r8d, r8d; PartName
0x1800ce3a9  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800ce3ad  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800ce3b1  movups  xmmword ptr [rbp+57h+NtName.Length], xmm0
0x1800ce3b5  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x1800ce3b9  movups  [rbp+57h+FileInformation], xmm0
0x1800ce3bd  movups  xmmword ptr [rbp+57h+RelativeName.RelativeName.Length], xmm1
0x1800ce3c1  movups  xmmword ptr [rbp+57h+RelativeName.ContainingDirectory], xmm1
0x1800ce3c5  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x1800ce3cc  nop     dword ptr [rax+rax+00h]
0x1800ce3d1  test    al, al
0x1800ce3d3  jz      loc_1800CE53A
0x1800ce3d9  movzx   eax, [rbp+57h+RelativeName.RelativeName.Length]
0x1800ce3dd  mov     rsi, [rbp+57h+NtName.Buffer]
0x1800ce3e1  test    ax, ax
0x1800ce3e4  jnz     loc_1800CE517
0x1800ce3ea  mov     eax, r14d
0x1800ce3ed  mov     [rbp+57h+RelativeName.ContainingDirectory], rax
0x1800ce3f1  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x1800ce3f5  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800ce3f9  lea     rax, [rbp+57h+NtName]
0x1800ce3fd  mov     [rsp+0D0h+OpenOptions], 4000h; OpenOptions
0x1800ce405  xorps   xmm0, xmm0
0x1800ce408  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800ce40c  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800ce410  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800ce417  mov     edx, 80h; DesiredAccess
0x1800ce41c  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800ce423  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800ce427  mov     [rsp+0D0h+ShareAccess], 7; ShareAccess
0x1800ce42f  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800ce434  call    cs:__imp_NtOpenFile
0x1800ce43b  nop     dword ptr [rax+rax+00h]
0x1800ce440  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x1800ce444  mov     edi, eax
0x1800ce446  call    cs:__imp_RtlReleaseRelativeName
0x1800ce44d  nop     dword ptr [rax+rax+00h]
0x1800ce452  mov     rcx, gs:60h
0x1800ce45b  mov     r8, rsi; P
0x1800ce45e  xor     edx, edx; Flags
0x1800ce460  mov     rcx, [rcx+30h]; HeapHandle
0x1800ce464  call    cs:__imp_RtlFreeHeap
0x1800ce46b  nop     dword ptr [rax+rax+00h]
0x1800ce470  test    edi, edi
0x1800ce472  js      loc_1800CE50B
0x1800ce478  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800ce47c  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x1800ce480  mov     r9d, 10h; Length
0x1800ce486  mov     [rsp+0D0h+ShareAccess], 1Ch; FileInformationClass
0x1800ce48e  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800ce492  call    cs:__imp_NtQueryInformationFile
0x1800ce499  nop     dword ptr [rax+rax+00h]
0x1800ce49e  mov     rcx, [rbp+57h+FileHandle]; hFile
0x1800ce4a2  test    eax, eax
0x1800ce4a4  js      short loc_1800CE4ED
0x1800ce4a6  call    cs:__imp_NtClose
0x1800ce4ad  nop     dword ptr [rax+rax+00h]
0x1800ce4b2  test    rbx, rbx
0x1800ce4b5  jz      short loc_1800CE4BC
0x1800ce4b7  mov     eax, dword ptr [rbp+57h+FileInformation+4]
0x1800ce4ba  mov     [rbx], eax
0x1800ce4bc  mov     eax, dword ptr [rbp+57h+FileInformation]
0x1800ce4bf  cmp     eax, 0FFFFFFFFh
0x1800ce4c2  jz      loc_1800CE54D
0x1800ce4c8  mov     rcx, [rbp+57h+var_18]
0x1800ce4cc  xor     rcx, rsp; StackCookie
0x1800ce4cf  call    __security_check_cookie
0x1800ce4d4  lea     r11, [rsp+0D0h+var_10]
0x1800ce4dc  mov     rbx, [r11+30h]
0x1800ce4e0  mov     rsi, [r11+38h]
0x1800ce4e4  mov     rsp, r11
0x1800ce4e7  pop     r14
0x1800ce4e9  pop     rdi
0x1800ce4ea  pop     rbp
0x1800ce4eb  retn
0x1800ce4ed  mov     rdx, rbx; lpFileSizeHigh
0x1800ce4f0  call    GetFileSize
0x1800ce4f5  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800ce4f9  mov     ebx, eax
0x1800ce4fb  call    cs:__imp_NtClose
0x1800ce502  nop     dword ptr [rax+rax+00h]
0x1800ce507  mov     eax, ebx
0x1800ce509  jmp     short loc_1800CE4C8
0x1800ce50b  mov     ecx, edi
0x1800ce50d  call    BaseSetLastNTError
0x1800ce512  or      eax, 0FFFFFFFFh
0x1800ce515  jmp     short loc_1800CE4C8
0x1800ce517  mov     [rbp+57h+NtName.Length], ax
0x1800ce51b  mov     eax, dword ptr [rbp+57h+RelativeName.RelativeName.MaximumLength]
0x1800ce51e  mov     dword ptr [rbp+57h+NtName.MaximumLength], eax
0x1800ce521  movzx   eax, word ptr [rbp+57h+RelativeName.RelativeName+6]
0x1800ce525  mov     word ptr [rbp+57h+NtName+6], ax
0x1800ce529  mov     rax, [rbp+57h+RelativeName.RelativeName.Buffer]
0x1800ce52d  mov     [rbp+57h+NtName.Buffer], rax
0x1800ce531  mov     rax, [rbp+57h+RelativeName.ContainingDirectory]
0x1800ce535  jmp     loc_1800CE3F1
0x1800ce53a  mov     ecx, 3; LastError
0x1800ce53f  call    cs:__imp_RtlSetLastWin32Error
0x1800ce546  nop     dword ptr [rax+rax+00h]
0x1800ce54b  jmp     short loc_1800CE512
0x1800ce54d  xor     ecx, ecx; LastError
0x1800ce54f  call    cs:__imp_RtlSetLastWin32Error
0x1800ce556  nop     dword ptr [rax+rax+00h]
0x1800ce55b  mov     eax, dword ptr [rbp+57h+FileInformation]
0x1800ce55e  jmp     loc_1800CE4C8
```
