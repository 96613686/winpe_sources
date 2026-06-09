# CMessageDlg::_OnInit(bool *)

- ea: `0x1400022a0`
- end: `0x1400023a3`
- name: `?_OnInit@CMessageDlg@@EEAAJPEA_N@Z`
- size: `259`
- prototype: `__int64 __fastcall(CMessageDlg *__hidden this, bool *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400022a0`

## import_xrefs

- `USER32!GetDlgItem` at `0x1400022eb`
- `USER32!GetDlgItem` at `0x14000230b`
- `USER32!GetDlgItem` at `0x140002327`
- `USER32!GetDlgItem` at `0x14000233e`
- `USER32!GetDlgItem` at `0x140002354`
- `USER32!GetDlgItem` at `0x14000236b`
- `USER32!GetDlgItem` at `0x1400022eb`
- `USER32!GetDlgItem` at `0x14000230b`
- `USER32!GetDlgItem` at `0x140002327`
- `USER32!GetDlgItem` at `0x14000233e`
- `USER32!GetDlgItem` at `0x140002354`
- `USER32!GetDlgItem` at `0x14000236b`
- `USER32!LoadIconW` at `0x1400022b4`
- `USER32!LoadIconW` at `0x1400022b4`
- `USER32!SendDlgItemMessageW` at `0x1400022d9`
- `USER32!SendDlgItemMessageW` at `0x1400022d9`
- `USER32!ShowWindow` at `0x14000235f`
- `USER32!ShowWindow` at `0x140002376`
- `USER32!ShowWindow` at `0x14000235f`
- `USER32!ShowWindow` at `0x140002376`
- `USER32!SendMessageW` at `0x140002392`
- `USER32!SendMessageW` at `0x140002392`
- `USER32!SetWindowTextW` at `0x1400022f7`
- `USER32!SetWindowTextW` at `0x140002318`
- `USER32!SetWindowTextW` at `0x1400022f7`
- `USER32!SetWindowTextW` at `0x140002318`
- `USER32!EnableWindow` at `0x140002332`
- `USER32!EnableWindow` at `0x140002349`
- `USER32!EnableWindow` at `0x140002332`
- `USER32!EnableWindow` at `0x140002349`

## pseudocode

```c
__int64 __fastcall CMessageDlg::_OnInit(CMessageDlg *this, bool *a2)
{
  HICON IconW; // rax
  HWND *v4; // rdi
  const WCHAR *v5; // rbx
  HWND DlgItem; // rax
  HWND v7; // rcx
  HWND v8; // rax
  HWND v9; // rax
  HWND v10; // rax
  HWND v11; // rax
  HWND v12; // rax
  LPARAM v13; // r9

  IconW = LoadIconW(*((HINSTANCE *)this + 2), *((LPCWSTR *)this + 3));
  v4 = (HWND *)((char *)this + 8);
  if ( IconW )
    SendDlgItemMessageW(*v4, 105, 0x170u, (WPARAM)IconW, 0);
  v5 = (const WCHAR *)*((_QWORD *)this + 4);
  DlgItem = GetDlgItem(*v4, 106);
  SetWindowTextW(DlgItem, v5);
  v7 = *v4;
  if ( *((_WORD *)this + 20) )
  {
    v8 = GetDlgItem(v7, 104);
    SetWindowTextW(v8, (LPCWSTR)this + 20);
  }
  else
  {
    v9 = GetDlgItem(v7, 108);
    EnableWindow(v9, 0);
    v10 = GetDlgItem(*v4, 104);
    EnableWindow(v10, 0);
    v11 = GetDlgItem(*v4, 108);
    ShowWindow(v11, 0);
    v12 = GetDlgItem(*v4, 104);
    ShowWindow(v12, 0);
  }
  v13 = *((_QWORD *)this + 78);
  if ( v13 )
    SendMessageW(*v4, 0xCu, 0, v13);
  return 0;
}

```

## disassembly

```asm
0x1400022a0  push    rbx
0x1400022a2  push    rbp
0x1400022a3  push    rsi
0x1400022a4  push    rdi
0x1400022a5  sub     rsp, 38h
0x1400022a9  mov     rdx, [rcx+18h]; lpIconName
0x1400022ad  mov     rsi, rcx
0x1400022b0  mov     rcx, [rcx+10h]; hInstance
0x1400022b4  call    cs:__imp_LoadIconW
0x1400022ba  xor     ebp, ebp
0x1400022bc  lea     rdi, [rsi+8]
0x1400022c0  test    rax, rax
0x1400022c3  jz      short loc_1400022DF
0x1400022c5  mov     rcx, [rdi]; hDlg
0x1400022c8  lea     edx, [rbp+69h]; nIDDlgItem
0x1400022cb  mov     r9, rax; wParam
0x1400022ce  mov     [rsp+58h+lParam], rbp; lParam
0x1400022d3  mov     r8d, 170h; Msg
0x1400022d9  call    cs:__imp_SendDlgItemMessageW
0x1400022df  mov     rcx, [rdi]; hDlg
0x1400022e2  mov     edx, 6Ah ; 'j'; nIDDlgItem
0x1400022e7  mov     rbx, [rsi+20h]
0x1400022eb  call    cs:__imp_GetDlgItem
0x1400022f1  mov     rcx, rax; hWnd
0x1400022f4  mov     rdx, rbx; lpString
0x1400022f7  call    cs:__imp_SetWindowTextW
0x1400022fd  mov     rcx, [rdi]; hDlg
0x140002300  cmp     [rsi+28h], bp
0x140002304  jz      short loc_140002320
0x140002306  mov     edx, 68h ; 'h'; nIDDlgItem
0x14000230b  call    cs:__imp_GetDlgItem
0x140002311  mov     rcx, rax; hWnd
0x140002314  lea     rdx, [rsi+28h]; lpString
0x140002318  call    cs:__imp_SetWindowTextW
0x14000231e  jmp     short loc_14000237C
0x140002320  mov     ebx, 6Ch ; 'l'
0x140002325  mov     edx, ebx; nIDDlgItem
0x140002327  call    cs:__imp_GetDlgItem
0x14000232d  mov     rcx, rax; hWnd
0x140002330  xor     edx, edx; bEnable
0x140002332  call    cs:__imp_EnableWindow
0x140002338  mov     rcx, [rdi]; hDlg
0x14000233b  lea     edx, [rbx-4]; nIDDlgItem
0x14000233e  call    cs:__imp_GetDlgItem
0x140002344  mov     rcx, rax; hWnd
0x140002347  xor     edx, edx; bEnable
0x140002349  call    cs:__imp_EnableWindow
0x14000234f  mov     rcx, [rdi]; hDlg
0x140002352  mov     edx, ebx; nIDDlgItem
0x140002354  call    cs:__imp_GetDlgItem
0x14000235a  mov     rcx, rax; hWnd
0x14000235d  xor     edx, edx; nCmdShow
0x14000235f  call    cs:__imp_ShowWindow
0x140002365  mov     rcx, [rdi]; hDlg
0x140002368  lea     edx, [rbx-4]; nIDDlgItem
0x14000236b  call    cs:__imp_GetDlgItem
0x140002371  mov     rcx, rax; hWnd
0x140002374  xor     edx, edx; nCmdShow
0x140002376  call    cs:__imp_ShowWindow
0x14000237c  mov     r9, [rsi+270h]; lParam
0x140002383  test    r9, r9
0x140002386  jz      short loc_140002398
0x140002388  mov     rcx, [rdi]; hWnd
0x14000238b  xor     r8d, r8d; wParam
0x14000238e  lea     edx, [r8+0Ch]; Msg
0x140002392  call    cs:__imp_SendMessageW
0x140002398  xor     eax, eax
0x14000239a  add     rsp, 38h
0x14000239e  pop     rdi
0x14000239f  pop     rsi
0x1400023a0  pop     rbp
0x1400023a1  pop     rbx
0x1400023a2  retn
```
