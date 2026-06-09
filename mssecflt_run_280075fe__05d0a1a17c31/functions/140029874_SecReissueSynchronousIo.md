# SecReissueSynchronousIo

- ea: `0x140029874`
- end: `0x1400298f9`
- name: `SecReissueSynchronousIo`
- size: `133`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140028c8c`

## callees

- `0x14001047f`
- `0x1400104a3`
- `0x140029874`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1400298bf`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400298bf`

## pseudocode

```c
__int64 __fastcall SecReissueSynchronousIo(PFLT_CALLBACK_DATA CallbackData, __int64 a2, const UNICODE_STRING *a3)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // r9
  unsigned int v5; // ebx
  PFILE_OBJECT TargetFileObject; // rcx

  Iopb = CallbackData->Iopb;
  v5 = 0;
  TargetFileObject = Iopb->TargetFileObject;
  if ( (TargetFileObject->Flags & 0x200000) != 0 )
  {
    return (unsigned int)-1073741536;
  }
  else
  {
    if ( !Iopb->MajorFunction )
    {
      if ( !TargetFileObject || TargetFileObject->FileName.MaximumLength < a3->Length )
        return (unsigned int)-1073741306;
      RtlCopyUnicodeString(&TargetFileObject->FileName, a3);
      FltSetCallbackDataDirty_0(CallbackData);
    }
    FltReissueSynchronousIo_0(*(PFLT_INSTANCE *)(a2 + 24), CallbackData);
  }
  return v5;
}

```

## disassembly

```asm
0x140029874  mov     [rsp+arg_0], rbx
0x140029879  mov     [rsp+arg_8], rsi
0x14002987e  push    rdi
0x14002987f  sub     rsp, 20h
0x140029883  mov     r9, [rcx+10h]
0x140029887  mov     rdi, rcx
0x14002988a  xor     ebx, ebx
0x14002988c  mov     rsi, rdx
0x14002988f  mov     rcx, [r9+8]
0x140029893  test    dword ptr [rcx+50h], 200000h
0x14002989a  jz      short loc_1400298A3
0x14002989c  mov     ebx, 0C0000120h
0x1400298a1  jmp     short loc_1400298DF
0x1400298a3  cmp     [r9+4], bl
0x1400298a7  jnz     short loc_1400298D3
0x1400298a9  test    rcx, rcx
0x1400298ac  jz      short loc_1400298F2
0x1400298ae  movzx   eax, word ptr [r8]
0x1400298b2  cmp     [rcx+5Ah], ax
0x1400298b6  jb      short loc_1400298F2
0x1400298b8  add     rcx, 58h ; 'X'; DestinationString
0x1400298bc  mov     rdx, r8; SourceString
0x1400298bf  call    cs:__imp_RtlCopyUnicodeString
0x1400298c6  nop     dword ptr [rax+rax+00h]
0x1400298cb  mov     rcx, rdi; Data
0x1400298ce  call    FltSetCallbackDataDirty_0
0x1400298d3  mov     rcx, [rsi+18h]; InitiatingInstance
0x1400298d7  mov     rdx, rdi; CallbackData
0x1400298da  call    FltReissueSynchronousIo_0
0x1400298df  mov     rsi, [rsp+28h+arg_8]
0x1400298e4  mov     eax, ebx
0x1400298e6  mov     rbx, [rsp+28h+arg_0]
0x1400298eb  add     rsp, 20h
0x1400298ef  pop     rdi
0x1400298f0  retn
0x1400298f2  mov     ebx, 0C0000206h
0x1400298f7  jmp     short loc_1400298DF
```
