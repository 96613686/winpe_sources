# Compress

- ea: `0x180001c98`
- end: `0x180001dc9`
- name: `Compress`
- size: `305`
- prototype: `HRESULT __stdcall(PVOID context, const BYTE *input_buffer, LONG input_buffer_size, PBYTE output_buffer, LONG output_buffer_size, PLONG input_used, PLONG output_used, INT compression_level)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180002710`

## callees

- `0x180001c98`
- `0x1800021c4`
- `0x180003f55`

## pseudocode

```c
HRESULT __stdcall Compress(
        PVOID context,
        const BYTE *input_buffer,
        LONG input_buffer_size,
        PBYTE output_buffer,
        LONG output_buffer_size,
        PLONG input_used,
        PLONG output_used,
        INT compression_level)
{
  const void *v10; // rsi
  const void *v11; // rbp
  int v12; // r15d
  size_t v13; // r14
  _DWORD *v14; // rax
  _DWORD *v15; // rax
  _DWORD *v16; // rax

  HPConvertToSSYUV(context, *((_QWORD *)input_buffer + 3), *((_QWORD *)input_buffer + 4), output_buffer);
  v10 = (const void *)*((_QWORD *)context + 7);
  v11 = (const void *)*((_QWORD *)context + 8);
  v12 = *((unsigned __int16 *)context + 3) * *((unsigned __int16 *)context + 4);
  v13 = v12 / 4;
  memcpy_0(*((void **)input_buffer + 2), *((const void **)context + 6), v12);
  memcpy_0((void *)(v12 + *((_QWORD *)input_buffer + 2)), v10, v13);
  memcpy_0((void *)(v12 + v13 + *((_QWORD *)input_buffer + 2)), v11, v13);
  **((_DWORD **)input_buffer + 1) = 40;
  *(_DWORD *)(*((_QWORD *)input_buffer + 1) + 16LL) = 1448433993;
  *(_WORD *)(*((_QWORD *)input_buffer + 1) + 12LL) = 1;
  *(_WORD *)(*((_QWORD *)input_buffer + 1) + 14LL) = 24;
  *(_DWORD *)(*((_QWORD *)input_buffer + 1) + 4LL) = *((unsigned __int16 *)context + 42);
  *(_DWORD *)(*((_QWORD *)input_buffer + 1) + 8LL) = *((unsigned __int16 *)context + 43);
  *(_DWORD *)(*((_QWORD *)input_buffer + 1) + 20LL) = v12 + 2 * v13;
  *(_DWORD *)(*((_QWORD *)input_buffer + 1) + 32LL) = 0;
  *(_DWORD *)(*((_QWORD *)input_buffer + 1) + 36LL) = 0;
  v14 = (_DWORD *)*((_QWORD *)input_buffer + 5);
  if ( v14 )
    *v14 = 22857;
  v15 = (_DWORD *)*((_QWORD *)input_buffer + 6);
  if ( v15 )
    *v15 = 16;
  v16 = (_DWORD *)*((_QWORD *)input_buffer + 6);
  if ( v16 )
    *v16 = 16;
  return 0;
}

```

## disassembly

```asm
0x180001c98  push    rbx
0x180001c9a  push    rbp
0x180001c9b  push    rsi
0x180001c9c  push    rdi
0x180001c9d  push    r12
0x180001c9f  push    r13
0x180001ca1  push    r14
0x180001ca3  push    r15
0x180001ca5  sub     rsp, 28h
0x180001ca9  mov     r8, [rdx+20h]
0x180001cad  mov     r12, rdx
0x180001cb0  mov     rdx, [rdx+18h]
0x180001cb4  mov     r13, rcx
0x180001cb7  call    HPConvertToSSYUV
0x180001cbc  movzx   eax, word ptr [r13+6]
0x180001cc1  movzx   r15d, word ptr [r13+8]
0x180001cc6  mov     rcx, [r12+10h]; void *
0x180001ccb  mov     rsi, [r13+38h]
0x180001ccf  mov     rbp, [r13+40h]
0x180001cd3  imul    r15d, eax
0x180001cd7  mov     eax, r15d
0x180001cda  movsxd  rdi, r15d
0x180001cdd  cdq
0x180001cde  mov     r8, rdi; Size
0x180001ce1  and     edx, 3
0x180001ce4  add     eax, edx
0x180001ce6  mov     rdx, [r13+30h]; Src
0x180001cea  sar     eax, 2
0x180001ced  movsxd  r14, eax
0x180001cf0  call    memcpy_0
0x180001cf5  mov     rcx, [r12+10h]
0x180001cfa  mov     r8, r14; Size
0x180001cfd  add     rcx, rdi; void *
0x180001d00  mov     rdx, rsi; Src
0x180001d03  call    memcpy_0
0x180001d08  mov     rcx, [r12+10h]
0x180001d0d  mov     r8, r14; Size
0x180001d10  add     rcx, r14
0x180001d13  mov     rdx, rbp; Src
0x180001d16  add     rcx, rdi; void *
0x180001d19  call    memcpy_0
0x180001d1e  mov     rax, [r12+8]
0x180001d23  mov     dword ptr [rax], 28h ; '('
0x180001d29  mov     rax, [r12+8]
0x180001d2e  mov     dword ptr [rax+10h], 56555949h
0x180001d35  mov     rax, [r12+8]
0x180001d3a  mov     word ptr [rax+0Ch], 1
0x180001d40  mov     rax, [r12+8]
0x180001d45  mov     word ptr [rax+0Eh], 18h
0x180001d4b  mov     rax, [r12+8]
0x180001d50  movzx   ecx, word ptr [r13+54h]
0x180001d55  mov     [rax+4], ecx
0x180001d58  mov     rax, [r12+8]
0x180001d5d  movzx   ecx, word ptr [r13+56h]
0x180001d62  mov     [rax+8], ecx
0x180001d65  lea     ecx, [r15+r14*2]
0x180001d69  mov     rax, [r12+8]
0x180001d6e  mov     [rax+14h], ecx
0x180001d71  mov     rax, [r12+8]
0x180001d76  mov     dword ptr [rax+20h], 0
0x180001d7d  mov     rax, [r12+8]
0x180001d82  mov     dword ptr [rax+24h], 0
0x180001d89  mov     rax, [r12+28h]
0x180001d8e  test    rax, rax
0x180001d91  jz      short loc_180001D99
0x180001d93  mov     dword ptr [rax], 5949h
0x180001d99  mov     rax, [r12+30h]
0x180001d9e  mov     ecx, 10h
0x180001da3  test    rax, rax
0x180001da6  jz      short loc_180001DAA
0x180001da8  mov     [rax], ecx
0x180001daa  mov     rax, [r12+30h]
0x180001daf  test    rax, rax
0x180001db2  jz      short loc_180001DB6
0x180001db4  mov     [rax], ecx
0x180001db6  xor     eax, eax
0x180001db8  add     rsp, 28h
0x180001dbc  pop     r15
0x180001dbe  pop     r14
0x180001dc0  pop     r13
0x180001dc2  pop     r12
0x180001dc4  pop     rdi
0x180001dc5  pop     rsi
0x180001dc6  pop     rbp
0x180001dc7  pop     rbx
0x180001dc8  retn
```
