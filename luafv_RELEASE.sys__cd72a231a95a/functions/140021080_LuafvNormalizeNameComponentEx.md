# LuafvNormalizeNameComponentEx

- ea: `0x140021080`
- end: `0x1400211ef`
- name: `LuafvNormalizeNameComponentEx`
- size: `367`
- prototype: `NTSTATUS __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, struct _UNICODE_STRING *, __int64, PUNICODE_STRING FileName, PVOID FileInformation, ULONG Length, char)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, reparse_path, broker_com_uri`

## callees

- `0x140021080`

## import_xrefs

- `ntoskrnl!IoGetTransactionParameterBlock` at `0x1400210f3`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x1400210f3`
- `ntoskrnl!ObfDereferenceObject` at `0x1400211bb`
- `ntoskrnl!ObfDereferenceObject` at `0x1400211bb`
- `FLTMGR!FltQueryDirectoryFile` at `0x1400211a9`
- `FLTMGR!FltQueryDirectoryFile` at `0x1400211a9`
- `FLTMGR!FltClose` at `0x1400211cb`
- `FLTMGR!FltClose` at `0x1400211cb`
- `FLTMGR!FltCreateFileEx2` at `0x14002116a`
- `FLTMGR!FltCreateFileEx2` at `0x14002116a`

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
0x140021080  mov     [rsp-8+arg_0], rbx
0x140021085  mov     [rsp-8+arg_8], rdi
0x14002108a  push    rbp
0x14002108b  lea     rbp, [rsp-2Fh]
0x140021090  sub     rsp, 0F0h
0x140021097  mov     eax, [rbp+2Fh+arg_38]
0x14002109a  xor     edi, edi
0x14002109c  not     eax
0x14002109e  mov     [rbp+2Fh+FileHandle], rdi
0x1400210a2  and     eax, 1
0x1400210a5  mov     [rbp+2Fh+FileObject], rdi
0x1400210a9  add     eax, 8
0x1400210ac  mov     qword ptr [rbp+2Fh+var_30.Length], 30h ; '0'
0x1400210b4  shl     eax, 6
0x1400210b7  xorps   xmm1, xmm1
0x1400210ba  xorps   xmm0, xmm0
0x1400210bd  mov     [rbp+2Fh+var_30.Attributes], eax
0x1400210c0  mov     eax, 28h ; '('
0x1400210c5  mov     dword ptr [rbp+2Fh+var_30+1Ch], edi
0x1400210c8  mov     rbx, rcx
0x1400210cb  mov     [rbp+2Fh+var_30.RootDirectory], rdi
0x1400210cf  movups  xmmword ptr [rbp+2Fh+var_58.Size], xmm1
0x1400210d3  mov     rcx, rdx; FileObject
0x1400210d6  mov     [rbp+2Fh+var_58.Size], ax
0x1400210da  movups  xmmword ptr [rbp+2Fh+var_68], xmm0
0x1400210de  mov     [rbp+2Fh+var_30.ObjectName], r8
0x1400210e2  movdqu  xmmword ptr [rbp+2Fh+var_30.SecurityDescriptor], xmm0
0x1400210e7  mov     [rbp+2Fh+var_38], 1
0x1400210ef  movups  xmmword ptr [rbp+2Fh+var_58.DeviceObjectHint], xmm1
0x1400210f3  call    cs:__imp_IoGetTransactionParameterBlock
0x1400210fa  nop     dword ptr [rax+rax+00h]
0x1400210ff  mov     rcx, cs:LuafvDriverData; Filter
0x140021106  lea     r9, [rbp+2Fh+FileObject]; FileObject
0x14002110a  mov     [rbp+2Fh+var_58.TxnParameters], rax
0x14002110e  lea     r8, [rbp+2Fh+FileHandle]; FileHandle
0x140021112  lea     rax, [rbp+2Fh+var_58]
0x140021116  mov     rdx, rbx; Instance
0x140021119  mov     [rsp+0F0h+DriverContext], rax; DriverContext
0x14002111e  lea     rax, [rbp+2Fh+var_68]
0x140021122  mov     [rsp+0F0h+Flags], 900h; Flags
0x14002112a  mov     [rsp+0F0h+EaLength], edi; EaLength
0x14002112e  mov     [rsp+0F0h+EaBuffer], rdi; EaBuffer
0x140021133  mov     [rsp+0F0h+CreateOptions], 4021h; CreateOptions
0x14002113b  mov     [rsp+0F0h+CreateDisposition], 1; CreateDisposition
0x140021143  mov     [rsp+0F0h+ShareAccess], 7; ShareAccess
0x14002114b  mov     [rsp+0F0h+FileAttributes], edi; FileAttributes
0x14002114f  mov     [rsp+0F0h+AllocationSize], rdi; AllocationSize
0x140021154  mov     [rsp+0F0h+IoStatusBlock], rax; IoStatusBlock
0x140021159  lea     rax, [rbp+2Fh+var_30]
0x14002115d  mov     [rsp+0F0h+ObjectAttributes], rax; ObjectAttributes
0x140021162  mov     [rsp+0F0h+DesiredAccess], 100000h; DesiredAccess
0x14002116a  call    cs:__imp_FltCreateFileEx2
0x140021171  nop     dword ptr [rax+rax+00h]
0x140021176  test    eax, eax
0x140021178  js      short loc_1400211D9
0x14002117a  mov     rax, [rbp+2Fh+FileName]
0x14002117e  mov     rcx, rbx; Instance
0x140021181  mov     r9d, [rbp+2Fh+Length]; Length
0x140021185  mov     r8, [rbp+2Fh+FileInformation]; FileInformation
0x140021189  mov     rdx, [rbp+2Fh+FileObject]; FileObject
0x14002118d  mov     qword ptr [rsp+0F0h+FileAttributes], rdi; LengthReturned
0x140021192  mov     byte ptr [rsp+0F0h+AllocationSize], 1; RestartScan
0x140021197  mov     [rsp+0F0h+IoStatusBlock], rax; FileName
0x14002119c  mov     byte ptr [rsp+0F0h+ObjectAttributes], 1; ReturnSingleEntry
0x1400211a1  mov     [rsp+0F0h+DesiredAccess], 0Ch; FileInformationClass
0x1400211a9  call    cs:__imp_FltQueryDirectoryFile
0x1400211b0  nop     dword ptr [rax+rax+00h]
0x1400211b5  mov     rcx, [rbp+2Fh+FileObject]; Object
0x1400211b9  mov     ebx, eax
0x1400211bb  call    cs:__imp_ObfDereferenceObject
0x1400211c2  nop     dword ptr [rax+rax+00h]
0x1400211c7  mov     rcx, [rbp+2Fh+FileHandle]; FileHandle
0x1400211cb  call    cs:__imp_FltClose
0x1400211d2  nop     dword ptr [rax+rax+00h]
0x1400211d7  mov     eax, ebx
0x1400211d9  lea     r11, [rsp+0F0h+var_s0]
0x1400211e1  mov     rbx, [r11+10h]
0x1400211e5  mov     rdi, [r11+18h]
0x1400211e9  mov     rsp, r11
0x1400211ec  pop     rbp
0x1400211ed  retn
```
