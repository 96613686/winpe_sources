# __FrameHandler4::GetRangeOfTrysToCheck(FH4::TryBlockMap4 &,int,_xDISPATCHER_CONTEXT *,FH4::FuncInfo4 *,int)

- ea: `0x1800021a4`
- end: `0x180002301`
- name: `?GetRangeOfTrysToCheck@__FrameHandler4@@SA?AU?$pair@Viterator@TryBlockMap4@FH4@@V123@@std@@AEAVTryBlockMap4@FH4@@HPEAU_xDISPATCHER_CONTEXT@@PEAUFuncInfo4@5@H@Z`
- size: `349`
- prototype: `__int64 __fastcall(__int64, int *, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x1800033d8`
- `0x1800038f4`

## callees

- `0x1800021a4`
- `0x180002438`

## pseudocode

```c
__int64 __fastcall __FrameHandler4::GetRangeOfTrysToCheck(__int64 a1, int *a2, int a3)
{
  int v6; // ebx
  int v7; // r14d
  int v8; // r12d
  _BYTE *v9; // r13
  signed int v10; // r11d
  int v11; // r10d
  __int64 v12; // rcx
  __int64 v13; // r9
  unsigned int v14; // r11d
  __int64 v15; // rcx
  __int64 v16; // r8
  _BYTE *v17; // rdx
  int v18; // eax
  __int64 v19; // rcx
  _DWORD *v20; // r13
  int v21; // eax
  int v22; // eax
  __int64 result; // rax
  int *v24; // [rsp+20h] [rbp-58h] BYREF
  int v25; // [rsp+28h] [rbp-50h]
  int v26; // [rsp+2Ch] [rbp-4Ch]

  v24 = a2;
  v25 = 0;
  v6 = v26;
  v7 = 0;
  FH4::TryBlockMap4::setBuffer(a2, &v24);
  v8 = *a2;
  if ( *a2 )
  {
    v9 = (_BYTE *)*((_QWORD *)a2 + 1);
    v10 = a2[6];
    v11 = 0;
    do
    {
      if ( a3 >= v10 && a3 <= a2[7] )
        v7 = v11;
      v12 = *v9 & 0xF;
      ++v11;
      v13 = *((char *)&FH4::s_negLengthTab + v12);
      LOBYTE(v12) = *((_BYTE *)&FH4::s_shiftTab + v12);
      v14 = *(_DWORD *)&v9[-v13 - 4];
      *((_QWORD *)a2 + 1) = &v9[-v13];
      v10 = v14 >> v12;
      a2[6] = v10;
      v15 = v9[-v13] & 0xF;
      v16 = *((char *)&FH4::s_negLengthTab + v15);
      v17 = &v9[-v16 - v13];
      v18 = *((_DWORD *)v17 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v15);
      *((_QWORD *)a2 + 1) = v17;
      a2[7] = v18;
      v19 = *v17 & 0xF;
      v20 = &v9[-*((char *)&FH4::s_negLengthTab + v19) - v16 - v13];
      v21 = *(v20 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v19);
      *((_QWORD *)a2 + 1) = v20;
      a2[8] = v21;
      v22 = *v20;
      v9 = v20 + 1;
      *((_QWORD *)a2 + 1) = v9;
      a2[9] = v22;
    }
    while ( v11 != v8 );
    v6 = v26;
  }
  v24 = a2;
  v25 = 0;
  v26 = v6;
  FH4::TryBlockMap4::setBuffer(a2, &v24);
  *(_QWORD *)a1 = a2;
  *(_DWORD *)(a1 + 24) = v7 + 1;
  *(_DWORD *)(a1 + 28) = v26;
  result = a1;
  *(_DWORD *)(a1 + 8) = 0;
  *(_DWORD *)(a1 + 12) = v6;
  *(_QWORD *)(a1 + 16) = a2;
  return result;
}

```

## disassembly

```asm
0x1800021a4  mov     rax, rsp
0x1800021a7  push    rbx
0x1800021a8  push    rbp
0x1800021a9  push    rsi
0x1800021aa  push    rdi
0x1800021ab  push    r12
0x1800021ad  push    r13
0x1800021af  push    r14
0x1800021b1  push    r15
0x1800021b3  sub     rsp, 38h
0x1800021b7  mov     rdi, rdx
0x1800021ba  mov     [rax-58h], rdx
0x1800021be  mov     rsi, rcx
0x1800021c1  lea     rdx, [rax-58h]
0x1800021c5  xor     ebp, ebp
0x1800021c7  mov     rcx, rdi
0x1800021ca  mov     [rax-50h], ebp
0x1800021cd  mov     r15d, r8d
0x1800021d0  mov     ebx, [rsp+78h+var_4C]
0x1800021d4  xor     r14d, r14d
0x1800021d7  mov     [rax-4Ch], ebx
0x1800021da  call    ?setBuffer@TryBlockMap4@FH4@@QEAAXViterator@12@@Z; FH4::TryBlockMap4::setBuffer(FH4::TryBlockMap4::iterator)
0x1800021df  mov     r12d, [rdi]
0x1800021e2  test    r12d, r12d
0x1800021e5  jz      loc_1800022B8
0x1800021eb  mov     r13, [rdi+8]
0x1800021ef  lea     rbx, cs:180000000h
0x1800021f6  mov     r11d, [rdi+18h]
0x1800021fa  xor     r10d, r10d
0x1800021fd  cmp     r15d, r11d
0x180002200  jl      short loc_180002215
0x180002202  cmp     r15d, [rdi+1Ch]
0x180002206  jg      short loc_180002215
0x180002208  test    ebp, ebp
0x18000220a  mov     eax, r10d
0x18000220d  mov     r14d, r10d
0x180002210  cmovz   eax, ebp
0x180002213  mov     ebp, eax
0x180002215  movzx   ecx, byte ptr [r13+0]
0x18000221a  mov     rax, r13
0x18000221d  and     ecx, 0Fh
0x180002220  mov     rdx, r13
0x180002223  inc     r10d
0x180002226  movsx   r9, byte ptr [rcx+rbx+10238h]
0x18000222f  mov     cl, [rcx+rbx+10248h]
0x180002236  sub     rax, r9
0x180002239  mov     r11d, [rax-4]
0x18000223d  mov     [rdi+8], rax
0x180002241  shr     r11d, cl
0x180002244  mov     [rdi+18h], r11d
0x180002248  movzx   ecx, byte ptr [rax]
0x18000224b  and     ecx, 0Fh
0x18000224e  movsx   r8, byte ptr [rcx+rbx+10238h]
0x180002257  mov     cl, [rcx+rbx+10248h]
0x18000225e  sub     rdx, r8
0x180002261  sub     rdx, r9
0x180002264  mov     eax, [rdx-4]
0x180002267  shr     eax, cl
0x180002269  mov     [rdi+8], rdx
0x18000226d  mov     [rdi+1Ch], eax
0x180002270  movzx   ecx, byte ptr [rdx]
0x180002273  and     ecx, 0Fh
0x180002276  movsx   rax, byte ptr [rcx+rbx+10238h]
0x18000227f  mov     cl, [rcx+rbx+10248h]
0x180002286  sub     r13, rax
0x180002289  sub     r13, r8
0x18000228c  sub     r13, r9
0x18000228f  mov     eax, [r13-4]
0x180002293  shr     eax, cl
0x180002295  mov     [rdi+8], r13
0x180002299  mov     [rdi+20h], eax
0x18000229c  mov     eax, [r13+0]
0x1800022a0  add     r13, 4
0x1800022a4  mov     [rdi+8], r13
0x1800022a8  mov     [rdi+24h], eax
0x1800022ab  cmp     r10d, r12d
0x1800022ae  jnz     loc_1800021FD
0x1800022b4  mov     ebx, [rsp+78h+var_4C]
0x1800022b8  lea     rdx, [rsp+78h+var_58]
0x1800022bd  mov     [rsp+78h+var_58], rdi
0x1800022c2  mov     rcx, rdi
0x1800022c5  mov     [rsp+78h+var_50], ebp
0x1800022c9  mov     [rsp+78h+var_4C], ebx
0x1800022cd  call    ?setBuffer@TryBlockMap4@FH4@@QEAAXViterator@12@@Z; FH4::TryBlockMap4::setBuffer(FH4::TryBlockMap4::iterator)
0x1800022d2  lea     eax, [r14+1]
0x1800022d6  mov     [rsi], rdi
0x1800022d9  mov     [rsi+18h], eax
0x1800022dc  mov     eax, [rsp+78h+var_4C]
0x1800022e0  mov     [rsi+1Ch], eax
0x1800022e3  mov     rax, rsi
0x1800022e6  mov     [rsi+8], ebp
0x1800022e9  mov     [rsi+0Ch], ebx
0x1800022ec  mov     [rsi+10h], rdi
0x1800022f0  add     rsp, 38h
0x1800022f4  pop     r15
0x1800022f6  pop     r14
0x1800022f8  pop     r13
0x1800022fa  pop     r12
0x1800022fc  pop     rdi
0x1800022fd  pop     rsi
0x1800022fe  pop     rbp
0x1800022ff  pop     rbx
0x180002300  retn
```
