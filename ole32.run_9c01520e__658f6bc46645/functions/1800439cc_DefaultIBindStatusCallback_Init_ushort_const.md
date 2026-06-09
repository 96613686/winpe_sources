# DefaultIBindStatusCallback::Init(ushort const *)

- ea: `0x1800439cc`
- end: `0x180043b0c`
- name: `?Init@DefaultIBindStatusCallback@@QEAAHPEBG@Z`
- size: `320`
- prototype: `int __fastcall(DefaultIBindStatusCallback *this, const wchar_t *pszTitle)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180033e80`

## callees

- `0x1800398b8`
- `0x1800439cc`
- `0x180046460`

## import_xrefs

- `USER32!CreateDialogParamW` at `0x180043a22`
- `USER32!CreateDialogParamW` at `0x180043a22`
- `USER32!MoveWindow` at `0x180043ada`
- `USER32!MoveWindow` at `0x180043ada`
- `USER32!GetDesktopWindow` at `0x180043a7d`
- `USER32!GetDesktopWindow` at `0x180043a7d`
- `USER32!GetClientRect` at `0x180043a90`
- `USER32!GetClientRect` at `0x180043a90`
- `USER32!GetWindowRect` at `0x180043a68`
- `USER32!GetWindowRect` at `0x180043a68`
- `USER32!SetWindowTextW` at `0x180043a46`
- `USER32!SetWindowTextW` at `0x180043a46`

## pseudocode

```c
int __fastcall DefaultIBindStatusCallback::Init(DefaultIBindStatusCallback *this, const wchar_t *pszTitle)
{
  int result; // eax
  int v5; // ebx
  HINSTANCE v6; // rcx
  HWND__ *m_hwndParent; // r8
  HWND__ *DialogParamW; // rax
  HWND__ *m_hDlg; // rcx
  HWND__ *DesktopWindow; // rcx
  tagRECT rectParent; // [rsp+30h] [rbp-30h] BYREF
  tagRECT rectDLG; // [rsp+40h] [rbp-20h] BYREF

  result = CallInitCommonControls();
  v5 = 0;
  if ( result )
  {
    v6 = g_hinst;
    m_hwndParent = this->m_hwndParent;
    this->m_hInstance = g_hinst;
    DialogParamW = CreateDialogParamW(v6, (LPCWSTR)0x65, m_hwndParent, DialogProc, (LPARAM)&this->CHlprDialog);
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
        (rectParent.right - rectParent.left - (rectDLG.right - rectDLG.left)) / 2,
        (rectParent.bottom - rectParent.top - (rectDLG.bottom - rectDLG.top)) / 2,
        rectDLG.right - rectDLG.left,
        rectDLG.bottom - rectDLG.top,
        0);
    }
    LOBYTE(v5) = this->m_hDlg != 0;
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x1800439cc  mov     [rsp-18h+arg_10], rbx
0x1800439d1  push    rbp
0x1800439d2  push    rsi
0x1800439d3  push    rdi
0x1800439d4  mov     rbp, rsp
0x1800439d7  sub     rsp, 60h
0x1800439db  mov     rax, cs:__security_cookie
0x1800439e2  xor     rax, rsp
0x1800439e5  mov     [rbp+var_10], rax
0x1800439e9  mov     rsi, pszTitle
0x1800439ec  mov     rdi, this
0x1800439ef  call    ?CallInitCommonControls@@YAHXZ; CallInitCommonControls(void)
0x1800439f4  xor     ebx, ebx
0x1800439f6  test    eax, eax
0x1800439f8  jz      loc_180043AEF
0x1800439fe  mov     this, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInstance
0x180043a05  lea     rax, [rdi+10h]
0x180043a09  mov     r8, [rdi+38h]; hWndParent
0x180043a0d  lea     r9, DialogProc; lpDialogFunc
0x180043a14  mov     edx, 65h ; 'e'; lpTemplateName
0x180043a19  mov     [rax+8], this
0x180043a1d  mov     [rsp+60h+dwInitParam], rax; dwInitParam
0x180043a22  call    cs:__imp_CreateDialogParamW
0x180043a29  nop     dword ptr [rax+rax+00h]
0x180043a2e  mov     [rdi+40h], rax
0x180043a32  test    rax, rax
0x180043a35  jz      loc_180043AE6
0x180043a3b  test    rsi, rsi
0x180043a3e  jz      short loc_180043A52
0x180043a40  mov     pszTitle, rsi; lpString
0x180043a43  mov     this, rax; hWnd
0x180043a46  call    cs:__imp_SetWindowTextW
0x180043a4d  nop     dword ptr [rax+rax+00h]
0x180043a52  mov     this, [rdi+40h]; hWnd
0x180043a56  lea     pszTitle, [rbp+rectDLG]; lpRect
0x180043a5a  xorps   xmm0, xmm0
0x180043a5d  xorps   xmm1, xmm1
0x180043a60  movups  xmmword ptr [rbp+rectDLG.left], xmm0
0x180043a64  movups  xmmword ptr [rbp+rectParent.left], xmm1
0x180043a68  call    cs:__imp_GetWindowRect
0x180043a6f  nop     dword ptr [rax+rax+00h]
0x180043a74  mov     this, [rdi+38h]
0x180043a78  test    this, this
0x180043a7b  jnz     short loc_180043A8C
0x180043a7d  call    cs:__imp_GetDesktopWindow
0x180043a84  nop     dword ptr [rax+rax+00h]
0x180043a89  mov     this, rax; hWnd
0x180043a8c  lea     pszTitle, [rbp+rectParent]; lpRect
0x180043a90  call    cs:__imp_GetClientRect
0x180043a97  nop     dword ptr [rax+rax+00h]
0x180043a9c  mov     ecx, [rbp+rectDLG.bottom]
0x180043a9f  mov     r10d, 2
0x180043aa5  sub     ecx, [rbp+rectDLG.top]
0x180043aa8  mov     eax, [rbp+rectParent.bottom]
0x180043aab  sub     eax, [rbp+rectParent.top]
0x180043aae  mov     r9d, [rbp+rectDLG.right]
0x180043ab2  sub     eax, ecx
0x180043ab4  sub     r9d, [rbp+rectDLG.left]; nWidth
0x180043ab8  cdq
0x180043ab9  idiv    r10d
0x180043abc  mov     [rsp+60h+bRepaint], ebx; bRepaint
0x180043ac0  mov     r8d, eax; Y
0x180043ac3  mov     dword ptr [rsp+60h+dwInitParam], ecx; nHeight
0x180043ac7  mov     eax, [rbp+rectParent.right]
0x180043aca  sub     eax, [rbp+rectParent.left]
0x180043acd  mov     this, [rdi+40h]; hWnd
0x180043ad1  sub     eax, r9d
0x180043ad4  cdq
0x180043ad5  idiv    r10d
0x180043ad8  mov     edx, eax; X
0x180043ada  call    cs:__imp_MoveWindow
0x180043ae1  nop     dword ptr [rax+rax+00h]
0x180043ae6  cmp     [rdi+40h], rbx
0x180043aea  setnz   bl
0x180043aed  mov     eax, ebx
0x180043aef  mov     this, [rbp+var_10]
0x180043af3  xor     this, rsp; StackCookie
0x180043af6  call    __security_check_cookie
0x180043afb  mov     rbx, [rsp+60h+arg_10]
0x180043b03  add     rsp, 60h
0x180043b07  pop     rdi
0x180043b08  pop     rsi
0x180043b09  pop     rbp
0x180043b0a  retn
```
