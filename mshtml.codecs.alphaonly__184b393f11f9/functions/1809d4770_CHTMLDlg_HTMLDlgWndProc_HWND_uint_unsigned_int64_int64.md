# CHTMLDlg::HTMLDlgWndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x1809d4770`
- end: `0x1809d4bc7`
- name: `?HTMLDlgWndProc@CHTMLDlg@@CA_JPEAUHWND__@@I_K_J@Z`
- size: `1111`
- prototype: `__int64 __fastcall(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)`
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x1800d9410`
- `0x1800da0d0`
- `0x1807d88d0`
- `0x1809d37e4`
- `0x1809d4770`
- `0x1809d5bdc`
- `0x1809d6f2c`
- `0x1809d7788`
- `0x1809d78b0`
- `0x1809dd210`
- `0x1810c2d60`
- `0x1810d1010`

## import_xrefs

- `USER32!MoveWindow` at `0x1809d493e`
- `USER32!MoveWindow` at `0x1809d493e`
- `USER32!RemoveMenu` at `0x1809d4a4c`
- `USER32!RemoveMenu` at `0x1809d4a63`
- `USER32!RemoveMenu` at `0x1809d4a7a`
- `USER32!RemoveMenu` at `0x1809d4a9f`
- `USER32!RemoveMenu` at `0x1809d4a4c`
- `USER32!RemoveMenu` at `0x1809d4a63`
- `USER32!RemoveMenu` at `0x1809d4a7a`
- `USER32!RemoveMenu` at `0x1809d4a9f`
- `USER32!GetSystemMenu` at `0x1809d4a29`
- `USER32!GetSystemMenu` at `0x1809d4a29`
- `USER32!SetWindowLongPtrW` at `0x1809d4831`
- `USER32!SetWindowLongPtrW` at `0x1809d4ab4`
- `USER32!SetWindowLongPtrW` at `0x1809d4831`
- `USER32!SetWindowLongPtrW` at `0x1809d4ab4`
- `USER32!DefWindowProcW` at `0x1809d4ba4`
- `USER32!DefWindowProcW` at `0x1809d4ba4`
- `USER32!PostMessageW` at `0x1809d49c4`
- `USER32!PostMessageW` at `0x1809d49c4`
- `USER32!GetWindowLongPtrW` at `0x1809d47a2`
- `USER32!GetWindowLongPtrW` at `0x1809d47a2`
- `USER32!GetClientRect` at `0x1809d494b`
- `USER32!GetClientRect` at `0x1809d494b`
- `USER32!SendMessageW` at `0x1809d4b59`
- `USER32!SendMessageW` at `0x1809d4b93`
- `USER32!SendMessageW` at `0x1809d4b59`
- `USER32!SendMessageW` at `0x1809d4b93`
- `USER32!IsIconic` at `0x1809d484e`
- `USER32!IsIconic` at `0x1809d484e`
- `USER32!GetWindowRect` at `0x1809d4880`
- `USER32!GetWindowRect` at `0x1809d48bc`
- `USER32!GetWindowRect` at `0x1809d4880`
- `USER32!GetWindowRect` at `0x1809d48bc`
- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x1809d4b77`
- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x1809d4b77`

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
0x1809d4770  push    rbp
0x1809d4772  push    rbx
0x1809d4773  push    rsi
0x1809d4774  push    rdi
0x1809d4775  push    r12
0x1809d4777  push    r13
0x1809d4779  push    r14
0x1809d477b  push    r15
0x1809d477d  mov     rbp, rsp
0x1809d4780  sub     rsp, 68h
0x1809d4784  mov     rax, cs:__security_cookie
0x1809d478b  xor     rax, rsp
0x1809d478e  mov     [rbp+var_18], rax
0x1809d4792  mov     edi, edx
0x1809d4794  mov     r15, r9
0x1809d4797  mov     edx, 0FFFFFFEBh; nIndex
0x1809d479c  mov     r12, r8
0x1809d479f  mov     rsi, rcx
0x1809d47a2  call    cs:__imp_GetWindowLongPtrW
0x1809d47a8  xor     r13d, r13d
0x1809d47ab  mov     r14d, 1
0x1809d47b1  mov     rbx, rax
0x1809d47b4  test    rax, rax
0x1809d47b7  jnz     short loc_1809D47CA
0x1809d47b9  cmp     edi, 81h
0x1809d47bf  jz      short loc_1809D4823
0x1809d47c1  cmp     edi, r14d
0x1809d47c4  jnz     loc_1809D4B99
0x1809d47ca  mov     eax, 82h
0x1809d47cf  cmp     edi, eax
0x1809d47d1  ja      loc_1809D4AC7
0x1809d47d7  jz      loc_1809D4AAA
0x1809d47dd  mov     eax, edi
0x1809d47df  sub     eax, r14d
0x1809d47e2  jz      loc_1809D4A24
0x1809d47e8  sub     eax, r14d
0x1809d47eb  jz      loc_1809D49FA
0x1809d47f1  sub     eax, 4
0x1809d47f4  jz      loc_1809D49CF
0x1809d47fa  sub     eax, 0Ah
0x1809d47fd  jz      loc_1809D4990
0x1809d4803  sub     eax, 4
0x1809d4806  jz      loc_1809D497B
0x1809d480c  sub     eax, 10h
0x1809d480f  jz      loc_1809D4962
0x1809d4815  sub     eax, 23h ; '#'
0x1809d4818  jz      short loc_1809D484B
0x1809d481a  cmp     eax, 3Ah ; ':'
0x1809d481d  jnz     loc_1809D4B99
0x1809d4823  mov     rbx, [r15]
0x1809d4826  mov     edx, 0FFFFFFEBh; nIndex
0x1809d482b  mov     r8, rbx; dwNewLong
0x1809d482e  mov     rcx, rsi; hWnd
0x1809d4831  call    cs:__imp_SetWindowLongPtrW
0x1809d4837  mov     rcx, rbx; this
0x1809d483a  mov     [rbx+120h], rsi
0x1809d4841  call    ?PrivateAddRef@CBase@@UEAAKXZ; CBase::PrivateAddRef(void)
0x1809d4846  jmp     loc_1809D4B99
0x1809d484b  mov     rcx, rsi; hWnd
0x1809d484e  call    cs:__imp_IsIconic
0x1809d4854  test    eax, eax
0x1809d4856  jnz     loc_1809D4B01
0x1809d485c  mov     eax, [rbx+1D0h]
0x1809d4862  mov     ecx, 900h
0x1809d4867  and     eax, ecx
0x1809d4869  xorps   xmm0, xmm0
0x1809d486c  movdqu  xmmword ptr [rbp+Rect.left], xmm0
0x1809d4871  cmp     eax, ecx
0x1809d4873  jz      loc_1809D4944
0x1809d4879  lea     rdx, [rbp+Rect]; lpRect
0x1809d487d  mov     rcx, rsi; hWnd
0x1809d4880  call    cs:__imp_GetWindowRect
0x1809d4886  mov     ecx, [rbx+1D0h]
0x1809d488c  mov     edi, 100h
0x1809d4891  mov     r10d, [rbp+Rect.bottom]
0x1809d4895  test    edi, ecx
0x1809d4897  jnz     short loc_1809D48DF
0x1809d4899  add     r10d, [rbx+0B0h]
0x1809d48a0  mov     rcx, [rbx+128h]; hWnd
0x1809d48a7  mov     [rbp+Rect.bottom], r10d
0x1809d48ab  test    rcx, rcx
0x1809d48ae  jz      short loc_1809D48D3
0x1809d48b0  xorps   xmm0, xmm0
0x1809d48b3  lea     rdx, [rbp+var_28]; lpRect
0x1809d48b7  movdqu  xmmword ptr [rbp+var_28.left], xmm0
0x1809d48bc  call    cs:__imp_GetWindowRect
0x1809d48c2  mov     r10d, [rbp+Rect.bottom]
0x1809d48c6  mov     eax, [rbp+var_28.bottom]
0x1809d48c9  sub     eax, [rbp+var_28.top]
0x1809d48cc  add     r10d, eax
0x1809d48cf  mov     [rbp+Rect.bottom], r10d
0x1809d48d3  or      [rbx+1D0h], edi
0x1809d48d9  mov     ecx, [rbx+1D0h]
0x1809d48df  mov     edx, 800h
0x1809d48e4  test    edx, ecx
0x1809d48e6  jnz     short loc_1809D4904
0x1809d48e8  add     r10d, [rbx+1A0h]
0x1809d48ef  mov     eax, [rbx+19Ch]
0x1809d48f5  add     [rbp+Rect.right], eax
0x1809d48f8  or      ecx, edx
0x1809d48fa  mov     [rbp+Rect.bottom], r10d
0x1809d48fe  mov     [rbx+1D0h], ecx
0x1809d4904  test    byte ptr [rbx+9Ch], 4
0x1809d490b  jz      short loc_1809D4920
0x1809d490d  xor     r8d, r8d; HWND
0x1809d4910  lea     rdx, [rbp+Rect]; struct tagRECT *
0x1809d4914  mov     rcx, rbx; this
0x1809d4917  call    ?VerifyDialogRect@CHTMLDlg@@QEAAXPEAUtagRECT@@PEAUHWND__@@@Z; CHTMLDlg::VerifyDialogRect(tagRECT *,HWND__ *)
0x1809d491c  mov     r10d, [rbp+Rect.bottom]
0x1809d4920  mov     r8d, [rbp+Rect.top]; Y
0x1809d4924  mov     rcx, rsi; hWnd
0x1809d4927  mov     r9d, [rbp+Rect.right]
0x1809d492b  sub     r10d, r8d
0x1809d492e  mov     edx, [rbp+Rect.left]; X
0x1809d4931  sub     r9d, edx; nWidth
0x1809d4934  mov     [rsp+68h+bRepaint], r14d; bRepaint
0x1809d4939  mov     [rsp+68h+nHeight], r10d; nHeight
0x1809d493e  call    cs:__imp_MoveWindow
0x1809d4944  lea     rdx, [rbp+Rect]; lpRect
0x1809d4948  mov     rcx, rsi; hWnd
0x1809d494b  call    cs:__imp_GetClientRect
0x1809d4951  lea     rdx, [rbp+Rect]; struct tagRECT *
0x1809d4955  mov     rcx, rbx; this
0x1809d4958  call    ?OnWindowPosChanged@CHTMLDlg@@AEAA_JPEAUtagRECT@@@Z; CHTMLDlg::OnWindowPosChanged(tagRECT *)
0x1809d495d  jmp     loc_1809D4B01
0x1809d4962  mov     eax, cs:?g_dwMinDialogWidth@@3KA; ulong g_dwMinDialogWidth
0x1809d4968  mov     [r15+18h], eax
0x1809d496c  mov     eax, cs:?g_dwMinDialogHeight@@3KA; ulong g_dwMinDialogHeight
0x1809d4972  mov     [r15+1Ch], eax
0x1809d4976  jmp     loc_1809D4B99
0x1809d497b  cmp     [rbx+90h], r13
0x1809d4982  jz      loc_1809D4B99
0x1809d4988  mov     rax, r14
0x1809d498b  jmp     loc_1809D4BAA
0x1809d4990  cmp     [rbx+1B9h], r13b
0x1809d4997  jnz     loc_1809D4B01
0x1809d499d  mov     rcx, [rbx+120h]; hWnd
0x1809d49a4  xor     r9d, r9d; lParam
0x1809d49a7  xor     r8d, r8d; wParam
0x1809d49aa  mov     [rbx+1B9h], r14b
0x1809d49b1  test    byte ptr [rbx+9Ch], 2
0x1809d49b8  mov     edx, 405h
0x1809d49bd  jnz     short loc_1809D49C4
0x1809d49bf  mov     edx, 404h; Msg
0x1809d49c4  call    cs:__imp_PostMessageW
0x1809d49ca  jmp     loc_1809D4B01
0x1809d49cf  mov     rcx, [rbx+0E0h]
0x1809d49d6  test    rcx, rcx
0x1809d49d9  jz      loc_1809D4B01
0x1809d49df  mov     rax, [rcx]
0x1809d49e2  test    r12w, r12w
0x1809d49e6  mov     edx, r13d
0x1809d49e9  setnz   dl
0x1809d49ec  mov     rax, [rax+30h]
0x1809d49f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1809d49f5  jmp     loc_1809D4B01
0x1809d49fa  mov     rcx, [rbx+0A0h]; this
0x1809d4a01  call    ?DestroyNavigationBar@CHTMLDlgSite@@QEAAXXZ; CHTMLDlgSite::DestroyNavigationBar(void)
0x1809d4a06  mov     rcx, [rbx+0A0h]
0x1809d4a0d  xor     edx, edx; struct ITrustStateNotify *
0x1809d4a0f  add     rcx, 60h ; '`'; this
0x1809d4a13  call    ?Connect@CTrustStateImpl@@QEAAJPEAUITrustStateNotify@@PEAUITrustState@@@Z; CTrustStateImpl::Connect(ITrustStateNotify *,ITrustState *)
0x1809d4a18  mov     [rbx+120h], r13
0x1809d4a1f  jmp     loc_1809D4B01
0x1809d4a24  xor     edx, edx; bRevert
0x1809d4a26  mov     rcx, rsi; hWnd
0x1809d4a29  call    cs:__imp_GetSystemMenu
0x1809d4a2f  mov     r14, rax
0x1809d4a32  test    rax, rax
0x1809d4a35  jz      loc_1809D4B99
0x1809d4a3b  cmp     [rbx+48h], r13d
0x1809d4a3f  jnz     short loc_1809D4A52
0x1809d4a41  xor     r8d, r8d; uFlags
0x1809d4a44  mov     edx, 0F020h; uPosition
0x1809d4a49  mov     rcx, rax; hMenu
0x1809d4a4c  call    cs:__imp_RemoveMenu
0x1809d4a52  cmp     [rbx+4Ch], r13d
0x1809d4a56  jnz     short loc_1809D4A69
0x1809d4a58  xor     r8d, r8d; uFlags
0x1809d4a5b  mov     edx, 0F030h; uPosition
0x1809d4a60  mov     rcx, r14; hMenu
0x1809d4a63  call    cs:__imp_RemoveMenu
0x1809d4a69  cmp     [rbx+54h], r13d
0x1809d4a6d  jnz     short loc_1809D4A80
0x1809d4a6f  xor     r8d, r8d; uFlags
0x1809d4a72  mov     edx, 0F000h; uPosition
0x1809d4a77  mov     rcx, r14; hMenu
0x1809d4a7a  call    cs:__imp_RemoveMenu
0x1809d4a80  cmp     [rbx+48h], r13d
0x1809d4a84  jnz     loc_1809D4B99
0x1809d4a8a  cmp     [rbx+4Ch], r13d
0x1809d4a8e  jnz     loc_1809D4B99
0x1809d4a94  xor     r8d, r8d; uFlags
0x1809d4a97  mov     edx, 0F120h; uPosition
0x1809d4a9c  mov     rcx, r14; hMenu
0x1809d4a9f  call    cs:__imp_RemoveMenu
0x1809d4aa5  jmp     loc_1809D4B99
0x1809d4aaa  xor     r8d, r8d; dwNewLong
0x1809d4aad  mov     rcx, rsi; hWnd
0x1809d4ab0  lea     edx, [r8-15h]; nIndex
0x1809d4ab4  call    cs:__imp_SetWindowLongPtrW
0x1809d4aba  mov     rcx, rbx; this
0x1809d4abd  call    ?PrivateRelease@CBase@@UEAAKXZ; CBase::PrivateRelease(void)
0x1809d4ac2  jmp     loc_1809D4B99
0x1809d4ac7  mov     eax, edi
0x1809d4ac9  sub     eax, 86h
0x1809d4ace  jz      loc_1809D4B61
0x1809d4ad4  sub     eax, 289h
0x1809d4ad9  jz      short loc_1809D4B29
0x1809d4adb  sub     eax, 2
0x1809d4ade  jz      short loc_1809D4B29
0x1809d4ae0  sub     eax, 0F1h
0x1809d4ae5  jz      short loc_1809D4B1F
0x1809d4ae7  sub     eax, r14d
0x1809d4aea  jz      short loc_1809D4B15
0x1809d4aec  sub     eax, r14d
0x1809d4aef  jz      short loc_1809D4B08
0x1809d4af1  cmp     eax, r14d
0x1809d4af4  jnz     loc_1809D4B99
0x1809d4afa  mov     [rbx+1BAh], r14b
0x1809d4b01  xor     eax, eax
0x1809d4b03  jmp     loc_1809D4BAA
0x1809d4b08  mov     rcx, rbx; this
0x1809d4b0b  call    ?Close@CHTMLDlg@@QEAA_JXZ; CHTMLDlg::Close(void)
0x1809d4b10  jmp     loc_1809D4BAA
0x1809d4b15  mov     rcx, rbx; this
0x1809d4b18  call    ?UnlockParentWindow@CHTMLDlg@@QEAAXXZ; CHTMLDlg::UnlockParentWindow(void)
0x1809d4b1d  jmp     short loc_1809D4B99
0x1809d4b1f  mov     rcx, rbx; this
0x1809d4b22  call    ?SetShowable@CHTMLDlg@@QEAAXH@Z; CHTMLDlg::SetShowable(int)
0x1809d4b27  jmp     short loc_1809D4B99
0x1809d4b29  mov     rcx, [rbx+0D8h]
0x1809d4b30  test    rcx, rcx
0x1809d4b33  jz      short loc_1809D4B99
0x1809d4b35  mov     qword ptr [rbp+Rect.left], r13
0x1809d4b39  lea     rdx, [rbp+Rect]
0x1809d4b3d  mov     rax, [rcx]
0x1809d4b40  mov     rax, [rax+18h]
0x1809d4b44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1809d4b49  test    eax, eax
0x1809d4b4b  js      short loc_1809D4B99
0x1809d4b4d  mov     rcx, qword ptr [rbp+Rect.left]; hWnd
0x1809d4b51  mov     r9, r15; lParam
0x1809d4b54  mov     r8, r12; wParam
0x1809d4b57  mov     edx, edi; Msg
0x1809d4b59  call    cs:__imp_SendMessageW
0x1809d4b5f  jmp     short loc_1809D4BAA
0x1809d4b61  mov     rcx, [rbx+0A0h]
0x1809d4b68  lea     rdx, [rbp+Rect]; phwnd
0x1809d4b6c  mov     qword ptr [rbp+Rect.left], r13
0x1809d4b70  mov     rcx, [rcx+0C8h]; punk
0x1809d4b77  call    cs:__imp_IUnknown_GetWindow
0x1809d4b7d  test    eax, eax
0x1809d4b7f  js      short loc_1809D4B99
0x1809d4b81  mov     rcx, qword ptr [rbp+Rect.left]; hWnd
0x1809d4b85  mov     r9, r12; lParam
0x1809d4b88  mov     edx, 8064h; Msg
0x1809d4b8d  mov     r8d, 86h; wParam
0x1809d4b93  call    cs:__imp_SendMessageW
0x1809d4b99  mov     r9, r15; lParam
0x1809d4b9c  mov     r8, r12; wParam
0x1809d4b9f  mov     edx, edi; Msg
0x1809d4ba1  mov     rcx, rsi; hWnd
0x1809d4ba4  call    cs:__imp_DefWindowProcW
0x1809d4baa  mov     rcx, [rbp+var_18]
0x1809d4bae  xor     rcx, rsp; StackCookie
0x1809d4bb1  call    __security_check_cookie
0x1809d4bb6  add     rsp, 68h
0x1809d4bba  pop     r15
0x1809d4bbc  pop     r14
0x1809d4bbe  pop     r13
0x1809d4bc0  pop     r12
0x1809d4bc2  pop     rdi
0x1809d4bc3  pop     rsi
0x1809d4bc4  pop     rbx
0x1809d4bc5  pop     rbp
0x1809d4bc6  retn
```
