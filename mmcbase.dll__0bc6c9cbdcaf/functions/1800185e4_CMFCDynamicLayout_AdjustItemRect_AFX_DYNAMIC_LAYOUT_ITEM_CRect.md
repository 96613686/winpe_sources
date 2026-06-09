# CMFCDynamicLayout::AdjustItemRect(AFX_DYNAMIC_LAYOUT_ITEM &,CRect &)

- ea: `0x1800185e4`
- end: `0x18001879d`
- name: `?AdjustItemRect@CMFCDynamicLayout@@IEBAIAEAUAFX_DYNAMIC_LAYOUT_ITEM@@AEAVCRect@@@Z`
- size: `441`
- prototype: `unsigned int __fastcall(CMFCDynamicLayout *__hidden this, struct AFX_DYNAMIC_LAYOUT_ITEM *, struct CRect *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180018500`

## callees

- `0x1800185e4`
- `0x18001895c`
- `0x180018ac0`
- `0x18001b550`

## import_xrefs

- `USER32!SetRectEmpty` at `0x180018613`
- `USER32!SetRectEmpty` at `0x180018613`

## pseudocode

```c
__int64 __fastcall CMFCDynamicLayout::AdjustItemRect(
        CMFCDynamicLayout *this,
        struct AFX_DYNAMIC_LAYOUT_ITEM *a2,
        struct tagRECT *a3)
{
  unsigned int v7; // edx
  int v8; // ebx
  int v9; // r11d
  double v10; // xmm6_8
  double v11; // xmm5_8
  double v12; // xmm4_8
  double v13; // xmm2_8
  double v14; // xmm3_8
  double v15; // xmm1_8
  LONG v16; // ecx
  int v17; // r8d
  int v18; // [rsp+20h] [rbp-38h] BYREF
  int v19; // [rsp+24h] [rbp-34h]
  int v20; // [rsp+28h] [rbp-30h]
  int v21; // [rsp+2Ch] [rbp-2Ch]

  SetRectEmpty(a3);
  CMFCDynamicLayout::GetHostWndRect(this, (struct CRect *)&v18);
  if ( (unsigned int)CRect::IsRectNull((CRect *)&v18) )
    return 3;
  v7 = 0;
  v8 = v18;
  v9 = v19;
  v10 = *((double *)a2 + 2);
  v11 = *((double *)a2 + 3);
  v12 = *((double *)a2 + 4);
  v13 = (double)(v20 - v18) * 0.01;
  v14 = (double)(v21 - v19) * 0.01;
  if ( *((int *)a2 + 10) <= 0 )
    v15 = *((double *)a2 + 1);
  else
    v15 = (double)*((int *)a2 + 10) * v13 + *((double *)a2 + 1);
  if ( *((int *)a2 + 11) > 0 )
    v10 = v10 + (double)*((int *)a2 + 11) * v14;
  if ( *((int *)a2 + 12) > 0 )
    v11 = v11 + (double)*((int *)a2 + 12) * v13;
  if ( *((int *)a2 + 13) > 0 )
    v12 = v12 + (double)*((int *)a2 + 13) * v14;
  v16 = v18 + (int)v15;
  a3->left = v16;
  a3->right = (int)v11 + v16;
  v17 = v9 + (int)v10;
  a3->top = v17;
  a3->bottom = (int)v12 + v17;
  if ( (double)(v8 + (int)v15) == (double)v8 + *((double *)a2 + 1) && (double)v17 == (double)v9 + *((double *)a2 + 2) )
    v7 = 2;
  if ( (double)(int)v11 == *((double *)a2 + 3) && (double)(int)v12 == *((double *)a2 + 4) )
    v7 |= 1u;
  return v7;
}

```

## disassembly

```asm
0x1800185e4  mov     [rsp+arg_8], rbx
0x1800185e9  mov     [rsp+arg_18], rsi
0x1800185ee  push    rdi
0x1800185ef  sub     rsp, 50h
0x1800185f3  movaps  [rsp+58h+var_18], xmm6
0x1800185f8  mov     rax, cs:__security_cookie
0x1800185ff  xor     rax, rsp
0x180018602  mov     [rsp+58h+var_28], rax
0x180018607  mov     rbx, rcx
0x18001860a  mov     rsi, r8
0x18001860d  mov     rcx, r8; lprc
0x180018610  mov     rdi, rdx
0x180018613  call    cs:__imp_SetRectEmpty
0x180018619  lea     rdx, [rsp+58h+var_38]; struct CRect *
0x18001861e  mov     rcx, rbx; this
0x180018621  call    ?GetHostWndRect@CMFCDynamicLayout@@QEBAXAEAVCRect@@@Z; CMFCDynamicLayout::GetHostWndRect(CRect &)
0x180018626  lea     rcx, [rsp+58h+var_38]; this
0x18001862b  call    ?IsRectNull@CRect@@QEBAHXZ; CRect::IsRectNull(void)
0x180018630  xor     ecx, ecx
0x180018632  test    eax, eax
0x180018634  jz      short loc_18001863E
0x180018636  lea     eax, [rcx+3]
0x180018639  jmp     loc_18001877B
0x18001863e  mov     eax, [rsp+58h+var_30]
0x180018642  mov     edx, ecx
0x180018644  mov     ebx, [rsp+58h+var_38]
0x180018648  sub     eax, ebx
0x18001864a  mov     r11d, [rsp+58h+var_34]
0x18001864f  movsd   xmm6, qword ptr [rdi+10h]
0x180018654  movsd   xmm5, qword ptr [rdi+18h]
0x180018659  movsd   xmm4, qword ptr [rdi+20h]
0x18001865e  movd    xmm2, eax
0x180018662  mov     eax, [rsp+58h+var_2C]
0x180018666  sub     eax, r11d
0x180018669  cvtdq2pd xmm2, xmm2
0x18001866d  movd    xmm3, eax
0x180018671  mulsd   xmm2, cs:__real@3f847ae147ae147b
0x180018679  cvtdq2pd xmm3, xmm3
0x18001867d  mulsd   xmm3, cs:__real@3f847ae147ae147b
0x180018685  cmp     [rdi+28h], ecx
0x180018688  jle     short loc_18001869E
0x18001868a  movd    xmm1, dword ptr [rdi+28h]
0x18001868f  cvtdq2pd xmm1, xmm1
0x180018693  mulsd   xmm1, xmm2
0x180018697  addsd   xmm1, qword ptr [rdi+8]
0x18001869c  jmp     short loc_1800186A3
0x18001869e  movsd   xmm1, qword ptr [rdi+8]
0x1800186a3  cmp     [rdi+2Ch], ecx
0x1800186a6  jle     short loc_1800186B9
0x1800186a8  movd    xmm0, dword ptr [rdi+2Ch]
0x1800186ad  cvtdq2pd xmm0, xmm0
0x1800186b1  mulsd   xmm0, xmm3
0x1800186b5  addsd   xmm6, xmm0
0x1800186b9  cmp     [rdi+30h], ecx
0x1800186bc  jle     short loc_1800186CF
0x1800186be  movd    xmm0, dword ptr [rdi+30h]
0x1800186c3  cvtdq2pd xmm0, xmm0
0x1800186c7  mulsd   xmm0, xmm2
0x1800186cb  addsd   xmm5, xmm0
0x1800186cf  cmp     [rdi+34h], ecx
0x1800186d2  jle     short loc_1800186E5
0x1800186d4  movd    xmm0, dword ptr [rdi+34h]
0x1800186d9  cvtdq2pd xmm0, xmm0
0x1800186dd  mulsd   xmm0, xmm3
0x1800186e1  addsd   xmm4, xmm0
0x1800186e5  cvttsd2si ecx, xmm1
0x1800186e9  cvttsd2si r10d, xmm5
0x1800186ee  add     ecx, ebx
0x1800186f0  mov     [rsi], ecx
0x1800186f2  movd    xmm0, ebx
0x1800186f6  cvttsd2si r8d, xmm6
0x1800186fb  lea     eax, [r10+rcx]
0x1800186ff  mov     [rsi+8], eax
0x180018702  movd    xmm1, ecx
0x180018706  add     r8d, r11d
0x180018709  cvttsd2si r9d, xmm4
0x18001870e  mov     [rsi+4], r8d
0x180018712  cvtdq2pd xmm0, xmm0
0x180018716  lea     eax, [r9+r8]
0x18001871a  mov     [rsi+0Ch], eax
0x18001871d  cvtdq2pd xmm1, xmm1
0x180018721  addsd   xmm0, qword ptr [rdi+8]
0x180018726  ucomisd xmm1, xmm0
0x18001872a  jp      short loc_180018752
0x18001872c  jnz     short loc_180018752
0x18001872e  movd    xmm0, r11d
0x180018733  cvtdq2pd xmm0, xmm0
0x180018737  movd    xmm1, r8d
0x18001873c  addsd   xmm0, qword ptr [rdi+10h]
0x180018741  cvtdq2pd xmm1, xmm1
0x180018745  ucomisd xmm1, xmm0
0x180018749  jp      short loc_180018752
0x18001874b  jnz     short loc_180018752
0x18001874d  mov     edx, 2
0x180018752  movd    xmm0, r10d
0x180018757  cvtdq2pd xmm0, xmm0
0x18001875b  ucomisd xmm0, qword ptr [rdi+18h]
0x180018760  jp      short loc_180018779
0x180018762  jnz     short loc_180018779
0x180018764  movd    xmm0, r9d
0x180018769  cvtdq2pd xmm0, xmm0
0x18001876d  ucomisd xmm0, qword ptr [rdi+20h]
0x180018772  jp      short loc_180018779
0x180018774  jnz     short loc_180018779
0x180018776  or      edx, 1
0x180018779  mov     eax, edx
0x18001877b  mov     rcx, [rsp+58h+var_28]
0x180018780  xor     rcx, rsp; StackCookie
0x180018783  call    __security_check_cookie
0x180018788  mov     rbx, [rsp+58h+arg_8]
0x18001878d  mov     rsi, [rsp+58h+arg_18]
0x180018792  movaps  xmm6, [rsp+58h+var_18]
0x180018797  add     rsp, 50h
0x18001879b  pop     rdi
0x18001879c  retn
```
