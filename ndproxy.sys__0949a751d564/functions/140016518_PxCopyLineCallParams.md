# PxCopyLineCallParams

- ea: `0x140016518`
- end: `0x140016622`
- name: `PxCopyLineCallParams`
- size: `266`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140015fa0`

## callees

- `0x1400081c0`
- `0x140016518`

## pseudocode

```c
__int64 __fastcall PxCopyLineCallParams(__int64 a1, __int64 a2)
{
  void *v3; // r15
  unsigned int v5; // r12d
  unsigned int v6; // esi
  size_t v7; // r8
  __int64 v8; // rcx
  int v9; // edi
  __int64 v10; // rbx
  __int64 v11; // rdx

  v3 = (void *)((a2 + 188) & 0xFFFFFFFFFFFFFFF8uLL);
  *(_OWORD *)a2 = *(_OWORD *)a1;
  v5 = ((a2 + 188) & 0xFFFFFFF8) - a2;
  v6 = 0;
  *(_OWORD *)(a2 + 16) = *(_OWORD *)(a1 + 16);
  *(_OWORD *)(a2 + 32) = *(_OWORD *)(a1 + 32);
  *(_OWORD *)(a2 + 48) = *(_OWORD *)(a1 + 48);
  *(_OWORD *)(a2 + 64) = *(_OWORD *)(a1 + 64);
  *(_OWORD *)(a2 + 80) = *(_OWORD *)(a1 + 80);
  *(_OWORD *)(a2 + 96) = *(_OWORD *)(a1 + 96);
  *(_OWORD *)(a2 + 112) = *(_OWORD *)(a1 + 112);
  *(_OWORD *)(a2 + 128) = *(_OWORD *)(a1 + 128);
  *(_OWORD *)(a2 + 144) = *(_OWORD *)(a1 + 144);
  *(_OWORD *)(a2 + 160) = *(_OWORD *)(a1 + 160);
  *(_DWORD *)(a2 + 176) = *(_DWORD *)(a1 + 176);
  do
  {
    v7 = *(unsigned int *)(a1 + PxTapiCallParamList[2 * (int)v6]);
    if ( (_DWORD)v7 )
    {
      v8 = PxTapiCallParamList[2 * (int)v6 + 1];
      v9 = (int)v3;
      v10 = (unsigned int)v7;
      v11 = *(unsigned int *)(v8 + a1);
      *(_DWORD *)(v8 + a2) = (_DWORD)v3 - a2;
      memmove(v3, (const void *)(a1 + v11), v7);
      v3 = (void *)(((unsigned __int64)v3 + v10 + 8) & 0xFFFFFFFFFFFFFFF8uLL);
      v5 += (_DWORD)v3 - v9;
    }
    ++v6;
  }
  while ( v6 < 8 );
  return v5;
}

```

## disassembly

```asm
0x140016518  push    rbx
0x14001651a  push    rbp
0x14001651b  push    rsi
0x14001651c  push    rdi
0x14001651d  push    r12
0x14001651f  push    r13
0x140016521  push    r14
0x140016523  push    r15
0x140016525  sub     rsp, 28h
0x140016529  movups  xmm0, xmmword ptr [rcx]
0x14001652c  lea     r15, [rdx+0BCh]
0x140016533  mov     rbp, rdx
0x140016536  and     r15, 0FFFFFFFFFFFFFFF8h
0x14001653a  lea     r13, PxTapiCallParamList
0x140016541  movups  xmmword ptr [rdx], xmm0
0x140016544  mov     r12d, r15d
0x140016547  mov     r14, rcx
0x14001654a  movups  xmm1, xmmword ptr [rcx+10h]
0x14001654e  sub     r12d, edx
0x140016551  xor     esi, esi
0x140016553  movups  xmmword ptr [rdx+10h], xmm1
0x140016557  movups  xmm0, xmmword ptr [rcx+20h]
0x14001655b  movups  xmmword ptr [rdx+20h], xmm0
0x14001655f  movups  xmm1, xmmword ptr [rcx+30h]
0x140016563  movups  xmmword ptr [rdx+30h], xmm1
0x140016567  movups  xmm0, xmmword ptr [rcx+40h]
0x14001656b  movups  xmmword ptr [rdx+40h], xmm0
0x14001656f  movups  xmm1, xmmword ptr [rcx+50h]
0x140016573  movups  xmmword ptr [rdx+50h], xmm1
0x140016577  movups  xmm0, xmmword ptr [rcx+60h]
0x14001657b  movups  xmmword ptr [rdx+60h], xmm0
0x14001657f  movups  xmm1, xmmword ptr [rcx+70h]
0x140016583  movups  xmmword ptr [rdx+70h], xmm1
0x140016587  movups  xmm0, xmmword ptr [rcx+80h]
0x14001658e  movups  xmmword ptr [rdx+80h], xmm0
0x140016595  movups  xmm1, xmmword ptr [rcx+90h]
0x14001659c  movups  xmmword ptr [rdx+90h], xmm1
0x1400165a3  movups  xmm0, xmmword ptr [rcx+0A0h]
0x1400165aa  movups  xmmword ptr [rdx+0A0h], xmm0
0x1400165b1  mov     eax, [rcx+0B0h]
0x1400165b7  mov     [rdx+0B0h], eax
0x1400165bd  movsxd  rcx, esi
0x1400165c0  add     rcx, rcx
0x1400165c3  mov     rax, [r13+rcx*8+0]
0x1400165c8  mov     r8d, [r14+rax]; Size
0x1400165cc  test    r8d, r8d
0x1400165cf  jz      short loc_140016606
0x1400165d1  mov     rcx, [r13+rcx*8+8]
0x1400165d6  mov     eax, r15d
0x1400165d9  sub     eax, ebp
0x1400165db  mov     edi, r15d
0x1400165de  mov     ebx, r8d
0x1400165e1  mov     edx, [rcx+r14]
0x1400165e5  mov     [rcx+rbp], eax
0x1400165e8  add     rdx, r14; Src
0x1400165eb  mov     rcx, r15; void *
0x1400165ee  call    memmove
0x1400165f3  add     r15, 8
0x1400165f7  add     r15, rbx
0x1400165fa  and     r15, 0FFFFFFFFFFFFFFF8h
0x1400165fe  mov     ecx, r15d
0x140016601  sub     ecx, edi
0x140016603  add     r12d, ecx
0x140016606  inc     esi
0x140016608  cmp     esi, 8
0x14001660b  jb      short loc_1400165BD
0x14001660d  mov     eax, r12d
0x140016610  add     rsp, 28h
0x140016614  pop     r15
0x140016616  pop     r14
0x140016618  pop     r13
0x14001661a  pop     r12
0x14001661c  pop     rdi
0x14001661d  pop     rsi
0x14001661e  pop     rbp
0x14001661f  pop     rbx
0x140016620  retn
```
