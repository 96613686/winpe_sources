# CompressedStreamDump::CompressedMemStream::AddNewBucket(void)

- ea: `0x18001dd28`
- end: `0x18001ddd0`
- name: `?AddNewBucket@CompressedMemStream@CompressedStreamDump@@AEAAXXZ`
- size: `168`
- prototype: `void __fastcall(CompressedStreamDump::CompressedMemStream *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001db40`

## callees

- `0x180001710`
- `0x18001cf78`
- `0x18001dd28`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CompressedStreamDump::CompressedMemStream::AddNewBucket(
        CompressedStreamDump::CompressedMemStream *this)
{
  _QWORD *v2; // rcx
  __int64 v3; // rdx
  __int128 v4; // xmm1
  _BYTE v5[40]; // [rsp+20h] [rbp-38h] BYREF

  v2 = (_QWORD *)((char *)this + 312);
  memset(&v5[8], 0, 32);
  v3 = v2[1];
  *(_QWORD *)v5 = 0xCCCCCCCCCCCCCCCDuLL * ((v3 - *v2) >> 3);
  if ( v3 == v2[2] )
  {
    std::vector<MemoryBucket>::_Emplace_reallocate<MemoryBucket const &>(v2, v3, v5);
  }
  else
  {
    v4 = *(_OWORD *)&v5[16];
    *(_OWORD *)v3 = *(_OWORD *)v5;
    *(_OWORD *)(v3 + 16) = v4;
    *(_QWORD *)(v3 + 32) = *(_OWORD *)&_mm_unpackhi_pd((__m128d)0LL, (__m128d)0LL);
    v2[1] += 40LL;
  }
  *((_QWORD *)this + 42) = *((_QWORD *)this + 40) - 40LL;
}

```

## disassembly

```asm
0x18001dd28  push    rbx
0x18001dd2a  sub     rsp, 50h
0x18001dd2e  mov     rax, cs:__security_cookie
0x18001dd35  xor     rax, rsp
0x18001dd38  mov     [rsp+58h+var_10], rax
0x18001dd3d  mov     rbx, rcx
0x18001dd40  mov     r8, 0CCCCCCCCCCCCCCCDh
0x18001dd4a  add     rcx, 138h
0x18001dd51  xorps   xmm0, xmm0
0x18001dd54  xorps   xmm2, xmm2
0x18001dd57  movdqu  [rsp+58h+var_38+8], xmm0
0x18001dd5d  mov     rdx, [rcx+8]
0x18001dd61  mov     rax, rdx
0x18001dd64  sub     rax, [rcx]
0x18001dd67  sar     rax, 3
0x18001dd6b  imul    rax, r8
0x18001dd6f  movdqu  [rsp+58h+var_20], xmm2
0x18001dd75  mov     qword ptr [rsp+58h+var_38], rax
0x18001dd7a  cmp     rdx, [rcx+10h]
0x18001dd7e  jz      short loc_18001DDA1
0x18001dd80  movups  xmm0, [rsp+58h+var_38]
0x18001dd85  movups  xmm1, xmmword ptr [rsp+30h]
0x18001dd8a  movups  xmmword ptr [rdx], xmm0
0x18001dd8d  movups  xmmword ptr [rdx+10h], xmm1
0x18001dd91  unpckhpd xmm2, xmm2
0x18001dd95  movsd   qword ptr [rdx+20h], xmm2
0x18001dd9a  add     qword ptr [rcx+8], 28h ; '('
0x18001dd9f  jmp     short loc_18001DDAB
0x18001dda1  lea     r8, [rsp+58h+var_38]
0x18001dda6  call    ??$_Emplace_reallocate@AEBUMemoryBucket@@@?$vector@UMemoryBucket@@V?$allocator@UMemoryBucket@@@std@@@std@@AEAAPEAUMemoryBucket@@QEAU2@AEBU2@@Z; std::vector<MemoryBucket>::_Emplace_reallocate<MemoryBucket const &>(MemoryBucket * const,MemoryBucket const &)
0x18001ddab  mov     rax, [rbx+140h]
0x18001ddb2  sub     rax, 28h ; '('
0x18001ddb6  mov     [rbx+150h], rax
0x18001ddbd  mov     rcx, [rsp+58h+var_10]
0x18001ddc2  xor     rcx, rsp; StackCookie
0x18001ddc5  call    __security_check_cookie
0x18001ddca  add     rsp, 50h
0x18001ddce  pop     rbx
0x18001ddcf  retn
```
