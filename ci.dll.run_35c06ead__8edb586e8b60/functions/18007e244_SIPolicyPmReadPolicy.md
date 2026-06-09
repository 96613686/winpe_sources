# SIPolicyPmReadPolicy

- ea: `0x18007e244`
- end: `0x18007e3f0`
- name: `SIPolicyPmReadPolicy`
- size: `428`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180071f7c`
- `0x18007dcec`

## callees

- `0x18002c0d0`
- `0x18007e244`
- `0x180091e90`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18007e348`
- `ntoskrnl!ExAllocatePool2` at `0x18007e348`
- `ntoskrnl!ZwClose` at `0x18007e3be`
- `ntoskrnl!ZwClose` at `0x18007e3be`
- `ntoskrnl!ZwCreateFile` at `0x18007e2e6`
- `ntoskrnl!ZwCreateFile` at `0x18007e2e6`
- `ntoskrnl!ZwQueryInformationFile` at `0x18007e316`
- `ntoskrnl!ZwQueryInformationFile` at `0x18007e316`
- `ntoskrnl!ZwReadFile` at `0x18007e393`
- `ntoskrnl!ZwReadFile` at `0x18007e393`

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
0x18007e244  mov     [rsp-8+arg_0], rbx
0x18007e249  push    rbp
0x18007e24a  push    rsi
0x18007e24b  push    rdi
0x18007e24c  push    r14
0x18007e24e  push    r15
0x18007e250  lea     rbp, [rsp-37h]
0x18007e255  sub     rsp, 0D0h
0x18007e25c  mov     rax, cs:__security_cookie
0x18007e263  xor     rax, rsp
0x18007e266  mov     [rbp+57h+var_30], rax
0x18007e26a  xor     eax, eax
0x18007e26c  mov     [rbp+57h+ObjectAttributes.ObjectName], rdx
0x18007e270  mov     [rsp+0F0h+EaLength], eax; EaLength
0x18007e274  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18007e278  mov     [rsp+0F0h+EaBuffer], rax; EaBuffer
0x18007e27d  xorps   xmm0, xmm0
0x18007e280  mov     [rsp+0F0h+CreateOptions], 20h ; ' '; CreateOptions
0x18007e288  mov     r15, r9
0x18007e28b  mov     [rbp+57h+var_38], rax
0x18007e28f  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18007e293  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x18007e297  mov     r14, r8
0x18007e29a  mov     eax, 1
0x18007e29f  mov     [rbp+57h+FileHandle], 0
0x18007e2a7  mov     [rsp+0F0h+CreateDisposition], eax; CreateDisposition
0x18007e2ab  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18007e2af  mov     [rsp+0F0h+ShareAccess], eax; ShareAccess
0x18007e2b3  mov     edx, 120089h; DesiredAccess
0x18007e2b8  mov     [rsp+0F0h+FileAttributes], 80h; FileAttributes
0x18007e2c0  mov     [rsp+0F0h+AllocationSize], 0; AllocationSize
0x18007e2c9  movups  [rbp+57h+FileInformation], xmm0
0x18007e2cd  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18007e2d5  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18007e2d9  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x18007e2e1  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18007e2e6  call    cs:__imp_ZwCreateFile
0x18007e2ed  nop     dword ptr [rax+rax+00h]
0x18007e2f2  mov     ebx, eax
0x18007e2f4  test    eax, eax
0x18007e2f6  js      loc_18007E3B5
0x18007e2fc  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x18007e300  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x18007e304  mov     r9d, 18h; Length
0x18007e30a  mov     dword ptr [rsp+0F0h+AllocationSize], 5; FileInformationClass
0x18007e312  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18007e316  call    cs:__imp_ZwQueryInformationFile
0x18007e31d  nop     dword ptr [rax+rax+00h]
0x18007e322  mov     ebx, eax
0x18007e324  test    eax, eax
0x18007e326  js      loc_18007E3B5
0x18007e32c  mov     edi, dword ptr [rbp+57h+FileInformation+8]
0x18007e32f  test    edi, edi
0x18007e331  jnz     short loc_18007E33A
0x18007e333  mov     ebx, 0C0000225h
0x18007e338  jmp     short loc_18007E3B5
0x18007e33a  mov     rdx, rdi
0x18007e33d  mov     ecx, 100h
0x18007e342  mov     r8d, 69734943h
0x18007e348  call    cs:__imp_ExAllocatePool2
0x18007e34f  nop     dword ptr [rax+rax+00h]
0x18007e354  mov     rsi, rax
0x18007e357  test    rax, rax
0x18007e35a  jnz     short loc_18007E363
0x18007e35c  mov     ebx, 0C000009Ah
0x18007e361  jmp     short loc_18007E3B5
0x18007e363  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x18007e367  lea     rax, [rbp+57h+IoStatusBlock]
0x18007e36b  mov     qword ptr [rsp+0F0h+CreateOptions], 0; Key
0x18007e374  xor     r9d, r9d; ApcContext
0x18007e377  mov     qword ptr [rsp+0F0h+CreateDisposition], 0; ByteOffset
0x18007e380  xor     r8d, r8d; ApcRoutine
0x18007e383  mov     [rsp+0F0h+ShareAccess], edi; Length
0x18007e387  xor     edx, edx; Event
0x18007e389  mov     qword ptr [rsp+0F0h+FileAttributes], rsi; Buffer
0x18007e38e  mov     [rsp+0F0h+AllocationSize], rax; IoStatusBlock
0x18007e393  call    cs:__imp_ZwReadFile
0x18007e39a  nop     dword ptr [rax+rax+00h]
0x18007e39f  mov     ebx, eax
0x18007e3a1  test    eax, eax
0x18007e3a3  js      short loc_18007E3AD
0x18007e3a5  mov     [r15], edi
0x18007e3a8  mov     [r14], rsi
0x18007e3ab  jmp     short loc_18007E3B5
0x18007e3ad  mov     rcx, rsi
0x18007e3b0  call    SIPolicyFree
0x18007e3b5  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18007e3b9  test    rcx, rcx
0x18007e3bc  jz      short loc_18007E3CA
0x18007e3be  call    cs:__imp_ZwClose
0x18007e3c5  nop     dword ptr [rax+rax+00h]
0x18007e3ca  mov     eax, ebx
0x18007e3cc  mov     rcx, [rbp+57h+var_30]
0x18007e3d0  xor     rcx, rsp; StackCookie
0x18007e3d3  call    __security_check_cookie
0x18007e3d8  mov     rbx, [rsp+0F0h+arg_0]
0x18007e3e0  add     rsp, 0D0h
0x18007e3e7  pop     r15
0x18007e3e9  pop     r14
0x18007e3eb  pop     rdi
0x18007e3ec  pop     rsi
0x18007e3ed  pop     rbp
0x18007e3ee  retn
```
