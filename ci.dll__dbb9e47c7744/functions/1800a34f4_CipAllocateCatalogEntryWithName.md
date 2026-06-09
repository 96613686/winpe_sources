# CipAllocateCatalogEntryWithName

- ea: `0x1800a34f4`
- end: `0x1800a3585`
- name: `CipAllocateCatalogEntryWithName`
- size: `145`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800a2f98`

## callees

- `0x1800a34f4`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1800a3551`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1800a3551`
- `ntoskrnl!ExAllocatePool2` at `0x1800a3519`
- `ntoskrnl!ExAllocatePool2` at `0x1800a3519`

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
0x1800a34f4  push    rbx
0x1800a34f6  push    rsi
0x1800a34f7  push    rdi
0x1800a34f8  push    r14
0x1800a34fa  sub     rsp, 28h
0x1800a34fe  mov     r14, rdx
0x1800a3501  mov     rsi, rcx
0x1800a3504  movzx   edx, word ptr [rcx]
0x1800a3507  mov     r8d, 72634943h
0x1800a350d  add     rdx, 118h
0x1800a3514  mov     ecx, 100h
0x1800a3519  call    cs:__imp_ExAllocatePool2
0x1800a3520  nop     dword ptr [rax+rax+00h]
0x1800a3525  mov     rbx, rax
0x1800a3528  test    rax, rax
0x1800a352b  jz      short loc_1800A357E
0x1800a352d  lea     rcx, [rax+118h]
0x1800a3534  xor     edi, edi
0x1800a3536  mov     [rax+0D0h], rcx
0x1800a353d  mov     rdx, rsi; SourceString
0x1800a3540  movzx   ecx, word ptr [rsi]
0x1800a3543  mov     [rax+0CAh], cx
0x1800a354a  lea     rcx, [rax+0C8h]; DestinationString
0x1800a3551  call    cs:__imp_RtlCopyUnicodeString
0x1800a3558  nop     dword ptr [rax+rax+00h]
0x1800a355d  mov     rax, ds:0FFFFF78000000014h
0x1800a3567  mov     [rbx+0F0h], rax
0x1800a356e  mov     [r14], rbx
0x1800a3571  mov     eax, edi
0x1800a3573  add     rsp, 28h
0x1800a3577  pop     r14
0x1800a3579  pop     rdi
0x1800a357a  pop     rsi
0x1800a357b  pop     rbx
0x1800a357c  retn
0x1800a357e  mov     edi, 0C0000017h
0x1800a3583  jmp     short loc_1800A3571
```
