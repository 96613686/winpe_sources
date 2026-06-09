# LuafvIsInProfile

- ea: `0x140004c3c`
- end: `0x140004d56`
- name: `LuafvIsInProfile`
- size: `282`
- prototype: `__int64 __fastcall(struct _FLT_CALLBACK_DATA *, struct _FLT_FILE_NAME_INFORMATION *, __int64, BOOLEAN *, PUNICODE_STRING DestinationString)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140025820`

## callees

- `0x140004708`
- `0x140004c3c`

## import_xrefs

- `ntoskrnl!RtlPrefixUnicodeString` at `0x140004cbc`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140004cbc`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140004d24`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140004d24`
- `ntoskrnl!ExAllocatePool2` at `0x140004ced`
- `ntoskrnl!ExAllocatePool2` at `0x140004ced`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140004d3d`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140004d3d`
- `FLTMGR!FltGetFileNameInformation` at `0x140004c80`
- `FLTMGR!FltGetFileNameInformation` at `0x140004c80`

## pseudocode

```c
__int64 __fastcall LuafvIsInProfile(
        struct _FLT_CALLBACK_DATA *a1,
        struct _FLT_FILE_NAME_INFORMATION *a2,
        __int64 a3,
        BOOLEAN *a4,
        PUNICODE_STRING DestinationString)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  NTSTATUS v9; // edi
  BOOLEAN v10; // si
  PUNICODE_STRING v11; // rbx
  __int64 Pool2; // rax
  PFLT_FILE_NAME_INFORMATION v13; // r8
  UNICODE_STRING *p_Name; // rdx
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+58h] [rbp+10h] BYREF

  FileNameInformation = a2;
  Iopb = a1->Iopb;
  FileNameInformation = 0;
  *a4 = 0;
  if ( Iopb->TargetFileObject->DeviceObject->DeviceType == 20 )
    return 0;
  v9 = FltGetFileNameInformation(a1, 1u, &FileNameInformation);
  if ( v9 >= 0 && !LuafvIsExcludedFile(&FileNameInformation->Name) )
  {
    v10 = RtlPrefixUnicodeString((PCUNICODE_STRING)(a3 + 120), &FileNameInformation->Name, 1u);
    if ( v10 )
    {
      v11 = DestinationString;
      if ( DestinationString )
      {
        Pool2 = ExAllocatePool2(256, FileNameInformation->Name.MaximumLength, 1717663052);
        v11->Buffer = (PWSTR)Pool2;
        if ( !Pool2 )
        {
          v9 = -1073741670;
          goto LABEL_11;
        }
        v13 = FileNameInformation;
        p_Name = &FileNameInformation->Name;
        v11->Length = FileNameInformation->Name.Length;
        v11->MaximumLength = v13->Name.MaximumLength;
        RtlCopyUnicodeString(v11, p_Name);
      }
    }
    *a4 = v10;
  }
LABEL_11:
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140004c3c  mov     [rsp+FileNameInformation], rdx
0x140004c41  push    rbx
0x140004c42  push    rsi
0x140004c43  push    rdi
0x140004c44  push    r14
0x140004c46  sub     rsp, 28h
0x140004c4a  mov     rax, [rcx+10h]
0x140004c4e  mov     r14, r9
0x140004c51  mov     [rsp+48h+FileNameInformation], 0
0x140004c5a  mov     rbx, r8
0x140004c5d  mov     byte ptr [r9], 0
0x140004c61  mov     rdx, [rax+8]
0x140004c65  mov     rax, [rdx+8]
0x140004c69  cmp     dword ptr [rax+48h], 14h
0x140004c6d  jnz     short loc_140004C76
0x140004c6f  xor     eax, eax
0x140004c71  jmp     loc_140004D4B
0x140004c76  lea     r8, [rsp+48h+FileNameInformation]; FileNameInformation
0x140004c7b  mov     edx, 1; NameOptions
0x140004c80  call    cs:__imp_FltGetFileNameInformation
0x140004c87  nop     dword ptr [rax+rax+00h]
0x140004c8c  mov     edi, eax
0x140004c8e  test    eax, eax
0x140004c90  js      loc_140004D33
0x140004c96  mov     rcx, [rsp+48h+FileNameInformation]
0x140004c9b  add     rcx, 8
0x140004c9f  call    LuafvIsExcludedFile
0x140004ca4  test    al, al
0x140004ca6  jnz     loc_140004D33
0x140004cac  mov     rdx, [rsp+48h+FileNameInformation]
0x140004cb1  lea     rcx, [rbx+78h]; String1
0x140004cb5  add     rdx, 8; String2
0x140004cb9  mov     r8b, 1; CaseInSensitive
0x140004cbc  call    cs:__imp_RtlPrefixUnicodeString
0x140004cc3  nop     dword ptr [rax+rax+00h]
0x140004cc8  mov     sil, al
0x140004ccb  test    al, al
0x140004ccd  jz      short loc_140004D30
0x140004ccf  mov     rbx, [rsp+48h+DestinationString]
0x140004cd4  test    rbx, rbx
0x140004cd7  jz      short loc_140004D30
0x140004cd9  mov     rcx, [rsp+48h+FileNameInformation]
0x140004cde  mov     r8d, 6661754Ch
0x140004ce4  movzx   edx, word ptr [rcx+0Ah]
0x140004ce8  mov     ecx, 100h
0x140004ced  call    cs:__imp_ExAllocatePool2
0x140004cf4  nop     dword ptr [rax+rax+00h]
0x140004cf9  mov     [rbx+8], rax
0x140004cfd  test    rax, rax
0x140004d00  jnz     short loc_140004D09
0x140004d02  mov     edi, 0C000009Ah
0x140004d07  jmp     short loc_140004D33
0x140004d09  mov     r8, [rsp+48h+FileNameInformation]
0x140004d0e  mov     rcx, rbx; DestinationString
0x140004d11  lea     rdx, [r8+8]; SourceString
0x140004d15  movzx   eax, word ptr [rdx]
0x140004d18  mov     [rbx], ax
0x140004d1b  movzx   eax, word ptr [r8+0Ah]
0x140004d20  mov     [rbx+2], ax
0x140004d24  call    cs:__imp_RtlCopyUnicodeString
0x140004d2b  nop     dword ptr [rax+rax+00h]
0x140004d30  mov     [r14], sil
0x140004d33  mov     rcx, [rsp+48h+FileNameInformation]; FileNameInformation
0x140004d38  test    rcx, rcx
0x140004d3b  jz      short loc_140004D49
0x140004d3d  call    cs:__imp_FltReleaseFileNameInformation
0x140004d44  nop     dword ptr [rax+rax+00h]
0x140004d49  mov     eax, edi
0x140004d4b  add     rsp, 28h
0x140004d4f  pop     r14
0x140004d51  pop     rdi
0x140004d52  pop     rsi
0x140004d53  pop     rbx
0x140004d54  retn
```
