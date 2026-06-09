# CNovSetDlg::OnInitDialog(uint,unsigned __int64,__int64,int &)

- ea: `0x14002d3f4`
- end: `0x14002d67c`
- name: `?OnInitDialog@CNovSetDlg@@QEAA_JI_K_JAEAH@Z`
- size: `648`
- prototype: `__int64 __usercall@<rax>(CNovSetDlg *__hidden this@<rcx>, unsigned int@<edx>, unsigned __int64@<r8>, __int64@<r9>, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140023d70`

## callees

- `0x140002463`
- `0x14001b1fc`
- `0x140025ecc`
- `0x14002d3f4`
- `0x14002d980`
- `0x14002df5c`
- `0x14004ad80`

## import_xrefs

- `GDI32!GetTextMetricsW` at `0x14002d592`
- `GDI32!GetTextMetricsW` at `0x14002d592`
- `GDI32!CreateFontIndirectW` at `0x14002d62b`
- `GDI32!CreateFontIndirectW` at `0x14002d62b`
- `GDI32!GetObjectW` at `0x14002d614`
- `GDI32!GetObjectW` at `0x14002d614`
- `USER32!SendMessageW` at `0x14002d482`
- `USER32!SendMessageW` at `0x14002d4fe`
- `USER32!SendMessageW` at `0x14002d518`
- `USER32!SendMessageW` at `0x14002d5e5`
- `USER32!SendMessageW` at `0x14002d649`
- `USER32!SendMessageW` at `0x14002d482`
- `USER32!SendMessageW` at `0x14002d4fe`
- `USER32!SendMessageW` at `0x14002d518`
- `USER32!SendMessageW` at `0x14002d5e5`
- `USER32!SendMessageW` at `0x14002d649`
- `USER32!GetDlgItem` at `0x14002d42c`
- `USER32!GetDlgItem` at `0x14002d5c8`
- `USER32!GetDlgItem` at `0x14002d42c`
- `USER32!GetDlgItem` at `0x14002d5c8`
- `USER32!ReleaseDC` at `0x14002d5b3`
- `USER32!ReleaseDC` at `0x14002d5b3`
- `USER32!GetDC` at `0x14002d566`
- `USER32!GetDC` at `0x14002d566`
- `USER32!SetWindowPos` at `0x14002d4dc`
- `USER32!SetWindowPos` at `0x14002d4dc`
- `USER32!GetParent` at `0x14002d495`
- `USER32!GetParent` at `0x14002d495`
- `USER32!GetClientRect` at `0x14002d54c`
- `USER32!GetClientRect` at `0x14002d54c`

## pseudocode

```c
__int64 __fastcall CNovSetDlg::OnInitDialog(HWND *this, __int64 a2, __int64 a3, __int64 a4, int *a5)
{
  HWND DlgItem; // rax
  HWND v7; // rdx
  HWND v8; // rsi
  CEventLogger *v9; // r9
  HWND v10; // rbx
  HWND Parent; // rax
  __int64 v12; // rdx
  HWND v13; // rcx
  HWND v14; // rcx
  HDC DC; // rbx
  HWND v16; // rcx
  HWND v17; // rsi
  void *v18; // rbx
  HFONT v19; // rax
  int X[4]; // [rsp+40h] [rbp-C0h] BYREF
  struct tagRECT Rect; // [rsp+50h] [rbp-B0h] BYREF
  tagTEXTMETRICW tm; // [rsp+60h] [rbp-A0h] BYREF
  LOGFONTW pv; // [rsp+A0h] [rbp-60h] BYREF

  DlgItem = GetDlgItem(this[1], 1046);
  v7 = this[1];
  v8 = DlgItem;
  *(_OWORD *)X = 0;
  *((_QWORD *)_AtlModule + 123) = v7;
  ATL::CDialogImplBaseT<ATL::CWindow>::ExecuteDlgInit(this, 2003);
  v9 = _AtlModule;
  *a5 = 0;
  SendMessageW(this[1], 0x80u, 0, *((_QWORD *)v9 + 75));
  v10 = this[1];
  Parent = GetParent(v10);
  CenterRectangle(Parent, v10, (struct tagRECT *)X);
  SetWindowPos(this[1], 0, X[0], X[1], 0, 0, 1u);
  if ( v8 )
  {
    SendMessageW(v8, 0x406u, 1u, 196608);
    SendMessageW(v8, 0x414u, 1u, 0);
  }
  CNovSetDlg::SetDialogToMatchSettings((CNovSetDlg *)this);
  CNovSetDlg::OnVScroll((CNovSetDlg *)this, v12, 5, 0);
  v13 = this[1];
  Rect = 0;
  GetClientRect(v13, &Rect);
  v14 = this[1];
  dword_140064230 = Rect.bottom;
  DC = GetDC(v14);
  memset(&tm, 0, sizeof(tm));
  GetTextMetricsW(DC, &tm);
  v16 = this[1];
  dword_140064234 = tm.tmHeight + tm.tmExternalLeading;
  ReleaseDC(v16, DC);
  v17 = GetDlgItem(this[1], 1048);
  v18 = (void *)SendMessageW(this[1], 0x31u, 0, 0);
  if ( v18 )
  {
    memset_0(&pv, 0, sizeof(pv));
    GetObjectW(v18, 92, &pv);
    pv.lfWeight = 700;
    v19 = CreateFontIndirectW(&pv);
    this[12] = (HWND)v19;
    SendMessageW(v17, 0x30u, (WPARAM)v19, 1);
  }
  return 0;
}

```

## disassembly

```asm
0x14002d3f4  mov     [rsp-8+arg_8], rbx
0x14002d3f9  mov     [rsp-8+arg_10], rsi
0x14002d3fe  push    rbp
0x14002d3ff  push    rdi
0x14002d400  push    r15
0x14002d402  lea     rbp, [rsp-10h]
0x14002d407  sub     rsp, 110h
0x14002d40e  mov     rax, cs:__security_cookie
0x14002d415  xor     rax, rsp
0x14002d418  mov     [rbp+20h+var_20], rax
0x14002d41c  mov     rbx, [rbp+20h+arg_20]
0x14002d420  mov     rdi, rcx
0x14002d423  mov     rcx, [rcx+8]; hDlg
0x14002d427  mov     edx, 416h; nIDDlgItem
0x14002d42c  call    cs:__imp_GetDlgItem
0x14002d433  nop     dword ptr [rax+rax+00h]
0x14002d438  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002d43f  xorps   xmm0, xmm0
0x14002d442  mov     rdx, [rdi+8]
0x14002d446  mov     rsi, rax
0x14002d449  movups  xmmword ptr [rsp+120h+X], xmm0
0x14002d44e  mov     [rcx+3D8h], rdx
0x14002d455  mov     edx, 7D3h
0x14002d45a  mov     rcx, rdi
0x14002d45d  call    ?ExecuteDlgInit@?$CDialogImplBaseT@VCWindow@ATL@@@ATL@@QEAAHH@Z; ATL::CDialogImplBaseT<ATL::CWindow>::ExecuteDlgInit(int)
0x14002d462  mov     r9, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002d469  xor     r8d, r8d; wParam
0x14002d46c  mov     dword ptr [rbx], 0
0x14002d472  mov     edx, 80h; Msg
0x14002d477  mov     rcx, [rdi+8]; hWnd
0x14002d47b  mov     r9, [r9+258h]; lParam
0x14002d482  call    cs:__imp_SendMessageW
0x14002d489  nop     dword ptr [rax+rax+00h]
0x14002d48e  mov     rbx, [rdi+8]
0x14002d492  mov     rcx, rbx; hWnd
0x14002d495  call    cs:__imp_GetParent
0x14002d49c  nop     dword ptr [rax+rax+00h]
0x14002d4a1  lea     r8, [rsp+120h+X]; struct tagRECT *
0x14002d4a6  mov     rdx, rbx; HWND
0x14002d4a9  mov     rcx, rax; hWnd
0x14002d4ac  call    ?CenterRectangle@@YAXPEAUHWND__@@0PEAUtagRECT@@@Z; CenterRectangle(HWND__ *,HWND__ *,tagRECT *)
0x14002d4b1  mov     r9d, [rsp+120h+X+4]; Y
0x14002d4b6  mov     r15d, 1
0x14002d4bc  mov     r8d, [rsp+120h+X]; X
0x14002d4c1  xor     edx, edx; hWndInsertAfter
0x14002d4c3  mov     rcx, [rdi+8]; hWnd
0x14002d4c7  mov     [rsp+120h+uFlags], r15d; uFlags
0x14002d4cc  mov     [rsp+120h+cy], 0; cy
0x14002d4d4  mov     dword ptr [rsp+120h+var_100], 0; int *
0x14002d4dc  call    cs:__imp_SetWindowPos
0x14002d4e3  nop     dword ptr [rax+rax+00h]
0x14002d4e8  test    rsi, rsi
0x14002d4eb  jz      short loc_14002D524
0x14002d4ed  mov     r9d, 30000h; lParam
0x14002d4f3  mov     r8d, r15d; wParam
0x14002d4f6  mov     edx, 406h; Msg
0x14002d4fb  mov     rcx, rsi; hWnd
0x14002d4fe  call    cs:__imp_SendMessageW
0x14002d505  nop     dword ptr [rax+rax+00h]
0x14002d50a  xor     r9d, r9d; lParam
0x14002d50d  mov     r8d, r15d; wParam
0x14002d510  mov     edx, 414h; Msg
0x14002d515  mov     rcx, rsi; hWnd
0x14002d518  call    cs:__imp_SendMessageW
0x14002d51f  nop     dword ptr [rax+rax+00h]
0x14002d524  mov     rcx, rdi; this
0x14002d527  call    ?SetDialogToMatchSettings@CNovSetDlg@@AEAAXXZ; CNovSetDlg::SetDialogToMatchSettings(void)
0x14002d52c  xor     r9d, r9d; __int64
0x14002d52f  mov     rcx, rdi; this
0x14002d532  lea     r8d, [r9+5]; unsigned __int64
0x14002d536  call    ?OnVScroll@CNovSetDlg@@QEAA_JI_K_JAEAH@Z; CNovSetDlg::OnVScroll(uint,unsigned __int64,__int64,int &)
0x14002d53b  mov     rcx, [rdi+8]; hWnd
0x14002d53f  lea     rdx, [rsp+120h+Rect]; lpRect
0x14002d544  xorps   xmm0, xmm0
0x14002d547  movups  xmmword ptr [rsp+120h+Rect.left], xmm0
0x14002d54c  call    cs:__imp_GetClientRect
0x14002d553  nop     dword ptr [rax+rax+00h]
0x14002d558  mov     eax, [rsp+120h+Rect.bottom]
0x14002d55c  mov     rcx, [rdi+8]; hWnd
0x14002d560  mov     cs:dword_140064230, eax
0x14002d566  call    cs:__imp_GetDC
0x14002d56d  nop     dword ptr [rax+rax+00h]
0x14002d572  xorps   xmm0, xmm0
0x14002d575  lea     rdx, [rsp+120h+tm]; lptm
0x14002d57a  movups  xmmword ptr [rbp+20h+tm.tmOverhang], xmm0
0x14002d57e  mov     rcx, rax; hdc
0x14002d581  mov     rbx, rax
0x14002d584  movups  xmmword ptr [rbp+20h+tm.tmFirstChar], xmm0
0x14002d588  movups  xmmword ptr [rsp+120h+tm.tmHeight], xmm0
0x14002d58d  movups  xmmword ptr [rsp+120h+tm.tmExternalLeading], xmm0
0x14002d592  call    cs:__imp_GetTextMetricsW
0x14002d599  nop     dword ptr [rax+rax+00h]
0x14002d59e  mov     edx, [rsp+120h+tm.tmExternalLeading]
0x14002d5a2  add     edx, [rsp+120h+tm.tmHeight]
0x14002d5a6  mov     rcx, [rdi+8]; hWnd
0x14002d5aa  mov     cs:dword_140064234, edx
0x14002d5b0  mov     rdx, rbx; hDC
0x14002d5b3  call    cs:__imp_ReleaseDC
0x14002d5ba  nop     dword ptr [rax+rax+00h]
0x14002d5bf  mov     rcx, [rdi+8]; hDlg
0x14002d5c3  mov     edx, 418h; nIDDlgItem
0x14002d5c8  call    cs:__imp_GetDlgItem
0x14002d5cf  nop     dword ptr [rax+rax+00h]
0x14002d5d4  mov     rcx, [rdi+8]; hWnd
0x14002d5d8  xor     r9d, r9d; lParam
0x14002d5db  xor     r8d, r8d; wParam
0x14002d5de  mov     rsi, rax
0x14002d5e1  lea     edx, [r9+31h]; Msg
0x14002d5e5  call    cs:__imp_SendMessageW
0x14002d5ec  nop     dword ptr [rax+rax+00h]
0x14002d5f1  mov     rbx, rax
0x14002d5f4  test    rax, rax
0x14002d5f7  jz      short loc_14002D655
0x14002d5f9  xor     edx, edx; Val
0x14002d5fb  lea     rcx, [rbp+20h+pv]; void *
0x14002d5ff  lea     r8d, [rdx+5Ch]; Size
0x14002d603  call    memset_0
0x14002d608  lea     r8, [rbp+20h+pv]; pv
0x14002d60c  mov     edx, 5Ch ; '\'; c
0x14002d611  mov     rcx, rbx; h
0x14002d614  call    cs:__imp_GetObjectW
0x14002d61b  nop     dword ptr [rax+rax+00h]
0x14002d620  lea     rcx, [rbp+20h+pv]; lplf
0x14002d624  mov     [rbp+20h+var_70], 2BCh
0x14002d62b  call    cs:__imp_CreateFontIndirectW
0x14002d632  nop     dword ptr [rax+rax+00h]
0x14002d637  mov     r9, r15; lParam
0x14002d63a  mov     edx, 30h ; '0'; Msg
0x14002d63f  mov     r8, rax; wParam
0x14002d642  mov     [rdi+60h], rax
0x14002d646  mov     rcx, rsi; hWnd
0x14002d649  call    cs:__imp_SendMessageW
0x14002d650  nop     dword ptr [rax+rax+00h]
0x14002d655  xor     eax, eax
0x14002d657  mov     rcx, [rbp+20h+var_20]
0x14002d65b  xor     rcx, rsp; StackCookie
0x14002d65e  call    __security_check_cookie
0x14002d663  lea     r11, [rsp+120h+var_10]
0x14002d66b  mov     rbx, [r11+28h]
0x14002d66f  mov     rsi, [r11+30h]
0x14002d673  mov     rsp, r11
0x14002d676  pop     r15
0x14002d678  pop     rdi
0x14002d679  pop     rbp
0x14002d67a  retn
```
