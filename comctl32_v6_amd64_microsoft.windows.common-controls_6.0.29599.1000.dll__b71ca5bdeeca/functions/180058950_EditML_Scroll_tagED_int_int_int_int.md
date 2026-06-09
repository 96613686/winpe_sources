# EditML_Scroll(tagED *,int,int,int,int)

- ea: `0x180058950`
- end: `0x180058f54`
- name: `?EditML_Scroll@@YAJPEAUtagED@@HHHH@Z`
- size: `1540`
- prototype: `__int64 __usercall@<rax>(struct tagED *@<rcx>, int@<edx>, int@<r8d>, int@<r9d>, int)`
- caller_count: `6`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x18005773c`
- `0x1800580a0`
- `0x18005b520`
- `0x18005c478`
- `0x18005ef38`
- `0x1800ddca8`

## callees

- `0x1800579a8`
- `0x180058950`
- `0x180059558`
- `0x18005c9f4`
- `0x18005cd64`
- `0x18005d448`
- `0x18005eeb4`
- `0x180114520`

## import_xrefs

- `GDI32!SelectObject` at `0x180058cc6`
- `GDI32!SelectObject` at `0x180058cc6`
- `GDI32!ExtTextOutW` at `0x180058e51`
- `GDI32!ExtTextOutW` at `0x180058e84`
- `GDI32!ExtTextOutW` at `0x180058e51`
- `GDI32!ExtTextOutW` at `0x180058e84`
- `USER32!ScrollWindowEx` at `0x180058d34`
- `USER32!ScrollWindowEx` at `0x180058ebd`
- `USER32!ScrollWindowEx` at `0x180058d34`
- `USER32!ScrollWindowEx` at `0x180058ebd`
- `USER32!CopyRect` at `0x180058c6d`
- `USER32!CopyRect` at `0x180058c6d`
- `USER32!IntersectRect` at `0x180058c96`
- `USER32!IntersectRect` at `0x180058c96`
- `USER32!SetScrollInfo` at `0x180058b07`
- `USER32!SetScrollInfo` at `0x180058b07`
- `USER32!GetScrollInfo` at `0x180058b49`
- `USER32!GetScrollInfo` at `0x180058b49`
- `USER32!IsWindowVisible` at `0x180058c34`
- `USER32!IsWindowVisible` at `0x180058c34`
- `USER32!UnionRect` at `0x180058dd4`
- `USER32!UnionRect` at `0x180058e1b`
- `USER32!UnionRect` at `0x180058dd4`
- `USER32!UnionRect` at `0x180058e1b`
- `USER32!GetClientRect` at `0x180058c5c`
- `USER32!GetClientRect` at `0x180058c5c`
- `USER32!UpdateWindow` at `0x1800589ab`
- `USER32!UpdateWindow` at `0x180058f1d`
- `USER32!UpdateWindow` at `0x1800589ab`
- `USER32!UpdateWindow` at `0x180058f1d`
- `USER32!InvalidateRect` at `0x180058f13`
- `USER32!InvalidateRect` at `0x180058f13`
- `USER32!ScrollDC` at `0x180058d86`
- `USER32!ScrollDC` at `0x180058ee6`
- `USER32!ScrollDC` at `0x180058d86`
- `USER32!ScrollDC` at `0x180058ee6`

## pseudocode

```c
int __fastcall EditML_Scroll(struct tagED *a1, int a2, int a3, int nTrackPos, BOOL redraw)
{
  int v9; // esi
  int v10; // esi
  int v11; // ecx
  int v12; // eax
  int *v14; // rdi
  int v15; // edx
  int v16; // r11d
  int v17; // r9d
  signed int v18; // ecx
  __int64 v19; // rax
  int v20; // r8d
  HWND v21; // rcx
  HWND v22; // rcx
  int v23; // eax
  int v24; // ecx
  int v25; // eax
  int v26; // edx
  int v27; // esi
  int v28; // edx
  int v29; // ecx
  int v30; // r13d
  int v31; // r14d
  HWND v32; // rcx
  struct tagRECT *v33; // r15
  HDC DC; // rdi
  int v35; // r8d
  void *v36; // rdx
  int v37; // r12d
  int v38; // ecx
  int v39; // ecx
  LONG v40; // edx
  int v41; // eax
  int v42; // [rsp+40h] [rbp-51h]
  struct tagRECT Rect; // [rsp+48h] [rbp-49h] BYREF
  struct tagRECT rcUpdate; // [rsp+58h] [rbp-39h] BYREF
  SCROLLINFO v45; // [rsp+68h] [rbp-29h] BYREF
  struct tagSCROLLINFO v46; // [rsp+88h] [rbp-9h] BYREF

  v42 = 0;
  memset(&v45, 0, sizeof(v45));
  if ( redraw && a3 != -1 )
    UpdateWindow(*((HWND *)a1 + 8));
  if ( *((int *)a1 + 29) < 0 )
  {
    if ( !a2 )
    {
      v9 = *((_DWORD *)a1 + 38);
      if ( v9 > *((_DWORD *)a1 + 22) - *((_DWORD *)a1 + 20) )
      {
        v10 = *((_DWORD *)a1 + 20) + v9 - *((_DWORD *)a1 + 12) - *((_DWORD *)a1 + 22);
        goto LABEL_11;
      }
      goto LABEL_10;
    }
LABEL_9:
    v10 = *((_DWORD *)a1 + 10);
    goto LABEL_11;
  }
  if ( a2 )
    goto LABEL_9;
LABEL_10:
  v10 = *((_DWORD *)a1 + 12);
LABEL_11:
  if ( a3 <= 4 )
  {
    if ( a3 != 4 )
    {
      if ( a3 != -1 )
      {
        if ( (unsigned int)a3 >= 2 )
        {
          if ( a3 != 2 && a3 != 3 )
            return 0;
          if ( a2 )
            v11 = *((_DWORD *)a1 + 11) - 1;
          else
            v11 = *((_DWORD *)a1 + 22) + ~*((_DWORD *)a1 + 20);
          v12 = 1;
          if ( v11 )
            v12 = v11;
          nTrackPos = -v12;
          if ( a3 != 2 )
            nTrackPos = v12;
          goto LABEL_28;
        }
        v42 = nTrackPos;
        nTrackPos = a3 != 0 ? 1 : -1;
LABEL_26:
        if ( !a2 )
          nTrackPos *= *((_DWORD *)a1 + 50);
LABEL_28:
        nTrackPos += v10;
        goto LABEL_40;
      }
      nTrackPos = v10;
      goto LABEL_40;
    }
LABEL_44:
    if ( !a2 )
      goto LABEL_41;
    if ( *((_DWORD *)a1 + 5) >= 0xFFFFu )
    {
      v22 = (HWND)*((_QWORD *)a1 + 8);
      v46.cbSize = 28;
      memset(&v46.nMin, 0, 20);
      v46.fMask = 16;
      GetScrollInfo(v22, 1, &v46);
      nTrackPos = v46.nTrackPos;
    }
    goto LABEL_47;
  }
  switch ( a3 )
  {
    case 5:
      goto LABEL_44;
    case 6:
      nTrackPos = 0;
      break;
    case 7:
      v14 = (int *)((char *)a1 + 20);
      if ( !a2 )
        v14 = (int *)((char *)a1 + 152);
      nTrackPos = *v14;
      break;
    case 182:
      goto LABEL_26;
    case 190:
      return v10;
    default:
      return 0;
  }
LABEL_40:
  if ( !a2 )
  {
LABEL_41:
    v15 = *((_DWORD *)a1 + 38);
    v16 = 0x100000;
    v17 = v15;
    v18 = *((_DWORD *)a1 + 22) - *((_DWORD *)a1 + 20);
    v45.nMax = v15;
    goto LABEL_42;
  }
LABEL_47:
  v23 = *((_DWORD *)a1 + 5);
  v15 = v23;
  v45.nMax = v23;
  if ( v23 )
  {
    v15 = v23 - 1;
    v45.nMax = v23 - 1;
  }
  v18 = *((_DWORD *)a1 + 11);
  v17 = v23 - 1;
  v16 = 0x200000;
  if ( !v23 )
    v17 = 0;
LABEL_42:
  v19 = *((_QWORD *)a1 + 46);
  v45.nPage = v18;
  v20 = v18;
  if ( (v16 & *(_DWORD *)(v19 + 12)) != 0 )
  {
    v21 = (HWND)*((_QWORD *)a1 + 8);
    v45.cbSize = 28;
    *(_QWORD *)&v45.fMask = 31;
    v45.nPos = nTrackPos;
    nTrackPos = SetScrollInfo(v21, a2 != 0, &v45, redraw);
  }
  else
  {
    if ( v18 >= v17 + 1 )
      v20 = v17 + 1;
    if ( v20 <= 0 )
    {
      v18 = 0;
      v45.nPage = 0;
    }
    else if ( v18 >= v17 + 1 )
    {
      v18 = v17 + 1;
      v45.nPage = v17 + 1;
    }
    if ( v18 )
      v24 = v18 - 1;
    else
      v24 = 0;
    v25 = 0;
    v26 = v15 - v24;
    if ( nTrackPos > 0 )
      v25 = nTrackPos;
    if ( v25 >= v26 )
    {
      nTrackPos = v26;
    }
    else if ( nTrackPos <= 0 )
    {
      nTrackPos = 0;
    }
  }
  v27 = v10 - nTrackPos;
  if ( !v27 )
    return 0;
  if ( *((int *)a1 + 29) >= 0 )
  {
    if ( !a2 )
    {
LABEL_74:
      v30 = 0;
      *((_DWORD *)a1 + 12) = nTrackPos;
      v31 = v27;
      goto LABEL_75;
    }
  }
  else if ( !a2 )
  {
    v28 = *((_DWORD *)a1 + 20);
    v29 = *((_DWORD *)a1 + 38);
    if ( v29 > *((_DWORD *)a1 + 22) - v28 )
    {
      v27 = -v27;
      nTrackPos = v29 - *((_DWORD *)a1 + 22) - nTrackPos + v28;
      if ( nTrackPos < 0 )
      {
        v27 += nTrackPos;
        nTrackPos = 0;
      }
    }
    goto LABEL_74;
  }
  v31 = 0;
  *((_DWORD *)a1 + 10) = nTrackPos;
  v30 = *((_DWORD *)a1 + 51) * v27;
LABEL_75:
  if ( a3 != 5 )
    Edit_NotifyParent(a1, (a2 != 0) + 1537);
  if ( !redraw || !IsWindowVisible(*((HWND *)a1 + 8)) )
    return (unsigned __int16)-(__int16)v27 | 0x10000;
  v32 = (HWND)*((_QWORD *)a1 + 8);
  Rect = 0;
  rcUpdate = 0;
  *(_OWORD *)&v46.cbSize = 0;
  GetClientRect(v32, &Rect);
  v33 = (struct tagRECT *)((char *)a1 + 80);
  CopyRect((LPRECT)&v46, (const RECT *)a1 + 5);
  if ( a2 )
  {
    v46.cbSize -= *((_DWORD *)a1 + 67);
    v46.nMin += *((_DWORD *)a1 + 68);
  }
  IntersectRect(&Rect, &Rect, (const RECT *)&v46);
  ++Rect.bottom;
  DC = Edit_GetDC(a1, 0);
  Edit_SetClip(a1, DC, v35);
  v36 = (void *)*((_QWORD *)a1 + 24);
  if ( v36 )
    SelectObject(DC, v36);
  Edit_GetBrush(a1, DC);
  if ( a2 )
  {
    if ( v42 )
      ScrollWindowEx(*((HWND *)a1 + 8), v31, v30, 0, 0, 0, &rcUpdate, ((unsigned __int16)v42 << 16) | 0x11);
    else
      ScrollDC(DC, v31, v30, &Rect, &Rect, 0, &rcUpdate);
    goto LABEL_110;
  }
  v37 = *((_DWORD *)a1 + 12) + *((_DWORD *)a1 + 22) - v33->left;
  v38 = *((_DWORD *)a1 + 29);
  Rect = *v33;
  if ( v42 )
  {
    if ( v38 < 0 )
      v31 = -v31;
    ScrollWindowEx(*((HWND *)a1 + 8), v31, v30, 0, 0, 0, &rcUpdate, ((unsigned __int16)v42 << 16) | 0x11);
  }
  else
  {
    if ( v38 < 0 )
      v31 = -v31;
    ScrollDC(DC, v31, v30, &Rect, &Rect, 0, &rcUpdate);
  }
  v39 = *((_DWORD *)a1 + 67);
  if ( v39 )
  {
    v40 = v33->left - v39;
    Rect.right = v33->left;
    Rect.left = v40;
    if ( *((_DWORD *)a1 + 34) )
    {
LABEL_97:
      UnionRect(&rcUpdate, &rcUpdate, &Rect);
      goto LABEL_98;
    }
    if ( *((int *)a1 + 29) < 0 )
    {
      if ( v37 >= *((_DWORD *)a1 + 38) )
        goto LABEL_97;
    }
    else if ( !*((_DWORD *)a1 + 12) )
    {
      goto LABEL_97;
    }
    ExtTextOutW(DC, v40, Rect.top, 0x16u, &Rect, &WindowName, 0, 0);
  }
LABEL_98:
  v41 = *((_DWORD *)a1 + 68);
  if ( v41 )
  {
    Rect.left = *((_DWORD *)a1 + 22);
    Rect.right = Rect.left + v41;
    if ( !*((_DWORD *)a1 + 34) )
    {
      if ( *((int *)a1 + 29) >= 0 )
      {
        if ( v37 >= *((_DWORD *)a1 + 38) )
          goto LABEL_102;
      }
      else if ( !*((_DWORD *)a1 + 12) )
      {
        goto LABEL_102;
      }
      ExtTextOutW(DC, Rect.left, Rect.top, 0x16u, &Rect, &WindowName, 0, 0);
      goto LABEL_110;
    }
LABEL_102:
    UnionRect(&rcUpdate, &rcUpdate, &Rect);
  }
LABEL_110:
  EditML_SetCaretPosition(a1, DC);
  Edit_ReleaseDC(a1, DC, 0);
  InvalidateRect(*((HWND *)a1 + 8), &rcUpdate, 1);
  UpdateWindow(*((HWND *)a1 + 8));
  return (unsigned __int16)-(__int16)v27 | 0x10000;
}

```

## disassembly

```asm
0x180058950  mov     [rsp-8+arg_8], rbx
0x180058955  push    rbp
0x180058956  push    rsi
0x180058957  push    rdi
0x180058958  push    r12
0x18005895a  push    r13
0x18005895c  push    r14
0x18005895e  push    r15
0x180058960  lea     rbp, [rsp-1Fh]
0x180058965  sub     rsp, 0B0h
0x18005896c  mov     rax, cs:__security_cookie
0x180058973  xor     rax, rsp
0x180058976  mov     [rbp+4Fh+var_38], rax
0x18005897a  mov     r13d, [rbp+4Fh+redraw]
0x18005897e  xorps   xmm0, xmm0
0x180058981  xor     r14d, r14d
0x180058984  mov     edi, r9d
0x180058987  mov     [rbp+4Fh+var_A0], r14d
0x18005898b  mov     r15d, r8d
0x18005898e  mov     r12d, edx
0x180058991  mov     rbx, rcx
0x180058994  movups  xmmword ptr [rbp+4Fh+var_78.cbSize], xmm0
0x180058998  movups  xmmword ptr [rbp+4Fh+var_78.nMax], xmm0
0x18005899c  test    r13d, r13d
0x18005899f  jz      short loc_1800589B1
0x1800589a1  cmp     r8d, 0FFFFFFFFh
0x1800589a5  jz      short loc_1800589B1
0x1800589a7  mov     rcx, [rcx+40h]; hWnd
0x1800589ab  call    cs:__imp_UpdateWindow
0x1800589b1  cmp     [rbx+74h], r14d
0x1800589b5  jge     short loc_1800589D7
0x1800589b7  test    r12d, r12d
0x1800589ba  jnz     short loc_1800589DC
0x1800589bc  mov     eax, [rbx+58h]
0x1800589bf  sub     eax, [rbx+50h]
0x1800589c2  mov     esi, [rbx+98h]
0x1800589c8  cmp     esi, eax
0x1800589ca  jle     short loc_1800589E1
0x1800589cc  sub     esi, [rbx+30h]
0x1800589cf  sub     esi, [rbx+58h]
0x1800589d2  add     esi, [rbx+50h]
0x1800589d5  jmp     short loc_1800589E4
0x1800589d7  test    r12d, r12d
0x1800589da  jz      short loc_1800589E1
0x1800589dc  mov     esi, [rbx+28h]
0x1800589df  jmp     short loc_1800589E4
0x1800589e1  mov     esi, [rbx+30h]
0x1800589e4  cmp     r15d, 4
0x1800589e8  jg      short loc_180058A5F
0x1800589ea  jz      loc_180058B14
0x1800589f0  cmp     r15d, 0FFFFFFFFh
0x1800589f4  jz      short loc_180058A5B
0x1800589f6  test    r15d, r15d
0x1800589f9  jz      short loc_180058A3C
0x1800589fb  cmp     r15d, 1
0x1800589ff  jz      short loc_180058A3C
0x180058a01  cmp     r15d, 2
0x180058a05  jz      short loc_180058A11
0x180058a07  cmp     r15d, 3
0x180058a0b  jnz     loc_180058BC2
0x180058a11  test    r12d, r12d
0x180058a14  jz      short loc_180058A1D
0x180058a16  mov     ecx, [rbx+2Ch]
0x180058a19  dec     ecx
0x180058a1b  jmp     short loc_180058A25
0x180058a1d  mov     ecx, [rbx+50h]
0x180058a20  not     ecx
0x180058a22  add     ecx, [rbx+58h]
0x180058a25  test    ecx, ecx
0x180058a27  mov     eax, 1
0x180058a2c  cmovnz  eax, ecx
0x180058a2f  mov     edi, eax
0x180058a31  neg     edi
0x180058a33  cmp     r15d, 2
0x180058a37  cmovnz  edi, eax
0x180058a3a  jmp     short loc_180058A57
0x180058a3c  mov     [rbp+4Fh+var_A0], edi
0x180058a3f  mov     eax, r15d
0x180058a42  neg     eax
0x180058a44  sbb     edi, edi
0x180058a46  and     edi, 2
0x180058a49  dec     edi
0x180058a4b  test    r12d, r12d
0x180058a4e  jnz     short loc_180058A57
0x180058a50  imul    edi, [rbx+0C8h]
0x180058a57  add     edi, esi
0x180058a59  jmp     short loc_180058AA4
0x180058a5b  mov     edi, esi
0x180058a5d  jmp     short loc_180058AA4
0x180058a5f  mov     ecx, r15d
0x180058a62  sub     ecx, 5
0x180058a65  jz      loc_180058B14
0x180058a6b  sub     ecx, 1
0x180058a6e  jz      short loc_180058AA1
0x180058a70  sub     ecx, 1
0x180058a73  jz      short loc_180058A8D
0x180058a75  sub     ecx, 0AFh
0x180058a7b  jz      short loc_180058A4B
0x180058a7d  cmp     ecx, 8
0x180058a80  jnz     loc_180058BC2
0x180058a86  mov     eax, esi
0x180058a88  jmp     loc_180058F2D
0x180058a8d  lea     rdi, [rbx+14h]
0x180058a91  test    r12d, r12d
0x180058a94  jnz     short loc_180058A9D
0x180058a96  lea     rdi, [rbx+98h]
0x180058a9d  mov     edi, [rdi]
0x180058a9f  jmp     short loc_180058AA4
0x180058aa1  mov     edi, r14d
0x180058aa4  test    r12d, r12d
0x180058aa7  jnz     loc_180058B52
0x180058aad  mov     edx, [rbx+98h]
0x180058ab3  mov     r11d, 100000h
0x180058ab9  mov     ecx, [rbx+58h]
0x180058abc  mov     r9d, edx
0x180058abf  sub     ecx, [rbx+50h]
0x180058ac2  mov     [rbp+4Fh+var_78.nMax], edx
0x180058ac5  mov     rax, [rbx+170h]
0x180058acc  mov     r10d, ecx
0x180058acf  mov     [rbp+4Fh+var_78.nPage], ecx
0x180058ad2  mov     r8d, ecx
0x180058ad5  mov     r14d, ecx
0x180058ad8  test    [rax+0Ch], r11d
0x180058adc  jz      loc_180058B7C
0x180058ae2  mov     rcx, [rbx+40h]; hwnd
0x180058ae6  lea     r8, [rbp+4Fh+var_78]; lpsi
0x180058aea  xor     edx, edx
0x180058aec  mov     [rbp+4Fh+var_78.cbSize], 1Ch
0x180058af3  test    r12d, r12d
0x180058af6  mov     qword ptr [rbp+4Fh+var_78.fMask], 1Fh
0x180058afe  mov     r9d, r13d; redraw
0x180058b01  mov     [rbp+4Fh+var_78.nPos], edi
0x180058b04  setnz   dl; nBar
0x180058b07  call    cs:__imp_SetScrollInfo
0x180058b0d  mov     edi, eax
0x180058b0f  jmp     loc_180058BBE
0x180058b14  test    r12d, r12d
0x180058b17  jz      short loc_180058AAD
0x180058b19  cmp     dword ptr [rbx+14h], 0FFFFh
0x180058b20  jb      short loc_180058B52
0x180058b22  mov     rcx, [rbx+40h]; hwnd
0x180058b26  lea     r8, [rbp+4Fh+var_58]; lpsi
0x180058b2a  xorps   xmm0, xmm0
0x180058b2d  mov     [rbp+4Fh+var_58.nTrackPos], r14d
0x180058b31  mov     edx, 1; nBar
0x180058b36  mov     [rbp+4Fh+var_58.cbSize], 1Ch
0x180058b3d  movdqu  xmmword ptr [rbp+4Fh+var_58.nMin], xmm0
0x180058b42  mov     [rbp+4Fh+var_58.fMask], 10h
0x180058b49  call    cs:__imp_GetScrollInfo
0x180058b4f  mov     edi, [rbp+4Fh+var_58.nTrackPos]
0x180058b52  mov     eax, [rbx+14h]
0x180058b55  mov     edx, eax
0x180058b57  mov     [rbp+4Fh+var_78.nMax], eax
0x180058b5a  test    eax, eax
0x180058b5c  jz      short loc_180058B64
0x180058b5e  lea     edx, [rax-1]
0x180058b61  mov     [rbp+4Fh+var_78.nMax], edx
0x180058b64  mov     ecx, [rbx+2Ch]
0x180058b67  lea     r9d, [rax-1]
0x180058b6b  test    eax, eax
0x180058b6d  mov     r11d, 200000h
0x180058b73  cmovz   r9d, eax
0x180058b77  jmp     loc_180058AC5
0x180058b7c  lea     eax, [r9+1]
0x180058b80  cmp     r14d, eax
0x180058b83  cmovge  r8d, eax
0x180058b87  test    r8d, r8d
0x180058b8a  jle     short loc_180058B98
0x180058b8c  cmp     r10d, eax
0x180058b8f  jl      short loc_180058B9D
0x180058b91  mov     ecx, eax
0x180058b93  mov     [rbp+4Fh+var_78.nPage], eax
0x180058b96  jmp     short loc_180058B9D
0x180058b98  xor     ecx, ecx
0x180058b9a  mov     [rbp+4Fh+var_78.nPage], ecx
0x180058b9d  test    ecx, ecx
0x180058b9f  jz      short loc_180058BA5
0x180058ba1  dec     ecx
0x180058ba3  jmp     short loc_180058BA7
0x180058ba5  xor     ecx, ecx
0x180058ba7  xor     eax, eax
0x180058ba9  sub     edx, ecx
0x180058bab  test    edi, edi
0x180058bad  cmovg   eax, edi
0x180058bb0  cmp     eax, edx
0x180058bb2  jge     short loc_180058BBC
0x180058bb4  test    edi, edi
0x180058bb6  jg      short loc_180058BBE
0x180058bb8  xor     edi, edi
0x180058bba  jmp     short loc_180058BBE
0x180058bbc  mov     edi, edx
0x180058bbe  sub     esi, edi
0x180058bc0  jnz     short loc_180058BC9
0x180058bc2  xor     eax, eax
0x180058bc4  jmp     loc_180058F2D
0x180058bc9  cmp     dword ptr [rbx+74h], 0
0x180058bcd  jge     loc_180058D3C
0x180058bd3  test    r12d, r12d
0x180058bd6  jnz     loc_180058D45
0x180058bdc  mov     eax, [rbx+58h]
0x180058bdf  mov     edx, [rbx+50h]
0x180058be2  sub     eax, edx
0x180058be4  mov     ecx, [rbx+98h]
0x180058bea  cmp     ecx, eax
0x180058bec  jle     short loc_180058C00
0x180058bee  sub     ecx, [rbx+58h]
0x180058bf1  neg     esi
0x180058bf3  sub     ecx, edi
0x180058bf5  lea     edi, [rcx+rdx]
0x180058bf8  test    edi, edi
0x180058bfa  jns     short loc_180058C00
0x180058bfc  add     esi, edi
0x180058bfe  xor     edi, edi
0x180058c00  xor     r13d, r13d
0x180058c03  mov     [rbx+30h], edi
0x180058c06  mov     r14d, esi
0x180058c09  cmp     r15d, 5
0x180058c0d  jz      short loc_180058C26
0x180058c0f  mov     eax, r12d
0x180058c12  mov     rcx, rbx; struct tagED *
0x180058c15  neg     eax
0x180058c17  sbb     edx, edx
0x180058c19  neg     edx
0x180058c1b  add     edx, 601h; int
0x180058c21  call    ?Edit_NotifyParent@@YAXPEAUtagED@@H@Z; Edit_NotifyParent(tagED *,int)
0x180058c26  cmp     [rbp+4Fh+redraw], 0
0x180058c2a  jz      loc_180058F23
0x180058c30  mov     rcx, [rbx+40h]; hWnd
0x180058c34  call    cs:__imp_IsWindowVisible
0x180058c3a  test    eax, eax
0x180058c3c  jz      loc_180058F23
0x180058c42  mov     rcx, [rbx+40h]; hWnd
0x180058c46  lea     rdx, [rbp+4Fh+Rect]; lpRect
0x180058c4a  xorps   xmm0, xmm0
0x180058c4d  xorps   xmm1, xmm1
0x180058c50  movups  xmmword ptr [rbp+4Fh+Rect.left], xmm0
0x180058c54  movups  xmmword ptr [rbp+4Fh+rcUpdate.left], xmm1
0x180058c58  movups  xmmword ptr [rbp+4Fh+var_58.cbSize], xmm0
0x180058c5c  call    cs:__imp_GetClientRect
0x180058c62  lea     r15, [rbx+50h]
0x180058c66  mov     rdx, r15; lprcSrc
0x180058c69  lea     rcx, [rbp+4Fh+var_58]; lprcDst
0x180058c6d  call    cs:__imp_CopyRect
0x180058c73  test    r12d, r12d
0x180058c76  jz      short loc_180058C8A
0x180058c78  mov     eax, [rbx+10Ch]
0x180058c7e  sub     [rbp+4Fh+var_58.cbSize], eax
0x180058c81  mov     eax, [rbx+110h]
0x180058c87  add     [rbp+4Fh+var_58.nMin], eax
0x180058c8a  lea     r8, [rbp+4Fh+var_58]; lprcSrc2
0x180058c8e  lea     rdx, [rbp+4Fh+Rect]; lprcSrc1
0x180058c92  lea     rcx, [rbp+4Fh+Rect]; lprcDst
0x180058c96  call    cs:__imp_IntersectRect
0x180058c9c  inc     [rbp+4Fh+Rect.bottom]
0x180058c9f  xor     edx, edx; int
0x180058ca1  mov     rcx, rbx; struct tagED *
0x180058ca4  call    ?Edit_GetDC@@YAPEAUHDC__@@PEAUtagED@@H@Z; Edit_GetDC(tagED *,int)
0x180058ca9  mov     rdx, rax; HDC
0x180058cac  mov     rcx, rbx; struct tagED *
0x180058caf  mov     rdi, rax
0x180058cb2  call    ?Edit_SetClip@@YAXPEAUtagED@@PEAUHDC__@@H@Z; Edit_SetClip(tagED *,HDC__ *,int)
0x180058cb7  mov     rdx, [rbx+0C0h]; h
0x180058cbe  test    rdx, rdx
0x180058cc1  jz      short loc_180058CCC
0x180058cc3  mov     rcx, rdi; hdc
0x180058cc6  call    cs:__imp_SelectObject
0x180058ccc  mov     rdx, rdi; HDC
0x180058ccf  mov     rcx, rbx; struct tagED *
0x180058cd2  call    ?Edit_GetBrush@@YAPEAUHBRUSH__@@PEAUtagED@@PEAUHDC__@@@Z; Edit_GetBrush(tagED *,HDC__ *)
0x180058cd7  mov     eax, [rbp+4Fh+var_A0]
0x180058cda  xor     edx, edx
0x180058cdc  test    r12d, r12d
0x180058cdf  jnz     loc_180058E8C
0x180058ce5  mov     r12d, [rbx+58h]
0x180058ce9  sub     r12d, [r15]
0x180058cec  movups  xmm0, xmmword ptr [r15]
0x180058cf0  add     r12d, [rbx+30h]
0x180058cf4  mov     ecx, [rbx+74h]
0x180058cf7  movdqu  xmmword ptr [rbp+4Fh+Rect.left], xmm0
0x180058cfc  test    eax, eax
0x180058cfe  jz      short loc_180058D5B
0x180058d00  movzx   eax, ax
0x180058d03  shl     eax, 10h
0x180058d06  or      eax, 11h
0x180058d09  test    ecx, ecx
0x180058d0b  jns     short loc_180058D10
0x180058d0d  neg     r14d
0x180058d10  mov     rcx, [rbx+40h]; hWnd
0x180058d14  xor     r9d, r9d; prcScroll
0x180058d17  mov     [rsp+0E0h+flags], eax; flags
0x180058d1b  mov     r8d, r13d; dy
0x180058d1e  lea     rax, [rbp+4Fh+rcUpdate]
0x180058d22  mov     [rsp+0E0h+prcUpdate], rax; prcUpdate
0x180058d27  mov     [rsp+0E0h+hrgnUpdate], rdx; hrgnUpdate
0x180058d2c  mov     [rsp+0E0h+prcClip], rdx; prcClip
0x180058d31  mov     edx, r14d; dx
0x180058d34  call    cs:__imp_ScrollWindowEx
0x180058d3a  jmp     short loc_180058D8C
0x180058d3c  test    r12d, r12d
0x180058d3f  jz      loc_180058C00
  ... truncated ...
```
