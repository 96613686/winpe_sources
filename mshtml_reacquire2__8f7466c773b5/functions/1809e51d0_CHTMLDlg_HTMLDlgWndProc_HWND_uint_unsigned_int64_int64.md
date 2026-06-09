# CHTMLDlg::HTMLDlgWndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x1809e51d0`
- end: `0x1809e569a`
- name: `?HTMLDlgWndProc@CHTMLDlg@@CA_JPEAUHWND__@@I_K_J@Z`
- size: `1226`
- prototype: `__int64 __fastcall(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)`
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x18021a4b0`
- `0x18021b1b0`
- `0x1807e4524`
- `0x1809e4164`
- `0x1809e51d0`
- `0x1809e6794`
- `0x1809e7b70`
- `0x1809e8408`
- `0x1809e8544`
- `0x1809ee220`
- `0x1810f65c0`
- `0x181104010`

## import_xrefs

- `USER32!MoveWindow` at `0x1809e53bc`
- `USER32!MoveWindow` at `0x1809e53bc`
- `USER32!RemoveMenu` at `0x1809e54e2`
- `USER32!RemoveMenu` at `0x1809e54ff`
- `USER32!RemoveMenu` at `0x1809e551c`
- `USER32!RemoveMenu` at `0x1809e5547`
- `USER32!RemoveMenu` at `0x1809e54e2`
- `USER32!RemoveMenu` at `0x1809e54ff`
- `USER32!RemoveMenu` at `0x1809e551c`
- `USER32!RemoveMenu` at `0x1809e5547`
- `USER32!GetSystemMenu` at `0x1809e54b9`
- `USER32!GetSystemMenu` at `0x1809e54b9`
- `USER32!SetWindowLongPtrW` at `0x1809e5297`
- `USER32!SetWindowLongPtrW` at `0x1809e5562`
- `USER32!SetWindowLongPtrW` at `0x1809e5297`
- `USER32!SetWindowLongPtrW` at `0x1809e5562`
- `USER32!DefWindowProcW` at `0x1809e5670`
- `USER32!DefWindowProcW` at `0x1809e5670`
- `USER32!PostMessageW` at `0x1809e544e`
- `USER32!PostMessageW` at `0x1809e544e`
- `USER32!GetWindowLongPtrW` at `0x1809e5202`
- `USER32!GetWindowLongPtrW` at `0x1809e5202`
- `USER32!GetClientRect` at `0x1809e53cf`
- `USER32!GetClientRect` at `0x1809e53cf`
- `USER32!SendMessageW` at `0x1809e5613`
- `USER32!SendMessageW` at `0x1809e5659`
- `USER32!SendMessageW` at `0x1809e5613`
- `USER32!SendMessageW` at `0x1809e5659`
- `USER32!IsIconic` at `0x1809e52ba`
- `USER32!IsIconic` at `0x1809e52ba`
- `USER32!GetWindowRect` at `0x1809e52f2`
- `USER32!GetWindowRect` at `0x1809e5334`
- `USER32!GetWindowRect` at `0x1809e52f2`
- `USER32!GetWindowRect` at `0x1809e5334`
- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x1809e5637`
- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x1809e5637`

## pseudocode

```c
__int64 __fastcall CHTMLDlg::HTMLDlgWndProc(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)
{
  int v8; // edx
  LONG_PTR WindowLongPtrW; // rbx
  CBase *v10; // rbx
  int v11; // eax
  int v12; // ecx
  int bottom; // r10d
  HWND v14; // rcx
  HWND v16; // rcx
  UINT v17; // edx
  __int64 v18; // rcx
  struct ITrustState *v19; // r8
  HMENU SystemMenu; // rax
  HMENU v21; // r14
  __int64 v22; // rcx
  __int64 v23; // rcx
  struct tagRECT Rect; // [rsp+30h] [rbp-38h] BYREF
  struct tagRECT v25; // [rsp+40h] [rbp-28h] BYREF

  WindowLongPtrW = GetWindowLongPtrW(hWnd, -21);
  if ( WindowLongPtrW )
    goto LABEL_4;
  if ( Msg == 129 )
  {
LABEL_14:
    v10 = *(CBase **)lParam;
    SetWindowLongPtrW(hWnd, -21, *(_QWORD *)lParam);
    *((_QWORD *)v10 + 36) = hWnd;
    CBase::PrivateAddRef(v10);
    return DefWindowProcW(hWnd, Msg, wParam, lParam);
  }
  if ( Msg == 1 )
  {
LABEL_4:
    if ( Msg > 0x82 )
    {
      switch ( Msg )
      {
        case 0x86u:
          v23 = *(_QWORD *)(WindowLongPtrW + 160);
          *(_QWORD *)&Rect.left = 0;
          if ( IUnknown_GetWindow(*(IUnknown **)(v23 + 200), (HWND *)&Rect) >= 0 )
            SendMessageW(*(HWND *)&Rect.left, 0x8064u, 0x86u, wParam);
          return DefWindowProcW(hWnd, Msg, wParam, lParam);
        case 0x30Fu:
        case 0x311u:
          v22 = *(_QWORD *)(WindowLongPtrW + 216);
          if ( v22 )
          {
            *(_QWORD *)&Rect.left = 0;
            if ( (*(int (__fastcall **)(__int64, struct tagRECT *))(*(_QWORD *)v22 + 24LL))(v22, &Rect) >= 0 )
              return SendMessageW(*(HWND *)&Rect.left, Msg, wParam, lParam);
          }
          return DefWindowProcW(hWnd, Msg, wParam, lParam);
        case 0x402u:
          CHTMLDlg::SetShowable((CHTMLDlg *)WindowLongPtrW, v8);
          return DefWindowProcW(hWnd, Msg, wParam, lParam);
        case 0x403u:
          CHTMLDlg::UnlockParentWindow((CHTMLDlg *)WindowLongPtrW);
          return DefWindowProcW(hWnd, Msg, wParam, lParam);
        case 0x404u:
          return CHTMLDlg::Close((CHTMLDlg *)WindowLongPtrW);
      }
      if ( Msg != 1029 )
        return DefWindowProcW(hWnd, Msg, wParam, lParam);
      *(_BYTE *)(WindowLongPtrW + 442) = 1;
    }
    else
    {
      switch ( Msg )
      {
        case 0x82u:
          SetWindowLongPtrW(hWnd, -21, 0);
          CBase::PrivateRelease((CBase *)WindowLongPtrW);
          return DefWindowProcW(hWnd, Msg, wParam, lParam);
        case 1u:
          SystemMenu = GetSystemMenu(hWnd, 0);
          v21 = SystemMenu;
          if ( SystemMenu )
          {
            if ( !*(_DWORD *)(WindowLongPtrW + 72) )
              RemoveMenu(SystemMenu, 0xF020u, 0);
            if ( !*(_DWORD *)(WindowLongPtrW + 76) )
              RemoveMenu(v21, 0xF030u, 0);
            if ( !*(_DWORD *)(WindowLongPtrW + 84) )
              RemoveMenu(v21, 0xF000u, 0);
            if ( !*(_DWORD *)(WindowLongPtrW + 72) && !*(_DWORD *)(WindowLongPtrW + 76) )
              RemoveMenu(v21, 0xF120u, 0);
          }
          return DefWindowProcW(hWnd, Msg, wParam, lParam);
        case 2u:
          CHTMLDlgSite::DestroyNavigationBar(*(CHTMLDlgSite **)(WindowLongPtrW + 160));
          CTrustStateImpl::Connect((CTrustStateImpl *)(*(_QWORD *)(WindowLongPtrW + 160) + 96LL), 0, v19);
          *(_QWORD *)(WindowLongPtrW + 288) = 0;
          break;
        case 6u:
          v18 = *(_QWORD *)(WindowLongPtrW + 224);
          if ( v18 )
            (*(void (__fastcall **)(__int64, bool))(*(_QWORD *)v18 + 48LL))(v18, (_WORD)wParam != 0);
          break;
        case 0x10u:
          if ( !*(_BYTE *)(WindowLongPtrW + 441) )
          {
            v16 = *(HWND *)(WindowLongPtrW + 288);
            *(_BYTE *)(WindowLongPtrW + 441) = 1;
            v17 = 1029;
            if ( (*(_BYTE *)(WindowLongPtrW + 156) & 2) == 0 )
              v17 = 1028;
            PostMessageW(v16, v17, 0, 0);
          }
          break;
        case 0x14u:
          if ( *(_QWORD *)(WindowLongPtrW + 144) )
            return 1;
          return DefWindowProcW(hWnd, Msg, wParam, lParam);
        case 0x24u:
          *(_DWORD *)(lParam + 24) = g_dwMinDialogWidth;
          *(_DWORD *)(lParam + 28) = g_dwMinDialogHeight;
          return DefWindowProcW(hWnd, Msg, wParam, lParam);
        case 0x47u:
          if ( !IsIconic(hWnd) )
          {
            v11 = *(_DWORD *)(WindowLongPtrW + 464) & 0x900;
            Rect = 0;
            if ( v11 != 2304 )
            {
              GetWindowRect(hWnd, &Rect);
              v12 = *(_DWORD *)(WindowLongPtrW + 464);
              bottom = Rect.bottom;
              if ( (v12 & 0x100) == 0 )
              {
                bottom = *(_DWORD *)(WindowLongPtrW + 176) + Rect.bottom;
                v14 = *(HWND *)(WindowLongPtrW + 296);
                Rect.bottom = bottom;
                if ( v14 )
                {
                  v25 = 0;
                  GetWindowRect(v14, &v25);
                  bottom = v25.bottom - v25.top + Rect.bottom;
                  Rect.bottom = bottom;
                }
                *(_DWORD *)(WindowLongPtrW + 464) |= 0x100u;
                v12 = *(_DWORD *)(WindowLongPtrW + 464);
              }
              if ( (v12 & 0x800) == 0 )
              {
                bottom += *(_DWORD *)(WindowLongPtrW + 416);
                Rect.right += *(_DWORD *)(WindowLongPtrW + 412);
                Rect.bottom = bottom;
                *(_DWORD *)(WindowLongPtrW + 464) = v12 | 0x800;
              }
              if ( (*(_BYTE *)(WindowLongPtrW + 156) & 4) != 0 )
              {
                CHTMLDlg::VerifyDialogRect((CHTMLDlg *)WindowLongPtrW, &Rect, 0);
                bottom = Rect.bottom;
              }
              MoveWindow(hWnd, Rect.left, Rect.top, Rect.right - Rect.left, bottom - Rect.top, 1);
            }
            GetClientRect(hWnd, &Rect);
            CHTMLDlg::OnWindowPosChanged((CHTMLDlg *)WindowLongPtrW, &Rect);
          }
          break;
        case 0x81u:
          goto LABEL_14;
        default:
          return DefWindowProcW(hWnd, Msg, wParam, lParam);
      }
    }
    return 0;
  }
  return DefWindowProcW(hWnd, Msg, wParam, lParam);
}

```

## disassembly

```asm
0x1809e51d0  push    rbp
0x1809e51d2  push    rbx
0x1809e51d3  push    rsi
0x1809e51d4  push    rdi
0x1809e51d5  push    r12
0x1809e51d7  push    r13
0x1809e51d9  push    r14
0x1809e51db  push    r15
0x1809e51dd  mov     rbp, rsp
0x1809e51e0  sub     rsp, 68h
0x1809e51e4  mov     rax, cs:__security_cookie
0x1809e51eb  xor     rax, rsp
0x1809e51ee  mov     [rbp+var_18], rax
0x1809e51f2  mov     edi, edx
0x1809e51f4  mov     r15, r9
0x1809e51f7  mov     edx, 0FFFFFFEBh; nIndex
0x1809e51fc  mov     r12, r8
0x1809e51ff  mov     rsi, rcx
0x1809e5202  call    cs:__imp_GetWindowLongPtrW
0x1809e5209  nop     dword ptr [rax+rax+00h]
0x1809e520e  xor     r13d, r13d
0x1809e5211  mov     r14d, 1
0x1809e5217  mov     rbx, rax
0x1809e521a  test    rax, rax
0x1809e521d  jnz     short loc_1809E5230
0x1809e521f  cmp     edi, 81h
0x1809e5225  jz      short loc_1809E5289
0x1809e5227  cmp     edi, r14d
0x1809e522a  jnz     loc_1809E5665
0x1809e5230  mov     eax, 82h
0x1809e5235  cmp     edi, eax
0x1809e5237  ja      loc_1809E557B
0x1809e523d  jz      loc_1809E5558
0x1809e5243  mov     eax, edi
0x1809e5245  sub     eax, r14d
0x1809e5248  jz      loc_1809E54B4
0x1809e524e  sub     eax, r14d
0x1809e5251  jz      loc_1809E548A
0x1809e5257  sub     eax, 4
0x1809e525a  jz      loc_1809E545F
0x1809e5260  sub     eax, 0Ah
0x1809e5263  jz      loc_1809E541A
0x1809e5269  sub     eax, 4
0x1809e526c  jz      loc_1809E5405
0x1809e5272  sub     eax, 10h
0x1809e5275  jz      loc_1809E53EC
0x1809e527b  sub     eax, 23h ; '#'
0x1809e527e  jz      short loc_1809E52B7
0x1809e5280  cmp     eax, 3Ah ; ':'
0x1809e5283  jnz     loc_1809E5665
0x1809e5289  mov     rbx, [r15]
0x1809e528c  mov     edx, 0FFFFFFEBh; nIndex
0x1809e5291  mov     r8, rbx; dwNewLong
0x1809e5294  mov     rcx, rsi; hWnd
0x1809e5297  call    cs:__imp_SetWindowLongPtrW
0x1809e529e  nop     dword ptr [rax+rax+00h]
0x1809e52a3  mov     rcx, rbx; this
0x1809e52a6  mov     [rbx+120h], rsi
0x1809e52ad  call    ?PrivateAddRef@CBase@@UEAAKXZ; CBase::PrivateAddRef(void)
0x1809e52b2  jmp     loc_1809E5665
0x1809e52b7  mov     rcx, rsi; hWnd
0x1809e52ba  call    cs:__imp_IsIconic
0x1809e52c1  nop     dword ptr [rax+rax+00h]
0x1809e52c6  test    eax, eax
0x1809e52c8  jnz     loc_1809E55B5
0x1809e52ce  mov     eax, [rbx+1D0h]
0x1809e52d4  mov     ecx, 900h
0x1809e52d9  and     eax, ecx
0x1809e52db  xorps   xmm0, xmm0
0x1809e52de  movdqu  xmmword ptr [rbp+Rect.left], xmm0
0x1809e52e3  cmp     eax, ecx
0x1809e52e5  jz      loc_1809E53C8
0x1809e52eb  lea     rdx, [rbp+Rect]; lpRect
0x1809e52ef  mov     rcx, rsi; hWnd
0x1809e52f2  call    cs:__imp_GetWindowRect
0x1809e52f9  nop     dword ptr [rax+rax+00h]
0x1809e52fe  mov     ecx, [rbx+1D0h]
0x1809e5304  mov     edi, 100h
0x1809e5309  mov     r10d, [rbp+Rect.bottom]
0x1809e530d  test    edi, ecx
0x1809e530f  jnz     short loc_1809E535D
0x1809e5311  add     r10d, [rbx+0B0h]
0x1809e5318  mov     rcx, [rbx+128h]; hWnd
0x1809e531f  mov     [rbp+Rect.bottom], r10d
0x1809e5323  test    rcx, rcx
0x1809e5326  jz      short loc_1809E5351
0x1809e5328  xorps   xmm0, xmm0
0x1809e532b  lea     rdx, [rbp+var_28]; lpRect
0x1809e532f  movdqu  xmmword ptr [rbp+var_28.left], xmm0
0x1809e5334  call    cs:__imp_GetWindowRect
0x1809e533b  nop     dword ptr [rax+rax+00h]
0x1809e5340  mov     r10d, [rbp+Rect.bottom]
0x1809e5344  mov     eax, [rbp+var_28.bottom]
0x1809e5347  sub     eax, [rbp+var_28.top]
0x1809e534a  add     r10d, eax
0x1809e534d  mov     [rbp+Rect.bottom], r10d
0x1809e5351  or      [rbx+1D0h], edi
0x1809e5357  mov     ecx, [rbx+1D0h]
0x1809e535d  mov     edx, 800h
0x1809e5362  test    edx, ecx
0x1809e5364  jnz     short loc_1809E5382
0x1809e5366  add     r10d, [rbx+1A0h]
0x1809e536d  mov     eax, [rbx+19Ch]
0x1809e5373  add     [rbp+Rect.right], eax
0x1809e5376  or      ecx, edx
0x1809e5378  mov     [rbp+Rect.bottom], r10d
0x1809e537c  mov     [rbx+1D0h], ecx
0x1809e5382  test    byte ptr [rbx+9Ch], 4
0x1809e5389  jz      short loc_1809E539E
0x1809e538b  xor     r8d, r8d; HWND
0x1809e538e  lea     rdx, [rbp+Rect]; struct tagRECT *
0x1809e5392  mov     rcx, rbx; this
0x1809e5395  call    ?VerifyDialogRect@CHTMLDlg@@QEAAXPEAUtagRECT@@PEAUHWND__@@@Z; CHTMLDlg::VerifyDialogRect(tagRECT *,HWND__ *)
0x1809e539a  mov     r10d, [rbp+Rect.bottom]
0x1809e539e  mov     r8d, [rbp+Rect.top]; Y
0x1809e53a2  mov     rcx, rsi; hWnd
0x1809e53a5  mov     r9d, [rbp+Rect.right]
0x1809e53a9  sub     r10d, r8d
0x1809e53ac  mov     edx, [rbp+Rect.left]; X
0x1809e53af  sub     r9d, edx; nWidth
0x1809e53b2  mov     [rsp+68h+bRepaint], r14d; bRepaint
0x1809e53b7  mov     [rsp+68h+nHeight], r10d; nHeight
0x1809e53bc  call    cs:__imp_MoveWindow
0x1809e53c3  nop     dword ptr [rax+rax+00h]
0x1809e53c8  lea     rdx, [rbp+Rect]; lpRect
0x1809e53cc  mov     rcx, rsi; hWnd
0x1809e53cf  call    cs:__imp_GetClientRect
0x1809e53d6  nop     dword ptr [rax+rax+00h]
0x1809e53db  lea     rdx, [rbp+Rect]; struct tagRECT *
0x1809e53df  mov     rcx, rbx; this
0x1809e53e2  call    ?OnWindowPosChanged@CHTMLDlg@@AEAA_JPEAUtagRECT@@@Z; CHTMLDlg::OnWindowPosChanged(tagRECT *)
0x1809e53e7  jmp     loc_1809E55B5
0x1809e53ec  mov     eax, cs:?g_dwMinDialogWidth@@3KA; ulong g_dwMinDialogWidth
0x1809e53f2  mov     [r15+18h], eax
0x1809e53f6  mov     eax, cs:?g_dwMinDialogHeight@@3KA; ulong g_dwMinDialogHeight
0x1809e53fc  mov     [r15+1Ch], eax
0x1809e5400  jmp     loc_1809E5665
0x1809e5405  cmp     [rbx+90h], r13
0x1809e540c  jz      loc_1809E5665
0x1809e5412  mov     rax, r14
0x1809e5415  jmp     loc_1809E567C
0x1809e541a  cmp     [rbx+1B9h], r13b
0x1809e5421  jnz     loc_1809E55B5
0x1809e5427  mov     rcx, [rbx+120h]; hWnd
0x1809e542e  xor     r9d, r9d; lParam
0x1809e5431  xor     r8d, r8d; wParam
0x1809e5434  mov     [rbx+1B9h], r14b
0x1809e543b  test    byte ptr [rbx+9Ch], 2
0x1809e5442  mov     edx, 405h
0x1809e5447  jnz     short loc_1809E544E
0x1809e5449  mov     edx, 404h; Msg
0x1809e544e  call    cs:__imp_PostMessageW
0x1809e5455  nop     dword ptr [rax+rax+00h]
0x1809e545a  jmp     loc_1809E55B5
0x1809e545f  mov     rcx, [rbx+0E0h]
0x1809e5466  test    rcx, rcx
0x1809e5469  jz      loc_1809E55B5
0x1809e546f  mov     rax, [rcx]
0x1809e5472  test    r12w, r12w
0x1809e5476  mov     edx, r13d
0x1809e5479  setnz   dl
0x1809e547c  mov     rax, [rax+30h]
0x1809e5480  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1809e5485  jmp     loc_1809E55B5
0x1809e548a  mov     rcx, [rbx+0A0h]; this
0x1809e5491  call    ?DestroyNavigationBar@CHTMLDlgSite@@QEAAXXZ; CHTMLDlgSite::DestroyNavigationBar(void)
0x1809e5496  mov     rcx, [rbx+0A0h]
0x1809e549d  xor     edx, edx; struct ITrustStateNotify *
0x1809e549f  add     rcx, 60h ; '`'; this
0x1809e54a3  call    ?Connect@CTrustStateImpl@@QEAAJPEAUITrustStateNotify@@PEAUITrustState@@@Z; CTrustStateImpl::Connect(ITrustStateNotify *,ITrustState *)
0x1809e54a8  mov     [rbx+120h], r13
0x1809e54af  jmp     loc_1809E55B5
0x1809e54b4  xor     edx, edx; bRevert
0x1809e54b6  mov     rcx, rsi; hWnd
0x1809e54b9  call    cs:__imp_GetSystemMenu
0x1809e54c0  nop     dword ptr [rax+rax+00h]
0x1809e54c5  mov     r14, rax
0x1809e54c8  test    rax, rax
0x1809e54cb  jz      loc_1809E5665
0x1809e54d1  cmp     [rbx+48h], r13d
0x1809e54d5  jnz     short loc_1809E54EE
0x1809e54d7  xor     r8d, r8d; uFlags
0x1809e54da  mov     edx, 0F020h; uPosition
0x1809e54df  mov     rcx, rax; hMenu
0x1809e54e2  call    cs:__imp_RemoveMenu
0x1809e54e9  nop     dword ptr [rax+rax+00h]
0x1809e54ee  cmp     [rbx+4Ch], r13d
0x1809e54f2  jnz     short loc_1809E550B
0x1809e54f4  xor     r8d, r8d; uFlags
0x1809e54f7  mov     edx, 0F030h; uPosition
0x1809e54fc  mov     rcx, r14; hMenu
0x1809e54ff  call    cs:__imp_RemoveMenu
0x1809e5506  nop     dword ptr [rax+rax+00h]
0x1809e550b  cmp     [rbx+54h], r13d
0x1809e550f  jnz     short loc_1809E5528
0x1809e5511  xor     r8d, r8d; uFlags
0x1809e5514  mov     edx, 0F000h; uPosition
0x1809e5519  mov     rcx, r14; hMenu
0x1809e551c  call    cs:__imp_RemoveMenu
0x1809e5523  nop     dword ptr [rax+rax+00h]
0x1809e5528  cmp     [rbx+48h], r13d
0x1809e552c  jnz     loc_1809E5665
0x1809e5532  cmp     [rbx+4Ch], r13d
0x1809e5536  jnz     loc_1809E5665
0x1809e553c  xor     r8d, r8d; uFlags
0x1809e553f  mov     edx, 0F120h; uPosition
0x1809e5544  mov     rcx, r14; hMenu
0x1809e5547  call    cs:__imp_RemoveMenu
0x1809e554e  nop     dword ptr [rax+rax+00h]
0x1809e5553  jmp     loc_1809E5665
0x1809e5558  xor     r8d, r8d; dwNewLong
0x1809e555b  mov     rcx, rsi; hWnd
0x1809e555e  lea     edx, [r8-15h]; nIndex
0x1809e5562  call    cs:__imp_SetWindowLongPtrW
0x1809e5569  nop     dword ptr [rax+rax+00h]
0x1809e556e  mov     rcx, rbx; this
0x1809e5571  call    ?PrivateRelease@CBase@@UEAAKXZ; CBase::PrivateRelease(void)
0x1809e5576  jmp     loc_1809E5665
0x1809e557b  mov     eax, edi
0x1809e557d  sub     eax, 86h
0x1809e5582  jz      loc_1809E5621
0x1809e5588  sub     eax, 289h
0x1809e558d  jz      short loc_1809E55E3
0x1809e558f  sub     eax, 2
0x1809e5592  jz      short loc_1809E55E3
0x1809e5594  sub     eax, 0F1h
0x1809e5599  jz      short loc_1809E55D6
0x1809e559b  sub     eax, r14d
0x1809e559e  jz      short loc_1809E55C9
0x1809e55a0  sub     eax, r14d
0x1809e55a3  jz      short loc_1809E55BC
0x1809e55a5  cmp     eax, r14d
0x1809e55a8  jnz     loc_1809E5665
0x1809e55ae  mov     [rbx+1BAh], r14b
0x1809e55b5  xor     eax, eax
0x1809e55b7  jmp     loc_1809E567C
0x1809e55bc  mov     rcx, rbx; this
0x1809e55bf  call    ?Close@CHTMLDlg@@QEAA_JXZ; CHTMLDlg::Close(void)
0x1809e55c4  jmp     loc_1809E567C
0x1809e55c9  mov     rcx, rbx; this
0x1809e55cc  call    ?UnlockParentWindow@CHTMLDlg@@QEAAXXZ; CHTMLDlg::UnlockParentWindow(void)
0x1809e55d1  jmp     loc_1809E5665
0x1809e55d6  mov     rcx, rbx; this
0x1809e55d9  call    ?SetShowable@CHTMLDlg@@QEAAXH@Z; CHTMLDlg::SetShowable(int)
0x1809e55de  jmp     loc_1809E5665
0x1809e55e3  mov     rcx, [rbx+0D8h]
0x1809e55ea  test    rcx, rcx
0x1809e55ed  jz      short loc_1809E5665
0x1809e55ef  mov     qword ptr [rbp+Rect.left], r13
0x1809e55f3  lea     rdx, [rbp+Rect]
0x1809e55f7  mov     rax, [rcx]
0x1809e55fa  mov     rax, [rax+18h]
0x1809e55fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1809e5603  test    eax, eax
0x1809e5605  js      short loc_1809E5665
0x1809e5607  mov     rcx, qword ptr [rbp+Rect.left]; hWnd
0x1809e560b  mov     r9, r15; lParam
0x1809e560e  mov     r8, r12; wParam
0x1809e5611  mov     edx, edi; Msg
0x1809e5613  call    cs:__imp_SendMessageW
0x1809e561a  nop     dword ptr [rax+rax+00h]
0x1809e561f  jmp     short loc_1809E567C
0x1809e5621  mov     rcx, [rbx+0A0h]
0x1809e5628  lea     rdx, [rbp+Rect]; phwnd
0x1809e562c  mov     qword ptr [rbp+Rect.left], r13
0x1809e5630  mov     rcx, [rcx+0C8h]; punk
0x1809e5637  call    cs:__imp_IUnknown_GetWindow
0x1809e563e  nop     dword ptr [rax+rax+00h]
0x1809e5643  test    eax, eax
0x1809e5645  js      short loc_1809E5665
0x1809e5647  mov     rcx, qword ptr [rbp+Rect.left]; hWnd
0x1809e564b  mov     r9, r12; lParam
0x1809e564e  mov     edx, 8064h; Msg
0x1809e5653  mov     r8d, 86h; wParam
0x1809e5659  call    cs:__imp_SendMessageW
0x1809e5660  nop     dword ptr [rax+rax+00h]
0x1809e5665  mov     r9, r15; lParam
0x1809e5668  mov     r8, r12; wParam
0x1809e566b  mov     edx, edi; Msg
0x1809e566d  mov     rcx, rsi; hWnd
0x1809e5670  call    cs:__imp_DefWindowProcW
0x1809e5677  nop     dword ptr [rax+rax+00h]
0x1809e567c  mov     rcx, [rbp+var_18]
0x1809e5680  xor     rcx, rsp; StackCookie
0x1809e5683  call    __security_check_cookie
0x1809e5688  add     rsp, 68h
0x1809e568c  pop     r15
0x1809e568e  pop     r14
0x1809e5690  pop     r13
0x1809e5692  pop     r12
0x1809e5694  pop     rdi
0x1809e5695  pop     rsi
0x1809e5696  pop     rbx
0x1809e5697  pop     rbp
0x1809e5698  retn
```
