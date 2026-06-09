# VmbusTlFindAndReferenceWildcardDescriptor

- ea: `0x14002672c`
- end: `0x1400267c1`
- name: `VmbusTlFindAndReferenceWildcardDescriptor`
- size: `149`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140006be0`

## callees

- `0x14000a048`
- `0x14000c0a0`
- `0x14002672c`

## string_xrefs

- `0x140026798`: `VmbusTlFindAndReferenceWildcardDescriptor`

## pseudocode

```c
_QWORD *__fastcall VmbusTlFindAndReferenceWildcardDescriptor(__int64 a1, const void *a2)
{
  _QWORD *v2; // rsi
  _QWORD *i; // rdi
  _QWORD *v5; // rbx

  v2 = (_QWORD *)(a1 + 1416);
  for ( i = *(_QWORD **)(a1 + 1416); ; i = (_QWORD *)*i )
  {
    if ( i == v2 )
      return 0;
    v5 = i - 12;
    if ( !memcmp(i + 2, a2, 0x10u) )
      break;
  }
  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (unsigned int)"VmbusTlFindAndReferenceWildcardDescriptor",
      102,
      (_DWORD)i - 96,
      v5[1],
      (__int64)"Reference object");
  if ( _InterlockedIncrement64(v5 + 1) <= 1 )
    __fastfail(0xEu);
  return v5;
}

```

## disassembly

```asm
0x14002672c  push    rbx
0x14002672e  push    rbp
0x14002672f  push    rsi
0x140026730  push    rdi
0x140026731  sub     rsp, 38h
0x140026735  lea     rsi, [rcx+588h]
0x14002673c  mov     rbp, rdx
0x14002673f  mov     rdi, [rsi]
0x140026742  jmp     short loc_140026761
0x140026744  lea     rbx, [rdi-60h]
0x140026748  mov     r8d, 10h; Size
0x14002674e  lea     rcx, [rbx+70h]; Buf1
0x140026752  mov     rdx, rbp; Buf2
0x140026755  call    memcmp
0x14002675a  test    eax, eax
0x14002675c  jz      short loc_140026775
0x14002675e  mov     rdi, [rdi]
0x140026761  cmp     rdi, rsi
0x140026764  jnz     short loc_140026744
0x140026766  xor     ebx, ebx
0x140026768  mov     rax, rbx
0x14002676b  add     rsp, 38h
0x14002676f  pop     rdi
0x140026770  pop     rsi
0x140026771  pop     rbp
0x140026772  pop     rbx
0x140026773  retn
0x140026775  mov     eax, cs:dword_140013058
0x14002677b  cmp     eax, 5
0x14002677e  jbe     short loc_1400267A4
0x140026780  mov     r9, [rbx+8]
0x140026784  lea     rax, aReferenceObjec; "Reference object"
0x14002678b  mov     r8, rbx
0x14002678e  mov     [rsp+58h+var_38], rax
0x140026793  mov     edx, 66h ; 'f'
0x140026798  lea     rcx, aVmbustlfindand; "VmbusTlFindAndReferenceWildcardDescript"...
0x14002679f  call    HvsocketTraceReferenceCount
0x1400267a4  mov     eax, 1
0x1400267a9  lock xadd [rbx+8], rax
0x1400267af  inc     rax
0x1400267b2  cmp     rax, 1
0x1400267b6  jg      short loc_140026768
0x1400267b8  mov     ecx, 0Eh
0x1400267bd  int     29h; Win8: RtlFailFast(ecx)
0x1400267bf  jmp     short loc_140026768
```
