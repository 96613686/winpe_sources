# VmbusTlFindAndReferencePartition

- ea: `0x14001f540`
- end: `0x14001f5db`
- name: `VmbusTlFindAndReferencePartition`
- size: `155`
- prototype: `_QWORD *__fastcall(__int64, const void *)`
- caller_count: `12`
- callee_count: `3`
- tags: ``

## callers

- `0x140019a10`
- `0x14001a148`
- `0x14001a790`
- `0x14001a9f0`
- `0x14001bd20`
- `0x14001c2d0`
- `0x14001d530`
- `0x14001d728`
- `0x14001e1c0`
- `0x14001edd0`
- `0x140020b80`
- `0x140021550`

## callees

- `0x14000a048`
- `0x14000c0a0`
- `0x14001f540`

## pseudocode

```c
_QWORD *__fastcall VmbusTlFindAndReferencePartition(__int64 a1, const void *a2)
{
  _QWORD *v2; // rsi
  _QWORD *i; // rbx
  _QWORD *v5; // rdi

  v2 = (_QWORD *)(a1 + 128);
  for ( i = *(_QWORD **)(a1 + 128); ; i = (_QWORD *)*i )
  {
    if ( i == v2 )
      return 0;
    v5 = i - 27;
    if ( !memcmp(i + 2, a2, 0x10u) )
      break;
  }
  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (const int *)"VmbusTlFindAndReferencePartition",
      2143,
      (__int64)(i - 27),
      v5[1],
      (const int *)"Reference object");
  if ( _InterlockedIncrement64(v5 + 1) <= 1 )
    __fastfail(0xEu);
  return i - 27;
}

```

## disassembly

```asm
0x14001f540  push    rbx
0x14001f542  push    rbp
0x14001f543  push    rsi
0x14001f544  push    rdi
0x14001f545  sub     rsp, 38h
0x14001f549  lea     rsi, [rcx+80h]
0x14001f550  mov     rbp, rdx
0x14001f553  mov     rbx, [rsi]
0x14001f556  jmp     short loc_14001F57B
0x14001f558  lea     rdi, [rbx-0D8h]
0x14001f55f  mov     r8d, 10h; Size
0x14001f565  lea     rcx, [rdi+0E8h]; Buf1
0x14001f56c  mov     rdx, rbp; Buf2
0x14001f56f  call    memcmp
0x14001f574  test    eax, eax
0x14001f576  jz      short loc_14001F58C
0x14001f578  mov     rbx, [rbx]
0x14001f57b  cmp     rbx, rsi
0x14001f57e  jnz     short loc_14001F558
0x14001f580  xor     eax, eax
0x14001f582  add     rsp, 38h
0x14001f586  pop     rdi
0x14001f587  pop     rsi
0x14001f588  pop     rbp
0x14001f589  pop     rbx
0x14001f58a  retn
0x14001f58c  mov     eax, cs:dword_140013058
0x14001f592  cmp     eax, 5
0x14001f595  jbe     short loc_14001F5BB
0x14001f597  mov     r9, [rdi+8]
0x14001f59b  lea     rax, aReferenceObjec; "Reference object"
0x14001f5a2  mov     r8, rdi
0x14001f5a5  mov     [rsp+58h+var_38], rax
0x14001f5aa  mov     edx, 85Fh
0x14001f5af  lea     rcx, aVmbustlfindand_3; "VmbusTlFindAndReferencePartition"
0x14001f5b6  call    HvsocketTraceReferenceCount
0x14001f5bb  mov     ecx, 1
0x14001f5c0  lock xadd [rdi+8], rcx
0x14001f5c6  inc     rcx
0x14001f5c9  cmp     rcx, 1
0x14001f5cd  jg      short loc_14001F5D6
0x14001f5cf  mov     ecx, 0Eh
0x14001f5d4  int     29h; Win8: RtlFailFast(ecx)
0x14001f5d6  mov     rax, rdi
0x14001f5d9  jmp     short loc_14001F582
```
