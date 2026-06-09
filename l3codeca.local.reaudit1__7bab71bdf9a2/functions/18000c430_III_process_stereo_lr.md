# III_process_stereo_lr

- ea: `0x18000c430`
- end: `0x18000c5de`
- name: `III_process_stereo_lr`
- size: `430`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c990`
- `0x18000cc80`
- `0x18000d370`

## callees

- `0x18000c430`

## pseudocode

```c
__int64 __fastcall III_process_stereo_lr(__int64 a1, __int64 a2, int a3, int a4, int a5)
{
  __int64 v5; // rdi
  int v6; // r11d
  __m128 si128; // xmm2
  __int64 result; // rax

  if ( a5 && a3 < a4 )
  {
    if ( (unsigned int)(a4 - a3) < 0x10 )
      goto LABEL_11;
    v5 = a4 - 1;
    if ( a1 + 4LL * a3 <= (unsigned __int64)(a2 + 4 * v5) && a1 + 4 * v5 >= (unsigned __int64)(a2 + 4LL * a3) )
      goto LABEL_11;
    v6 = (a4 - a3) % 16;
    si128 = (__m128)_mm_load_si128((const __m128i *)&_xmm);
    do
    {
      result = a3;
      a3 += 16;
      *(__m128 *)(a1 + 4 * result) = _mm_mul_ps(
                                       _mm_add_ps(*(__m128 *)(a2 + 4 * result), *(__m128 *)(a1 + 4 * result)),
                                       si128);
      *(__m128 *)(a1 + 4 * result + 16) = _mm_mul_ps(
                                            _mm_add_ps(
                                              *(__m128 *)(a2 + 4 * result + 16),
                                              *(__m128 *)(a1 + 4 * result + 16)),
                                            si128);
      *(__m128 *)(a1 + 4 * result + 32) = _mm_mul_ps(
                                            _mm_add_ps(
                                              *(__m128 *)(a2 + 4 * result + 32),
                                              *(__m128 *)(a1 + 4 * result + 32)),
                                            si128);
      *(__m128 *)(a1 + 4 * result + 48) = _mm_mul_ps(
                                            _mm_add_ps(
                                              *(__m128 *)(a2 + 4 * result + 48),
                                              *(__m128 *)(a1 + 4 * result + 48)),
                                            si128);
    }
    while ( a3 < a4 - v6 );
    if ( a3 < a4 )
    {
LABEL_11:
      if ( a4 - a3 < 4 )
        goto LABEL_15;
      do
      {
        result = a3;
        a3 += 4;
        *(float *)(a1 + 4 * result) = (float)(*(float *)(a2 + 4 * result) + *(float *)(a1 + 4 * result)) * 0.5;
        *(float *)(a1 + 4 * result + 4) = (float)(*(float *)(a2 + 4 * result + 4) + *(float *)(a1 + 4 * result + 4))
                                        * 0.5;
        *(float *)(a1 + 4 * result + 8) = (float)(*(float *)(a2 + 4 * result + 8) + *(float *)(a1 + 4 * result + 8))
                                        * 0.5;
        *(float *)(a1 + 4 * result + 12) = (float)(*(float *)(a2 + 4 * result + 12) + *(float *)(a1 + 4 * result + 12))
                                         * 0.5;
      }
      while ( a3 < a4 - 3 );
      if ( a3 < a4 )
      {
LABEL_15:
        do
        {
          result = a3++;
          *(float *)(a1 + 4 * result) = (float)(*(float *)(a2 + 4 * result) + *(float *)(a1 + 4 * result)) * 0.5;
        }
        while ( a3 < a4 );
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000c430  sub     rsp, 8
0x18000c434  cmp     [rsp+8+arg_20], 0
0x18000c439  mov     r10, rcx
0x18000c43c  jz      loc_18000C5D9
0x18000c442  cmp     r8d, r9d
0x18000c445  jge     loc_18000C5D9
0x18000c44b  mov     r11d, r9d
0x18000c44e  mov     [rsp+8+arg_0], rbx
0x18000c453  sub     r11d, r8d
0x18000c456  mov     [rsp+8+var_8], rdi
0x18000c45a  cmp     r11d, 10h
0x18000c45e  jb      loc_18000C51E
0x18000c464  lea     eax, [r9-1]
0x18000c468  movsxd  rbx, r8d
0x18000c46b  movsxd  rdi, eax
0x18000c46e  lea     rcx, [rcx+rbx*4]
0x18000c472  lea     rax, [rdx+rdi*4]
0x18000c476  cmp     rcx, rax
0x18000c479  ja      short loc_18000C48C
0x18000c47b  lea     rcx, [rdx+rbx*4]
0x18000c47f  lea     rax, [r10+rdi*4]
0x18000c483  cmp     rax, rcx
0x18000c486  jnb     loc_18000C51E
0x18000c48c  and     r11d, 8000000Fh
0x18000c493  jge     short loc_18000C49F
0x18000c495  dec     r11d
0x18000c498  or      r11d, 0FFFFFFF0h
0x18000c49c  inc     r11d
0x18000c49f  mov     ecx, r9d
0x18000c4a2  sub     ecx, r11d
0x18000c4a5  movdqa  xmm2, cs:__xmm@3f0000003f0000003f0000003f000000
0x18000c4ad  nop     dword ptr [rax]
0x18000c4b0  movsxd  rax, r8d
0x18000c4b3  add     r8d, 10h
0x18000c4b7  movups  xmm0, xmmword ptr [r10+rax*4]
0x18000c4bc  movups  xmm1, xmmword ptr [rdx+rax*4]
0x18000c4c0  addps   xmm1, xmm0
0x18000c4c3  mulps   xmm1, xmm2
0x18000c4c6  movups  xmmword ptr [r10+rax*4], xmm1
0x18000c4cb  movups  xmm0, xmmword ptr [r10+rax*4+10h]
0x18000c4d1  movups  xmm1, xmmword ptr [rdx+rax*4+10h]
0x18000c4d6  addps   xmm1, xmm0
0x18000c4d9  mulps   xmm1, xmm2
0x18000c4dc  movups  xmmword ptr [r10+rax*4+10h], xmm1
0x18000c4e2  movups  xmm0, xmmword ptr [r10+rax*4+20h]
0x18000c4e8  movups  xmm1, xmmword ptr [rdx+rax*4+20h]
0x18000c4ed  addps   xmm1, xmm0
0x18000c4f0  mulps   xmm1, xmm2
0x18000c4f3  movups  xmmword ptr [r10+rax*4+20h], xmm1
0x18000c4f9  movups  xmm0, xmmword ptr [r10+rax*4+30h]
0x18000c4ff  movups  xmm1, xmmword ptr [rdx+rax*4+30h]
0x18000c504  addps   xmm1, xmm0
0x18000c507  mulps   xmm1, xmm2
0x18000c50a  movups  xmmword ptr [r10+rax*4+30h], xmm1
0x18000c510  cmp     r8d, ecx
0x18000c513  jl      short loc_18000C4B0
0x18000c515  cmp     r8d, r9d
0x18000c518  jge     loc_18000C5D0
0x18000c51e  movss   xmm1, cs:__real@3f000000
0x18000c526  mov     eax, r9d
0x18000c529  sub     eax, r8d
0x18000c52c  cmp     eax, 4
0x18000c52f  jl      short loc_18000C5B0
0x18000c531  lea     ecx, [r9-3]
0x18000c535  nop     word ptr [rax+rax+00000000h]
0x18000c540  movsxd  rax, r8d
0x18000c543  add     r8d, 4
0x18000c547  movss   xmm0, dword ptr [rdx+rax*4]
0x18000c54c  addss   xmm0, dword ptr [r10+rax*4]
0x18000c552  mulss   xmm0, xmm1
0x18000c556  movss   dword ptr [r10+rax*4], xmm0
0x18000c55c  movss   xmm0, dword ptr [rdx+rax*4+4]
0x18000c562  addss   xmm0, dword ptr [r10+rax*4+4]
0x18000c569  mulss   xmm0, xmm1
0x18000c56d  movss   dword ptr [r10+rax*4+4], xmm0
0x18000c574  movss   xmm0, dword ptr [rdx+rax*4+8]
0x18000c57a  addss   xmm0, dword ptr [r10+rax*4+8]
0x18000c581  mulss   xmm0, xmm1
0x18000c585  movss   dword ptr [r10+rax*4+8], xmm0
0x18000c58c  movss   xmm0, dword ptr [rdx+rax*4+0Ch]
0x18000c592  addss   xmm0, dword ptr [r10+rax*4+0Ch]
0x18000c599  mulss   xmm0, xmm1
0x18000c59d  movss   dword ptr [r10+rax*4+0Ch], xmm0
0x18000c5a4  cmp     r8d, ecx
0x18000c5a7  jl      short loc_18000C540
0x18000c5a9  cmp     r8d, r9d
0x18000c5ac  jge     short loc_18000C5D0
0x18000c5ae  xchg    ax, ax
0x18000c5b0  movsxd  rax, r8d
0x18000c5b3  inc     r8d
0x18000c5b6  movss   xmm0, dword ptr [rdx+rax*4]
0x18000c5bb  addss   xmm0, dword ptr [r10+rax*4]
0x18000c5c1  mulss   xmm0, xmm1
0x18000c5c5  movss   dword ptr [r10+rax*4], xmm0
0x18000c5cb  cmp     r8d, r9d
0x18000c5ce  jl      short loc_18000C5B0
0x18000c5d0  mov     rbx, [rsp+8+arg_0]
0x18000c5d5  mov     rdi, [rsp+8+var_8]
0x18000c5d9  add     rsp, 8
0x18000c5dd  retn
```
