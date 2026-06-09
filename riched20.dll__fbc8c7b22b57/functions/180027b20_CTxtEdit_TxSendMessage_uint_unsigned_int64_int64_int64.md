# CTxtEdit::TxSendMessage(uint,unsigned __int64,__int64,__int64 *)

- ea: `0x180027b20`
- end: `0x18002a6e8`
- name: `?TxSendMessage@CTxtEdit@@UEAAJI_K_JPEA_J@Z`
- size: `11208`
- prototype: `__int64 __usercall@<rax>(CTxtEdit *__hidden this@<rcx>, unsigned int@<edx>, unsigned __int64@<r8>, __int64@<r9>, __int64 *)`
- caller_count: `0`
- callee_count: `131`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800066b0`
- `0x1800159d8`
- `0x180016d90`
- `0x1800182a0`
- `0x18001be70`
- `0x18001ff28`
- `0x1800238dc`
- `0x180026344`
- `0x18002720c`
- `0x1800274a0`
- `0x180027524`
- `0x180027678`
- `0x180027794`
- `0x180027b20`
- `0x18002a740`
- `0x18002a790`
- `0x18002ac10`
- `0x18002af60`
- `0x18002b0b0`
- `0x18002c17c`
- `0x18002c58c`
- `0x18002c5d8`
- `0x18002c650`
- `0x18002c900`
- `0x18002c990`
- `0x18002ce34`
- `0x18002d048`
- `0x18002d9b8`
- `0x18002dce0`
- `0x18002e85c`
- `0x18002e888`
- `0x180030ce0`
- `0x1800376f4`
- `0x180039990`
- `0x180039f90`
- `0x18003aa30`
- `0x18003e56c`
- `0x18003ebc4`
- `0x18003ed88`
- `0x18003eeec`
- `0x180040214`
- `0x180040b14`
- `0x180040e04`
- `0x180040f58`
- `0x180040fe8`
- `0x1800416f0`
- `0x180041df8`
- `0x180041fe8`
- `0x180042bf8`
- `0x18004315c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180028374`
- `KERNEL32!GetCurrentThreadId` at `0x180028374`
- `KERNEL32!GetSystemDefaultLangID` at `0x18002866a`
- `KERNEL32!GetSystemDefaultLangID` at `0x18002866a`
- `KERNEL32!FindAtomA` at `0x1800283a6`
- `KERNEL32!FindAtomA` at `0x1800283a6`
- `USER32!GetFocus` at `0x1800287fe`
- `USER32!GetFocus` at `0x18002882a`
- `USER32!GetFocus` at `0x1800287fe`
- `USER32!GetFocus` at `0x18002882a`
- `USER32!IsChild` at `0x180028812`
- `USER32!IsChild` at `0x180028812`
- `USER32!GetKeyState` at `0x180028bcf`
- `USER32!GetKeyState` at `0x180028bcf`

## pseudocode

```c
__int64 __fastcall CTxtEdit::TxSendMessage(CTxtEdit *this, unsigned int a2, HWND a3, struct IUnknown **a4, __int64 *a5)
{
  __int64 *v5; // r15
  __int64 v6; // rsi
  unsigned __int64 v7; // r14
  __int64 v9; // r12
  int v10; // eax
  __int16 v11; // r13
  __int16 v12; // r8
  unsigned int v13; // edi
  unsigned int v14; // ecx
  struct IUndoBuilder *v15; // rdi
  __int64 v16; // rcx
  __int64 Component; // rax
  __int64 v18; // r8
  __int64 v19; // rdx
  int WordBreak; // edi
  __int64 v21; // rcx
  void ***v22; // rax
  _QWORD *v23; // rcx
  CDetectURL *v24; // rcx
  struct CTxtEdit *v25; // rbx
  CTextMsgFilter *v27; // rax
  CTextMsgFilter *v28; // rsi
  char *v29; // r8
  void (__fastcall *v30)(CTextMsgFilter *, HWND, char *); // rax
  int v31; // esi
  unsigned int v32; // eax
  bool v33; // zf
  __int64 v34; // rcx
  struct IAntiEvent *v35; // rbx
  struct IAntiEvent *v36; // rcx
  struct IAntiEvent *v37; // rcx
  unsigned __int64 v38; // r9
  __int64 v39; // rcx
  int v40; // eax
  CTextMsgFilter *v41; // rax
  int v42; // eax
  unsigned int DefaultCodePage; // ecx
  signed int v44; // r14d
  unsigned int v45; // edx
  unsigned int v46; // r12d
  struct IUndoBuilder *v47; // rdx
  DWORD CurrentThreadId; // eax
  __int64 v49; // rcx
  __int64 v50; // r8
  int TextRange; // eax
  __int16 v52; // cx
  int v53; // r13d
  int v54; // edx
  unsigned int v55; // r14d
  __int64 v56; // rax
  int v57; // r13d
  unsigned __int16 v58; // di
  int KeyboardFlag; // eax
  unsigned __int16 v60; // cx
  int v61; // ecx
  _WORD *v62; // rdi
  __int64 v63; // rax
  int v64; // eax
  LANGID SystemDefaultLangID; // ax
  unsigned int v66; // eax
  HKL v67; // r10
  CTxtSelection *v68; // r11
  HWND Focus; // rax
  int v70; // r9d
  void (__fastcall **v71)(CTxtEdit *, GUID *, HWND *); // rax
  const struct _GUID *v72; // rcx
  __int64 v73; // rcx
  __int16 v74; // ax
  unsigned __int64 v75; // rsi
  unsigned __int16 v76; // dx
  int v77; // r13d
  __int64 v78; // rcx
  __int64 v79; // rdi
  HDC v80; // rdx
  int v81; // r8d
  int v82; // r9d
  HWND v83; // rax
  int v84; // ecx
  int v85; // edx
  int v86; // r15d
  int v87; // eax
  int v88; // edi
  int v89; // eax
  LONG v90; // eax
  __int64 v91; // rcx
  struct IUndoBuilder *v92; // rdi
  __int64 v93; // rax
  unsigned int v94; // r9d
  struct IUndoMgr *v95; // rdx
  int v96; // eax
  __int64 v97; // rcx
  __int64 v98; // rcx
  HWND v99; // rax
  unsigned int v100; // eax
  CObjectMgr *ObjectMgr; // rax
  int SelMost; // eax
  int v103; // r10d
  int v104; // edi
  int v105; // r8d
  int v106; // r8d
  int CpFromAcp; // r14d
  int v108; // eax
  unsigned __int16 *v109; // r9
  unsigned int v110; // edx
  CDisplay *v111; // rsi
  const struct CTxtRange *v112; // r14
  __int64 v113; // rdx
  int v114; // edx
  struct CTxtRange *v115; // rax
  CTxtSelection *v116; // rax
  __int16 v117; // r9
  unsigned __int16 v118; // di
  __int16 v119; // ax
  __int64 v120; // rcx
  int v121; // eax
  CDisplay *v122; // rcx
  CTxtRange *v123; // rsi
  CDisplay *v124; // r14
  int v125; // eax
  __int16 v126; // ax
  __int16 v127; // r12
  int v128; // eax
  __int16 v129; // cx
  __int16 v130; // cx
  __int64 v131; // rax
  __int64 v132; // rdx
  _DWORD *v133; // rcx
  _QWORD *v134; // rdx
  void *v135; // rsi
  __int16 v136; // cx
  __int64 Sel; // [rsp+40h] [rbp-C0h] BYREF
  HWND hWndParent; // [rsp+48h] [rbp-B8h] BYREF
  struct IUnknown **v139; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v140; // [rsp+58h] [rbp-A8h] BYREF
  HWND v141; // [rsp+60h] [rbp-A0h] BYREF
  int v142; // [rsp+68h] [rbp-98h]
  int v143; // [rsp+6Ch] [rbp-94h] BYREF
  int v144; // [rsp+70h] [rbp-90h]
  int v145; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned __int64 v146; // [rsp+78h] [rbp-88h] BYREF
  void **v147; // [rsp+80h] [rbp-80h] BYREF
  void **v148; // [rsp+88h] [rbp-78h] BYREF
  int v149; // [rsp+90h] [rbp-70h]
  __int64 v150; // [rsp+98h] [rbp-68h]
  __int64 v151; // [rsp+A0h] [rbp-60h]
  __int64 UndoMgr; // [rsp+A8h] [rbp-58h]
  struct CTxtEdit *v153; // [rsp+B0h] [rbp-50h]
  unsigned int v154; // [rsp+B8h] [rbp-48h]
  struct IAntiEvent *v155; // [rsp+C0h] [rbp-40h]
  int v156; // [rsp+C8h] [rbp-38h]
  _OWORD v157[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 *v158; // [rsp+F0h] [rbp-10h]
  PARAFORMAT2 v159; // [rsp+100h] [rbp+0h] BYREF
  struct _selchange String[3]; // [rsp+1C0h] [rbp+C0h] BYREF

  v5 = a5;
  v158 = a5;
  v6 = (__int64)a4;
  v140 = a2;
  v7 = (unsigned __int64)a3;
  hWndParent = a3;
  v139 = a4;
  Sel = 0;
  memset(v157, 0, sizeof(v157));
  if ( this )
  {
    *((_QWORD *)&v157[0] + 1) = *((_QWORD *)this + 18);
    *((_QWORD *)this + 18) = v157;
    *(_QWORD *)&v157[0] = this;
    CCallMgr::NotifyEnterContext((CCallMgr *)v157);
    a2 = v140;
    v7 = (unsigned __int64)hWndParent;
    v6 = (__int64)v139;
  }
  v9 = 16;
  if ( CW32System::_MSMouseRoller == a2 )
  {
    v58 = (unsigned int)CW32System::GetKeyboardFlag(0x30u, 0x11u) != 0 ? 8 : 0;
    KeyboardFlag = CW32System::GetKeyboardFlag(3u, 0x10u);
    v6 = (__int64)v139;
    v60 = v58 | 4;
    a2 = 522;
    v140 = 522;
    if ( !KeyboardFlag )
      v60 = v58;
    v61 = ((unsigned __int16)v7 << 16) | v60;
    v7 = v61;
    hWndParent = (HWND)v61;
  }
  if ( *((_QWORD *)this + 38) )
    goto LABEL_43;
  v10 = *((_DWORD *)this + 45);
  v11 = v6;
  v146 = v7;
  v12 = v7;
  v13 = a2;
  if ( (v10 & 0x10000000) == 0 )
  {
    v33 = (CW32System::_sysiniflags & 4) == 0;
    *((_DWORD *)this + 45) = v10 | 0x10000000;
    if ( !v33
      || (CurrentThreadId = GetCurrentThreadId()) != 0
      && (CW32System::sprintf_s((char *)String, 20, "AIMM:%08x", CurrentThreadId), FindAtomA((LPCSTR)String)) )
    {
      v141 = 0;
      CTxtEdit::TxGetWindow(this, &v141);
      if ( v141 )
        CW32System::PostMessage(v141, 0x4CCu, 0x40u, 64);
    }
    v12 = v146;
    v6 = (__int64)v139;
    v7 = (unsigned __int64)hWndParent;
    a2 = v140;
  }
  if ( v13 > 0x468 )
  {
    switch ( v13 )
    {
      case 0x469u:
      case 0x46Au:
      case 0x46Bu:
      case 0x47Du:
        goto LABEL_73;
      case 0x478u:
        if ( (v11 & 0xC) != 0 )
          goto LABEL_73;
        goto LABEL_17;
      case 0x4CCu:
        if ( (v11 & 0xC0) != 0 || (v12 & 0xC0) != 0 )
          goto LABEL_73;
        goto LABEL_17;
      default:
        goto LABEL_14;
    }
  }
  if ( v13 != 1128 )
  {
    if ( v13 > 0x10D )
    {
      if ( v13 != 642 && v13 != 646 && v13 != 648 )
        goto LABEL_14;
    }
    else if ( v13 != 269 )
    {
      if ( v13 == 81 )
      {
        v57 = v11 & 0x3FF;
        if ( v57 != 18 && v57 != 4 && v57 != 17 )
        {
LABEL_17:
          v147 = &CGenUndoBuilder::`vftable'{for `IUndoBuilder'};
          v151 = 0;
          v14 = v156 & 0xFFFFFFE0 | 1;
          v148 = &CGenUndoBuilder::`vftable'{for `IReEntrantComponent'};
          v33 = (*((_DWORD *)this + 45) & 0x100000) == 0;
          UndoMgr = *((_QWORD *)this + 10);
          v154 = 0;
          v155 = 0;
          v153 = this;
          v156 = v14;
          if ( v33 )
          {
            v15 = 0;
            v141 = 0;
            v156 = v14 | 0x10;
          }
          else
          {
            v15 = (struct IUndoBuilder *)&v147;
            v16 = *((_QWORD *)this + 18);
            v141 = (HWND)&v147;
            Component = CCallMgr::GetComponent(v16, 1);
            v149 = 1;
            v19 = Component - 8;
            if ( !Component )
              v19 = 0;
            v151 = v19;
            v150 = *(_QWORD *)(v18 + 16);
            *(_QWORD *)(v18 + 16) = &v148;
            a2 = v140;
            v7 = (unsigned __int64)hWndParent;
            v6 = (__int64)v139;
          }
          if ( a2 == 20 )
          {
LABEL_22:
            Sel = 1;
LABEL_23:
            WordBreak = 0;
            goto LABEL_24;
          }
          if ( a2 <= 0xB0 )
          {
            if ( a2 == 176 )
            {
              Sel = CTxtEdit::OnGetSel(this, (int *)v7, (int *)v6);
              goto LABEL_23;
            }
            switch ( a2 )
            {
              case 5u:
                WordBreak = 1;
                *((_WORD *)this + 92) |= 0xC0u;
                break;
              case 7u:
                WordBreak = CTxtEdit::OnSetFocus(this);
                break;
              case 8u:
                Sel = CTxtEdit::OnKillFocus(this);
                goto LABEL_23;
              case 0xCu:
                v70 = 1200;
                if ( v7 )
                  v70 = v7;
                WordBreak = CTxtEdit::SetText(this, (const unsigned __int16 *)v6, 0x8000u, v70, v15, &Sel);
                break;
              case 0xDu:
                HIDWORD(String[0].nmhdr.hwndFrom) = 1;
                LODWORD(String[0].nmhdr.idFrom) = 1200;
                LODWORD(String[0].nmhdr.hwndFrom) = 2 * v7;
                *(_OWORD *)((char *)&String[0].nmhdr.idFrom + 4) = 0;
                Sel = (int)CTxtEdit::GetTextEx(this, (struct _gettextex *)String, (unsigned __int16 *)v6);
                goto LABEL_23;
              case 0xEu:
                v141 = (HWND)0x4B00000000BLL;
                Sel = (int)CTxtEdit::GetTextLengthEx(this, (struct _gettextlengthex *)&v141);
                goto LABEL_23;
              case 0x15u:
                (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 6) + 72LL))(
                  *((_QWORD *)this + 6),
                  0,
                  0);
                goto LABEL_23;
              case 0x1Au:
                Sel = 0;
                CW32System::InitSysParams(1);
                if ( CW32System::_bDigitSubstMode )
                  CTxtEdit::OrCharFlags(this, 2u, v15);
                goto LABEL_23;
              case 0x21u:
                Sel = 1;
                Focus = GetFocus();
                if ( !IsChild(hWndParent, Focus) && (!hWndParent || hWndParent != GetFocus()) )
                  *((_DWORD *)this + 45) |= 0x100u;
                WordBreak = 1;
                break;
              case 0x30u:
                Sel = CTxtEdit::OnSetFont(this, (HFONT)v7);
                goto LABEL_23;
              case 0x31u:
                goto LABEL_23;
              case 0x3Du:
                if ( (_DWORD)v6 != -16 )
                  goto LABEL_171;
                v71 = *(void (__fastcall ***)(CTxtEdit *, GUID *, HWND *))this;
                v141 = 0;
                (*v71)(this, &IID_IUnknown, &v141);
                Sel = CW32System::LResultFromObject(v72, (unsigned __int64)hWndParent, (struct IUnknown *)v141);
                (*(void (__fastcall **)(HWND))(*(_QWORD *)v141 + 16LL))(v141);
                goto LABEL_23;
              case 0x50u:
                v62 = (_WORD *)((char *)this + 184);
                if ( (v7 & 1) == 0 && (*((_WORD *)this + 92) & 0x100) != 0 )
                {
                  if ( (v6 & 0x3FF) == 9 && ((unsigned __int16)v6 >> 10) - 1 <= 1u )
                  {
                    LOBYTE(v7) = 1;
                    hWndParent = (HWND)1;
                  }
                  else
                  {
                    LOBYTE(v7) = 0;
                    hWndParent = 0;
                  }
                }
                goto LABEL_163;
              case 0x51u:
                v62 = (_WORD *)((char *)this + 184);
                if ( (*((_WORD *)this + 92) & 0x100) == 0 )
                  goto LABEL_165;
                if ( !v7
                  || ((v63 = *((_QWORD *)this + 20)) == 0
                    ? (SystemDefaultLangID = GetSystemDefaultLangID(),
                       v64 = CW32System::ConvertLanguageIDtoCodePage(SystemDefaultLangID))
                    : (v64 = *(unsigned __int16 *)(v63 + 18)),
                      v7 == CW32System::GetCharSet(v64, 0)) )
                {
                  LOBYTE(v7) = 1;
                  hWndParent = (HWND)1;
                }
                else
                {
                  LOBYTE(v7) = 0;
                  hWndParent = 0;
                }
LABEL_163:
                if ( (*v62 & 0x100) != 0 )
                {
                  WordBreak = 0;
                  if ( (v7 & 1) == 0 )
                    break;
                }
LABEL_165:
                CW32System::RefreshKeyboardLayout();
                if ( (CW32System::_wKeyboardFlags & 0x30) != 0 && (CW32System::_wKeyboardFlags & 3) != 0 )
                  CW32System::_wKeyboardFlags |= 0x8000u;
                if ( !CTxtEdit::GetSel(this) )
                {
LABEL_442:
                  CGenUndoBuilder::~CGenUndoBuilder((CGenUndoBuilder *)&v147);
                  CCallMgr::~CCallMgr((CCallMgr *)v157);
                  return 2147942414LL;
                }
                WordBreak = 0;
                v66 = CW32System::ConvertLanguageIDtoCodePage((unsigned __int16)v139);
                if ( CTxtSelection::CheckChangeFont(v68, v67, v66, 0, 0) )
LABEL_171:
                  WordBreak = 1;
                break;
              case 0x7Bu:
                WordBreak = CTxtEdit::OnContextMenu(this, v6);
                break;
              case 0xA7u:
LABEL_296:
                CTxtEdit::OnTxMButtonDown(this, (__int16)v6, SWORD1(v6), 0x80000000);
                goto LABEL_23;
              default:
                goto LABEL_171;
            }
          }
          else
          {
            if ( a2 <= 0x200 )
            {
              if ( a2 != 512 )
              {
                v38 = 0x180000000uLL;
                switch ( a2 )
                {
                  case 0xB1u:
                    goto LABEL_416;
                  case 0xB5u:
                    Sel = CTxtEdit::TxVScroll(this, v7, 0);
                    goto LABEL_23;
                  case 0xB6u:
                    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 8) + 304LL))(
                      *((_QWORD *)this + 8),
                      (unsigned int)v6,
                      (unsigned int)v7);
                    WordBreak = 0;
                    Sel = (*(_DWORD *)(*((_QWORD *)this + 8) + 56LL) >> 17) & 1;
                    goto LABEL_24;
                  case 0xB7u:
                    CTxtEdit::OnScrollCaret(this);
                    goto LABEL_23;
                  case 0xB8u:
                    Sel = -((*((_DWORD *)this + 45) >> 14) & 1);
                    goto LABEL_23;
                  case 0xB9u:
                    *((_DWORD *)this + 45) &= ~0x4000u;
                    *((_DWORD *)this + 45) |= v7 != 0 ? 0x4000 : 0;
                    goto LABEL_23;
                  case 0xBAu:
                    if ( (*((_BYTE *)this + 180) & 8) == 0 )
                    {
                      WordBreak = -2147221491;
                      goto LABEL_24;
                    }
                    if ( (*(unsigned int (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 8) + 264LL))(
                           *((_QWORD *)this + 8),
                           *((unsigned int *)this + 68),
                           0xFFFFFFFFLL) )
                    {
                      v39 = (*(int (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 184LL))(*((_QWORD *)this + 8));
                      v40 = 0;
                      Sel = v39;
                    }
                    else
                    {
                      v40 = -2147467259;
                    }
                    goto LABEL_69;
                  case 0xBBu:
                    WordBreak = CTxtEdit::TxLineIndex(this, v7, &Sel);
                    goto LABEL_24;
                  case 0xBCu:
                  case 0xBDu:
                  case 0xC8u:
                    goto LABEL_23;
                  case 0xBEu:
                    v93 = *(_QWORD *)this;
                    LODWORD(v146) = 0;
                    v145 = 0;
                    if ( !(*(unsigned int (__fastcall **)(CTxtEdit *, _QWORD, _QWORD, unsigned __int64 *, _QWORD, int *))(v93 + 48))(
                            this,
                            0,
                            0,
                            &v146,
                            0,
                            &v145)
                      && v145 )
                    {
                      Sel = (int)v146;
                    }
                    goto LABEL_23;
                  case 0xC1u:
                    WordBreak = CTxtEdit::TxLineLength(this, v7, &Sel);
                    goto LABEL_24;
                  case 0xC2u:
                    hWndParent = (HWND)((v7 != 0) + 32770LL);
                    WordBreak = CTxtEdit::SetText(
                                  this,
                                  (const unsigned __int16 *)v6,
                                  (unsigned int)hWndParent,
                                  1200,
                                  v15,
                                  &Sel);
                    goto LABEL_24;
                  case 0xC4u:
                    if ( (*((_BYTE *)this + 180) & 8) == 0 || !v6 )
                      goto LABEL_331;
                    Sel = (*(int (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD))(**((_QWORD **)this + 8) + 208LL))(
                            *((_QWORD *)this + 8),
                            (unsigned int)v7,
                            v6,
                            *(unsigned __int16 *)v6);
                    goto LABEL_23;
                  case 0xC5u:
                    v6 = v7;
                    v139 = (struct IUnknown **)v7;
                    goto LABEL_282;
                  case 0xC6u:
                    v73 = *((_QWORD *)this + 10);
                    goto LABEL_193;
                  case 0xC7u:
                    goto LABEL_311;
                  case 0xC9u:
                    LODWORD(v6) = v7;
                    v139 = (struct IUnknown **)v7;
                    goto LABEL_229;
                  case 0xCBu:
                    WordBreak = 0;
                    if ( (*(_DWORD *)(*((_QWORD *)this + 8) + 56LL) & 0x20000) == 0 || v7 && (!v6 || !*(_DWORD *)v6) )
                      goto LABEL_24;
                    v77 = 32;
                    if ( v7 > 0x20 )
                      hWndParent = (HWND)32;
                    memset_0(&v159, 0, sizeof(v159));
                    v78 = *((_QWORD *)this + 6);
                    v159.cbSize = 188;
                    v143 = 0;
                    v79 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v78 + 24LL))(v78);
                    GetECDefaultHeightAndWidth(this, v80, v81, v82, (int)CW32System::_yPerInchScreenDC, &v143, 0, 0);
                    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 6) + 32LL))(
                      *((_QWORD *)this + 6),
                      v79);
                    v83 = hWndParent;
                    if ( hWndParent )
                    {
                      v84 = *(_DWORD *)v6;
                      v142 = *(_DWORD *)v6;
                      if ( (unsigned __int64)hWndParent > 1 )
                      {
                        v85 = 0;
                        v142 = v84;
                        v144 = 0;
                        v77 = (int)hWndParent;
                        if ( (int)hWndParent <= 0 )
                          goto LABEL_275;
LABEL_268:
                        v86 = v142;
                        while ( 1 )
                        {
                          v142 = v85 + 1;
                          if ( (unsigned __int64)v83 > 1 )
                          {
                            v87 = *(_DWORD *)v6;
                            v142 = v85 + 1;
                          }
                          else
                          {
                            v87 = (v85 + 1) * v86;
                          }
                          v88 = CW32System::_xPerInchScreenDC;
                          v89 = CW32System::MulDiv(v87, v143, 4);
                          v90 = CW32System::MulDiv(v89, 1440, v88);
                          v91 = v144;
                          v6 += 4;
                          v85 = v142;
                          v144 = v142;
                          v159.rgxTabs[v91] = v90;
                          if ( v85 >= v77 )
                            break;
                          v83 = hWndParent;
                        }
                        v5 = v158;
LABEL_275:
                        v159.cTabCount = v77;
                        v159.dwMask = 16;
                        CParaFormat::Set((CParaFormat *)String, &v159);
                        v92 = (struct IUndoBuilder *)v141;
                        if ( v141 )
                          (*(void (__fastcall **)(HWND))(*(_QWORD *)v141 + 48LL))(v141);
                        v56 = CTxtEdit::OnSetParaFormat(this, 4u, (struct CParaFormat *)String, v92, 0x20000010u);
LABEL_136:
                        Sel = v56;
                        CTabsArray::Release(qword_1800A72C0, SHIWORD(String[0].nmhdr.code));
                        goto LABEL_23;
                      }
                    }
                    else
                    {
                      v142 = 32;
                    }
                    v85 = 0;
                    v144 = 0;
                    goto LABEL_268;
                  case 0xCDu:
                    CTxtEdit::ClearUndo(this, v15);
                    goto LABEL_23;
                  case 0xCEu:
                    if ( (*((_BYTE *)this + 180) & 8) == 0 )
                      goto LABEL_331;
                    Sel = (*(int (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 200LL))(*((_QWORD *)this + 8));
                    goto LABEL_23;
                  case 0xD0u:
                    *((_QWORD *)this + 7) = v6;
                    *((_WORD *)this + 94) &= ~0x20u;
                    goto LABEL_23;
                  case 0xD1u:
                    if ( (*((_BYTE *)this + 188) & 0x20) == 0 )
                      Sel = *((_QWORD *)this + 7);
                    goto LABEL_23;
                  case 0xD5u:
                    Sel = *((unsigned int *)this + 54);
                    goto LABEL_23;
                  case 0xD6u:
                    goto LABEL_395;
                  case 0xD7u:
                    goto LABEL_328;
                  case 0x100u:
                    WordBreak = CTxtEdit::OnTxKeyDown(this, v7, v6, v15);
                    goto LABEL_24;
                  case 0x101u:
                    if ( v7 == 93 )
                    {
                      CTxtEdit::HandleKbdContextMenu(this);
                      v7 = (unsigned __int64)hWndParent;
                      WordBreak = 0;
                      v6 = (__int64)v139;
                    }
                    else
                    {
                      WordBreak = 1;
                    }
                    CW32System::_fLRMorRLM = 0;
                    if ( v7 - 16 <= 1 )
                    {
                      if ( (*((_BYTE *)this + 192) & 1) != 0 )
                      {
                        v52 = *((_WORD *)this + 92);
                        if ( (v52 & 3u) < 2
                          && (v52 & 0xCu) < 8
                          && (CW32System::_wKeyboardFlags & 0x30) != 0
                          && (CW32System::_wKeyboardFlags & 3) != 0
                          && (CW32System::_wKeyboardFlags & 0x8000) == 0 )
                        {
                          WORD1(String[0].nmhdr.hwndFrom) = (CW32System::_wKeyboardFlags & 1) != 0;
                          CTxtEdit::OnSetParaFormat(
                            this,
                            0,
                            (struct CParaFormat *)String,
                            (struct IUndoBuilder *)v141,
                            0x20010000u);
                          CTxtEdit::TxNotify(this, (WORD1(String[0].nmhdr.hwndFrom) != 0) + 1808, 0);
                          v7 = (unsigned __int64)hWndParent;
                          v6 = (__int64)v139;
                        }
                      }
                      v75 = (unsigned __int64)v6 >> 16;
                      if ( v7 == 17 )
                      {
                        if ( (v75 & 0x100) == 0 )
                          v9 = 32;
                        v139 = (struct IUnknown **)v9;
                      }
                      else
                      {
                        v139 = (struct IUnknown **)(((_BYTE)v75 != 54) + 1LL);
                        if ( GetKeyState(16) < 0 )
                        {
                          LOWORD(v9) = (_WORD)v139;
                        }
                        else
                        {
                          LOWORD(v9) = 3;
                          v139 = (struct IUnknown **)3;
                        }
                      }
                      CW32System::_wKeyboardFlags &= ~(v9 | 0x9000);
                    }
                    else if ( v7 == 18 )
                    {
                      v74 = 4160;
                      if ( (v6 & 0x1000000) == 0 )
                        v74 = 4224;
                      CW32System::_wKeyboardFlags &= ~v74;
                    }
                    goto LABEL_24;
                  case 0x102u:
                    if ( (CW32System::_wKeyboardFlags & 0x5000) == 0 )
                      goto LABEL_198;
                    if ( (CW32System::_wKeyboardFlags & 0x4000) != 0 )
                    {
                      v143 = 0;
                      CW32System::AnsiFilter(&v140, (unsigned __int64 *)&hWndParent, v6, &v143, 0);
                      LOWORD(v7) = (_WORD)hWndParent;
                      LODWORD(v6) = (_DWORD)v139;
                      goto LABEL_198;
                    }
                    CW32System::_wKeyboardFlags &= ~0x1000u;
                    goto LABEL_23;
                  case 0x104u:
                    if ( !(unsigned int)CTxtEdit::OnTxSysKeyDown(this, v7, v6, v15) )
                      goto LABEL_22;
                    goto LABEL_171;
                  case 0x105u:
                    if ( (unsigned int)(v7 - 16) > 2 )
                    {
                      v76 = CW32System::_wKeyboardFlags;
                    }
                    else
                    {
                      v76 = ~(unsigned __int16)GetKbdFlags(v7, v6) & CW32System::_wKeyboardFlags;
                      CW32System::_wKeyboardFlags = v76;
                    }
                    if ( (unsigned int)(v7 - 96) <= 9 || v7 == 12 || v7 == 45 || (unsigned int)(v7 - 33) <= 7 )
                    {
                      CW32System::_wKeyboardFlags = v76 | 0x4000;
                      if ( (unsigned int)(v7 - 96) > 9 )
                      {
                        if ( v7 == 12 )
                          v7 = 101;
                        else
                          v7 = *(unsigned __int8 *)(v7 + v38 + 642855);
                        hWndParent = (HWND)v7;
                      }
                      if ( !CW32System::_wNumKeyPad && v7 == 96 )
                        CW32System::_wKeyboardFlags = v76 | 0x6000;
                      CW32System::_wNumKeyPad = v7 + 10 * CW32System::_wNumKeyPad - 96;
                    }
                    goto LABEL_171;
                  case 0x106u:
                    WordBreak = CTxtEdit::OnTxSysChar(this, v7, v6, v15);
                    Sel = WordBreak;
                    if ( WordBreak )
                      goto LABEL_171;
                    goto LABEL_24;
                  case 0x113u:
                    CTxtEdit::OnTxTimer(this, v7);
                    goto LABEL_171;
                  case 0x114u:
                    if ( (*((_BYTE *)this + 180) & 8) != 0 )
                    {
                      CDisplay::HScroll(*((CDisplay **)this + 8), v7, WORD1(v7));
                      WordBreak = 0;
                    }
                    else
                    {
                      v40 = -2147221491;
LABEL_69:
                      WordBreak = v40;
                    }
                    goto LABEL_24;
                  case 0x115u:
                    CTxtEdit::TxVScroll(this, v7, WORD1(v7));
                    goto LABEL_23;
                  default:
                    goto LABEL_171;
                }
              }
              *((_WORD *)this + 92) |= 0xC0u;
              WordBreak = CTxtEdit::OnTxMouseMove(this, (__int16)v6, SWORD1(v6), (unsigned __int16)v7, v15);
              goto LABEL_24;
            }
            if ( a2 <= 0x300 )
            {
              if ( a2 == 768 )
              {
LABEL_307:
                WordBreak = CTxtEdit::CutOrCopySelection(this, a2, v7, v6, v15);
                Sel = WordBreak;
              }
              else
              {
                switch ( a2 )
                {
                  case 0x201u:
                    if ( (*((_DWORD *)this + 45) & 0x100) != 0 )
                    {
                      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 144LL))(*((_QWORD *)this + 6));
                      *((_DWORD *)this + 45) &= ~0x100u;
                      goto LABEL_23;
                    }
                    WordBreak = CTxtEdit::OnTxLButtonDown(this, (__int16)v6, SWORD1(v6), (unsigned __int16)v7);
                    break;
                  case 0x202u:
                    WordBreak = CTxtEdit::OnTxLButtonUp(this, (__int16)v6, SWORD1(v6), (unsigned __int16)v7, 3);
                    goto LABEL_24;
                  case 0x203u:
                    WordBreak = CTxtEdit::OnTxLButtonDblClk(this, (__int16)v6, SWORD1(v6), (unsigned __int16)v7);
                    goto LABEL_24;
                  case 0x204u:
                  case 0x205u:
                  case 0x206u:
                    WordBreak = 0;
                    if ( !(unsigned int)CTxtEdit::HandleLinkNotification(this, a2, v7, v6, 0) )
                    {
                      if ( v140 == 517 )
                      {
                        WordBreak = CTxtEdit::OnTxRButtonUp(this, (__int16)v139, SWORD1(v139), v94, 0);
                      }
                      else if ( v140 == 516 )
                      {
                        WordBreak = CTxtEdit::OnTxRButtonDown(
                                      this,
                                      (__int16)v139,
                                      SWORD1(v139),
                                      (unsigned __int16)hWndParent);
                      }
                    }
                    goto LABEL_24;
                  case 0x207u:
                  case 0x209u:
                    goto LABEL_296;
                  case 0x208u:
                    CTxtEdit::OnTxMButtonUp(this, (__int16)v6, SWORD1(v6), 0x80000000);
                    goto LABEL_23;
                  case 0x20Au:
                    Sel = CTxtEdit::HandleMouseWheel(this, v7, 512);
                    goto LABEL_23;
                  case 0x233u:
                    CTxtEdit::OnDropFiles(this, (void *)v7);
                    goto LABEL_23;
                  case 0x286u:
LABEL_198:
                    WordBreak = CTxtEdit::OnTxChar(this, v7, v6, v15);
                    CW32System::_wKeyboardFlags &= ~0x1000u;
                    Sel = WordBreak;
                    goto LABEL_24;
                  default:
                    goto LABEL_171;
                }
              }
              goto LABEL_24;
            }
            if ( a2 > 0x401 )
            {
              switch ( a2 )
              {
                case 0x426u:
LABEL_395:
                  WordBreak = CTxtEdit::OnPosFromChar(this, v7, v6, &Sel);
                  goto LABEL_24;
                case 0x427u:
LABEL_328:
                  WordBreak = CTxtEdit::TxCharFromPos(this, (struct tagPOINT *)v6, &Sel);
                  goto LABEL_24;
                case 0x432u:
                  Sel = CLightDTEngine::CanPaste((CTxtEdit *)((char *)this + 96), 0, v7, 0);
                  goto LABEL_23;
                case 0x433u:
                  if ( (*((_BYTE *)this + 180) & 8) == 0 )
                    goto LABEL_331;
                  CTxtEdit::OnDisplayBand(this, (const struct tagRECT *)v6, 0);
                  goto LABEL_22;
                case 0x434u:
                  CTxtEdit::OnExGetSel(this, (struct _charrange *)v6);
                  goto LABEL_23;
                case 0x435u:
LABEL_282:
                  if ( !v6 )
                  {
                    LODWORD(v6) = 0x10000;
                    v139 = (struct IUnknown **)0x10000;
                  }
                  if ( (*((_DWORD *)this + 45) & 0x80000) != 0 && (int)v6 < 0 )
                  {
                    LODWORD(v6) = 0;
                    v139 = 0;
                  }
                  *((_DWORD *)this + 54) = v6;
                  goto LABEL_23;
                case 0x436u:
LABEL_229:
                  WordBreak = CTxtEdit::TxLineFromCp(this, v6, &Sel);
                  goto LABEL_24;
                case 0x437u:
                  if ( v6 )
                  {
                    LODWORD(v7) = *(_DWORD *)v6;
                    hWndParent = (HWND)*(int *)v6;
                    v6 = *(int *)(v6 + 4);
                    v139 = (struct IUnknown **)v6;
LABEL_416:
                    Sel = CTxtEdit::OnSetSel(this, v7, v6);
                  }
                  else
                  {
                    Sel = -2147467259;
                  }
                  goto LABEL_23;
                case 0x438u:
                case 0x44Fu:
                case 0x47Bu:
                case 0x47Cu:
                  Sel = CTxtEdit::OnFindText(this, a2, v7, (struct _findtextexw *)v6);
                  goto LABEL_23;
                case 0x439u:
                  if ( (*((_BYTE *)this + 180) & 8) == 0 )
                  {
LABEL_331:
                    WordBreak = -2147221491;
                    goto LABEL_24;
                  }
                  Sel = CTxtEdit::OnFormatRange(this, v6, v7 != 0, 0);
                  goto LABEL_23;
                case 0x43Au:
                  Sel = CTxtEdit::OnGetCharFormat(this, (struct CHARFORMAT2W *)v6, v7);
                  goto LABEL_23;
                case 0x43Bu:
                  Sel = *((unsigned int *)this + 44);
                  goto LABEL_23;
                case 0x43Cu:
                  if ( v6 )
                  {
                    if ( v7 == 1702066039 )
                    {
                      CW32System::GetAimmObject((struct IUnknown **)v6);
                    }
                    else
                    {
                      *(_QWORD *)v6 = (char *)this + 8;
                      (*(void (__fastcall **)(CTxtEdit *))(*(_QWORD *)this + 8LL))(this);
                    }
                  }
                  goto LABEL_22;
                case 0x43Du:
                  Sel = CTxtEdit::OnGetParaFormat(this, (struct PARAFORMAT2 *)v6, v7);
                  goto LABEL_23;
                case 0x43Eu:
                  CTxtEdit::GetSelMin(this);
                  SelMost = CTxtEdit::GetSelMost(this);
                  TextRange = CTxtEdit::GetTextRange(this, v103, SelMost - v103 + 1, (unsigned __int16 *)v6);
                  goto LABEL_119;
                case 0x43Fu:
                  v110 = *((_DWORD *)this + 45);
                  if ( (v110 & 0x80000) == 0 )
                    goto LABEL_369;
                  if ( v6 )
                  {
                    v110 = (v7 != 0 ? 0x20 : 0) | v110 & 0xFFFFFFDF;
                    *((_DWORD *)this + 45) = v110;
LABEL_369:
                    if ( v6 && (v110 & 0x80u) != 0 )
                      goto LABEL_23;
                  }
                  TextRange = CTxtEdit::OnHideSelectionChange(this, v7);
                  goto LABEL_119;
                case 0x440u:
                  goto LABEL_393;
                case 0x441u:
                  WordBreak = CDisplay::RequestResize(*((CDisplay **)this + 8));
                  goto LABEL_24;
                case 0x442u:
                  memset(String, 0, 36);
                  v116 = CTxtEdit::GetSel(this);
                  if ( v116 )
                    CTxtSelection::SetSelectionInfo(v116, String);
                  Sel = String[0].seltyp;
                  goto LABEL_23;
                case 0x444u:
                  v42 = *(_DWORD *)v6;
                  DefaultCodePage = 1200;
                  v44 = *(_DWORD *)(v6 + 4);
                  if ( *(_DWORD *)v6 == 60 )
                    goto LABEL_83;
                  if ( v42 == 92 || v42 == 116 )
                    goto LABEL_85;
                  if ( v42 == 84 )
                  {
LABEL_83:
                    if ( (v44 & 0x20000000) != 0 )
                      DefaultCodePage = CTxtEdit::GetDefaultCodePage(this, 0x444u);
LABEL_85:
                    v45 = *((_DWORD *)this + 45);
                    if ( (v45 & 0x80000) != 0 && v44 < 0 && *(int *)(v6 + 12) <= 0 )
                      v44 &= ~0x80000000;
                    if ( *(_DWORD *)v6 == 92 || (v46 = 0, *(_DWORD *)v6 == 60) )
                    {
                      v46 = 0x8000;
                      v44 &= ~(v45 >> 14) & 0x2000 | 0xF800003F;
                    }
                    BYTE4(String[0].nmhdr.hwndFrom) = 0;
                    CCharFormat::Set((CCharFormat *)String, (const struct CHARFORMAT2W *)v6, DefaultCodePage);
                    Sel = CTxtEdit::OnSetCharFormat(
                            this,
                            (unsigned __int64)hWndParent,
                            (struct CCharFormat *)String,
                            v15,
                            v44,
                            v46);
                  }
                  goto LABEL_23;
                case 0x445u:
                  Sel = *((unsigned int *)this + 44);
                  *((_DWORD *)this + 44) = v6;
                  if ( (v6 & 0x40000) != 0 )
                    CDisplay::UpdateView(*((CDisplay **)this + 8));
                  goto LABEL_23;
                case 0x446u:
                  WordBreak = -2147467259;
                  ObjectMgr = CTxtEdit::GetObjectMgr(this);
                  if ( !ObjectMgr )
                    goto LABEL_24;
                  CObjectMgr::SetRECallback(ObjectMgr, (struct IRichEditOleCallback *)v139);
                  goto LABEL_22;
                case 0x447u:
                  WordBreak = 0;
                  if ( !(unsigned int)IsValidParaFormat((const struct _paraformat *)v6) )
                    goto LABEL_24;
                  v55 = *(_DWORD *)(v6 + 4);
                  if ( (v55 & 0x43000000) != 0 )
                    goto LABEL_24;
                  if ( (v55 & 0x10) != 0 )
                  {
                    v121 = *(__int16 *)(v6 + 26);
                    if ( *(_WORD *)(v6 + 26) )
                    {
                      v53 = 32;
                      v54 = 0;
                      if ( (__int16)v121 > 32 || (v53 = *(__int16 *)(v6 + 26), v121 > 0) )
                      {
                        do
                        {
                          if ( (*(_DWORD *)(v6 + 4LL * v54 + 28) & 0xF000000u) > 0x4000000 )
                            break;
                          ++v54;
                        }
                        while ( v54 < v53 );
                      }
                      if ( v54 != v53 )
                        goto LABEL_24;
                    }
                  }
                  if ( *(_DWORD *)v6 == 156 )
                    v55 = v55 & 0x8001003F | 0x20000000;
                  CParaFormat::Set((CParaFormat *)String, (const struct PARAFORMAT2 *)v6);
                  v56 = CTxtEdit::OnSetParaFormat(
                          this,
                          (unsigned __int64)hWndParent,
                          (struct CParaFormat *)String,
                          (struct IUndoBuilder *)v141,
                          v55);
                  goto LABEL_136;
                case 0x448u:
                  v49 = *((_QWORD *)this + 8);
                  v50 = 0x7FFFFF;
                  if ( v6 < 0x7FFFFF )
                    v50 = v6;
                  v139 = (struct IUnknown **)v50;
                  TextRange = (*(__int64 (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v49 + 88LL))(v49, v7);
                  goto LABEL_119;
                case 0x449u:
                case 0x44Au:
                  CTxtRange::CTxtRange((CTxtRange *)String, this, 0, -*((_DWORD *)this + 68));
                  hWndParent = (HWND)CW32System::ValidateStreamWparam((unsigned __int64)hWndParent);
                  if ( ((unsigned __int16)hWndParent & 0x8000) != 0 )
                  {
                    v123 = CTxtEdit::GetSel(this);
                    if ( !v123 )
                    {
                      CTxtRange::~CTxtRange((CTxtRange *)String);
                      goto LABEL_442;
                    }
                  }
                  else
                  {
                    v123 = (CTxtRange *)String;
                    if ( v140 != 1097 )
                      goto LABEL_456;
                    v15 = 0;
                    CTxtEdit::ClearUndo(this, (struct IUndoBuilder *)&v147);
                    if ( ((unsigned __int16)hWndParent & 0x1000) == 0 )
                      CTxtEdit::CloseFile(this, 0);
                  }
                  if ( v140 == 1097 )
                  {
                    if ( (*((_DWORD *)this + 44) & 0x200000) != 0
                      && (unsigned int)CTxtRange::IsProtected(v123, 0) == 2
                      && (unsigned int)CTxtEdit::QueryUseProtection(
                                         this,
                                         v123,
                                         v140,
                                         (unsigned __int64)hWndParent,
                                         (__int64)v139) )
                    {
                      CTxtEdit::Beep(this);
                      CTxtRange::~CTxtRange((CTxtRange *)String);
                      goto LABEL_23;
                    }
                    v124 = (CDisplay *)*((_QWORD *)this + 8);
                    CDisplay::Freeze(v124);
                    Sel = (int)CLightDTEngine::LoadFromEs(
                                 (CTxtEdit *)((char *)this + 96),
                                 v123,
                                 (int)hWndParent,
                                 (struct _editstream *)v139,
                                 0,
                                 v15);
                    if ( (*((_WORD *)this + 92) & 0x2000) != 0 )
                      CRchTxtPtr::Check_rpPF((CRchTxtPtr *)(*((_QWORD *)this + 37) + 8LL));
                    if ( *((char *)this + 180) < 0 )
                      CDisplay::SaveUpdateCaret(*((CDisplay **)this + 8), 1);
                    CDisplay::Thaw(v124);
LABEL_457:
                    CTxtRange::~CTxtRange((CTxtRange *)String);
                    goto LABEL_23;
                  }
LABEL_456:
                  Sel = CLightDTEngine::SaveToEs(
                          (CTxtEdit *)((char *)this + 96),
                          v123,
                          (int)hWndParent,
                          (struct _editstream *)v139);
                  goto LABEL_457;
                case 0x44Bu:
                  v104 = ValidateTextRange((struct _textrangew *)v6);
                  if ( !v104 )
                    goto LABEL_23;
                  CpFromAcp = CTxtEdit::GetCpFromAcp(this, *(_DWORD *)v6, v105);
                  v108 = v104 >= 0
                       ? 1 - CpFromAcp + CTxtEdit::GetCpFromAcp(this, *(_DWORD *)(v6 + 4), v106)
                       : *((_DWORD *)this + 68) + 1;
                  v109 = *(unsigned __int16 **)(v6 + 8);
                  if ( !v109 )
                    goto LABEL_23;
                  TextRange = CTxtEdit::SafeGetTextRange(this, CpFromAcp, v108, v109);
                  goto LABEL_119;
                case 0x44Cu:
                  WordBreak = CTxtEdit::TxFindWordBreak(this, v7, v6, &Sel);
                  goto LABEL_24;
                case 0x450u:
                  if ( (*((_BYTE *)this + 188) & 0x20) != 0 )
                    Sel = *((_QWORD *)this + 7);
                  goto LABEL_23;
                case 0x451u:
                  if ( (*((_DWORD *)this + 45) & 0x80000) != 0 )
                  {
                    *((_WORD *)this + 94) |= 0x20u;
                    *((_QWORD *)this + 7) = v6;
                  }
                  goto LABEL_23;
                case 0x452u:
                  Sel = CTxtEdit::HandleSetUndoLimit(this, v7);
                  goto LABEL_23;
                case 0x454u:
                  v95 = (struct IUndoMgr *)*((_QWORD *)this + 11);
                  goto LABEL_313;
                case 0x455u:
                  v73 = *((_QWORD *)this + 11);
LABEL_193:
                  if ( !v73 )
                    goto LABEL_23;
                  TextRange = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v73 + 72LL))(v73);
                  goto LABEL_119;
                case 0x456u:
                  v97 = *((_QWORD *)this + 10);
                  goto LABEL_322;
                case 0x457u:
                  v97 = *((_QWORD *)this + 11);
LABEL_322:
                  if ( !v97 )
                    goto LABEL_23;
                  TextRange = (*(__int64 (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v97 + 40LL))(v97, v7);
LABEL_119:
                  Sel = TextRange;
                  goto LABEL_23;
                case 0x458u:
                  v98 = *((_QWORD *)this + 10);
                  if ( v98 )
                  {
                    if ( !v7
                      || (v99 = (HWND)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v98 + 48LL))(v98),
                          hWndParent == v99) )
                    {
                      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 10) + 88LL))(*((_QWORD *)this + 10));
                    }
                  }
                  goto LABEL_23;
                case 0x459u:
                  if ( (*((_DWORD *)this + 45) & 0x80000) == 0 )
                    Sel = CTxtEdit::HandleSetTextMode(this, v7);
                  goto LABEL_23;
                case 0x45Au:
                  Sel = (*((_DWORD *)this + 45) & 1) + 1LL;
                  v131 = *((_QWORD *)this + 10);
                  if ( !v131 || (v132 = 4, (*(_BYTE *)(v131 + 32) & 8) == 0) )
                    v132 = 8;
                  if ( (*((_WORD *)this + 92) & 0x100) == 0 )
                    v9 = 32;
                  Sel |= v132 | v9;
                  goto LABEL_23;
                case 0x45Bu:
                  if ( v6 || (v7 | 1) != 1 )
                  {
                    Sel = -2147024809;
                    WordBreak = -2147024809;
                    goto LABEL_24;
                  }
                  if ( v7 != 1 || *((_QWORD *)this + 19) )
                  {
                    WordBreak = 0;
                    if ( !v7 )
                    {
                      v135 = (void *)*((_QWORD *)this + 19);
                      if ( v135 )
                      {
                        CDetectURL::~CDetectURL(*((CDetectURL **)this + 19));
                        CW32System::FreePv(v135);
                        *((_QWORD *)this + 19) = 0;
                      }
                    }
                    goto LABEL_24;
                  }
                  v133 = CW32System::PvAlloc(0x30u, 0x40u);
                  if ( !v133 )
                  {
                    *((_QWORD *)this + 19) = 0;
                    WordBreak = -2147024882;
                    Sel = -2147024882;
                    goto LABEL_24;
                  }
                  *(_QWORD *)v133 = &CDetectURL::`vftable';
                  v134 = (_QWORD *)((char *)this + 128);
                  v133[10] &= ~1u;
                  v133[6] = 1;
                  v133[7] = 0x3FFFFFFF;
                  if ( this != (CTxtEdit *)-128LL )
                  {
                    *((_QWORD *)v133 + 1) = *v134;
                    *v134 = v133;
                  }
                  *((_QWORD *)v133 + 2) = this;
                  *((_QWORD *)this + 19) = v133;
                  goto LABEL_23;
                case 0x45Cu:
                  if ( *((_QWORD *)this + 19) )
                    goto LABEL_22;
                  goto LABEL_23;
                case 0x45Eu:
                  TextRange = CTxtEdit::GetTextEx(this, (struct _gettextex *)v7, (unsigned __int16 *)v6);
                  goto LABEL_119;
                case 0x45Fu:
                  TextRange = CTxtEdit::GetTextLengthEx(this, (struct _gettextlengthex *)v7);
                  goto LABEL_119;
                case 0x461u:
                  WordBreak = 0;
                  if ( v7 )
                    WordBreak = CTxtEdit::SetText(
                                  this,
                                  (const unsigned __int16 *)v6,
                                  *(_DWORD *)v7,
                                  *(_DWORD *)(v7 + 4),
                                  (struct IUndoBuilder *)v141,
                                  &Sel);
                  goto LABEL_24;
                case 0x46Cu:
                  if ( v7 )
                    TextRange = CTxtEdit::GetCpFromAcp(this, v6, 512);
                  else
                    TextRange = CTxtEdit::GetAcpFromCp(this, v6, 512);
                  goto LABEL_119;
                case 0x478u:
                  *((_DWORD *)this + 45) &= 0xFF9FFFFF;
                  *((_DWORD *)this + 45) |= ((v6 & 1) << 22) | ((_DWORD)v6 << 20) & 0x200000;
                  *((_WORD *)this + 92) &= ~0x400u;
                  *((_WORD *)this + 92) |= ((_WORD)v6 << 6) & 0x400;
                  *((_WORD *)this + 94) &= 0xFFF9u;
                  *((_WORD *)this + 94) |= ((unsigned __int64)v6 >> 3) & 4 | ((unsigned __int64)v6 >> 6) & 2;
                  goto LABEL_22;
                case 0x479u:
                  v125 = *((_DWORD *)this + 45);
                  if ( (v125 & 0x200000) != 0 )
                    Sel |= 2uLL;
                  if ( (v125 & 0x400000) != 0 )
                    Sel |= 1uLL;
                  if ( (*((_WORD *)this + 92) & 0x400) != 0 )
                    Sel |= 0x10uLL;
                  v126 = *((_WORD *)this + 94);
                  if ( (v126 & 2) != 0 )
                    Sel |= 0x80uLL;
                  if ( (v126 & 4) != 0 )
                    Sel |= 0x20uLL;
                  goto LABEL_23;
                case 0x497u:
                  TextRange = CTxtEdit::GetDefaultCodePage(this, v7);
                  goto LABEL_119;
                case 0x4A8u:
                  *((_WORD *)this + 94) |= 0x200u;
                  goto LABEL_23;
                case 0x4C8u:
                  if ( v6 )
                  {
                    v117 = *((_WORD *)this + 92);
                    v118 = *(_WORD *)(v6 + 4) & *(_WORD *)(v6 + 6)
                         | ~*(_WORD *)(v6 + 4)
                         & ((*((_WORD *)this + 94) >> 2) & 0x40
                          | ((v117 & 0x10) != 0 ? 4 : 0)
                          | ((v117 & 3) != 0 ? 8 : 0)
                          | ((v117 & 0xC) != 0 ? 0x10 : 0));
                    *((_WORD *)this + 94) = *((_WORD *)this + 94) & 0xFEFF | (4 * (v118 & 0x40));
                    if ( (*((_BYTE *)this + 180) & 1) == 0 )
                    {
                      if ( (((unsigned __int8)v117 >> 2) & 4) != (v118 & 4) )
                      {
                        v119 = 0;
                        if ( (v117 & 0x10) == 0 )
                          v119 = 16;
                        v120 = *((_QWORD *)this + 8);
                        *((_WORD *)this + 92) = v117 & 0xFFEF | v119;
                        if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v120 + 120LL))(v120) )
                        {
                          *(_DWORD *)(*((_QWORD *)this + 8) + 56LL) |= 0x80u;
                          (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 6) + 72LL))(
                            *((_QWORD *)this + 6),
                            0,
                            0);
                        }
                      }
                      *((_WORD *)this + 92) &= 0xFFF0u;
                      *((_WORD *)this + 92) |= (unsigned __int16)(v118 & 0x10 | (v118 >> 1) & 4) >> 2;
                      if ( (*((_BYTE *)this + 184) & 0xF) != 0 )
                        CTxtEdit::SetContextDirection(this, 1);
                    }
                  }
                  goto LABEL_23;
                case 0x4C9u:
                  if ( v6 && *(_DWORD *)v6 == 8 )
                  {
                    *(_WORD *)(v6 + 4) = 92;
                    *((_WORD *)v139 + 3) = ((*((_WORD *)this + 92) & 3) != 0 ? 8 : 0)
                                         | ((*((_WORD *)this + 92) & 0xC) != 0 ? 0x10 : 0)
                                         | ((unsigned __int16)(*((_WORD *)this + 92) & 0x10
                                                             | *((_WORD *)this + 94) & 0x100) >> 2);
                  }
                  goto LABEL_23;
                case 0x4CAu:
                  WordBreak = CTxtEdit::OnSetTypographyOptions(this, v7, v6);
                  Sel = WordBreak == 0;
                  goto LABEL_24;
                case 0x4CBu:
                  Sel = *((unsigned __int8 *)this + 198);
                  goto LABEL_23;
                case 0x4CCu:
                  if ( (*((_DWORD *)this + 45) & 0x80000) != 0 )
                    goto LABEL_23;
                  v127 = *((_WORD *)this + 93) & 1 | v6 & v7 | *((_WORD *)this + 93) & ~(_WORD)v6;
                  *((_WORD *)this + 93) = v127;
                  if ( (v7 & 1) != 0 )
                  {
                    v128 = CTxtEdit::HandleSetTextMode(this, 5u);
                    v129 = *((_WORD *)this + 93);
                    LOWORD(v7) = (_WORD)hWndParent;
                    if ( v128 < 0 )
                      v130 = v129 & 0xFFFE;
                    else
                      v130 = v129 | 2;
                    *((_WORD *)this + 93) = v130;
                  }
                  if ( (v7 & 0x1000) != 0 )
                    CTxtEdit::OrCharFlags(this, 1u, v15);
                  *((_WORD *)this + 93) = *((_WORD *)this + 93) & 0xFBFF
                                        | ((*((_WORD *)this + 93) & 0x200) == 0 && (v127 & 0x400) != 0 ? 0x400 : 0);
                  goto LABEL_481;
                case 0x4CDu:
LABEL_481:
                  if ( (*((_DWORD *)this + 45) & 0x80000) == 0 )
                    Sel = *((unsigned __int16 *)this + 93) | (unsigned __int64)Sel;
                  goto LABEL_23;
                case 0x4DCu:
                  v111 = (CDisplay *)*((_QWORD *)this + 8);
                  CDisplay::Freeze(v111);
                  if ( hWndParent == (HWND)5 )
                  {
                    WordBreak = CTxtEdit::GetViewKind(this, &Sel);
                    CDisplay::Thaw(v111);
                    goto LABEL_24;
                  }
                  if ( (*(_DWORD *)(*((_QWORD *)this + 8) + 56LL) & 0x20000) == 0 )
                    goto LABEL_389;
                  if ( (*((_BYTE *)this + 180) & 1) == 0 )
                    goto LABEL_389;
                  v112 = (const struct CTxtRange *)*((_QWORD *)this + 37);
                  if ( !v112 )
                    goto LABEL_389;
                  if ( hWndParent == (HWND)1 )
                  {
                    v114 = 2;
                  }
                  else
                  {
                    if ( hWndParent )
                    {
                      if ( (*((_WORD *)this + 92) & 0x2000) == 0
                        || !(unsigned int)CTxtEdit::IsntProtectedOrReadOnly(
                                            this,
                                            v140,
                                            (unsigned __int64)hWndParent,
                                            (__int64)v139,
                                            1) )
                      {
LABEL_389:
                        CDisplay::Thaw(v111);
                        goto LABEL_23;
                      }
                      CTxtRange::CTxtRange((CTxtRange *)String, v112);
                      WordBreak = 0;
                      if ( hWndParent != (HWND)2 )
                      {
                        if ( hWndParent == (HWND)3 )
                        {
                          WordBreak = CTxtRange::ExpandOutline((CTxtRange *)String, (__int16)v139, WORD1(v139) == 1);
                        }
                        else if ( hWndParent == (HWND)4 )
                        {
                          WordBreak = CTxtEdit::MoveSelection(this, (__int64)v139, (struct IUndoBuilder *)v141);
                          v113 = 1;
LABEL_387:
                          (*(void (__fastcall **)(const struct CTxtRange *, __int64))(*(_QWORD *)v112 + 568LL))(
                            v112,
                            v113);
                        }
                        *((_DWORD *)this + 45) |= 0x4000u;
                        Sel = WordBreak == 0;
                        CTxtRange::~CTxtRange((CTxtRange *)String);
                        CDisplay::Thaw(v111);
                        goto LABEL_24;
                      }
                      WordBreak = CTxtRange::Promote((CTxtRange *)String, (__int64)v139, (struct IUndoBuilder *)v141);
                      CTxtRange::Update_iFormat(v112, -1);
                      v113 = 0;
                      goto LABEL_387;
                    }
                    v114 = 4;
                  }
                  WordBreak = CTxtEdit::SetViewKind(this, v114);
                  Sel = WordBreak == 0;
                  CDisplay::Thaw(v111);
                  goto LABEL_24;
                case 0x4DDu:
                  if ( !v6 )
                    goto LABEL_23;
                  *(_DWORD *)v6 = *(_DWORD *)(*((_QWORD *)this + 8) + 72LL);
                  v100 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 288LL))(*((_QWORD *)this + 8));
                  *(_DWORD *)(v6 + 4) = v100;
                  *(_DWORD *)(v6 + 4) = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 8) + 64LL))(
                                          *((_QWORD *)this + 8),
                                          v100);
                  goto LABEL_22;
                case 0x4DEu:
                  if ( !v6 )
                    goto LABEL_23;
                  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, int))(**((_QWORD **)this + 8) + 336LL))(
                    *((_QWORD *)this + 8),
                    *(unsigned int *)v6,
                    *(unsigned int *)(v6 + 4),
                    0,
                    1);
                  goto LABEL_22;
                case 0x4DFu:
                  Sel = CTxtEdit::OnSetFontSize(this, v7, v15);
                  goto LABEL_23;
                case 0x4E0u:
                  if ( !v7 || !v6 )
                    goto LABEL_23;
                  *(_DWORD *)v7 = *((unsigned __int16 *)this + 101);
                  *(_DWORD *)v139 = *((unsigned __int16 *)this + 102);
                  goto LABEL_22;
                case 0x4E1u:
                  if ( ((unsigned int)v6 | (unsigned int)v7) >= 0x10000
                    || v7 | v6 && ((int)v7 >= v6 << 6 || v6 >= (int)((_DWORD)v7 << 6)) )
                  {
                    goto LABEL_23;
                  }
                  v122 = (CDisplay *)*((_QWORD *)this + 8);
                  *((_WORD *)this + 101) = v7;
                  *((_WORD *)this + 102) = v6;
                  CDisplay::UpdateView(v122);
                  goto LABEL_22;
                case 0x50Du:
                  Sel = ((unsigned __int64)*((unsigned __int16 *)this + 94) >> 7) & 1;
                  goto LABEL_23;
                case 0x50Eu:
                  if ( v6 == 1 )
                    v136 = 128;
                  else
                    v136 = 0;
                  *((_WORD *)this + 94) &= ~0x80u;
                  *((_WORD *)this + 94) |= v136;
                  goto LABEL_22;
                default:
                  goto LABEL_171;
              }
            }
            if ( a2 == 1025 )
            {
              Sel = CTxtEdit::OnSetSel(this, (unsigned __int16)v6, WORD1(v6));
              goto LABEL_23;
            }
            switch ( a2 )
            {
              case 0x301u:
                goto LABEL_307;
              case 0x302u:
LABEL_393:
                WordBreak = 0;
                if ( (unsigned int)CTxtEdit::IsntProtectedOrReadOnly(this, a2, v7, v6, 1) )
                {
                  v115 = CTxtEdit::GetSel(this);
                  WordBreak = CTxtEdit::PasteDataObjectToRange(
                                this,
                                0,
                                v115,
                                (unsigned __int16)hWndParent,
                                (struct _repastespecial *)v139,
                                (struct IUndoBuilder *)v141,
                                0);
                }
                break;
              case 0x303u:
                CTxtEdit::OnClear(this, v15);
                goto LABEL_23;
              case 0x304u:
LABEL_311:
                v95 = (struct IUndoMgr *)*((_QWORD *)this + 10);
LABEL_313:
                WordBreak = 0;
                if ( v95 )
                {
                  v96 = *((_DWORD *)this + 45);
                  if ( (v96 & 4) == 0 && (v96 & 0x100000) != 0 )
                  {
                    WordBreak = CTxtEdit::PopAndExecuteAntiEvent(this, v95, (void *)v7);
                    if ( !WordBreak )
                      Sel = 1;
                  }
                }
                break;
              case 0x305u:
                WordBreak = CLightDTEngine::RenderClipboardFormat((CTxtEdit *)((char *)this + 96), v7);
                Sel = WordBreak;
                break;
              case 0x306u:
                WordBreak = CLightDTEngine::RenderAllClipboardFormats((CTxtEdit *)((char *)this + 96));
                Sel = WordBreak;
                break;
              case 0x307u:
                WordBreak = 0;
                Sel = 0;
                break;
              default:
                goto LABEL_171;
            }
          }
LABEL_24:
          if ( v5 )
            *v5 = Sel;
          if ( CW32System::_fHaveAIMM && WordBreak == 1 )
          {
            v141 = 0;
            CTxtEdit::TxGetWindow(this, &v141);
            WordBreak = CW32System::AIMMDefWndProc(v141, v140, (unsigned __int64)hWndParent, (__int64)v139, v5);
          }
          v147 = &CGenUndoBuilder::`vftable'{for `IUndoBuilder'};
          v148 = &CGenUndoBuilder::`vftable'{for `IReEntrantComponent'};
          if ( (v156 & 0x10) == 0 )
          {
            v21 = *((_QWORD *)v153 + 18);
            v22 = *(void ****)(v21 + 16);
            v23 = (_QWORD *)(v21 + 16);
            while ( v22 )
            {
              if ( v22 == &v148 )
              {
                *v23 = v22[2];
                break;
              }
              v23 = v22 + 2;
              v22 = (void ***)v22[2];
            }
          }
          if ( (v156 & 1) != 0 )
          {
            if ( v151 )
            {
LABEL_37:
              CCallMgr::~CCallMgr((CCallMgr *)v157);
              return (unsigned int)WordBreak;
            }
            v24 = (CDetectURL *)*((_QWORD *)v153 + 19);
            if ( v24 )
            {
              v47 = (struct IUndoBuilder *)&v147;
              if ( !UndoMgr )
                v47 = 0;
              CDetectURL::ScanAndUpdate(v24, v47);
            }
            v25 = v153;
            if ( !(unsigned int)CCallMgr::GetChangeEvent(*((CCallMgr **)v153 + 18)) )
            {
              ((void (__fastcall *)(void ***))v147[4])(&v147);
              goto LABEL_37;
            }
            if ( !v155 )
              goto LABEL_37;
            if ( UndoMgr )
              goto LABEL_517;
            v31 = 0;
            v32 = 100;
            v33 = (v156 & 4) == 0;
            if ( (v156 & 4) != 0 )
            {
              v32 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v25 + 10) + 16LL))(*((_QWORD *)v25 + 10));
              v33 = (v156 & 4) == 0;
            }
            UndoMgr = CTxtEdit::CreateUndoMgr(v153, v32, (unsigned int)!v33 + 1);
            if ( UndoMgr )
            {
LABEL_517:
              if ( (v156 & 0xC) == 0 )
              {
                v34 = *((_QWORD *)v153 + 11);
                if ( v34 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 64LL))(v34);
              }
              if ( (v156 & 2) != 0 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)UndoMgr + 80LL))(UndoMgr);
              v31 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IAntiEvent *))(*(_QWORD *)UndoMgr + 24LL))(
                      UndoMgr,
                      v154,
                      v155);
            }
            v35 = v155;
            v36 = v155;
            v155 = 0;
            CommitAEList(v36, v153);
            if ( UndoMgr )
            {
              if ( !v31 )
                goto LABEL_37;
            }
            v37 = v35;
          }
          else
          {
            v37 = v155;
            if ( !v155 )
              goto LABEL_37;
          }
          DestroyAEList(v37);
          goto LABEL_37;
        }
        goto LABEL_73;
      }
      if ( v13 != 256 && v13 != 260 )
      {
        if ( !v13 )
          goto LABEL_17;
LABEL_14:
        if ( v13 != CW32System::_MSIMEReconvertMsg
          && v13 != CW32System::_MSIMEDocFeedMsg
          && v13 != CW32System::_MSIMEQueryPositionMsg )
        {
          goto LABEL_17;
        }
        goto LABEL_73;
      }
      if ( v12 != 229 )
        goto LABEL_17;
    }
  }
LABEL_73:
  v33 = (*((_DWORD *)this + 45) & 0x8000000) == 0;
  v141 = 0;
  if ( !v33 )
    CTxtEdit::TxGetWindow(this, &v141);
  v41 = (CTextMsgFilter *)CW32System::PvAlloc(0xA0u, 0x40u);
  if ( !v41 )
    goto LABEL_76;
  v27 = CTextMsgFilter::CTextMsgFilter(v41);
  v28 = v27;
  if ( !v27 )
    goto LABEL_76;
  v29 = (char *)this + 16;
  v30 = *(void (__fastcall **)(CTextMsgFilter *, HWND, char *))(*(_QWORD *)v27 + 24LL);
  if ( !this )
    v29 = 0;
  v30(v28, v141, v29);
  (*(void (__fastcall **)(char *, CTextMsgFilter *))(*((_QWORD *)this + 2) + 208LL))((char *)this + 16, v28);
LABEL_43:
  if ( (*(unsigned int (__fastcall **)(_QWORD, unsigned int *, HWND *, struct IUnknown ***, __int64 *))(**((_QWORD **)this + 38) + 32LL))(
         *((_QWORD *)this + 38),
         &v140,
         &hWndParent,
         &v139,
         &Sel) )
  {
LABEL_76:
    a2 = v140;
    v7 = (unsigned __int64)hWndParent;
    v6 = (__int64)v139;
    goto LABEL_17;
  }
  if ( a5 )
    *a5 = Sel;
  CCallMgr::~CCallMgr((CCallMgr *)v157);
  return 0;
}

```

## disassembly

```asm
0x180027b20  push    rbp
0x180027b22  push    rbx
0x180027b23  push    rsi
0x180027b24  push    r12
0x180027b26  push    r14
0x180027b28  push    r15
0x180027b2a  lea     rbp, [rsp-158h]
0x180027b32  sub     rsp, 258h
0x180027b39  mov     rax, cs:__security_cookie
0x180027b40  xor     rax, rsp
0x180027b43  mov     [rbp+180h+var_50], rax
0x180027b4a  mov     r15, [rbp+180h+arg_20]
0x180027b51  xorps   xmm0, xmm0
0x180027b54  mov     [rbp+180h+var_190], r15
0x180027b58  mov     rsi, r9
0x180027b5b  mov     [rsp+280h+var_228], edx
0x180027b5f  mov     r14, r8
0x180027b62  mov     [rsp+280h+hWndParent], r8
0x180027b67  mov     rbx, rcx
0x180027b6a  mov     [rsp+280h+var_230], r9
0x180027b6f  mov     [rsp+280h+var_240], 0
0x180027b78  movups  [rbp+180h+var_1B0], xmm0
0x180027b7c  movups  [rbp+180h+var_1A0], xmm0
0x180027b80  test    rcx, rcx
0x180027b83  jz      short loc_180027BB6
0x180027b85  mov     rax, [rcx+90h]
0x180027b8c  mov     qword ptr [rbp+180h+var_1B0+8], rax
0x180027b90  lea     rax, [rbp+180h+var_1B0]
0x180027b94  mov     [rcx+90h], rax
0x180027b9b  mov     qword ptr [rbp+180h+var_1B0], rcx
0x180027b9f  lea     rcx, [rbp+180h+var_1B0]; this
0x180027ba3  call    ?NotifyEnterContext@CCallMgr@@AEAAXXZ; CCallMgr::NotifyEnterContext(void)
0x180027ba8  mov     edx, [rsp+280h+var_228]
0x180027bac  mov     r14, [rsp+280h+hWndParent]
0x180027bb1  mov     rsi, [rsp+280h+var_230]
0x180027bb6  cmp     cs:?_MSMouseRoller@CW32System@@2IA, edx; uint CW32System::_MSMouseRoller
0x180027bbc  mov     r12d, 10h
0x180027bc2  mov     [rsp+280h+var_30], rdi
0x180027bca  jz      loc_180028568
0x180027bd0  cmp     qword ptr [rbx+130h], 0
0x180027bd8  lea     r9, cs:180000000h
0x180027bdf  mov     [rsp+280h+var_38], r13
0x180027be7  mov     ecx, 3FFh
0x180027bec  jnz     loc_180027E94
0x180027bf2  mov     eax, [rbx+0B4h]
0x180027bf8  mov     r13, rsi
0x180027bfb  mov     [rsp+280h+var_208], r14
0x180027c00  mov     r8, r14
0x180027c03  mov     edi, edx
0x180027c05  bt      eax, 1Ch
0x180027c09  jnb     loc_18002835D
0x180027c0f  cmp     edi, 468h
0x180027c15  ja      loc_180027E1F
0x180027c1b  jz      loc_180028081; jumptable 0000000180027E42 cases 1129-1131,1149
0x180027c21  cmp     edi, 10Dh
0x180027c27  ja      loc_18002806F
0x180027c2d  jz      loc_180028081; jumptable 0000000180027E42 cases 1129-1131,1149
0x180027c33  mov     eax, edi
0x180027c35  sub     eax, 51h ; 'Q'
0x180027c38  jz      loc_180028542
0x180027c3e  sub     eax, 0AFh
0x180027c43  jz      loc_1800285FD
0x180027c49  cmp     eax, 4
0x180027c4c  jz      loc_1800285FD
0x180027c52  test    edi, edi
0x180027c54  jz      short loc_180027C7A
0x180027c56  cmp     edi, cs:?_MSIMEReconvertMsg@CW32System@@2IA; jumptable 0000000180027E42 default case, cases 1132-1143,1145-1148,1150-1227
0x180027c5c  jz      loc_180028081; jumptable 0000000180027E42 cases 1129-1131,1149
0x180027c62  cmp     edi, cs:?_MSIMEDocFeedMsg@CW32System@@2IA; uint CW32System::_MSIMEDocFeedMsg
0x180027c68  jz      loc_180028081; jumptable 0000000180027E42 cases 1129-1131,1149
0x180027c6e  cmp     edi, cs:?_MSIMEQueryPositionMsg@CW32System@@2IA; uint CW32System::_MSIMEQueryPositionMsg
0x180027c74  jz      loc_180028081; jumptable 0000000180027E42 cases 1129-1131,1149
0x180027c7a  mov     ecx, [rbp+180h+var_1B8]
0x180027c7d  lea     rax, ??_7CGenUndoBuilder@@6BIUndoBuilder@@@; const CGenUndoBuilder::`vftable'{for `IUndoBuilder'}
0x180027c84  mov     [rbp+180h+var_200], rax
0x180027c88  and     ecx, 0FFFFFFE1h
0x180027c8b  lea     rax, ??_7CGenUndoBuilder@@6BIReEntrantComponent@@@; const CGenUndoBuilder::`vftable'{for `IReEntrantComponent'}
0x180027c92  mov     [rbp+180h+var_1E0], 0
0x180027c9a  or      ecx, 1
0x180027c9d  mov     [rbp+180h+var_1F8], rax
0x180027ca1  test    dword ptr [rbx+0B4h], 100000h
0x180027cab  mov     r13d, 1
0x180027cb1  mov     rax, [rbx+50h]
0x180027cb5  mov     [rbp+180h+var_1D8], rax
0x180027cb9  mov     [rbp+180h+var_1C8], 0
0x180027cc0  mov     [rbp+180h+var_1C0], 0
0x180027cc8  mov     [rbp+180h+var_1D0], rbx
0x180027ccc  mov     [rbp+180h+var_1B8], ecx
0x180027ccf  jz      loc_18002805D
0x180027cd5  mov     r8, [rbx+90h]
0x180027cdc  lea     rdi, [rbp+180h+var_200]
0x180027ce0  mov     rcx, r8
0x180027ce3  mov     [rsp+280h+var_220], rdi
0x180027ce8  mov     edx, r13d
0x180027ceb  call    ?GetComponent@CCallMgr@@QEAAPEAVIReEntrantComponent@@W4CompName@@@Z; CCallMgr::GetComponent(CompName)
0x180027cf0  xor     ecx, ecx
0x180027cf2  mov     [rbp+180h+var_1F0], r13d
0x180027cf6  test    rax, rax
0x180027cf9  lea     rdx, [rax-8]
0x180027cfd  cmovz   rdx, rcx
0x180027d01  mov     [rbp+180h+var_1E0], rdx
0x180027d05  mov     rax, [r8+10h]
0x180027d09  mov     [rbp+180h+var_1E8], rax
0x180027d0d  lea     rax, [rbp+180h+var_1F8]
0x180027d11  mov     [r8+10h], rax
0x180027d15  mov     edx, [rsp+280h+var_228]; unsigned int
0x180027d19  mov     r14, [rsp+280h+hWndParent]
0x180027d1e  mov     rsi, [rsp+280h+var_230]
0x180027d23  cmp     edx, 14h
0x180027d26  jnz     loc_180027FB4
0x180027d2c  mov     [rsp+280h+var_240], r13
0x180027d31  xor     edi, edi; jumptable 0000000180027FFF cases 188,189,200
0x180027d33  test    r15, r15
0x180027d36  jz      short loc_180027D40
0x180027d38  mov     rax, [rsp+280h+var_240]
0x180027d3d  mov     [r15], rax
0x180027d40  cmp     cs:?_fHaveAIMM@CW32System@@2HA, 0; int CW32System::_fHaveAIMM
0x180027d47  jnz     loc_1800280C5
0x180027d4d  test    byte ptr [rbp+180h+var_1B8], 10h
0x180027d51  lea     rax, ??_7CGenUndoBuilder@@6BIUndoBuilder@@@; const CGenUndoBuilder::`vftable'{for `IUndoBuilder'}
0x180027d58  mov     [rbp+180h+var_200], rax
0x180027d5c  lea     rax, ??_7CGenUndoBuilder@@6BIReEntrantComponent@@@; const CGenUndoBuilder::`vftable'{for `IReEntrantComponent'}
0x180027d63  mov     [rbp+180h+var_1F8], rax
0x180027d67  jnz     short loc_180027D95
0x180027d69  mov     rax, [rbp+180h+var_1D0]
0x180027d6d  mov     rcx, [rax+90h]
0x180027d74  mov     rax, [rcx+10h]
0x180027d78  add     rcx, 10h
0x180027d7c  test    rax, rax
0x180027d7f  jz      short loc_180027D95
0x180027d81  mov     rdx, [rax+10h]
0x180027d85  lea     r9, [rbp+180h+var_1F8]
0x180027d89  cmp     rax, r9
0x180027d8c  jnz     loc_180028339
0x180027d92  mov     [rcx], rdx
0x180027d95  test    byte ptr [rbp+180h+var_1B8], 1
0x180027d99  jz      loc_1800281DC
0x180027d9f  cmp     [rbp+180h+var_1E0], 0
0x180027da4  jnz     short loc_180027DE3
0x180027da6  mov     rax, [rbp+180h+var_1D0]
0x180027daa  mov     rcx, [rax+98h]; this
0x180027db1  test    rcx, rcx
0x180027db4  jnz     loc_1800281FD
0x180027dba  mov     rbx, [rbp+180h+var_1D0]
0x180027dbe  mov     rcx, [rbx+90h]; this
0x180027dc5  call    ?GetChangeEvent@CCallMgr@@QEAAHXZ; CCallMgr::GetChangeEvent(void)
0x180027dca  test    eax, eax
0x180027dcc  jnz     loc_180027EE1
0x180027dd2  mov     rax, [rbp+180h+var_200]
0x180027dd6  lea     rcx, [rbp+180h+var_200]
0x180027dda  mov     rax, [rax+20h]
0x180027dde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027de3  lea     rcx, [rbp+180h+var_1B0]; this
0x180027de7  call    ??1CCallMgr@@QEAA@XZ; CCallMgr::~CCallMgr(void)
0x180027dec  mov     eax, edi
0x180027dee  mov     r13, [rsp+280h+var_38]
0x180027df6  mov     rdi, [rsp+280h+var_30]
0x180027dfe  mov     rcx, [rbp+180h+var_50]
0x180027e05  xor     rcx, rsp; StackCookie
0x180027e08  call    __security_check_cookie
0x180027e0d  add     rsp, 258h
0x180027e14  pop     r15
0x180027e16  pop     r14
0x180027e18  pop     r12
0x180027e1a  pop     rsi
0x180027e1b  pop     rbx
0x180027e1c  pop     rbp
0x180027e1d  retn
0x180027e1f  lea     eax, [rdi-469h]; switch 100 cases
0x180027e25  cmp     eax, 63h
0x180027e28  ja      def_180027E42; jumptable 0000000180027E42 default case, cases 1132-1143,1145-1148,1150-1227
0x180027e2e  movzx   eax, ds:(byte_18002A1F8 - 180000000h)[r9+rax]
0x180027e37  mov     ecx, ds:(jpt_180027E42 - 180000000h)[r9+rax*4]
0x180027e3f  add     rcx, r9
0x180027e42  jmp     rcx; switch jump
0x180027e48  mov     rcx, rax; this
0x180027e4b  call    ??0CTextMsgFilter@@QEAA@XZ; CTextMsgFilter::CTextMsgFilter(void)
0x180027e50  mov     rsi, rax
0x180027e53  test    rax, rax
0x180027e56  jz      loc_1800280B2
0x180027e5c  mov     rdx, [rax]
0x180027e5f  lea     r8, [rbx+10h]
0x180027e63  xor     ecx, ecx
0x180027e65  test    rbx, rbx
0x180027e68  mov     rax, [rdx+18h]
0x180027e6c  cmovz   r8, rcx
0x180027e70  mov     rdx, [rsp+280h+var_220]
0x180027e75  mov     rcx, rsi
0x180027e78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e7d  mov     rax, [rbx+10h]
0x180027e81  lea     rcx, [rbx+10h]
0x180027e85  mov     rdx, rsi
0x180027e88  mov     rax, [rax+0D0h]
0x180027e8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e94  mov     rcx, [rbx+130h]
0x180027e9b  lea     rdx, [rsp+280h+var_240]
0x180027ea0  mov     [rsp+280h+var_260], rdx
0x180027ea5  lea     r9, [rsp+280h+var_230]
0x180027eaa  lea     r8, [rsp+280h+hWndParent]
0x180027eaf  lea     rdx, [rsp+280h+var_228]
0x180027eb4  mov     rax, [rcx]
0x180027eb7  mov     rax, [rax+20h]
0x180027ebb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ec0  test    eax, eax
0x180027ec2  jnz     loc_1800280B2
0x180027ec8  test    r15, r15
0x180027ecb  jnz     loc_180028631
0x180027ed1  lea     rcx, [rbp+180h+var_1B0]; this
0x180027ed5  call    ??1CCallMgr@@QEAA@XZ; CCallMgr::~CCallMgr(void)
0x180027eda  xor     eax, eax
0x180027edc  jmp     loc_180027DEE
0x180027ee1  cmp     [rbp+180h+var_1C0], 0
0x180027ee6  jz      loc_180027DE3
0x180027eec  cmp     [rbp+180h+var_1D8], 0
0x180027ef1  jnz     short loc_180027F32
0x180027ef3  xor     esi, esi
0x180027ef5  mov     eax, 64h ; 'd'
0x180027efa  test    byte ptr [rbp+180h+var_1B8], 4
0x180027efe  jz      short loc_180027F14
0x180027f00  mov     rcx, [rbx+50h]
0x180027f04  mov     rax, [rcx]
0x180027f07  mov     rax, [rax+10h]
0x180027f0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027f10  test    byte ptr [rbp+180h+var_1B8], 4
0x180027f14  mov     rcx, [rbp+180h+var_1D0]
0x180027f18  mov     r8d, esi
0x180027f1b  setnz   r8b
0x180027f1f  mov     edx, eax
0x180027f21  inc     r8d
0x180027f24  call    ?CreateUndoMgr@CTxtEdit@@QEAAPEAVIUndoMgr@@KW4USFlags@@@Z; CTxtEdit::CreateUndoMgr(ulong,USFlags)
0x180027f29  mov     [rbp+180h+var_1D8], rax
0x180027f2d  test    rax, rax
0x180027f30  jz      short loc_180027F80
0x180027f32  test    byte ptr [rbp+180h+var_1B8], 0Ch
0x180027f36  jnz     short loc_180027F51
0x180027f38  mov     rax, [rbp+180h+var_1D0]
0x180027f3c  mov     rcx, [rax+58h]
0x180027f40  test    rcx, rcx
0x180027f43  jz      short loc_180027F51
0x180027f45  mov     rax, [rcx]
0x180027f48  mov     rax, [rax+40h]
0x180027f4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027f51  test    byte ptr [rbp+180h+var_1B8], 2
0x180027f55  jz      short loc_180027F67
0x180027f57  mov     rcx, [rbp+180h+var_1D8]
0x180027f5b  mov     rax, [rcx]
0x180027f5e  mov     rax, [rax+50h]
0x180027f62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027f67  mov     rcx, [rbp+180h+var_1D8]
0x180027f6b  mov     r8, [rbp+180h+var_1C0]
0x180027f6f  mov     edx, [rbp+180h+var_1C8]
0x180027f72  mov     rax, [rcx]
0x180027f75  mov     rax, [rax+18h]
0x180027f79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027f7e  mov     esi, eax
0x180027f80  mov     rbx, [rbp+180h+var_1C0]
0x180027f84  mov     rdx, [rbp+180h+var_1D0]; struct CTxtEdit *
0x180027f88  mov     rcx, rbx; struct IAntiEvent *
0x180027f8b  mov     [rbp+180h+var_1C0], 0
0x180027f93  call    ?CommitAEList@@YAXPEAVIAntiEvent@@PEAVCTxtEdit@@@Z; CommitAEList(IAntiEvent *,CTxtEdit *)
0x180027f98  cmp     [rbp+180h+var_1D8], 0
0x180027f9d  jz      short loc_180027FA7
0x180027f9f  test    esi, esi
0x180027fa1  jz      loc_180027DE3
0x180027fa7  mov     rcx, rbx; struct IAntiEvent *
0x180027faa  call    ?DestroyAEList@@YAXPEAVIAntiEvent@@@Z; DestroyAEList(IAntiEvent *)
0x180027faf  jmp     loc_180027DE3
0x180027fb4  cmp     edx, 0B0h
0x180027fba  jbe     loc_180028215
0x180027fc0  mov     r8d, 200h; int
0x180027fc6  cmp     edx, r8d
0x180027fc9  ja      loc_180028108
0x180027fcf  jz      loc_180028307
0x180027fd5  add     edx, 0FFFFFF4Fh; switch 101 cases
0x180027fdb  cmp     edx, 64h
0x180027fde  ja      def_180027FFF; jumptable 0000000180027FFF default case, cases 178-180,191,192,195,202,204,207,210-212,216-255,259,263-274
0x180027fe4  lea     r9, cs:180000000h
0x180027feb  movzx   eax, ds:(byte_18002A2E8 - 180000000h)[r9+rdx]
0x180027ff4  mov     ecx, ds:(jpt_180027FFF - 180000000h)[r9+rax*4]
0x180027ffc  add     rcx, r9
0x180027fff  jmp     rcx; switch jump
0x180028005  test    byte ptr [rbx+0B4h], 8; jumptable 0000000180027FFF case 186
0x18002800c  jz      loc_1800283DF
0x180028012  mov     rcx, [rbx+40h]
0x180028016  mov     r8d, 0FFFFFFFFh
0x18002801c  mov     edx, [rbx+110h]
0x180028022  mov     rax, [rcx]
0x180028025  mov     rax, [rax+108h]
0x18002802c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028031  test    eax, eax
0x180028033  jz      loc_180028A59
0x180028039  mov     rcx, [rbx+40h]
0x18002803d  mov     rax, [rcx]
0x180028040  mov     rax, [rax+0B8h]
0x180028047  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002804c  movsxd  rcx, eax
0x18002804f  xor     eax, eax
0x180028051  mov     [rsp+280h+var_240], rcx
0x180028056  mov     edi, eax
0x180028058  jmp     loc_180027D33
  ... truncated ...
```
