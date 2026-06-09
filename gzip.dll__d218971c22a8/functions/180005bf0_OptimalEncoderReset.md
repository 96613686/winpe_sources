# OptimalEncoderReset

- ea: `0x180005bf0`
- end: `0x180005cf2`
- name: `OptimalEncoderReset`
- size: `258`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800028e0`

## callees

- `0x180003930`
- `0x180005bf0`
- `0x180006ad5`

## pseudocode

```c
void *__fastcall OptimalEncoderReset(__int64 a1)
{
  __int64 v1; // rdi
  __int64 v3; // rsi
  int v4; // edx
  __m128i si128; // xmm0
  __int64 v6; // rdx
  void *result; // rax

  v1 = *(_QWORD *)(a1 + 88);
  *(_QWORD *)(v1 + 541164) = 0;
  *(_QWORD *)(v1 + 541176) = v1 + 475628;
  *(_DWORD *)(a1 + 72) = 0x8000;
  *(_DWORD *)(a1 + 32) = 0x8000;
  *(_DWORD *)(a1 + 36) = 0x8000;
  DeflateInitRecordingTables(v1 + 552548, (_WORD *)(v1 + 552836), v1 + 541956, (_WORD *)(v1 + 541988));
  memset_0((void *)(v1 + 344556), 0, 0x20000u);
  *(_DWORD *)(v1 + 541184) = 1024;
  v3 = *(_QWORD *)(a1 + 88);
  LOBYTE(v4) = 8;
  memset_0((void *)(v3 + 555140), v4, 0x100u);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v6 = 0;
  *(__m128i *)(v3 + 555397) = si128;
  *(__m128i *)(v3 + 555412) = si128;
  do
  {
    *(_BYTE *)(v6 + v3 + 555620) = ((unsigned __int8)v6 >> 1) + 1;
    v6 = (unsigned int)(v6 + 1);
  }
  while ( (int)v6 < 32 );
  memset_0((void *)(v1 + 553412), 0, 0x480u);
  result = memset_0((void *)(v1 + 555428), 0, 0x80u);
  *(_WORD *)(v1 + 553924) = 1;
  return result;
}

```

## disassembly

```asm
0x180005bf0  mov     [rsp+arg_0], rbx
0x180005bf5  mov     [rsp+arg_8], rsi
0x180005bfa  push    rdi
0x180005bfb  sub     rsp, 20h
0x180005bff  mov     rdi, [rcx+58h]
0x180005c03  mov     rbx, rcx
0x180005c06  mov     qword ptr [rdi+841ECh], 0
0x180005c11  lea     rax, [rdi+741ECh]
0x180005c18  mov     [rdi+841F8h], rax
0x180005c1f  lea     r9, [rdi+84524h]
0x180005c26  mov     eax, 8000h
0x180005c2b  lea     r8, [rdi+84504h]
0x180005c32  mov     [rcx+48h], eax
0x180005c35  lea     rdx, [rdi+86F84h]
0x180005c3c  mov     [rcx+20h], eax
0x180005c3f  mov     [rcx+24h], eax
0x180005c42  lea     rcx, [rdi+86E64h]
0x180005c49  call    DeflateInitRecordingTables
0x180005c4e  lea     rcx, [rdi+541ECh]; void *
0x180005c55  xor     edx, edx; Val
0x180005c57  mov     r8d, 20000h; Size
0x180005c5d  call    memset_0
0x180005c62  mov     dword ptr [rdi+84200h], 400h
0x180005c6c  mov     r8d, 100h; Size
0x180005c72  mov     rsi, [rbx+58h]
0x180005c76  mov     dl, 8; Val
0x180005c78  lea     rcx, [rsi+87884h]; void *
0x180005c7f  call    memset_0
0x180005c84  movdqa  xmm0, cs:__xmm@06060606060606060606060606060606
0x180005c8c  xor     edx, edx
0x180005c8e  movups  xmmword ptr [rsi+87985h], xmm0
0x180005c95  movups  xmmword ptr [rsi+87994h], xmm0
0x180005c9c  lea     ebx, [rdx+1]
0x180005c9f  mov     cl, dl
0x180005ca1  shr     cl, 1
0x180005ca3  add     cl, bl
0x180005ca5  mov     [rdx+rsi+87A64h], cl
0x180005cac  add     edx, ebx
0x180005cae  cmp     edx, 20h ; ' '
0x180005cb1  jl      short loc_180005C9F
0x180005cb3  lea     rcx, [rdi+871C4h]; void *
0x180005cba  xor     edx, edx; Val
0x180005cbc  mov     r8d, 480h; Size
0x180005cc2  call    memset_0
0x180005cc7  lea     rcx, [rdi+879A4h]; void *
0x180005cce  xor     edx, edx; Val
0x180005cd0  mov     r8d, 80h; Size
0x180005cd6  call    memset_0
0x180005cdb  mov     rsi, [rsp+28h+arg_8]
0x180005ce0  mov     [rdi+873C4h], bx
0x180005ce7  mov     rbx, [rsp+28h+arg_0]
0x180005cec  add     rsp, 20h
0x180005cf0  pop     rdi
0x180005cf1  retn
```
