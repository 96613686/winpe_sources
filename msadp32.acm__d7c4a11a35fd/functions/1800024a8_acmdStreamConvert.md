# acmdStreamConvert

- ea: `0x1800024a8`
- end: `0x18000259a`
- name: `acmdStreamConvert`
- size: `242`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001cd0`

## callees

- `0x1800024a8`
- `0x180006010`

## pseudocode

```c
__int64 __fastcall acmdStreamConvert(__int64 a1, __int64 a2, __int64 a3)
{
  _WORD *v3; // r10
  unsigned __int16 *v5; // rax
  int v6; // r9d
  unsigned int v7; // edi
  unsigned int v8; // ecx
  unsigned int v9; // eax
  int v10; // r8d
  unsigned int v11; // edi
  unsigned int v12; // eax
  unsigned int v13; // r11d
  unsigned int v14; // r11d

  v3 = *(_WORD **)(a2 + 12);
  v5 = *(unsigned __int16 **)(a2 + 4);
  v6 = *(_DWORD *)(a3 + 64) & 4;
  if ( *v3 == 1 )
  {
    v14 = *(_DWORD *)(a3 + 24);
    v3 = *(_WORD **)(a2 + 4);
    if ( v6 )
      v14 -= v14 % v5[6];
    goto LABEL_11;
  }
  v7 = v5[7];
  v8 = v5[1];
  v9 = *(_DWORD *)(a3 + 24);
  v10 = 0;
  v11 = v7 >> 3 << (v8 >> 1);
  v12 = v9 / v11;
  v13 = v12;
  if ( v6 )
    v13 = v12 - v12 % (unsigned __int16)v3[9];
  if ( v13 >= 2 )
  {
    v14 = v11 * (v13 & 0xFFFFFFFE);
LABEL_11:
    *(_DWORD *)(a3 + 28) = v14;
    *(_DWORD *)(a3 + 52) = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD, _WORD *))(a2 + 52))(
                             *(_QWORD *)(a3 + 16),
                             v14,
                             *(_QWORD *)(a3 + 40),
                             *(unsigned int *)(a3 + 48),
                             (unsigned __int16)v3[6],
                             (unsigned __int16)v3[9],
                             (unsigned __int16)v3[10],
                             v3 + 11);
    return 0;
  }
  *(_DWORD *)(a3 + 52) = 0;
  if ( !v6 )
    v10 = *(_DWORD *)(a3 + 24);
  *(_DWORD *)(a3 + 28) = v10;
  return 0;
}

```

## disassembly

```asm
0x1800024a8  mov     [rsp+arg_0], rbx
0x1800024ad  mov     [rsp+arg_8], rsi
0x1800024b2  push    rdi
0x1800024b3  sub     rsp, 50h
0x1800024b7  mov     r10, [rdx+0Ch]
0x1800024bb  mov     ecx, 1
0x1800024c0  mov     r9d, [r8+40h]
0x1800024c4  mov     rbx, r8
0x1800024c7  mov     rax, [rdx+4]
0x1800024cb  and     r9d, 4
0x1800024cf  mov     rsi, rdx
0x1800024d2  cmp     cx, [r10]
0x1800024d6  jz      short loc_180002528
0x1800024d8  movzx   edi, word ptr [rax+0Eh]
0x1800024dc  xor     edx, edx
0x1800024de  movzx   ecx, word ptr [rax+2]
0x1800024e2  mov     eax, [r8+18h]
0x1800024e6  xor     r8d, r8d
0x1800024e9  shr     edi, 3
0x1800024ec  shr     ecx, 1
0x1800024ee  shl     edi, cl
0x1800024f0  div     edi
0x1800024f2  mov     r11d, eax
0x1800024f5  test    r9d, r9d
0x1800024f8  jz      short loc_180002506
0x1800024fa  movzx   ecx, word ptr [r10+12h]
0x1800024ff  xor     edx, edx
0x180002501  div     ecx
0x180002503  sub     r11d, edx
0x180002506  cmp     r11d, 2
0x18000250a  jnb     short loc_18000251E
0x18000250c  mov     [rbx+34h], r8d
0x180002510  test    r9d, r9d
0x180002513  cmovz   r8d, [rbx+18h]
0x180002518  mov     [rbx+1Ch], r8d
0x18000251c  jmp     short loc_180002588
0x18000251e  and     r11d, 0FFFFFFFEh
0x180002522  imul    r11d, edi
0x180002526  jmp     short loc_180002542
0x180002528  mov     r11d, [r8+18h]
0x18000252c  mov     r10, rax
0x18000252f  test    r9d, r9d
0x180002532  jz      short loc_180002542
0x180002534  movzx   ecx, word ptr [rax+0Ch]
0x180002538  xor     edx, edx
0x18000253a  mov     eax, r11d
0x18000253d  div     ecx
0x18000253f  sub     r11d, edx
0x180002542  mov     [rbx+1Ch], r11d
0x180002546  lea     rcx, [r10+16h]
0x18000254a  movzx   r8d, word ptr [r10+14h]
0x18000254f  mov     edx, r11d
0x180002552  movzx   r9d, word ptr [r10+12h]
0x180002557  movzx   r10d, word ptr [r10+0Ch]
0x18000255c  mov     rax, [rsi+34h]
0x180002560  mov     [rsp+58h+var_20], rcx
0x180002565  mov     rcx, [rbx+10h]
0x180002569  mov     [rsp+58h+var_28], r8d
0x18000256e  mov     r8, [rbx+28h]
0x180002572  mov     [rsp+58h+var_30], r9d
0x180002577  mov     r9d, [rbx+30h]
0x18000257b  mov     [rsp+58h+var_38], r10d
0x180002580  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002585  mov     [rbx+34h], eax
0x180002588  mov     rbx, [rsp+58h+arg_0]
0x18000258d  xor     eax, eax
0x18000258f  mov     rsi, [rsp+58h+arg_8]
0x180002594  add     rsp, 50h
0x180002598  pop     rdi
0x180002599  retn
```
