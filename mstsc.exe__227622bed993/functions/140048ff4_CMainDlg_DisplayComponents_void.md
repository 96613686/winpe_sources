# CMainDlg::DisplayComponents(void)

- ea: `0x140048ff4`
- end: `0x140049156`
- name: `?DisplayComponents@CMainDlg@@AEAAXXZ`
- size: `354`
- prototype: `void __fastcall(CMainDlg *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140047e30`

## callees

- `0x140003b2c`
- `0x140048ff4`
- `0x14004ae2c`
- `0x14009f674`
- `0x1400b4964`
- `0x1400fa8b0`
- `0x140111220`

## import_xrefs

- `USER32!CreateDialogIndirectParamW` at `0x1400490d3`
- `USER32!CreateDialogIndirectParamW` at `0x1400490d3`
- `USER32!ShowWindow` at `0x1400490e8`
- `USER32!ShowWindow` at `0x140049138`
- `USER32!ShowWindow` at `0x1400490e8`
- `USER32!ShowWindow` at `0x140049138`
- `USER32!SetWindowPos` at `0x140049125`
- `USER32!SetWindowPos` at `0x140049125`
- `USER32!GetWindowRect` at `0x14004907d`
- `USER32!GetWindowRect` at `0x14004907d`
- `USER32!GetDlgItem` at `0x14004905e`
- `USER32!GetDlgItem` at `0x1400490f7`
- `USER32!GetDlgItem` at `0x14004905e`
- `USER32!GetDlgItem` at `0x1400490f7`

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
0x140048ff4  mov     [rsp+arg_8], rbx
0x140048ff9  push    rdi
0x140048ffa  sub     rsp, 60h
0x140048ffe  mov     rax, cs:__security_cookie
0x140049005  xor     rax, rsp
0x140049008  mov     [rsp+68h+var_18], rax
0x14004900d  cmp     qword ptr [rcx+218h], 0
0x140049015  xorps   xmm0, xmm0
0x140049018  movups  xmmword ptr [rsp+68h+Rect.left], xmm0
0x14004901d  mov     rbx, rcx
0x140049020  jnz     short loc_140049055
0x140049022  mov     ecx, 868h; Size
0x140049027  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14004902c  test    rax, rax
0x14004902f  jz      short loc_14004904E
0x140049031  mov     r8, [rbx+50h]
0x140049035  mov     r9d, 1; int
0x14004903b  mov     rdx, [rbx+20h]; HINSTANCE
0x14004903f  add     r8, 35078h; struct ISharedSettings *
0x140049046  mov     rcx, rax; this
0x140049049  call    ??0CTscCredsPane@@QEAA@PEAUHINSTANCE__@@PEAVISharedSettings@@H@Z; CTscCredsPane::CTscCredsPane(HINSTANCE__ *,ISharedSettings *,int)
0x14004904e  mov     [rbx+218h], rax
0x140049055  mov     rcx, [rbx+8]; hDlg
0x140049059  mov     edx, 32FFh; nIDDlgItem
0x14004905e  call    cs:__imp_GetDlgItem
0x140049064  cmp     qword ptr [rbx+218h], 0
0x14004906c  mov     rdi, rax
0x14004906f  jz      loc_140049133
0x140049075  lea     rdx, [rsp+68h+Rect]; lpRect
0x14004907a  mov     rcx, rax; hWnd
0x14004907d  call    cs:__imp_GetWindowRect
0x140049083  mov     rcx, [rbx+8]; hWnd
0x140049087  lea     rdx, [rsp+68h+Rect]; lprc
0x14004908c  call    ?ScreenToClientRect@CClientUtilsWin32@@SAXPEAUHWND__@@PEAUtagRECT@@@Z; CClientUtilsWin32::ScreenToClientRect(HWND__ *,tagRECT *)
0x140049091  mov     rcx, [rbx+218h]
0x140049098  mov     edx, 3A9Ah; unsigned int
0x14004909d  movups  xmm0, xmmword ptr [rsp+68h+Rect.left]
0x1400490a2  movdqu  xmmword ptr [rcx+34h], xmm0
0x1400490a7  mov     rcx, [rbx+20h]; HINSTANCE
0x1400490ab  call    ?TSLoadDlgTemplate@@YAPEAUDLGTEMPLATE@@PEAUHINSTANCE__@@I@Z; TSLoadDlgTemplate(HINSTANCE__ *,uint)
0x1400490b0  test    rax, rax
0x1400490b3  jz      short loc_140049133
0x1400490b5  mov     rcx, [rbx+218h]
0x1400490bc  lea     r9, ?StaticCredPaneDialogProc@CTscCredsPane@@SA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x1400490c3  mov     r8, [rbx+8]; hWndParent
0x1400490c7  mov     rdx, rax; lpTemplate
0x1400490ca  mov     [rsp+68h+dwInitParam], rcx; dwInitParam
0x1400490cf  mov     rcx, [rbx+20h]; hInstance
0x1400490d3  call    cs:__imp_CreateDialogIndirectParamW
0x1400490d9  mov     rcx, rax; hWnd
0x1400490dc  mov     [rbx+220h], rax
0x1400490e3  mov     edx, 4; nCmdShow
0x1400490e8  call    cs:__imp_ShowWindow
0x1400490ee  mov     rcx, [rbx+8]; hDlg
0x1400490f2  mov     edx, 1394h; nIDDlgItem
0x1400490f7  call    cs:__imp_GetDlgItem
0x1400490fd  mov     rcx, [rbx+220h]; hWnd
0x140049104  xor     r9d, r9d; Y
0x140049107  mov     [rsp+68h+uFlags], 3; uFlags
0x14004910f  mov     rdx, rax; hWndInsertAfter
0x140049112  mov     [rsp+68h+cy], 0; cy
0x14004911a  xor     r8d, r8d; X
0x14004911d  mov     dword ptr [rsp+68h+dwInitParam], 0; cx
0x140049125  call    cs:__imp_SetWindowPos
0x14004912b  mov     rcx, rbx; this
0x14004912e  call    ?UpdateCredPaneWithServerName@CMainDlg@@AEAAXXZ; CMainDlg::UpdateCredPaneWithServerName(void)
0x140049133  xor     edx, edx; nCmdShow
0x140049135  mov     rcx, rdi; hWnd
0x140049138  call    cs:__imp_ShowWindow
0x14004913e  mov     rcx, [rsp+68h+var_18]
0x140049143  xor     rcx, rsp; StackCookie
0x140049146  call    __security_check_cookie
0x14004914b  mov     rbx, [rsp+68h+arg_8]
0x140049150  add     rsp, 60h
0x140049154  pop     rdi
0x140049155  retn
```
