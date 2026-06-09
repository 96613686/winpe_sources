# RleCompressGetFormat

- ea: `0x18000249c`
- end: `0x180002574`
- name: `RleCompressGetFormat`
- size: `216`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001cd0`

## callees

- `0x18000249c`
- `0x180003768`

## pseudocode

```c
__int64 __fastcall RleCompressGetFormat(__int64 a1, unsigned int *a2, __int64 a3)
{
  unsigned int v4; // ecx
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // rax

  if ( !a2 || *((_WORD *)a2 + 7) != 8 || a2[4] )
    return 4294967294LL;
  v4 = a2[8];
  if ( v4 )
  {
    if ( v4 > 0x100 )
      return 4294967294LL;
  }
  else
  {
    v4 = 256;
  }
  if ( !a3 )
    return 4 * v4 + 40;
  if ( *a2 >= 0x28 )
  {
    *(_OWORD *)a3 = *(_OWORD *)a2;
    *(_OWORD *)(a3 + 16) = *((_OWORD *)a2 + 1);
    *(_QWORD *)(a3 + 32) = *((_QWORD *)a2 + 4);
    *(_DWORD *)a3 = 40;
    *(_WORD *)(a3 + 14) = 8;
    *(_DWORD *)(a3 + 16) = 1;
    v6 = a2[1] * (unsigned __int64)a2[2];
    if ( v6 > 0xFFFFFFFF || (v7 = 2LL * (unsigned int)v6, v7 > 0xFFFFFFFF) )
      LODWORD(v7) = -1;
    *(_DWORD *)(a3 + 20) = v7;
    if ( (_DWORD)v7 != -1 )
    {
      memcpy_0((void *)(a3 + 40), (char *)a2 + *a2, 4LL * v4);
      return 0;
    }
  }
  return 4294967294LL;
}

```

## disassembly

```asm
0x18000249c  sub     rsp, 28h
0x1800024a0  mov     r10, r8
0x1800024a3  mov     r9, rdx
0x1800024a6  test    rdx, rdx
0x1800024a9  jz      loc_18000256A
0x1800024af  mov     eax, 8
0x1800024b4  cmp     [rdx+0Eh], ax
0x1800024b8  jnz     loc_18000256A
0x1800024be  cmp     dword ptr [rdx+10h], 0
0x1800024c2  jnz     loc_18000256A
0x1800024c8  mov     ecx, [rdx+20h]
0x1800024cb  test    ecx, ecx
0x1800024cd  jnz     short loc_1800024D6
0x1800024cf  mov     ecx, 100h
0x1800024d4  jmp     short loc_1800024E2
0x1800024d6  cmp     ecx, 100h
0x1800024dc  ja      loc_18000256A
0x1800024e2  test    r10, r10
0x1800024e5  jnz     short loc_1800024F0
0x1800024e7  lea     eax, ds:28h[rcx*4]
0x1800024ee  jmp     short loc_18000256F
0x1800024f0  cmp     dword ptr [rdx], 28h ; '('
0x1800024f3  jb      short loc_18000256A
0x1800024f5  movups  xmm0, xmmword ptr [rdx]
0x1800024f8  movups  xmmword ptr [r8], xmm0
0x1800024fc  movups  xmm1, xmmword ptr [rdx+10h]
0x180002500  movups  xmmword ptr [r8+10h], xmm1
0x180002505  movsd   xmm0, qword ptr [rdx+20h]
0x18000250a  movsd   qword ptr [r8+20h], xmm0
0x180002510  mov     dword ptr [r8], 28h ; '('
0x180002517  mov     [r8+0Eh], ax
0x18000251c  mov     dword ptr [r8+10h], 1
0x180002524  mov     r8d, 0FFFFFFFFh
0x18000252a  mov     edx, [rdx+8]
0x18000252d  mov     eax, [r9+4]
0x180002531  imul    rdx, rax
0x180002535  cmp     rdx, r8
0x180002538  ja      short loc_180002544
0x18000253a  mov     eax, edx
0x18000253c  add     rax, rax
0x18000253f  cmp     rax, r8
0x180002542  jbe     short loc_180002547
0x180002544  mov     eax, r8d
0x180002547  mov     [r10+14h], eax
0x18000254b  cmp     eax, r8d
0x18000254e  jz      short loc_18000256A
0x180002550  mov     edx, [r9]
0x180002553  mov     r8d, ecx
0x180002556  add     rdx, r9; Src
0x180002559  shl     r8, 2; Size
0x18000255d  lea     rcx, [r10+28h]; void *
0x180002561  call    memcpy_0
0x180002566  xor     eax, eax
0x180002568  jmp     short loc_18000256F
0x18000256a  mov     eax, 0FFFFFFFEh
0x18000256f  add     rsp, 28h
0x180002573  retn
```
