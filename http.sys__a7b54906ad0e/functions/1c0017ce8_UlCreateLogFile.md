# UlCreateLogFile

- ea: `0x1c0017ce8`
- end: `0x1c0017e28`
- name: `UlCreateLogFile`
- size: `320`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1c0017690`
- `0x1c0033f60`

## callees

- `0x1c0017ce8`
- `0x1c0018040`
- `0x1c009846c`
- `0x1c00d5938`
- `0x1c00d5aa0`

## import_xrefs

- `ntoskrnl!SeImpersonateClientEx` at `0x1c0028a29`
- `ntoskrnl!SeImpersonateClientEx` at `0x1c0028a29`
- `ntoskrnl!ZwCreateFile` at `0x1c0017da3`
- `ntoskrnl!ZwCreateFile` at `0x1c0017da3`
- `ntoskrnl!PsRevertToSelf` at `0x1c0028a47`
- `ntoskrnl!PsRevertToSelf` at `0x1c0028a47`
- `ntoskrnl!ZwClose` at `0x1c0028aa3`
- `ntoskrnl!ZwClose` at `0x1c0028aa3`

## pseudocode

```c
__int64 __fastcall UlCreateLogFile(
        struct _UNICODE_STRING *a1,
        _OWORD *a2,
        struct _SECURITY_CLIENT_CONTEXT *a3,
        char a4,
        void **a5)
{
  void **v5; // r12
  char v6; // r14
  _OWORD *v7; // rdi
  int v11; // edx
  NTSTATUS LogFileSecurity; // ebx
  int v13; // ecx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+68h] [rbp-41h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+78h] [rbp-31h] BYREF
  __int64 v17; // [rsp+98h] [rbp-11h]
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-9h] BYREF
  void *FileHandle; // [rsp+108h] [rbp+5Fh] BYREF

  v5 = a5;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  v6 = 0;
  FileHandle = 0;
  v7 = 0;
  *a5 = 0;
  ObjectAttributes.RootDirectory = 0;
  v17 = 0;
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 1600;
  ObjectAttributes.ObjectName = a1;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  IoStatusBlock = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( a3 )
  {
    LogFileSecurity = SeImpersonateClientEx(a3, 0);
    if ( LogFileSecurity < 0 )
      goto LABEL_13;
    v6 = 1;
  }
  LogFileSecurity = ZwCreateFile(
                      &FileHandle,
                      0x120116u,
                      &ObjectAttributes,
                      &IoStatusBlock,
                      0,
                      0x80u,
                      1u,
                      3u,
                      0x40u,
                      0,
                      0);
  if ( v6 )
    PsRevertToSelf();
  if ( LogFileSecurity < 0 )
    goto LABEL_13;
  if ( !a4 || IoStatusBlock.Information != 1 )
    goto LABEL_7;
  if ( a2 )
  {
    v7 = a2;
  }
  else
  {
    LogFileSecurity = UlpBuildSecurityToLogFile(SecurityDescriptor);
    if ( LogFileSecurity < 0 )
      goto LABEL_13;
    v7 = SecurityDescriptor;
  }
  LogFileSecurity = UlpQueryLogFileSecurity(FileHandle, v7);
  if ( LogFileSecurity >= 0 )
  {
LABEL_7:
    v13 = (int)FileHandle;
    *v5 = FileHandle;
    goto LABEL_8;
  }
LABEL_13:
  v13 = (int)FileHandle;
  if ( FileHandle )
    ZwClose(FileHandle);
LABEL_8:
  if ( v7 == SecurityDescriptor )
    UlCleanupSecurityDescriptor(v7);
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x400) != 0 )
    WPP_SF_SddP(v13, v11, a1->Buffer, LogFileSecurity, IoStatusBlock.Status, IoStatusBlock.Information);
  return (unsigned int)LogFileSecurity;
}

```

## disassembly

```asm
0x1c0017ce8  mov     rax, rsp
0x1c0017ceb  mov     [rax+10h], rbx
0x1c0017cef  mov     [rax+18h], rsi
0x1c0017cf3  mov     [rax+20h], rdi
0x1c0017cf7  push    rbp
0x1c0017cf8  push    r12
0x1c0017cfa  push    r13
0x1c0017cfc  push    r14
0x1c0017cfe  push    r15
0x1c0017d00  lea     rbp, [rax-57h]
0x1c0017d04  sub     rsp, 0D0h
0x1c0017d0b  mov     r12, [rbp+4Fh+arg_20]
0x1c0017d0f  xor     eax, eax
0x1c0017d11  and     dword ptr [rbp+4Fh+ObjectAttributes+4], eax
0x1c0017d14  xorps   xmm0, xmm0
0x1c0017d17  and     dword ptr [rbp+4Fh+ObjectAttributes+1Ch], eax
0x1c0017d1a  xor     r14b, r14b
0x1c0017d1d  and     [rbp+4Fh+FileHandle], rax
0x1c0017d21  xor     edi, edi
0x1c0017d23  and     [r12], rax
0x1c0017d27  mov     r15b, r9b
0x1c0017d2a  and     [rbp+4Fh+ObjectAttributes.RootDirectory], rax
0x1c0017d2e  mov     rsi, rdx
0x1c0017d31  mov     [rbp+4Fh+var_60], rax
0x1c0017d35  mov     r13, rcx
0x1c0017d38  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x1c0017d3f  mov     [rbp+4Fh+ObjectAttributes.Attributes], 640h
0x1c0017d46  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rcx
0x1c0017d4a  movups  [rbp+4Fh+SecurityDescriptor], xmm0
0x1c0017d4e  movups  [rbp+4Fh+var_70], xmm0
0x1c0017d52  movups  xmmword ptr [rbp+4Fh+IoStatusBlock], xmm0
0x1c0017d56  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x1c0017d5b  test    r8, r8
0x1c0017d5e  jnz     loc_1C0028A24
0x1c0017d64  and     [rsp+0F0h+var_A0], edi
0x1c0017d68  lea     r9, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x1c0017d6c  and     qword ptr [rsp+0F0h+var_A8], rdi
0x1c0017d71  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x1c0017d75  mov     [rsp+0F0h+CreateOptions], 40h ; '@'; CreateOptions
0x1c0017d7d  lea     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x1c0017d81  mov     [rsp+0F0h+CreateDisposition], 3; CreateDisposition
0x1c0017d89  mov     edx, 120116h; DesiredAccess
0x1c0017d8e  mov     [rsp+0F0h+ShareAccess], 1; ShareAccess
0x1c0017d96  mov     [rsp+0F0h+FileAttributes], 80h; FileAttributes
0x1c0017d9e  and     [rsp+0F0h+var_D0], rdi
0x1c0017da3  call    cs:__imp_ZwCreateFile
0x1c0017daa  nop     dword ptr [rax+rax+00h]
0x1c0017daf  mov     ebx, eax
0x1c0017db1  test    r14b, r14b
0x1c0017db4  jnz     loc_1C0028A47
0x1c0017dba  test    ebx, ebx
0x1c0017dbc  js      short loc_1C0017E1F
0x1c0017dbe  test    r15b, r15b
0x1c0017dc1  jz      short loc_1C0017DCE
0x1c0017dc3  cmp     [rbp+4Fh+IoStatusBlock.Information], 1
0x1c0017dc8  jz      loc_1C0028A59
0x1c0017dce  mov     rcx, [rbp+4Fh+FileHandle]; Handle
0x1c0017dd2  mov     [r12], rcx
0x1c0017dd6  test    ebx, ebx
0x1c0017dd8  js      loc_1C0028A9A
0x1c0017dde  lea     rax, [rbp+4Fh+SecurityDescriptor]
0x1c0017de2  cmp     rdi, rax
0x1c0017de5  jz      loc_1C0028AB5
0x1c0017deb  test    dword ptr cs:WPP_MAIN_CB.Queue, 400h
0x1c0017df5  jnz     loc_1C0028AC3
0x1c0017dfb  lea     r11, [rsp+0F0h+var_20]
0x1c0017e03  mov     eax, ebx
0x1c0017e05  mov     rbx, [r11+38h]
0x1c0017e09  mov     rsi, [r11+40h]
0x1c0017e0d  mov     rdi, [r11+48h]
0x1c0017e11  mov     rsp, r11
0x1c0017e14  pop     r15
0x1c0017e16  pop     r14
0x1c0017e18  pop     r13
0x1c0017e1a  pop     r12
0x1c0017e1c  pop     rbp
0x1c0017e1d  retn
0x1c0017e1f  mov     rcx, [rbp+4Fh+FileHandle]
0x1c0017e23  jmp     loc_1C0028A9A
0x1c0028a24  xor     edx, edx; ServerThread
0x1c0028a26  mov     rcx, r8; ClientContext
0x1c0028a29  call    cs:__imp_SeImpersonateClientEx
0x1c0028a30  nop     dword ptr [rax+rax+00h]
0x1c0028a35  mov     ebx, eax
0x1c0028a37  test    eax, eax
0x1c0028a39  js      loc_1C0017E1F
0x1c0028a3f  mov     r14b, 1
0x1c0028a42  jmp     loc_1C0017D64
0x1c0028a47  call    cs:__imp_PsRevertToSelf
0x1c0028a4e  nop     dword ptr [rax+rax+00h]
0x1c0028a53  nop
0x1c0028a54  jmp     loc_1C0017DBA
0x1c0028a59  test    rsi, rsi
0x1c0028a5c  jnz     short loc_1C0028A7C
0x1c0028a5e  mov     r8b, 1
0x1c0028a61  lea     rcx, [rbp+4Fh+SecurityDescriptor]; SecurityDescriptor
0x1c0028a65  xor     edx, edx
0x1c0028a67  call    UlpBuildSecurityToLogFile
0x1c0028a6c  mov     ebx, eax
0x1c0028a6e  test    eax, eax
0x1c0028a70  js      loc_1C0017E1F
0x1c0028a76  lea     rdi, [rbp+4Fh+SecurityDescriptor]
0x1c0028a7a  jmp     short loc_1C0028A7F
0x1c0028a7c  mov     rdi, rsi
0x1c0028a7f  mov     rcx, [rbp+4Fh+FileHandle]; Handle
0x1c0028a83  mov     rdx, rdi; SecurityDescriptor
0x1c0028a86  call    UlpQueryLogFileSecurity
0x1c0028a8b  mov     ebx, eax
0x1c0028a8d  test    eax, eax
0x1c0028a8f  js      loc_1C0017E1F
0x1c0028a95  jmp     loc_1C0017DCE
0x1c0028a9a  test    rcx, rcx
0x1c0028a9d  jz      loc_1C0017DDE
0x1c0028aa3  call    cs:__imp_ZwClose
0x1c0028aaa  nop     dword ptr [rax+rax+00h]
0x1c0028aaf  nop
0x1c0028ab0  jmp     loc_1C0017DDE
0x1c0028ab5  mov     rcx, rdi
0x1c0028ab8  call    UlCleanupSecurityDescriptor
0x1c0028abd  nop
0x1c0028abe  jmp     loc_1C0017DEB
0x1c0028ac3  mov     rax, [rbp+4Fh+IoStatusBlock.Information]
0x1c0028ac7  mov     r9d, ebx
0x1c0028aca  mov     r8, [r13+8]
0x1c0028ace  mov     qword ptr [rsp+0F0h+FileAttributes], rax
0x1c0028ad3  mov     eax, dword ptr [rbp+4Fh+IoStatusBlock]
0x1c0028ad6  mov     dword ptr [rsp+0F0h+var_D0], eax
0x1c0028ada  call    WPP_SF_SddP
0x1c0028adf  nop
0x1c0028ae0  jmp     loc_1C0017DFB
```
