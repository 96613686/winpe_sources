# LoadCodePageTable

- ea: `0x14002c4c4`
- end: `0x14002c75d`
- name: `LoadCodePageTable`
- size: `665`
- prototype: `__int64 __fastcall(__int64, ULONG, struct _CPTABLEINFO *, PVOID *)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400070a0`
- `0x140013830`
- `0x140014a90`
- `0x14002c854`

## callees

- `0x14002c2e0`
- `0x14002c4c4`
- `0x14003aba0`
- `0x14003b0c0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14002c555`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002c555`
- `ntoskrnl!RtlInitCodePageTable` at `0x14002c6ea`
- `ntoskrnl!RtlInitCodePageTable` at `0x14002c6ea`
- `ntoskrnl!KeReleaseMutex` at `0x14002c72d`
- `ntoskrnl!KeReleaseMutex` at `0x14002c72d`
- `ntoskrnl!ZwQueryInformationFile` at `0x14002c632`
- `ntoskrnl!ZwQueryInformationFile` at `0x14002c632`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002c6b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002c6b9`
- `ntoskrnl!ZwClose` at `0x14002c6d4`
- `ntoskrnl!ZwClose` at `0x14002c6fd`
- `ntoskrnl!ZwClose` at `0x14002c6d4`
- `ntoskrnl!ZwClose` at `0x14002c6fd`
- `ntoskrnl!ZwCreateFile` at `0x14002c5f5`
- `ntoskrnl!ZwCreateFile` at `0x14002c5f5`
- `ntoskrnl!ZwReadFile` at `0x14002c6a2`
- `ntoskrnl!ZwReadFile` at `0x14002c6a2`
- `ntoskrnl!ExAllocatePool2` at `0x14002c663`
- `ntoskrnl!ExAllocatePool2` at `0x14002c663`

## pseudocode

```c
__int64 __fastcall LoadCodePageTable(__int64 a1, ULONG a2, struct _CPTABLEINFO *a3, PVOID *a4)
{
  NTSTATUS v8; // ebx
  ULONG v9; // r14d
  void *Pool2; // rax
  void *FileHandle; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-98h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-88h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-78h] BYREF
  __int128 FileInformation; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v17; // [rsp+C8h] [rbp-38h]
  _WORD v18[264]; // [rsp+D0h] [rbp-30h] BYREF

  memset(v18, 0, 520);
  *(_QWORD *)&DestinationString.Length = 34078720;
  FileHandle = 0;
  DestinationString.Buffer = v18;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  KeWaitForSingleObject((PVOID)(a1 + 2208), Executive, 0, 0, 0);
  if ( !a3 || !a4 )
  {
    v8 = -1073741811;
    goto LABEL_19;
  }
  if ( !a3->CodePage )
  {
    if ( !(unsigned int)GetNlsTablePath(a2, &DestinationString) )
    {
      v8 = -1073741762;
      goto LABEL_20;
    }
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v8 = ZwCreateFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 0, 0, 1u, 1u, 0x20u, 0, 0);
    if ( v8 < 0 )
    {
LABEL_20:
      a3->CodePage = 0;
      goto LABEL_21;
    }
    v17 = 0;
    FileInformation = 0;
    v8 = ZwQueryInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 0x18u, FileStandardInformation);
    if ( v8 >= 0 )
    {
      v9 = DWORD2(FileInformation);
      if ( DWORD2(FileInformation) )
      {
        Pool2 = (void *)ExAllocatePool2(258, DWORD2(FileInformation), 827483726);
        *a4 = Pool2;
        if ( Pool2 )
        {
          v8 = ZwReadFile(FileHandle, 0, 0, 0, &IoStatusBlock, Pool2, v9, 0, 0);
          if ( v8 < 0 )
          {
            ExFreePoolWithTag(*a4, 0);
            *a4 = 0;
          }
        }
        else
        {
          v8 = -1073741670;
        }
        ZwClose(FileHandle);
        if ( v8 >= 0 )
        {
          RtlInitCodePageTable((PUSHORT)*a4, a3);
          goto LABEL_21;
        }
        goto LABEL_20;
      }
    }
    ZwClose(FileHandle);
    if ( v8 >= 0 )
      goto LABEL_21;
LABEL_19:
    if ( !a3 )
      goto LABEL_21;
    goto LABEL_20;
  }
  v8 = 0;
LABEL_21:
  KeReleaseMutex((PRKMUTEX)(a1 + 2208), 0);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14002c4c4  push    rbp
0x14002c4c6  push    rbx
0x14002c4c7  push    rsi
0x14002c4c8  push    rdi
0x14002c4c9  push    r12
0x14002c4cb  push    r14
0x14002c4cd  push    r15
0x14002c4cf  lea     rbp, [rsp-1F0h]
0x14002c4d7  sub     rsp, 2F0h
0x14002c4de  mov     rax, cs:__security_cookie
0x14002c4e5  xor     rax, rsp
0x14002c4e8  mov     [rbp+220h+var_40], rax
0x14002c4ef  mov     rsi, r8
0x14002c4f2  mov     r14d, edx
0x14002c4f5  mov     r15, rcx
0x14002c4f8  xor     r12d, r12d
0x14002c4fb  xor     edx, edx; Val
0x14002c4fd  mov     [rbp+220h+var_250], r12w
0x14002c502  mov     r8d, 206h; Size
0x14002c508  lea     rcx, [rbp+220h+var_24E]; void *
0x14002c50c  mov     rdi, r9
0x14002c50f  call    memset
0x14002c514  xorps   xmm0, xmm0
0x14002c517  mov     qword ptr [rsp+320h+DestinationString.Length], 2080000h
0x14002c520  xor     eax, eax
0x14002c522  mov     [rsp+320h+FileHandle], r12
0x14002c527  lea     rax, [rbp+220h+var_250]
0x14002c52b  mov     [rsp+320h+Timeout], r12; Timeout
0x14002c530  movups  xmmword ptr [rbp+220h+ObjectAttributes.ObjectName], xmm0
0x14002c534  xor     r9d, r9d; Alertable
0x14002c537  mov     [rsp+320h+DestinationString.Buffer], rax
0x14002c53c  xor     r8d, r8d; WaitMode
0x14002c53f  lea     rcx, [r15+8A0h]; Object
0x14002c546  xor     edx, edx; WaitReason
0x14002c548  movups  xmmword ptr [rbp+220h+ObjectAttributes.Length], xmm0
0x14002c54c  movups  xmmword ptr [rbp+220h+ObjectAttributes+1Ch], xmm0
0x14002c550  movups  xmmword ptr [rsp+320h+IoStatusBlock], xmm0
0x14002c555  call    cs:__imp_KeWaitForSingleObject
0x14002c55c  nop     dword ptr [rax+rax+00h]
0x14002c561  test    rsi, rsi
0x14002c564  jz      loc_14002C716
0x14002c56a  test    rdi, rdi
0x14002c56d  jz      loc_14002C716
0x14002c573  cmp     [rsi], r12w
0x14002c577  jz      short loc_14002C581
0x14002c579  mov     ebx, r12d
0x14002c57c  jmp     loc_14002C724
0x14002c581  lea     rdx, [rsp+320h+DestinationString]; DestinationString
0x14002c586  mov     ecx, r14d; Value
0x14002c589  call    GetNlsTablePath
0x14002c58e  test    eax, eax
0x14002c590  jz      loc_14002C70F
0x14002c596  mov     [rsp+320h+EaLength], r12d; EaLength
0x14002c59b  lea     rax, [rsp+320h+DestinationString]
0x14002c5a0  mov     [rsp+320h+EaBuffer], r12; EaBuffer
0x14002c5a5  lea     r9, [rsp+320h+IoStatusBlock]; IoStatusBlock
0x14002c5aa  mov     [rsp+320h+CreateOptions], 20h ; ' '; CreateOptions
0x14002c5b2  lea     r8, [rbp+220h+ObjectAttributes]; ObjectAttributes
0x14002c5b6  mov     [rbp+220h+ObjectAttributes.ObjectName], rax
0x14002c5ba  lea     rcx, [rsp+320h+FileHandle]; FileHandle
0x14002c5bf  mov     eax, 1
0x14002c5c4  mov     [rbp+220h+ObjectAttributes.Length], 30h ; '0'
0x14002c5cb  mov     [rsp+320h+CreateDisposition], eax; CreateDisposition
0x14002c5cf  xorps   xmm0, xmm0
0x14002c5d2  mov     [rsp+320h+ShareAccess], eax; ShareAccess
0x14002c5d6  mov     edx, 100001h; DesiredAccess
0x14002c5db  mov     [rsp+320h+FileAttributes], r12d; FileAttributes
0x14002c5e0  mov     [rsp+320h+Timeout], r12; AllocationSize
0x14002c5e5  mov     [rbp+220h+ObjectAttributes.RootDirectory], r12
0x14002c5e9  mov     [rbp+220h+ObjectAttributes.Attributes], 240h
0x14002c5f0  movdqu  xmmword ptr [rbp+220h+ObjectAttributes.SecurityDescriptor], xmm0
0x14002c5f5  call    cs:__imp_ZwCreateFile
0x14002c5fc  nop     dword ptr [rax+rax+00h]
0x14002c601  mov     ebx, eax
0x14002c603  test    eax, eax
0x14002c605  js      loc_14002C720
0x14002c60b  mov     rcx, [rsp+320h+FileHandle]; FileHandle
0x14002c610  lea     r8, [rbp+220h+FileInformation]; FileInformation
0x14002c614  xor     eax, eax
0x14002c616  mov     dword ptr [rsp+320h+Timeout], 5; FileInformationClass
0x14002c61e  xorps   xmm0, xmm0
0x14002c621  mov     [rbp+220h+var_258], rax
0x14002c625  lea     rdx, [rsp+320h+IoStatusBlock]; IoStatusBlock
0x14002c62a  movups  [rbp+220h+FileInformation], xmm0
0x14002c62e  lea     r9d, [rax+18h]; Length
0x14002c632  call    cs:__imp_ZwQueryInformationFile
0x14002c639  nop     dword ptr [rax+rax+00h]
0x14002c63e  mov     ebx, eax
0x14002c640  test    eax, eax
0x14002c642  js      loc_14002C6F8
0x14002c648  mov     r14d, dword ptr [rbp+220h+FileInformation+8]
0x14002c64c  test    r14d, r14d
0x14002c64f  jz      loc_14002C6F8
0x14002c655  mov     edx, r14d
0x14002c658  mov     ecx, 102h
0x14002c65d  mov     r8d, 3152664Eh
0x14002c663  call    cs:__imp_ExAllocatePool2
0x14002c66a  nop     dword ptr [rax+rax+00h]
0x14002c66f  mov     [rdi], rax
0x14002c672  test    rax, rax
0x14002c675  jz      short loc_14002C6CA
0x14002c677  mov     rcx, [rsp+320h+FileHandle]; FileHandle
0x14002c67c  xor     r9d, r9d; ApcContext
0x14002c67f  mov     qword ptr [rsp+320h+CreateOptions], r12; Key
0x14002c684  xor     r8d, r8d; ApcRoutine
0x14002c687  mov     qword ptr [rsp+320h+CreateDisposition], r12; ByteOffset
0x14002c68c  xor     edx, edx; Event
0x14002c68e  mov     [rsp+320h+ShareAccess], r14d; Length
0x14002c693  mov     qword ptr [rsp+320h+FileAttributes], rax; Buffer
0x14002c698  lea     rax, [rsp+320h+IoStatusBlock]
0x14002c69d  mov     [rsp+320h+Timeout], rax; IoStatusBlock
0x14002c6a2  call    cs:__imp_ZwReadFile
0x14002c6a9  nop     dword ptr [rax+rax+00h]
0x14002c6ae  mov     ebx, eax
0x14002c6b0  test    eax, eax
0x14002c6b2  jns     short loc_14002C6CF
0x14002c6b4  mov     rcx, [rdi]; P
0x14002c6b7  xor     edx, edx; Tag
0x14002c6b9  call    cs:__imp_ExFreePoolWithTag
0x14002c6c0  nop     dword ptr [rax+rax+00h]
0x14002c6c5  mov     [rdi], r12
0x14002c6c8  jmp     short loc_14002C6CF
0x14002c6ca  mov     ebx, 0C000009Ah
0x14002c6cf  mov     rcx, [rsp+320h+FileHandle]; Handle
0x14002c6d4  call    cs:__imp_ZwClose
0x14002c6db  nop     dword ptr [rax+rax+00h]
0x14002c6e0  test    ebx, ebx
0x14002c6e2  js      short loc_14002C720
0x14002c6e4  mov     rcx, [rdi]; TableBase
0x14002c6e7  mov     rdx, rsi; CodePageTable
0x14002c6ea  call    cs:__imp_RtlInitCodePageTable
0x14002c6f1  nop     dword ptr [rax+rax+00h]
0x14002c6f6  jmp     short loc_14002C724
0x14002c6f8  mov     rcx, [rsp+320h+FileHandle]; Handle
0x14002c6fd  call    cs:__imp_ZwClose
0x14002c704  nop     dword ptr [rax+rax+00h]
0x14002c709  test    ebx, ebx
0x14002c70b  jns     short loc_14002C724
0x14002c70d  jmp     short loc_14002C71B
0x14002c70f  mov     ebx, 0C000003Eh
0x14002c714  jmp     short loc_14002C720
0x14002c716  mov     ebx, 0C000000Dh
0x14002c71b  test    rsi, rsi
0x14002c71e  jz      short loc_14002C724
0x14002c720  mov     [rsi], r12w
0x14002c724  xor     edx, edx; Wait
0x14002c726  lea     rcx, [r15+8A0h]; Mutex
0x14002c72d  call    cs:__imp_KeReleaseMutex
0x14002c734  nop     dword ptr [rax+rax+00h]
0x14002c739  mov     eax, ebx
0x14002c73b  mov     rcx, [rbp+220h+var_40]
0x14002c742  xor     rcx, rsp; StackCookie
0x14002c745  call    __security_check_cookie
0x14002c74a  add     rsp, 2F0h
0x14002c751  pop     r15
0x14002c753  pop     r14
0x14002c755  pop     r12
0x14002c757  pop     rdi
0x14002c758  pop     rsi
0x14002c759  pop     rbx
0x14002c75a  pop     rbp
0x14002c75b  retn
```
