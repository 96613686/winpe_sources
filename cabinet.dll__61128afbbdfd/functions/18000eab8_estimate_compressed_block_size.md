# estimate_compressed_block_size

- ea: `0x18000eab8`
- end: `0x18000eb7a`
- name: `estimate_compressed_block_size`
- size: `194`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001870`
- `0x18000e558`

## callees

- `0x18000eab8`

## pseudocode

```c
__int64 __fastcall estimate_compressed_block_size(__int64 a1)
{
  int v2; // r8d
  __int64 i; // rcx
  int v4; // edx
  int v5; // eax
  unsigned int v6; // r11d
  unsigned __int8 j; // r10
  int v8; // edi
  int v9; // ebx
  __int64 v10; // rax
  __int64 k; // rdx
  int v12; // ecx
  int v13; // eax

  v2 = 1200;
  for ( i = 0; i != 256; ++i )
  {
    v4 = *(unsigned __int16 *)(a1 + 2 * i + 10560);
    v5 = *(unsigned __int8 *)(a1 + i + 9608);
    v2 += v5 * v4;
  }
  v6 = *(_DWORD *)(a1 + 2208);
  for ( j = 0; j < v6; ++j )
  {
    v8 = 8;
    v9 = 8 * j + 256;
    do
    {
      v10 = v9++;
      v2 += ((unsigned __int8)dec_extra_bits[j] + *(unsigned __int8 *)(v10 + a1 + 9608))
          * *(unsigned __int16 *)(a1 + 2 * v10 + 10560);
      --v8;
    }
    while ( v8 );
  }
  for ( k = 0; k != 249; ++k )
  {
    v12 = *(unsigned __int16 *)(a1 + 2 * k + 15462);
    v13 = *(unsigned __int8 *)(a1 + k + 10309);
    v2 += v13 * v12;
  }
  return (unsigned int)(v2 + 7) >> 3;
}

```

## disassembly

```asm
0x18000eab8  push    rbx
0x18000eaba  push    rsi
0x18000eabb  push    rdi
0x18000eabc  mov     r9, rcx
0x18000eabf  mov     r8d, 4B0h
0x18000eac5  xor     ecx, ecx
0x18000eac7  movzx   edx, word ptr [r9+rcx*2+2940h]
0x18000ead0  movzx   eax, byte ptr [r9+rcx+2588h]
0x18000ead9  inc     rcx
0x18000eadc  imul    edx, eax
0x18000eadf  add     r8d, edx
0x18000eae2  cmp     rcx, 100h
0x18000eae9  jnz     short loc_18000EAC7
0x18000eaeb  mov     r11d, [r9+8A0h]
0x18000eaf2  xor     r10b, r10b
0x18000eaf5  test    r11d, r11d
0x18000eaf8  jz      short loc_18000EB49
0x18000eafa  movzx   eax, r10b
0x18000eafe  lea     rcx, dec_extra_bits
0x18000eb05  mov     edi, 8
0x18000eb0a  lea     ebx, ds:100h[rax*8]
0x18000eb11  movzx   eax, r10b
0x18000eb15  movzx   esi, byte ptr [rax+rcx]
0x18000eb19  movsxd  rax, ebx
0x18000eb1c  inc     ebx
0x18000eb1e  movzx   ecx, byte ptr [rax+r9+2588h]
0x18000eb27  movzx   edx, word ptr [r9+rax*2+2940h]
0x18000eb30  add     ecx, esi
0x18000eb32  imul    edx, ecx
0x18000eb35  add     r8d, edx
0x18000eb38  sub     edi, 1
0x18000eb3b  jnz     short loc_18000EB19
0x18000eb3d  inc     r10b
0x18000eb40  movzx   eax, r10b
0x18000eb44  cmp     eax, r11d
0x18000eb47  jb      short loc_18000EAFA
0x18000eb49  xor     edx, edx
0x18000eb4b  movzx   ecx, word ptr [r9+rdx*2+3C66h]
0x18000eb54  movzx   eax, byte ptr [r9+rdx+2845h]
0x18000eb5d  inc     rdx
0x18000eb60  imul    ecx, eax
0x18000eb63  add     r8d, ecx
0x18000eb66  cmp     rdx, 0F9h
0x18000eb6d  jnz     short loc_18000EB4B
0x18000eb6f  lea     eax, [r8+7]
0x18000eb73  shr     eax, 3
0x18000eb76  pop     rdi
0x18000eb77  pop     rsi
0x18000eb78  pop     rbx
0x18000eb79  retn
```
