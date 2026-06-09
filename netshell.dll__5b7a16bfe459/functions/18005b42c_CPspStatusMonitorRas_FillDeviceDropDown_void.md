# CPspStatusMonitorRas::FillDeviceDropDown(void)

- ea: `0x18005b42c`
- end: `0x18005b694`
- name: `?FillDeviceDropDown@CPspStatusMonitorRas@@AEAAXXZ`
- size: `616`
- prototype: `void __fastcall(CPspStatusMonitorRas *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18005d100`

## callees

- `0x1800172ac`
- `0x1800174d0`
- `0x180017714`
- `0x18001e1e0`
- `0x18005b42c`

## import_xrefs

- `USER32!GetWindowRect` at `0x18005b59d`
- `USER32!GetWindowRect` at `0x18005b5cd`
- `USER32!GetWindowRect` at `0x18005b59d`
- `USER32!GetWindowRect` at `0x18005b5cd`
- `USER32!ShowWindow` at `0x18005b582`
- `USER32!ShowWindow` at `0x18005b582`
- `USER32!EnableWindow` at `0x18005b64f`
- `USER32!EnableWindow` at `0x18005b64f`
- `USER32!SendDlgItemMessageW` at `0x18005b474`
- `USER32!SendDlgItemMessageW` at `0x18005b4a9`
- `USER32!SendDlgItemMessageW` at `0x18005b4cc`
- `USER32!SendDlgItemMessageW` at `0x18005b4ec`
- `USER32!SendDlgItemMessageW` at `0x18005b50a`
- `USER32!SendDlgItemMessageW` at `0x18005b52d`
- `USER32!SendDlgItemMessageW` at `0x18005b474`
- `USER32!SendDlgItemMessageW` at `0x18005b4a9`
- `USER32!SendDlgItemMessageW` at `0x18005b4cc`
- `USER32!SendDlgItemMessageW` at `0x18005b4ec`
- `USER32!SendDlgItemMessageW` at `0x18005b50a`
- `USER32!SendDlgItemMessageW` at `0x18005b52d`
- `USER32!SetDlgItemInt` at `0x18005b66d`
- `USER32!SetDlgItemInt` at `0x18005b66d`
- `USER32!MoveWindow` at `0x18005b632`
- `USER32!MoveWindow` at `0x18005b632`

## pseudocode

```c
void __fastcall CPspStatusMonitorRas::FillDeviceDropDown(HWND *this)
{
  HWND *v1; // rdi
  _QWORD *v3; // rbx
  _QWORD *lParam; // rax
  int v5; // eax
  int v6; // eax
  struct CRasDeviceInfo *v7; // rax
  unsigned int v8; // ebx
  HWND *DlgItem; // rax
  HWND v10; // rcx
  HWND *v11; // rax
  int v12; // r9d
  HWND *v13; // rax
  HWND *v14; // rax
  UINT ActiveDeviceCount; // eax
  _BYTE v16[8]; // [rsp+30h] [rbp-40h] BYREF
  struct tagRECT si128; // [rsp+38h] [rbp-38h] BYREF
  int v18; // [rsp+48h] [rbp-28h]
  int v19; // [rsp+4Ch] [rbp-24h]
  struct tagRECT Rect; // [rsp+50h] [rbp-20h] BYREF

  v1 = this + 1;
  SendDlgItemMessageW(this[1], 24206, 0x14Bu, 0, 0);
  v3 = this[15];
  while ( 1 )
  {
    v3 = (_QWORD *)*v3;
    if ( v3 == (_QWORD *)this[15] )
      break;
    lParam = (_QWORD *)v3[2];
    if ( lParam[3] > 7u )
      lParam = (_QWORD *)*lParam;
    v5 = SendDlgItemMessageW(*v1, 24206, 0x143u, 0, (LPARAM)lParam);
    if ( v5 != -1 )
      SendDlgItemMessageW(*v1, 24206, 0x151u, v5, v3[2]);
  }
  SendDlgItemMessageW(*v1, 24206, 0x14Eu, 0, 0);
  v6 = SendDlgItemMessageW(*v1, 24206, 0x147u, 0, 0);
  if ( v6 != -1 )
  {
    v7 = (struct CRasDeviceInfo *)SendDlgItemMessageW(*v1, 24206, 0x150u, v6, 0);
    CPspStatusMonitorRas::SetButtonStatus((CPspStatusMonitorRas *)this, v7);
  }
  if ( (unsigned __int64)this[16] > 1 )
  {
    ActiveDeviceCount = CPspStatusMonitorRas::GetActiveDeviceCount((CPspStatusMonitorRas *)this);
    SetDlgItemInt(*v1, 24204, ActiveDeviceCount, 0);
  }
  else
  {
    v8 = 0;
    si128 = (struct tagRECT)_mm_load_si128((const __m128i *)&_xmm);
    v18 = 24201;
    v19 = 24207;
    do
    {
      DlgItem = (HWND *)ATL::CWindow::GetDlgItem(v1, v16, *((unsigned int *)&si128.left + (int)v8));
      ShowWindow(*DlgItem, 0);
      ++v8;
    }
    while ( v8 < 6 );
    v10 = *v1;
    Rect = 0;
    if ( GetWindowRect(v10, &Rect) )
    {
      si128 = 0;
      v11 = (HWND *)ATL::CWindow::GetDlgItem(v1, v16, 24205);
      if ( GetWindowRect(*v11, &si128) )
      {
        v12 = Rect.right - si128.right;
        si128.left -= Rect.left;
        si128.top -= Rect.top;
        si128.right -= Rect.left;
        si128.bottom = Rect.bottom - v12 - Rect.top;
        v13 = (HWND *)ATL::CWindow::GetDlgItem(v1, v16, 24205);
        MoveWindow(*v13, si128.left, si128.top, si128.right - si128.left, si128.bottom - si128.top, 1);
      }
    }
    v14 = (HWND *)ATL::CWindow::GetDlgItem(v1, v16, 24202);
    EnableWindow(*v14, 0);
  }
}

```

## disassembly

```asm
0x18005b42c  mov     [rsp-18h+arg_8], rbx
0x18005b431  mov     [rsp-18h+arg_10], rsi
0x18005b436  push    rbp
0x18005b437  push    rdi
0x18005b438  push    r15
0x18005b43a  mov     rbp, rsp
0x18005b43d  sub     rsp, 70h
0x18005b441  mov     rax, cs:__security_cookie
0x18005b448  xor     rax, rsp
0x18005b44b  mov     [rbp+var_10], rax
0x18005b44f  lea     rdi, [rcx+8]
0x18005b453  mov     [rsp+70h+lParam], 0; lParam
0x18005b45c  mov     rsi, rcx
0x18005b45f  mov     r15d, 5E8Eh
0x18005b465  mov     rcx, [rdi]; hDlg
0x18005b468  mov     edx, r15d; nIDDlgItem
0x18005b46b  xor     r9d, r9d; wParam
0x18005b46e  mov     r8d, 14Bh; Msg
0x18005b474  call    cs:__imp_SendDlgItemMessageW
0x18005b47a  mov     rbx, [rsi+78h]
0x18005b47e  mov     rbx, [rbx]
0x18005b481  cmp     rbx, [rsi+78h]
0x18005b485  jz      short loc_18005B4D4
0x18005b487  mov     rax, [rbx+10h]
0x18005b48b  cmp     qword ptr [rax+18h], 7
0x18005b490  jbe     short loc_18005B495
0x18005b492  mov     rax, [rax]
0x18005b495  mov     rcx, [rdi]; hDlg
0x18005b498  xor     r9d, r9d; wParam
0x18005b49b  mov     r8d, 143h; Msg
0x18005b4a1  mov     [rsp+70h+lParam], rax; lParam
0x18005b4a6  mov     edx, r15d; nIDDlgItem
0x18005b4a9  call    cs:__imp_SendDlgItemMessageW
0x18005b4af  cmp     eax, 0FFFFFFFFh
0x18005b4b2  jz      short loc_18005B47E
0x18005b4b4  mov     rcx, [rdi]; hDlg
0x18005b4b7  mov     r8d, 151h; Msg
0x18005b4bd  movsxd  r9, eax; wParam
0x18005b4c0  mov     edx, r15d; nIDDlgItem
0x18005b4c3  mov     rax, [rbx+10h]
0x18005b4c7  mov     [rsp+70h+lParam], rax; lParam
0x18005b4cc  call    cs:__imp_SendDlgItemMessageW
0x18005b4d2  jmp     short loc_18005B47E
0x18005b4d4  mov     rcx, [rdi]; hDlg
0x18005b4d7  xor     r9d, r9d; wParam
0x18005b4da  mov     r8d, 14Eh; Msg
0x18005b4e0  mov     [rsp+70h+lParam], 0; lParam
0x18005b4e9  mov     edx, r15d; nIDDlgItem
0x18005b4ec  call    cs:__imp_SendDlgItemMessageW
0x18005b4f2  mov     rcx, [rdi]; hDlg
0x18005b4f5  xor     r9d, r9d; wParam
0x18005b4f8  mov     r8d, 147h; Msg
0x18005b4fe  mov     [rsp+70h+lParam], 0; lParam
0x18005b507  mov     edx, r15d; nIDDlgItem
0x18005b50a  call    cs:__imp_SendDlgItemMessageW
0x18005b510  cmp     eax, 0FFFFFFFFh
0x18005b513  jz      short loc_18005B53E
0x18005b515  mov     rcx, [rdi]; hDlg
0x18005b518  mov     r8d, 150h; Msg
0x18005b51e  movsxd  r9, eax; wParam
0x18005b521  mov     edx, r15d; nIDDlgItem
0x18005b524  mov     [rsp+70h+lParam], 0; lParam
0x18005b52d  call    cs:__imp_SendDlgItemMessageW
0x18005b533  mov     rdx, rax; struct CRasDeviceInfo *
0x18005b536  mov     rcx, rsi; this
0x18005b539  call    ?SetButtonStatus@CPspStatusMonitorRas@@AEAAXPEAVCRasDeviceInfo@@@Z; CPspStatusMonitorRas::SetButtonStatus(CRasDeviceInfo *)
0x18005b53e  cmp     qword ptr [rsi+80h], 1
0x18005b546  ja      loc_18005B657
0x18005b54c  movdqa  xmm0, cs:__xmm@00005e8a00005e8c00005e8b00005e8e
0x18005b554  xor     ebx, ebx
0x18005b556  movdqu  xmmword ptr [rbp+var_38.left], xmm0
0x18005b55b  mov     [rbp+var_28], 5E89h
0x18005b562  mov     [rbp+var_24], 5E8Fh
0x18005b569  movsxd  r8, ebx
0x18005b56c  lea     rdx, [rbp+var_40]
0x18005b570  mov     rcx, rdi
0x18005b573  mov     r8d, [rbp+r8*4+var_38.left]
0x18005b578  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x18005b57d  xor     edx, edx; nCmdShow
0x18005b57f  mov     rcx, [rax]; hWnd
0x18005b582  call    cs:__imp_ShowWindow
0x18005b588  inc     ebx
0x18005b58a  cmp     ebx, 6
0x18005b58d  jb      short loc_18005B569
0x18005b58f  mov     rcx, [rdi]; hWnd
0x18005b592  lea     rdx, [rbp+Rect]; lpRect
0x18005b596  xorps   xmm0, xmm0
0x18005b599  movups  xmmword ptr [rbp+Rect.left], xmm0
0x18005b59d  call    cs:__imp_GetWindowRect
0x18005b5a3  test    eax, eax
0x18005b5a5  jz      loc_18005B638
0x18005b5ab  xorps   xmm0, xmm0
0x18005b5ae  lea     rdx, [rbp+var_40]
0x18005b5b2  mov     ebx, 5E8Dh
0x18005b5b7  mov     rcx, rdi
0x18005b5ba  mov     r8d, ebx
0x18005b5bd  movups  xmmword ptr [rbp+var_38.left], xmm0
0x18005b5c1  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x18005b5c6  lea     rdx, [rbp+var_38]; lpRect
0x18005b5ca  mov     rcx, [rax]; hWnd
0x18005b5cd  call    cs:__imp_GetWindowRect
0x18005b5d3  test    eax, eax
0x18005b5d5  jz      short loc_18005B638
0x18005b5d7  mov     ecx, [rbp+Rect.right]
0x18005b5da  mov     r8d, ebx
0x18005b5dd  mov     eax, [rbp+Rect.left]
0x18005b5e0  mov     r9d, ecx
0x18005b5e3  sub     r9d, [rbp+var_38.right]
0x18005b5e7  sub     [rbp+var_38.left], eax
0x18005b5ea  sub     ecx, r9d
0x18005b5ed  mov     edx, [rbp+Rect.top]
0x18005b5f0  sub     ecx, eax
0x18005b5f2  mov     eax, [rbp+Rect.bottom]
0x18005b5f5  sub     [rbp+var_38.top], edx
0x18005b5f8  sub     eax, r9d
0x18005b5fb  sub     eax, edx
0x18005b5fd  mov     [rbp+var_38.right], ecx
0x18005b600  lea     rdx, [rbp+var_40]
0x18005b604  mov     [rbp+var_38.bottom], eax
0x18005b607  mov     rcx, rdi
0x18005b60a  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x18005b60f  mov     ecx, [rbp+var_38.bottom]
0x18005b612  mov     r8d, [rbp+var_38.top]; Y
0x18005b616  sub     ecx, r8d
0x18005b619  mov     r9d, [rbp+var_38.right]
0x18005b61d  mov     edx, [rbp+var_38.left]; X
0x18005b620  sub     r9d, edx; nWidth
0x18005b623  mov     [rsp+70h+bRepaint], 1; bRepaint
0x18005b62b  mov     dword ptr [rsp+70h+lParam], ecx; nHeight
0x18005b62f  mov     rcx, [rax]; hWnd
0x18005b632  call    cs:__imp_MoveWindow
0x18005b638  mov     r8d, 5E8Ah
0x18005b63e  lea     rdx, [rbp+var_40]
0x18005b642  mov     rcx, rdi
0x18005b645  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x18005b64a  xor     edx, edx; bEnable
0x18005b64c  mov     rcx, [rax]; hWnd
0x18005b64f  call    cs:__imp_EnableWindow
0x18005b655  jmp     short loc_18005B673
0x18005b657  mov     rcx, rsi; this
0x18005b65a  call    ?GetActiveDeviceCount@CPspStatusMonitorRas@@AEAAIXZ; CPspStatusMonitorRas::GetActiveDeviceCount(void)
0x18005b65f  mov     rcx, [rdi]; hDlg
0x18005b662  xor     r9d, r9d; bSigned
0x18005b665  mov     r8d, eax; uValue
0x18005b668  mov     edx, 5E8Ch; nIDDlgItem
0x18005b66d  call    cs:__imp_SetDlgItemInt
0x18005b673  mov     rcx, [rbp+var_10]
0x18005b677  xor     rcx, rsp; StackCookie
0x18005b67a  call    __security_check_cookie
0x18005b67f  lea     r11, [rsp+70h+var_s0]
0x18005b684  mov     rbx, [r11+28h]
0x18005b688  mov     rsi, [r11+30h]
0x18005b68c  mov     rsp, r11
0x18005b68f  pop     r15
0x18005b691  pop     rdi
0x18005b692  pop     rbp
0x18005b693  retn
```
