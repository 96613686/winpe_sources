# CFmtBar::ComboBox_WMDrawItem(tagDRAWITEMSTRUCT *)

- ea: `0x180085eb8`
- end: `0x1800861ec`
- name: `?ComboBox_WMDrawItem@CFmtBar@@AEAAXPEAUtagDRAWITEMSTRUCT@@@Z`
- size: `820`
- prototype: `void __fastcall(CFmtBar *__hidden this, struct tagDRAWITEMSTRUCT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180087fa0`

## callees

- `0x180085eb8`
- `0x1800cc9ba`
- `0x1800cca00`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x1800860dc`
- `GDI32!CreateCompatibleDC` at `0x1800860dc`
- `GDI32!SelectObject` at `0x1800860fe`
- `GDI32!SelectObject` at `0x18008619c`
- `GDI32!SelectObject` at `0x1800860fe`
- `GDI32!SelectObject` at `0x18008619c`
- `GDI32!DeleteDC` at `0x1800861a5`
- `GDI32!DeleteDC` at `0x1800861a5`
- `GDI32!SetBkColor` at `0x180085f25`
- `GDI32!SetBkColor` at `0x180085f42`
- `GDI32!SetBkColor` at `0x1800861bf`
- `GDI32!SetBkColor` at `0x180085f25`
- `GDI32!SetBkColor` at `0x180085f42`
- `GDI32!SetBkColor` at `0x1800861bf`
- `GDI32!SetTextColor` at `0x180085f5c`
- `GDI32!SetTextColor` at `0x1800861b2`
- `GDI32!SetTextColor` at `0x180085f5c`
- `GDI32!SetTextColor` at `0x1800861b2`
- `GDI32!GetTextExtentPoint32W` at `0x180086019`
- `GDI32!GetTextExtentPoint32W` at `0x180086019`
- `GDI32!ExtTextOutW` at `0x180085fec`
- `GDI32!ExtTextOutW` at `0x180085fec`
- `GDI32!GetLayout` at `0x18008610a`
- `GDI32!GetLayout` at `0x18008610a`
- `USER32!SendMessageW` at `0x180085f7b`
- `USER32!SendMessageW` at `0x180085f9a`
- `USER32!SendMessageW` at `0x18008606d`
- `USER32!SendMessageW` at `0x180086083`
- `USER32!SendMessageW` at `0x1800860b7`
- `USER32!SendMessageW` at `0x1800860d3`
- `USER32!SendMessageW` at `0x180085f7b`
- `USER32!SendMessageW` at `0x180085f9a`
- `USER32!SendMessageW` at `0x18008606d`
- `USER32!SendMessageW` at `0x180086083`
- `USER32!SendMessageW` at `0x1800860b7`
- `USER32!SendMessageW` at `0x1800860d3`
- `USER32!GetSysColor` at `0x180085f1a`
- `USER32!GetSysColor` at `0x180085f37`
- `USER32!GetSysColor` at `0x180085f51`
- `USER32!GetSysColor` at `0x180085f1a`
- `USER32!GetSysColor` at `0x180085f37`
- `USER32!GetSysColor` at `0x180085f51`
- `MSIMG32!AlphaBlend` at `0x180086190`
- `MSIMG32!AlphaBlend` at `0x180086190`

## pseudocode

```c
void __fastcall CFmtBar::ComboBox_WMDrawItem(CFmtBar *this, struct tagDRAWITEMSTRUCT *a2)
{
  int itemData; // r14d
  bool v5; // zf
  HDC hDC; // rbx
  COLORREF v7; // eax
  COLORREF v8; // eax
  int v9; // ecx
  COLORREF SysColor; // eax
  COLORREF v11; // eax
  COLORREF v12; // eax
  UINT itemID; // esi
  HWND hwndItem; // r15
  LRESULT v15; // rax
  __int64 v16; // rsi
  __int64 c; // rax
  RECT *p_rcItem; // r15
  WPARAM v19; // r8
  HDC CompatibleDC; // rax
  HDC v21; // rsi
  void *v22; // rdx
  HGDIOBJ v23; // r12
  DWORD v24; // eax
  int v25; // r8d
  COLORREF color; // [rsp+64h] [rbp-9Ch]
  COLORREF v27; // [rsp+68h] [rbp-98h]
  struct tagSIZE psizl; // [rsp+70h] [rbp-90h] BYREF
  LPARAM v29; // [rsp+80h] [rbp-80h] BYREF
  HWND v30; // [rsp+88h] [rbp-78h]
  HWND v31; // [rsp+90h] [rbp-70h]
  LPARAM *v32; // [rsp+B0h] [rbp-50h]
  LPARAM v33[2]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR lParam[48]; // [rsp+E0h] [rbp-20h] BYREF

  itemData = a2->itemData;
  psizl = 0;
  memset_0(&v29, 0, 0x48u);
  v5 = (a2->itemState & 1) == 0;
  hDC = a2->hDC;
  *(_OWORD *)v33 = 0;
  if ( v5 )
  {
    SysColor = GetSysColor(5);
    v8 = SetBkColor(hDC, SysColor);
    v9 = 8;
  }
  else
  {
    v7 = GetSysColor(13);
    v8 = SetBkColor(hDC, v7);
    v9 = 14;
  }
  v27 = v8;
  v11 = GetSysColor(v9);
  v12 = SetTextColor(hDC, v11);
  itemID = a2->itemID;
  hwndItem = a2->hwndItem;
  color = v12;
  if ( (unsigned __int64)SendMessageW(hwndItem, 0x149u, itemID, 0) <= 0x29 )
  {
    v15 = SendMessageW(hwndItem, 0x148u, itemID, (LPARAM)lParam);
    v16 = -1;
    if ( v15 != -1 )
    {
      c = -1;
      do
        ++c;
      while ( lParam[c] );
      p_rcItem = &a2->rcItem;
      ExtTextOutW(hDC, a2->rcItem.left + 20, a2->rcItem.top, 2u, &a2->rcItem, lParam, c, 0);
      if ( (a2->itemState & 1) == 0 )
        goto LABEL_13;
      do
        ++v16;
      while ( lParam[v16] );
      if ( GetTextExtentPoint32W(hDC, lParam, v16, &psizl) && psizl.cx + 20 >= a2->rcItem.right )
      {
        memset_0(&v29, 0, 0x48u);
        v30 = (HWND)*((_QWORD *)this + 5);
        v31 = v30;
        v32 = (LPARAM *)lParam;
        LODWORD(v29) = 72;
        SendMessageW(v30, 0x152u, 0, (LPARAM)v33);
        SendMessageW(*((HWND *)this + 8), 0x40Cu, 0, (LPARAM)&v29);
        SendMessageW(
          *((HWND *)this + 8),
          0x412u,
          0,
          (unsigned __int16)(LOWORD(p_rcItem->left) + LOWORD(v33[0]) + 20)
        | ((unsigned __int64)(unsigned __int16)(LOWORD(a2->rcItem.top) + WORD2(v33[0])) << 16));
        v19 = 1;
      }
      else
      {
LABEL_13:
        v19 = 0;
      }
      SendMessageW(*((HWND *)this + 8), 0x411u, v19, (LPARAM)&v29);
      CompatibleDC = CreateCompatibleDC(hDC);
      v21 = CompatibleDC;
      if ( CompatibleDC )
      {
        v22 = (void *)*((_QWORD *)this + 14);
        if ( !v22 )
        {
LABEL_22:
          DeleteDC(v21);
          goto LABEL_23;
        }
        v23 = SelectObject(CompatibleDC, v22);
        v24 = GetLayout(hDC) & 1;
        if ( (itemData & 4) != 0 )
        {
          v25 = -(v24 != 0);
        }
        else
        {
          if ( (itemData & 0x4002) != 0x4002 )
          {
LABEL_21:
            SelectObject(v21, v23);
            goto LABEL_22;
          }
          v25 = -(v24 == 0);
        }
        AlphaBlend(
          hDC,
          p_rcItem->left,
          a2->rcItem.top + (a2->rcItem.bottom - a2->rcItem.top - 12) / 2,
          20,
          12,
          v21,
          v25 & 0x14,
          0,
          20,
          12,
          (BLENDFUNCTION)33488896);
        goto LABEL_21;
      }
    }
  }
LABEL_23:
  SetTextColor(hDC, color);
  SetBkColor(hDC, v27);
}

```

## disassembly

```asm
0x180085eb8  mov     [rsp-8+arg_10], rbx
0x180085ebd  push    rbp
0x180085ebe  push    rsi
0x180085ebf  push    rdi
0x180085ec0  push    r12
0x180085ec2  push    r13
0x180085ec4  push    r14
0x180085ec6  push    r15
0x180085ec8  lea     rbp, [rsp-50h]
0x180085ecd  sub     rsp, 150h
0x180085ed4  mov     rax, cs:__security_cookie
0x180085edb  xor     rax, rsp
0x180085ede  mov     [rbp+80h+var_40], rax
0x180085ee2  mov     r14d, [rdx+38h]
0x180085ee6  xor     r12d, r12d
0x180085ee9  mov     rdi, rdx
0x180085eec  mov     qword ptr [rsp+180h+psizl.cx], r12
0x180085ef1  mov     r13, rcx
0x180085ef4  xor     edx, edx; Val
0x180085ef6  lea     rcx, [rbp+80h+var_100]; void *
0x180085efa  lea     r8d, [r12+48h]; Size
0x180085eff  call    memset_0
0x180085f04  test    byte ptr [rdi+10h], 1
0x180085f08  xorps   xmm0, xmm0
0x180085f0b  mov     rbx, [rdi+20h]
0x180085f0f  movups  xmmword ptr [rbp+80h+var_B0], xmm0
0x180085f13  jz      short loc_180085F32
0x180085f15  lea     ecx, [r12+0Dh]; nIndex
0x180085f1a  call    cs:__imp_GetSysColor
0x180085f20  mov     edx, eax; color
0x180085f22  mov     rcx, rbx; hdc
0x180085f25  call    cs:__imp_SetBkColor
0x180085f2b  lea     ecx, [r12+0Eh]
0x180085f30  jmp     short loc_180085F4D
0x180085f32  mov     ecx, 5; nIndex
0x180085f37  call    cs:__imp_GetSysColor
0x180085f3d  mov     edx, eax; color
0x180085f3f  mov     rcx, rbx; hdc
0x180085f42  call    cs:__imp_SetBkColor
0x180085f48  mov     ecx, 8; nIndex
0x180085f4d  mov     [rsp+180h+var_118], eax
0x180085f51  call    cs:__imp_GetSysColor
0x180085f57  mov     edx, eax; color
0x180085f59  mov     rcx, rbx; hdc
0x180085f5c  call    cs:__imp_SetTextColor
0x180085f62  mov     esi, [rdi+8]
0x180085f65  xor     r9d, r9d; lParam
0x180085f68  mov     r15, [rdi+18h]
0x180085f6c  mov     r8d, esi; wParam
0x180085f6f  mov     rcx, r15; hWnd
0x180085f72  mov     [rsp+180h+color], eax
0x180085f76  mov     edx, 149h; Msg
0x180085f7b  call    cs:__imp_SendMessageW
0x180085f81  cmp     rax, 29h ; ')'
0x180085f85  ja      loc_1800861AB
0x180085f8b  lea     r9, [rbp+80h+lParam]; lParam
0x180085f8f  mov     r8d, esi; wParam
0x180085f92  mov     edx, 148h; Msg
0x180085f97  mov     rcx, r15; hWnd
0x180085f9a  call    cs:__imp_SendMessageW
0x180085fa0  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180085fa4  cmp     rax, rsi
0x180085fa7  jz      loc_1800861AB
0x180085fad  lea     rcx, [rbp+80h+lParam]
0x180085fb1  mov     rax, rsi
0x180085fb4  inc     rax
0x180085fb7  cmp     [rcx+rax*2], r12w
0x180085fbc  jnz     short loc_180085FB4
0x180085fbe  mov     r8d, [rdi+2Ch]; y
0x180085fc2  lea     r15, [rdi+28h]
0x180085fc6  mov     edx, [r15]
0x180085fc9  mov     r9d, 2; options
0x180085fcf  mov     [rsp+180h+lpDx], r12; lpDx
0x180085fd4  add     edx, 14h; x
0x180085fd7  mov     [rsp+180h+c], eax; c
0x180085fdb  mov     rcx, rbx; hdc
0x180085fde  lea     rax, [rbp+80h+lParam]
0x180085fe2  mov     [rsp+180h+lpString], rax; lpString
0x180085fe7  mov     [rsp+180h+lprect], r15; lprect
0x180085fec  call    cs:__imp_ExtTextOutW
0x180085ff2  test    byte ptr [rdi+10h], 1
0x180085ff6  jz      loc_1800860C3
0x180085ffc  lea     rax, [rbp+80h+lParam]
0x180086000  inc     rsi
0x180086003  cmp     [rax+rsi*2], r12w
0x180086008  jnz     short loc_180086000
0x18008600a  mov     r8d, esi; c
0x18008600d  lea     r9, [rsp+180h+psizl]; psizl
0x180086012  lea     rdx, [rbp+80h+lParam]; lpString
0x180086016  mov     rcx, rbx; hdc
0x180086019  call    cs:__imp_GetTextExtentPoint32W
0x18008601f  test    eax, eax
0x180086021  jz      loc_1800860C3
0x180086027  mov     eax, [rsp+180h+psizl.cx]
0x18008602b  add     eax, 14h
0x18008602e  cmp     eax, [rdi+30h]
0x180086031  jl      loc_1800860C3
0x180086037  mov     esi, 48h ; 'H'
0x18008603c  lea     rcx, [rbp+80h+var_100]; void *
0x180086040  mov     r8d, esi; Size
0x180086043  xor     edx, edx; Val
0x180086045  call    memset_0
0x18008604a  mov     rcx, [r13+28h]; hWnd
0x18008604e  lea     rax, [rbp+80h+lParam]
0x180086052  lea     r9, [rbp+80h+var_B0]; lParam
0x180086056  mov     [rbp+80h+var_F8], rcx
0x18008605a  xor     r8d, r8d; wParam
0x18008605d  mov     [rbp+80h+var_F0], rcx
0x180086061  mov     edx, 152h; Msg
0x180086066  mov     [rbp+80h+var_D0], rax
0x18008606a  mov     dword ptr [rbp+80h+var_100], esi
0x18008606d  call    cs:__imp_SendMessageW
0x180086073  mov     rcx, [r13+40h]; hWnd
0x180086077  lea     r9, [rbp+80h+var_100]; lParam
0x18008607b  xor     r8d, r8d; wParam
0x18008607e  mov     edx, 40Ch; Msg
0x180086083  call    cs:__imp_SendMessageW
0x180086089  movzx   eax, word ptr [rbp+80h+var_B0+4]
0x18008608d  xor     r8d, r8d; wParam
0x180086090  add     ax, [rdi+2Ch]
0x180086094  mov     edx, 412h; Msg
0x180086099  mov     rcx, [r13+40h]; hWnd
0x18008609d  movzx   r9d, ax
0x1800860a1  movzx   eax, word ptr [rbp+80h+var_B0]
0x1800860a5  add     ax, 14h
0x1800860a9  shl     r9, 10h
0x1800860ad  add     ax, [r15]
0x1800860b1  movzx   eax, ax
0x1800860b4  or      r9, rax; lParam
0x1800860b7  call    cs:__imp_SendMessageW
0x1800860bd  lea     r8d, [rsi-47h]
0x1800860c1  jmp     short loc_1800860C6
0x1800860c3  xor     r8d, r8d; wParam
0x1800860c6  mov     rcx, [r13+40h]; hWnd
0x1800860ca  lea     r9, [rbp+80h+var_100]; lParam
0x1800860ce  mov     edx, 411h; Msg
0x1800860d3  call    cs:__imp_SendMessageW
0x1800860d9  mov     rcx, rbx; hdc
0x1800860dc  call    cs:__imp_CreateCompatibleDC
0x1800860e2  mov     rsi, rax
0x1800860e5  test    rax, rax
0x1800860e8  jz      loc_1800861AB
0x1800860ee  mov     rdx, [r13+70h]; h
0x1800860f2  test    rdx, rdx
0x1800860f5  jz      loc_1800861A2
0x1800860fb  mov     rcx, rax; hdc
0x1800860fe  call    cs:__imp_SelectObject
0x180086104  mov     rcx, rbx; hdc
0x180086107  mov     r12, rax
0x18008610a  call    cs:__imp_GetLayout
0x180086110  and     eax, 1
0x180086113  test    r14b, 4
0x180086117  jz      short loc_180086120
0x180086119  neg     eax
0x18008611b  sbb     r8d, r8d
0x18008611e  jmp     short loc_180086135
0x180086120  mov     ecx, 4002h
0x180086125  and     r14d, ecx
0x180086128  cmp     r14d, ecx
0x18008612b  jnz     short loc_180086196
0x18008612d  neg     eax
0x18008612f  sbb     r8d, r8d
0x180086132  not     r8d
0x180086135  mov     eax, [rdi+34h]
0x180086138  xor     r11d, r11d
0x18008613b  sub     eax, [rdi+2Ch]
0x18008613e  and     r8d, 14h
0x180086142  mov     dword ptr [rsp+180h+var_120.BlendOp], 1FF0000h
0x18008614a  lea     r10d, [r11+0Ch]
0x18008614e  sub     eax, r10d
0x180086151  lea     ecx, [r11+2]
0x180086155  cdq
0x180086156  idiv    ecx
0x180086158  mov     ecx, dword ptr [rsp+180h+var_120.BlendOp]
0x18008615c  add     eax, [rdi+2Ch]
0x18008615f  mov     edx, [r15]; xoriginDest
0x180086162  mov     dword ptr [rsp+180h+ftn.BlendOp], ecx; ftn
0x180086166  lea     ecx, [r11+14h]
0x18008616a  mov     [rsp+180h+hSrc], r10d; hSrc
0x18008616f  mov     r9d, ecx; wDest
0x180086172  mov     [rsp+180h+wSrc], ecx; wSrc
0x180086176  mov     rcx, rbx; hdcDest
0x180086179  mov     dword ptr [rsp+180h+lpDx], r11d; yoriginSrc
0x18008617e  mov     [rsp+180h+c], r8d; xoriginSrc
0x180086183  mov     r8d, eax; yoriginDest
0x180086186  mov     [rsp+180h+lpString], rsi; hdcSrc
0x18008618b  mov     dword ptr [rsp+180h+lprect], r10d; hDest
0x180086190  call    cs:__imp_AlphaBlend
0x180086196  mov     rdx, r12; h
0x180086199  mov     rcx, rsi; hdc
0x18008619c  call    cs:__imp_SelectObject
0x1800861a2  mov     rcx, rsi; hdc
0x1800861a5  call    cs:__imp_DeleteDC
0x1800861ab  mov     edx, [rsp+180h+color]; color
0x1800861af  mov     rcx, rbx; hdc
0x1800861b2  call    cs:__imp_SetTextColor
0x1800861b8  mov     edx, [rsp+180h+var_118]; color
0x1800861bc  mov     rcx, rbx; hdc
0x1800861bf  call    cs:__imp_SetBkColor
0x1800861c5  mov     rcx, [rbp+80h+var_40]
0x1800861c9  xor     rcx, rsp; StackCookie
0x1800861cc  call    __security_check_cookie
0x1800861d1  mov     rbx, [rsp+180h+arg_10]
0x1800861d9  add     rsp, 150h
0x1800861e0  pop     r15
0x1800861e2  pop     r14
0x1800861e4  pop     r13
0x1800861e6  pop     r12
0x1800861e8  pop     rdi
0x1800861e9  pop     rsi
0x1800861ea  pop     rbp
0x1800861eb  retn
```
