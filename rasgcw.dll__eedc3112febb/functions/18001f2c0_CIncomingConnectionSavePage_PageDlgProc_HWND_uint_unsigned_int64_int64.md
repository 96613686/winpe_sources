# CIncomingConnectionSavePage::PageDlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18001f2c0`
- end: `0x18001f44e`
- name: `?PageDlgProc@CIncomingConnectionSavePage@@CAHPEAUHWND__@@I_K_J@Z`
- size: `398`
- prototype: `__int64 __fastcall(HWND hWnd, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18001f174`
- `0x18001f2c0`
- `0x18001f680`

## import_xrefs

- `USER32!PostMessageW` at `0x18001f3e1`
- `USER32!PostMessageW` at `0x18001f401`
- `USER32!PostMessageW` at `0x18001f42e`
- `USER32!PostMessageW` at `0x18001f3e1`
- `USER32!PostMessageW` at `0x18001f401`
- `USER32!PostMessageW` at `0x18001f42e`
- `USER32!GetPropW` at `0x18001f311`
- `USER32!GetPropW` at `0x18001f311`
- `USER32!RemovePropW` at `0x18001f306`
- `USER32!RemovePropW` at `0x18001f306`
- `USER32!ShowWindow` at `0x18001f39d`
- `USER32!ShowWindow` at `0x18001f3a9`
- `USER32!ShowWindow` at `0x18001f39d`
- `USER32!ShowWindow` at `0x18001f3a9`
- `USER32!SetPropW` at `0x18001f2f2`
- `USER32!SetPropW` at `0x18001f2f2`
- `USER32!GetDlgItem` at `0x18001f355`
- `USER32!GetDlgItem` at `0x18001f368`
- `USER32!GetDlgItem` at `0x18001f37b`
- `USER32!GetDlgItem` at `0x18001f38e`
- `USER32!GetDlgItem` at `0x18001f355`
- `USER32!GetDlgItem` at `0x18001f368`
- `USER32!GetDlgItem` at `0x18001f37b`
- `USER32!GetDlgItem` at `0x18001f38e`
- `USER32!GetParent` at `0x18001f3cd`
- `USER32!GetParent` at `0x18001f3ea`
- `USER32!GetParent` at `0x18001f419`
- `USER32!GetParent` at `0x18001f3cd`
- `USER32!GetParent` at `0x18001f3ea`
- `USER32!GetParent` at `0x18001f419`

## pseudocode

```c
__int64 __fastcall CIncomingConnectionSavePage::PageDlgProc(
        HWND hWnd,
        int a2,
        __int64 a3,
        CIncomingConnectionSavePage **a4)
{
  CIncomingConnectionSavePage *v4; // rbx
  CIncomingConnectionSavePage *PropW; // rax
  CIncomingConnectionSavePage *v9; // rbp
  int v10; // edi
  int v11; // edi
  HWND DlgItem; // rax
  HWND v13; // rcx
  HWND v14; // rax
  HWND v15; // rcx
  HWND v16; // rax
  HWND v17; // rcx
  HWND v18; // rax
  HWND Parent; // rax
  HWND v21; // rax
  HWND v22; // rax

  v4 = (CIncomingConnectionSavePage *)a4;
  if ( a2 == 272 )
  {
    if ( *(_DWORD *)a4 == 104 )
      v4 = a4[6];
    SetPropW(hWnd, L"_Win32_this_", v4);
    goto LABEL_13;
  }
  if ( a2 == 2 )
  {
    RemovePropW(hWnd, L"_Win32_this_");
    return 0;
  }
  PropW = (CIncomingConnectionSavePage *)GetPropW(hWnd, L"_Win32_this_");
  v9 = PropW;
  v10 = a2 - 78;
  if ( !v10 )
  {
    if ( *((_DWORD *)v4 + 4) == -207 )
    {
      CIncomingConnectionSavePage::SaveRassrvSettings(PropW);
      return 1;
    }
    if ( *((_DWORD *)v4 + 4) != -200 )
      return 0;
    Parent = GetParent(hWnd);
    PostMessageW(Parent, 0x470u, 0, 0);
    v21 = GetParent(hWnd);
    PostMessageW(v21, 0x48Au, 0, 6);
LABEL_18:
    if ( !(unsigned int)CIncomingConnectionSavePage::LaunchRASServiceStartThread(v9, v9) )
    {
      v22 = GetParent(hWnd);
      PostMessageW(v22, 0x471u, 5u, 0);
    }
    return 1;
  }
  v11 = v10 - 194;
  if ( v11 )
  {
    if ( v11 != 1 || a3 != 2023 )
      return 0;
    goto LABEL_18;
  }
  v4 = PropW;
LABEL_13:
  *((_QWORD *)v4 + 8) = hWnd;
  DlgItem = GetDlgItem(hWnd, 2020);
  v13 = (HWND)*((_QWORD *)v4 + 8);
  *((_QWORD *)v4 + 9) = DlgItem;
  v14 = GetDlgItem(v13, 2021);
  v15 = (HWND)*((_QWORD *)v4 + 8);
  *((_QWORD *)v4 + 10) = v14;
  v16 = GetDlgItem(v15, 2023);
  v17 = (HWND)*((_QWORD *)v4 + 8);
  *((_QWORD *)v4 + 11) = v16;
  v18 = GetDlgItem(v17, 2022);
  *((_QWORD *)v4 + 12) = v18;
  ShowWindow(v18, 0);
  ShowWindow(*((HWND *)v4 + 11), 0);
  return 1;
}

```

## disassembly

```asm
0x18001f2c0  push    rbx
0x18001f2c2  push    rbp
0x18001f2c3  push    rsi
0x18001f2c4  push    rdi
0x18001f2c5  push    r14
0x18001f2c7  sub     rsp, 30h
0x18001f2cb  mov     rbx, r9
0x18001f2ce  mov     r14, r8
0x18001f2d1  mov     edi, edx
0x18001f2d3  mov     rsi, rcx
0x18001f2d6  cmp     edx, 110h
0x18001f2dc  jnz     short loc_18001F2FA
0x18001f2de  cmp     dword ptr [r9], 68h ; 'h'
0x18001f2e2  jnz     short loc_18001F2E8
0x18001f2e4  mov     rbx, [r9+30h]
0x18001f2e8  mov     r8, rbx; hData
0x18001f2eb  lea     rdx, aWin32This_10; "_Win32_this_"
0x18001f2f2  call    cs:__imp_SetPropW
0x18001f2f8  jmp     short loc_18001F349
0x18001f2fa  lea     rdx, aWin32This_10; "_Win32_this_"
0x18001f301  cmp     edi, 2
0x18001f304  jnz     short loc_18001F311
0x18001f306  call    cs:__imp_RemovePropW
0x18001f30c  jmp     loc_18001F3C6
0x18001f311  call    cs:__imp_GetPropW
0x18001f317  mov     rbp, rax
0x18001f31a  sub     edi, 4Eh ; 'N'
0x18001f31d  jz      loc_18001F3B4
0x18001f323  sub     edi, 0C2h
0x18001f329  jz      short loc_18001F346
0x18001f32b  cmp     edi, 1
0x18001f32e  jnz     loc_18001F3C6
0x18001f334  cmp     r14, 7E7h
0x18001f33b  jz      loc_18001F407
0x18001f341  jmp     loc_18001F3C6
0x18001f346  mov     rbx, rbp
0x18001f349  mov     edx, 7E4h; nIDDlgItem
0x18001f34e  mov     [rbx+40h], rsi
0x18001f352  mov     rcx, rsi; hDlg
0x18001f355  call    cs:__imp_GetDlgItem
0x18001f35b  mov     rcx, [rbx+40h]; hDlg
0x18001f35f  mov     edx, 7E5h; nIDDlgItem
0x18001f364  mov     [rbx+48h], rax
0x18001f368  call    cs:__imp_GetDlgItem
0x18001f36e  mov     rcx, [rbx+40h]; hDlg
0x18001f372  mov     edx, 7E7h; nIDDlgItem
0x18001f377  mov     [rbx+50h], rax
0x18001f37b  call    cs:__imp_GetDlgItem
0x18001f381  mov     rcx, [rbx+40h]; hDlg
0x18001f385  mov     edx, 7E6h; nIDDlgItem
0x18001f38a  mov     [rbx+58h], rax
0x18001f38e  call    cs:__imp_GetDlgItem
0x18001f394  mov     rcx, rax; hWnd
0x18001f397  mov     [rbx+60h], rax
0x18001f39b  xor     edx, edx; nCmdShow
0x18001f39d  call    cs:__imp_ShowWindow
0x18001f3a3  mov     rcx, [rbx+58h]; hWnd
0x18001f3a7  xor     edx, edx; nCmdShow
0x18001f3a9  call    cs:__imp_ShowWindow
0x18001f3af  jmp     loc_18001F43E
0x18001f3b4  cmp     dword ptr [rbx+10h], 0FFFFFF31h
0x18001f3bb  jz      short loc_18001F436
0x18001f3bd  cmp     dword ptr [rbx+10h], 0FFFFFF38h
0x18001f3c4  jz      short loc_18001F3CA
0x18001f3c6  xor     eax, eax
0x18001f3c8  jmp     short loc_18001F443
0x18001f3ca  mov     rcx, rsi; hWnd
0x18001f3cd  call    cs:__imp_GetParent
0x18001f3d3  xor     r9d, r9d; lParam
0x18001f3d6  xor     r8d, r8d; wParam
0x18001f3d9  mov     rcx, rax; hWnd
0x18001f3dc  mov     edx, 470h; Msg
0x18001f3e1  call    cs:__imp_PostMessageW
0x18001f3e7  mov     rcx, rsi; hWnd
0x18001f3ea  call    cs:__imp_GetParent
0x18001f3f0  mov     r9d, 6; lParam
0x18001f3f6  xor     r8d, r8d; wParam
0x18001f3f9  mov     rcx, rax; hWnd
0x18001f3fc  mov     edx, 48Ah; Msg
0x18001f401  call    cs:__imp_PostMessageW
0x18001f407  mov     rdx, rbp; struct CIncomingConnectionSavePage *
0x18001f40a  mov     rcx, rbp; this
0x18001f40d  call    ?LaunchRASServiceStartThread@CIncomingConnectionSavePage@@AEAAHPEAV1@@Z; CIncomingConnectionSavePage::LaunchRASServiceStartThread(CIncomingConnectionSavePage *)
0x18001f412  test    eax, eax
0x18001f414  jnz     short loc_18001F43E
0x18001f416  mov     rcx, rsi; hWnd
0x18001f419  call    cs:__imp_GetParent
0x18001f41f  xor     r9d, r9d; lParam
0x18001f422  mov     edx, 471h; Msg
0x18001f427  mov     rcx, rax; hWnd
0x18001f42a  lea     r8d, [r9+5]; wParam
0x18001f42e  call    cs:__imp_PostMessageW
0x18001f434  jmp     short loc_18001F43E
0x18001f436  mov     rcx, rbp; this
0x18001f439  call    ?SaveRassrvSettings@CIncomingConnectionSavePage@@AEAAHXZ; CIncomingConnectionSavePage::SaveRassrvSettings(void)
0x18001f43e  mov     eax, 1
0x18001f443  add     rsp, 30h
0x18001f447  pop     r14
0x18001f449  pop     rdi
0x18001f44a  pop     rsi
0x18001f44b  pop     rbp
0x18001f44c  pop     rbx
0x18001f44d  retn
```
