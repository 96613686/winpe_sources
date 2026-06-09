# CscPathUtilsAllocFullPathFromParentPathAndLeafFile

- ea: `0x14008ede4`
- end: `0x14008ee6f`
- name: `CscPathUtilsAllocFullPathFromParentPathAndLeafFile`
- size: `139`
- prototype: `__int64 __fastcall(PUNICODE_STRING Destination, PCUNICODE_STRING SourceString, PCUNICODE_STRING Source)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x1400837e0`

## callees

- `0x14008ede4`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14008ee35`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14008ee35`
- `ntoskrnl!ExAllocatePool2` at `0x14008ee1a`
- `ntoskrnl!ExAllocatePool2` at `0x14008ee1a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14008ee47`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14008ee47`

## pseudocode

```c
__int64 __fastcall CscPathUtilsAllocFullPathFromParentPathAndLeafFile(
        PUNICODE_STRING Destination,
        PCUNICODE_STRING SourceString,
        PCUNICODE_STRING Source)
{
  __int64 v4; // r9
  WCHAR *Pool2; // rax

  v4 = (unsigned __int16)(Source->Length + SourceString->Length);
  Destination->Length = v4;
  Destination->MaximumLength = v4;
  Pool2 = (WCHAR *)ExAllocatePool2(258, (unsigned __int16)v4, 1061124178, v4);
  Destination->Buffer = Pool2;
  if ( Pool2 )
  {
    RtlCopyUnicodeString(Destination, SourceString);
    RtlAppendUnicodeStringToString(Destination, Source);
    return 0;
  }
  else
  {
    *(_DWORD *)&Destination->Length = 0;
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x14008ede4  mov     [rsp+arg_0], rbx
0x14008ede9  mov     [rsp+arg_8], rsi
0x14008edee  push    rdi
0x14008edef  sub     rsp, 20h
0x14008edf3  movzx   r9d, word ptr [rdx]
0x14008edf7  mov     rsi, rdx
0x14008edfa  add     r9w, [r8]
0x14008edfe  mov     rdi, r8
0x14008ee01  movzx   edx, r9w
0x14008ee05  mov     rbx, rcx
0x14008ee08  mov     [rcx], dx
0x14008ee0b  mov     r8d, 3F3F7852h
0x14008ee11  mov     [rcx+2], dx
0x14008ee15  mov     ecx, 102h
0x14008ee1a  call    cs:__imp_ExAllocatePool2
0x14008ee21  nop     dword ptr [rax+rax+00h]
0x14008ee26  mov     [rbx+8], rax
0x14008ee2a  test    rax, rax
0x14008ee2d  jz      short loc_14008EE57
0x14008ee2f  mov     rdx, rsi; SourceString
0x14008ee32  mov     rcx, rbx; DestinationString
0x14008ee35  call    cs:__imp_RtlCopyUnicodeString
0x14008ee3c  nop     dword ptr [rax+rax+00h]
0x14008ee41  mov     rdx, rdi; Source
0x14008ee44  mov     rcx, rbx; Destination
0x14008ee47  call    cs:__imp_RtlAppendUnicodeStringToString
0x14008ee4e  nop     dword ptr [rax+rax+00h]
0x14008ee53  xor     eax, eax
0x14008ee55  jmp     short loc_14008EE5E
0x14008ee57  mov     [rbx], eax
0x14008ee59  mov     eax, 0C000009Ah
0x14008ee5e  mov     rbx, [rsp+28h+arg_0]
0x14008ee63  mov     rsi, [rsp+28h+arg_8]
0x14008ee68  add     rsp, 20h
0x14008ee6c  pop     rdi
0x14008ee6d  retn
```
