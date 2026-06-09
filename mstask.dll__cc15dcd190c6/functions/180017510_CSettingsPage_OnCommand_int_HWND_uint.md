# CSettingsPage::_OnCommand(int,HWND__ *,uint)

- ea: `0x180017510`
- end: `0x180017645`
- name: `?_OnCommand@CSettingsPage@@EEAA_JHPEAUHWND__@@I@Z`
- size: `309`
- prototype: `__int64 __fastcall(CSettingsPage *__hidden this, int, HWND, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180013404`
- `0x18001347c`
- `0x180017510`
- `0x18001b010`

## import_xrefs

- `USER32!IsDlgButtonChecked` at `0x180017567`
- `USER32!IsDlgButtonChecked` at `0x1800175be`
- `USER32!IsDlgButtonChecked` at `0x180017567`
- `USER32!IsDlgButtonChecked` at `0x1800175be`

## pseudocode

```c
__int64 __fastcall CSettingsPage::_OnCommand(CSettingsPage *this, int a2, HWND a3, int a4)
{
  int v5; // edx
  int v6; // edx
  int v7; // edx
  int v8; // edx
  bool v9; // zf
  UINT v10; // eax
  HWND v11; // rcx
  unsigned __int16 v12; // r8
  int v13; // edx
  int v14; // edx
  UINT v15; // eax
  HWND v16; // rcx
  int v17; // edx
  int v18; // edx
  int v19; // edx
  int v20; // edx
  bool v22; // zf

  if ( a2 <= 1677 )
  {
    if ( a2 == 1677 )
    {
      if ( a4 )
        return 1;
      v15 = IsDlgButtonChecked(*((HWND *)this + 14), 1677);
      v16 = (HWND)*((_QWORD *)this + 14);
      if ( v15 == 1 )
      {
        Spin_Enable(v16, 1679, 0x48u);
        v12 = 0;
        v13 = 1681;
        goto LABEL_11;
      }
      Spin_Disable(v16, 1679);
      v14 = 1681;
    }
    else
    {
      v5 = a2 - 1671;
      if ( v5 )
      {
        v6 = v5 - 1;
        if ( !v6 || (v7 = v6 - 1) == 0 || (v8 = v7 - 1) == 0 )
        {
LABEL_25:
          v22 = a4 == 0;
          goto LABEL_27;
        }
        v9 = v8 == 1;
LABEL_23:
        if ( !v9 )
          return 0;
        goto LABEL_25;
      }
      if ( a4 )
        return 1;
      v10 = IsDlgButtonChecked(*((HWND *)this + 14), 1671);
      v11 = (HWND)*((_QWORD *)this + 14);
      if ( v10 == 1 )
      {
        Spin_Enable(v11, 1684, *((_WORD *)this + 340));
        v12 = *((_WORD *)this + 341);
        v13 = 1698;
LABEL_11:
        Spin_Enable(*((HWND *)this + 14), v13, v12);
LABEL_28:
        (*(void (__fastcall **)(CSettingsPage *))(*(_QWORD *)this + 144LL))(this);
        return 1;
      }
      Spin_Disable(v11, 1684);
      v14 = 1698;
    }
    Spin_Disable(*((HWND *)this + 14), v14);
    goto LABEL_28;
  }
  v17 = a2 - 1678;
  if ( v17 )
  {
    v18 = v17 - 2;
    if ( v18 )
    {
      v19 = v18 - 3;
      if ( v19 )
      {
        v20 = v19 - 6;
        if ( v20 )
        {
          v9 = v20 == 11;
          goto LABEL_23;
        }
      }
    }
  }
  v22 = a4 == 768;
LABEL_27:
  if ( v22 )
    goto LABEL_28;
  return 1;
}

```

## disassembly

```asm
0x180017510  push    rbx
0x180017512  sub     rsp, 20h
0x180017516  mov     eax, 68Dh
0x18001751b  mov     rbx, rcx
0x18001751e  cmp     edx, eax
0x180017520  jg      loc_1800175FA
0x180017526  jz      loc_1800175AF
0x18001752c  mov     eax, 687h
0x180017531  sub     edx, eax
0x180017533  jz      short loc_180017558
0x180017535  sub     edx, 1
0x180017538  jz      loc_18001761A
0x18001753e  sub     edx, 1
0x180017541  jz      loc_18001761A
0x180017547  sub     edx, 1
0x18001754a  jz      loc_18001761A
0x180017550  cmp     edx, 1
0x180017553  jmp     loc_180017614
0x180017558  test    r9d, r9d
0x18001755b  jnz     loc_18001763A
0x180017561  mov     rcx, [rcx+70h]; hDlg
0x180017565  mov     edx, eax; nIDButton
0x180017567  call    cs:__imp_IsDlgButtonChecked
0x18001756d  mov     rcx, [rbx+70h]; hDlg
0x180017571  mov     edx, 694h; nIDDlgItem
0x180017576  cmp     eax, 1
0x180017579  jnz     short loc_1800175A3
0x18001757b  movzx   r8d, word ptr [rbx+2A8h]; unsigned __int16
0x180017583  call    ?Spin_Enable@@YAXPEAUHWND__@@HG@Z; Spin_Enable(HWND__ *,int,ushort)
0x180017588  movzx   r8d, word ptr [rbx+2AAh]; unsigned __int16
0x180017590  mov     edx, 6A2h; nIDDlgItem
0x180017595  mov     rcx, [rbx+70h]; hDlg
0x180017599  call    ?Spin_Enable@@YAXPEAUHWND__@@HG@Z; Spin_Enable(HWND__ *,int,ushort)
0x18001759e  jmp     loc_180017628
0x1800175a3  call    ?Spin_Disable@@YAXPEAUHWND__@@H@Z; Spin_Disable(HWND__ *,int)
0x1800175a8  mov     edx, 6A2h
0x1800175ad  jmp     short loc_1800175EF
0x1800175af  test    r9d, r9d
0x1800175b2  jnz     loc_18001763A
0x1800175b8  mov     rcx, [rcx+70h]; hDlg
0x1800175bc  mov     edx, eax; nIDButton
0x1800175be  call    cs:__imp_IsDlgButtonChecked
0x1800175c4  mov     rcx, [rbx+70h]; hDlg
0x1800175c8  mov     edx, 68Fh; nIDDlgItem
0x1800175cd  cmp     eax, 1
0x1800175d0  jnz     short loc_1800175E5
0x1800175d2  lea     r8d, [rax+47h]; unsigned __int16
0x1800175d6  call    ?Spin_Enable@@YAXPEAUHWND__@@HG@Z; Spin_Enable(HWND__ *,int,ushort)
0x1800175db  xor     r8d, r8d
0x1800175de  mov     edx, 691h
0x1800175e3  jmp     short loc_180017595
0x1800175e5  call    ?Spin_Disable@@YAXPEAUHWND__@@H@Z; Spin_Disable(HWND__ *,int)
0x1800175ea  mov     edx, 691h; nIDDlgItem
0x1800175ef  mov     rcx, [rbx+70h]; hDlg
0x1800175f3  call    ?Spin_Disable@@YAXPEAUHWND__@@H@Z; Spin_Disable(HWND__ *,int)
0x1800175f8  jmp     short loc_180017628
0x1800175fa  sub     edx, 68Eh
0x180017600  jz      short loc_18001761F
0x180017602  sub     edx, 2
0x180017605  jz      short loc_18001761F
0x180017607  sub     edx, 3
0x18001760a  jz      short loc_18001761F
0x18001760c  sub     edx, 6
0x18001760f  jz      short loc_18001761F
0x180017611  cmp     edx, 0Bh
0x180017614  jz      short loc_18001761A
0x180017616  xor     eax, eax
0x180017618  jmp     short loc_18001763F
0x18001761a  test    r9d, r9d
0x18001761d  jmp     short loc_180017626
0x18001761f  cmp     r9d, 300h
0x180017626  jnz     short loc_18001763A
0x180017628  mov     rax, [rbx]
0x18001762b  mov     rcx, rbx
0x18001762e  mov     rax, [rax+90h]
0x180017635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001763a  mov     eax, 1
0x18001763f  add     rsp, 20h
0x180017643  pop     rbx
0x180017644  retn
```
