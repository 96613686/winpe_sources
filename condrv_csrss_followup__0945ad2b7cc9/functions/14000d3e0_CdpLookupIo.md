# CdpLookupIo

- ea: `0x14000d3e0`
- end: `0x14000d433`
- name: `CdpLookupIo`
- size: `83`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000ca90`
- `0x14000cc10`
- `0x14000cd40`

## callees

- `0x14000d3e0`

## pseudocode

```c
_QWORD *__fastcall CdpLookupIo(__int64 a1, unsigned int *a2)
{
  int v2; // r9d
  _QWORD **v4; // r10
  _QWORD *i; // rdx
  _QWORD *result; // rax

  v2 = *a2;
  v4 = (_QWORD **)(a1 + 16 * (*a2 % 5uLL));
  for ( i = *v4; i != v4; i = (_QWORD *)*i )
  {
    result = i - 21;
    if ( *((_DWORD *)i - 8) == v2 && *((_DWORD *)result + 35) == a2[1] )
      return result;
  }
  return 0;
}

```

## disassembly

```asm
0x14000d3e0  mov     r9d, [rdx]
0x14000d3e3  mov     r11, rdx
0x14000d3e6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x14000d3f0  mov     r10d, r9d
0x14000d3f3  mul     r9
0x14000d3f6  shr     rdx, 2
0x14000d3fa  lea     rax, [rdx+rdx*4]
0x14000d3fe  sub     r10, rax
0x14000d401  shl     r10, 4
0x14000d405  add     r10, rcx
0x14000d408  mov     rdx, [r10]
0x14000d40b  cmp     rdx, r10
0x14000d40e  jz      short loc_14000D430
0x14000d410  cmp     [rdx-20h], r9d
0x14000d414  lea     rax, [rdx-0A8h]
0x14000d41b  jnz     short loc_14000D42B
0x14000d41d  mov     ecx, [r11+4]
0x14000d421  cmp     [rax+8Ch], ecx
0x14000d427  jnz     short loc_14000D42B
0x14000d429  retn
0x14000d42b  mov     rdx, [rdx]
0x14000d42e  jmp     short loc_14000D40B
0x14000d430  xor     eax, eax
0x14000d432  retn
```
