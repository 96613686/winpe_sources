# GetFileInformation

- ea: `0x14001d010`
- end: `0x14001d373`
- name: `GetFileInformation`
- size: `867`
- prototype: `__int64 __fastcall(__int64, struct _UNICODE_STRING *, char *, __int64, char **, void *, void **)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14001af3c`
- `0x14001c3d0`

## callees

- `0x140001874`
- `0x140006000`
- `0x14001b650`
- `0x14001d010`
- `0x14001dd40`
- `0x140021200`
- `0x140024f80`

## import_xrefs

- `ntoskrnl!ZwQueryDirectoryFile` at `0x14001d2ba`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x14001d2ba`
- `ntoskrnl!IoCreateFileEx` at `0x14001d175`
- `ntoskrnl!IoCreateFileEx` at `0x14001d175`
- `ntoskrnl!ZwClose` at `0x14001d20e`
- `ntoskrnl!ZwClose` at `0x14001d20e`
- `ntoskrnl!ObfDereferenceObject` at `0x14001d320`
- `ntoskrnl!ObfDereferenceObject` at `0x14001d320`
- `FLTMGR!FltQueryDirectoryFile` at `0x14001d27b`
- `FLTMGR!FltQueryDirectoryFile` at `0x14001d27b`
- `FLTMGR!FltClose` at `0x14001d200`
- `FLTMGR!FltClose` at `0x14001d200`
- `FLTMGR!FltCreateFileEx2` at `0x14001d1e1`
- `FLTMGR!FltCreateFileEx2` at `0x14001d1e1`

## pseudocode

```c
__int64 __fastcall GetFileInformation(
        __int64 a1,
        struct _UNICODE_STRING *a2,
        char *a3,
        __int64 a4,
        char **a5,
        void *a6,
        void **a7)
{
  void *v8; // rax
  __int128 v11; // xmm0
  __int128 *v12; // rdi
  __int64 result; // rax
  __int64 v14; // r14
  unsigned __int64 v15; // r14
  struct _FLT_INSTANCE *v16; // rdx
  NTSTATUS v17; // eax
  void *v18; // rcx
  int v19; // ebx
  void *v20; // rcx
  char *v21; // rdi
  ULONG v22; // esi
  NTSTATUS v23; // eax
  char *Pool; // rax
  void *FileHandle; // [rsp+80h] [rbp-61h] BYREF
  PFILE_OBJECT FileObject; // [rsp+88h] [rbp-59h] BYREF
  __int128 v27; // [rsp+90h] [rbp-51h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A0h] [rbp-41h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-31h] BYREF

  FileHandle = 0;
  v8 = *a7;
  FileObject = 0;
  v27 = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  if ( v8 )
    goto LABEL_13;
  v8 = a6;
  if ( a6 )
  {
    v11 = *(_OWORD *)(a1 + 80);
LABEL_12:
    v27 = v11;
LABEL_13:
    v14 = *(_QWORD *)(a1 + 168);
    ObjectAttributes.RootDirectory = v8;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)&v27;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 576;
    FileObject = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v15 = v14 & 0xFFFFFFFFFFFFFFF8uLL;
    if ( v15 )
      v16 = *(struct _FLT_INSTANCE **)(v15 + 16);
    else
      v16 = 0;
    if ( LuafvDriverData )
      v17 = FltCreateFileEx2(
              LuafvDriverData,
              v16,
              &FileHandle,
              &FileObject,
              0x100001u,
              &ObjectAttributes,
              &IoStatusBlock,
              0,
              0x80u,
              7u,
              1u,
              0x21u,
              0,
              0,
              0x800u,
              0);
    else
      v17 = IoCreateFileEx(
              &FileHandle,
              0x100001u,
              &ObjectAttributes,
              &IoStatusBlock,
              0,
              0x80u,
              7u,
              1u,
              0x21u,
              0,
              0,
              CreateFileTypeNone,
              0,
              0x800u,
              0);
    v18 = *a7;
    v19 = v17;
    if ( *a7 )
    {
      if ( LuafvDriverData )
        FltClose(v18);
      else
        ZwClose(v18);
    }
    if ( v19 >= 0 )
    {
      v20 = FileHandle;
      v21 = a3;
      *a7 = FileHandle;
      v22 = 176;
      while ( 1 )
      {
        v23 = FileObject
            ? FltQueryDirectoryFile(
                *(PFLT_INSTANCE *)(v15 + 16),
                FileObject,
                v21,
                v22,
                FileIdBothDirectoryInformation,
                1u,
                a2,
                1u,
                0)
            : ZwQueryDirectoryFile(v20, 0, 0, 0, &IoStatusBlock, v21, v22, FileIdBothDirectoryInformation, 1u, a2, 1u);
        v19 = v23;
        if ( v23 != -2147483643 && v23 != -1073741789 )
          break;
        if ( v21 != a3 )
          LuafvFreePool(v21);
        v22 *= 2;
        Pool = LuafvAllocatePool(1, v22, 1);
        v21 = Pool;
        if ( !Pool )
        {
          v19 = -1073741670;
          break;
        }
        memset(Pool, 0, v22);
        v20 = FileHandle;
      }
      if ( FileObject )
        ObfDereferenceObject(FileObject);
      if ( v19 >= 0 )
      {
        *a5 = v21;
        return (unsigned int)v19;
      }
      if ( v21 != a3 && v21 )
        LuafvFreePool(v21);
      if ( v19 == -1073741809 )
        v19 = 0;
    }
    else
    {
      *a7 = 0;
      if ( v19 != -1073741772 && v19 != -1073741766 )
        return (unsigned int)v19;
      v19 = 0;
    }
    *a5 = 0;
    return (unsigned int)v19;
  }
  if ( *(_QWORD *)(a1 + 248) )
  {
    v12 = (__int128 *)(a1 + 240);
LABEL_11:
    v11 = *v12;
    v8 = 0;
    goto LABEL_12;
  }
  v12 = (__int128 *)(a1 + 240);
  if ( (unsigned int)Feature_Bugfix_LuafvTableNode__private_IsEnabledDeviceUsageNoInline() )
    result = LuafvBuildTableNodeName2(a1, 0, 0, 0, 1, 1, (__int64)v12);
  else
    result = LuafvBuildTableNodeName(a1, 0, 0, 0, 1, (__int64)v12);
  if ( (int)result >= 0 )
    goto LABEL_11;
  return result;
}

```

## disassembly

```asm
0x14001d010  push    rbp
0x14001d012  push    rbx
0x14001d013  push    rsi
0x14001d014  push    rdi
0x14001d015  push    r12
0x14001d017  push    r13
0x14001d019  push    r14
0x14001d01b  push    r15
0x14001d01d  lea     rbp, [rsp-7]
0x14001d022  sub     rsp, 0E8h
0x14001d029  mov     rsi, [rbp+3Fh+arg_30]
0x14001d02d  xorps   xmm0, xmm0
0x14001d030  xor     r13d, r13d
0x14001d033  xor     eax, eax
0x14001d035  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.ObjectName], xmm0
0x14001d039  mov     r15, r8
0x14001d03c  mov     [rbp+3Fh+FileHandle], r13
0x14001d040  mov     rax, [rsi]
0x14001d043  mov     r12, rdx
0x14001d046  mov     [rbp+3Fh+FileObject], r13
0x14001d04a  mov     rbx, rcx
0x14001d04d  movups  [rbp+3Fh+var_90], xmm0
0x14001d051  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.Length], xmm0
0x14001d055  movups  xmmword ptr [rbp+3Fh+ObjectAttributes+1Ch], xmm0
0x14001d059  movups  xmmword ptr [rbp+3Fh+IoStatusBlock], xmm0
0x14001d05d  test    rax, rax
0x14001d060  jnz     short loc_14001D0D6
0x14001d062  mov     rax, [rbp+3Fh+arg_28]
0x14001d066  test    rax, rax
0x14001d069  jz      short loc_14001D071
0x14001d06b  movups  xmm0, xmmword ptr [rcx+50h]
0x14001d06f  jmp     short loc_14001D0D1
0x14001d071  cmp     [rcx+0F8h], r13
0x14001d078  jnz     short loc_14001D0C4
0x14001d07a  lea     rdi, [rcx+0F0h]
0x14001d081  call    Feature_Bugfix_LuafvTableNode__private_IsEnabledDeviceUsageNoInline
0x14001d086  xor     r9d, r9d
0x14001d089  xor     r8d, r8d
0x14001d08c  xor     edx, edx
0x14001d08e  mov     rcx, rbx
0x14001d091  test    eax, eax
0x14001d093  jnz     short loc_14001D0A6
0x14001d095  mov     qword ptr [rsp+120h+FileAttributes], rdi
0x14001d09a  mov     byte ptr [rsp+120h+AllocationSize], 1
0x14001d09f  call    LuafvBuildTableNodeName
0x14001d0a4  jmp     short loc_14001D0BA
0x14001d0a6  mov     qword ptr [rsp+120h+ShareAccess], rdi
0x14001d0ab  mov     byte ptr [rsp+120h+FileAttributes], 1
0x14001d0b0  mov     byte ptr [rsp+120h+AllocationSize], 1
0x14001d0b5  call    LuafvBuildTableNodeName2
0x14001d0ba  test    eax, eax
0x14001d0bc  js      loc_14001D35E
0x14001d0c2  jmp     short loc_14001D0CB
0x14001d0c4  lea     rdi, [rcx+0F0h]
0x14001d0cb  movups  xmm0, xmmword ptr [rdi]
0x14001d0ce  mov     rax, r13
0x14001d0d1  movdqu  [rbp+3Fh+var_90], xmm0
0x14001d0d6  mov     r14, [rbx+0A8h]
0x14001d0dd  xorps   xmm0, xmm0
0x14001d0e0  mov     [rbp+3Fh+ObjectAttributes.RootDirectory], rax
0x14001d0e4  lea     rax, [rbp+3Fh+var_90]
0x14001d0e8  mov     [rbp+3Fh+ObjectAttributes.ObjectName], rax
0x14001d0ec  mov     [rbp+3Fh+ObjectAttributes.Length], 30h ; '0'
0x14001d0f3  mov     [rbp+3Fh+ObjectAttributes.Attributes], 240h
0x14001d0fa  mov     [rbp+3Fh+FileObject], r13
0x14001d0fe  movdqu  xmmword ptr [rbp+3Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x14001d103  and     r14, 0FFFFFFFFFFFFFFF8h
0x14001d107  jz      short loc_14001D10F
0x14001d109  mov     rdx, [r14+10h]
0x14001d10d  jmp     short loc_14001D112
0x14001d10f  mov     rdx, r13; Instance
0x14001d112  mov     rcx, cs:LuafvDriverData; Filter
0x14001d119  test    rcx, rcx
0x14001d11c  jnz     short loc_14001D183
0x14001d11e  mov     [rsp+120h+DriverContext], r13; DriverContext
0x14001d123  lea     r9, [rbp+3Fh+IoStatusBlock]; IoStatusBlock
0x14001d127  mov     [rsp+120h+Options], 800h; Options
0x14001d12f  lea     r8, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x14001d133  mov     [rsp+120h+InternalParameters], r13; InternalParameters
0x14001d138  lea     rcx, [rbp+3Fh+FileHandle]; FileHandle
0x14001d13c  mov     [rsp+120h+CreateFileType], r13d; CreateFileType
0x14001d141  mov     edx, 100001h; DesiredAccess
0x14001d146  mov     [rsp+120h+EaLength], r13d; EaLength
0x14001d14b  mov     [rsp+120h+EaBuffer], r13; EaBuffer
0x14001d150  mov     [rsp+120h+CreateOptions], 21h ; '!'; CreateOptions
0x14001d158  mov     [rsp+120h+Disposition], 1; Disposition
0x14001d160  mov     [rsp+120h+ShareAccess], 7; ShareAccess
0x14001d168  mov     [rsp+120h+FileAttributes], 80h; FileAttributes
0x14001d170  mov     [rsp+120h+AllocationSize], r13; AllocationSize
0x14001d175  call    cs:__imp_IoCreateFileEx
0x14001d17c  nop     dword ptr [rax+rax+00h]
0x14001d181  jmp     short loc_14001D1ED
0x14001d183  mov     [rsp+120h+var_A8], r13; DriverContext
0x14001d188  lea     rax, [rbp+3Fh+IoStatusBlock]
0x14001d18c  mov     dword ptr [rsp+120h+DriverContext], 800h; Flags
0x14001d194  lea     r9, [rbp+3Fh+FileObject]; FileObject
0x14001d198  mov     [rsp+120h+Options], r13d; EaLength
0x14001d19d  lea     r8, [rbp+3Fh+FileHandle]; FileHandle
0x14001d1a1  mov     [rsp+120h+InternalParameters], r13; EaBuffer
0x14001d1a6  mov     [rsp+120h+CreateFileType], 21h ; '!'; CreateOptions
0x14001d1ae  mov     [rsp+120h+EaLength], 1; CreateDisposition
0x14001d1b6  mov     dword ptr [rsp+120h+EaBuffer], 7; ShareAccess
0x14001d1be  mov     [rsp+120h+CreateOptions], 80h; FileAttributes
0x14001d1c6  mov     qword ptr [rsp+120h+Disposition], r13; AllocationSize
0x14001d1cb  mov     qword ptr [rsp+120h+ShareAccess], rax; IoStatusBlock
0x14001d1d0  lea     rax, [rbp+3Fh+ObjectAttributes]
0x14001d1d4  mov     qword ptr [rsp+120h+FileAttributes], rax; ObjectAttributes
0x14001d1d9  mov     dword ptr [rsp+120h+AllocationSize], 100001h; DesiredAccess
0x14001d1e1  call    cs:__imp_FltCreateFileEx2
0x14001d1e8  nop     dword ptr [rax+rax+00h]
0x14001d1ed  mov     rcx, [rsi]; Handle
0x14001d1f0  mov     ebx, eax
0x14001d1f2  test    rcx, rcx
0x14001d1f5  jz      short loc_14001D21A
0x14001d1f7  cmp     cs:LuafvDriverData, r13
0x14001d1fe  jz      short loc_14001D20E
0x14001d200  call    cs:__imp_FltClose
0x14001d207  nop     dword ptr [rax+rax+00h]
0x14001d20c  jmp     short loc_14001D21A
0x14001d20e  call    cs:__imp_ZwClose
0x14001d215  nop     dword ptr [rax+rax+00h]
0x14001d21a  test    ebx, ebx
0x14001d21c  jns     short loc_14001D23D
0x14001d21e  mov     [rsi], r13
0x14001d221  cmp     ebx, 0C0000034h
0x14001d227  jz      short loc_14001D235
0x14001d229  cmp     ebx, 0C000003Ah
0x14001d22f  jnz     loc_14001D35C
0x14001d235  mov     ebx, r13d
0x14001d238  jmp     loc_14001D355
0x14001d23d  mov     rcx, [rbp+3Fh+FileHandle]; FileHandle
0x14001d241  mov     rdi, r15
0x14001d244  mov     [rsi], rcx
0x14001d247  mov     esi, 0B0h
0x14001d24c  mov     rdx, [rbp+3Fh+FileObject]; FileObject
0x14001d250  test    rdx, rdx
0x14001d253  jz      short loc_14001D289
0x14001d255  mov     rcx, [r14+10h]; Instance
0x14001d259  mov     r9d, esi; Length
0x14001d25c  mov     qword ptr [rsp+120h+CreateOptions], r13; LengthReturned
0x14001d261  mov     r8, rdi; FileInformation
0x14001d264  mov     byte ptr [rsp+120h+Disposition], 1; RestartScan
0x14001d269  mov     qword ptr [rsp+120h+ShareAccess], r12; FileName
0x14001d26e  mov     byte ptr [rsp+120h+FileAttributes], 1; ReturnSingleEntry
0x14001d273  mov     dword ptr [rsp+120h+AllocationSize], 25h ; '%'; FileInformationClass
0x14001d27b  call    cs:__imp_FltQueryDirectoryFile
0x14001d282  nop     dword ptr [rax+rax+00h]
0x14001d287  jmp     short loc_14001D2C6
0x14001d289  mov     byte ptr [rsp+120h+EaLength], 1; RestartScan
0x14001d28e  lea     rax, [rbp+3Fh+IoStatusBlock]
0x14001d292  mov     [rsp+120h+EaBuffer], r12; FileName
0x14001d297  xor     r9d, r9d; ApcContext
0x14001d29a  mov     byte ptr [rsp+120h+CreateOptions], 1; ReturnSingleEntry
0x14001d29f  xor     r8d, r8d; ApcRoutine
0x14001d2a2  mov     [rsp+120h+Disposition], 25h ; '%'; FileInformationClass
0x14001d2aa  xor     edx, edx; Event
0x14001d2ac  mov     [rsp+120h+ShareAccess], esi; Length
0x14001d2b0  mov     qword ptr [rsp+120h+FileAttributes], rdi; FileInformation
0x14001d2b5  mov     [rsp+120h+AllocationSize], rax; IoStatusBlock
0x14001d2ba  call    cs:__imp_ZwQueryDirectoryFile
0x14001d2c1  nop     dword ptr [rax+rax+00h]
0x14001d2c6  mov     ebx, eax
0x14001d2c8  cmp     eax, 80000005h
0x14001d2cd  jz      short loc_14001D2D6
0x14001d2cf  cmp     eax, 0C0000023h
0x14001d2d4  jnz     short loc_14001D317
0x14001d2d6  cmp     rdi, r15
0x14001d2d9  jz      short loc_14001D2E3
0x14001d2db  mov     rcx, rdi
0x14001d2de  call    LuafvFreePool
0x14001d2e3  add     esi, esi
0x14001d2e5  mov     r8b, 1
0x14001d2e8  mov     edx, esi
0x14001d2ea  mov     ecx, 1
0x14001d2ef  call    LuafvAllocatePool
0x14001d2f4  mov     rdi, rax
0x14001d2f7  test    rax, rax
0x14001d2fa  jz      short loc_14001D312
0x14001d2fc  mov     r8d, esi; Size
0x14001d2ff  xor     edx, edx; Val
0x14001d301  mov     rcx, rax; void *
0x14001d304  call    memset
0x14001d309  mov     rcx, [rbp+3Fh+FileHandle]
0x14001d30d  jmp     loc_14001D24C
0x14001d312  mov     ebx, 0C000009Ah
0x14001d317  mov     rcx, [rbp+3Fh+FileObject]; Object
0x14001d31b  test    rcx, rcx
0x14001d31e  jz      short loc_14001D32C
0x14001d320  call    cs:__imp_ObfDereferenceObject
0x14001d327  nop     dword ptr [rax+rax+00h]
0x14001d32c  test    ebx, ebx
0x14001d32e  js      short loc_14001D339
0x14001d330  mov     rax, [rbp+3Fh+arg_20]
0x14001d334  mov     [rax], rdi
0x14001d337  jmp     short loc_14001D35C
0x14001d339  cmp     rdi, r15
0x14001d33c  jz      short loc_14001D34B
0x14001d33e  test    rdi, rdi
0x14001d341  jz      short loc_14001D34B
0x14001d343  mov     rcx, rdi
0x14001d346  call    LuafvFreePool
0x14001d34b  cmp     ebx, 0C000000Fh
0x14001d351  cmovz   ebx, r13d
0x14001d355  mov     rax, [rbp+3Fh+arg_20]
0x14001d359  mov     [rax], r13
0x14001d35c  mov     eax, ebx
0x14001d35e  add     rsp, 0E8h
0x14001d365  pop     r15
0x14001d367  pop     r14
0x14001d369  pop     r13
0x14001d36b  pop     r12
0x14001d36d  pop     rdi
0x14001d36e  pop     rsi
0x14001d36f  pop     rbx
0x14001d370  pop     rbp
0x14001d371  retn
```
