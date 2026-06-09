# RxCeFreeTransformBufferAndMdl

- ea: `0x1400359f8`
- end: `0x140035a6f`
- name: `RxCeFreeTransformBufferAndMdl`
- size: `119`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x14000e9c0`
- `0x14000f1a0`
- `0x140017700`
- `0x14008b2f8`
- `0x14008c298`

## callees

- `0x1400359f8`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140035a2c`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140035a2c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035a48`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035a48`
- `rdbss!RxFreeMdl` at `0x140035a57`
- `rdbss!RxFreeMdl` at `0x140035a57`

## pseudocode

```c
__int64 __fastcall RxCeFreeTransformBufferAndMdl(struct _MDL *a1, ULONG a2)
{
  char *MappedSystemVa; // rax
  char *v5; // rcx

  if ( (a1->MdlFlags & 5) != 0 )
    MappedSystemVa = (char *)a1->MappedSystemVa;
  else
    MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(a1, 0, MmCached, 0, 0, 0x40000000u);
  v5 = MappedSystemVa - 80;
  if ( !_bittest16(&a1->MdlFlags, 0xCu) )
    v5 = MappedSystemVa;
  ExFreePoolWithTag(v5, a2);
  return RxFreeMdl(a1);
}

```

## disassembly

```asm
0x1400359f8  mov     [rsp+arg_0], rbx
0x1400359fd  push    rdi
0x1400359fe  sub     rsp, 30h
0x140035a02  test    byte ptr [rcx+0Ah], 5
0x140035a06  mov     edi, edx
0x140035a08  mov     rbx, rcx
0x140035a0b  jz      short loc_140035A13
0x140035a0d  mov     rax, [rcx+18h]
0x140035a11  jmp     short loc_140035A38
0x140035a13  xor     r9d, r9d; RequestedAddress
0x140035a16  mov     [rsp+38h+Priority], 40000000h; Priority
0x140035a1e  xor     edx, edx; AccessMode
0x140035a20  mov     [rsp+38h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140035a28  lea     r8d, [r9+1]; CacheType
0x140035a2c  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140035a33  nop     dword ptr [rax+rax+00h]
0x140035a38  bt      word ptr [rbx+0Ah], 0Ch
0x140035a3e  lea     rcx, [rax-50h]
0x140035a42  mov     edx, edi; Tag
0x140035a44  cmovnb  rcx, rax; P
0x140035a48  call    cs:__imp_ExFreePoolWithTag
0x140035a4f  nop     dword ptr [rax+rax+00h]
0x140035a54  mov     rcx, rbx
0x140035a57  call    cs:__imp_RxFreeMdl
0x140035a5e  nop     dword ptr [rax+rax+00h]
0x140035a63  mov     rbx, [rsp+38h+arg_0]
0x140035a68  add     rsp, 30h
0x140035a6c  pop     rdi
0x140035a6d  retn
```
