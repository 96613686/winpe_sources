# CFmtBar::WndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180087fa0`
- end: `0x1800882d8`
- name: `?WndProc@CFmtBar@@AEAA_JPEAUHWND__@@I_K_J@Z`
- size: `824`
- prototype: `__int64 __fastcall(CFmtBar *__hidden this, HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800864f0`

## callees

- `0x1800259a4`
- `0x1800859fc`
- `0x180085eb8`
- `0x1800869a4`
- `0x180087334`
- `0x1800877b4`
- `0x180087d80`
- `0x180087fa0`
- `0x1800cc9ba`
- `0x1800cca00`

## import_xrefs

- `MSOERT2!UpdateRebarBandColors` at `0x180088046`
- `MSOERT2!UpdateRebarBandColors` at `0x180088046`
- `USER32!SendMessageA` at `0x180088058`
- `USER32!SendMessageA` at `0x180088058`
- `USER32!SetWindowLongPtrA` at `0x180088153`
- `USER32!SetWindowLongPtrA` at `0x1800881a3`
- `USER32!SetWindowLongPtrA` at `0x1800881da`
- `USER32!SetWindowLongPtrA` at `0x180088203`
- `USER32!SetWindowLongPtrA` at `0x180088295`
- `USER32!SetWindowLongPtrA` at `0x180088153`
- `USER32!SetWindowLongPtrA` at `0x1800881a3`
- `USER32!SetWindowLongPtrA` at `0x1800881da`
- `USER32!SetWindowLongPtrA` at `0x180088203`
- `USER32!SetWindowLongPtrA` at `0x180088295`
- `USER32!DestroyWindow` at `0x18008821e`
- `USER32!DestroyWindow` at `0x18008821e`
- `USER32!GetClientRect` at `0x1800880b0`
- `USER32!GetClientRect` at `0x1800880f7`
- `USER32!GetClientRect` at `0x1800880b0`
- `USER32!GetClientRect` at `0x1800880f7`
- `USER32!DefWindowProcA` at `0x180088069`
- `USER32!DefWindowProcA` at `0x180088069`
- `USER32!SetWindowPos` at `0x180088133`
- `USER32!SetWindowPos` at `0x180088133`
- `USER32!BeginPaint` at `0x180088097`
- `USER32!BeginPaint` at `0x180088097`
- `USER32!EndPaint` at `0x1800880dd`
- `USER32!EndPaint` at `0x1800880dd`
- `USER32!DrawEdge` at `0x1800880d0`
- `USER32!DrawEdge` at `0x1800880d0`
- `USER32!GetWindow` at `0x18008817a`
- `USER32!GetWindow` at `0x180088192`
- `USER32!GetWindow` at `0x1800881b2`
- `USER32!GetWindow` at `0x18008817a`
- `USER32!GetWindow` at `0x180088192`
- `USER32!GetWindow` at `0x1800881b2`
- `USER32!RemovePropA` at `0x180088164`
- `USER32!RemovePropA` at `0x1800881c2`
- `USER32!RemovePropA` at `0x1800881eb`
- `USER32!RemovePropA` at `0x180088214`
- `USER32!RemovePropA` at `0x180088164`
- `USER32!RemovePropA` at `0x1800881c2`
- `USER32!RemovePropA` at `0x1800881eb`
- `USER32!RemovePropA` at `0x180088214`

## pseudocode

```c
LRESULT __fastcall CFmtBar::WndProc(CFmtBar *this, HWND hWnd, UINT Msg, WPARAM wParam, struct tagNMHDR *lParam)
{
  HDC v10; // rbx
  HWND v11; // rcx
  LONG_PTR v12; // r8
  LONG_PTR v13; // rbx
  HWND Window; // rax
  HWND v15; // rax
  LONG_PTR v16; // r8
  LONG_PTR v17; // r8
  struct tagRECT Rect; // [rsp+40h] [rbp-51h] BYREF
  struct tagPAINTSTRUCT Paint; // [rsp+50h] [rbp-41h] BYREF

  if ( Msg > 0x2C )
  {
    switch ( Msg )
    {
      case 0x4Eu:
        CFmtBar::WMNotify(this, (unsigned __int64)hWnd, lParam);
        break;
      case 0x7Eu:
LABEL_14:
        SendMessageA(*((HWND *)this + 7), Msg, wParam, (LPARAM)lParam);
        return DefWindowProcA(hWnd, Msg, wParam, (LPARAM)lParam);
      case 0x82u:
        SetWindowLongPtrA(*((HWND *)this + 3), -21, 0);
        *((_QWORD *)this + 3) = 0;
        CFmtBar::Release(this);
        return DefWindowProcA(hWnd, Msg, wParam, (LPARAM)lParam);
      case 0x111u:
        if ( (unsigned int)CFmtBar::OnWMCommand(this, hWnd, (unsigned __int16)wParam, WORD1(wParam)) )
          return DefWindowProcA(hWnd, Msg, wParam, (LPARAM)lParam);
        break;
      case 0x30Fu:
      case 0x311u:
        goto LABEL_14;
      default:
        return DefWindowProcA(hWnd, Msg, wParam, (LPARAM)lParam);
    }
  }
  else
  {
    switch ( Msg )
    {
      case 0x2Cu:
        CFmtBar::OnMeasureItem(this, (struct tagMEASUREITEMSTRUCT *)lParam);
        return DefWindowProcA(hWnd, Msg, wParam, (LPARAM)lParam);
      case 2u:
        v12 = *((_QWORD *)this + 21);
        if ( v12 )
        {
          SetWindowLongPtrA(*((HWND *)this + 4), -4, v12);
          RemovePropA(*((HWND *)this + 4), "OE_This");
        }
        if ( *((_QWORD *)this + 11) && GetWindow(*((HWND *)this + 5), 5u) )
        {
          v13 = *((_QWORD *)this + 11);
          Window = GetWindow(*((HWND *)this + 5), 5u);
          SetWindowLongPtrA(Window, -4, v13);
          v15 = GetWindow(*((HWND *)this + 5), 5u);
          RemovePropA(v15, "OE_This");
        }
        v16 = *((_QWORD *)this + 12);
        if ( v16 )
        {
          SetWindowLongPtrA(*((HWND *)this + 5), -4, v16);
          RemovePropA(*((HWND *)this + 5), "OE_This");
        }
        v17 = *((_QWORD *)this + 13);
        if ( v17 )
        {
          SetWindowLongPtrA(*((HWND *)this + 6), -4, v17);
          RemovePropA(*((HWND *)this + 6), "OE_This");
        }
        DestroyWindow(*((HWND *)this + 8));
        *((_QWORD *)this + 8) = 0;
        return DefWindowProcA(hWnd, Msg, wParam, (LPARAM)lParam);
      case 5u:
        v11 = (HWND)*((_QWORD *)this + 7);
        Rect = 0;
        GetClientRect(v11, &Rect);
        if ( Rect.right != (unsigned __int16)lParam )
          SetWindowPos(*((HWND *)this + 7), 0, 0, 2, (unsigned __int16)lParam, WORD1(lParam), 0x14u);
        return DefWindowProcA(hWnd, Msg, wParam, (LPARAM)lParam);
    }
    if ( Msg != 15 )
    {
      if ( Msg == 21 )
      {
        CFmtBar::_SetToolbarBitmaps(this);
        UpdateRebarBandColors(*((_QWORD *)this + 7));
      }
      else if ( Msg != 26 )
      {
        if ( Msg == 43 )
        {
          if ( LODWORD(lParam->hwndFrom) == 1 )
          {
            Color_WMDrawItem(*((HWND *)this + 3), (struct tagDRAWITEMSTRUCT *)lParam, *((HMENU *)this + 9));
          }
          else if ( LODWORD(lParam->hwndFrom) == 3 )
          {
            CFmtBar::ComboBox_WMDrawItem(this, (struct tagDRAWITEMSTRUCT *)lParam);
          }
        }
        return DefWindowProcA(hWnd, Msg, wParam, (LPARAM)lParam);
      }
      goto LABEL_14;
    }
    if ( (*((_BYTE *)this + 120) & 4) == 0 )
      return DefWindowProcA(hWnd, Msg, wParam, (LPARAM)lParam);
    memset_0(&Paint, 0, sizeof(Paint));
    Rect = 0;
    v10 = BeginPaint(hWnd, &Paint);
    if ( v10 )
    {
      GetClientRect(hWnd, &Rect);
      Rect.top = Rect.bottom - 3;
      DrawEdge(v10, &Rect, 1u, 8u);
      EndPaint(hWnd, &Paint);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180087fa0  push    rbp
0x180087fa2  push    rbx
0x180087fa3  push    rsi
0x180087fa4  push    rdi
0x180087fa5  push    r12
0x180087fa7  push    r14
0x180087fa9  push    r15
0x180087fab  lea     rbp, [rsp-1Fh]
0x180087fb0  sub     rsp, 0B0h
0x180087fb7  mov     rax, cs:__security_cookie
0x180087fbe  xor     rax, rsp
0x180087fc1  mov     [rbp+4Fh+var_40], rax
0x180087fc5  mov     r14, [rbp+4Fh+lParam]
0x180087fc9  mov     r15, r9
0x180087fcc  mov     esi, r8d
0x180087fcf  mov     r12, rdx
0x180087fd2  mov     rdi, rcx
0x180087fd5  cmp     r8d, 2Ch ; ','
0x180087fd9  ja      loc_18008823E
0x180087fdf  jz      loc_180088231
0x180087fe5  cmp     r8d, 2
0x180087fe9  jz      loc_18008813E
0x180087fef  cmp     r8d, 5
0x180087ff3  jz      loc_1800880E8
0x180087ff9  cmp     r8d, 0Fh
0x180087ffd  jz      short loc_180088074
0x180087fff  cmp     r8d, 15h
0x180088003  jz      short loc_18008803D
0x180088005  cmp     r8d, 1Ah
0x180088009  jz      short loc_18008804C
0x18008800b  cmp     r8d, 2Bh ; '+'
0x18008800f  jnz     short loc_18008805E
0x180088011  mov     ecx, [r14]
0x180088014  sub     ecx, 1
0x180088017  jz      short loc_18008802B
0x180088019  cmp     ecx, 2
0x18008801c  jnz     short loc_18008805E
0x18008801e  mov     rdx, r14; struct tagDRAWITEMSTRUCT *
0x180088021  mov     rcx, rdi; this
0x180088024  call    ?ComboBox_WMDrawItem@CFmtBar@@AEAAXPEAUtagDRAWITEMSTRUCT@@@Z; CFmtBar::ComboBox_WMDrawItem(tagDRAWITEMSTRUCT *)
0x180088029  jmp     short loc_18008805E
0x18008802b  mov     r8, [rdi+48h]; HMENU
0x18008802f  mov     rdx, r14; struct tagDRAWITEMSTRUCT *
0x180088032  mov     rcx, [rdi+18h]; HWND
0x180088036  call    ?Color_WMDrawItem@@YAXPEAUHWND__@@PEAUtagDRAWITEMSTRUCT@@PEAUHMENU__@@@Z; Color_WMDrawItem(HWND__ *,tagDRAWITEMSTRUCT *,HMENU__ *)
0x18008803b  jmp     short loc_18008805E
0x18008803d  call    ?_SetToolbarBitmaps@CFmtBar@@AEAAJXZ; CFmtBar::_SetToolbarBitmaps(void)
0x180088042  mov     rcx, [rdi+38h]
0x180088046  call    cs:__imp_UpdateRebarBandColors
0x18008804c  mov     rcx, [rdi+38h]; hWnd
0x180088050  mov     r9, r14; lParam
0x180088053  mov     r8, r15; wParam
0x180088056  mov     edx, esi; Msg
0x180088058  call    cs:__imp_SendMessageA
0x18008805e  mov     r9, r14; lParam
0x180088061  mov     r8, r15; wParam
0x180088064  mov     edx, esi; Msg
0x180088066  mov     rcx, r12; hWnd
0x180088069  call    cs:__imp_DefWindowProcA
0x18008806f  jmp     loc_1800882BA
0x180088074  test    byte ptr [rcx+78h], 4
0x180088078  jz      short loc_18008805E
0x18008807a  xor     edx, edx; Val
0x18008807c  lea     rcx, [rbp+4Fh+Paint]; void *
0x180088080  lea     r8d, [rdx+48h]; Size
0x180088084  call    memset_0
0x180088089  xorps   xmm0, xmm0
0x18008808c  lea     rdx, [rbp+4Fh+Paint]; lpPaint
0x180088090  mov     rcx, r12; hWnd
0x180088093  movups  xmmword ptr [rbp+4Fh+Rect.left], xmm0
0x180088097  call    cs:__imp_BeginPaint
0x18008809d  mov     rbx, rax
0x1800880a0  test    rax, rax
0x1800880a3  jz      loc_1800882B8
0x1800880a9  lea     rdx, [rbp+4Fh+Rect]; lpRect
0x1800880ad  mov     rcx, r12; hWnd
0x1800880b0  call    cs:__imp_GetClientRect
0x1800880b6  mov     edx, [rbp+4Fh+Rect.bottom]
0x1800880b9  mov     r9d, 8; grfFlags
0x1800880bf  add     edx, 0FFFFFFFDh
0x1800880c2  mov     rcx, rbx; hdc
0x1800880c5  mov     [rbp+4Fh+Rect.top], edx
0x1800880c8  lea     rdx, [rbp+4Fh+Rect]; qrc
0x1800880cc  lea     r8d, [r9-7]; edge
0x1800880d0  call    cs:__imp_DrawEdge
0x1800880d6  lea     rdx, [rbp+4Fh+Paint]; lpPaint
0x1800880da  mov     rcx, r12; hWnd
0x1800880dd  call    cs:__imp_EndPaint
0x1800880e3  jmp     loc_1800882B8
0x1800880e8  mov     rcx, [rcx+38h]; hWnd
0x1800880ec  lea     rdx, [rbp+4Fh+Rect]; lpRect
0x1800880f0  xorps   xmm0, xmm0
0x1800880f3  movups  xmmword ptr [rbp+4Fh+Rect.left], xmm0
0x1800880f7  call    cs:__imp_GetClientRect
0x1800880fd  movzx   edx, r14w
0x180088101  cmp     [rbp+4Fh+Rect.right], edx
0x180088104  jz      loc_18008805E
0x18008810a  mov     [rsp+0E0h+uFlags], 14h; uFlags
0x180088112  mov     rax, r14
0x180088115  shr     rax, 10h
0x180088119  mov     r9d, 2; Y
0x18008811f  movzx   ecx, ax
0x180088122  xor     r8d, r8d; X
0x180088125  mov     [rsp+0E0h+cy], ecx; cy
0x180088129  mov     rcx, [rdi+38h]; hWnd
0x18008812d  mov     [rsp+0E0h+var_C0], edx; cx
0x180088131  xor     edx, edx; hWndInsertAfter
0x180088133  call    cs:__imp_SetWindowPos
0x180088139  jmp     loc_18008805E
0x18008813e  mov     r8, [rcx+0A8h]; dwNewLong
0x180088145  test    r8, r8
0x180088148  jz      short loc_18008816A
0x18008814a  mov     rcx, [rcx+20h]; hWnd
0x18008814e  mov     edx, 0FFFFFFFCh; nIndex
0x180088153  call    cs:__imp_SetWindowLongPtrA
0x180088159  mov     rcx, [rdi+20h]; hWnd
0x18008815d  lea     rdx, aOeThis; "OE_This"
0x180088164  call    cs:__imp_RemovePropA
0x18008816a  cmp     qword ptr [rdi+58h], 0
0x18008816f  jz      short loc_1800881C8
0x180088171  mov     rcx, [rdi+28h]; hWnd
0x180088175  mov     edx, 5; uCmd
0x18008817a  call    cs:__imp_GetWindow
0x180088180  test    rax, rax
0x180088183  jz      short loc_1800881C8
0x180088185  mov     rcx, [rdi+28h]; hWnd
0x180088189  mov     edx, 5; uCmd
0x18008818e  mov     rbx, [rdi+58h]
0x180088192  call    cs:__imp_GetWindow
0x180088198  mov     r8, rbx; dwNewLong
0x18008819b  mov     edx, 0FFFFFFFCh; nIndex
0x1800881a0  mov     rcx, rax; hWnd
0x1800881a3  call    cs:__imp_SetWindowLongPtrA
0x1800881a9  mov     rcx, [rdi+28h]; hWnd
0x1800881ad  mov     edx, 5; uCmd
0x1800881b2  call    cs:__imp_GetWindow
0x1800881b8  mov     rcx, rax; hWnd
0x1800881bb  lea     rdx, aOeThis; "OE_This"
0x1800881c2  call    cs:__imp_RemovePropA
0x1800881c8  mov     r8, [rdi+60h]; dwNewLong
0x1800881cc  test    r8, r8
0x1800881cf  jz      short loc_1800881F1
0x1800881d1  mov     rcx, [rdi+28h]; hWnd
0x1800881d5  mov     edx, 0FFFFFFFCh; nIndex
0x1800881da  call    cs:__imp_SetWindowLongPtrA
0x1800881e0  mov     rcx, [rdi+28h]; hWnd
0x1800881e4  lea     rdx, aOeThis; "OE_This"
0x1800881eb  call    cs:__imp_RemovePropA
0x1800881f1  mov     r8, [rdi+68h]; dwNewLong
0x1800881f5  test    r8, r8
0x1800881f8  jz      short loc_18008821A
0x1800881fa  mov     rcx, [rdi+30h]; hWnd
0x1800881fe  mov     edx, 0FFFFFFFCh; nIndex
0x180088203  call    cs:__imp_SetWindowLongPtrA
0x180088209  mov     rcx, [rdi+30h]; hWnd
0x18008820d  lea     rdx, aOeThis; "OE_This"
0x180088214  call    cs:__imp_RemovePropA
0x18008821a  mov     rcx, [rdi+40h]; hWnd
0x18008821e  call    cs:__imp_DestroyWindow
0x180088224  mov     qword ptr [rdi+40h], 0
0x18008822c  jmp     loc_18008805E
0x180088231  mov     rdx, r14; struct tagMEASUREITEMSTRUCT *
0x180088234  call    ?OnMeasureItem@CFmtBar@@AEAAXPEAUtagMEASUREITEMSTRUCT@@@Z; CFmtBar::OnMeasureItem(tagMEASUREITEMSTRUCT *)
0x180088239  jmp     loc_18008805E
0x18008823e  mov     eax, esi
0x180088240  sub     eax, 4Eh ; 'N'
0x180088243  jz      short loc_1800882B0
0x180088245  sub     eax, 30h ; '0'
0x180088248  jz      loc_18008804C
0x18008824e  sub     eax, 4
0x180088251  jz      short loc_18008828A
0x180088253  sub     eax, 8Fh
0x180088258  jz      short loc_180088273
0x18008825a  sub     eax, 1FEh
0x18008825f  jz      loc_18008804C
0x180088265  cmp     eax, 2
0x180088268  jz      loc_18008804C
0x18008826e  jmp     loc_18008805E
0x180088273  shr     r9, 10h; unsigned __int16
0x180088277  movzx   r8d, r15w; int
0x18008827b  call    ?OnWMCommand@CFmtBar@@QEAAJPEAUHWND__@@HG@Z; CFmtBar::OnWMCommand(HWND__ *,int,ushort)
0x180088280  test    eax, eax
0x180088282  jnz     loc_18008805E
0x180088288  jmp     short loc_1800882B8
0x18008828a  mov     rcx, [rcx+18h]; hWnd
0x18008828e  xor     r8d, r8d; dwNewLong
0x180088291  lea     edx, [r8-15h]; nIndex
0x180088295  call    cs:__imp_SetWindowLongPtrA
0x18008829b  mov     rcx, rdi; this
0x18008829e  mov     qword ptr [rdi+18h], 0
0x1800882a6  call    ?Release@CFmtBar@@QEAAKXZ; CFmtBar::Release(void)
0x1800882ab  jmp     loc_18008805E
0x1800882b0  mov     r8, r14; struct tagNMHDR *
0x1800882b3  call    ?WMNotify@CFmtBar@@AEAAX_KPEAUtagNMHDR@@@Z; CFmtBar::WMNotify(unsigned __int64,tagNMHDR *)
0x1800882b8  xor     eax, eax
0x1800882ba  mov     rcx, [rbp+4Fh+var_40]
0x1800882be  xor     rcx, rsp; StackCookie
0x1800882c1  call    __security_check_cookie
0x1800882c6  add     rsp, 0B0h
0x1800882cd  pop     r15
0x1800882cf  pop     r14
0x1800882d1  pop     r12
0x1800882d3  pop     rdi
0x1800882d4  pop     rsi
0x1800882d5  pop     rbx
0x1800882d6  pop     rbp
0x1800882d7  retn
```
