# lldpCopyTlvToMib

- ea: `0x140003e60`
- end: `0x140003f0d`
- name: `lldpCopyTlvToMib`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140001690`

## callees

- `0x140003e60`
- `0x140006840`

## pseudocode

```c
char *__fastcall lldpCopyTlvToMib(__int64 a1, unsigned int a2, __int64 a3, unsigned int a4)
{
  __int64 v5; // r10
  __int64 v6; // r11
  __int16 v7; // dx
  _WORD *v8; // r9
  size_t v9; // r8
  char *result; // rax

  if ( a2 >= 2 )
  {
    v5 = a2;
    v6 = a3 + 20LL * a4;
    v7 = a2 - 2;
    *(_WORD *)a1 ^= (*(_WORD *)a1 ^ (2 * *(_WORD *)(v6 + 4))) & 0xFE;
    v8 = (_WORD *)(a1 + 2);
    *(_BYTE *)(a1 + 1) = v7;
    *(_WORD *)a1 ^= ((unsigned __int8)*(_WORD *)a1 ^ HIBYTE(v7)) & 1;
    if ( *(_WORD *)(v6 + 4) == 127 )
    {
      *v8 = *(_WORD *)(v6 + 8);
      *(_BYTE *)(a1 + 4) = *(_BYTE *)(v6 + 10);
      v8 = (_WORD *)(a1 + 6);
      *(_BYTE *)(a1 + 5) = *(_BYTE *)(v6 + 11);
    }
    v9 = *(unsigned __int16 *)(v6 + 12);
    result = (char *)v8 + v9;
    if ( (unsigned __int64)v8 + v9 <= a1 + v5 )
      return (char *)memmove(v8, (const void *)(a3 + *(unsigned int *)(v6 + 16)), v9);
  }
  return result;
}

```

## disassembly

```asm
0x140003e60  cmp     edx, 2
0x140003e63  jb      locret_140003F0B
0x140003e69  push    rbx
0x140003e6a  sub     rsp, 20h
0x140003e6e  mov     eax, r9d
0x140003e71  mov     rbx, r8
0x140003e74  mov     r10d, edx
0x140003e77  mov     edx, 0FEh
0x140003e7c  lea     r9, [rax+rax*4]
0x140003e80  movzx   eax, word ptr [rcx]
0x140003e83  lea     r11, [r8+r9*4]
0x140003e87  movzx   r9d, word ptr [r8+r9*4+4]
0x140003e8d  add     r9w, r9w
0x140003e91  xor     r9w, ax
0x140003e95  and     r9w, dx
0x140003e99  lea     edx, [r10-2]
0x140003e9d  xor     r9w, ax
0x140003ea1  mov     [rcx], r9w
0x140003ea5  lea     r9, [rcx+2]
0x140003ea9  mov     [rcx+1], dl
0x140003eac  movzx   eax, word ptr [rcx]
0x140003eaf  shr     edx, 8
0x140003eb2  xor     dx, ax
0x140003eb5  and     dx, 1
0x140003eb9  xor     dx, ax
0x140003ebc  mov     [rcx], dx
0x140003ebf  cmp     word ptr [r11+4], 7Fh
0x140003ec5  jnz     short loc_140003EE5
0x140003ec7  movzx   eax, word ptr [r11+8]
0x140003ecc  mov     [r9], ax
0x140003ed0  movzx   eax, byte ptr [r11+0Ah]
0x140003ed5  mov     [r9+2], al
0x140003ed9  lea     r9, [rcx+6]
0x140003edd  movzx   eax, byte ptr [r11+0Bh]
0x140003ee2  mov     [rcx+5], al
0x140003ee5  movzx   r8d, word ptr [r11+0Ch]; Size
0x140003eea  lea     rdx, [rcx+r10]
0x140003eee  lea     rax, [r8+r9]
0x140003ef2  cmp     rax, rdx
0x140003ef5  ja      short loc_140003F06
0x140003ef7  mov     edx, [r11+10h]
0x140003efb  mov     rcx, r9; void *
0x140003efe  add     rdx, rbx; Src
0x140003f01  call    memmove
0x140003f06  add     rsp, 20h
0x140003f0a  pop     rbx
0x140003f0b  retn
```
