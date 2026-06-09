# init_compression_memory

- ea: `0x18001727c`
- end: `0x180017486`
- name: `init_compression_memory`
- size: `522`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001ab8`
- `0x180016e08`

## callees

- `0x18000e51c`
- `0x18001562a`

## pseudocode

```c
void *__fastcall init_compression_memory(__int64 a1)
{
  __int64 v2; // rdx
  __int64 v3; // rax
  __m128i v4; // xmm1
  int v5; // ecx
  void *v6; // rcx

  memset_0(*(void **)(a1 + 16), 0, 0x40000u);
  v2 = *(unsigned int *)(a1 + 8);
  v3 = *(_QWORD *)(a1 + 17272);
  v4 = _mm_loadu_si128((const __m128i *)(a1 + 17280));
  *(_DWORD *)(a1 + 1144) = v2;
  *(_QWORD *)a1 = v3 - v2;
  *(_DWORD *)(a1 + 100) = 1;
  *(_DWORD *)(a1 + 104) = 1;
  *(__m128i *)(a1 + 24) = _mm_sub_epi64(
                            v4,
                            _mm_unpacklo_epi64((__m128i)(unsigned __int64)(4 * v2), (__m128i)(unsigned __int64)(4 * v2)));
  *(_DWORD *)(a1 + 88) = 1;
  *(_DWORD *)(a1 + 92) = 1;
  *(_DWORD *)(a1 + 96) = 1;
  *(_DWORD *)(a1 + 108) = 1;
  LODWORD(v3) = *(_DWORD *)(a1 + 2208);
  *(_DWORD *)(a1 + 2204) = v2;
  *(_BYTE *)(a1 + 2481) = 1;
  *(_DWORD *)(a1 + 2484) = 1;
  *(_BYTE *)(a1 + 44) = 32;
  *(_DWORD *)(a1 + 40) = 0;
  *(_DWORD *)(a1 + 48) = 0;
  memset_0((void *)(a1 + 14760), 0, 8 * (int)v3 + 256);
  memset_0((void *)(a1 + 16956), 0, 0xF9u);
  memset_0((void *)(a1 + 9608), 8, 0x100u);
  memset_0((void *)(a1 + 9864), 9, 8 * *(_DWORD *)(a1 + 2208));
  memset_0((void *)(a1 + 10309), 6, 0xF9u);
  *(_QWORD *)(a1 + 17254) = 0x303030303030303LL;
  prevent_far_matches(a1);
  v5 = *(_DWORD *)(a1 + 1144);
  *(_DWORD *)(a1 + 2500) = v5;
  *(_DWORD *)(a1 + 2496) = v5;
  v6 = *(void **)(a1 + 80);
  *(_DWORD *)(a1 + 2200) = 0;
  *(_DWORD *)(a1 + 2488) = 1;
  memset_0(v6, 0, 0x2000u);
  *(_DWORD *)(a1 + 88) = 1;
  *(_DWORD *)(a1 + 92) = 1;
  *(_DWORD *)(a1 + 96) = 1;
  *(_QWORD *)(a1 + 56) = 0;
  *(_BYTE *)(a1 + 2224) = 0;
  *(_DWORD *)(a1 + 2516) = 0;
  *(_DWORD *)(a1 + 2216) = 0;
  *(_DWORD *)(a1 + 17296) = 0;
  memset_0((void *)(a1 + 10560), 0, 0xAF0u);
  memset_0((void *)(a1 + 15462), 0, 0x3E4u);
  *(_OWORD *)(a1 + 17206) = 0;
  *(_OWORD *)(a1 + 17222) = 0;
  return memset_0(*(void **)(a1 + 17272), 0, (unsigned int)(*(_DWORD *)(a1 + 2492) + 4353 + *(_DWORD *)(a1 + 8)));
}

```

## disassembly

```asm
0x18001727c  mov     [rsp+arg_0], rbx
0x180017281  mov     [rsp+arg_8], rdi
0x180017286  push    r14
0x180017288  sub     rsp, 20h
0x18001728c  mov     rdi, rcx
0x18001728f  xor     edx, edx; Val
0x180017291  mov     rcx, [rcx+10h]; void *
0x180017295  mov     r8d, 40000h; Size
0x18001729b  call    memset_0
0x1800172a0  mov     edx, [rdi+8]
0x1800172a3  lea     rcx, [rdi+39A8h]; void *
0x1800172aa  mov     rax, [rdi+4378h]
0x1800172b1  mov     r14d, 1
0x1800172b7  movdqu  xmm1, xmmword ptr [rdi+4380h]
0x1800172bf  mov     [rdi+478h], edx
0x1800172c5  sub     rax, rdx
0x1800172c8  mov     [rdi], rax
0x1800172cb  lea     rax, ds:0[rdx*4]
0x1800172d3  movq    xmm0, rax
0x1800172d8  mov     [rdi+64h], r14d
0x1800172dc  punpcklqdq xmm0, xmm0
0x1800172e0  psubq   xmm1, xmm0
0x1800172e4  mov     [rdi+68h], r14d
0x1800172e8  movdqu  xmmword ptr [rdi+18h], xmm1
0x1800172ed  mov     [rdi+58h], r14d
0x1800172f1  mov     [rdi+5Ch], r14d
0x1800172f5  mov     [rdi+60h], r14d
0x1800172f9  mov     [rdi+6Ch], r14d
0x1800172fd  mov     eax, [rdi+8A0h]
0x180017303  mov     [rdi+89Ch], edx
0x180017309  xor     edx, edx; Val
0x18001730b  mov     [rdi+9B1h], r14b
0x180017312  mov     [rdi+9B4h], r14d
0x180017319  lea     eax, ds:100h[rax*8]
0x180017320  mov     byte ptr [rdi+2Ch], 20h ; ' '
0x180017324  movsxd  r8, eax; Size
0x180017327  mov     dword ptr [rdi+28h], 0
0x18001732e  mov     dword ptr [rdi+30h], 0
0x180017335  call    memset_0
0x18001733a  lea     rcx, [rdi+423Ch]; void *
0x180017341  xor     edx, edx; Val
0x180017343  mov     r8d, 0F9h; Size
0x180017349  call    memset_0
0x18001734e  lea     edx, [r14+7]; Val
0x180017352  mov     r8d, 100h; Size
0x180017358  lea     rcx, [rdi+2588h]; void *
0x18001735f  call    memset_0
0x180017364  mov     eax, [rdi+8A0h]
0x18001736a  lea     rcx, [rdi+2688h]; void *
0x180017371  shl     eax, 3
0x180017374  lea     edx, [r14+8]; Val
0x180017378  movsxd  r8, eax; Size
0x18001737b  call    memset_0
0x180017380  lea     rcx, [rdi+2845h]; void *
0x180017387  mov     r8d, 0F9h; Size
0x18001738d  lea     edx, [r14+5]; Val
0x180017391  call    memset_0
0x180017396  mov     rax, 303030303030303h
0x1800173a0  mov     rcx, rdi
0x1800173a3  mov     [rdi+4366h], rax
0x1800173aa  call    prevent_far_matches
0x1800173af  mov     ecx, [rdi+478h]
0x1800173b5  xor     edx, edx; Val
0x1800173b7  mov     [rdi+9C4h], ecx
0x1800173bd  mov     r8d, 2000h; Size
0x1800173c3  mov     [rdi+9C0h], ecx
0x1800173c9  mov     rcx, [rdi+50h]; void *
0x1800173cd  mov     dword ptr [rdi+898h], 0
0x1800173d7  mov     [rdi+9B8h], r14d
0x1800173de  call    memset_0
0x1800173e3  mov     [rdi+58h], r14d
0x1800173e7  lea     rcx, [rdi+2940h]; void *
0x1800173ee  mov     [rdi+5Ch], r14d
0x1800173f2  xor     edx, edx; Val
0x1800173f4  mov     [rdi+60h], r14d
0x1800173f8  mov     r8d, 0AF0h; Size
0x1800173fe  mov     qword ptr [rdi+38h], 0
0x180017406  mov     byte ptr [rdi+8B0h], 0
0x18001740d  mov     dword ptr [rdi+9D4h], 0
0x180017417  mov     dword ptr [rdi+8A8h], 0
0x180017421  mov     dword ptr [rdi+4390h], 0
0x18001742b  call    memset_0
0x180017430  lea     rcx, [rdi+3C66h]; void *
0x180017437  xor     edx, edx; Val
0x180017439  mov     r8d, 3E4h; Size
0x18001743f  call    memset_0
0x180017444  xorps   xmm0, xmm0
0x180017447  xor     edx, edx; Val
0x180017449  movups  xmmword ptr [rdi+4336h], xmm0
0x180017450  movups  xmmword ptr [rdi+4346h], xmm0
0x180017457  mov     ecx, [rdi+9BCh]
0x18001745d  mov     r8d, [rdi+8]
0x180017461  add     ecx, 1101h
0x180017467  add     r8d, ecx; Size
0x18001746a  mov     rcx, [rdi+4378h]; void *
0x180017471  mov     rbx, [rsp+28h+arg_0]
0x180017476  mov     rdi, [rsp+28h+arg_8]
0x18001747b  add     rsp, 20h
0x18001747f  pop     r14
0x180017481  jmp     memset_0
```
