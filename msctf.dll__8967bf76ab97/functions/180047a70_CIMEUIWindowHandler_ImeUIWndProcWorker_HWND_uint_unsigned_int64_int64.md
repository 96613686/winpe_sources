# CIMEUIWindowHandler::ImeUIWndProcWorker(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180047a70`
- end: `0x18004828f`
- name: `?ImeUIWndProcWorker@CIMEUIWindowHandler@@SA_JPEAUHWND__@@I_K_J@Z`
- size: `2079`
- prototype: `__int64 __fastcall(HWND hWnd, unsigned int, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180047a60`

## callees

- `0x1800185f0`
- `0x18001a460`
- `0x18001a9e0`
- `0x18001cc80`
- `0x18001f16c`
- `0x1800454c0`
- `0x180047a70`
- `0x180048298`
- `0x180048564`
- `0x1800485e4`
- `0x18004886c`
- `0x180049234`
- `0x1800516cc`
- `0x180079614`
- `0x180093bf8`
- `0x18009bf7c`
- `0x1800e381c`
- `0x1800e3960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047cbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047d94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047f0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047f4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047cbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047d94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047f0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047f4a`
- `api-ms-win-core-atoms-l1-1-0!FindAtomW` at `0x180047c81`
- `api-ms-win-core-atoms-l1-1-0!FindAtomW` at `0x180047c81`
- `USER32!SetCoalescableTimer` at `0x180047dda`
- `USER32!SetCoalescableTimer` at `0x180047dda`
- `USER32!DefWindowProcW` at `0x180047b4c`
- `USER32!DefWindowProcW` at `0x180047b4c`
- `USER32!SetTimer` at `0x180048174`
- `USER32!SetTimer` at `0x180048174`
- `USER32!KillTimer` at `0x180047dbb`
- `USER32!KillTimer` at `0x180047e44`
- `USER32!KillTimer` at `0x180048068`
- `USER32!KillTimer` at `0x1800481e2`
- `USER32!KillTimer` at `0x18004823f`
- `USER32!KillTimer` at `0x180047dbb`
- `USER32!KillTimer` at `0x180047e44`
- `USER32!KillTimer` at `0x180048068`
- `USER32!KillTimer` at `0x1800481e2`
- `USER32!KillTimer` at `0x18004823f`
- `USER32!GetWindowLongPtrW` at `0x180047b7d`
- `USER32!GetWindowLongPtrW` at `0x180047b8b`
- `USER32!GetWindowLongPtrW` at `0x180047e91`
- `USER32!GetWindowLongPtrW` at `0x180047b7d`
- `USER32!GetWindowLongPtrW` at `0x180047b8b`
- `USER32!GetWindowLongPtrW` at `0x180047e91`
- `USER32!IsWindow` at `0x180047cd0`
- `USER32!IsWindow` at `0x180047cd0`
- `IMM32!ImmLockIMC` at `0x180047bcb`
- `IMM32!ImmLockIMC` at `0x180047e6d`
- `IMM32!ImmLockIMC` at `0x1800480a8`
- `IMM32!ImmLockIMC` at `0x180047bcb`
- `IMM32!ImmLockIMC` at `0x180047e6d`
- `IMM32!ImmLockIMC` at `0x1800480a8`
- `IMM32!ImmUnlockIMC` at `0x180047dad`
- `IMM32!ImmUnlockIMC` at `0x180047ebd`
- `IMM32!ImmUnlockIMC` at `0x1800480e0`
- `IMM32!ImmUnlockIMC` at `0x180047dad`
- `IMM32!ImmUnlockIMC` at `0x180047ebd`
- `IMM32!ImmUnlockIMC` at `0x1800480e0`
- `IMM32!ImmLockIMCC` at `0x180047c24`
- `IMM32!ImmLockIMCC` at `0x180047d01`
- `IMM32!ImmLockIMCC` at `0x180047d5f`
- `IMM32!ImmLockIMCC` at `0x180047fcf`
- `IMM32!ImmLockIMCC` at `0x180047c24`
- `IMM32!ImmLockIMCC` at `0x180047d01`
- `IMM32!ImmLockIMCC` at `0x180047d5f`
- `IMM32!ImmLockIMCC` at `0x180047fcf`
- `IMM32!ImmUnlockIMCC` at `0x180047cb4`
- `IMM32!ImmUnlockIMCC` at `0x180047d8a`
- `IMM32!ImmUnlockIMCC` at `0x180047f00`
- `IMM32!ImmUnlockIMCC` at `0x180047f3c`
- `IMM32!ImmUnlockIMCC` at `0x180047cb4`
- `IMM32!ImmUnlockIMCC` at `0x180047d8a`
- `IMM32!ImmUnlockIMCC` at `0x180047f00`
- `IMM32!ImmUnlockIMCC` at `0x180047f3c`
- `IMM32!ImmGetAppCompatFlags` at `0x180048254`
- `IMM32!ImmGetAppCompatFlags` at `0x180048254`

## string_xrefs

- `0x180047d71`: `UIComposition::UpdateShowCompWndFlag. comp==NULL`
- `0x180047eeb`: `UIComposition::OnImeSetContext. _pCicContext==NULL`
- `0x18004818d`: `UIComposition::OnImeSetContext. comp==NULL`
- `0x180047f9c`: `UIComposition::UpdateShowCompWndFlag. imc->hWNd==NULL`
- `0x180048024`: `UIComposition::UpdateCompWndFlag. imc_ctfime==NULL`
- `0x180048051`: `UIComposition::UpdateCompWndFlag. _pCicContext==NULL`
- `0x180048130`: `UIComposition::UpdateShowCompWndFlag. imc==NULL`

## pseudocode

```c
LRESULT __fastcall CIMEUIWindowHandler::ImeUIWndProcWorker(HWND hWnd, unsigned int a2, unsigned __int64 a3, __int64 a4)
{
  int v4; // r14d
  bool v8; // zf
  LONG_PTR WindowLongPtrW; // r15
  HIMC v11; // rax
  HIMC v12; // r12
  LPINPUTCONTEXT v13; // rax
  int v14; // ecx
  LPINPUTCONTEXT v15; // rbx
  __int64 v16; // rax
  HIMCC v17; // rcx
  int v18; // eax
  HIMCC *v19; // r15
  HIMCC *v20; // rdx
  HIMCC *v21; // rax
  int IsWindowFiltered; // eax
  HIMC v23; // r15
  int v24; // eax
  struct tagINPUTCONTEXT *v25; // r14
  struct tagINPUTCONTEXT *v26; // rcx
  HIMCC v27; // rax
  _DWORD *v28; // rcx
  LPINPUTCONTEXT v29; // rbx
  int v30; // eax
  LONG_PTR v31; // rax
  HIMC hCompStr; // rcx
  int v33; // eax
  struct tagINPUTCONTEXT *v34; // rdx
  LPINPUTCONTEXT v35; // rax
  int v36; // ecx
  unsigned int v37; // ebx
  unsigned int v38; // ebx
  void **v39; // [rsp+30h] [rbp-49h] BYREF
  LPINPUTCONTEXT v40; // [rsp+38h] [rbp-41h]
  HIMC v41; // [rsp+40h] [rbp-39h]
  __int64 v42; // [rsp+48h] [rbp-31h]
  HIMCC v43; // [rsp+50h] [rbp-29h]
  HIMCC v44; // [rsp+58h] [rbp-21h]
  __int64 v45; // [rsp+60h] [rbp-19h]
  HWND v46; // [rsp+68h] [rbp-11h]
  _QWORD v47[3]; // [rsp+70h] [rbp-9h] BYREF
  int v48; // [rsp+88h] [rbp+Fh]
  int v49; // [rsp+8Ch] [rbp+13h]
  void **v50; // [rsp+90h] [rbp+17h] BYREF
  HIMCC *v51; // [rsp+98h] [rbp+1Fh]
  HIMCC v52; // [rsp+A0h] [rbp+27h]
  int v53; // [rsp+A8h] [rbp+2Fh]

  v4 = a4;
  if ( a2 == 275 )
    goto LABEL_20;
  if ( a2 > 0x10E )
  {
    if ( a2 != 271 && a2 != 641 )
    {
      if ( a2 == 642 )
        return CIMEUIWindowHandler::ImeUINotifyHandler(hWnd, 0x282u, a3, a4);
      v8 = a2 == 645;
      goto LABEL_8;
    }
LABEL_20:
    WindowLongPtrW = GetWindowLongPtrW(hWnd, 8);
    v11 = (HIMC)GetWindowLongPtrW(hWnd, 0);
    v12 = v11;
    if ( a2 != 641 )
    {
      if ( a2 == 275 )
      {
        if ( a3 == 1 )
        {
          KillTimer(hWnd, 1u);
          if ( WindowLongPtrW && v12 )
          {
            v41 = v12;
            HIDWORD(v42) = 0;
            v39 = &IMCLock::`vftable';
            v40 = ImmLockIMC(v12);
            v29 = v40;
            v30 = -2147467259;
            if ( v40 )
              v30 = 0;
            LODWORD(v42) = v30;
            v31 = GetWindowLongPtrW(hWnd, 8);
            if ( v31 )
            {
              UIComposition::OnImeSetContextAfter(*(UIComposition **)(v31 + 16), (struct IMCLock *)&v39);
              v12 = v41;
              v29 = v40;
            }
            if ( v29 )
              ImmUnlockIMC(v12);
          }
        }
        else if ( a3 )
        {
          if ( a3 == 2 )
          {
            KillTimer(hWnd, 2u);
            CIMEUIWindowHandler::ImeUIDelayedReconvertFuncCall(hWnd);
          }
        }
        else
        {
          KillTimer(hWnd, 0);
          if ( WindowLongPtrW )
          {
            *(_DWORD *)(*(_QWORD *)(WindowLongPtrW + 16) + 652LL) = 0;
            if ( v12 )
            {
              v39 = &IMCLock::`vftable';
              v41 = v12;
              v42 = 0;
              v35 = ImmLockIMC(v12);
              v36 = -2147467259;
              v40 = v35;
              if ( v35 )
                v36 = 0;
              LODWORD(v42) = v36;
              UIComposition::UpdateCompositionRect(*(UIComposition **)(WindowLongPtrW + 16), (struct IMCLock *)&v39);
              v39 = &IMCLock::`vftable';
              if ( v40 )
                ImmUnlockIMC(v41);
            }
          }
        }
      }
      else
      {
        v37 = a2 - 269;
        if ( v37 )
        {
          v38 = v37 - 1;
          if ( v38 )
          {
            if ( v38 == 1 && (v4 & 8) != 0 && WindowLongPtrW )
            {
              if ( v11 )
              {
                IMCLock::IMCLock((IMCLock *)v47, v11);
                UIComposition::OnImeCompositionUpdate(
                  *(UIComposition **)(WindowLongPtrW + 16),
                  (struct IMCLock *)v47,
                  *(HWND *)(WindowLongPtrW + 8));
                IMCLock::~IMCLock((IMCLock *)v47);
              }
              SetTimer(hWnd, 0, 0xAu, 0);
              *(_DWORD *)(*(_QWORD *)(WindowLongPtrW + 16) + 652LL) = 1;
            }
          }
          else
          {
            KillTimer(hWnd, 0);
            if ( WindowLongPtrW )
            {
              *(_DWORD *)(*(_QWORD *)(WindowLongPtrW + 16) + 652LL) = 0;
              if ( v12 )
              {
                IMCLock::IMCLock((IMCLock *)v47, v12);
                UIComposition::OnImeEndComposition(*(UIComposition **)(WindowLongPtrW + 16), (struct IMCLock *)v47);
                IMCLock::~IMCLock((IMCLock *)v47);
              }
            }
          }
        }
        else if ( WindowLongPtrW && v11 )
        {
          IMCLock::IMCLock((IMCLock *)v47, v11);
          UIComposition::OnImeStartComposition(
            *(UIComposition **)(WindowLongPtrW + 16),
            (struct IMCLock *)v47,
            *(HWND *)(WindowLongPtrW + 8));
          IMCLock::~IMCLock((IMCLock *)v47);
        }
      }
      return 0;
    }
    if ( WindowLongPtrW )
    {
      if ( v11 )
      {
        v47[2] = v11;
        v49 = 0;
        v47[0] = &IMCLock::`vftable';
        v13 = ImmLockIMC(v11);
        v8 = v13 == 0;
        v47[1] = v13;
        v14 = -2147467259;
        v15 = v13;
        v16 = *(_QWORD *)(WindowLongPtrW + 16);
        if ( !v8 )
          v14 = 0;
        v48 = v14;
        v45 = v16;
        if ( !(_DWORD)a3 )
          goto LABEL_55;
        if ( !v15 )
        {
          CicTrace(2u, "UIComposition::UpdateShowCompWndFlag. imc==NULL");
          goto LABEL_55;
        }
        v17 = *(HIMCC *)&v15[1].lfFont.W.lfWidth;
        v18 = 0;
        v44 = v17;
        v19 = 0;
        v51 = 0;
        v20 = 0;
        v52 = v17;
        v53 = 0;
        if ( v17 )
        {
          v21 = (HIMCC *)ImmLockIMCC(v17);
          v17 = v44;
          v20 = v21;
          v19 = v21;
          v51 = v21;
          v8 = v21 == 0;
          v18 = -2147467259;
          if ( !v8 )
            v18 = 0;
          v53 = v18;
        }
        v50 = &IMCCLock<tagCANDIDATEINFO>::`vftable';
        if ( v20 && v18 >= 0 )
        {
          v43 = *v20;
          if ( v43 )
          {
            v46 = v15->hWnd;
            if ( FindAtomW(L"_AIMM12_PROCESS_ATOM_") )
              IsWindowFiltered = MsimtfIsWindowFiltered(v46);
            else
              IsWindowFiltered = 0;
            if ( v4 >= 0 || !IsWindowFiltered )
              goto LABEL_38;
            hCompStr = (HIMC)v15->hCompStr;
            v33 = 0;
            v40 = 0;
            v34 = 0;
            v41 = hCompStr;
            LODWORD(v42) = 0;
            if ( hCompStr )
            {
              v34 = (struct tagINPUTCONTEXT *)ImmLockIMCC((HIMCC)hCompStr);
              v40 = v34;
              v33 = -2147467259;
              if ( v34 )
                v33 = 0;
              LODWORD(v42) = v33;
            }
            v39 = &IMCCLock<tagCANDIDATEINFO>::`vftable';
            if ( v34 && v33 >= 0 )
            {
              v4 &= ~0x80000000;
              if ( v34->lfFont.A.lfEscapement && (ImmGetAppCompatFlags(0) & 0x4000000) != 0 )
                EscbCompComplete(
                  (struct IMCLock *)v47,
                  *((_DWORD *)v43 + 344),
                  *((struct ITfContext **)v43 + 6),
                  *((struct tag_LIBTHREAD **)v43 + 173),
                  1);
              InternalIMCCLock::~InternalIMCCLock((InternalIMCCLock *)&v39);
LABEL_38:
              *((_DWORD *)v43 + 67) = v4;
              if ( v19 && !ImmUnlockIMCC(v44) )
                GetLastError();
              if ( IsWindow(v15->hWnd) )
              {
                v23 = *(HIMC *)&v15[1].lfFont.W.lfWidth;
                v24 = 0;
                v40 = 0;
                v25 = 0;
                v41 = v23;
                v26 = 0;
                LODWORD(v42) = 0;
                if ( v23 )
                {
                  v26 = (struct tagINPUTCONTEXT *)ImmLockIMCC((HIMCC)v23);
                  v40 = v26;
                  v25 = v26;
                  v24 = -2147467259;
                  if ( v26 )
                    v24 = 0;
                  LODWORD(v42) = v24;
                }
                v39 = &IMCCLock<tagCANDIDATEINFO>::`vftable';
                if ( v26 && v24 >= 0 )
                {
                  v46 = v26->hWnd;
                  if ( v46 )
                  {
                    v27 = v15->hCompStr;
                    v43 = v27;
                    if ( v27 && (v28 = ImmLockIMCC(v27)) != 0 )
                    {
                      if ( *((int *)v46 + 67) < 0 && v28[11] )
                        *(_DWORD *)(v45 + 656) |= 1u;
                      else
                        *(_DWORD *)(v45 + 656) &= ~1u;
                      if ( !ImmUnlockIMCC(v43) )
                        GetLastError();
                    }
                    else
                    {
                      CicTrace(2u, "UIComposition::UpdateShowCompWndFlag. comp==NULL");
                    }
                    if ( v25 && !ImmUnlockIMCC((HIMCC)v23) )
                      GetLastError();
                    goto LABEL_55;
                  }
                  CicTrace(2u, "UIComposition::UpdateCompWndFlag. _pCicContext==NULL");
                }
                else
                {
                  CicTrace(2u, "UIComposition::UpdateCompWndFlag. imc_ctfime==NULL");
                }
                InternalIMCCLock::~InternalIMCCLock((InternalIMCCLock *)&v39);
              }
              else
              {
                CicTrace(2u, "UIComposition::UpdateShowCompWndFlag. imc->hWNd==NULL");
              }
LABEL_55:
              *(_DWORD *)(v45 + 636) = a3;
              goto LABEL_56;
            }
            CicTrace(2u, "UIComposition::OnImeSetContext. comp==NULL");
            InternalIMCCLock::~InternalIMCCLock((InternalIMCCLock *)&v39);
            InternalIMCCLock::~InternalIMCCLock((InternalIMCCLock *)&v50);
LABEL_56:
            if ( v15 )
              ImmUnlockIMC(v12);
            goto LABEL_58;
          }
          CicTrace(2u, "UIComposition::OnImeSetContext. _pCicContext==NULL");
          v17 = v44;
        }
        else if ( !v19 )
        {
          goto LABEL_56;
        }
        if ( !ImmUnlockIMCC(v17) )
          GetLastError();
        goto LABEL_56;
      }
      UIComposition::HideCompositionWindow(*(UIComposition **)(WindowLongPtrW + 16));
    }
LABEL_58:
    KillTimer(hWnd, 1u);
    SetCoalescableTimer(hWnd, 1u, 0x12Cu, 0, 0x2BCu);
    return 0;
  }
  switch ( a2 )
  {
    case 0x10Eu:
      goto LABEL_20;
    case 1u:
      UI::OnCreate(hWnd);
      return 0;
    case 2u:
    case 0x16u:
      UI::OnDestroy(hWnd);
      return 0;
  }
  v8 = a2 == 269;
LABEL_8:
  if ( v8 )
    goto LABEL_20;
  if ( a2 == WM_MSIME_RECONVERT
    || a2 == WM_MSIME_UIREADY
    || a2 == WM_MSIME_MODEBIAS
    || a2 == WM_MSIME_SHOWIMEPAD
    || a2 == WM_MSIME_MOUSE
    || a2 == WM_MSIME_SERVICE
    || a2 == WM_MSIME_RECONVERTREQUEST
    || a2 == WM_MSIME_DOCUMENTFEED
    || a2 == WM_MSIME_QUERYPOSITION
    || a2 == WM_MSIME_KEYMAP )
  {
    return CIMEUIWindowHandler::ImeUIMsImeHandler(hWnd, a2, a3, a4);
  }
  else
  {
    return DefWindowProcW(hWnd, a2, a3, a4);
  }
}

```

## disassembly

```asm
0x180047a70  push    rbp
0x180047a72  push    rbx
0x180047a73  push    rsi
0x180047a74  push    rdi
0x180047a75  push    r14
0x180047a77  lea     rbp, [rsp-37h]
0x180047a7c  sub     rsp, 0B0h
0x180047a83  mov     r14, r9
0x180047a86  mov     rsi, r8
0x180047a89  mov     ebx, edx
0x180047a8b  mov     rdi, rcx
0x180047a8e  cmp     edx, 113h
0x180047a94  jz      loc_180047B60
0x180047a9a  cmp     edx, 10Eh
0x180047aa0  ja      loc_180047DFF
0x180047aa6  jz      loc_180047B60
0x180047aac  mov     eax, edx
0x180047aae  sub     eax, 1
0x180047ab1  jz      loc_180047F75
0x180047ab7  sub     eax, 1
0x180047aba  jz      loc_180047EC8
0x180047ac0  sub     eax, 14h
0x180047ac3  jz      loc_180047EC8
0x180047ac9  cmp     eax, 0F7h
0x180047ace  jz      loc_180047B60
0x180047ad4  cmp     ebx, cs:?WM_MSIME_RECONVERT@@3IA; uint WM_MSIME_RECONVERT
0x180047ada  jz      loc_180047F55
0x180047ae0  cmp     ebx, cs:?WM_MSIME_UIREADY@@3IA; uint WM_MSIME_UIREADY
0x180047ae6  jz      loc_180047F55
0x180047aec  cmp     ebx, cs:?WM_MSIME_MODEBIAS@@3IA; uint WM_MSIME_MODEBIAS
0x180047af2  jz      loc_180047F55
0x180047af8  cmp     ebx, cs:?WM_MSIME_SHOWIMEPAD@@3IA; uint WM_MSIME_SHOWIMEPAD
0x180047afe  jz      loc_180047F55
0x180047b04  cmp     ebx, cs:?WM_MSIME_MOUSE@@3IA; uint WM_MSIME_MOUSE
0x180047b0a  jz      loc_180047F55
0x180047b10  cmp     ebx, cs:?WM_MSIME_SERVICE@@3IA; uint WM_MSIME_SERVICE
0x180047b16  jz      loc_180047F55
0x180047b1c  cmp     ebx, cs:?WM_MSIME_RECONVERTREQUEST@@3IA; uint WM_MSIME_RECONVERTREQUEST
0x180047b22  jz      loc_180047F55
0x180047b28  cmp     ebx, cs:?WM_MSIME_DOCUMENTFEED@@3IA; uint WM_MSIME_DOCUMENTFEED
0x180047b2e  jz      loc_180047F55
0x180047b34  cmp     ebx, cs:?WM_MSIME_QUERYPOSITION@@3IA; uint WM_MSIME_QUERYPOSITION
0x180047b3a  jz      loc_180047F55
0x180047b40  cmp     ebx, cs:?WM_MSIME_KEYMAP@@3IA; uint WM_MSIME_KEYMAP
0x180047b46  jz      loc_180047F55
0x180047b4c  call    cs:__imp_DefWindowProcW
0x180047b52  add     rsp, 0B0h
0x180047b59  pop     r14
0x180047b5b  pop     rdi
0x180047b5c  pop     rsi
0x180047b5d  pop     rbx
0x180047b5e  pop     rbp
0x180047b5f  retn
0x180047b60  mov     [rsp+0D0h+arg_0], r12
0x180047b68  mov     edx, 8; nIndex
0x180047b6d  mov     [rsp+0D0h+arg_8], r13
0x180047b75  mov     [rsp+0D0h+arg_10], r15
0x180047b7d  call    cs:__imp_GetWindowLongPtrW
0x180047b83  xor     edx, edx; nIndex
0x180047b85  mov     rcx, rdi; hWnd
0x180047b88  mov     r15, rax
0x180047b8b  call    cs:__imp_GetWindowLongPtrW
0x180047b91  mov     r12, rax
0x180047b94  cmp     ebx, 281h
0x180047b9a  jnz     loc_180047E28
0x180047ba0  test    r15, r15
0x180047ba3  jz      loc_180047DB3
0x180047ba9  test    rax, rax
0x180047bac  jz      loc_180047F67
0x180047bb2  xor     r13d, r13d
0x180047bb5  mov     [rbp+57h+var_50], rax
0x180047bb9  lea     rbx, ??_7IMCLock@@6B@; const IMCLock::`vftable'
0x180047bc0  mov     [rbp+57h+var_44], r13d
0x180047bc4  mov     rcx, rax; HIMC
0x180047bc7  mov     [rbp+57h+var_60], rbx
0x180047bcb  call    cs:__imp_ImmLockIMC
0x180047bd1  test    rax, rax
0x180047bd4  mov     [rbp+57h+var_58], rax
0x180047bd8  mov     ecx, 80004005h
0x180047bdd  mov     rbx, rax
0x180047be0  mov     rax, [r15+10h]
0x180047be4  cmovnz  ecx, r13d
0x180047be8  mov     [rbp+57h+var_48], ecx
0x180047beb  mov     [rbp+57h+var_70], rax
0x180047bef  test    esi, esi
0x180047bf1  jz      loc_180047D9A
0x180047bf7  test    rbx, rbx
0x180047bfa  jz      loc_180048130
0x180047c00  mov     rcx, [rbx+188h]; HIMCC
0x180047c07  mov     eax, r13d
0x180047c0a  mov     [rbp+57h+var_78], rcx
0x180047c0e  mov     r15d, r13d
0x180047c11  mov     [rbp+57h+var_38], r13
0x180047c15  mov     edx, r13d
0x180047c18  mov     [rbp+57h+var_30], rcx
0x180047c1c  mov     [rbp+57h+var_28], eax
0x180047c1f  test    rcx, rcx
0x180047c22  jz      short loc_180047C47
0x180047c24  call    cs:__imp_ImmLockIMCC
0x180047c2a  mov     rcx, [rbp+57h+var_78]
0x180047c2e  mov     rdx, rax
0x180047c31  mov     r15, rax
0x180047c34  mov     [rbp+57h+var_38], rax
0x180047c38  test    rdx, rdx
0x180047c3b  mov     eax, 80004005h
0x180047c40  cmovnz  eax, r13d
0x180047c44  mov     [rbp+57h+var_28], eax
0x180047c47  lea     r8, ??_7?$IMCCLock@UtagCANDIDATEINFO@@@@6B@; const IMCCLock<tagCANDIDATEINFO>::`vftable'
0x180047c4e  mov     [rbp+57h+var_40], r8
0x180047c52  test    rdx, rdx
0x180047c55  jz      loc_180047F8E
0x180047c5b  test    eax, eax
0x180047c5d  js      loc_180047F8E
0x180047c63  mov     rax, [rdx]
0x180047c66  mov     [rbp+57h+var_80], rax
0x180047c6a  test    rax, rax
0x180047c6d  jz      loc_180047EEB
0x180047c73  mov     rax, [rbx]
0x180047c76  lea     rcx, aAimm12ProcessA; "_AIMM12_PROCESS_ATOM_"
0x180047c7d  mov     [rbp+57h+var_68], rax
0x180047c81  call    cs:__imp_FindAtomW
0x180047c87  test    ax, ax
0x180047c8a  jnz     loc_180048043
0x180047c90  mov     eax, r13d
0x180047c93  test    r14d, r14d
0x180047c96  jns     short loc_180047CA0
0x180047c98  test    eax, eax
0x180047c9a  jnz     loc_180047FB2
0x180047ca0  mov     rax, [rbp+57h+var_80]
0x180047ca4  mov     [rax+10Ch], r14d
0x180047cab  test    r15, r15
0x180047cae  jz      short loc_180047CC4
0x180047cb0  mov     rcx, [rbp+57h+var_78]; HIMCC
0x180047cb4  call    cs:__imp_ImmUnlockIMCC
0x180047cba  test    eax, eax
0x180047cbc  jnz     short loc_180047CC4
0x180047cbe  call    cs:__imp_GetLastError
0x180047cc4  test    rbx, rbx
0x180047cc7  jz      loc_180048130
0x180047ccd  mov     rcx, [rbx]; hWnd
0x180047cd0  call    cs:__imp_IsWindow
0x180047cd6  test    eax, eax
0x180047cd8  jz      loc_180047F9C
0x180047cde  mov     r15, [rbx+188h]
0x180047ce5  mov     eax, r13d
0x180047ce8  mov     [rbp+57h+var_98], r13
0x180047cec  mov     r14, r13
0x180047cef  mov     [rbp+57h+var_90], r15
0x180047cf3  mov     rcx, r13
0x180047cf6  mov     dword ptr [rbp+57h+var_88], eax
0x180047cf9  test    r15, r15
0x180047cfc  jz      short loc_180047D20
0x180047cfe  mov     rcx, r15; HIMCC
0x180047d01  call    cs:__imp_ImmLockIMCC
0x180047d07  mov     rcx, rax
0x180047d0a  mov     [rbp+57h+var_98], rax
0x180047d0e  mov     r14, rax
0x180047d11  test    rcx, rcx
0x180047d14  mov     eax, 80004005h
0x180047d19  cmovnz  eax, r13d
0x180047d1d  mov     dword ptr [rbp+57h+var_88], eax
0x180047d20  lea     rdx, ??_7?$IMCCLock@UtagCANDIDATEINFO@@@@6B@; const IMCCLock<tagCANDIDATEINFO>::`vftable'
0x180047d27  mov     [rbp+57h+var_A0], rdx
0x180047d2b  test    rcx, rcx
0x180047d2e  jz      loc_180048024
0x180047d34  test    eax, eax
0x180047d36  js      loc_180048024
0x180047d3c  mov     rax, [rcx]
0x180047d3f  mov     [rbp+57h+var_68], rax
0x180047d43  test    rax, rax
0x180047d46  jz      loc_180048051
0x180047d4c  mov     rax, [rbx+120h]
0x180047d53  mov     [rbp+57h+var_80], rax
0x180047d57  test    rax, rax
0x180047d5a  jz      short loc_180047D71
0x180047d5c  mov     rcx, rax; HIMCC
0x180047d5f  call    cs:__imp_ImmLockIMCC
0x180047d65  mov     rcx, rax
0x180047d68  test    rax, rax
0x180047d6b  jnz     loc_180047F19
0x180047d71  lea     rdx, aUicompositionU_3; "UIComposition::UpdateShowCompWndFlag. c"...
0x180047d78  mov     ecx, 2; unsigned int
0x180047d7d  call    ?CicTrace@@YAXKPEBDZZ; CicTrace(ulong,char const *,...)
0x180047d82  test    r14, r14
0x180047d85  jz      short loc_180047D9A
0x180047d87  mov     rcx, r15; HIMCC
0x180047d8a  call    cs:__imp_ImmUnlockIMCC
0x180047d90  test    eax, eax
0x180047d92  jnz     short loc_180047D9A
0x180047d94  call    cs:__imp_GetLastError
0x180047d9a  mov     r14, [rbp+57h+var_70]
0x180047d9e  mov     [r14+27Ch], esi
0x180047da5  test    rbx, rbx
0x180047da8  jz      short loc_180047DB3
0x180047daa  mov     rcx, r12; HIMC
0x180047dad  call    cs:__imp_ImmUnlockIMC
0x180047db3  mov     edx, 1; uIDEvent
0x180047db8  mov     rcx, rdi; hWnd
0x180047dbb  call    cs:__imp_KillTimer
0x180047dc1  xor     r9d, r9d; lpTimerFunc
0x180047dc4  mov     [rsp+0D0h+uToleranceDelay], 2BCh; uToleranceDelay
0x180047dcc  mov     edx, 1; nIDEvent
0x180047dd1  mov     r8d, 12Ch; uElapse
0x180047dd7  mov     rcx, rdi; hWnd
0x180047dda  call    cs:__imp_SetCoalescableTimer
0x180047de0  mov     r13, [rsp+0D0h+arg_8]
0x180047de8  xor     eax, eax
0x180047dea  mov     r12, [rsp+0D0h+arg_0]
0x180047df2  mov     r15, [rsp+0D0h+arg_10]
0x180047dfa  jmp     loc_180047B52
0x180047dff  mov     eax, ebx
0x180047e01  sub     eax, 10Fh
0x180047e06  jz      loc_180047B60
0x180047e0c  sub     eax, 172h
0x180047e11  jz      loc_180047B60
0x180047e17  sub     eax, 1
0x180047e1a  jz      loc_180047ED4
0x180047e20  cmp     eax, 3
0x180047e23  jmp     loc_180047ACE
0x180047e28  cmp     ebx, 113h
0x180047e2e  jnz     loc_1800480EB
0x180047e34  cmp     rsi, 1
0x180047e38  jnz     loc_18004805A
0x180047e3e  mov     rdx, rsi; uIDEvent
0x180047e41  mov     rcx, rdi; hWnd
0x180047e44  call    cs:__imp_KillTimer
0x180047e4a  test    r15, r15
0x180047e4d  jz      short loc_180047DE0
0x180047e4f  test    r12, r12
0x180047e52  jz      short loc_180047DE0
0x180047e54  xor     r13d, r13d
0x180047e57  mov     [rbp+57h+var_90], r12
0x180047e5b  lea     rbx, ??_7IMCLock@@6B@; const IMCLock::`vftable'
0x180047e62  mov     dword ptr [rbp+57h+var_88+4], r13d
0x180047e66  mov     rcx, r12; HIMC
0x180047e69  mov     [rbp+57h+var_A0], rbx
0x180047e6d  call    cs:__imp_ImmLockIMC
0x180047e73  mov     [rbp+57h+var_98], rax
0x180047e77  mov     edx, 8; nIndex
0x180047e7c  mov     rbx, rax
0x180047e7f  mov     rcx, rdi; hWnd
0x180047e82  mov     eax, 80004005h
0x180047e87  test    rbx, rbx
0x180047e8a  cmovnz  eax, r13d
0x180047e8e  mov     dword ptr [rbp+57h+var_88], eax
0x180047e91  call    cs:__imp_GetWindowLongPtrW
0x180047e97  test    rax, rax
0x180047e9a  jz      short loc_180047EB1
0x180047e9c  mov     rcx, [rax+10h]; this
0x180047ea0  lea     rdx, [rbp+57h+var_A0]; struct IMCLock *
0x180047ea4  call    ?OnImeSetContextAfter@UIComposition@@QEAAJAEAVIMCLock@@@Z; UIComposition::OnImeSetContextAfter(IMCLock &)
0x180047ea9  mov     r12, [rbp+57h+var_90]
0x180047ead  mov     rbx, [rbp+57h+var_98]
0x180047eb1  test    rbx, rbx
0x180047eb4  jz      loc_180047DE0
0x180047eba  mov     rcx, r12; HIMC
0x180047ebd  call    cs:__imp_ImmUnlockIMC
0x180047ec3  jmp     loc_180047DE0
0x180047ec8  call    ?OnDestroy@UI@@SAXPEAUHWND__@@@Z; UI::OnDestroy(HWND__ *)
0x180047ecd  xor     eax, eax
0x180047ecf  jmp     loc_180047B52
0x180047ed4  mov     edx, 282h; unsigned int
0x180047ed9  add     rsp, 0B0h
0x180047ee0  pop     r14
0x180047ee2  pop     rdi
0x180047ee3  pop     rsi
0x180047ee4  pop     rbx
0x180047ee5  pop     rbp
0x180047ee6  jmp     ?ImeUINotifyHandler@CIMEUIWindowHandler@@CA_JPEAUHWND__@@I_K_J@Z; CIMEUIWindowHandler::ImeUINotifyHandler(HWND__ *,uint,unsigned __int64,__int64)
0x180047eeb  lea     rdx, aUicompositionO_1; "UIComposition::OnImeSetContext. _pCicCo"...
0x180047ef2  mov     ecx, 2; unsigned int
0x180047ef7  call    ?CicTrace@@YAXKPEBDZZ; CicTrace(ulong,char const *,...)
0x180047efc  mov     rcx, [rbp+57h+var_78]; HIMCC
0x180047f00  call    cs:__imp_ImmUnlockIMCC
0x180047f06  test    eax, eax
0x180047f08  jnz     loc_180047DA5
0x180047f0e  call    cs:__imp_GetLastError
0x180047f14  jmp     loc_180047DA5
0x180047f19  mov     rax, [rbp+57h+var_68]
0x180047f1d  cmp     [rax+10Ch], r13d
0x180047f24  jge     short loc_180047F2C
0x180047f26  cmp     [rcx+2Ch], r13d
0x180047f2a  jnz     short loc_180047F81
0x180047f2c  mov     r13, [rbp+57h+var_70]
0x180047f30  and     dword ptr [r13+290h], 0FFFFFFFEh
0x180047f38  mov     rcx, [rbp+57h+var_80]; HIMCC
0x180047f3c  call    cs:__imp_ImmUnlockIMCC
0x180047f42  test    eax, eax
0x180047f44  jnz     loc_180047D82
0x180047f4a  call    cs:__imp_GetLastError
0x180047f50  jmp     loc_180047D82
0x180047f55  add     rsp, 0B0h
0x180047f5c  pop     r14
0x180047f5e  pop     rdi
0x180047f5f  pop     rsi
0x180047f60  pop     rbx
0x180047f61  pop     rbp
0x180047f62  jmp     ?ImeUIMsImeHandler@CIMEUIWindowHandler@@CA_JPEAUHWND__@@I_K_J@Z; CIMEUIWindowHandler::ImeUIMsImeHandler(HWND__ *,uint,unsigned __int64,__int64)
0x180047f67  mov     rcx, [r15+10h]; this
0x180047f6b  call    ?HideCompositionWindow@UIComposition@@QEAAJXZ; UIComposition::HideCompositionWindow(void)
  ... truncated ...
```
