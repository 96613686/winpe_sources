# ASN1BEREncCharString

- ea: `0x1800072a0`
- end: `0x1800072fb`
- name: `ASN1BEREncCharString`
- size: `91`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x1800066a0`
- `0x1800067c0`
- `0x180006b00`
- `0x180006f20`
- `0x18000a140`
- `0x18000a1a0`

## callees

- `0x1800072a0`
- `0x180007b80`
- `0x180007e40`
- `0x18000aadd`

## pseudocode

```c
__int64 __fastcall ASN1BEREncCharString(__int64 a1, unsigned int a2, unsigned int a3, const void *a4)
{
  __int64 v5; // rbx

  v5 = a3;
  if ( !(unsigned int)ASN1BEREncTag(a1, a2) || !(unsigned int)ASN1BEREncLength(a1, v5) )
    return 0;
  memcpy_0(*(void **)(a1 + 40), a4, (unsigned int)v5);
  *(_QWORD *)(a1 + 40) += v5;
  return 1;
}

```

## disassembly

```asm
0x1800072a0  mov     [rsp+arg_0], rbx; ASN1BEREncCharString
0x1800072a5  mov     [rsp+arg_8], rsi
0x1800072aa  push    rdi
0x1800072ab  sub     rsp, 20h
0x1800072af  mov     rsi, r9
0x1800072b2  mov     ebx, r8d
0x1800072b5  mov     rdi, rcx
0x1800072b8  call    ASN1BEREncTag
0x1800072bd  test    eax, eax
0x1800072bf  jz      short loc_1800072F7
0x1800072c1  mov     edx, ebx
0x1800072c3  mov     rcx, rdi
0x1800072c6  call    ASN1BEREncLength
0x1800072cb  test    eax, eax
0x1800072cd  jz      short loc_1800072F7
0x1800072cf  mov     rcx, [rdi+28h]; void *
0x1800072d3  mov     r8d, ebx; Size
0x1800072d6  mov     rdx, rsi; Src
0x1800072d9  call    memcpy_0
0x1800072de  add     [rdi+28h], rbx
0x1800072e2  mov     eax, 1
0x1800072e7  mov     rbx, [rsp+28h+arg_0]
0x1800072ec  mov     rsi, [rsp+28h+arg_8]
0x1800072f1  add     rsp, 20h
0x1800072f5  pop     rdi
0x1800072f6  retn
0x1800072f7  xor     eax, eax
0x1800072f9  jmp     short loc_1800072E7
```
