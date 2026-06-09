# CAMCTreeView::OnSelChangedWorker(tagNMTREEVIEWW *,__int64 *)

- ea: `0x1400d61a8`
- end: `0x1400d63b6`
- name: `?OnSelChangedWorker@CAMCTreeView@@IEAAXPEAUtagNMTREEVIEWW@@PEA_J@Z`
- size: `526`
- prototype: `void __fastcall(CAMCTreeView *__hidden this, struct tagNMTREEVIEWW *, __int64 *)`
- caller_count: `3`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x1400d60e0`
- `0x1400d66a0`
- `0x1400d6dd0`

## callees

- `0x14002274c`
- `0x14002a050`
- `0x14003e024`
- `0x14005c7ac`
- `0x14006623c`
- `0x1400cbe04`
- `0x1400cbe2c`
- `0x1400d61a8`
- `0x1400f3010`

## import_xrefs

- `USER32!GetFocus` at `0x1400d636a`
- `USER32!GetFocus` at `0x1400d636a`
- `USER32!UpdateWindow` at `0x1400d621a`
- `USER32!UpdateWindow` at `0x1400d621a`
- `MFC42u!__imp_?GetActiveView@CFrameWnd@@QEBAPEAVCView@@XZ` at `0x1400d6347`
- `MFC42u!__imp_?GetActiveView@CFrameWnd@@QEBAPEAVCView@@XZ` at `0x1400d6347`
- `MFC42u!__imp_?GetParentFrame@CWnd@@QEBAPEAVCFrameWnd@@XZ` at `0x1400d62f8`
- `MFC42u!__imp_?GetParentFrame@CWnd@@QEBAPEAVCFrameWnd@@XZ` at `0x1400d6336`
- `MFC42u!__imp_?GetParentFrame@CWnd@@QEBAPEAVCFrameWnd@@XZ` at `0x1400d62f8`
- `MFC42u!__imp_?GetParentFrame@CWnd@@QEBAPEAVCFrameWnd@@XZ` at `0x1400d6336`
- `MFC42u!__imp_?SetActiveView@CFrameWnd@@QEAAXPEAVCView@@H@Z` at `0x1400d630f`
- `MFC42u!__imp_?SetActiveView@CFrameWnd@@QEAAXPEAVCView@@H@Z` at `0x1400d635e`
- `MFC42u!__imp_?SetActiveView@CFrameWnd@@QEAAXPEAVCView@@H@Z` at `0x1400d630f`
- `MFC42u!__imp_?SetActiveView@CFrameWnd@@QEAAXPEAVCView@@H@Z` at `0x1400d635e`
- `MFC42u!__imp_?SetFocus@CWnd@@QEAAPEAV1@XZ` at `0x1400d6378`
- `MFC42u!__imp_?SetFocus@CWnd@@QEAAPEAV1@XZ` at `0x1400d6378`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400d626f`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400d6296`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400d632b`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400d63a5`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400d626f`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400d6296`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400d632b`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400d63a5`
- `mmcbase!?MMCErrorBox@@YAHII@Z` at `0x1400d62b3`
- `mmcbase!?MMCErrorBox@@YAHII@Z` at `0x1400d62b3`

## pseudocode

```c
void __fastcall CAMCTreeView::OnSelChangedWorker(CAMCTreeView *this, struct tagNMTREEVIEWW *a2, __int64 *a3)
{
  unsigned int v6; // ebx
  int v7; // eax
  __int64 v8; // rsi
  __int64 v9; // rsi
  __int64 v10; // r8
  __int64 v11; // r8
  __int64 v12; // rax
  CFrameWnd *ParentFrame; // rax
  CFrameWnd *v14; // rax
  CFrameWnd *v15; // rbx
  HWND v16; // rbx
  _BYTE v17[72]; // [rsp+20h] [rbp-48h] BYREF

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 22, WPP_6033b5b997f23f8d916bc9bad54228b4_Traceguids);
  if ( *((_DWORD *)this + 80) != 1 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 41) + 136LL) + 224LL))(*((_QWORD *)this + 41) + 136LL);
    UpdateWindow(*((HWND *)this + 8));
    v7 = CAMCTreeView::OnSelectNode(this, a2->itemNew.hItem, (struct HNODE__ *)a2->itemNew.lParam);
    v8 = v7;
    if ( v7 )
    {
      if ( v7 == 1 )
        return;
      MMCErrorBox(0x2EE0u, 0x10u);
      v12 = v8;
    }
    else
    {
      v9 = *(_QWORD *)(*((_QWORD *)this + 41) + 1360LL);
      if ( v9 )
      {
        LOBYTE(v10) = CAMCTreeView::GetRootItem(this) != a2->itemNew.hItem;
        CStandardToolbar::ScEnableUpOneLevel(v9, v17, v10);
        mmcerror::SC::~SC((mmcerror::SC *)v17);
        LOBYTE(v11) = CAMCView::HasListOrListPad(*((CAMCView **)this + 41));
        CStandardToolbar::ScEnableExportList(v9, v17, v11);
        mmcerror::SC::~SC((mmcerror::SC *)v17);
      }
      v12 = 0;
    }
    *a3 = v12;
    if ( v6 != -1 )
    {
      if ( v6 )
      {
        if ( v6 == 1 )
        {
          ParentFrame = CWnd::GetParentFrame(this);
          if ( ParentFrame )
            CFrameWnd::SetActiveView(ParentFrame, this, 1);
          CAMCView::ScDeferSettingFocusToResultPane(*((_QWORD *)this + 41), v17);
        }
        else
        {
          (*(void (__fastcall **)(__int64, _BYTE *, _QWORD))(*(_QWORD *)(*((_QWORD *)this + 41) + 136LL) + 96LL))(
            *((_QWORD *)this + 41) + 136LL,
            v17,
            v6);
        }
        mmcerror::SC::~SC((mmcerror::SC *)v17);
      }
      else
      {
        v14 = CWnd::GetParentFrame(this);
        v15 = v14;
        if ( !v14 || CFrameWnd::GetActiveView(v14) == this )
        {
          v16 = (HWND)*((_QWORD *)this + 8);
          if ( GetFocus() != v16 )
            CWnd::SetFocus(this);
        }
        else
        {
          CFrameWnd::SetActiveView(v15, this, 1);
        }
      }
    }
    (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)(*((_QWORD *)this + 41) + 136LL) + 152LL))(
      *((_QWORD *)this + 41) + 136LL,
      v17);
    mmcerror::SC::~SC((mmcerror::SC *)v17);
  }
}

```

## disassembly

```asm
0x1400d61a8  push    rbx
0x1400d61aa  push    rbp
0x1400d61ab  push    rsi
0x1400d61ac  push    rdi
0x1400d61ad  push    r14
0x1400d61af  sub     rsp, 40h
0x1400d61b3  mov     r14, r8
0x1400d61b6  mov     rbp, rdx
0x1400d61b9  mov     rdi, rcx
0x1400d61bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d61c3  lea     rax, WPP_GLOBAL_Control
0x1400d61ca  cmp     rcx, rax
0x1400d61cd  jz      short loc_1400D61EA
0x1400d61cf  cmp     byte ptr [rcx+19h], 5
0x1400d61d3  jb      short loc_1400D61EA
0x1400d61d5  mov     rcx, [rcx+10h]
0x1400d61d9  lea     r8, WPP_6033b5b997f23f8d916bc9bad54228b4_Traceguids
0x1400d61e0  mov     edx, 16h
0x1400d61e5  call    WPP_SF_
0x1400d61ea  cmp     dword ptr [rdi+140h], 1
0x1400d61f1  jz      loc_1400D63AB
0x1400d61f7  mov     rcx, [rdi+148h]
0x1400d61fe  add     rcx, 88h
0x1400d6205  mov     rax, [rcx]
0x1400d6208  mov     rax, [rax+0E0h]
0x1400d620f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400d6214  mov     rcx, [rdi+40h]; hWnd
0x1400d6218  mov     ebx, eax
0x1400d621a  call    cs:__imp_UpdateWindow
0x1400d6220  mov     r8, [rbp+88h]; struct HNODE__ *
0x1400d6227  mov     rcx, rdi; this
0x1400d622a  mov     rdx, [rbp+60h]; struct _TREEITEM *
0x1400d622e  call    ?OnSelectNode@CAMCTreeView@@AEAAJPEAU_TREEITEM@@PEAUHNODE__@@@Z; CAMCTreeView::OnSelectNode(_TREEITEM *,HNODE__ *)
0x1400d6233  movsxd  rsi, eax
0x1400d6236  test    eax, eax
0x1400d6238  jnz     short loc_1400D62A0
0x1400d623a  mov     rcx, [rdi+148h]
0x1400d6241  mov     rsi, [rcx+550h]
0x1400d6248  test    rsi, rsi
0x1400d624b  jz      short loc_1400D629C
0x1400d624d  mov     rcx, rdi; this
0x1400d6250  call    ?GetRootItem@CAMCTreeView@@QEAAPEAU_TREEITEM@@XZ; CAMCTreeView::GetRootItem(void)
0x1400d6255  cmp     rax, [rbp+60h]
0x1400d6259  lea     rdx, [rsp+68h+var_48]
0x1400d625e  mov     rcx, rsi
0x1400d6261  setnz   r8b
0x1400d6265  call    ?ScEnableUpOneLevel@CStandardToolbar@@QEAA?AVSC@mmcerror@@_N@Z; CStandardToolbar::ScEnableUpOneLevel(bool)
0x1400d626a  lea     rcx, [rsp+68h+var_48]
0x1400d626f  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x1400d6275  mov     rcx, [rdi+148h]; this
0x1400d627c  call    ?HasListOrListPad@CAMCView@@QEBA_NXZ; CAMCView::HasListOrListPad(void)
0x1400d6281  mov     r8b, al
0x1400d6284  lea     rdx, [rsp+68h+var_48]
0x1400d6289  mov     rcx, rsi
0x1400d628c  call    ?ScEnableExportList@CStandardToolbar@@QEAA?AVSC@mmcerror@@_N@Z; CStandardToolbar::ScEnableExportList(bool)
0x1400d6291  lea     rcx, [rsp+68h+var_48]
0x1400d6296  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x1400d629c  xor     eax, eax
0x1400d629e  jmp     short loc_1400D62BC
0x1400d62a0  cmp     esi, 1
0x1400d62a3  jz      loc_1400D63AB
0x1400d62a9  mov     edx, 10h
0x1400d62ae  mov     ecx, 2EE0h
0x1400d62b3  call    cs:__imp_?MMCErrorBox@@YAHII@Z; MMCErrorBox(uint,uint)
0x1400d62b9  mov     rax, rsi
0x1400d62bc  mov     [r14], rax
0x1400d62bf  cmp     ebx, 0FFFFFFFFh
0x1400d62c2  jz      loc_1400D637E
0x1400d62c8  test    ebx, ebx
0x1400d62ca  jz      short loc_1400D6333
0x1400d62cc  cmp     ebx, 1
0x1400d62cf  jz      short loc_1400D62F5
0x1400d62d1  mov     rcx, [rdi+148h]
0x1400d62d8  lea     rdx, [rsp+68h+var_48]
0x1400d62dd  add     rcx, 88h
0x1400d62e4  mov     r8d, ebx
0x1400d62e7  mov     rax, [rcx]
0x1400d62ea  mov     rax, [rax+60h]
0x1400d62ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400d62f3  jmp     short loc_1400D6326
0x1400d62f5  mov     rcx, rdi
0x1400d62f8  call    cs:__imp_?GetParentFrame@CWnd@@QEBAPEAVCFrameWnd@@XZ; CWnd::GetParentFrame(void)
0x1400d62fe  test    rax, rax
0x1400d6301  jz      short loc_1400D6315
0x1400d6303  mov     r8d, 1
0x1400d6309  mov     rdx, rdi
0x1400d630c  mov     rcx, rax
0x1400d630f  call    cs:__imp_?SetActiveView@CFrameWnd@@QEAAXPEAVCView@@H@Z; CFrameWnd::SetActiveView(CView *,int)
0x1400d6315  mov     rcx, [rdi+148h]
0x1400d631c  lea     rdx, [rsp+68h+var_48]
0x1400d6321  call    ?ScDeferSettingFocusToResultPane@CAMCView@@QEAA?AVSC@mmcerror@@XZ; CAMCView::ScDeferSettingFocusToResultPane(void)
0x1400d6326  lea     rcx, [rsp+68h+var_48]
0x1400d632b  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x1400d6331  jmp     short loc_1400D637E
0x1400d6333  mov     rcx, rdi
0x1400d6336  call    cs:__imp_?GetParentFrame@CWnd@@QEBAPEAVCFrameWnd@@XZ; CWnd::GetParentFrame(void)
0x1400d633c  mov     rbx, rax
0x1400d633f  test    rax, rax
0x1400d6342  jz      short loc_1400D6366
0x1400d6344  mov     rcx, rax
0x1400d6347  call    cs:__imp_?GetActiveView@CFrameWnd@@QEBAPEAVCView@@XZ; CFrameWnd::GetActiveView(void)
0x1400d634d  cmp     rax, rdi
0x1400d6350  jz      short loc_1400D6366
0x1400d6352  mov     r8d, 1
0x1400d6358  mov     rdx, rdi
0x1400d635b  mov     rcx, rbx
0x1400d635e  call    cs:__imp_?SetActiveView@CFrameWnd@@QEAAXPEAVCView@@H@Z; CFrameWnd::SetActiveView(CView *,int)
0x1400d6364  jmp     short loc_1400D637E
0x1400d6366  mov     rbx, [rdi+40h]
0x1400d636a  call    cs:__imp_GetFocus
0x1400d6370  cmp     rax, rbx
0x1400d6373  jz      short loc_1400D637E
0x1400d6375  mov     rcx, rdi
0x1400d6378  call    cs:__imp_?SetFocus@CWnd@@QEAAPEAV1@XZ; CWnd::SetFocus(void)
0x1400d637e  mov     rcx, [rdi+148h]
0x1400d6385  lea     rdx, [rsp+68h+var_48]
0x1400d638a  add     rcx, 88h
0x1400d6391  mov     rax, [rcx]
0x1400d6394  mov     rax, [rax+98h]
0x1400d639b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400d63a0  lea     rcx, [rsp+68h+var_48]
0x1400d63a5  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x1400d63ab  add     rsp, 40h
0x1400d63af  pop     r14
0x1400d63b1  pop     rdi
0x1400d63b2  pop     rsi
0x1400d63b3  pop     rbp
0x1400d63b4  pop     rbx
0x1400d63b5  retn
```
