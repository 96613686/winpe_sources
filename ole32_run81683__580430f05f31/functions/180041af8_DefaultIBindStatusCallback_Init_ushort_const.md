# DefaultIBindStatusCallback::Init(ushort const *)

- ea: `0x180041af8`
- end: `0x180041c1a`
- name: `?Init@DefaultIBindStatusCallback@@QEAAHPEBG@Z`
- size: `290`
- prototype: `int __fastcall(DefaultIBindStatusCallback *this, const wchar_t *pszTitle)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180030c90`

## callees

- `0x1800362b8`
- `0x180041af8`
- `0x180052390`

## import_xrefs

- `USER32!CreateDialogParamW` at `0x180041b4f`
- `USER32!CreateDialogParamW` at `0x180041b4f`
- `USER32!MoveWindow` at `0x180041bed`
- `USER32!MoveWindow` at `0x180041bed`
- `USER32!GetDesktopWindow` at `0x180041b98`
- `USER32!GetDesktopWindow` at `0x180041b98`
- `USER32!GetClientRect` at `0x180041ba5`
- `USER32!GetClientRect` at `0x180041ba5`
- `USER32!GetWindowRect` at `0x180041b89`
- `USER32!GetWindowRect` at `0x180041b89`
- `USER32!SetWindowTextW` at `0x180041b6d`
- `USER32!SetWindowTextW` at `0x180041b6d`

## pseudocode

```c
int __fastcall DefaultIBindStatusCallback::Init(DefaultIBindStatusCallback *this, const wchar_t *pszTitle)
{
  int result; // eax
  HINSTANCE v5; // rcx
  HWND__ *m_hwndParent; // r8
  HWND__ *DialogParamW; // rax
  HWND__ *m_hDlg; // rcx
  HWND__ *DesktopWindow; // rcx
  tagRECT rectParent; // [rsp+30h] [rbp-30h] BYREF
  tagRECT rectDLG; // [rsp+40h] [rbp-20h] BYREF

  result = CallInitCommonControls();
  if ( result )
  {
    v5 = g_hinst;
    m_hwndParent = this->m_hwndParent;
    this->m_hInstance = g_hinst;
    DialogParamW = CreateDialogParamW(v5, (LPCWSTR)0x65, m_hwndParent, DialogProc, (LPARAM)&this->CHlprDialog);
    this->m_hDlg = DialogParamW;
    if ( DialogParamW )
    {
      if ( pszTitle )
        SetWindowTextW(DialogParamW, pszTitle);
      m_hDlg = this->m_hDlg;
      rectDLG = 0;
      rectParent = 0;
      GetWindowRect(m_hDlg, &rectDLG);
      DesktopWindow = this->m_hwndParent;
      if ( !DesktopWindow )
        DesktopWindow = GetDesktopWindow();
      GetClientRect(DesktopWindow, &rectParent);
      MoveWindow(
        this->m_hDlg,
        (rectParent.right - (rectDLG.right - rectDLG.left) - rectParent.left) / 2,
        (rectParent.bottom - (rectDLG.bottom - rectDLG.top) - rectParent.top) / 2,
        rectDLG.right - rectDLG.left,
        rectDLG.bottom - rectDLG.top,
        0);
    }
    return this->m_hDlg != 0;
  }
  return result;
}

```

## disassembly

```asm
0x180041af8  mov     [rsp-8+arg_10], rbx
0x180041afd  mov     [rsp-8+arg_18], rdi
0x180041b02  push    rbp
0x180041b03  mov     rbp, rsp
0x180041b06  sub     rsp, 60h
0x180041b0a  mov     rax, cs:__security_cookie
0x180041b11  xor     rax, rsp
0x180041b14  mov     [rbp+var_10], rax
0x180041b18  mov     rdi, pszTitle
0x180041b1b  mov     rbx, this
0x180041b1e  call    ?CallInitCommonControls@@YAHXZ; CallInitCommonControls(void)
0x180041b23  test    eax, eax
0x180041b25  jz      loc_180041BFC
0x180041b2b  mov     this, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInstance
0x180041b32  lea     rax, [rbx+10h]
0x180041b36  mov     r8, [rbx+38h]; hWndParent
0x180041b3a  lea     r9, DialogProc; lpDialogFunc
0x180041b41  mov     edx, 65h ; 'e'; lpTemplateName
0x180041b46  mov     [rax+8], this
0x180041b4a  mov     [rsp+60h+dwInitParam], rax; dwInitParam
0x180041b4f  call    cs:__imp_CreateDialogParamW
0x180041b55  mov     [rbx+40h], rax
0x180041b59  test    rax, rax
0x180041b5c  jz      loc_180041BF3
0x180041b62  test    rdi, rdi
0x180041b65  jz      short loc_180041B73
0x180041b67  mov     pszTitle, rdi; lpString
0x180041b6a  mov     this, rax; hWnd
0x180041b6d  call    cs:__imp_SetWindowTextW
0x180041b73  mov     this, [rbx+40h]; hWnd
0x180041b77  lea     pszTitle, [rbp+rectDLG]; lpRect
0x180041b7b  xorps   xmm0, xmm0
0x180041b7e  xorps   xmm1, xmm1
0x180041b81  movups  xmmword ptr [rbp+rectDLG.left], xmm0
0x180041b85  movups  xmmword ptr [rbp+rectParent.left], xmm1
0x180041b89  call    cs:__imp_GetWindowRect
0x180041b8f  mov     this, [rbx+38h]
0x180041b93  test    this, this
0x180041b96  jnz     short loc_180041BA1
0x180041b98  call    cs:__imp_GetDesktopWindow
0x180041b9e  mov     this, rax; hWnd
0x180041ba1  lea     pszTitle, [rbp+rectParent]; lpRect
0x180041ba5  call    cs:__imp_GetClientRect
0x180041bab  mov     ecx, [rbp+rectDLG.bottom]
0x180041bae  mov     r10d, 2
0x180041bb4  sub     ecx, [rbp+rectDLG.top]
0x180041bb7  mov     eax, [rbp+rectParent.bottom]
0x180041bba  mov     r9d, [rbp+rectDLG.right]
0x180041bbe  sub     eax, ecx
0x180041bc0  sub     eax, [rbp+rectParent.top]
0x180041bc3  sub     r9d, [rbp+rectDLG.left]; nWidth
0x180041bc7  cdq
0x180041bc8  idiv    r10d
0x180041bcb  mov     [rsp+60h+bRepaint], 0; bRepaint
0x180041bd3  mov     r8d, eax; Y
0x180041bd6  mov     dword ptr [rsp+60h+dwInitParam], ecx; nHeight
0x180041bda  mov     eax, [rbp+rectParent.right]
0x180041bdd  mov     this, [rbx+40h]; hWnd
0x180041be1  sub     eax, r9d
0x180041be4  sub     eax, [rbp+rectParent.left]
0x180041be7  cdq
0x180041be8  idiv    r10d
0x180041beb  mov     edx, eax; X
0x180041bed  call    cs:__imp_MoveWindow
0x180041bf3  xor     eax, eax
0x180041bf5  cmp     [rbx+40h], rax
0x180041bf9  setnz   al
0x180041bfc  mov     this, [rbp+var_10]
0x180041c00  xor     this, rsp; StackCookie
0x180041c03  call    __security_check_cookie
0x180041c08  lea     r11, [rsp+60h+var_s0]
0x180041c0d  mov     rbx, [r11+20h]
0x180041c11  mov     rdi, [r11+28h]
0x180041c15  mov     rsp, r11
0x180041c18  pop     rbp
0x180041c19  retn
```
