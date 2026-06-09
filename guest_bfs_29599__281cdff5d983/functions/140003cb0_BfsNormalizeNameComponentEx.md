# BfsNormalizeNameComponentEx

- ea: `0x140003cb0`
- end: `0x140003e3d`
- name: `BfsNormalizeNameComponentEx`
- size: `397`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, PFILE_OBJECT FileObject@<rdx>, PUNICODE_STRING FileName, PVOID FileInformation, ULONG Length, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, reparse_path, broker_com_uri`

## callees

- `0x140003cb0`

## import_xrefs

- `ntoskrnl!IoGetTransactionParameterBlock` at `0x140003d2b`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x140003d2b`
- `ntoskrnl!ObfDereferenceObject` at `0x140003e09`
- `ntoskrnl!ObfDereferenceObject` at `0x140003e09`
- `FLTMGR!FltClose` at `0x140003e19`
- `FLTMGR!FltClose` at `0x140003e19`
- `FLTMGR!FltQueryDirectoryFile` at `0x140003df7`
- `FLTMGR!FltQueryDirectoryFile` at `0x140003df7`
- `FLTMGR!FltCreateFileEx2` at `0x140003db2`
- `FLTMGR!FltCreateFileEx2` at `0x140003db2`

## pseudocode

```c
__int64 __fastcall BfsNormalizeNameComponentEx(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        struct _UNICODE_STRING *a3,
        __int64 a4,
        PUNICODE_STRING FileName,
        PVOID FileInformation,
        ULONG Length,
        char a8)
{
  NTSTATUS DirectoryFile; // ebx
  void *FileHandle; // [rsp+80h] [rbp-41h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+88h] [rbp-39h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+98h] [rbp-29h] BYREF
  __int64 v14; // [rsp+B8h] [rbp-9h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C0h] [rbp-1h] BYREF
  PFILE_OBJECT FileObjecta; // [rsp+110h] [rbp+4Fh] BYREF

  FileHandle = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  ObjectAttributes.RootDirectory = 0;
  FileObjecta = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = a3;
  ObjectAttributes.Attributes = (((a8 & 1) == 0) + 8) << 6;
  memset(&DriverContext, 0, 24);
  DriverContext.Size = 40;
  IoStatusBlock = 0;
  v14 = 1;
  DriverContext.TxnParameters = IoGetTransactionParameterBlock(FileObject);
  DirectoryFile = FltCreateFileEx2(
                    gBfsFilterHandle,
                    Instance,
                    &FileHandle,
                    &FileObjecta,
                    0x100000u,
                    &ObjectAttributes,
                    &IoStatusBlock,
                    0,
                    0,
                    7u,
                    1u,
                    0x4021u,
                    0,
                    0,
                    0x900u,
                    &DriverContext);
  if ( DirectoryFile >= 0 )
  {
    DirectoryFile = FltQueryDirectoryFile(
                      Instance,
                      FileObjecta,
                      FileInformation,
                      Length,
                      FileNamesInformation,
                      1u,
                      FileName,
                      1u,
                      0);
    ObfDereferenceObject(FileObjecta);
    FltClose(FileHandle);
  }
  return (unsigned int)DirectoryFile;
}

```

## disassembly

```asm
0x140003cb0  mov     [rsp-8+arg_0], rbx
0x140003cb5  mov     [rsp-8+arg_8], rdi
0x140003cba  push    rbp
0x140003cbb  lea     rbp, [rsp-2Fh]
0x140003cc0  sub     rsp, 0F0h
0x140003cc7  xor     eax, eax
0x140003cc9  mov     [rbp+2Fh+FileHandle], 0
0x140003cd1  mov     dword ptr [rbp+2Fh+var_30+1Ch], eax
0x140003cd4  xorps   xmm1, xmm1
0x140003cd7  mov     [rbp+2Fh+var_30.RootDirectory], rax
0x140003cdb  xorps   xmm0, xmm0
0x140003cde  mov     eax, [rbp+2Fh+arg_38]
0x140003ce1  mov     rdi, rcx
0x140003ce4  not     eax
0x140003ce6  mov     [rbp+2Fh+FileObject], 0
0x140003cee  and     eax, 1
0x140003cf1  mov     qword ptr [rbp+2Fh+var_30.Length], 30h ; '0'
0x140003cf9  add     eax, 8
0x140003cfc  mov     [rbp+2Fh+var_30.ObjectName], r8
0x140003d00  shl     eax, 6
0x140003d03  mov     rcx, rdx; FileObject
0x140003d06  mov     [rbp+2Fh+var_30.Attributes], eax
0x140003d09  mov     eax, 28h ; '('
0x140003d0e  movups  xmmword ptr [rbp+2Fh+var_58.Size], xmm1
0x140003d12  mov     [rbp+2Fh+var_58.Size], ax
0x140003d16  movups  xmmword ptr [rbp+2Fh+var_68], xmm0
0x140003d1a  mov     [rbp+2Fh+var_38], 1
0x140003d22  movdqu  xmmword ptr [rbp+2Fh+var_30.SecurityDescriptor], xmm0
0x140003d27  movups  xmmword ptr [rbp+2Fh+var_58.DeviceObjectHint], xmm1
0x140003d2b  call    cs:__imp_IoGetTransactionParameterBlock
0x140003d32  nop     dword ptr [rax+rax+00h]
0x140003d37  mov     rcx, cs:gBfsFilterHandle; Filter
0x140003d3e  lea     r9, [rbp+2Fh+FileObject]; FileObject
0x140003d42  mov     [rbp+2Fh+var_58.TxnParameters], rax
0x140003d46  lea     r8, [rbp+2Fh+FileHandle]; FileHandle
0x140003d4a  lea     rax, [rbp+2Fh+var_58]
0x140003d4e  mov     rdx, rdi; Instance
0x140003d51  mov     [rsp+0F0h+DriverContext], rax; DriverContext
0x140003d56  lea     rax, [rbp+2Fh+var_68]
0x140003d5a  mov     [rsp+0F0h+Flags], 900h; Flags
0x140003d62  mov     [rsp+0F0h+EaLength], 0; EaLength
0x140003d6a  mov     [rsp+0F0h+EaBuffer], 0; EaBuffer
0x140003d73  mov     [rsp+0F0h+CreateOptions], 4021h; CreateOptions
0x140003d7b  mov     [rsp+0F0h+CreateDisposition], 1; CreateDisposition
0x140003d83  mov     [rsp+0F0h+ShareAccess], 7; ShareAccess
0x140003d8b  mov     [rsp+0F0h+FileAttributes], 0; FileAttributes
0x140003d93  mov     [rsp+0F0h+AllocationSize], 0; AllocationSize
0x140003d9c  mov     [rsp+0F0h+IoStatusBlock], rax; IoStatusBlock
0x140003da1  lea     rax, [rbp+2Fh+var_30]
0x140003da5  mov     [rsp+0F0h+ObjectAttributes], rax; ObjectAttributes
0x140003daa  mov     [rsp+0F0h+DesiredAccess], 100000h; DesiredAccess
0x140003db2  call    cs:__imp_FltCreateFileEx2
0x140003db9  nop     dword ptr [rax+rax+00h]
0x140003dbe  mov     ebx, eax
0x140003dc0  test    eax, eax
0x140003dc2  js      short loc_140003E25
0x140003dc4  mov     rax, [rbp+2Fh+FileName]
0x140003dc8  mov     rcx, rdi; Instance
0x140003dcb  mov     r9d, [rbp+2Fh+Length]; Length
0x140003dcf  mov     r8, [rbp+2Fh+FileInformation]; FileInformation
0x140003dd3  mov     rdx, [rbp+2Fh+FileObject]; FileObject
0x140003dd7  mov     qword ptr [rsp+0F0h+FileAttributes], 0; LengthReturned
0x140003de0  mov     byte ptr [rsp+0F0h+AllocationSize], 1; RestartScan
0x140003de5  mov     [rsp+0F0h+IoStatusBlock], rax; FileName
0x140003dea  mov     byte ptr [rsp+0F0h+ObjectAttributes], 1; ReturnSingleEntry
0x140003def  mov     [rsp+0F0h+DesiredAccess], 0Ch; FileInformationClass
0x140003df7  call    cs:__imp_FltQueryDirectoryFile
0x140003dfe  nop     dword ptr [rax+rax+00h]
0x140003e03  mov     rcx, [rbp+2Fh+FileObject]; Object
0x140003e07  mov     ebx, eax
0x140003e09  call    cs:__imp_ObfDereferenceObject
0x140003e10  nop     dword ptr [rax+rax+00h]
0x140003e15  mov     rcx, [rbp+2Fh+FileHandle]; FileHandle
0x140003e19  call    cs:__imp_FltClose
0x140003e20  nop     dword ptr [rax+rax+00h]
0x140003e25  lea     r11, [rsp+0F0h+var_s0]
0x140003e2d  mov     eax, ebx
0x140003e2f  mov     rbx, [r11+10h]
0x140003e33  mov     rdi, [r11+18h]
0x140003e37  mov     rsp, r11
0x140003e3a  pop     rbp
0x140003e3b  retn
```
