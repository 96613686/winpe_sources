# CMainFrame::ScUpdateAllScopes(long,__int64)

- ea: `0x1400bdf50`
- end: `0x1400be148`
- name: `?ScUpdateAllScopes@CMainFrame@@UEAA?AVSC@mmcerror@@J_J@Z`
- size: `504`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x14000c1d0`
- `0x140048be4`
- `0x14004dcdc`
- `0x14007aa44`
- `0x1400bb3d8`
- `0x1400bd1b0`
- `0x1400bdf50`

## import_xrefs

- `USER32!SendMessageW` at `0x1400be0e1`
- `USER32!SendMessageW` at `0x1400be0e1`
- `MFC42u!__imp_??0AFX_MAINTAIN_STATE2@@QEAA@PEAVAFX_MODULE_STATE@@@Z` at `0x1400bdf7e`
- `MFC42u!__imp_??0AFX_MAINTAIN_STATE2@@QEAA@PEAVAFX_MODULE_STATE@@@Z` at `0x1400bdf7e`
- `MFC42u!__imp_?AfxGetAppModuleState@@YAPEAVAFX_MODULE_STATE@@XZ` at `0x1400bdf71`
- `MFC42u!__imp_?AfxGetAppModuleState@@YAPEAVAFX_MODULE_STATE@@XZ` at `0x1400bdf71`
- `MFC42u!__imp_?UpdateAllViews@CDocument@@QEAAXPEAVCView@@_JPEAVCObject@@@Z` at `0x1400bdffe`
- `MFC42u!__imp_?UpdateAllViews@CDocument@@QEAAXPEAVCView@@_JPEAVCObject@@@Z` at `0x1400be108`
- `MFC42u!__imp_?UpdateAllViews@CDocument@@QEAAXPEAVCView@@_JPEAVCObject@@@Z` at `0x1400bdffe`
- `MFC42u!__imp_?UpdateAllViews@CDocument@@QEAAXPEAVCView@@_JPEAVCObject@@@Z` at `0x1400be108`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400be049`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400be099`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400be120`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400be049`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400be099`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400be120`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1400be053`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1400be0a3`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1400be053`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1400be0a3`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x1400bdf8b`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x1400bdf8b`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1400bdfd0`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1400bdfd0`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x1400be115`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x1400be115`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1400be03e`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1400be08e`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1400be03e`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1400be08e`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x1400bdf9d`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x1400bdf9d`
- `mmcbase!?TraceAndClear@SC@mmcerror@@QEAAXXZ` at `0x1400be061`
- `mmcbase!?TraceAndClear@SC@mmcerror@@QEAAXXZ` at `0x1400be061`

## string_xrefs

- `0x1400bdf92`: `CMainFrame::ScUpdateAllScopes`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
mmcerror::SC *__fastcall CMainFrame::ScUpdateAllScopes(__int64 a1, mmcerror::SC *a2, int a3, struct CObject *a4)
{
  __int64 v5; // r14
  struct AFX_MODULE_STATE *AppModuleState; // rax
  CAMCDoc *v9; // rdi
  const struct mmcerror::SC *v10; // rdx
  int NumberOfPersistedViews; // esi
  int i; // edi
  CAMCView *v13; // r14
  __int64 v14; // rax
  struct CChildFrame *ParentFrame; // r15
  __int64 v16; // rax
  bool IsPersisted; // al
  int v18; // ecx
  _QWORD v20[2]; // [rsp+28h] [rbp-58h] BYREF
  _BYTE v21[24]; // [rsp+38h] [rbp-48h] BYREF
  __int64 v22; // [rsp+50h] [rbp-30h] BYREF
  int v23; // [rsp+58h] [rbp-28h]
  __int64 v24; // [rsp+5Ch] [rbp-24h]
  _BYTE v25[24]; // [rsp+68h] [rbp-18h] BYREF

  v5 = a3;
  AppModuleState = AfxGetAppModuleState();
  AFX_MAINTAIN_STATE2::AFX_MAINTAIN_STATE2((AFX_MAINTAIN_STATE2 *)v20, AppModuleState);
  mmcerror::SC::SC((mmcerror::SC *)v21, 0);
  mmcerror::SC::SetFunctionName((mmcerror::SC *)v21, L"CMainFrame::ScUpdateAllScopes");
  v9 = CAMCDoc::m_pDoc;
  if ( !CAMCDoc::m_pDoc )
    goto LABEL_17;
  if ( (_DWORD)v5 != 789 )
  {
    CDocument::UpdateAllViews(CAMCDoc::m_pDoc, 0, v5, a4);
LABEL_17:
    v10 = (const struct mmcerror::SC *)v21;
    goto LABEL_18;
  }
  if ( !a4 )
  {
    v22 = 0;
    v24 = 0;
    v23 = 0;
    CDocument::UpdateAllViews(CAMCDoc::m_pDoc, 0, 789, (struct CObject *)&v22);
    NumberOfPersistedViews = CAMCDoc::GetNumberOfPersistedViews(v9);
    for ( i = 0; i < v23; ++i )
    {
      v13 = *(CAMCView **)(v22 + 8LL * i);
      v14 = ScCheckPointers(v25, v13, 2147942487LL);
      mmcerror::SC::operator=(v21, v14);
      mmcerror::SC::~SC((mmcerror::SC *)v25);
      if ( (unsigned __int8)mmcerror::SC::operator bool(v21)
        || (ParentFrame = CAMCView::GetParentFrame(v13),
            v16 = ScCheckPointers(v25, ParentFrame, 2147942487LL),
            mmcerror::SC::operator=(v21, v16),
            mmcerror::SC::~SC((mmcerror::SC *)v25),
            (unsigned __int8)mmcerror::SC::operator bool(v21)) )
      {
        mmcerror::SC::TraceAndClear((mmcerror::SC *)v21);
      }
      else
      {
        IsPersisted = CAMCView::IsPersisted(v13);
        v18 = NumberOfPersistedViews - 1;
        if ( !IsPersisted )
          v18 = NumberOfPersistedViews;
        NumberOfPersistedViews = v18;
        if ( !v18 )
          CMainFrame::OnWindowNew((CMainFrame *)(a1 - 344));
        SendMessageW(*((HWND *)ParentFrame + 8), 0x112u, 0xF060u, 0);
      }
    }
    CArray<CAMCView *,CAMCView *>::~CArray<CAMCView *,CAMCView *>(&v22);
    goto LABEL_17;
  }
  v10 = (const struct mmcerror::SC *)mmcerror::SC::operator=(v21, 2147549183LL);
LABEL_18:
  mmcerror::SC::SC(a2, v10);
  mmcerror::SC::~SC((mmcerror::SC *)v21);
  *(_QWORD *)(v20[1] + 8LL) = v20[0];
  return a2;
}

```

## disassembly

```asm
0x1400bdf50  push    rbp
0x1400bdf52  push    rbx
0x1400bdf53  push    rsi
0x1400bdf54  push    rdi
0x1400bdf55  push    r13
0x1400bdf57  push    r14
0x1400bdf59  push    r15
0x1400bdf5b  mov     rbp, rsp
0x1400bdf5e  sub     rsp, 80h
0x1400bdf65  mov     rsi, r9
0x1400bdf68  movsxd  r14, r8d
0x1400bdf6b  mov     rbx, rdx
0x1400bdf6e  mov     r13, rcx
0x1400bdf71  call    cs:__imp_?AfxGetAppModuleState@@YAPEAVAFX_MODULE_STATE@@XZ; AfxGetAppModuleState(void)
0x1400bdf77  mov     rdx, rax
0x1400bdf7a  lea     rcx, [rbp+var_58]
0x1400bdf7e  call    cs:__imp_??0AFX_MAINTAIN_STATE2@@QEAA@PEAVAFX_MODULE_STATE@@@Z; AFX_MAINTAIN_STATE2::AFX_MAINTAIN_STATE2(AFX_MODULE_STATE *)
0x1400bdf84  nop
0x1400bdf85  xor     edx, edx
0x1400bdf87  lea     rcx, [rbp+var_48]
0x1400bdf8b  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x1400bdf91  nop
0x1400bdf92  lea     rdx, aCmainframeScup; "CMainFrame::ScUpdateAllScopes"
0x1400bdf99  lea     rcx, [rbp+var_48]
0x1400bdf9d  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x1400bdfa3  mov     rdi, cs:?m_pDoc@CAMCDoc@@0PEAV1@EA; CAMCDoc * CAMCDoc::m_pDoc
0x1400bdfaa  test    rdi, rdi
0x1400bdfad  jz      loc_1400BE10E
0x1400bdfb3  mov     r8d, 315h
0x1400bdfb9  cmp     r14d, r8d
0x1400bdfbc  jnz     loc_1400BE0FD
0x1400bdfc2  test    rsi, rsi
0x1400bdfc5  jz      short loc_1400BDFDE
0x1400bdfc7  mov     edx, 8000FFFFh
0x1400bdfcc  lea     rcx, [rbp+var_48]
0x1400bdfd0  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x1400bdfd6  mov     rdx, rax
0x1400bdfd9  jmp     loc_1400BE112
0x1400bdfde  mov     [rbp+var_30], 0
0x1400bdfe6  mov     [rbp+var_24], 0
0x1400bdfee  mov     [rbp+var_28], 0
0x1400bdff5  lea     r9, [rbp+var_30]
0x1400bdff9  xor     edx, edx
0x1400bdffb  mov     rcx, rdi
0x1400bdffe  call    cs:__imp_?UpdateAllViews@CDocument@@QEAAXPEAVCView@@_JPEAVCObject@@@Z; CDocument::UpdateAllViews(CView *,__int64,CObject *)
0x1400be004  mov     rcx, rdi; this
0x1400be007  call    ?GetNumberOfPersistedViews@CAMCDoc@@QEAAHXZ; CAMCDoc::GetNumberOfPersistedViews(void)
0x1400be00c  mov     esi, eax
0x1400be00e  xor     edi, edi
0x1400be010  cmp     [rbp+var_28], edi
0x1400be013  jle     loc_1400BE0F2
0x1400be019  movsxd  rdx, edi
0x1400be01c  mov     rcx, [rbp+var_30]
0x1400be020  mov     r14, [rcx+rdx*8]
0x1400be024  mov     r8d, 80070057h
0x1400be02a  mov     rdx, r14
0x1400be02d  lea     rcx, [rbp+var_18]
0x1400be031  call    ?ScCheckPointers@@YA?AVSC@mmcerror@@PEBXJ@Z; ScCheckPointers(void const *,long)
0x1400be036  nop
0x1400be037  mov     rdx, rax
0x1400be03a  lea     rcx, [rbp+var_48]
0x1400be03e  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x1400be044  nop
0x1400be045  lea     rcx, [rbp+var_18]
0x1400be049  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x1400be04f  lea     rcx, [rbp+var_48]
0x1400be053  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x1400be059  test    al, al
0x1400be05b  jz      short loc_1400BE069
0x1400be05d  lea     rcx, [rbp+var_48]
0x1400be061  call    cs:__imp_?TraceAndClear@SC@mmcerror@@QEAAXXZ; mmcerror::SC::TraceAndClear(void)
0x1400be067  jmp     short loc_1400BE0E7
0x1400be069  mov     rcx, r14; this
0x1400be06c  call    ?GetParentFrame@CAMCView@@IEBAPEAVCChildFrame@@XZ; CAMCView::GetParentFrame(void)
0x1400be071  mov     r15, rax
0x1400be074  mov     r8d, 80070057h
0x1400be07a  mov     rdx, rax
0x1400be07d  lea     rcx, [rbp+var_18]
0x1400be081  call    ?ScCheckPointers@@YA?AVSC@mmcerror@@PEBXJ@Z; ScCheckPointers(void const *,long)
0x1400be086  nop
0x1400be087  mov     rdx, rax
0x1400be08a  lea     rcx, [rbp+var_48]
0x1400be08e  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x1400be094  nop
0x1400be095  lea     rcx, [rbp+var_18]
0x1400be099  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x1400be09f  lea     rcx, [rbp+var_48]
0x1400be0a3  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x1400be0a9  test    al, al
0x1400be0ab  jnz     short loc_1400BE05D
0x1400be0ad  mov     rcx, r14; this
0x1400be0b0  call    ?IsPersisted@CAMCView@@QEBA_NXZ; CAMCView::IsPersisted(void)
0x1400be0b5  lea     ecx, [rsi-1]
0x1400be0b8  test    al, al
0x1400be0ba  cmovz   ecx, esi
0x1400be0bd  mov     esi, ecx
0x1400be0bf  test    ecx, ecx
0x1400be0c1  jnz     short loc_1400BE0CF
0x1400be0c3  lea     rcx, [r13-158h]; this
0x1400be0ca  call    ?OnWindowNew@CMainFrame@@IEAAXXZ; CMainFrame::OnWindowNew(void)
0x1400be0cf  xor     r9d, r9d; lParam
0x1400be0d2  mov     edx, 112h; Msg
0x1400be0d7  mov     r8d, 0F060h; wParam
0x1400be0dd  mov     rcx, [r15+40h]; hWnd
0x1400be0e1  call    cs:__imp_SendMessageW
0x1400be0e7  inc     edi
0x1400be0e9  cmp     edi, [rbp+var_28]
0x1400be0ec  jl      loc_1400BE019
0x1400be0f2  lea     rcx, [rbp+var_30]
0x1400be0f6  call    ??1?$CArray@PEAVCAMCView@@PEAV1@@@QEAA@XZ; CArray<CAMCView *,CAMCView *>::~CArray<CAMCView *,CAMCView *>(void)
0x1400be0fb  jmp     short loc_1400BE10E
0x1400be0fd  mov     r8, r14
0x1400be100  mov     r9, rsi
0x1400be103  xor     edx, edx
0x1400be105  mov     rcx, rdi
0x1400be108  call    cs:__imp_?UpdateAllViews@CDocument@@QEAAXPEAVCView@@_JPEAVCObject@@@Z; CDocument::UpdateAllViews(CView *,__int64,CObject *)
0x1400be10e  lea     rdx, [rbp+var_48]
0x1400be112  mov     rcx, rbx
0x1400be115  call    cs:__imp_??0SC@mmcerror@@QEAA@AEBV01@@Z; mmcerror::SC::SC(mmcerror::SC const &)
0x1400be11b  nop
0x1400be11c  lea     rcx, [rbp+var_48]
0x1400be120  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x1400be126  nop
0x1400be127  mov     rax, [rbp+var_50]
0x1400be12b  mov     rcx, [rbp+var_58]
0x1400be12f  mov     [rax+8], rcx
0x1400be133  mov     rax, rbx
0x1400be136  add     rsp, 80h
0x1400be13d  pop     r15
0x1400be13f  pop     r14
0x1400be141  pop     r13
0x1400be143  pop     rdi
0x1400be144  pop     rsi
0x1400be145  pop     rbx
0x1400be146  pop     rbp
0x1400be147  retn
```
