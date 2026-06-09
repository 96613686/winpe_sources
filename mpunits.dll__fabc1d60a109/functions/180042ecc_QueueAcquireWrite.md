# QueueAcquireWrite

- ea: `0x180042ecc`
- end: `0x18004311a`
- name: `QueueAcquireWrite`
- size: `590`
- prototype: ``
- caller_count: `60`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009d30`
- `0x180009f50`
- `0x18000a030`
- `0x18000a720`
- `0x18000a770`
- `0x18000a8d0`
- `0x18000a920`
- `0x18000a9a0`
- `0x1800195d0`
- `0x180019770`
- `0x180019bb0`
- `0x180019cd0`
- `0x180019d30`
- `0x180019db0`
- `0x18001b8a0`
- `0x18001b930`
- `0x18001b990`
- `0x18001bbe0`
- `0x180021110`
- `0x1800213c0`
- `0x180021780`
- `0x180021c40`
- `0x180021e90`
- `0x1800225a0`
- `0x180022770`
- `0x180022a20`
- `0x180022b00`
- `0x180022bd0`
- `0x180022f20`
- `0x180023470`
- `0x180034390`
- `0x180034430`
- `0x1800344b0`
- `0x1800347b0`
- `0x180038fc0`
- `0x180039050`
- `0x180039130`
- `0x1800391c0`
- `0x1800392c8`
- `0x180039330`
- `0x180039530`
- `0x18003c220`
- `0x18003c2b0`
- `0x18003c540`
- `0x18003e004`
- `0x18003e0b8`
- `0x18003f270`
- `0x18003f470`
- `0x18003f6d8`
- `0x18003f748`

## callees

- `0x180042ecc`
- `0x18004379c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SwitchToThread` at `0x180042f62`
- `api-ms-win-core-processthreads-l1-1-0!SwitchToThread` at `0x180042f62`

## pseudocode

```c
signed __int64 __fastcall QueueAcquireWrite(unsigned __int64 a1)
{
  unsigned __int64 v2; // rdi
  unsigned __int64 v3; // r8
  unsigned __int64 v4; // rax
  unsigned __int64 v5; // rax
  __int64 v6; // rbp
  unsigned __int64 v7; // rdx
  unsigned __int64 v8; // rsi
  unsigned __int64 v9; // r10
  __int64 v10; // r9
  __int64 v11; // r8
  unsigned __int64 v12; // r8
  unsigned __int64 v13; // r8
  unsigned __int64 v14; // rax
  bool v15; // zf
  signed __int64 result; // rax
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // rcx
  unsigned __int64 v19; // rcx

  do
  {
    while ( 1 )
    {
      _m_prefetchw((const void *)a1);
      v2 = *(_QWORD *)a1;
      v3 = *(_QWORD *)a1;
      if ( *(_QWORD *)a1 <= 0x1FFFu )
      {
        v4 = __rdtsc();
        v5 = 4 * (((unsigned __int64)HIDWORD(v4) << 32) | (unsigned int)v4 & 0xFFFFF800);
        v3 = v5 ^ (v2 ^ v5) & 0xFFFFFFFFFFFE1FFFuLL;
      }
      v6 = (v3 >> 25) & 0x1FFF;
      v7 = (v3 + 0x2000000) ^ (v3 ^ (v3 + 0x2000000)) & 0xFFFFFFC001FFFFFFuLL;
      if ( (v7 & 0x3FFE000000LL) != ((v7 >> 26) & 0x3FFE000000LL) )
        break;
      SwitchToThread();
    }
  }
  while ( v2 != _InterlockedCompareExchange64(
                  (volatile signed __int64 *)a1,
                  (v7 << 13) ^ ((v7 << 13) ^ v7) & 0xFFF8003FFFFFFFFFuLL,
                  v2) );
  v8 = (unsigned __int8)(v2 >> 17);
  do
  {
    while ( 1 )
    {
      v9 = *(_QWORD *)a1;
      v10 = *(_QWORD *)a1 >> 51;
      v11 = *(_QWORD *)a1 & 0x1FFFLL;
      if ( v10 == v6 && !v11 )
      {
        v12 = (v9 + 0x1FFF) ^ ((v9 + 0x1FFF) ^ (v9 + 0x8000000001FFFLL)) & 0xFFF8000000000000uLL;
        if ( ((v12 >> 26) & 0x3FFE000000LL) == (v12 & 0x3FFE000000LL) )
        {
          v13 = v12 & 0x1FFF;
        }
        else
        {
          v14 = __rdtsc();
          v13 = v12 & 0xFFFFFFFFFE001FFFuLL | (4 * (((unsigned __int64)(unsigned __int8)v8 << 15) | v14 & 0x7800));
        }
        result = _InterlockedCompareExchange64((volatile signed __int64 *)a1, v13, v9);
        v15 = v9 == result;
        goto LABEL_13;
      }
      v17 = __rdtsc();
      if ( (((unsigned __int8)((((unsigned __int64)HIDWORD(v17) << 32) | (unsigned int)v17) >> 11)
           - (unsigned __int8)(v9 >> 13))
          & 0xE) == 0
        && ((v9 >> 25) & 0x1FFF) - v10 >= 2
        && ((v9 >> 25) & 0x1FFF) == ((v2 >> 25) & 0x1FFF) + 1
        && !v11 )
      {
        break;
      }
      if ( (unsigned int)CondLock_Wait(a1 ^ v6, a1, *(_QWORD *)a1, -(__int64)((v8 & 0x80u) != 0LL) - 2) )
      {
        v19 = v8;
        v8 -= 2LL;
        if ( v19 <= 2 )
          v8 = 0;
      }
      else if ( v8 < 0xFF )
      {
        ++v8;
      }
    }
    if ( v2 > 0x1FFF )
      v18 = v2 ^ (v2 ^ (v9 + 0x1FFF)) & 0xFFF8000001FFFFFFuLL;
    else
      v18 = 0x1FFF;
    result = _InterlockedCompareExchange64((volatile signed __int64 *)a1, v18, v9);
    v15 = v9 == result;
LABEL_13:
    ;
  }
  while ( !v15 );
  return result;
}

```

## disassembly

```asm
0x180042ecc  mov     [rsp+arg_8], rbx
0x180042ed1  mov     [rsp+arg_10], rbp
0x180042ed6  push    rsi
0x180042ed7  push    rdi
0x180042ed8  push    r12
0x180042eda  push    r14
0x180042edc  push    r15
0x180042ede  sub     rsp, 20h
0x180042ee2  mov     rbx, rcx
0x180042ee5  mov     r15d, 1FFFh
0x180042eeb  mov     r12, 3FFE000000h
0x180042ef5  prefetchw byte ptr [rbx]
0x180042ef8  mov     rdi, [rbx]
0x180042efb  mov     r8, rdi
0x180042efe  cmp     rdi, r15
0x180042f01  ja      short loc_180042F26
0x180042f03  rdtsc
0x180042f05  shl     rdx, 20h
0x180042f09  or      rax, rdx
0x180042f0c  and     rax, 0FFFFFFFFFFFFF800h
0x180042f12  shl     rax, 2
0x180042f16  mov     r8, rax
0x180042f19  xor     r8, rdi
0x180042f1c  and     r8, 0FFFFFFFFFFFE1FFFh
0x180042f23  xor     r8, rax
0x180042f26  lea     rax, [r8+2000000h]
0x180042f2d  mov     rcx, 0FFFFFFC001FFFFFFh
0x180042f37  mov     rdx, rax
0x180042f3a  mov     rbp, r8
0x180042f3d  xor     rdx, r8
0x180042f40  shr     rbp, 19h
0x180042f44  and     rdx, rcx
0x180042f47  and     rbp, r15
0x180042f4a  xor     rdx, rax
0x180042f4d  mov     rcx, rdx
0x180042f50  mov     rax, rdx
0x180042f53  shr     rcx, 1Ah
0x180042f57  and     rax, r12
0x180042f5a  and     rcx, r12
0x180042f5d  cmp     rax, rcx
0x180042f60  jnz     short loc_180042F6A
0x180042f62  call    cs:__imp_SwitchToThread
0x180042f68  jmp     short loc_180042EF5
0x180042f6a  mov     rax, rdx
0x180042f6d  mov     rcx, 0FFF8003FFFFFFFFFh
0x180042f77  shl     rax, 0Dh
0x180042f7b  xor     rdx, rax
0x180042f7e  and     rdx, rcx
0x180042f81  xor     rdx, rax
0x180042f84  mov     rax, rdi
0x180042f87  lock cmpxchg [rbx], rdx
0x180042f8c  jnz     loc_180042EF5
0x180042f92  mov     r14, rbp
0x180042f95  mov     rax, rdi
0x180042f98  xor     r14, rbx
0x180042f9b  shr     rax, 11h
0x180042f9f  movzx   esi, al
0x180042fa2  mov     r10, [rbx]
0x180042fa5  mov     r9, r10
0x180042fa8  mov     r8, r10
0x180042fab  shr     r9, 33h
0x180042faf  and     r8, r15
0x180042fb2  cmp     r9, rbp
0x180042fb5  jnz     loc_180043057
0x180042fbb  test    r8, r8
0x180042fbe  jnz     loc_180043057
0x180042fc4  lea     rax, [r10+1FFFh]
0x180042fcb  mov     rcx, 0FFF8000000000000h
0x180042fd5  mov     r8, 8000000001FFFh
0x180042fdf  add     r8, r10
0x180042fe2  xor     r8, rax
0x180042fe5  and     r8, rcx
0x180042fe8  xor     r8, rax
0x180042feb  mov     rcx, r8
0x180042fee  mov     rax, r8
0x180042ff1  shr     rcx, 1Ah
0x180042ff5  and     rax, r12
0x180042ff8  and     rcx, r12
0x180042ffb  cmp     rcx, rax
0x180042ffe  jnz     short loc_180043005
0x180043000  and     r8, r15
0x180043003  jmp     short loc_180043032
0x180043005  rdtsc
0x180043007  shl     rdx, 20h
0x18004300b  or      rax, rdx
0x18004300e  movzx   ecx, sil
0x180043012  shl     rcx, 0Fh
0x180043016  and     eax, 7800h
0x18004301b  or      rax, rcx
0x18004301e  mov     rcx, r8
0x180043021  shl     rax, 2
0x180043025  and     rcx, 0FFFFFFFFFE001FFFh
0x18004302c  mov     r8, rax
0x18004302f  or      r8, rcx
0x180043032  mov     rax, r10
0x180043035  lock cmpxchg [rbx], r8
0x18004303a  jnz     loc_180042FA2
0x180043040  mov     rbx, [rsp+48h+arg_8]
0x180043045  mov     rbp, [rsp+48h+arg_10]
0x18004304a  add     rsp, 20h
0x18004304e  pop     r15
0x180043050  pop     r14
0x180043052  pop     r12
0x180043054  pop     rdi
0x180043055  pop     rsi
0x180043056  retn
0x180043057  rdtsc
0x180043059  shl     rdx, 20h
0x18004305d  mov     rcx, r10
0x180043060  or      rax, rdx
0x180043063  shr     rcx, 0Dh
0x180043067  shr     rax, 0Bh
0x18004306b  sub     al, cl
0x18004306d  test    al, 0Eh
0x18004306f  jnz     short loc_1800430CF
0x180043071  mov     rcx, r10
0x180043074  shr     rcx, 19h
0x180043078  and     rcx, r15
0x18004307b  mov     rax, rcx
0x18004307e  sub     rax, r9
0x180043081  cmp     rax, 2
0x180043085  jb      short loc_1800430CF
0x180043087  mov     rax, rdi
0x18004308a  shr     rax, 19h
0x18004308e  and     rax, r15
0x180043091  inc     rax
0x180043094  cmp     rcx, rax
0x180043097  jnz     short loc_1800430CF
0x180043099  test    r8, r8
0x18004309c  jnz     short loc_1800430CF
0x18004309e  cmp     rdi, r15
0x1800430a1  ja      short loc_1800430A8
0x1800430a3  mov     rcx, r15
0x1800430a6  jmp     short loc_1800430C2
0x1800430a8  lea     rcx, [r10+1FFFh]
0x1800430af  mov     rax, 0FFF8000001FFFFFFh
0x1800430b9  xor     rcx, rdi
0x1800430bc  and     rcx, rax
0x1800430bf  xor     rcx, rdi
0x1800430c2  mov     rax, r10
0x1800430c5  lock cmpxchg [rbx], rcx
0x1800430ca  jmp     loc_18004303A
0x1800430cf  mov     al, sil
0x1800430d2  mov     r8, r10
0x1800430d5  and     al, 80h
0x1800430d7  mov     rdx, rbx
0x1800430da  neg     al
0x1800430dc  mov     rcx, r14
0x1800430df  sbb     r9, r9
0x1800430e2  add     r9, 0FFFFFFFFFFFFFFFEh
0x1800430e6  call    CondLock_Wait
0x1800430eb  test    eax, eax
0x1800430ed  jz      short loc_180043105
0x1800430ef  mov     rcx, rsi
0x1800430f2  xor     eax, eax
0x1800430f4  add     rsi, 0FFFFFFFFFFFFFFFEh
0x1800430f8  cmp     rcx, 2
0x1800430fc  cmovbe  rsi, rax
0x180043100  jmp     loc_180042FA2
0x180043105  cmp     rsi, 0FFh
0x18004310c  jnb     loc_180042FA2
0x180043112  inc     rsi
0x180043115  jmp     loc_180042FA2
```
