# VmbusTlFindAndReferenceWildcardDescriptor

- ea: `0x1400267cc`
- end: `0x140026861`
- name: `VmbusTlFindAndReferenceWildcardDescriptor`
- size: `149`
- prototype: `_QWORD *__fastcall(__int64, const void *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140006be0`

## callees

- `0x14000a048`
- `0x14000c0a0`
- `0x1400267cc`

## string_xrefs

- `0x140026838`: `VmbusTlFindAndReferenceWildcardDescriptor`

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
      (const int *)"VmbusTlFindAndReferenceWildcardDescriptor",
      102,
      (__int64)(i - 12),
      v5[1],
      (const int *)"Reference object");
  if ( _InterlockedIncrement64(v5 + 1) <= 1 )
    __fastfail(0xEu);
  return v5;
}

```

## disassembly

```asm
0x1400267cc  push    rbx
0x1400267ce  push    rbp
0x1400267cf  push    rsi
0x1400267d0  push    rdi
0x1400267d1  sub     rsp, 38h
0x1400267d5  lea     rsi, [rcx+588h]
0x1400267dc  mov     rbp, rdx
0x1400267df  mov     rdi, [rsi]
0x1400267e2  jmp     short loc_140026801
0x1400267e4  lea     rbx, [rdi-60h]
0x1400267e8  mov     r8d, 10h; Size
0x1400267ee  lea     rcx, [rbx+70h]; Buf1
0x1400267f2  mov     rdx, rbp; Buf2
0x1400267f5  call    memcmp
0x1400267fa  test    eax, eax
0x1400267fc  jz      short loc_140026815
0x1400267fe  mov     rdi, [rdi]
0x140026801  cmp     rdi, rsi
0x140026804  jnz     short loc_1400267E4
0x140026806  xor     ebx, ebx
0x140026808  mov     rax, rbx
0x14002680b  add     rsp, 38h
0x14002680f  pop     rdi
0x140026810  pop     rsi
0x140026811  pop     rbp
0x140026812  pop     rbx
0x140026813  retn
0x140026815  mov     eax, cs:dword_140013058
0x14002681b  cmp     eax, 5
0x14002681e  jbe     short loc_140026844
0x140026820  mov     r9, [rbx+8]
0x140026824  lea     rax, aReferenceObjec; "Reference object"
0x14002682b  mov     r8, rbx
0x14002682e  mov     [rsp+58h+var_38], rax
0x140026833  mov     edx, 66h ; 'f'
0x140026838  lea     rcx, aVmbustlfindand; "VmbusTlFindAndReferenceWildcardDescript"...
0x14002683f  call    HvsocketTraceReferenceCount
0x140026844  mov     eax, 1
0x140026849  lock xadd [rbx+8], rax
0x14002684f  inc     rax
0x140026852  cmp     rax, 1
0x140026856  jg      short loc_140026808
0x140026858  mov     ecx, 0Eh
0x14002685d  int     29h; Win8: RtlFailFast(ecx)
0x14002685f  jmp     short loc_140026808
```
