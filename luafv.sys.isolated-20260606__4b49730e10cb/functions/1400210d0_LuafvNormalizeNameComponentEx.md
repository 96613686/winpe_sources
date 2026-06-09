# LuafvNormalizeNameComponentEx

- ea: `0x1400210d0`
- end: `0x14002123f`
- name: `LuafvNormalizeNameComponentEx`
- size: `367`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, PFILE_OBJECT FileObject@<rdx>, PUNICODE_STRING FileName, PVOID FileInformation, ULONG Length, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, reparse_path, broker_com_uri`

## callees

- `0x1400210d0`

## import_xrefs

- `ntoskrnl!IoGetTransactionParameterBlock` at `0x140021143`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x140021143`
- `ntoskrnl!ObfDereferenceObject` at `0x14002120b`
- `ntoskrnl!ObfDereferenceObject` at `0x14002120b`
- `FLTMGR!FltQueryDirectoryFile` at `0x1400211f9`
- `FLTMGR!FltQueryDirectoryFile` at `0x1400211f9`
- `FLTMGR!FltClose` at `0x14002121b`
- `FLTMGR!FltClose` at `0x14002121b`
- `FLTMGR!FltCreateFileEx2` at `0x1400211ba`
- `FLTMGR!FltCreateFileEx2` at `0x1400211ba`

## pseudocode

```c
NTSTATUS __fastcall LuafvNormalizeNameComponentEx(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        struct _UNICODE_STRING *a3,
        __int64 a4,
        PUNICODE_STRING FileName,
        PVOID FileInformation,
        ULONG Length,
        char a8)
{
  NTSTATUS result; // eax
  NTSTATUS DirectoryFile; // ebx
  void *FileHandle; // [rsp+80h] [rbp-41h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+88h] [rbp-39h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+98h] [rbp-29h] BYREF
  __int64 v14; // [rsp+B8h] [rbp-9h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C0h] [rbp-1h] BYREF
  PFILE_OBJECT FileObjecta; // [rsp+110h] [rbp+4Fh] BYREF

  FileHandle = 0;
  FileObjecta = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = (((a8 & 1) == 0) + 8) << 6;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  ObjectAttributes.RootDirectory = 0;
  memset(&DriverContext, 0, 24);
  DriverContext.Size = 40;
  IoStatusBlock = 0;
  ObjectAttributes.ObjectName = a3;
  v14 = 1;
  DriverContext.TxnParameters = IoGetTransactionParameterBlock(FileObject);
  result = FltCreateFileEx2(
             LuafvDriverData,
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
  if ( result >= 0 )
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
    return DirectoryFile;
  }
  return result;
}

```

## disassembly

```asm
0x1400210d0  mov     [rsp-8+arg_0], rbx
0x1400210d5  mov     [rsp-8+arg_8], rdi
0x1400210da  push    rbp
0x1400210db  lea     rbp, [rsp-2Fh]
0x1400210e0  sub     rsp, 0F0h
0x1400210e7  mov     eax, [rbp+2Fh+arg_38]
0x1400210ea  xor     edi, edi
0x1400210ec  not     eax
0x1400210ee  mov     [rbp+2Fh+FileHandle], rdi
0x1400210f2  and     eax, 1
0x1400210f5  mov     [rbp+2Fh+FileObject], rdi
0x1400210f9  add     eax, 8
0x1400210fc  mov     qword ptr [rbp+2Fh+var_30.Length], 30h ; '0'
0x140021104  shl     eax, 6
0x140021107  xorps   xmm1, xmm1
0x14002110a  xorps   xmm0, xmm0
0x14002110d  mov     [rbp+2Fh+var_30.Attributes], eax
0x140021110  mov     eax, 28h ; '('
0x140021115  mov     dword ptr [rbp+2Fh+var_30+1Ch], edi
0x140021118  mov     rbx, rcx
0x14002111b  mov     [rbp+2Fh+var_30.RootDirectory], rdi
0x14002111f  movups  xmmword ptr [rbp+2Fh+var_58.Size], xmm1
0x140021123  mov     rcx, rdx; FileObject
0x140021126  mov     [rbp+2Fh+var_58.Size], ax
0x14002112a  movups  xmmword ptr [rbp+2Fh+var_68], xmm0
0x14002112e  mov     [rbp+2Fh+var_30.ObjectName], r8
0x140021132  movdqu  xmmword ptr [rbp+2Fh+var_30.SecurityDescriptor], xmm0
0x140021137  mov     [rbp+2Fh+var_38], 1
0x14002113f  movups  xmmword ptr [rbp+2Fh+var_58.DeviceObjectHint], xmm1
0x140021143  call    cs:__imp_IoGetTransactionParameterBlock
0x14002114a  nop     dword ptr [rax+rax+00h]
0x14002114f  mov     rcx, cs:LuafvDriverData; Filter
0x140021156  lea     r9, [rbp+2Fh+FileObject]; FileObject
0x14002115a  mov     [rbp+2Fh+var_58.TxnParameters], rax
0x14002115e  lea     r8, [rbp+2Fh+FileHandle]; FileHandle
0x140021162  lea     rax, [rbp+2Fh+var_58]
0x140021166  mov     rdx, rbx; Instance
0x140021169  mov     [rsp+0F0h+DriverContext], rax; DriverContext
0x14002116e  lea     rax, [rbp+2Fh+var_68]
0x140021172  mov     [rsp+0F0h+Flags], 900h; Flags
0x14002117a  mov     [rsp+0F0h+EaLength], edi; EaLength
0x14002117e  mov     [rsp+0F0h+EaBuffer], rdi; EaBuffer
0x140021183  mov     [rsp+0F0h+CreateOptions], 4021h; CreateOptions
0x14002118b  mov     [rsp+0F0h+CreateDisposition], 1; CreateDisposition
0x140021193  mov     [rsp+0F0h+ShareAccess], 7; ShareAccess
0x14002119b  mov     [rsp+0F0h+FileAttributes], edi; FileAttributes
0x14002119f  mov     [rsp+0F0h+AllocationSize], rdi; AllocationSize
0x1400211a4  mov     [rsp+0F0h+IoStatusBlock], rax; IoStatusBlock
0x1400211a9  lea     rax, [rbp+2Fh+var_30]
0x1400211ad  mov     [rsp+0F0h+ObjectAttributes], rax; ObjectAttributes
0x1400211b2  mov     [rsp+0F0h+DesiredAccess], 100000h; DesiredAccess
0x1400211ba  call    cs:__imp_FltCreateFileEx2
0x1400211c1  nop     dword ptr [rax+rax+00h]
0x1400211c6  test    eax, eax
0x1400211c8  js      short loc_140021229
0x1400211ca  mov     rax, [rbp+2Fh+FileName]
0x1400211ce  mov     rcx, rbx; Instance
0x1400211d1  mov     r9d, [rbp+2Fh+Length]; Length
0x1400211d5  mov     r8, [rbp+2Fh+FileInformation]; FileInformation
0x1400211d9  mov     rdx, [rbp+2Fh+FileObject]; FileObject
0x1400211dd  mov     qword ptr [rsp+0F0h+FileAttributes], rdi; LengthReturned
0x1400211e2  mov     byte ptr [rsp+0F0h+AllocationSize], 1; RestartScan
0x1400211e7  mov     [rsp+0F0h+IoStatusBlock], rax; FileName
0x1400211ec  mov     byte ptr [rsp+0F0h+ObjectAttributes], 1; ReturnSingleEntry
0x1400211f1  mov     [rsp+0F0h+DesiredAccess], 0Ch; FileInformationClass
0x1400211f9  call    cs:__imp_FltQueryDirectoryFile
0x140021200  nop     dword ptr [rax+rax+00h]
0x140021205  mov     rcx, [rbp+2Fh+FileObject]; Object
0x140021209  mov     ebx, eax
0x14002120b  call    cs:__imp_ObfDereferenceObject
0x140021212  nop     dword ptr [rax+rax+00h]
0x140021217  mov     rcx, [rbp+2Fh+FileHandle]; FileHandle
0x14002121b  call    cs:__imp_FltClose
0x140021222  nop     dword ptr [rax+rax+00h]
0x140021227  mov     eax, ebx
0x140021229  lea     r11, [rsp+0F0h+var_s0]
0x140021231  mov     rbx, [r11+10h]
0x140021235  mov     rdi, [r11+18h]
0x140021239  mov     rsp, r11
0x14002123c  pop     rbp
0x14002123d  retn
```
