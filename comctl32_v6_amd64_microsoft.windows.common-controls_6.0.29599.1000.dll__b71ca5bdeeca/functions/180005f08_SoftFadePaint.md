# _SoftFadePaint

- ea: `0x180005f08`
- end: `0x18000630f`
- name: `_SoftFadePaint`
- size: `1031`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180005e7c`
- `0x1800076f0`

## callees

- `0x180005f08`
- `0x180006cf4`
- `0x180007124`
- `0x180114520`

## import_xrefs

- `GDI32!SelectClipRgn` at `0x18000603c`
- `GDI32!SelectClipRgn` at `0x180006304`
- `GDI32!SelectClipRgn` at `0x18000603c`
- `GDI32!SelectClipRgn` at `0x180006304`
- `GDI32!BitBlt` at `0x180006218`
- `GDI32!BitBlt` at `0x18000625a`
- `GDI32!BitBlt` at `0x18000629c`
- `GDI32!BitBlt` at `0x1800062de`
- `GDI32!BitBlt` at `0x180006218`
- `GDI32!BitBlt` at `0x18000625a`
- `GDI32!BitBlt` at `0x18000629c`
- `GDI32!BitBlt` at `0x1800062de`
- `GDI32!GdiAlphaBlend` at `0x180005fc5`
- `GDI32!GdiAlphaBlend` at `0x180006103`
- `GDI32!GdiAlphaBlend` at `0x180006153`
- `GDI32!GdiAlphaBlend` at `0x1800061a3`
- `GDI32!GdiAlphaBlend` at `0x180005fc5`
- `GDI32!GdiAlphaBlend` at `0x180006103`
- `GDI32!GdiAlphaBlend` at `0x180006153`
- `GDI32!GdiAlphaBlend` at `0x1800061a3`
- `GDI32!GetClipRgn` at `0x180006023`
- `GDI32!GetClipRgn` at `0x180006023`
- `USER32!IsRectEmpty` at `0x180005f6a`
- `USER32!IsRectEmpty` at `0x1800060bd`
- `USER32!IsRectEmpty` at `0x18000610d`
- `USER32!IsRectEmpty` at `0x18000615d`
- `USER32!IsRectEmpty` at `0x1800061ad`
- `USER32!IsRectEmpty` at `0x1800061da`
- `USER32!IsRectEmpty` at `0x180006222`
- `USER32!IsRectEmpty` at `0x180006264`
- `USER32!IsRectEmpty` at `0x1800062a6`
- `USER32!IsRectEmpty` at `0x180005f6a`
- `USER32!IsRectEmpty` at `0x1800060bd`
- `USER32!IsRectEmpty` at `0x18000610d`
- `USER32!IsRectEmpty` at `0x18000615d`
- `USER32!IsRectEmpty` at `0x1800061ad`
- `USER32!IsRectEmpty` at `0x1800061da`
- `USER32!IsRectEmpty` at `0x180006222`
- `USER32!IsRectEmpty` at `0x180006264`
- `USER32!IsRectEmpty` at `0x1800062a6`

## pseudocode

```c
int __fastcall SoftFadePaint(__int64 a1, BLENDFUNCTION *a2)
{
  HDC v2; // rdi
  int ClipRgn; // r15d
  int v6; // r14d
  BOOL v7; // eax
  LONG *v8; // r10
  LONG yoriginSrc; // r8d
  LONG v10; // ecx
  LONG xoriginSrc; // edx
  LONG right; // r9d
  int result; // eax
  HRGN v14; // rdx
  LONG v15; // edx
  LONG v16; // r9d
  LONG v17; // r8d
  LONG bottom; // ecx
  LONG v19; // eax
  LONG v20; // eax
  HDC v21; // rsi
  HDC hdcSrc; // r14
  HRGN v23; // rdx
  RECT rc; // [rsp+60h] [rbp-19h] BYREF
  RECT v25; // [rsp+70h] [rbp-9h] BYREF
  RECT v26; // [rsp+80h] [rbp+7h] BYREF
  RECT v27; // [rsp+90h] [rbp+17h] BYREF

  v2 = *(HDC *)(a1 + 32);
  ClipRgn = -1;
  if ( *(_QWORD *)(a1 + 120) )
  {
    v14 = *(HRGN *)(a1 + 128);
    if ( v14 )
    {
      ClipRgn = GetClipRgn(v2, v14);
      if ( ClipRgn != -1 )
        SelectClipRgn(v2, *(HRGN *)(a1 + 120));
    }
  }
  v6 = 0;
  rc = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v7 = IsRectEmpty((const RECT *)(a1 + 104));
  v8 = (LONG *)(a1 + 96);
  if ( !v7 )
  {
    v15 = *(_DWORD *)(a1 + 88);
    v6 = 1;
    v16 = *v8;
    v17 = *(_DWORD *)(a1 + 108);
    bottom = *(_DWORD *)(a1 + 116);
    if ( *(_DWORD *)(a1 + 92) > v17 )
      v17 = *(_DWORD *)(a1 + 92);
    rc.top = *(_DWORD *)(a1 + 92);
    v25.bottom = *(_DWORD *)(a1 + 100);
    if ( v25.bottom < bottom )
      bottom = v25.bottom;
    rc.left = v15;
    v19 = *(_DWORD *)(a1 + 104);
    rc.right = v16;
    if ( v15 > v19 )
      v19 = v15;
    rc.bottom = v17;
    v26.right = v19;
    v20 = *(_DWORD *)(a1 + 112);
    v25.left = v15;
    if ( v16 < v20 )
      v20 = v16;
    v25.right = v16;
    v27.left = v20;
    v25.top = bottom;
    v26.left = v15;
    v26.top = v17;
    v26.bottom = bottom;
    v27.right = v16;
    v27.top = v17;
    v27.bottom = bottom;
  }
  if ( a2 )
  {
    if ( !v6 )
    {
      yoriginSrc = *(_DWORD *)(a1 + 92);
      v10 = *(_DWORD *)(a1 + 100);
      xoriginSrc = *(_DWORD *)(a1 + 88);
      right = *v8;
LABEL_6:
      result = GdiAlphaBlend(
                 v2,
                 xoriginSrc,
                 yoriginSrc,
                 right - xoriginSrc,
                 v10 - yoriginSrc,
                 *(HDC *)(a1 + 8),
                 xoriginSrc,
                 yoriginSrc,
                 right - xoriginSrc,
                 v10 - yoriginSrc,
                 *a2);
      goto LABEL_7;
    }
    if ( !IsRectEmpty(&rc) )
      GdiAlphaBlend(
        v2,
        rc.left,
        rc.top,
        rc.right - rc.left,
        rc.bottom - rc.top,
        *(HDC *)(a1 + 8),
        rc.left,
        rc.top,
        rc.right - rc.left,
        rc.bottom - rc.top,
        *a2);
    if ( !IsRectEmpty(&v25) )
      GdiAlphaBlend(
        v2,
        v25.left,
        v25.top,
        v25.right - v25.left,
        v25.bottom - v25.top,
        *(HDC *)(a1 + 8),
        v25.left,
        v25.top,
        v25.right - v25.left,
        v25.bottom - v25.top,
        *a2);
    if ( !IsRectEmpty(&v26) )
      GdiAlphaBlend(
        v2,
        v26.left,
        v26.top,
        v26.right - v26.left,
        v26.bottom - v26.top,
        *(HDC *)(a1 + 8),
        v26.left,
        v26.top,
        v26.right - v26.left,
        v26.bottom - v26.top,
        *a2);
    result = IsRectEmpty(&v27);
    if ( !result )
    {
      v10 = v27.bottom;
      yoriginSrc = v27.top;
      right = v27.right;
      xoriginSrc = v27.left;
      goto LABEL_6;
    }
  }
  else if ( v6 )
  {
    v21 = *(HDC *)(a1 + 32);
    hdcSrc = *(HDC *)(a1 + 8);
    if ( !IsRectEmpty(&rc) )
      BitBlt(v21, rc.left, rc.top, rc.right - rc.left, rc.bottom - rc.top, hdcSrc, rc.left, rc.top, 0xCC0020u);
    if ( !IsRectEmpty(&v25) )
      BitBlt(v21, v25.left, v25.top, v25.right - v25.left, v25.bottom - v25.top, hdcSrc, v25.left, v25.top, 0xCC0020u);
    if ( !IsRectEmpty(&v26) )
      BitBlt(v21, v26.left, v26.top, v26.right - v26.left, v26.bottom - v26.top, hdcSrc, v26.left, v26.top, 0xCC0020u);
    if ( !IsRectEmpty(&v27) )
      BitBlt(v21, v27.left, v27.top, v27.right - v27.left, v27.bottom - v27.top, hdcSrc, v27.left, v27.top, 0xCC0020u);
    result = CCEndDoubleBufferNoPaint(a1);
  }
  else
  {
    result = CCEndDoubleBuffer(a1);
  }
LABEL_7:
  if ( ClipRgn != -1 )
  {
    if ( ClipRgn )
      v23 = *(HRGN *)(a1 + 128);
    else
      v23 = 0;
    return SelectClipRgn(v2, v23);
  }
  return result;
}

```

## disassembly

```asm
0x180005f08  mov     [rsp-8+arg_10], rbx
0x180005f0d  mov     [rsp-8+arg_18], rsi
0x180005f12  push    rbp
0x180005f13  push    rdi
0x180005f14  push    r12
0x180005f16  push    r14
0x180005f18  push    r15
0x180005f1a  lea     rbp, [rsp-37h]
0x180005f1f  sub     rsp, 0B0h
0x180005f26  mov     rax, cs:__security_cookie
0x180005f2d  xor     rax, rsp
0x180005f30  mov     [rbp+57h+var_30], rax
0x180005f34  mov     rdi, [rcx+20h]
0x180005f38  or      r15d, 0FFFFFFFFh
0x180005f3c  cmp     qword ptr [rcx+78h], 0
0x180005f41  mov     rsi, rdx
0x180005f44  mov     rbx, rcx
0x180005f47  jnz     loc_180006010
0x180005f4d  xorps   xmm0, xmm0
0x180005f50  lea     rcx, [rbx+68h]; lprc
0x180005f54  xorps   xmm1, xmm1
0x180005f57  xor     r14d, r14d
0x180005f5a  movups  xmmword ptr [rbp+57h+rc.left], xmm0
0x180005f5e  movups  xmmword ptr [rbp+57h+var_60.left], xmm1
0x180005f62  movups  xmmword ptr [rbp+57h+var_50.left], xmm0
0x180005f66  movups  xmmword ptr [rbp+57h+var_40.left], xmm1
0x180005f6a  call    cs:__imp_IsRectEmpty
0x180005f70  lea     r10, [rbx+60h]
0x180005f74  test    eax, eax
0x180005f76  jz      loc_180006047
0x180005f7c  test    rsi, rsi
0x180005f7f  jz      short loc_180005FFD
0x180005f81  test    r14d, r14d
0x180005f84  jnz     loc_1800060B9
0x180005f8a  mov     r8d, [rbx+5Ch]; yoriginDest
0x180005f8e  mov     ecx, [rbx+64h]
0x180005f91  mov     edx, [rbx+58h]; xoriginDest
0x180005f94  mov     r9d, [r10]
0x180005f97  mov     eax, [rsi]
0x180005f99  sub     ecx, r8d
0x180005f9c  mov     dword ptr [rsp+0D0h+ftn.BlendOp], eax; ftn
0x180005fa0  sub     r9d, edx; wDest
0x180005fa3  mov     rax, [rbx+8]
0x180005fa7  mov     [rsp+0D0h+hSrc], ecx; hSrc
0x180005fab  mov     [rsp+0D0h+wSrc], r9d; wSrc
0x180005fb0  mov     [rsp+0D0h+yoriginSrc], r8d; yoriginSrc
0x180005fb5  mov     [rsp+0D0h+xoriginSrc], edx; xoriginSrc
0x180005fb9  mov     [rsp+0D0h+hdcSrc], rax; hdcSrc
0x180005fbe  mov     [rsp+0D0h+hDest], ecx; hDest
0x180005fc2  mov     rcx, rdi; hdcDest
0x180005fc5  call    cs:__imp_GdiAlphaBlend
0x180005fcb  cmp     r15d, 0FFFFFFFFh
0x180005fcf  jnz     loc_1800062F1
0x180005fd5  mov     rcx, [rbp+57h+var_30]
0x180005fd9  xor     rcx, rsp; StackCookie
0x180005fdc  call    __security_check_cookie
0x180005fe1  lea     r11, [rsp+0D0h+var_20]
0x180005fe9  mov     rbx, [r11+40h]
0x180005fed  mov     rsi, [r11+48h]
0x180005ff1  mov     rsp, r11
0x180005ff4  pop     r15
0x180005ff6  pop     r14
0x180005ff8  pop     r12
0x180005ffa  pop     rdi
0x180005ffb  pop     rbp
0x180005ffc  retn
0x180005ffd  test    r14d, r14d
0x180006000  jnz     loc_1800061CE
0x180006006  mov     rcx, rbx
0x180006009  call    CCEndDoubleBuffer
0x18000600e  jmp     short loc_180005FCB
0x180006010  mov     rdx, [rcx+80h]; hrgn
0x180006017  test    rdx, rdx
0x18000601a  jz      loc_180005F4D
0x180006020  mov     rcx, rdi; hdc
0x180006023  call    cs:__imp_GetClipRgn
0x180006029  mov     r15d, eax
0x18000602c  cmp     eax, 0FFFFFFFFh
0x18000602f  jz      loc_180005F4D
0x180006035  mov     rdx, [rbx+78h]; hrgn
0x180006039  mov     rcx, rdi; hdc
0x18000603c  call    cs:__imp_SelectClipRgn
0x180006042  jmp     loc_180005F4D
0x180006047  mov     edx, [rbx+58h]
0x18000604a  mov     r14d, 1
0x180006050  mov     r9d, [r10]
0x180006053  mov     eax, [rbx+5Ch]
0x180006056  mov     r8d, [rbx+6Ch]
0x18000605a  cmp     eax, r8d
0x18000605d  mov     ecx, [rbx+74h]
0x180006060  cmovg   r8d, eax
0x180006064  mov     [rbp+57h+rc.top], eax
0x180006067  mov     eax, [rbx+64h]
0x18000606a  cmp     eax, ecx
0x18000606c  mov     [rbp+57h+var_60.bottom], eax
0x18000606f  cmovl   ecx, eax
0x180006072  mov     [rbp+57h+rc.left], edx
0x180006075  mov     eax, [rbx+68h]
0x180006078  cmp     edx, eax
0x18000607a  mov     [rbp+57h+rc.right], r9d
0x18000607e  cmovg   eax, edx
0x180006081  mov     [rbp+57h+rc.bottom], r8d
0x180006085  mov     [rbp+57h+var_50.right], eax
0x180006088  mov     eax, [rbx+70h]
0x18000608b  cmp     r9d, eax
0x18000608e  mov     [rbp+57h+var_60.left], edx
0x180006091  cmovl   eax, r9d
0x180006095  mov     [rbp+57h+var_60.right], r9d
0x180006099  mov     [rbp+57h+var_40.left], eax
0x18000609c  mov     [rbp+57h+var_60.top], ecx
0x18000609f  mov     [rbp+57h+var_50.left], edx
0x1800060a2  mov     [rbp+57h+var_50.top], r8d
0x1800060a6  mov     [rbp+57h+var_50.bottom], ecx
0x1800060a9  mov     [rbp+57h+var_40.right], r9d
0x1800060ad  mov     [rbp+57h+var_40.top], r8d
0x1800060b1  mov     [rbp+57h+var_40.bottom], ecx
0x1800060b4  jmp     loc_180005F7C
0x1800060b9  lea     rcx, [rbp+57h+rc]; lprc
0x1800060bd  call    cs:__imp_IsRectEmpty
0x1800060c3  test    eax, eax
0x1800060c5  jnz     short loc_180006109
0x1800060c7  mov     ecx, [rbp+57h+rc.bottom]
0x1800060ca  mov     r8d, [rbp+57h+rc.top]; yoriginDest
0x1800060ce  sub     ecx, r8d
0x1800060d1  mov     edx, [rbp+57h+rc.left]; xoriginDest
0x1800060d4  mov     eax, [rsi]
0x1800060d6  mov     r9d, [rbp+57h+rc.right]
0x1800060da  mov     dword ptr [rsp+0D0h+ftn.BlendOp], eax; ftn
0x1800060de  sub     r9d, edx; wDest
0x1800060e1  mov     rax, [rbx+8]
0x1800060e5  mov     [rsp+0D0h+hSrc], ecx; hSrc
0x1800060e9  mov     [rsp+0D0h+wSrc], r9d; wSrc
0x1800060ee  mov     [rsp+0D0h+yoriginSrc], r8d; yoriginSrc
0x1800060f3  mov     [rsp+0D0h+xoriginSrc], edx; xoriginSrc
0x1800060f7  mov     [rsp+0D0h+hdcSrc], rax; hdcSrc
0x1800060fc  mov     [rsp+0D0h+hDest], ecx; hDest
0x180006100  mov     rcx, rdi; hdcDest
0x180006103  call    cs:__imp_GdiAlphaBlend
0x180006109  lea     rcx, [rbp+57h+var_60]; lprc
0x18000610d  call    cs:__imp_IsRectEmpty
0x180006113  test    eax, eax
0x180006115  jnz     short loc_180006159
0x180006117  mov     ecx, [rbp+57h+var_60.bottom]
0x18000611a  mov     r8d, [rbp+57h+var_60.top]; yoriginDest
0x18000611e  sub     ecx, r8d
0x180006121  mov     edx, [rbp+57h+var_60.left]; xoriginDest
0x180006124  mov     eax, [rsi]
0x180006126  mov     r9d, [rbp+57h+var_60.right]
0x18000612a  mov     dword ptr [rsp+0D0h+ftn.BlendOp], eax; ftn
0x18000612e  sub     r9d, edx; wDest
0x180006131  mov     rax, [rbx+8]
0x180006135  mov     [rsp+0D0h+hSrc], ecx; hSrc
0x180006139  mov     [rsp+0D0h+wSrc], r9d; wSrc
0x18000613e  mov     [rsp+0D0h+yoriginSrc], r8d; yoriginSrc
0x180006143  mov     [rsp+0D0h+xoriginSrc], edx; xoriginSrc
0x180006147  mov     [rsp+0D0h+hdcSrc], rax; hdcSrc
0x18000614c  mov     [rsp+0D0h+hDest], ecx; hDest
0x180006150  mov     rcx, rdi; hdcDest
0x180006153  call    cs:__imp_GdiAlphaBlend
0x180006159  lea     rcx, [rbp+57h+var_50]; lprc
0x18000615d  call    cs:__imp_IsRectEmpty
0x180006163  test    eax, eax
0x180006165  jnz     short loc_1800061A9
0x180006167  mov     ecx, [rbp+57h+var_50.bottom]
0x18000616a  mov     r8d, [rbp+57h+var_50.top]; yoriginDest
0x18000616e  sub     ecx, r8d
0x180006171  mov     edx, [rbp+57h+var_50.left]; xoriginDest
0x180006174  mov     eax, [rsi]
0x180006176  mov     r9d, [rbp+57h+var_50.right]
0x18000617a  mov     dword ptr [rsp+0D0h+ftn.BlendOp], eax; ftn
0x18000617e  sub     r9d, edx; wDest
0x180006181  mov     rax, [rbx+8]
0x180006185  mov     [rsp+0D0h+hSrc], ecx; hSrc
0x180006189  mov     [rsp+0D0h+wSrc], r9d; wSrc
0x18000618e  mov     [rsp+0D0h+yoriginSrc], r8d; yoriginSrc
0x180006193  mov     [rsp+0D0h+xoriginSrc], edx; xoriginSrc
0x180006197  mov     [rsp+0D0h+hdcSrc], rax; hdcSrc
0x18000619c  mov     [rsp+0D0h+hDest], ecx; hDest
0x1800061a0  mov     rcx, rdi; hdcDest
0x1800061a3  call    cs:__imp_GdiAlphaBlend
0x1800061a9  lea     rcx, [rbp+57h+var_40]; lprc
0x1800061ad  call    cs:__imp_IsRectEmpty
0x1800061b3  test    eax, eax
0x1800061b5  jnz     loc_180005FCB
0x1800061bb  mov     ecx, [rbp+57h+var_40.bottom]
0x1800061be  mov     r8d, [rbp+57h+var_40.top]
0x1800061c2  mov     r9d, [rbp+57h+var_40.right]
0x1800061c6  mov     edx, [rbp+57h+var_40.left]
0x1800061c9  jmp     loc_180005F97
0x1800061ce  mov     rsi, [rbx+20h]
0x1800061d2  lea     rcx, [rbp+57h+rc]; lprc
0x1800061d6  mov     r14, [rbx+8]
0x1800061da  call    cs:__imp_IsRectEmpty
0x1800061e0  mov     r12d, 0CC0020h
0x1800061e6  test    eax, eax
0x1800061e8  jnz     short loc_18000621E
0x1800061ea  mov     r8d, [rbp+57h+rc.top]; y
0x1800061ee  mov     rcx, rsi; hdc
0x1800061f1  mov     edx, [rbp+57h+rc.left]; x
0x1800061f4  mov     eax, [rbp+57h+rc.bottom]
0x1800061f7  mov     r9d, [rbp+57h+rc.right]
0x1800061fb  sub     eax, r8d
0x1800061fe  mov     [rsp+0D0h+wSrc], r12d; rop
0x180006203  sub     r9d, edx; cx
0x180006206  mov     [rsp+0D0h+yoriginSrc], r8d; y1
0x18000620b  mov     [rsp+0D0h+xoriginSrc], edx; x1
0x18000620f  mov     [rsp+0D0h+hdcSrc], r14; hdcSrc
0x180006214  mov     [rsp+0D0h+hDest], eax; cy
0x180006218  call    cs:__imp_BitBlt
0x18000621e  lea     rcx, [rbp+57h+var_60]; lprc
0x180006222  call    cs:__imp_IsRectEmpty
0x180006228  test    eax, eax
0x18000622a  jnz     short loc_180006260
0x18000622c  mov     r8d, [rbp+57h+var_60.top]; y
0x180006230  mov     rcx, rsi; hdc
0x180006233  mov     edx, [rbp+57h+var_60.left]; x
0x180006236  mov     eax, [rbp+57h+var_60.bottom]
0x180006239  mov     r9d, [rbp+57h+var_60.right]
0x18000623d  sub     eax, r8d
0x180006240  mov     [rsp+0D0h+wSrc], r12d; rop
0x180006245  sub     r9d, edx; cx
0x180006248  mov     [rsp+0D0h+yoriginSrc], r8d; y1
0x18000624d  mov     [rsp+0D0h+xoriginSrc], edx; x1
0x180006251  mov     [rsp+0D0h+hdcSrc], r14; hdcSrc
0x180006256  mov     [rsp+0D0h+hDest], eax; cy
0x18000625a  call    cs:__imp_BitBlt
0x180006260  lea     rcx, [rbp+57h+var_50]; lprc
0x180006264  call    cs:__imp_IsRectEmpty
0x18000626a  test    eax, eax
0x18000626c  jnz     short loc_1800062A2
0x18000626e  mov     r8d, [rbp+57h+var_50.top]; y
0x180006272  mov     rcx, rsi; hdc
0x180006275  mov     edx, [rbp+57h+var_50.left]; x
0x180006278  mov     eax, [rbp+57h+var_50.bottom]
0x18000627b  mov     r9d, [rbp+57h+var_50.right]
0x18000627f  sub     eax, r8d
0x180006282  mov     [rsp+0D0h+wSrc], r12d; rop
0x180006287  sub     r9d, edx; cx
0x18000628a  mov     [rsp+0D0h+yoriginSrc], r8d; y1
0x18000628f  mov     [rsp+0D0h+xoriginSrc], edx; x1
0x180006293  mov     [rsp+0D0h+hdcSrc], r14; hdcSrc
0x180006298  mov     [rsp+0D0h+hDest], eax; cy
0x18000629c  call    cs:__imp_BitBlt
0x1800062a2  lea     rcx, [rbp+57h+var_40]; lprc
0x1800062a6  call    cs:__imp_IsRectEmpty
0x1800062ac  test    eax, eax
0x1800062ae  jnz     short loc_1800062E4
0x1800062b0  mov     r8d, [rbp+57h+var_40.top]; y
0x1800062b4  mov     rcx, rsi; hdc
0x1800062b7  mov     edx, [rbp+57h+var_40.left]; x
0x1800062ba  mov     eax, [rbp+57h+var_40.bottom]
0x1800062bd  mov     r9d, [rbp+57h+var_40.right]
0x1800062c1  sub     eax, r8d
0x1800062c4  mov     [rsp+0D0h+wSrc], r12d; rop
0x1800062c9  sub     r9d, edx; cx
0x1800062cc  mov     [rsp+0D0h+yoriginSrc], r8d; y1
0x1800062d1  mov     [rsp+0D0h+xoriginSrc], edx; x1
0x1800062d5  mov     [rsp+0D0h+hdcSrc], r14; hdcSrc
0x1800062da  mov     [rsp+0D0h+hDest], eax; cy
0x1800062de  call    cs:__imp_BitBlt
0x1800062e4  mov     rcx, rbx
0x1800062e7  call    CCEndDoubleBufferNoPaint
0x1800062ec  jmp     loc_180005FCB
0x1800062f1  test    r15d, r15d
0x1800062f4  jz      short loc_1800062FF
0x1800062f6  mov     rdx, [rbx+80h]
0x1800062fd  jmp     short loc_180006301
0x1800062ff  xor     edx, edx; hrgn
0x180006301  mov     rcx, rdi; hdc
0x180006304  call    cs:__imp_SelectClipRgn
0x18000630a  jmp     loc_180005FD5
```
