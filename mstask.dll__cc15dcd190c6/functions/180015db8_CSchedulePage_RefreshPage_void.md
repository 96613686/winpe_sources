# CSchedulePage::_RefreshPage(void)

- ea: `0x180015db8`
- end: `0x1800161b7`
- name: `?_RefreshPage@CSchedulePage@@AEAAHXZ`
- size: `1023`
- prototype: `__int64 __fastcall(CSchedulePage *__hidden this)`
- caller_count: `3`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x180014aa0`
- `0x180015570`
- `0x1800159c0`

## callees

- `0x180013ea0`
- `0x180015db8`
- `0x180016598`
- `0x18001662c`
- `0x180016830`
- `0x1800168a4`
- `0x180016ab0`
- `0x180016b70`
- `0x180016c84`
- `0x18001aac0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180016138`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180016138`
- `USER32!SendMessageW` at `0x180015e64`
- `USER32!SendMessageW` at `0x180015fa0`
- `USER32!SendMessageW` at `0x180016024`
- `USER32!SendMessageW` at `0x18001604f`
- `USER32!SendMessageW` at `0x1800160d4`
- `USER32!SendMessageW` at `0x180016182`
- `USER32!SendMessageW` at `0x180015e64`
- `USER32!SendMessageW` at `0x180015fa0`
- `USER32!SendMessageW` at `0x180016024`
- `USER32!SendMessageW` at `0x18001604f`
- `USER32!SendMessageW` at `0x1800160d4`
- `USER32!SendMessageW` at `0x180016182`
- `USER32!EnableWindow` at `0x180015e00`
- `USER32!EnableWindow` at `0x180015e1f`
- `USER32!EnableWindow` at `0x180015e99`
- `USER32!EnableWindow` at `0x180015f01`
- `USER32!EnableWindow` at `0x180015e00`
- `USER32!EnableWindow` at `0x180015e1f`
- `USER32!EnableWindow` at `0x180015e99`
- `USER32!EnableWindow` at `0x180015f01`
- `USER32!CheckDlgButton` at `0x180015e76`
- `USER32!CheckDlgButton` at `0x180015ed3`
- `USER32!CheckDlgButton` at `0x180015e76`
- `USER32!CheckDlgButton` at `0x180015ed3`
- `USER32!GetDlgItem` at `0x180015df0`
- `USER32!GetDlgItem` at `0x180015e0f`
- `USER32!GetDlgItem` at `0x180015e4b`
- `USER32!GetDlgItem` at `0x180015e85`
- `USER32!GetDlgItem` at `0x180015ee2`
- `USER32!GetDlgItem` at `0x180015ef1`
- `USER32!GetDlgItem` at `0x180015f87`
- `USER32!GetDlgItem` at `0x180015ff8`
- `USER32!GetDlgItem` at `0x18001600f`
- `USER32!GetDlgItem` at `0x18001603a`
- `USER32!GetDlgItem` at `0x1800160c0`
- `USER32!GetDlgItem` at `0x180016167`
- `USER32!GetDlgItem` at `0x180015df0`
- `USER32!GetDlgItem` at `0x180015e0f`
- `USER32!GetDlgItem` at `0x180015e4b`
- `USER32!GetDlgItem` at `0x180015e85`
- `USER32!GetDlgItem` at `0x180015ee2`
- `USER32!GetDlgItem` at `0x180015ef1`
- `USER32!GetDlgItem` at `0x180015f87`
- `USER32!GetDlgItem` at `0x180015ff8`
- `USER32!GetDlgItem` at `0x18001600f`
- `USER32!GetDlgItem` at `0x18001603a`
- `USER32!GetDlgItem` at `0x1800160c0`
- `USER32!GetDlgItem` at `0x180016167`
- `USER32!SendDlgItemMessageW` at `0x1800160fc`
- `USER32!SendDlgItemMessageW` at `0x1800160fc`

## pseudocode

```c
__int64 __fastcall CSchedulePage::_RefreshPage(CSchedulePage *this)
{
  HWND v2; // rax
  HWND v3; // rax
  HWND v4; // rcx
  HWND v5; // rax
  HWND v6; // rax
  __int64 v7; // rax
  int v8; // ecx
  bool v9; // zf
  HWND v10; // rcx
  HWND DlgItem; // rax
  BOOL v12; // edx
  int v13; // edx
  int v14; // edx
  int v15; // edx
  int v16; // edx
  int v17; // edx
  int v18; // edx
  int v19; // edx
  unsigned int v20; // esi
  int v21; // edx
  HWND v22; // rcx
  HWND v23; // rax
  int v24; // esi
  int v25; // edx
  int v26; // edx
  int v27; // edx
  int v28; // edx
  int v29; // edx
  int v30; // edx
  int v31; // edx
  HWND v33; // rax
  WPARAM v34; // r8
  HWND v35; // rax
  HWND v36; // rax
  __int64 v37; // rcx
  WORD v38; // ax
  HWND v39; // rcx
  HWND v40; // rax
  struct _SYSTEMTIME SystemTime; // [rsp+30h] [rbp-28h] BYREF

  if ( *((_QWORD *)this + 91) )
  {
    v7 = *((_QWORD *)this + 86);
    v8 = 0;
    while ( v7 )
    {
      v7 = *(_QWORD *)(v7 + 8);
      ++v8;
    }
    v9 = v8 == 1;
    v10 = (HWND)*((_QWORD *)this + 14);
    if ( v9 )
    {
      DlgItem = GetDlgItem(v10, 1676);
      if ( !DlgItem )
        goto LABEL_19;
      v12 = 1;
    }
    else
    {
      *((_DWORD *)this + 190) = 1;
      CheckDlgButton(v10, 1676, 1u);
      DlgItem = GetDlgItem(*((HWND *)this + 14), 1676);
      if ( !DlgItem )
        goto LABEL_19;
      v12 = 0;
    }
    EnableWindow(DlgItem, v12);
LABEL_19:
    v13 = *(_DWORD *)(*((_QWORD *)this + 91) + 56LL);
    if ( v13 )
    {
      v14 = v13 - 1;
      if ( v14 )
      {
        v15 = v14 - 1;
        if ( v15 )
        {
          v16 = v15 - 1;
          if ( v16 && (v17 = v16 - 1) != 0 )
          {
            v18 = v17 - 1;
            if ( v18 )
            {
              v19 = v18 - 1;
              if ( v19 )
              {
                if ( v19 != 1 )
                  return 0;
                v20 = 5;
              }
              else
              {
                v20 = 4;
              }
            }
            else
            {
              v20 = 6;
            }
          }
          else
          {
            v20 = 2;
          }
        }
        else
        {
          v20 = 1;
        }
      }
      else
      {
        v20 = 0;
      }
    }
    else
    {
      v20 = 3;
    }
    v21 = *((_DWORD *)this + 185);
    if ( v21 != -1 && v21 != v20 )
      CSchedulePage::_ShowControls(this, v21, 0);
    v22 = (HWND)*((_QWORD *)this + 14);
    *((_DWORD *)this + 185) = v20;
    v23 = GetDlgItem(v22, 1690);
    if ( v23 )
      SendMessageW(v23, 0x14Eu, v20, 0);
    v24 = 1;
    v25 = *(_DWORD *)(*((_QWORD *)this + 91) + 56LL);
    if ( v25 )
    {
      v26 = v25 - 1;
      if ( v26 )
      {
        v27 = v26 - 1;
        if ( v27 )
        {
          v28 = v27 - 1;
          if ( v28 && (v29 = v28 - 1) != 0 )
          {
            v30 = v29 - 1;
            if ( v30 )
            {
              v31 = v30 - 1;
              if ( v31 )
              {
                if ( v31 != 1 )
                  return 0;
                v24 = 0;
                v33 = GetDlgItem(*((HWND *)this + 14), 1690);
                v34 = 5;
              }
              else
              {
                v24 = 0;
                v33 = GetDlgItem(*((HWND *)this + 14), 1690);
                v34 = 4;
              }
              SendMessageW(v33, 0x14Eu, v34, 0);
            }
            else
            {
              v24 = 0;
              v35 = GetDlgItem(*((HWND *)this + 14), 1690);
              SendMessageW(v35, 0x14Eu, 6u, 0);
              CSchedulePage::_ShowControls(this, 6, 8);
              CSchedulePage::_UpdateIdleControls(this);
            }
          }
          else
          {
            CSchedulePage::_ShowControls(this, 2, 8);
            CSchedulePage::_UpdateMonthlyControls((HWND *)this);
          }
        }
        else
        {
          CSchedulePage::_ShowControls(this, 1, 8);
          CSchedulePage::_UpdateWeeklyControls((HWND *)this);
        }
      }
      else
      {
        CSchedulePage::_ShowControls(this, 0, 8);
        v36 = GetDlgItem(*((HWND *)this + 14), 1690);
        SendMessageW(v36, 0x14Eu, 0, 0);
        SendDlgItemMessageW(*((HWND *)this + 14), 1704, 0x467u, 0, *(unsigned __int16 *)(*((_QWORD *)this + 91) + 60LL));
      }
    }
    else
    {
      CSchedulePage::_ShowControls(this, 3, 8);
      CSchedulePage::_UpdateOnceOnlyControls((HWND *)this);
    }
    CSchedulePage::_EnableTimeTriggerSpecificCtrls(this, v24);
    if ( v24 == 1 )
    {
      SystemTime = 0;
      GetSystemTime(&SystemTime);
      v37 = *((_QWORD *)this + 91);
      SystemTime.wHour = *(_WORD *)(v37 + 40);
      v38 = *(_WORD *)(v37 + 42);
      v39 = (HWND)*((_QWORD *)this + 14);
      SystemTime.wMinute = v38;
      SystemTime.wSecond = 0;
      v40 = GetDlgItem(v39, 1691);
      if ( v40 )
        SendMessageW(v40, 0x1002u, 0, (LPARAM)&SystemTime);
    }
    CSchedulePage::_UpdateTriggerString(this);
    CSchedulePage::_ShowTriggerStringDispCtrls(this);
    return 1;
  }
  v2 = GetDlgItem(*((HWND *)this + 14), 1690);
  if ( v2 )
    EnableWindow(v2, 0);
  v3 = GetDlgItem(*((HWND *)this + 14), 1695);
  if ( v3 )
    EnableWindow(v3, 0);
  CSchedulePage::_EnableTimeTriggerSpecificCtrls(this, 0);
  CSchedulePage::_ShowTriggerStringDispCtrls(this);
  v4 = (HWND)*((_QWORD *)this + 14);
  *((_DWORD *)this + 190) = 1;
  v5 = GetDlgItem(v4, 1692);
  if ( v5 )
    SendMessageW(v5, 0x14Eu, 0, 0);
  CheckDlgButton(*((HWND *)this + 14), 1676, 1u);
  v6 = GetDlgItem(*((HWND *)this + 14), 1676);
  if ( v6 )
    EnableWindow(v6, 0);
  return 1;
}

```

## disassembly

```asm
0x180015db8  mov     [rsp+arg_8], rbx
0x180015dbd  mov     [rsp+arg_10], rsi
0x180015dc2  push    rdi
0x180015dc3  sub     rsp, 50h
0x180015dc7  mov     rax, cs:__security_cookie
0x180015dce  xor     rax, rsp
0x180015dd1  mov     [rsp+58h+var_18], rax
0x180015dd6  cmp     qword ptr [rcx+2D8h], 0
0x180015dde  mov     rbx, rcx
0x180015de1  jnz     loc_180015EA4
0x180015de7  mov     rcx, [rcx+70h]; hDlg
0x180015deb  mov     edx, 69Ah; nIDDlgItem
0x180015df0  call    cs:__imp_GetDlgItem
0x180015df6  test    rax, rax
0x180015df9  jz      short loc_180015E06
0x180015dfb  xor     edx, edx; bEnable
0x180015dfd  mov     rcx, rax; hWnd
0x180015e00  call    cs:__imp_EnableWindow
0x180015e06  mov     rcx, [rbx+70h]; hDlg
0x180015e0a  mov     edx, 69Fh; nIDDlgItem
0x180015e0f  call    cs:__imp_GetDlgItem
0x180015e15  test    rax, rax
0x180015e18  jz      short loc_180015E25
0x180015e1a  xor     edx, edx; bEnable
0x180015e1c  mov     rcx, rax; hWnd
0x180015e1f  call    cs:__imp_EnableWindow
0x180015e25  xor     edx, edx; int
0x180015e27  mov     rcx, rbx; this
0x180015e2a  call    ?_EnableTimeTriggerSpecificCtrls@CSchedulePage@@AEAAXH@Z; CSchedulePage::_EnableTimeTriggerSpecificCtrls(int)
0x180015e2f  mov     rcx, rbx; this
0x180015e32  call    ?_ShowTriggerStringDispCtrls@CSchedulePage@@AEAAXXZ; CSchedulePage::_ShowTriggerStringDispCtrls(void)
0x180015e37  mov     rcx, [rbx+70h]; hDlg
0x180015e3b  mov     edi, 1
0x180015e40  mov     edx, 69Ch; nIDDlgItem
0x180015e45  mov     [rbx+2F8h], edi
0x180015e4b  call    cs:__imp_GetDlgItem
0x180015e51  test    rax, rax
0x180015e54  jz      short loc_180015E6A
0x180015e56  xor     r9d, r9d; lParam
0x180015e59  xor     r8d, r8d; wParam
0x180015e5c  mov     edx, 14Eh; Msg
0x180015e61  mov     rcx, rax; hWnd
0x180015e64  call    cs:__imp_SendMessageW
0x180015e6a  mov     rcx, [rbx+70h]; hDlg
0x180015e6e  mov     r8d, edi; uCheck
0x180015e71  mov     edx, 68Ch; nIDButton
0x180015e76  call    cs:__imp_CheckDlgButton
0x180015e7c  mov     rcx, [rbx+70h]; hDlg
0x180015e80  mov     edx, 68Ch; nIDDlgItem
0x180015e85  call    cs:__imp_GetDlgItem
0x180015e8b  test    rax, rax
0x180015e8e  jz      loc_180016198
0x180015e94  xor     edx, edx; bEnable
0x180015e96  mov     rcx, rax; hWnd
0x180015e99  call    cs:__imp_EnableWindow
0x180015e9f  jmp     loc_180016198
0x180015ea4  mov     rax, [rbx+2B0h]
0x180015eab  xor     ecx, ecx
0x180015ead  lea     edi, [rcx+1]
0x180015eb0  jmp     short loc_180015EB8
0x180015eb2  mov     rax, [rax+8]
0x180015eb6  add     ecx, edi
0x180015eb8  test    rax, rax
0x180015ebb  jnz     short loc_180015EB2
0x180015ebd  cmp     ecx, edi
0x180015ebf  mov     edx, 68Ch; nIDDlgItem
0x180015ec4  mov     rcx, [rbx+70h]; hDlg
0x180015ec8  jz      short loc_180015EF1
0x180015eca  mov     r8d, edi; uCheck
0x180015ecd  mov     [rbx+2F8h], edi
0x180015ed3  call    cs:__imp_CheckDlgButton
0x180015ed9  mov     rcx, [rbx+70h]; hDlg
0x180015edd  mov     edx, 68Ch; nIDDlgItem
0x180015ee2  call    cs:__imp_GetDlgItem
0x180015ee8  test    rax, rax
0x180015eeb  jz      short loc_180015F07
0x180015eed  xor     edx, edx
0x180015eef  jmp     short loc_180015EFE
0x180015ef1  call    cs:__imp_GetDlgItem
0x180015ef7  test    rax, rax
0x180015efa  jz      short loc_180015F07
0x180015efc  mov     edx, edi; bEnable
0x180015efe  mov     rcx, rax; hWnd
0x180015f01  call    cs:__imp_EnableWindow
0x180015f07  mov     rcx, [rbx+2D8h]
0x180015f0e  mov     edx, [rcx+38h]
0x180015f11  test    edx, edx
0x180015f13  jz      short loc_180015F59
0x180015f15  sub     edx, edi
0x180015f17  jz      short loc_180015F55
0x180015f19  sub     edx, edi
0x180015f1b  jz      short loc_180015F51
0x180015f1d  sub     edx, edi
0x180015f1f  jz      short loc_180015F4A
0x180015f21  sub     edx, edi
0x180015f23  jz      short loc_180015F4A
0x180015f25  sub     edx, edi
0x180015f27  jz      short loc_180015F43
0x180015f29  sub     edx, edi
0x180015f2b  jz      short loc_180015F3C
0x180015f2d  cmp     edx, edi
0x180015f2f  jnz     loc_180015FE6
0x180015f35  mov     esi, 5
0x180015f3a  jmp     short loc_180015F5E
0x180015f3c  mov     esi, 4
0x180015f41  jmp     short loc_180015F5E
0x180015f43  mov     esi, 6
0x180015f48  jmp     short loc_180015F5E
0x180015f4a  mov     esi, 2
0x180015f4f  jmp     short loc_180015F5E
0x180015f51  mov     esi, edi
0x180015f53  jmp     short loc_180015F5E
0x180015f55  xor     esi, esi
0x180015f57  jmp     short loc_180015F5E
0x180015f59  mov     esi, 3
0x180015f5e  mov     edx, [rbx+2E4h]; int
0x180015f64  cmp     edx, 0FFFFFFFFh
0x180015f67  jz      short loc_180015F78
0x180015f69  cmp     edx, esi
0x180015f6b  jz      short loc_180015F78
0x180015f6d  xor     r8d, r8d; int
0x180015f70  mov     rcx, rbx; this
0x180015f73  call    ?_ShowControls@CSchedulePage@@AEAAXHH@Z; CSchedulePage::_ShowControls(int,int)
0x180015f78  mov     rcx, [rbx+70h]; hDlg
0x180015f7c  mov     edx, 69Ah; nIDDlgItem
0x180015f81  mov     [rbx+2E4h], esi
0x180015f87  call    cs:__imp_GetDlgItem
0x180015f8d  test    rax, rax
0x180015f90  jz      short loc_180015FA6
0x180015f92  mov     r8d, esi; wParam
0x180015f95  xor     r9d, r9d; lParam
0x180015f98  mov     edx, 14Eh; Msg
0x180015f9d  mov     rcx, rax; hWnd
0x180015fa0  call    cs:__imp_SendMessageW
0x180015fa6  mov     rcx, [rbx+2D8h]
0x180015fad  mov     esi, edi
0x180015faf  mov     edx, [rcx+38h]
0x180015fb2  test    edx, edx
0x180015fb4  jz      loc_180016104
0x180015fba  sub     edx, edi
0x180015fbc  jz      loc_1800160A9
0x180015fc2  sub     edx, edi
0x180015fc4  jz      loc_18001608F
0x180015fca  sub     edx, edi
0x180015fcc  jz      loc_180016071
0x180015fd2  sub     edx, edi
0x180015fd4  jz      loc_180016071
0x180015fda  sub     edx, edi
0x180015fdc  jz      short loc_18001602F
0x180015fde  sub     edx, edi
0x180015fe0  jz      short loc_180016004
0x180015fe2  cmp     edx, edi
0x180015fe4  jz      short loc_180015FED
0x180015fe6  xor     eax, eax
0x180015fe8  jmp     loc_18001619A
0x180015fed  mov     rcx, [rbx+70h]; hDlg
0x180015ff1  xor     esi, esi
0x180015ff3  mov     edx, 69Ah; nIDDlgItem
0x180015ff8  call    cs:__imp_GetDlgItem
0x180015ffe  lea     r8d, [rsi+5]
0x180016002  jmp     short loc_180016019
0x180016004  mov     rcx, [rbx+70h]; hDlg
0x180016008  xor     esi, esi
0x18001600a  mov     edx, 69Ah; nIDDlgItem
0x18001600f  call    cs:__imp_GetDlgItem
0x180016015  lea     r8d, [rsi+4]; wParam
0x180016019  mov     edx, 14Eh; Msg
0x18001601e  xor     r9d, r9d; lParam
0x180016021  mov     rcx, rax; hWnd
0x180016024  call    cs:__imp_SendMessageW
0x18001602a  jmp     loc_18001611D
0x18001602f  mov     rcx, [rbx+70h]; hDlg
0x180016033  mov     edx, 69Ah; nIDDlgItem
0x180016038  xor     esi, esi
0x18001603a  call    cs:__imp_GetDlgItem
0x180016040  xor     r9d, r9d; lParam
0x180016043  lea     r8d, [rsi+6]; wParam
0x180016047  mov     rcx, rax; hWnd
0x18001604a  mov     edx, 14Eh; Msg
0x18001604f  call    cs:__imp_SendMessageW
0x180016055  lea     edx, [rsi+6]; int
0x180016058  mov     rcx, rbx; this
0x18001605b  lea     r8d, [rsi+8]; int
0x18001605f  call    ?_ShowControls@CSchedulePage@@AEAAXHH@Z; CSchedulePage::_ShowControls(int,int)
0x180016064  mov     rcx, rbx; this
0x180016067  call    ?_UpdateIdleControls@CSchedulePage@@AEAAXXZ; CSchedulePage::_UpdateIdleControls(void)
0x18001606c  jmp     loc_18001611D
0x180016071  mov     edx, 2; int
0x180016076  mov     rcx, rbx; this
0x180016079  lea     r8d, [rdx+6]; int
0x18001607d  call    ?_ShowControls@CSchedulePage@@AEAAXHH@Z; CSchedulePage::_ShowControls(int,int)
0x180016082  mov     rcx, rbx; this
0x180016085  call    ?_UpdateMonthlyControls@CSchedulePage@@AEAAXXZ; CSchedulePage::_UpdateMonthlyControls(void)
0x18001608a  jmp     loc_18001611D
0x18001608f  mov     r8d, 8; int
0x180016095  mov     edx, edi; int
0x180016097  mov     rcx, rbx; this
0x18001609a  call    ?_ShowControls@CSchedulePage@@AEAAXHH@Z; CSchedulePage::_ShowControls(int,int)
0x18001609f  mov     rcx, rbx; this
0x1800160a2  call    ?_UpdateWeeklyControls@CSchedulePage@@AEAAXXZ; CSchedulePage::_UpdateWeeklyControls(void)
0x1800160a7  jmp     short loc_18001611D
0x1800160a9  xor     edx, edx; int
0x1800160ab  mov     rcx, rbx; this
0x1800160ae  lea     r8d, [rdx+8]; int
0x1800160b2  call    ?_ShowControls@CSchedulePage@@AEAAXHH@Z; CSchedulePage::_ShowControls(int,int)
0x1800160b7  mov     rcx, [rbx+70h]; hDlg
0x1800160bb  mov     edx, 69Ah; nIDDlgItem
0x1800160c0  call    cs:__imp_GetDlgItem
0x1800160c6  xor     r9d, r9d; lParam
0x1800160c9  xor     r8d, r8d; wParam
0x1800160cc  mov     rcx, rax; hWnd
0x1800160cf  mov     edx, 14Eh; Msg
0x1800160d4  call    cs:__imp_SendMessageW
0x1800160da  mov     rax, [rbx+2D8h]
0x1800160e1  xor     r9d, r9d; wParam
0x1800160e4  mov     edx, 6A8h; nIDDlgItem
0x1800160e9  mov     r8d, 467h; Msg
0x1800160ef  movzx   ecx, word ptr [rax+3Ch]
0x1800160f3  mov     [rsp+58h+lParam], rcx; lParam
0x1800160f8  mov     rcx, [rbx+70h]; hDlg
0x1800160fc  call    cs:__imp_SendDlgItemMessageW
0x180016102  jmp     short loc_18001611D
0x180016104  mov     edx, 3; int
0x180016109  mov     rcx, rbx; this
0x18001610c  lea     r8d, [rdx+5]; int
0x180016110  call    ?_ShowControls@CSchedulePage@@AEAAXHH@Z; CSchedulePage::_ShowControls(int,int)
0x180016115  mov     rcx, rbx; this
0x180016118  call    ?_UpdateOnceOnlyControls@CSchedulePage@@AEAAXXZ; CSchedulePage::_UpdateOnceOnlyControls(void)
0x18001611d  mov     edx, esi; int
0x18001611f  mov     rcx, rbx; this
0x180016122  call    ?_EnableTimeTriggerSpecificCtrls@CSchedulePage@@AEAAXH@Z; CSchedulePage::_EnableTimeTriggerSpecificCtrls(int)
0x180016127  cmp     esi, edi
0x180016129  jnz     short loc_180016188
0x18001612b  xorps   xmm0, xmm0
0x18001612e  lea     rcx, [rsp+58h+SystemTime]; lpSystemTime
0x180016133  movups  xmmword ptr [rsp+58h+SystemTime.wYear], xmm0
0x180016138  call    cs:__imp_GetSystemTime
0x18001613e  mov     rcx, [rbx+2D8h]
0x180016145  mov     edx, 69Bh; nIDDlgItem
0x18001614a  movzx   eax, word ptr [rcx+28h]
0x18001614e  mov     [rsp+58h+SystemTime.wHour], ax
0x180016153  movzx   eax, word ptr [rcx+2Ah]
0x180016157  mov     rcx, [rbx+70h]; hDlg
0x18001615b  mov     [rsp+58h+SystemTime.wMinute], ax
0x180016160  xor     eax, eax
0x180016162  mov     [rsp+58h+SystemTime.wSecond], ax
0x180016167  call    cs:__imp_GetDlgItem
0x18001616d  test    rax, rax
0x180016170  jz      short loc_180016188
0x180016172  lea     r9, [rsp+58h+SystemTime]; lParam
0x180016177  xor     r8d, r8d; wParam
0x18001617a  mov     edx, 1002h; Msg
0x18001617f  mov     rcx, rax; hWnd
0x180016182  call    cs:__imp_SendMessageW
0x180016188  mov     rcx, rbx; this
0x18001618b  call    ?_UpdateTriggerString@CSchedulePage@@AEAAXXZ; CSchedulePage::_UpdateTriggerString(void)
0x180016190  mov     rcx, rbx; this
0x180016193  call    ?_ShowTriggerStringDispCtrls@CSchedulePage@@AEAAXXZ; CSchedulePage::_ShowTriggerStringDispCtrls(void)
0x180016198  mov     eax, edi
0x18001619a  mov     rcx, [rsp+58h+var_18]
0x18001619f  xor     rcx, rsp; StackCookie
0x1800161a2  call    __security_check_cookie
0x1800161a7  mov     rbx, [rsp+58h+arg_8]
0x1800161ac  mov     rsi, [rsp+58h+arg_10]
0x1800161b1  add     rsp, 50h
0x1800161b5  pop     rdi
0x1800161b6  retn
```
