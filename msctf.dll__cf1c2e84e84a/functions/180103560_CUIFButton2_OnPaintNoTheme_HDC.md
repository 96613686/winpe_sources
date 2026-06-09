# CUIFButton2::OnPaintNoTheme(HDC__ *)

- ea: `0x180103560`
- end: `0x180103a0a`
- name: `?OnPaintNoTheme@CUIFButton2@@MEAAXPEAUHDC__@@@Z`
- size: `1194`
- prototype: `void __fastcall(CUIFButton2 *__hidden this, HDC)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180092984`
- `0x180094964`
- `0x180103560`
- `0x180106a60`
- `0x18010a010`

## import_xrefs

- `USER32!OffsetRect` at `0x1801037ac`
- `USER32!OffsetRect` at `0x1801037ac`
- `USER32!SetRect` at `0x18010364c`
- `USER32!SetRect` at `0x18010364c`
- `GDI32!DeleteObject` at `0x1801039d4`
- `GDI32!DeleteObject` at `0x1801039d4`
- `GDI32!CreateCompatibleDC` at `0x1801035e5`
- `GDI32!CreateCompatibleDC` at `0x1801035e5`
- `GDI32!DeleteDC` at `0x1801039dd`
- `GDI32!DeleteDC` at `0x1801039dd`
- `GDI32!SelectObject` at `0x18010362d`
- `GDI32!SelectObject` at `0x180103659`
- `GDI32!SelectObject` at `0x1801039bd`
- `GDI32!SelectObject` at `0x1801039ca`
- `GDI32!SelectObject` at `0x18010362d`
- `GDI32!SelectObject` at `0x180103659`
- `GDI32!SelectObject` at `0x1801039bd`
- `GDI32!SelectObject` at `0x1801039ca`
- `GDI32!BitBlt` at `0x1801039b0`
- `GDI32!BitBlt` at `0x1801039b0`
- `GDI32!CreateCompatibleBitmap` at `0x180103614`
- `GDI32!CreateCompatibleBitmap` at `0x180103614`

## pseudocode

```c
void __fastcall CUIFButton2::OnPaintNoTheme(CUIFButton2 *this, HDC a2)
{
  __int64 v2; // rbx
  unsigned __int64 v3; // rdi
  unsigned int DrawFlag; // r13d
  _DWORD *v6; // rcx
  int v7; // r15d
  int v8; // r12d
  HDC v9; // r9
  HDC hdcSrc; // r14
  int v11; // edx
  int v12; // r15d
  HBITMAP CompatibleBitmap; // rax
  int v14; // r12d
  HGDIOBJ v15; // rax
  int v16; // edx
  int v17; // r9d
  int v18; // eax
  unsigned __int64 v19; // rcx
  int v20; // r8d
  LONG v21; // eax
  int v22; // eax
  LONG v23; // eax
  LONG v24; // eax
  __int64 v25; // rcx
  LONG bottom; // eax
  int yBottom[2]; // [rsp+20h] [rbp-99h]
  int cy; // [rsp+50h] [rbp-69h]
  int cya; // [rsp+50h] [rbp-69h]
  int xRight; // [rsp+58h] [rbp-61h]
  int xRighta; // [rsp+58h] [rbp-61h]
  void *xRightb; // [rsp+58h] [rbp-61h]
  int v33; // [rsp+64h] [rbp-55h]
  int dy[2]; // [rsp+68h] [rbp-51h] BYREF
  unsigned __int64 v35; // [rsp+70h] [rbp-49h]
  HDC hdc; // [rsp+78h] [rbp-41h]
  HGDIOBJ h; // [rsp+80h] [rbp-39h]
  HGDIOBJ ho; // [rsp+88h] [rbp-31h]
  struct tagRECT v39; // [rsp+90h] [rbp-29h] BYREF
  struct tagRECT rc; // [rsp+A0h] [rbp-19h] BYREF
  __int128 v41; // [rsp+B0h] [rbp-9h] BYREF
  __int128 v42; // [rsp+C0h] [rbp+7h] BYREF

  v2 = 0;
  hdc = a2;
  v33 = 0;
  v3 = 0;
  *(_QWORD *)dy = 0;
  v35 = 0;
  rc = 0;
  v42 = 0;
  v41 = 0;
  v39 = 0;
  if ( *((_QWORD *)this + 6) )
  {
    DrawFlag = CUIFButton2::MakeDrawFlag(this);
    v7 = v6[22];
    xRight = v6[24];
    v8 = v6[23];
    cy = v6[25];
    hdcSrc = CreateCompatibleDC(v9);
    if ( hdcSrc )
    {
      v11 = xRight - v7;
      v12 = cy - v8;
      xRighta = v11;
      cya = cy - v8;
      CompatibleBitmap = CreateCompatibleBitmap(hdc, v11, cya);
      ho = CompatibleBitmap;
      if ( !CompatibleBitmap )
      {
LABEL_49:
        DeleteDC(hdcSrc);
        return;
      }
      v14 = xRighta;
      h = SelectObject(hdcSrc, CompatibleBitmap);
      SetRect(&rc, 0, 0, xRighta, v12);
      v15 = SelectObject(hdcSrc, *((HGDIOBJ *)this + 14));
      v16 = 0;
      xRightb = v15;
      if ( *((_QWORD *)this + 19) )
      {
        v3 = *(_QWORD *)((char *)this + 212);
        v35 = v3;
      }
      if ( *((_QWORD *)this + 20) )
      {
        v2 = *(_QWORD *)((char *)this + 204);
      }
      else
      {
        if ( !*((_QWORD *)this + 23) )
          goto LABEL_11;
        v2 = *(_QWORD *)((char *)this + 220);
      }
      v33 = HIDWORD(v2);
LABEL_11:
      v17 = *((_DWORD *)this + 21);
      if ( (v17 & 0x400) != 0 )
      {
        if ( HIDWORD(v3) && HIDWORD(v2) )
          v16 = 2;
        v20 = v2;
        LODWORD(v19) = v16 + HIDWORD(v2) + HIDWORD(v3);
        if ( (int)v3 > (int)v2 )
          v20 = v3;
      }
      else
      {
        if ( !(_DWORD)v3 || (v18 = 2, !(_DWORD)v2) )
          v18 = 0;
        v19 = HIDWORD(v3);
        v20 = v3 + v18 + v2;
        if ( SHIDWORD(v3) <= SHIDWORD(v2) )
          LODWORD(v19) = HIDWORD(v2);
      }
      if ( (v17 & 3) != 0 )
      {
        if ( (*((_DWORD *)this + 21) & 3) == 1 )
        {
          v21 = (rc.left + rc.right - v20) / 2;
          goto LABEL_29;
        }
        if ( (*((_DWORD *)this + 21) & 3) == 2 )
        {
          v21 = rc.right - v3 - 2;
          goto LABEL_29;
        }
      }
      v21 = rc.left + 2;
LABEL_29:
      v39.left = v21;
      v39.right = v20 + v21;
      v22 = v17 & 0xC;
      if ( (v17 & 0xC) != 0 )
      {
        if ( v22 == 4 )
        {
          v23 = (rc.top + rc.bottom - (int)v19) / 2;
          goto LABEL_35;
        }
        if ( v22 == 8 )
        {
          v23 = rc.bottom - v19 - 2;
LABEL_35:
          v39.top = v23;
          v24 = v19 + v23;
          v25 = *((_QWORD *)this + 6);
          v39.bottom = v24;
          (*(void (__fastcall **)(__int64, _QWORD, _QWORD, int *))(*(_QWORD *)v25 + 88LL))(
            v25,
            (v17 & 0x200) != 0 ? 165 : 84,
            DrawFlag,
            dy);
          OffsetRect(&v39, dy[0], dy[1]);
          if ( (*((_DWORD *)this + 21) & 0x400) != 0 )
          {
            DWORD1(v41) = v39.top;
            LODWORD(v41) = (v39.left + v39.right - (int)v2) / 2;
            HIDWORD(v41) = v33 + v39.top;
            DWORD2(v41) = v41 + v2;
            LODWORD(v42) = (v39.left + v39.right - (int)v3) / 2;
            DWORD1(v42) = v39.bottom - HIDWORD(v35);
            DWORD2(v42) = v3 + v42;
            bottom = v39.bottom;
          }
          else
          {
            LODWORD(v41) = v39.left;
            DWORD2(v41) = v2 + v39.left;
            DWORD1(v41) = (v39.top + v39.bottom - v33) / 2;
            HIDWORD(v41) = DWORD1(v41) + v33;
            LODWORD(v42) = v39.right - v3;
            DWORD1(v42) = (v39.top + v39.bottom - HIDWORD(v35)) / 2;
            bottom = HIDWORD(v35) + DWORD1(v42);
            DWORD2(v42) = v39.right;
          }
          HIDWORD(v42) = bottom;
          if ( (unsigned int)CUIFObject::IsRTL(this) )
            *(_DWORD *)(*((_QWORD *)this + 6) + 8LL) = 1;
          (*(void (__fastcall **)(_QWORD, HDC, struct tagRECT *, _QWORD, unsigned int))(**((_QWORD **)this + 6) + 96LL))(
            *((_QWORD *)this + 6),
            hdcSrc,
            &rc,
            (*((_DWORD *)this + 21) & 0x200) != 0 ? 165 : 84,
            DrawFlag);
          if ( *((_QWORD *)this + 19) )
            (*(void (__fastcall **)(_QWORD, HDC, __int128 *))(**((_QWORD **)this + 6) + 112LL))(
              *((_QWORD *)this + 6),
              hdcSrc,
              &v42);
          if ( *((_QWORD *)this + 20) )
          {
            (*(void (__fastcall **)(_QWORD, HDC, __int128 *))(**((_QWORD **)this + 6) + 120LL))(
              *((_QWORD *)this + 6),
              hdcSrc,
              &v41);
          }
          else if ( *((_QWORD *)this + 23) )
          {
            *(_QWORD *)yBottom = *((_QWORD *)this + 24);
            (*(void (__fastcall **)(_QWORD, HDC, __int128 *))(**((_QWORD **)this + 6) + 128LL))(
              *((_QWORD *)this + 6),
              hdcSrc,
              &v41);
          }
          if ( (unsigned int)CUIFObject::IsRTL(this) )
            *(_DWORD *)(*((_QWORD *)this + 6) + 8LL) = 0;
          yBottom[0] = DrawFlag;
          (*(void (__fastcall **)(_QWORD, HDC, struct tagRECT *, _QWORD, int *))(**((_QWORD **)this + 6) + 104LL))(
            *((_QWORD *)this + 6),
            hdcSrc,
            &rc,
            (*((_DWORD *)this + 21) & 0x200) != 0 ? 165 : 84,
            *(int **)yBottom);
          BitBlt(hdc, *((_DWORD *)this + 22), *((_DWORD *)this + 23), v14, cya, hdcSrc, 0, 0, 0xCC0020u);
          SelectObject(hdcSrc, xRightb);
          SelectObject(hdcSrc, h);
          DeleteObject(ho);
          goto LABEL_49;
        }
      }
      v23 = rc.top + 2;
      goto LABEL_35;
    }
  }
}

```

## disassembly

```asm
0x180103560  mov     [rsp-8+arg_10], rbx
0x180103565  push    rbp
0x180103566  push    rsi
0x180103567  push    rdi
0x180103568  push    r12
0x18010356a  push    r13
0x18010356c  push    r14
0x18010356e  push    r15
0x180103570  lea     rbp, [rsp-27h]
0x180103575  sub     rsp, 0E0h
0x18010357c  mov     rax, cs:__security_cookie
0x180103583  xor     rax, rsp
0x180103586  mov     [rbp+57h+var_40], rax
0x18010358a  xor     ebx, ebx
0x18010358c  mov     [rbp+57h+hdc], rdx
0x180103590  xorps   xmm0, xmm0
0x180103593  mov     [rbp+57h+var_B0], rbx
0x180103597  xor     edi, edi
0x180103599  mov     qword ptr [rbp+57h+dy], rbx
0x18010359d  xorps   xmm1, xmm1
0x1801035a0  mov     r9, rdx
0x1801035a3  mov     rsi, rcx
0x1801035a6  mov     [rbp+57h+var_A0], rdi
0x1801035aa  movups  xmmword ptr [rbp+57h+rc.left], xmm0
0x1801035ae  movups  [rbp+57h+var_50], xmm0
0x1801035b2  movups  [rbp+57h+var_60], xmm1
0x1801035b6  movups  xmmword ptr [rbp+57h+var_80.left], xmm0
0x1801035ba  cmp     [rcx+30h], rbx
0x1801035be  jz      loc_1801039E3
0x1801035c4  call    ?MakeDrawFlag@CUIFButton2@@AEAAKXZ; CUIFButton2::MakeDrawFlag(void)
0x1801035c9  mov     r12d, [rcx+60h]
0x1801035cd  mov     r13d, eax
0x1801035d0  mov     eax, [rcx+64h]
0x1801035d3  mov     r15d, [rcx+58h]
0x1801035d7  mov     [rbp+57h+xRight], r12d
0x1801035db  mov     r12d, [rcx+5Ch]
0x1801035df  mov     rcx, r9; hdc
0x1801035e2  mov     [rbp+57h+cy], eax
0x1801035e5  call    cs:__imp_CreateCompatibleDC
0x1801035eb  mov     r14, rax
0x1801035ee  test    rax, rax
0x1801035f1  jz      loc_1801039E3
0x1801035f7  mov     eax, [rbp+57h+xRight]
0x1801035fa  mov     rcx, [rbp+57h+hdc]; hdc
0x1801035fe  sub     eax, r15d
0x180103601  mov     r15d, [rbp+57h+cy]
0x180103605  mov     edx, eax; cx
0x180103607  sub     r15d, r12d
0x18010360a  mov     [rbp+57h+xRight], eax
0x18010360d  mov     r8d, r15d; cy
0x180103610  mov     [rbp+57h+cy], r15d
0x180103614  call    cs:__imp_CreateCompatibleBitmap
0x18010361a  mov     [rbp+57h+ho], rax
0x18010361e  test    rax, rax
0x180103621  jz      loc_1801039DA
0x180103627  mov     rdx, rax; h
0x18010362a  mov     rcx, r14; hdc
0x18010362d  call    cs:__imp_SelectObject
0x180103633  mov     r12d, [rbp+57h+xRight]
0x180103637  lea     rcx, [rbp+57h+rc]; lprc
0x18010363b  mov     r9d, r12d; xRight
0x18010363e  mov     [rbp+57h+h], rax
0x180103642  xor     r8d, r8d; yTop
0x180103645  mov     [rsp+110h+yBottom], r15d; yBottom
0x18010364a  xor     edx, edx; xLeft
0x18010364c  call    cs:__imp_SetRect
0x180103652  mov     rdx, [rsi+70h]; h
0x180103656  mov     rcx, r14; hdc
0x180103659  call    cs:__imp_SelectObject
0x18010365f  xor     edx, edx
0x180103661  mov     qword ptr [rbp+57h+xRight], rax
0x180103665  cmp     [rsi+98h], rdx
0x18010366c  jz      short loc_180103679
0x18010366e  mov     rdi, [rsi+0D4h]
0x180103675  mov     [rbp+57h+var_A0], rdi
0x180103679  cmp     [rsi+0A0h], rdx
0x180103680  jz      short loc_18010368B
0x180103682  mov     rbx, [rsi+0CCh]
0x180103689  jmp     short loc_18010369B
0x18010368b  cmp     [rsi+0B8h], rdx
0x180103692  jz      short loc_18010369F
0x180103694  mov     rbx, [rsi+0DCh]
0x18010369b  mov     [rbp+57h+var_B0], rbx
0x18010369f  mov     r9d, [rsi+54h]
0x1801036a3  mov     r15d, 2
0x1801036a9  bt      r9d, 0Ah
0x1801036ae  jb      short loc_1801036D9
0x1801036b0  test    edi, edi
0x1801036b2  jz      short loc_1801036BB
0x1801036b4  mov     eax, r15d
0x1801036b7  test    ebx, ebx
0x1801036b9  jnz     short loc_1801036BD
0x1801036bb  mov     eax, edx
0x1801036bd  lea     r8d, [rax+rbx]
0x1801036c1  mov     rcx, rdi
0x1801036c4  shr     rcx, 20h
0x1801036c8  mov     rax, rbx
0x1801036cb  shr     rax, 20h
0x1801036cf  add     r8d, edi
0x1801036d2  cmp     ecx, eax
0x1801036d4  cmovle  ecx, eax
0x1801036d7  jmp     short loc_180103706
0x1801036d9  mov     rcx, rdi
0x1801036dc  shr     rcx, 20h
0x1801036e0  test    ecx, ecx
0x1801036e2  jz      short loc_1801036F2
0x1801036e4  mov     rax, rbx
0x1801036e7  shr     rax, 20h
0x1801036eb  test    eax, eax
0x1801036ed  jz      short loc_1801036F2
0x1801036ef  mov     edx, r15d
0x1801036f2  mov     rax, rbx
0x1801036f5  mov     r8d, ebx
0x1801036f8  shr     rax, 20h
0x1801036fc  add     eax, edx
0x1801036fe  add     ecx, eax
0x180103700  cmp     edi, ebx
0x180103702  cmovg   r8d, edi
0x180103706  mov     eax, r9d
0x180103709  and     eax, 3
0x18010370c  jz      short loc_180103731
0x18010370e  sub     eax, 1
0x180103711  jz      short loc_180103722
0x180103713  cmp     eax, 1
0x180103716  jnz     short loc_180103731
0x180103718  mov     eax, [rbp+57h+rc.right]
0x18010371b  sub     eax, edi
0x18010371d  add     eax, 0FFFFFFFEh
0x180103720  jmp     short loc_180103737
0x180103722  mov     eax, [rbp+57h+rc.right]
0x180103725  sub     eax, r8d
0x180103728  add     eax, [rbp+57h+rc.left]
0x18010372b  cdq
0x18010372c  idiv    r15d
0x18010372f  jmp     short loc_180103737
0x180103731  mov     eax, [rbp+57h+rc.left]
0x180103734  add     eax, 2
0x180103737  mov     [rbp+57h+var_80.left], eax
0x18010373a  add     eax, r8d
0x18010373d  mov     [rbp+57h+var_80.right], eax
0x180103740  mov     eax, r9d
0x180103743  and     eax, 0Ch
0x180103746  jz      short loc_18010376A
0x180103748  cmp     eax, 4
0x18010374b  jz      short loc_18010375C
0x18010374d  cmp     eax, 8
0x180103750  jnz     short loc_18010376A
0x180103752  mov     eax, [rbp+57h+rc.bottom]
0x180103755  sub     eax, ecx
0x180103757  add     eax, 0FFFFFFFEh
0x18010375a  jmp     short loc_180103770
0x18010375c  mov     eax, [rbp+57h+rc.bottom]
0x18010375f  sub     eax, ecx
0x180103761  add     eax, [rbp+57h+rc.top]
0x180103764  cdq
0x180103765  idiv    r15d
0x180103768  jmp     short loc_180103770
0x18010376a  mov     eax, [rbp+57h+rc.top]
0x18010376d  add     eax, 2
0x180103770  mov     [rbp+57h+var_80.top], eax
0x180103773  and     r9d, 200h
0x18010377a  add     eax, ecx
0x18010377c  mov     r8d, r13d
0x18010377f  mov     rcx, [rsi+30h]
0x180103783  neg     r9d
0x180103786  mov     [rbp+57h+var_80.bottom], eax
0x180103789  lea     r9, [rbp+57h+dy]
0x18010378d  sbb     edx, edx
0x18010378f  and     edx, 51h
0x180103792  mov     rax, [rcx]
0x180103795  add     edx, 54h ; 'T'
0x180103798  mov     rax, [rax+58h]
0x18010379c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801037a1  mov     r8d, [rbp+57h+dy+4]; dy
0x1801037a5  lea     rcx, [rbp+57h+var_80]; lprc
0x1801037a9  mov     edx, [rbp+57h+dy]; dx
0x1801037ac  call    cs:__imp_OffsetRect
0x1801037b2  test    dword ptr [rsi+54h], 400h
0x1801037b9  jnz     short loc_180103809
0x1801037bb  mov     r9d, [rbp+57h+var_80.bottom]
0x1801037bf  mov     eax, r9d
0x1801037c2  mov     r8d, dword ptr [rbp+57h+var_B0+4]
0x1801037c6  sub     eax, r8d
0x1801037c9  add     eax, [rbp+57h+var_80.top]
0x1801037cc  mov     ecx, [rbp+57h+var_80.left]
0x1801037cf  cdq
0x1801037d0  sub     r9d, dword ptr [rbp+57h+var_A0+4]
0x1801037d4  add     r9d, [rbp+57h+var_80.top]
0x1801037d8  idiv    r15d
0x1801037db  mov     dword ptr [rbp+57h+var_60], ecx
0x1801037de  add     ecx, ebx
0x1801037e0  mov     dword ptr [rbp+57h+var_60+8], ecx
0x1801037e3  mov     dword ptr [rbp+57h+var_60+4], eax
0x1801037e6  lea     ecx, [rax+r8]
0x1801037ea  mov     eax, r9d
0x1801037ed  cdq
0x1801037ee  mov     dword ptr [rbp+57h+var_60+0Ch], ecx
0x1801037f1  mov     ecx, [rbp+57h+var_80.right]
0x1801037f4  idiv    r15d
0x1801037f7  sub     ecx, edi
0x1801037f9  mov     dword ptr [rbp+57h+var_50], ecx
0x1801037fc  add     ecx, edi
0x1801037fe  mov     dword ptr [rbp+57h+var_50+4], eax
0x180103801  add     eax, dword ptr [rbp+57h+var_A0+4]
0x180103804  mov     dword ptr [rbp+57h+var_50+8], ecx
0x180103807  jmp     short loc_180103852
0x180103809  mov     r8d, [rbp+57h+var_80.right]
0x18010380d  mov     eax, r8d
0x180103810  sub     eax, ebx
0x180103812  sub     r8d, edi
0x180103815  add     eax, [rbp+57h+var_80.left]
0x180103818  add     r8d, [rbp+57h+var_80.left]
0x18010381c  cdq
0x18010381d  idiv    r15d
0x180103820  mov     edx, [rbp+57h+var_80.top]
0x180103823  mov     dword ptr [rbp+57h+var_60+4], edx
0x180103826  add     edx, dword ptr [rbp+57h+var_B0+4]
0x180103829  mov     dword ptr [rbp+57h+var_60], eax
0x18010382c  lea     ecx, [rax+rbx]
0x18010382f  mov     dword ptr [rbp+57h+var_60+0Ch], edx
0x180103832  mov     eax, r8d
0x180103835  mov     dword ptr [rbp+57h+var_60+8], ecx
0x180103838  mov     ecx, dword ptr [rbp+57h+var_A0+4]
0x18010383b  cdq
0x18010383c  idiv    r15d
0x18010383f  mov     edx, [rbp+57h+var_80.bottom]
0x180103842  sub     edx, ecx
0x180103844  mov     dword ptr [rbp+57h+var_50], eax
0x180103847  add     eax, edi
0x180103849  mov     dword ptr [rbp+57h+var_50+4], edx
0x18010384c  mov     dword ptr [rbp+57h+var_50+8], eax
0x18010384f  lea     eax, [rdx+rcx]
0x180103852  mov     rcx, rsi; this
0x180103855  mov     dword ptr [rbp+57h+var_50+0Ch], eax
0x180103858  call    ?IsRTL@CUIFObject@@IEAAHXZ; CUIFObject::IsRTL(void)
0x18010385d  xor     ebx, ebx
0x18010385f  test    eax, eax
0x180103861  jz      short loc_18010386E
0x180103863  mov     rax, [rsi+30h]
0x180103867  mov     dword ptr [rax+8], 1
0x18010386e  mov     eax, [rsi+54h]
0x180103871  lea     r8, [rbp+57h+rc]
0x180103875  mov     rcx, [rsi+30h]
0x180103879  mov     edi, 200h
0x18010387e  and     eax, edi
0x180103880  mov     [rsp+110h+yBottom], r13d
0x180103885  neg     eax
0x180103887  mov     rdx, r14
0x18010388a  mov     r10, [rcx]
0x18010388d  sbb     r9d, r9d
0x180103890  and     r9d, 51h
0x180103894  add     r9d, 54h ; 'T'
0x180103898  mov     rax, [r10+60h]
0x18010389c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801038a1  mov     r9, [rsi+98h]
0x1801038a8  test    r9, r9
0x1801038ab  jz      short loc_1801038E1
0x1801038ad  mov     r10, [rsi+30h]
0x1801038b1  lea     r8, [rbp+57h+var_50]
0x1801038b5  mov     ecx, [rsi+54h]
0x1801038b8  mov     rdx, r14
0x1801038bb  shr     ecx, 0Ah
0x1801038be  and     ecx, 1
0x1801038c1  mov     rax, [r10]
0x1801038c4  mov     [rsp+110h+x1], ecx
0x1801038c8  mov     rcx, r10
0x1801038cb  mov     dword ptr [rsp+110h+hdcSrc], r13d
0x1801038d0  mov     [rsp+110h+yBottom], 0FFFFFFFFh
0x1801038d8  mov     rax, [rax+70h]
0x1801038dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801038e1  mov     r9, [rsi+0A0h]
0x1801038e8  test    r9, r9
0x1801038eb  jz      short loc_18010390B
0x1801038ed  mov     r10, [rsi+30h]
0x1801038f1  lea     rcx, [rsi+0CCh]
0x1801038f8  mov     [rsp+110h+hdcSrc], rcx
0x1801038fd  mov     [rsp+110h+yBottom], r13d
0x180103902  mov     rax, [r10]
0x180103905  mov     rax, [rax+78h]
0x180103909  jmp     short loc_180103936
0x18010390b  mov     r9, [rsi+0B8h]
0x180103912  test    r9, r9
0x180103915  jz      short loc_180103945
0x180103917  mov     r10, [rsi+30h]
0x18010391b  mov     rcx, [rsi+0C0h]
0x180103922  mov     dword ptr [rsp+110h+hdcSrc], r13d
0x180103927  mov     qword ptr [rsp+110h+yBottom], rcx
0x18010392c  mov     rax, [r10]
0x18010392f  mov     rax, [rax+80h]
0x180103936  lea     r8, [rbp+57h+var_60]
0x18010393a  mov     rdx, r14
0x18010393d  mov     rcx, r10
0x180103940  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103945  mov     rcx, rsi; this
0x180103948  call    ?IsRTL@CUIFObject@@IEAAHXZ; CUIFObject::IsRTL(void)
0x18010394d  test    eax, eax
0x18010394f  jz      short loc_180103958
0x180103951  mov     rax, [rsi+30h]
0x180103955  mov     [rax+8], ebx
0x180103958  mov     eax, [rsi+54h]
  ... truncated ...
```
