# GetCompressedFileSizeW

- ea: `0x1800c7fa0`
- end: `0x1800c8164`
- name: `GetCompressedFileSizeW`
- size: `452`
- prototype: `DWORD __stdcall(LPCWSTR lpFileName, LPDWORD lpFileSizeHigh)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800c7f50`

## callees

- `0x1800134a0`
- `0x1800c7fa0`
- `0x1800c8170`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x1800c8005`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x1800c8005`
- `ntdll!RtlReleaseRelativeName` at `0x1800c807a`
- `ntdll!RtlReleaseRelativeName` at `0x1800c807a`
- `ntdll!NtQueryInformationFile` at `0x1800c80b6`
- `ntdll!NtQueryInformationFile` at `0x1800c80b6`
- `ntdll!NtOpenFile` at `0x1800c806e`
- `ntdll!NtOpenFile` at `0x1800c806e`
- `ntdll!RtlSetLastWin32Error` at `0x1800c814c`
- `ntdll!RtlSetLastWin32Error` at `0x1800c8156`
- `ntdll!RtlSetLastWin32Error` at `0x1800c814c`
- `ntdll!RtlSetLastWin32Error` at `0x1800c8156`
- `ntdll!NtClose` at `0x1800c80c4`
- `ntdll!NtClose` at `0x1800c810e`
- `ntdll!NtClose` at `0x1800c80c4`
- `ntdll!NtClose` at `0x1800c810e`
- `ntdll!RtlFreeHeap` at `0x1800c8092`
- `ntdll!RtlFreeHeap` at `0x1800c8092`

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
0x1800c7fa0  mov     [rsp-8+arg_10], rbx
0x1800c7fa5  mov     [rsp-8+arg_18], rsi
0x1800c7faa  push    rbp
0x1800c7fab  push    rdi
0x1800c7fac  push    r14
0x1800c7fae  lea     rbp, [rsp-47h]
0x1800c7fb3  sub     rsp, 0C0h
0x1800c7fba  mov     rax, cs:__security_cookie
0x1800c7fc1  xor     rax, rsp
0x1800c7fc4  mov     [rbp+57h+var_18], rax
0x1800c7fc8  xorps   xmm0, xmm0
0x1800c7fcb  lea     r9, [rbp+57h+RelativeName]; RelativeName
0x1800c7fcf  xorps   xmm1, xmm1
0x1800c7fd2  mov     rbx, rdx
0x1800c7fd5  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800c7fd9  xor     r14d, r14d
0x1800c7fdc  lea     rdx, [rbp+57h+NtName]; NtName
0x1800c7fe0  xor     eax, eax
0x1800c7fe2  mov     [rbp+57h+FileHandle], r14
0x1800c7fe6  xor     r8d, r8d; PartName
0x1800c7fe9  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800c7fed  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800c7ff1  movups  xmmword ptr [rbp+57h+NtName.Length], xmm0
0x1800c7ff5  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x1800c7ff9  movups  [rbp+57h+FileInformation], xmm0
0x1800c7ffd  movups  xmmword ptr [rbp+57h+RelativeName.RelativeName.Length], xmm1
0x1800c8001  movups  xmmword ptr [rbp+57h+RelativeName.ContainingDirectory], xmm1
0x1800c8005  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x1800c800b  test    al, al
0x1800c800d  jz      loc_1800C8147
0x1800c8013  movzx   eax, [rbp+57h+RelativeName.RelativeName.Length]
0x1800c8017  mov     rsi, [rbp+57h+NtName.Buffer]
0x1800c801b  test    ax, ax
0x1800c801e  jnz     loc_1800C8124
0x1800c8024  mov     eax, r14d
0x1800c8027  mov     [rbp+57h+RelativeName.ContainingDirectory], rax
0x1800c802b  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x1800c802f  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800c8033  lea     rax, [rbp+57h+NtName]
0x1800c8037  mov     [rsp+0D0h+OpenOptions], 4000h; OpenOptions
0x1800c803f  xorps   xmm0, xmm0
0x1800c8042  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800c8046  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800c804a  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800c8051  mov     edx, 80h; DesiredAccess
0x1800c8056  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800c805d  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800c8061  mov     [rsp+0D0h+ShareAccess], 7; ShareAccess
0x1800c8069  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800c806e  call    cs:__imp_NtOpenFile
0x1800c8074  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x1800c8078  mov     edi, eax
0x1800c807a  call    cs:__imp_RtlReleaseRelativeName
0x1800c8080  mov     rcx, gs:60h
0x1800c8089  mov     r8, rsi; P
0x1800c808c  xor     edx, edx; Flags
0x1800c808e  mov     rcx, [rcx+30h]; HeapHandle
0x1800c8092  call    cs:__imp_RtlFreeHeap
0x1800c8098  test    edi, edi
0x1800c809a  js      short loc_1800C8118
0x1800c809c  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800c80a0  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x1800c80a4  mov     r9d, 10h; Length
0x1800c80aa  mov     [rsp+0D0h+ShareAccess], 1Ch; FileInformationClass
0x1800c80b2  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800c80b6  call    cs:__imp_NtQueryInformationFile
0x1800c80bc  mov     rcx, [rbp+57h+FileHandle]; hFile
0x1800c80c0  test    eax, eax
0x1800c80c2  js      short loc_1800C8100
0x1800c80c4  call    cs:__imp_NtClose
0x1800c80ca  test    rbx, rbx
0x1800c80cd  jz      short loc_1800C80D4
0x1800c80cf  mov     eax, dword ptr [rbp+57h+FileInformation+4]
0x1800c80d2  mov     [rbx], eax
0x1800c80d4  mov     eax, dword ptr [rbp+57h+FileInformation]
0x1800c80d7  cmp     eax, 0FFFFFFFFh
0x1800c80da  jz      short loc_1800C8154
0x1800c80dc  mov     rcx, [rbp+57h+var_18]
0x1800c80e0  xor     rcx, rsp; StackCookie
0x1800c80e3  call    __security_check_cookie
0x1800c80e8  lea     r11, [rsp+0D0h+var_10]
0x1800c80f0  mov     rbx, [r11+30h]
0x1800c80f4  mov     rsi, [r11+38h]
0x1800c80f8  mov     rsp, r11
0x1800c80fb  pop     r14
0x1800c80fd  pop     rdi
0x1800c80fe  pop     rbp
0x1800c80ff  retn
0x1800c8100  mov     rdx, rbx; lpFileSizeHigh
0x1800c8103  call    GetFileSize
0x1800c8108  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800c810c  mov     ebx, eax
0x1800c810e  call    cs:__imp_NtClose
0x1800c8114  mov     eax, ebx
0x1800c8116  jmp     short loc_1800C80DC
0x1800c8118  mov     ecx, edi
0x1800c811a  call    BaseSetLastNTError
0x1800c811f  or      eax, 0FFFFFFFFh
0x1800c8122  jmp     short loc_1800C80DC
0x1800c8124  mov     [rbp+57h+NtName.Length], ax
0x1800c8128  mov     eax, dword ptr [rbp+57h+RelativeName.RelativeName.MaximumLength]
0x1800c812b  mov     dword ptr [rbp+57h+NtName.MaximumLength], eax
0x1800c812e  movzx   eax, word ptr [rbp+57h+RelativeName.RelativeName+6]
0x1800c8132  mov     word ptr [rbp+57h+NtName+6], ax
0x1800c8136  mov     rax, [rbp+57h+RelativeName.RelativeName.Buffer]
0x1800c813a  mov     [rbp+57h+NtName.Buffer], rax
0x1800c813e  mov     rax, [rbp+57h+RelativeName.ContainingDirectory]
0x1800c8142  jmp     loc_1800C802B
0x1800c8147  mov     ecx, 3; LastError
0x1800c814c  call    cs:__imp_RtlSetLastWin32Error
0x1800c8152  jmp     short loc_1800C811F
0x1800c8154  xor     ecx, ecx; LastError
0x1800c8156  call    cs:__imp_RtlSetLastWin32Error
0x1800c815c  mov     eax, dword ptr [rbp+57h+FileInformation]
0x1800c815f  jmp     loc_1800C80DC
```
