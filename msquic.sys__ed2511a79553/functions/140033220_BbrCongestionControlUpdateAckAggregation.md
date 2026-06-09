# BbrCongestionControlUpdateAckAggregation

- ea: `0x140033220`
- end: `0x1400332f5`
- name: `BbrCongestionControlUpdateAckAggregation`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140032950`

## callees

- `0x1400321a0`
- `0x140033220`
- `0x1400336a0`

## pseudocode

```c
unsigned __int64 __fastcall BbrCongestionControlUpdateAckAggregation(__int64 a1, __int64 a2)
{
  char v2; // r11
  __int64 Bandwidth; // rax
  char v7; // r11
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // r10
  __int64 v10; // rax
  unsigned __int64 v11; // rsi
  __int64 v12; // r8

  v2 = *(_BYTE *)(a1 + 136);
  if ( (v2 & 0x10) == 0 )
  {
    *(_QWORD *)(a1 + 200) = *(_QWORD *)a2;
    *(_BYTE *)(a1 + 136) = v2 | 0x10;
    return 0;
  }
  Bandwidth = BbrCongestionControlGetBandwidth();
  v8 = *(_QWORD *)(a1 + 208);
  v9 = (*(_QWORD *)a2 - *(_QWORD *)(a1 + 200)) * Bandwidth;
  v10 = *(unsigned int *)(a2 + 32);
  v11 = v9 / 0x7A1200;
  if ( v8 <= v9 / 0x7A1200 )
  {
    *(_QWORD *)(a1 + 208) = v10;
    *(_QWORD *)(a1 + 200) = *(_QWORD *)a2;
    *(_BYTE *)(a1 + 136) = v7 | 0x10;
    return 0;
  }
  v12 = *(_QWORD *)(a1 + 168);
  *(_QWORD *)(a1 + 208) = v8 + v10;
  QuicSlidingWindowExtremumUpdateMax(a1 + 272, v8 + v10 - v11, v12);
  return *(_QWORD *)(a1 + 208) - v11;
}

```

## disassembly

```asm
0x140033220  mov     [rsp+arg_0], rbx
0x140033225  mov     [rsp+arg_8], rsi
0x14003322a  push    rdi
0x14003322b  sub     rsp, 20h
0x14003322f  mov     r11b, [rcx+88h]
0x140033236  mov     rdi, rdx
0x140033239  mov     rbx, rcx
0x14003323c  test    r11b, 10h
0x140033240  jnz     short loc_14003325E
0x140033242  mov     rax, [rdx]
0x140033245  or      r11b, 10h
0x140033249  mov     [rcx+0C8h], rax
0x140033250  mov     [rcx+88h], r11b
0x140033257  xor     eax, eax
0x140033259  jmp     loc_1400332E4
0x14003325e  call    BbrCongestionControlGetBandwidth
0x140033263  mov     rdx, [rdi]
0x140033266  mov     r10, rax
0x140033269  sub     rdx, [rbx+0C8h]
0x140033270  mov     rax, 431BDE82D7B634DBh
0x14003327a  mov     rcx, [rbx+0D0h]
0x140033281  imul    r10, rdx
0x140033285  mul     r10
0x140033288  mov     eax, [rdi+20h]
0x14003328b  mov     rsi, rdx
0x14003328e  shr     rsi, 12h
0x140033292  shr     rsi, 3
0x140033296  cmp     rcx, rsi
0x140033299  ja      short loc_1400332B9
0x14003329b  mov     [rbx+0D0h], rax
0x1400332a2  or      r11b, 10h
0x1400332a6  mov     rax, [rdi]
0x1400332a9  mov     [rbx+0C8h], rax
0x1400332b0  mov     [rbx+88h], r11b
0x1400332b7  jmp     short loc_140033257
0x1400332b9  mov     r8, [rbx+0A8h]
0x1400332c0  lea     rdx, [rcx+rax]
0x1400332c4  mov     [rbx+0D0h], rdx
0x1400332cb  lea     rcx, [rbx+110h]
0x1400332d2  sub     rdx, rsi
0x1400332d5  call    QuicSlidingWindowExtremumUpdateMax
0x1400332da  mov     rax, [rbx+0D0h]
0x1400332e1  sub     rax, rsi
0x1400332e4  mov     rbx, [rsp+28h+arg_0]
0x1400332e9  mov     rsi, [rsp+28h+arg_8]
0x1400332ee  add     rsp, 20h
0x1400332f2  pop     rdi
0x1400332f3  retn
```
