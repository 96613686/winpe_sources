# CipAllocateCatalogEntryWithName

- ea: `0x1800a1ec4`
- end: `0x1800a1f55`
- name: `CipAllocateCatalogEntryWithName`
- size: `145`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800a1968`

## callees

- `0x1800a1ec4`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1800a1f21`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1800a1f21`
- `ntoskrnl!ExAllocatePool2` at `0x1800a1ee9`
- `ntoskrnl!ExAllocatePool2` at `0x1800a1ee9`

## pseudocode

```c
__int64 __fastcall CipAllocateCatalogEntryWithName(PCUNICODE_STRING SourceString, __int64 *a2)
{
  __int64 Pool2; // rax
  __int64 v5; // rbx
  unsigned int v6; // edi

  Pool2 = ExAllocatePool2(256, SourceString->Length + 280LL, 1919109443);
  v5 = Pool2;
  if ( Pool2 )
  {
    v6 = 0;
    *(_QWORD *)(Pool2 + 208) = Pool2 + 280;
    *(_WORD *)(Pool2 + 202) = SourceString->Length;
    RtlCopyUnicodeString((PUNICODE_STRING)(Pool2 + 200), SourceString);
    *(_QWORD *)(v5 + 240) = MEMORY[0xFFFFF78000000014];
    *a2 = v5;
  }
  else
  {
    return (unsigned int)-1073741801;
  }
  return v6;
}

```

## disassembly

```asm
0x1800a1ec4  push    rbx
0x1800a1ec6  push    rsi
0x1800a1ec7  push    rdi
0x1800a1ec8  push    r14
0x1800a1eca  sub     rsp, 28h
0x1800a1ece  mov     r14, rdx
0x1800a1ed1  mov     rsi, rcx
0x1800a1ed4  movzx   edx, word ptr [rcx]
0x1800a1ed7  mov     r8d, 72634943h
0x1800a1edd  add     rdx, 118h
0x1800a1ee4  mov     ecx, 100h
0x1800a1ee9  call    cs:__imp_ExAllocatePool2
0x1800a1ef0  nop     dword ptr [rax+rax+00h]
0x1800a1ef5  mov     rbx, rax
0x1800a1ef8  test    rax, rax
0x1800a1efb  jz      short loc_1800A1F4E
0x1800a1efd  lea     rcx, [rax+118h]
0x1800a1f04  xor     edi, edi
0x1800a1f06  mov     [rax+0D0h], rcx
0x1800a1f0d  mov     rdx, rsi; SourceString
0x1800a1f10  movzx   ecx, word ptr [rsi]
0x1800a1f13  mov     [rax+0CAh], cx
0x1800a1f1a  lea     rcx, [rax+0C8h]; DestinationString
0x1800a1f21  call    cs:__imp_RtlCopyUnicodeString
0x1800a1f28  nop     dword ptr [rax+rax+00h]
0x1800a1f2d  mov     rax, ds:0FFFFF78000000014h
0x1800a1f37  mov     [rbx+0F0h], rax
0x1800a1f3e  mov     [r14], rbx
0x1800a1f41  mov     eax, edi
0x1800a1f43  add     rsp, 28h
0x1800a1f47  pop     r14
0x1800a1f49  pop     rdi
0x1800a1f4a  pop     rsi
0x1800a1f4b  pop     rbx
0x1800a1f4c  retn
0x1800a1f4e  mov     edi, 0C0000017h
0x1800a1f53  jmp     short loc_1800A1F41
```
