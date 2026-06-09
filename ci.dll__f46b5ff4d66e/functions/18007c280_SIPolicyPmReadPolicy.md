# SIPolicyPmReadPolicy

- ea: `0x18007c280`
- end: `0x18007c42c`
- name: `SIPolicyPmReadPolicy`
- size: `428`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800709ec`
- `0x18007bd28`

## callees

- `0x18002bef0`
- `0x18007c280`
- `0x1800a00c0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18007c384`
- `ntoskrnl!ExAllocatePool2` at `0x18007c384`
- `ntoskrnl!ZwClose` at `0x18007c3fa`
- `ntoskrnl!ZwClose` at `0x18007c3fa`
- `ntoskrnl!ZwCreateFile` at `0x18007c322`
- `ntoskrnl!ZwCreateFile` at `0x18007c322`
- `ntoskrnl!ZwQueryInformationFile` at `0x18007c352`
- `ntoskrnl!ZwQueryInformationFile` at `0x18007c352`
- `ntoskrnl!ZwReadFile` at `0x18007c3cf`
- `ntoskrnl!ZwReadFile` at `0x18007c3cf`

## pseudocode

```c
__int64 __fastcall SIPolicyPmReadPolicy(__int64 a1, struct _UNICODE_STRING *a2, _QWORD *a3, ULONG *a4)
{
  NTSTATUS v6; // ebx
  ULONG v7; // edi
  void *Pool2; // rsi
  void *FileHandle; // [rsp+60h] [rbp-39h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+68h] [rbp-31h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-21h] BYREF
  __int128 FileInformation; // [rsp+A8h] [rbp+Fh] BYREF
  __int64 v14; // [rsp+B8h] [rbp+1Fh]

  ObjectAttributes.ObjectName = a2;
  v14 = 0;
  ObjectAttributes.RootDirectory = 0;
  FileHandle = 0;
  FileInformation = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  IoStatusBlock = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v6 = ZwCreateFile(&FileHandle, 0x120089u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 1u, 1u, 0x20u, 0, 0);
  if ( v6 >= 0 )
  {
    v6 = ZwQueryInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 0x18u, FileStandardInformation);
    if ( v6 >= 0 )
    {
      v7 = DWORD2(FileInformation);
      if ( DWORD2(FileInformation) )
      {
        Pool2 = (void *)ExAllocatePool2(256, DWORD2(FileInformation), 1769163075);
        if ( Pool2 )
        {
          v6 = ZwReadFile(FileHandle, 0, 0, 0, &IoStatusBlock, Pool2, v7, 0, 0);
          if ( v6 < 0 )
          {
            SIPolicyFree(Pool2);
          }
          else
          {
            *a4 = v7;
            *a3 = Pool2;
          }
        }
        else
        {
          v6 = -1073741670;
        }
      }
      else
      {
        v6 = -1073741275;
      }
    }
  }
  if ( FileHandle )
    ZwClose(FileHandle);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18007c280  mov     [rsp-8+arg_0], rbx
0x18007c285  push    rbp
0x18007c286  push    rsi
0x18007c287  push    rdi
0x18007c288  push    r14
0x18007c28a  push    r15
0x18007c28c  lea     rbp, [rsp-37h]
0x18007c291  sub     rsp, 0D0h
0x18007c298  mov     rax, cs:__security_cookie
0x18007c29f  xor     rax, rsp
0x18007c2a2  mov     [rbp+57h+var_30], rax
0x18007c2a6  xor     eax, eax
0x18007c2a8  mov     [rbp+57h+ObjectAttributes.ObjectName], rdx
0x18007c2ac  mov     [rsp+0F0h+EaLength], eax; EaLength
0x18007c2b0  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18007c2b4  mov     [rsp+0F0h+EaBuffer], rax; EaBuffer
0x18007c2b9  xorps   xmm0, xmm0
0x18007c2bc  mov     [rsp+0F0h+CreateOptions], 20h ; ' '; CreateOptions
0x18007c2c4  mov     r15, r9
0x18007c2c7  mov     [rbp+57h+var_38], rax
0x18007c2cb  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18007c2cf  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x18007c2d3  mov     r14, r8
0x18007c2d6  mov     eax, 1
0x18007c2db  mov     [rbp+57h+FileHandle], 0
0x18007c2e3  mov     [rsp+0F0h+CreateDisposition], eax; CreateDisposition
0x18007c2e7  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18007c2eb  mov     [rsp+0F0h+ShareAccess], eax; ShareAccess
0x18007c2ef  mov     edx, 120089h; DesiredAccess
0x18007c2f4  mov     [rsp+0F0h+FileAttributes], 80h; FileAttributes
0x18007c2fc  mov     [rsp+0F0h+AllocationSize], 0; AllocationSize
0x18007c305  movups  [rbp+57h+FileInformation], xmm0
0x18007c309  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18007c311  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18007c315  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x18007c31d  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18007c322  call    cs:__imp_ZwCreateFile
0x18007c329  nop     dword ptr [rax+rax+00h]
0x18007c32e  mov     ebx, eax
0x18007c330  test    eax, eax
0x18007c332  js      loc_18007C3F1
0x18007c338  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x18007c33c  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x18007c340  mov     r9d, 18h; Length
0x18007c346  mov     dword ptr [rsp+0F0h+AllocationSize], 5; FileInformationClass
0x18007c34e  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18007c352  call    cs:__imp_ZwQueryInformationFile
0x18007c359  nop     dword ptr [rax+rax+00h]
0x18007c35e  mov     ebx, eax
0x18007c360  test    eax, eax
0x18007c362  js      loc_18007C3F1
0x18007c368  mov     edi, dword ptr [rbp+57h+FileInformation+8]
0x18007c36b  test    edi, edi
0x18007c36d  jnz     short loc_18007C376
0x18007c36f  mov     ebx, 0C0000225h
0x18007c374  jmp     short loc_18007C3F1
0x18007c376  mov     rdx, rdi
0x18007c379  mov     ecx, 100h
0x18007c37e  mov     r8d, 69734943h
0x18007c384  call    cs:__imp_ExAllocatePool2
0x18007c38b  nop     dword ptr [rax+rax+00h]
0x18007c390  mov     rsi, rax
0x18007c393  test    rax, rax
0x18007c396  jnz     short loc_18007C39F
0x18007c398  mov     ebx, 0C000009Ah
0x18007c39d  jmp     short loc_18007C3F1
0x18007c39f  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x18007c3a3  lea     rax, [rbp+57h+IoStatusBlock]
0x18007c3a7  mov     qword ptr [rsp+0F0h+CreateOptions], 0; Key
0x18007c3b0  xor     r9d, r9d; ApcContext
0x18007c3b3  mov     qword ptr [rsp+0F0h+CreateDisposition], 0; ByteOffset
0x18007c3bc  xor     r8d, r8d; ApcRoutine
0x18007c3bf  mov     [rsp+0F0h+ShareAccess], edi; Length
0x18007c3c3  xor     edx, edx; Event
0x18007c3c5  mov     qword ptr [rsp+0F0h+FileAttributes], rsi; Buffer
0x18007c3ca  mov     [rsp+0F0h+AllocationSize], rax; IoStatusBlock
0x18007c3cf  call    cs:__imp_ZwReadFile
0x18007c3d6  nop     dword ptr [rax+rax+00h]
0x18007c3db  mov     ebx, eax
0x18007c3dd  test    eax, eax
0x18007c3df  js      short loc_18007C3E9
0x18007c3e1  mov     [r15], edi
0x18007c3e4  mov     [r14], rsi
0x18007c3e7  jmp     short loc_18007C3F1
0x18007c3e9  mov     rcx, rsi
0x18007c3ec  call    SIPolicyFree
0x18007c3f1  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18007c3f5  test    rcx, rcx
0x18007c3f8  jz      short loc_18007C406
0x18007c3fa  call    cs:__imp_ZwClose
0x18007c401  nop     dword ptr [rax+rax+00h]
0x18007c406  mov     eax, ebx
0x18007c408  mov     rcx, [rbp+57h+var_30]
0x18007c40c  xor     rcx, rsp; StackCookie
0x18007c40f  call    __security_check_cookie
0x18007c414  mov     rbx, [rsp+0F0h+arg_0]
0x18007c41c  add     rsp, 0D0h
0x18007c423  pop     r15
0x18007c425  pop     r14
0x18007c427  pop     rdi
0x18007c428  pop     rsi
0x18007c429  pop     rbp
0x18007c42a  retn
```
