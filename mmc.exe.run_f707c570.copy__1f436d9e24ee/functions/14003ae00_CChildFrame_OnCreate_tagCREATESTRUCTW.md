# CChildFrame::OnCreate(tagCREATESTRUCTW *)

- ea: `0x14003ae00`
- end: `0x14003b0a1`
- name: `?OnCreate@CChildFrame@@IEAAHPEAUtagCREATESTRUCTW@@@Z`
- size: `673`
- prototype: `__int64 __fastcall(CChildFrame *__hidden this, struct tagCREATESTRUCTW *)`
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x14000c1d0`
- `0x140014448`
- `0x14001ad8c`
- `0x14002bfc0`
- `0x14002c4bc`
- `0x14003ae00`
- `0x14004a54c`
- `0x14004a570`
- `0x140054490`
- `0x140054cc4`
- `0x14006623c`
- `0x1400ac650`
- `0x1400c292c`
- `0x1400d1810`
- `0x1400f3010`

## import_xrefs

- `USER32!IsWindow` at `0x14003af32`
- `USER32!IsWindow` at `0x14003af32`
- `MFC42u!__imp_?OnCreate@CMDIChildWnd@@IEAAHPEAUtagCREATESTRUCTW@@@Z` at `0x14003ae4d`
- `MFC42u!__imp_?OnCreate@CMDIChildWnd@@IEAAHPEAUtagCREATESTRUCTW@@@Z` at `0x14003ae4d`
- `MFC42u!__imp_??2@YAPEAX_K@Z` at `0x14003af55`
- `MFC42u!__imp_??2@YAPEAX_K@Z` at `0x14003af55`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14003afe5`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14003b029`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14003b08b`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14003afe5`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14003b029`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14003b08b`
- `mmcbase!?s_CallDepth@SC@mmcerror@@0IA` at `0x14003ae24`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x14003afda`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x14003b01e`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x14003afda`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x14003b01e`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x14003ae41`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x14003ae41`

## string_xrefs

- `0x14003ae36`: `CChildFrame::OnCreate`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
// Hidden C++ exception states: #wind=3
__int64 __fastcall CChildFrame::OnCreate(CChildFrame *this, struct tagCREATESTRUCTW *a2)
{
  unsigned int v4; // r15d
  unsigned int *v5; // rdx
  int v6; // r8d
  __int64 v7; // r14
  __int64 v8; // rbx
  __int64 v9; // r14
  CMenuButtonsMgrImpl *v10; // rax
  CMenuButtonsMgrImpl *v11; // rdi
  CMenuButtonsMgrImpl **v12; // rbx
  struct CMainFrame *v13; // rdi
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  int v17; // edx
  CMenuButtonsMgrImpl *v19; // [rsp+30h] [rbp-48h] BYREF
  signed __int64 v20; // [rsp+38h] [rbp-40h] BYREF
  __int128 v21; // [rsp+40h] [rbp-38h]
  _BYTE v22[40]; // [rsp+50h] [rbp-28h] BYREF

  v21 = 0;
  ++mmcerror::SC::s_CallDepth;
  v20 = 3;
  mmcerror::SC::SetFunctionName((mmcerror::SC *)&v20, L"CChildFrame::OnCreate");
  v4 = -1;
  if ( CMDIChildWnd::OnCreate(this, a2) == -1 )
  {
    v20 = 0x8000FFFF00000003uLL;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 10, WPP_2af5b5ba7865315b7a5d27c22d7d9b88_Traceguids);
  }
  else
  {
    (*(void (__fastcall **)(char *, CChildFrame *, __int64, __int64))(*((_QWORD *)this + 57) + 392LL))(
      (char *)this + 456,
      this,
      1342177536,
      4099);
    CStatBar::CreatePanes((CChildFrame *)((char *)this + 456), v5, v6);
    CDockSite::Create((char *)this + 408, 1);
    CList<CDockSite *,CDockSite *>::AddTail(*((_QWORD *)this + 52), (char *)this + 456);
    (*(void (__fastcall **)(char *, __int64))(*((_QWORD *)this + 51) + 8LL))((char *)this + 408, 1);
    CDockManager<CDockSite>::Attach((char *)this + 384, (char *)this + 408);
    v7 = *((_QWORD *)this + 126);
    if ( !v7 )
      goto LABEL_24;
    v8 = *((_QWORD *)this + 8);
    if ( v8 && IsWindow(*((HWND *)this + 8)) )
      *(_QWORD *)(v7 + 1008) = v8;
    v9 = v7 + 904;
    if ( !v9 )
      goto LABEL_24;
    v10 = (CMenuButtonsMgrImpl *)operator new(0x48u);
    if ( v10 )
      v11 = CMenuButtonsMgrImpl::CMenuButtonsMgrImpl(v10);
    else
      v11 = 0;
    v19 = v11;
    v12 = (CMenuButtonsMgrImpl **)((char *)this + 1032);
    if ( (CMenuButtonsMgrImpl **)((char *)this + 1032) != &v19 )
    {
      v19 = 0;
      if ( v11 != *v12 )
      {
        std::unique_ptr<CMenuButtonsMgrImpl>::_Delete((char *)this + 1032);
        *v12 = v11;
      }
    }
    std::unique_ptr<CMenuButtonsMgrImpl>::_Delete(&v19);
    if ( *v12 )
    {
      *(_QWORD *)(v9 + 24) = *v12;
      v13 = AMCGetMainWnd();
      v14 = ScCheckPointers(v22, v13, 2147549183LL);
      mmcerror::SC::operator=(&v20, v14);
      mmcerror::SC::~SC((mmcerror::SC *)v22);
      if ( !HIDWORD(v20) || (_DWORD)v20 == 3 && v20 >= 0 )
      {
        v15 = CMenuButtonsMgrImpl::ScInit(*v12, v22, v13, this);
        mmcerror::SC::operator=(&v20, v15);
        mmcerror::SC::~SC((mmcerror::SC *)v22);
        if ( !HIDWORD(v20) || (_DWORD)v20 == 3 && v20 >= 0 )
        {
          v16 = _com_ptr_t<_com_IIID<IScopeTree,&_GUID const IID_IScopeTree>>::operator->(v9 + 128);
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v16 + 248LL))(v16, v9);
          AppendToSystemMenu(this, v17);
          CChildFrame::RenderDockSites(this);
          v4 = 0;
        }
      }
    }
    else
    {
LABEL_24:
      v20 = 0x8000FFFF00000003uLL;
    }
  }
  mmcerror::SC::~SC((mmcerror::SC *)&v20);
  return v4;
}

```

## disassembly

```asm
0x14003ae00  push    rbp
0x14003ae02  push    rbx
0x14003ae03  push    rsi
0x14003ae04  push    rdi
0x14003ae05  push    r14
0x14003ae07  push    r15
0x14003ae09  mov     rbp, rsp
0x14003ae0c  sub     rsp, 78h
0x14003ae10  mov     rbx, rdx
0x14003ae13  mov     rsi, rcx
0x14003ae16  xorps   xmm0, xmm0
0x14003ae19  movdqu  [rbp+var_38], xmm0
0x14003ae1e  mov     r14d, 1
0x14003ae24  mov     rax, cs:__imp_?s_CallDepth@SC@mmcerror@@0IA; uint mmcerror::SC::s_CallDepth
0x14003ae2b  add     [rax], r14d
0x14003ae2e  mov     [rbp+var_40], 3
0x14003ae36  lea     rdx, aCchildframeOnc; "CChildFrame::OnCreate"
0x14003ae3d  lea     rcx, [rbp+var_40]
0x14003ae41  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x14003ae47  mov     rdx, rbx
0x14003ae4a  mov     rcx, rsi
0x14003ae4d  call    cs:__imp_?OnCreate@CMDIChildWnd@@IEAAHPEAUtagCREATESTRUCTW@@@Z; CMDIChildWnd::OnCreate(tagCREATESTRUCTW *)
0x14003ae53  or      r15d, 0FFFFFFFFh
0x14003ae57  cmp     eax, r15d
0x14003ae5a  jnz     short loc_14003AEA4
0x14003ae5c  mov     dword ptr [rbp+var_40], 3
0x14003ae63  mov     dword ptr [rbp+var_40+4], 8000FFFFh
0x14003ae6a  lea     rax, WPP_GLOBAL_Control
0x14003ae71  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ae78  cmp     rcx, rax
0x14003ae7b  jz      loc_14003B087
0x14003ae81  cmp     byte ptr [rcx+19h], 2
0x14003ae85  jb      loc_14003B087
0x14003ae8b  lea     edx, [r14+9]
0x14003ae8f  lea     r8, WPP_2af5b5ba7865315b7a5d27c22d7d9b88_Traceguids
0x14003ae96  mov     rcx, [rcx+10h]
0x14003ae9a  call    WPP_SF_
0x14003ae9f  jmp     loc_14003B087
0x14003aea4  lea     rdi, [rsi+1C8h]
0x14003aeab  mov     rax, [rdi]
0x14003aeae  mov     r9d, 1003h
0x14003aeb4  mov     r8d, 50000100h
0x14003aeba  mov     rdx, rsi
0x14003aebd  mov     rcx, rdi
0x14003aec0  mov     rax, [rax+188h]
0x14003aec7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003aecc  mov     rcx, rdi; this
0x14003aecf  call    ?CreatePanes@CStatBar@@QEAAHPEAIH@Z; CStatBar::CreatePanes(uint *,int)
0x14003aed4  lea     rbx, [rsi+198h]
0x14003aedb  mov     edx, r14d
0x14003aede  mov     rcx, rbx
0x14003aee1  call    ?Create@CDockSite@@QEAAHW4DSS_STYLE@1@@Z; CDockSite::Create(CDockSite::DSS_STYLE)
0x14003aee6  mov     rdx, rdi
0x14003aee9  mov     rcx, [rsi+1A0h]
0x14003aef0  call    ?AddTail@?$CList@PEAVCDockSite@@PEAV1@@@QEAAPEAU__POSITION@@PEAVCDockSite@@@Z; CList<CDockSite *,CDockSite *>::AddTail(CDockSite *)
0x14003aef5  mov     rax, [rbx]
0x14003aef8  mov     edx, r14d
0x14003aefb  mov     rcx, rbx
0x14003aefe  mov     rax, [rax+8]
0x14003af02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003af07  lea     rcx, [rsi+180h]
0x14003af0e  mov     rdx, rbx
0x14003af11  call    ?Attach@?$CDockManager@VCDockSite@@@@QEAAHPEAVCDockSite@@@Z; CDockManager<CDockSite>::Attach(CDockSite *)
0x14003af16  mov     r14, [rsi+3F0h]
0x14003af1d  test    r14, r14
0x14003af20  jz      loc_14003B079
0x14003af26  mov     rbx, [rsi+40h]
0x14003af2a  test    rbx, rbx
0x14003af2d  jz      short loc_14003AF43
0x14003af2f  mov     rcx, rbx; hWnd
0x14003af32  call    cs:__imp_IsWindow
0x14003af38  test    eax, eax
0x14003af3a  jz      short loc_14003AF43
0x14003af3c  mov     [r14+3F0h], rbx
0x14003af43  add     r14, 388h
0x14003af4a  jz      loc_14003B079
0x14003af50  mov     ecx, 48h ; 'H'
0x14003af55  call    cs:__imp_??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14003af5b  mov     [rbp+arg_10], rax
0x14003af5f  test    rax, rax
0x14003af62  jz      short loc_14003AF71
0x14003af64  mov     rcx, rax; this
0x14003af67  call    ??0CMenuButtonsMgrImpl@@QEAA@XZ; CMenuButtonsMgrImpl::CMenuButtonsMgrImpl(void)
0x14003af6c  mov     rdi, rax
0x14003af6f  jmp     short loc_14003AF73
0x14003af71  xor     edi, edi
0x14003af73  mov     [rbp+var_48], rdi
0x14003af77  lea     rbx, [rsi+408h]
0x14003af7e  lea     rax, [rbp+var_48]
0x14003af82  cmp     rbx, rax
0x14003af85  jz      short loc_14003AF9F
0x14003af87  mov     [rbp+var_48], 0
0x14003af8f  cmp     rdi, [rbx]
0x14003af92  jz      short loc_14003AF9F
0x14003af94  mov     rcx, rbx
0x14003af97  call    ?_Delete@?$unique_ptr@VCMenuButtonsMgrImpl@@U?$default_delete@VCMenuButtonsMgrImpl@@@std@@@std@@AEAAXXZ; std::unique_ptr<CMenuButtonsMgrImpl>::_Delete(void)
0x14003af9c  mov     [rbx], rdi
0x14003af9f  lea     rcx, [rbp+var_48]
0x14003afa3  call    ?_Delete@?$unique_ptr@VCMenuButtonsMgrImpl@@U?$default_delete@VCMenuButtonsMgrImpl@@@std@@@std@@AEAAXXZ; std::unique_ptr<CMenuButtonsMgrImpl>::_Delete(void)
0x14003afa8  mov     rax, [rbx]
0x14003afab  test    rax, rax
0x14003afae  jz      loc_14003B079
0x14003afb4  mov     [r14+18h], rax
0x14003afb8  call    ?AMCGetMainWnd@@YAPEAVCMainFrame@@XZ; AMCGetMainWnd(void)
0x14003afbd  mov     rdi, rax
0x14003afc0  mov     r8d, 8000FFFFh
0x14003afc6  mov     rdx, rax
0x14003afc9  lea     rcx, [rbp+var_28]
0x14003afcd  call    ?ScCheckPointers@@YA?AVSC@mmcerror@@PEBXJ@Z; ScCheckPointers(void const *,long)
0x14003afd2  nop
0x14003afd3  mov     rdx, rax
0x14003afd6  lea     rcx, [rbp+var_40]
0x14003afda  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x14003afe0  nop
0x14003afe1  lea     rcx, [rbp+var_28]
0x14003afe5  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x14003afeb  mov     eax, dword ptr [rbp+var_40+4]
0x14003afee  test    eax, eax
0x14003aff0  jz      short loc_14003B004
0x14003aff2  cmp     dword ptr [rbp+var_40], 3
0x14003aff6  jnz     loc_14003B087
0x14003affc  test    eax, eax
0x14003affe  js      loc_14003B087
0x14003b004  mov     r9, rsi
0x14003b007  mov     r8, rdi
0x14003b00a  lea     rdx, [rbp+var_28]
0x14003b00e  mov     rcx, [rbx]
0x14003b011  call    ?ScInit@CMenuButtonsMgrImpl@@QEAA?AVSC@mmcerror@@PEAVCMainFrame@@PEAVCChildFrame@@@Z; CMenuButtonsMgrImpl::ScInit(CMainFrame *,CChildFrame *)
0x14003b016  nop
0x14003b017  mov     rdx, rax
0x14003b01a  lea     rcx, [rbp+var_40]
0x14003b01e  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x14003b024  nop
0x14003b025  lea     rcx, [rbp+var_28]
0x14003b029  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x14003b02f  mov     eax, dword ptr [rbp+var_40+4]
0x14003b032  test    eax, eax
0x14003b034  jz      short loc_14003B040
0x14003b036  cmp     dword ptr [rbp+var_40], 3
0x14003b03a  jnz     short loc_14003B087
0x14003b03c  test    eax, eax
0x14003b03e  js      short loc_14003B087
0x14003b040  lea     rcx, [r14+80h]
0x14003b047  call    ??C?$_com_ptr_t@V?$_com_IIID@UIScopeTree@@$1?IID_IScopeTree@@3U_GUID@@B@@@@QEBAPEAUIScopeTree@@XZ; _com_ptr_t<_com_IIID<IScopeTree,&_GUID const IID_IScopeTree>>::operator->(void)
0x14003b04c  mov     r8, rax
0x14003b04f  mov     rcx, [rax]
0x14003b052  mov     rax, [rcx+0F8h]
0x14003b059  mov     rdx, r14
0x14003b05c  mov     rcx, r8
0x14003b05f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b064  mov     rcx, rsi; this
0x14003b067  call    ?AppendToSystemMenu@@YAHPEAVCWnd@@H@Z; AppendToSystemMenu(CWnd *,int)
0x14003b06c  mov     rcx, rsi; this
0x14003b06f  call    ?RenderDockSites@CChildFrame@@QEAAXXZ; CChildFrame::RenderDockSites(void)
0x14003b074  xor     r15d, r15d
0x14003b077  jmp     short loc_14003B087
0x14003b079  mov     dword ptr [rbp+var_40], 3
0x14003b080  mov     dword ptr [rbp+var_40+4], 8000FFFFh
0x14003b087  lea     rcx, [rbp+var_40]
0x14003b08b  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x14003b091  mov     eax, r15d
0x14003b094  add     rsp, 78h
0x14003b098  pop     r15
0x14003b09a  pop     r14
0x14003b09c  pop     rdi
0x14003b09d  pop     rsi
0x14003b09e  pop     rbx
0x14003b09f  pop     rbp
0x14003b0a0  retn
```
