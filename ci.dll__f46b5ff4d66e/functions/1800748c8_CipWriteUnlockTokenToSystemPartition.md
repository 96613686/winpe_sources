# CipWriteUnlockTokenToSystemPartition

- ea: `0x1800748c8`
- end: `0x180074acc`
- name: `CipWriteUnlockTokenToSystemPartition`
- size: `516`
- prototype: `__int64 __fastcall(PVOID Buffer, ULONG Length)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800743dc`

## callees

- `0x1800748c8`
- `0x1800bc1b8`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x180074a95`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180074aa5`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180074a95`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180074aa5`
- `ntoskrnl!ZwClose` at `0x1800749ab`
- `ntoskrnl!ZwClose` at `0x180074a65`
- `ntoskrnl!ZwClose` at `0x180074a85`
- `ntoskrnl!ZwClose` at `0x1800749ab`
- `ntoskrnl!ZwClose` at `0x180074a65`
- `ntoskrnl!ZwClose` at `0x180074a85`
- `ntoskrnl!ZwCreateFile` at `0x180074997`
- `ntoskrnl!ZwCreateFile` at `0x180074a15`
- `ntoskrnl!ZwCreateFile` at `0x180074997`
- `ntoskrnl!ZwCreateFile` at `0x180074a15`
- `ntoskrnl!ZwWriteFile` at `0x180074a4f`
- `ntoskrnl!ZwWriteFile` at `0x180074a4f`

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
0x1800748c8  mov     [rsp-8+arg_0], rbx
0x1800748cd  mov     [rsp-8+arg_8], rsi
0x1800748d2  push    rbp
0x1800748d3  push    rdi
0x1800748d4  push    r14
0x1800748d6  lea     rbp, [rsp-47h]
0x1800748db  sub     rsp, 0F0h
0x1800748e2  xorps   xmm0, xmm0
0x1800748e5  lea     r8, [rbp+57h+UnicodeString]
0x1800748e9  mov     edi, edx
0x1800748eb  xor     r14d, r14d
0x1800748ee  xorps   xmm1, xmm1
0x1800748f1  mov     [rbp+57h+FileHandle], r14
0x1800748f5  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800748f9  xor     eax, eax
0x1800748fb  lea     rdx, [rbp+57h+var_80]
0x1800748ff  movups  xmmword ptr [rbp+57h+var_40.ObjectName], xmm0
0x180074903  mov     rsi, rcx
0x180074906  mov     [rbp+57h+Handle], r14
0x18007490a  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18007490e  movups  xmmword ptr [rbp+57h+var_40+1Ch], xmm0
0x180074912  movups  xmmword ptr [rbp+57h+UnicodeString.Length], xmm0
0x180074916  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18007491a  movups  xmmword ptr [rbp+57h+var_40.Length], xmm0
0x18007491e  movups  xmmword ptr [rbp+57h+var_80.Length], xmm0
0x180074922  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x180074926  call    CipGetSupplementalPolicyPath
0x18007492b  mov     ebx, eax
0x18007492d  test    eax, eax
0x18007492f  js      loc_180074A7C
0x180074935  mov     [rsp+100h+EaLength], r14d; EaLength
0x18007493a  lea     rax, [rbp+57h+UnicodeString]
0x18007493e  mov     [rsp+100h+EaBuffer], r14; EaBuffer
0x180074943  lea     ebx, [r14+30h]
0x180074947  mov     [rsp+100h+CreateOptions], 204021h; CreateOptions
0x18007494f  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180074953  mov     [rsp+100h+CreateDisposition], 2; CreateDisposition
0x18007495b  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18007495f  mov     [rsp+100h+ShareAccess], 3; ShareAccess
0x180074967  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18007496b  xorps   xmm0, xmm0
0x18007496e  mov     [rsp+100h+FileAttributes], 80h; FileAttributes
0x180074976  mov     edx, 100001h; DesiredAccess
0x18007497b  mov     [rsp+100h+AllocationSize], r14; AllocationSize
0x180074980  mov     [rbp+57h+ObjectAttributes.Length], ebx
0x180074983  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x180074987  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x18007498e  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180074992  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180074997  call    cs:__imp_ZwCreateFile
0x18007499e  nop     dword ptr [rax+rax+00h]
0x1800749a3  test    eax, eax
0x1800749a5  js      short loc_1800749B7
0x1800749a7  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800749ab  call    cs:__imp_ZwClose
0x1800749b2  nop     dword ptr [rax+rax+00h]
0x1800749b7  mov     [rsp+100h+EaLength], r14d; EaLength
0x1800749bc  lea     rax, [rbp+57h+var_80]
0x1800749c0  mov     [rsp+100h+EaBuffer], r14; EaBuffer
0x1800749c5  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800749c9  mov     [rsp+100h+CreateOptions], 60h ; '`'; CreateOptions
0x1800749d1  lea     r8, [rbp+57h+var_40]; ObjectAttributes
0x1800749d5  mov     [rsp+100h+CreateDisposition], 5; CreateDisposition
0x1800749dd  lea     rcx, [rbp+57h+Handle]; FileHandle
0x1800749e1  mov     [rsp+100h+ShareAccess], 1; ShareAccess
0x1800749e9  xorps   xmm0, xmm0
0x1800749ec  mov     [rsp+100h+FileAttributes], 80h; FileAttributes
0x1800749f4  mov     edx, 40010080h; DesiredAccess
0x1800749f9  mov     [rsp+100h+AllocationSize], r14; AllocationSize
0x1800749fe  mov     [rbp+57h+var_40.Length], ebx
0x180074a01  mov     [rbp+57h+var_40.RootDirectory], r14
0x180074a05  mov     [rbp+57h+var_40.Attributes], 240h
0x180074a0c  mov     [rbp+57h+var_40.ObjectName], rax
0x180074a10  movdqu  xmmword ptr [rbp+57h+var_40.SecurityDescriptor], xmm0
0x180074a15  call    cs:__imp_ZwCreateFile
0x180074a1c  nop     dword ptr [rax+rax+00h]
0x180074a21  mov     ebx, eax
0x180074a23  test    eax, eax
0x180074a25  js      short loc_180074A7C
0x180074a27  mov     rcx, [rbp+57h+Handle]; FileHandle
0x180074a2b  lea     rax, [rbp+57h+IoStatusBlock]
0x180074a2f  mov     qword ptr [rsp+100h+CreateOptions], r14; Key
0x180074a34  xor     r9d, r9d; ApcContext
0x180074a37  mov     qword ptr [rsp+100h+CreateDisposition], r14; ByteOffset
0x180074a3c  xor     r8d, r8d; ApcRoutine
0x180074a3f  mov     [rsp+100h+ShareAccess], edi; Length
0x180074a43  xor     edx, edx; Event
0x180074a45  mov     qword ptr [rsp+100h+FileAttributes], rsi; Buffer
0x180074a4a  mov     [rsp+100h+AllocationSize], rax; IoStatusBlock
0x180074a4f  call    cs:__imp_ZwWriteFile
0x180074a56  nop     dword ptr [rax+rax+00h]
0x180074a5b  mov     ebx, eax
0x180074a5d  test    eax, eax
0x180074a5f  js      short loc_180074A7C
0x180074a61  mov     rcx, [rbp+57h+Handle]; Handle
0x180074a65  call    cs:__imp_ZwClose
0x180074a6c  nop     dword ptr [rax+rax+00h]
0x180074a71  mov     rcx, r14
0x180074a74  mov     ebx, eax
0x180074a76  mov     [rbp+57h+Handle], rcx
0x180074a7a  jmp     short loc_180074A80
0x180074a7c  mov     rcx, [rbp+57h+Handle]; Handle
0x180074a80  test    rcx, rcx
0x180074a83  jz      short loc_180074A91
0x180074a85  call    cs:__imp_ZwClose
0x180074a8c  nop     dword ptr [rax+rax+00h]
0x180074a91  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x180074a95  call    cs:__imp_RtlFreeUnicodeString
0x180074a9c  nop     dword ptr [rax+rax+00h]
0x180074aa1  lea     rcx, [rbp+57h+var_80]; UnicodeString
0x180074aa5  call    cs:__imp_RtlFreeUnicodeString
0x180074aac  nop     dword ptr [rax+rax+00h]
0x180074ab1  lea     r11, [rsp+100h+var_10]
0x180074ab9  mov     eax, ebx
0x180074abb  mov     rbx, [r11+20h]
0x180074abf  mov     rsi, [r11+28h]
0x180074ac3  mov     rsp, r11
0x180074ac6  pop     r14
0x180074ac8  pop     rdi
0x180074ac9  pop     rbp
0x180074aca  retn
```
