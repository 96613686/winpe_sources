# CDXGISwapChain::EmulateScalingNone(_D3DKMT_PRESENT &,_D3DKMT_DIRTYREGIONS &,tagRECT const &)

- ea: `0x1800624a8`
- end: `0x1800627af`
- name: `?EmulateScalingNone@CDXGISwapChain@@QEAAXAEAU_D3DKMT_PRESENT@@AEAU_D3DKMT_DIRTYREGIONS@@AEBUtagRECT@@@Z`
- size: `775`
- prototype: `void __fastcall(CDXGISwapChain *__hidden this, struct _D3DKMT_PRESENT *, struct _D3DKMT_DIRTYREGIONS *, const struct tagRECT *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180008d40`

## callees

- `0x180040910`
- `0x1800624a8`
- `0x180075fa0`
- `0x18009c894`

## import_xrefs

- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!SubtractRect` at `0x180062715`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!SubtractRect` at `0x180062715`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IntersectRect` at `0x1800625c7`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IntersectRect` at `0x180062766`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IntersectRect` at `0x1800625c7`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IntersectRect` at `0x180062766`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!SetRect` at `0x1800626b7`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!SetRect` at `0x1800626b7`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IsRectEmpty` at `0x1800626d1`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IsRectEmpty` at `0x1800626d1`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!OffsetRect` at `0x1800625af`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!OffsetRect` at `0x1800625fa`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!OffsetRect` at `0x18006260b`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!OffsetRect` at `0x180062739`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!OffsetRect` at `0x1800625af`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!OffsetRect` at `0x1800625fa`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!OffsetRect` at `0x18006260b`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!OffsetRect` at `0x180062739`
- `ext-ms-win-ntuser-windowclass-l1-1-0!GetWindowLongA` at `0x180062574`
- `ext-ms-win-ntuser-windowclass-l1-1-0!GetWindowLongA` at `0x180062574`

## pseudocode

```c
void __fastcall CDXGISwapChain::EmulateScalingNone(
        CDXGISwapChain *this,
        struct tagRECT *a2,
        LONG *a3,
        const struct tagRECT *a4)
{
  struct tagRECT v4; // xmm0
  bool v6; // r15
  unsigned int v9; // eax
  unsigned int v10; // ecx
  char v11; // bl
  unsigned int v12; // ecx
  char v13; // al
  LONG top; // r8d
  unsigned __int64 v15; // rax
  struct tagRECT *v16; // r12
  struct tagRECT v17; // xmm0
  int v18; // ebx
  int v19; // ebx
  float v20; // xmm0_4
  LONG right; // r9d
  LONG bottom; // r8d
  LONG left; // edx
  __int64 v24; // rcx
  unsigned int v25; // ebx
  unsigned int i; // esi
  BOOL v27; // eax
  unsigned int v28; // ecx
  int v29; // [rsp+38h] [rbp-59h]
  int v30; // [rsp+3Ch] [rbp-55h]
  struct tagRECT rcDst; // [rsp+48h] [rbp-49h] BYREF
  RECT rcSrc2; // [rsp+58h] [rbp-39h] BYREF
  struct tagRECT rc; // [rsp+68h] [rbp-29h] BYREF

  v4 = *a4;
  a2[5].right |= 0x40u;
  a2[2] = v4;
  *(_QWORD *)&a2[4].right = a3 + 1;
  v6 = 0;
  a2[4].left = *a3;
  v9 = a4->right - a4->left;
  v10 = *((_DWORD *)this + 94);
  if ( v9 <= v10 )
  {
    v11 = 0;
    v6 = v9 < v10;
  }
  else
  {
    v11 = 1;
  }
  v12 = a4->bottom - a4->top;
  if ( v12 > *((_DWORD *)this + 95) )
  {
    v11 = 1;
LABEL_10:
    if ( CDXGISwapChain::IsHwndUnderlying(this) )
    {
      LODWORD(v15) = GetWindowLongA(*((HWND *)this + 42), -20);
      top = a4->top;
    }
    else
    {
      v15 = 0;
    }
    v16 = a2 + 3;
    rc = *a4;
    v29 = *(LONG *)((char *)&a4->left + ((v15 >> 19) & 8)) - *(LONG *)((char *)&a2[3].left + ((v15 >> 19) & 8));
    v30 = *(LONG *)((char *)&a2[3].left + ((v15 >> 19) & 8)) - *(LONG *)((char *)&a4->left + ((v15 >> 19) & 8));
    OffsetRect(&rc, v30, -top);
    rcDst = 0;
    if ( !IntersectRect(&rcDst, a2 + 3, &rc) )
    {
      v17 = rcDst;
      *(_QWORD *)&a2[4].right = v16;
      v6 = 0;
      a2[4].left = 1;
      *v16 = v17;
    }
    a2[2] = *v16;
    OffsetRect(a2 + 2, v29, a4->top);
    OffsetRect(&rcDst, v29, a4->top);
    if ( v11 )
    {
      a2[22].right = -1;
      v18 = (int)(float)((float)(FLOAT_to_SRGB(*((float *)this + 420)) * 255.0) + 0.5) << 8;
      v19 = ((int)(float)((float)(FLOAT_to_SRGB(*((float *)this + 421)) * 255.0) + 0.5) | v18) << 8;
      v20 = FLOAT_to_SRGB(*((float *)this + 422));
      right = rcDst.right;
      bottom = rcDst.bottom;
      left = rcDst.left;
      a2[1].bottom = (int)(float)((float)(v20 * 255.0) + 0.5) | v19;
      SetRect((LPRECT)&a2[(unsigned int)a2[25].left + 25].top, left, bottom, right, a4->bottom);
      if ( !IsRectEmpty((const RECT *)&a2[(unsigned int)a2[25].left + 25].top) )
        ++a2[25].left;
      v24 = (unsigned int)a2[25].left;
      rcSrc2.left = rcDst.left;
      rcSrc2.top = rcDst.top;
      rcSrc2.right = rcDst.right;
      rcSrc2.bottom = a4->bottom;
      if ( SubtractRect((LPRECT)&a2[v24 + 25].top, a4, &rcSrc2) )
        ++a2[25].left;
    }
    if ( v6 )
    {
      OffsetRect(&rcDst, v30, -a4->top);
      v25 = 0;
      for ( i = 0; i < *a3; v25 = v28 )
      {
        v27 = IntersectRect((LPRECT)&a3[4 * v25 + 1], (const RECT *)&a3[4 * i + 1], &rcDst);
        v28 = v25 + 1;
        if ( !v27 )
          v28 = v25;
        ++i;
      }
      a2[4].left = v25;
    }
    return;
  }
  v13 = v6;
  if ( v12 < *((_DWORD *)this + 95) )
    v13 = 1;
  v6 = v13;
  if ( v11 || v13 )
    goto LABEL_10;
}

```

## disassembly

```asm
0x1800624a8  mov     rax, rsp
0x1800624ab  push    rbp
0x1800624ac  push    rbx
0x1800624ad  push    rsi
0x1800624ae  push    rdi
0x1800624af  push    r12
0x1800624b1  push    r13
0x1800624b3  push    r14
0x1800624b5  push    r15
0x1800624b7  lea     rbp, [rax-5Fh]
0x1800624bb  sub     rsp, 0A8h
0x1800624c2  movaps  xmmword ptr [rax-58h], xmm6
0x1800624c6  movaps  xmmword ptr [rax-68h], xmm7
0x1800624ca  mov     rax, cs:__security_cookie
0x1800624d1  xor     rax, rsp
0x1800624d4  mov     [rbp+57h+var_70], rax
0x1800624d8  movups  xmm0, xmmword ptr [r9]
0x1800624dc  or      dword ptr [rdx+58h], 40h
0x1800624e0  mov     r13, rcx
0x1800624e3  lea     rcx, [r8+4]
0x1800624e7  mov     [rbp+57h+var_A8], r8
0x1800624eb  movdqu  xmmword ptr [rdx+20h], xmm0
0x1800624f0  mov     [rdx+48h], rcx
0x1800624f4  xor     r15b, r15b
0x1800624f7  mov     eax, [r8]
0x1800624fa  mov     rsi, r9
0x1800624fd  mov     [rdx+40h], eax
0x180062500  mov     rdi, rdx
0x180062503  mov     eax, [r9+8]
0x180062507  mov     r14d, 1
0x18006250d  sub     eax, [r9]
0x180062510  mov     ecx, [r13+178h]
0x180062517  cmp     eax, ecx
0x180062519  jbe     short loc_180062520
0x18006251b  mov     bl, r14b
0x18006251e  jmp     short loc_18006252C
0x180062520  xor     bl, bl
0x180062522  movzx   r15d, r15b
0x180062526  cmp     eax, ecx
0x180062528  cmovb   r15d, r14d
0x18006252c  mov     ecx, [r9+0Ch]
0x180062530  mov     r8d, [r9+4]
0x180062534  sub     ecx, r8d
0x180062537  cmp     ecx, [r13+17Ch]
0x18006253e  jbe     short loc_180062545
0x180062540  mov     bl, r14b
0x180062543  jmp     short loc_18006255C
0x180062545  movzx   eax, r15b
0x180062549  cmovb   eax, r14d
0x18006254d  mov     r15b, al
0x180062550  test    bl, bl
0x180062552  jnz     short loc_18006255C
0x180062554  test    al, al
0x180062556  jz      loc_180062781
0x18006255c  mov     rcx, r13; this
0x18006255f  call    ?IsHwndUnderlying@CDXGISwapChain@@QEBA_NXZ; CDXGISwapChain::IsHwndUnderlying(void)
0x180062564  test    al, al
0x180062566  jz      short loc_180062580
0x180062568  mov     rcx, [r13+150h]; hWnd
0x18006256f  mov     edx, 0FFFFFFECh; nIndex
0x180062574  call    cs:__imp_GetWindowLongA
0x18006257a  mov     r8d, [rsi+4]
0x18006257e  jmp     short loc_180062582
0x180062580  xor     eax, eax
0x180062582  movups  xmm0, xmmword ptr [rsi]
0x180062585  shr     rax, 13h
0x180062589  lea     r12, [rdi+30h]
0x18006258d  and     eax, 8
0x180062590  neg     r8d; dy
0x180062593  movdqu  xmmword ptr [rbp+57h+rc.left], xmm0
0x180062598  mov     ecx, [rax+rsi]
0x18006259b  sub     ecx, [rax+r12]
0x18006259f  mov     eax, ecx
0x1800625a1  mov     [rbp+57h+var_B0], ecx
0x1800625a4  neg     eax
0x1800625a6  lea     rcx, [rbp+57h+rc]; lprc
0x1800625aa  mov     edx, eax; dx
0x1800625ac  mov     [rbp+57h+var_AC], eax
0x1800625af  call    cs:__imp_OffsetRect
0x1800625b5  xorps   xmm0, xmm0
0x1800625b8  lea     r8, [rbp+57h+rc]; lprcSrc2
0x1800625bc  mov     rdx, r12; lprcSrc1
0x1800625bf  lea     rcx, [rbp+57h+rcDst]; lprcDst
0x1800625c3  movups  xmmword ptr [rbp+57h+rcDst.left], xmm0
0x1800625c7  call    cs:__imp_IntersectRect
0x1800625cd  test    eax, eax
0x1800625cf  jnz     short loc_1800625E6
0x1800625d1  movups  xmm0, xmmword ptr [rbp+57h+rcDst.left]
0x1800625d5  mov     [rdi+48h], r12
0x1800625d9  xor     r15b, r15b
0x1800625dc  mov     [rdi+40h], r14d
0x1800625e0  movdqu  xmmword ptr [r12], xmm0
0x1800625e6  movups  xmm0, xmmword ptr [r12]
0x1800625eb  mov     edx, [rbp+57h+var_B0]; dx
0x1800625ee  lea     rcx, [rdi+20h]; lprc
0x1800625f2  movdqu  xmmword ptr [rcx], xmm0
0x1800625f6  mov     r8d, [rsi+4]; dy
0x1800625fa  call    cs:__imp_OffsetRect
0x180062600  mov     r8d, [rsi+4]; dy
0x180062604  lea     rcx, [rbp+57h+rcDst]; lprc
0x180062608  mov     edx, [rbp+57h+var_B0]; dx
0x18006260b  call    cs:__imp_OffsetRect
0x180062611  test    bl, bl
0x180062613  jz      loc_180062726
0x180062619  mov     dword ptr [rdi+168h], 0FFFFFFFFh
0x180062623  movss   xmm0, dword ptr [r13+690h]; float
0x18006262c  call    ?FLOAT_to_SRGB@@YAMM@Z; FLOAT_to_SRGB(float)
0x180062631  movss   xmm7, cs:__real@437f0000
0x180062639  movss   xmm6, cs:__real@3f000000
0x180062641  mulss   xmm0, xmm7
0x180062645  addss   xmm0, xmm6
0x180062649  cvttss2si rbx, xmm0
0x18006264e  movss   xmm0, dword ptr [r13+694h]; float
0x180062657  shl     ebx, 8
0x18006265a  call    ?FLOAT_to_SRGB@@YAMM@Z; FLOAT_to_SRGB(float)
0x18006265f  mulss   xmm0, xmm7
0x180062663  addss   xmm0, xmm6
0x180062667  cvttss2si rax, xmm0
0x18006266c  movss   xmm0, dword ptr [r13+698h]; float
0x180062675  or      ebx, eax
0x180062677  shl     ebx, 8
0x18006267a  call    ?FLOAT_to_SRGB@@YAMM@Z; FLOAT_to_SRGB(float)
0x18006267f  mov     r9d, [rbp+57h+rcDst.right]; xRight
0x180062683  mov     r8d, [rbp+57h+rcDst.bottom]; yTop
0x180062687  mov     edx, [rbp+57h+rcDst.left]; xLeft
0x18006268a  mulss   xmm0, xmm7
0x18006268e  addss   xmm0, xmm6
0x180062692  cvttss2si rax, xmm0
0x180062697  or      ebx, eax
0x180062699  mov     [rdi+1Ch], ebx
0x18006269c  mov     ecx, [rdi+190h]
0x1800626a2  mov     eax, [rsi+0Ch]
0x1800626a5  shl     rcx, 4
0x1800626a9  add     rcx, 194h
0x1800626b0  mov     [rsp+0E0h+yBottom], eax; yBottom
0x1800626b4  add     rcx, rdi; lprc
0x1800626b7  call    cs:__imp_SetRect
0x1800626bd  mov     ecx, [rdi+190h]
0x1800626c3  shl     rcx, 4
0x1800626c7  add     rcx, 194h
0x1800626ce  add     rcx, rdi; lprc
0x1800626d1  call    cs:__imp_IsRectEmpty
0x1800626d7  test    eax, eax
0x1800626d9  jnz     short loc_1800626E2
0x1800626db  add     [rdi+190h], r14d
0x1800626e2  mov     eax, [rbp+57h+rcDst.left]
0x1800626e5  lea     r8, [rbp+57h+rcSrc2]; lprcSrc2
0x1800626e9  mov     ecx, [rdi+190h]
0x1800626ef  mov     rdx, rsi; lprcSrc1
0x1800626f2  mov     [rbp+57h+rcSrc2.left], eax
0x1800626f5  mov     eax, [rbp+57h+rcDst.top]
0x1800626f8  shl     rcx, 4
0x1800626fc  mov     [rbp+57h+rcSrc2.top], eax
0x1800626ff  add     rcx, 194h
0x180062706  mov     eax, [rbp+57h+rcDst.right]
0x180062709  add     rcx, rdi; lprcDst
0x18006270c  mov     [rbp+57h+rcSrc2.right], eax
0x18006270f  mov     eax, [rsi+0Ch]
0x180062712  mov     [rbp+57h+rcSrc2.bottom], eax
0x180062715  call    cs:__imp_SubtractRect
0x18006271b  test    eax, eax
0x18006271d  jz      short loc_180062726
0x18006271f  add     [rdi+190h], r14d
0x180062726  test    r15b, r15b
0x180062729  jz      short loc_180062781
0x18006272b  mov     r8d, [rsi+4]
0x18006272f  lea     rcx, [rbp+57h+rcDst]; lprc
0x180062733  mov     edx, [rbp+57h+var_AC]; dx
0x180062736  neg     r8d; dy
0x180062739  call    cs:__imp_OffsetRect
0x18006273f  mov     r15, [rbp+57h+var_A8]
0x180062743  xor     ebx, ebx
0x180062745  xor     esi, esi
0x180062747  cmp     [r15], ebx
0x18006274a  jbe     short loc_18006277E
0x18006274c  lea     r12, [r15+4]
0x180062750  mov     edx, esi
0x180062752  lea     r8, [rbp+57h+rcDst]; lprcSrc2
0x180062756  shl     rdx, 4
0x18006275a  mov     ecx, ebx
0x18006275c  add     rdx, r12; lprcSrc1
0x18006275f  shl     rcx, 4
0x180062763  add     rcx, r12; lprcDst
0x180062766  call    cs:__imp_IntersectRect
0x18006276c  test    eax, eax
0x18006276e  lea     ecx, [rbx+1]
0x180062771  cmovz   ecx, ebx
0x180062774  add     esi, r14d
0x180062777  mov     ebx, ecx
0x180062779  cmp     esi, [r15]
0x18006277c  jb      short loc_180062750
0x18006277e  mov     [rdi+40h], ebx
0x180062781  mov     rcx, [rbp+57h+var_70]
0x180062785  xor     rcx, rsp; StackCookie
0x180062788  call    __security_check_cookie
0x18006278d  lea     r11, [rsp+0E0h+var_38]
0x180062795  movaps  xmm6, xmmword ptr [r11-18h]
0x18006279a  movaps  xmm7, xmmword ptr [r11-28h]
0x18006279f  mov     rsp, r11
0x1800627a2  pop     r15
0x1800627a4  pop     r14
0x1800627a6  pop     r13
0x1800627a8  pop     r12
0x1800627aa  pop     rdi
0x1800627ab  pop     rsi
0x1800627ac  pop     rbx
0x1800627ad  pop     rbp
0x1800627ae  retn
```
