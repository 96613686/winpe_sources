# CipWriteUnlockTokenToSystemPartition

- ea: `0x180075e84`
- end: `0x180076088`
- name: `CipWriteUnlockTokenToSystemPartition`
- size: `516`
- prototype: `__int64 __fastcall(PVOID Buffer, ULONG Length)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800759a8`

## callees

- `0x180075e84`
- `0x1800bd638`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x180076051`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180076061`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180076051`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180076061`
- `ntoskrnl!ZwClose` at `0x180075f67`
- `ntoskrnl!ZwClose` at `0x180076021`
- `ntoskrnl!ZwClose` at `0x180076041`
- `ntoskrnl!ZwClose` at `0x180075f67`
- `ntoskrnl!ZwClose` at `0x180076021`
- `ntoskrnl!ZwClose` at `0x180076041`
- `ntoskrnl!ZwCreateFile` at `0x180075f53`
- `ntoskrnl!ZwCreateFile` at `0x180075fd1`
- `ntoskrnl!ZwCreateFile` at `0x180075f53`
- `ntoskrnl!ZwCreateFile` at `0x180075fd1`
- `ntoskrnl!ZwWriteFile` at `0x18007600b`
- `ntoskrnl!ZwWriteFile` at `0x18007600b`

## pseudocode

```c
__int64 __fastcall CipWriteUnlockTokenToSystemPartition(PVOID Buffer, ULONG Length)
{
  NTSTATUS SupplementalPolicyPath; // ebx
  NTSTATUS v5; // eax
  HANDLE v6; // rcx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-49h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+70h] [rbp-39h] BYREF
  struct _UNICODE_STRING v10; // [rsp+80h] [rbp-29h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES v12; // [rsp+C0h] [rbp+17h] BYREF
  HANDLE Handle; // [rsp+120h] [rbp+77h] BYREF
  void *FileHandle; // [rsp+128h] [rbp+7Fh] BYREF

  FileHandle = 0;
  Handle = 0;
  UnicodeString = 0;
  memset(&ObjectAttributes, 0, 44);
  memset(&v12, 0, 44);
  v10 = 0;
  IoStatusBlock = 0;
  SupplementalPolicyPath = CipGetSupplementalPolicyPath(Buffer, &v10, &UnicodeString);
  if ( SupplementalPolicyPath < 0 )
    goto LABEL_7;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = &UnicodeString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwCreateFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 3u, 2u, 0x204021u, 0, 0) >= 0 )
    ZwClose(FileHandle);
  v12.Length = 48;
  v12.RootDirectory = 0;
  v12.Attributes = 576;
  v12.ObjectName = &v10;
  *(_OWORD *)&v12.SecurityDescriptor = 0;
  SupplementalPolicyPath = ZwCreateFile(&Handle, 0x40010080u, &v12, &IoStatusBlock, 0, 0x80u, 1u, 5u, 0x60u, 0, 0);
  if ( SupplementalPolicyPath < 0
    || (SupplementalPolicyPath = ZwWriteFile(Handle, 0, 0, 0, &IoStatusBlock, Buffer, Length, 0, 0),
        SupplementalPolicyPath < 0) )
  {
LABEL_7:
    v6 = Handle;
  }
  else
  {
    v5 = ZwClose(Handle);
    v6 = 0;
    SupplementalPolicyPath = v5;
    Handle = 0;
  }
  if ( v6 )
    ZwClose(v6);
  RtlFreeUnicodeString(&UnicodeString);
  RtlFreeUnicodeString(&v10);
  return (unsigned int)SupplementalPolicyPath;
}

```

## disassembly

```asm
0x180075e84  mov     [rsp-8+arg_0], rbx
0x180075e89  mov     [rsp-8+arg_8], rsi
0x180075e8e  push    rbp
0x180075e8f  push    rdi
0x180075e90  push    r14
0x180075e92  lea     rbp, [rsp-47h]
0x180075e97  sub     rsp, 0F0h
0x180075e9e  xorps   xmm0, xmm0
0x180075ea1  lea     r8, [rbp+57h+UnicodeString]
0x180075ea5  mov     edi, edx
0x180075ea7  xor     r14d, r14d
0x180075eaa  xorps   xmm1, xmm1
0x180075ead  mov     [rbp+57h+FileHandle], r14
0x180075eb1  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180075eb5  xor     eax, eax
0x180075eb7  lea     rdx, [rbp+57h+var_80]
0x180075ebb  movups  xmmword ptr [rbp+57h+var_40.ObjectName], xmm0
0x180075ebf  mov     rsi, rcx
0x180075ec2  mov     [rbp+57h+Handle], r14
0x180075ec6  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180075eca  movups  xmmword ptr [rbp+57h+var_40+1Ch], xmm0
0x180075ece  movups  xmmword ptr [rbp+57h+UnicodeString.Length], xmm0
0x180075ed2  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180075ed6  movups  xmmword ptr [rbp+57h+var_40.Length], xmm0
0x180075eda  movups  xmmword ptr [rbp+57h+var_80.Length], xmm0
0x180075ede  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x180075ee2  call    CipGetSupplementalPolicyPath
0x180075ee7  mov     ebx, eax
0x180075ee9  test    eax, eax
0x180075eeb  js      loc_180076038
0x180075ef1  mov     [rsp+100h+EaLength], r14d; EaLength
0x180075ef6  lea     rax, [rbp+57h+UnicodeString]
0x180075efa  mov     [rsp+100h+EaBuffer], r14; EaBuffer
0x180075eff  lea     ebx, [r14+30h]
0x180075f03  mov     [rsp+100h+CreateOptions], 204021h; CreateOptions
0x180075f0b  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180075f0f  mov     [rsp+100h+CreateDisposition], 2; CreateDisposition
0x180075f17  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180075f1b  mov     [rsp+100h+ShareAccess], 3; ShareAccess
0x180075f23  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180075f27  xorps   xmm0, xmm0
0x180075f2a  mov     [rsp+100h+FileAttributes], 80h; FileAttributes
0x180075f32  mov     edx, 100001h; DesiredAccess
0x180075f37  mov     [rsp+100h+AllocationSize], r14; AllocationSize
0x180075f3c  mov     [rbp+57h+ObjectAttributes.Length], ebx
0x180075f3f  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x180075f43  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x180075f4a  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180075f4e  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180075f53  call    cs:__imp_ZwCreateFile
0x180075f5a  nop     dword ptr [rax+rax+00h]
0x180075f5f  test    eax, eax
0x180075f61  js      short loc_180075F73
0x180075f63  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180075f67  call    cs:__imp_ZwClose
0x180075f6e  nop     dword ptr [rax+rax+00h]
0x180075f73  mov     [rsp+100h+EaLength], r14d; EaLength
0x180075f78  lea     rax, [rbp+57h+var_80]
0x180075f7c  mov     [rsp+100h+EaBuffer], r14; EaBuffer
0x180075f81  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180075f85  mov     [rsp+100h+CreateOptions], 60h ; '`'; CreateOptions
0x180075f8d  lea     r8, [rbp+57h+var_40]; ObjectAttributes
0x180075f91  mov     [rsp+100h+CreateDisposition], 5; CreateDisposition
0x180075f99  lea     rcx, [rbp+57h+Handle]; FileHandle
0x180075f9d  mov     [rsp+100h+ShareAccess], 1; ShareAccess
0x180075fa5  xorps   xmm0, xmm0
0x180075fa8  mov     [rsp+100h+FileAttributes], 80h; FileAttributes
0x180075fb0  mov     edx, 40010080h; DesiredAccess
0x180075fb5  mov     [rsp+100h+AllocationSize], r14; AllocationSize
0x180075fba  mov     [rbp+57h+var_40.Length], ebx
0x180075fbd  mov     [rbp+57h+var_40.RootDirectory], r14
0x180075fc1  mov     [rbp+57h+var_40.Attributes], 240h
0x180075fc8  mov     [rbp+57h+var_40.ObjectName], rax
0x180075fcc  movdqu  xmmword ptr [rbp+57h+var_40.SecurityDescriptor], xmm0
0x180075fd1  call    cs:__imp_ZwCreateFile
0x180075fd8  nop     dword ptr [rax+rax+00h]
0x180075fdd  mov     ebx, eax
0x180075fdf  test    eax, eax
0x180075fe1  js      short loc_180076038
0x180075fe3  mov     rcx, [rbp+57h+Handle]; FileHandle
0x180075fe7  lea     rax, [rbp+57h+IoStatusBlock]
0x180075feb  mov     qword ptr [rsp+100h+CreateOptions], r14; Key
0x180075ff0  xor     r9d, r9d; ApcContext
0x180075ff3  mov     qword ptr [rsp+100h+CreateDisposition], r14; ByteOffset
0x180075ff8  xor     r8d, r8d; ApcRoutine
0x180075ffb  mov     [rsp+100h+ShareAccess], edi; Length
0x180075fff  xor     edx, edx; Event
0x180076001  mov     qword ptr [rsp+100h+FileAttributes], rsi; Buffer
0x180076006  mov     [rsp+100h+AllocationSize], rax; IoStatusBlock
0x18007600b  call    cs:__imp_ZwWriteFile
0x180076012  nop     dword ptr [rax+rax+00h]
0x180076017  mov     ebx, eax
0x180076019  test    eax, eax
0x18007601b  js      short loc_180076038
0x18007601d  mov     rcx, [rbp+57h+Handle]; Handle
0x180076021  call    cs:__imp_ZwClose
0x180076028  nop     dword ptr [rax+rax+00h]
0x18007602d  mov     rcx, r14
0x180076030  mov     ebx, eax
0x180076032  mov     [rbp+57h+Handle], rcx
0x180076036  jmp     short loc_18007603C
0x180076038  mov     rcx, [rbp+57h+Handle]; Handle
0x18007603c  test    rcx, rcx
0x18007603f  jz      short loc_18007604D
0x180076041  call    cs:__imp_ZwClose
0x180076048  nop     dword ptr [rax+rax+00h]
0x18007604d  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x180076051  call    cs:__imp_RtlFreeUnicodeString
0x180076058  nop     dword ptr [rax+rax+00h]
0x18007605d  lea     rcx, [rbp+57h+var_80]; UnicodeString
0x180076061  call    cs:__imp_RtlFreeUnicodeString
0x180076068  nop     dword ptr [rax+rax+00h]
0x18007606d  lea     r11, [rsp+100h+var_10]
0x180076075  mov     eax, ebx
0x180076077  mov     rbx, [r11+20h]
0x18007607b  mov     rsi, [r11+28h]
0x18007607f  mov     rsp, r11
0x180076082  pop     r14
0x180076084  pop     rdi
0x180076085  pop     rbp
0x180076086  retn
```
