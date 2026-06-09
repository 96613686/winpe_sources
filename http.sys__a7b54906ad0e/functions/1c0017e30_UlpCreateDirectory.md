# UlpCreateDirectory

- ea: `0x1c0017e30`
- end: `0x1c0017f68`
- name: `UlpCreateDirectory`
- size: `312`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1c00d56c0`

## callees

- `0x1c0017e30`
- `0x1c00d5938`

## import_xrefs

- `ntoskrnl!SeImpersonateClientEx` at `0x1c0028ae9`
- `ntoskrnl!SeImpersonateClientEx` at `0x1c0028ae9`
- `ntoskrnl!ZwCreateFile` at `0x1c0017ee6`
- `ntoskrnl!ZwCreateFile` at `0x1c0017ee6`
- `ntoskrnl!PsRevertToSelf` at `0x1c0028b07`
- `ntoskrnl!PsRevertToSelf` at `0x1c0028b07`
- `ntoskrnl!ZwClose` at `0x1c0028b3d`
- `ntoskrnl!ZwClose` at `0x1c0028b3d`

## pseudocode

```c
NTSTATUS __fastcall UlpCreateDirectory(
        struct _UNICODE_STRING *a1,
        void *a2,
        char a3,
        struct _SECURITY_CLIENT_CONTEXT *a4,
        char a5,
        char a6,
        void **a7,
        _BYTE *a8)
{
  _BYTE *v9; // r15
  void **v10; // r12
  int v11; // ebx
  char v13; // si
  NTSTATUS LogFileSecurity; // ebx
  NTSTATUS result; // eax
  void *v16; // rdx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-29h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-19h] BYREF
  void *FileHandle; // [rsp+D0h] [rbp+47h] BYREF

  v9 = a8;
  v10 = a7;
  FileHandle = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  v11 = a5 != 0 ? 0xE0000 : 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 1600;
  *a8 = 0;
  *v10 = 0;
  v13 = 0;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = a1;
  ObjectAttributes.SecurityDescriptor = a2;
  ObjectAttributes.SecurityQualityOfService = 0;
  IoStatusBlock = 0;
  if ( !a4 )
  {
LABEL_2:
    LogFileSecurity = ZwCreateFile(&FileHandle, v11 + 33, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 1u, 3u, 1u, 0, 0);
    if ( v13 )
      PsRevertToSelf();
    if ( LogFileSecurity < 0 )
      return LogFileSecurity;
    result = IoStatusBlock.Status;
    if ( IoStatusBlock.Status < 0 )
      return result;
    if ( a5 )
    {
      v16 = 0;
      if ( IoStatusBlock.Information == 1 )
      {
        if ( a6 || !a2 )
          goto LABEL_7;
        v16 = a2;
        *v9 = 1;
      }
      else if ( !a6 || !a3 )
      {
        goto LABEL_7;
      }
      LogFileSecurity = UlpQueryLogFileSecurity(FileHandle, v16);
    }
LABEL_7:
    if ( LogFileSecurity < 0 )
    {
      if ( FileHandle )
        ZwClose(FileHandle);
    }
    else
    {
      *v10 = FileHandle;
    }
    return LogFileSecurity;
  }
  result = SeImpersonateClientEx(a4, 0);
  if ( result >= 0 )
  {
    v13 = 1;
    goto LABEL_2;
  }
  return result;
}

```

## disassembly

```asm
0x1c0017e30  mov     [rsp-8+arg_8], rbx
0x1c0017e35  mov     [rsp-8+arg_10], rsi
0x1c0017e3a  push    rbp
0x1c0017e3b  push    rdi
0x1c0017e3c  push    r12
0x1c0017e3e  push    r13
0x1c0017e40  push    r15
0x1c0017e42  lea     rbp, [rsp-17h]
0x1c0017e47  sub     rsp, 0A0h
0x1c0017e4e  mov     al, [rbp+37h+arg_20]
0x1c0017e51  mov     rdi, rdx
0x1c0017e54  mov     r15, [rbp+37h+arg_38]
0x1c0017e58  xor     edx, edx; ServerThread
0x1c0017e5a  mov     r12, [rbp+37h+arg_30]
0x1c0017e5e  neg     al
0x1c0017e60  xorps   xmm0, xmm0
0x1c0017e63  mov     [rbp+37h+FileHandle], rdx
0x1c0017e67  sbb     ebx, ebx
0x1c0017e69  mov     qword ptr [rbp+37h+ObjectAttributes.Length], 30h ; '0'
0x1c0017e71  and     ebx, 0E0000h
0x1c0017e77  mov     qword ptr [rbp+37h+ObjectAttributes.Attributes], 640h
0x1c0017e7f  mov     [r15], dl
0x1c0017e82  mov     r13b, r8b
0x1c0017e85  mov     [r12], rdx
0x1c0017e89  mov     sil, dl
0x1c0017e8c  mov     [rbp+37h+ObjectAttributes.RootDirectory], rdx
0x1c0017e90  mov     [rbp+37h+ObjectAttributes.ObjectName], rcx
0x1c0017e94  mov     [rbp+37h+ObjectAttributes.SecurityDescriptor], rdi
0x1c0017e98  mov     [rbp+37h+ObjectAttributes.SecurityQualityOfService], rdx
0x1c0017e9c  movups  xmmword ptr [rbp+37h+IoStatusBlock], xmm0
0x1c0017ea0  test    r9, r9
0x1c0017ea3  jnz     loc_1C0028AE6
0x1c0017ea9  mov     [rsp+0C0h+EaLength], edx; EaLength
0x1c0017ead  lea     r9, [rbp+37h+IoStatusBlock]; IoStatusBlock
0x1c0017eb1  mov     [rsp+0C0h+EaBuffer], rdx; EaBuffer
0x1c0017eb6  lea     r8, [rbp+37h+ObjectAttributes]; ObjectAttributes
0x1c0017eba  mov     [rsp+0C0h+CreateOptions], 1; CreateOptions
0x1c0017ec2  lea     rcx, [rbp+37h+FileHandle]; FileHandle
0x1c0017ec6  mov     [rsp+0C0h+CreateDisposition], 3; CreateDisposition
0x1c0017ece  mov     [rsp+0C0h+ShareAccess], 1; ShareAccess
0x1c0017ed6  mov     [rsp+0C0h+FileAttributes], 80h; FileAttributes
0x1c0017ede  mov     [rsp+0C0h+AllocationSize], rdx; AllocationSize
0x1c0017ee3  lea     edx, [rbx+21h]; DesiredAccess
0x1c0017ee6  call    cs:__imp_ZwCreateFile
0x1c0017eed  nop     dword ptr [rax+rax+00h]
0x1c0017ef2  mov     ebx, eax
0x1c0017ef4  test    sil, sil
0x1c0017ef7  jnz     loc_1C0028B07
0x1c0017efd  test    ebx, ebx
0x1c0017eff  js      short loc_1C0017F1E
0x1c0017f01  mov     eax, dword ptr [rbp+37h+IoStatusBlock]
0x1c0017f04  test    eax, eax
0x1c0017f06  js      short loc_1C0017F20
0x1c0017f08  cmp     [rbp+37h+arg_20], 0
0x1c0017f0c  jnz     short loc_1C0017F3D
0x1c0017f0e  test    ebx, ebx
0x1c0017f10  js      loc_1C0028B30
0x1c0017f16  mov     rax, [rbp+37h+FileHandle]
0x1c0017f1a  mov     [r12], rax
0x1c0017f1e  mov     eax, ebx
0x1c0017f20  lea     r11, [rsp+0C0h+var_20]
0x1c0017f28  mov     rbx, [r11+38h]
0x1c0017f2c  mov     rsi, [r11+40h]
0x1c0017f30  mov     rsp, r11
0x1c0017f33  pop     r15
0x1c0017f35  pop     r13
0x1c0017f37  pop     r12
0x1c0017f39  pop     rdi
0x1c0017f3a  pop     rbp
0x1c0017f3b  retn
0x1c0017f3d  xor     edx, edx
0x1c0017f3f  cmp     [rbp+37h+IoStatusBlock.Information], 1
0x1c0017f44  jnz     loc_1C0028B19
0x1c0017f4a  cmp     [rbp+37h+arg_28], dl
0x1c0017f4d  jnz     short loc_1C0017F0E
0x1c0017f4f  test    rdi, rdi
0x1c0017f52  jz      short loc_1C0017F0E
0x1c0017f54  mov     rdx, rdi; SecurityDescriptor
0x1c0017f57  mov     byte ptr [r15], 1
0x1c0017f5b  mov     rcx, [rbp+37h+FileHandle]; Handle
0x1c0017f5f  call    UlpQueryLogFileSecurity
0x1c0017f64  mov     ebx, eax
0x1c0017f66  jmp     short loc_1C0017F0E
0x1c0028ae6  mov     rcx, r9; ClientContext
0x1c0028ae9  call    cs:__imp_SeImpersonateClientEx
0x1c0028af0  nop     dword ptr [rax+rax+00h]
0x1c0028af5  xor     edx, edx
0x1c0028af7  test    eax, eax
0x1c0028af9  js      loc_1C0017F20
0x1c0028aff  mov     sil, 1
0x1c0028b02  jmp     loc_1C0017EA9
0x1c0028b07  call    cs:__imp_PsRevertToSelf
0x1c0028b0e  nop     dword ptr [rax+rax+00h]
0x1c0028b13  nop
0x1c0028b14  jmp     loc_1C0017EFD
0x1c0028b19  cmp     [rbp+37h+arg_28], dl
0x1c0028b1c  jz      loc_1C0017F0E
0x1c0028b22  test    r13b, r13b
0x1c0028b25  jz      loc_1C0017F0E
0x1c0028b2b  jmp     loc_1C0017F5B
0x1c0028b30  mov     rcx, [rbp+37h+FileHandle]; Handle
0x1c0028b34  test    rcx, rcx
0x1c0028b37  jz      loc_1C0017F1E
0x1c0028b3d  call    cs:__imp_ZwClose
0x1c0028b44  nop     dword ptr [rax+rax+00h]
0x1c0028b49  nop
0x1c0028b4a  jmp     loc_1C0017F1E
```
