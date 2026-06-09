# WcpPrivilegedRemoveFile

- ea: `0x14000eb48`
- end: `0x14000ecbd`
- name: `WcpPrivilegedRemoveFile`
- size: `373`
- prototype: `__int64 __fastcall(POBJECT_ATTRIBUTES ObjectAttributes)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x14000ecc4`

## callees

- `0x14000df1c`
- `0x14000eb48`
- `0x14000fa88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ebb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ebb1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000eb89`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000eb89`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14000eba1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14000eba1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000eca1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000eca1`
- `ntdll!NtSetInformationFile` at `0x14000ec4c`
- `ntdll!NtSetInformationFile` at `0x14000ec4c`
- `ntdll!NtClose` at `0x14000ec86`
- `ntdll!NtClose` at `0x14000ec86`
- `ntdll!RtlNtStatusToDosError` at `0x14000ec62`
- `ntdll!RtlNtStatusToDosError` at `0x14000ec62`
- `ntdll!NtOpenFile` at `0x14000ec03`
- `ntdll!NtOpenFile` at `0x14000ec03`

## pseudocode

```c
__int64 __fastcall WcpPrivilegedRemoveFile(POBJECT_ATTRIBUTES ObjectAttributes, __int64 a2, __int64 a3, __int64 a4)
{
  HANDLE CurrentProcess; // rax
  __int64 v9; // r8
  signed int LastError; // eax
  int v11; // ebx
  int v12; // ebx
  int v13; // eax
  int FileInformation; // [rsp+30h] [rbp-38h] BYREF
  int v16; // [rsp+34h] [rbp-34h] BYREF
  void *FileHandle; // [rsp+38h] [rbp-30h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-28h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+48h] [rbp-20h] BYREF

  FileInformation = 0;
  IoStatusBlock = 0;
  FileHandle = 0;
  TokenHandle = 0;
  v16 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
  {
    v11 = WcpSetPrivilege(TokenHandle, 17, v9, &v16);
    if ( v11 < 0 )
    {
      v12 = v11 | 0x10000000;
      goto LABEL_12;
    }
    v13 = NtOpenFile(&FileHandle, 0x110000u, ObjectAttributes, &IoStatusBlock, 7u, 0x204020u);
    if ( v13 >= 0 )
    {
      v12 = EnsurePathNotRedirected(FileHandle, a2, a3, a4);
      if ( v12 < 0 )
        goto LABEL_12;
      FileInformation = 17;
      v13 = NtSetInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 4u, (FILE_INFORMATION_CLASS)64);
      if ( v13 >= 0 )
      {
        v12 = 0;
        goto LABEL_12;
      }
    }
    LastError = RtlNtStatusToDosError(v13);
  }
  else
  {
    LastError = GetLastError();
  }
  v12 = LastError;
  if ( LastError > 0 )
    v12 = (unsigned __int16)LastError | 0x80070000;
LABEL_12:
  if ( FileHandle && NtClose(FileHandle) < 0 )
    __int2c();
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14000eb48  push    rbp
0x14000eb4a  push    rbx
0x14000eb4b  push    rsi
0x14000eb4c  push    rdi
0x14000eb4d  push    r14
0x14000eb4f  push    r15
0x14000eb51  mov     rbp, rsp
0x14000eb54  sub     rsp, 68h
0x14000eb58  xorps   xmm0, xmm0
0x14000eb5b  mov     [rbp+FileInformation], 0
0x14000eb62  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x14000eb66  mov     rsi, r9
0x14000eb69  mov     [rbp+FileHandle], 0
0x14000eb71  mov     r14, r8
0x14000eb74  mov     [rbp+TokenHandle], 0
0x14000eb7c  mov     r15, rdx
0x14000eb7f  mov     [rbp+var_34], 0
0x14000eb86  mov     rdi, rcx
0x14000eb89  call    cs:__imp_GetCurrentProcess
0x14000eb90  nop     dword ptr [rax+rax+00h]
0x14000eb95  lea     r8, [rbp+TokenHandle]; TokenHandle
0x14000eb99  mov     edx, 28h ; '('; DesiredAccess
0x14000eb9e  mov     rcx, rax; ProcessHandle
0x14000eba1  call    cs:__imp_OpenProcessToken
0x14000eba8  nop     dword ptr [rax+rax+00h]
0x14000ebad  test    eax, eax
0x14000ebaf  jnz     short loc_14000EBC2
0x14000ebb1  call    cs:__imp_GetLastError
0x14000ebb8  nop     dword ptr [rax+rax+00h]
0x14000ebbd  jmp     loc_14000EC6E
0x14000ebc2  mov     rcx, [rbp+TokenHandle]
0x14000ebc6  lea     r9, [rbp+var_34]
0x14000ebca  mov     edx, 11h
0x14000ebcf  call    WcpSetPrivilege
0x14000ebd4  mov     ebx, eax
0x14000ebd6  test    eax, eax
0x14000ebd8  jns     short loc_14000EBE3
0x14000ebda  bts     ebx, 1Ch
0x14000ebde  jmp     loc_14000EC7D
0x14000ebe3  mov     [rsp+68h+OpenOptions], 204020h; OpenOptions
0x14000ebeb  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x14000ebef  mov     r8, rdi; ObjectAttributes
0x14000ebf2  mov     [rsp+68h+ShareAccess], 7; ShareAccess
0x14000ebfa  mov     edx, 110000h; DesiredAccess
0x14000ebff  lea     rcx, [rbp+FileHandle]; FileHandle
0x14000ec03  call    cs:__imp_NtOpenFile
0x14000ec0a  nop     dword ptr [rax+rax+00h]
0x14000ec0f  test    eax, eax
0x14000ec11  js      short loc_14000EC60
0x14000ec13  mov     rcx, [rbp+FileHandle]
0x14000ec17  mov     r9, rsi
0x14000ec1a  mov     r8, r14
0x14000ec1d  mov     rdx, r15
0x14000ec20  call    EnsurePathNotRedirected
0x14000ec25  mov     ebx, eax
0x14000ec27  test    eax, eax
0x14000ec29  js      short loc_14000EC7D
0x14000ec2b  mov     rcx, [rbp+FileHandle]; FileHandle
0x14000ec2f  lea     r8, [rbp+FileInformation]; FileInformation
0x14000ec33  mov     r9d, 4; Length
0x14000ec39  mov     [rbp+FileInformation], 11h
0x14000ec40  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x14000ec44  mov     [rsp+68h+ShareAccess], 40h ; '@'; FileInformationClass
0x14000ec4c  call    cs:__imp_NtSetInformationFile
0x14000ec53  nop     dword ptr [rax+rax+00h]
0x14000ec58  test    eax, eax
0x14000ec5a  js      short loc_14000EC60
0x14000ec5c  xor     ebx, ebx
0x14000ec5e  jmp     short loc_14000EC7D
0x14000ec60  mov     ecx, eax; Status
0x14000ec62  call    cs:__imp_RtlNtStatusToDosError
0x14000ec69  nop     dword ptr [rax+rax+00h]
0x14000ec6e  mov     ebx, eax
0x14000ec70  test    eax, eax
0x14000ec72  jle     short loc_14000EC7D
0x14000ec74  movzx   ebx, ax
0x14000ec77  or      ebx, 80070000h
0x14000ec7d  mov     rcx, [rbp+FileHandle]; Handle
0x14000ec81  test    rcx, rcx
0x14000ec84  jz      short loc_14000EC98
0x14000ec86  call    cs:__imp_NtClose
0x14000ec8d  nop     dword ptr [rax+rax+00h]
0x14000ec92  test    eax, eax
0x14000ec94  jns     short loc_14000EC98
0x14000ec96  int     2Ch; Windows NT - assertion failure
0x14000ec98  mov     rcx, [rbp+TokenHandle]; hObject
0x14000ec9c  test    rcx, rcx
0x14000ec9f  jz      short loc_14000ECAD
0x14000eca1  call    cs:__imp_CloseHandle
0x14000eca8  nop     dword ptr [rax+rax+00h]
0x14000ecad  mov     eax, ebx
0x14000ecaf  add     rsp, 68h
0x14000ecb3  pop     r15
0x14000ecb5  pop     r14
0x14000ecb7  pop     rdi
0x14000ecb8  pop     rsi
0x14000ecb9  pop     rbx
0x14000ecba  pop     rbp
0x14000ecbb  retn
```
