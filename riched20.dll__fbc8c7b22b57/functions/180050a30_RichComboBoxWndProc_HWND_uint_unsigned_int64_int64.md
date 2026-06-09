# RichComboBoxWndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180050a30`
- end: `0x180051780`
- name: `?RichComboBoxWndProc@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `3408`
- prototype: `__int64 __fastcall(HWND, UINT Msg, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `34`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800230e0`
- `0x1800344c4`
- `0x18003c960`
- `0x1800416f0`
- `0x180041bd0`
- `0x1800478d4`
- `0x18004e5a4`
- `0x18004ea64`
- `0x18004ed04`
- `0x18004edcc`
- `0x18004f05c`
- `0x18004f840`
- `0x18004fec8`
- `0x18004ffa0`
- `0x180050068`
- `0x1800500f4`
- `0x180050244`
- `0x180050300`
- `0x1800503d8`
- `0x1800506ec`
- `0x1800507dc`
- `0x180050874`
- `0x180050a30`
- `0x1800518d0`
- `0x180051d9c`
- `0x18005d0bc`
- `0x180061970`
- `0x180062124`
- `0x180062394`
- `0x1800624e8`
- `0x180062b98`
- `0x18006bb30`
- `0x180092088`
- `0x180095010`

## import_xrefs

- `USER32!GetWindowLongPtrW` at `0x180050a66`
- `USER32!GetWindowLongPtrW` at `0x180050b02`
- `USER32!GetWindowLongPtrW` at `0x180050a66`
- `USER32!GetWindowLongPtrW` at `0x180050b02`
- `USER32!DestroyWindow` at `0x180050ac8`
- `USER32!DestroyWindow` at `0x180050ac8`
- `USER32!ReleaseDC` at `0x180050e4b`
- `USER32!ReleaseDC` at `0x1800515b0`
- `USER32!ReleaseDC` at `0x180050e4b`
- `USER32!ReleaseDC` at `0x1800515b0`
- `USER32!GetDC` at `0x180050e1f`
- `USER32!GetDC` at `0x180051572`
- `USER32!GetDC` at `0x180050e1f`
- `USER32!GetDC` at `0x180051572`
- `USER32!EnableWindow` at `0x180050cbb`
- `USER32!EnableWindow` at `0x180050cbb`
- `USER32!InvalidateRect` at `0x180050c9a`
- `USER32!InvalidateRect` at `0x180050c9a`

## pseudocode

```c
__int64 __fastcall RichComboBoxWndProc(HWND a1, UINT Msg, unsigned __int64 a3, __int64 a4)
{
  UINT v4; // esi
  LONG_PTR WindowLongPtrW; // rdi
  __int64 v9; // rcx
  HWND v10; // rcx
  unsigned __int64 v11; // rdx
  __int64 v12; // r8
  unsigned __int64 v13; // r9
  __int64 Options; // rax
  __int64 *v15; // r9
  int v16; // eax
  unsigned __int64 v17; // r8
  unsigned int v18; // edx
  HDC v19; // rax
  HDC v20; // rbx
  void (__fastcall **v21)(LONG_PTR, GUID *, struct IUnknown **); // rax
  const struct _GUID *v22; // rcx
  int v23; // r8d
  unsigned __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // rax
  unsigned int v27; // edx
  unsigned __int64 v28; // rax
  unsigned __int64 v29; // rax
  int v30; // ecx
  HWND v31; // rcx
  HWND v32; // rcx
  int v33; // eax
  int v34; // eax
  __int64 v35; // r8
  HDC DC; // rbx
  HDC v37; // rdx
  int v38; // r8d
  int v39; // r9d
  int ECDefaultHeightAndWidth; // r15d
  HWND v41; // rcx
  UINT v42; // esi
  unsigned __int64 v43; // rsi
  _WORD *i; // rbx
  __int64 v45; // rax
  int v46; // [rsp+40h] [rbp-40h] BYREF
  __int64 v47; // [rsp+48h] [rbp-38h] BYREF
  struct IUnknown *v48; // [rsp+50h] [rbp-30h] BYREF
  __int64 v49; // [rsp+58h] [rbp-28h] BYREF
  _BYTE v50[32]; // [rsp+60h] [rbp-20h] BYREF
  unsigned int v51; // [rsp+C8h] [rbp+48h] BYREF
  unsigned __int64 bEnable; // [rsp+D0h] [rbp+50h] BYREF

  bEnable = a3;
  v51 = Msg;
  v4 = Msg;
  v47 = 1;
  WindowLongPtrW = GetWindowLongPtrW(a1, 0);
  switch ( v4 )
  {
    case 1u:
      if ( WindowLongPtrW )
        goto LABEL_15;
      CCmbBxWinHost::OnNCCreate(a1, (const struct tagCREATESTRUCTW *)a4);
      WindowLongPtrW = GetWindowLongPtrW(a1, 0);
      break;
    case 2u:
      if ( WindowLongPtrW )
      {
        v9 = *(_QWORD *)(WindowLongPtrW + 248);
        if ( v9 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
        v10 = *(HWND *)(WindowLongPtrW + 128);
        if ( v10 )
          DestroyWindow(v10);
        CTxtWinHost::Shutdown((CTxtWinHost *)WindowLongPtrW);
        (*(void (__fastcall **)(LONG_PTR))(*(_QWORD *)WindowLongPtrW + 16LL))(WindowLongPtrW);
      }
      return 0;
    case 0x81u:
      return CCmbBxWinHost::OnNCCreate(a1, (const struct tagCREATESTRUCTW *)a4);
  }
  if ( !WindowLongPtrW )
    return CW32System::DefWindowProc(a1, v4, bEnable, a4);
LABEL_15:
  if ( !*(_QWORD *)(WindowLongPtrW + 32) )
    return 0;
  (*(void (__fastcall **)(LONG_PTR))(*(_QWORD *)WindowLongPtrW + 8LL))(WindowLongPtrW);
  if ( v4 > 0x149 )
  {
    if ( v4 > 0x200 )
    {
      if ( v4 > 0x43F )
      {
        switch ( v4 )
        {
          case 0x443u:
            goto LABEL_221;
          case 0x44Du:
            CTxtWinHost::OnSetOptions((CTxtWinHost *)WindowLongPtrW, bEnable, a4);
            v45 = *(_DWORD *)(WindowLongPtrW + 44) & 0x10C99C0;
            v47 = v45;
            if ( (*(_BYTE *)(WindowLongPtrW + 52) & 8) != 0 )
            {
              Options = v45 | 1;
              goto LABEL_220;
            }
            goto LABEL_221;
          case 0x44Eu:
            Options = CTxtWinHost::OnGetOptions((CTxtWinHost *)WindowLongPtrW);
            goto LABEL_220;
        }
        if ( v4 != 1117 )
        {
          if ( v4 == 1121 )
          {
            v43 = bEnable;
            for ( i = (_WORD *)a4; *i != 13; ++i )
              ;
            *i = 0;
            (*(void (__fastcall **)(_QWORD, __int64, unsigned __int64, __int64, _QWORD))(**(_QWORD **)(WindowLongPtrW + 32)
                                                                                       + 24LL))(
              *(_QWORD *)(WindowLongPtrW + 32),
              1121,
              v43,
              a4,
              0);
            *i = 13;
            CW32System::SendMessage(*(HWND *)(WindowLongPtrW + 128), 0x461u, v43, i + 1);
            goto LABEL_221;
          }
          goto LABEL_192;
        }
        goto LABEL_221;
      }
      if ( v4 == 1087 )
      {
        if ( a4 )
        {
          *(_DWORD *)(WindowLongPtrW + 44) |= 0x100u;
          v35 = 0;
          if ( bEnable )
          {
            *(_DWORD *)(WindowLongPtrW + 44) &= ~0x100u;
            v35 = 32;
          }
          (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(WindowLongPtrW + 32) + 152LL))(
            *(_QWORD *)(WindowLongPtrW + 32),
            32,
            v35);
        }
        goto LABEL_192;
      }
      if ( v4 != 513 )
      {
        if ( v4 == 514 )
        {
          v26 = CCmbBxWinHost::OnLButtonUp((CCmbBxWinHost *)WindowLongPtrW, v11, v12);
          goto LABEL_162;
        }
        if ( v4 != 515 )
        {
          if ( v4 == 522 )
          {
            if ( !CCmbBxWinHost::OnMouseWheel((CCmbBxWinHost *)WindowLongPtrW, bEnable, a4) )
              goto LABEL_221;
            goto LABEL_193;
          }
          if ( v4 != 533 )
          {
            if ( v4 != 1026 )
              goto LABEL_192;
            CCmbBxWinHost::OnLButtonUp((CCmbBxWinHost *)WindowLongPtrW, v11, v12);
            *(_DWORD *)(WindowLongPtrW + 120) |= 0x808u;
            goto LABEL_173;
          }
          v34 = *(_DWORD *)(WindowLongPtrW + 120);
          if ( (v34 & 0x100) == 0 )
            goto LABEL_221;
          if ( (v34 & 2) != 0 )
          {
            CCmbBxWinHost::HideListBox((CCmbBxWinHost *)WindowLongPtrW, 1, 0);
          }
          else
          {
            *(_DWORD *)(WindowLongPtrW + 120) = v34 & 0xFFFFFEEF;
            CCmbBxWinHost::DrawButton((CCmbBxWinHost *)WindowLongPtrW, 0, 0);
          }
          goto LABEL_192;
        }
      }
      v26 = CCmbBxWinHost::OnLButtonDown((CCmbBxWinHost *)WindowLongPtrW, v11, a4);
    }
    else
    {
      if ( v4 != 512 )
      {
        switch ( v4 )
        {
          case 0x14Au:
            v4 = 385;
            goto LABEL_209;
          case 0x14Bu:
            v4 = 388;
            goto LABEL_209;
          case 0x14Cu:
            v4 = 399;
            goto LABEL_209;
          case 0x14Du:
            v47 = -1;
            v31 = *(HWND *)(WindowLongPtrW + 128);
            if ( !v31 )
              goto LABEL_221;
            v47 = RichListBoxWndProc(v31, 0x18Cu, bEnable, a4);
            goto LABEL_212;
          case 0x14Eu:
            v32 = *(HWND *)(WindowLongPtrW + 128);
            if ( !v32 )
              goto LABEL_221;
            v47 = RichListBoxWndProc(v32, 0x186u, bEnable, a4);
            if ( v47 != -1 )
              RichListBoxWndProc(*(HWND *)(WindowLongPtrW + 128), 0x197u, bEnable, 0);
            goto LABEL_212;
          case 0x14Fu:
            v33 = *(_DWORD *)(WindowLongPtrW + 120) & 2;
            if ( bEnable )
            {
              if ( !v33 )
                CCmbBxWinHost::ShowListBox((CCmbBxWinHost *)WindowLongPtrW, v11);
            }
            else if ( v33 )
            {
              CCmbBxWinHost::HideListBox((CCmbBxWinHost *)WindowLongPtrW, 1, 0);
            }
            goto LABEL_221;
          case 0x150u:
            v4 = 409;
            goto LABEL_209;
          case 0x151u:
            v4 = 410;
            goto LABEL_209;
          case 0x152u:
          case 0x159u:
          case 0x15Au:
          case 0x15Du:
          case 0x15Eu:
          case 0x15Fu:
          case 0x160u:
          case 0x161u:
            goto LABEL_221;
          case 0x153u:
            Options = CCmbBxWinHost::CbSetItemHeight((CCmbBxWinHost *)WindowLongPtrW, bEnable == 0xFFFFFFFF, a4);
            goto LABEL_220;
          case 0x154u:
            if ( bEnable == 0xFFFFFFFF )
              Options = *(int *)(WindowLongPtrW + 212);
            else
              Options = RichListBoxWndProc(*(HWND *)(WindowLongPtrW + 128), 0x1A1u, 0, 0);
            goto LABEL_220;
          case 0x155u:
            v30 = -((_DWORD)bEnable != 0);
            *(_DWORD *)(WindowLongPtrW + 120) &= ~0x400u;
            *(_DWORD *)(WindowLongPtrW + 120) |= v30 & 0x400;
            goto LABEL_138;
          case 0x156u:
            v29 = (unsigned __int64)*(unsigned int *)(WindowLongPtrW + 120) >> 10;
            goto LABEL_135;
          case 0x157u:
            v29 = (unsigned __int64)*(unsigned int *)(WindowLongPtrW + 120) >> 1;
LABEL_135:
            Options = v29 & 1;
            goto LABEL_220;
          case 0x158u:
            v4 = 418;
            goto LABEL_209;
          case 0x15Bu:
            v4 = 398;
            goto LABEL_209;
          case 0x15Cu:
            v4 = 407;
            goto LABEL_209;
          default:
            goto LABEL_192;
        }
      }
      v26 = CCmbBxWinHost::OnMouseMove((CCmbBxWinHost *)WindowLongPtrW, v11, a4);
    }
LABEL_162:
    if ( !v26 )
      goto LABEL_221;
    goto LABEL_192;
  }
  if ( v4 == 329 )
  {
    v4 = 394;
    goto LABEL_209;
  }
  if ( v4 > 0xB2 )
  {
    if ( v4 > 0x111 )
    {
      switch ( v4 )
      {
        case 0x140u:
          v4 = 176;
          break;
        case 0x141u:
          v4 = 197;
          break;
        case 0x142u:
          if ( *(_DWORD *)(WindowLongPtrW + 240) != 3 )
          {
            v4 = 177;
            if ( (*(_DWORD *)(WindowLongPtrW + 52) & 0x8000) == 0
              || (unsigned int)CTxtEdit::GetAdjustedTextLength(*(CTxtEdit **)(WindowLongPtrW + 32))
              || bEnable == -1 )
            {
              v28 = (__int16)a4;
              a4 = SWORD1(a4);
              bEnable = v28;
            }
            else
            {
              a4 = 0;
              bEnable = 0;
            }
            break;
          }
          goto LABEL_122;
        case 0x143u:
          v4 = 384;
          goto LABEL_209;
        case 0x144u:
          v4 = 386;
          goto LABEL_209;
        case 0x146u:
          v4 = 395;
          goto LABEL_209;
        case 0x147u:
          v4 = 392;
          goto LABEL_209;
        case 0x148u:
          v4 = 393;
          goto LABEL_209;
      }
    }
    else
    {
      if ( v4 != 273 )
      {
        switch ( v4 )
        {
          case 0xB3u:
          case 0xB4u:
          case 0xCCu:
          case 0xCFu:
            goto LABEL_221;
          case 0xD2u:
LABEL_138:
            v47 = 0;
            goto LABEL_221;
          case 0xD3u:
            v27 = bEnable;
            if ( (bEnable & 1) != 0 )
            {
              *(_DWORD *)(WindowLongPtrW + 204) = (unsigned __int16)a4;
              v27 = bEnable;
            }
            if ( (v27 & 2) != 0 )
            {
              *(_DWORD *)(WindowLongPtrW + 200) = WORD1(a4);
              v27 = bEnable;
            }
            CTxtWinHost::OnSetMargins(
              (CTxtWinHost *)WindowLongPtrW,
              v27,
              *(_DWORD *)(WindowLongPtrW + 196) + (unsigned __int16)a4,
              WORD1(a4) + *(_DWORD *)(WindowLongPtrW + 192));
            goto LABEL_221;
          case 0x100u:
            v26 = (*(__int64 (__fastcall **)(LONG_PTR, _QWORD, _QWORD))(*(_QWORD *)WindowLongPtrW + 432LL))(
                    WindowLongPtrW,
                    (unsigned __int16)bEnable,
                    (unsigned int)a4);
            break;
          case 0x102u:
            if ( CW32System::_dwPlatformId == 1 || (*(_DWORD *)(WindowLongPtrW + 52) & 0x40000) != 0 )
            {
              v46 = 0;
              LOBYTE(v46) = (*(_DWORD *)(WindowLongPtrW + 52) & 0x20000) != 0;
              CW32System::AnsiFilter(&v51, &bEnable, a4, &v46, 0);
              if ( BYTE1(v46) )
              {
                *(_DWORD *)(WindowLongPtrW + 52) |= 0x20000u;
                *(_WORD *)(WindowLongPtrW + 98) = (_WORD)bEnable << 8;
                goto LABEL_221;
              }
              if ( BYTE2(v46) )
              {
                bEnable |= *(unsigned __int16 *)(WindowLongPtrW + 98);
                *(_DWORD *)(WindowLongPtrW + 52) &= ~0x20000u;
                *(_WORD *)(WindowLongPtrW + 98) = 0;
LABEL_96:
                v4 = 646;
                goto LABEL_192;
              }
              if ( HIBYTE(v46) )
                goto LABEL_96;
              v4 = v51;
            }
            v26 = (*(__int64 (__fastcall **)(LONG_PTR, _QWORD, _QWORD))(*(_QWORD *)WindowLongPtrW + 440LL))(
                    WindowLongPtrW,
                    (unsigned __int16)bEnable,
                    (unsigned int)a4);
            break;
          default:
            if ( v4 == 260
              && !(*(__int64 (__fastcall **)(LONG_PTR, _QWORD, _QWORD))(*(_QWORD *)WindowLongPtrW + 496LL))(
                    WindowLongPtrW,
                    (unsigned __int16)bEnable,
                    (unsigned int)a4) )
            {
              goto LABEL_221;
            }
            goto LABEL_192;
        }
        goto LABEL_162;
      }
      if ( (unsigned int)CCmbBxWinHost::OnCommand((CCmbBxWinHost *)WindowLongPtrW, bEnable, v12) )
        goto LABEL_221;
    }
LABEL_192:
    if ( (*(unsigned int (__fastcall **)(_QWORD, _QWORD, unsigned __int64, __int64, __int64 *))(**(_QWORD **)(WindowLongPtrW + 32)
                                                                                              + 24LL))(
           *(_QWORD *)(WindowLongPtrW + 32),
           v4,
           bEnable,
           a4,
           &v47) != 1 )
    {
LABEL_194:
      switch ( v4 )
      {
        case 0x30u:
          DC = GetDC(a1);
          ECDefaultHeightAndWidth = GetECDefaultHeightAndWidth(
                                      *(struct ITextServices **)(WindowLongPtrW + 32),
                                      v37,
                                      v38,
                                      v39,
                                      (int)CW32System::_yPerInchScreenDC,
                                      (int *)&v51,
                                      0,
                                      0);
          ReleaseDC(a1, DC);
          if ( ECDefaultHeightAndWidth )
            *(_DWORD *)(WindowLongPtrW + 208) = ECDefaultHeightAndWidth;
          *(_DWORD *)(WindowLongPtrW + 212) = 0;
          CCmbBxWinHost::CbCalcControlRects(
            (CCmbBxWinHost *)WindowLongPtrW,
            (struct tagRECT *)(WindowLongPtrW + 144),
            1);
          *(_DWORD *)(WindowLongPtrW + 120) |= 2u;
          CCmbBxWinHost::HideListBox((CCmbBxWinHost *)WindowLongPtrW, 0, 0);
          goto LABEL_209;
        case 0xB1u:
          (*(void (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, _QWORD))(**(_QWORD **)(WindowLongPtrW + 32) + 24LL))(
            *(_QWORD *)(WindowLongPtrW + 32),
            1087,
            0,
            0,
            0);
          break;
        case 0xC5u:
          break;
        case 0x439u:
        case 0x444u:
        case 0x447u:
        case 0x478u:
        case 0x4C8u:
        case 0x4CAu:
LABEL_209:
          v41 = *(HWND *)(WindowLongPtrW + 128);
          if ( v41 )
          {
            v47 = CW32System::SendMessage(v41, v4, bEnable, (unsigned __int16 *)a4);
            v42 = v4 - 388;
            if ( v42 )
            {
              if ( v42 == 2 )
LABEL_212:
                CCmbBxWinHost::UpdateEditBox((CCmbBxWinHost *)WindowLongPtrW);
            }
            else
            {
              (*(void (__fastcall **)(_QWORD, __int64, unsigned __int64))(**(_QWORD **)(WindowLongPtrW + 32) + 24LL))(
                *(_QWORD *)(WindowLongPtrW + 32),
                12,
                bEnable);
            }
          }
          goto LABEL_221;
        default:
          goto LABEL_221;
      }
      v47 = 1;
      goto LABEL_221;
    }
LABEL_193:
    v47 = CW32System::DefWindowProc(a1, v4, bEnable, a4);
    goto LABEL_194;
  }
  if ( v4 == 178 )
    goto LABEL_221;
  if ( v4 <= 0x15 )
  {
    switch ( v4 )
    {
      case 0x15u:
        goto LABEL_48;
      case 1u:
        Options = (*(__int64 (__fastcall **)(LONG_PTR, __int64))(*(_QWORD *)WindowLongPtrW + 472LL))(WindowLongPtrW, a4);
        goto LABEL_220;
      case 5u:
        Options = CCmbBxWinHost::OnSize((CCmbBxWinHost *)WindowLongPtrW, bEnable, a4);
        goto LABEL_220;
    }
    if ( v4 != 7 )
    {
      if ( v4 == 8 )
      {
        v47 = CCmbBxWinHost::OnKillFocus((CCmbBxWinHost *)WindowLongPtrW, bEnable, v12);
        if ( v47 )
          goto LABEL_193;
        goto LABEL_192;
      }
      if ( v4 != 10 )
      {
        if ( v4 != 12 )
        {
          switch ( v4 )
          {
            case 0xDu:
              memset(v50, 0, 28);
              if ( CW32System::_dwPlatformId != 1 && (*(_DWORD *)(WindowLongPtrW + 52) & 0x40000) == 0 )
                goto LABEL_192;
              v15 = (__int64 *)v50;
              break;
            case 0xEu:
              v49 = 0;
              if ( CW32System::_dwPlatformId != 1 && (*(_DWORD *)(WindowLongPtrW + 52) & 0x40000) == 0 )
                goto LABEL_192;
              v15 = &v49;
              break;
            case 0xFu:
              Options = CCmbBxWinHost::OnPaint((CCmbBxWinHost *)WindowLongPtrW, v11, v12);
LABEL_220:
              v47 = Options;
              goto LABEL_221;
            default:
              goto LABEL_192;
          }
          CW32System::AnsiFilter(&v51, &bEnable, a4, v15, 0);
          v4 = v51;
          goto LABEL_192;
        }
        if ( *(_DWORD *)(WindowLongPtrW + 240) == 2 )
          goto LABEL_192;
LABEL_122:
        v47 = -1;
        goto LABEL_221;
      }
      v16 = *(_DWORD *)(WindowLongPtrW + 120);
      if ( (v16 & 0x10) != 0 )
      {
        *(_DWORD *)(WindowLongPtrW + 120) = v16 & 0xFFFFFFEF;
        CCmbBxWinHost::DrawButton((CCmbBxWinHost *)WindowLongPtrW, 0, 0);
        if ( (*(_BYTE *)(WindowLongPtrW + 120) & 2) != 0 )
          CCmbBxWinHost::HideListBox((CCmbBxWinHost *)WindowLongPtrW, 1, 0);
      }
      v17 = bEnable;
      v18 = *(_DWORD *)(WindowLongPtrW + 52);
      if ( ((v18 >> 11) & 1) != (bEnable == 0) )
      {
        InvalidateRect(*(HWND *)(WindowLongPtrW + 16), 0, 1);
        CTxtWinHost::SetScrollBarsForWmEnable((CTxtWinHost *)WindowLongPtrW, bEnable);
        EnableWindow(*(HWND *)(WindowLongPtrW + 128), bEnable);
        v18 = *(_DWORD *)(WindowLongPtrW + 52);
        v17 = bEnable;
      }
      *(_DWORD *)(WindowLongPtrW + 52) = (v17 == 0 ? 0x800 : 0) | v18 & 0xFFFFF7FF;
      v47 = 0;
LABEL_48:
      CW32System::SendMessage(*(HWND *)(WindowLongPtrW + 128), v4, bEnable, (unsigned __int16 *)a4);
      (*(void (__fastcall **)(LONG_PTR))(*(_QWORD *)WindowLongPtrW + 448LL))(WindowLongPtrW);
      goto LABEL_192;
    }
LABEL_173:
    v47 = CCmbBxWinHost::OnSetFocus((CCmbBxWinHost *)WindowLongPtrW, v11, v12);
    if ( v47 )
      goto LABEL_193;
    goto LABEL_192;
  }
  switch ( v4 )
  {
    case 0x18u:
      CTxtWinHost::OnTxVisibleChange((CTxtWinHost *)WindowLongPtrW, bEnable);
      goto LABEL_221;
    case 0x20u:
      if ( (HWND)bEnable != a1 )
        goto LABEL_221;
      v47 = CW32System::DefWindowProc(a1, v4, bEnable, a4);
      if ( v47 )
        goto LABEL_221;
      Options = CCmbBxWinHost::OnSetCursor((CCmbBxWinHost *)WindowLongPtrW, v24, v25);
      goto LABEL_220;
    case 0x2Bu:
      v23 = 1;
LABEL_70:
      v47 = CCmbBxWinHost::CbMessageItemHandler((CCmbBxWinHost *)WindowLongPtrW, 0, v23, v13, a4);
      if ( v47 )
        goto LABEL_221;
      goto LABEL_193;
    case 0x2Du:
      v23 = 3;
      goto LABEL_70;
    case 0x3Du:
      v21 = *(void (__fastcall ***)(LONG_PTR, GUID *, struct IUnknown **))WindowLongPtrW;
      v48 = 0;
      (*v21)(WindowLongPtrW, &IID_IUnknown, &v48);
      v47 = CW32System::LResultFromObject(v22, bEnable, v48);
      ((void (__fastcall *)(struct IUnknown *))v48->lpVtbl->Release)(v48);
      goto LABEL_221;
    case 0x7Cu:
      Options = CW32System::DefWindowProc(a1, 0x7Cu, bEnable, a4);
      goto LABEL_220;
  }
  if ( v4 != 125 )
  {
    if ( v4 == 133 )
    {
      v47 = CW32System::DefWindowProc(a1, 0x85u, bEnable, a4);
      if ( (*(unsigned int (__fastcall **)(LONG_PTR))(*(_QWORD *)WindowLongPtrW + 424LL))(WindowLongPtrW) == 1
        && CW32System::_dwMajorVersion < 4 )
      {
        v19 = GetDC(a1);
        v20 = v19;
        if ( v19 )
        {
          CTxtWinHost::DrawSunkenBorder((CTxtWinHost *)WindowLongPtrW, a1, v19);
          ReleaseDC(a1, v20);
        }
      }
      goto LABEL_221;
    }
    if ( v4 == 135 )
    {
      CW32System::SendMessage(*(HWND *)(WindowLongPtrW + 128), 0x87u, bEnable, (unsigned __int16 *)a4);
      Options = (*(__int64 (__fastcall **)(LONG_PTR, unsigned __int64, __int64))(*(_QWORD *)WindowLongPtrW + 456LL))(
                  WindowLongPtrW,
                  bEnable,
                  a4);
      goto LABEL_220;
    }
    goto LABEL_192;
  }
LABEL_221:
  (*(void (__fastcall **)(LONG_PTR))(*(_QWORD *)WindowLongPtrW + 16LL))(WindowLongPtrW);
  return v47;
}

```

## disassembly

```asm
0x180050a30  mov     [rsp-38h+arg_0], rbx
0x180050a35  mov     [rsp-38h+bEnable], r8
0x180050a3a  mov     [rsp-38h+arg_8], edx
0x180050a3e  push    rbp
0x180050a3f  push    rsi
0x180050a40  push    rdi
0x180050a41  push    r12
0x180050a43  push    r13
0x180050a45  push    r14
0x180050a47  push    r15
0x180050a49  mov     rbp, rsp
0x180050a4c  sub     rsp, 80h
0x180050a53  mov     esi, edx
0x180050a55  mov     ebx, 1
0x180050a5a  xor     edx, edx; nIndex
0x180050a5c  mov     [rbp+var_38], rbx
0x180050a60  mov     r14, r9
0x180050a63  mov     r12, rcx
0x180050a66  call    cs:__imp_GetWindowLongPtrW
0x180050a6d  nop     dword ptr [rax+rax+00h]
0x180050a72  mov     rdi, rax
0x180050a75  xor     r13d, r13d
0x180050a78  mov     eax, esi
0x180050a7a  sub     eax, ebx
0x180050a7c  jz      short loc_180050AED
0x180050a7e  sub     eax, ebx
0x180050a80  jz      short loc_180050A9B
0x180050a82  cmp     eax, 7Fh
0x180050a85  jnz     loc_180050B11
0x180050a8b  mov     rdx, r14; struct tagCREATESTRUCTW *
0x180050a8e  mov     rcx, r12; HWND
0x180050a91  call    ?OnNCCreate@CCmbBxWinHost@@SA_JPEAUHWND__@@PEBUtagCREATESTRUCTW@@@Z; CCmbBxWinHost::OnNCCreate(HWND__ *,tagCREATESTRUCTW const *)
0x180050a96  jmp     loc_180051704
0x180050a9b  test    rdi, rdi
0x180050a9e  jz      loc_180050B32
0x180050aa4  mov     rcx, [rdi+0F8h]
0x180050aab  test    rcx, rcx
0x180050aae  jz      short loc_180050ABC
0x180050ab0  mov     rax, [rcx]
0x180050ab3  mov     rax, [rax+10h]
0x180050ab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050abc  mov     rcx, [rdi+80h]; hWnd
0x180050ac3  test    rcx, rcx
0x180050ac6  jz      short loc_180050AD4
0x180050ac8  call    cs:__imp_DestroyWindow
0x180050acf  nop     dword ptr [rax+rax+00h]
0x180050ad4  mov     rcx, rdi; this
0x180050ad7  call    ?Shutdown@CTxtWinHost@@QEAAXXZ; CTxtWinHost::Shutdown(void)
0x180050adc  mov     rax, [rdi]
0x180050adf  mov     rcx, rdi
0x180050ae2  mov     rax, [rax+10h]
0x180050ae6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050aeb  jmp     short loc_180050B32
0x180050aed  test    rdi, rdi
0x180050af0  jnz     short loc_180050B2C
0x180050af2  mov     rdx, r14; struct tagCREATESTRUCTW *
0x180050af5  mov     rcx, r12; HWND
0x180050af8  call    ?OnNCCreate@CCmbBxWinHost@@SA_JPEAUHWND__@@PEBUtagCREATESTRUCTW@@@Z; CCmbBxWinHost::OnNCCreate(HWND__ *,tagCREATESTRUCTW const *)
0x180050afd  xor     edx, edx; nIndex
0x180050aff  mov     rcx, r12; hWnd
0x180050b02  call    cs:__imp_GetWindowLongPtrW
0x180050b09  nop     dword ptr [rax+rax+00h]
0x180050b0e  mov     rdi, rax
0x180050b11  test    rdi, rdi
0x180050b14  jnz     short loc_180050B2C
0x180050b16  mov     r8, [rbp+bEnable]; unsigned __int64
0x180050b1a  mov     r9, r14; __int64
0x180050b1d  mov     edx, esi; unsigned int
0x180050b1f  mov     rcx, r12; HWND
0x180050b22  call    ?DefWindowProc@CW32System@@SA_JPEAUHWND__@@I_K_J@Z; CW32System::DefWindowProc(HWND__ *,uint,unsigned __int64,__int64)
0x180050b27  jmp     loc_180051704
0x180050b2c  cmp     [rdi+20h], r13
0x180050b30  jnz     short loc_180050B39
0x180050b32  xor     eax, eax
0x180050b34  jmp     loc_180051704
0x180050b39  mov     rax, [rdi]
0x180050b3c  mov     rcx, rdi
0x180050b3f  mov     rax, [rax+8]
0x180050b43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050b48  mov     eax, 149h
0x180050b4d  mov     ecx, 43Fh
0x180050b52  mov     r15d, 3
0x180050b58  cmp     esi, eax
0x180050b5a  ja      loc_18005119A
0x180050b60  jz      loc_180051190
0x180050b66  mov     eax, 0B2h
0x180050b6b  cmp     esi, eax
0x180050b6d  ja      loc_180050F22
0x180050b73  jz      loc_1800516F1; jumptable 00000001800511CD cases 338,345,346,349-353
0x180050b79  cmp     esi, 15h
0x180050b7c  ja      loc_180050D5F
0x180050b82  jz      loc_180050CE7
0x180050b88  mov     eax, esi
0x180050b8a  sub     eax, ebx
0x180050b8c  jz      loc_180050D45
0x180050b92  sub     eax, 4
0x180050b95  jz      loc_180050D31
0x180050b9b  sub     eax, 2
0x180050b9e  jz      loc_1800513CB
0x180050ba4  sub     eax, ebx
0x180050ba6  jz      loc_180050D13
0x180050bac  sub     eax, 2
0x180050baf  jz      loc_180050C49
0x180050bb5  sub     eax, 2
0x180050bb8  jz      short loc_180050C37
0x180050bba  sub     eax, ebx
0x180050bbc  jz      short loc_180050BF6
0x180050bbe  sub     eax, ebx
0x180050bc0  jz      short loc_180050BD7
0x180050bc2  cmp     eax, ebx
0x180050bc4  jnz     def_1800511CD; jumptable 00000001800511CD default case
0x180050bca  mov     rcx, rdi; this
0x180050bcd  call    ?OnPaint@CCmbBxWinHost@@QEAA_J_K_J@Z; CCmbBxWinHost::OnPaint(unsigned __int64,__int64)
0x180050bd2  jmp     loc_1800516ED
0x180050bd7  cmp     cs:?_dwPlatformId@CW32System@@0KA, ebx; ulong CW32System::_dwPlatformId
0x180050bdd  mov     [rbp+var_28], r13
0x180050be1  jz      short loc_180050BF0
0x180050be3  test    dword ptr [rdi+34h], 40000h
0x180050bea  jz      def_1800511CD; jumptable 00000001800511CD default case
0x180050bf0  lea     r9, [rbp+var_28]
0x180050bf4  jmp     short loc_180050C1A
0x180050bf6  cmp     cs:?_dwPlatformId@CW32System@@0KA, ebx; ulong CW32System::_dwPlatformId
0x180050bfc  xorps   xmm0, xmm0
0x180050bff  movups  xmmword ptr [rbp+var_20], xmm0
0x180050c03  movups  xmmword ptr [rbp+var_20+0Ch], xmm0
0x180050c07  jz      short loc_180050C16
0x180050c09  test    dword ptr [rdi+34h], 40000h
0x180050c10  jz      def_1800511CD; jumptable 00000001800511CD default case
0x180050c16  lea     r9, [rbp+var_20]; void *
0x180050c1a  mov     r8, r14; __int64
0x180050c1d  mov     dword ptr [rsp+80h+var_60], r13d; int
0x180050c22  lea     rdx, [rbp+bEnable]; unsigned __int64 *
0x180050c26  lea     rcx, [rbp+arg_8]; unsigned int *
0x180050c2a  call    ?AnsiFilter@CW32System@@SAXAEAIAEA_K_JPEAXH@Z; CW32System::AnsiFilter(uint &,unsigned __int64 &,__int64,void *,int)
0x180050c2f  mov     esi, [rbp+arg_8]
0x180050c32  jmp     def_1800511CD; jumptable 00000001800511CD default case
0x180050c37  cmp     dword ptr [rdi+0F0h], 2
0x180050c3e  jnz     loc_18005112C
0x180050c44  jmp     def_1800511CD; jumptable 00000001800511CD default case
0x180050c49  mov     eax, [rdi+78h]
0x180050c4c  test    al, 10h
0x180050c4e  jz      short loc_180050C76
0x180050c50  and     eax, 0FFFFFFEFh
0x180050c53  xor     r8d, r8d; int
0x180050c56  xor     edx, edx; HDC
0x180050c58  mov     [rdi+78h], eax
0x180050c5b  mov     rcx, rdi; this
0x180050c5e  call    ?DrawButton@CCmbBxWinHost@@IEAAXPEAUHDC__@@H@Z; CCmbBxWinHost::DrawButton(HDC__ *,int)
0x180050c63  test    byte ptr [rdi+78h], 2
0x180050c67  jz      short loc_180050C76
0x180050c69  xor     r8d, r8d; int
0x180050c6c  mov     edx, ebx; int
0x180050c6e  mov     rcx, rdi; this
0x180050c71  call    ?HideListBox@CCmbBxWinHost@@QEAAHHH@Z; CCmbBxWinHost::HideListBox(int,int)
0x180050c76  mov     r8, [rbp+bEnable]
0x180050c7a  mov     ecx, r13d
0x180050c7d  mov     edx, [rdi+34h]
0x180050c80  test    r8, r8
0x180050c83  mov     eax, edx
0x180050c85  setz    cl
0x180050c88  shr     eax, 0Bh
0x180050c8b  and     eax, ebx
0x180050c8d  cmp     eax, ecx
0x180050c8f  jz      short loc_180050CCE
0x180050c91  mov     rcx, [rdi+10h]; hWnd
0x180050c95  mov     r8d, ebx; bErase
0x180050c98  xor     edx, edx; lpRect
0x180050c9a  call    cs:__imp_InvalidateRect
0x180050ca1  nop     dword ptr [rax+rax+00h]
0x180050ca6  mov     edx, dword ptr [rbp+bEnable]; int
0x180050ca9  mov     rcx, rdi; this
0x180050cac  call    ?SetScrollBarsForWmEnable@CTxtWinHost@@QEAAXH@Z; CTxtWinHost::SetScrollBarsForWmEnable(int)
0x180050cb1  mov     edx, dword ptr [rbp+bEnable]; bEnable
0x180050cb4  mov     rcx, [rdi+80h]; hWnd
0x180050cbb  call    cs:__imp_EnableWindow
0x180050cc2  nop     dword ptr [rax+rax+00h]
0x180050cc7  mov     edx, [rdi+34h]
0x180050cca  mov     r8, [rbp+bEnable]
0x180050cce  neg     r8
0x180050cd1  sbb     eax, eax
0x180050cd3  btr     edx, 0Bh
0x180050cd7  not     eax
0x180050cd9  and     eax, 800h
0x180050cde  or      edx, eax
0x180050ce0  mov     [rdi+34h], edx
0x180050ce3  mov     [rbp+var_38], r13
0x180050ce7  mov     r8, [rbp+bEnable]; unsigned __int64
0x180050ceb  mov     r9, r14; unsigned __int16 *
0x180050cee  mov     rcx, [rdi+80h]; hWnd
0x180050cf5  mov     edx, esi; Msg
0x180050cf7  call    ?SendMessage@CW32System@@SA_JPEAUHWND__@@I_K_J@Z; CW32System::SendMessage(HWND__ *,uint,unsigned __int64,__int64)
0x180050cfc  mov     rax, [rdi]
0x180050cff  mov     rcx, rdi
0x180050d02  mov     rax, [rax+1C0h]
0x180050d09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050d0e  jmp     def_1800511CD; jumptable 00000001800511CD default case
0x180050d13  mov     rdx, [rbp+bEnable]; unsigned __int64
0x180050d17  mov     rcx, rdi; this
0x180050d1a  call    ?OnKillFocus@CCmbBxWinHost@@QEAA_J_K_J@Z; CCmbBxWinHost::OnKillFocus(unsigned __int64,__int64)
0x180050d1f  mov     [rbp+var_38], rax
0x180050d23  test    rax, rax
0x180050d26  jz      def_1800511CD; jumptable 00000001800511CD default case
0x180050d2c  jmp     loc_1800514E1
0x180050d31  mov     rdx, [rbp+bEnable]; unsigned __int64
0x180050d35  mov     r8, r14; __int64
0x180050d38  mov     rcx, rdi; this
0x180050d3b  call    ?OnSize@CCmbBxWinHost@@QEAA_J_K_J@Z; CCmbBxWinHost::OnSize(unsigned __int64,__int64)
0x180050d40  jmp     loc_1800516ED
0x180050d45  mov     rax, [rdi]
0x180050d48  mov     rdx, r14
0x180050d4b  mov     rcx, rdi
0x180050d4e  mov     rax, [rax+1D8h]
0x180050d55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050d5a  jmp     loc_1800516ED
0x180050d5f  mov     eax, esi
0x180050d61  sub     eax, 18h
0x180050d64  jz      loc_180050F12
0x180050d6a  sub     eax, 8
0x180050d6d  jz      loc_180050EDE
0x180050d73  sub     eax, 0Bh
0x180050d76  jz      loc_180050ED9
0x180050d7c  sub     eax, 2
0x180050d7f  jz      loc_180050EB5
0x180050d85  sub     eax, 10h
0x180050d88  jz      loc_180050E72
0x180050d8e  sub     eax, 3Fh ; '?'
0x180050d91  jz      loc_180050E5C
0x180050d97  sub     eax, ebx
0x180050d99  jz      loc_1800516F1; jumptable 00000001800511CD cases 338,345,346,349-353
0x180050d9f  sub     eax, 8
0x180050da2  jz      short loc_180050DE0
0x180050da4  cmp     eax, 2
0x180050da7  jnz     def_1800511CD; jumptable 00000001800511CD default case
0x180050dad  mov     r8, [rbp+bEnable]; unsigned __int64
0x180050db1  mov     r9, r14; unsigned __int16 *
0x180050db4  mov     rcx, [rdi+80h]; hWnd
0x180050dbb  mov     edx, esi; Msg
0x180050dbd  call    ?SendMessage@CW32System@@SA_JPEAUHWND__@@I_K_J@Z; CW32System::SendMessage(HWND__ *,uint,unsigned __int64,__int64)
0x180050dc2  mov     rax, [rdi]
0x180050dc5  mov     r8, r14
0x180050dc8  mov     rdx, [rbp+bEnable]
0x180050dcc  mov     rcx, rdi
0x180050dcf  mov     rax, [rax+1C8h]
0x180050dd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050ddb  jmp     loc_1800516ED
0x180050de0  mov     r8, [rbp+bEnable]; unsigned __int64
0x180050de4  mov     r9, r14; __int64
0x180050de7  mov     edx, esi; unsigned int
0x180050de9  mov     rcx, r12; HWND
0x180050dec  call    ?DefWindowProc@CW32System@@SA_JPEAUHWND__@@I_K_J@Z; CW32System::DefWindowProc(HWND__ *,uint,unsigned __int64,__int64)
0x180050df1  mov     [rbp+var_38], rax
0x180050df5  mov     rcx, rdi
0x180050df8  mov     rax, [rdi]
0x180050dfb  mov     rax, [rax+1A8h]
0x180050e02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050e07  cmp     eax, ebx
0x180050e09  jnz     loc_1800516F1; jumptable 00000001800511CD cases 338,345,346,349-353
0x180050e0f  cmp     cs:?_dwMajorVersion@CW32System@@2KA, 4; ulong CW32System::_dwMajorVersion
0x180050e16  jnb     loc_1800516F1; jumptable 00000001800511CD cases 338,345,346,349-353
0x180050e1c  mov     rcx, r12; hWnd
0x180050e1f  call    cs:__imp_GetDC
0x180050e26  nop     dword ptr [rax+rax+00h]
0x180050e2b  mov     rbx, rax
0x180050e2e  test    rax, rax
0x180050e31  jz      loc_1800516F1; jumptable 00000001800511CD cases 338,345,346,349-353
0x180050e37  mov     r8, rax; HDC
0x180050e3a  mov     rdx, r12; HWND
0x180050e3d  mov     rcx, rdi; this
0x180050e40  call    ?DrawSunkenBorder@CTxtWinHost@@QEAAXPEAUHWND__@@PEAUHDC__@@@Z; CTxtWinHost::DrawSunkenBorder(HWND__ *,HDC__ *)
0x180050e45  mov     rdx, rbx; hDC
0x180050e48  mov     rcx, r12; hWnd
0x180050e4b  call    cs:__imp_ReleaseDC
0x180050e52  nop     dword ptr [rax+rax+00h]
0x180050e57  jmp     loc_1800516F1; jumptable 00000001800511CD cases 338,345,346,349-353
0x180050e5c  mov     r8, [rbp+bEnable]; unsigned __int64
0x180050e60  mov     r9, r14; __int64
0x180050e63  mov     edx, esi; unsigned int
0x180050e65  mov     rcx, r12; HWND
0x180050e68  call    ?DefWindowProc@CW32System@@SA_JPEAUHWND__@@I_K_J@Z; CW32System::DefWindowProc(HWND__ *,uint,unsigned __int64,__int64)
0x180050e6d  jmp     loc_1800516ED
0x180050e72  mov     rax, [rdi]
0x180050e75  lea     r8, [rbp+var_30]
0x180050e79  lea     rdx, IID_IUnknown
0x180050e80  mov     [rbp+var_30], r13
0x180050e84  mov     rcx, rdi
0x180050e87  mov     rax, [rax]
0x180050e8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050e8f  mov     r8, [rbp+var_30]; struct IUnknown *
0x180050e93  mov     rdx, [rbp+bEnable]; unsigned __int64
0x180050e97  call    ?LResultFromObject@CW32System@@SA_JAEBU_GUID@@_KPEAUIUnknown@@@Z; CW32System::LResultFromObject(_GUID const &,unsigned __int64,IUnknown *)
0x180050e9c  mov     rcx, [rbp+var_30]
0x180050ea0  mov     [rbp+var_38], rax
0x180050ea4  mov     rax, [rcx]
0x180050ea7  mov     rax, [rax+10h]
0x180050eab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050eb0  jmp     loc_1800516F1; jumptable 00000001800511CD cases 338,345,346,349-353
0x180050eb5  mov     r8d, r15d; int
0x180050eb8  xor     edx, edx; HDC
0x180050eba  mov     [rsp+80h+var_60], r14; __int64
0x180050ebf  mov     rcx, rdi; this
  ... truncated ...
```
