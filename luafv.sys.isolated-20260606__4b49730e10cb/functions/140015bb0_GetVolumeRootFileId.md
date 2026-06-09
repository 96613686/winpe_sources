# GetVolumeRootFileId

- ea: `0x140015bb0`
- end: `0x140015e1f`
- name: `GetVolumeRootFileId`
- size: `623`
- prototype: `NTSTATUS __fastcall(struct _UNICODE_STRING *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14001af8c`

## callees

- `0x140001874`
- `0x140015bb0`
- `0x140021250`
- `0x140024fd0`

## import_xrefs

- `ntoskrnl!ZwQueryInformationFile` at `0x140015da9`
- `ntoskrnl!ZwQueryInformationFile` at `0x140015da9`
- `ntoskrnl!IoCreateFileEx` at `0x140015ce3`
- `ntoskrnl!IoCreateFileEx` at `0x140015ce3`
- `ntoskrnl!ZwClose` at `0x140015df2`
- `ntoskrnl!ZwClose` at `0x140015df2`
- `ntoskrnl!ObfDereferenceObject` at `0x140015dcb`
- `ntoskrnl!ObfDereferenceObject` at `0x140015dcb`
- `FLTMGR!FltClose` at `0x140015de4`
- `FLTMGR!FltClose` at `0x140015de4`
- `FLTMGR!FltQueryInformationFile` at `0x140015d8b`
- `FLTMGR!FltQueryInformationFile` at `0x140015d8b`
- `FLTMGR!FltCreateFileEx2` at `0x140015d53`
- `FLTMGR!FltCreateFileEx2` at `0x140015d53`

## pseudocode

```c
NTSTATUS __fastcall GetVolumeRootFileId(struct _UNICODE_STRING *a1, _QWORD *a2)
{
  PWSTR Buffer; // rsi
  int v4; // edi
  unsigned __int64 v5; // rsi
  struct _UNICODE_STRING *v6; // rbx
  NTSTATUS result; // eax
  NTSTATUS v8; // eax
  NTSTATUS v9; // ebx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp+7h] BYREF
  PFILE_OBJECT FileObject; // [rsp+F0h] [rbp+67h] BYREF
  void *FileHandle; // [rsp+100h] [rbp+77h] BYREF
  __int64 FileInformation; // [rsp+108h] [rbp+7Fh] BYREF

  Buffer = a1[10].Buffer;
  FileHandle = 0;
  FileInformation = 0;
  v4 = (int)a1;
  FileObject = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  v5 = (unsigned __int64)Buffer & 0xFFFFFFFFFFFFFFF8uLL;
  if ( !v5 || *(struct _UNICODE_STRING **)(v5 + 32) != a1 )
    return -1073741811;
  v6 = a1 + 15;
  if ( a1[15].Buffer
    || (!(unsigned int)Feature_Bugfix_LuafvTableNode__private_IsEnabledDeviceUsageNoInline()
      ? (result = LuafvBuildTableNodeName(v4, 0, 0, 0, 1, (__int64)v6))
      : (result = LuafvBuildTableNodeName2(v4, 0, 0, 0, 1, 1, (__int64)v6)),
        result >= 0) )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = v6;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( LuafvDriverData )
    {
      result = FltCreateFileEx2(
                 LuafvDriverData,
                 *(PFLT_INSTANCE *)(v5 + 16),
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
    }
    else
    {
      FileObject = 0;
      result = IoCreateFileEx(
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
    }
    if ( result >= 0 )
    {
      if ( FileObject )
        v8 = FltQueryInformationFile(
               *(PFLT_INSTANCE *)(v5 + 16),
               FileObject,
               &FileInformation,
               8u,
               FileInternalInformation,
               0);
      else
        v8 = ZwQueryInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 8u, FileInternalInformation);
      v9 = v8;
      if ( v8 >= 0 )
        *a2 = FileInformation;
      if ( FileObject )
        ObfDereferenceObject(FileObject);
      if ( LuafvDriverData )
        FltClose(FileHandle);
      else
        ZwClose(FileHandle);
      return v9;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140015bb0  mov     [rsp-8+arg_8], rbx
0x140015bb5  push    rbp
0x140015bb6  push    rsi
0x140015bb7  push    rdi
0x140015bb8  push    r14
0x140015bba  push    r15
0x140015bbc  lea     rbp, [rsp-37h]
0x140015bc1  sub     rsp, 0C0h
0x140015bc8  mov     rsi, [rcx+0A8h]
0x140015bcf  xorps   xmm0, xmm0
0x140015bd2  xor     r15d, r15d
0x140015bd5  xor     eax, eax
0x140015bd7  mov     [rbp+57h+FileHandle], r15
0x140015bdb  mov     r14, rdx
0x140015bde  mov     [rbp+57h+FileInformation], r15
0x140015be2  mov     rdi, rcx
0x140015be5  mov     [rbp+57h+FileObject], r15
0x140015be9  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140015bed  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x140015bf1  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140015bf5  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140015bf9  and     rsi, 0FFFFFFFFFFFFFFF8h
0x140015bfd  jz      loc_140015E02
0x140015c03  cmp     [rsi+20h], rcx
0x140015c07  jnz     loc_140015E02
0x140015c0d  lea     rbx, [rcx+0F0h]
0x140015c14  cmp     [rcx+0F8h], r15
0x140015c1b  jnz     short loc_140015C5E
0x140015c1d  call    Feature_Bugfix_LuafvTableNode__private_IsEnabledDeviceUsageNoInline
0x140015c22  xor     r9d, r9d
0x140015c25  xor     r8d, r8d
0x140015c28  xor     edx, edx
0x140015c2a  mov     rcx, rdi
0x140015c2d  test    eax, eax
0x140015c2f  jz      short loc_140015C47
0x140015c31  mov     qword ptr [rsp+0E0h+ShareAccess], rbx
0x140015c36  mov     byte ptr [rsp+0E0h+FileAttributes], 1
0x140015c3b  mov     byte ptr [rsp+0E0h+AllocationSize], 1
0x140015c40  call    LuafvBuildTableNodeName2
0x140015c45  jmp     short loc_140015C56
0x140015c47  mov     qword ptr [rsp+0E0h+FileAttributes], rbx
0x140015c4c  mov     byte ptr [rsp+0E0h+AllocationSize], 1
0x140015c51  call    LuafvBuildTableNodeName
0x140015c56  test    eax, eax
0x140015c58  js      loc_140015E07
0x140015c5e  mov     rcx, cs:LuafvDriverData; Filter
0x140015c65  xorps   xmm0, xmm0
0x140015c68  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140015c6f  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x140015c73  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140015c7a  mov     [rbp+57h+ObjectAttributes.ObjectName], rbx
0x140015c7e  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140015c83  test    rcx, rcx
0x140015c86  jnz     short loc_140015CF1
0x140015c88  mov     [rsp+0E0h+DriverContext], r15; DriverContext
0x140015c8d  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140015c91  mov     [rsp+0E0h+Options], 800h; Options
0x140015c99  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140015c9d  mov     [rsp+0E0h+InternalParameters], r15; InternalParameters
0x140015ca2  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x140015ca6  mov     [rsp+0E0h+CreateFileType], r15d; CreateFileType
0x140015cab  mov     edx, 100001h; DesiredAccess
0x140015cb0  mov     [rsp+0E0h+EaLength], r15d; EaLength
0x140015cb5  mov     [rsp+0E0h+EaBuffer], r15; EaBuffer
0x140015cba  mov     [rsp+0E0h+CreateOptions], 21h ; '!'; CreateOptions
0x140015cc2  mov     [rsp+0E0h+Disposition], 1; Disposition
0x140015cca  mov     [rsp+0E0h+ShareAccess], 7; ShareAccess
0x140015cd2  mov     [rsp+0E0h+FileAttributes], 80h; FileAttributes
0x140015cda  mov     [rsp+0E0h+AllocationSize], r15; AllocationSize
0x140015cdf  mov     [rbp+57h+FileObject], r15
0x140015ce3  call    cs:__imp_IoCreateFileEx
0x140015cea  nop     dword ptr [rax+rax+00h]
0x140015cef  jmp     short loc_140015D5F
0x140015cf1  mov     rdx, [rsi+10h]; Instance
0x140015cf5  lea     rax, [rbp+57h+IoStatusBlock]
0x140015cf9  mov     [rsp+0E0h+var_68], r15; DriverContext
0x140015cfe  lea     r9, [rbp+57h+FileObject]; FileObject
0x140015d02  mov     dword ptr [rsp+0E0h+DriverContext], 800h; Flags
0x140015d0a  lea     r8, [rbp+57h+FileHandle]; FileHandle
0x140015d0e  mov     [rsp+0E0h+Options], r15d; EaLength
0x140015d13  mov     [rsp+0E0h+InternalParameters], r15; EaBuffer
0x140015d18  mov     [rsp+0E0h+CreateFileType], 21h ; '!'; CreateOptions
0x140015d20  mov     [rsp+0E0h+EaLength], 1; CreateDisposition
0x140015d28  mov     dword ptr [rsp+0E0h+EaBuffer], 7; ShareAccess
0x140015d30  mov     [rsp+0E0h+CreateOptions], 80h; FileAttributes
0x140015d38  mov     qword ptr [rsp+0E0h+Disposition], r15; AllocationSize
0x140015d3d  mov     qword ptr [rsp+0E0h+ShareAccess], rax; IoStatusBlock
0x140015d42  lea     rax, [rbp+57h+ObjectAttributes]
0x140015d46  mov     qword ptr [rsp+0E0h+FileAttributes], rax; ObjectAttributes
0x140015d4b  mov     dword ptr [rsp+0E0h+AllocationSize], 100001h; DesiredAccess
0x140015d53  call    cs:__imp_FltCreateFileEx2
0x140015d5a  nop     dword ptr [rax+rax+00h]
0x140015d5f  test    eax, eax
0x140015d61  js      loc_140015E07
0x140015d67  mov     rdx, [rbp+57h+FileObject]; FileObject
0x140015d6b  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x140015d6f  mov     r9d, 8; Length
0x140015d75  test    rdx, rdx
0x140015d78  jz      short loc_140015D99
0x140015d7a  mov     rcx, [rsi+10h]; Instance
0x140015d7e  mov     qword ptr [rsp+0E0h+FileAttributes], r15; LengthReturned
0x140015d83  mov     dword ptr [rsp+0E0h+AllocationSize], 6; FileInformationClass
0x140015d8b  call    cs:__imp_FltQueryInformationFile
0x140015d92  nop     dword ptr [rax+rax+00h]
0x140015d97  jmp     short loc_140015DB5
0x140015d99  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140015d9d  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140015da1  mov     dword ptr [rsp+0E0h+AllocationSize], 6; FileInformationClass
0x140015da9  call    cs:__imp_ZwQueryInformationFile
0x140015db0  nop     dword ptr [rax+rax+00h]
0x140015db5  mov     ebx, eax
0x140015db7  test    eax, eax
0x140015db9  js      short loc_140015DC2
0x140015dbb  mov     rax, [rbp+57h+FileInformation]
0x140015dbf  mov     [r14], rax
0x140015dc2  mov     rcx, [rbp+57h+FileObject]; Object
0x140015dc6  test    rcx, rcx
0x140015dc9  jz      short loc_140015DD7
0x140015dcb  call    cs:__imp_ObfDereferenceObject
0x140015dd2  nop     dword ptr [rax+rax+00h]
0x140015dd7  cmp     cs:LuafvDriverData, r15
0x140015dde  mov     rcx, [rbp+57h+FileHandle]; Handle
0x140015de2  jz      short loc_140015DF2
0x140015de4  call    cs:__imp_FltClose
0x140015deb  nop     dword ptr [rax+rax+00h]
0x140015df0  jmp     short loc_140015DFE
0x140015df2  call    cs:__imp_ZwClose
0x140015df9  nop     dword ptr [rax+rax+00h]
0x140015dfe  mov     eax, ebx
0x140015e00  jmp     short loc_140015E07
0x140015e02  mov     eax, 0C000000Dh
0x140015e07  mov     rbx, [rsp+0E0h+arg_8]
0x140015e0f  add     rsp, 0C0h
0x140015e16  pop     r15
0x140015e18  pop     r14
0x140015e1a  pop     rdi
0x140015e1b  pop     rsi
0x140015e1c  pop     rbp
0x140015e1d  retn
```
