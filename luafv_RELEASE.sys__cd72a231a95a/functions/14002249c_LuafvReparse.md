# LuafvReparse

- ea: `0x14002249c`
- end: `0x140022567`
- name: `LuafvReparse`
- size: `203`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, _QWORD *, char)`
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x140025300`
- `0x140025820`

## callees

- `0x140014a90`
- `0x14002249c`
- `0x140022570`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140022520`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140022520`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022502`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022502`
- `ntoskrnl!ExAllocatePool2` at `0x1400224db`
- `ntoskrnl!ExAllocatePool2` at `0x1400224db`
- `FLTMGR!FltSetCallbackDataDirty` at `0x14002253e`
- `FLTMGR!FltSetCallbackDataDirty` at `0x14002253e`

## pseudocode

```c
__int64 __fastcall LuafvReparse(PFLT_CALLBACK_DATA CallbackData, _QWORD *a2, char a3)
{
  __int64 result; // rax
  __int64 v7; // rax
  const UNICODE_STRING *v8; // rsi
  __int64 Pool2; // rbp
  PFILE_OBJECT TargetFileObject; // rdi
  PWSTR Buffer; // rcx
  unsigned int v12; // edi

  result = LuafvSetEcp(CallbackData, a2);
  if ( (int)result >= 0 )
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
0x14002249c  push    rbx
0x14002249e  push    rbp
0x14002249f  push    rsi
0x1400224a0  push    rdi
0x1400224a1  sub     rsp, 28h
0x1400224a5  mov     sil, r8b
0x1400224a8  mov     rdi, rdx
0x1400224ab  mov     rbx, rcx
0x1400224ae  call    LuafvSetEcp
0x1400224b3  test    eax, eax
0x1400224b5  js      loc_14002254E
0x1400224bb  mov     rcx, [rdi]
0x1400224be  test    sil, sil
0x1400224c1  mov     r8d, 6661754Ch
0x1400224c7  lea     rax, [rcx+30h]
0x1400224cb  cmovz   rax, rcx
0x1400224cf  mov     ecx, 100h
0x1400224d4  lea     rsi, [rax+10h]
0x1400224d8  movzx   edx, word ptr [rsi]
0x1400224db  call    cs:__imp_ExAllocatePool2
0x1400224e2  nop     dword ptr [rax+rax+00h]
0x1400224e7  mov     rbp, rax
0x1400224ea  test    rax, rax
0x1400224ed  jz      short loc_140022558
0x1400224ef  mov     rax, [rbx+10h]
0x1400224f3  mov     rdi, [rax+8]
0x1400224f7  mov     rcx, [rdi+60h]; P
0x1400224fb  test    rcx, rcx
0x1400224fe  jz      short loc_14002250E
0x140022500  xor     edx, edx; Tag
0x140022502  call    cs:__imp_ExFreePoolWithTag
0x140022509  nop     dword ptr [rax+rax+00h]
0x14002250e  movzx   eax, word ptr [rsi]
0x140022511  lea     rcx, [rdi+58h]; DestinationString
0x140022515  mov     rdx, rsi; SourceString
0x140022518  mov     [rdi+5Ah], ax
0x14002251c  mov     [rdi+60h], rbp
0x140022520  call    cs:__imp_RtlCopyUnicodeString
0x140022527  nop     dword ptr [rax+rax+00h]
0x14002252c  mov     rcx, rbx; Data
0x14002252f  mov     qword ptr [rbx+20h], 0
0x140022537  mov     dword ptr [rbx+18h], 104h
0x14002253e  call    cs:__imp_FltSetCallbackDataDirty
0x140022545  nop     dword ptr [rax+rax+00h]
0x14002254a  xor     edi, edi
0x14002254c  mov     eax, edi
0x14002254e  add     rsp, 28h
0x140022552  pop     rdi
0x140022553  pop     rsi
0x140022554  pop     rbp
0x140022555  pop     rbx
0x140022556  retn
0x140022558  mov     rcx, rbx; CallbackData
0x14002255b  mov     edi, 0C000009Ah
0x140022560  call    LuafvRemoveEcp
0x140022565  jmp     short loc_14002254C
```
