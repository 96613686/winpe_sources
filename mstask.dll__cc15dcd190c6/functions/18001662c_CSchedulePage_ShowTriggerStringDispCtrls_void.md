# CSchedulePage::_ShowTriggerStringDispCtrls(void)

- ea: `0x18001662c`
- end: `0x180016829`
- name: `?_ShowTriggerStringDispCtrls@CSchedulePage@@AEAAXXZ`
- size: `509`
- prototype: `void __fastcall(CSchedulePage *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180014aa0`
- `0x1800159c0`
- `0x180015db8`

## callees

- `0x18001662c`

## import_xrefs

- `USER32!EnableWindow` at `0x180016714`
- `USER32!EnableWindow` at `0x1800167f9`
- `USER32!EnableWindow` at `0x180016818`
- `USER32!EnableWindow` at `0x180016714`
- `USER32!EnableWindow` at `0x1800167f9`
- `USER32!EnableWindow` at `0x180016818`
- `USER32!GetDlgItem` at `0x18001664f`
- `USER32!GetDlgItem` at `0x180016670`
- `USER32!GetDlgItem` at `0x18001668f`
- `USER32!GetDlgItem` at `0x1800166bd`
- `USER32!GetDlgItem` at `0x1800166df`
- `USER32!GetDlgItem` at `0x180016701`
- `USER32!GetDlgItem` at `0x180016723`
- `USER32!GetDlgItem` at `0x180016748`
- `USER32!GetDlgItem` at `0x180016767`
- `USER32!GetDlgItem` at `0x180016786`
- `USER32!GetDlgItem` at `0x1800167a5`
- `USER32!GetDlgItem` at `0x1800167c7`
- `USER32!GetDlgItem` at `0x1800167e9`
- `USER32!GetDlgItem` at `0x180016808`
- `USER32!GetDlgItem` at `0x18001664f`
- `USER32!GetDlgItem` at `0x180016670`
- `USER32!GetDlgItem` at `0x18001668f`
- `USER32!GetDlgItem` at `0x1800166bd`
- `USER32!GetDlgItem` at `0x1800166df`
- `USER32!GetDlgItem` at `0x180016701`
- `USER32!GetDlgItem` at `0x180016723`
- `USER32!GetDlgItem` at `0x180016748`
- `USER32!GetDlgItem` at `0x180016767`
- `USER32!GetDlgItem` at `0x180016786`
- `USER32!GetDlgItem` at `0x1800167a5`
- `USER32!GetDlgItem` at `0x1800167c7`
- `USER32!GetDlgItem` at `0x1800167e9`
- `USER32!GetDlgItem` at `0x180016808`
- `USER32!ShowWindow` at `0x180016661`
- `USER32!ShowWindow` at `0x180016680`
- `USER32!ShowWindow` at `0x1800166a2`
- `USER32!ShowWindow` at `0x1800166d0`
- `USER32!ShowWindow` at `0x1800166f2`
- `USER32!ShowWindow` at `0x180016758`
- `USER32!ShowWindow` at `0x180016777`
- `USER32!ShowWindow` at `0x180016796`
- `USER32!ShowWindow` at `0x1800167b8`
- `USER32!ShowWindow` at `0x1800167da`
- `USER32!ShowWindow` at `0x180016661`
- `USER32!ShowWindow` at `0x180016680`
- `USER32!ShowWindow` at `0x1800166a2`
- `USER32!ShowWindow` at `0x1800166d0`
- `USER32!ShowWindow` at `0x1800166f2`
- `USER32!ShowWindow` at `0x180016758`
- `USER32!ShowWindow` at `0x180016777`
- `USER32!ShowWindow` at `0x180016796`
- `USER32!ShowWindow` at `0x1800167b8`
- `USER32!ShowWindow` at `0x1800167da`

## pseudocode

```c
void __fastcall CSchedulePage::_ShowTriggerStringDispCtrls(CSchedulePage *this)
{
  HWND v2; // rcx
  HWND DlgItem; // rax
  BOOL v4; // ebx
  HWND v5; // rax
  HWND v6; // rax
  HWND v7; // rax
  HWND v8; // rax
  HWND v9; // rax
  HWND v10; // rax
  BOOL v11; // edx
  HWND v12; // rax
  HWND v13; // rax
  HWND v14; // rax
  HWND v15; // rax
  HWND v16; // rax
  HWND v17; // rax

  v2 = (HWND)*((_QWORD *)this + 14);
  if ( *((_DWORD *)this + 190) == 1 )
  {
    DlgItem = GetDlgItem(v2, 1693);
    v4 = 0;
    if ( DlgItem )
      ShowWindow(DlgItem, 0);
    v5 = GetDlgItem(*((HWND *)this + 14), 500);
    if ( v5 )
      ShowWindow(v5, 0);
    v6 = GetDlgItem(*((HWND *)this + 14), 1692);
    if ( v6 )
      ShowWindow(v6, 8);
    if ( !*((_DWORD *)this + 192) )
    {
      v7 = GetDlgItem(*((HWND *)this + 14), 1694);
      if ( v7 )
        ShowWindow(v7, 8);
      v8 = GetDlgItem(*((HWND *)this + 14), 1695);
      if ( v8 )
        ShowWindow(v8, 8);
      v9 = GetDlgItem(*((HWND *)this + 14), 1694);
      if ( v9 )
        EnableWindow(v9, 1);
      v10 = GetDlgItem(*((HWND *)this + 14), 1695);
      if ( v10 )
      {
        LOBYTE(v4) = *((_QWORD *)this + 91) != 0;
        v11 = v4;
LABEL_31:
        EnableWindow(v10, v11);
      }
    }
  }
  else
  {
    v12 = GetDlgItem(v2, 1692);
    if ( v12 )
      ShowWindow(v12, 0);
    v13 = GetDlgItem(*((HWND *)this + 14), 1694);
    if ( v13 )
      ShowWindow(v13, 0);
    v14 = GetDlgItem(*((HWND *)this + 14), 1695);
    if ( v14 )
      ShowWindow(v14, 0);
    v15 = GetDlgItem(*((HWND *)this + 14), 1693);
    if ( v15 )
      ShowWindow(v15, 8);
    v16 = GetDlgItem(*((HWND *)this + 14), 500);
    if ( v16 )
      ShowWindow(v16, 8);
    v17 = GetDlgItem(*((HWND *)this + 14), 1694);
    if ( v17 )
      EnableWindow(v17, 0);
    v10 = GetDlgItem(*((HWND *)this + 14), 1695);
    if ( v10 )
    {
      v11 = 0;
      goto LABEL_31;
    }
  }
}

```

## disassembly

```asm
0x18001662c  mov     [rsp+arg_0], rbx
0x180016631  push    rdi
0x180016632  sub     rsp, 20h
0x180016636  mov     rdi, rcx
0x180016639  mov     rcx, [rcx+70h]; hDlg
0x18001663d  cmp     dword ptr [rdi+2F8h], 1
0x180016644  jnz     loc_180016743
0x18001664a  mov     edx, 69Dh; nIDDlgItem
0x18001664f  call    cs:__imp_GetDlgItem
0x180016655  xor     ebx, ebx
0x180016657  test    rax, rax
0x18001665a  jz      short loc_180016667
0x18001665c  xor     edx, edx; nCmdShow
0x18001665e  mov     rcx, rax; hWnd
0x180016661  call    cs:__imp_ShowWindow
0x180016667  mov     rcx, [rdi+70h]; hDlg
0x18001666b  mov     edx, 1F4h; nIDDlgItem
0x180016670  call    cs:__imp_GetDlgItem
0x180016676  test    rax, rax
0x180016679  jz      short loc_180016686
0x18001667b  xor     edx, edx; nCmdShow
0x18001667d  mov     rcx, rax; hWnd
0x180016680  call    cs:__imp_ShowWindow
0x180016686  mov     rcx, [rdi+70h]; hDlg
0x18001668a  mov     edx, 69Ch; nIDDlgItem
0x18001668f  call    cs:__imp_GetDlgItem
0x180016695  test    rax, rax
0x180016698  jz      short loc_1800166A8
0x18001669a  mov     edx, 8; nCmdShow
0x18001669f  mov     rcx, rax; hWnd
0x1800166a2  call    cs:__imp_ShowWindow
0x1800166a8  cmp     [rdi+300h], ebx
0x1800166ae  jnz     loc_18001681E
0x1800166b4  mov     rcx, [rdi+70h]; hDlg
0x1800166b8  mov     edx, 69Eh; nIDDlgItem
0x1800166bd  call    cs:__imp_GetDlgItem
0x1800166c3  test    rax, rax
0x1800166c6  jz      short loc_1800166D6
0x1800166c8  mov     edx, 8; nCmdShow
0x1800166cd  mov     rcx, rax; hWnd
0x1800166d0  call    cs:__imp_ShowWindow
0x1800166d6  mov     rcx, [rdi+70h]; hDlg
0x1800166da  mov     edx, 69Fh; nIDDlgItem
0x1800166df  call    cs:__imp_GetDlgItem
0x1800166e5  test    rax, rax
0x1800166e8  jz      short loc_1800166F8
0x1800166ea  mov     edx, 8; nCmdShow
0x1800166ef  mov     rcx, rax; hWnd
0x1800166f2  call    cs:__imp_ShowWindow
0x1800166f8  mov     rcx, [rdi+70h]; hDlg
0x1800166fc  mov     edx, 69Eh; nIDDlgItem
0x180016701  call    cs:__imp_GetDlgItem
0x180016707  test    rax, rax
0x18001670a  jz      short loc_18001671A
0x18001670c  mov     edx, 1; bEnable
0x180016711  mov     rcx, rax; hWnd
0x180016714  call    cs:__imp_EnableWindow
0x18001671a  mov     rcx, [rdi+70h]; hDlg
0x18001671e  mov     edx, 69Fh; nIDDlgItem
0x180016723  call    cs:__imp_GetDlgItem
0x180016729  test    rax, rax
0x18001672c  jz      loc_18001681E
0x180016732  cmp     [rdi+2D8h], rbx
0x180016739  setnz   bl
0x18001673c  mov     edx, ebx
0x18001673e  jmp     loc_180016815
0x180016743  mov     edx, 69Ch; nIDDlgItem
0x180016748  call    cs:__imp_GetDlgItem
0x18001674e  test    rax, rax
0x180016751  jz      short loc_18001675E
0x180016753  xor     edx, edx; nCmdShow
0x180016755  mov     rcx, rax; hWnd
0x180016758  call    cs:__imp_ShowWindow
0x18001675e  mov     rcx, [rdi+70h]; hDlg
0x180016762  mov     edx, 69Eh; nIDDlgItem
0x180016767  call    cs:__imp_GetDlgItem
0x18001676d  test    rax, rax
0x180016770  jz      short loc_18001677D
0x180016772  xor     edx, edx; nCmdShow
0x180016774  mov     rcx, rax; hWnd
0x180016777  call    cs:__imp_ShowWindow
0x18001677d  mov     rcx, [rdi+70h]; hDlg
0x180016781  mov     edx, 69Fh; nIDDlgItem
0x180016786  call    cs:__imp_GetDlgItem
0x18001678c  test    rax, rax
0x18001678f  jz      short loc_18001679C
0x180016791  xor     edx, edx; nCmdShow
0x180016793  mov     rcx, rax; hWnd
0x180016796  call    cs:__imp_ShowWindow
0x18001679c  mov     rcx, [rdi+70h]; hDlg
0x1800167a0  mov     edx, 69Dh; nIDDlgItem
0x1800167a5  call    cs:__imp_GetDlgItem
0x1800167ab  test    rax, rax
0x1800167ae  jz      short loc_1800167BE
0x1800167b0  mov     edx, 8; nCmdShow
0x1800167b5  mov     rcx, rax; hWnd
0x1800167b8  call    cs:__imp_ShowWindow
0x1800167be  mov     rcx, [rdi+70h]; hDlg
0x1800167c2  mov     edx, 1F4h; nIDDlgItem
0x1800167c7  call    cs:__imp_GetDlgItem
0x1800167cd  test    rax, rax
0x1800167d0  jz      short loc_1800167E0
0x1800167d2  mov     edx, 8; nCmdShow
0x1800167d7  mov     rcx, rax; hWnd
0x1800167da  call    cs:__imp_ShowWindow
0x1800167e0  mov     rcx, [rdi+70h]; hDlg
0x1800167e4  mov     edx, 69Eh; nIDDlgItem
0x1800167e9  call    cs:__imp_GetDlgItem
0x1800167ef  test    rax, rax
0x1800167f2  jz      short loc_1800167FF
0x1800167f4  xor     edx, edx; bEnable
0x1800167f6  mov     rcx, rax; hWnd
0x1800167f9  call    cs:__imp_EnableWindow
0x1800167ff  mov     rcx, [rdi+70h]; hDlg
0x180016803  mov     edx, 69Fh; nIDDlgItem
0x180016808  call    cs:__imp_GetDlgItem
0x18001680e  test    rax, rax
0x180016811  jz      short loc_18001681E
0x180016813  xor     edx, edx; bEnable
0x180016815  mov     rcx, rax; hWnd
0x180016818  call    cs:__imp_EnableWindow
0x18001681e  mov     rbx, [rsp+28h+arg_0]
0x180016823  add     rsp, 20h
0x180016827  pop     rdi
0x180016828  retn
```
