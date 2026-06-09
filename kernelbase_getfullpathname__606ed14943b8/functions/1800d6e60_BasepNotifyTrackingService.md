# BasepNotifyTrackingService

- ea: `0x1800d6e60`
- end: `0x1800d71a8`
- name: `BasepNotifyTrackingService`
- size: `840`
- prototype: `__int64 __fastcall(PHANDLE FileHandle, POBJECT_ATTRIBUTES ObjectAttributes)`
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800d4240`
- `0x180100030`

## callees

- `0x180053c30`
- `0x1800d6e60`
- `0x1801373a0`
- `0x180194eb9`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800d6f18`
- `ntdll!RtlInitUnicodeString` at `0x1800d6f18`
- `ntdll!NtQueryInformationFile` at `0x1800d7027`
- `ntdll!NtQueryInformationFile` at `0x1800d7027`
- `ntdll!NtOpenFile` at `0x1800d6ff2`
- `ntdll!NtOpenFile` at `0x1800d70ce`
- `ntdll!NtOpenFile` at `0x1800d6ff2`
- `ntdll!NtOpenFile` at `0x1800d70ce`
- `ntdll!NtSetInformationFile` at `0x1800d6fad`
- `ntdll!NtSetInformationFile` at `0x1800d7089`
- `ntdll!NtSetInformationFile` at `0x1800d7116`
- `ntdll!NtSetInformationFile` at `0x1800d714e`
- `ntdll!NtSetInformationFile` at `0x1800d6fad`
- `ntdll!NtSetInformationFile` at `0x1800d7089`
- `ntdll!NtSetInformationFile` at `0x1800d7116`
- `ntdll!NtSetInformationFile` at `0x1800d714e`
- `ntdll!RtlUnicodeStringToOemString` at `0x1800d6f31`
- `ntdll!RtlUnicodeStringToOemString` at `0x1800d6f31`
- `ntdll!NtClose` at `0x1800d70e7`
- `ntdll!NtClose` at `0x1800d70e7`
- `ext-ms-win-kernel32-file-l1-1-0!BasepGetComputerNameFromNtPath` at `0x1800d6ed2`
- `ext-ms-win-kernel32-file-l1-1-0!BasepGetComputerNameFromNtPath` at `0x1800d6ed2`

## pseudocode

```c
__int64 __fastcall BasepNotifyTrackingService(
        PHANDLE FileHandle,
        POBJECT_ATTRIBUTES ObjectAttributes,
        __int64 a3,
        __int64 a4)
{
  int ComputerNameFromNtPath; // eax
  NTSTATUS v9; // ebx
  __int64 Length; // rbx
  int v11; // esi
  HANDLE v12; // rcx
  struct _STRING v14; // [rsp+38h] [rbp-200h] BYREF
  int v15; // [rsp+48h] [rbp-1F0h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-1E8h] BYREF
  HANDLE FileHandlea; // [rsp+60h] [rbp-1D8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-1D0h] BYREF
  __int128 v19; // [rsp+78h] [rbp-1C0h] BYREF
  __int128 v20; // [rsp+88h] [rbp-1B0h]
  __int64 v21; // [rsp+98h] [rbp-1A0h]
  __int64 FileInformation; // [rsp+A0h] [rbp-198h] BYREF
  int v23; // [rsp+A8h] [rbp-190h]
  _BYTE v24[36]; // [rsp+ACh] [rbp-18Ch] BYREF
  WCHAR SourceString[16]; // [rsp+D0h] [rbp-168h] BYREF
  char v26; // [rsp+F0h] [rbp-148h] BYREF

  v19 = 0;
  v20 = 0;
  v21 = 0;
  IoStatusBlock = 0;
  v15 = 16;
  if ( (unsigned __int8)IsBasepGetComputerNameFromNtPathPresent() )
    ComputerNameFromNtPath = BasepGetComputerNameFromNtPath(a4, a3, SourceString, &v15);
  else
    ComputerNameFromNtPath = 50;
  if ( ComputerNameFromNtPath )
  {
    v23 = 0;
  }
  else
  {
    *(_DWORD *)(&v14.MaximumLength + 1) = 0;
    DestinationString = 0;
    *(_DWORD *)&v14.Length = 17039360;
    v14.Buffer = &v26;
    RtlInitUnicodeString(&DestinationString, SourceString);
    v9 = RtlUnicodeStringToOemString(&v14, &DestinationString, 0);
    if ( v9 < 0 )
      return (unsigned int)v9;
    if ( v14.Length > 0x1Eu )
      return (unsigned int)-2147483643;
    Length = v14.Length;
    memcpy_0(v24, v14.Buffer, v14.Length);
    v24[Length] = 0;
    v23 = v14.Length + 1;
  }
  FileInformation = a3;
  v9 = NtSetInformationFile(*FileHandle, &IoStatusBlock, &FileInformation, 0x30u, FileTrackingInformation);
  if ( v9 == -1073741790 )
  {
    CloseHandle(*FileHandle);
    v9 = NtOpenFile(FileHandle, 0x100180u, ObjectAttributes, &IoStatusBlock, 7u, 0x20u);
    if ( v9 < 0 )
    {
      *FileHandle = (HANDLE)-1LL;
    }
    else
    {
      v9 = NtQueryInformationFile(*FileHandle, &IoStatusBlock, &v19, 0x28u, FileBasicInformation);
      if ( v9 >= 0 )
      {
        v11 = v21;
        v19 = 0;
        v20 = 0;
        v21 = (unsigned int)v21 & 0xFFFFFFFE;
        v9 = NtSetInformationFile(*FileHandle, &IoStatusBlock, &v19, 0x28u, FileBasicInformation);
        if ( v9 >= 0 )
        {
          FileHandlea = 0;
          v9 = NtOpenFile(&FileHandlea, 0x40100000u, ObjectAttributes, &IoStatusBlock, 7u, 0x20u);
          if ( v9 >= 0 )
          {
            NtClose(*FileHandle);
            v12 = FileHandlea;
            *FileHandle = FileHandlea;
            v9 = NtSetInformationFile(v12, &IoStatusBlock, &FileInformation, 0x30u, FileTrackingInformation);
          }
          if ( v9 < 0 )
          {
            LODWORD(v21) = v11;
            NtSetInformationFile(*FileHandle, &IoStatusBlock, &v19, 0x28u, FileBasicInformation);
          }
        }
      }
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800d6e60  push    rbx
0x1800d6e62  push    rsi
0x1800d6e63  push    rdi
0x1800d6e64  push    r14
0x1800d6e66  sub     rsp, 218h
0x1800d6e6d  mov     rax, cs:__security_cookie
0x1800d6e74  xor     rax, rsp
0x1800d6e77  mov     [rsp+238h+var_38], rax
0x1800d6e7f  mov     rbx, r9
0x1800d6e82  mov     rsi, r8
0x1800d6e85  mov     r14, rdx
0x1800d6e88  mov     rdi, rcx
0x1800d6e8b  xorps   xmm0, xmm0
0x1800d6e8e  xor     eax, eax
0x1800d6e90  movups  [rsp+238h+var_1C0], xmm0
0x1800d6e95  movups  [rsp+238h+var_1B0], xmm0
0x1800d6e9d  mov     [rsp+238h+var_1A0], rax
0x1800d6ea5  movups  xmmword ptr [rsp+238h+IoStatusBlock], xmm0
0x1800d6eaa  mov     [rsp+238h+var_1F0], 10h
0x1800d6eb2  call    IsBasepGetComputerNameFromNtPathPresent
0x1800d6eb7  test    al, al
0x1800d6eb9  jz      loc_1800D7177
0x1800d6ebf  lea     r9, [rsp+238h+var_1F0]
0x1800d6ec4  lea     r8, [rsp+238h+SourceString]
0x1800d6ecc  mov     rdx, rsi
0x1800d6ecf  mov     rcx, rbx
0x1800d6ed2  call    cs:__imp_BasepGetComputerNameFromNtPath
0x1800d6ed9  nop     dword ptr [rax+rax+00h]
0x1800d6ede  test    eax, eax
0x1800d6ee0  jnz     loc_1800D715C
0x1800d6ee6  xorps   xmm0, xmm0
0x1800d6ee9  movups  xmmword ptr [rsp+238h+var_200.Length], xmm0
0x1800d6eee  xorps   xmm1, xmm1
0x1800d6ef1  movups  xmmword ptr [rsp+238h+DestinationString.Length], xmm1
0x1800d6ef6  mov     dword ptr [rsp+238h+var_200.Length], 1040000h
0x1800d6efe  lea     rax, [rsp+238h+var_148]
0x1800d6f06  mov     [rsp+238h+var_200.Buffer], rax
0x1800d6f0b  lea     rdx, [rsp+238h+SourceString]; SourceString
0x1800d6f13  lea     rcx, [rsp+238h+DestinationString]; DestinationString
0x1800d6f18  call    cs:__imp_RtlInitUnicodeString
0x1800d6f1f  nop     dword ptr [rax+rax+00h]
0x1800d6f24  xor     r8d, r8d; AllocateDestinationString
0x1800d6f27  lea     rdx, [rsp+238h+DestinationString]; SourceString
0x1800d6f2c  lea     rcx, [rsp+238h+var_200]; DestinationString
0x1800d6f31  call    cs:__imp_RtlUnicodeStringToOemString
0x1800d6f38  nop     dword ptr [rax+rax+00h]
0x1800d6f3d  mov     ebx, eax
0x1800d6f3f  mov     [rsp+238h+var_208], eax
0x1800d6f43  test    eax, eax
0x1800d6f45  js      loc_1800D7188
0x1800d6f4b  cmp     [rsp+238h+var_200.Length], 1Eh
0x1800d6f51  ja      loc_1800D716C
0x1800d6f57  movzx   ebx, [rsp+238h+var_200.Length]
0x1800d6f5c  mov     r8d, ebx; Size
0x1800d6f5f  mov     rdx, [rsp+238h+var_200.Buffer]; Src
0x1800d6f64  lea     rcx, [rsp+238h+var_18C]; void *
0x1800d6f6c  call    memcpy_0
0x1800d6f71  mov     [rsp+rbx+238h+var_18C], 0
0x1800d6f79  movzx   eax, [rsp+238h+var_200.Length]
0x1800d6f7e  inc     eax
0x1800d6f80  mov     [rsp+238h+var_190], eax
0x1800d6f87  mov     [rsp+238h+FileInformation], rsi
0x1800d6f8f  mov     [rsp+238h+FileInformationClass], 24h ; '$'; FileInformationClass
0x1800d6f97  mov     r9d, 30h ; '0'; Length
0x1800d6f9d  lea     r8, [rsp+238h+FileInformation]; FileInformation
0x1800d6fa5  lea     rdx, [rsp+238h+IoStatusBlock]; IoStatusBlock
0x1800d6faa  mov     rcx, [rdi]; FileHandle
0x1800d6fad  call    cs:__imp_NtSetInformationFile
0x1800d6fb4  nop     dword ptr [rax+rax+00h]
0x1800d6fb9  mov     ebx, eax
0x1800d6fbb  mov     [rsp+238h+var_208], eax
0x1800d6fbf  cmp     eax, 0C0000022h
0x1800d6fc4  jnz     loc_1800D7188
0x1800d6fca  mov     rcx, [rdi]; hObject
0x1800d6fcd  call    CloseHandle
0x1800d6fd2  mov     [rsp+238h+OpenOptions], 20h ; ' '; OpenOptions
0x1800d6fda  mov     [rsp+238h+FileInformationClass], 7; ShareAccess
0x1800d6fe2  lea     r9, [rsp+238h+IoStatusBlock]; IoStatusBlock
0x1800d6fe7  mov     r8, r14; ObjectAttributes
0x1800d6fea  mov     edx, 100180h; DesiredAccess
0x1800d6fef  mov     rcx, rdi; FileHandle
0x1800d6ff2  call    cs:__imp_NtOpenFile
0x1800d6ff9  nop     dword ptr [rax+rax+00h]
0x1800d6ffe  mov     ebx, eax
0x1800d7000  mov     [rsp+238h+var_208], eax
0x1800d7004  test    eax, eax
0x1800d7006  js      loc_1800D7181
0x1800d700c  mov     [rsp+238h+FileInformationClass], 4; FileInformationClass
0x1800d7014  mov     r9d, 28h ; '('; Length
0x1800d701a  lea     r8, [rsp+238h+var_1C0]; FileInformation
0x1800d701f  lea     rdx, [rsp+238h+IoStatusBlock]; IoStatusBlock
0x1800d7024  mov     rcx, [rdi]; FileHandle
0x1800d7027  call    cs:__imp_NtQueryInformationFile
0x1800d702e  nop     dword ptr [rax+rax+00h]
0x1800d7033  mov     ebx, eax
0x1800d7035  mov     [rsp+238h+var_208], eax
0x1800d7039  test    eax, eax
0x1800d703b  js      loc_1800D7188
0x1800d7041  mov     esi, dword ptr [rsp+238h+var_1A0]
0x1800d7048  xorps   xmm0, xmm0
0x1800d704b  xor     eax, eax
0x1800d704d  movups  [rsp+238h+var_1C0], xmm0
0x1800d7052  movups  [rsp+238h+var_1B0], xmm0
0x1800d705a  mov     [rsp+238h+var_1A0], rax
0x1800d7062  mov     eax, esi
0x1800d7064  and     eax, 0FFFFFFFEh
0x1800d7067  mov     dword ptr [rsp+238h+var_1A0], eax
0x1800d706e  mov     [rsp+238h+FileInformationClass], 4; FileInformationClass
0x1800d7076  mov     r9d, 28h ; '('; Length
0x1800d707c  lea     r8, [rsp+238h+var_1C0]; FileInformation
0x1800d7081  lea     rdx, [rsp+238h+IoStatusBlock]; IoStatusBlock
0x1800d7086  mov     rcx, [rdi]; FileHandle
0x1800d7089  call    cs:__imp_NtSetInformationFile
0x1800d7090  nop     dword ptr [rax+rax+00h]
0x1800d7095  mov     ebx, eax
0x1800d7097  mov     [rsp+238h+var_208], eax
0x1800d709b  test    eax, eax
0x1800d709d  js      loc_1800D7188
0x1800d70a3  mov     [rsp+238h+FileHandle], 0
0x1800d70ac  mov     [rsp+238h+OpenOptions], 20h ; ' '; OpenOptions
0x1800d70b4  mov     [rsp+238h+FileInformationClass], 7; ShareAccess
0x1800d70bc  lea     r9, [rsp+238h+IoStatusBlock]; IoStatusBlock
0x1800d70c1  mov     r8, r14; ObjectAttributes
0x1800d70c4  mov     edx, 40100000h; DesiredAccess
0x1800d70c9  lea     rcx, [rsp+238h+FileHandle]; FileHandle
0x1800d70ce  call    cs:__imp_NtOpenFile
0x1800d70d5  nop     dword ptr [rax+rax+00h]
0x1800d70da  mov     ebx, eax
0x1800d70dc  mov     [rsp+238h+var_208], eax
0x1800d70e0  test    eax, eax
0x1800d70e2  js      short loc_1800D7128
0x1800d70e4  mov     rcx, [rdi]; Handle
0x1800d70e7  call    cs:__imp_NtClose
0x1800d70ee  nop     dword ptr [rax+rax+00h]
0x1800d70f3  mov     rcx, [rsp+238h+FileHandle]; FileHandle
0x1800d70f8  mov     [rdi], rcx
0x1800d70fb  mov     [rsp+238h+FileInformationClass], 24h ; '$'; FileInformationClass
0x1800d7103  mov     r9d, 30h ; '0'; Length
0x1800d7109  lea     r8, [rsp+238h+FileInformation]; FileInformation
0x1800d7111  lea     rdx, [rsp+238h+IoStatusBlock]; IoStatusBlock
0x1800d7116  call    cs:__imp_NtSetInformationFile
0x1800d711d  nop     dword ptr [rax+rax+00h]
0x1800d7122  mov     ebx, eax
0x1800d7124  mov     [rsp+238h+var_208], eax
0x1800d7128  test    ebx, ebx
0x1800d712a  jns     short loc_1800D7188
0x1800d712c  mov     dword ptr [rsp+238h+var_1A0], esi
0x1800d7133  mov     [rsp+238h+FileInformationClass], 4; FileInformationClass
0x1800d713b  mov     r9d, 28h ; '('; Length
0x1800d7141  lea     r8, [rsp+238h+var_1C0]; FileInformation
0x1800d7146  lea     rdx, [rsp+238h+IoStatusBlock]; IoStatusBlock
0x1800d714b  mov     rcx, [rdi]; FileHandle
0x1800d714e  call    cs:__imp_NtSetInformationFile
0x1800d7155  nop     dword ptr [rax+rax+00h]
0x1800d715a  jmp     short loc_1800D7188
0x1800d715c  mov     [rsp+238h+var_190], 0
0x1800d7167  jmp     loc_1800D6F87
0x1800d716c  mov     ebx, 80000005h
0x1800d7171  mov     [rsp+238h+var_208], ebx
0x1800d7175  jmp     short loc_1800D7188
0x1800d7177  mov     eax, 32h ; '2'
0x1800d717c  jmp     loc_1800D6EDE
0x1800d7181  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x1800d7188  mov     eax, ebx
0x1800d718a  mov     rcx, [rsp+238h+var_38]
0x1800d7192  xor     rcx, rsp; StackCookie
0x1800d7195  call    __security_check_cookie
0x1800d719a  add     rsp, 218h
0x1800d71a1  pop     r14
0x1800d71a3  pop     rdi
0x1800d71a4  pop     rsi
0x1800d71a5  pop     rbx
0x1800d71a6  retn
0x180197cba  push    rbp
0x180197cbc  sub     rsp, 30h
0x180197cc0  mov     rbp, rdx
0x180197cc3  add     rsp, 30h
0x180197cc7  pop     rbp
0x180197cc8  retn
```
