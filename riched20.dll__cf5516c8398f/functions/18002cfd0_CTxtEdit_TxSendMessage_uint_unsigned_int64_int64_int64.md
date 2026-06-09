# CTxtEdit::TxSendMessage(uint,unsigned __int64,__int64,__int64 *)

- ea: `0x18002cfd0`
- end: `0x18002fb88`
- name: `?TxSendMessage@CTxtEdit@@UEAAJI_K_JPEA_J@Z`
- size: `11192`
- prototype: `__int64 __usercall@<rax>(CTxtEdit *__hidden this@<rcx>, unsigned int@<edx>, unsigned __int64@<r8>, __int64@<r9>, __int64 *)`
- caller_count: `0`
- callee_count: `131`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180006610`
- `0x180016b44`
- `0x180017ef0`
- `0x18001c988`
- `0x18001d040`
- `0x18001ebcc`
- `0x180022474`
- `0x180022780`
- `0x180023010`
- `0x180025440`
- `0x18002bb70`
- `0x18002c948`
- `0x18002c9d8`
- `0x18002cb28`
- `0x18002cc44`
- `0x18002cfd0`
- `0x18002fbe0`
- `0x18002fc30`
- `0x1800300b0`
- `0x180030400`
- `0x180030540`
- `0x180031580`
- `0x180031974`
- `0x1800319c0`
- `0x180031a38`
- `0x180031cbc`
- `0x180031d48`
- `0x1800321c8`
- `0x1800323d8`
- `0x180032d3c`
- `0x180033060`
- `0x180033b5c`
- `0x180038bd0`
- `0x180039294`
- `0x1800396fc`
- `0x18003a3b4`
- `0x18003dc58`
- `0x18003dfc0`
- `0x18003e190`
- `0x18003e2d4`
- `0x18003f6c0`
- `0x18003ffa8`
- `0x180040294`
- `0x180040318`
- `0x18004098c`
- `0x180040c1c`
- `0x1800412d4`
- `0x1800415e0`
- `0x180041c94`
- `0x18004206c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18002d828`
- `KERNEL32!GetCurrentThreadId` at `0x18002d828`
- `KERNEL32!GetProcessHeap` at `0x18002d8ea`
- `KERNEL32!GetProcessHeap` at `0x18002d8ea`
- `KERNEL32!HeapAlloc` at `0x18002d55f`
- `KERNEL32!HeapAlloc` at `0x18002d55f`
- `KERNEL32!GetSystemDefaultLangID` at `0x18002db2d`
- `KERNEL32!GetSystemDefaultLangID` at `0x18002db2d`
- `KERNEL32!FindAtomA` at `0x18002d854`
- `KERNEL32!FindAtomA` at `0x18002d854`
- `USER32!GetFocus` at `0x18002dcbb`
- `USER32!GetFocus` at `0x18002dcdb`
- `USER32!GetFocus` at `0x18002dcbb`
- `USER32!GetFocus` at `0x18002dcdb`
- `USER32!IsChild` at `0x18002dcc9`
- `USER32!IsChild` at `0x18002dcc9`
- `USER32!GetKeyState` at `0x18002e07a`
- `USER32!GetKeyState` at `0x18002e07a`

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
  HANDLE ProcessHeap; // rax
  CTextMsgFilter *v42; // rax
  int v43; // eax
  unsigned int DefaultCodePage; // ecx
  signed int v45; // r14d
  unsigned int v46; // edx
  unsigned int v47; // r12d
  struct IUndoBuilder *v48; // rdx
  DWORD CurrentThreadId; // eax
  __int64 v50; // rcx
  __int64 v51; // r8
  int TextRange; // eax
  __int16 v53; // cx
  int v54; // r13d
  int v55; // edx
  unsigned int v56; // r14d
  __int64 v57; // rax
  int v58; // r13d
  unsigned __int16 v59; // di
  int KeyboardFlag; // eax
  unsigned __int16 v61; // cx
  int v62; // ecx
  _WORD *v63; // rdi
  __int64 v64; // rax
  int v65; // eax
  LANGID SystemDefaultLangID; // ax
  unsigned int v67; // eax
  HKL v68; // r10
  CTxtSelection *v69; // r11
  HWND Focus; // rax
  int v71; // r9d
  void (__fastcall **v72)(CTxtEdit *, GUID *, HWND *); // rax
  const struct _GUID *v73; // rcx
  __int64 v74; // rcx
  __int16 v75; // ax
  unsigned __int64 v76; // rsi
  unsigned __int16 v77; // dx
  int v78; // r13d
  __int64 v79; // rcx
  __int64 v80; // rdi
  HDC v81; // rdx
  int v82; // r8d
  int v83; // r9d
  HWND v84; // rax
  int v85; // ecx
  int v86; // edx
  int v87; // r15d
  int v88; // eax
  int v89; // edi
  int v90; // eax
  LONG v91; // eax
  __int64 v92; // rcx
  struct IUndoBuilder *v93; // rdi
  __int64 v94; // rax
  unsigned int v95; // r9d
  struct IUndoMgr *v96; // rdx
  int v97; // eax
  __int64 v98; // rcx
  __int64 v99; // rcx
  HWND v100; // rax
  unsigned int v101; // eax
  CObjectMgr *ObjectMgr; // rax
  int SelMost; // eax
  int v104; // r10d
  int v105; // edi
  int v106; // r8d
  int v107; // r8d
  int CpFromAcp; // r14d
  int v109; // eax
  unsigned __int16 *v110; // r9
  unsigned int v111; // edx
  CDisplay *v112; // rsi
  const struct CTxtRange *v113; // r14
  __int64 v114; // rdx
  int v115; // ecx
  struct CTxtRange *v116; // rax
  CTxtSelection *v117; // rax
  __int16 v118; // r9
  unsigned __int16 v119; // di
  __int16 v120; // ax
  __int64 v121; // rcx
  int v122; // eax
  CDisplay *v123; // rcx
  CTxtRange *v124; // rsi
  CDisplay *v125; // r14
  int v126; // eax
  __int16 v127; // ax
  __int16 v128; // r12
  int v129; // eax
  __int16 v130; // cx
  __int16 v131; // cx
  __int64 v132; // rax
  __int64 v133; // rcx
  _DWORD *v134; // rcx
  _QWORD *v135; // rdx
  void *v136; // rsi
  __int16 v137; // cx
  __int64 Sel; // [rsp+40h] [rbp-C0h] BYREF
  HWND hWndParent; // [rsp+48h] [rbp-B8h] BYREF
  struct IUnknown **v140; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v141; // [rsp+58h] [rbp-A8h] BYREF
  HWND v142; // [rsp+60h] [rbp-A0h] BYREF
  int v143; // [rsp+68h] [rbp-98h]
  int v144; // [rsp+6Ch] [rbp-94h] BYREF
  HWND v145; // [rsp+70h] [rbp-90h] BYREF
  int v146; // [rsp+78h] [rbp-88h]
  int v147; // [rsp+7Ch] [rbp-84h] BYREF
  void **v148; // [rsp+80h] [rbp-80h] BYREF
  void **v149; // [rsp+88h] [rbp-78h] BYREF
  int v150; // [rsp+90h] [rbp-70h]
  __int64 v151; // [rsp+98h] [rbp-68h]
  __int64 v152; // [rsp+A0h] [rbp-60h]
  __int64 UndoMgr; // [rsp+A8h] [rbp-58h]
  struct CTxtEdit *v154; // [rsp+B0h] [rbp-50h]
  unsigned int v155; // [rsp+B8h] [rbp-48h]
  struct IAntiEvent *v156; // [rsp+C0h] [rbp-40h]
  int v157; // [rsp+C8h] [rbp-38h]
  _OWORD v158[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 *v159; // [rsp+F0h] [rbp-10h]
  PARAFORMAT2 v160; // [rsp+100h] [rbp+0h] BYREF
  struct _selchange String[3]; // [rsp+1C0h] [rbp+C0h] BYREF

  v5 = a5;
  v159 = a5;
  v6 = (__int64)a4;
  v141 = a2;
  v7 = (unsigned __int64)a3;
  hWndParent = a3;
  v140 = a4;
  Sel = 0;
  memset(v158, 0, sizeof(v158));
  if ( this )
  {
    *((_QWORD *)&v158[0] + 1) = *((_QWORD *)this + 18);
    *((_QWORD *)this + 18) = v158;
    *(_QWORD *)&v158[0] = this;
    CCallMgr::NotifyEnterContext((CCallMgr *)v158);
    a2 = v141;
    v7 = (unsigned __int64)hWndParent;
    v6 = (__int64)v140;
  }
  v9 = 16;
  if ( CW32System::_MSMouseRoller == a2 )
  {
    v59 = (unsigned int)CW32System::GetKeyboardFlag(0x30u, 0x11u) != 0 ? 8 : 0;
    KeyboardFlag = CW32System::GetKeyboardFlag(3u, 0x10u);
    v6 = (__int64)v140;
    v61 = v59 | 4;
    a2 = 522;
    v141 = 522;
    if ( !KeyboardFlag )
      v61 = v59;
    v62 = ((unsigned __int16)v7 << 16) | v61;
    v7 = v62;
    hWndParent = (HWND)v62;
  }
  if ( *((_QWORD *)this + 38) )
    goto LABEL_43;
  v10 = *((_DWORD *)this + 45);
  v11 = v6;
  v145 = (HWND)v7;
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
      v142 = 0;
      CTxtEdit::TxGetWindow(this, &v142);
      if ( v142 )
        CW32System::PostMessage(v142, 0x4CCu, 0x40u, 64);
    }
    v12 = (__int16)v145;
    v6 = (__int64)v140;
    v7 = (unsigned __int64)hWndParent;
    a2 = v141;
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
        v58 = v11 & 0x3FF;
        if ( v58 != 18 && v58 != 4 && v58 != 17 )
        {
LABEL_17:
          v148 = &CGenUndoBuilder::`vftable'{for `IUndoBuilder'};
          v152 = 0;
          v14 = v157 & 0xFFFFFFE0 | 1;
          v149 = &CGenUndoBuilder::`vftable'{for `IReEntrantComponent'};
          v33 = (*((_DWORD *)this + 45) & 0x100000) == 0;
          UndoMgr = *((_QWORD *)this + 10);
          v155 = 0;
          v156 = 0;
          v154 = this;
          v157 = v14;
          if ( v33 )
          {
            v15 = 0;
            v142 = 0;
            v157 = v14 | 0x10;
          }
          else
          {
            v15 = (struct IUndoBuilder *)&v148;
            v16 = *((_QWORD *)this + 18);
            v142 = (HWND)&v148;
            Component = CCallMgr::GetComponent(v16, 1);
            v150 = 1;
            v19 = Component - 8;
            if ( !Component )
              v19 = 0;
            v152 = v19;
            v151 = *(_QWORD *)(v18 + 16);
            *(_QWORD *)(v18 + 16) = &v149;
            a2 = v141;
            v7 = (unsigned __int64)hWndParent;
            v6 = (__int64)v140;
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
                v71 = 1200;
                if ( v7 )
                  v71 = v7;
                WordBreak = CTxtEdit::SetText(this, (const unsigned __int16 *)v6, 0x8000u, v71, v15, &Sel);
                break;
              case 0xDu:
                HIDWORD(String[0].nmhdr.hwndFrom) = 1;
                LODWORD(String[0].nmhdr.idFrom) = 1200;
                LODWORD(String[0].nmhdr.hwndFrom) = 2 * v7;
                *(_OWORD *)((char *)&String[0].nmhdr.idFrom + 4) = 0;
                Sel = (int)CTxtEdit::GetTextEx(this, (struct _gettextex *)String, (unsigned __int16 *)v6);
                goto LABEL_23;
              case 0xEu:
                v142 = (HWND)0x4B00000000BLL;
                Sel = (int)CTxtEdit::GetTextLengthEx(this, (struct _gettextlengthex *)&v142);
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
                  goto LABEL_174;
                v72 = *(void (__fastcall ***)(CTxtEdit *, GUID *, HWND *))this;
                v142 = 0;
                (*v72)(this, &IID_IUnknown, &v142);
                Sel = CW32System::LResultFromObject(v73, (unsigned __int64)hWndParent, (struct IUnknown *)v142);
                (*(void (__fastcall **)(HWND))(*(_QWORD *)v142 + 16LL))(v142);
                goto LABEL_23;
              case 0x50u:
                v63 = (_WORD *)((char *)this + 184);
                if ( (*((_WORD *)this + 92) & 0x100) != 0 && (v7 & 1) == 0 )
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
                goto LABEL_166;
              case 0x51u:
                v63 = (_WORD *)((char *)this + 184);
                if ( (*((_WORD *)this + 92) & 0x100) == 0 )
                  goto LABEL_168;
                if ( !v7
                  || ((v64 = *((_QWORD *)this + 20)) == 0
                    ? (SystemDefaultLangID = GetSystemDefaultLangID(),
                       v65 = CW32System::ConvertLanguageIDtoCodePage(SystemDefaultLangID))
                    : (v65 = *(unsigned __int16 *)(v64 + 18)),
                      v7 == CW32System::GetCharSet(v65, 0)) )
                {
                  LOBYTE(v7) = 1;
                  hWndParent = (HWND)1;
                }
                else
                {
                  LOBYTE(v7) = 0;
                  hWndParent = 0;
                }
LABEL_166:
                if ( (*v63 & 0x100) != 0 )
                {
                  WordBreak = 0;
                  if ( (v7 & 1) == 0 )
                    break;
                }
LABEL_168:
                CW32System::RefreshKeyboardLayout();
                if ( (CW32System::_wKeyboardFlags & 0x30) != 0 && (CW32System::_wKeyboardFlags & 3) != 0 )
                  CW32System::_wKeyboardFlags |= 0x8000u;
                if ( !CTxtEdit::GetSel(this) )
                {
LABEL_445:
                  CGenUndoBuilder::~CGenUndoBuilder((CGenUndoBuilder *)&v148);
                  CCallMgr::~CCallMgr((CCallMgr *)v158);
                  return 2147942414LL;
                }
                WordBreak = 0;
                v67 = CW32System::ConvertLanguageIDtoCodePage((unsigned __int16)v140);
                if ( CTxtSelection::CheckChangeFont(v69, v68, v67, 0, 0) )
LABEL_174:
                  WordBreak = 1;
                break;
              case 0x7Bu:
                WordBreak = CTxtEdit::OnContextMenu(this, v6);
                break;
              case 0xA7u:
LABEL_299:
                CTxtEdit::OnTxMButtonDown(this, (__int16)v6, SWORD1(v6), 0x80000000);
                goto LABEL_23;
              default:
                goto LABEL_174;
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
                    goto LABEL_419;
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
                    v94 = *(_QWORD *)this;
                    LODWORD(v145) = 0;
                    v147 = 0;
                    if ( !(*(unsigned int (__fastcall **)(CTxtEdit *, _QWORD, _QWORD, HWND *, _QWORD, int *))(v94 + 48))(
                            this,
                            0,
                            0,
                            &v145,
                            0,
                            &v147)
                      && v147 )
                    {
                      Sel = (int)v145;
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
                      goto LABEL_334;
                    Sel = (*(int (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD))(**((_QWORD **)this + 8) + 208LL))(
                            *((_QWORD *)this + 8),
                            (unsigned int)v7,
                            v6,
                            *(unsigned __int16 *)v6);
                    goto LABEL_23;
                  case 0xC5u:
                    v6 = v7;
                    v140 = (struct IUnknown **)v7;
                    goto LABEL_285;
                  case 0xC6u:
                    v74 = *((_QWORD *)this + 10);
                    goto LABEL_196;
                  case 0xC7u:
                    goto LABEL_314;
                  case 0xC9u:
                    LODWORD(v6) = v7;
                    v140 = (struct IUnknown **)v7;
                    goto LABEL_232;
                  case 0xCBu:
                    WordBreak = 0;
                    if ( (*(_DWORD *)(*((_QWORD *)this + 8) + 56LL) & 0x20000) == 0 || v7 && (!v6 || !*(_DWORD *)v6) )
                      goto LABEL_24;
                    v78 = 32;
                    if ( v7 > 0x20 )
                      hWndParent = (HWND)32;
                    memset_0(&v160, 0, sizeof(v160));
                    v79 = *((_QWORD *)this + 6);
                    v160.cbSize = 188;
                    v144 = 0;
                    v80 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v79 + 24LL))(v79);
                    GetECDefaultHeightAndWidth(this, v81, v82, v83, (int)CW32System::_yPerInchScreenDC, &v144, 0, 0);
                    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 6) + 32LL))(
                      *((_QWORD *)this + 6),
                      v80);
                    v84 = hWndParent;
                    if ( hWndParent )
                    {
                      v85 = *(_DWORD *)v6;
                      v143 = *(_DWORD *)v6;
                      if ( (unsigned __int64)hWndParent > 1 )
                      {
                        v86 = 0;
                        v143 = v85;
                        v146 = 0;
                        v78 = (int)hWndParent;
                        if ( (int)hWndParent <= 0 )
                          goto LABEL_278;
LABEL_271:
                        v87 = v143;
                        while ( 1 )
                        {
                          v143 = v86 + 1;
                          if ( (unsigned __int64)v84 > 1 )
                          {
                            v88 = *(_DWORD *)v6;
                            v143 = v86 + 1;
                          }
                          else
                          {
                            v88 = (v86 + 1) * v87;
                          }
                          v89 = CW32System::_xPerInchScreenDC;
                          v90 = CW32System::MulDiv(v88, v144, 4);
                          v91 = CW32System::MulDiv(v90, 1440, v89);
                          v92 = v146;
                          v6 += 4;
                          v86 = v143;
                          v146 = v143;
                          v160.rgxTabs[v92] = v91;
                          if ( v86 >= v78 )
                            break;
                          v84 = hWndParent;
                        }
                        v5 = v159;
LABEL_278:
                        v160.cTabCount = v78;
                        v160.dwMask = 16;
                        CParaFormat::Set((CParaFormat *)String, &v160);
                        v93 = (struct IUndoBuilder *)v142;
                        if ( v142 )
                          (*(void (__fastcall **)(HWND))(*(_QWORD *)v142 + 48LL))(v142);
                        v57 = CTxtEdit::OnSetParaFormat(this, 4u, (struct CParaFormat *)String, v93, 0x20000010u);
LABEL_139:
                        Sel = v57;
                        CTabsArray::Release(qword_1800A41E0, SHIWORD(String[0].nmhdr.code));
                        goto LABEL_23;
                      }
                    }
                    else
                    {
                      v143 = 32;
                    }
                    v86 = 0;
                    v146 = 0;
                    goto LABEL_271;
                  case 0xCDu:
                    CTxtEdit::ClearUndo(this, v15);
                    goto LABEL_23;
                  case 0xCEu:
                    if ( (*((_BYTE *)this + 180) & 8) == 0 )
                      goto LABEL_334;
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
                    goto LABEL_398;
                  case 0xD7u:
                    goto LABEL_331;
                  case 0x100u:
                    WordBreak = CTxtEdit::OnTxKeyDown(this, v7, v6, v15);
                    goto LABEL_24;
                  case 0x101u:
                    if ( v7 == 93 )
                    {
                      CTxtEdit::HandleKbdContextMenu(this);
                      v7 = (unsigned __int64)hWndParent;
                      WordBreak = 0;
                      v6 = (__int64)v140;
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
                        v53 = *((_WORD *)this + 92);
                        if ( (v53 & 3u) < 2
                          && (v53 & 0xCu) < 8
                          && (CW32System::_wKeyboardFlags & 0x30) != 0
                          && (CW32System::_wKeyboardFlags & 3) != 0
                          && (CW32System::_wKeyboardFlags & 0x8000) == 0 )
                        {
                          WORD1(String[0].nmhdr.hwndFrom) = (CW32System::_wKeyboardFlags & 1) != 0;
                          CTxtEdit::OnSetParaFormat(
                            this,
                            0,
                            (struct CParaFormat *)String,
                            (struct IUndoBuilder *)v142,
                            0x20010000u);
                          CTxtEdit::TxNotify(this, (WORD1(String[0].nmhdr.hwndFrom) != 0) + 1808, 0);
                          v7 = (unsigned __int64)hWndParent;
                          v6 = (__int64)v140;
                        }
                      }
                      v76 = (unsigned __int64)v6 >> 16;
                      if ( v7 == 17 )
                      {
                        if ( (v76 & 0x100) == 0 )
                          v9 = 32;
                        v140 = (struct IUnknown **)v9;
                      }
                      else
                      {
                        v140 = (struct IUnknown **)(((_BYTE)v76 != 54) + 1LL);
                        if ( GetKeyState(16) < 0 )
                        {
                          LOWORD(v9) = (_WORD)v140;
                        }
                        else
                        {
                          LOWORD(v9) = 3;
                          v140 = (struct IUnknown **)3;
                        }
                      }
                      CW32System::_wKeyboardFlags &= ~(v9 | 0x9000);
                    }
                    else if ( v7 == 18 )
                    {
                      v75 = 4160;
                      if ( (v6 & 0x1000000) == 0 )
                        v75 = 4224;
                      CW32System::_wKeyboardFlags &= ~v75;
                    }
                    goto LABEL_24;
                  case 0x102u:
                    if ( (CW32System::_wKeyboardFlags & 0x5000) == 0 )
                      goto LABEL_201;
                    if ( (CW32System::_wKeyboardFlags & 0x4000) != 0 )
                    {
                      v144 = 0;
                      CW32System::AnsiFilter(&v141, (unsigned __int64 *)&hWndParent, v6, &v144, 0);
                      LOWORD(v7) = (_WORD)hWndParent;
                      LODWORD(v6) = (_DWORD)v140;
                      goto LABEL_201;
                    }
                    CW32System::_wKeyboardFlags &= ~0x1000u;
                    goto LABEL_23;
                  case 0x104u:
                    if ( !(unsigned int)CTxtEdit::OnTxSysKeyDown(this, v7, v6, v15) )
                      goto LABEL_22;
                    goto LABEL_174;
                  case 0x105u:
                    if ( (unsigned int)(v7 - 16) > 2 )
                    {
                      v77 = CW32System::_wKeyboardFlags;
                    }
                    else
                    {
                      v77 = ~(unsigned __int16)GetKbdFlags(v7, v6) & CW32System::_wKeyboardFlags;
                      CW32System::_wKeyboardFlags = v77;
                    }
                    if ( (unsigned int)(v7 - 96) <= 9 || v7 == 12 || v7 == 45 || (unsigned int)(v7 - 33) <= 7 )
                    {
                      CW32System::_wKeyboardFlags = v77 | 0x4000;
                      if ( (unsigned int)(v7 - 96) > 9 )
                      {
                        if ( v7 == 12 )
                          v7 = 101;
                        else
                          v7 = *(unsigned __int8 *)(v7 + v38 + 630599);
                        hWndParent = (HWND)v7;
                      }
                      if ( !CW32System::_wNumKeyPad && v7 == 96 )
                        CW32System::_wKeyboardFlags = v77 | 0x6000;
                      CW32System::_wNumKeyPad = v7 + 10 * CW32System::_wNumKeyPad - 96;
                    }
                    goto LABEL_174;
                  case 0x106u:
                    WordBreak = CTxtEdit::OnTxSysChar(this, v7, v6, v15);
                    Sel = WordBreak;
                    if ( WordBreak )
                      goto LABEL_174;
                    goto LABEL_24;
                  case 0x113u:
                    CTxtEdit::OnTxTimer(this, v7);
                    goto LABEL_174;
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
                    goto LABEL_174;
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
LABEL_310:
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
                      if ( v141 == 517 )
                      {
                        WordBreak = CTxtEdit::OnTxRButtonUp(this, (__int16)v140, SWORD1(v140), v95, 0);
                      }
                      else if ( v141 == 516 )
                      {
                        WordBreak = CTxtEdit::OnTxRButtonDown(
                                      this,
                                      (__int16)v140,
                                      SWORD1(v140),
                                      (unsigned __int16)hWndParent);
                      }
                    }
                    goto LABEL_24;
                  case 0x207u:
                  case 0x209u:
                    goto LABEL_299;
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
LABEL_201:
                    WordBreak = CTxtEdit::OnTxChar(this, v7, v6, v15);
                    CW32System::_wKeyboardFlags &= ~0x1000u;
                    Sel = WordBreak;
                    goto LABEL_24;
                  default:
                    goto LABEL_174;
                }
              }
              goto LABEL_24;
            }
            if ( a2 > 0x401 )
            {
              switch ( a2 )
              {
                case 0x426u:
LABEL_398:
                  WordBreak = CTxtEdit::OnPosFromChar(this, v7, v6, &Sel);
                  goto LABEL_24;
                case 0x427u:
LABEL_331:
                  WordBreak = CTxtEdit::TxCharFromPos(this, (struct tagPOINT *)v6, &Sel);
                  goto LABEL_24;
                case 0x432u:
                  Sel = CLightDTEngine::CanPaste((CTxtEdit *)((char *)this + 96), 0, v7, 0);
                  goto LABEL_23;
                case 0x433u:
                  if ( (*((_BYTE *)this + 180) & 8) == 0 )
                    goto LABEL_334;
                  CTxtEdit::OnDisplayBand(this, (const struct tagRECT *)v6, 0);
                  goto LABEL_22;
                case 0x434u:
                  CTxtEdit::OnExGetSel(this, (struct _charrange *)v6);
                  goto LABEL_23;
                case 0x435u:
LABEL_285:
                  if ( !v6 )
                  {
                    LODWORD(v6) = 0x10000;
                    v140 = (struct IUnknown **)0x10000;
                  }
                  if ( (*((_DWORD *)this + 45) & 0x80000) != 0 && (int)v6 < 0 )
                  {
                    LODWORD(v6) = 0;
                    v140 = 0;
                  }
                  *((_DWORD *)this + 54) = v6;
                  goto LABEL_23;
                case 0x436u:
LABEL_232:
                  WordBreak = CTxtEdit::TxLineFromCp(this, v6, &Sel);
                  goto LABEL_24;
                case 0x437u:
                  if ( v6 )
                  {
                    LODWORD(v7) = *(_DWORD *)v6;
                    hWndParent = (HWND)*(int *)v6;
                    v6 = *(int *)(v6 + 4);
                    v140 = (struct IUnknown **)v6;
LABEL_419:
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
LABEL_334:
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
                  TextRange = CTxtEdit::GetTextRange(this, v104, SelMost - v104 + 1, (unsigned __int16 *)v6);
                  goto LABEL_120;
                case 0x43Fu:
                  v111 = *((_DWORD *)this + 45);
                  if ( (v111 & 0x80000) == 0 )
                    goto LABEL_372;
                  if ( v6 )
                  {
                    v111 = (v7 != 0 ? 0x20 : 0) | v111 & 0xFFFFFFDF;
                    *((_DWORD *)this + 45) = v111;
LABEL_372:
                    if ( v6 && (v111 & 0x80u) != 0 )
                      goto LABEL_23;
                  }
                  TextRange = CTxtEdit::OnHideSelectionChange(this, v7);
                  goto LABEL_120;
                case 0x440u:
                  goto LABEL_396;
                case 0x441u:
                  WordBreak = CDisplay::RequestResize(*((CDisplay **)this + 8));
                  goto LABEL_24;
                case 0x442u:
                  memset(String, 0, 36);
                  v117 = CTxtEdit::GetSel(this);
                  if ( v117 )
                    CTxtSelection::SetSelectionInfo(v117, String);
                  Sel = String[0].seltyp;
                  goto LABEL_23;
                case 0x444u:
                  v43 = *(_DWORD *)v6;
                  DefaultCodePage = 1200;
                  v45 = *(_DWORD *)(v6 + 4);
                  if ( *(_DWORD *)v6 == 60 )
                    goto LABEL_84;
                  if ( v43 == 92 || v43 == 116 )
                    goto LABEL_86;
                  if ( v43 == 84 )
                  {
LABEL_84:
                    if ( (v45 & 0x20000000) != 0 )
                      DefaultCodePage = CTxtEdit::GetDefaultCodePage(this, 0x444u);
LABEL_86:
                    v46 = *((_DWORD *)this + 45);
                    if ( (v46 & 0x80000) != 0 && v45 < 0 && *(int *)(v6 + 12) <= 0 )
                      v45 &= ~0x80000000;
                    if ( *(_DWORD *)v6 == 92 || (v47 = 0, *(_DWORD *)v6 == 60) )
                    {
                      v47 = 0x8000;
                      v45 &= ~(v46 >> 14) & 0x2000 | 0xF800003F;
                    }
                    BYTE4(String[0].nmhdr.hwndFrom) = 0;
                    CCharFormat::Set((CCharFormat *)String, (const struct CHARFORMAT2W *)v6, DefaultCodePage);
                    Sel = CTxtEdit::OnSetCharFormat(
                            this,
                            (unsigned __int64)hWndParent,
                            (struct CCharFormat *)String,
                            v15,
                            v45,
                            v47);
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
                  CObjectMgr::SetRECallback(ObjectMgr, (struct IRichEditOleCallback *)v140);
                  goto LABEL_22;
                case 0x447u:
                  WordBreak = 0;
                  if ( !(unsigned int)IsValidParaFormat((const struct _paraformat *)v6) )
                    goto LABEL_24;
                  v56 = *(_DWORD *)(v6 + 4);
                  if ( (v56 & 0x43000000) != 0 )
                    goto LABEL_24;
                  if ( (v56 & 0x10) != 0 )
                  {
                    v122 = *(__int16 *)(v6 + 26);
                    if ( *(_WORD *)(v6 + 26) )
                    {
                      v54 = 32;
                      v55 = 0;
                      if ( (__int16)v122 > 32 || (v54 = *(__int16 *)(v6 + 26), v122 > 0) )
                      {
                        do
                        {
                          if ( (*(_DWORD *)(v6 + 4LL * v55 + 28) & 0xF000000u) > 0x4000000 )
                            break;
                          ++v55;
                        }
                        while ( v55 < v54 );
                      }
                      if ( v55 != v54 )
                        goto LABEL_24;
                    }
                  }
                  if ( *(_DWORD *)v6 == 156 )
                    v56 = v56 & 0x8001003F | 0x20000000;
                  CParaFormat::Set((CParaFormat *)String, (const struct PARAFORMAT2 *)v6);
                  v57 = CTxtEdit::OnSetParaFormat(
                          this,
                          (unsigned __int64)hWndParent,
                          (struct CParaFormat *)String,
                          (struct IUndoBuilder *)v142,
                          v56);
                  goto LABEL_139;
                case 0x448u:
                  v50 = *((_QWORD *)this + 8);
                  v51 = 0x7FFFFF;
                  if ( v6 < 0x7FFFFF )
                    v51 = v6;
                  v140 = (struct IUnknown **)v51;
                  TextRange = (*(__int64 (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v50 + 88LL))(v50, v7);
                  goto LABEL_120;
                case 0x449u:
                case 0x44Au:
                  CTxtRange::CTxtRange((CTxtRange *)String, this, 0, -*((_DWORD *)this + 68));
                  hWndParent = (HWND)CW32System::ValidateStreamWparam((unsigned __int64)hWndParent);
                  if ( ((unsigned __int16)hWndParent & 0x8000) != 0 )
                  {
                    v124 = CTxtEdit::GetSel(this);
                    if ( !v124 )
                    {
                      CTxtRange::~CTxtRange((CTxtRange *)String);
                      goto LABEL_445;
                    }
                  }
                  else
                  {
                    v124 = (CTxtRange *)String;
                    if ( v141 != 1097 )
                      goto LABEL_459;
                    v15 = 0;
                    CTxtEdit::ClearUndo(this, (struct IUndoBuilder *)&v148);
                    if ( ((unsigned __int16)hWndParent & 0x1000) == 0 )
                      CTxtEdit::CloseFile(this, 0);
                  }
                  if ( v141 == 1097 )
                  {
                    if ( (*((_DWORD *)this + 44) & 0x200000) != 0
                      && (unsigned int)CTxtRange::IsProtected(v124, 0) == 2
                      && (unsigned int)CTxtEdit::QueryUseProtection(
                                         this,
                                         v124,
                                         v141,
                                         (unsigned __int64)hWndParent,
                                         (__int64)v140) )
                    {
                      CTxtEdit::Beep(this);
                      CTxtRange::~CTxtRange((CTxtRange *)String);
                      goto LABEL_23;
                    }
                    v125 = (CDisplay *)*((_QWORD *)this + 8);
                    CDisplay::Freeze(v125);
                    Sel = (int)CLightDTEngine::LoadFromEs(
                                 (CTxtEdit *)((char *)this + 96),
                                 v124,
                                 (int)hWndParent,
                                 (struct _editstream *)v140,
                                 0,
                                 v15);
                    if ( (*((_WORD *)this + 92) & 0x2000) != 0 )
                      CRchTxtPtr::Check_rpPF((CRchTxtPtr *)(*((_QWORD *)this + 37) + 8LL));
                    if ( *((char *)this + 180) < 0 )
                      CDisplay::SaveUpdateCaret(*((CDisplay **)this + 8), 1);
                    CDisplay::Thaw(v125);
LABEL_460:
                    CTxtRange::~CTxtRange((CTxtRange *)String);
                    goto LABEL_23;
                  }
LABEL_459:
                  Sel = CLightDTEngine::SaveToEs(
                          (CTxtEdit *)((char *)this + 96),
                          v124,
                          (int)hWndParent,
                          (struct _editstream *)v140);
                  goto LABEL_460;
                case 0x44Bu:
                  v105 = ValidateTextRange((struct _textrangew *)v6);
                  if ( !v105 )
                    goto LABEL_23;
                  CpFromAcp = CTxtEdit::GetCpFromAcp(this, *(_DWORD *)v6, v106);
                  v109 = v105 >= 0
                       ? 1 - CpFromAcp + CTxtEdit::GetCpFromAcp(this, *(_DWORD *)(v6 + 4), v107)
                       : *((_DWORD *)this + 68) + 1;
                  v110 = *(unsigned __int16 **)(v6 + 8);
                  if ( !v110 )
                    goto LABEL_23;
                  TextRange = CTxtEdit::SafeGetTextRange(this, CpFromAcp, v109, v110);
                  goto LABEL_120;
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
                  v96 = (struct IUndoMgr *)*((_QWORD *)this + 11);
                  goto LABEL_316;
                case 0x455u:
                  v74 = *((_QWORD *)this + 11);
LABEL_196:
                  if ( !v74 )
                    goto LABEL_23;
                  TextRange = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v74 + 72LL))(v74);
                  goto LABEL_120;
                case 0x456u:
                  v98 = *((_QWORD *)this + 10);
                  goto LABEL_325;
                case 0x457u:
                  v98 = *((_QWORD *)this + 11);
LABEL_325:
                  if ( !v98 )
                    goto LABEL_23;
                  TextRange = (*(__int64 (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v98 + 40LL))(v98, v7);
LABEL_120:
                  Sel = TextRange;
                  goto LABEL_23;
                case 0x458u:
                  v99 = *((_QWORD *)this + 10);
                  if ( v99 )
                  {
                    if ( !v7
                      || (v100 = (HWND)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v99 + 48LL))(v99),
                          hWndParent == v100) )
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
                  v132 = *((_QWORD *)this + 10);
                  if ( !v132 || (v133 = 4, (*(_BYTE *)(v132 + 32) & 8) == 0) )
                    v133 = 8;
                  if ( (*((_WORD *)this + 92) & 0x100) == 0 )
                    v9 = 32;
                  Sel |= v133 | v9;
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
                      v136 = (void *)*((_QWORD *)this + 19);
                      if ( v136 )
                      {
                        CDetectURL::~CDetectURL(*((CDetectURL **)this + 19));
                        CW32System::FreePv(v136);
                        *((_QWORD *)this + 19) = 0;
                      }
                    }
                    goto LABEL_24;
                  }
                  v134 = CW32System::PvAlloc(0x30u, 0x40u);
                  if ( !v134 )
                  {
                    *((_QWORD *)this + 19) = 0;
                    WordBreak = -2147024882;
                    Sel = -2147024882;
                    goto LABEL_24;
                  }
                  *(_QWORD *)v134 = &CDetectURL::`vftable';
                  v135 = (_QWORD *)((char *)this + 128);
                  v134[10] &= ~1u;
                  v134[6] = 1;
                  v134[7] = 0x3FFFFFFF;
                  if ( this != (CTxtEdit *)-128LL )
                  {
                    *((_QWORD *)v134 + 1) = *v135;
                    *v135 = v134;
                  }
                  *((_QWORD *)v134 + 2) = this;
                  *((_QWORD *)this + 19) = v134;
                  goto LABEL_23;
                case 0x45Cu:
                  if ( *((_QWORD *)this + 19) )
                    goto LABEL_22;
                  goto LABEL_23;
                case 0x45Eu:
                  TextRange = CTxtEdit::GetTextEx(this, (struct _gettextex *)v7, (unsigned __int16 *)v6);
                  goto LABEL_120;
                case 0x45Fu:
                  TextRange = CTxtEdit::GetTextLengthEx(this, (struct _gettextlengthex *)v7);
                  goto LABEL_120;
                case 0x461u:
                  WordBreak = 0;
                  if ( v7 )
                    WordBreak = CTxtEdit::SetText(
                                  this,
                                  (const unsigned __int16 *)v6,
                                  *(_DWORD *)v7,
                                  *(_DWORD *)(v7 + 4),
                                  (struct IUndoBuilder *)v142,
                                  &Sel);
                  goto LABEL_24;
                case 0x46Cu:
                  if ( v7 )
                    TextRange = CTxtEdit::GetCpFromAcp(this, v6, 512);
                  else
                    TextRange = CTxtEdit::GetAcpFromCp(this, v6, 512);
                  goto LABEL_120;
                case 0x478u:
                  *((_DWORD *)this + 45) &= 0xFF9FFFFF;
                  *((_DWORD *)this + 45) |= ((v6 & 1) << 22) | ((_DWORD)v6 << 20) & 0x200000;
                  *((_WORD *)this + 92) &= ~0x400u;
                  *((_WORD *)this + 92) |= ((_WORD)v6 << 6) & 0x400;
                  *((_WORD *)this + 94) &= 0xFFF9u;
                  *((_WORD *)this + 94) |= ((unsigned __int64)v6 >> 3) & 4 | ((unsigned __int64)v6 >> 6) & 2;
                  goto LABEL_22;
                case 0x479u:
                  v126 = *((_DWORD *)this + 45);
                  if ( (v126 & 0x200000) != 0 )
                    Sel |= 2uLL;
                  if ( (v126 & 0x400000) != 0 )
                    Sel |= 1uLL;
                  if ( (*((_WORD *)this + 92) & 0x400) != 0 )
                    Sel |= 0x10uLL;
                  v127 = *((_WORD *)this + 94);
                  if ( (v127 & 2) != 0 )
                    Sel |= 0x80uLL;
                  if ( (v127 & 4) != 0 )
                    Sel |= 0x20uLL;
                  goto LABEL_23;
                case 0x497u:
                  TextRange = CTxtEdit::GetDefaultCodePage(this, v7);
                  goto LABEL_120;
                case 0x4A8u:
                  *((_WORD *)this + 94) |= 0x200u;
                  goto LABEL_23;
                case 0x4C8u:
                  if ( v6 )
                  {
                    v118 = *((_WORD *)this + 92);
                    v119 = *(_WORD *)(v6 + 4) & *(_WORD *)(v6 + 6)
                         | ~*(_WORD *)(v6 + 4)
                         & ((*((_WORD *)this + 94) >> 2) & 0x40
                          | ((v118 & 0x10) != 0 ? 4 : 0)
                          | ((v118 & 3) != 0 ? 8 : 0)
                          | ((v118 & 0xC) != 0 ? 0x10 : 0));
                    *((_WORD *)this + 94) = *((_WORD *)this + 94) & 0xFEFF | (4 * (v119 & 0x40));
                    if ( (*((_BYTE *)this + 180) & 1) == 0 )
                    {
                      if ( (((unsigned __int8)v118 >> 2) & 4) != (v119 & 4) )
                      {
                        v120 = 0;
                        if ( (v118 & 0x10) == 0 )
                          v120 = 16;
                        v121 = *((_QWORD *)this + 8);
                        *((_WORD *)this + 92) = v118 & 0xFFEF | v120;
                        if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v121 + 120LL))(v121) )
                        {
                          *(_DWORD *)(*((_QWORD *)this + 8) + 56LL) |= 0x80u;
                          (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 6) + 72LL))(
                            *((_QWORD *)this + 6),
                            0,
                            0);
                        }
                      }
                      *((_WORD *)this + 92) &= 0xFFF0u;
                      *((_WORD *)this + 92) |= (unsigned __int16)(v119 & 0x10 | (v119 >> 1) & 4) >> 2;
                      if ( (*((_BYTE *)this + 184) & 0xF) != 0 )
                        CTxtEdit::SetContextDirection(this, 1);
                    }
                  }
                  goto LABEL_23;
                case 0x4C9u:
                  if ( v6 && *(_DWORD *)v6 == 8 )
                  {
                    *(_WORD *)(v6 + 4) = 92;
                    *((_WORD *)v140 + 3) = ((*((_WORD *)this + 92) & 3) != 0 ? 8 : 0)
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
                  v128 = *((_WORD *)this + 93) & 1 | v6 & v7 | *((_WORD *)this + 93) & ~(_WORD)v6;
                  *((_WORD *)this + 93) = v128;
                  if ( (v7 & 1) != 0 )
                  {
                    v129 = CTxtEdit::HandleSetTextMode(this, 5u);
                    v130 = *((_WORD *)this + 93);
                    LOWORD(v7) = (_WORD)hWndParent;
                    if ( v129 < 0 )
                      v131 = v130 & 0xFFFE;
                    else
                      v131 = v130 | 2;
                    *((_WORD *)this + 93) = v131;
                  }
                  if ( (v7 & 0x1000) != 0 )
                    CTxtEdit::OrCharFlags(this, 1u, v15);
                  *((_WORD *)this + 93) = *((_WORD *)this + 93) & 0xFBFF
                                        | ((*((_WORD *)this + 93) & 0x200) == 0 && (v128 & 0x400) != 0 ? 0x400 : 0);
                  goto LABEL_484;
                case 0x4CDu:
LABEL_484:
                  if ( (*((_DWORD *)this + 45) & 0x80000) == 0 )
                    Sel = *((unsigned __int16 *)this + 93) | (unsigned __int64)Sel;
                  goto LABEL_23;
                case 0x4DCu:
                  v112 = (CDisplay *)*((_QWORD *)this + 8);
                  CDisplay::Freeze(v112);
                  if ( hWndParent == (HWND)5 )
                  {
                    WordBreak = CTxtEdit::GetViewKind(this, &Sel);
                    CDisplay::Thaw(v112);
                    goto LABEL_24;
                  }
                  if ( (*(_DWORD *)(*((_QWORD *)this + 8) + 56LL) & 0x20000) == 0 )
                    goto LABEL_392;
                  if ( (*((_BYTE *)this + 180) & 1) == 0 )
                    goto LABEL_392;
                  v113 = (const struct CTxtRange *)*((_QWORD *)this + 37);
                  if ( !v113 )
                    goto LABEL_392;
                  if ( hWndParent == (HWND)1 )
                  {
                    v115 = 2;
                  }
                  else
                  {
                    if ( hWndParent )
                    {
                      if ( (*((_WORD *)this + 92) & 0x2000) == 0
                        || !(unsigned int)CTxtEdit::IsntProtectedOrReadOnly(
                                            this,
                                            v141,
                                            (unsigned __int64)hWndParent,
                                            (__int64)v140,
                                            1) )
                      {
LABEL_392:
                        CDisplay::Thaw(v112);
                        goto LABEL_23;
                      }
                      CTxtRange::CTxtRange((CTxtRange *)String, v113);
                      WordBreak = 0;
                      if ( hWndParent != (HWND)2 )
                      {
                        if ( hWndParent == (HWND)3 )
                        {
                          WordBreak = CTxtRange::ExpandOutline((CTxtRange *)String, (__int16)v140, WORD1(v140) == 1);
                        }
                        else if ( hWndParent == (HWND)4 )
                        {
                          WordBreak = CTxtEdit::MoveSelection(this, (__int64)v140, (struct IUndoBuilder *)v142);
                          v114 = 1;
LABEL_390:
                          (*(void (__fastcall **)(const struct CTxtRange *, __int64))(*(_QWORD *)v113 + 568LL))(
                            v113,
                            v114);
                        }
                        *((_DWORD *)this + 45) |= 0x4000u;
                        Sel = WordBreak == 0;
                        CTxtRange::~CTxtRange((CTxtRange *)String);
                        CDisplay::Thaw(v112);
                        goto LABEL_24;
                      }
                      WordBreak = CTxtRange::Promote((CTxtRange *)String, (__int64)v140, (struct IUndoBuilder *)v142);
                      CTxtRange::Update_iFormat(v113, -1);
                      v114 = 0;
                      goto LABEL_390;
                    }
                    v115 = 4;
                  }
                  WordBreak = CTxtEdit::SetViewKind(this, v115);
                  Sel = WordBreak == 0;
                  CDisplay::Thaw(v112);
                  goto LABEL_24;
                case 0x4DDu:
                  if ( !v6 )
                    goto LABEL_23;
                  *(_DWORD *)v6 = *(_DWORD *)(*((_QWORD *)this + 8) + 72LL);
                  v101 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 288LL))(*((_QWORD *)this + 8));
                  *(_DWORD *)(v6 + 4) = v101;
                  *(_DWORD *)(v6 + 4) = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 8) + 64LL))(
                                          *((_QWORD *)this + 8),
                                          v101);
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
                  *(_DWORD *)v140 = *((unsigned __int16 *)this + 102);
                  goto LABEL_22;
                case 0x4E1u:
                  if ( ((unsigned int)v6 | (unsigned int)v7) >= 0x10000
                    || v7 | v6 && ((int)v7 >= v6 << 6 || v6 >= (int)((_DWORD)v7 << 6)) )
                  {
                    goto LABEL_23;
                  }
                  v123 = (CDisplay *)*((_QWORD *)this + 8);
                  *((_WORD *)this + 101) = v7;
                  *((_WORD *)this + 102) = v6;
                  CDisplay::UpdateView(v123);
                  goto LABEL_22;
                case 0x50Du:
                  Sel = ((unsigned __int64)*((unsigned __int16 *)this + 94) >> 7) & 1;
                  goto LABEL_23;
                case 0x50Eu:
                  if ( v6 == 1 )
                    v137 = 128;
                  else
                    v137 = 0;
                  *((_WORD *)this + 94) &= ~0x80u;
                  *((_WORD *)this + 94) |= v137;
                  goto LABEL_22;
                default:
                  goto LABEL_174;
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
                goto LABEL_310;
              case 0x302u:
LABEL_396:
                WordBreak = 0;
                if ( (unsigned int)CTxtEdit::IsntProtectedOrReadOnly(this, a2, v7, v6, 1) )
                {
                  v116 = CTxtEdit::GetSel(this);
                  WordBreak = CTxtEdit::PasteDataObjectToRange(
                                this,
                                0,
                                v116,
                                (unsigned __int16)hWndParent,
                                (struct _repastespecial *)v140,
                                (struct IUndoBuilder *)v142,
                                0);
                }
                break;
              case 0x303u:
                CTxtEdit::OnClear(this, v15);
                goto LABEL_23;
              case 0x304u:
LABEL_314:
                v96 = (struct IUndoMgr *)*((_QWORD *)this + 10);
LABEL_316:
                WordBreak = 0;
                if ( v96 )
                {
                  v97 = *((_DWORD *)this + 45);
                  if ( (v97 & 4) == 0 && (v97 & 0x100000) != 0 )
                  {
                    WordBreak = CTxtEdit::PopAndExecuteAntiEvent(this, v96, (void *)v7);
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
                goto LABEL_174;
            }
          }
LABEL_24:
          if ( v5 )
            *v5 = Sel;
          if ( CW32System::_fHaveAIMM && WordBreak == 1 )
          {
            v142 = 0;
            CTxtEdit::TxGetWindow(this, &v142);
            WordBreak = CW32System::AIMMDefWndProc(v142, v141, (unsigned __int64)hWndParent, (__int64)v140, v5);
          }
          v148 = &CGenUndoBuilder::`vftable'{for `IUndoBuilder'};
          v149 = &CGenUndoBuilder::`vftable'{for `IReEntrantComponent'};
          if ( (v157 & 0x10) == 0 )
          {
            v21 = *((_QWORD *)v154 + 18);
            v22 = *(void ****)(v21 + 16);
            v23 = (_QWORD *)(v21 + 16);
            while ( v22 )
            {
              if ( v22 == &v149 )
              {
                *v23 = v22[2];
                break;
              }
              v23 = v22 + 2;
              v22 = (void ***)v22[2];
            }
          }
          if ( (v157 & 1) != 0 )
          {
            if ( v152 )
            {
LABEL_37:
              CCallMgr::~CCallMgr((CCallMgr *)v158);
              return (unsigned int)WordBreak;
            }
            v24 = (CDetectURL *)*((_QWORD *)v154 + 19);
            if ( v24 )
            {
              v48 = (struct IUndoBuilder *)&v148;
              if ( !UndoMgr )
                v48 = 0;
              CDetectURL::ScanAndUpdate(v24, v48);
            }
            v25 = v154;
            if ( !(unsigned int)CCallMgr::GetChangeEvent(*((CCallMgr **)v154 + 18)) )
            {
              ((void (__fastcall *)(void ***))v148[4])(&v148);
              goto LABEL_37;
            }
            if ( !v156 )
              goto LABEL_37;
            if ( UndoMgr )
              goto LABEL_520;
            v31 = 0;
            v32 = 100;
            v33 = (v157 & 4) == 0;
            if ( (v157 & 4) != 0 )
            {
              v32 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v25 + 10) + 16LL))(*((_QWORD *)v25 + 10));
              v33 = (v157 & 4) == 0;
            }
            UndoMgr = CTxtEdit::CreateUndoMgr(v154, v32, (unsigned int)!v33 + 1);
            if ( UndoMgr )
            {
LABEL_520:
              if ( (v157 & 0xC) == 0 )
              {
                v34 = *((_QWORD *)v154 + 11);
                if ( v34 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 64LL))(v34);
              }
              if ( (v157 & 2) != 0 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)UndoMgr + 80LL))(UndoMgr);
              v31 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IAntiEvent *))(*(_QWORD *)UndoMgr + 24LL))(
                      UndoMgr,
                      v155,
                      v156);
            }
            v35 = v156;
            v36 = v156;
            v156 = 0;
            CommitAEList(v36, v154);
            if ( UndoMgr )
            {
              if ( !v31 )
                goto LABEL_37;
            }
            v37 = v35;
          }
          else
          {
            v37 = v156;
            if ( !v156 )
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
  v145 = 0;
  if ( !v33 )
    CTxtEdit::TxGetWindow(this, &v145);
  ProcessHeap = g_hHeap;
  if ( !g_hHeap )
  {
    ProcessHeap = GetProcessHeap();
    g_hHeap = ProcessHeap;
    if ( !ProcessHeap )
      goto LABEL_77;
  }
  v42 = (CTextMsgFilter *)HeapAlloc(ProcessHeap, 8u, 0xA0u);
  if ( !v42 )
    goto LABEL_77;
  v27 = CTextMsgFilter::CTextMsgFilter(v42);
  v28 = v27;
  if ( !v27 )
    goto LABEL_77;
  v29 = (char *)this + 16;
  v30 = *(void (__fastcall **)(CTextMsgFilter *, HWND, char *))(*(_QWORD *)v27 + 24LL);
  if ( !this )
    v29 = 0;
  v30(v28, v145, v29);
  (*(void (__fastcall **)(char *, CTextMsgFilter *))(*((_QWORD *)this + 2) + 208LL))((char *)this + 16, v28);
LABEL_43:
  if ( (*(unsigned int (__fastcall **)(_QWORD, unsigned int *, HWND *, struct IUnknown ***, __int64 *))(**((_QWORD **)this + 38) + 32LL))(
         *((_QWORD *)this + 38),
         &v141,
         &hWndParent,
         &v140,
         &Sel) )
  {
LABEL_77:
    a2 = v141;
    v7 = (unsigned __int64)hWndParent;
    v6 = (__int64)v140;
    goto LABEL_17;
  }
  if ( a5 )
    *a5 = Sel;
  CCallMgr::~CCallMgr((CCallMgr *)v158);
  return 0;
}

```

## disassembly

```asm
0x18002cfd0  push    rbp
0x18002cfd2  push    rbx
0x18002cfd3  push    rsi
0x18002cfd4  push    r12
0x18002cfd6  push    r14
0x18002cfd8  push    r15
0x18002cfda  lea     rbp, [rsp-158h]
0x18002cfe2  sub     rsp, 258h
0x18002cfe9  mov     rax, cs:__security_cookie
0x18002cff0  xor     rax, rsp
0x18002cff3  mov     [rbp+180h+var_50], rax
0x18002cffa  mov     r15, [rbp+180h+arg_20]
0x18002d001  xorps   xmm0, xmm0
0x18002d004  mov     [rbp+180h+var_190], r15
0x18002d008  mov     rsi, r9
0x18002d00b  mov     [rsp+280h+var_228], edx
0x18002d00f  mov     r14, r8
0x18002d012  mov     [rsp+280h+hWndParent], r8
0x18002d017  mov     rbx, rcx
0x18002d01a  mov     [rsp+280h+var_230], r9
0x18002d01f  mov     [rsp+280h+var_240], 0
0x18002d028  movups  [rbp+180h+var_1B0], xmm0
0x18002d02c  movups  [rbp+180h+var_1A0], xmm0
0x18002d030  test    rcx, rcx
0x18002d033  jz      short loc_18002D066
0x18002d035  mov     rax, [rcx+90h]
0x18002d03c  mov     qword ptr [rbp+180h+var_1B0+8], rax
0x18002d040  lea     rax, [rbp+180h+var_1B0]
0x18002d044  mov     [rcx+90h], rax
0x18002d04b  mov     qword ptr [rbp+180h+var_1B0], rcx
0x18002d04f  lea     rcx, [rbp+180h+var_1B0]; this
0x18002d053  call    ?NotifyEnterContext@CCallMgr@@AEAAXXZ; CCallMgr::NotifyEnterContext(void)
0x18002d058  mov     edx, [rsp+280h+var_228]
0x18002d05c  mov     r14, [rsp+280h+hWndParent]
0x18002d061  mov     rsi, [rsp+280h+var_230]
0x18002d066  cmp     cs:?_MSMouseRoller@CW32System@@2IA, edx; uint CW32System::_MSMouseRoller
0x18002d06c  mov     r12d, 10h
0x18002d072  mov     [rsp+280h+var_30], rdi
0x18002d07a  jz      loc_18002DA2B
0x18002d080  cmp     qword ptr [rbx+130h], 0
0x18002d088  lea     r9, cs:180000000h
0x18002d08f  mov     [rsp+280h+var_38], r13
0x18002d097  mov     ecx, 3FFh
0x18002d09c  jnz     loc_18002D33F
0x18002d0a2  mov     eax, [rbx+0B4h]
0x18002d0a8  mov     r13, rsi
0x18002d0ab  mov     [rsp+280h+var_210], r14
0x18002d0b0  mov     r8, r14
0x18002d0b3  mov     edi, edx
0x18002d0b5  bt      eax, 1Ch
0x18002d0b9  jnb     loc_18002D811
0x18002d0bf  cmp     edi, 468h
0x18002d0c5  ja      loc_18002D2CE
0x18002d0cb  jz      loc_18002D528; jumptable 000000018002D2F1 cases 1129-1131,1149
0x18002d0d1  cmp     edi, 10Dh
0x18002d0d7  ja      loc_18002D516
0x18002d0dd  jz      loc_18002D528; jumptable 000000018002D2F1 cases 1129-1131,1149
0x18002d0e3  mov     eax, edi
0x18002d0e5  sub     eax, 51h ; 'Q'
0x18002d0e8  jz      loc_18002DA05
0x18002d0ee  sub     eax, 0AFh
0x18002d0f3  jz      loc_18002DAC0
0x18002d0f9  cmp     eax, 4
0x18002d0fc  jz      loc_18002DAC0
0x18002d102  test    edi, edi
0x18002d104  jz      short loc_18002D12A
0x18002d106  cmp     edi, cs:?_MSIMEReconvertMsg@CW32System@@2IA; jumptable 000000018002D2F1 default case, cases 1132-1143,1145-1148,1150-1227
0x18002d10c  jz      loc_18002D528; jumptable 000000018002D2F1 cases 1129-1131,1149
0x18002d112  cmp     edi, cs:?_MSIMEDocFeedMsg@CW32System@@2IA; uint CW32System::_MSIMEDocFeedMsg
0x18002d118  jz      loc_18002D528; jumptable 000000018002D2F1 cases 1129-1131,1149
0x18002d11e  cmp     edi, cs:?_MSIMEQueryPositionMsg@CW32System@@2IA; uint CW32System::_MSIMEQueryPositionMsg
0x18002d124  jz      loc_18002D528; jumptable 000000018002D2F1 cases 1129-1131,1149
0x18002d12a  mov     ecx, [rbp+180h+var_1B8]
0x18002d12d  lea     rax, ??_7CGenUndoBuilder@@6BIUndoBuilder@@@; const CGenUndoBuilder::`vftable'{for `IUndoBuilder'}
0x18002d134  mov     [rbp+180h+var_200], rax
0x18002d138  and     ecx, 0FFFFFFE1h
0x18002d13b  lea     rax, ??_7CGenUndoBuilder@@6BIReEntrantComponent@@@; const CGenUndoBuilder::`vftable'{for `IReEntrantComponent'}
0x18002d142  mov     [rbp+180h+var_1E0], 0
0x18002d14a  or      ecx, 1
0x18002d14d  mov     [rbp+180h+var_1F8], rax
0x18002d151  test    dword ptr [rbx+0B4h], 100000h
0x18002d15b  mov     r13d, 1
0x18002d161  mov     rax, [rbx+50h]
0x18002d165  mov     [rbp+180h+var_1D8], rax
0x18002d169  mov     [rbp+180h+var_1C8], 0
0x18002d170  mov     [rbp+180h+var_1C0], 0
0x18002d178  mov     [rbp+180h+var_1D0], rbx
0x18002d17c  mov     [rbp+180h+var_1B8], ecx
0x18002d17f  jz      loc_18002D504
0x18002d185  mov     r8, [rbx+90h]
0x18002d18c  lea     rdi, [rbp+180h+var_200]
0x18002d190  mov     rcx, r8
0x18002d193  mov     [rsp+280h+var_220], rdi
0x18002d198  mov     edx, r13d
0x18002d19b  call    ?GetComponent@CCallMgr@@QEAAPEAVIReEntrantComponent@@W4CompName@@@Z; CCallMgr::GetComponent(CompName)
0x18002d1a0  xor     ecx, ecx
0x18002d1a2  mov     [rbp+180h+var_1F0], r13d
0x18002d1a6  test    rax, rax
0x18002d1a9  lea     rdx, [rax-8]
0x18002d1ad  cmovz   rdx, rcx
0x18002d1b1  mov     [rbp+180h+var_1E0], rdx
0x18002d1b5  mov     rax, [r8+10h]
0x18002d1b9  mov     [rbp+180h+var_1E8], rax
0x18002d1bd  lea     rax, [rbp+180h+var_1F8]
0x18002d1c1  mov     [r8+10h], rax
0x18002d1c5  mov     edx, [rsp+280h+var_228]; unsigned int
0x18002d1c9  mov     r14, [rsp+280h+hWndParent]
0x18002d1ce  mov     rsi, [rsp+280h+var_230]
0x18002d1d3  cmp     edx, 14h
0x18002d1d6  jnz     loc_18002D45F
0x18002d1dc  mov     [rsp+280h+var_240], r13
0x18002d1e1  xor     edi, edi; jumptable 000000018002D4AA cases 188,189,200
0x18002d1e3  test    r15, r15
0x18002d1e6  jz      short loc_18002D1F0
0x18002d1e8  mov     rax, [rsp+280h+var_240]
0x18002d1ed  mov     [r15], rax
0x18002d1f0  cmp     cs:?_fHaveAIMM@CW32System@@2HA, 0; int CW32System::_fHaveAIMM
0x18002d1f7  jnz     loc_18002D581
0x18002d1fd  test    byte ptr [rbp+180h+var_1B8], 10h
0x18002d201  lea     rax, ??_7CGenUndoBuilder@@6BIUndoBuilder@@@; const CGenUndoBuilder::`vftable'{for `IUndoBuilder'}
0x18002d208  mov     [rbp+180h+var_200], rax
0x18002d20c  lea     rax, ??_7CGenUndoBuilder@@6BIReEntrantComponent@@@; const CGenUndoBuilder::`vftable'{for `IReEntrantComponent'}
0x18002d213  mov     [rbp+180h+var_1F8], rax
0x18002d217  jnz     short loc_18002D245
0x18002d219  mov     rax, [rbp+180h+var_1D0]
0x18002d21d  mov     rcx, [rax+90h]
0x18002d224  mov     rax, [rcx+10h]
0x18002d228  add     rcx, 10h
0x18002d22c  test    rax, rax
0x18002d22f  jz      short loc_18002D245
0x18002d231  mov     rdx, [rax+10h]
0x18002d235  lea     r9, [rbp+180h+var_1F8]
0x18002d239  cmp     rax, r9
0x18002d23c  jnz     loc_18002D7ED
0x18002d242  mov     [rcx], rdx
0x18002d245  test    byte ptr [rbp+180h+var_1B8], 1
0x18002d249  jz      loc_18002D694
0x18002d24f  cmp     [rbp+180h+var_1E0], 0
0x18002d254  jnz     short loc_18002D293
0x18002d256  mov     rax, [rbp+180h+var_1D0]
0x18002d25a  mov     rcx, [rax+98h]; this
0x18002d261  test    rcx, rcx
0x18002d264  jnz     loc_18002D6B5
0x18002d26a  mov     rbx, [rbp+180h+var_1D0]
0x18002d26e  mov     rcx, [rbx+90h]; this
0x18002d275  call    ?GetChangeEvent@CCallMgr@@QEAAHXZ; CCallMgr::GetChangeEvent(void)
0x18002d27a  test    eax, eax
0x18002d27c  jnz     loc_18002D38C
0x18002d282  mov     rax, [rbp+180h+var_200]
0x18002d286  lea     rcx, [rbp+180h+var_200]
0x18002d28a  mov     rax, [rax+20h]
0x18002d28e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d293  lea     rcx, [rbp+180h+var_1B0]; this
0x18002d297  call    ??1CCallMgr@@QEAA@XZ; CCallMgr::~CCallMgr(void)
0x18002d29c  mov     eax, edi
0x18002d29e  mov     r13, [rsp+280h+var_38]
0x18002d2a6  mov     rdi, [rsp+280h+var_30]
0x18002d2ae  mov     rcx, [rbp+180h+var_50]
0x18002d2b5  xor     rcx, rsp; StackCookie
0x18002d2b8  call    __security_check_cookie
0x18002d2bd  add     rsp, 258h
0x18002d2c4  pop     r15
0x18002d2c6  pop     r14
0x18002d2c8  pop     r12
0x18002d2ca  pop     rsi
0x18002d2cb  pop     rbx
0x18002d2cc  pop     rbp
0x18002d2cd  retn
0x18002d2ce  lea     eax, [rdi-469h]; switch 100 cases
0x18002d2d4  cmp     eax, 63h
0x18002d2d7  ja      def_18002D2F1; jumptable 000000018002D2F1 default case, cases 1132-1143,1145-1148,1150-1227
0x18002d2dd  movzx   eax, ds:(byte_18002F698 - 180000000h)[r9+rax]
0x18002d2e6  mov     ecx, ds:(jpt_18002D2F1 - 180000000h)[r9+rax*4]
0x18002d2ee  add     rcx, r9
0x18002d2f1  jmp     rcx; switch jump
0x18002d2f3  mov     rcx, rax; this
0x18002d2f6  call    ??0CTextMsgFilter@@QEAA@XZ; CTextMsgFilter::CTextMsgFilter(void)
0x18002d2fb  mov     rsi, rax
0x18002d2fe  test    rax, rax
0x18002d301  jz      loc_18002D56E
0x18002d307  mov     rdx, [rax]
0x18002d30a  lea     r8, [rbx+10h]
0x18002d30e  xor     ecx, ecx
0x18002d310  test    rbx, rbx
0x18002d313  mov     rax, [rdx+18h]
0x18002d317  cmovz   r8, rcx
0x18002d31b  mov     rdx, [rsp+280h+var_210]
0x18002d320  mov     rcx, rsi
0x18002d323  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d328  mov     rax, [rbx+10h]
0x18002d32c  lea     rcx, [rbx+10h]
0x18002d330  mov     rdx, rsi
0x18002d333  mov     rax, [rax+0D0h]
0x18002d33a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d33f  mov     rcx, [rbx+130h]
0x18002d346  lea     rdx, [rsp+280h+var_240]
0x18002d34b  mov     [rsp+280h+var_260], rdx
0x18002d350  lea     r9, [rsp+280h+var_230]
0x18002d355  lea     r8, [rsp+280h+hWndParent]
0x18002d35a  lea     rdx, [rsp+280h+var_228]
0x18002d35f  mov     rax, [rcx]
0x18002d362  mov     rax, [rax+20h]
0x18002d366  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d36b  test    eax, eax
0x18002d36d  jnz     loc_18002D56E
0x18002d373  test    r15, r15
0x18002d376  jnz     loc_18002DAF4
0x18002d37c  lea     rcx, [rbp+180h+var_1B0]; this
0x18002d380  call    ??1CCallMgr@@QEAA@XZ; CCallMgr::~CCallMgr(void)
0x18002d385  xor     eax, eax
0x18002d387  jmp     loc_18002D29E
0x18002d38c  cmp     [rbp+180h+var_1C0], 0
0x18002d391  jz      loc_18002D293
0x18002d397  cmp     [rbp+180h+var_1D8], 0
0x18002d39c  jnz     short loc_18002D3DD
0x18002d39e  xor     esi, esi
0x18002d3a0  mov     eax, 64h ; 'd'
0x18002d3a5  test    byte ptr [rbp+180h+var_1B8], 4
0x18002d3a9  jz      short loc_18002D3BF
0x18002d3ab  mov     rcx, [rbx+50h]
0x18002d3af  mov     rax, [rcx]
0x18002d3b2  mov     rax, [rax+10h]
0x18002d3b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d3bb  test    byte ptr [rbp+180h+var_1B8], 4
0x18002d3bf  mov     rcx, [rbp+180h+var_1D0]
0x18002d3c3  mov     r8d, esi
0x18002d3c6  setnz   r8b
0x18002d3ca  mov     edx, eax
0x18002d3cc  inc     r8d
0x18002d3cf  call    ?CreateUndoMgr@CTxtEdit@@QEAAPEAVIUndoMgr@@KW4USFlags@@@Z; CTxtEdit::CreateUndoMgr(ulong,USFlags)
0x18002d3d4  mov     [rbp+180h+var_1D8], rax
0x18002d3d8  test    rax, rax
0x18002d3db  jz      short loc_18002D42B
0x18002d3dd  test    byte ptr [rbp+180h+var_1B8], 0Ch
0x18002d3e1  jnz     short loc_18002D3FC
0x18002d3e3  mov     rax, [rbp+180h+var_1D0]
0x18002d3e7  mov     rcx, [rax+58h]
0x18002d3eb  test    rcx, rcx
0x18002d3ee  jz      short loc_18002D3FC
0x18002d3f0  mov     rax, [rcx]
0x18002d3f3  mov     rax, [rax+40h]
0x18002d3f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d3fc  test    byte ptr [rbp+180h+var_1B8], 2
0x18002d400  jz      short loc_18002D412
0x18002d402  mov     rcx, [rbp+180h+var_1D8]
0x18002d406  mov     rax, [rcx]
0x18002d409  mov     rax, [rax+50h]
0x18002d40d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d412  mov     rcx, [rbp+180h+var_1D8]
0x18002d416  mov     r8, [rbp+180h+var_1C0]
0x18002d41a  mov     edx, [rbp+180h+var_1C8]
0x18002d41d  mov     rax, [rcx]
0x18002d420  mov     rax, [rax+18h]
0x18002d424  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d429  mov     esi, eax
0x18002d42b  mov     rbx, [rbp+180h+var_1C0]
0x18002d42f  mov     rdx, [rbp+180h+var_1D0]; struct CTxtEdit *
0x18002d433  mov     rcx, rbx; struct IAntiEvent *
0x18002d436  mov     [rbp+180h+var_1C0], 0
0x18002d43e  call    ?CommitAEList@@YAXPEAVIAntiEvent@@PEAVCTxtEdit@@@Z; CommitAEList(IAntiEvent *,CTxtEdit *)
0x18002d443  cmp     [rbp+180h+var_1D8], 0
0x18002d448  jz      short loc_18002D452
0x18002d44a  test    esi, esi
0x18002d44c  jz      loc_18002D293
0x18002d452  mov     rcx, rbx; struct IAntiEvent *
0x18002d455  call    ?DestroyAEList@@YAXPEAVIAntiEvent@@@Z; DestroyAEList(IAntiEvent *)
0x18002d45a  jmp     loc_18002D293
0x18002d45f  cmp     edx, 0B0h
0x18002d465  jbe     loc_18002D6CD
0x18002d46b  mov     r8d, 200h; int
0x18002d471  cmp     edx, r8d
0x18002d474  ja      loc_18002D5C4
0x18002d47a  jz      loc_18002D7BB
0x18002d480  add     edx, 0FFFFFF4Fh; switch 101 cases
0x18002d486  cmp     edx, 64h
0x18002d489  ja      def_18002D4AA; jumptable 000000018002D4AA default case, cases 178-180,191,192,195,202,204,207,210-212,216-255,259,263-274
0x18002d48f  lea     r9, cs:180000000h
0x18002d496  movzx   eax, ds:(byte_18002F788 - 180000000h)[r9+rdx]
0x18002d49f  mov     ecx, ds:(jpt_18002D4AA - 180000000h)[r9+rax*4]
0x18002d4a7  add     rcx, r9
0x18002d4aa  jmp     rcx; switch jump
0x18002d4ac  test    byte ptr [rbx+0B4h], 8; jumptable 000000018002D4AA case 186
0x18002d4b3  jz      loc_18002D887
0x18002d4b9  mov     rcx, [rbx+40h]
0x18002d4bd  mov     r8d, 0FFFFFFFFh
0x18002d4c3  mov     edx, [rbx+110h]
0x18002d4c9  mov     rax, [rcx]
0x18002d4cc  mov     rax, [rax+108h]
0x18002d4d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d4d8  test    eax, eax
0x18002d4da  jz      loc_18002DF04
0x18002d4e0  mov     rcx, [rbx+40h]
0x18002d4e4  mov     rax, [rcx]
0x18002d4e7  mov     rax, [rax+0B8h]
0x18002d4ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d4f3  movsxd  rcx, eax
0x18002d4f6  xor     eax, eax
0x18002d4f8  mov     [rsp+280h+var_240], rcx
0x18002d4fd  mov     edi, eax
0x18002d4ff  jmp     loc_18002D1E3
  ... truncated ...
```
