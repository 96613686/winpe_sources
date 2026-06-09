# CAMCListView::OnPaint(void)

- ea: `0x14003ac80`
- end: `0x14003adee`
- name: `?OnPaint@CAMCListView@@IEAAXXZ`
- size: `366`
- prototype: `void __fastcall(CAMCListView *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1400253a4`
- `0x140025400`
- `0x14002f838`
- `0x14003ac80`
- `0x14005a420`
- `0x140062455`
- `0x1400e9e10`

## import_xrefs

- `USER32!GetClientRect` at `0x14003acc0`
- `USER32!GetClientRect` at `0x14003acc0`
- `USER32!SendMessageW` at `0x14003acf5`
- `USER32!SendMessageW` at `0x14003ad6a`
- `USER32!SendMessageW` at `0x14003acf5`
- `USER32!SendMessageW` at `0x14003ad6a`
- `USER32!SystemParametersInfoW` at `0x14003ad3e`
- `USER32!SystemParametersInfoW` at `0x14003ad3e`
- `MFC42u!__imp_?Default@CWnd@@IEAA_JXZ` at `0x14003aca2`
- `MFC42u!__imp_?Default@CWnd@@IEAA_JXZ` at `0x14003aca2`
- `MFC42u!__imp_?GetStyle@CWnd@@QEBAKXZ` at `0x14003acd9`
- `MFC42u!__imp_?GetStyle@CWnd@@QEBAKXZ` at `0x14003acd9`
- `MFC42u!__imp_?MoveWindow@CWnd@@QEAAXHHHHH@Z` at `0x14003ad93`
- `MFC42u!__imp_?MoveWindow@CWnd@@QEAAXHHHHH@Z` at `0x14003ad93`
- `MFC42u!__imp_?SetWindowTextW@CWnd@@QEAAXPEBG@Z` at `0x14003ada3`
- `MFC42u!__imp_?SetWindowTextW@CWnd@@QEAAXPEBG@Z` at `0x14003ada3`
- `MFC42u!__imp_?ShowWindow@CWnd@@QEAAHH@Z` at `0x14003adb1`
- `MFC42u!__imp_?ShowWindow@CWnd@@QEAAHH@Z` at `0x14003add0`
- `MFC42u!__imp_?ShowWindow@CWnd@@QEAAHH@Z` at `0x14003adb1`
- `MFC42u!__imp_?ShowWindow@CWnd@@QEAAHH@Z` at `0x14003add0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CAMCListView::OnPaint(CAMCListView *this)
{
  struct CAMCHeaderCtrl *HeaderCtrl; // rbx
  LONG top; // eax
  void **v4; // [rsp+30h] [rbp-69h] BYREF
  WPARAM wParam; // [rsp+38h] [rbp-61h]
  struct tagRECT Rect; // [rsp+40h] [rbp-59h] BYREF
  LPARAM lParam; // [rsp+50h] [rbp-49h] BYREF
  int v8; // [rsp+5Ch] [rbp-3Dh]
  struct tagLOGFONTW pvParam; // [rsp+60h] [rbp-39h] BYREF

  CWnd::Default(this);
  if ( CAMCListView::NeedsCustomPaint(this) )
  {
    GetClientRect(*((HWND *)this + 8), &Rect);
    HeaderCtrl = CAMCListView::GetHeaderCtrl(this);
    if ( HeaderCtrl && (CWnd::GetStyle(this) & 3) == 1 )
    {
      SendMessageW(*((HWND *)HeaderCtrl + 8), 0x1207u, 0, (LPARAM)&lParam);
      top = v8 + Rect.top;
    }
    else
    {
      top = Rect.top;
    }
    Rect.top = top + 10;
    memset_0(&pvParam, 0, sizeof(pvParam));
    wParam = 0;
    v4 = &CFont::`vftable';
    SystemParametersInfoW(0x1Fu, 0x5Cu, &pvParam, 0);
    CFont::CreateFontIndirectW((CFont *)&v4, &pvParam);
    SendMessageW(*((HWND *)this + 71), 0x30u, wParam, 1);
    CWnd::MoveWindow(
      (CAMCListView *)((char *)this + 504),
      Rect.left,
      Rect.top,
      Rect.right - Rect.left,
      Rect.bottom - Rect.top,
      1);
    CWnd::SetWindowTextW((CAMCListView *)((char *)this + 504), *((const unsigned __int16 **)this + 34));
    CWnd::ShowWindow((CAMCListView *)((char *)this + 504), 5);
    v4 = &CFont::`vftable';
    CGdiObject::~CGdiObject((CGdiObject *)&v4);
  }
  else
  {
    CWnd::ShowWindow((CAMCListView *)((char *)this + 504), 0);
  }
}

```

## disassembly

```asm
0x14003ac80  push    rbp
0x14003ac82  push    rbx
0x14003ac83  push    rsi
0x14003ac84  push    rdi
0x14003ac85  lea     rbp, [rsp-3Fh]
0x14003ac8a  sub     rsp, 0D8h
0x14003ac91  mov     rax, cs:__security_cookie
0x14003ac98  xor     rax, rsp
0x14003ac9b  mov     [rbp+57h+var_30], rax
0x14003ac9f  mov     rdi, rcx
0x14003aca2  call    cs:__imp_?Default@CWnd@@IEAA_JXZ; CWnd::Default(void)
0x14003aca8  mov     rcx, rdi; this
0x14003acab  call    ?NeedsCustomPaint@CAMCListView@@AEAA_NXZ; CAMCListView::NeedsCustomPaint(void)
0x14003acb0  test    al, al
0x14003acb2  jz      loc_14003ADC7
0x14003acb8  lea     rdx, [rbp+57h+Rect]; lpRect
0x14003acbc  mov     rcx, [rdi+40h]; hWnd
0x14003acc0  call    cs:__imp_GetClientRect
0x14003acc6  mov     rcx, rdi; this
0x14003acc9  call    ?GetHeaderCtrl@CAMCListView@@QEBAPEAVCAMCHeaderCtrl@@XZ; CAMCListView::GetHeaderCtrl(void)
0x14003acce  mov     rbx, rax
0x14003acd1  test    rax, rax
0x14003acd4  jz      short loc_14003AD03
0x14003acd6  mov     rcx, rdi
0x14003acd9  call    cs:__imp_?GetStyle@CWnd@@QEBAKXZ; CWnd::GetStyle(void)
0x14003acdf  and     al, 3
0x14003ace1  cmp     al, 1
0x14003ace3  jnz     short loc_14003AD03
0x14003ace5  lea     r9, [rbp+57h+lParam]; lParam
0x14003ace9  xor     r8d, r8d; wParam
0x14003acec  mov     edx, 1207h; Msg
0x14003acf1  mov     rcx, [rbx+40h]; hWnd
0x14003acf5  call    cs:__imp_SendMessageW
0x14003acfb  mov     eax, [rbp+57h+Rect.top]
0x14003acfe  add     eax, [rbp+57h+var_94]
0x14003ad01  jmp     short loc_14003AD06
0x14003ad03  mov     eax, [rbp+57h+Rect.top]
0x14003ad06  add     eax, 0Ah
0x14003ad09  mov     [rbp+57h+Rect.top], eax
0x14003ad0c  mov     ebx, 5Ch ; '\'
0x14003ad11  mov     r8d, ebx; Size
0x14003ad14  xor     edx, edx; Val
0x14003ad16  lea     rcx, [rbp+57h+pvParam]; void *
0x14003ad1a  call    memset_0
0x14003ad1f  mov     [rbp+57h+wParam], 0
0x14003ad27  lea     rsi, ??_7CFont@@6B@; const CFont::`vftable'
0x14003ad2e  mov     [rbp+57h+var_C0], rsi
0x14003ad32  xor     r9d, r9d; fWinIni
0x14003ad35  lea     r8, [rbp+57h+pvParam]; pvParam
0x14003ad39  mov     edx, ebx; uiParam
0x14003ad3b  lea     ecx, [rbx-3Dh]; uiAction
0x14003ad3e  call    cs:__imp_SystemParametersInfoW
0x14003ad44  lea     rdx, [rbp+57h+pvParam]; struct tagLOGFONTW *
0x14003ad48  lea     rcx, [rbp+57h+var_C0]; this
0x14003ad4c  call    ?CreateFontIndirectW@CFont@@QEAAHPEBUtagLOGFONTW@@@Z; CFont::CreateFontIndirectW(tagLOGFONTW const *)
0x14003ad51  lea     rbx, [rdi+1F8h]
0x14003ad58  mov     r9d, 1; lParam
0x14003ad5e  mov     r8, [rbp+57h+wParam]; wParam
0x14003ad62  lea     edx, [r9+2Fh]; Msg
0x14003ad66  mov     rcx, [rbx+40h]; hWnd
0x14003ad6a  call    cs:__imp_SendMessageW
0x14003ad70  mov     eax, [rbp+57h+Rect.bottom]
0x14003ad73  mov     r8d, [rbp+57h+Rect.top]
0x14003ad77  sub     eax, r8d
0x14003ad7a  mov     r9d, [rbp+57h+Rect.right]
0x14003ad7e  mov     edx, [rbp+57h+Rect.left]
0x14003ad81  sub     r9d, edx
0x14003ad84  mov     [rsp+0F0h+var_C8], 1
0x14003ad8c  mov     [rsp+0F0h+var_D0], eax
0x14003ad90  mov     rcx, rbx
0x14003ad93  call    cs:__imp_?MoveWindow@CWnd@@QEAAXHHHHH@Z; CWnd::MoveWindow(int,int,int,int,int)
0x14003ad99  mov     rdx, [rdi+110h]
0x14003ada0  mov     rcx, rbx
0x14003ada3  call    cs:__imp_?SetWindowTextW@CWnd@@QEAAXPEBG@Z; CWnd::SetWindowTextW(ushort const *)
0x14003ada9  mov     edx, 5
0x14003adae  mov     rcx, rbx
0x14003adb1  call    cs:__imp_?ShowWindow@CWnd@@QEAAHH@Z; CWnd::ShowWindow(int)
0x14003adb7  nop
0x14003adb8  mov     [rbp+57h+var_C0], rsi
0x14003adbc  lea     rcx, [rbp+57h+var_C0]; this
0x14003adc0  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x14003adc5  jmp     short loc_14003ADD6
0x14003adc7  lea     rcx, [rdi+1F8h]
0x14003adce  xor     edx, edx
0x14003add0  call    cs:__imp_?ShowWindow@CWnd@@QEAAHH@Z; CWnd::ShowWindow(int)
0x14003add6  mov     rcx, [rbp+57h+var_30]
0x14003adda  xor     rcx, rsp; StackCookie
0x14003addd  call    __security_check_cookie
0x14003ade2  add     rsp, 0D8h
0x14003ade9  pop     rdi
0x14003adea  pop     rsi
0x14003adeb  pop     rbx
0x14003adec  pop     rbp
0x14003aded  retn
```
