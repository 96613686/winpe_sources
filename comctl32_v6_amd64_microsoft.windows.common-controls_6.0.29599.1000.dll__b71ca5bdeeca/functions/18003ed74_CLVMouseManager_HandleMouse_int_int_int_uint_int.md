# CLVMouseManager::HandleMouse(int,int,int,uint,int)

- ea: `0x18003ed74`
- end: `0x18003fd58`
- name: `?HandleMouse@CLVMouseManager@@QEAAXHHHIH@Z`
- size: `4068`
- prototype: `void __usercall(CLVMouseManager *__hidden this@<rcx>, int@<edx>, int@<r8d>, int@<r9d>, unsigned int, int)`
- caller_count: `1`
- callee_count: `38`
- tags: `installer_update`

## callers

- `0x18005fe40`

## callees

- `0x180027b5c`
- `0x180027ddc`
- `0x18002b17c`
- `0x1800347f4`
- `0x180034ac0`
- `0x180036850`
- `0x18003c818`
- `0x18003d5cc`
- `0x18003d5fc`
- `0x18003e370`
- `0x18003e394`
- `0x18003ed74`
- `0x18003fd60`
- `0x18003fe20`
- `0x18003fe90`
- `0x18003feac`
- `0x180090c1c`
- `0x180092afc`
- `0x1800932c4`
- `0x18009de88`
- `0x1800bf09c`
- `0x1800dbd6c`
- `0x1800e53b0`
- `0x1800e6874`
- `0x1800ef828`
- `0x1801072a4`
- `0x18010f7e0`
- `0x180114520`
- `0x180114ebc`
- `0x18014c04c`
- `0x18014d1bc`
- `0x18014d7e8`
- `0x1801c50e4`
- `0x1801c79d4`
- `0x1801cb998`
- `0x1801cbaa4`
- `0x1801cc928`
- `0x1801d1010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003ef03`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003ef03`
- `USER32!GetDoubleClickTime` at `0x18003eff5`
- `USER32!GetDoubleClickTime` at `0x18003fab0`
- `USER32!GetDoubleClickTime` at `0x18003eff5`
- `USER32!GetDoubleClickTime` at `0x18003fab0`
- `USER32!GetFocus` at `0x18003ee27`
- `USER32!GetFocus` at `0x18003ee27`
- `USER32!ClientToScreen` at `0x18003fcef`
- `USER32!ClientToScreen` at `0x18003fcef`
- `USER32!GetCapture` at `0x18003eee1`
- `USER32!GetCapture` at `0x18003eee1`
- `USER32!SetTimer` at `0x18003f00d`
- `USER32!SetTimer` at `0x18003fac8`
- `USER32!SetTimer` at `0x18003f00d`
- `USER32!SetTimer` at `0x18003fac8`
- `USER32!SetCapture` at `0x18003eeb5`
- `USER32!SetCapture` at `0x18003eeb5`
- `USER32!KillTimer` at `0x18003edfc`
- `USER32!KillTimer` at `0x18003eefd`
- `USER32!KillTimer` at `0x18003f147`
- `USER32!KillTimer` at `0x18003f465`
- `USER32!KillTimer` at `0x18003edfc`
- `USER32!KillTimer` at `0x18003eefd`
- `USER32!KillTimer` at `0x18003f147`
- `USER32!KillTimer` at `0x18003f465`
- `USER32!SendMessageW` at `0x18003fd15`
- `USER32!SendMessageW` at `0x18003fd15`
- `USER32!IsWindow` at `0x18003ee15`
- `USER32!IsWindow` at `0x18003f4c3`
- `USER32!IsWindow` at `0x18003f520`
- `USER32!IsWindow` at `0x18003f7cc`
- `USER32!IsWindow` at `0x18003f9d8`
- `USER32!IsWindow` at `0x18003fa6c`
- `USER32!IsWindow` at `0x18003fc4f`
- `USER32!IsWindow` at `0x18003fd20`
- `USER32!IsWindow` at `0x18003ee15`
- `USER32!IsWindow` at `0x18003f4c3`
- `USER32!IsWindow` at `0x18003f520`
- `USER32!IsWindow` at `0x18003f7cc`
- `USER32!IsWindow` at `0x18003f9d8`
- `USER32!IsWindow` at `0x18003fa6c`
- `USER32!IsWindow` at `0x18003fc4f`
- `USER32!IsWindow` at `0x18003fd20`
- `USER32!UpdateWindow` at `0x18003f20c`
- `USER32!UpdateWindow` at `0x18003f7ae`
- `USER32!UpdateWindow` at `0x18003f20c`
- `USER32!UpdateWindow` at `0x18003f7ae`
- `USER32!GetShellWindow` at `0x18003ee8a`
- `USER32!GetShellWindow` at `0x18003ee8a`
- `USER32!IsChild` at `0x18003ee96`
- `USER32!IsChild` at `0x18003ee96`

## pseudocode

```c
void __fastcall CLVMouseManager::HandleMouse(CLVMouseManager *this, int a2, int a3, int a4, unsigned int a5, int a6)
{
  int v8; // r14d
  __int64 v10; // rcx
  HWND v11; // rbx
  CListView *v12; // rcx
  __int64 v13; // rbx
  __int64 v14; // rcx
  HWND v15; // rbx
  HWND ShellWindow; // rax
  __int64 v17; // rcx
  HWND v18; // rbx
  DWORD TickCount; // eax
  __int64 v20; // rcx
  __int64 v21; // rcx
  unsigned int v22; // r15d
  bool v23; // zf
  CLVInPlaceEditingManager *v24; // rcx
  CLVInPlaceEditingManager *v25; // rcx
  __int64 v26; // rcx
  __int16 v27; // bx
  unsigned int v28; // r12d
  int v29; // r8d
  UINT flags; // ecx
  UINT DoubleClickTime; // eax
  int v32; // r14d
  __int64 v33; // rax
  __int64 v34; // r13
  int v35; // eax
  int v36; // r12d
  CListGroup *v37; // r13
  __int64 v38; // rcx
  int *v39; // r8
  int v40; // edx
  GroupManagerHelpers *v41; // r14
  int GroupFail; // eax
  int ListviewItemIndex; // eax
  int v44; // r14d
  __int64 v45; // rdx
  int v46; // r13d
  int v47; // eax
  CLVFooter *v48; // rcx
  __int64 v49; // rcx
  __int64 v50; // rcx
  int iSubItem; // r8d
  CListView *v52; // rcx
  __int64 v53; // rcx
  UINT v54; // r9d
  __int64 v55; // rax
  BOOL v56; // r11d
  __int64 v57; // rcx
  UINT v58; // r9d
  CListView *v59; // r10
  int v60; // r11d
  __int64 v61; // r10
  int v62; // r11d
  int v63; // eax
  int v64; // r14d
  int v65; // eax
  int v66; // r9d
  __int64 v67; // r10
  __int64 v68; // r11
  __int64 v69; // r9
  LONG v70; // r8d
  LONG v71; // edx
  __int64 v72; // rcx
  int v73; // r12d
  BOOL v74; // r14d
  __int64 v75; // rax
  int CanEditSubItems; // eax
  __int64 v77; // r8
  BOOL v78; // r14d
  int v79; // ecx
  int v80; // edx
  BOOL v81; // eax
  __int128 v82; // xmm1
  __int128 v83; // xmm0
  __int128 v84; // xmm1
  UINT v85; // eax
  __int64 v86; // rcx
  __int64 v87; // rcx
  __int64 v88; // rcx
  int v90; // [rsp+30h] [rbp-D0h]
  int v93; // [rsp+3Ch] [rbp-C4h]
  __int16 v94; // [rsp+42h] [rbp-BEh]
  int v95; // [rsp+48h] [rbp-B8h]
  int v96; // [rsp+48h] [rbp-B8h]
  __int16 v97; // [rsp+4Ah] [rbp-B6h]
  int v98; // [rsp+54h] [rbp-ACh]
  int v99; // [rsp+58h] [rbp-A8h]
  int v100; // [rsp+60h] [rbp-A0h]
  __int64 v101; // [rsp+60h] [rbp-A0h]
  int v102; // [rsp+68h] [rbp-98h]
  HWND hWnd; // [rsp+70h] [rbp-90h]
  HWND v104; // [rsp+78h] [rbp-88h]
  HWND Focus; // [rsp+80h] [rbp-80h]
  __int64 v106; // [rsp+88h] [rbp-78h] BYREF
  __int128 v107; // [rsp+90h] [rbp-70h]
  __int64 v108; // [rsp+A0h] [rbp-60h]
  struct tagLVHITTESTINFO v109; // [rsp+A8h] [rbp-58h] BYREF
  struct tagPOINT Point; // [rsp+C0h] [rbp-40h] BYREF
  tagNMITEMACTIVATE v111; // [rsp+D0h] [rbp-30h] BYREF

  v8 = a2;
  v97 = HIWORD(a3);
  v94 = HIWORD(a4);
  if ( *((_DWORD *)this + 1) )
    return;
  v10 = *((_QWORD *)this + 14);
  v11 = *(HWND *)(v10 + 96);
  *((_DWORD *)this + 1) = 1;
  hWnd = v11;
  if ( (*(_BYTE *)(v10 + 176) & 0x40) != 0 )
  {
    if ( *((_DWORD *)this + 3) )
    {
      if ( *((_DWORD *)this + 2) )
      {
        KillTimer(*(HWND *)(v10 + 96), 0x2Eu);
        v12 = (CListView *)*((_QWORD *)this + 14);
        *((_DWORD *)this + 3) = 0;
        CListView::NotifyItemActivate(v12, (struct tagNMITEMACTIVATE *)((char *)this + 24));
        if ( !IsWindow(v11) )
          return;
      }
    }
  }
  v13 = *((_QWORD *)this + 14);
  Focus = GetFocus();
  v104 = *(HWND *)(v13 + 96);
  v14 = *((_QWORD *)this + 14);
  Point.x = a5 & 2;
  v98 = Point.x != 0 ? -5 : -2;
  if ( (unsigned int)ChildOfActiveWindow(*(HWND *)(v14 + 96))
    || (unsigned int)fShouldFirstClickActivate()
    || (v15 = *(HWND *)(*((_QWORD *)this + 14) + 96LL),
        ShellWindow = GetShellWindow(),
        v102 = 0,
        IsChild(ShellWindow, v15)) )
  {
    v102 = 1;
  }
  SetCapture(*(HWND *)(*((_QWORD *)this + 14) + 96LL));
  v17 = *((_QWORD *)this + 14);
  *((_DWORD *)this + 24) = a3;
  *((_DWORD *)this + 25) = a4;
  if ( !(unsigned int)CLVInPlaceEditingManager::DismissEdit(*(CLVInPlaceEditingManager **)(v17 + 416), 0) )
  {
    v18 = *(HWND *)(*((_QWORD *)this + 14) + 96LL);
    if ( GetCapture() != v18 )
      goto LABEL_196;
  }
  KillTimer(*(HWND *)(*((_QWORD *)this + 14) + 96LL), 0x31u);
  TickCount = GetTickCount();
  v20 = *((_QWORD *)this + 14) + 96LL;
  *((_DWORD *)this + 26) = TickCount;
  CCReleaseCapture(v20);
  v21 = *((_QWORD *)this + 14);
  v22 = a5 & 0xFFFFFFF3;
  v23 = (*(_BYTE *)(v21 + 112) & 4) == 0;
  v24 = *(CLVInPlaceEditingManager **)(v21 + 416);
  if ( v23 )
    v22 = a5;
  v100 = *((_DWORD *)v24 + 4);
  if ( (unsigned int)CLVInPlaceEditingManager::IsInSubItemEdit(v24)
    || (unsigned int)CLVInPlaceEditingManager::IsInGroupEdit(v25) )
  {
    CLVInPlaceEditingManager::DismissEdit(v25, 0);
  }
  v26 = *((_QWORD *)this + 14);
  v27 = v97;
  LOWORD(v109.pt.y) = a4;
  *(_OWORD *)&v109.flags = 0;
  LOWORD(v109.pt.x) = a3;
  HIWORD(v109.pt.x) = v97;
  HIWORD(v109.pt.y) = v94;
  v28 = CLVHitTestManager::OnHitTest(*(CLVHitTestManager **)(v26 + 400), &v109, 1, 1);
  v99 = v28;
  v95 = *(_DWORD *)(*((_QWORD *)this + 14) + 176LL);
  v93 = 0;
  memset_0(&v111, 0, sizeof(v111));
  flags = v109.flags;
  if ( (v109.flags & 0xF3000000) == 0 )
    goto LABEL_58;
  if ( !v8 && (v22 & 2) == 0 && (v109.flags & 0x40000000) == 0 )
  {
    DoubleClickTime = GetDoubleClickTime();
    SetTimer(*(HWND *)(*((_QWORD *)this + 14) + 96LL), 0x31u, DoubleClickTime, 0);
    flags = v109.flags;
    v32 = v22 & 2;
    goto LABEL_22;
  }
  v32 = v22 & 2;
  if ( (v22 & 2) == 0 && a2 != v32 && v109.flags == 0x10000000 )
  {
    v41 = *(GroupManagerHelpers **)(*((_QWORD *)this + 14) + 336LL);
    GroupFail = GroupManagerHelpers::FindGroupFail(v41, (const struct CLVGroupManager *)v28, v29);
    if ( GroupFail != -1 )
    {
      CListGroup::ToggleCollaspe(*(CListGroup **)(*(_QWORD *)(*((_QWORD *)v41 + 9) + 8LL) + 8LL * GroupFail), GroupFail);
      if ( !CLVMouseManager::SetFocus(this, *(HWND *)(*((_QWORD *)this + 14) + 96LL)) )
        return;
      goto LABEL_196;
    }
    v8 = a2;
LABEL_58:
    v46 = v28;
LABEL_59:
    v48 = *(CLVFooter **)(*((_QWORD *)this + 14) + 496LL);
    if ( *((_DWORD *)v48 + 11) && (unsigned int)CLVFooter::CheckMouseClick(v48, a3, a4) )
      goto LABEL_196;
    v49 = *((_QWORD *)this + 14);
    if ( !**(_DWORD **)(v49 + 512) )
    {
      v50 = *(_QWORD *)(v49 + 696);
      if ( v50 )
      {
        WORD2(v101) = a4;
        LOWORD(v101) = a3;
        WORD1(v101) = v27;
        HIWORD(v101) = v94;
        if ( !(*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v50 + 192LL))(v50, v101) )
          goto LABEL_196;
      }
    }
    v96 = v95 & 0x40;
    iSubItem = v109.iSubItem;
    if ( v109.iSubItem )
    {
      v52 = (CListView *)*((_QWORD *)this + 14);
      if ( *((_WORD *)v52 + 82) == 1 && !CListView::IsFullRowSelect(v52) && (*(_DWORD *)(v53 + 112) & 0x400) == 0 )
      {
        v46 = -1;
        v109.flags = v54;
      }
    }
    LOWORD(v111.ptAction.y) = a4;
    v111.iItem = v46;
    v111.iSubItem = iSubItem;
    v111.uChanged = 0;
    LOWORD(v111.ptAction.x) = a3;
    HIWORD(v111.ptAction.x) = v27;
    HIWORD(v111.ptAction.y) = v94;
    v111.uKeyFlags = CListView::GetLVKeyFlags();
    v55 = *((_QWORD *)this + 14);
    v111.uNewState = 0;
    *(_DWORD *)(*(_QWORD *)(v55 + 384) + 32LL) = v46;
    v56 = v46 >= 0
       && CLVItemStore::OnGetItemState(*(CLVItemStore **)(*((_QWORD *)this + 14) + 512LL), v46, v109.iGroup, 2u);
    v90 = v56;
    if ( v8 )
    {
      CLVInPlaceEditingManager::CancelPendingEdit(*(CLVInPlaceEditingManager **)(*((_QWORD *)this + 14) + 416LL));
      KillTimer(*(HWND *)(*((_QWORD *)this + 14) + 96LL), 0x2Bu);
      if ( (v109.flags & 1) != 0 && (v22 & 0xC) == 0 )
        CLVSelectionManager::DeselectAll(*(CLVSelectionManager **)(*((_QWORD *)this + 14) + 456LL), -1, -1);
      if ( CCSendNotify(*((_QWORD *)this + 14) + 96LL, (v22 & 2) != 0 ? -6 : -3, (LPARAM)&v111) )
        goto LABEL_196;
      if ( IsWindow(hWnd) )
      {
        if ( (v22 & 2) == 0 )
        {
          if ( (v109.flags & 6) != 0 )
          {
            if ( !v96 || !*((_DWORD *)this + 2) || (v22 & 0xC) != 0 )
              CListView::NotifyItemActivate(*((CListView **)this + 14), &v111);
          }
          else if ( (v109.flags & 8) != 0 )
          {
            v57 = *((_QWORD *)this + 14);
            if ( (*(_BYTE *)(v57 + 176) & 4) != 0 )
              CLVItemStore::HandleStateIconClick(*(CLVItemStore **)(v57 + 512), v46);
          }
        }
        if ( IsWindow(hWnd) )
          goto LABEL_196;
      }
      return;
    }
    v58 = v109.flags;
    if ( (v109.flags & 8) != 0 && (v22 & 2) != 0 && (*(_DWORD *)(*((_QWORD *)this + 14) + 176LL) & 0x8000000) != 0 )
    {
      v58 = v109.flags & 0xFFFFFFF5 | 2;
      v109.flags = v58;
    }
    if ( (v58 & 6) == 0 )
    {
      if ( (v58 & 8) != 0 )
      {
        if ( (v22 & 2) != 0 && (*(_DWORD *)(*((_QWORD *)this + 14) + 176LL) & 0x8000000) != 0 )
          goto LABEL_196;
        if ( !CLVMouseManager::SetFocus(this, *(HWND *)(*((_QWORD *)this + 14) + 96LL)) )
          return;
        if ( CCSendNotify(*((_QWORD *)this + 14) + 96LL, v98, (LPARAM)&v111) )
          goto LABEL_196;
        v86 = *((_QWORD *)this + 14);
        if ( (*(_BYTE *)(v86 + 176) & 4) != 0 )
        {
          v106 = 0;
          v108 = 1;
          v107 = 0;
          CCSendNotify(v86 + 96, -189, (LPARAM)&v106);
          CLVItemStore::HandleStateIconClick(*(CLVItemStore **)(*((_QWORD *)this + 14) + 512LL), v46);
        }
        goto LABEL_194;
      }
      if ( (v58 & 1) == 0 )
        goto LABEL_196;
      if ( !CLVMouseManager::SetFocus(this, *(HWND *)(*((_QWORD *)this + 14) + 96LL)) )
        return;
      v87 = *((_QWORD *)this + 14);
      if ( (*(_BYTE *)(v87 + 112) & 4) != 0
        || !(unsigned int)CheckForDragBeginEx(*(HWND *)(v87 + 96), 0)
        || CCSendNotify(*((_QWORD *)this + 14) + 96LL, -156, (LPARAM)&v111) )
      {
        if ( !IsWindow(hWnd) )
          return;
        if ( Focus != v104 && (v22 & 0xE) == 0 && (*(_BYTE *)(*((_QWORD *)this + 14) + 112LL) & 8) == 0 || !v102 )
          goto LABEL_196;
        if ( (v22 & 0xC) == 0 )
          CLVSelectionManager::DeselectAll(*(CLVSelectionManager **)(*((_QWORD *)this + 14) + 456LL), -1, -1);
        if ( CCSendNotify(*((_QWORD *)this + 14) + 96LL, v98, (LPARAM)&v111) )
          goto LABEL_196;
        goto LABEL_194;
      }
      if ( (v22 & 0xC) == 0 )
        CLVSelectionManager::DeselectAll(*(CLVSelectionManager **)(*((_QWORD *)this + 14) + 456LL), -1, -1);
      v70 = a4;
      v71 = a3;
      goto LABEL_184;
    }
    if ( (v58 & 0x4000000) != 0 || !CListView::RestrictSelectToContents(*((CListView **)this + 14)) || v60 )
    {
      CCPlaySound(L"CCSelect");
      if ( (v22 & 2) != 0 && (v22 & 0xC) != 0 )
      {
        v64 = v90;
      }
      else
      {
        v64 = v90;
        CLVSelectionManager::ButtonSelect(
          *(CLVSelectionManager **)(*((_QWORD *)this + 14) + 456LL),
          v46,
          v109.iGroup,
          v22,
          v90);
      }
      if ( !a6 )
      {
        v65 = CheckForDragBeginEx(*(HWND *)(*((_QWORD *)this + 14) + 96LL), 0);
LABEL_109:
        if ( v65 )
        {
          if ( v64
            || !CListView::RestrictSelectToContents(*(CListView **)(*(_QWORD *)(*((_QWORD *)this + 14) + 456LL) + 48LL))
            || (*(_BYTE *)(v67 + 112) & 4) != 0
            || (*(_DWORD *)(v67 + 112) & 0x400) != 0
            || (v66 & 0xE) == 0
            || (v66 & 0x4000000) != 0
            || CCSendNotify(v68 + 96, -156, (LPARAM)&v111)
            || CListView::RestrictSelectToContents(*((CListView **)this + 14))
            && !CLVMouseManager::SetFocus(this, *(HWND *)(v69 + 96)) )
          {
            CLVFocusManager::SetFocusSel(
              *(CLVFocusManager **)(*((_QWORD *)this + 14) + 384LL),
              v46,
              v109.iGroup,
              1,
              0,
              0);
            if ( (v22 & 4) == 0 )
            {
              *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 14) + 456LL) + 4LL) = v46;
              *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 14) + 456LL) + 8LL) = v109.iGroup;
            }
            UpdateWindow(*(HWND *)(*((_QWORD *)this + 14) + 96LL));
            **(_DWORD **)(*((_QWORD *)this + 14) + 360LL) = v46;
            goto LABEL_46;
          }
          v70 = a4;
          v71 = a3;
LABEL_184:
          CLVSelectionManager::DragSelect(*(CLVSelectionManager **)(*((_QWORD *)this + 14) + 456LL), v71, v70);
          v78 = CCSendNotify(*((_QWORD *)this + 14) + 96LL, v98, (LPARAM)&v111) == 0;
          goto LABEL_185;
        }
        if ( !IsWindow(hWnd) )
          return;
        if ( (v22 & 2) != 0 || (v22 & 8) == 0 )
        {
          v73 = v22 & 4;
          if ( (v22 & 4) != 0 )
            goto LABEL_135;
        }
        else
        {
          v72 = *((_QWORD *)this + 14);
          if ( (v22 & 4) != 0 )
          {
            CLVFocusManager::SetFocusSel(*(CLVFocusManager **)(v72 + 384), v46, v109.iGroup, 0, 0, 0);
            v73 = v22 & 4;
LABEL_135:
            if ( !CLVMouseManager::SetFocus(this, *(HWND *)(*((_QWORD *)this + 14) + 96LL)) )
              return;
            if ( !v73 && (v22 & 0xA) == 0 )
            {
              v74 = v64 && *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 14) + 456LL) + 12LL) == 1;
              CLVSelectionManager::DeselectAll(
                *(CLVSelectionManager **)(*((_QWORD *)this + 14) + 456LL),
                v46,
                v109.iGroup);
              if ( (v109.flags & 4) != 0 )
              {
                if ( v74 )
                {
                  v75 = *((_QWORD *)this + 14);
                  if ( (*(_BYTE *)(v75 + 176) & 0xC0) == 0 && (Focus == v104 || (*(_DWORD *)(v75 + 112) & 0x400) != 0) )
                  {
                    *(_DWORD *)(*(_QWORD *)(v75 + 416) + 8LL) = v46;
                    *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 14) + 416LL) + 12LL) = v109.iGroup;
                    CanEditSubItems = CLVInPlaceEditingManager::CanEditSubItems(*(CLVInPlaceEditingManager **)(*((_QWORD *)this + 14) + 416LL));
                    *(_DWORD *)(v77 + 40) = CanEditSubItems != 0 ? v109.iSubItem : 0;
                    CListView::CancelPendingTimer(
                      *(CListView **)(*(_QWORD *)(*((_QWORD *)this + 14) + 448LL) + 24LL),
                      0x200u,
                      43);
                    CLVInPlaceEditingManager::SetupPendingNameEdit(*(CLVInPlaceEditingManager **)(*((_QWORD *)this + 14)
                                                                                                + 416LL));
                  }
                }
              }
            }
            v78 = CCSendNotify(*((_QWORD *)this + 14) + 96LL, v98, (LPARAM)&v111) == 0;
            if ( !IsWindow(hWnd) )
              return;
            v79 = *(_DWORD *)(*((_QWORD *)this + 14) + 176LL);
            if ( (v79 & 0xC0) != 0 && (v22 & 2) == 0 )
            {
              if ( v96 && *((_DWORD *)this + 2) )
              {
                v80 = v90;
              }
              else
              {
                v80 = v90;
                if ( !v90 )
                  goto LABEL_185;
              }
              if ( !v102 )
                goto LABEL_185;
              v81 = v96 && (v22 & 8) == 0 && !v73;
              if ( v80 && (v79 & 0x80u) != 0 )
                goto LABEL_166;
              if ( !v81 )
                goto LABEL_185;
              if ( *((_DWORD *)this + 31) )
              {
                v82 = *(_OWORD *)&v111.hdr.code;
                *(_OWORD *)((char *)this + 24) = *(_OWORD *)&v111.hdr.hwndFrom;
                *((_DWORD *)this + 3) = 1;
                v83 = *(_OWORD *)&v111.uNewState;
                *(_OWORD *)((char *)this + 40) = v82;
                v84 = *(_OWORD *)&v111.ptAction.y;
                *(_OWORD *)((char *)this + 56) = v83;
                *(_QWORD *)&v83 = *(_QWORD *)&v111.uKeyFlags;
                *(_OWORD *)((char *)this + 72) = v84;
                *((_QWORD *)this + 11) = v83;
                v85 = GetDoubleClickTime();
                SetTimer(*(HWND *)(*((_QWORD *)this + 14) + 96LL), 0x2Eu, v85, 0);
              }
              else
              {
LABEL_166:
                CListView::NotifyItemActivate(*((CListView **)this + 14), &v111);
                if ( !IsWindow(hWnd) )
                  return;
              }
            }
LABEL_185:
            if ( v78 )
            {
LABEL_194:
              if ( Point.x )
              {
                v88 = *((_QWORD *)this + 14);
                LOWORD(Point.x) = a3;
                HIWORD(Point.x) = v27;
                LOWORD(Point.y) = a4;
                HIWORD(Point.y) = v94;
                ClientToScreen(*(HWND *)(v88 + 96), &Point);
                SendMessageW(
                  *(HWND *)(*((_QWORD *)this + 14) + 96LL),
                  0x7Bu,
                  *(_QWORD *)(*((_QWORD *)this + 14) + 96LL),
                  LOWORD(Point.x) | (unsigned __int64)(LOWORD(Point.y) << 16));
              }
            }
LABEL_196:
            if ( IsWindow(hWnd) )
              *((_DWORD *)this + 1) = 0;
            return;
          }
          v106 = 0;
          v108 = 2;
          v107 = 0;
          CCSendNotify(v72 + 96, -189, (LPARAM)&v106);
          CLVFocusManager::SetFocusSel(*(CLVFocusManager **)(*((_QWORD *)this + 14) + 384LL), v46, v109.iGroup, 1, 0, 1);
          v73 = v22 & 4;
        }
        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 14) + 456LL) + 4LL) = v46;
        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 14) + 456LL) + 8LL) = v109.iGroup;
        goto LABEL_135;
      }
    }
    else
    {
      if ( CListView::RestrictSelectToContents(v59) )
      {
        v63 = v62;
        LOBYTE(v63) = (v22 & 2) == 0;
        v93 = CheckForDragBeginEx(*(HWND *)(v61 + 96), v63);
      }
      if ( (v22 & 0xC) == 0 && ((v22 & 2) == 0 || **(_DWORD **)(*((_QWORD *)this + 14) + 384LL) != v46) )
        CLVSelectionManager::DeselectAll(*(CLVSelectionManager **)(*((_QWORD *)this + 14) + 456LL), -1, -1);
      v64 = v90;
    }
    v65 = v93;
    goto LABEL_109;
  }
LABEL_22:
  v33 = *((_QWORD *)this + 14);
  v34 = *(_QWORD *)(v33 + 336);
  if ( (flags & 0x10000000) == 0 )
  {
    if ( *(_DWORD *)(v34 + 64) )
    {
      if ( (flags & 0x20000000) != 0 )
      {
        v47 = GroupManagerHelpers::FindGroupFail(
                *(GroupManagerHelpers **)(v33 + 336),
                (const struct CLVGroupManager *)v28,
                v29);
        if ( v47 != -1
          && !(unsigned int)CListGroup::OnButtonDown(
                              *(CListGroup **)(*(_QWORD *)(*(_QWORD *)(v34 + 72) + 8LL) + 8LL * v47),
                              v109.pt) )
        {
          goto LABEL_196;
        }
      }
    }
    v46 = -1;
    v109.flags = 1;
    goto LABEL_51;
  }
  v35 = GroupManagerHelpers::FindGroupFail(
          *(GroupManagerHelpers **)(v33 + 336),
          (const struct CLVGroupManager *)v28,
          v29);
  v36 = v35;
  if ( v35 == -1 )
  {
    v46 = v99;
LABEL_51:
    v8 = a2;
    goto LABEL_59;
  }
  v37 = *(CListGroup **)(*(_QWORD *)(*(_QWORD *)(v34 + 72) + 8LL) + 8LL * v35);
  if ( v32 )
  {
    v38 = *((_QWORD *)this + 14);
    v39 = *(int **)(v38 + 384);
    if ( v39[2] != v35 )
    {
      v40 = *v39;
      if ( *v39 == -1 )
      {
LABEL_36:
        CLVGroupManager::SetFocusedGroup(*(CLVGroupManager **)(*((_QWORD *)this + 14) + 336LL), v36);
        goto LABEL_37;
      }
LABEL_35:
      CLVItemStore::OnSetItemState(*(CLVItemStore **)(v38 + 512), v40, v39[1], 0, 1u);
      **(_DWORD **)(*((_QWORD *)this + 14) + 384LL) = -1;
      goto LABEL_36;
    }
    if ( *v39 != -1 )
    {
      v40 = *v39;
      goto LABEL_35;
    }
  }
LABEL_37:
  if ( v36 == v100 )
    KillTimer(*(HWND *)(*((_QWORD *)this + 14) + 96LL), 0x31u);
  if ( (int)CListGroup::OnButtonDown(v37, v109.pt) < 0
    && (unsigned int)CheckForDragBeginEx(*(HWND *)(*((_QWORD *)this + 14) + 96LL), 1) )
  {
    if ( (*((_BYTE *)v37 + 96) & 0x20) == 0 )
      CListGroup::Select(v37, v36, 0, 0, 1);
    ListviewItemIndex = CListGroup::GetListviewItemIndex(v37, v36, 0);
    v44 = ListviewItemIndex;
    if ( (v22 & 4) == 0 )
    {
      *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 14) + 456LL) + 4LL) = ListviewItemIndex;
      *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 14) + 456LL) + 8LL) = v109.iGroup;
    }
    UpdateWindow(*(HWND *)(*((_QWORD *)this + 14) + 96LL));
    **(_DWORD **)(*((_QWORD *)this + 14) + 360LL) = v44;
    LOWORD(v111.ptAction.x) = a3;
    *(_QWORD *)&v111.iSubItem = 0;
    *(_QWORD *)&v111.uOldState = 0;
    LOWORD(v111.ptAction.y) = a4;
    v111.lParam = 0;
    v111.iItem = v44;
    HIWORD(v111.ptAction.x) = v27;
    HIWORD(v111.ptAction.y) = v94;
    v111.uKeyFlags = CListView::GetLVKeyFlags();
LABEL_46:
    CCSendNotify(*((_QWORD *)this + 14) + 96LL, (a5 & 2) != 0 ? -111 : -109, (LPARAM)&v111);
    **(_DWORD **)(*((_QWORD *)this + 14) + 360LL) = -1;
    goto LABEL_196;
  }
  if ( (unsigned int)CLVInPlaceEditingManager::IsInEdit(*(CLVInPlaceEditingManager **)(*((_QWORD *)this + 14) + 416LL))
    || CLVMouseManager::SetFocus(this, *(HWND *)(v45 + 96)) )
  {
    goto LABEL_196;
  }
}

```

## disassembly

```asm
0x18003ed74  mov     [rsp-8+arg_8], rbx
0x18003ed79  push    rbp
0x18003ed7a  push    rsi
0x18003ed7b  push    rdi
0x18003ed7c  push    r12
0x18003ed7e  push    r13
0x18003ed80  push    r14
0x18003ed82  push    r15
0x18003ed84  lea     rbp, [rsp-30h]
0x18003ed89  sub     rsp, 130h
0x18003ed90  mov     rax, cs:__security_cookie
0x18003ed97  xor     rax, rsp
0x18003ed9a  mov     [rbp+60h+var_40], rax
0x18003ed9e  xor     edi, edi
0x18003eda0  mov     [rsp+160h+var_12C], r9d
0x18003eda5  mov     r13d, r9d
0x18003eda8  mov     r12d, r8d
0x18003edab  mov     r14d, edx
0x18003edae  mov     [rsp+160h+var_128], r8d
0x18003edb3  mov     rsi, rcx
0x18003edb6  mov     [rsp+160h+var_130], edx
0x18003edba  mov     [rsp+160h+var_118], r8d
0x18003edbf  mov     dword ptr [rsp+160h+var_120], r9d
0x18003edc4  cmp     [rcx+4], edi
0x18003edc7  jnz     loc_18003FD31
0x18003edcd  mov     rcx, [rcx+70h]
0x18003edd1  lea     r15d, [rdi+1]
0x18003edd5  mov     rbx, [rcx+60h]
0x18003edd9  mov     [rsi+4], r15d
0x18003eddd  test    byte ptr [rcx+0B0h], 40h
0x18003ede4  mov     [rsp+160h+hWnd], rbx
0x18003ede9  jz      short loc_18003EE23
0x18003edeb  cmp     [rsi+0Ch], edi
0x18003edee  jz      short loc_18003EE23
0x18003edf0  cmp     [rsi+8], edi
0x18003edf3  jz      short loc_18003EE23
0x18003edf5  mov     rcx, [rcx+60h]; hWnd
0x18003edf9  lea     edx, [rdi+2Eh]; uIDEvent
0x18003edfc  call    cs:__imp_KillTimer
0x18003ee02  mov     rcx, [rsi+70h]; this
0x18003ee06  lea     rdx, [rsi+18h]; struct tagNMITEMACTIVATE *
0x18003ee0a  mov     [rsi+0Ch], edi
0x18003ee0d  call    ?NotifyItemActivate@CListView@@QEAAXPEAUtagNMITEMACTIVATE@@@Z; CListView::NotifyItemActivate(tagNMITEMACTIVATE *)
0x18003ee12  mov     rcx, rbx; hWnd
0x18003ee15  call    cs:__imp_IsWindow
0x18003ee1b  test    eax, eax
0x18003ee1d  jz      loc_18003FD31
0x18003ee23  mov     rbx, [rsi+70h]
0x18003ee27  call    cs:__imp_GetFocus
0x18003ee2d  mov     edi, [rbp+60h+arg_20]
0x18003ee33  mov     edx, edi
0x18003ee35  mov     [rbp+60h+var_E0], rax
0x18003ee39  and     edx, 2
0x18003ee3c  mov     rax, [rbx+60h]
0x18003ee40  mov     ecx, edx
0x18003ee42  mov     [rsp+160h+var_E8], rax
0x18003ee47  neg     ecx
0x18003ee49  mov     rcx, [rsi+70h]
0x18003ee4d  sbb     eax, eax
0x18003ee4f  mov     [rbp+60h+Point.x], edx
0x18003ee52  and     eax, 0FFFFFFFDh
0x18003ee55  add     eax, 0FFFFFFFEh
0x18003ee58  mov     rcx, [rcx+60h]; hWnd
0x18003ee5c  mov     [rsp+160h+var_10C], eax
0x18003ee60  mov     eax, edx
0x18003ee62  neg     eax
0x18003ee64  sbb     eax, eax
0x18003ee66  and     eax, 0FFFFFFFEh
0x18003ee69  add     eax, 0FFFFFF93h
0x18003ee6c  mov     [rsp+160h+var_F4], eax
0x18003ee70  call    ChildOfActiveWindow
0x18003ee75  test    eax, eax
0x18003ee77  jnz     short loc_18003EEA8
0x18003ee79  call    ?fShouldFirstClickActivate@@YAHXZ; fShouldFirstClickActivate(void)
0x18003ee7e  test    eax, eax
0x18003ee80  jnz     short loc_18003EEA8
0x18003ee82  mov     rax, [rsi+70h]
0x18003ee86  mov     rbx, [rax+60h]
0x18003ee8a  call    cs:__imp_GetShellWindow
0x18003ee90  mov     rcx, rax; hWndParent
0x18003ee93  mov     rdx, rbx; hWnd
0x18003ee96  call    cs:__imp_IsChild
0x18003ee9c  mov     [rsp+160h+var_F8], 0
0x18003eea4  test    eax, eax
0x18003eea6  jz      short loc_18003EEAD
0x18003eea8  mov     [rsp+160h+var_F8], r15d
0x18003eead  mov     rcx, [rsi+70h]
0x18003eeb1  mov     rcx, [rcx+60h]; hWnd
0x18003eeb5  call    cs:__imp_SetCapture
0x18003eebb  mov     rcx, [rsi+70h]
0x18003eebf  xor     edx, edx; int
0x18003eec1  mov     [rsi+60h], r12d
0x18003eec5  mov     [rsi+64h], r13d
0x18003eec9  mov     rcx, [rcx+1A0h]; this
0x18003eed0  call    ?DismissEdit@CLVInPlaceEditingManager@@QEAAHH@Z; CLVInPlaceEditingManager::DismissEdit(int)
0x18003eed5  test    eax, eax
0x18003eed7  jnz     short loc_18003EEF0
0x18003eed9  mov     rax, [rsi+70h]
0x18003eedd  mov     rbx, [rax+60h]
0x18003eee1  call    cs:__imp_GetCapture
0x18003eee7  cmp     rax, rbx
0x18003eeea  jnz     loc_18003FD1B
0x18003eef0  mov     rcx, [rsi+70h]
0x18003eef4  mov     edx, 31h ; '1'; uIDEvent
0x18003eef9  mov     rcx, [rcx+60h]; hWnd
0x18003eefd  call    cs:__imp_KillTimer
0x18003ef03  call    cs:__imp_GetTickCount
0x18003ef09  mov     rcx, [rsi+70h]
0x18003ef0d  add     rcx, 60h ; '`'
0x18003ef11  mov     [rsi+68h], eax
0x18003ef14  call    CCReleaseCapture
0x18003ef19  mov     rcx, [rsi+70h]
0x18003ef1d  mov     r15d, edi
0x18003ef20  and     r15d, 0FFFFFFF3h
0x18003ef24  test    byte ptr [rcx+70h], 4
0x18003ef28  mov     rcx, [rcx+1A0h]; this
0x18003ef2f  cmovz   r15d, edi
0x18003ef33  mov     eax, [rcx+10h]
0x18003ef36  mov     dword ptr [rsp+160h+var_100], eax
0x18003ef3a  call    ?IsInSubItemEdit@CLVInPlaceEditingManager@@QEAAHXZ; CLVInPlaceEditingManager::IsInSubItemEdit(void)
0x18003ef3f  test    eax, eax
0x18003ef41  jnz     short loc_18003EF4C
0x18003ef43  call    ?IsInGroupEdit@CLVInPlaceEditingManager@@QEAAHXZ; CLVInPlaceEditingManager::IsInGroupEdit(void)
0x18003ef48  test    eax, eax
0x18003ef4a  jz      short loc_18003EF53
0x18003ef4c  xor     edx, edx; int
0x18003ef4e  call    ?DismissEdit@CLVInPlaceEditingManager@@QEAAHH@Z; CLVInPlaceEditingManager::DismissEdit(int)
0x18003ef53  mov     rcx, [rsi+70h]
0x18003ef57  lea     rdx, [rbp+60h+var_B8]; struct tagLVHITTESTINFO *
0x18003ef5b  movzx   ebx, word ptr [rsp+160h+var_118+2]
0x18003ef60  xorps   xmm0, xmm0
0x18003ef63  movzx   edi, [rsp+160h+var_120+2]
0x18003ef68  mov     word ptr [rbp+60h+var_B8.y], r13w
0x18003ef6d  mov     r13d, 1
0x18003ef73  movdqu  xmmword ptr [rbp+60h+var_B0], xmm0
0x18003ef78  mov     word ptr [rbp+60h+var_B8.x], r12w
0x18003ef7d  mov     r9d, r13d; int
0x18003ef80  mov     word ptr [rbp+60h+var_B8.x+2], bx
0x18003ef84  mov     r8d, r13d; int
0x18003ef87  mov     word ptr [rbp+60h+var_B8.y+2], di
0x18003ef8b  mov     rcx, [rcx+190h]; this
0x18003ef92  call    ?OnHitTest@CLVHitTestManager@@QEAAHPEAUtagLVHITTESTINFO@@HH@Z; CLVHitTestManager::OnHitTest(tagLVHITTESTINFO *,int,int)
0x18003ef97  mov     rcx, [rsi+70h]
0x18003ef9b  lea     r8d, [r13+47h]; Size
0x18003ef9f  mov     r12d, eax
0x18003efa2  mov     [rsp+160h+var_108], eax
0x18003efa6  xor     edx, edx; Val
0x18003efa8  mov     eax, [rcx+0B0h]
0x18003efae  lea     rcx, [rbp+60h+var_90]; void *
0x18003efb2  mov     [rsp+160h+var_118], eax
0x18003efb6  xor     eax, eax
0x18003efb8  mov     [rsp+160h+var_124], eax
0x18003efbc  mov     [rsp+160h+var_110], eax
0x18003efc0  mov     dword ptr [rsp+160h+var_120], eax
0x18003efc4  call    memset_0
0x18003efc9  mov     ecx, [rbp+60h+var_B0]
0x18003efcc  test    ecx, 0F3000000h
0x18003efd2  jz      loc_18003F30C
0x18003efd8  test    r14d, r14d
0x18003efdb  jnz     loc_18003F07F
0x18003efe1  test    r15b, 2
0x18003efe5  jnz     loc_18003F07F
0x18003efeb  bt      ecx, 1Eh
0x18003efef  jb      loc_18003F07F
0x18003eff5  call    cs:__imp_GetDoubleClickTime
0x18003effb  mov     rcx, [rsi+70h]
0x18003efff  lea     edx, [r13+30h]; nIDEvent
0x18003f003  xor     r9d, r9d; lpTimerFunc
0x18003f006  mov     r8d, eax; uElapse
0x18003f009  mov     rcx, [rcx+60h]; hWnd
0x18003f00d  call    cs:__imp_SetTimer
0x18003f013  mov     ecx, [rbp+60h+var_B0]
0x18003f016  mov     r14d, r15d
0x18003f019  and     r14d, 2
0x18003f01d  mov     rax, [rsi+70h]
0x18003f021  mov     r13, [rax+150h]
0x18003f028  bt      ecx, 1Ch
0x18003f02c  jnb     loc_18003F2BE
0x18003f032  mov     edx, r12d; struct CLVGroupManager *
0x18003f035  mov     rcx, r13; this
0x18003f038  call    ?FindGroupFail@GroupManagerHelpers@@YAHAEBVCLVGroupManager@@H@Z; GroupManagerHelpers::FindGroupFail(CLVGroupManager const &,int)
0x18003f03d  movsxd  r12, eax
0x18003f040  cmp     r12d, 0FFFFFFFFh
0x18003f044  jz      loc_18003F2B2
0x18003f04a  mov     rcx, [r13+48h]
0x18003f04e  mov     rcx, [rcx+8]
0x18003f052  mov     r13, [rcx+r12*8]
0x18003f056  test    r14d, r14d
0x18003f059  jz      loc_18003F133
0x18003f05f  mov     rcx, [rsi+70h]
0x18003f063  mov     r8, [rcx+180h]
0x18003f06a  cmp     [r8+8], r12d
0x18003f06e  jnz     short loc_18003F0EC
0x18003f070  cmp     dword ptr [r8], 0FFFFFFFFh
0x18003f074  jz      loc_18003F133
0x18003f07a  mov     edx, [r8]
0x18003f07d  jmp     short loc_18003F0F4
0x18003f07f  mov     r14d, r15d
0x18003f082  and     r14d, 2
0x18003f086  jnz     short loc_18003F01D
0x18003f088  cmp     [rsp+160h+var_130], r14d
0x18003f08d  jz      short loc_18003F01D
0x18003f08f  cmp     ecx, 10000000h
0x18003f095  jnz     short loc_18003F01D
0x18003f097  mov     rax, [rsi+70h]
0x18003f09b  mov     edx, r12d; struct CLVGroupManager *
0x18003f09e  mov     r14, [rax+150h]
0x18003f0a5  mov     rcx, r14; this
0x18003f0a8  call    ?FindGroupFail@GroupManagerHelpers@@YAHAEBVCLVGroupManager@@H@Z; GroupManagerHelpers::FindGroupFail(CLVGroupManager const &,int)
0x18003f0ad  cmp     eax, 0FFFFFFFFh
0x18003f0b0  jz      loc_18003F307
0x18003f0b6  mov     rdx, [r14+48h]
0x18003f0ba  movsxd  r8, eax
0x18003f0bd  mov     rcx, [rdx+8]
0x18003f0c1  mov     edx, eax; int
0x18003f0c3  mov     rcx, [rcx+r8*8]; this
0x18003f0c7  call    ?ToggleCollaspe@CListGroup@@QEAAXH@Z; CListGroup::ToggleCollaspe(int)
0x18003f0cc  mov     rdx, [rsi+70h]
0x18003f0d0  mov     rcx, rsi; this
0x18003f0d3  mov     rdx, [rdx+60h]; HWND
0x18003f0d7  call    ?SetFocus@CLVMouseManager@@QEAAHPEAUHWND__@@@Z; CLVMouseManager::SetFocus(HWND__ *)
0x18003f0dc  test    eax, eax
0x18003f0de  jz      loc_18003FD31
0x18003f0e4  mov     r14d, r13d
0x18003f0e7  jmp     loc_18003F2A9
0x18003f0ec  mov     edx, [r8]; int
0x18003f0ef  cmp     edx, 0FFFFFFFFh
0x18003f0f2  jz      short loc_18003F120
0x18003f0f4  mov     r8d, [r8+4]; int
0x18003f0f8  xor     r9d, r9d; unsigned int
0x18003f0fb  mov     rcx, [rcx+200h]; this
0x18003f102  mov     [rsp+160h+var_140], 1; unsigned int
0x18003f10a  call    ?OnSetItemState@CLVItemStore@@QEAAHHHII@Z; CLVItemStore::OnSetItemState(int,int,uint,uint)
0x18003f10f  mov     rax, [rsi+70h]
0x18003f113  mov     rcx, [rax+180h]
0x18003f11a  mov     dword ptr [rcx], 0FFFFFFFFh
0x18003f120  mov     rcx, [rsi+70h]
0x18003f124  mov     edx, r12d; int
0x18003f127  mov     rcx, [rcx+150h]; this
0x18003f12e  call    ?SetFocusedGroup@CLVGroupManager@@QEAAXH@Z; CLVGroupManager::SetFocusedGroup(int)
0x18003f133  cmp     r12d, dword ptr [rsp+160h+var_100]
0x18003f138  jnz     short loc_18003F14D
0x18003f13a  mov     rcx, [rsi+70h]
0x18003f13e  mov     edx, 31h ; '1'; uIDEvent
0x18003f143  mov     rcx, [rcx+60h]; hWnd
0x18003f147  call    cs:__imp_KillTimer
0x18003f14d  mov     rdx, qword ptr [rbp+60h+var_B8.x]; struct tagPOINT
0x18003f151  mov     rcx, r13; this
0x18003f154  call    ?OnButtonDown@CListGroup@@QEAAJUtagPOINT@@@Z; CListGroup::OnButtonDown(tagPOINT)
0x18003f159  mov     r14d, 1
0x18003f15f  test    eax, eax
0x18003f161  jns     loc_18003F27D
0x18003f167  mov     rcx, [rsi+70h]
0x18003f16b  lea     r9, [rsp+160h+var_120]
0x18003f170  mov     r8d, [rsp+160h+var_12C]
0x18003f175  mov     edx, [rsp+160h+var_128]
0x18003f179  mov     [rsp+160h+var_140], r14d; int
0x18003f17e  mov     rcx, [rcx+60h]; hWnd
0x18003f182  call    CheckForDragBeginEx
0x18003f187  cmp     dword ptr [rsp+160h+var_120], 202h
0x18003f18f  mov     ecx, eax
0x18003f191  mov     [rsp+160h+var_124], eax
0x18003f195  mov     eax, [rsp+160h+var_110]
0x18003f199  cmovz   eax, r14d
0x18003f19d  mov     [rsp+160h+var_110], eax
0x18003f1a1  test    ecx, ecx
0x18003f1a3  jz      loc_18003F27D
0x18003f1a9  test    eax, eax
0x18003f1ab  jnz     loc_18003F27D
0x18003f1b1  test    byte ptr [r13+60h], 20h
0x18003f1b6  jnz     short loc_18003F1CE
0x18003f1b8  xor     r9d, r9d; int
0x18003f1bb  mov     [rsp+160h+var_140], r14d; int
0x18003f1c0  xor     r8d, r8d; int
0x18003f1c3  mov     edx, r12d; int
0x18003f1c6  mov     rcx, r13; this
0x18003f1c9  call    ?Select@CListGroup@@QEAAHHHHH@Z; CListGroup::Select(int,int,int,int)
0x18003f1ce  xor     r8d, r8d; int
0x18003f1d1  mov     edx, r12d; int
0x18003f1d4  mov     rcx, r13; this
0x18003f1d7  call    ?GetListviewItemIndex@CListGroup@@QEBAHHH@Z; CListGroup::GetListviewItemIndex(int,int)
0x18003f1dc  mov     r14d, eax
0x18003f1df  test    r15b, 4
0x18003f1e3  jnz     short loc_18003F204
0x18003f1e5  mov     rcx, [rsi+70h]
0x18003f1e9  mov     rdx, [rcx+1C8h]
0x18003f1f0  mov     [rdx+4], eax
0x18003f1f3  mov     rcx, [rsi+70h]
0x18003f1f7  mov     rdx, [rcx+1C8h]
0x18003f1fe  mov     ecx, [rbp+60h+var_B0+0Ch]
0x18003f201  mov     [rdx+8], ecx
0x18003f204  mov     rcx, [rsi+70h]
0x18003f208  mov     rcx, [rcx+60h]; hWnd
0x18003f20c  call    cs:__imp_UpdateWindow
0x18003f212  mov     rax, [rsi+70h]
0x18003f216  mov     rcx, [rax+168h]
0x18003f21d  mov     eax, [rsp+160h+var_128]
0x18003f221  mov     [rcx], r14d
0x18003f224  xor     ecx, ecx
0x18003f226  mov     word ptr [rbp+60h+var_90.ptAction.x], ax
  ... truncated ...
```
