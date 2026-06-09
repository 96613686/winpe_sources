# CToolbar::GrowToolbar(int,int,uint)

- ea: `0x180012d90`
- end: `0x1800133d9`
- name: `?GrowToolbar@CToolbar@@AEAAHHHI@Z`
- size: `1609`
- prototype: `__int64 __fastcall(CToolbar *__hidden this, int, int, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180012630`
- `0x1800134f0`
- `0x1800567b0`

## callees

- `0x180012d90`
- `0x1800bffd0`
- `0x180114520`
- `0x180114ebc`

## import_xrefs

- `GDI32!DeleteObject` at `0x1800133be`
- `GDI32!DeleteObject` at `0x1800133be`
- `GDI32!GetTextMetricsW` at `0x180013383`
- `GDI32!GetTextMetricsW` at `0x180013383`
- `GDI32!SelectObject` at `0x18001335d`
- `GDI32!SelectObject` at `0x1800133a0`
- `GDI32!SelectObject` at `0x18001335d`
- `GDI32!SelectObject` at `0x1800133a0`
- `GDI32!CreateFontIndirectW` at `0x1800132f5`
- `GDI32!CreateFontIndirectW` at `0x1800132f5`
- `USER32!GetKeyState` at `0x180012f25`
- `USER32!GetKeyState` at `0x180012f25`
- `USER32!GetCapture` at `0x1800131d1`
- `USER32!GetCapture` at `0x1800131d1`
- `USER32!GetDC` at `0x180013346`
- `USER32!GetDC` at `0x180013346`
- `USER32!InvalidateRect` at `0x1800132a2`
- `USER32!InvalidateRect` at `0x1800132a2`
- `USER32!ReleaseDC` at `0x1800133ad`
- `USER32!ReleaseDC` at `0x1800133ad`
- `UxTheme!GetThemeFont` at `0x1800132e0`
- `UxTheme!GetThemeFont` at `0x1800132e0`
- `UxTheme!GetThemeBackgroundExtent` at `0x18001303f`
- `UxTheme!GetThemeBackgroundExtent` at `0x18001303f`

## pseudocode

```c
__int64 __fastcall CToolbar::GrowToolbar(CToolbar *this, int a2, LONG a3, char a4)
{
  char v4; // bl
  int v6; // eax
  LONG v7; // r14d
  int v8; // r12d
  int v9; // esi
  LONG v10; // esi
  LONG *v11; // r15
  int v12; // r12d
  int v13; // ebx
  int v14; // r15d
  __int64 v15; // r9
  __int64 v16; // rdx
  __int64 v17; // rax
  BOOL v18; // r12d
  __int64 v19; // r8
  char v20; // r13
  char v21; // al
  int v22; // r13d
  unsigned int v23; // ecx
  int v25; // ecx
  unsigned int v26; // ecx
  HWND v27; // rbx
  HWND Capture; // rax
  void *v29; // rbx
  HFONT v30; // r15
  int v31; // r12d
  HDC DC; // rax
  HDC v33; // r13
  HGDIOBJ v34; // rbx
  LONG tmHeight; // eax
  int v36; // [rsp+30h] [rbp-D0h]
  LONG v37; // [rsp+30h] [rbp-D0h]
  LONG *v39; // [rsp+38h] [rbp-C8h]
  int v40; // [rsp+40h] [rbp-C0h]
  __int64 v41; // [rsp+40h] [rbp-C0h]
  struct tagRECT pExtentRect; // [rsp+48h] [rbp-B8h] BYREF
  RECT pContentRect; // [rsp+58h] [rbp-A8h] BYREF
  struct tagTEXTMETRICW tm; // [rsp+68h] [rbp-98h] BYREF
  LOGFONTW pFont; // [rsp+B0h] [rbp-50h] BYREF

  v4 = a4;
  if ( !a2 || (v40 = 0, !a3) )
    v40 = 1;
  if ( (a4 & 4) != 0 )
  {
    v25 = *((_DWORD *)this + 95);
    if ( a3 )
    {
      *((_DWORD *)this + 62) = a3;
      v26 = v25 | 0x200000;
    }
    else
    {
      v26 = v25 & 0xFFDFFFFF;
    }
    if ( a2 )
    {
      *((_DWORD *)this + 61) = a2;
      v23 = v26 | 0x400000;
    }
    else
    {
      v23 = v26 & 0xFFBFFFFF;
    }
    *((_DWORD *)this + 95) = v23;
    goto LABEL_57;
  }
  v6 = 24;
  v7 = 22;
  if ( a2 )
    v6 = a2;
  if ( a3 )
    v7 = a3;
  v8 = a4 & 1;
  if ( (a4 & 1) != 0 )
  {
    if ( (*((_DWORD *)this + 18) & 0x1000) != 0 )
      v9 = v6 + *((_DWORD *)this + 59) + *((_DWORD *)this + 72);
    else
      v9 = v6;
    v7 += *((_DWORD *)this + 71);
    v10 = *((_DWORD *)this + 70) + v9;
    if ( v10 < *((_DWORD *)this + 61) && *((_DWORD *)this + 56) && *((int *)this + 57) > 0 )
      v10 = *((_DWORD *)this + 61);
    goto LABEL_12;
  }
  if ( v7 == -1 )
    v7 = *((_DWORD *)this + 62);
  if ( v6 == -1 )
    v10 = *((_DWORD *)this + 61);
  else
    v10 = v6;
  v29 = (void *)*((_QWORD *)this + 51);
  v37 = *((_DWORD *)this + 60);
  if ( !v29 )
  {
    v30 = (HFONT)*((_QWORD *)this + 24);
    v31 = 0;
LABEL_88:
    if ( v30 )
    {
      DC = GetDC(*((HWND *)this + 7));
      v33 = DC;
      if ( DC )
      {
        v34 = SelectObject(DC, v30);
        memset(&tm, 0, sizeof(tm));
        GetTextMetricsW(v33, &tm);
        tmHeight = v37;
        if ( v37 <= tm.tmHeight )
          tmHeight = tm.tmHeight;
        v37 = tmHeight;
        SelectObject(v33, v34);
        ReleaseDC(*((HWND *)this + 7), v33);
      }
      if ( v31 )
        DeleteObject(v30);
    }
    v8 = 0;
    goto LABEL_90;
  }
  memset_0(&pFont, 0, sizeof(pFont));
  if ( GetThemeFont(v29, 0, 0, 0, 210, &pFont) >= 0 )
  {
    v31 = 1;
    v30 = CreateFontIndirectW(&pFont);
    goto LABEL_88;
  }
LABEL_90:
  v4 = a4;
  if ( v7 < *((_DWORD *)this + 71) + v37 )
    v7 = *((_DWORD *)this + 71) + v37;
  if ( v10 < *((_DWORD *)this + 59) + *((_DWORD *)this + 70) )
    v10 = *((_DWORD *)this + 59) + *((_DWORD *)this + 70);
LABEL_12:
  if ( *((_QWORD *)this + 17) )
  {
    v11 = (LONG *)((char *)this + 244);
    v39 = (LONG *)((char *)this + 244);
    if ( v10 <= *((_DWORD *)this + 61) && v7 <= *((_DWORD *)this + 62) )
      goto LABEL_15;
  }
  if ( (unsigned int)CToolbar::CheckMonoMask(this, v10, v7) )
  {
    v11 = (LONG *)((char *)this + 244);
    v39 = (LONG *)((char *)this + 244);
LABEL_15:
    if ( (v4 & 2) != 0 )
      return 1;
    if ( !v8 )
    {
      v11 = (LONG *)((char *)this + 244);
      v39 = (LONG *)((char *)this + 244);
      if ( *((_DWORD *)this + 61) != v10 || *((_DWORD *)this + 62) != v7 )
      {
        InvalidateRect(*((HWND *)this + 7), 0, 1);
        v39 = (LONG *)((char *)this + 244);
      }
    }
    if ( *((_QWORD *)this + 51) && (v40 || *v11 != v10 || *((_DWORD *)this + 62) != v7) )
    {
      v12 = -1;
      *(_QWORD *)&pContentRect.left = 0;
      v13 = 1;
      pContentRect.right = v10;
      pContentRect.bottom = v7;
      v36 = -1;
      if ( *((int *)this + 66) > -1 )
      {
        v14 = 1;
        while ( 1 )
        {
          pExtentRect = 0;
          if ( v12 != -1 )
            break;
LABEL_45:
          if ( GetThemeBackgroundExtent(*((HTHEME *)this + 51), 0, v14, v13, &pContentRect, &pExtentRect) >= 0 )
          {
            if ( v10 <= pExtentRect.right - pExtentRect.left )
              v10 = pExtentRect.right - pExtentRect.left;
            if ( v7 <= pExtentRect.bottom - pExtentRect.top )
              v7 = pExtentRect.bottom - pExtentRect.top;
          }
          v36 = ++v12;
          if ( v12 >= *((_DWORD *)this + 66) )
          {
            v11 = v39;
            goto LABEL_52;
          }
        }
        v15 = *((_QWORD *)this + 18);
        v16 = *((int *)this + 87);
        v17 = v12;
        v18 = 0;
        v19 = v15 + 80 * v17;
        v41 = v19;
        v20 = *(_BYTE *)(v19 + 8);
        if ( (_DWORD)v16 != -1 )
          v18 = v15 + 80 * v16 == v19;
        if ( (v20 & 2) == 0 )
        {
          if ( GetKeyState(1) < 0 )
          {
            v27 = (HWND)*((_QWORD *)this + 7);
            Capture = GetCapture();
            v19 = v41;
            if ( Capture == v27 )
            {
              v18 = 0;
              goto LABEL_29;
            }
          }
          else
          {
            v19 = v41;
          }
        }
        if ( v18 )
        {
LABEL_31:
          if ( (*((_DWORD *)this + 30) & 1) != 0 && (v21 = *(_BYTE *)(v19 + 9), (v21 & 8) != 0) )
          {
            v14 = 2;
            if ( v21 >= 0 )
              v14 = 3;
          }
          else
          {
            v14 = (*(char *)(v19 + 9) < 0) + 1;
          }
          if ( (v20 & 2) != 0 )
          {
            v13 = 3;
          }
          else if ( (v20 & 4) == 0 || (*((_DWORD *)this + 18) & 0x8000000) != 0 )
          {
            v13 = 4;
          }
          else
          {
            v22 = v20 & 1;
            if ( v18 )
            {
              v13 = v22 != 0 ? 6 : 2;
            }
            else
            {
              v13 = 1;
              if ( v22 )
                v13 = 5;
            }
          }
          v12 = v36;
          if ( (*((_DWORD *)this + 30) & 0x400) != 0 && (*((_BYTE *)this + 380) & 0x20) != 0 && v13 == 1 )
            v13 = 7;
          goto LABEL_45;
        }
LABEL_29:
        if ( *((_DWORD *)this + 88) == (v19 - *((_QWORD *)this + 18)) / 80 )
          v18 = 1;
        goto LABEL_31;
      }
    }
LABEL_52:
    v23 = *((_DWORD *)this + 95);
    if ( (v23 & 0x400000) != 0 )
      v10 = *v11;
    *v11 = v10;
    if ( (v23 & 0x200000) != 0 )
      v7 = *((_DWORD *)this + 62);
    *((_DWORD *)this + 65) = *((_DWORD *)this + 109);
    *((_DWORD *)this + 62) = v7;
LABEL_57:
    *((_QWORD *)this + 37) = -1;
    *((_DWORD *)this + 95) = v23 & 0xFFFEFFEF | 0x10;
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180012d90  mov     [rsp-8+arg_18], rbx
0x180012d95  push    rbp
0x180012d96  push    rsi
0x180012d97  push    rdi
0x180012d98  push    r12
0x180012d9a  push    r13
0x180012d9c  push    r14
0x180012d9e  push    r15
0x180012da0  lea     rbp, [rsp-20h]
0x180012da5  sub     rsp, 120h
0x180012dac  mov     rax, cs:__security_cookie
0x180012db3  xor     rax, rsp
0x180012db6  mov     [rbp+50h+var_40], rax
0x180012dba  xor     r10d, r10d
0x180012dbd  mov     ebx, r9d
0x180012dc0  mov     [rsp+150h+var_11C], ebx
0x180012dc4  mov     rdi, rcx
0x180012dc7  mov     r13d, 1
0x180012dcd  test    edx, edx
0x180012dcf  jnz     loc_180012F9C
0x180012dd5  mov     dword ptr [rsp+150h+var_110], r13d
0x180012dda  test    bl, 4
0x180012ddd  jnz     loc_180013100
0x180012de3  test    edx, edx
0x180012de5  mov     eax, 18h
0x180012dea  mov     r14d, 16h
0x180012df0  mov     r12d, ebx
0x180012df3  cmovnz  eax, edx
0x180012df6  test    r8d, r8d
0x180012df9  cmovnz  r14d, r8d
0x180012dfd  and     r12d, r13d
0x180012e00  mov     dword ptr [rsp+150h+var_118], r12d
0x180012e05  jz      loc_180013216
0x180012e0b  test    dword ptr [rcx+48h], 1000h
0x180012e12  jz      loc_18001319C
0x180012e18  mov     esi, [rcx+120h]
0x180012e1e  add     esi, [rcx+0ECh]
0x180012e24  add     esi, eax
0x180012e26  add     r14d, [rcx+11Ch]
0x180012e2d  add     esi, [rcx+118h]
0x180012e33  mov     eax, [rcx+0F4h]
0x180012e39  cmp     esi, eax
0x180012e3b  jl      loc_18001317B
0x180012e41  cmp     [rdi+88h], r10
0x180012e48  jz      loc_180013148
0x180012e4e  lea     r15, [rdi+0F4h]
0x180012e55  mov     [rsp+150h+var_118], r15
0x180012e5a  cmp     esi, [r15]
0x180012e5d  jg      loc_180013148
0x180012e63  cmp     r14d, [rdi+0F8h]
0x180012e6a  jg      loc_180013148
0x180012e70  test    bl, 2
0x180012e73  jnz     loc_1800130CC
0x180012e79  test    r12d, r12d
0x180012e7c  jz      loc_180013284
0x180012e82  cmp     [rdi+198h], r10
0x180012e89  jz      loc_180013082
0x180012e8f  cmp     dword ptr [rsp+150h+var_110], r10d
0x180012e94  jnz     short loc_180012E9F
0x180012e96  cmp     [r15], esi
0x180012e99  jz      loc_1800131B2
0x180012e9f  or      r12d, 0FFFFFFFFh
0x180012ea3  mov     qword ptr [rsp+150h+var_F8.left], 0
0x180012eac  mov     ebx, r13d
0x180012eaf  mov     [rsp+150h+var_F8.right], esi
0x180012eb3  mov     [rsp+150h+var_F8.bottom], r14d
0x180012eb8  mov     [rsp+150h+var_11C], r13d
0x180012ebd  mov     [rsp+150h+var_120], r12d
0x180012ec2  cmp     [rdi+108h], r12d
0x180012ec9  jle     loc_180013082
0x180012ecf  mov     r15d, r13d
0x180012ed2  xorps   xmm0, xmm0
0x180012ed5  movups  xmmword ptr [rsp+150h+var_108.left], xmm0
0x180012eda  cmp     r12d, 0FFFFFFFFh
0x180012ede  jz      loc_18001301C
0x180012ee4  mov     r9, [rdi+90h]
0x180012eeb  movsxd  rdx, dword ptr [rdi+15Ch]
0x180012ef2  movsxd  rax, r12d
0x180012ef5  mov     r12d, r10d
0x180012ef8  lea     r8, [rax+rax*4]
0x180012efc  shl     r8, 4
0x180012f00  add     r8, r9
0x180012f03  mov     [rsp+150h+var_110], r8
0x180012f08  movzx   r13d, byte ptr [r8+8]
0x180012f0d  cmp     edx, 0FFFFFFFFh
0x180012f10  jnz     loc_1800131FA
0x180012f16  lea     ecx, [rdx+2]; nVirtKey
0x180012f19  mov     eax, r13d
0x180012f1c  and     eax, 2
0x180012f1f  mov     [rsp+150h+var_11C], eax
0x180012f23  jnz     short loc_180012F3C
0x180012f25  call    cs:__imp_GetKeyState
0x180012f2b  xor     r10d, r10d
0x180012f2e  test    ax, ax
0x180012f31  js      loc_1800131CD
0x180012f37  mov     r8, [rsp+150h+var_110]
0x180012f3c  test    r12d, r12d
0x180012f3f  jnz     loc_18001313E
0x180012f45  mov     rcx, r8
0x180012f48  mov     rax, 6666666666666667h
0x180012f52  sub     rcx, [rdi+90h]
0x180012f59  imul    rcx
0x180012f5c  sar     rdx, 5
0x180012f60  mov     rax, rdx
0x180012f63  shr     rax, 3Fh
0x180012f67  add     rdx, rax
0x180012f6a  movsxd  rax, dword ptr [rdi+160h]
0x180012f71  cmp     rax, rdx
0x180012f74  mov     edx, 1
0x180012f79  cmovz   r12d, edx
0x180012f7d  mov     ecx, [rdi+78h]
0x180012f80  test    dl, cl
0x180012f82  jz      short loc_180012F8C
0x180012f84  mov     al, [r8+9]
0x180012f88  test    al, 8
0x180012f8a  jnz     short loc_180012FAF
0x180012f8c  cmp     [r8+9], r10b
0x180012f90  mov     r15d, r10d
0x180012f93  setl    r15b
0x180012f97  add     r15d, edx
0x180012f9a  jmp     short loc_180012FBF
0x180012f9c  mov     dword ptr [rsp+150h+var_110], r10d
0x180012fa1  test    r8d, r8d
0x180012fa4  jnz     loc_180012DDA
0x180012faa  jmp     loc_180012DD5
0x180012faf  mov     r15d, 2
0x180012fb5  test    al, al
0x180012fb7  js      short loc_180012FBF
0x180012fb9  mov     r15d, 3
0x180012fbf  cmp     [rsp+150h+var_11C], r10d
0x180012fc4  jnz     loc_180013171
0x180012fca  test    r13b, 4
0x180012fce  jz      loc_1800131F0
0x180012fd4  test    dword ptr [rdi+48h], 8000000h
0x180012fdb  jnz     loc_1800131F0
0x180012fe1  and     r13d, edx
0x180012fe4  test    r12d, r12d
0x180012fe7  jnz     loc_180013309
0x180012fed  mov     ebx, edx
0x180012fef  test    r13d, r13d
0x180012ff2  jnz     loc_1800130F6
0x180012ff8  mov     r12d, [rsp+150h+var_120]
0x180012ffd  bt      ecx, 0Ah
0x180013001  mov     r13d, 1
0x180013007  setb    cl
0x18001300a  test    byte ptr [rdi+17Ch], 20h
0x180013011  setnz   al
0x180013014  test    al, cl
0x180013016  jnz     loc_18001312E
0x18001301c  mov     rcx, [rdi+198h]; hTheme
0x180013023  lea     rax, [rsp+150h+var_108]
0x180013028  mov     [rsp+150h+pExtentRect], rax; pExtentRect
0x18001302d  mov     r9d, ebx; iStateId
0x180013030  lea     rax, [rsp+150h+var_F8]
0x180013035  mov     r8d, r15d; iPartId
0x180013038  xor     edx, edx; hdc
0x18001303a  mov     [rsp+150h+pContentRect], rax; pContentRect
0x18001303f  call    cs:__imp_GetThemeBackgroundExtent
0x180013045  xor     r10d, r10d
0x180013048  test    eax, eax
0x18001304a  js      short loc_180013068
0x18001304c  mov     eax, [rsp+150h+var_108.right]
0x180013050  sub     eax, [rsp+150h+var_108.left]
0x180013054  cmp     esi, eax
0x180013056  cmovle  esi, eax
0x180013059  mov     eax, [rsp+150h+var_108.bottom]
0x18001305d  sub     eax, [rsp+150h+var_108.top]
0x180013061  cmp     r14d, eax
0x180013064  cmovle  r14d, eax
0x180013068  add     r12d, r13d
0x18001306b  mov     [rsp+150h+var_120], r12d
0x180013070  cmp     r12d, [rdi+108h]
0x180013077  jl      loc_180012ED2
0x18001307d  mov     r15, [rsp+150h+var_118]
0x180013082  mov     ecx, [rdi+17Ch]
0x180013088  bt      ecx, 16h
0x18001308c  jnb     short loc_180013091
0x18001308e  mov     esi, [r15]
0x180013091  mov     [r15], esi
0x180013094  bt      ecx, 15h
0x180013098  jnb     short loc_1800130A1
0x18001309a  mov     r14d, [rdi+0F8h]
0x1800130a1  mov     eax, [rdi+1B4h]
0x1800130a7  mov     [rdi+104h], eax
0x1800130ad  mov     [rdi+0F8h], r14d
0x1800130b4  btr     ecx, 10h
0x1800130b8  mov     qword ptr [rdi+128h], 0FFFFFFFFFFFFFFFFh
0x1800130c3  or      ecx, 10h
0x1800130c6  mov     [rdi+17Ch], ecx
0x1800130cc  mov     eax, r13d
0x1800130cf  mov     rcx, [rbp+50h+var_40]
0x1800130d3  xor     rcx, rsp; StackCookie
0x1800130d6  call    __security_check_cookie
0x1800130db  mov     rbx, [rsp+150h+arg_18]
0x1800130e3  add     rsp, 120h
0x1800130ea  pop     r15
0x1800130ec  pop     r14
0x1800130ee  pop     r13
0x1800130f0  pop     r12
0x1800130f2  pop     rdi
0x1800130f3  pop     rsi
0x1800130f4  pop     rbp
0x1800130f5  retn
0x1800130f6  mov     ebx, 5
0x1800130fb  jmp     loc_180012FF8
0x180013100  mov     ecx, [rcx+17Ch]
0x180013106  test    r8d, r8d
0x180013109  jz      loc_1800131C4
0x18001310f  mov     [rdi+0F8h], r8d
0x180013116  bts     ecx, 15h
0x18001311a  test    edx, edx
0x18001311c  jnz     loc_1800131A3
0x180013122  btr     ecx, 16h
0x180013126  mov     [rdi+17Ch], ecx
0x18001312c  jmp     short loc_1800130B4
0x18001312e  cmp     ebx, r13d
0x180013131  mov     eax, 7
0x180013136  cmovz   ebx, eax
0x180013139  jmp     loc_18001301C
0x18001313e  mov     edx, 1
0x180013143  jmp     loc_180012F7D
0x180013148  mov     r8d, r14d; int
0x18001314b  mov     edx, esi; int
0x18001314d  mov     rcx, rdi; this
0x180013150  call    ?CheckMonoMask@CToolbar@@AEAAHHH@Z; CToolbar::CheckMonoMask(int,int)
0x180013155  xor     r10d, r10d
0x180013158  test    eax, eax
0x18001315a  jz      loc_1800133D2
0x180013160  lea     r15, [rdi+0F4h]
0x180013167  mov     [rsp+150h+var_118], r15
0x18001316c  jmp     loc_180012E70
0x180013171  mov     ebx, 3
0x180013176  jmp     loc_180012FF8
0x18001317b  cmp     [rcx+0E0h], r10d
0x180013182  jz      loc_180012E41
0x180013188  cmp     [rcx+0E4h], r10d
0x18001318f  jle     loc_180012E41
0x180013195  mov     esi, eax
0x180013197  jmp     loc_180012E41
0x18001319c  mov     esi, eax
0x18001319e  jmp     loc_180012E26
0x1800131a3  mov     [rdi+0F4h], edx
0x1800131a9  bts     ecx, 16h
0x1800131ad  jmp     loc_180013126
0x1800131b2  cmp     [rdi+0F8h], r14d
0x1800131b9  jz      loc_180013082
0x1800131bf  jmp     loc_180012E9F
0x1800131c4  btr     ecx, 15h
0x1800131c8  jmp     loc_18001311A
0x1800131cd  mov     rbx, [rdi+38h]
0x1800131d1  call    cs:__imp_GetCapture
0x1800131d7  mov     r8, [rsp+150h+var_110]
0x1800131dc  xor     r10d, r10d
0x1800131df  cmp     rax, rbx
0x1800131e2  jnz     loc_180012F3C
0x1800131e8  mov     r12d, r10d
0x1800131eb  jmp     loc_180012F45
0x1800131f0  mov     ebx, 4
0x1800131f5  jmp     loc_180012FF8
0x1800131fa  lea     rcx, [rdx+rdx*4]
0x1800131fe  shl     rcx, 4
0x180013202  add     rcx, r9
0x180013205  cmp     rcx, r8
0x180013208  mov     ecx, 1
0x18001320d  cmovz   r12d, ecx
0x180013211  jmp     loc_180012F19
0x180013216  cmp     r14d, 0FFFFFFFFh
0x18001321a  jz      loc_18001332B
0x180013220  cmp     eax, 0FFFFFFFFh
0x180013223  jz      loc_180013337
0x180013229  mov     esi, eax
0x18001322b  mov     rbx, [rcx+198h]
0x180013232  mov     eax, [rcx+0F0h]
0x180013238  mov     [rsp+150h+var_120], eax
0x18001323c  test    rbx, rbx
0x18001323f  jnz     short loc_1800132B5
0x180013241  mov     r15, [rcx+0C0h]
0x180013248  mov     r12d, r10d
0x18001324b  test    r15, r15
0x18001324e  jnz     loc_180013342
0x180013254  mov     r12d, dword ptr [rsp+150h+var_118]
0x180013259  mov     ecx, [rsp+150h+var_120]
0x18001325d  add     ecx, [rdi+11Ch]
0x180013263  mov     edx, [rdi+118h]
0x180013269  cmp     r14d, ecx
0x18001326c  mov     ebx, [rsp+150h+var_11C]
0x180013270  cmovl   r14d, ecx
0x180013274  add     edx, [rdi+0ECh]
0x18001327a  cmp     esi, edx
0x18001327c  cmovl   esi, edx
0x18001327f  jmp     loc_180012E41
0x180013284  lea     r15, [rdi+0F4h]
0x18001328b  mov     [rsp+150h+var_118], r15
0x180013290  cmp     [r15], esi
0x180013293  jz      loc_180013319
0x180013299  mov     rcx, [rdi+38h]; hWnd
0x18001329d  mov     r8d, r13d; bErase
0x1800132a0  xor     edx, edx; lpRect
0x1800132a2  call    cs:__imp_InvalidateRect
0x1800132a8  xor     r10d, r10d
  ... truncated ...
```
