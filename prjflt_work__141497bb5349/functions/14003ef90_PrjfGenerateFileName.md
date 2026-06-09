# PrjfGenerateFileName

- ea: `0x14003ef90`
- end: `0x14003f06b`
- name: `PrjfGenerateFileName`
- size: `219`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, PFLT_CALLBACK_DATA CallbackData, int, _BYTE *, PFLT_NAME_CONTROL NameCtrl)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000b1d0`
- `0x14003ef90`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14003f02e`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14003f02e`
- `FLTMGR!FltCheckAndGrowNameControl` at `0x14003f00e`
- `FLTMGR!FltCheckAndGrowNameControl` at `0x14003f00e`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14003efd6`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14003efd6`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003f04c`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003f04c`
- `FLTMGR!FltGetFileNameInformation` at `0x14003efee`
- `FLTMGR!FltGetFileNameInformation` at `0x14003efee`

## pseudocode

```c
__int64 __fastcall PrjfGenerateFileName(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        PFLT_CALLBACK_DATA CallbackData,
        int a4,
        _BYTE *a5,
        PFLT_NAME_CONTROL NameCtrl)
{
  FLT_FILE_NAME_OPTIONS v6; // ebx
  NTSTATUS FileNameInformationUnsafe; // eax
  NTSTATUS v10; // ebx
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+40h] [rbp+18h] BYREF

  FileNameInformation = 0;
  v6 = a4 & 0xFEFFFFFF;
  if ( CallbackData )
  {
    FileNameInformationUnsafe = FltGetFileNameInformation(CallbackData, v6, &FileNameInformation);
  }
  else
  {
    if ( !FileObject->FsContext )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(Instance, FileObject);
    FileNameInformationUnsafe = FltGetFileNameInformationUnsafe(FileObject, Instance, v6, &FileNameInformation);
  }
  v10 = FileNameInformationUnsafe;
  if ( FileNameInformationUnsafe >= 0 )
  {
    v10 = FltCheckAndGrowNameControl(NameCtrl, FileNameInformation->Name.Length);
    if ( v10 >= 0 )
    {
      RtlCopyUnicodeString(&NameCtrl->Name, &FileNameInformation->Name);
      *a5 = 0;
    }
  }
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14003ef90  mov     [rsp+arg_0], rbx
0x14003ef95  mov     [rsp+arg_8], rsi
0x14003ef9a  push    rdi
0x14003ef9b  sub     rsp, 20h
0x14003ef9f  mov     ebx, r9d
0x14003efa2  mov     [rsp+28h+FileNameInformation], 0
0x14003efab  btr     ebx, 18h
0x14003efaf  mov     rax, r8
0x14003efb2  mov     rdi, rdx
0x14003efb5  mov     rsi, rcx
0x14003efb8  test    r8, r8
0x14003efbb  jnz     short loc_14003EFE4
0x14003efbd  cmp     [rdx+18h], r8
0x14003efc1  jnz     short loc_14003EFC8
0x14003efc3  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14003efc8  lea     r9, [rsp+28h+FileNameInformation]; FileNameInformation
0x14003efcd  mov     r8d, ebx; NameOptions
0x14003efd0  mov     rdx, rsi; Instance
0x14003efd3  mov     rcx, rdi; FileObject
0x14003efd6  call    cs:__imp_FltGetFileNameInformationUnsafe
0x14003efdd  nop     dword ptr [rax+rax+00h]
0x14003efe2  jmp     short loc_14003EFFA
0x14003efe4  lea     r8, [rsp+28h+FileNameInformation]; FileNameInformation
0x14003efe9  mov     edx, ebx; NameOptions
0x14003efeb  mov     rcx, rax; CallbackData
0x14003efee  call    cs:__imp_FltGetFileNameInformation
0x14003eff5  nop     dword ptr [rax+rax+00h]
0x14003effa  mov     ebx, eax
0x14003effc  test    eax, eax
0x14003effe  js      short loc_14003F042
0x14003f000  mov     rdx, [rsp+28h+FileNameInformation]
0x14003f005  mov     rcx, [rsp+28h+NameCtrl]; NameCtrl
0x14003f00a  movzx   edx, word ptr [rdx+8]; NewSize
0x14003f00e  call    cs:__imp_FltCheckAndGrowNameControl
0x14003f015  nop     dword ptr [rax+rax+00h]
0x14003f01a  mov     ebx, eax
0x14003f01c  test    eax, eax
0x14003f01e  js      short loc_14003F042
0x14003f020  mov     rdx, [rsp+28h+FileNameInformation]
0x14003f025  mov     rcx, [rsp+28h+NameCtrl]; DestinationString
0x14003f02a  add     rdx, 8; SourceString
0x14003f02e  call    cs:__imp_RtlCopyUnicodeString
0x14003f035  nop     dword ptr [rax+rax+00h]
0x14003f03a  mov     rax, [rsp+28h+arg_20]
0x14003f03f  mov     byte ptr [rax], 0
0x14003f042  mov     rcx, [rsp+28h+FileNameInformation]; FileNameInformation
0x14003f047  test    rcx, rcx
0x14003f04a  jz      short loc_14003F058
0x14003f04c  call    cs:__imp_FltReleaseFileNameInformation
0x14003f053  nop     dword ptr [rax+rax+00h]
0x14003f058  mov     rsi, [rsp+28h+arg_8]
0x14003f05d  mov     eax, ebx
0x14003f05f  mov     rbx, [rsp+28h+arg_0]
0x14003f064  add     rsp, 20h
0x14003f068  pop     rdi
0x14003f069  retn
```
