# LuafvQueryShortNameFromGlobal

- ea: `0x140014808`
- end: `0x140014967`
- name: `LuafvQueryShortNameFromGlobal`
- size: `351`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400201a0`

## callees

- `0x140014808`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140014903`
- `ntoskrnl!ObfDereferenceObject` at `0x140014903`
- `FLTMGR!FltClose` at `0x140014913`
- `FLTMGR!FltClose` at `0x140014913`
- `FLTMGR!FltQueryInformationFile` at `0x1400148f1`
- `FLTMGR!FltQueryInformationFile` at `0x1400148f1`
- `FLTMGR!FltCreateFileEx2` at `0x1400148bd`
- `FLTMGR!FltCreateFileEx2` at `0x1400148bd`

## pseudocode

```c
__int64 __fastcall LuafvQueryShortNameFromGlobal(PFLT_INSTANCE Instance, struct _UNICODE_STRING *a2, __int64 a3)
{
  unsigned int v4; // esi
  NTSTATUS v6; // eax
  NTSTATUS v7; // ebx
  __int64 v8; // rax
  void *FileHandle; // [rsp+80h] [rbp-9h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+88h] [rbp-1h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp+Fh] BYREF
  ULONG LengthReturned; // [rsp+F8h] [rbp+6Fh] BYREF
  PFILE_OBJECT FileObject; // [rsp+108h] [rbp+7Fh] BYREF

  ObjectAttributes.ObjectName = a2;
  v4 = 4;
  LengthReturned = 0;
  FileObject = 0;
  ObjectAttributes.RootDirectory = 0;
  FileHandle = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  IoStatusBlock = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v6 = FltCreateFileEx2(
         LuafvDriverData,
         Instance,
         &FileHandle,
         &FileObject,
         0x100000u,
         &ObjectAttributes,
         &IoStatusBlock,
         0,
         0,
         7u,
         1u,
         0x20u,
         0,
         0,
         0x901u,
         0);
  if ( v6 < 0 )
  {
    if ( v6 == -1073741772 || v6 == -1073741766 )
      return 1;
    else
      *(struct _IO_STATUS_BLOCK *)(a3 + 24) = IoStatusBlock;
  }
  else
  {
    v7 = FltQueryInformationFile(
           Instance,
           FileObject,
           *(PVOID *)(*(_QWORD *)(a3 + 16) + 40LL),
           *(_DWORD *)(*(_QWORD *)(a3 + 16) + 24LL),
           FileAlternateNameInformation,
           &LengthReturned);
    ObfDereferenceObject(FileObject);
    FltClose(FileHandle);
    *(_DWORD *)(a3 + 24) = v7;
    if ( v7 < 0 )
      v8 = 0;
    else
      v8 = LengthReturned;
    *(_QWORD *)(a3 + 32) = v8;
  }
  return v4;
}

```

## disassembly

```asm
0x140014808  mov     [rsp-8+arg_0], rbx
0x14001480d  push    rbp
0x14001480e  push    rsi
0x14001480f  push    rdi
0x140014810  lea     rbp, [rsp-47h]
0x140014815  sub     rsp, 0D0h
0x14001481c  xor     eax, eax
0x14001481e  mov     [rbp+57h+var_48.ObjectName], rdx
0x140014822  mov     [rsp+0E0h+DriverContext], rax; DriverContext
0x140014827  lea     r9, [rbp+57h+FileObject]; FileObject
0x14001482b  mov     [rsp+0E0h+Flags], 901h; Flags
0x140014833  xorps   xmm0, xmm0
0x140014836  mov     [rsp+0E0h+EaLength], eax; EaLength
0x14001483a  mov     rdi, r8
0x14001483d  mov     [rsp+0E0h+EaBuffer], rax; EaBuffer
0x140014842  lea     esi, [rax+4]
0x140014845  mov     [rsp+0E0h+CreateOptions], 20h ; ' '; CreateOptions
0x14001484d  lea     r8, [rbp+57h+FileHandle]; FileHandle
0x140014851  mov     [rsp+0E0h+CreateDisposition], 1; CreateDisposition
0x140014859  mov     rbx, rcx
0x14001485c  mov     [rsp+0E0h+ShareAccess], 7; ShareAccess
0x140014864  mov     rdx, rcx; Instance
0x140014867  mov     rcx, cs:LuafvDriverData; Filter
0x14001486e  mov     [rsp+0E0h+FileAttributes], eax; FileAttributes
0x140014872  mov     [rsp+0E0h+AllocationSize], rax; AllocationSize
0x140014877  mov     [rbp+57h+LengthReturned], eax
0x14001487a  mov     [rbp+57h+FileObject], rax
0x14001487e  mov     [rbp+57h+var_48.RootDirectory], rax
0x140014882  lea     rax, [rbp+57h+var_58]
0x140014886  mov     [rsp+0E0h+IoStatusBlock], rax; IoStatusBlock
0x14001488b  lea     rax, [rbp+57h+var_48]
0x14001488f  mov     [rsp+0E0h+ObjectAttributes], rax; ObjectAttributes
0x140014894  mov     [rsp+0E0h+DesiredAccess], 100000h; DesiredAccess
0x14001489c  mov     [rbp+57h+FileHandle], 0
0x1400148a4  mov     qword ptr [rbp+57h+var_48.Length], 30h ; '0'
0x1400148ac  mov     qword ptr [rbp+57h+var_48.Attributes], 240h
0x1400148b4  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x1400148b8  movdqu  xmmword ptr [rbp+57h+var_48.SecurityDescriptor], xmm0
0x1400148bd  call    cs:__imp_FltCreateFileEx2
0x1400148c4  nop     dword ptr [rax+rax+00h]
0x1400148c9  test    eax, eax
0x1400148cb  js      short loc_140014933
0x1400148cd  mov     r8, [rdi+10h]
0x1400148d1  lea     rax, [rbp+57h+LengthReturned]
0x1400148d5  mov     rdx, [rbp+57h+FileObject]; FileObject
0x1400148d9  mov     rcx, rbx; Instance
0x1400148dc  mov     [rsp+0E0h+ObjectAttributes], rax; LengthReturned
0x1400148e1  mov     [rsp+0E0h+DesiredAccess], 15h; FileInformationClass
0x1400148e9  mov     r9d, [r8+18h]; Length
0x1400148ed  mov     r8, [r8+28h]; FileInformation
0x1400148f1  call    cs:__imp_FltQueryInformationFile
0x1400148f8  nop     dword ptr [rax+rax+00h]
0x1400148fd  mov     rcx, [rbp+57h+FileObject]; Object
0x140014901  mov     ebx, eax
0x140014903  call    cs:__imp_ObfDereferenceObject
0x14001490a  nop     dword ptr [rax+rax+00h]
0x14001490f  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140014913  call    cs:__imp_FltClose
0x14001491a  nop     dword ptr [rax+rax+00h]
0x14001491f  mov     [rdi+18h], ebx
0x140014922  test    ebx, ebx
0x140014924  js      short loc_14001492B
0x140014926  mov     eax, [rbp+57h+LengthReturned]
0x140014929  jmp     short loc_14001492D
0x14001492b  xor     eax, eax
0x14001492d  mov     [rdi+20h], rax
0x140014931  jmp     short loc_140014951
0x140014933  cmp     eax, 0C0000034h
0x140014938  jz      short loc_14001494C
0x14001493a  cmp     eax, 0C000003Ah
0x14001493f  jz      short loc_14001494C
0x140014941  movups  xmm0, xmmword ptr [rbp+57h+var_58]
0x140014945  movdqu  xmmword ptr [rdi+18h], xmm0
0x14001494a  jmp     short loc_140014951
0x14001494c  mov     esi, 1
0x140014951  mov     rbx, [rsp+0E0h+arg_0]
0x140014959  mov     eax, esi
0x14001495b  add     rsp, 0D0h
0x140014962  pop     rdi
0x140014963  pop     rsi
0x140014964  pop     rbp
0x140014965  retn
```
