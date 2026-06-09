# CAMCTreeView::OnCreate(tagCREATESTRUCTW *)

- ea: `0x140024c60`
- end: `0x140025083`
- name: `?OnCreate@CAMCTreeView@@IEAAHPEAUtagCREATESTRUCTW@@@Z`
- size: `1059`
- prototype: `__int64 __fastcall(CAMCTreeView *__hidden this, struct tagCREATESTRUCTW *)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x140024c60`
- `0x14002508c`
- `0x140025178`
- `0x140025204`
- `0x1400253a4`
- `0x14004f814`
- `0x1400598b4`
- `0x14005999c`
- `0x140065380`
- `0x14006623c`
- `0x1400d585c`
- `0x1400d6714`
- `0x1400f3010`

## import_xrefs

- `GDI32!DeleteObject` at `0x140024f21`
- `GDI32!DeleteObject` at `0x140024f21`
- `USER32!LoadImageW` at `0x140024e8b`
- `USER32!LoadImageW` at `0x140024e8b`
- `USER32!SendMessageW` at `0x140024f92`
- `USER32!SendMessageW` at `0x140024f92`
- `USER32!IsWindow` at `0x140024e03`
- `USER32!IsWindow` at `0x140024e03`
- `MFC42u!__imp_?Attach@CGdiObject@@QEAAHPEAX@Z` at `0x140024ee9`
- `MFC42u!__imp_?Attach@CGdiObject@@QEAAHPEAX@Z` at `0x140024ee9`
- `MFC42u!__imp_?OnCreate@CView@@IEAAHPEAUtagCREATESTRUCTW@@@Z` at `0x140024cd7`
- `MFC42u!__imp_?OnCreate@CView@@IEAAHPEAUtagCREATESTRUCTW@@@Z` at `0x140024cd7`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x140024fbe`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x140025016`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14002505e`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x140024fbe`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x140025016`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14002505e`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x140024fc8`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x140024fea`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x140024fc8`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x140024fea`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x140024c88`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x140024c88`
- `mmcbase!LoadStandardOverlays` at `0x140024f54`
- `mmcbase!LoadStandardOverlays` at `0x140024f54`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x140024fe0`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x140024fe0`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x140024fb3`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x140024fb3`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x140024c9a`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x140024c9a`
- `UxTheme!SetWindowTheme` at `0x140024d15`
- `UxTheme!SetWindowTheme` at `0x140024d15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140024e99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140024e99`

## string_xrefs

- `0x140024c8f`: `CAMCTreeView::OnCreate`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CAMCTreeView::OnCreate(HWND *this, struct tagCREATESTRUCTW *a2)
{
  __int64 v4; // rcx
  __int64 v5; // rdx
  HWND *v6; // r14
  struct CAMCView *AMCView; // rax
  unsigned __int64 v8; // r8
  __int64 *v9; // rdx
  __int64 *v10; // rax
  __int64 *v11; // rcx
  HWND v12; // rdi
  __int64 v13; // rcx
  HWND *v14; // rbx
  HWND v15; // rbx
  HWND v16; // rcx
  bool v17; // cl
  __int64 v18; // rcx
  __int64 v19; // rcx
  struct _IMAGELIST **v20; // rdi
  HANDLE ImageW; // rbx
  signed int LastError; // eax
  bool v23; // sf
  int v24; // eax
  __int64 v25; // rax
  unsigned int NodeManager; // eax
  HWND v28; // [rsp+30h] [rbp-50h] BYREF
  void **v29; // [rsp+38h] [rbp-48h] BYREF
  __int64 v30; // [rsp+40h] [rbp-40h]
  _BYTE v31[24]; // [rsp+48h] [rbp-38h] BYREF
  _BYTE v32[32]; // [rsp+60h] [rbp-20h] BYREF
  int v33; // [rsp+C0h] [rbp+40h] BYREF
  int v34; // [rsp+C8h] [rbp+48h] BYREF

  mmcerror::SC::SC((mmcerror::SC *)v31, 0);
  mmcerror::SC::SetFunctionName((mmcerror::SC *)v31, L"CAMCTreeView::OnCreate");
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 27, WPP_6033b5b997f23f8d916bc9bad54228b4_Traceguids);
  if ( CView::OnCreate((CView *)this, a2) == -1 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_50;
    v5 = 28;
    goto LABEL_49;
  }
  v6 = this + 8;
  SetWindowTheme(this[8], L"Explorer", 0);
  AMCView = GetAMCView((struct CWnd *)this);
  this[41] = (HWND)AMCView;
  if ( !AMCView )
  {
    v4 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_50;
    v5 = 29;
    goto LABEL_49;
  }
  v8 = *((_QWORD *)AMCView + 8);
  v9 = (__int64 *)*((_QWORD *)AMCView + 46);
  v10 = (__int64 *)v9[1];
  v11 = v9;
  if ( !*((_BYTE *)v10 + 25) )
  {
    do
    {
      if ( v10[4] >= v8 )
      {
        v11 = v10;
        v10 = (__int64 *)*v10;
      }
      else
      {
        v10 = (__int64 *)v10[2];
      }
    }
    while ( !*((_BYTE *)v10 + 25) );
    if ( v11 != v9 && v8 >= v11[4] )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11[6] + 8LL))(v11[6]);
  }
  v28 = 0;
  ATL::CComObject<EmbeddedWindowTreeProvider>::CreateInstance(&v28, v9, v8);
  v12 = v28;
  (*(void (__fastcall **)(HWND))(*(_QWORD *)v28 + 8LL))(v28);
  (*(void (__fastcall **)(HWND))(*(_QWORD *)v12 + 72LL))(v12);
  v14 = (HWND *)std::map<HWND__ *,CAMCTreeView::UiProviderContext>::operator[](v13, this + 8);
  *v14 = *v6;
  v14[1] = v12;
  (*(void (__fastcall **)(HWND))(*(_QWORD *)v12 + 8LL))(v12);
  v15 = v14[1];
  v16 = *v6;
  *((_QWORD *)v15 + 9) = *v6;
  v17 = v16 && IsWindow(v16);
  **((_BYTE **)v15 + 11) = v17;
  v18 = *((_QWORD *)this[41] + 16);
  if ( !v18 || (v19 = *(_QWORD *)(v18 + 512)) == 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_50;
    v5 = 30;
LABEL_49:
    WPP_SF_(*(_QWORD *)(v4 + 16), v5, WPP_6033b5b997f23f8d916bc9bad54228b4_Traceguids);
    goto LABEL_50;
  }
  v20 = (struct _IMAGELIST **)(this + 49);
  (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v19 + 88LL))(v19, (char *)this + 392);
  v30 = 0;
  v29 = &CBitmap::`vftable';
  ImageW = LoadImageW(hInstance, (LPCWSTR)0x9E, 0, 0, 0, 0x2000u);
  if ( ImageW )
    goto LABEL_53;
  LastError = GetLastError();
  v23 = LastError < 0;
  if ( LastError > 0 )
  {
    LastError = (unsigned __int16)LastError | 0x80070000;
    v23 = LastError < 0;
  }
  if ( !v23 )
  {
LABEL_53:
    if ( !CGdiObject::Attach((CGdiObject *)&v29, ImageW) )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 11, WPP_799888a1cce93b9936bfd71a80878bc5_Traceguids, 158);
      DeleteObject(ImageW);
    }
  }
  else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    WPP_SF_Dd(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      10,
      WPP_799888a1cce93b9936bfd71a80878bc5_Traceguids,
      158,
      LastError);
  }
  IsolationAwareImageList_Add(*v20, v30, 0);
  v34 = 0;
  v33 = 0;
  v24 = LoadStandardOverlays(*v20, 16, &v34, &v33);
  if ( v24 < 0 && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) )
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      31,
      WPP_6033b5b997f23f8d916bc9bad54228b4_Traceguids,
      (unsigned int)v24);
  SendMessageW(*v6, 0x1109u, 0, (LPARAM)*v20);
  v25 = CMMCViewDropTarget::ScRegisterAsDropTarget(this + 24, v32, *v6);
  mmcerror::SC::operator=(v31, v25);
  mmcerror::SC::~SC((mmcerror::SC *)v32);
  if ( !(unsigned __int8)mmcerror::SC::operator bool(v31) )
  {
    NodeManager = CAMCTreeView::CreateNodeManager((CAMCTreeView *)this);
    mmcerror::SC::operator=(v31, NodeManager);
    if ( !(unsigned __int8)mmcerror::SC::operator bool(v31) )
    {
      CAMCTreeView::OverrideWndProcForUiAutomation((CAMCTreeView *)this);
      v29 = &CBitmap::`vftable';
      CGdiObject::~CGdiObject((CGdiObject *)&v29);
      mmcerror::SC::~SC((mmcerror::SC *)v31);
      return 0;
    }
  }
  v29 = &CBitmap::`vftable';
  CGdiObject::~CGdiObject((CGdiObject *)&v29);
LABEL_50:
  mmcerror::SC::~SC((mmcerror::SC *)v31);
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x140024c60  mov     [rsp-28h+arg_0], rbx
0x140024c65  mov     [rsp-28h+arg_8], rsi
0x140024c6a  push    rbp
0x140024c6b  push    rdi
0x140024c6c  push    r12
0x140024c6e  push    r13
0x140024c70  push    r14
0x140024c72  mov     rbp, rsp
0x140024c75  sub     rsp, 80h
0x140024c7c  mov     rbx, rdx
0x140024c7f  mov     rsi, rcx
0x140024c82  xor     edx, edx
0x140024c84  lea     rcx, [rbp+var_38]
0x140024c88  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x140024c8e  nop
0x140024c8f  lea     rdx, aCamctreeviewOn_3; "CAMCTreeView::OnCreate"
0x140024c96  lea     rcx, [rbp+var_38]
0x140024c9a  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x140024ca0  lea     r12, WPP_GLOBAL_Control
0x140024ca7  lea     r13, WPP_6033b5b997f23f8d916bc9bad54228b4_Traceguids
0x140024cae  mov     rcx, cs:WPP_GLOBAL_Control
0x140024cb5  cmp     rcx, r12
0x140024cb8  jz      short loc_140024CD1
0x140024cba  cmp     byte ptr [rcx+19h], 5
0x140024cbe  jb      short loc_140024CD1
0x140024cc0  mov     edx, 1Bh
0x140024cc5  mov     r8, r13
0x140024cc8  mov     rcx, [rcx+10h]
0x140024ccc  call    WPP_SF_
0x140024cd1  mov     rdx, rbx
0x140024cd4  mov     rcx, rsi
0x140024cd7  call    cs:__imp_?OnCreate@CView@@IEAAHPEAUtagCREATESTRUCTW@@@Z; CView::OnCreate(tagCREATESTRUCTW *)
0x140024cdd  cmp     eax, 0FFFFFFFFh
0x140024ce0  jnz     short loc_140024D04
0x140024ce2  mov     rcx, cs:WPP_GLOBAL_Control
0x140024ce9  cmp     rcx, r12
0x140024cec  jz      loc_14002505A
0x140024cf2  cmp     byte ptr [rcx+19h], 2
0x140024cf6  jb      loc_14002505A
0x140024cfc  lea     edx, [rax+1Dh]
0x140024cff  jmp     loc_14002504D
0x140024d04  lea     r14, [rsi+40h]
0x140024d08  xor     r8d, r8d; pszSubIdList
0x140024d0b  lea     rdx, pszSubAppName; "Explorer"
0x140024d12  mov     rcx, [r14]; hwnd
0x140024d15  call    cs:__imp_SetWindowTheme
0x140024d1b  mov     rcx, rsi; struct CWnd *
0x140024d1e  call    ?GetAMCView@@YAPEAVCAMCView@@PEAVCWnd@@@Z; GetAMCView(CWnd *)
0x140024d23  mov     [rsi+148h], rax
0x140024d2a  test    rax, rax
0x140024d2d  jnz     short loc_140024D51
0x140024d2f  mov     rcx, cs:WPP_GLOBAL_Control
0x140024d36  cmp     rcx, r12
0x140024d39  jz      loc_14002505A
0x140024d3f  cmp     byte ptr [rcx+19h], 2
0x140024d43  jb      loc_14002505A
0x140024d49  lea     edx, [rax+1Dh]
0x140024d4c  jmp     loc_14002504D
0x140024d51  mov     r8, [rax+40h]
0x140024d55  mov     rdx, [rax+170h]
0x140024d5c  mov     rax, [rdx+8]
0x140024d60  mov     rcx, rdx
0x140024d63  cmp     byte ptr [rax+19h], 0
0x140024d67  jnz     short loc_140024D9C
0x140024d69  cmp     [rax+20h], r8
0x140024d6d  jnb     short loc_140024D75
0x140024d6f  mov     rax, [rax+10h]
0x140024d73  jmp     short loc_140024D7B
0x140024d75  mov     rcx, rax
0x140024d78  mov     rax, [rax]
0x140024d7b  cmp     byte ptr [rax+19h], 0
0x140024d7f  jz      short loc_140024D69
0x140024d81  cmp     rcx, rdx
0x140024d84  jz      short loc_140024D9C
0x140024d86  cmp     r8, [rcx+20h]
0x140024d8a  jb      short loc_140024D9C
0x140024d8c  mov     rcx, [rcx+30h]
0x140024d90  mov     rax, [rcx]
0x140024d93  mov     rax, [rax+8]
0x140024d97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024d9c  mov     [rbp+var_50], 0
0x140024da4  lea     rcx, [rbp+var_50]
0x140024da8  call    ?CreateInstance@?$CComObject@VEmbeddedWindowTreeProvider@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<EmbeddedWindowTreeProvider>::CreateInstance(ATL::CComObject<EmbeddedWindowTreeProvider> * *)
0x140024dad  mov     rdi, [rbp+var_50]
0x140024db1  mov     rax, [rdi]
0x140024db4  mov     rcx, rdi
0x140024db7  mov     rax, [rax+8]
0x140024dbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024dc0  mov     rax, [rdi]
0x140024dc3  mov     rcx, rdi
0x140024dc6  mov     rax, [rax+48h]
0x140024dca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024dcf  mov     rdx, r14
0x140024dd2  call    ??A?$map@PEAUHWND__@@UUiProviderContext@CAMCTreeView@@U?$less@PEAUHWND__@@@std@@V?$allocator@U?$pair@QEAUHWND__@@UUiProviderContext@CAMCTreeView@@@std@@@5@@std@@QEAAAEAUUiProviderContext@CAMCTreeView@@AEBQEAUHWND__@@@Z; std::map<HWND__ *,CAMCTreeView::UiProviderContext>::operator[](HWND__ * const &)
0x140024dd7  mov     rbx, rax
0x140024dda  mov     rdx, [r14]
0x140024ddd  mov     [rax], rdx
0x140024de0  mov     [rax+8], rdi
0x140024de4  mov     rdx, [rdi]
0x140024de7  mov     rcx, rdi
0x140024dea  mov     rax, [rdx+8]
0x140024dee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024df3  mov     rbx, [rbx+8]
0x140024df7  mov     rcx, [r14]; hWnd
0x140024dfa  mov     [rbx+48h], rcx
0x140024dfe  test    rcx, rcx
0x140024e01  jz      short loc_140024E11
0x140024e03  call    cs:__imp_IsWindow
0x140024e09  test    eax, eax
0x140024e0b  jz      short loc_140024E11
0x140024e0d  mov     cl, 1
0x140024e0f  jmp     short loc_140024E13
0x140024e11  xor     cl, cl
0x140024e13  mov     rax, [rbx+58h]
0x140024e17  mov     [rax], cl
0x140024e19  mov     rax, [rsi+148h]
0x140024e20  mov     rcx, [rax+80h]
0x140024e27  test    rcx, rcx
0x140024e2a  jz      loc_140025036
0x140024e30  mov     rcx, [rcx+200h]
0x140024e37  test    rcx, rcx
0x140024e3a  jz      loc_140025036
0x140024e40  lea     rdi, [rsi+188h]
0x140024e47  mov     rax, [rcx]
0x140024e4a  mov     rdx, rdi
0x140024e4d  mov     rax, [rax+58h]
0x140024e51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024e56  mov     [rbp+var_40], 0
0x140024e5e  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x140024e65  mov     [rbp+var_48], rax
0x140024e69  mov     [rsp+80h+fuLoad], 2000h; fuLoad
0x140024e71  mov     [rsp+80h+cy], 0; cy
0x140024e79  xor     r9d, r9d; cx
0x140024e7c  xor     r8d, r8d; type
0x140024e7f  mov     edx, 9Eh; name
0x140024e84  mov     rcx, cs:hInstance; hInst
0x140024e8b  call    cs:__imp_LoadImageW
0x140024e91  mov     rbx, rax
0x140024e94  test    rax, rax
0x140024e97  jnz     short loc_140024EE2
0x140024e99  call    cs:__imp_GetLastError
0x140024e9f  test    eax, eax
0x140024ea1  jle     short loc_140024EAD
0x140024ea3  movzx   eax, ax
0x140024ea6  or      eax, 80070000h
0x140024eab  test    eax, eax
0x140024ead  jns     short loc_140024EE2
0x140024eaf  mov     rcx, cs:WPP_GLOBAL_Control
0x140024eb6  cmp     rcx, r12
0x140024eb9  jz      short loc_140024F27
0x140024ebb  cmp     byte ptr [rcx+19h], 2
0x140024ebf  jb      short loc_140024F27
0x140024ec1  mov     edx, 0Ah
0x140024ec6  mov     [rsp+80h+cy], eax
0x140024eca  mov     r9d, 9Eh
0x140024ed0  lea     r8, WPP_799888a1cce93b9936bfd71a80878bc5_Traceguids
0x140024ed7  mov     rcx, [rcx+10h]
0x140024edb  call    WPP_SF_Dd
0x140024ee0  jmp     short loc_140024F27
0x140024ee2  mov     rdx, rbx
0x140024ee5  lea     rcx, [rbp+var_48]
0x140024ee9  call    cs:__imp_?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x140024eef  test    eax, eax
0x140024ef1  jnz     short loc_140024F27
0x140024ef3  mov     rcx, cs:WPP_GLOBAL_Control
0x140024efa  cmp     rcx, r12
0x140024efd  jz      short loc_140024F1E
0x140024eff  cmp     byte ptr [rcx+19h], 2
0x140024f03  jb      short loc_140024F1E
0x140024f05  lea     edx, [rax+0Bh]
0x140024f08  mov     r9d, 9Eh
0x140024f0e  lea     r8, WPP_799888a1cce93b9936bfd71a80878bc5_Traceguids
0x140024f15  mov     rcx, [rcx+10h]
0x140024f19  call    WPP_SF_d
0x140024f1e  mov     rcx, rbx; ho
0x140024f21  call    cs:__imp_DeleteObject
0x140024f27  xor     r8d, r8d
0x140024f2a  mov     rdx, [rbp+var_40]
0x140024f2e  mov     rcx, [rdi]
0x140024f31  call    IsolationAwareImageList_Add
0x140024f36  mov     [rbp+arg_18], 0
0x140024f3d  mov     [rbp+arg_10], 0
0x140024f44  lea     r9, [rbp+arg_10]
0x140024f48  lea     r8, [rbp+arg_18]
0x140024f4c  mov     edx, 10h
0x140024f51  mov     rcx, [rdi]
0x140024f54  call    cs:__imp_?LoadStandardOverlays@@YAJPEAU_IMAGELIST@@HPEAH1@Z; LoadStandardOverlays(_IMAGELIST *,int,int *,int *)
0x140024f5a  test    eax, eax
0x140024f5c  jns     short loc_140024F84
0x140024f5e  mov     rcx, cs:WPP_GLOBAL_Control
0x140024f65  cmp     rcx, r12
0x140024f68  jz      short loc_140024F84
0x140024f6a  cmp     byte ptr [rcx+19h], 1
0x140024f6e  jb      short loc_140024F84
0x140024f70  mov     edx, 1Fh
0x140024f75  mov     r9d, eax
0x140024f78  mov     r8, r13
0x140024f7b  mov     rcx, [rcx+10h]
0x140024f7f  call    WPP_SF_d
0x140024f84  mov     r9, [rdi]; lParam
0x140024f87  xor     r8d, r8d; wParam
0x140024f8a  mov     edx, 1109h; Msg
0x140024f8f  mov     rcx, [r14]; hWnd
0x140024f92  call    cs:__imp_SendMessageW
0x140024f98  lea     rcx, [rsi+0C0h]
0x140024f9f  mov     r8, [r14]
0x140024fa2  lea     rdx, [rbp+var_20]
0x140024fa6  call    ?ScRegisterAsDropTarget@CMMCViewDropTarget@@IEAA?AVSC@mmcerror@@PEAUHWND__@@@Z; CMMCViewDropTarget::ScRegisterAsDropTarget(HWND__ *)
0x140024fab  nop
0x140024fac  mov     rdx, rax
0x140024faf  lea     rcx, [rbp+var_38]
0x140024fb3  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x140024fb9  nop
0x140024fba  lea     rcx, [rbp+var_20]
0x140024fbe  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x140024fc4  lea     rcx, [rbp+var_38]
0x140024fc8  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x140024fce  test    al, al
0x140024fd0  jnz     short loc_140025020
0x140024fd2  mov     rcx, rsi; this
0x140024fd5  call    ?CreateNodeManager@CAMCTreeView@@IEAAJXZ; CAMCTreeView::CreateNodeManager(void)
0x140024fda  mov     edx, eax
0x140024fdc  lea     rcx, [rbp+var_38]
0x140024fe0  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x140024fe6  lea     rcx, [rbp+var_38]
0x140024fea  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x140024ff0  test    al, al
0x140024ff2  jnz     short loc_140025020
0x140024ff4  mov     rcx, rsi; this
0x140024ff7  call    ?OverrideWndProcForUiAutomation@CAMCTreeView@@IEAAXXZ; CAMCTreeView::OverrideWndProcForUiAutomation(void)
0x140024ffc  nop
0x140024ffd  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x140025004  mov     [rbp+var_48], rax
0x140025008  lea     rcx, [rbp+var_48]; this
0x14002500c  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x140025011  nop
0x140025012  lea     rcx, [rbp+var_38]
0x140025016  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x14002501c  xor     eax, eax
0x14002501e  jmp     short loc_140025067
0x140025020  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x140025027  mov     [rbp+var_48], rax
0x14002502b  lea     rcx, [rbp+var_48]; this
0x14002502f  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x140025034  jmp     short loc_14002505A
0x140025036  mov     rcx, cs:WPP_GLOBAL_Control
0x14002503d  cmp     rcx, r12
0x140025040  jz      short loc_14002505A
0x140025042  cmp     byte ptr [rcx+19h], 2
0x140025046  jb      short loc_14002505A
0x140025048  mov     edx, 1Eh
0x14002504d  mov     r8, r13
0x140025050  mov     rcx, [rcx+10h]
0x140025054  call    WPP_SF_
0x140025059  nop
0x14002505a  lea     rcx, [rbp+var_38]
0x14002505e  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x140025064  or      eax, 0FFFFFFFFh
0x140025067  lea     r11, [rsp+80h+var_s0]
0x14002506f  mov     rbx, [r11+30h]
0x140025073  mov     rsi, [r11+38h]
0x140025077  mov     rsp, r11
0x14002507a  pop     r14
0x14002507c  pop     r13
0x14002507e  pop     r12
0x140025080  pop     rdi
0x140025081  pop     rbp
0x140025082  retn
```
