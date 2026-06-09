# BfsReparseNamedPipe

- ea: `0x14000bf74`
- end: `0x14000bfdf`
- name: `BfsReparseNamedPipe`
- size: `107`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA Data)`
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x140002620`
- `0x14000b94c`

## callees

- `0x14000bf74`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000bf9c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bf9c`
- `FLTMGR!FltSetCallbackDataDirty` at `0x14000bfc2`
- `FLTMGR!FltSetCallbackDataDirty` at `0x14000bfc2`

## pseudocode

```c
void __fastcall BfsReparseNamedPipe(PFLT_CALLBACK_DATA Data, UNICODE_STRING *a2)
{
  PFILE_OBJECT TargetFileObject; // rdi
  PWSTR Buffer; // rcx

  TargetFileObject = Data->Iopb->TargetFileObject;
  Buffer = TargetFileObject->FileName.Buffer;
  if ( Buffer )
    ExFreePoolWithTag(Buffer, 0);
  TargetFileObject->FileName = *a2;
  Data->IoStatus.Information = 0;
  Data->IoStatus.Status = 260;
  FltSetCallbackDataDirty(Data);
}

```

## disassembly

```asm
0x14000bf74  mov     [rsp+arg_0], rbx
0x14000bf79  mov     [rsp+arg_8], rsi
0x14000bf7e  push    rdi
0x14000bf7f  sub     rsp, 20h
0x14000bf83  mov     rax, [rcx+10h]
0x14000bf87  mov     rbx, rcx
0x14000bf8a  mov     rsi, rdx
0x14000bf8d  mov     rdi, [rax+8]
0x14000bf91  mov     rcx, [rdi+60h]; P
0x14000bf95  test    rcx, rcx
0x14000bf98  jz      short loc_14000BFA8
0x14000bf9a  xor     edx, edx; Tag
0x14000bf9c  call    cs:__imp_ExFreePoolWithTag
0x14000bfa3  nop     dword ptr [rax+rax+00h]
0x14000bfa8  movups  xmm0, xmmword ptr [rsi]
0x14000bfab  mov     rcx, rbx; Data
0x14000bfae  movdqu  xmmword ptr [rdi+58h], xmm0
0x14000bfb3  mov     qword ptr [rbx+20h], 0
0x14000bfbb  mov     dword ptr [rbx+18h], 104h
0x14000bfc2  call    cs:__imp_FltSetCallbackDataDirty
0x14000bfc9  nop     dword ptr [rax+rax+00h]
0x14000bfce  mov     rbx, [rsp+28h+arg_0]
0x14000bfd3  mov     rsi, [rsp+28h+arg_8]
0x14000bfd8  add     rsp, 20h
0x14000bfdc  pop     rdi
0x14000bfdd  retn
```
