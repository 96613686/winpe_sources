# QuerySymbolicLink

- ea: `0x140028f24`
- end: `0x140028f90`
- name: `QuerySymbolicLink`
- size: `108`
- prototype: `__int64 __fastcall(HANDLE LinkHandle, PUNICODE_STRING LinkTarget)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x14002814c`
- `0x140028364`

## callees

- `0x1400280d4`
- `0x140028f24`

## import_xrefs

- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x140028f5d`
- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x140028f5d`

## pseudocode

```c
NTSTATUS __fastcall QuerySymbolicLink(HANDLE LinkHandle, PUNICODE_STRING LinkTarget)
{
  NTSTATUS result; // eax
  ULONG ReturnedLength; // [rsp+38h] [rbp+10h] BYREF

  ReturnedLength = 0;
  do
  {
    LinkTarget->MaximumLength = QueryBufferLength;
    LinkTarget->Buffer = (PWSTR)QueryBuffer;
    result = ZwQuerySymbolicLinkObject(LinkHandle, LinkTarget, &ReturnedLength);
    if ( result != -2147483643 && result != -1073741789 )
      break;
    result = GrowQueryBuffer(ReturnedLength);
  }
  while ( result >= 0 );
  return result;
}

```

## disassembly

```asm
0x140028f24  mov     [rsp+arg_0], rbx
0x140028f29  push    rdi
0x140028f2a  sub     rsp, 20h
0x140028f2e  mov     rbx, rdx
0x140028f31  mov     [rsp+28h+ReturnedLength], 0
0x140028f39  mov     rdi, rcx
0x140028f3c  movzx   eax, word ptr cs:QueryBufferLength
0x140028f43  lea     r8, [rsp+28h+ReturnedLength]; ReturnedLength
0x140028f48  mov     [rbx+2], ax
0x140028f4c  mov     rdx, rbx; LinkTarget
0x140028f4f  mov     rax, cs:QueryBuffer
0x140028f56  mov     rcx, rdi; LinkHandle
0x140028f59  mov     [rbx+8], rax
0x140028f5d  call    cs:__imp_ZwQuerySymbolicLinkObject
0x140028f64  nop     dword ptr [rax+rax+00h]
0x140028f69  cmp     eax, 80000005h
0x140028f6e  jz      short loc_140028F77
0x140028f70  cmp     eax, 0C0000023h
0x140028f75  jnz     short loc_140028F84
0x140028f77  mov     ecx, [rsp+28h+ReturnedLength]
0x140028f7b  call    GrowQueryBuffer
0x140028f80  test    eax, eax
0x140028f82  jns     short loc_140028F3C
0x140028f84  mov     rbx, [rsp+28h+arg_0]
0x140028f89  add     rsp, 20h
0x140028f8d  pop     rdi
0x140028f8e  retn
```
