# SIPolicyPmReadPolicy

- ea: `0x18007d830`
- end: `0x18007d9dc`
- name: `SIPolicyPmReadPolicy`
- size: `428`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180071c9c`
- `0x18007d2d8`

## callees

- `0x18002bf20`
- `0x18007d830`
- `0x1800a16f0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18007d934`
- `ntoskrnl!ExAllocatePool2` at `0x18007d934`
- `ntoskrnl!ZwClose` at `0x18007d9aa`
- `ntoskrnl!ZwClose` at `0x18007d9aa`
- `ntoskrnl!ZwCreateFile` at `0x18007d8d2`
- `ntoskrnl!ZwCreateFile` at `0x18007d8d2`
- `ntoskrnl!ZwQueryInformationFile` at `0x18007d902`
- `ntoskrnl!ZwQueryInformationFile` at `0x18007d902`
- `ntoskrnl!ZwReadFile` at `0x18007d97f`
- `ntoskrnl!ZwReadFile` at `0x18007d97f`

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
0x18007d830  mov     [rsp-8+arg_0], rbx
0x18007d835  push    rbp
0x18007d836  push    rsi
0x18007d837  push    rdi
0x18007d838  push    r14
0x18007d83a  push    r15
0x18007d83c  lea     rbp, [rsp-37h]
0x18007d841  sub     rsp, 0D0h
0x18007d848  mov     rax, cs:__security_cookie
0x18007d84f  xor     rax, rsp
0x18007d852  mov     [rbp+57h+var_30], rax
0x18007d856  xor     eax, eax
0x18007d858  mov     [rbp+57h+ObjectAttributes.ObjectName], rdx
0x18007d85c  mov     [rsp+0F0h+EaLength], eax; EaLength
0x18007d860  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18007d864  mov     [rsp+0F0h+EaBuffer], rax; EaBuffer
0x18007d869  xorps   xmm0, xmm0
0x18007d86c  mov     [rsp+0F0h+CreateOptions], 20h ; ' '; CreateOptions
0x18007d874  mov     r15, r9
0x18007d877  mov     [rbp+57h+var_38], rax
0x18007d87b  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18007d87f  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x18007d883  mov     r14, r8
0x18007d886  mov     eax, 1
0x18007d88b  mov     [rbp+57h+FileHandle], 0
0x18007d893  mov     [rsp+0F0h+CreateDisposition], eax; CreateDisposition
0x18007d897  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18007d89b  mov     [rsp+0F0h+ShareAccess], eax; ShareAccess
0x18007d89f  mov     edx, 120089h; DesiredAccess
0x18007d8a4  mov     [rsp+0F0h+FileAttributes], 80h; FileAttributes
0x18007d8ac  mov     [rsp+0F0h+AllocationSize], 0; AllocationSize
0x18007d8b5  movups  [rbp+57h+FileInformation], xmm0
0x18007d8b9  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18007d8c1  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18007d8c5  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x18007d8cd  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18007d8d2  call    cs:__imp_ZwCreateFile
0x18007d8d9  nop     dword ptr [rax+rax+00h]
0x18007d8de  mov     ebx, eax
0x18007d8e0  test    eax, eax
0x18007d8e2  js      loc_18007D9A1
0x18007d8e8  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x18007d8ec  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x18007d8f0  mov     r9d, 18h; Length
0x18007d8f6  mov     dword ptr [rsp+0F0h+AllocationSize], 5; FileInformationClass
0x18007d8fe  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18007d902  call    cs:__imp_ZwQueryInformationFile
0x18007d909  nop     dword ptr [rax+rax+00h]
0x18007d90e  mov     ebx, eax
0x18007d910  test    eax, eax
0x18007d912  js      loc_18007D9A1
0x18007d918  mov     edi, dword ptr [rbp+57h+FileInformation+8]
0x18007d91b  test    edi, edi
0x18007d91d  jnz     short loc_18007D926
0x18007d91f  mov     ebx, 0C0000225h
0x18007d924  jmp     short loc_18007D9A1
0x18007d926  mov     rdx, rdi
0x18007d929  mov     ecx, 100h
0x18007d92e  mov     r8d, 69734943h
0x18007d934  call    cs:__imp_ExAllocatePool2
0x18007d93b  nop     dword ptr [rax+rax+00h]
0x18007d940  mov     rsi, rax
0x18007d943  test    rax, rax
0x18007d946  jnz     short loc_18007D94F
0x18007d948  mov     ebx, 0C000009Ah
0x18007d94d  jmp     short loc_18007D9A1
0x18007d94f  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x18007d953  lea     rax, [rbp+57h+IoStatusBlock]
0x18007d957  mov     qword ptr [rsp+0F0h+CreateOptions], 0; Key
0x18007d960  xor     r9d, r9d; ApcContext
0x18007d963  mov     qword ptr [rsp+0F0h+CreateDisposition], 0; ByteOffset
0x18007d96c  xor     r8d, r8d; ApcRoutine
0x18007d96f  mov     [rsp+0F0h+ShareAccess], edi; Length
0x18007d973  xor     edx, edx; Event
0x18007d975  mov     qword ptr [rsp+0F0h+FileAttributes], rsi; Buffer
0x18007d97a  mov     [rsp+0F0h+AllocationSize], rax; IoStatusBlock
0x18007d97f  call    cs:__imp_ZwReadFile
0x18007d986  nop     dword ptr [rax+rax+00h]
0x18007d98b  mov     ebx, eax
0x18007d98d  test    eax, eax
0x18007d98f  js      short loc_18007D999
0x18007d991  mov     [r15], edi
0x18007d994  mov     [r14], rsi
0x18007d997  jmp     short loc_18007D9A1
0x18007d999  mov     rcx, rsi
0x18007d99c  call    SIPolicyFree
0x18007d9a1  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18007d9a5  test    rcx, rcx
0x18007d9a8  jz      short loc_18007D9B6
0x18007d9aa  call    cs:__imp_ZwClose
0x18007d9b1  nop     dword ptr [rax+rax+00h]
0x18007d9b6  mov     eax, ebx
0x18007d9b8  mov     rcx, [rbp+57h+var_30]
0x18007d9bc  xor     rcx, rsp; StackCookie
0x18007d9bf  call    __security_check_cookie
0x18007d9c4  mov     rbx, [rsp+0F0h+arg_0]
0x18007d9cc  add     rsp, 0D0h
0x18007d9d3  pop     r15
0x18007d9d5  pop     r14
0x18007d9d7  pop     rdi
0x18007d9d8  pop     rsi
0x18007d9d9  pop     rbp
0x18007d9da  retn
```
