# CToolTipsMgr::CreateBalloonRgn(int,int,int,int,int,int,int)

- ea: `0x18013246c`
- end: `0x1801328c3`
- name: `?CreateBalloonRgn@CToolTipsMgr@@AEAAPEAUHRGN__@@HHHHHHH@Z`
- size: `1111`
- prototype: `HRGN(CToolTipsMgr *__hidden this, int, int, int, int, int, int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18007370c`

## callees

- `0x180114520`
- `0x1801322a0`
- `0x18013246c`

## import_xrefs

- `GDI32!DeleteObject` at `0x180132892`
- `GDI32!DeleteObject` at `0x180132892`
- `GDI32!CombineRgn` at `0x180132888`
- `GDI32!CombineRgn` at `0x180132888`
- `GDI32!CreateRectRgn` at `0x18013279c`
- `GDI32!CreateRectRgn` at `0x18013279c`
- `GDI32!CreateRoundRectRgn` at `0x180132855`
- `GDI32!CreateRoundRectRgn` at `0x180132855`
- `GDI32!CreatePolygonRgn` at `0x180132869`
- `GDI32!CreatePolygonRgn` at `0x180132869`
- `USER32!SetRect` at `0x1801324ec`
- `USER32!SetRect` at `0x1801324ec`
- `USER32!EqualRect` at `0x18013276b`
- `USER32!EqualRect` at `0x180132780`
- `USER32!EqualRect` at `0x18013276b`
- `USER32!EqualRect` at `0x180132780`
- `USER32!GetWindowRgn` at `0x1801327ad`
- `USER32!GetWindowRgn` at `0x1801327ad`
- `UxTheme!GetThemeBackgroundRegion` at `0x1801327d8`
- `UxTheme!GetThemeBackgroundRegion` at `0x180132800`
- `UxTheme!GetThemeBackgroundRegion` at `0x1801327d8`
- `UxTheme!GetThemeBackgroundRegion` at `0x180132800`

## pseudocode

```c
HRGN __fastcall CToolTipsMgr::CreateBalloonRgn(
        CToolTipsMgr *this,
        int a2,
        int a3,
        int a4,
        LONG a5,
        int yTop,
        int a7,
        int a8)
{
  int yBottom; // ecx
  int v13; // eax
  int v14; // r10d
  int x; // r8d
  int v16; // r11d
  int v17; // ecx
  int v18; // ecx
  int v19; // r14d
  unsigned __int64 v20; // r9
  int v21; // ecx
  int v22; // eax
  int v23; // edx
  int v24; // r8d
  int v25; // r8d
  int v26; // eax
  int v27; // r8d
  int v28; // eax
  int v29; // r8d
  __int64 v30; // r11
  int v31; // eax
  int v32; // ecx
  int v33; // ebx
  int v34; // eax
  int v35; // edx
  int v36; // ecx
  __int64 v37; // r8
  int v38; // ecx
  int v39; // eax
  HRGN RectRgn; // rax
  HWND v41; // rcx
  struct tagRECT v42; // xmm0
  RECT v43; // xmm1
  HRGN v44; // rax
  POINT v46; // [rsp+30h] [rbp-59h]
  __int64 v47; // [rsp+30h] [rbp-59h]
  int y2; // [rsp+38h] [rbp-51h]
  int y1; // [rsp+3Ch] [rbp-4Dh]
  HRGN hrgnSrc2; // [rsp+40h] [rbp-49h] BYREF
  HRGN hrgnSrc1; // [rsp+48h] [rbp-41h] BYREF
  RECT rc2; // [rsp+50h] [rbp-39h] BYREF
  struct tagRECT rc; // [rsp+60h] [rbp-29h] BYREF
  POINT pptl; // [rsp+70h] [rbp-19h] BYREF
  int v55; // [rsp+78h] [rbp-11h]
  int v56; // [rsp+7Ch] [rbp-Dh]
  __int64 v57; // [rsp+80h] [rbp-9h]

  hrgnSrc1 = 0;
  yBottom = a5 - yTop;
  if ( !a7 )
    yBottom = a5;
  v13 = 0;
  y2 = yBottom;
  if ( !a7 )
    v13 = yTop;
  y1 = v13;
  rc = 0;
  rc2 = 0;
  SetRect(&rc, 0, v13, a4, yBottom);
  if ( a4 >= 30 )
  {
    hrgnSrc2 = 0;
    v14 = yTop + 1;
    if ( a2 == (unsigned int)a4 >> 1 || a4 < yTop + 33 )
    {
      v16 = a8;
      v46.x = (a4 - v14) / 2;
      x = v46.x;
      if ( a8 )
        goto LABEL_17;
    }
    else
    {
      if ( a2 <= (int)((unsigned int)a4 >> 1) )
      {
        x = 16;
        if ( a2 > 16 )
          x = a2;
      }
      else if ( a2 >= a4 - 16 )
      {
        x = a4 - v14 - 16;
      }
      else
      {
        x = a2 - v14;
      }
      v16 = a8;
      if ( a8 )
      {
        x = a4 - x;
        v46.x = x;
LABEL_17:
        v17 = -(a2 + x - a4);
        if ( a2 + x - a4 > 0 )
          v17 = a2 + x - a4;
        if ( v17 > 2 )
        {
LABEL_26:
          if ( a7 )
            v19 = a5 - yTop - 2;
          else
            v19 = yTop + 2;
          v46.y = v19;
          v20 = (unsigned __int64)v46;
          pptl = v46;
          if ( v16 )
            v21 = x - v14;
          else
            v21 = v14 + x;
          v22 = v14 + x;
          v23 = v21;
          v24 = x - v14;
          if ( v16 )
          {
            v25 = a2 + v24 - a4;
            v26 = -v25;
            if ( v25 > 0 )
              v26 = v25;
            if ( v26 <= 2 )
            {
              v21 = a4 - a2;
              v23 = a4 - a2;
            }
          }
          else
          {
            v27 = v22 - a2;
            v28 = a2 - v22;
            if ( v27 > 0 )
              v28 = v27;
            if ( v28 <= 2 )
            {
              v21 = a2;
              v23 = a2;
            }
          }
          v55 = v21;
          v56 = v19;
          if ( v16 )
          {
            v29 = a4 - a2;
            LODWORD(v47) = a4 - a2;
          }
          else
          {
            v29 = a2;
            LODWORD(v47) = a2;
          }
          v30 = *((_QWORD *)this + 36);
          HIDWORD(v47) = a3;
          v57 = v47;
          if ( !v30 )
          {
            v33 = 0;
            *((_DWORD *)this + 52) &= ~0x40u;
            goto LABEL_75;
          }
          v31 = v20;
          if ( (int)v20 >= v23 )
          {
            v20 = __PAIR64__(v19, v23);
          }
          else
          {
            v31 = v23;
            v23 = v20;
          }
          if ( v29 == v23 )
          {
            v32 = 1;
          }
          else
          {
            v32 = 0;
            if ( v29 == v31 )
              v32 = 2;
          }
          if ( a7 )
          {
            if ( a7 == 0 )
            {
LABEL_54:
              v33 = 0;
              goto LABEL_55;
            }
            v35 = 0;
            v36 = v32 - 1;
            if ( v36 )
            {
              if ( v36 == 1 )
              {
                v37 = 4;
              }
              else
              {
                v37 = 0;
                v35 = -2147024809;
              }
            }
            else
            {
              v37 = 6;
            }
            if ( v35 < 0 )
              v37 = 0;
            v33 = v37;
            if ( v35 < 0 )
              goto LABEL_55;
          }
          else
          {
            v38 = v32 - 1;
            if ( v38 )
            {
              if ( v38 != 1 )
                goto LABEL_54;
              v37 = 3;
              v33 = 3;
            }
            else
            {
              v37 = 1;
              v33 = 1;
            }
          }
          if ( (int)CalculateBalloonStemRect(v30, (unsigned int)(a7 != 0) + 1, v37, v20, &rc2) >= 0
            && rc2.top >= 0
            && rc2.bottom <= a5 )
          {
            v34 = 1;
            goto LABEL_56;
          }
LABEL_55:
          v34 = 0;
LABEL_56:
          *((_DWORD *)this + 52) &= ~0x40u;
          *((_DWORD *)this + 52) |= v34 << 6;
LABEL_75:
          v39 = *((_DWORD *)this + 52);
          if ( (v39 & 0x40) != 0 )
          {
            if ( (v39 & 0x80u) == 0
              || !EqualRect((const RECT *)((char *)this + 332), &rc)
              || !EqualRect((const RECT *)((char *)this + 348), &rc2)
              || *((_DWORD *)this + 82) != v33
              || (RectRgn = CreateRectRgn(0, 0, 0, 0),
                  v41 = (HWND)*((_QWORD *)this + 1),
                  hrgnSrc1 = RectRgn,
                  !GetWindowRgn(v41, RectRgn)) )
            {
              GetThemeBackgroundRegion(*((HTHEME *)this + 36), 0, 3, 0, &rc, &hrgnSrc1);
              GetThemeBackgroundRegion(*((HTHEME *)this + 36), 0, 6, v33, &rc2, &hrgnSrc2);
              v42 = rc;
              *((_DWORD *)this + 52) |= 0x80u;
              v43 = rc2;
              *((_DWORD *)this + 82) = v33;
              *(struct tagRECT *)((char *)this + 332) = v42;
              *(RECT *)((char *)this + 348) = v43;
            }
            v44 = hrgnSrc2;
          }
          else
          {
            *((_DWORD *)this + 52) = v39 & 0xFFFFFF7F;
            hrgnSrc1 = CreateRoundRectRgn(0, y1, a4, y2, 13, 13);
            v44 = CreatePolygonRgn(&pptl, 3, 1);
            hrgnSrc2 = v44;
          }
          if ( v44 )
          {
            CombineRgn(hrgnSrc1, hrgnSrc1, v44, 2);
            DeleteObject(hrgnSrc2);
          }
          return hrgnSrc1;
        }
        x = a4 - a2;
LABEL_25:
        v46.x = x;
        goto LABEL_26;
      }
    }
    v18 = a2 - x;
    if ( a2 - x < 0 )
      v18 = x - a2;
    if ( v18 <= 2 )
      x = a2;
    goto LABEL_25;
  }
  return hrgnSrc1;
}

```

## disassembly

```asm
0x18013246c  mov     [rsp-8+arg_8], rbx
0x180132471  push    rbp
0x180132472  push    rsi
0x180132473  push    rdi
0x180132474  push    r12
0x180132476  push    r13
0x180132478  push    r14
0x18013247a  push    r15
0x18013247c  lea     rbp, [rsp-7]
0x180132481  sub     rsp, 90h
0x180132488  mov     rax, cs:__security_cookie
0x18013248f  xor     rax, rsp
0x180132492  mov     [rbp+37h+var_38], rax
0x180132496  mov     r14d, [rbp+37h+yTop]
0x18013249a  mov     rdi, rcx
0x18013249d  mov     r12d, [rbp+37h+arg_30]
0x1801324a1  mov     r13d, r8d
0x1801324a4  mov     r15d, [rbp+37h+arg_20]
0x1801324a8  mov     ebx, edx
0x1801324aa  sub     r15d, r14d
0x1801324ad  mov     [rbp+37h+hrgnSrc1], 0
0x1801324b5  test    r12d, r12d
0x1801324b8  mov     ecx, r15d
0x1801324bb  xorps   xmm0, xmm0
0x1801324be  xorps   xmm1, xmm1
0x1801324c1  cmovz   ecx, [rbp+37h+arg_20]
0x1801324c5  mov     esi, r9d
0x1801324c8  xor     eax, eax
0x1801324ca  mov     [rbp+37h+y2], ecx
0x1801324cd  mov     [rsp+0C0h+yBottom], ecx; yBottom
0x1801324d1  test    r12d, r12d
0x1801324d4  lea     rcx, [rbp+37h+rc]; lprc
0x1801324d8  cmovz   eax, r14d
0x1801324dc  xor     edx, edx; xLeft
0x1801324de  mov     r8d, eax; yTop
0x1801324e1  mov     [rbp+37h+y1], eax
0x1801324e4  movups  xmmword ptr [rbp+37h+rc.left], xmm0
0x1801324e8  movups  xmmword ptr [rbp+37h+rc2.left], xmm1
0x1801324ec  call    cs:__imp_SetRect
0x1801324f2  cmp     esi, 1Eh
0x1801324f5  jl      loc_180132898
0x1801324fb  mov     ecx, esi
0x1801324fd  mov     [rbp+37h+hrgnSrc2], 0
0x180132505  shr     ecx, 1
0x180132507  lea     r10d, [r14+1]
0x18013250b  mov     [rbp+37h+var_90], 0
0x180132513  mov     r9d, 2
0x180132519  cmp     ebx, ecx
0x18013251b  jz      short loc_180132567
0x18013251d  lea     eax, [r10+20h]
0x180132521  cmp     esi, eax
0x180132523  jl      short loc_180132567
0x180132525  cmp     ebx, ecx
0x180132527  jle     short loc_180132544
0x180132529  lea     eax, [rsi-10h]
0x18013252c  cmp     ebx, eax
0x18013252e  jge     short loc_180132538
0x180132530  mov     r8d, ebx
0x180132533  sub     r8d, r10d
0x180132536  jmp     short loc_180132551
0x180132538  mov     r8d, esi
0x18013253b  sub     r8d, r10d
0x18013253e  sub     r8d, 10h
0x180132542  jmp     short loc_180132551
0x180132544  mov     r8d, 10h
0x18013254a  cmp     ebx, r8d
0x18013254d  cmovg   r8d, ebx
0x180132551  mov     r11d, [rbp+37h+arg_38]
0x180132555  test    r11d, r11d
0x180132558  jz      short loc_18013259A
0x18013255a  mov     eax, esi
0x18013255c  sub     eax, r8d
0x18013255f  mov     r8d, eax
0x180132562  mov     dword ptr [rbp+37h+var_90], eax
0x180132565  jmp     short loc_18013257F
0x180132567  mov     r11d, [rbp+37h+arg_38]
0x18013256b  mov     eax, esi
0x18013256d  sub     eax, r10d
0x180132570  cdq
0x180132571  idiv    r9d
0x180132574  mov     dword ptr [rbp+37h+var_90], eax
0x180132577  mov     r8d, eax
0x18013257a  test    r11d, r11d
0x18013257d  jz      short loc_18013259A
0x18013257f  mov     edx, r8d
0x180132582  sub     edx, esi
0x180132584  add     edx, ebx
0x180132586  mov     ecx, edx
0x180132588  neg     ecx
0x18013258a  cmovs   ecx, edx
0x18013258d  cmp     ecx, r9d
0x180132590  jg      short loc_1801325B1
0x180132592  mov     r8d, esi
0x180132595  sub     r8d, ebx
0x180132598  jmp     short loc_1801325AD
0x18013259a  mov     eax, r8d
0x18013259d  sub     eax, ebx
0x18013259f  mov     ecx, eax
0x1801325a1  neg     ecx
0x1801325a3  cmovs   ecx, eax
0x1801325a6  cmp     ecx, r9d
0x1801325a9  cmovle  r8d, ebx
0x1801325ad  mov     dword ptr [rbp+37h+var_90], r8d
0x1801325b1  test    r12d, r12d
0x1801325b4  jz      short loc_1801325BC
0x1801325b6  lea     r14d, [r15-2]
0x1801325ba  jmp     short loc_1801325BF
0x1801325bc  add     r14d, r9d
0x1801325bf  mov     dword ptr [rbp+37h+var_90+4], r14d
0x1801325c3  mov     r9, [rbp+37h+var_90]
0x1801325c7  mov     qword ptr [rbp+37h+pptl.x], r9
0x1801325cb  test    r11d, r11d
0x1801325ce  jz      short loc_1801325D8
0x1801325d0  mov     ecx, r8d
0x1801325d3  sub     ecx, r10d
0x1801325d6  jmp     short loc_1801325DC
0x1801325d8  lea     ecx, [r10+r8]
0x1801325dc  lea     eax, [r10+r8]
0x1801325e0  mov     edx, ecx
0x1801325e2  sub     r8d, r10d
0x1801325e5  test    r11d, r11d
0x1801325e8  cmovz   r8d, eax
0x1801325ec  jz      short loc_18013260A
0x1801325ee  sub     r8d, esi
0x1801325f1  add     r8d, ebx
0x1801325f4  mov     eax, r8d
0x1801325f7  neg     eax
0x1801325f9  cmovs   eax, r8d
0x1801325fd  cmp     eax, 2
0x180132600  jg      short loc_18013261F
0x180132602  mov     ecx, esi
0x180132604  sub     ecx, ebx
0x180132606  mov     edx, ecx
0x180132608  jmp     short loc_18013261F
0x18013260a  sub     r8d, ebx
0x18013260d  mov     eax, r8d
0x180132610  neg     eax
0x180132612  cmovs   eax, r8d
0x180132616  cmp     eax, 2
0x180132619  jg      short loc_18013261F
0x18013261b  mov     ecx, ebx
0x18013261d  mov     edx, ebx
0x18013261f  mov     [rbp+37h+var_48], ecx
0x180132622  mov     [rbp+37h+var_44], r14d
0x180132626  test    r11d, r11d
0x180132629  jz      short loc_180132637
0x18013262b  mov     r8d, esi
0x18013262e  sub     r8d, ebx
0x180132631  mov     dword ptr [rbp+37h+var_90], r8d
0x180132635  jmp     short loc_18013263D
0x180132637  mov     r8d, ebx
0x18013263a  mov     dword ptr [rbp+37h+var_90], ebx
0x18013263d  mov     r11, [rdi+120h]
0x180132644  mov     r15d, 1
0x18013264a  mov     dword ptr [rbp+37h+var_90+4], r13d
0x18013264e  mov     rax, [rbp+37h+var_90]
0x180132652  mov     [rbp+37h+var_40], rax
0x180132656  lea     r13d, [r15+2]
0x18013265a  test    r11, r11
0x18013265d  jz      loc_180132745
0x180132663  neg     r12d
0x180132666  mov     eax, r9d
0x180132669  sbb     r10d, r10d
0x18013266c  neg     r10d
0x18013266f  add     r10d, r15d
0x180132672  cmp     r9d, edx
0x180132675  jge     short loc_180132682
0x180132677  mov     [rbp+37h+var_90], r9
0x18013267b  mov     eax, edx
0x18013267d  mov     edx, dword ptr [rbp+37h+var_90]
0x180132680  jmp     short loc_18013268D
0x180132682  mov     dword ptr [rbp+37h+var_90], edx
0x180132685  mov     dword ptr [rbp+37h+var_90+4], r14d
0x180132689  mov     r9, [rbp+37h+var_90]
0x18013268d  cmp     r8d, edx
0x180132690  jnz     short loc_180132697
0x180132692  mov     ecx, r15d
0x180132695  jmp     short loc_1801326A2
0x180132697  xor     ecx, ecx
0x180132699  cmp     r8d, eax
0x18013269c  lea     eax, [rcx+2]
0x18013269f  cmovz   ecx, eax
0x1801326a2  mov     edx, r10d
0x1801326a5  sub     edx, r15d
0x1801326a8  jz      short loc_1801326FB
0x1801326aa  cmp     edx, r15d
0x1801326ad  jz      short loc_1801326C8
0x1801326af  xor     ebx, ebx
0x1801326b1  xor     eax, eax
0x1801326b3  and     dword ptr [rdi+0D0h], 0FFFFFFBFh
0x1801326ba  shl     eax, 6
0x1801326bd  or      [rdi+0D0h], eax
0x1801326c3  jmp     loc_18013274E
0x1801326c8  xor     edx, edx
0x1801326ca  sub     ecx, r15d
0x1801326cd  jz      short loc_1801326E6
0x1801326cf  cmp     ecx, r15d
0x1801326d2  jz      short loc_1801326DE
0x1801326d4  xor     r8d, r8d
0x1801326d7  mov     edx, 80070057h
0x1801326dc  jmp     short loc_1801326EC
0x1801326de  mov     r8d, 4
0x1801326e4  jmp     short loc_1801326EC
0x1801326e6  mov     r8d, 6
0x1801326ec  xor     eax, eax
0x1801326ee  test    edx, edx
0x1801326f0  cmovs   r8d, eax
0x1801326f4  mov     ebx, r8d
0x1801326f7  js      short loc_1801326B1
0x1801326f9  jmp     short loc_180132713
0x1801326fb  sub     ecx, r15d
0x1801326fe  jz      short loc_18013270D
0x180132700  cmp     ecx, r15d
0x180132703  jnz     short loc_1801326AF
0x180132705  mov     r8d, r13d
0x180132708  mov     ebx, r13d
0x18013270b  jmp     short loc_180132713
0x18013270d  mov     r8d, r15d
0x180132710  mov     ebx, r15d
0x180132713  lea     rax, [rbp+37h+rc2]
0x180132717  mov     edx, r10d
0x18013271a  mov     rcx, r11
0x18013271d  mov     qword ptr [rsp+0C0h+yBottom], rax
0x180132722  call    ?CalculateBalloonStemRect@@YAJPEAXW4_BALLOON_STEM_DIRECTION@@HUtagPOINT@@PEAUtagRECT@@@Z; CalculateBalloonStemRect(void *,_BALLOON_STEM_DIRECTION,int,tagPOINT,tagRECT *)
0x180132727  test    eax, eax
0x180132729  js      short loc_1801326B1
0x18013272b  cmp     [rbp+37h+rc2.top], 0
0x18013272f  jl      short loc_1801326B1
0x180132731  mov     eax, [rbp+37h+arg_20]
0x180132734  cmp     [rbp+37h+rc2.bottom], eax
0x180132737  jg      loc_1801326B1
0x18013273d  mov     eax, r15d
0x180132740  jmp     loc_1801326B3
0x180132745  xor     ebx, ebx
0x180132747  and     dword ptr [rdi+0D0h], 0FFFFFFBFh
0x18013274e  mov     eax, [rdi+0D0h]
0x180132754  test    al, 40h
0x180132756  jz      loc_180132832
0x18013275c  test    al, al
0x18013275e  jns     short loc_1801327B7
0x180132760  lea     rcx, [rdi+14Ch]; lprc1
0x180132767  lea     rdx, [rbp+37h+rc]; lprc2
0x18013276b  call    cs:__imp_EqualRect
0x180132771  test    eax, eax
0x180132773  jz      short loc_1801327B7
0x180132775  lea     rcx, [rdi+15Ch]; lprc1
0x18013277c  lea     rdx, [rbp+37h+rc2]; lprc2
0x180132780  call    cs:__imp_EqualRect
0x180132786  test    eax, eax
0x180132788  jz      short loc_1801327B7
0x18013278a  cmp     [rdi+148h], ebx
0x180132790  jnz     short loc_1801327B7
0x180132792  xor     r9d, r9d; y2
0x180132795  xor     r8d, r8d; x2
0x180132798  xor     edx, edx; y1
0x18013279a  xor     ecx, ecx; x1
0x18013279c  call    cs:__imp_CreateRectRgn
0x1801327a2  mov     rcx, [rdi+8]; hWnd
0x1801327a6  mov     rdx, rax; hRgn
0x1801327a9  mov     [rbp+37h+hrgnSrc1], rax
0x1801327ad  call    cs:__imp_GetWindowRgn
0x1801327b3  test    eax, eax
0x1801327b5  jnz     short loc_18013282C
0x1801327b7  mov     rcx, [rdi+120h]; hTheme
0x1801327be  lea     rax, [rbp+37h+hrgnSrc1]
0x1801327c2  mov     [rsp+0C0h+pRegion], rax; pRegion
0x1801327c7  xor     r9d, r9d; iStateId
0x1801327ca  lea     rax, [rbp+37h+rc]
0x1801327ce  mov     r8d, r13d; iPartId
0x1801327d1  xor     edx, edx; hdc
0x1801327d3  mov     qword ptr [rsp+0C0h+yBottom], rax; pRect
0x1801327d8  call    cs:__imp_GetThemeBackgroundRegion
0x1801327de  mov     rcx, [rdi+120h]; hTheme
0x1801327e5  lea     rax, [rbp+37h+hrgnSrc2]
0x1801327e9  mov     [rsp+0C0h+pRegion], rax; pRegion
0x1801327ee  xor     edx, edx; hdc
0x1801327f0  lea     rax, [rbp+37h+rc2]
0x1801327f4  mov     r9d, ebx; iStateId
0x1801327f7  mov     qword ptr [rsp+0C0h+yBottom], rax; pRect
0x1801327fc  lea     r8d, [rdx+6]; iPartId
0x180132800  call    cs:__imp_GetThemeBackgroundRegion
0x180132806  movups  xmm0, xmmword ptr [rbp+37h+rc.left]
0x18013280a  bts     dword ptr [rdi+0D0h], 7
0x180132812  movups  xmm1, xmmword ptr [rbp+37h+rc2.left]
0x180132816  mov     [rdi+148h], ebx
0x18013281c  movdqu  xmmword ptr [rdi+14Ch], xmm0
0x180132824  movdqu  xmmword ptr [rdi+15Ch], xmm1
0x18013282c  mov     rax, [rbp+37h+hrgnSrc2]
0x180132830  jmp     short loc_180132873
0x180132832  mov     r9d, [rbp+37h+y2]; y2
0x180132836  btr     eax, 7
0x18013283a  mov     edx, [rbp+37h+y1]; y1
0x18013283d  mov     r8d, esi; x2
0x180132840  mov     [rdi+0D0h], eax
0x180132846  xor     ecx, ecx; x1
0x180132848  mov     eax, 0Dh
0x18013284d  mov     dword ptr [rsp+0C0h+pRegion], eax; h
0x180132851  mov     [rsp+0C0h+yBottom], eax; w
0x180132855  call    cs:__imp_CreateRoundRectRgn
0x18013285b  mov     r8d, r15d; iMode
  ... truncated ...
```
