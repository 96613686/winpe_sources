# FillMemoryNonTemporal(uint *,uint,uint,uint,uint)

- ea: `0x140013c80`
- end: `0x140013d9e`
- name: `?FillMemoryNonTemporal@@YAXPEAIIIII@Z`
- size: `286`
- prototype: `void __fastcall(unsigned int *, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140013b50`

## callees

- `0x140013c80`

## pseudocode

```c
void __fastcall FillMemoryNonTemporal(unsigned __int64 a1, unsigned int a2, unsigned int a3, int a4, unsigned int a5)
{
  int v5; // ebp
  unsigned int v9; // r10d
  __m128 v10; // xmm0
  __int64 v11; // r11
  int *v12; // rax
  int v13; // edi
  int v14; // edx
  int v15; // ecx
  int v16; // r9d
  int i; // ecx
  int j; // ecx
  unsigned __int64 v19; // r8
  unsigned __int64 v20; // r9
  unsigned int *v21; // r10

  v5 = 0;
  if ( !g_SSE2InstructionsAvailable )
  {
    if ( !a3 )
      return;
    v19 = (unsigned __int64)(unsigned int)(4 * a4) >> 2;
    while ( 1 )
    {
      if ( v19 )
      {
        if ( (a1 & 4) == 0 )
        {
          v20 = v19;
          v21 = (unsigned int *)a1;
LABEL_19:
          memset64(v21, a5 | ((unsigned __int64)a5 << 32), v20 >> 1);
          if ( (v20 & 1) != 0 )
            v21[v20 - 1] = a5;
          goto LABEL_21;
        }
        v20 = v19 - 1;
        *(_DWORD *)a1 = a5;
        if ( v19 != 1 )
        {
          v21 = (unsigned int *)(a1 + 4);
          goto LABEL_19;
        }
      }
LABEL_21:
      a1 += a2;
      if ( ++v5 >= a3 )
        return;
    }
  }
  v9 = 0;
  v10 = _mm_shuffle_ps((__m128)a5, (__m128)a5, 0);
  if ( a3 )
  {
    v11 = a2;
    do
    {
      v12 = (int *)a1;
      v13 = -(int)(a1 >> 2) & 3;
      v14 = (a4 - v13) >> 2;
      v15 = 0;
      v16 = a4 - 4 * v14 - v13;
      if ( v13 )
      {
        do
        {
          _mm_stream_si32(v12, a5);
          ++v15;
          ++v12;
        }
        while ( v15 < v13 );
      }
      for ( i = 0; i < v14; v12 += 4 )
      {
        _mm_stream_ps((float *)v12, v10);
        ++i;
      }
      for ( j = 0; j < v16; ++v12 )
      {
        ++j;
        _mm_stream_si32(v12, a5);
      }
      a1 += v11;
      ++v9;
    }
    while ( v9 < a3 );
  }
}

```

## disassembly

```asm
0x140013c80  push    rbx
0x140013c82  push    rbp
0x140013c83  push    rsi
0x140013c84  push    rdi
0x140013c85  push    r14
0x140013c87  xor     ebp, ebp
0x140013c89  mov     ebx, r9d
0x140013c8c  cmp     cs:?g_SSE2InstructionsAvailable@@3HA, ebp; int g_SSE2InstructionsAvailable
0x140013c92  mov     r14d, r8d
0x140013c95  mov     rsi, rcx
0x140013c98  jz      loc_140013D36
0x140013c9e  movss   xmm0, [rsp+28h+arg_20]
0x140013ca4  mov     r10d, ebp
0x140013ca7  shufps  xmm0, xmm0, 0
0x140013cab  test    r8d, r8d
0x140013cae  jz      loc_140013D2E
0x140013cb4  mov     r8d, [rsp+28h+arg_20]
0x140013cb9  mov     r11d, edx
0x140013cbc  nop     dword ptr [rax+00h]
0x140013cc0  mov     rdi, rsi
0x140013cc3  mov     edx, ebx
0x140013cc5  shr     rdi, 2
0x140013cc9  mov     r9d, ebx
0x140013ccc  neg     edi
0x140013cce  mov     rax, rsi
0x140013cd1  and     edi, 3
0x140013cd4  sub     edx, edi
0x140013cd6  sar     edx, 2
0x140013cd9  lea     ecx, ds:0[rdx*4]
0x140013ce0  sub     r9d, ecx
0x140013ce3  mov     ecx, ebp
0x140013ce5  sub     r9d, edi
0x140013ce8  test    edi, edi
0x140013cea  jz      short loc_140013CFA
0x140013cec  movnti  dword ptr [rax], r8d
0x140013cf0  inc     ecx
0x140013cf2  add     rax, 4
0x140013cf6  cmp     ecx, edi
0x140013cf8  jl      short loc_140013CEC
0x140013cfa  mov     ecx, ebp
0x140013cfc  test    edx, edx
0x140013cfe  jle     short loc_140013D0D
0x140013d00  movntps xmmword ptr [rax], xmm0
0x140013d03  inc     ecx
0x140013d05  add     rax, 10h
0x140013d09  cmp     ecx, edx
0x140013d0b  jl      short loc_140013D00
0x140013d0d  mov     ecx, ebp
0x140013d0f  test    r9d, r9d
0x140013d12  jle     short loc_140013D23
0x140013d14  inc     ecx
0x140013d16  movnti  dword ptr [rax], r8d
0x140013d1a  lea     rax, [rax+4]
0x140013d1e  cmp     ecx, r9d
0x140013d21  jl      short loc_140013D14
0x140013d23  add     rsi, r11
0x140013d26  inc     r10d
0x140013d29  cmp     r10d, r14d
0x140013d2c  jb      short loc_140013CC0
0x140013d2e  pop     r14
0x140013d30  pop     rdi
0x140013d31  pop     rsi
0x140013d32  pop     rbp
0x140013d33  pop     rbx
0x140013d34  retn
0x140013d36  test    r14d, r14d
0x140013d39  jz      short loc_140013D2E
0x140013d3b  mov     r11d, [rsp+28h+arg_20]
0x140013d40  lea     r8d, ds:0[r9*4]
0x140013d48  shr     r8, 2
0x140013d4c  mov     ebx, edx
0x140013d4e  test    r8, r8
0x140013d51  jz      short loc_140013D92
0x140013d53  test    sil, 4
0x140013d57  jz      short loc_140013D6B
0x140013d59  lea     r9, [r8-1]
0x140013d5d  mov     [rsi], r11d
0x140013d60  test    r9, r9
0x140013d63  jz      short loc_140013D92
0x140013d65  lea     r10, [rsi+4]
0x140013d69  jmp     short loc_140013D71
0x140013d6b  mov     r9, r8
0x140013d6e  mov     r10, rsi
0x140013d71  mov     rax, r11
0x140013d74  mov     rcx, r9
0x140013d77  shl     rax, 20h
0x140013d7b  mov     rdi, r10
0x140013d7e  or      rax, r11
0x140013d81  shr     rcx, 1
0x140013d84  rep stosq
0x140013d87  test    r9b, 1
0x140013d8b  jz      short loc_140013D92
0x140013d8d  mov     [r10+r9*4-4], r11d
0x140013d92  add     rsi, rbx
0x140013d95  inc     ebp
0x140013d97  cmp     ebp, r14d
0x140013d9a  jb      short loc_140013D4E
0x140013d9c  jmp     short loc_140013D2E
```
