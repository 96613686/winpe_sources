# ComputeFlushPeriod

- ea: `0x180001fd0`
- end: `0x18000221c`
- name: `ComputeFlushPeriod`
- size: `588`
- prototype: `__int64 __fastcall(unsigned __int64)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001e20`

## pseudocode

```c
__int64 __fastcall ComputeFlushPeriod(unsigned __int64 a1)
{
  __int64 v1; // r10
  unsigned int v2; // eax
  unsigned int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax

  v1 = *(_QWORD *)(*(_QWORD *)(a1 + 328) + 8LL);
  v2 = 1025
     * (*(unsigned __int8 *)(v1 - 13)
      + ((1025
        * (*(unsigned __int8 *)(v1 - 14)
         + ((1025
           * (*(unsigned __int8 *)(v1 - 15)
            + ((1025 * *(unsigned __int8 *)(v1 - 16)) ^ ((1025 * (unsigned int)*(unsigned __int8 *)(v1 - 16)) >> 6))))
          ^ ((1025
            * (*(unsigned __int8 *)(v1 - 15)
             + ((1025 * *(unsigned __int8 *)(v1 - 16)) ^ ((1025 * (unsigned int)*(unsigned __int8 *)(v1 - 16)) >> 6)))) >> 6))))
       ^ ((1025
         * (*(unsigned __int8 *)(v1 - 14)
          + ((1025
            * (*(unsigned __int8 *)(v1 - 15)
             + ((1025 * *(unsigned __int8 *)(v1 - 16)) ^ ((1025 * (unsigned int)*(unsigned __int8 *)(v1 - 16)) >> 6))))
           ^ ((1025
             * (*(unsigned __int8 *)(v1 - 15)
              + ((1025 * *(unsigned __int8 *)(v1 - 16)) ^ ((1025 * (unsigned int)*(unsigned __int8 *)(v1 - 16)) >> 6)))) >> 6)))) >> 6)));
  v3 = 1025 * (*(unsigned __int8 *)(v1 - 12) + (v2 ^ (v2 >> 6)));
  v4 = 1025 * (*(unsigned __int8 *)(v1 - 11) + (v3 ^ (v3 >> 6)));
  v5 = 1025 * (*(unsigned __int8 *)(v1 - 10) + (v4 ^ (v4 >> 6)));
  v6 = 1025 * (*(unsigned __int8 *)(v1 - 9) + (v5 ^ (v5 >> 6)));
  v7 = 1025 * (*(unsigned __int8 *)(v1 - 8) + (v6 ^ (v6 >> 6)));
  v8 = 1025 * (*(unsigned __int8 *)(v1 - 7) + (v7 ^ (v7 >> 6)));
  v9 = 1025 * (*(unsigned __int8 *)(v1 - 6) + (v8 ^ (v8 >> 6)));
  v10 = 1025 * (*(unsigned __int8 *)(v1 - 5) + (v9 ^ (v9 >> 6)));
  v11 = 1025 * (*(unsigned __int8 *)(v1 - 4) + (v10 ^ (v10 >> 6)));
  v12 = 1025 * (*(unsigned __int8 *)(v1 - 3) + (v11 ^ (v11 >> 6)));
  v13 = 1025 * (*(unsigned __int8 *)(v1 - 2) + (v12 ^ (v12 >> 6)));
  v14 = 1025 * (*(unsigned __int8 *)(v1 - 1) + (v13 ^ (v13 >> 6)));
  v15 = 1025 * ((unsigned __int8)(a1 >> 4) + (v14 ^ (v14 >> 6)));
  v16 = 1025
      * ((unsigned __int8)(a1 >> 20)
       + ((1025 * ((unsigned __int8)(a1 >> 12) + (v15 ^ (v15 >> 6))))
        ^ ((1025 * ((unsigned __int8)(a1 >> 12) + (v15 ^ (v15 >> 6)))) >> 6)));
  v17 = 1025
      * ((unsigned __int8)(a1 >> 36)
       + ((1025 * ((unsigned __int8)(a1 >> 28) + (v16 ^ (v16 >> 6))))
        ^ ((1025 * ((unsigned __int8)(a1 >> 28) + (v16 ^ (v16 >> 6)))) >> 6)));
  v18 = 1025
      * ((unsigned __int8)(a1 >> 52)
       + ((1025 * ((unsigned __int8)(a1 >> 44) + (v17 ^ (v17 >> 6))))
        ^ ((1025 * ((unsigned __int8)(a1 >> 44) + (v17 ^ (v17 >> 6)))) >> 6)));
  v19 = 9 * ((1025 * ((a1 >> 60) + (v18 ^ (v18 >> 6)))) ^ ((1025 * ((a1 >> 60) + (v18 ^ (v18 >> 6)))) >> 6));
  return 32769 * (v19 ^ (v19 >> 11)) % 0x927C0 + 600000;
}

```

## disassembly

```asm
0x180001fd0  push    rbx
0x180001fd2  push    rbp
0x180001fd3  push    rsi
0x180001fd4  push    rdi
0x180001fd5  push    r14
0x180001fd7  mov     rax, [rcx+148h]
0x180001fde  mov     r14, rcx
0x180001fe1  shr     r14, 4
0x180001fe5  movzx   r8d, r14b
0x180001fe9  mov     r10, [rax+8]
0x180001fed  mov     rax, r14
0x180001ff0  shr     rax, 30h
0x180001ff4  movzx   ebp, al
0x180001ff7  mov     rax, r14
0x180001ffa  shr     rax, 28h
0x180001ffe  movzx   esi, al
0x180002001  mov     rax, r14
0x180002004  shr     rax, 20h
0x180002008  movzx   edi, al
0x18000200b  mov     rax, r14
0x18000200e  shr     rax, 18h
0x180002012  movzx   ebx, al
0x180002015  mov     rax, r14
0x180002018  shr     rax, 10h
0x18000201c  movzx   r11d, al
0x180002020  mov     rax, r14
0x180002023  shr     rax, 8
0x180002027  movzx   r9d, al
0x18000202b  movzx   eax, byte ptr [r10-10h]
0x180002030  imul    ecx, eax, 401h
0x180002036  movzx   eax, byte ptr [r10-0Fh]
0x18000203b  mov     edx, ecx
0x18000203d  shr     edx, 6
0x180002040  xor     edx, ecx
0x180002042  add     edx, eax
0x180002044  imul    eax, edx, 401h
0x18000204a  mov     ecx, eax
0x18000204c  shr     ecx, 6
0x18000204f  xor     ecx, eax
0x180002051  movzx   eax, byte ptr [r10-0Eh]
0x180002056  add     ecx, eax
0x180002058  imul    eax, ecx, 401h
0x18000205e  mov     ecx, eax
0x180002060  shr     ecx, 6
0x180002063  xor     ecx, eax
0x180002065  movzx   eax, byte ptr [r10-0Dh]
0x18000206a  add     ecx, eax
0x18000206c  imul    eax, ecx, 401h
0x180002072  mov     ecx, eax
0x180002074  shr     ecx, 6
0x180002077  xor     ecx, eax
0x180002079  movzx   eax, byte ptr [r10-0Ch]
0x18000207e  add     ecx, eax
0x180002080  imul    eax, ecx, 401h
0x180002086  mov     ecx, eax
0x180002088  shr     ecx, 6
0x18000208b  xor     ecx, eax
0x18000208d  movzx   eax, byte ptr [r10-0Bh]
0x180002092  add     ecx, eax
0x180002094  imul    eax, ecx, 401h
0x18000209a  mov     ecx, eax
0x18000209c  shr     ecx, 6
0x18000209f  xor     ecx, eax
0x1800020a1  movzx   eax, byte ptr [r10-0Ah]
0x1800020a6  add     ecx, eax
0x1800020a8  imul    eax, ecx, 401h
0x1800020ae  mov     ecx, eax
0x1800020b0  shr     ecx, 6
0x1800020b3  xor     ecx, eax
0x1800020b5  movzx   eax, byte ptr [r10-9]
0x1800020ba  add     ecx, eax
0x1800020bc  imul    eax, ecx, 401h
0x1800020c2  mov     ecx, eax
0x1800020c4  shr     ecx, 6
0x1800020c7  xor     ecx, eax
0x1800020c9  movzx   eax, byte ptr [r10-8]
0x1800020ce  add     ecx, eax
0x1800020d0  imul    eax, ecx, 401h
0x1800020d6  mov     ecx, eax
0x1800020d8  shr     ecx, 6
0x1800020db  xor     ecx, eax
0x1800020dd  movzx   eax, byte ptr [r10-7]
0x1800020e2  add     ecx, eax
0x1800020e4  imul    eax, ecx, 401h
0x1800020ea  mov     ecx, eax
0x1800020ec  shr     ecx, 6
0x1800020ef  xor     ecx, eax
0x1800020f1  shr     r14, 38h
0x1800020f5  movzx   eax, byte ptr [r10-6]
0x1800020fa  add     ecx, eax
0x1800020fc  imul    eax, ecx, 401h
0x180002102  mov     ecx, eax
0x180002104  shr     ecx, 6
0x180002107  xor     ecx, eax
0x180002109  movzx   eax, byte ptr [r10-5]
0x18000210e  add     ecx, eax
0x180002110  imul    eax, ecx, 401h
0x180002116  mov     ecx, eax
0x180002118  shr     ecx, 6
0x18000211b  xor     ecx, eax
0x18000211d  movzx   eax, byte ptr [r10-4]
0x180002122  add     ecx, eax
0x180002124  imul    eax, ecx, 401h
0x18000212a  mov     ecx, eax
0x18000212c  shr     ecx, 6
0x18000212f  xor     ecx, eax
0x180002131  movzx   eax, byte ptr [r10-3]
0x180002136  add     ecx, eax
0x180002138  imul    eax, ecx, 401h
0x18000213e  mov     ecx, eax
0x180002140  shr     ecx, 6
0x180002143  xor     ecx, eax
0x180002145  movzx   eax, byte ptr [r10-2]
0x18000214a  add     ecx, eax
0x18000214c  imul    eax, ecx, 401h
0x180002152  mov     ecx, eax
0x180002154  shr     ecx, 6
0x180002157  xor     ecx, eax
0x180002159  movzx   eax, byte ptr [r10-1]
0x18000215e  add     ecx, eax
0x180002160  imul    eax, ecx, 401h
0x180002166  mov     ecx, eax
0x180002168  shr     ecx, 6
0x18000216b  xor     ecx, eax
0x18000216d  add     ecx, r8d
0x180002170  imul    eax, ecx, 401h
0x180002176  mov     ecx, eax
0x180002178  shr     ecx, 6
0x18000217b  xor     ecx, eax
0x18000217d  add     ecx, r9d
0x180002180  imul    eax, ecx, 401h
0x180002186  mov     ecx, eax
0x180002188  shr     ecx, 6
0x18000218b  xor     ecx, eax
0x18000218d  add     ecx, r11d
0x180002190  imul    eax, ecx, 401h
0x180002196  mov     ecx, eax
0x180002198  shr     ecx, 6
0x18000219b  xor     ecx, eax
0x18000219d  add     ecx, ebx
0x18000219f  imul    eax, ecx, 401h
0x1800021a5  mov     ecx, eax
0x1800021a7  shr     ecx, 6
0x1800021aa  xor     ecx, eax
0x1800021ac  add     ecx, edi
0x1800021ae  imul    eax, ecx, 401h
0x1800021b4  mov     ecx, eax
0x1800021b6  shr     ecx, 6
0x1800021b9  xor     ecx, eax
0x1800021bb  add     ecx, esi
0x1800021bd  imul    eax, ecx, 401h
0x1800021c3  mov     ecx, eax
0x1800021c5  shr     ecx, 6
0x1800021c8  xor     ecx, eax
0x1800021ca  add     ecx, ebp
0x1800021cc  imul    eax, ecx, 401h
0x1800021d2  mov     ecx, eax
0x1800021d4  shr     ecx, 6
0x1800021d7  xor     ecx, eax
0x1800021d9  add     ecx, r14d
0x1800021dc  imul    eax, ecx, 401h
0x1800021e2  mov     ecx, eax
0x1800021e4  shr     ecx, 6
0x1800021e7  xor     ecx, eax
0x1800021e9  lea     eax, [rcx+rcx*8]
0x1800021ec  mov     ecx, eax
0x1800021ee  shr     ecx, 0Bh
0x1800021f1  xor     ecx, eax
0x1800021f3  mov     eax, 6FD91D85h
0x1800021f8  imul    r8d, ecx, 8001h
0x1800021ff  mul     r8d
0x180002202  shr     edx, 12h
0x180002205  imul    ecx, edx, 927C0h
0x18000220b  sub     r8d, ecx
0x18000220e  lea     eax, [r8+927C0h]
0x180002215  pop     r14
0x180002217  pop     rdi
0x180002218  pop     rsi
0x180002219  pop     rbp
0x18000221a  pop     rbx
0x18000221b  retn
```
