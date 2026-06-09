# LuafvIsInProfile

- ea: `0x140004a74`
- end: `0x140004b8e`
- name: `LuafvIsInProfile`
- size: `282`
- prototype: `__int64 __fastcall(int, int, int, int, PUNICODE_STRING DestinationString)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400258a0`

## callees

- `0x1400044d8`
- `0x140004a74`

## import_xrefs

- `ntoskrnl!RtlPrefixUnicodeString` at `0x140004af4`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140004af4`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140004b5c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140004b5c`
- `ntoskrnl!ExAllocatePool2` at `0x140004b25`
- `ntoskrnl!ExAllocatePool2` at `0x140004b25`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140004b75`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140004b75`
- `FLTMGR!FltGetFileNameInformation` at `0x140004ab8`
- `FLTMGR!FltGetFileNameInformation` at `0x140004ab8`

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
  if ( v9 >= 0 && !(unsigned __int8)LuafvIsExcludedFile(&FileNameInformation->Name) )
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
0x140004a74  mov     [rsp+FileNameInformation], rdx
0x140004a79  push    rbx
0x140004a7a  push    rsi
0x140004a7b  push    rdi
0x140004a7c  push    r14
0x140004a7e  sub     rsp, 28h
0x140004a82  mov     rax, [rcx+10h]
0x140004a86  mov     r14, r9
0x140004a89  mov     [rsp+48h+FileNameInformation], 0
0x140004a92  mov     rbx, r8
0x140004a95  mov     byte ptr [r9], 0
0x140004a99  mov     rdx, [rax+8]
0x140004a9d  mov     rax, [rdx+8]
0x140004aa1  cmp     dword ptr [rax+48h], 14h
0x140004aa5  jnz     short loc_140004AAE
0x140004aa7  xor     eax, eax
0x140004aa9  jmp     loc_140004B83
0x140004aae  lea     r8, [rsp+48h+FileNameInformation]; FileNameInformation
0x140004ab3  mov     edx, 1; NameOptions
0x140004ab8  call    cs:__imp_FltGetFileNameInformation
0x140004abf  nop     dword ptr [rax+rax+00h]
0x140004ac4  mov     edi, eax
0x140004ac6  test    eax, eax
0x140004ac8  js      loc_140004B6B
0x140004ace  mov     rcx, [rsp+48h+FileNameInformation]
0x140004ad3  add     rcx, 8
0x140004ad7  call    LuafvIsExcludedFile
0x140004adc  test    al, al
0x140004ade  jnz     loc_140004B6B
0x140004ae4  mov     rdx, [rsp+48h+FileNameInformation]
0x140004ae9  lea     rcx, [rbx+78h]; String1
0x140004aed  add     rdx, 8; String2
0x140004af1  mov     r8b, 1; CaseInSensitive
0x140004af4  call    cs:__imp_RtlPrefixUnicodeString
0x140004afb  nop     dword ptr [rax+rax+00h]
0x140004b00  mov     sil, al
0x140004b03  test    al, al
0x140004b05  jz      short loc_140004B68
0x140004b07  mov     rbx, [rsp+48h+DestinationString]
0x140004b0c  test    rbx, rbx
0x140004b0f  jz      short loc_140004B68
0x140004b11  mov     rcx, [rsp+48h+FileNameInformation]
0x140004b16  mov     r8d, 6661754Ch
0x140004b1c  movzx   edx, word ptr [rcx+0Ah]
0x140004b20  mov     ecx, 100h
0x140004b25  call    cs:__imp_ExAllocatePool2
0x140004b2c  nop     dword ptr [rax+rax+00h]
0x140004b31  mov     [rbx+8], rax
0x140004b35  test    rax, rax
0x140004b38  jnz     short loc_140004B41
0x140004b3a  mov     edi, 0C000009Ah
0x140004b3f  jmp     short loc_140004B6B
0x140004b41  mov     r8, [rsp+48h+FileNameInformation]
0x140004b46  mov     rcx, rbx; DestinationString
0x140004b49  lea     rdx, [r8+8]; SourceString
0x140004b4d  movzx   eax, word ptr [rdx]
0x140004b50  mov     [rbx], ax
0x140004b53  movzx   eax, word ptr [r8+0Ah]
0x140004b58  mov     [rbx+2], ax
0x140004b5c  call    cs:__imp_RtlCopyUnicodeString
0x140004b63  nop     dword ptr [rax+rax+00h]
0x140004b68  mov     [r14], sil
0x140004b6b  mov     rcx, [rsp+48h+FileNameInformation]; FileNameInformation
0x140004b70  test    rcx, rcx
0x140004b73  jz      short loc_140004B81
0x140004b75  call    cs:__imp_FltReleaseFileNameInformation
0x140004b7c  nop     dword ptr [rax+rax+00h]
0x140004b81  mov     eax, edi
0x140004b83  add     rsp, 28h
0x140004b87  pop     r14
0x140004b89  pop     rdi
0x140004b8a  pop     rsi
0x140004b8b  pop     rbx
0x140004b8c  retn
```
