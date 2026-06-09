# CProgress::CreateTheWindow(void)

- ea: `0x18001ec9c`
- end: `0x18001ee93`
- name: `?CreateTheWindow@CProgress@@QEAAXXZ`
- size: `503`
- prototype: `void __fastcall(CProgress *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001dd04`

## callees

- `0x180005a4c`
- `0x18000ad54`
- `0x18001d570`
- `0x18001ec9c`
- `0x180075c90`

## import_xrefs

- `USER32!MoveWindow` at `0x18001ede1`
- `USER32!MoveWindow` at `0x18001ede1`
- `USER32!SetWindowTextA` at `0x18001ee36`
- `USER32!SetWindowTextA` at `0x18001ee36`
- `USER32!ShowWindow` at `0x18001ee6c`
- `USER32!ShowWindow` at `0x18001ee6c`
- `USER32!GetWindowRect` at `0x18001ed3d`
- `USER32!GetWindowRect` at `0x18001edb8`
- `USER32!GetWindowRect` at `0x18001ed3d`
- `USER32!GetWindowRect` at `0x18001edb8`
- `USER32!SendMessageA` at `0x18001ee13`
- `USER32!SendMessageA` at `0x18001ee29`
- `USER32!SendMessageA` at `0x18001ee52`
- `USER32!SendMessageA` at `0x18001ee13`
- `USER32!SendMessageA` at `0x18001ee29`
- `USER32!SendMessageA` at `0x18001ee52`
- `USER32!GetDlgItem` at `0x18001edef`
- `USER32!GetDlgItem` at `0x18001edef`
- `GDI32!CreateICA` at `0x18001ecf5`
- `GDI32!CreateICA` at `0x18001ecf5`
- `GDI32!GetDeviceCaps` at `0x18001ed0a`
- `GDI32!GetDeviceCaps` at `0x18001ed1e`
- `GDI32!GetDeviceCaps` at `0x18001ed0a`
- `GDI32!GetDeviceCaps` at `0x18001ed1e`

## pseudocode

```c
void __fastcall CProgress::CreateTheWindow(CProgress *this)
{
  HWND v2; // rcx
  HDC v3; // rbx
  HWND v4; // rbx
  HINSTANCE ResourceInstance; // rax
  HWND DialogParamA; // rax
  HWND DlgItem; // rax
  bool v8; // cc
  HWND v9; // rcx
  int v10; // eax
  HWND v11; // rcx
  struct tagRECT v12[3]; // [rsp+30h] [rbp-9h] BYREF
  struct tagRECT Rect; // [rsp+60h] [rbp+27h] BYREF
  struct tagRECT v14; // [rsp+70h] [rbp+37h] BYREF

  if ( !*((_DWORD *)this + 16) )
  {
    v2 = (HWND)*((_QWORD *)this + 5);
    if ( v2 )
    {
      Rect = 0;
      GetWindowRect(v2, &Rect);
      *((_DWORD *)this + 4) = (Rect.right - Rect.left) / 2 - 100;
      *((_DWORD *)this + 5) = (Rect.bottom - Rect.top) / 2 - 25;
    }
    else
    {
      memset(v12, 0, sizeof(v12));
      *(_QWORD *)&v12[0].left = CreateICA("DISPLAY", 0, 0, 0);
      v3 = *(HDC *)&v12[0].left;
      *((_DWORD *)this + 4) = GetDeviceCaps(*(HDC *)&v12[0].left, 8) - 100;
      *((_DWORD *)this + 5) = GetDeviceCaps(v3, 10) - 25;
      CPalDC::~CPalDC((CPalDC *)v12);
    }
    v4 = (HWND)*((_QWORD *)this + 5);
    ResourceInstance = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
    DialogParamA = (HWND)IsolationAwareCreateDialogParamA(ResourceInstance, (LPCSTR)0x78, v4, ProgressDialogProc, 0);
    *(_QWORD *)this = DialogParamA;
    if ( DialogParamA )
    {
      v14 = 0;
      GetWindowRect(DialogParamA, &v14);
      MoveWindow(*(HWND *)this, v14.left, *((_DWORD *)this + 5), v14.right - v14.left, v14.bottom - v14.top, 0);
      DlgItem = GetDlgItem(*(HWND *)this, 121);
      v8 = *((_DWORD *)this + 12) <= 0;
      *((_QWORD *)this + 1) = DlgItem;
      if ( !v8 )
      {
        SendMessageA(DlgItem, 0x401u, 0, (unsigned __int64)*((unsigned __int16 *)this + 24) << 16);
        SendMessageA(*((HWND *)this + 1), 0x404u, 1u, 0);
      }
      SetWindowTextA(*(HWND *)this, *((LPCSTR *)this + 7));
      while ( 1 )
      {
        v10 = *((_DWORD *)this + 17);
        if ( v10 < 0 )
          break;
        v9 = (HWND)*((_QWORD *)this + 1);
        *((_DWORD *)this + 17) = v10 - 1;
        SendMessageA(v9, 0x405u, 0, 0);
      }
      v11 = *(HWND *)this;
      *((_DWORD *)this + 17) = v10 - 1;
      ShowWindow(v11, 5);
    }
    else
    {
      *((_DWORD *)this + 16) = 1;
    }
  }
}

```

## disassembly

```asm
0x18001ec9c  mov     [rsp-8+arg_8], rbx
0x18001eca1  mov     [rsp-8+arg_10], rdi
0x18001eca6  push    rbp
0x18001eca7  lea     rbp, [rsp-57h]
0x18001ecac  sub     rsp, 90h
0x18001ecb3  mov     rax, cs:__security_cookie
0x18001ecba  xor     rax, rsp
0x18001ecbd  mov     [rbp+57h+var_10], rax
0x18001ecc1  cmp     dword ptr [rcx+40h], 0
0x18001ecc5  mov     rdi, rcx
0x18001ecc8  jnz     loc_18001EE72
0x18001ecce  mov     rcx, [rcx+28h]; hWnd
0x18001ecd2  xorps   xmm0, xmm0
0x18001ecd5  test    rcx, rcx
0x18001ecd8  jnz     short loc_18001ED35
0x18001ecda  xor     r9d, r9d; pdm
0x18001ecdd  lea     rcx, pszDriver; "DISPLAY"
0x18001ece4  xor     r8d, r8d; pszPort
0x18001ece7  xor     edx, edx; pszDevice
0x18001ece9  movups  [rbp+57h+var_60], xmm0
0x18001eced  movups  [rbp+57h+var_50], xmm0
0x18001ecf1  movups  [rbp+57h+var_40], xmm0
0x18001ecf5  call    cs:__imp_CreateICA
0x18001ecfb  mov     rcx, rax; hdc
0x18001ecfe  mov     qword ptr [rbp+57h+var_60], rax
0x18001ed02  mov     edx, 8; index
0x18001ed07  mov     rbx, rax
0x18001ed0a  call    cs:__imp_GetDeviceCaps
0x18001ed10  mov     edx, 0Ah; index
0x18001ed15  mov     rcx, rbx; hdc
0x18001ed18  sub     eax, 64h ; 'd'
0x18001ed1b  mov     [rdi+10h], eax
0x18001ed1e  call    cs:__imp_GetDeviceCaps
0x18001ed24  sub     eax, 19h
0x18001ed27  lea     rcx, [rbp+57h+var_60]; this
0x18001ed2b  mov     [rdi+14h], eax
0x18001ed2e  call    ??1CPalDC@@QEAA@XZ; CPalDC::~CPalDC(void)
0x18001ed33  jmp     short loc_18001ED66
0x18001ed35  lea     rdx, [rbp+57h+Rect]; lpRect
0x18001ed39  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x18001ed3d  call    cs:__imp_GetWindowRect
0x18001ed43  mov     eax, [rbp+57h+Rect.right]
0x18001ed46  mov     ecx, 2
0x18001ed4b  sub     eax, [rbp+57h+Rect.left]
0x18001ed4e  cdq
0x18001ed4f  idiv    ecx
0x18001ed51  sub     eax, 64h ; 'd'
0x18001ed54  mov     [rdi+10h], eax
0x18001ed57  mov     eax, [rbp+57h+Rect.bottom]
0x18001ed5a  sub     eax, [rbp+57h+Rect.top]
0x18001ed5d  cdq
0x18001ed5e  idiv    ecx
0x18001ed60  sub     eax, 19h
0x18001ed63  mov     [rdi+14h], eax
0x18001ed66  mov     rbx, [rdi+28h]
0x18001ed6a  lea     rcx, ?_Module@@3VCHtmlHelpModule@@A; this
0x18001ed71  call    ?GetResourceInstance@CHtmlHelpModule@@QEAAPEAUHINSTANCE__@@XZ; CHtmlHelpModule::GetResourceInstance(void)
0x18001ed76  lea     r9, ProgressDialogProc; lpDialogFunc
0x18001ed7d  mov     qword ptr [rsp+90h+nHeight], 0; LPARAM
0x18001ed86  mov     r8, rbx; hWndParent
0x18001ed89  mov     edx, 78h ; 'x'; lpTemplateName
0x18001ed8e  mov     rcx, rax; hInstance
0x18001ed91  call    IsolationAwareCreateDialogParamA
0x18001ed96  mov     [rdi], rax
0x18001ed99  test    rax, rax
0x18001ed9c  jnz     short loc_18001EDAA
0x18001ed9e  mov     dword ptr [rdi+40h], 1
0x18001eda5  jmp     loc_18001EE72
0x18001edaa  xorps   xmm0, xmm0
0x18001edad  lea     rdx, [rbp+57h+var_20]; lpRect
0x18001edb1  mov     rcx, rax; hWnd
0x18001edb4  movups  xmmword ptr [rbp+57h+var_20.left], xmm0
0x18001edb8  call    cs:__imp_GetWindowRect
0x18001edbe  mov     eax, [rbp+57h+var_20.bottom]
0x18001edc1  mov     r9d, [rbp+57h+var_20.right]
0x18001edc5  sub     eax, [rbp+57h+var_20.top]
0x18001edc8  mov     edx, [rbp+57h+var_20.left]; X
0x18001edcb  sub     r9d, edx; nWidth
0x18001edce  mov     r8d, [rdi+14h]; Y
0x18001edd2  mov     rcx, [rdi]; hWnd
0x18001edd5  mov     [rsp+90h+bRepaint], 0; bRepaint
0x18001eddd  mov     [rsp+90h+nHeight], eax; nHeight
0x18001ede1  call    cs:__imp_MoveWindow
0x18001ede7  mov     rcx, [rdi]; hDlg
0x18001edea  mov     edx, 79h ; 'y'; nIDDlgItem
0x18001edef  call    cs:__imp_GetDlgItem
0x18001edf5  cmp     dword ptr [rdi+30h], 0
0x18001edf9  mov     [rdi+8], rax
0x18001edfd  jle     short loc_18001EE2F
0x18001edff  movzx   r9d, word ptr [rdi+30h]
0x18001ee04  xor     r8d, r8d; wParam
0x18001ee07  shl     r9, 10h; lParam
0x18001ee0b  mov     edx, 401h; Msg
0x18001ee10  mov     rcx, rax; hWnd
0x18001ee13  call    cs:__imp_SendMessageA
0x18001ee19  mov     rcx, [rdi+8]; hWnd
0x18001ee1d  xor     r9d, r9d; lParam
0x18001ee20  mov     edx, 404h; Msg
0x18001ee25  lea     r8d, [r9+1]; wParam
0x18001ee29  call    cs:__imp_SendMessageA
0x18001ee2f  mov     rdx, [rdi+38h]; lpString
0x18001ee33  mov     rcx, [rdi]; hWnd
0x18001ee36  call    cs:__imp_SetWindowTextA
0x18001ee3c  jmp     short loc_18001EE58
0x18001ee3e  mov     rcx, [rdi+8]; hWnd
0x18001ee42  dec     eax
0x18001ee44  xor     r9d, r9d; lParam
0x18001ee47  mov     [rdi+44h], eax
0x18001ee4a  xor     r8d, r8d; wParam
0x18001ee4d  mov     edx, 405h; Msg
0x18001ee52  call    cs:__imp_SendMessageA
0x18001ee58  mov     eax, [rdi+44h]
0x18001ee5b  test    eax, eax
0x18001ee5d  jns     short loc_18001EE3E
0x18001ee5f  mov     rcx, [rdi]; hWnd
0x18001ee62  dec     eax
0x18001ee64  mov     edx, 5; nCmdShow
0x18001ee69  mov     [rdi+44h], eax
0x18001ee6c  call    cs:__imp_ShowWindow
0x18001ee72  mov     rcx, [rbp+57h+var_10]
0x18001ee76  xor     rcx, rsp; StackCookie
0x18001ee79  call    __security_check_cookie
0x18001ee7e  lea     r11, [rsp+90h+var_s0]
0x18001ee86  mov     rbx, [r11+18h]
0x18001ee8a  mov     rdi, [r11+20h]
0x18001ee8e  mov     rsp, r11
0x18001ee91  pop     rbp
0x18001ee92  retn
```
