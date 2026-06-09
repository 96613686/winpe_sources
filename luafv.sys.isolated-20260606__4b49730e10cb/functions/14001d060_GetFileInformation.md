# GetFileInformation

- ea: `0x14001d060`
- end: `0x14001d3c3`
- name: `GetFileInformation`
- size: `867`
- prototype: `__int64 __fastcall(__int64, struct _UNICODE_STRING *, void *, __int64, _QWORD *, void *, void **)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14001af8c`
- `0x14001c420`

## callees

- `0x140001874`
- `0x140006380`
- `0x14001b6a0`
- `0x14001d060`
- `0x14001dd90`
- `0x140021250`
- `0x140024fd0`

## import_xrefs

- `ntoskrnl!ZwQueryDirectoryFile` at `0x14001d30a`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x14001d30a`
- `ntoskrnl!IoCreateFileEx` at `0x14001d1c5`
- `ntoskrnl!IoCreateFileEx` at `0x14001d1c5`
- `ntoskrnl!ZwClose` at `0x14001d25e`
- `ntoskrnl!ZwClose` at `0x14001d25e`
- `ntoskrnl!ObfDereferenceObject` at `0x14001d370`
- `ntoskrnl!ObfDereferenceObject` at `0x14001d370`
- `FLTMGR!FltQueryDirectoryFile` at `0x14001d2cb`
- `FLTMGR!FltQueryDirectoryFile` at `0x14001d2cb`
- `FLTMGR!FltClose` at `0x14001d250`
- `FLTMGR!FltClose` at `0x14001d250`
- `FLTMGR!FltCreateFileEx2` at `0x14001d231`
- `FLTMGR!FltCreateFileEx2` at `0x14001d231`

## pseudocode

```c
__int64 __fastcall GetFileInformation(
        __int64 a1,
        struct _UNICODE_STRING *a2,
        void *a3,
        __int64 a4,
        _QWORD *a5,
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
  void *v21; // rdi
  ULONG v22; // esi
  NTSTATUS v23; // eax
  __int64 v24; // r8
  void *Pool; // rax
  void *FileHandle; // [rsp+80h] [rbp-61h] BYREF
  PFILE_OBJECT FileObject; // [rsp+88h] [rbp-59h] BYREF
  __int128 v28; // [rsp+90h] [rbp-51h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A0h] [rbp-41h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-31h] BYREF

  FileHandle = 0;
  v8 = *a7;
  FileObject = 0;
  v28 = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  if ( v8 )
    goto LABEL_13;
  v8 = a6;
  if ( a6 )
  {
    v11 = *(_OWORD *)(a1 + 80);
LABEL_12:
    v28 = v11;
LABEL_13:
    v14 = *(_QWORD *)(a1 + 168);
    ObjectAttributes.RootDirectory = v8;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)&v28;
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
        LOBYTE(v24) = 1;
        Pool = (void *)LuafvAllocatePool(1, v22, v24);
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
0x14001d060  push    rbp
0x14001d062  push    rbx
0x14001d063  push    rsi
0x14001d064  push    rdi
0x14001d065  push    r12
0x14001d067  push    r13
0x14001d069  push    r14
0x14001d06b  push    r15
0x14001d06d  lea     rbp, [rsp-7]
0x14001d072  sub     rsp, 0E8h
0x14001d079  mov     rsi, [rbp+3Fh+arg_30]
0x14001d07d  xorps   xmm0, xmm0
0x14001d080  xor     r13d, r13d
0x14001d083  xor     eax, eax
0x14001d085  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.ObjectName], xmm0
0x14001d089  mov     r15, r8
0x14001d08c  mov     [rbp+3Fh+FileHandle], r13
0x14001d090  mov     rax, [rsi]
0x14001d093  mov     r12, rdx
0x14001d096  mov     [rbp+3Fh+FileObject], r13
0x14001d09a  mov     rbx, rcx
0x14001d09d  movups  [rbp+3Fh+var_90], xmm0
0x14001d0a1  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.Length], xmm0
0x14001d0a5  movups  xmmword ptr [rbp+3Fh+ObjectAttributes+1Ch], xmm0
0x14001d0a9  movups  xmmword ptr [rbp+3Fh+IoStatusBlock], xmm0
0x14001d0ad  test    rax, rax
0x14001d0b0  jnz     short loc_14001D126
0x14001d0b2  mov     rax, [rbp+3Fh+arg_28]
0x14001d0b6  test    rax, rax
0x14001d0b9  jz      short loc_14001D0C1
0x14001d0bb  movups  xmm0, xmmword ptr [rcx+50h]
0x14001d0bf  jmp     short loc_14001D121
0x14001d0c1  cmp     [rcx+0F8h], r13
0x14001d0c8  jnz     short loc_14001D114
0x14001d0ca  lea     rdi, [rcx+0F0h]
0x14001d0d1  call    Feature_Bugfix_LuafvTableNode__private_IsEnabledDeviceUsageNoInline
0x14001d0d6  xor     r9d, r9d
0x14001d0d9  xor     r8d, r8d
0x14001d0dc  xor     edx, edx
0x14001d0de  mov     rcx, rbx
0x14001d0e1  test    eax, eax
0x14001d0e3  jnz     short loc_14001D0F6
0x14001d0e5  mov     qword ptr [rsp+120h+FileAttributes], rdi
0x14001d0ea  mov     byte ptr [rsp+120h+AllocationSize], 1
0x14001d0ef  call    LuafvBuildTableNodeName
0x14001d0f4  jmp     short loc_14001D10A
0x14001d0f6  mov     qword ptr [rsp+120h+ShareAccess], rdi
0x14001d0fb  mov     byte ptr [rsp+120h+FileAttributes], 1
0x14001d100  mov     byte ptr [rsp+120h+AllocationSize], 1
0x14001d105  call    LuafvBuildTableNodeName2
0x14001d10a  test    eax, eax
0x14001d10c  js      loc_14001D3AE
0x14001d112  jmp     short loc_14001D11B
0x14001d114  lea     rdi, [rcx+0F0h]
0x14001d11b  movups  xmm0, xmmword ptr [rdi]
0x14001d11e  mov     rax, r13
0x14001d121  movdqu  [rbp+3Fh+var_90], xmm0
0x14001d126  mov     r14, [rbx+0A8h]
0x14001d12d  xorps   xmm0, xmm0
0x14001d130  mov     [rbp+3Fh+ObjectAttributes.RootDirectory], rax
0x14001d134  lea     rax, [rbp+3Fh+var_90]
0x14001d138  mov     [rbp+3Fh+ObjectAttributes.ObjectName], rax
0x14001d13c  mov     [rbp+3Fh+ObjectAttributes.Length], 30h ; '0'
0x14001d143  mov     [rbp+3Fh+ObjectAttributes.Attributes], 240h
0x14001d14a  mov     [rbp+3Fh+FileObject], r13
0x14001d14e  movdqu  xmmword ptr [rbp+3Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x14001d153  and     r14, 0FFFFFFFFFFFFFFF8h
0x14001d157  jz      short loc_14001D15F
0x14001d159  mov     rdx, [r14+10h]
0x14001d15d  jmp     short loc_14001D162
0x14001d15f  mov     rdx, r13; Instance
0x14001d162  mov     rcx, cs:LuafvDriverData; Filter
0x14001d169  test    rcx, rcx
0x14001d16c  jnz     short loc_14001D1D3
0x14001d16e  mov     [rsp+120h+DriverContext], r13; DriverContext
0x14001d173  lea     r9, [rbp+3Fh+IoStatusBlock]; IoStatusBlock
0x14001d177  mov     [rsp+120h+Options], 800h; Options
0x14001d17f  lea     r8, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x14001d183  mov     [rsp+120h+InternalParameters], r13; InternalParameters
0x14001d188  lea     rcx, [rbp+3Fh+FileHandle]; FileHandle
0x14001d18c  mov     [rsp+120h+CreateFileType], r13d; CreateFileType
0x14001d191  mov     edx, 100001h; DesiredAccess
0x14001d196  mov     [rsp+120h+EaLength], r13d; EaLength
0x14001d19b  mov     [rsp+120h+EaBuffer], r13; EaBuffer
0x14001d1a0  mov     [rsp+120h+CreateOptions], 21h ; '!'; CreateOptions
0x14001d1a8  mov     [rsp+120h+Disposition], 1; Disposition
0x14001d1b0  mov     [rsp+120h+ShareAccess], 7; ShareAccess
0x14001d1b8  mov     [rsp+120h+FileAttributes], 80h; FileAttributes
0x14001d1c0  mov     [rsp+120h+AllocationSize], r13; AllocationSize
0x14001d1c5  call    cs:__imp_IoCreateFileEx
0x14001d1cc  nop     dword ptr [rax+rax+00h]
0x14001d1d1  jmp     short loc_14001D23D
0x14001d1d3  mov     [rsp+120h+var_A8], r13; DriverContext
0x14001d1d8  lea     rax, [rbp+3Fh+IoStatusBlock]
0x14001d1dc  mov     dword ptr [rsp+120h+DriverContext], 800h; Flags
0x14001d1e4  lea     r9, [rbp+3Fh+FileObject]; FileObject
0x14001d1e8  mov     [rsp+120h+Options], r13d; EaLength
0x14001d1ed  lea     r8, [rbp+3Fh+FileHandle]; FileHandle
0x14001d1f1  mov     [rsp+120h+InternalParameters], r13; EaBuffer
0x14001d1f6  mov     [rsp+120h+CreateFileType], 21h ; '!'; CreateOptions
0x14001d1fe  mov     [rsp+120h+EaLength], 1; CreateDisposition
0x14001d206  mov     dword ptr [rsp+120h+EaBuffer], 7; ShareAccess
0x14001d20e  mov     [rsp+120h+CreateOptions], 80h; FileAttributes
0x14001d216  mov     qword ptr [rsp+120h+Disposition], r13; AllocationSize
0x14001d21b  mov     qword ptr [rsp+120h+ShareAccess], rax; IoStatusBlock
0x14001d220  lea     rax, [rbp+3Fh+ObjectAttributes]
0x14001d224  mov     qword ptr [rsp+120h+FileAttributes], rax; ObjectAttributes
0x14001d229  mov     dword ptr [rsp+120h+AllocationSize], 100001h; DesiredAccess
0x14001d231  call    cs:__imp_FltCreateFileEx2
0x14001d238  nop     dword ptr [rax+rax+00h]
0x14001d23d  mov     rcx, [rsi]; Handle
0x14001d240  mov     ebx, eax
0x14001d242  test    rcx, rcx
0x14001d245  jz      short loc_14001D26A
0x14001d247  cmp     cs:LuafvDriverData, r13
0x14001d24e  jz      short loc_14001D25E
0x14001d250  call    cs:__imp_FltClose
0x14001d257  nop     dword ptr [rax+rax+00h]
0x14001d25c  jmp     short loc_14001D26A
0x14001d25e  call    cs:__imp_ZwClose
0x14001d265  nop     dword ptr [rax+rax+00h]
0x14001d26a  test    ebx, ebx
0x14001d26c  jns     short loc_14001D28D
0x14001d26e  mov     [rsi], r13
0x14001d271  cmp     ebx, 0C0000034h
0x14001d277  jz      short loc_14001D285
0x14001d279  cmp     ebx, 0C000003Ah
0x14001d27f  jnz     loc_14001D3AC
0x14001d285  mov     ebx, r13d
0x14001d288  jmp     loc_14001D3A5
0x14001d28d  mov     rcx, [rbp+3Fh+FileHandle]; FileHandle
0x14001d291  mov     rdi, r15
0x14001d294  mov     [rsi], rcx
0x14001d297  mov     esi, 0B0h
0x14001d29c  mov     rdx, [rbp+3Fh+FileObject]; FileObject
0x14001d2a0  test    rdx, rdx
0x14001d2a3  jz      short loc_14001D2D9
0x14001d2a5  mov     rcx, [r14+10h]; Instance
0x14001d2a9  mov     r9d, esi; Length
0x14001d2ac  mov     qword ptr [rsp+120h+CreateOptions], r13; LengthReturned
0x14001d2b1  mov     r8, rdi; FileInformation
0x14001d2b4  mov     byte ptr [rsp+120h+Disposition], 1; RestartScan
0x14001d2b9  mov     qword ptr [rsp+120h+ShareAccess], r12; FileName
0x14001d2be  mov     byte ptr [rsp+120h+FileAttributes], 1; ReturnSingleEntry
0x14001d2c3  mov     dword ptr [rsp+120h+AllocationSize], 25h ; '%'; FileInformationClass
0x14001d2cb  call    cs:__imp_FltQueryDirectoryFile
0x14001d2d2  nop     dword ptr [rax+rax+00h]
0x14001d2d7  jmp     short loc_14001D316
0x14001d2d9  mov     byte ptr [rsp+120h+EaLength], 1; RestartScan
0x14001d2de  lea     rax, [rbp+3Fh+IoStatusBlock]
0x14001d2e2  mov     [rsp+120h+EaBuffer], r12; FileName
0x14001d2e7  xor     r9d, r9d; ApcContext
0x14001d2ea  mov     byte ptr [rsp+120h+CreateOptions], 1; ReturnSingleEntry
0x14001d2ef  xor     r8d, r8d; ApcRoutine
0x14001d2f2  mov     [rsp+120h+Disposition], 25h ; '%'; FileInformationClass
0x14001d2fa  xor     edx, edx; Event
0x14001d2fc  mov     [rsp+120h+ShareAccess], esi; Length
0x14001d300  mov     qword ptr [rsp+120h+FileAttributes], rdi; FileInformation
0x14001d305  mov     [rsp+120h+AllocationSize], rax; IoStatusBlock
0x14001d30a  call    cs:__imp_ZwQueryDirectoryFile
0x14001d311  nop     dword ptr [rax+rax+00h]
0x14001d316  mov     ebx, eax
0x14001d318  cmp     eax, 80000005h
0x14001d31d  jz      short loc_14001D326
0x14001d31f  cmp     eax, 0C0000023h
0x14001d324  jnz     short loc_14001D367
0x14001d326  cmp     rdi, r15
0x14001d329  jz      short loc_14001D333
0x14001d32b  mov     rcx, rdi
0x14001d32e  call    LuafvFreePool
0x14001d333  add     esi, esi
0x14001d335  mov     r8b, 1
0x14001d338  mov     edx, esi
0x14001d33a  mov     ecx, 1
0x14001d33f  call    LuafvAllocatePool
0x14001d344  mov     rdi, rax
0x14001d347  test    rax, rax
0x14001d34a  jz      short loc_14001D362
0x14001d34c  mov     r8d, esi; Size
0x14001d34f  xor     edx, edx; Val
0x14001d351  mov     rcx, rax; void *
0x14001d354  call    memset
0x14001d359  mov     rcx, [rbp+3Fh+FileHandle]
0x14001d35d  jmp     loc_14001D29C
0x14001d362  mov     ebx, 0C000009Ah
0x14001d367  mov     rcx, [rbp+3Fh+FileObject]; Object
0x14001d36b  test    rcx, rcx
0x14001d36e  jz      short loc_14001D37C
0x14001d370  call    cs:__imp_ObfDereferenceObject
0x14001d377  nop     dword ptr [rax+rax+00h]
0x14001d37c  test    ebx, ebx
0x14001d37e  js      short loc_14001D389
0x14001d380  mov     rax, [rbp+3Fh+arg_20]
0x14001d384  mov     [rax], rdi
0x14001d387  jmp     short loc_14001D3AC
0x14001d389  cmp     rdi, r15
0x14001d38c  jz      short loc_14001D39B
0x14001d38e  test    rdi, rdi
0x14001d391  jz      short loc_14001D39B
0x14001d393  mov     rcx, rdi
0x14001d396  call    LuafvFreePool
0x14001d39b  cmp     ebx, 0C000000Fh
0x14001d3a1  cmovz   ebx, r13d
0x14001d3a5  mov     rax, [rbp+3Fh+arg_20]
0x14001d3a9  mov     [rax], r13
0x14001d3ac  mov     eax, ebx
0x14001d3ae  add     rsp, 0E8h
0x14001d3b5  pop     r15
0x14001d3b7  pop     r14
0x14001d3b9  pop     r13
0x14001d3bb  pop     r12
0x14001d3bd  pop     rdi
0x14001d3be  pop     rsi
0x14001d3bf  pop     rbx
0x14001d3c0  pop     rbp
0x14001d3c1  retn
```
