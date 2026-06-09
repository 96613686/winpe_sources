# LuafvGenerateFileName

- ea: `0x1400202d0`
- end: `0x1400203f7`
- name: `LuafvGenerateFileName`
- size: `295`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, PFLT_CALLBACK_DATA CallbackData, int, char *, PFLT_NAME_CONTROL NameCtrl)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400202d0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140020357`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140020357`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140020370`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140020370`
- `FLTMGR!FltCheckAndGrowNameControl` at `0x140020339`
- `FLTMGR!FltCheckAndGrowNameControl` at `0x140020339`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x1400203d8`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x1400203d8`
- `FLTMGR!FltGetFileNameInformation` at `0x140020311`
- `FLTMGR!FltGetFileNameInformation` at `0x140020311`

## pseudocode

```c
__int64 __fastcall LuafvGenerateFileName(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        PFLT_CALLBACK_DATA CallbackData,
        int a4,
        char *a5,
        PFLT_NAME_CONTROL NameCtrl)
{
  struct _FILE_OBJECT *v6; // rax
  FLT_FILE_NAME_OPTIONS v7; // r10d
  char v8; // si
  NTSTATUS FileNameInformationUnsafe; // eax
  NTSTATUS v10; // ebx
  PFLT_NAME_CONTROL v11; // rdi
  unsigned int *FsContext; // rdx
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+38h] [rbp+10h] BYREF

  FileNameInformation = 0;
  v6 = FileObject;
  if ( FileObject )
  {
    FsContext = (unsigned int *)FileObject->FsContext;
    if ( FsContext )
    {
      if ( *(_WORD *)FsContext == 30310 )
      {
        v6 = (struct _FILE_OBJECT *)*((_QWORD *)FsContext + 30);
        if ( !v6 )
          return FsContext[62];
        v8 = *((_BYTE *)FsContext + 252);
        v7 = a4 & 0xFEFFFFFF;
        goto LABEL_13;
      }
    }
  }
  v7 = a4 & 0xFEFFFFFF;
  v8 = 1;
  if ( !CallbackData )
  {
LABEL_13:
    FileNameInformationUnsafe = FltGetFileNameInformationUnsafe(v6, Instance, v7, &FileNameInformation);
    goto LABEL_4;
  }
  FileNameInformationUnsafe = FltGetFileNameInformation(CallbackData, v7, &FileNameInformation);
LABEL_4:
  v10 = FileNameInformationUnsafe;
  if ( FileNameInformationUnsafe >= 0 )
  {
    v11 = NameCtrl;
    v10 = FltCheckAndGrowNameControl(NameCtrl, FileNameInformation->Name.Length);
    if ( v10 >= 0 )
    {
      RtlCopyUnicodeString(&v11->Name, &FileNameInformation->Name);
      *a5 = v8;
    }
    FltReleaseFileNameInformation(FileNameInformation);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1400202d0  mov     [rsp+arg_10], rbx
0x1400202d5  push    rsi
0x1400202d6  sub     rsp, 20h
0x1400202da  mov     [rsp+28h+FileNameInformation], 0
0x1400202e3  mov     r10d, r9d
0x1400202e6  mov     r9, r8
0x1400202e9  mov     rax, rdx
0x1400202ec  test    rdx, rdx
0x1400202ef  jnz     loc_14002038F
0x1400202f5  btr     r10d, 18h
0x1400202fa  mov     sil, 1
0x1400202fd  test    r9, r9
0x140020300  jz      loc_1400203CA
0x140020306  lea     r8, [rsp+28h+FileNameInformation]; FileNameInformation
0x14002030b  mov     edx, r10d; NameOptions
0x14002030e  mov     rcx, r9; CallbackData
0x140020311  call    cs:__imp_FltGetFileNameInformation
0x140020318  nop     dword ptr [rax+rax+00h]
0x14002031d  mov     ebx, eax
0x14002031f  test    eax, eax
0x140020321  js      short loc_140020381
0x140020323  mov     rdx, [rsp+28h+FileNameInformation]
0x140020328  mov     [rsp+28h+arg_0], rdi
0x14002032d  mov     rdi, [rsp+28h+NameCtrl]
0x140020332  mov     rcx, rdi; NameCtrl
0x140020335  movzx   edx, word ptr [rdx+8]; NewSize
0x140020339  call    cs:__imp_FltCheckAndGrowNameControl
0x140020340  nop     dword ptr [rax+rax+00h]
0x140020345  mov     ebx, eax
0x140020347  test    eax, eax
0x140020349  js      short loc_14002036B
0x14002034b  mov     rdx, [rsp+28h+FileNameInformation]
0x140020350  mov     rcx, rdi; DestinationString
0x140020353  add     rdx, 8; SourceString
0x140020357  call    cs:__imp_RtlCopyUnicodeString
0x14002035e  nop     dword ptr [rax+rax+00h]
0x140020363  mov     rax, [rsp+28h+arg_20]
0x140020368  mov     [rax], sil
0x14002036b  mov     rcx, [rsp+28h+FileNameInformation]; FileNameInformation
0x140020370  call    cs:__imp_FltReleaseFileNameInformation
0x140020377  nop     dword ptr [rax+rax+00h]
0x14002037c  mov     rdi, [rsp+28h+arg_0]
0x140020381  mov     eax, ebx
0x140020383  mov     rbx, [rsp+28h+arg_10]
0x140020388  add     rsp, 20h
0x14002038c  pop     rsi
0x14002038d  retn
0x14002038f  mov     rdx, [rdx+18h]
0x140020393  test    rdx, rdx
0x140020396  jz      loc_1400202F5
0x14002039c  mov     r8d, 7666h
0x1400203a2  cmp     [rdx], r8w
0x1400203a6  jnz     loc_1400202F5
0x1400203ac  mov     rax, [rdx+0F0h]
0x1400203b3  test    rax, rax
0x1400203b6  jnz     short loc_1400203E9
0x1400203b8  mov     eax, [rdx+0F8h]
0x1400203be  mov     rbx, [rsp+28h+arg_10]
0x1400203c3  add     rsp, 20h
0x1400203c7  pop     rsi
0x1400203c8  retn
0x1400203ca  mov     rdx, rcx; Instance
0x1400203cd  lea     r9, [rsp+28h+FileNameInformation]; FileNameInformation
0x1400203d2  mov     rcx, rax; FileObject
0x1400203d5  mov     r8d, r10d; NameOptions
0x1400203d8  call    cs:__imp_FltGetFileNameInformationUnsafe
0x1400203df  nop     dword ptr [rax+rax+00h]
0x1400203e4  jmp     loc_14002031D
0x1400203e9  movzx   esi, byte ptr [rdx+0FCh]
0x1400203f0  btr     r10d, 18h
0x1400203f5  jmp     short loc_1400203CA
```
