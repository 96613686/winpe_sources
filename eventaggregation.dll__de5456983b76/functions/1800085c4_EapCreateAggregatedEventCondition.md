# EapCreateAggregatedEventCondition

- ea: `0x1800085c4`
- end: `0x1800086bf`
- name: `EapCreateAggregatedEventCondition`
- size: `251`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180001e00`

## callees

- `0x180001970`
- `0x180002e30`
- `0x1800085c4`
- `0x1800088d0`

## pseudocode

```c
__int64 __fastcall EapCreateAggregatedEventCondition(__int64 a1, int a2, __int64 a3)
{
  char v3; // bl
  __int64 v4; // rdx
  int v6; // eax
  __int64 v7; // r8
  unsigned int v8; // edi
  __int64 v9; // rcx
  unsigned __int16 v10; // dx
  unsigned int v11; // ebx
  bool v12; // zf
  __int64 v14; // [rsp+20h] [rbp-58h] BYREF
  __int64 v15; // [rsp+28h] [rbp-50h]
  __int64 v16; // [rsp+30h] [rbp-48h]
  int v17; // [rsp+38h] [rbp-40h]
  int v18; // [rsp+3Ch] [rbp-3Ch]
  _QWORD v19[7]; // [rsp+40h] [rbp-38h] BYREF

  v17 = a2;
  v16 = a1;
  v19[0] = &v14;
  v3 = a2;
  v4 = *(_QWORD *)(a1 + 8);
  v19[1] = EapFreeAggregatedEventConditionNextChild;
  v15 = 0;
  v19[4] = EapCreateAggregatedEventConditionVisitNode;
  v18 = 0;
  v14 = 0;
  v19[2] = 0;
  v19[3] = 0;
  v6 = EapTreeTraverse(v19, v4);
  v7 = v14;
  v8 = v6;
  if ( v6 < 0 )
  {
    v10 = WORD1(v15);
  }
  else
  {
    v8 = 0;
    v9 = 56LL * WORD1(v15);
    v10 = WORD1(v15) - 1;
    *(_OWORD *)a3 = *(_OWORD *)(v9 + v14 - 56);
    *(_OWORD *)(a3 + 16) = *(_OWORD *)(v9 + v7 - 40);
    *(_OWORD *)(a3 + 32) = *(_OWORD *)(v9 + v7 - 24);
    *(_QWORD *)(a3 + 48) = *(_QWORD *)(v9 + v7 - 8);
    WORD1(v15) = v10;
  }
  if ( v7 )
  {
    v11 = v3 & 1;
    if ( v10 )
    {
      do
      {
        EapDeleteAggregatedEventCondition(v7 - 56 + 56LL * v10, v11);
        v7 = v14;
        v12 = WORD1(v15) == 1;
        v10 = --WORD1(v15);
      }
      while ( !v12 );
    }
    EaLibFree(v7);
  }
  return v8;
}

```

## disassembly

```asm
0x1800085c4  push    rbp
0x1800085c6  push    rbx
0x1800085c7  push    rsi
0x1800085c8  push    rdi
0x1800085c9  push    r14
0x1800085cb  push    r15
0x1800085cd  mov     rbp, rsp
0x1800085d0  sub     rsp, 78h
0x1800085d4  xor     r14d, r14d
0x1800085d7  mov     [rbp+var_40], edx
0x1800085da  lea     rax, [rbp+var_58]
0x1800085de  mov     [rbp+var_48], rcx
0x1800085e2  mov     [rbp+var_38], rax
0x1800085e6  mov     ebx, edx
0x1800085e8  mov     rdx, [rcx+8]
0x1800085ec  lea     rax, EapFreeAggregatedEventConditionNextChild
0x1800085f3  mov     [rbp+var_30], rax
0x1800085f7  lea     rcx, [rbp+var_38]
0x1800085fb  lea     rax, EapCreateAggregatedEventConditionVisitNode
0x180008602  mov     [rbp+var_50], r14
0x180008606  mov     [rbp+var_18], rax
0x18000860a  mov     rsi, r8
0x18000860d  mov     [rbp+var_3C], r14d
0x180008611  mov     [rbp+var_58], r14
0x180008615  mov     [rbp+var_28], r14
0x180008619  mov     [rbp+var_20], r14
0x18000861d  call    EapTreeTraverse
0x180008622  mov     r8, [rbp+var_58]
0x180008626  mov     edi, eax
0x180008628  mov     r15d, 0FFFFh
0x18000862e  test    eax, eax
0x180008630  js      short loc_180008670
0x180008632  movzx   edx, word ptr [rbp+var_50+2]
0x180008636  mov     edi, r14d
0x180008639  imul    rcx, rdx, 38h ; '8'
0x18000863d  add     dx, r15w
0x180008641  movups  xmm0, xmmword ptr [rcx+r8-38h]
0x180008647  movups  xmmword ptr [rsi], xmm0
0x18000864a  movups  xmm1, xmmword ptr [rcx+r8-28h]
0x180008650  movups  xmmword ptr [rsi+10h], xmm1
0x180008654  movups  xmm0, xmmword ptr [rcx+r8-18h]
0x18000865a  movups  xmmword ptr [rsi+20h], xmm0
0x18000865e  movsd   xmm1, qword ptr [rcx+r8-8]
0x180008665  movsd   qword ptr [rsi+30h], xmm1
0x18000866a  mov     word ptr [rbp+var_50+2], dx
0x18000866e  jmp     short loc_180008674
0x180008670  movzx   edx, word ptr [rbp+var_50+2]
0x180008674  test    r8, r8
0x180008677  jz      short loc_1800086B0
0x180008679  and     ebx, 1
0x18000867c  test    dx, dx
0x18000867f  jz      short loc_1800086A8
0x180008681  movzx   eax, dx
0x180008684  add     r8, 0FFFFFFFFFFFFFFC8h
0x180008688  imul    rcx, rax, 38h ; '8'
0x18000868c  mov     edx, ebx
0x18000868e  add     rcx, r8
0x180008691  call    EapDeleteAggregatedEventCondition
0x180008696  movzx   edx, word ptr [rbp+var_50+2]
0x18000869a  mov     r8, [rbp+var_58]
0x18000869e  add     dx, r15w
0x1800086a2  mov     word ptr [rbp+var_50+2], dx
0x1800086a6  jnz     short loc_180008681
0x1800086a8  mov     rcx, r8
0x1800086ab  call    EaLibFree
0x1800086b0  mov     eax, edi
0x1800086b2  add     rsp, 78h
0x1800086b6  pop     r15
0x1800086b8  pop     r14
0x1800086ba  pop     rdi
0x1800086bb  pop     rsi
0x1800086bc  pop     rbx
0x1800086bd  pop     rbp
0x1800086be  retn
```
