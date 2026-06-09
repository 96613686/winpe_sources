# CTxtEdit::OnTxRButtonUp(int,int,int,int,ulong,int)

- ea: `0x18016cfe4`
- end: `0x18016d5d3`
- name: `?OnTxRButtonUp@CTxtEdit@@AEAAJHHHHKH@Z`
- size: `1519`
- prototype: `__int64 __usercall@<rax>(CTxtEdit *__hidden this@<rcx>, int@<edx>, int@<r8d>, int@<r9d>, int, unsigned int, int)`
- caller_count: `8`
- callee_count: `23`
- tags: `loader_planting`

## callers

- `0x1800c13a0`
- `0x1800fa984`
- `0x1801177f0`
- `0x18011ba20`
- `0x18016b3e4`
- `0x180201d40`
- `0x180207468`
- `0x180207ad0`

## callees

- `0x1800117e4`
- `0x180016630`
- `0x18001b1b4`
- `0x1800966e4`
- `0x180098154`
- `0x1800af734`
- `0x1800b26ec`
- `0x1800c1b90`
- `0x1800e58b8`
- `0x1800f1f94`
- `0x1800f88e8`
- `0x1801018a8`
- `0x18010b5b8`
- `0x18010cd68`
- `0x180113728`
- `0x1801281a8`
- `0x180163f8c`
- `0x18016cfe4`
- `0x1801cd524`
- `0x1801ce314`
- `0x1801e95b8`
- `0x180272c30`
- `0x18027f010`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-0!GetParent` at `0x18016d442`
- `ext-ms-win-ntuser-window-l1-1-0!GetParent` at `0x18016d505`
- `ext-ms-win-ntuser-window-l1-1-0!GetParent` at `0x18016d442`
- `ext-ms-win-ntuser-window-l1-1-0!GetParent` at `0x18016d505`
- `ext-ms-win-ntuser-window-l1-1-2!ClientToScreen` at `0x18016d3bd`
- `ext-ms-win-ntuser-window-l1-1-2!ClientToScreen` at `0x18016d4f5`
- `ext-ms-win-ntuser-window-l1-1-2!ClientToScreen` at `0x18016d3bd`
- `ext-ms-win-ntuser-window-l1-1-2!ClientToScreen` at `0x18016d4f5`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PeekMessageW` at `0x18016d47b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PeekMessageW` at `0x18016d47b`
- `ext-ms-win-ntuser-menu-l1-1-0!CreatePopupMenu` at `0x18016d35d`
- `ext-ms-win-ntuser-menu-l1-1-0!CreatePopupMenu` at `0x18016d35d`
- `ext-ms-win-ntuser-menu-l1-1-0!DestroyMenu` at `0x18016d497`
- `ext-ms-win-ntuser-menu-l1-1-0!DestroyMenu` at `0x18016d5a5`
- `ext-ms-win-ntuser-menu-l1-1-0!DestroyMenu` at `0x18016d497`
- `ext-ms-win-ntuser-menu-l1-1-0!DestroyMenu` at `0x18016d5a5`
- `ext-ms-win-ntuser-menu-l1-1-0!AppendMenuW` at `0x18016d37a`
- `ext-ms-win-ntuser-menu-l1-1-0!AppendMenuW` at `0x18016d37a`
- `ext-ms-win-ntuser-menu-l1-1-0!TrackPopupMenu` at `0x18016d407`
- `ext-ms-win-ntuser-menu-l1-1-0!TrackPopupMenu` at `0x18016d57b`
- `ext-ms-win-ntuser-menu-l1-1-0!TrackPopupMenu` at `0x18016d407`
- `ext-ms-win-ntuser-menu-l1-1-0!TrackPopupMenu` at `0x18016d57b`

## pseudocode

```c
_BOOL8 __fastcall CTxtEdit::OnTxRButtonUp(
        CTxtEdit *this,
        UINT a2,
        unsigned int a3,
        int a4,
        int a5,
        unsigned int a6,
        char a7)
{
  struct COleObject *FirstObjectInRange; // r14
  CDisplay *v11; // rcx
  int v12; // ecx
  CTxtSelection *Sel; // rax
  CTxtSelection *v15; // rdi
  __int64 v16; // r15
  char v17; // si
  void (__fastcall ***v18)(_QWORD, GUID *, __int64 *); // rcx
  int v19; // r14d
  char v20; // r14
  UINT v21; // eax
  int v22; // esi
  int v23; // r14d
  UINT v24; // eax
  __int64 seltyp; // rdx
  __int64 v26; // rcx
  HMENU PopupMenu; // rax
  HWND v28; // rcx
  unsigned __int8 v29; // al
  HWND Parent; // rax
  HMENU v31; // rcx
  HWND v32; // rdi
  __int64 v33; // rcx
  __int64 v34; // rcx
  const struct tagPOINT *nReserved; // [rsp+20h] [rbp-91h]
  HMENU hMenu; // [rsp+40h] [rbp-71h] BYREF
  struct tagPOINT Point; // [rsp+48h] [rbp-69h] BYREF
  struct tagPOINT v38; // [rsp+50h] [rbp-61h] BYREF
  __int64 v39; // [rsp+58h] [rbp-59h] BYREF
  __int64 v40; // [rsp+60h] [rbp-51h] BYREF
  tagMSG Msg; // [rsp+68h] [rbp-49h] BYREF
  struct _selchange v42; // [rsp+98h] [rbp-19h] BYREF
  HWND hWnd; // [rsp+100h] [rbp+4Fh] BYREF
  int v44; // [rsp+118h] [rbp+67h] BYREF

  v44 = a4;
  FirstObjectInRange = 0;
  v38 = (struct tagPOINT)__PAIR64__(a3, a2);
  Point = (struct tagPOINT)__PAIR64__(a3, a2);
  hMenu = 0;
  v40 = 0;
  v11 = (CDisplay *)*((_QWORD *)this + 17);
  v39 = 0;
  hWnd = 0;
  memset(&v42, 0, sizeof(v42));
  CDisplay::PointuvFromPoint(v11, (struct Ptls6::tagLSPOINTUV *)&v39, &v38);
  if ( *((char *)this + 176) >= 0 )
    CTxtEdit::TxSetFocus(this);
  v12 = *((_DWORD *)this + 44);
  if ( (v12 & 0x80u) == 0 && (*((_DWORD *)this + 46) & 0x80) != 0 )
    return 1;
  if ( (v12 & 0x20000) != 0 )
  {
    *((_DWORD *)this + 44) = v12 & 0xBFFDFFFF;
    CTxtEdit::TxKillTimer(this, 0x1B2u);
  }
  Sel = CTxtEdit::GetSel(this);
  v15 = Sel;
  if ( !Sel )
    return 0;
  v16 = 0;
  CTxtSelection::SetSelectionInfo(Sel, &v42);
  v17 = a7;
  if ( *((_QWORD *)this + 30) )
  {
    if ( (unsigned int)CRchTxtPtr::GetObjectCount((CTxtSelection *)((char *)v15 + 8)) )
    {
      if ( (unsigned int)CTxtSelection::PointInSel(v15, v39, 0, 0, -1) || (v17 & 2) != 0 )
      {
        FirstObjectInRange = CObjectMgr::GetFirstObjectInRange(
                               (CObjectMgr *)(*((_QWORD *)v15 + 3) - 8LL),
                               v42.chrg.cpMin,
                               v42.chrg.cpMax,
                               0,
                               (struct CTxtStory *)((*((_QWORD *)v15 + 3) - 8LL) & -(__int64)(*((_QWORD *)v15 + 3) != 0)));
      }
      else
      {
        LODWORD(nReserved) = 0;
        if ( (unsigned int)CObjectMgr::HandleClick(*((_QWORD *)this + 30), this, &v39, 0) == 3 )
        {
          FirstObjectInRange = *(struct COleObject **)(*((_QWORD *)this + 30) + 48LL);
          CTxtSelection::SetSelectionInfo(v15, &v42);
        }
      }
    }
    v16 = *(_QWORD *)(*((_QWORD *)this + 30) + 24LL);
    if ( FirstObjectInRange )
    {
      v18 = (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)FirstObjectInRange + 7);
      if ( v18 )
        (**v18)(v18, &IID_IOleObject, &v40);
    }
  }
  v19 = v17 & 1;
  if ( (v17 & 1) == 0
    && *((_DWORD *)v15 + 26) == v19
    && (v17 & 2) == 0
    && !(unsigned int)CTxtSelection::PointInSel(v15, v39, 0, 0, -1) )
  {
    CTxtSelection::SetCaret(v15, v39, (unsigned int)(v19 + 1), 0);
  }
  LOBYTE(v44) = 0;
  if ( *((_QWORD *)this + 75)
    && !*((_DWORD *)v15 + 26)
    && (*(_DWORD *)CRchTxtPtr::GetCF((CTxtSelection *)((char *)v15 + 8)) & 0x10000000) == 0 )
  {
    if ( !v16 && (v17 & 1) == 0 && (v17 & 0x1C) == 0 )
      goto LABEL_44;
    CSpellChecker::MaybeShowContextMenu(
      *((CSpellChecker **)this + 75),
      (v17 & 0xC) != 0,
      *((_DWORD *)v15 + 10),
      &v38,
      nReserved,
      (bool *)&v44);
  }
  if ( !v16 || (_BYTE)v44 )
    goto LABEL_44;
  v20 = v17;
  Msg.hwnd = (HWND)v42.chrg;
  memset(&Msg.message, 0, 32);
  v21 = (v17 & 8) != 0;
  v22 = v17 & 0x10;
  Msg.message = v21;
  v23 = v20 & 4;
  if ( v23 )
  {
    v24 = v21 | 0x4000;
LABEL_37:
    Msg.message = v24;
    goto LABEL_38;
  }
  if ( !v22 )
  {
    v24 = v21 | 0x2000;
    goto LABEL_37;
  }
LABEL_38:
  CTxtEdit::AddSpellingInfoToContextMenu(this, v15, (struct _getcontextmenuexex *)&Msg);
  seltyp = v42.seltyp;
  *(&Msg.message + 1) = a2;
  LODWORD(Msg.wParam) = a3;
  if ( v23 )
  {
    LOWORD(seltyp) = v42.seltyp | 0x4000;
  }
  else if ( !v22 )
  {
    LOWORD(seltyp) = v42.seltyp | 0x2000;
  }
  (*(void (__fastcall **)(__int64, __int64, __int64, tagMSG *, HMENU *))(*(_QWORD *)v16 + 96LL))(
    v16,
    seltyp,
    v40,
    &Msg,
    &hMenu);
  if ( Msg.lParam )
    (*(void (__fastcall **)(LPARAM))(*(_QWORD *)Msg.lParam + 16LL))(Msg.lParam);
LABEL_44:
  if ( *((int *)v15 + 26) > 0 )
    CRunPtrBase::AdjustBackward((CTxtSelection *)((char *)v15 + 64));
  if ( *((_QWORD *)this + 69) )
  {
LABEL_62:
    v26 = v40;
    goto LABEL_63;
  }
  v26 = v40;
  if ( !v40 )
  {
    if ( (*(_DWORD *)CRchTxtPtr::GetCF((CTxtSelection *)((char *)v15 + 8)) & 0x10000000) != 0
      && !(unsigned int)CTxtEdit::TxGetWindow(this, &hWnd) )
    {
      if ( hMenu )
      {
        AppendMenuW(hMenu, 0x800u, 0, 0);
        PopupMenu = hMenu;
      }
      else
      {
        PopupMenu = CreatePopupMenu();
        hMenu = PopupMenu;
      }
      if ( PopupMenu )
      {
        CFreezeDisplay::CFreezeDisplay((CFreezeDisplay *)&v38, *((struct CDisplay **)this + 17));
        GetMathContextMenuInternal(v15, hMenu, 0, 0);
        ClientToScreen(hWnd, &Point);
        v28 = hWnd;
        v29 = CW32System::_fRightHanded;
        *((_DWORD *)this + 70) |= 0x100u;
        TrackPopupMenu(hMenu, v29 != 0 ? 10 : 2, Point.x, Point.y, 0, v28, 0);
        memset(&Msg, 0, sizeof(Msg));
        while ( PeekMessageW(&Msg, hWnd, 0x111u, 0x111u, 1u) )
        {
          if ( !(unsigned int)ProcessMathMenuID((struct ITextRange2 *)v15, Msg.wParam) )
          {
            Parent = GetParent(hWnd);
            if ( !Parent )
              Parent = hWnd;
            CW32System::SendMessage(Parent, 0x111u, Msg.wParam, Msg.lParam);
          }
        }
        v31 = hMenu;
        *((_DWORD *)this + 70) &= ~0x100u;
        DestroyMenu(v31);
        CFreezeDisplay::~CFreezeDisplay((CFreezeDisplay *)&v38);
      }
      return 0;
    }
    goto LABEL_62;
  }
LABEL_63:
  if ( hMenu )
  {
    if ( !(unsigned int)CTxtEdit::TxGetWindow(this, &hWnd) )
    {
      ClientToScreen(hWnd, &Point);
      v32 = GetParent(hWnd);
      if ( !v32 )
        v32 = hWnd;
      CTouchHandlerPtr::ShowGrippers((CTxtEdit *)((char *)this + 592), 0, 0);
      v33 = *((_QWORD *)this + 74);
      if ( v33 )
        (*(void (__fastcall **)(__int64, HMENU))(*(_QWORD *)v33 + 72LL))(v33, hMenu);
      TrackPopupMenu(hMenu, CW32System::_fRightHanded != 0 ? 10 : 2, Point.x, Point.y, 0, v32, 0);
      v34 = *((_QWORD *)this + 74);
      if ( v34 )
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v34 + 72LL))(v34, 0);
    }
    DestroyMenu(hMenu);
    v26 = v40;
  }
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  return v16 == 0;
}

```

## disassembly

```asm
0x18016cfe4  mov     [rsp-8+arg_8], rbx
0x18016cfe9  mov     [rsp-8+arg_18], r9d
0x18016cfee  push    rbp
0x18016cfef  push    rsi
0x18016cff0  push    rdi
0x18016cff1  push    r12
0x18016cff3  push    r13
0x18016cff5  push    r14
0x18016cff7  push    r15
0x18016cff9  lea     rbp, [rsp-0Fh]
0x18016cffe  sub     rsp, 0C0h
0x18016d005  xor     r14d, r14d
0x18016d008  mov     [rbp+3Fh+var_A0.x], edx
0x18016d00b  mov     [rbp+3Fh+var_A0.y], r8d
0x18016d00f  xorps   xmm0, xmm0
0x18016d012  mov     rax, qword ptr [rbp+3Fh+var_A0.x]
0x18016d016  mov     r12d, r8d
0x18016d019  mov     qword ptr [rbp+3Fh+Point.x], rax
0x18016d01d  lea     r8, [rbp+3Fh+var_A0]; struct tagPOINT *
0x18016d021  xor     eax, eax
0x18016d023  mov     [rbp+3Fh+hMenu], r14
0x18016d027  mov     r13d, edx
0x18016d02a  mov     dword ptr [rbp+3Fh+var_58.seltyp], eax
0x18016d02d  mov     rbx, rcx
0x18016d030  mov     [rbp+3Fh+var_90], r14
0x18016d034  mov     rcx, [rcx+88h]; this
0x18016d03b  lea     rdx, [rbp+3Fh+var_98]; struct Ptls6::tagLSPOINTUV *
0x18016d03f  mov     [rbp+3Fh+var_98], r14
0x18016d043  mov     [rbp+3Fh+hWnd], r14
0x18016d047  movups  xmmword ptr [rbp+3Fh+var_58.nmhdr.hwndFrom], xmm0
0x18016d04b  movups  xmmword ptr [rbp+3Fh+var_58.nmhdr.code], xmm0
0x18016d04f  call    ?PointuvFromPoint@CDisplay@@QEBAXAEAUtagLSPOINTUV@Ptls6@@AEBUtagPOINT@@@Z; CDisplay::PointuvFromPoint(Ptls6::tagLSPOINTUV &,tagPOINT const &)
0x18016d054  test    byte ptr [rbx+0B0h], 80h
0x18016d05b  jnz     short loc_18016D065
0x18016d05d  mov     rcx, rbx; this
0x18016d060  call    ?TxSetFocus@CTxtEdit@@QEAAXXZ; CTxtEdit::TxSetFocus(void)
0x18016d065  mov     ecx, [rbx+0B0h]
0x18016d06b  mov     edx, 1
0x18016d070  test    cl, cl
0x18016d072  js      short loc_18016D088
0x18016d074  mov     eax, [rbx+0B8h]
0x18016d07a  shr     eax, 7
0x18016d07d  test    dl, al
0x18016d07f  jz      short loc_18016D088
0x18016d081  mov     eax, edx
0x18016d083  jmp     loc_18016D4AE
0x18016d088  bt      ecx, 11h
0x18016d08c  jnb     short loc_18016D0A7
0x18016d08e  and     ecx, 0BFFDFFFFh
0x18016d094  mov     edx, 1B2h; unsigned int
0x18016d099  mov     [rbx+0B0h], ecx
0x18016d09f  mov     rcx, rbx; this
0x18016d0a2  call    ?TxKillTimer@CTxtEdit@@QEAAXI@Z; CTxtEdit::TxKillTimer(uint)
0x18016d0a7  mov     rcx, rbx; this
0x18016d0aa  call    ?GetSel@CTxtEdit@@QEAAPEAVCTxtSelection@@XZ; CTxtEdit::GetSel(void)
0x18016d0af  mov     rdi, rax
0x18016d0b2  test    rax, rax
0x18016d0b5  jz      loc_18016D4AC
0x18016d0bb  lea     rdx, [rbp+3Fh+var_58]; struct _selchange *
0x18016d0bf  mov     rcx, rax; this
0x18016d0c2  mov     r15, r14
0x18016d0c5  call    ?SetSelectionInfo@CTxtSelection@@QEAAXPEAU_selchange@@@Z; CTxtSelection::SetSelectionInfo(_selchange *)
0x18016d0ca  mov     esi, [rbp+3Fh+arg_30]
0x18016d0cd  cmp     [rbx+0F0h], r14
0x18016d0d4  jz      loc_18016D19F
0x18016d0da  lea     rcx, [rdi+8]; this
0x18016d0de  call    ?GetObjectCount@CRchTxtPtr@@QEBAJXZ; CRchTxtPtr::GetObjectCount(void)
0x18016d0e3  test    eax, eax
0x18016d0e5  jz      loc_18016D170
0x18016d0eb  mov     rdx, [rbp+3Fh+var_98]
0x18016d0ef  xor     r9d, r9d
0x18016d0f2  xor     r8d, r8d
0x18016d0f5  mov     [rsp+0F0h+nReserved], 0FFFFFFFFh
0x18016d0fd  mov     rcx, rdi
0x18016d100  call    ?PointInSel@CTxtSelection@@QEBAHUtagLSPOINTUV@Ptls6@@PEBURECTUV@@W4HITTEST@@J@Z; CTxtSelection::PointInSel(Ptls6::tagLSPOINTUV,RECTUV const *,HITTEST,long)
0x18016d105  test    eax, eax
0x18016d107  jnz     short loc_18016D148
0x18016d109  test    sil, 2
0x18016d10d  jnz     short loc_18016D148
0x18016d10f  mov     rcx, [rbx+0F0h]
0x18016d116  lea     r8, [rbp+3Fh+var_98]
0x18016d11a  xor     r9d, r9d
0x18016d11d  mov     [rsp+0F0h+nReserved], r14d
0x18016d122  mov     rdx, rbx
0x18016d125  call    ?HandleClick@CObjectMgr@@QEAA?AW4ClickStatus@@PEAVCTxtEdit@@AEBUtagLSPOINTUV@Ptls6@@HH@Z; CObjectMgr::HandleClick(CTxtEdit *,Ptls6::tagLSPOINTUV const &,int,int)
0x18016d12a  cmp     eax, 3
0x18016d12d  jnz     short loc_18016D170
0x18016d12f  mov     rax, [rbx+0F0h]
0x18016d136  lea     rdx, [rbp+3Fh+var_58]; struct _selchange *
0x18016d13a  mov     rcx, rdi; this
0x18016d13d  mov     r14, [rax+30h]
0x18016d141  call    ?SetSelectionInfo@CTxtSelection@@QEAAXPEAU_selchange@@@Z; CTxtSelection::SetSelectionInfo(_selchange *)
0x18016d146  jmp     short loc_18016D170
0x18016d148  mov     rax, [rdi+18h]
0x18016d14c  mov     r8d, [rbp+3Fh+var_58.chrg.cpMax]; int
0x18016d150  mov     edx, [rbp+3Fh+var_58.chrg.cpMin]; int
0x18016d153  lea     rcx, [rax-8]; this
0x18016d157  neg     rax
0x18016d15a  sbb     rax, rax
0x18016d15d  xor     r9d, r9d; int *
0x18016d160  and     rax, rcx
0x18016d163  mov     qword ptr [rsp+0F0h+nReserved], rax; struct CTxtStory *
0x18016d168  call    ?GetFirstObjectInRange@CObjectMgr@@QEAAPEAVCOleObject@@JJPEAJPEAVCTxtStory@@@Z; CObjectMgr::GetFirstObjectInRange(long,long,long *,CTxtStory *)
0x18016d16d  mov     r14, rax
0x18016d170  mov     rcx, [rbx+0F0h]
0x18016d177  mov     r15, [rcx+18h]
0x18016d17b  test    r14, r14
0x18016d17e  jz      short loc_18016D19F
0x18016d180  mov     rcx, [r14+38h]
0x18016d184  test    rcx, rcx
0x18016d187  jz      short loc_18016D19F
0x18016d189  mov     rax, [rcx]
0x18016d18c  lea     r8, [rbp+3Fh+var_90]
0x18016d190  lea     rdx, IID_IOleObject
0x18016d197  mov     rax, [rax]
0x18016d19a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016d19f  mov     r14d, esi
0x18016d1a2  and     r14d, 1
0x18016d1a6  jnz     short loc_18016D1E5
0x18016d1a8  cmp     [rdi+68h], r14d
0x18016d1ac  jnz     short loc_18016D1E5
0x18016d1ae  test    sil, 2
0x18016d1b2  jnz     short loc_18016D1E5
0x18016d1b4  mov     rdx, [rbp+3Fh+var_98]
0x18016d1b8  xor     r9d, r9d
0x18016d1bb  xor     r8d, r8d
0x18016d1be  mov     [rsp+0F0h+nReserved], 0FFFFFFFFh; struct tagPOINT *
0x18016d1c6  mov     rcx, rdi
0x18016d1c9  call    ?PointInSel@CTxtSelection@@QEBAHUtagLSPOINTUV@Ptls6@@PEBURECTUV@@W4HITTEST@@J@Z; CTxtSelection::PointInSel(Ptls6::tagLSPOINTUV,RECTUV const *,HITTEST,long)
0x18016d1ce  test    eax, eax
0x18016d1d0  jnz     short loc_18016D1E5
0x18016d1d2  mov     rdx, [rbp+3Fh+var_98]
0x18016d1d6  lea     r8d, [r14+1]
0x18016d1da  xor     r9d, r9d
0x18016d1dd  mov     rcx, rdi
0x18016d1e0  call    ?SetCaret@CTxtSelection@@QEAAXUtagLSPOINTUV@Ptls6@@HH@Z; CTxtSelection::SetCaret(Ptls6::tagLSPOINTUV,int,int)
0x18016d1e5  xor     eax, eax
0x18016d1e7  mov     byte ptr [rbp+3Fh+arg_18], al
0x18016d1ea  cmp     [rbx+258h], rax
0x18016d1f1  jz      short loc_18016D241
0x18016d1f3  cmp     [rdi+68h], eax
0x18016d1f6  jnz     short loc_18016D241
0x18016d1f8  lea     rcx, [rdi+8]; this
0x18016d1fc  call    ?GetCF@CRchTxtPtr@@QEBAPEBVCCharFormat@@XZ; CRchTxtPtr::GetCF(void)
0x18016d201  test    dword ptr [rax], 10000000h
0x18016d207  jnz     short loc_18016D241
0x18016d209  test    r15, r15
0x18016d20c  jnz     short loc_18016D21D
0x18016d20e  test    r14d, r14d
0x18016d211  jnz     short loc_18016D21D
0x18016d213  test    sil, 1Ch
0x18016d217  jz      loc_18016D301
0x18016d21d  mov     r8d, [rdi+28h]; int
0x18016d221  lea     rax, [rbp+3Fh+arg_18]
0x18016d225  mov     rcx, [rbx+258h]; this
0x18016d22c  lea     r9, [rbp+3Fh+var_A0]; struct tagPOINT *
0x18016d230  test    sil, 0Ch
0x18016d234  mov     [rsp+0F0h+var_C8], rax; bool *
0x18016d239  setnz   dl; bool
0x18016d23c  call    ?MaybeShowContextMenu@CSpellChecker@@QEAAJ_NJPEBUtagPOINT@@1PEA_N@Z; CSpellChecker::MaybeShowContextMenu(bool,long,tagPOINT const *,tagPOINT const *,bool *)
0x18016d241  test    r15, r15
0x18016d244  jz      loc_18016D301
0x18016d24a  cmp     byte ptr [rbp+3Fh+arg_18], 0
0x18016d24e  jnz     loc_18016D301
0x18016d254  mov     rax, qword ptr [rbp+3Fh+var_58.chrg.cpMin]
0x18016d258  mov     r14d, esi
0x18016d25b  mov     [rbp+3Fh+Msg.hwnd], rax
0x18016d25f  xorps   xmm0, xmm0
0x18016d262  xor     eax, eax
0x18016d264  mov     qword ptr [rbp+3Fh+Msg.time], 0
0x18016d26c  test    sil, 8
0x18016d270  mov     [rbp+3Fh+Msg.lParam], rax
0x18016d274  movdqu  xmmword ptr [rbp+3Fh+Msg.message], xmm0
0x18016d279  lea     ecx, [rax+1]
0x18016d27c  cmovnz  eax, ecx
0x18016d27f  and     esi, 10h
0x18016d282  mov     [rbp+3Fh+Msg.message], eax
0x18016d285  and     r14d, 4
0x18016d289  jz      short loc_18016D291
0x18016d28b  bts     eax, 0Eh
0x18016d28f  jmp     short loc_18016D299
0x18016d291  test    esi, esi
0x18016d293  jnz     short loc_18016D29C
0x18016d295  bts     eax, 0Dh
0x18016d299  mov     [rbp+3Fh+Msg.message], eax
0x18016d29c  lea     r8, [rbp+3Fh+Msg]; struct _getcontextmenuexex *
0x18016d2a0  mov     rdx, rdi; struct CTxtRange *
0x18016d2a3  mov     rcx, rbx; this
0x18016d2a6  call    ?AddSpellingInfoToContextMenu@CTxtEdit@@AEAAJPEBVCTxtRange@@AEAU_getcontextmenuexex@@@Z; CTxtEdit::AddSpellingInfoToContextMenu(CTxtRange const *,_getcontextmenuexex &)
0x18016d2ab  movzx   edx, [rbp+3Fh+var_58.seltyp]
0x18016d2af  mov     dword ptr [rbp+3Fh+Msg+0Ch], r13d
0x18016d2b3  mov     dword ptr [rbp+3Fh+Msg.wParam], r12d
0x18016d2b7  test    r14d, r14d
0x18016d2ba  jz      short loc_18016D2C3
0x18016d2bc  or      dx, 4000h
0x18016d2c1  jmp     short loc_18016D2CC
0x18016d2c3  test    esi, esi
0x18016d2c5  jnz     short loc_18016D2CC
0x18016d2c7  or      dx, 2000h
0x18016d2cc  mov     rax, [r15]
0x18016d2cf  lea     rcx, [rbp+3Fh+hMenu]
0x18016d2d3  mov     r8, [rbp+3Fh+var_90]
0x18016d2d7  lea     r9, [rbp+3Fh+Msg]
0x18016d2db  mov     qword ptr [rsp+0F0h+nReserved], rcx
0x18016d2e0  mov     rcx, r15
0x18016d2e3  mov     rax, [rax+60h]
0x18016d2e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016d2ec  mov     rcx, [rbp+3Fh+Msg.lParam]
0x18016d2f0  test    rcx, rcx
0x18016d2f3  jz      short loc_18016D301
0x18016d2f5  mov     rax, [rcx]
0x18016d2f8  mov     rax, [rax+10h]
0x18016d2fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016d301  cmp     dword ptr [rdi+68h], 0
0x18016d305  jle     short loc_18016D310
0x18016d307  lea     rcx, [rdi+40h]; this
0x18016d30b  call    ?AdjustBackward@CRunPtrBase@@QEAAXXZ; CRunPtrBase::AdjustBackward(void)
0x18016d310  cmp     qword ptr [rbx+228h], 0
0x18016d318  jnz     loc_18016D4CA
0x18016d31e  mov     rcx, [rbp+3Fh+var_90]
0x18016d322  test    rcx, rcx
0x18016d325  jnz     loc_18016D4CE
0x18016d32b  lea     rcx, [rdi+8]; this
0x18016d32f  call    ?GetCF@CRchTxtPtr@@QEBAPEBVCCharFormat@@XZ; CRchTxtPtr::GetCF(void)
0x18016d334  test    dword ptr [rax], 10000000h
0x18016d33a  jz      loc_18016D4CA
0x18016d340  lea     rdx, [rbp+3Fh+hWnd]; HWND *
0x18016d344  mov     rcx, rbx; this
0x18016d347  call    ?TxGetWindow@CTxtEdit@@QEAAJPEAPEAUHWND__@@@Z; CTxtEdit::TxGetWindow(HWND__ * *)
0x18016d34c  test    eax, eax
0x18016d34e  jnz     loc_18016D4CA
0x18016d354  mov     rcx, [rbp+3Fh+hMenu]; hMenu
0x18016d358  test    rcx, rcx
0x18016d35b  jnz     short loc_18016D36F
0x18016d35d  call    cs:__imp_CreatePopupMenu
0x18016d364  nop     dword ptr [rax+rax+00h]
0x18016d369  mov     [rbp+3Fh+hMenu], rax
0x18016d36d  jmp     short loc_18016D38A
0x18016d36f  xor     r9d, r9d; lpNewItem
0x18016d372  xor     r8d, r8d; uIDNewItem
0x18016d375  mov     edx, 800h; uFlags
0x18016d37a  call    cs:__imp_AppendMenuW
0x18016d381  nop     dword ptr [rax+rax+00h]
0x18016d386  mov     rax, [rbp+3Fh+hMenu]
0x18016d38a  test    rax, rax
0x18016d38d  jz      loc_18016D4AC
0x18016d393  mov     rdx, [rbx+88h]; struct CDisplay *
0x18016d39a  lea     rcx, [rbp+3Fh+var_A0]; this
0x18016d39e  call    ??0CFreezeDisplay@@QEAA@PEAVCDisplay@@@Z; CFreezeDisplay::CFreezeDisplay(CDisplay *)
0x18016d3a3  mov     rdx, [rbp+3Fh+hMenu]
0x18016d3a7  xor     r9d, r9d
0x18016d3aa  xor     r8d, r8d
0x18016d3ad  mov     rcx, rdi
0x18016d3b0  call    GetMathContextMenuInternal
0x18016d3b5  mov     rcx, [rbp+3Fh+hWnd]; hWnd
0x18016d3b9  lea     rdx, [rbp+3Fh+Point]; lpPoint
0x18016d3bd  call    cs:__imp_ClientToScreen
0x18016d3c4  nop     dword ptr [rax+rax+00h]
0x18016d3c9  mov     rcx, [rbp+3Fh+hWnd]
0x18016d3cd  mov     al, cs:?_fRightHanded@CW32System@@0EA; uchar CW32System::_fRightHanded
0x18016d3d3  bts     dword ptr [rbx+118h], 8
0x18016d3db  mov     r9d, [rbp+3Fh+Point.y]; y
0x18016d3df  neg     al
0x18016d3e1  mov     r8d, [rbp+3Fh+Point.x]; x
0x18016d3e5  sbb     edx, edx
0x18016d3e7  mov     [rsp+0F0h+prcRect], 0; prcRect
0x18016d3f0  mov     [rsp+0F0h+var_C8], rcx; hWnd
0x18016d3f5  and     edx, 8
0x18016d3f8  mov     rcx, [rbp+3Fh+hMenu]; hMenu
0x18016d3fc  add     edx, 2; uFlags
0x18016d3ff  mov     [rsp+0F0h+nReserved], 0; nReserved
0x18016d407  call    cs:__imp_TrackPopupMenu
0x18016d40e  nop     dword ptr [rax+rax+00h]
0x18016d413  xorps   xmm0, xmm0
0x18016d416  mov     esi, 1
0x18016d41b  movups  xmmword ptr [rbp+3Fh+Msg.hwnd], xmm0
0x18016d41f  mov     r14d, 111h
0x18016d425  movups  xmmword ptr [rbp-39h], xmm0
0x18016d429  movups  xmmword ptr [rbp+3Fh+Msg.time], xmm0
0x18016d42d  jmp     short loc_18016D469
0x18016d42f  mov     edx, dword ptr [rbp+3Fh+Msg.wParam]; unsigned int
0x18016d432  mov     rcx, rdi; struct ITextRange2 *
0x18016d435  call    ?ProcessMathMenuID@@YAJPEAUITextRange2@@K@Z; ProcessMathMenuID(ITextRange2 *,ulong)
0x18016d43a  test    eax, eax
0x18016d43c  jnz     short loc_18016D469
0x18016d43e  mov     rcx, [rbp+3Fh+hWnd]; hWnd
0x18016d442  call    cs:__imp_GetParent
0x18016d449  nop     dword ptr [rax+rax+00h]
0x18016d44e  mov     r9, [rbp+3Fh+Msg.lParam]; __int64
0x18016d452  mov     edx, r14d; unsigned int
0x18016d455  mov     r8, [rbp+3Fh+Msg.wParam]; unsigned __int64
0x18016d459  test    rax, rax
0x18016d45c  cmovz   rax, [rbp+3Fh+hWnd]
0x18016d461  mov     rcx, rax; hWnd
0x18016d464  call    ?SendMessage@CW32System@@SA_JPEAUHWND__@@I_K_J@Z; CW32System::SendMessage(HWND__ *,uint,unsigned __int64,__int64)
0x18016d469  mov     rdx, [rbp+3Fh+hWnd]; hWnd
0x18016d46d  lea     rcx, [rbp+3Fh+Msg]; lpMsg
0x18016d471  mov     r9d, r14d; wMsgFilterMax
0x18016d474  mov     [rsp+0F0h+nReserved], esi; wRemoveMsg
0x18016d478  mov     r8d, r14d; wMsgFilterMin
  ... truncated ...
```
