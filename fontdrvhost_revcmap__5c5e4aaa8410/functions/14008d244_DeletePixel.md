# DeletePixel

- ea: `0x14008d244`
- end: `0x14008d2c1`
- name: `DeletePixel`
- size: `125`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14008d2c8`

## callees

- `0x1400675a0`
- `0x14008d244`

## pseudocode

```c
__int64 __fastcall DeletePixel(__int64 a1, int a2)
{
  __int64 result; // rax
  _WORD *v3; // rdi

  result = (unsigned int)*(__int16 *)(a1 + 2);
  v3 = (_WORD *)a1;
  if ( a2 == (_DWORD)result )
  {
    if ( (*(_WORD *)a1 & 0x200) != 0 )
      result = os_raise(0xFFFFFFFFLL, 0);
    ++v3[1];
  }
  else
  {
    v3 = *(_WORD **)(a1 + 8);
    result = (unsigned int)((__int16)v3[1] - 1);
    if ( a2 != (_DWORD)result )
      result = os_raise(0xFFFFFFFFLL, 0);
    if ( (*v3 & 0x200) != 0 )
      result = os_raise(0xFFFFFFFFLL, 0);
    --v3[1];
  }
  *v3 |= 0x200u;
  return result;
}

```

## disassembly

```asm
0x14008d244  mov     [rsp+arg_0], rbx
0x14008d249  mov     [rsp+arg_8], rsi
0x14008d24e  push    rdi
0x14008d24f  sub     rsp, 20h
0x14008d253  movsx   eax, word ptr [rcx+2]
0x14008d257  mov     rdi, rcx
0x14008d25a  cmp     edx, eax
0x14008d25c  jnz     short loc_14008D27D
0x14008d25e  mov     esi, 200h
0x14008d263  test    [rcx], si
0x14008d266  jz      short loc_14008D272
0x14008d268  or      ecx, 0FFFFFFFFh
0x14008d26b  xor     edx, edx
0x14008d26d  call    os_raise
0x14008d272  mov     ecx, 1
0x14008d277  add     [rdi+2], cx
0x14008d27b  jmp     short loc_14008D2AE
0x14008d27d  mov     rdi, [rcx+8]
0x14008d281  or      ebx, 0FFFFFFFFh
0x14008d284  movsx   eax, word ptr [rdi+2]
0x14008d288  dec     eax
0x14008d28a  cmp     edx, eax
0x14008d28c  jz      short loc_14008D297
0x14008d28e  xor     edx, edx
0x14008d290  mov     ecx, ebx
0x14008d292  call    os_raise
0x14008d297  mov     esi, 200h
0x14008d29c  test    [rdi], si
0x14008d29f  jz      short loc_14008D2AA
0x14008d2a1  xor     edx, edx
0x14008d2a3  mov     ecx, ebx
0x14008d2a5  call    os_raise
0x14008d2aa  add     [rdi+2], bx
0x14008d2ae  or      [rdi], si
0x14008d2b1  mov     rsi, [rsp+28h+arg_8]
0x14008d2b6  mov     rbx, [rsp+28h+arg_0]
0x14008d2bb  add     rsp, 20h
0x14008d2bf  pop     rdi
0x14008d2c0  retn
```
