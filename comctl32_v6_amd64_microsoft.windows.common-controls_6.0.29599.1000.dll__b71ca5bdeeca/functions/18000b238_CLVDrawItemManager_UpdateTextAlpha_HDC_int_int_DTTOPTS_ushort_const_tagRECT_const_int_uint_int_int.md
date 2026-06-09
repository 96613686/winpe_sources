# CLVDrawItemManager::_UpdateTextAlpha(HDC__ *,int,int,_DTTOPTS *,ushort const *,tagRECT const *,int,uint,int,int)

- ea: `0x18000b238`
- end: `0x18000b5bb`
- name: `?_UpdateTextAlpha@CLVDrawItemManager@@IEAAXPEAUHDC__@@HHPEAU_DTTOPTS@@PEBGPEBUtagRECT@@HIHH@Z`
- size: `899`
- prototype: `void(CLVDrawItemManager *__hidden this, HDC, int, int, struct _DTTOPTS *, const unsigned __int16 *, const struct tagRECT *, int, unsigned int, int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800abadc`

## callees

- `0x18000b238`
- `0x18000b5c4`
- `0x180114520`

## import_xrefs

- `GDI32!DeleteObject` at `0x18000b49d`
- `GDI32!DeleteObject` at `0x18000b49d`
- `GDI32!CreateDPIScaledDIBSection` at `0x18000b384`
- `GDI32!CreateDPIScaledDIBSection` at `0x18000b384`
- `GDI32!SelectObject` at `0x18000b39c`
- `GDI32!SelectObject` at `0x18000b3ba`
- `GDI32!SelectObject` at `0x18000b487`
- `GDI32!SelectObject` at `0x18000b494`
- `GDI32!SelectObject` at `0x18000b39c`
- `GDI32!SelectObject` at `0x18000b3ba`
- `GDI32!SelectObject` at `0x18000b487`
- `GDI32!SelectObject` at `0x18000b494`
- `GDI32!DeleteDC` at `0x18000b4a6`
- `GDI32!DeleteDC` at `0x18000b4a6`
- `GDI32!CreateCompatibleDC` at `0x18000b316`
- `GDI32!CreateCompatibleDC` at `0x18000b316`
- `GDI32!BitBlt` at `0x18000b30d`
- `GDI32!BitBlt` at `0x18000b30d`
- `GDI32!GetStockObject` at `0x18000b3ca`
- `GDI32!GetStockObject` at `0x18000b3ca`
- `GDI32!GetDCDpiScaleValue` at `0x18000b45e`
- `GDI32!GetDCDpiScaleValue` at `0x18000b45e`
- `GDI32!GetCurrentObject` at `0x18000b3ae`
- `GDI32!GetCurrentObject` at `0x18000b3ae`
- `USER32!FillRect` at `0x18000b3da`
- `USER32!FillRect` at `0x18000b3da`
- `UxTheme!EndBufferedPaint` at `0x18000b4b4`
- `UxTheme!EndBufferedPaint` at `0x18000b4b4`
- `UxTheme!BeginBufferedPaint` at `0x18000b2ca`
- `UxTheme!BeginBufferedPaint` at `0x18000b2ca`
- `UxTheme!BufferedPaintInit` at `0x18000b58d`
- `UxTheme!BufferedPaintInit` at `0x18000b58d`
- `UxTheme!__imp_GetBufferedPaintBitsEx` at `0x18000b475`
- `UxTheme!__imp_GetBufferedPaintBitsEx` at `0x18000b475`

## pseudocode

```c
void __fastcall CLVDrawItemManager::_UpdateTextAlpha(
        CLVDrawItemManager *this,
        HDC a2,
        unsigned int a3,
        __int64 a4,
        struct _DTTOPTS *a5,
        const unsigned __int16 *a6,
        const struct tagRECT *prcTarget,
        int a8,
        unsigned int a9,
        int a10)
{
  __int64 v13; // rcx
  HPAINTBUFFER v14; // r15
  HDC CompatibleDC; // rax
  HDC v16; // rdi
  LONG v17; // ecx
  void *v18; // rax
  void *v19; // rbx
  HGDIOBJ CurrentObject; // rax
  HBRUSH StockObject; // rax
  unsigned int v22; // r9d
  int DCDpiScaleValue; // esi
  unsigned int v24; // r9d
  int v25; // ecx
  int v26; // edx
  int v27; // r10d
  __int64 v28; // r14
  __int64 v29; // rax
  int v30; // r8d
  __int64 v31; // rsi
  __int64 v32; // r9
  _DWORD *v33; // r11
  int i; // eax
  __int64 y1; // [rsp+38h] [rbp-C8h]
  HGDIOBJ h; // [rsp+78h] [rbp-88h]
  HGDIOBJ v37; // [rsp+80h] [rbp-80h]
  HDC hdc; // [rsp+88h] [rbp-78h] BYREF
  __int64 v39; // [rsp+90h] [rbp-70h] BYREF
  __int64 v40; // [rsp+98h] [rbp-68h] BYREF
  int v41; // [rsp+A0h] [rbp-60h] BYREF
  int v42; // [rsp+A4h] [rbp-5Ch] BYREF
  RECT rc; // [rsp+A8h] [rbp-58h] BYREF
  _DWORD v44[3]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v45; // [rsp+C4h] [rbp-3Ch]
  __int128 v46; // [rsp+CCh] [rbp-34h]
  __int64 v47; // [rsp+DCh] [rbp-24h]
  BP_PAINTPARAMS pPaintParams; // [rsp+E8h] [rbp-18h] BYREF

  v13 = *(_QWORD *)(*(_QWORD *)this + 368LL);
  if ( !*(_DWORD *)(v13 + 32) )
  {
    *(_DWORD *)(v13 + 32) = 1;
    BufferedPaintInit();
  }
  pPaintParams.cbSize = 24;
  pPaintParams.dwFlags = 32769;
  hdc = 0;
  *(_OWORD *)&pPaintParams.prcExclude = 0;
  v14 = BeginBufferedPaint(a2, prcTarget, BPBF_TOPDOWNDIB, &pPaintParams, &hdc);
  if ( v14 )
  {
    BitBlt(
      hdc,
      prcTarget->left,
      prcTarget->top,
      prcTarget->right - prcTarget->left,
      prcTarget->bottom - prcTarget->top,
      a2,
      prcTarget->left,
      prcTarget->top,
      0xCC0020u);
    CompatibleDC = CreateCompatibleDC(a2);
    v16 = CompatibleDC;
    if ( CompatibleDC )
    {
      v17 = prcTarget->bottom - prcTarget->top;
      rc.right = prcTarget->right - prcTarget->left;
      rc.bottom = v17;
      v44[1] = rc.right;
      v44[2] = v17;
      v39 = 0;
      *(_QWORD *)&rc.left = 0;
      v46 = 0;
      v47 = 0;
      v44[0] = 40;
      v45 = 2097153;
      v18 = (void *)CreateDPIScaledDIBSection(CompatibleDC, v44, 0, &v39, 0, 0, 0);
      v19 = v18;
      if ( v18 )
      {
        v37 = SelectObject(v16, v18);
        CurrentObject = GetCurrentObject(a2, 6u);
        h = SelectObject(v16, CurrentObject);
        StockObject = (HBRUSH)GetStockObject(4);
        FillRect(v16, &rc, StockObject);
        v22 = a9 & 0xFFFBFFFF;
        if ( (a9 & 0x40000) == 0 )
          v22 = a9;
        LODWORD(y1) = a8;
        SHThemeDrawText(0, v16, a3, 0, a5, a6, &rc, y1, v22, a10);
        v40 = 0;
        v42 = 0;
        v41 = 1;
        DCDpiScaleValue = GetDCDpiScaleValue(v16);
        if ( (int)GetBufferedPaintBitsEx(v14, &v40, &v42, &v41) >= 0 && DCDpiScaleValue == v41 )
        {
          v24 = 0;
          v25 = rc.right - rc.left;
          v26 = rc.bottom - rc.top;
          v27 = v42;
          if ( (*(_DWORD *)(*(_QWORD *)this + 128LL) & 0x400000) != 0 )
            v24 = v42 - v25;
          v28 = v39;
          if ( v41 > 1 )
          {
            v26 *= v41;
            v29 = v24 * v41;
            v27 = v41 * v42;
            v25 *= v41;
          }
          else
          {
            v29 = v24;
          }
          v30 = 0;
          if ( v26 > 0 )
          {
            v31 = v40 + 4 * v29;
            do
            {
              v32 = v31 + 4LL * v27 * v30;
              v33 = (_DWORD *)(v28 + 4LL * v25 * (v26 - v30 - 1));
              for ( i = 0; i < v25; ++i )
              {
                if ( *v33 )
                {
                  if ( !*(_BYTE *)(v32 + 3) )
                    *(_BYTE *)(v32 + 3) = -1;
                }
                v32 += 4;
                ++v33;
              }
              ++v30;
            }
            while ( v30 < v26 );
          }
        }
        SelectObject(v16, h);
        SelectObject(v16, v37);
        DeleteObject(v19);
      }
      DeleteDC(v16);
    }
    EndBufferedPaint(v14, 1);
  }
}

```

## disassembly

```asm
0x18000b238  mov     [rsp-8+arg_18], rbx
0x18000b23d  push    rbp
0x18000b23e  push    rsi
0x18000b23f  push    rdi
0x18000b240  push    r12
0x18000b242  push    r13
0x18000b244  push    r14
0x18000b246  push    r15
0x18000b248  lea     rbp, [rsp-10h]
0x18000b24d  sub     rsp, 110h
0x18000b254  mov     rax, cs:__security_cookie
0x18000b25b  xor     rax, rsp
0x18000b25e  mov     [rbp+40h+var_40], rax
0x18000b262  mov     rax, [rbp+40h+arg_28]
0x18000b266  mov     r14, rcx
0x18000b269  mov     rbx, [rbp+40h+prcTarget]
0x18000b270  mov     r12d, r8d
0x18000b273  mov     r13, [rbp+40h+arg_20]
0x18000b277  mov     rsi, rdx
0x18000b27a  mov     [rsp+140h+var_D0], rax
0x18000b27f  mov     rax, [rcx]
0x18000b282  mov     rcx, [rax+170h]
0x18000b289  cmp     dword ptr [rcx+20h], 0
0x18000b28d  jz      loc_18000B586
0x18000b293  xorps   xmm0, xmm0
0x18000b296  mov     [rbp+40h+pPaintParams.cbSize], 18h
0x18000b29d  lea     rax, [rbp+40h+hdc]
0x18000b2a1  mov     [rbp+40h+pPaintParams.dwFlags], 8001h
0x18000b2a8  lea     r9, [rbp+40h+pPaintParams]; pPaintParams
0x18000b2ac  mov     [rsp+140h+phdc], rax; phdc
0x18000b2b1  mov     r8d, 2; dwFormat
0x18000b2b7  mov     [rbp+40h+hdc], 0
0x18000b2bf  mov     rdx, rbx; prcTarget
0x18000b2c2  mov     rcx, rsi; hdcTarget
0x18000b2c5  movdqu  xmmword ptr [rbp+40h+pPaintParams.prcExclude], xmm0
0x18000b2ca  call    cs:__imp_BeginBufferedPaint
0x18000b2d0  mov     r15, rax
0x18000b2d3  test    rax, rax
0x18000b2d6  jz      loc_18000B4BA
0x18000b2dc  mov     r8d, [rbx+4]; y
0x18000b2e0  mov     ecx, [rbx+0Ch]
0x18000b2e3  mov     edx, [rbx]; x
0x18000b2e5  sub     ecx, r8d
0x18000b2e8  mov     r9d, [rbx+8]
0x18000b2ec  mov     [rsp+140h+rop], 0CC0020h; rop
0x18000b2f4  sub     r9d, edx; cx
0x18000b2f7  mov     dword ptr [rsp+140h+y1], r8d; y1
0x18000b2fc  mov     [rsp+140h+x1], edx; x1
0x18000b300  mov     [rsp+140h+hdcSrc], rsi; hdcSrc
0x18000b305  mov     dword ptr [rsp+140h+phdc], ecx; cy
0x18000b309  mov     rcx, [rbp+40h+hdc]; hdc
0x18000b30d  call    cs:__imp_BitBlt
0x18000b313  mov     rcx, rsi; hdc
0x18000b316  call    cs:__imp_CreateCompatibleDC
0x18000b31c  xor     r8d, r8d
0x18000b31f  mov     rdi, rax
0x18000b322  test    rax, rax
0x18000b325  jz      loc_18000B4AC
0x18000b32b  mov     edx, [rbx+8]
0x18000b32e  lea     r9, [rbp+40h+var_B0]
0x18000b332  sub     edx, [rbx]
0x18000b334  xorps   xmm0, xmm0
0x18000b337  mov     ecx, [rbx+0Ch]
0x18000b33a  xor     eax, eax
0x18000b33c  sub     ecx, [rbx+4]
0x18000b33f  movups  [rbp+40h+var_84], xmm0
0x18000b343  mov     [rsp+140h+x1], r8d
0x18000b348  mov     [rbp+40h+rc.right], edx
0x18000b34b  mov     [rbp+40h+rc.bottom], ecx
0x18000b34e  mov     dword ptr [rbp+40h+var_84], edx
0x18000b351  lea     rdx, [rbp+40h+var_88]
0x18000b355  mov     dword ptr [rbp+40h+var_84+4], ecx
0x18000b358  mov     rcx, rdi
0x18000b35b  mov     dword ptr [rsp+140h+hdcSrc], r8d
0x18000b360  mov     [rbp+40h+var_B0], r8
0x18000b364  mov     qword ptr [rbp+40h+rc.left], r8
0x18000b368  movups  [rbp+40h+var_74], xmm0
0x18000b36c  mov     [rbp+40h+var_64], rax
0x18000b370  mov     [rbp+40h+var_88], 28h ; '('
0x18000b377  mov     qword ptr [rbp+40h+var_84+8], 200001h
0x18000b37f  mov     [rsp+140h+phdc], r8
0x18000b384  call    cs:__imp_CreateDPIScaledDIBSection
0x18000b38a  mov     rbx, rax
0x18000b38d  test    rax, rax
0x18000b390  jz      loc_18000B4A3
0x18000b396  mov     rdx, rax; h
0x18000b399  mov     rcx, rdi; hdc
0x18000b39c  call    cs:__imp_SelectObject
0x18000b3a2  mov     edx, 6; type
0x18000b3a7  mov     rcx, rsi; hdc
0x18000b3aa  mov     [rbp+40h+var_C0], rax
0x18000b3ae  call    cs:__imp_GetCurrentObject
0x18000b3b4  mov     rdx, rax; h
0x18000b3b7  mov     rcx, rdi; hdc
0x18000b3ba  call    cs:__imp_SelectObject
0x18000b3c0  mov     ecx, 4; i
0x18000b3c5  mov     [rsp+140h+h], rax
0x18000b3ca  call    cs:__imp_GetStockObject
0x18000b3d0  lea     rdx, [rbp+40h+rc]; lprc
0x18000b3d4  mov     rcx, rdi; hDC
0x18000b3d7  mov     r8, rax; hbr
0x18000b3da  call    cs:__imp_FillRect
0x18000b3e0  mov     edx, [rbp+40h+arg_40]
0x18000b3e6  mov     r8d, r12d
0x18000b3e9  mov     eax, [rbp+40h+arg_48]
0x18000b3ef  mov     r9d, edx
0x18000b3f2  mov     [rsp+140h+var_E0], 0
0x18000b3fa  btr     r9d, 12h
0x18000b3ff  mov     [rsp+140h+var_E8], 0FFFFFFh
0x18000b407  bt      edx, 12h
0x18000b40b  mov     [rsp+140h+var_F8], eax
0x18000b40f  mov     eax, [rbp+40h+arg_38]
0x18000b415  cmovnb  r9d, edx
0x18000b419  mov     [rsp+140h+rop], r9d
0x18000b41e  mov     rdx, rdi
0x18000b421  mov     dword ptr [rsp+140h+y1], eax
0x18000b425  xor     r9d, r9d
0x18000b428  lea     rax, [rbp+40h+rc]
0x18000b42c  xor     ecx, ecx
0x18000b42e  mov     qword ptr [rsp+140h+x1], rax
0x18000b433  mov     rax, [rsp+140h+var_D0]
0x18000b438  mov     [rsp+140h+hdcSrc], rax
0x18000b43d  mov     [rsp+140h+phdc], r13
0x18000b442  call    SHThemeDrawText
0x18000b447  xor     r12d, r12d
0x18000b44a  mov     rcx, rdi
0x18000b44d  mov     [rbp+40h+var_A8], r12
0x18000b451  mov     [rbp+40h+var_9C], r12d
0x18000b455  lea     r13d, [r12+1]
0x18000b45a  mov     [rbp+40h+var_A0], r13d
0x18000b45e  call    cs:__imp_GetDCDpiScaleValue
0x18000b464  lea     r9, [rbp+40h+var_A0]
0x18000b468  mov     rcx, r15
0x18000b46b  lea     r8, [rbp+40h+var_9C]
0x18000b46f  mov     esi, eax
0x18000b471  lea     rdx, [rbp+40h+var_A8]
0x18000b475  call    cs:__imp_GetBufferedPaintBitsEx
0x18000b47b  test    eax, eax
0x18000b47d  jns     short loc_18000B4E1
0x18000b47f  mov     rdx, [rsp+140h+h]; h
0x18000b484  mov     rcx, rdi; hdc
0x18000b487  call    cs:__imp_SelectObject
0x18000b48d  mov     rdx, [rbp+40h+var_C0]; h
0x18000b491  mov     rcx, rdi; hdc
0x18000b494  call    cs:__imp_SelectObject
0x18000b49a  mov     rcx, rbx; ho
0x18000b49d  call    cs:__imp_DeleteObject
0x18000b4a3  mov     rcx, rdi; hdc
0x18000b4a6  call    cs:__imp_DeleteDC
0x18000b4ac  mov     edx, 1; fUpdateTarget
0x18000b4b1  mov     rcx, r15; hBufferedPaint
0x18000b4b4  call    cs:__imp_EndBufferedPaint
0x18000b4ba  mov     rcx, [rbp+40h+var_40]
0x18000b4be  xor     rcx, rsp; StackCookie
0x18000b4c1  call    __security_check_cookie
0x18000b4c6  mov     rbx, [rsp+140h+arg_18]
0x18000b4ce  add     rsp, 110h
0x18000b4d5  pop     r15
0x18000b4d7  pop     r14
0x18000b4d9  pop     r13
0x18000b4db  pop     r12
0x18000b4dd  pop     rdi
0x18000b4de  pop     rsi
0x18000b4df  pop     rbp
0x18000b4e0  retn
0x18000b4e1  mov     r8d, [rbp+40h+var_A0]
0x18000b4e5  cmp     esi, r8d
0x18000b4e8  jnz     short loc_18000B47F
0x18000b4ea  mov     rax, [r14]
0x18000b4ed  mov     r9d, r12d
0x18000b4f0  mov     ecx, [rbp+40h+rc.right]
0x18000b4f3  mov     edx, [rbp+40h+rc.bottom]
0x18000b4f6  sub     ecx, [rbp+40h+rc.left]
0x18000b4f9  sub     edx, [rbp+40h+rc.top]
0x18000b4fc  test    dword ptr [rax+80h], 400000h
0x18000b506  mov     r10d, [rbp+40h+var_9C]
0x18000b50a  jnz     loc_18000B598
0x18000b510  mov     r14, [rbp+40h+var_B0]
0x18000b514  mov     r11, [rbp+40h+var_A8]
0x18000b518  cmp     r8d, r13d
0x18000b51b  jg      loc_18000B5A3
0x18000b521  mov     eax, r9d
0x18000b524  mov     r8d, r12d
0x18000b527  test    edx, edx
0x18000b529  jle     loc_18000B47F
0x18000b52f  lea     rsi, [r11+rax*4]
0x18000b533  mov     eax, r8d
0x18000b536  imul    eax, r10d
0x18000b53a  cdqe
0x18000b53c  lea     r9, [rsi+rax*4]
0x18000b540  mov     eax, edx
0x18000b542  sub     eax, r8d
0x18000b545  sub     eax, r13d
0x18000b548  imul    eax, ecx
0x18000b54b  cdqe
0x18000b54d  lea     r11, [r14+rax*4]
0x18000b551  mov     eax, r12d
0x18000b554  test    ecx, ecx
0x18000b556  jle     short loc_18000B56C
0x18000b558  cmp     [r11], r12d
0x18000b55b  jnz     short loc_18000B579
0x18000b55d  add     r9, 4
0x18000b561  add     r11, 4
0x18000b565  add     eax, r13d
0x18000b568  cmp     eax, ecx
0x18000b56a  jl      short loc_18000B558
0x18000b56c  add     r8d, r13d
0x18000b56f  cmp     r8d, edx
0x18000b572  jl      short loc_18000B533
0x18000b574  jmp     loc_18000B47F
0x18000b579  cmp     [r9+3], r12b
0x18000b57d  jnz     short loc_18000B55D
0x18000b57f  mov     byte ptr [r9+3], 0FFh
0x18000b584  jmp     short loc_18000B55D
0x18000b586  mov     dword ptr [rcx+20h], 1
0x18000b58d  call    cs:__imp_BufferedPaintInit
0x18000b593  jmp     loc_18000B293
0x18000b598  mov     r9d, r10d
0x18000b59b  sub     r9d, ecx
0x18000b59e  jmp     loc_18000B510
0x18000b5a3  mov     eax, r8d
0x18000b5a6  imul    edx, r8d
0x18000b5aa  imul    eax, r9d
0x18000b5ae  imul    r10d, r8d
0x18000b5b2  imul    ecx, r8d
0x18000b5b6  jmp     loc_18000B524
```
