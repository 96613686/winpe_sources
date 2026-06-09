# InternalDeleteFileW

- ea: `0x1800d3ee8`
- end: `0x1800d41d8`
- name: `InternalDeleteFileW`
- size: `752`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800d3eb0`
- `0x1800d4240`
- `0x18018cc80`
- `0x18018ccd0`

## callees

- `0x18004b9d0`
- `0x1800d3ee8`
- `0x18018d67c`

## import_xrefs

- `ntdll!RtlReleaseRelativeName` at `0x1800d405a`
- `ntdll!RtlReleaseRelativeName` at `0x1801a0b3c`
- `ntdll!RtlReleaseRelativeName` at `0x1801a0b6c`
- `ntdll!RtlReleaseRelativeName` at `0x1800d405a`
- `ntdll!RtlReleaseRelativeName` at `0x1801a0b3c`
- `ntdll!RtlReleaseRelativeName` at `0x1801a0b6c`
- `ntdll!NtQueryInformationFile` at `0x1800d402a`
- `ntdll!NtQueryInformationFile` at `0x1800d402a`
- `ntdll!NtOpenFile` at `0x1800d3ff6`
- `ntdll!NtOpenFile` at `0x1801a0b22`
- `ntdll!NtOpenFile` at `0x1801a0be6`
- `ntdll!NtOpenFile` at `0x1800d3ff6`
- `ntdll!NtOpenFile` at `0x1801a0b22`
- `ntdll!NtOpenFile` at `0x1801a0be6`
- `ntdll!NtSetInformationFile` at `0x1800d40af`
- `ntdll!NtSetInformationFile` at `0x1800d410e`
- `ntdll!NtSetInformationFile` at `0x1800d40af`
- `ntdll!NtSetInformationFile` at `0x1800d410e`
- `ntdll!RtlSetLastWin32Error` at `0x1800d412e`
- `ntdll!RtlSetLastWin32Error` at `0x1800d412e`
- `ntdll!NtClose` at `0x1800d40cd`
- `ntdll!NtClose` at `0x1801a0b9a`
- `ntdll!NtClose` at `0x1801a0bbe`
- `ntdll!NtClose` at `0x1800d40cd`
- `ntdll!NtClose` at `0x1801a0b9a`
- `ntdll!NtClose` at `0x1801a0bbe`
- `ntdll!RtlFreeHeap` at `0x1800d4078`
- `ntdll!RtlFreeHeap` at `0x1801a0b5a`
- `ntdll!RtlFreeHeap` at `0x1801a0b8a`
- `ntdll!RtlFreeHeap` at `0x1800d4078`
- `ntdll!RtlFreeHeap` at `0x1801a0b5a`
- `ntdll!RtlFreeHeap` at `0x1801a0b8a`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x1800d3f58`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x1800d3f58`

## pseudocode

```c
__int64 __fastcall InternalDeleteFileW(__int64 a1, int a2)
{
  ULARGE_INTEGER AppCompatFlags; // r14
  int v4; // eax
  __int64 v5; // rcx
  PVOID v7; // rbx
  HANDLE ContainingDirectory; // rax
  NTSTATUS FileRedirectionStatus; // edi
  NTSTATUS v10; // ebx
  NTSTATUS v11; // eax
  int v12; // ecx
  NTSTATUS v13; // eax
  __int64 FileInformation; // [rsp+30h] [rbp-59h] BYREF
  PVOID P[2]; // [rsp+38h] [rbp-51h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+48h] [rbp-41h] BYREF
  struct _RTL_RELATIVE_NAME_U RelativeName; // [rsp+58h] [rbp-31h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-11h] BYREF
  char v19; // [rsp+F8h] [rbp+6Fh] BYREF
  int v20; // [rsp+100h] [rbp+77h] BYREF
  HANDLE FileHandle; // [rsp+108h] [rbp+7Fh] BYREF

  FileHandle = 0;
  v19 = 0;
  memset(&ObjectAttributes, 0, 44);
  v20 = 0;
  *(_OWORD *)P = 0;
  IoStatusBlock = 0;
  AppCompatFlags = NtCurrentPeb()->AppCompatFlags;
  FileInformation = 0;
  memset(&RelativeName, 0, sizeof(RelativeName));
  v4 = RtlDosPathNameToRelativeNtPathName_U_WithStatus(a1, P, 0, &RelativeName);
  if ( v4 < 0 )
  {
    if ( v4 != -1073741801 && v4 != -1073741670 )
    {
      RtlSetLastWin32Error(3u);
      return 0;
    }
    v5 = (unsigned int)v4;
LABEL_4:
    BaseSetLastNTError(v5);
    return 0;
  }
  v7 = P[1];
  if ( RelativeName.RelativeName.Length )
  {
    LOWORD(P[0]) = RelativeName.RelativeName.Length;
    *(_DWORD *)((char *)P + 2) = *(_DWORD *)&RelativeName.RelativeName.MaximumLength;
    HIWORD(P[0]) = *(&RelativeName.RelativeName.MaximumLength + 2);
    P[1] = RelativeName.RelativeName.Buffer;
    ContainingDirectory = RelativeName.ContainingDirectory;
  }
  else
  {
    ContainingDirectory = 0;
    RelativeName.ContainingDirectory = 0;
  }
  ObjectAttributes.RootDirectory = ContainingDirectory;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)P;
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  FileRedirectionStatus = NtOpenFile(&FileHandle, 0x10080u, &ObjectAttributes, &IoStatusBlock, 7u, 0x204040u);
  if ( FileRedirectionStatus < 0 )
  {
    if ( FileRedirectionStatus == -1073741811 )
    {
      v11 = NtOpenFile(&FileHandle, 0x10000u, &ObjectAttributes, &IoStatusBlock, 7u, 0x4040u);
      goto LABEL_33;
    }
    if ( FileRedirectionStatus != -1073741790 )
      goto LABEL_34;
LABEL_32:
    v11 = NtOpenFile(&FileHandle, 0x10000u, &ObjectAttributes, &IoStatusBlock, 7u, 0x204040u);
LABEL_33:
    FileRedirectionStatus = v11;
    if ( v11 < 0 )
    {
LABEL_34:
      RtlReleaseRelativeName(&RelativeName);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
LABEL_36:
      v5 = (unsigned int)FileRedirectionStatus;
      goto LABEL_4;
    }
    goto LABEL_11;
  }
  FileRedirectionStatus = NtQueryInformationFile(
                            FileHandle,
                            &IoStatusBlock,
                            &FileInformation,
                            8u,
                            FileAttributeTagInformation);
  if ( FileRedirectionStatus >= 0 )
  {
    if ( (FileInformation & 0x400) == 0 )
      goto LABEL_11;
    if ( (unsigned int)(HIDWORD(FileInformation) + 1610612733) <= 0x16 )
    {
      v12 = 4194817;
      if ( _bittest(&v12, HIDWORD(FileInformation) + 1610612733) )
        goto LABEL_11;
    }
    NtClose(FileHandle);
    v13 = NtOpenFile(&FileHandle, 0x10000u, &ObjectAttributes, &IoStatusBlock, 7u, 0x4040u);
    FileRedirectionStatus = v13;
    if ( v13 >= 0 )
      goto LABEL_11;
    if ( ((v13 + 1073741194) & 0xFFFFFFFC) != 0 || v13 == -1073741193 )
      goto LABEL_34;
    goto LABEL_32;
  }
  if ( FileRedirectionStatus != -1073741822 && FileRedirectionStatus != -1073741811 )
    goto LABEL_35;
LABEL_11:
  if ( (a2 & 0x10000) != 0 )
  {
    FileRedirectionStatus = BasepGetFileRedirectionStatus(P[1], FileHandle);
    if ( FileRedirectionStatus < 0 )
    {
LABEL_35:
      RtlReleaseRelativeName(&RelativeName);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
      NtClose(FileHandle);
      goto LABEL_36;
    }
  }
  RtlReleaseRelativeName(&RelativeName);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
  if ( (AppCompatFlags.QuadPart & 0x100000000LL) != 0
    || (v20 = 3,
        v10 = NtSetInformationFile(FileHandle, &IoStatusBlock, &v20, 4u, (FILE_INFORMATION_CLASS)64),
        (int)(v10 + 0x80000000) >= 0)
    && v10 != -1073741535 )
  {
    v19 = 1;
    v10 = NtSetInformationFile(FileHandle, &IoStatusBlock, &v19, 1u, FileDispositionInformation);
  }
  NtClose(FileHandle);
  if ( v10 < 0 )
  {
    v5 = (unsigned int)v10;
    goto LABEL_4;
  }
  return 1;
}

```

## disassembly

```asm
0x1800d3ee8  mov     [rsp-8+arg_0], rbx
0x1800d3eed  push    rbp
0x1800d3eee  push    rsi
0x1800d3eef  push    rdi
0x1800d3ef0  push    r12
0x1800d3ef2  push    r13
0x1800d3ef4  push    r14
0x1800d3ef6  push    r15
0x1800d3ef8  lea     rbp, [rsp-27h]
0x1800d3efd  sub     rsp, 0B0h
0x1800d3f04  xorps   xmm0, xmm0
0x1800d3f07  lea     r9, [rbp+57h+RelativeName]
0x1800d3f0b  xor     r15d, r15d
0x1800d3f0e  xorps   xmm1, xmm1
0x1800d3f11  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800d3f15  mov     [rbp+57h+FileHandle], r15
0x1800d3f19  xor     eax, eax
0x1800d3f1b  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800d3f1f  mov     [rbp+57h+arg_8], r15b
0x1800d3f23  mov     esi, edx
0x1800d3f25  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800d3f29  mov     [rbp+57h+arg_10], r15d
0x1800d3f2d  xor     r8d, r8d
0x1800d3f30  movups  xmmword ptr [rbp+57h+P], xmm0
0x1800d3f34  lea     rdx, [rbp+57h+P]
0x1800d3f38  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x1800d3f3c  mov     rax, gs:60h
0x1800d3f45  mov     r14, [rax+2C8h]
0x1800d3f4c  mov     [rbp+57h+FileInformation], r15
0x1800d3f50  movups  xmmword ptr [rbp+57h+RelativeName.RelativeName.Length], xmm0
0x1800d3f54  movups  xmmword ptr [rbp+57h+RelativeName.ContainingDirectory], xmm0
0x1800d3f58  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U_WithStatus
0x1800d3f5f  nop     dword ptr [rax+rax+00h]
0x1800d3f64  test    eax, eax
0x1800d3f66  jns     short loc_1800D3F98
0x1800d3f68  cmp     eax, 0C0000017h
0x1800d3f6d  jnz     loc_1800D411E
0x1800d3f73  mov     ecx, eax
0x1800d3f75  call    BaseSetLastNTError
0x1800d3f7a  xor     eax, eax
0x1800d3f7c  mov     rbx, [rsp+0E0h+arg_0]
0x1800d3f84  add     rsp, 0B0h
0x1800d3f8b  pop     r15
0x1800d3f8d  pop     r14
0x1800d3f8f  pop     r13
0x1800d3f91  pop     r12
0x1800d3f93  pop     rdi
0x1800d3f94  pop     rsi
0x1800d3f95  pop     rbp
0x1800d3f96  retn
0x1800d3f98  movzx   eax, [rbp+57h+RelativeName.RelativeName.Length]
0x1800d3f9c  mov     rbx, [rbp+57h+P+8]
0x1800d3fa0  test    ax, ax
0x1800d3fa3  jnz     loc_1800D413F
0x1800d3fa9  mov     rax, r15
0x1800d3fac  mov     [rbp+57h+RelativeName.ContainingDirectory], rax
0x1800d3fb0  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x1800d3fb4  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800d3fb8  lea     rax, [rbp+57h+P]
0x1800d3fbc  mov     [rsp+0E0h+OpenOptions], 204040h; OpenOptions
0x1800d3fc4  xorps   xmm0, xmm0
0x1800d3fc7  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800d3fcb  mov     r13d, 7
0x1800d3fd1  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800d3fd8  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800d3fdc  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800d3fe3  mov     edx, 10080h; DesiredAccess
0x1800d3fe8  mov     [rsp+0E0h+ShareAccess], r13d; ShareAccess
0x1800d3fed  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800d3ff1  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800d3ff6  call    cs:__imp_NtOpenFile
0x1800d3ffd  nop     dword ptr [rax+rax+00h]
0x1800d4002  mov     edi, eax
0x1800d4004  mov     r12d, 10000h
0x1800d400a  test    eax, eax
0x1800d400c  js      loc_1800D4162
0x1800d4012  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800d4016  lea     r9d, [r13+1]; Length
0x1800d401a  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x1800d401e  mov     [rsp+0E0h+ShareAccess], 23h ; '#'; FileInformationClass
0x1800d4026  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800d402a  call    cs:__imp_NtQueryInformationFile
0x1800d4031  nop     dword ptr [rax+rax+00h]
0x1800d4036  mov     edi, eax
0x1800d4038  test    eax, eax
0x1800d403a  js      loc_1800D417B
0x1800d4040  test    dword ptr [rbp+57h+FileInformation], 400h
0x1800d4047  jnz     loc_1800D4198
0x1800d404d  test    r12d, esi
0x1800d4050  jnz     loc_1800D41BC
0x1800d4056  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x1800d405a  call    cs:__imp_RtlReleaseRelativeName
0x1800d4061  nop     dword ptr [rax+rax+00h]
0x1800d4066  mov     rcx, gs:60h
0x1800d406f  mov     r8, rbx; P
0x1800d4072  xor     edx, edx; Flags
0x1800d4074  mov     rcx, [rcx+30h]; HeapHandle
0x1800d4078  call    cs:__imp_RtlFreeHeap
0x1800d407f  nop     dword ptr [rax+rax+00h]
0x1800d4084  bt      r14, 20h ; ' '
0x1800d4089  mov     edi, 1
0x1800d408e  jb      short loc_1800D40F3
0x1800d4090  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800d4094  lea     r9d, [rdi+3]; Length
0x1800d4098  lea     r8, [rbp+57h+arg_10]; FileInformation
0x1800d409c  mov     [rbp+57h+arg_10], 3
0x1800d40a3  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800d40a7  mov     [rsp+0E0h+ShareAccess], 40h ; '@'; FileInformationClass
0x1800d40af  call    cs:__imp_NtSetInformationFile
0x1800d40b6  nop     dword ptr [rax+rax+00h]
0x1800d40bb  mov     ebx, eax
0x1800d40bd  mov     eax, 80000000h
0x1800d40c2  lea     ecx, [rbx+rax]
0x1800d40c5  test    eax, ecx
0x1800d40c7  jz      short loc_1800D40EB
0x1800d40c9  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800d40cd  call    cs:__imp_NtClose
0x1800d40d4  nop     dword ptr [rax+rax+00h]
0x1800d40d9  test    ebx, ebx
0x1800d40db  js      short loc_1800D40E4
0x1800d40dd  mov     eax, edi
0x1800d40df  jmp     loc_1800D3F7C
0x1800d40e4  mov     ecx, ebx
0x1800d40e6  jmp     loc_1800D3F75
0x1800d40eb  cmp     ebx, 0C0000121h
0x1800d40f1  jz      short loc_1800D40C9
0x1800d40f3  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800d40f7  lea     r8, [rbp+57h+arg_8]; FileInformation
0x1800d40fb  mov     r9d, edi; Length
0x1800d40fe  mov     [rbp+57h+arg_8], dil
0x1800d4102  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800d4106  mov     [rsp+0E0h+ShareAccess], 0Dh; FileInformationClass
0x1800d410e  call    cs:__imp_NtSetInformationFile
0x1800d4115  nop     dword ptr [rax+rax+00h]
0x1800d411a  mov     ebx, eax
0x1800d411c  jmp     short loc_1800D40C9
0x1800d411e  cmp     eax, 0C000009Ah
0x1800d4123  jz      loc_1800D3F73
0x1800d4129  mov     ecx, 3; LastError
0x1800d412e  call    cs:__imp_RtlSetLastWin32Error
0x1800d4135  nop     dword ptr [rax+rax+00h]
0x1800d413a  jmp     loc_1800D3F7A
0x1800d413f  mov     word ptr [rbp+57h+P], ax
0x1800d4143  mov     eax, dword ptr [rbp+57h+RelativeName.RelativeName.MaximumLength]
0x1800d4146  mov     dword ptr [rbp+57h+P+2], eax
0x1800d4149  movzx   eax, word ptr [rbp+57h+RelativeName.RelativeName+6]
0x1800d414d  mov     word ptr [rbp+57h+P+6], ax
0x1800d4151  mov     rax, [rbp+57h+RelativeName.RelativeName.Buffer]
0x1800d4155  mov     [rbp+57h+P+8], rax
0x1800d4159  mov     rax, [rbp+57h+RelativeName.ContainingDirectory]
0x1800d415d  jmp     loc_1800D3FB0
0x1800d4162  cmp     edi, 0C000000Dh
0x1800d4168  jnz     loc_1801A0BAD
0x1800d416e  mov     [rsp+0E0h+OpenOptions], 4040h
0x1800d4176  jmp     loc_1801A0B0E
0x1800d417b  cmp     edi, 0C0000002h
0x1800d4181  jz      loc_1800D404D
0x1800d4187  cmp     edi, 0C000000Dh
0x1800d418d  jz      loc_1800D404D
0x1800d4193  jmp     loc_1801A0B68
0x1800d4198  mov     eax, dword ptr [rbp+57h+FileInformation+4]
0x1800d419b  add     eax, 5FFFFFFDh
0x1800d41a0  cmp     eax, 16h
0x1800d41a3  ja      loc_1801A0BBA
0x1800d41a9  mov     ecx, 400201h
0x1800d41ae  bt      ecx, eax
0x1800d41b1  jb      loc_1800D404D
0x1800d41b7  jmp     loc_1801A0BBA
0x1800d41bc  mov     rdx, [rbp+57h+FileHandle]
0x1800d41c0  mov     rcx, [rbp+57h+P+8]
0x1800d41c4  call    BasepGetFileRedirectionStatus
0x1800d41c9  mov     edi, eax
0x1800d41cb  test    eax, eax
0x1800d41cd  js      loc_1801A0B68
0x1800d41d3  jmp     loc_1800D4056
0x1801a0b06  mov     [rsp+0E0h+OpenOptions], 204040h; OpenOptions
0x1801a0b0e  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1801a0b12  mov     [rsp+0E0h+ShareAccess], r13d; ShareAccess
0x1801a0b17  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1801a0b1b  mov     edx, r12d; DesiredAccess
0x1801a0b1e  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1801a0b22  call    cs:__imp_NtOpenFile
0x1801a0b29  nop     dword ptr [rax+rax+00h]
0x1801a0b2e  mov     edi, eax
0x1801a0b30  test    eax, eax
0x1801a0b32  jns     loc_1800D404D
0x1801a0b38  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x1801a0b3c  call    cs:__imp_RtlReleaseRelativeName
0x1801a0b43  nop     dword ptr [rax+rax+00h]
0x1801a0b48  mov     rcx, gs:60h
0x1801a0b51  mov     r8, rbx; P
0x1801a0b54  xor     edx, edx; Flags
0x1801a0b56  mov     rcx, [rcx+30h]; HeapHandle
0x1801a0b5a  call    cs:__imp_RtlFreeHeap
0x1801a0b61  nop     dword ptr [rax+rax+00h]
0x1801a0b66  jmp     short loc_1801A0BA6
0x1801a0b68  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x1801a0b6c  call    cs:__imp_RtlReleaseRelativeName
0x1801a0b73  nop     dword ptr [rax+rax+00h]
0x1801a0b78  mov     rcx, gs:60h
0x1801a0b81  mov     r8, rbx; P
0x1801a0b84  xor     edx, edx; Flags
0x1801a0b86  mov     rcx, [rcx+30h]; HeapHandle
0x1801a0b8a  call    cs:__imp_RtlFreeHeap
0x1801a0b91  nop     dword ptr [rax+rax+00h]
0x1801a0b96  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1801a0b9a  call    cs:__imp_NtClose
0x1801a0ba1  nop     dword ptr [rax+rax+00h]
0x1801a0ba6  mov     ecx, edi
0x1801a0ba8  jmp     loc_1800D3F75
0x1801a0bad  cmp     edi, 0C0000022h
0x1801a0bb3  jnz     short loc_1801A0B38
0x1801a0bb5  jmp     loc_1801A0B06
0x1801a0bba  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1801a0bbe  call    cs:__imp_NtClose
0x1801a0bc5  nop     dword ptr [rax+rax+00h]
0x1801a0bca  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1801a0bce  mov     [rsp+0E0h+OpenOptions], 4040h; OpenOptions
0x1801a0bd6  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1801a0bda  mov     [rsp+0E0h+ShareAccess], r13d; ShareAccess
0x1801a0bdf  mov     edx, r12d; DesiredAccess
0x1801a0be2  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1801a0be6  call    cs:__imp_NtOpenFile
0x1801a0bed  nop     dword ptr [rax+rax+00h]
0x1801a0bf2  mov     edi, eax
0x1801a0bf4  test    eax, eax
0x1801a0bf6  jns     loc_1800D404D
0x1801a0bfc  lea     ecx, [rax+3FFFFD8Ah]
0x1801a0c02  test    ecx, 0FFFFFFFCh
0x1801a0c08  jnz     loc_1801A0B38
0x1801a0c0e  cmp     eax, 0C0000277h
0x1801a0c13  jz      loc_1801A0B38
0x1801a0c19  jmp     loc_1801A0B06
```
