# RichComboBoxWndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18004f6e0`
- end: `0x1800503f4`
- name: `?RichComboBoxWndProc@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `3348`
- prototype: `__int64 __fastcall(HWND, UINT Msg, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `34`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180020740`
- `0x1800352a8`
- `0x18003bd54`
- `0x180040c1c`
- `0x180041090`
- `0x180046854`
- `0x18004d3b0`
- `0x18004d854`
- `0x18004dac4`
- `0x18004db84`
- `0x18004de00`
- `0x18004e598`
- `0x18004ec08`
- `0x18004ece0`
- `0x18004eda0`
- `0x18004ee2c`
- `0x18004ef68`
- `0x18004f020`
- `0x18004f0f8`
- `0x18004f3c4`
- `0x18004f4a8`
- `0x18004f540`
- `0x18004f6e0`
- `0x180050534`
- `0x1800509ac`
- `0x18005ba50`
- `0x1800601b0`
- `0x1800608d0`
- `0x180060b40`
- `0x180060c84`
- `0x1800612d8`
- `0x180069ec0`
- `0x18008f770`
- `0x180092010`

## import_xrefs

- `USER32!GetWindowLongPtrW` at `0x18004f716`
- `USER32!GetWindowLongPtrW` at `0x18004f7a2`
- `USER32!GetWindowLongPtrW` at `0x18004f716`
- `USER32!GetWindowLongPtrW` at `0x18004f7a2`
- `USER32!DestroyWindow` at `0x18004f76e`
- `USER32!DestroyWindow` at `0x18004f76e`
- `USER32!ReleaseDC` at `0x18004fad3`
- `USER32!ReleaseDC` at `0x180050228`
- `USER32!ReleaseDC` at `0x18004fad3`
- `USER32!ReleaseDC` at `0x180050228`
- `USER32!GetDC` at `0x18004faad`
- `USER32!GetDC` at `0x1800501f0`
- `USER32!GetDC` at `0x18004faad`
- `USER32!GetDC` at `0x1800501f0`
- `USER32!EnableWindow` at `0x18004f94f`
- `USER32!EnableWindow` at `0x18004f94f`
- `USER32!InvalidateRect` at `0x18004f934`
- `USER32!InvalidateRect` at `0x18004f934`

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
0x18004f6e0  mov     [rsp-38h+arg_0], rbx
0x18004f6e5  mov     [rsp-38h+bEnable], r8
0x18004f6ea  mov     [rsp-38h+arg_8], edx
0x18004f6ee  push    rbp
0x18004f6ef  push    rsi
0x18004f6f0  push    rdi
0x18004f6f1  push    r12
0x18004f6f3  push    r13
0x18004f6f5  push    r14
0x18004f6f7  push    r15
0x18004f6f9  mov     rbp, rsp
0x18004f6fc  sub     rsp, 80h
0x18004f703  mov     esi, edx
0x18004f705  mov     ebx, 1
0x18004f70a  xor     edx, edx; nIndex
0x18004f70c  mov     [rbp+var_38], rbx
0x18004f710  mov     r14, r9
0x18004f713  mov     r12, rcx
0x18004f716  call    cs:__imp_GetWindowLongPtrW
0x18004f71c  mov     rdi, rax
0x18004f71f  xor     r13d, r13d
0x18004f722  mov     eax, esi
0x18004f724  sub     eax, ebx
0x18004f726  jz      short loc_18004F78D
0x18004f728  sub     eax, ebx
0x18004f72a  jz      short loc_18004F741
0x18004f72c  cmp     eax, 7Fh
0x18004f72f  jnz     short loc_18004F7AB
0x18004f731  mov     rdx, r14; struct tagCREATESTRUCTW *
0x18004f734  mov     rcx, r12; HWND
0x18004f737  call    ?OnNCCreate@CCmbBxWinHost@@SA_JPEAUHWND__@@PEBUtagCREATESTRUCTW@@@Z; CCmbBxWinHost::OnNCCreate(HWND__ *,tagCREATESTRUCTW const *)
0x18004f73c  jmp     loc_180050376
0x18004f741  test    rdi, rdi
0x18004f744  jz      loc_18004F7CC
0x18004f74a  mov     rcx, [rdi+0F8h]
0x18004f751  test    rcx, rcx
0x18004f754  jz      short loc_18004F762
0x18004f756  mov     rax, [rcx]
0x18004f759  mov     rax, [rax+10h]
0x18004f75d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f762  mov     rcx, [rdi+80h]; hWnd
0x18004f769  test    rcx, rcx
0x18004f76c  jz      short loc_18004F774
0x18004f76e  call    cs:__imp_DestroyWindow
0x18004f774  mov     rcx, rdi; this
0x18004f777  call    ?Shutdown@CTxtWinHost@@QEAAXXZ; CTxtWinHost::Shutdown(void)
0x18004f77c  mov     rax, [rdi]
0x18004f77f  mov     rcx, rdi
0x18004f782  mov     rax, [rax+10h]
0x18004f786  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f78b  jmp     short loc_18004F7CC
0x18004f78d  test    rdi, rdi
0x18004f790  jnz     short loc_18004F7C6
0x18004f792  mov     rdx, r14; struct tagCREATESTRUCTW *
0x18004f795  mov     rcx, r12; HWND
0x18004f798  call    ?OnNCCreate@CCmbBxWinHost@@SA_JPEAUHWND__@@PEBUtagCREATESTRUCTW@@@Z; CCmbBxWinHost::OnNCCreate(HWND__ *,tagCREATESTRUCTW const *)
0x18004f79d  xor     edx, edx; nIndex
0x18004f79f  mov     rcx, r12; hWnd
0x18004f7a2  call    cs:__imp_GetWindowLongPtrW
0x18004f7a8  mov     rdi, rax
0x18004f7ab  test    rdi, rdi
0x18004f7ae  jnz     short loc_18004F7C6
0x18004f7b0  mov     r8, [rbp+bEnable]; unsigned __int64
0x18004f7b4  mov     r9, r14; __int64
0x18004f7b7  mov     edx, esi; unsigned int
0x18004f7b9  mov     rcx, r12; HWND
0x18004f7bc  call    ?DefWindowProc@CW32System@@SA_JPEAUHWND__@@I_K_J@Z; CW32System::DefWindowProc(HWND__ *,uint,unsigned __int64,__int64)
0x18004f7c1  jmp     loc_180050376
0x18004f7c6  cmp     [rdi+20h], r13
0x18004f7ca  jnz     short loc_18004F7D3
0x18004f7cc  xor     eax, eax
0x18004f7ce  jmp     loc_180050376
0x18004f7d3  mov     rax, [rdi]
0x18004f7d6  mov     rcx, rdi
0x18004f7d9  mov     rax, [rax+8]
0x18004f7dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f7e2  mov     eax, 149h
0x18004f7e7  mov     ecx, 43Fh
0x18004f7ec  mov     r15d, 3
0x18004f7f2  cmp     esi, eax
0x18004f7f4  ja      loc_18004FE1C
0x18004f7fa  jz      loc_18004FE12
0x18004f800  mov     eax, 0B2h
0x18004f805  cmp     esi, eax
0x18004f807  ja      loc_18004FBA4
0x18004f80d  jz      loc_180050363; jumptable 000000018004FE4F cases 338,345,346,349-353
0x18004f813  cmp     esi, 15h
0x18004f816  ja      loc_18004F9ED
0x18004f81c  jz      loc_18004F975
0x18004f822  mov     eax, esi
0x18004f824  sub     eax, ebx
0x18004f826  jz      loc_18004F9D3
0x18004f82c  sub     eax, 4
0x18004f82f  jz      loc_18004F9BF
0x18004f835  sub     eax, 2
0x18004f838  jz      loc_180050049
0x18004f83e  sub     eax, ebx
0x18004f840  jz      loc_18004F9A1
0x18004f846  sub     eax, 2
0x18004f849  jz      loc_18004F8E3
0x18004f84f  sub     eax, 2
0x18004f852  jz      short loc_18004F8D1
0x18004f854  sub     eax, ebx
0x18004f856  jz      short loc_18004F890
0x18004f858  sub     eax, ebx
0x18004f85a  jz      short loc_18004F871
0x18004f85c  cmp     eax, ebx
0x18004f85e  jnz     def_18004FE4F; jumptable 000000018004FE4F default case
0x18004f864  mov     rcx, rdi; this
0x18004f867  call    ?OnPaint@CCmbBxWinHost@@QEAA_J_K_J@Z; CCmbBxWinHost::OnPaint(unsigned __int64,__int64)
0x18004f86c  jmp     loc_18005035F
0x18004f871  cmp     cs:?_dwPlatformId@CW32System@@0KA, ebx; ulong CW32System::_dwPlatformId
0x18004f877  mov     [rbp+var_28], r13
0x18004f87b  jz      short loc_18004F88A
0x18004f87d  test    dword ptr [rdi+34h], 40000h
0x18004f884  jz      def_18004FE4F; jumptable 000000018004FE4F default case
0x18004f88a  lea     r9, [rbp+var_28]
0x18004f88e  jmp     short loc_18004F8B4
0x18004f890  cmp     cs:?_dwPlatformId@CW32System@@0KA, ebx; ulong CW32System::_dwPlatformId
0x18004f896  xorps   xmm0, xmm0
0x18004f899  movups  xmmword ptr [rbp+var_20], xmm0
0x18004f89d  movups  xmmword ptr [rbp+var_20+0Ch], xmm0
0x18004f8a1  jz      short loc_18004F8B0
0x18004f8a3  test    dword ptr [rdi+34h], 40000h
0x18004f8aa  jz      def_18004FE4F; jumptable 000000018004FE4F default case
0x18004f8b0  lea     r9, [rbp+var_20]; void *
0x18004f8b4  mov     r8, r14; __int64
0x18004f8b7  mov     dword ptr [rsp+80h+var_60], r13d; int
0x18004f8bc  lea     rdx, [rbp+bEnable]; unsigned __int64 *
0x18004f8c0  lea     rcx, [rbp+arg_8]; unsigned int *
0x18004f8c4  call    ?AnsiFilter@CW32System@@SAXAEAIAEA_K_JPEAXH@Z; CW32System::AnsiFilter(uint &,unsigned __int64 &,__int64,void *,int)
0x18004f8c9  mov     esi, [rbp+arg_8]
0x18004f8cc  jmp     def_18004FE4F; jumptable 000000018004FE4F default case
0x18004f8d1  cmp     dword ptr [rdi+0F0h], 2
0x18004f8d8  jnz     loc_18004FDAE
0x18004f8de  jmp     def_18004FE4F; jumptable 000000018004FE4F default case
0x18004f8e3  mov     eax, [rdi+78h]
0x18004f8e6  test    al, 10h
0x18004f8e8  jz      short loc_18004F910
0x18004f8ea  and     eax, 0FFFFFFEFh
0x18004f8ed  xor     r8d, r8d; int
0x18004f8f0  xor     edx, edx; HDC
0x18004f8f2  mov     [rdi+78h], eax
0x18004f8f5  mov     rcx, rdi; this
0x18004f8f8  call    ?DrawButton@CCmbBxWinHost@@IEAAXPEAUHDC__@@H@Z; CCmbBxWinHost::DrawButton(HDC__ *,int)
0x18004f8fd  test    byte ptr [rdi+78h], 2
0x18004f901  jz      short loc_18004F910
0x18004f903  xor     r8d, r8d; int
0x18004f906  mov     edx, ebx; int
0x18004f908  mov     rcx, rdi; this
0x18004f90b  call    ?HideListBox@CCmbBxWinHost@@QEAAHHH@Z; CCmbBxWinHost::HideListBox(int,int)
0x18004f910  mov     r8, [rbp+bEnable]
0x18004f914  mov     ecx, r13d
0x18004f917  mov     edx, [rdi+34h]
0x18004f91a  test    r8, r8
0x18004f91d  mov     eax, edx
0x18004f91f  setz    cl
0x18004f922  shr     eax, 0Bh
0x18004f925  and     eax, ebx
0x18004f927  cmp     eax, ecx
0x18004f929  jz      short loc_18004F95C
0x18004f92b  mov     rcx, [rdi+10h]; hWnd
0x18004f92f  mov     r8d, ebx; bErase
0x18004f932  xor     edx, edx; lpRect
0x18004f934  call    cs:__imp_InvalidateRect
0x18004f93a  mov     edx, dword ptr [rbp+bEnable]; int
0x18004f93d  mov     rcx, rdi; this
0x18004f940  call    ?SetScrollBarsForWmEnable@CTxtWinHost@@QEAAXH@Z; CTxtWinHost::SetScrollBarsForWmEnable(int)
0x18004f945  mov     edx, dword ptr [rbp+bEnable]; bEnable
0x18004f948  mov     rcx, [rdi+80h]; hWnd
0x18004f94f  call    cs:__imp_EnableWindow
0x18004f955  mov     edx, [rdi+34h]
0x18004f958  mov     r8, [rbp+bEnable]
0x18004f95c  neg     r8
0x18004f95f  sbb     eax, eax
0x18004f961  btr     edx, 0Bh
0x18004f965  not     eax
0x18004f967  and     eax, 800h
0x18004f96c  or      edx, eax
0x18004f96e  mov     [rdi+34h], edx
0x18004f971  mov     [rbp+var_38], r13
0x18004f975  mov     r8, [rbp+bEnable]; unsigned __int64
0x18004f979  mov     r9, r14; unsigned __int16 *
0x18004f97c  mov     rcx, [rdi+80h]; hWnd
0x18004f983  mov     edx, esi; Msg
0x18004f985  call    ?SendMessage@CW32System@@SA_JPEAUHWND__@@I_K_J@Z; CW32System::SendMessage(HWND__ *,uint,unsigned __int64,__int64)
0x18004f98a  mov     rax, [rdi]
0x18004f98d  mov     rcx, rdi
0x18004f990  mov     rax, [rax+1C0h]
0x18004f997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f99c  jmp     def_18004FE4F; jumptable 000000018004FE4F default case
0x18004f9a1  mov     rdx, [rbp+bEnable]; unsigned __int64
0x18004f9a5  mov     rcx, rdi; this
0x18004f9a8  call    ?OnKillFocus@CCmbBxWinHost@@QEAA_J_K_J@Z; CCmbBxWinHost::OnKillFocus(unsigned __int64,__int64)
0x18004f9ad  mov     [rbp+var_38], rax
0x18004f9b1  test    rax, rax
0x18004f9b4  jz      def_18004FE4F; jumptable 000000018004FE4F default case
0x18004f9ba  jmp     loc_18005015F
0x18004f9bf  mov     rdx, [rbp+bEnable]; unsigned __int64
0x18004f9c3  mov     r8, r14; __int64
0x18004f9c6  mov     rcx, rdi; this
0x18004f9c9  call    ?OnSize@CCmbBxWinHost@@QEAA_J_K_J@Z; CCmbBxWinHost::OnSize(unsigned __int64,__int64)
0x18004f9ce  jmp     loc_18005035F
0x18004f9d3  mov     rax, [rdi]
0x18004f9d6  mov     rdx, r14
0x18004f9d9  mov     rcx, rdi
0x18004f9dc  mov     rax, [rax+1D8h]
0x18004f9e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f9e8  jmp     loc_18005035F
0x18004f9ed  mov     eax, esi
0x18004f9ef  sub     eax, 18h
0x18004f9f2  jz      loc_18004FB94
0x18004f9f8  sub     eax, 8
0x18004f9fb  jz      loc_18004FB60
0x18004fa01  sub     eax, 0Bh
0x18004fa04  jz      loc_18004FB5B
0x18004fa0a  sub     eax, 2
0x18004fa0d  jz      loc_18004FB37
0x18004fa13  sub     eax, 10h
0x18004fa16  jz      loc_18004FAF4
0x18004fa1c  sub     eax, 3Fh ; '?'
0x18004fa1f  jz      loc_18004FADE
0x18004fa25  sub     eax, ebx
0x18004fa27  jz      loc_180050363; jumptable 000000018004FE4F cases 338,345,346,349-353
0x18004fa2d  sub     eax, 8
0x18004fa30  jz      short loc_18004FA6E
0x18004fa32  cmp     eax, 2
0x18004fa35  jnz     def_18004FE4F; jumptable 000000018004FE4F default case
0x18004fa3b  mov     r8, [rbp+bEnable]; unsigned __int64
0x18004fa3f  mov     r9, r14; unsigned __int16 *
0x18004fa42  mov     rcx, [rdi+80h]; hWnd
0x18004fa49  mov     edx, esi; Msg
0x18004fa4b  call    ?SendMessage@CW32System@@SA_JPEAUHWND__@@I_K_J@Z; CW32System::SendMessage(HWND__ *,uint,unsigned __int64,__int64)
0x18004fa50  mov     rax, [rdi]
0x18004fa53  mov     r8, r14
0x18004fa56  mov     rdx, [rbp+bEnable]
0x18004fa5a  mov     rcx, rdi
0x18004fa5d  mov     rax, [rax+1C8h]
0x18004fa64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fa69  jmp     loc_18005035F
0x18004fa6e  mov     r8, [rbp+bEnable]; unsigned __int64
0x18004fa72  mov     r9, r14; __int64
0x18004fa75  mov     edx, esi; unsigned int
0x18004fa77  mov     rcx, r12; HWND
0x18004fa7a  call    ?DefWindowProc@CW32System@@SA_JPEAUHWND__@@I_K_J@Z; CW32System::DefWindowProc(HWND__ *,uint,unsigned __int64,__int64)
0x18004fa7f  mov     [rbp+var_38], rax
0x18004fa83  mov     rcx, rdi
0x18004fa86  mov     rax, [rdi]
0x18004fa89  mov     rax, [rax+1A8h]
0x18004fa90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fa95  cmp     eax, ebx
0x18004fa97  jnz     loc_180050363; jumptable 000000018004FE4F cases 338,345,346,349-353
0x18004fa9d  cmp     cs:?_dwMajorVersion@CW32System@@2KA, 4; ulong CW32System::_dwMajorVersion
0x18004faa4  jnb     loc_180050363; jumptable 000000018004FE4F cases 338,345,346,349-353
0x18004faaa  mov     rcx, r12; hWnd
0x18004faad  call    cs:__imp_GetDC
0x18004fab3  mov     rbx, rax
0x18004fab6  test    rax, rax
0x18004fab9  jz      loc_180050363; jumptable 000000018004FE4F cases 338,345,346,349-353
0x18004fabf  mov     r8, rax; HDC
0x18004fac2  mov     rdx, r12; HWND
0x18004fac5  mov     rcx, rdi; this
0x18004fac8  call    ?DrawSunkenBorder@CTxtWinHost@@QEAAXPEAUHWND__@@PEAUHDC__@@@Z; CTxtWinHost::DrawSunkenBorder(HWND__ *,HDC__ *)
0x18004facd  mov     rdx, rbx; hDC
0x18004fad0  mov     rcx, r12; hWnd
0x18004fad3  call    cs:__imp_ReleaseDC
0x18004fad9  jmp     loc_180050363; jumptable 000000018004FE4F cases 338,345,346,349-353
0x18004fade  mov     r8, [rbp+bEnable]; unsigned __int64
0x18004fae2  mov     r9, r14; __int64
0x18004fae5  mov     edx, esi; unsigned int
0x18004fae7  mov     rcx, r12; HWND
0x18004faea  call    ?DefWindowProc@CW32System@@SA_JPEAUHWND__@@I_K_J@Z; CW32System::DefWindowProc(HWND__ *,uint,unsigned __int64,__int64)
0x18004faef  jmp     loc_18005035F
0x18004faf4  mov     rax, [rdi]
0x18004faf7  lea     r8, [rbp+var_30]
0x18004fafb  lea     rdx, IID_IUnknown
0x18004fb02  mov     [rbp+var_30], r13
0x18004fb06  mov     rcx, rdi
0x18004fb09  mov     rax, [rax]
0x18004fb0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fb11  mov     r8, [rbp+var_30]; struct IUnknown *
0x18004fb15  mov     rdx, [rbp+bEnable]; unsigned __int64
0x18004fb19  call    ?LResultFromObject@CW32System@@SA_JAEBU_GUID@@_KPEAUIUnknown@@@Z; CW32System::LResultFromObject(_GUID const &,unsigned __int64,IUnknown *)
0x18004fb1e  mov     rcx, [rbp+var_30]
0x18004fb22  mov     [rbp+var_38], rax
0x18004fb26  mov     rax, [rcx]
0x18004fb29  mov     rax, [rax+10h]
0x18004fb2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fb32  jmp     loc_180050363; jumptable 000000018004FE4F cases 338,345,346,349-353
0x18004fb37  mov     r8d, r15d; int
0x18004fb3a  xor     edx, edx; HDC
0x18004fb3c  mov     [rsp+80h+var_60], r14; __int64
0x18004fb41  mov     rcx, rdi; this
0x18004fb44  call    ?CbMessageItemHandler@CCmbBxWinHost@@QEAA_JPEAUHDC__@@H_K_J@Z; CCmbBxWinHost::CbMessageItemHandler(HDC__ *,int,unsigned __int64,__int64)
0x18004fb49  mov     [rbp+var_38], rax
0x18004fb4d  test    rax, rax
0x18004fb50  jnz     loc_180050363; jumptable 000000018004FE4F cases 338,345,346,349-353
0x18004fb56  jmp     loc_18005015F
0x18004fb5b  mov     r8d, ebx
0x18004fb5e  jmp     short loc_18004FB3A
  ... truncated ...
```
