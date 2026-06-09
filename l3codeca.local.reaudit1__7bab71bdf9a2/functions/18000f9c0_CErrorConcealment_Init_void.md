# CErrorConcealment::Init(void)

- ea: `0x18000f9c0`
- end: `0x18000fbcc`
- name: `?Init@CErrorConcealment@@QEAAXXZ`
- size: `524`
- prototype: `void __fastcall(CErrorConcealment *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003fa0`
- `0x180005000`

## callees

- `0x180001cd4`
- `0x18000f9c0`

## pseudocode

```c
void __fastcall CErrorConcealment::Init(CErrorConcealment *this)
{
  __int64 v2; // rbp
  __int64 v3; // rbx
  __int64 v4; // r14
  __int64 v5; // rsi
  __int64 v6; // rcx
  _OWORD *v7; // rax
  char *v8; // rax

  v2 = 0;
  v3 = 0;
  do
  {
    *(_DWORD *)((char *)this + v3) = 0;
    v4 = 0;
    v5 = 0;
    v6 = v3;
    do
    {
      v7 = (_OWORD *)((char *)this + v5 + v6 + 4);
      *v7 = 0;
      v7[1] = 0;
      v7[2] = 0;
      v7[3] = 0;
      v7[4] = 0;
      v7[5] = 0;
      *(_OWORD *)((char *)v7 + 92) = 0;
      memset_0((char *)this + 12544 * v2 + 2508 * v4 + 112, 0, 0x900u);
      v8 = (char *)this + v5;
      ++v4;
      v6 = 12544 * v2;
      *(_QWORD *)&v8[v3 + 2416] = 0;
      *(_QWORD *)&v8[v3 + 2424] = 0;
      *(_QWORD *)&v8[v3 + 2432] = 0;
      *(_QWORD *)&v8[v3 + 2440] = 0;
      *(_QWORD *)&v8[v3 + 2448] = 0;
      *(_QWORD *)&v8[v3 + 2456] = 0;
      *(_QWORD *)&v8[v3 + 2464] = 0;
      *(_QWORD *)&v8[v3 + 2472] = 0;
      *(_QWORD *)&v8[v3 + 2480] = 0;
      *(_QWORD *)&v8[v3 + 2488] = 0;
      *(_QWORD *)&v8[v3 + 2496] = 0;
      *(_DWORD *)&v8[v3 + 2504] = 0;
      *(_DWORD *)((char *)this + 12544 * v2 + v5 + 2508) = 0;
      v5 += 2508;
    }
    while ( v4 != 4 );
    *(_OWORD *)((char *)this + v3 + 10036) = 0;
    *(_OWORD *)((char *)this + v3 + 10052) = 0;
    *(_OWORD *)((char *)this + v3 + 10068) = 0;
    *(_OWORD *)((char *)this + v3 + 10084) = 0;
    *(_OWORD *)((char *)this + v3 + 10100) = 0;
    *(_OWORD *)((char *)this + v3 + 10116) = 0;
    *(_OWORD *)((char *)this + v3 + 10128) = 0;
    memset_0((char *)this + 12544 * v2 + 10144, 0, 0x900u);
    *(_QWORD *)((char *)this + v3 + 12448) = 0;
    ++v2;
    *(_QWORD *)((char *)this + v3 + 12456) = 0;
    *(_QWORD *)((char *)this + v3 + 12464) = 0;
    *(_QWORD *)((char *)this + v3 + 12472) = 0;
    *(_QWORD *)((char *)this + v3 + 12480) = 0;
    *(_QWORD *)((char *)this + v3 + 12488) = 0;
    *(_QWORD *)((char *)this + v3 + 12496) = 0;
    *(_QWORD *)((char *)this + v3 + 12504) = 0;
    *(_QWORD *)((char *)this + v3 + 12512) = 0;
    *(_QWORD *)((char *)this + v3 + 12520) = 0;
    *(_QWORD *)((char *)this + v3 + 12528) = 0;
    *(_QWORD *)((char *)this + v3 + 12536) = 0;
    v3 += 12544;
  }
  while ( v2 != 2 );
  *((_DWORD *)this + 6331) = 42;
  *((_DWORD *)this + 6333) = 1044180;
  *((_DWORD *)this + 6332) = 144419;
  *((_DWORD *)this + 6330) = 0;
}

```

## disassembly

```asm
0x18000f9c0  push    rbx
0x18000f9c2  push    rbp
0x18000f9c3  push    rsi
0x18000f9c4  push    rdi
0x18000f9c5  push    r12
0x18000f9c7  push    r14
0x18000f9c9  push    r15
0x18000f9cb  sub     rsp, 20h
0x18000f9cf  xor     r12d, r12d
0x18000f9d2  mov     rdi, rcx
0x18000f9d5  mov     ebp, r12d
0x18000f9d8  mov     ebx, r12d
0x18000f9db  nop     dword ptr [rax+rax+00h]
0x18000f9e0  imul    r15, rbp, 3100h
0x18000f9e7  mov     [rdi+rbx], r12d
0x18000f9eb  mov     r14, r12
0x18000f9ee  add     r15, 70h ; 'p'
0x18000f9f2  mov     rsi, r12
0x18000f9f5  add     r15, rdi
0x18000f9f8  mov     rcx, rbx
0x18000f9fb  nop     dword ptr [rax+rax+00h]
0x18000fa00  xorps   xmm0, xmm0
0x18000fa03  lea     rax, [rdi+rsi]
0x18000fa07  add     rcx, 4
0x18000fa0b  xor     edx, edx; Val
0x18000fa0d  add     rax, rcx
0x18000fa10  mov     r8d, 900h; Size
0x18000fa16  imul    rcx, r14, 9CCh
0x18000fa1d  movups  xmmword ptr [rax], xmm0
0x18000fa20  movups  xmmword ptr [rax+10h], xmm0
0x18000fa24  movups  xmmword ptr [rax+20h], xmm0
0x18000fa28  add     rcx, r15; void *
0x18000fa2b  movups  xmmword ptr [rax+30h], xmm0
0x18000fa2f  movups  xmmword ptr [rax+40h], xmm0
0x18000fa33  movups  xmmword ptr [rax+50h], xmm0
0x18000fa37  movups  xmmword ptr [rax+5Ch], xmm0
0x18000fa3b  call    memset_0
0x18000fa40  lea     rax, [rdi+rsi]
0x18000fa44  inc     r14
0x18000fa47  imul    rcx, rbp, 3100h
0x18000fa4e  mov     [rax+rbx+970h], r12
0x18000fa56  mov     [rax+rbx+978h], r12
0x18000fa5e  mov     [rax+rbx+980h], r12
0x18000fa66  mov     [rax+rbx+988h], r12
0x18000fa6e  mov     [rax+rbx+990h], r12
0x18000fa76  mov     [rax+rbx+998h], r12
0x18000fa7e  mov     [rax+rbx+9A0h], r12
0x18000fa86  mov     [rax+rbx+9A8h], r12
0x18000fa8e  mov     [rax+rbx+9B0h], r12
0x18000fa96  mov     [rax+rbx+9B8h], r12
0x18000fa9e  mov     [rax+rbx+9C0h], r12
0x18000faa6  mov     [rax+rbx+9C8h], r12d
0x18000faae  lea     rax, [rdi+rsi]
0x18000fab2  mov     [rax+rcx+9CCh], r12d
0x18000faba  lea     rsi, [rsi+9CCh]
0x18000fac1  cmp     r14, 4
0x18000fac5  jnz     loc_18000FA00
0x18000facb  xorps   xmm0, xmm0
0x18000face  xor     edx, edx; Val
0x18000fad0  movups  xmmword ptr [rdi+rbx+2734h], xmm0
0x18000fad8  mov     r8d, 900h; Size
0x18000fade  movups  xmmword ptr [rdi+rbx+2744h], xmm0
0x18000fae6  movups  xmmword ptr [rdi+rbx+2754h], xmm0
0x18000faee  movups  xmmword ptr [rdi+rbx+2764h], xmm0
0x18000faf6  movups  xmmword ptr [rdi+rbx+2774h], xmm0
0x18000fafe  movups  xmmword ptr [rdi+rbx+2784h], xmm0
0x18000fb06  imul    rcx, rbp, 3100h
0x18000fb0d  movups  xmmword ptr [rdi+rbx+2790h], xmm0
0x18000fb15  add     rcx, 27A0h
0x18000fb1c  add     rcx, rdi; void *
0x18000fb1f  call    memset_0
0x18000fb24  mov     [rdi+rbx+30A0h], r12
0x18000fb2c  inc     rbp
0x18000fb2f  mov     [rdi+rbx+30A8h], r12
0x18000fb37  mov     [rdi+rbx+30B0h], r12
0x18000fb3f  mov     [rdi+rbx+30B8h], r12
0x18000fb47  mov     [rdi+rbx+30C0h], r12
0x18000fb4f  mov     [rdi+rbx+30C8h], r12
0x18000fb57  mov     [rdi+rbx+30D0h], r12
0x18000fb5f  mov     [rdi+rbx+30D8h], r12
0x18000fb67  mov     [rdi+rbx+30E0h], r12
0x18000fb6f  mov     [rdi+rbx+30E8h], r12
0x18000fb77  mov     [rdi+rbx+30F0h], r12
0x18000fb7f  mov     [rdi+rbx+30F8h], r12
0x18000fb87  add     rbx, 3100h
0x18000fb8e  cmp     rbp, 2
0x18000fb92  jnz     loc_18000F9E0
0x18000fb98  mov     dword ptr [rdi+62ECh], 2Ah ; '*'
0x18000fba2  mov     dword ptr [rdi+62F4h], 0FEED4h
0x18000fbac  mov     dword ptr [rdi+62F0h], 23423h
0x18000fbb6  mov     [rdi+62E8h], r12d
0x18000fbbd  add     rsp, 20h
0x18000fbc1  pop     r15
0x18000fbc3  pop     r14
0x18000fbc5  pop     r12
0x18000fbc7  pop     rdi
0x18000fbc8  pop     rsi
0x18000fbc9  pop     rbp
0x18000fbca  pop     rbx
0x18000fbcb  retn
```
