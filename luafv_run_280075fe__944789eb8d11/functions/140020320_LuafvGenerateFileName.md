# LuafvGenerateFileName

- ea: `0x140020320`
- end: `0x140020447`
- name: `LuafvGenerateFileName`
- size: `295`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, PFILE_OBJECT FileObject@<rdx>, PFLT_CALLBACK_DATA CallbackData@<r8>, __int64, PFLT_NAME_CONTROL NameCtrl)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140020320`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1400203a7`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400203a7`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400203c0`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400203c0`
- `FLTMGR!FltCheckAndGrowNameControl` at `0x140020389`
- `FLTMGR!FltCheckAndGrowNameControl` at `0x140020389`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x140020428`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x140020428`
- `FLTMGR!FltGetFileNameInformation` at `0x140020361`
- `FLTMGR!FltGetFileNameInformation` at `0x140020361`

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
0x140020320  mov     [rsp+arg_10], rbx
0x140020325  push    rsi
0x140020326  sub     rsp, 20h
0x14002032a  mov     [rsp+28h+FileNameInformation], 0
0x140020333  mov     r10d, r9d
0x140020336  mov     r9, r8
0x140020339  mov     rax, rdx
0x14002033c  test    rdx, rdx
0x14002033f  jnz     loc_1400203DF
0x140020345  btr     r10d, 18h
0x14002034a  mov     sil, 1
0x14002034d  test    r9, r9
0x140020350  jz      loc_14002041A
0x140020356  lea     r8, [rsp+28h+FileNameInformation]; FileNameInformation
0x14002035b  mov     edx, r10d; NameOptions
0x14002035e  mov     rcx, r9; CallbackData
0x140020361  call    cs:__imp_FltGetFileNameInformation
0x140020368  nop     dword ptr [rax+rax+00h]
0x14002036d  mov     ebx, eax
0x14002036f  test    eax, eax
0x140020371  js      short loc_1400203D1
0x140020373  mov     rdx, [rsp+28h+FileNameInformation]
0x140020378  mov     [rsp+28h+arg_0], rdi
0x14002037d  mov     rdi, [rsp+28h+NameCtrl]
0x140020382  mov     rcx, rdi; NameCtrl
0x140020385  movzx   edx, word ptr [rdx+8]; NewSize
0x140020389  call    cs:__imp_FltCheckAndGrowNameControl
0x140020390  nop     dword ptr [rax+rax+00h]
0x140020395  mov     ebx, eax
0x140020397  test    eax, eax
0x140020399  js      short loc_1400203BB
0x14002039b  mov     rdx, [rsp+28h+FileNameInformation]
0x1400203a0  mov     rcx, rdi; DestinationString
0x1400203a3  add     rdx, 8; SourceString
0x1400203a7  call    cs:__imp_RtlCopyUnicodeString
0x1400203ae  nop     dword ptr [rax+rax+00h]
0x1400203b3  mov     rax, [rsp+28h+arg_20]
0x1400203b8  mov     [rax], sil
0x1400203bb  mov     rcx, [rsp+28h+FileNameInformation]; FileNameInformation
0x1400203c0  call    cs:__imp_FltReleaseFileNameInformation
0x1400203c7  nop     dword ptr [rax+rax+00h]
0x1400203cc  mov     rdi, [rsp+28h+arg_0]
0x1400203d1  mov     eax, ebx
0x1400203d3  mov     rbx, [rsp+28h+arg_10]
0x1400203d8  add     rsp, 20h
0x1400203dc  pop     rsi
0x1400203dd  retn
0x1400203df  mov     rdx, [rdx+18h]
0x1400203e3  test    rdx, rdx
0x1400203e6  jz      loc_140020345
0x1400203ec  mov     r8d, 7666h
0x1400203f2  cmp     [rdx], r8w
0x1400203f6  jnz     loc_140020345
0x1400203fc  mov     rax, [rdx+0F0h]
0x140020403  test    rax, rax
0x140020406  jnz     short loc_140020439
0x140020408  mov     eax, [rdx+0F8h]
0x14002040e  mov     rbx, [rsp+28h+arg_10]
0x140020413  add     rsp, 20h
0x140020417  pop     rsi
0x140020418  retn
0x14002041a  mov     rdx, rcx; Instance
0x14002041d  lea     r9, [rsp+28h+FileNameInformation]; FileNameInformation
0x140020422  mov     rcx, rax; FileObject
0x140020425  mov     r8d, r10d; NameOptions
0x140020428  call    cs:__imp_FltGetFileNameInformationUnsafe
0x14002042f  nop     dword ptr [rax+rax+00h]
0x140020434  jmp     loc_14002036D
0x140020439  movzx   esi, byte ptr [rdx+0FCh]
0x140020440  btr     r10d, 18h
0x140020445  jmp     short loc_14002041A
```
