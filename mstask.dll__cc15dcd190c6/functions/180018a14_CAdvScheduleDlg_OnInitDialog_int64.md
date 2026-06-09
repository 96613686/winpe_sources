# CAdvScheduleDlg::_OnInitDialog(__int64)

- ea: `0x180018a14`
- end: `0x180018ed4`
- name: `?_OnInitDialog@CAdvScheduleDlg@@AEAA_J_J@Z`
- size: `1216`
- prototype: `__int64 __fastcall(CAdvScheduleDlg *__hidden this, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x180018540`

## callees

- `0x1800135a4`
- `0x1800185d8`
- `0x180018a14`
- `0x18001aac0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180018a72`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180018aa7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180018a72`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180018aa7`
- `USER32!SendMessageW` at `0x180018a8a`
- `USER32!SendMessageW` at `0x180018aba`
- `USER32!SendMessageW` at `0x180018bec`
- `USER32!SendMessageW` at `0x180018c4e`
- `USER32!SendMessageW` at `0x180018c88`
- `USER32!SendMessageW` at `0x180018da8`
- `USER32!SendMessageW` at `0x180018e6a`
- `USER32!SendMessageW` at `0x180018a8a`
- `USER32!SendMessageW` at `0x180018aba`
- `USER32!SendMessageW` at `0x180018bec`
- `USER32!SendMessageW` at `0x180018c4e`
- `USER32!SendMessageW` at `0x180018c88`
- `USER32!SendMessageW` at `0x180018da8`
- `USER32!SendMessageW` at `0x180018e6a`
- `USER32!EnableWindow` at `0x180018c93`
- `USER32!EnableWindow` at `0x180018cbc`
- `USER32!EnableWindow` at `0x180018cdb`
- `USER32!EnableWindow` at `0x180018cfa`
- `USER32!EnableWindow` at `0x180018d19`
- `USER32!EnableWindow` at `0x180018e75`
- `USER32!EnableWindow` at `0x180018c93`
- `USER32!EnableWindow` at `0x180018cbc`
- `USER32!EnableWindow` at `0x180018cdb`
- `USER32!EnableWindow` at `0x180018cfa`
- `USER32!EnableWindow` at `0x180018d19`
- `USER32!EnableWindow` at `0x180018e75`
- `USER32!CheckDlgButton` at `0x180018c08`
- `USER32!CheckDlgButton` at `0x180018c59`
- `USER32!CheckDlgButton` at `0x180018d39`
- `USER32!CheckDlgButton` at `0x180018e91`
- `USER32!CheckDlgButton` at `0x180018e9c`
- `USER32!CheckDlgButton` at `0x180018c08`
- `USER32!CheckDlgButton` at `0x180018c59`
- `USER32!CheckDlgButton` at `0x180018d39`
- `USER32!CheckDlgButton` at `0x180018e91`
- `USER32!CheckDlgButton` at `0x180018e9c`
- `USER32!GetDlgItem` at `0x180018a52`
- `USER32!GetDlgItem` at `0x180018bcf`
- `USER32!GetDlgItem` at `0x180018c36`
- `USER32!GetDlgItem` at `0x180018c68`
- `USER32!GetDlgItem` at `0x180018cac`
- `USER32!GetDlgItem` at `0x180018ccb`
- `USER32!GetDlgItem` at `0x180018cea`
- `USER32!GetDlgItem` at `0x180018d09`
- `USER32!GetDlgItem` at `0x180018e4a`
- `USER32!GetDlgItem` at `0x180018a52`
- `USER32!GetDlgItem` at `0x180018bcf`
- `USER32!GetDlgItem` at `0x180018c36`
- `USER32!GetDlgItem` at `0x180018c68`
- `USER32!GetDlgItem` at `0x180018cac`
- `USER32!GetDlgItem` at `0x180018ccb`
- `USER32!GetDlgItem` at `0x180018cea`
- `USER32!GetDlgItem` at `0x180018d09`
- `USER32!GetDlgItem` at `0x180018e4a`
- `USER32!SendDlgItemMessageW` at `0x180018add`
- `USER32!SendDlgItemMessageW` at `0x180018afb`
- `USER32!SendDlgItemMessageW` at `0x180018b19`
- `USER32!SendDlgItemMessageW` at `0x180018b3f`
- `USER32!SendDlgItemMessageW` at `0x180018b60`
- `USER32!SendDlgItemMessageW` at `0x180018b82`
- `USER32!SendDlgItemMessageW` at `0x180018d76`
- `USER32!SendDlgItemMessageW` at `0x180018d94`
- `USER32!SendDlgItemMessageW` at `0x180018e1b`
- `USER32!SendDlgItemMessageW` at `0x180018e3b`
- `USER32!SendDlgItemMessageW` at `0x180018add`
- `USER32!SendDlgItemMessageW` at `0x180018afb`
- `USER32!SendDlgItemMessageW` at `0x180018b19`
- `USER32!SendDlgItemMessageW` at `0x180018b3f`
- `USER32!SendDlgItemMessageW` at `0x180018b60`
- `USER32!SendDlgItemMessageW` at `0x180018b82`
- `USER32!SendDlgItemMessageW` at `0x180018d76`
- `USER32!SendDlgItemMessageW` at `0x180018d94`
- `USER32!SendDlgItemMessageW` at `0x180018e1b`
- `USER32!SendDlgItemMessageW` at `0x180018e3b`
- `USER32!CheckRadioButton` at `0x180018dbf`
- `USER32!CheckRadioButton` at `0x180018dbf`

## pseudocode

```c
__int64 __fastcall CAdvScheduleDlg::_OnInitDialog(CAdvScheduleDlg *this, unsigned int a2)
{
  HWND DlgItem; // r14
  __int64 v4; // rcx
  LPARAM *v5; // rax
  __int64 v6; // rcx
  __int16 v7; // ax
  HWND v8; // rcx
  HWND v9; // rax
  HWND v10; // rcx
  __int64 v11; // rcx
  __int16 v12; // ax
  HWND v13; // rcx
  HWND v14; // rax
  HWND v15; // rax
  HWND v16; // rdi
  HWND v17; // rax
  HWND v18; // rax
  HWND v19; // rax
  HWND v20; // rax
  HWND v21; // rcx
  __int64 v22; // r8
  HWND v23; // rcx
  unsigned int v24; // edx
  WPARAM v25; // r8
  unsigned int v26; // r8d
  unsigned int v27; // edx
  unsigned __int16 v28; // r8
  unsigned __int16 v29; // di
  HWND v30; // rax
  HWND v31; // rdi
  LPARAM v33[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Buffer[104]; // [rsp+40h] [rbp-C0h] BYREF

  UpdateTimeFormat((unsigned __int16 *)this + 12, a2);
  DlgItem = GetDlgItem(*((HWND *)this + 1), 1777);
  LoadStringW(g_hInstance, 0x436u, Buffer, 100);
  SendMessageW(DlgItem, 0x143u, 0, (LPARAM)Buffer);
  LoadStringW(g_hInstance, 0x435u, Buffer, 100);
  SendMessageW(DlgItem, 0x143u, 0, (LPARAM)Buffer);
  SendDlgItemMessageW(*((HWND *)this + 1), 1776, 0x465u, 0, 75535);
  SendDlgItemMessageW(*((HWND *)this + 1), 1784, 0x465u, 0, 9999);
  SendDlgItemMessageW(*((HWND *)this + 1), 1786, 0x465u, 0, 59);
  SendDlgItemMessageW(*((HWND *)this + 1), 1775, 0xC5u, 4u, 0);
  SendDlgItemMessageW(*((HWND *)this + 1), 1783, 0xC5u, 4u, 0);
  SendDlgItemMessageW(*((HWND *)this + 1), 1785, 0xC5u, 2u, 0);
  v4 = 16;
  *(_OWORD *)v33 = 0;
  v5 = v33;
  do
  {
    *(_BYTE *)v5 = 0;
    v5 = (LPARAM *)((char *)v5 + 1);
    --v4;
  }
  while ( v4 );
  v6 = *((_QWORD *)this + 2);
  LODWORD(v33[0]) = *(_DWORD *)(v6 + 4);
  v7 = *(_WORD *)(v6 + 8);
  v8 = (HWND)*((_QWORD *)this + 1);
  HIWORD(v33[0]) = v7;
  v9 = GetDlgItem(v8, 1773);
  if ( v9 )
    SendMessageW(v9, 0x1002u, 0, (LPARAM)v33);
  v10 = (HWND)*((_QWORD *)this + 1);
  if ( (*(_BYTE *)(*((_QWORD *)this + 2) + 28LL) & 1) != 0 )
  {
    CheckDlgButton(v10, 1790, 1u);
    v11 = *((_QWORD *)this + 2);
    LODWORD(v33[0]) = *(_DWORD *)(v11 + 10);
    v12 = *(_WORD *)(v11 + 14);
    v13 = (HWND)*((_QWORD *)this + 1);
    HIWORD(v33[0]) = v12;
    v14 = GetDlgItem(v13, 1778);
    if ( v14 )
      SendMessageW(v14, 0x1002u, 0, (LPARAM)v33);
  }
  else
  {
    CheckDlgButton(v10, 1790, 0);
    v15 = GetDlgItem(*((HWND *)this + 1), 1778);
    v16 = v15;
    if ( v15 )
    {
      SendMessageW(v15, 0x1032u, 0, (LPARAM)L" ");
      EnableWindow(v16, 0);
    }
  }
  if ( !*(_DWORD *)(*((_QWORD *)this + 2) + 32LL) )
  {
    v17 = GetDlgItem(*((HWND *)this + 1), 1772);
    if ( v17 )
      EnableWindow(v17, 0);
    v18 = GetDlgItem(*((HWND *)this + 1), 1773);
    if ( v18 )
      EnableWindow(v18, 0);
    v19 = GetDlgItem(*((HWND *)this + 1), 1790);
    if ( v19 )
      EnableWindow(v19, 0);
    v20 = GetDlgItem(*((HWND *)this + 1), 1778);
    if ( v20 )
      EnableWindow(v20, 0);
  }
  v21 = (HWND)*((_QWORD *)this + 1);
  if ( *(_DWORD *)(*((_QWORD *)this + 2) + 24LL) )
  {
    CheckDlgButton(v21, 1774, 1u);
    v22 = *((_QWORD *)this + 2);
    v23 = (HWND)*((_QWORD *)this + 1);
    v24 = *(_DWORD *)(v22 + 24) / 0x3Cu;
    if ( *(_DWORD *)(v22 + 24) == 60 * v24 )
    {
      SendDlgItemMessageW(v23, 1776, 0x467u, 0, (unsigned __int16)v24);
      v25 = 1;
    }
    else
    {
      SendDlgItemMessageW(v23, 1776, 0x467u, 0, *(unsigned __int16 *)(v22 + 24));
      v25 = 0;
    }
    SendMessageW(DlgItem, 0x14Eu, v25, 0);
    CheckRadioButton(*((HWND *)this + 1), 1780, 1781, 1781);
    v26 = *(_DWORD *)(*((_QWORD *)this + 2) + 20LL);
    v27 = v26 / 0x3C;
    v28 = v26 % 0x3C;
    if ( (unsigned __int16)v27 <= 0x270Fu )
      v29 = v28;
    else
      v29 = v28 + 60 * v27 - 10116;
    SendDlgItemMessageW(*((HWND *)this + 1), 1784, 0x467u, 0, (unsigned __int16)v27);
    SendDlgItemMessageW(*((HWND *)this + 1), 1786, 0x467u, 0, v29);
    v30 = GetDlgItem(*((HWND *)this + 1), 1782);
    v31 = v30;
    if ( v30 )
    {
      SendMessageW(v30, 0x1032u, 0, (LPARAM)L" ");
      EnableWindow(v31, 0);
    }
    if ( (*(_BYTE *)(*((_QWORD *)this + 2) + 28LL) & 2) != 0 )
      CheckDlgButton(*((HWND *)this + 1), 1779, 1u);
  }
  else
  {
    CheckDlgButton(v21, 1774, 0);
    CAdvScheduleDlg::_EnableRepeatCtrls(this, 0);
  }
  return 1;
}

```

## disassembly

```asm
0x180018a14  mov     [rsp-8+arg_8], rbx
0x180018a19  mov     [rsp-8+arg_10], rdi
0x180018a1e  push    rbp
0x180018a1f  push    r12
0x180018a21  push    r14
0x180018a23  lea     rbp, [rsp-20h]
0x180018a28  sub     rsp, 120h
0x180018a2f  mov     rax, cs:__security_cookie
0x180018a36  xor     rax, rsp
0x180018a39  mov     [rbp+30h+var_20], rax
0x180018a3d  mov     rbx, rcx
0x180018a40  add     rcx, 18h; unsigned __int16 *
0x180018a44  call    ?UpdateTimeFormat@@YAXPEAGK@Z; UpdateTimeFormat(ushort *,ulong)
0x180018a49  mov     rcx, [rbx+8]; hDlg
0x180018a4d  mov     edx, 6F1h; nIDDlgItem
0x180018a52  call    cs:__imp_GetDlgItem
0x180018a58  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180018a5f  lea     r8, [rsp+130h+Buffer]; lpBuffer
0x180018a64  mov     r9d, 64h ; 'd'; cchBufferMax
0x180018a6a  mov     edx, 436h; uID
0x180018a6f  mov     r14, rax
0x180018a72  call    cs:__imp_LoadStringW
0x180018a78  mov     edi, 143h
0x180018a7d  lea     r9, [rsp+130h+Buffer]; lParam
0x180018a82  mov     edx, edi; Msg
0x180018a84  xor     r8d, r8d; wParam
0x180018a87  mov     rcx, r14; hWnd
0x180018a8a  call    cs:__imp_SendMessageW
0x180018a90  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180018a97  lea     r8, [rsp+130h+Buffer]; lpBuffer
0x180018a9c  mov     r9d, 64h ; 'd'; cchBufferMax
0x180018aa2  mov     edx, 435h; uID
0x180018aa7  call    cs:__imp_LoadStringW
0x180018aad  lea     r9, [rsp+130h+Buffer]; lParam
0x180018ab2  xor     r8d, r8d; wParam
0x180018ab5  mov     edx, edi; Msg
0x180018ab7  mov     rcx, r14; hWnd
0x180018aba  call    cs:__imp_SendMessageW
0x180018ac0  mov     rcx, [rbx+8]; hDlg
0x180018ac4  mov     edi, 465h
0x180018ac9  mov     r8d, edi; Msg
0x180018acc  mov     [rsp+130h+lParam], 1270Fh; lParam
0x180018ad5  xor     r9d, r9d; wParam
0x180018ad8  mov     edx, 6F0h; nIDDlgItem
0x180018add  call    cs:__imp_SendDlgItemMessageW
0x180018ae3  mov     rcx, [rbx+8]; hDlg
0x180018ae7  xor     r9d, r9d; wParam
0x180018aea  mov     r8d, edi; Msg
0x180018aed  mov     [rsp+130h+lParam], 270Fh; lParam
0x180018af6  mov     edx, 6F8h; nIDDlgItem
0x180018afb  call    cs:__imp_SendDlgItemMessageW
0x180018b01  mov     rcx, [rbx+8]; hDlg
0x180018b05  xor     r9d, r9d; wParam
0x180018b08  mov     r8d, edi; Msg
0x180018b0b  mov     [rsp+130h+lParam], 3Bh ; ';'; lParam
0x180018b14  mov     edx, 6FAh; nIDDlgItem
0x180018b19  call    cs:__imp_SendDlgItemMessageW
0x180018b1f  mov     rcx, [rbx+8]; hDlg
0x180018b23  mov     edi, 4
0x180018b28  mov     r9d, edi; wParam
0x180018b2b  mov     [rsp+130h+lParam], 0; lParam
0x180018b34  mov     edx, 6EFh; nIDDlgItem
0x180018b39  mov     r8d, 0C5h; Msg
0x180018b3f  call    cs:__imp_SendDlgItemMessageW
0x180018b45  mov     rcx, [rbx+8]; hDlg
0x180018b49  mov     r9d, edi; wParam
0x180018b4c  mov     edx, 6F7h; nIDDlgItem
0x180018b51  mov     [rsp+130h+lParam], 0; lParam
0x180018b5a  mov     r8d, 0C5h; Msg
0x180018b60  call    cs:__imp_SendDlgItemMessageW
0x180018b66  mov     rcx, [rbx+8]; hDlg
0x180018b6a  lea     r9d, [rdi-2]; wParam
0x180018b6e  mov     edx, 6F9h; nIDDlgItem
0x180018b73  mov     [rsp+130h+lParam], 0; lParam
0x180018b7c  mov     r8d, 0C5h; Msg
0x180018b82  call    cs:__imp_SendDlgItemMessageW
0x180018b88  xorps   xmm0, xmm0
0x180018b8b  lea     ecx, [rdi+0Ch]
0x180018b8e  movups  xmmword ptr [rsp+130h+var_100], xmm0
0x180018b93  lea     rax, [rsp+130h+var_100]
0x180018b98  lea     r12d, [rdi-3]
0x180018b9c  mov     byte ptr [rax], 0
0x180018b9f  add     rax, r12
0x180018ba2  sub     rcx, r12
0x180018ba5  jnz     short loc_180018B9C
0x180018ba7  mov     rcx, [rbx+10h]
0x180018bab  mov     edx, 6EDh; nIDDlgItem
0x180018bb0  movzx   eax, word ptr [rcx+4]
0x180018bb4  mov     word ptr [rsp+130h+var_100], ax
0x180018bb9  movzx   eax, word ptr [rcx+6]
0x180018bbd  mov     word ptr [rsp+130h+var_100+2], ax
0x180018bc2  movzx   eax, word ptr [rcx+8]
0x180018bc6  mov     rcx, [rbx+8]; hDlg
0x180018bca  mov     word ptr [rsp+130h+var_100+6], ax
0x180018bcf  call    cs:__imp_GetDlgItem
0x180018bd5  mov     edi, 1002h
0x180018bda  test    rax, rax
0x180018bdd  jz      short loc_180018BF2
0x180018bdf  lea     r9, [rsp+130h+var_100]; lParam
0x180018be4  xor     r8d, r8d; wParam
0x180018be7  mov     edx, edi; Msg
0x180018be9  mov     rcx, rax; hWnd
0x180018bec  call    cs:__imp_SendMessageW
0x180018bf2  mov     rax, [rbx+10h]
0x180018bf6  mov     edx, 6FEh; nIDButton
0x180018bfb  mov     rcx, [rbx+8]; hDlg
0x180018bff  test    [rax+1Ch], r12b
0x180018c03  jz      short loc_180018C56
0x180018c05  mov     r8d, r12d; uCheck
0x180018c08  call    cs:__imp_CheckDlgButton
0x180018c0e  mov     rcx, [rbx+10h]
0x180018c12  mov     edx, 6F2h; nIDDlgItem
0x180018c17  movzx   eax, word ptr [rcx+0Ah]
0x180018c1b  mov     word ptr [rsp+130h+var_100], ax
0x180018c20  movzx   eax, word ptr [rcx+0Ch]
0x180018c24  mov     word ptr [rsp+130h+var_100+2], ax
0x180018c29  movzx   eax, word ptr [rcx+0Eh]
0x180018c2d  mov     rcx, [rbx+8]; hDlg
0x180018c31  mov     word ptr [rsp+130h+var_100+6], ax
0x180018c36  call    cs:__imp_GetDlgItem
0x180018c3c  test    rax, rax
0x180018c3f  jz      short loc_180018C99
0x180018c41  lea     r9, [rsp+130h+var_100]; lParam
0x180018c46  xor     r8d, r8d; wParam
0x180018c49  mov     edx, edi; Msg
0x180018c4b  mov     rcx, rax; hWnd
0x180018c4e  call    cs:__imp_SendMessageW
0x180018c54  jmp     short loc_180018C99
0x180018c56  xor     r8d, r8d; uCheck
0x180018c59  call    cs:__imp_CheckDlgButton
0x180018c5f  mov     rcx, [rbx+8]; hDlg
0x180018c63  mov     edx, 6F2h; nIDDlgItem
0x180018c68  call    cs:__imp_GetDlgItem
0x180018c6e  mov     rdi, rax
0x180018c71  test    rax, rax
0x180018c74  jz      short loc_180018C99
0x180018c76  lea     r9, lParam; " "
0x180018c7d  xor     r8d, r8d; wParam
0x180018c80  mov     edx, 1032h; Msg
0x180018c85  mov     rcx, rax; hWnd
0x180018c88  call    cs:__imp_SendMessageW
0x180018c8e  xor     edx, edx; bEnable
0x180018c90  mov     rcx, rdi; hWnd
0x180018c93  call    cs:__imp_EnableWindow
0x180018c99  mov     rax, [rbx+10h]
0x180018c9d  cmp     dword ptr [rax+20h], 0
0x180018ca1  jnz     short loc_180018D1F
0x180018ca3  mov     rcx, [rbx+8]; hDlg
0x180018ca7  mov     edx, 6ECh; nIDDlgItem
0x180018cac  call    cs:__imp_GetDlgItem
0x180018cb2  test    rax, rax
0x180018cb5  jz      short loc_180018CC2
0x180018cb7  xor     edx, edx; bEnable
0x180018cb9  mov     rcx, rax; hWnd
0x180018cbc  call    cs:__imp_EnableWindow
0x180018cc2  mov     rcx, [rbx+8]; hDlg
0x180018cc6  mov     edx, 6EDh; nIDDlgItem
0x180018ccb  call    cs:__imp_GetDlgItem
0x180018cd1  test    rax, rax
0x180018cd4  jz      short loc_180018CE1
0x180018cd6  xor     edx, edx; bEnable
0x180018cd8  mov     rcx, rax; hWnd
0x180018cdb  call    cs:__imp_EnableWindow
0x180018ce1  mov     rcx, [rbx+8]; hDlg
0x180018ce5  mov     edx, 6FEh; nIDDlgItem
0x180018cea  call    cs:__imp_GetDlgItem
0x180018cf0  test    rax, rax
0x180018cf3  jz      short loc_180018D00
0x180018cf5  xor     edx, edx; bEnable
0x180018cf7  mov     rcx, rax; hWnd
0x180018cfa  call    cs:__imp_EnableWindow
0x180018d00  mov     rcx, [rbx+8]; hDlg
0x180018d04  mov     edx, 6F2h; nIDDlgItem
0x180018d09  call    cs:__imp_GetDlgItem
0x180018d0f  test    rax, rax
0x180018d12  jz      short loc_180018D1F
0x180018d14  xor     edx, edx; bEnable
0x180018d16  mov     rcx, rax; hWnd
0x180018d19  call    cs:__imp_EnableWindow
0x180018d1f  mov     rax, [rbx+10h]
0x180018d23  mov     edx, 6EEh; nIDButton
0x180018d28  mov     rcx, [rbx+8]; hDlg
0x180018d2c  cmp     dword ptr [rax+18h], 0
0x180018d30  jbe     loc_180018E99
0x180018d36  mov     r8d, r12d; uCheck
0x180018d39  call    cs:__imp_CheckDlgButton
0x180018d3f  mov     r8, [rbx+10h]
0x180018d43  mov     edi, 88888889h
0x180018d48  mov     rcx, [rbx+8]; hDlg
0x180018d4c  mov     eax, edi
0x180018d4e  xor     r9d, r9d; wParam
0x180018d51  mul     dword ptr [r8+18h]
0x180018d55  shr     edx, 5
0x180018d58  imul    eax, edx, 3Ch ; '<'
0x180018d5b  cmp     [r8+18h], eax
0x180018d5f  jz      short loc_180018D81
0x180018d61  movzx   eax, word ptr [r8+18h]
0x180018d66  mov     edx, 6F0h; nIDDlgItem
0x180018d6b  mov     r8d, 467h; Msg
0x180018d71  mov     [rsp+130h+lParam], rax; lParam
0x180018d76  call    cs:__imp_SendDlgItemMessageW
0x180018d7c  xor     r8d, r8d
0x180018d7f  jmp     short loc_180018D9D
0x180018d81  movzx   eax, dx
0x180018d84  mov     r8d, 467h; Msg
0x180018d8a  mov     edx, 6F0h; nIDDlgItem
0x180018d8f  mov     [rsp+130h+lParam], rax; lParam
0x180018d94  call    cs:__imp_SendDlgItemMessageW
0x180018d9a  mov     r8, r12; wParam
0x180018d9d  xor     r9d, r9d; lParam
0x180018da0  mov     edx, 14Eh; Msg
0x180018da5  mov     rcx, r14; hWnd
0x180018da8  call    cs:__imp_SendMessageW
0x180018dae  mov     rcx, [rbx+8]; hDlg
0x180018db2  mov     r8d, 6F5h; nIDLastButton
0x180018db8  mov     r9d, r8d; nIDCheckButton
0x180018dbb  lea     edx, [r8-1]; nIDFirstButton
0x180018dbf  call    cs:__imp_CheckRadioButton
0x180018dc5  mov     rcx, [rbx+10h]
0x180018dc9  mov     eax, edi
0x180018dcb  mov     r8d, [rcx+14h]
0x180018dcf  mul     r8d
0x180018dd2  shr     edx, 5
0x180018dd5  movzx   eax, dx
0x180018dd8  imul    ecx, eax, 3Ch ; '<'
0x180018ddb  mov     eax, 270Fh
0x180018de0  sub     r8w, cx
0x180018de4  cmp     dx, ax
0x180018de7  jbe     short loc_180018DFD
0x180018de9  movzx   eax, dx
0x180018dec  imul    edi, eax, 3Ch ; '<'
0x180018def  mov     eax, 2784h
0x180018df4  add     di, r8w
0x180018df8  sub     di, ax
0x180018dfb  jmp     short loc_180018E01
0x180018dfd  movzx   edi, r8w
0x180018e01  mov     rcx, [rbx+8]; hDlg
0x180018e05  xor     r9d, r9d; wParam
0x180018e08  movzx   eax, dx
0x180018e0b  mov     r8d, 467h; Msg
0x180018e11  mov     edx, 6F8h; nIDDlgItem
0x180018e16  mov     [rsp+130h+lParam], rax; lParam
0x180018e1b  call    cs:__imp_SendDlgItemMessageW
0x180018e21  mov     rcx, [rbx+8]; hDlg
0x180018e25  xor     r9d, r9d; wParam
0x180018e28  movzx   eax, di
0x180018e2b  mov     edx, 6FAh; nIDDlgItem
0x180018e30  mov     r8d, 467h; Msg
0x180018e36  mov     [rsp+130h+lParam], rax; lParam
0x180018e3b  call    cs:__imp_SendDlgItemMessageW
0x180018e41  mov     rcx, [rbx+8]; hDlg
0x180018e45  mov     edx, 6F6h; nIDDlgItem
0x180018e4a  call    cs:__imp_GetDlgItem
0x180018e50  mov     rdi, rax
0x180018e53  test    rax, rax
0x180018e56  jz      short loc_180018E7B
0x180018e58  lea     r9, lParam; " "
0x180018e5f  xor     r8d, r8d; wParam
0x180018e62  mov     edx, 1032h; Msg
0x180018e67  mov     rcx, rax; hWnd
0x180018e6a  call    cs:__imp_SendMessageW
0x180018e70  xor     edx, edx; bEnable
0x180018e72  mov     rcx, rdi; hWnd
0x180018e75  call    cs:__imp_EnableWindow
0x180018e7b  mov     rax, [rbx+10h]
0x180018e7f  test    byte ptr [rax+1Ch], 2
0x180018e83  jz      short loc_180018EAC
0x180018e85  mov     rcx, [rbx+8]; hDlg
0x180018e89  mov     r8d, r12d; uCheck
0x180018e8c  mov     edx, 6F3h; nIDButton
0x180018e91  call    cs:__imp_CheckDlgButton
0x180018e97  jmp     short loc_180018EAC
0x180018e99  xor     r8d, r8d; uCheck
0x180018e9c  call    cs:__imp_CheckDlgButton
0x180018ea2  xor     edx, edx; int
0x180018ea4  mov     rcx, rbx; this
0x180018ea7  call    ?_EnableRepeatCtrls@CAdvScheduleDlg@@AEAAXH@Z; CAdvScheduleDlg::_EnableRepeatCtrls(int)
0x180018eac  mov     rax, r12
0x180018eaf  mov     rcx, [rbp+30h+var_20]
0x180018eb3  xor     rcx, rsp; StackCookie
0x180018eb6  call    __security_check_cookie
0x180018ebb  lea     r11, [rsp+130h+var_10]
0x180018ec3  mov     rbx, [r11+28h]
0x180018ec7  mov     rdi, [r11+30h]
0x180018ecb  mov     rsp, r11
0x180018ece  pop     r14
0x180018ed0  pop     r12
0x180018ed2  pop     rbp
0x180018ed3  retn
```
