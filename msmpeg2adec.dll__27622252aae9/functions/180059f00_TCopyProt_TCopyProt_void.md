# TCopyProt::TCopyProt(void)

- ea: `0x180059f00`
- end: `0x18005a36c`
- name: `??0TCopyProt@@QEAA@XZ`
- size: `1132`
- prototype: `TCopyProt *__fastcall(TCopyProt *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18005a380`

## callees

- `0x180001360`
- `0x1800013a0`
- `0x180059f00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18005a32f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18005a32f`
- `api-ms-win-mm-time-l1-1-0!timeGetTime` at `0x180059f3b`
- `api-ms-win-mm-time-l1-1-0!timeGetTime` at `0x180059f3b`

## pseudocode

```c
TCopyProt *__fastcall TCopyProt::TCopyProt(TCopyProt *this)
{
  __int64 i; // rbx
  unsigned __int8 Time; // al
  __int64 v4; // r8
  __int64 v5; // rcx
  _BYTE *v6; // rbx
  _BYTE *v7; // rbx
  _BYTE *v8; // rbx
  _BYTE *v9; // rbx
  _BYTE *v10; // rbx
  __m128 si128; // xmm2
  unsigned int v12; // ecx
  __int64 v13; // rax
  _QWORD *v14; // rcx

  *((_QWORD *)this + 4) = operator new(0x200u);
  for ( i = 0; i != 64; ++i )
    *(_QWORD *)(*((_QWORD *)this + 4) + 8 * i) = operator new(5u);
  Time = timeGetTime();
  v4 = *((_QWORD *)this + 4);
  *((_QWORD *)this + 5) = v4 + 8LL * ((Time ^ 0xB) & 0x3F);
  v5 = v4 + 8LL * ((Time ^ 0xC) & 0x3F);
  *((_QWORD *)this + 6) = v5;
  *((_QWORD *)this + 7) = v4 + 8LL * ((Time ^ 0x15) & 0x3F);
  *((_QWORD *)this + 8) = v4 + 8LL * ((Time ^ 0x19) & 0x3F);
  *((_QWORD *)this + 9) = v4 + 8LL * ((Time ^ 0x1D) & 0x3F);
  *((_QWORD *)this + 10) = v4 + 8LL * ((Time ^ 0x11) & 0x3F);
  *((_QWORD *)this + 11) = v4 + 8LL * ((Time ^ 3) & 0x3F);
  *((_QWORD *)this + 12) = v4 + 8LL * ((Time ^ 7) & 0x3F);
  *((_QWORD *)this + 13) = v4 + 8LL * ((Time ^ 0x10) & 0x3F);
  *((_QWORD *)this + 14) = v4 + 8LL * ((Time ^ 0x16) & 0x3F);
  *((_QWORD *)this + 16) = v5;
  *((_QWORD *)this + 17) = v4 + 8LL * ((Time ^ 0xD) & 0x3F);
  *((_QWORD *)this + 18) = v4 + 8LL * ((Time ^ 0xE) & 0x3F);
  *((_QWORD *)this + 19) = v4 + 8LL * ((Time ^ 0xF) & 0x3F);
  *((_QWORD *)this + 20) = v4 + 8LL * ((Time ^ 0xEC) & 0x3F);
  *((_QWORD *)this + 21) = v4 + 8LL * ((Time ^ 0xE1) & 0x3F);
  *((_DWORD *)this + 64) = 0;
  *((_WORD *)this + 60) = 0;
  *((_BYTE *)this + 122) = 0;
  *((_QWORD *)this + 22) = v4 + 8LL * ((Time ^ 0xF0) & 0x3F);
  *((_QWORD *)this + 23) = v4 + 8LL * ((Time ^ 0xF7) & 0x3F);
  *((_QWORD *)this + 24) = v4 + 8LL * ((Time ^ 0xE5) & 0x3F);
  *((_QWORD *)this + 25) = v4 + 8LL * ((Time ^ 0xE9) & 0x3F);
  *((_QWORD *)this + 26) = v4 + 8LL * ((Time ^ 0xFB) & 0x3F);
  *((_QWORD *)this + 27) = v4 + 8LL * ((Time ^ 1) & 0x3F);
  *((_QWORD *)this + 28) = v4 + 8LL * ((Time ^ 0x1E) & 0x3F);
  *((_QWORD *)this + 29) = v4 + 8LL * ((Time ^ 0xFD) & 0x3F);
  *((_QWORD *)this + 30) = v4 + 8LL * ((Time ^ 0xED) & 0x3F);
  *((_QWORD *)this + 31) = v4 + 8LL * ((Time ^ 0xF3) & 0x3F);
  *((_QWORD *)this + 33) = v4 + 8LL * ((Time ^ 0xEA) & 0x3F);
  v6 = operator new(0xEu);
  *(_DWORD *)v6 = (unsigned int)v6
                ^ (**((_DWORD **)this + 9) >> 8)
                ^ *(_DWORD *)(**((_QWORD **)this + 9) + 1LL)
                ^ (**((_DWORD **)this + 9) << 24);
  v6[4] = (unsigned __int8)v6 ^ 1;
  operator delete(**((void ***)this + 9));
  **((_QWORD **)this + 9) = v6;
  v7 = operator new(0xEu);
  *(_DWORD *)v7 = (unsigned int)v7
                ^ (**((_DWORD **)this + 9) >> 8)
                ^ *(_DWORD *)(**((_QWORD **)this + 9) + 1LL)
                ^ (**((_DWORD **)this + 9) << 24);
  v7[4] = (unsigned __int8)v7 ^ 0x47;
  operator delete(**((void ***)this + 9));
  **((_QWORD **)this + 9) = v7;
  v8 = operator new(0xEu);
  *(_DWORD *)v8 = (unsigned int)v8
                ^ (**((_DWORD **)this + 9) >> 8)
                ^ *(_DWORD *)(**((_QWORD **)this + 9) + 1LL)
                ^ (**((_DWORD **)this + 9) << 24);
  v8[4] = (unsigned __int8)v8 ^ 0xA0;
  operator delete(**((void ***)this + 9));
  **((_QWORD **)this + 9) = v8;
  v9 = operator new(0xEu);
  *(_DWORD *)v9 = (unsigned int)v9
                ^ (**((_DWORD **)this + 9) >> 8)
                ^ *(_DWORD *)(**((_QWORD **)this + 9) + 1LL)
                ^ (**((_DWORD **)this + 9) << 24);
  v9[4] = (unsigned __int8)v9 ^ 0xF6;
  operator delete(**((void ***)this + 9));
  **((_QWORD **)this + 9) = v9;
  v10 = operator new(0xEu);
  *(_DWORD *)v10 = (unsigned int)v10
                 ^ (**((_DWORD **)this + 9) >> 8)
                 ^ *(_DWORD *)(**((_QWORD **)this + 9) + 1LL)
                 ^ (**((_DWORD **)this + 9) << 24);
  v10[4] = (unsigned __int8)v10 ^ 0x13;
  operator delete(**((void ***)this + 9));
  si128 = (__m128)_mm_load_si128((const __m128i *)&_xmm);
  v12 = 0;
  **((_QWORD **)this + 9) = v10;
  do
  {
    v13 = (int)v12;
    v12 += 64;
    *(__m128 *)((char *)&TCopyProt::Dec_Tab_TR + v13) = _mm_xor_ps(
                                                          si128,
                                                          (__m128)_mm_loadu_si128((const __m128i *)((char *)&TCopyProt::Dec_Tab_TR
                                                                                                  + v13)));
    *(__m128 *)((char *)&TCopyProt::Dec_Tab_TR + v13 + 16) = _mm_xor_ps(
                                                               si128,
                                                               (__m128)_mm_loadu_si128((const __m128i *)((char *)&TCopyProt::Dec_Tab_TR + v13 + 16)));
    *(__m128 *)((char *)&TCopyProt::Dec_Tab_TR + v13 + 32) = _mm_xor_ps(
                                                               si128,
                                                               (__m128)_mm_loadu_si128((const __m128i *)((char *)&TCopyProt::Dec_Tab_TR + v13 + 32)));
    *(__m128 *)((char *)&TCopyProt::Dec_Tab_TR + v13 + 48) = _mm_xor_ps(
                                                               si128,
                                                               (__m128)_mm_loadu_si128((const __m128i *)((char *)&TCopyProt::Dec_Tab_TR + v13 + 48)));
  }
  while ( v12 < 0x100 );
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 288));
  v14 = (_QWORD *)*((_QWORD *)this + 4);
  *(_QWORD *)this = *v14;
  *((_QWORD *)this + 1) = v14[3];
  *((_QWORD *)this + 3) = v14[4];
  *((_QWORD *)this + 2) = v14[7];
  return this;
}

```

## disassembly

```asm
0x180059f00  mov     [rsp+arg_0], rbx
0x180059f05  push    rdi
0x180059f06  sub     rsp, 20h
0x180059f0a  mov     rdi, rcx
0x180059f0d  mov     ecx, 200h; Size
0x180059f12  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180059f17  mov     [rdi+20h], rax
0x180059f1b  xor     ebx, ebx
0x180059f1d  nop     dword ptr [rax]
0x180059f20  mov     ecx, 5; Size
0x180059f25  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180059f2a  mov     rcx, [rdi+20h]
0x180059f2e  mov     [rcx+rbx*8], rax
0x180059f32  inc     rbx
0x180059f35  cmp     rbx, 40h ; '@'
0x180059f39  jnz     short loc_180059F20
0x180059f3b  call    cs:__imp_timeGetTime
0x180059f42  nop     dword ptr [rax+rax+00h]
0x180059f47  movsxd  rdx, eax
0x180059f4a  mov     r8, [rdi+20h]
0x180059f4e  mov     rax, rdx
0x180059f51  xor     rax, 0Bh
0x180059f55  and     eax, 3Fh
0x180059f58  lea     rax, [r8+rax*8]
0x180059f5c  mov     [rdi+28h], rax
0x180059f60  mov     rax, rdx
0x180059f63  xor     rax, 0Ch
0x180059f67  and     eax, 3Fh
0x180059f6a  lea     rcx, [r8+rax*8]
0x180059f6e  mov     rax, rdx
0x180059f71  xor     rax, 15h
0x180059f75  mov     [rdi+30h], rcx
0x180059f79  and     eax, 3Fh
0x180059f7c  lea     rax, [r8+rax*8]
0x180059f80  mov     [rdi+38h], rax
0x180059f84  mov     rax, rdx
0x180059f87  xor     rax, 19h
0x180059f8b  and     eax, 3Fh
0x180059f8e  lea     rax, [r8+rax*8]
0x180059f92  mov     [rdi+40h], rax
0x180059f96  mov     rax, rdx
0x180059f99  xor     rax, 1Dh
0x180059f9d  and     eax, 3Fh
0x180059fa0  lea     rax, [r8+rax*8]
0x180059fa4  mov     [rdi+48h], rax
0x180059fa8  mov     rax, rdx
0x180059fab  xor     rax, 11h
0x180059faf  and     eax, 3Fh
0x180059fb2  lea     rax, [r8+rax*8]
0x180059fb6  mov     [rdi+50h], rax
0x180059fba  mov     rax, rdx
0x180059fbd  xor     rax, 3
0x180059fc1  and     eax, 3Fh
0x180059fc4  lea     rax, [r8+rax*8]
0x180059fc8  mov     [rdi+58h], rax
0x180059fcc  mov     rax, rdx
0x180059fcf  xor     rax, 7
0x180059fd3  and     eax, 3Fh
0x180059fd6  lea     rax, [r8+rax*8]
0x180059fda  mov     [rdi+60h], rax
0x180059fde  mov     rax, rdx
0x180059fe1  xor     rax, 10h
0x180059fe5  and     eax, 3Fh
0x180059fe8  lea     rax, [r8+rax*8]
0x180059fec  mov     [rdi+68h], rax
0x180059ff0  mov     rax, rdx
0x180059ff3  xor     rax, 16h
0x180059ff7  and     eax, 3Fh
0x180059ffa  lea     rax, [r8+rax*8]
0x180059ffe  mov     [rdi+70h], rax
0x18005a002  mov     rax, rdx
0x18005a005  xor     rax, 0Dh
0x18005a009  mov     [rdi+80h], rcx
0x18005a010  and     eax, 3Fh
0x18005a013  lea     rax, [r8+rax*8]
0x18005a017  mov     [rdi+88h], rax
0x18005a01e  mov     rax, rdx
0x18005a021  xor     rax, 0Eh
0x18005a025  and     eax, 3Fh
0x18005a028  lea     rax, [r8+rax*8]
0x18005a02c  mov     [rdi+90h], rax
0x18005a033  mov     rax, rdx
0x18005a036  xor     rax, 0Fh
0x18005a03a  and     eax, 3Fh
0x18005a03d  lea     rax, [r8+rax*8]
0x18005a041  mov     [rdi+98h], rax
0x18005a048  mov     rax, rdx
0x18005a04b  xor     rax, 0FFFFFFFFFFFFFFECh
0x18005a04f  and     eax, 3Fh
0x18005a052  lea     rax, [r8+rax*8]
0x18005a056  mov     [rdi+0A0h], rax
0x18005a05d  mov     rax, rdx
0x18005a060  xor     rax, 0FFFFFFFFFFFFFFE1h
0x18005a064  and     eax, 3Fh
0x18005a067  lea     rax, [r8+rax*8]
0x18005a06b  mov     [rdi+0A8h], rax
0x18005a072  mov     rax, rdx
0x18005a075  xor     rax, 0FFFFFFFFFFFFFFF0h
0x18005a079  and     eax, 3Fh
0x18005a07c  mov     dword ptr [rdi+100h], 0
0x18005a086  mov     ecx, 0Eh; Size
0x18005a08b  mov     word ptr [rdi+78h], 0
0x18005a091  mov     byte ptr [rdi+7Ah], 0
0x18005a095  lea     rax, [r8+rax*8]
0x18005a099  mov     [rdi+0B0h], rax
0x18005a0a0  mov     rax, rdx
0x18005a0a3  xor     rax, 0FFFFFFFFFFFFFFF7h
0x18005a0a7  and     eax, 3Fh
0x18005a0aa  lea     rax, [r8+rax*8]
0x18005a0ae  mov     [rdi+0B8h], rax
0x18005a0b5  mov     rax, rdx
0x18005a0b8  xor     rax, 0FFFFFFFFFFFFFFE5h
0x18005a0bc  and     eax, 3Fh
0x18005a0bf  lea     rax, [r8+rax*8]
0x18005a0c3  mov     [rdi+0C0h], rax
0x18005a0ca  mov     rax, rdx
0x18005a0cd  xor     rax, 0FFFFFFFFFFFFFFE9h
0x18005a0d1  and     eax, 3Fh
0x18005a0d4  lea     rax, [r8+rax*8]
0x18005a0d8  mov     [rdi+0C8h], rax
0x18005a0df  mov     rax, rdx
0x18005a0e2  xor     rax, 0FFFFFFFFFFFFFFFBh
0x18005a0e6  and     eax, 3Fh
0x18005a0e9  lea     rax, [r8+rax*8]
0x18005a0ed  mov     [rdi+0D0h], rax
0x18005a0f4  mov     rax, rdx
0x18005a0f7  xor     rax, 1
0x18005a0fb  and     eax, 3Fh
0x18005a0fe  lea     rax, [r8+rax*8]
0x18005a102  mov     [rdi+0D8h], rax
0x18005a109  mov     rax, rdx
0x18005a10c  xor     rax, 1Eh
0x18005a110  and     eax, 3Fh
0x18005a113  lea     rax, [r8+rax*8]
0x18005a117  mov     [rdi+0E0h], rax
0x18005a11e  mov     rax, rdx
0x18005a121  xor     rax, 0FFFFFFFFFFFFFFFDh
0x18005a125  and     eax, 3Fh
0x18005a128  lea     rax, [r8+rax*8]
0x18005a12c  mov     [rdi+0E8h], rax
0x18005a133  mov     rax, rdx
0x18005a136  xor     rax, 0FFFFFFFFFFFFFFEDh
0x18005a13a  and     eax, 3Fh
0x18005a13d  lea     rax, [r8+rax*8]
0x18005a141  mov     [rdi+0F0h], rax
0x18005a148  mov     rax, rdx
0x18005a14b  xor     rax, 0FFFFFFFFFFFFFFF3h
0x18005a14f  xor     rdx, 0FFFFFFFFFFFFFFEAh
0x18005a153  and     eax, 3Fh
0x18005a156  and     edx, 3Fh
0x18005a159  lea     rax, [r8+rax*8]
0x18005a15d  mov     [rdi+0F8h], rax
0x18005a164  lea     rax, [r8+rdx*8]
0x18005a168  mov     [rdi+108h], rax
0x18005a16f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005a174  mov     rcx, [rdi+48h]
0x18005a178  mov     rbx, rax
0x18005a17b  mov     r8d, [rcx]
0x18005a17e  mov     rdx, [rcx]
0x18005a181  mov     ecx, r8d
0x18005a184  shl     ecx, 18h
0x18005a187  shr     r8d, 8
0x18005a18b  xor     ecx, [rdx+1]
0x18005a18e  xor     ecx, r8d
0x18005a191  xor     ecx, eax
0x18005a193  mov     [rax], ecx
0x18005a195  xor     al, 1
0x18005a197  mov     [rbx+4], al
0x18005a19a  mov     rcx, [rdi+48h]
0x18005a19e  mov     rcx, [rcx]; Block
0x18005a1a1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005a1a6  mov     rax, [rdi+48h]
0x18005a1aa  mov     ecx, 0Eh; Size
0x18005a1af  mov     [rax], rbx
0x18005a1b2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005a1b7  mov     rcx, [rdi+48h]
0x18005a1bb  mov     rbx, rax
0x18005a1be  mov     r8d, [rcx]
0x18005a1c1  mov     rdx, [rcx]
0x18005a1c4  mov     ecx, r8d
0x18005a1c7  shr     r8d, 8
0x18005a1cb  shl     ecx, 18h
0x18005a1ce  xor     ecx, [rdx+1]
0x18005a1d1  xor     ecx, r8d
0x18005a1d4  xor     ecx, eax
0x18005a1d6  mov     [rax], ecx
0x18005a1d8  xor     al, 47h
0x18005a1da  mov     [rbx+4], al
0x18005a1dd  mov     rcx, [rdi+48h]
0x18005a1e1  mov     rcx, [rcx]; Block
0x18005a1e4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005a1e9  mov     rax, [rdi+48h]
0x18005a1ed  mov     ecx, 0Eh; Size
0x18005a1f2  mov     [rax], rbx
0x18005a1f5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005a1fa  mov     rcx, [rdi+48h]
0x18005a1fe  mov     rbx, rax
0x18005a201  mov     r8d, [rcx]
0x18005a204  mov     rdx, [rcx]
0x18005a207  mov     ecx, r8d
0x18005a20a  shl     ecx, 18h
0x18005a20d  shr     r8d, 8
0x18005a211  xor     ecx, [rdx+1]
0x18005a214  xor     ecx, r8d
0x18005a217  xor     ecx, eax
0x18005a219  mov     [rax], ecx
0x18005a21b  xor     al, 0A0h
0x18005a21d  mov     [rbx+4], al
0x18005a220  mov     rcx, [rdi+48h]
0x18005a224  mov     rcx, [rcx]; Block
0x18005a227  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005a22c  mov     rax, [rdi+48h]
0x18005a230  mov     ecx, 0Eh; Size
0x18005a235  mov     [rax], rbx
0x18005a238  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005a23d  mov     rcx, [rdi+48h]
0x18005a241  mov     rbx, rax
0x18005a244  mov     r8d, [rcx]
0x18005a247  mov     r9d, r8d
0x18005a24a  mov     rdx, [rcx]
0x18005a24d  shl     r9d, 18h
0x18005a251  shr     r8d, 8
0x18005a255  xor     r9d, [rdx+1]
0x18005a259  xor     r9d, r8d
0x18005a25c  xor     r9d, eax
0x18005a25f  mov     [rax], r9d
0x18005a262  xor     al, 0F6h
0x18005a264  mov     [rbx+4], al
0x18005a267  mov     rcx, [rdi+48h]
0x18005a26b  mov     rcx, [rcx]; Block
0x18005a26e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005a273  mov     rax, [rdi+48h]
0x18005a277  mov     ecx, 0Eh; Size
0x18005a27c  mov     [rax], rbx
0x18005a27f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005a284  mov     rcx, [rdi+48h]
0x18005a288  mov     rbx, rax
0x18005a28b  mov     r8d, [rcx]
0x18005a28e  mov     rdx, [rcx]
0x18005a291  mov     ecx, r8d
0x18005a294  shl     ecx, 18h
0x18005a297  shr     r8d, 8
0x18005a29b  xor     ecx, [rdx+1]
0x18005a29e  xor     ecx, r8d
0x18005a2a1  xor     ecx, eax
0x18005a2a3  mov     [rax], ecx
0x18005a2a5  xor     al, 13h
0x18005a2a7  mov     [rbx+4], al
0x18005a2aa  mov     rcx, [rdi+48h]
0x18005a2ae  mov     rcx, [rcx]; Block
0x18005a2b1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005a2b6  mov     rax, [rdi+48h]
0x18005a2ba  lea     rdx, ?Dec_Tab_TR@TCopyProt@@0PAEA; uchar near * TCopyProt::Dec_Tab_TR
0x18005a2c1  movdqa  xmm2, cs:__xmm@55555555555555555555555555555555
0x18005a2c9  xor     ecx, ecx
0x18005a2cb  mov     [rax], rbx
0x18005a2ce  xchg    ax, ax
0x18005a2d0  movsxd  rax, ecx
0x18005a2d3  movdqa  xmm1, xmm2
0x18005a2d7  add     ecx, 40h ; '@'
0x18005a2da  movdqu  xmm0, xmmword ptr [rax+rdx]
0x18005a2df  xorps   xmm1, xmm0
0x18005a2e2  movdqu  xmmword ptr [rax+rdx], xmm1
0x18005a2e7  movdqa  xmm1, xmm2
0x18005a2eb  movdqu  xmm0, xmmword ptr [rax+rdx+10h]
0x18005a2f1  xorps   xmm1, xmm0
0x18005a2f4  movdqu  xmmword ptr [rax+rdx+10h], xmm1
0x18005a2fa  movdqa  xmm1, xmm2
0x18005a2fe  movdqu  xmm0, xmmword ptr [rax+rdx+20h]
0x18005a304  xorps   xmm1, xmm0
0x18005a307  movdqu  xmmword ptr [rax+rdx+20h], xmm1
0x18005a30d  movdqa  xmm1, xmm2
0x18005a311  movdqu  xmm0, xmmword ptr [rax+rdx+30h]
0x18005a317  xorps   xmm1, xmm0
0x18005a31a  movdqu  xmmword ptr [rax+rdx+30h], xmm1
0x18005a320  cmp     ecx, 100h
0x18005a326  jb      short loc_18005A2D0
0x18005a328  lea     rcx, [rdi+120h]; lpCriticalSection
0x18005a32f  call    cs:__imp_InitializeCriticalSection
0x18005a336  nop     dword ptr [rax+rax+00h]
0x18005a33b  mov     rcx, [rdi+20h]
0x18005a33f  mov     rbx, [rsp+28h+arg_0]
0x18005a344  mov     rax, [rcx]
0x18005a347  mov     [rdi], rax
0x18005a34a  mov     rax, [rcx+18h]
0x18005a34e  mov     [rdi+8], rax
0x18005a352  mov     rax, [rcx+20h]
0x18005a356  mov     [rdi+18h], rax
0x18005a35a  mov     rax, [rcx+38h]
0x18005a35e  mov     [rdi+10h], rax
0x18005a362  mov     rax, rdi
0x18005a365  add     rsp, 20h
0x18005a369  pop     rdi
0x18005a36a  retn
```
