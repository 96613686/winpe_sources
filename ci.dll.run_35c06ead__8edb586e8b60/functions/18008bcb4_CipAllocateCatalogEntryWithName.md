# CipAllocateCatalogEntryWithName

- ea: `0x18008bcb4`
- end: `0x18008bd45`
- name: `CipAllocateCatalogEntryWithName`
- size: `145`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18008c1a0`

## callees

- `0x18008bcb4`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x18008bd11`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18008bd11`
- `ntoskrnl!ExAllocatePool2` at `0x18008bcd9`
- `ntoskrnl!ExAllocatePool2` at `0x18008bcd9`

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
0x18008bcb4  push    rbx
0x18008bcb6  push    rsi
0x18008bcb7  push    rdi
0x18008bcb8  push    r14
0x18008bcba  sub     rsp, 28h
0x18008bcbe  mov     r14, rdx
0x18008bcc1  mov     rsi, rcx
0x18008bcc4  movzx   edx, word ptr [rcx]
0x18008bcc7  mov     r8d, 72634943h
0x18008bccd  add     rdx, 118h
0x18008bcd4  mov     ecx, 100h
0x18008bcd9  call    cs:__imp_ExAllocatePool2
0x18008bce0  nop     dword ptr [rax+rax+00h]
0x18008bce5  mov     rbx, rax
0x18008bce8  test    rax, rax
0x18008bceb  jz      short loc_18008BD3E
0x18008bced  lea     rcx, [rax+118h]
0x18008bcf4  xor     edi, edi
0x18008bcf6  mov     [rax+0D0h], rcx
0x18008bcfd  mov     rdx, rsi; SourceString
0x18008bd00  movzx   ecx, word ptr [rsi]
0x18008bd03  mov     [rax+0CAh], cx
0x18008bd0a  lea     rcx, [rax+0C8h]; DestinationString
0x18008bd11  call    cs:__imp_RtlCopyUnicodeString
0x18008bd18  nop     dword ptr [rax+rax+00h]
0x18008bd1d  mov     rax, ds:0FFFFF78000000014h
0x18008bd27  mov     [rbx+0F0h], rax
0x18008bd2e  mov     [r14], rbx
0x18008bd31  mov     eax, edi
0x18008bd33  add     rsp, 28h
0x18008bd37  pop     r14
0x18008bd39  pop     rdi
0x18008bd3a  pop     rsi
0x18008bd3b  pop     rbx
0x18008bd3c  retn
0x18008bd3e  mov     edi, 0C0000017h
0x18008bd43  jmp     short loc_18008BD31
```
