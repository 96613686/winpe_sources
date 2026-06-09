# LuafvReparse

- ea: `0x1400224ec`
- end: `0x1400225b7`
- name: `LuafvReparse`
- size: `203`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x140025350`
- `0x1400258a0`

## callees

- `0x140014a90`
- `0x1400224ec`
- `0x1400225c0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140022570`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140022570`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022552`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022552`
- `ntoskrnl!ExAllocatePool2` at `0x14002252b`
- `ntoskrnl!ExAllocatePool2` at `0x14002252b`
- `FLTMGR!FltSetCallbackDataDirty` at `0x14002258e`
- `FLTMGR!FltSetCallbackDataDirty` at `0x14002258e`

## pseudocode

```c
NTSTATUS __fastcall LuafvReparse(PFLT_CALLBACK_DATA CallbackData, _QWORD *a2, char a3)
{
  NTSTATUS result; // eax
  __int64 v7; // rax
  const UNICODE_STRING *v8; // rsi
  __int64 Pool2; // rbp
  PFILE_OBJECT TargetFileObject; // rdi
  PWSTR Buffer; // rcx
  int v12; // edi

  result = LuafvSetEcp(CallbackData, a2);
  if ( result >= 0 )
  {
    v7 = *a2 + 48LL;
    if ( !a3 )
      v7 = *a2;
    v8 = (const UNICODE_STRING *)(v7 + 16);
    Pool2 = ExAllocatePool2(256, *(unsigned __int16 *)(v7 + 16), 1717663052);
    if ( Pool2 )
    {
      TargetFileObject = CallbackData->Iopb->TargetFileObject;
      Buffer = TargetFileObject->FileName.Buffer;
      if ( Buffer )
        ExFreePoolWithTag(Buffer, 0);
      TargetFileObject->FileName.MaximumLength = v8->Length;
      TargetFileObject->FileName.Buffer = (PWSTR)Pool2;
      RtlCopyUnicodeString(&TargetFileObject->FileName, v8);
      CallbackData->IoStatus.Information = 0;
      CallbackData->IoStatus.Status = 260;
      FltSetCallbackDataDirty(CallbackData);
      return 0;
    }
    else
    {
      v12 = -1073741670;
      LuafvRemoveEcp(CallbackData);
    }
    return v12;
  }
  return result;
}

```

## disassembly

```asm
0x1400224ec  push    rbx
0x1400224ee  push    rbp
0x1400224ef  push    rsi
0x1400224f0  push    rdi
0x1400224f1  sub     rsp, 28h
0x1400224f5  mov     sil, r8b
0x1400224f8  mov     rdi, rdx
0x1400224fb  mov     rbx, rcx
0x1400224fe  call    LuafvSetEcp
0x140022503  test    eax, eax
0x140022505  js      loc_14002259E
0x14002250b  mov     rcx, [rdi]
0x14002250e  test    sil, sil
0x140022511  mov     r8d, 6661754Ch
0x140022517  lea     rax, [rcx+30h]
0x14002251b  cmovz   rax, rcx
0x14002251f  mov     ecx, 100h
0x140022524  lea     rsi, [rax+10h]
0x140022528  movzx   edx, word ptr [rsi]
0x14002252b  call    cs:__imp_ExAllocatePool2
0x140022532  nop     dword ptr [rax+rax+00h]
0x140022537  mov     rbp, rax
0x14002253a  test    rax, rax
0x14002253d  jz      short loc_1400225A8
0x14002253f  mov     rax, [rbx+10h]
0x140022543  mov     rdi, [rax+8]
0x140022547  mov     rcx, [rdi+60h]; P
0x14002254b  test    rcx, rcx
0x14002254e  jz      short loc_14002255E
0x140022550  xor     edx, edx; Tag
0x140022552  call    cs:__imp_ExFreePoolWithTag
0x140022559  nop     dword ptr [rax+rax+00h]
0x14002255e  movzx   eax, word ptr [rsi]
0x140022561  lea     rcx, [rdi+58h]; DestinationString
0x140022565  mov     rdx, rsi; SourceString
0x140022568  mov     [rdi+5Ah], ax
0x14002256c  mov     [rdi+60h], rbp
0x140022570  call    cs:__imp_RtlCopyUnicodeString
0x140022577  nop     dword ptr [rax+rax+00h]
0x14002257c  mov     rcx, rbx; Data
0x14002257f  mov     qword ptr [rbx+20h], 0
0x140022587  mov     dword ptr [rbx+18h], 104h
0x14002258e  call    cs:__imp_FltSetCallbackDataDirty
0x140022595  nop     dword ptr [rax+rax+00h]
0x14002259a  xor     edi, edi
0x14002259c  mov     eax, edi
0x14002259e  add     rsp, 28h
0x1400225a2  pop     rdi
0x1400225a3  pop     rsi
0x1400225a4  pop     rbp
0x1400225a5  pop     rbx
0x1400225a6  retn
0x1400225a8  mov     rcx, rbx; CallbackData
0x1400225ab  mov     edi, 0C000009Ah
0x1400225b0  call    LuafvRemoveEcp
0x1400225b5  jmp     short loc_14002259C
```
