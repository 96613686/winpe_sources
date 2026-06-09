# CipWriteUnlockTokenToSystemPartition

- ea: `0x180076164`
- end: `0x180076368`
- name: `CipWriteUnlockTokenToSystemPartition`
- size: `516`
- prototype: `__int64 __fastcall(PVOID Buffer, ULONG Length)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180075c88`

## callees

- `0x180076164`
- `0x1800bd4d8`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x180076331`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180076341`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180076331`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180076341`
- `ntoskrnl!ZwClose` at `0x180076247`
- `ntoskrnl!ZwClose` at `0x180076301`
- `ntoskrnl!ZwClose` at `0x180076321`
- `ntoskrnl!ZwClose` at `0x180076247`
- `ntoskrnl!ZwClose` at `0x180076301`
- `ntoskrnl!ZwClose` at `0x180076321`
- `ntoskrnl!ZwCreateFile` at `0x180076233`
- `ntoskrnl!ZwCreateFile` at `0x1800762b1`
- `ntoskrnl!ZwCreateFile` at `0x180076233`
- `ntoskrnl!ZwCreateFile` at `0x1800762b1`
- `ntoskrnl!ZwWriteFile` at `0x1800762eb`
- `ntoskrnl!ZwWriteFile` at `0x1800762eb`

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
0x180076164  mov     [rsp-8+arg_0], rbx
0x180076169  mov     [rsp-8+arg_8], rsi
0x18007616e  push    rbp
0x18007616f  push    rdi
0x180076170  push    r14
0x180076172  lea     rbp, [rsp-47h]
0x180076177  sub     rsp, 0F0h
0x18007617e  xorps   xmm0, xmm0
0x180076181  lea     r8, [rbp+57h+UnicodeString]
0x180076185  mov     edi, edx
0x180076187  xor     r14d, r14d
0x18007618a  xorps   xmm1, xmm1
0x18007618d  mov     [rbp+57h+FileHandle], r14
0x180076191  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180076195  xor     eax, eax
0x180076197  lea     rdx, [rbp+57h+var_80]
0x18007619b  movups  xmmword ptr [rbp+57h+var_40.ObjectName], xmm0
0x18007619f  mov     rsi, rcx
0x1800761a2  mov     [rbp+57h+Handle], r14
0x1800761a6  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800761aa  movups  xmmword ptr [rbp+57h+var_40+1Ch], xmm0
0x1800761ae  movups  xmmword ptr [rbp+57h+UnicodeString.Length], xmm0
0x1800761b2  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800761b6  movups  xmmword ptr [rbp+57h+var_40.Length], xmm0
0x1800761ba  movups  xmmword ptr [rbp+57h+var_80.Length], xmm0
0x1800761be  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x1800761c2  call    CipGetSupplementalPolicyPath
0x1800761c7  mov     ebx, eax
0x1800761c9  test    eax, eax
0x1800761cb  js      loc_180076318
0x1800761d1  mov     [rsp+100h+EaLength], r14d; EaLength
0x1800761d6  lea     rax, [rbp+57h+UnicodeString]
0x1800761da  mov     [rsp+100h+EaBuffer], r14; EaBuffer
0x1800761df  lea     ebx, [r14+30h]
0x1800761e3  mov     [rsp+100h+CreateOptions], 204021h; CreateOptions
0x1800761eb  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800761ef  mov     [rsp+100h+CreateDisposition], 2; CreateDisposition
0x1800761f7  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800761fb  mov     [rsp+100h+ShareAccess], 3; ShareAccess
0x180076203  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180076207  xorps   xmm0, xmm0
0x18007620a  mov     [rsp+100h+FileAttributes], 80h; FileAttributes
0x180076212  mov     edx, 100001h; DesiredAccess
0x180076217  mov     [rsp+100h+AllocationSize], r14; AllocationSize
0x18007621c  mov     [rbp+57h+ObjectAttributes.Length], ebx
0x18007621f  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x180076223  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x18007622a  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18007622e  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180076233  call    cs:__imp_ZwCreateFile
0x18007623a  nop     dword ptr [rax+rax+00h]
0x18007623f  test    eax, eax
0x180076241  js      short loc_180076253
0x180076243  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180076247  call    cs:__imp_ZwClose
0x18007624e  nop     dword ptr [rax+rax+00h]
0x180076253  mov     [rsp+100h+EaLength], r14d; EaLength
0x180076258  lea     rax, [rbp+57h+var_80]
0x18007625c  mov     [rsp+100h+EaBuffer], r14; EaBuffer
0x180076261  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180076265  mov     [rsp+100h+CreateOptions], 60h ; '`'; CreateOptions
0x18007626d  lea     r8, [rbp+57h+var_40]; ObjectAttributes
0x180076271  mov     [rsp+100h+CreateDisposition], 5; CreateDisposition
0x180076279  lea     rcx, [rbp+57h+Handle]; FileHandle
0x18007627d  mov     [rsp+100h+ShareAccess], 1; ShareAccess
0x180076285  xorps   xmm0, xmm0
0x180076288  mov     [rsp+100h+FileAttributes], 80h; FileAttributes
0x180076290  mov     edx, 40010080h; DesiredAccess
0x180076295  mov     [rsp+100h+AllocationSize], r14; AllocationSize
0x18007629a  mov     [rbp+57h+var_40.Length], ebx
0x18007629d  mov     [rbp+57h+var_40.RootDirectory], r14
0x1800762a1  mov     [rbp+57h+var_40.Attributes], 240h
0x1800762a8  mov     [rbp+57h+var_40.ObjectName], rax
0x1800762ac  movdqu  xmmword ptr [rbp+57h+var_40.SecurityDescriptor], xmm0
0x1800762b1  call    cs:__imp_ZwCreateFile
0x1800762b8  nop     dword ptr [rax+rax+00h]
0x1800762bd  mov     ebx, eax
0x1800762bf  test    eax, eax
0x1800762c1  js      short loc_180076318
0x1800762c3  mov     rcx, [rbp+57h+Handle]; FileHandle
0x1800762c7  lea     rax, [rbp+57h+IoStatusBlock]
0x1800762cb  mov     qword ptr [rsp+100h+CreateOptions], r14; Key
0x1800762d0  xor     r9d, r9d; ApcContext
0x1800762d3  mov     qword ptr [rsp+100h+CreateDisposition], r14; ByteOffset
0x1800762d8  xor     r8d, r8d; ApcRoutine
0x1800762db  mov     [rsp+100h+ShareAccess], edi; Length
0x1800762df  xor     edx, edx; Event
0x1800762e1  mov     qword ptr [rsp+100h+FileAttributes], rsi; Buffer
0x1800762e6  mov     [rsp+100h+AllocationSize], rax; IoStatusBlock
0x1800762eb  call    cs:__imp_ZwWriteFile
0x1800762f2  nop     dword ptr [rax+rax+00h]
0x1800762f7  mov     ebx, eax
0x1800762f9  test    eax, eax
0x1800762fb  js      short loc_180076318
0x1800762fd  mov     rcx, [rbp+57h+Handle]; Handle
0x180076301  call    cs:__imp_ZwClose
0x180076308  nop     dword ptr [rax+rax+00h]
0x18007630d  mov     rcx, r14
0x180076310  mov     ebx, eax
0x180076312  mov     [rbp+57h+Handle], rcx
0x180076316  jmp     short loc_18007631C
0x180076318  mov     rcx, [rbp+57h+Handle]; Handle
0x18007631c  test    rcx, rcx
0x18007631f  jz      short loc_18007632D
0x180076321  call    cs:__imp_ZwClose
0x180076328  nop     dword ptr [rax+rax+00h]
0x18007632d  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x180076331  call    cs:__imp_RtlFreeUnicodeString
0x180076338  nop     dword ptr [rax+rax+00h]
0x18007633d  lea     rcx, [rbp+57h+var_80]; UnicodeString
0x180076341  call    cs:__imp_RtlFreeUnicodeString
0x180076348  nop     dword ptr [rax+rax+00h]
0x18007634d  lea     r11, [rsp+100h+var_10]
0x180076355  mov     eax, ebx
0x180076357  mov     rbx, [r11+20h]
0x18007635b  mov     rsi, [r11+28h]
0x18007635f  mov     rsp, r11
0x180076362  pop     r14
0x180076364  pop     rdi
0x180076365  pop     rbp
0x180076366  retn
```
