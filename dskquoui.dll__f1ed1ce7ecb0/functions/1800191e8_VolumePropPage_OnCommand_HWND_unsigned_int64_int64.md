# VolumePropPage::OnCommand(HWND__ *,unsigned __int64,__int64)

- ea: `0x1800191e8`
- end: `0x1800194f9`
- name: `?OnCommand@VolumePropPage@@AEAA_JPEAUHWND__@@_K_J@Z`
- size: `785`
- prototype: `__int64 __fastcall(VolumePropPage *__hidden this, HWND, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180018c30`

## callees

- `0x180018da4`
- `0x1800190e4`
- `0x1800191e8`
- `0x18001b120`
- `0x18001b1e0`
- `0x18001b26c`
- `0x18001b3b0`

## import_xrefs

- `USER32!IsWindowEnabled` at `0x1800192c0`
- `USER32!IsWindowEnabled` at `0x180019322`
- `USER32!IsWindowEnabled` at `0x1800192c0`
- `USER32!IsWindowEnabled` at `0x180019322`
- `USER32!GetParent` at `0x1800194c4`
- `USER32!GetParent` at `0x1800194c4`
- `USER32!SendMessageW` at `0x1800194d8`
- `USER32!SendMessageW` at `0x1800194d8`
- `USER32!CheckDlgButton` at `0x180019389`
- `USER32!CheckDlgButton` at `0x1800193ab`
- `USER32!CheckDlgButton` at `0x1800193cf`
- `USER32!CheckDlgButton` at `0x1800193f6`
- `USER32!CheckDlgButton` at `0x180019414`
- `USER32!CheckDlgButton` at `0x180019389`
- `USER32!CheckDlgButton` at `0x1800193ab`
- `USER32!CheckDlgButton` at `0x1800193cf`
- `USER32!CheckDlgButton` at `0x1800193f6`
- `USER32!CheckDlgButton` at `0x180019414`
- `USER32!GetDlgItem` at `0x1800192b7`
- `USER32!GetDlgItem` at `0x180019319`
- `USER32!GetDlgItem` at `0x1800192b7`
- `USER32!GetDlgItem` at `0x180019319`
- `USER32!IsDlgButtonChecked` at `0x180019363`
- `USER32!IsDlgButtonChecked` at `0x180019395`
- `USER32!IsDlgButtonChecked` at `0x180019363`
- `USER32!IsDlgButtonChecked` at `0x180019395`

## pseudocode

```c
__int64 __fastcall VolumePropPage::OnCommand(XBytes **this, HWND a2, unsigned __int64 a3, __int64 a4)
{
  __int64 v6; // rbx
  int v7; // ebp
  __int64 v8; // rax
  XBytes *v9; // rcx
  HWND v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  HWND DlgItem; // rax
  UINT v14; // ebp
  UINT v15; // eax
  UINT v16; // r8d
  _BYTE *v17; // r14
  UINT v18; // r8d
  __int64 v19; // rax
  XBytes *v20; // rcx
  __int64 v21; // rax
  XBytes *v22; // rcx
  HWND Parent; // rax
  XBytes *v25; // [rsp+20h] [rbp-38h]
  XBytes *v26; // [rsp+28h] [rbp-30h]

  v6 = 1;
  if ( (unsigned __int16)a3 > 0x3F1u )
  {
    if ( (unsigned __int16)a3 == 1012 )
      return VolumePropPage::OnButtonDetails((VolumePropPage *)this, (HWND)0x3F1, a3, a4);
    if ( (unsigned __int16)a3 != 1037 && (unsigned __int16)a3 != 1038 )
    {
      if ( (unsigned int)(unsigned __int16)a3 - 1088 >= 2 )
        return v6;
      goto LABEL_54;
    }
    if ( WORD1(a3) == 1 )
    {
      v25 = this[19];
      v26 = this[20];
      v21 = 0;
      if ( (_WORD)a3 == 1038 )
        v21 = 8;
      v22 = *(XBytes **)((char *)&v25 + v21);
      if ( v22 )
        XBytes::OnComboNotifySelChange(v22, 1038);
      goto LABEL_53;
    }
    return v6;
  }
  if ( (_WORD)a3 != 1009 )
  {
    v7 = 0;
    switch ( (unsigned __int16)a3 )
    {
      case 0x3EAu:
        v14 = IsDlgButtonChecked(a2, 1002);
        CheckDlgButton(a2, 1006, *(_QWORD *)this[19] == -1);
        v15 = IsDlgButtonChecked(a2, 1006);
        CheckDlgButton(a2, 1007, v15 != 1);
        v16 = v14 && ((_BYTE)this[12] & 3) == 2;
        CheckDlgButton(a2, 1005, v16);
        v17 = (char *)this + 100;
        v18 = v14 && (*v17 & 1) != 0;
        CheckDlgButton(a2, 1089, v18);
        if ( !v14 || (*(_DWORD *)v17 & 2) == 0 )
          LODWORD(v6) = 0;
        CheckDlgButton(a2, 1088, v6);
        VolumePropPage::EnableControls((VolumePropPage *)this, a2);
        goto LABEL_53;
      case 0x3EDu:
LABEL_53:
        v6 = 0;
LABEL_54:
        Parent = GetParent(a2);
        SendMessageW(Parent, 0x468u, (WPARAM)a2, 0);
        return v6;
      case 0x3EEu:
        DlgItem = GetDlgItem(*((HWND *)this[19] + 1), *((_DWORD *)this[19] + 4));
        if ( !IsWindowEnabled(DlgItem) )
          goto LABEL_24;
        XBytes::SetBytes(this[20], -1);
        XBytes::SetBytes(this[19], -1);
        break;
      case 0x3EFu:
        v10 = GetDlgItem(*((HWND *)this[19] + 1), *((_DWORD *)this[19] + 4));
        if ( IsWindowEnabled(v10) )
        {
LABEL_24:
          v6 = 0;
          if ( v7 )
            goto LABEL_54;
          return v6;
        }
        v11 = 0;
        if ( this[14] != (XBytes *)-1LL )
          v11 = (__int64)this[14];
        XBytes::SetBytes(this[19], v11);
        v12 = 0;
        if ( this[13] != (XBytes *)-1LL )
          v12 = (__int64)this[13];
        XBytes::SetBytes(this[20], v12);
        VolumePropPage::EnableControls((VolumePropPage *)this, a2);
        break;
      case 0x3F0u:
        goto LABEL_8;
      default:
        return v6;
    }
    v7 = 1;
    goto LABEL_24;
  }
LABEL_8:
  switch ( WORD1(a3) )
  {
    case 0x100u:
      return 0;
    case 0x200u:
      v25 = this[19];
      v26 = this[20];
      v19 = 0;
      if ( (_WORD)a3 == 1009 )
        v19 = 8;
      v20 = *(XBytes **)((char *)&v25 + v19);
      if ( v20 )
        XBytes::OnEditKillFocus(v20, 1009);
      return 0;
    case 0x400u:
      v25 = this[19];
      v26 = this[20];
      v8 = 0;
      if ( (_WORD)a3 == 1009 )
        v8 = 8;
      v9 = *(XBytes **)((char *)&v25 + v8);
      if ( v9 )
        XBytes::OnEditNotifyUpdate(v9, 1009);
      goto LABEL_53;
  }
  return v6;
}

```

## disassembly

```asm
0x1800191e8  push    rbx
0x1800191ea  push    rbp
0x1800191eb  push    rsi
0x1800191ec  push    rdi
0x1800191ed  push    r14
0x1800191ef  sub     rsp, 30h
0x1800191f3  mov     rax, r8
0x1800191f6  mov     rsi, rdx
0x1800191f9  shr     rax, 10h
0x1800191fd  mov     edx, 3F1h; HWND
0x180019202  mov     rdi, rcx
0x180019205  mov     ebx, 1
0x18001920a  movzx   ecx, ax
0x18001920d  cmp     r8w, dx
0x180019211  ja      loc_180019464
0x180019217  jz      short loc_180019249
0x180019219  xor     ebp, ebp
0x18001921b  movzx   eax, r8w
0x18001921f  lea     r9d, [rdx-7]
0x180019223  sub     eax, r9d
0x180019226  jz      loc_18001935D
0x18001922c  sub     eax, 3
0x18001922f  jz      loc_1800194BF
0x180019235  sub     eax, ebx
0x180019237  jz      loc_18001930B
0x18001923d  sub     eax, ebx
0x18001923f  jz      short loc_1800192A9
0x180019241  cmp     eax, ebx
0x180019243  jnz     loc_1800194EB
0x180019249  cmp     ecx, 100h
0x18001924f  jz      loc_18001945D
0x180019255  cmp     ecx, 200h
0x18001925b  jz      loc_18001942A
0x180019261  cmp     ecx, 400h
0x180019267  jnz     loc_1800194EB
0x18001926d  mov     rax, [rdi+98h]
0x180019274  mov     [rsp+58h+var_38], rax
0x180019279  mov     rax, [rdi+0A0h]
0x180019280  mov     [rsp+58h+var_30], rax
0x180019285  xor     eax, eax
0x180019287  cmp     dx, r8w
0x18001928b  lea     ecx, [rax+8]
0x18001928e  cmovz   eax, ecx
0x180019291  mov     rcx, [rsp+rax+58h+var_38]; this
0x180019296  test    rcx, rcx
0x180019299  jz      loc_1800194BF
0x18001929f  call    ?OnEditNotifyUpdate@XBytes@@QEAAH_J@Z; XBytes::OnEditNotifyUpdate(__int64)
0x1800192a4  jmp     loc_1800194BF
0x1800192a9  mov     rcx, [rdi+98h]
0x1800192b0  mov     edx, [rcx+10h]; nIDDlgItem
0x1800192b3  mov     rcx, [rcx+8]; hDlg
0x1800192b7  call    cs:__imp_GetDlgItem
0x1800192bd  mov     rcx, rax; hWnd
0x1800192c0  call    cs:__imp_IsWindowEnabled
0x1800192c6  test    eax, eax
0x1800192c8  jnz     loc_18001934E
0x1800192ce  mov     rcx, [rdi+98h]; this
0x1800192d5  xor     edx, edx
0x1800192d7  cmp     qword ptr [rdi+70h], 0FFFFFFFFFFFFFFFFh
0x1800192dc  cmovnz  rdx, [rdi+70h]; __int64
0x1800192e1  call    ?SetBytes@XBytes@@QEAAX_J@Z; XBytes::SetBytes(__int64)
0x1800192e6  mov     rcx, [rdi+0A0h]; this
0x1800192ed  xor     edx, edx
0x1800192ef  cmp     qword ptr [rdi+68h], 0FFFFFFFFFFFFFFFFh
0x1800192f4  cmovnz  rdx, [rdi+68h]; __int64
0x1800192f9  call    ?SetBytes@XBytes@@QEAAX_J@Z; XBytes::SetBytes(__int64)
0x1800192fe  mov     rdx, rsi; HWND
0x180019301  mov     rcx, rdi; this
0x180019304  call    ?EnableControls@VolumePropPage@@AEAAJPEAUHWND__@@@Z; VolumePropPage::EnableControls(HWND__ *)
0x180019309  jmp     short loc_18001934C
0x18001930b  mov     rcx, [rdi+98h]
0x180019312  mov     edx, [rcx+10h]; nIDDlgItem
0x180019315  mov     rcx, [rcx+8]; hDlg
0x180019319  call    cs:__imp_GetDlgItem
0x18001931f  mov     rcx, rax; hWnd
0x180019322  call    cs:__imp_IsWindowEnabled
0x180019328  test    eax, eax
0x18001932a  jz      short loc_18001934E
0x18001932c  mov     rcx, [rdi+0A0h]; this
0x180019333  or      rdx, 0FFFFFFFFFFFFFFFFh; __int64
0x180019337  call    ?SetBytes@XBytes@@QEAAX_J@Z; XBytes::SetBytes(__int64)
0x18001933c  mov     rcx, [rdi+98h]; this
0x180019343  or      rdx, 0FFFFFFFFFFFFFFFFh; __int64
0x180019347  call    ?SetBytes@XBytes@@QEAAX_J@Z; XBytes::SetBytes(__int64)
0x18001934c  mov     ebp, ebx
0x18001934e  xor     ebx, ebx
0x180019350  test    ebp, ebp
0x180019352  jz      loc_1800194EB
0x180019358  jmp     loc_1800194C1
0x18001935d  mov     edx, r9d; nIDButton
0x180019360  mov     rcx, rsi; hDlg
0x180019363  call    cs:__imp_IsDlgButtonChecked
0x180019369  mov     rcx, [rdi+98h]
0x180019370  xor     r8d, r8d
0x180019373  mov     r14d, 3EEh
0x180019379  mov     ebp, eax
0x18001937b  mov     edx, r14d; nIDButton
0x18001937e  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x180019382  mov     rcx, rsi; hDlg
0x180019385  setz    r8b; uCheck
0x180019389  call    cs:__imp_CheckDlgButton
0x18001938f  mov     edx, r14d; nIDButton
0x180019392  mov     rcx, rsi; hDlg
0x180019395  call    cs:__imp_IsDlgButtonChecked
0x18001939b  xor     r8d, r8d
0x18001939e  lea     edx, [r14+1]; nIDButton
0x1800193a2  cmp     eax, ebx
0x1800193a4  mov     rcx, rsi; hDlg
0x1800193a7  setnz   r8b; uCheck
0x1800193ab  call    cs:__imp_CheckDlgButton
0x1800193b1  test    ebp, ebp
0x1800193b3  jz      short loc_1800193C4
0x1800193b5  mov     eax, [rdi+60h]
0x1800193b8  and     eax, 3
0x1800193bb  cmp     al, 2
0x1800193bd  jnz     short loc_1800193C4
0x1800193bf  mov     r8d, ebx
0x1800193c2  jmp     short loc_1800193C7
0x1800193c4  xor     r8d, r8d; uCheck
0x1800193c7  mov     edx, 3EDh; nIDButton
0x1800193cc  mov     rcx, rsi; hDlg
0x1800193cf  call    cs:__imp_CheckDlgButton
0x1800193d5  lea     r14, [rdi+64h]
0x1800193d9  test    ebp, ebp
0x1800193db  jz      short loc_1800193EB
0x1800193dd  mov     eax, [r14]
0x1800193e0  and     eax, ebx
0x1800193e2  test    al, al
0x1800193e4  jz      short loc_1800193EB
0x1800193e6  mov     r8d, ebx
0x1800193e9  jmp     short loc_1800193EE
0x1800193eb  xor     r8d, r8d; uCheck
0x1800193ee  mov     edx, 441h; nIDButton
0x1800193f3  mov     rcx, rsi; hDlg
0x1800193f6  call    cs:__imp_CheckDlgButton
0x1800193fc  test    ebp, ebp
0x1800193fe  jz      short loc_180019407
0x180019400  mov     eax, [r14]
0x180019403  test    al, 2
0x180019405  jnz     short loc_180019409
0x180019407  xor     ebx, ebx
0x180019409  mov     r8d, ebx; uCheck
0x18001940c  mov     edx, 440h; nIDButton
0x180019411  mov     rcx, rsi; hDlg
0x180019414  call    cs:__imp_CheckDlgButton
0x18001941a  mov     rdx, rsi; HWND
0x18001941d  mov     rcx, rdi; this
0x180019420  call    ?EnableControls@VolumePropPage@@AEAAJPEAUHWND__@@@Z; VolumePropPage::EnableControls(HWND__ *)
0x180019425  jmp     loc_1800194BF
0x18001942a  mov     rax, [rdi+98h]
0x180019431  mov     [rsp+58h+var_38], rax
0x180019436  mov     rax, [rdi+0A0h]
0x18001943d  mov     [rsp+58h+var_30], rax
0x180019442  xor     eax, eax
0x180019444  cmp     dx, r8w
0x180019448  lea     ecx, [rax+8]
0x18001944b  cmovz   eax, ecx
0x18001944e  mov     rcx, [rsp+rax+58h+var_38]; this
0x180019453  test    rcx, rcx
0x180019456  jz      short loc_18001945D
0x180019458  call    ?OnEditKillFocus@XBytes@@QEAAH_J@Z; XBytes::OnEditKillFocus(__int64)
0x18001945d  xor     ebx, ebx
0x18001945f  jmp     loc_1800194EB
0x180019464  movzx   eax, r8w
0x180019468  sub     eax, 3F4h
0x18001946d  jz      short loc_1800194E0
0x18001946f  sub     eax, 19h
0x180019472  jz      short loc_180019483
0x180019474  sub     eax, ebx
0x180019476  jz      short loc_180019483
0x180019478  sub     eax, 32h ; '2'
0x18001947b  jz      short loc_1800194C1
0x18001947d  cmp     eax, ebx
0x18001947f  jz      short loc_1800194C1
0x180019481  jmp     short loc_1800194EB
0x180019483  cmp     ecx, ebx
0x180019485  jnz     short loc_1800194EB
0x180019487  mov     rax, [rdi+98h]
0x18001948e  mov     edx, 40Eh; __int64
0x180019493  mov     [rsp+58h+var_38], rax
0x180019498  mov     rax, [rdi+0A0h]
0x18001949f  mov     [rsp+58h+var_30], rax
0x1800194a4  xor     eax, eax
0x1800194a6  cmp     dx, r8w
0x1800194aa  lea     ecx, [rax+8]
0x1800194ad  cmovz   eax, ecx
0x1800194b0  mov     rcx, [rsp+rax+58h+var_38]; this
0x1800194b5  test    rcx, rcx
0x1800194b8  jz      short loc_1800194BF
0x1800194ba  call    ?OnComboNotifySelChange@XBytes@@QEAAH_J@Z; XBytes::OnComboNotifySelChange(__int64)
0x1800194bf  xor     ebx, ebx
0x1800194c1  mov     rcx, rsi; hWnd
0x1800194c4  call    cs:__imp_GetParent
0x1800194ca  xor     r9d, r9d; lParam
0x1800194cd  mov     r8, rsi; wParam
0x1800194d0  mov     rcx, rax; hWnd
0x1800194d3  mov     edx, 468h; Msg
0x1800194d8  call    cs:__imp_SendMessageW
0x1800194de  jmp     short loc_1800194EB
0x1800194e0  mov     rcx, rdi; this
0x1800194e3  call    ?OnButtonDetails@VolumePropPage@@AEAA_JPEAUHWND__@@_K_J@Z; VolumePropPage::OnButtonDetails(HWND__ *,unsigned __int64,__int64)
0x1800194e8  mov     rbx, rax
0x1800194eb  mov     rax, rbx
0x1800194ee  add     rsp, 30h
0x1800194f2  pop     r14
0x1800194f4  pop     rdi
0x1800194f5  pop     rsi
0x1800194f6  pop     rbp
0x1800194f7  pop     rbx
0x1800194f8  retn
```
