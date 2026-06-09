# CToolTipsMgr::Render(HDC__ *)

- ea: `0x180073438`
- end: `0x180073704`
- name: `?Render@CToolTipsMgr@@AEAAHPEAUHDC__@@@Z`
- size: `716`
- prototype: `__int64 __fastcall(CToolTipsMgr *__hidden this, HDC)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18006fd80`
- `0x1800733b0`

## callees

- `0x18004f420`
- `0x1800725b4`
- `0x180073340`
- `0x180073438`
- `0x180074068`
- `0x180074b48`
- `0x180074c1c`
- `0x180114520`
- `0x180114ebc`
- `0x1801d1010`

## import_xrefs

- `GDI32!CreateSolidBrush` at `0x1800736ce`
- `GDI32!CreateSolidBrush` at `0x1800736ce`
- `GDI32!DeleteObject` at `0x1800736f0`
- `GDI32!DeleteObject` at `0x1800736f9`
- `GDI32!DeleteObject` at `0x1800736f0`
- `GDI32!DeleteObject` at `0x1800736f9`
- `GDI32!SetBkMode` at `0x1800735a2`
- `GDI32!SetBkMode` at `0x1800735a2`
- `GDI32!SetTextColor` at `0x1800734c0`
- `GDI32!SetTextColor` at `0x1800734c0`
- `GDI32!SelectObject` at `0x1800734a3`
- `GDI32!SelectObject` at `0x1800734a3`
- `GDI32!CreateRectRgn` at `0x18007362e`
- `GDI32!CreateRectRgn` at `0x18007362e`
- `GDI32!FrameRgn` at `0x1800736e7`
- `GDI32!FrameRgn` at `0x1800736e7`
- `USER32!OffsetRect` at `0x18007369a`
- `USER32!OffsetRect` at `0x18007369a`
- `USER32!GetClientRect` at `0x1800734b1`
- `USER32!GetClientRect` at `0x1800734b1`
- `USER32!GetWindowRgn` at `0x1800736be`
- `USER32!GetWindowRgn` at `0x1800736be`

## pseudocode

```c
__int64 __fastcall CToolTipsMgr::Render(CToolTipsMgr *this, HDC a2)
{
  unsigned int v2; // esi
  int v5; // ebx
  LONG v6; // eax
  LONG v7; // ecx
  LONG v8; // eax
  int v9; // ebx
  __int64 v10; // rcx
  int v11; // r12d
  unsigned int v13; // r9d
  struct IControlMarkup *CurToolBestMarkup; // rax
  HRGN RectRgn; // rax
  HRGN v16; // r14
  __int64 v17; // rcx
  HBRUSH SolidBrush; // rbx
  struct tagRECT v19; // [rsp+30h] [rbp-69h] BYREF
  _QWORD v20[2]; // [rsp+40h] [rbp-59h] BYREF
  int v21; // [rsp+50h] [rbp-49h]
  int v22; // [rsp+58h] [rbp-41h]
  HDC v23; // [rsp+60h] [rbp-39h]
  struct tagRECT rc; // [rsp+68h] [rbp-31h] BYREF
  unsigned int v25; // [rsp+90h] [rbp-9h]
  struct tagRECT Rect; // [rsp+A0h] [rbp+7h] BYREF
  struct tagRECT v27; // [rsp+B0h] [rbp+17h] BYREF

  v2 = 0;
  Rect = 0;
  if ( *((_QWORD *)this + 13) && !(unsigned int)CToolTipsMgr::SetCurToolDispInfo(this) )
  {
    memset_0(v20, 0, 0x58u);
    v5 = *((_DWORD *)this + 6);
    SelectObject(a2, *((HGDIOBJ *)this + 14));
    GetClientRect(*((HWND *)this + 1), &Rect);
    SetTextColor(a2, *((_DWORD *)this + 57));
    v2 = 1;
    v20[0] = *((_QWORD *)this + 1);
    v6 = Rect.right - *((_DWORD *)this + 63);
    v20[1] = *(_QWORD *)(*((_QWORD *)this + 13) + 16LL);
    rc.left = Rect.left + *((_DWORD *)this + 61);
    v7 = Rect.top + *((_DWORD *)this + 62);
    rc.right = v6;
    v8 = Rect.bottom - *((_DWORD *)this + 64);
    v21 = -12;
    v23 = a2;
    v22 = 1;
    rc.top = v7;
    rc.bottom = v8;
    v9 = v5 & 0x40;
    if ( v9 && (*((_BYTE *)this + 208) & 8) == 0 )
      OffsetRect(&rc, 0, *((_DWORD *)this + 69));
    v10 = *((_QWORD *)this + 13);
    v25 = *((_DWORD *)this + 60);
    v11 = SendNotifyEx(*(_QWORD *)(v10 + 8), -1, 0, v20, (*(_DWORD *)(v10 + 4) >> 6) & 1);
    if ( v11 != 4 )
    {
      v19 = Rect;
      CToolTipsMgr::DrawTipBackground(this, a2, &v19);
      SetBkMode(a2, 1);
      v13 = *((_DWORD *)this + 60);
      ++rc.bottom;
      ++rc.right;
      v27 = rc;
      if ( !(unsigned int)CToolTipsMgr::RenderTitledTip(this, a2, &v27, v13) )
      {
        CToolTipsMgr::SetThemeRenderFlags(this, v25);
        CurToolBestMarkup = CToolTipsMgr::GetCurToolBestMarkup(this);
        (*(void (__fastcall **)(struct IControlMarkup *, HDC, struct tagRECT *))(*(_QWORD *)CurToolBestMarkup + 144LL))(
          CurToolBestMarkup,
          a2,
          &v27);
      }
      if ( !*((_QWORD *)this + 36) || v9 && (*((_BYTE *)this + 208) & 0x40) == 0 )
      {
        RectRgn = CreateRectRgn(1, 1, 2, 2);
        v16 = RectRgn;
        if ( RectRgn )
        {
          if ( GetWindowRgn(*((HWND *)this + 1), RectRgn) )
          {
            SolidBrush = CreateSolidBrush(*((_DWORD *)this + 57));
            FrameRgn(a2, v16, SolidBrush, 1, 1);
            DeleteObject(SolidBrush);
          }
          DeleteObject(v16);
        }
      }
      if ( (v11 & 4) == 0 && (v11 & 0x10) != 0 )
      {
        v17 = *((_QWORD *)this + 13);
        ++v22;
        SendNotifyEx(*(_QWORD *)(v17 + 8), -1, 0, v20, (*(_DWORD *)(v17 + 4) >> 6) & 1);
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180073438  mov     [rsp-8+arg_10], rbx
0x18007343d  mov     [rsp-8+arg_18], rsi
0x180073442  push    rbp
0x180073443  push    rdi
0x180073444  push    r12
0x180073446  push    r14
0x180073448  push    r15
0x18007344a  lea     rbp, [rsp-37h]
0x18007344f  sub     rsp, 0D0h
0x180073456  mov     rax, cs:__security_cookie
0x18007345d  xor     rax, rsp
0x180073460  mov     [rbp+57h+var_30], rax
0x180073464  xor     esi, esi
0x180073466  xorps   xmm0, xmm0
0x180073469  mov     r15, rdx
0x18007346c  mov     rdi, rcx
0x18007346f  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x180073473  cmp     [rcx+68h], rsi
0x180073477  jz      loc_18007355B
0x18007347d  call    ?SetCurToolDispInfo@CToolTipsMgr@@AEAAJXZ; CToolTipsMgr::SetCurToolDispInfo(void)
0x180073482  test    eax, eax
0x180073484  jnz     loc_18007355B
0x18007348a  xor     edx, edx; Val
0x18007348c  lea     r8d, [rsi+58h]; Size
0x180073490  lea     rcx, [rbp+57h+var_B0]; void *
0x180073494  call    memset_0
0x180073499  mov     rdx, [rdi+70h]; h
0x18007349d  mov     rcx, r15; hdc
0x1800734a0  mov     ebx, [rdi+18h]
0x1800734a3  call    cs:__imp_SelectObject
0x1800734a9  mov     rcx, [rdi+8]; hWnd
0x1800734ad  lea     rdx, [rbp+57h+Rect]; lpRect
0x1800734b1  call    cs:__imp_GetClientRect
0x1800734b7  mov     edx, [rdi+0E4h]; color
0x1800734bd  mov     rcx, r15; hdc
0x1800734c0  call    cs:__imp_SetTextColor
0x1800734c6  mov     rax, [rdi+8]
0x1800734ca  mov     esi, 1
0x1800734cf  mov     [rbp+57h+var_B0], rax
0x1800734d3  mov     rax, [rdi+68h]
0x1800734d7  mov     rcx, [rax+10h]
0x1800734db  mov     eax, [rbp+57h+Rect.right]
0x1800734de  sub     eax, [rdi+0FCh]
0x1800734e4  mov     [rbp+57h+var_A8], rcx
0x1800734e8  mov     ecx, [rdi+0F4h]
0x1800734ee  add     ecx, [rbp+57h+Rect.left]
0x1800734f1  mov     [rbp+57h+rc.left], ecx
0x1800734f4  mov     ecx, [rdi+0F8h]
0x1800734fa  add     ecx, [rbp+57h+Rect.top]
0x1800734fd  mov     [rbp+57h+rc.right], eax
0x180073500  mov     eax, [rbp+57h+Rect.bottom]
0x180073503  sub     eax, [rdi+100h]
0x180073509  mov     [rbp+57h+var_A0], 0FFFFFFF4h
0x180073510  mov     [rbp+57h+var_90], r15
0x180073514  mov     [rbp+57h+var_98], esi
0x180073517  mov     [rbp+57h+rc.top], ecx
0x18007351a  mov     [rbp+57h+rc.bottom], eax
0x18007351d  and     ebx, 40h
0x180073520  jnz     loc_180073680
0x180073526  mov     rcx, [rdi+68h]
0x18007352a  lea     r9, [rbp+57h+var_B0]
0x18007352e  mov     eax, [rdi+0F0h]
0x180073534  xor     r8d, r8d
0x180073537  mov     [rbp+57h+var_60], eax
0x18007353a  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18007353e  mov     eax, [rcx+4]
0x180073541  mov     rcx, [rcx+8]
0x180073545  shr     eax, 6
0x180073548  and     eax, esi
0x18007354a  mov     [rsp+0F0h+h], eax
0x18007354e  call    SendNotifyEx
0x180073553  mov     r12, rax
0x180073556  cmp     eax, 4
0x180073559  jnz     short loc_180073585
0x18007355b  mov     eax, esi
0x18007355d  mov     rcx, [rbp+57h+var_30]
0x180073561  xor     rcx, rsp; StackCookie
0x180073564  call    __security_check_cookie
0x180073569  lea     r11, [rsp+0F0h+var_20]
0x180073571  mov     rbx, [r11+40h]
0x180073575  mov     rsi, [r11+48h]
0x180073579  mov     rsp, r11
0x18007357c  pop     r15
0x18007357e  pop     r14
0x180073580  pop     r12
0x180073582  pop     rdi
0x180073583  pop     rbp
0x180073584  retn
0x180073585  movaps  xmm0, xmmword ptr [rbp+57h+Rect.left]
0x180073589  lea     r8, [rbp+57h+var_C0]; struct tagRECT
0x18007358d  mov     rdx, r15; HDC
0x180073590  movdqa  xmmword ptr [rbp+57h+var_C0.left], xmm0
0x180073595  mov     rcx, rdi; this
0x180073598  call    ?DrawTipBackground@CToolTipsMgr@@AEAAXPEAUHDC__@@UtagRECT@@@Z; CToolTipsMgr::DrawTipBackground(HDC__ *,tagRECT)
0x18007359d  mov     edx, esi; mode
0x18007359f  mov     rcx, r15; hdc
0x1800735a2  call    cs:__imp_SetBkMode
0x1800735a8  mov     edx, [rbp+57h+rc.bottom]
0x1800735ab  lea     r8, [rbp+57h+var_40]; struct tagRECT *
0x1800735af  mov     ecx, [rbp+57h+rc.right]
0x1800735b2  add     edx, esi
0x1800735b4  mov     eax, [rbp+57h+rc.left]
0x1800735b7  add     ecx, esi
0x1800735b9  mov     r9d, [rdi+0F0h]; unsigned int
0x1800735c0  mov     [rbp+57h+rc.bottom], edx
0x1800735c3  mov     [rbp+57h+rc.right], ecx
0x1800735c6  mov     [rbp+57h+var_40.right], ecx
0x1800735c9  mov     rcx, rdi; this
0x1800735cc  mov     [rbp+57h+var_40.bottom], edx
0x1800735cf  mov     rdx, r15; HDC
0x1800735d2  mov     [rbp+57h+var_40.left], eax
0x1800735d5  mov     eax, [rbp+57h+rc.top]
0x1800735d8  mov     [rbp+57h+var_40.top], eax
0x1800735db  call    ?RenderTitledTip@CToolTipsMgr@@AEAAHPEAUHDC__@@PEAUtagRECT@@I@Z; CToolTipsMgr::RenderTitledTip(HDC__ *,tagRECT *,uint)
0x1800735e0  test    eax, eax
0x1800735e2  jnz     short loc_180073613
0x1800735e4  mov     edx, [rbp+57h+var_60]; unsigned int
0x1800735e7  mov     rcx, rdi; this
0x1800735ea  call    ?SetThemeRenderFlags@CToolTipsMgr@@AEAAXK@Z; CToolTipsMgr::SetThemeRenderFlags(ulong)
0x1800735ef  mov     rcx, rdi; this
0x1800735f2  call    ?GetCurToolBestMarkup@CToolTipsMgr@@AEAAPEAUIControlMarkup@@XZ; CToolTipsMgr::GetCurToolBestMarkup(void)
0x1800735f7  mov     r9, rax
0x1800735fa  lea     r8, [rbp+57h+var_40]
0x1800735fe  mov     rdx, r15
0x180073601  mov     rcx, [rax]
0x180073604  mov     rax, [rcx+90h]
0x18007360b  mov     rcx, r9
0x18007360e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073613  cmp     qword ptr [rdi+120h], 0
0x18007361b  jnz     loc_1800736A5
0x180073621  mov     r8d, 2; x2
0x180073627  mov     edx, esi; y1
0x180073629  mov     r9d, r8d; y2
0x18007362c  mov     ecx, esi; x1
0x18007362e  call    cs:__imp_CreateRectRgn
0x180073634  mov     r14, rax
0x180073637  test    rax, rax
0x18007363a  jnz     short loc_1800736B7
0x18007363c  test    r12b, 4
0x180073640  jnz     loc_18007355B
0x180073646  test    r12b, 10h
0x18007364a  jz      loc_18007355B
0x180073650  mov     rcx, [rdi+68h]
0x180073654  lea     r9, [rbp+57h+var_B0]
0x180073658  add     [rbp+57h+var_98], esi
0x18007365b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18007365f  mov     r8d, [rcx+4]
0x180073663  mov     rcx, [rcx+8]
0x180073667  shr     r8d, 6
0x18007366b  and     r8d, esi
0x18007366e  mov     [rsp+0F0h+h], r8d
0x180073673  xor     r8d, r8d
0x180073676  call    SendNotifyEx
0x18007367b  jmp     loc_18007355B
0x180073680  test    byte ptr [rdi+0D0h], 8
0x180073687  jnz     loc_180073526
0x18007368d  mov     r8d, [rdi+114h]; dy
0x180073694  lea     rcx, [rbp+57h+rc]; lprc
0x180073698  xor     edx, edx; dx
0x18007369a  call    cs:__imp_OffsetRect
0x1800736a0  jmp     loc_180073526
0x1800736a5  test    ebx, ebx
0x1800736a7  jz      short loc_18007363C
0x1800736a9  test    byte ptr [rdi+0D0h], 40h
0x1800736b0  jnz     short loc_18007363C
0x1800736b2  jmp     loc_180073621
0x1800736b7  mov     rcx, [rdi+8]; hWnd
0x1800736bb  mov     rdx, r14; hRgn
0x1800736be  call    cs:__imp_GetWindowRgn
0x1800736c4  test    eax, eax
0x1800736c6  jz      short loc_1800736F6
0x1800736c8  mov     ecx, [rdi+0E4h]; color
0x1800736ce  call    cs:__imp_CreateSolidBrush
0x1800736d4  mov     r9d, esi; w
0x1800736d7  mov     [rsp+0F0h+h], esi; h
0x1800736db  mov     r8, rax; hbr
0x1800736de  mov     rdx, r14; hrgn
0x1800736e1  mov     rcx, r15; hdc
0x1800736e4  mov     rbx, rax
0x1800736e7  call    cs:__imp_FrameRgn
0x1800736ed  mov     rcx, rbx; ho
0x1800736f0  call    cs:__imp_DeleteObject
0x1800736f6  mov     rcx, r14; ho
0x1800736f9  call    cs:__imp_DeleteObject
0x1800736ff  jmp     loc_18007363C
```
