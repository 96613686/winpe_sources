# CMainDlg::DisplayComponents(void)

- ea: `0x14004b164`
- end: `0x14004b2c6`
- name: `?DisplayComponents@CMainDlg@@AEAAXXZ`
- size: `354`
- prototype: `void __fastcall(CMainDlg *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140049fa0`

## callees

- `0x140003b2c`
- `0x14004b164`
- `0x14004cf9c`
- `0x1400a17e4`
- `0x1400b6ad4`
- `0x1400fca20`
- `0x140113390`

## import_xrefs

- `USER32!CreateDialogIndirectParamW` at `0x14004b243`
- `USER32!CreateDialogIndirectParamW` at `0x14004b243`
- `USER32!ShowWindow` at `0x14004b258`
- `USER32!ShowWindow` at `0x14004b2a8`
- `USER32!ShowWindow` at `0x14004b258`
- `USER32!ShowWindow` at `0x14004b2a8`
- `USER32!SetWindowPos` at `0x14004b295`
- `USER32!SetWindowPos` at `0x14004b295`
- `USER32!GetWindowRect` at `0x14004b1ed`
- `USER32!GetWindowRect` at `0x14004b1ed`
- `USER32!GetDlgItem` at `0x14004b1ce`
- `USER32!GetDlgItem` at `0x14004b267`
- `USER32!GetDlgItem` at `0x14004b1ce`
- `USER32!GetDlgItem` at `0x14004b267`

## pseudocode

```c
void __fastcall CMainDlg::DisplayComponents(CMainDlg *this)
{
  bool v1; // zf
  CTscCredsPane *v3; // rax
  HWND DlgItem; // rax
  HWND v5; // rdi
  const DLGTEMPLATE *v6; // rax
  HWND DialogIndirectParamW; // rax
  HWND v8; // rax
  struct tagRECT Rect; // [rsp+40h] [rbp-28h] BYREF

  v1 = *((_QWORD *)this + 67) == 0;
  Rect = 0;
  if ( v1 )
  {
    v3 = (CTscCredsPane *)operator new(0x868u);
    if ( v3 )
      v3 = CTscCredsPane::CTscCredsPane(
             v3,
             *((HINSTANCE *)this + 4),
             (struct ISharedSettings *)(*((_QWORD *)this + 10) + 217208LL),
             1);
    *((_QWORD *)this + 67) = v3;
  }
  DlgItem = GetDlgItem(*((HWND *)this + 1), 13055);
  v5 = DlgItem;
  if ( *((_QWORD *)this + 67) )
  {
    GetWindowRect(DlgItem, &Rect);
    CClientUtilsWin32::ScreenToClientRect(*((HWND *)this + 1), &Rect);
    *(struct tagRECT *)(*((_QWORD *)this + 67) + 52LL) = Rect;
    v6 = TSLoadDlgTemplate(*((HINSTANCE *)this + 4), 0x3A9Au);
    if ( v6 )
    {
      DialogIndirectParamW = CreateDialogIndirectParamW(
                               *((HINSTANCE *)this + 4),
                               v6,
                               *((HWND *)this + 1),
                               CTscCredsPane::StaticCredPaneDialogProc,
                               *((_QWORD *)this + 67));
      *((_QWORD *)this + 68) = DialogIndirectParamW;
      ShowWindow(DialogIndirectParamW, 4);
      v8 = GetDlgItem(*((HWND *)this + 1), 5012);
      SetWindowPos(*((HWND *)this + 68), v8, 0, 0, 0, 0, 3u);
      CMainDlg::UpdateCredPaneWithServerName(this);
    }
  }
  ShowWindow(v5, 0);
}

```

## disassembly

```asm
0x14004b164  mov     [rsp+arg_8], rbx
0x14004b169  push    rdi
0x14004b16a  sub     rsp, 60h
0x14004b16e  mov     rax, cs:__security_cookie
0x14004b175  xor     rax, rsp
0x14004b178  mov     [rsp+68h+var_18], rax
0x14004b17d  cmp     qword ptr [rcx+218h], 0
0x14004b185  xorps   xmm0, xmm0
0x14004b188  movups  xmmword ptr [rsp+68h+Rect.left], xmm0
0x14004b18d  mov     rbx, rcx
0x14004b190  jnz     short loc_14004B1C5
0x14004b192  mov     ecx, 868h; Size
0x14004b197  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14004b19c  test    rax, rax
0x14004b19f  jz      short loc_14004B1BE
0x14004b1a1  mov     r8, [rbx+50h]
0x14004b1a5  mov     r9d, 1; int
0x14004b1ab  mov     rdx, [rbx+20h]; HINSTANCE
0x14004b1af  add     r8, 35078h; struct ISharedSettings *
0x14004b1b6  mov     rcx, rax; this
0x14004b1b9  call    ??0CTscCredsPane@@QEAA@PEAUHINSTANCE__@@PEAVISharedSettings@@H@Z; CTscCredsPane::CTscCredsPane(HINSTANCE__ *,ISharedSettings *,int)
0x14004b1be  mov     [rbx+218h], rax
0x14004b1c5  mov     rcx, [rbx+8]; hDlg
0x14004b1c9  mov     edx, 32FFh; nIDDlgItem
0x14004b1ce  call    cs:__imp_GetDlgItem
0x14004b1d4  cmp     qword ptr [rbx+218h], 0
0x14004b1dc  mov     rdi, rax
0x14004b1df  jz      loc_14004B2A3
0x14004b1e5  lea     rdx, [rsp+68h+Rect]; lpRect
0x14004b1ea  mov     rcx, rax; hWnd
0x14004b1ed  call    cs:__imp_GetWindowRect
0x14004b1f3  mov     rcx, [rbx+8]; hWnd
0x14004b1f7  lea     rdx, [rsp+68h+Rect]; lprc
0x14004b1fc  call    ?ScreenToClientRect@CClientUtilsWin32@@SAXPEAUHWND__@@PEAUtagRECT@@@Z; CClientUtilsWin32::ScreenToClientRect(HWND__ *,tagRECT *)
0x14004b201  mov     rcx, [rbx+218h]
0x14004b208  mov     edx, 3A9Ah; unsigned int
0x14004b20d  movups  xmm0, xmmword ptr [rsp+68h+Rect.left]
0x14004b212  movdqu  xmmword ptr [rcx+34h], xmm0
0x14004b217  mov     rcx, [rbx+20h]; HINSTANCE
0x14004b21b  call    ?TSLoadDlgTemplate@@YAPEAUDLGTEMPLATE@@PEAUHINSTANCE__@@I@Z; TSLoadDlgTemplate(HINSTANCE__ *,uint)
0x14004b220  test    rax, rax
0x14004b223  jz      short loc_14004B2A3
0x14004b225  mov     rcx, [rbx+218h]
0x14004b22c  lea     r9, ?StaticCredPaneDialogProc@CTscCredsPane@@SA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x14004b233  mov     r8, [rbx+8]; hWndParent
0x14004b237  mov     rdx, rax; lpTemplate
0x14004b23a  mov     [rsp+68h+dwInitParam], rcx; dwInitParam
0x14004b23f  mov     rcx, [rbx+20h]; hInstance
0x14004b243  call    cs:__imp_CreateDialogIndirectParamW
0x14004b249  mov     rcx, rax; hWnd
0x14004b24c  mov     [rbx+220h], rax
0x14004b253  mov     edx, 4; nCmdShow
0x14004b258  call    cs:__imp_ShowWindow
0x14004b25e  mov     rcx, [rbx+8]; hDlg
0x14004b262  mov     edx, 1394h; nIDDlgItem
0x14004b267  call    cs:__imp_GetDlgItem
0x14004b26d  mov     rcx, [rbx+220h]; hWnd
0x14004b274  xor     r9d, r9d; Y
0x14004b277  mov     [rsp+68h+uFlags], 3; uFlags
0x14004b27f  mov     rdx, rax; hWndInsertAfter
0x14004b282  mov     [rsp+68h+cy], 0; cy
0x14004b28a  xor     r8d, r8d; X
0x14004b28d  mov     dword ptr [rsp+68h+dwInitParam], 0; cx
0x14004b295  call    cs:__imp_SetWindowPos
0x14004b29b  mov     rcx, rbx; this
0x14004b29e  call    ?UpdateCredPaneWithServerName@CMainDlg@@AEAAXXZ; CMainDlg::UpdateCredPaneWithServerName(void)
0x14004b2a3  xor     edx, edx; nCmdShow
0x14004b2a5  mov     rcx, rdi; hWnd
0x14004b2a8  call    cs:__imp_ShowWindow
0x14004b2ae  mov     rcx, [rsp+68h+var_18]
0x14004b2b3  xor     rcx, rsp; StackCookie
0x14004b2b6  call    __security_check_cookie
0x14004b2bb  mov     rbx, [rsp+68h+arg_8]
0x14004b2c0  add     rsp, 60h
0x14004b2c4  pop     rdi
0x14004b2c5  retn
```
