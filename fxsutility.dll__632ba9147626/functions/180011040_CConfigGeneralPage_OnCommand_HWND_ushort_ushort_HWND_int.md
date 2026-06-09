# CConfigGeneralPage::OnCommand(HWND__ *,ushort,ushort,HWND__ *,int &)

- ea: `0x180011040`
- end: `0x180011302`
- name: `?OnCommand@CConfigGeneralPage@@UEAAKPEAUHWND__@@GG0AEAH@Z`
- size: `706`
- prototype: `unsigned int __usercall@<eax>(CConfigGeneralPage *__hidden this@<rcx>, HWND@<rdx>, unsigned __int16@<r8w>, unsigned __int16@<r9w>, HWND, int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005a28`
- `0x180005eac`
- `0x180005ed4`
- `0x18001067c`
- `0x1800107ac`
- `0x18001080c`
- `0x180011040`
- `0x18001352c`
- `0x180017010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800112d0`
- `KERNEL32!GetLastError` at `0x1800112d0`
- `USER32!SetDlgItemTextW` at `0x1800112ed`
- `USER32!SetDlgItemTextW` at `0x1800112ed`
- `USER32!SendMessageW` at `0x18001117a`
- `USER32!SendMessageW` at `0x18001117a`
- `USER32!SetDlgItemInt` at `0x180011165`
- `USER32!SetDlgItemInt` at `0x180011165`
- `USER32!CheckDlgButton` at `0x180011224`
- `USER32!CheckDlgButton` at `0x180011224`
- `USER32!GetDlgItemInt` at `0x180011124`
- `USER32!GetDlgItemInt` at `0x180011124`
- `USER32!SetFocus` at `0x180011183`
- `USER32!SetFocus` at `0x180011183`
- `USER32!IsDlgButtonChecked` at `0x1800111a8`
- `USER32!IsDlgButtonChecked` at `0x1800111d6`
- `USER32!IsDlgButtonChecked` at `0x1800111fd`
- `USER32!IsDlgButtonChecked` at `0x18001120f`
- `USER32!IsDlgButtonChecked` at `0x1800111a8`
- `USER32!IsDlgButtonChecked` at `0x1800111d6`
- `USER32!IsDlgButtonChecked` at `0x1800111fd`
- `USER32!IsDlgButtonChecked` at `0x18001120f`
- `USER32!SetActiveWindow` at `0x18001118c`
- `USER32!SetActiveWindow` at `0x18001118c`
- `USER32!DialogBoxParamW` at `0x1800112c5`
- `USER32!DialogBoxParamW` at `0x1800112c5`
- `USER32!GetDlgItem` at `0x18001113b`
- `USER32!GetDlgItem` at `0x18001113b`

## pseudocode

```c
__int64 __fastcall CConfigGeneralPage::OnCommand(
        CConfigGeneralPage *this,
        HWND a2,
        __int16 a3,
        unsigned __int16 a4,
        HWND a5,
        int *a6)
{
  int v6; // r14d
  unsigned int v10; // ebp
  HWND DlgItem; // rbx
  UINT v12; // eax
  CConfigGeneralPage *v13; // rcx
  UINT v14; // ebx
  CConfigGeneralPage *v15; // rcx
  INT_PTR v16; // rax

  v6 = a4;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_f5b496eade1b3798203481970613ce29_Traceguids);
  }
  v10 = 0;
  *a6 = 1;
  if ( v6 == 4505 )
  {
    v16 = DialogBoxParamW(
            *((HINSTANCE *)this + 1),
            (LPCWSTR)0x11FD,
            a2,
            CConfigGeneralPage::SelectDeviceDlgProc,
            (LPARAM)this);
    if ( v16 > 0 )
    {
      if ( (_DWORD)v16 == 2 )
        return v10;
    }
    else if ( GetLastError() )
    {
      return v10;
    }
    SetDlgItemTextW(a2, 4504, *((LPCWSTR *)this + 7));
    return v10;
  }
  if ( v6 == 4506 )
  {
    if ( a3 )
      return v10;
    goto LABEL_32;
  }
  if ( v6 != 4507 )
  {
    if ( v6 == 4508 || v6 == 4509 )
    {
      if ( a3 )
        return v10;
      v12 = IsDlgButtonChecked(a2, 4509);
      CConfigGeneralPage::EnableRingsAndSpinControls(v13, a2, v12 == 1);
    }
    else if ( v6 == 4510 )
    {
      if ( a3 != 768 )
        return v10;
      if ( GetDlgItemInt(a2, 4510, 0, 0) - 1 > 0x62 )
      {
        DlgItem = GetDlgItem(a2, 4510);
        CPage::DisplayErrorDialog(this, a2, 0x1238u, 0);
        SetDlgItemInt(a2, 4510, *((_DWORD *)this + 25), 0);
        SendMessageW(DlgItem, 0xB1u, 0, -1);
        SetFocus(DlgItem);
        SetActiveWindow(DlgItem);
      }
    }
    else if ( v6 != 4511 )
    {
      if ( v6 == 4512 )
        CConfigGeneralPage::DisplayAdditionalDeviceSettings(this, a2);
      else
        *a6 = 0;
      return v10;
    }
LABEL_32:
    (*(void (__fastcall **)(CConfigGeneralPage *, HWND))(*(_QWORD *)this + 80LL))(this, a2);
    return v10;
  }
  if ( !a3 )
  {
    v14 = IsDlgButtonChecked(a2, 4507);
    CConfigGeneralPage::EnableReceiveControls(v15, a2, v14 == 1);
    if ( v14 == 1 && IsDlgButtonChecked(a2, 4509) != 1 && IsDlgButtonChecked(a2, 4508) != 1 )
      CheckDlgButton(a2, 4509, 1u);
    (*(void (__fastcall **)(CConfigGeneralPage *, HWND))(*(_QWORD *)this + 80LL))(this, a2);
    if ( v14 == 1 )
    {
      v10 = SetServiceStartupType(0);
      if ( v10 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_f5b496eade1b3798203481970613ce29_Traceguids, v10);
        }
      }
    }
  }
  return v10;
}

```

## disassembly

```asm
0x180011040  push    rbx
0x180011042  push    rbp
0x180011043  push    rsi
0x180011044  push    rdi
0x180011045  push    r14
0x180011047  push    r15
0x180011049  sub     rsp, 38h
0x18001104d  movzx   r14d, r9w
0x180011051  movzx   ebx, r8w
0x180011055  mov     rdi, rdx
0x180011058  mov     rsi, rcx
0x18001105b  mov     rcx, cs:WPP_GLOBAL_Control
0x180011062  lea     rax, WPP_GLOBAL_Control
0x180011069  cmp     rcx, rax
0x18001106c  jz      short loc_180011092
0x18001106e  test    dword ptr [rcx+1Ch], 100h
0x180011075  jz      short loc_180011092
0x180011077  cmp     byte ptr [rcx+19h], 5
0x18001107b  jb      short loc_180011092
0x18001107d  mov     rcx, [rcx+10h]
0x180011081  lea     r8, WPP_f5b496eade1b3798203481970613ce29_Traceguids
0x180011088  mov     edx, 18h
0x18001108d  call    WPP_SF_
0x180011092  mov     rdx, [rsp+68h+arg_28]
0x18001109a  xor     r15d, r15d
0x18001109d  mov     ecx, r14d
0x1800110a0  mov     ebp, r15d
0x1800110a3  mov     dword ptr [rdx], 1
0x1800110a9  sub     ecx, 1199h
0x1800110af  jz      loc_1800112AD
0x1800110b5  sub     ecx, 1
0x1800110b8  jz      loc_180011294
0x1800110be  sub     ecx, 1
0x1800110c1  jz      loc_1800111C5
0x1800110c7  sub     ecx, 1
0x1800110ca  jz      loc_180011197
0x1800110d0  sub     ecx, 1
0x1800110d3  jz      loc_180011197
0x1800110d9  sub     ecx, 1
0x1800110dc  jz      short loc_180011104
0x1800110de  sub     ecx, 1
0x1800110e1  jz      loc_180011299
0x1800110e7  cmp     ecx, 1
0x1800110ea  jz      short loc_1800110F4
0x1800110ec  mov     [rdx], r15d
0x1800110ef  jmp     loc_1800112F3
0x1800110f4  mov     rdx, rdi; HWND
0x1800110f7  mov     rcx, rsi; this
0x1800110fa  call    ?DisplayAdditionalDeviceSettings@CConfigGeneralPage@@AEAAKPEAUHWND__@@@Z; CConfigGeneralPage::DisplayAdditionalDeviceSettings(HWND__ *)
0x1800110ff  jmp     loc_1800112F3
0x180011104  mov     eax, 300h
0x180011109  cmp     bx, ax
0x18001110c  jnz     loc_1800112F3
0x180011112  mov     r14d, 119Eh
0x180011118  xor     r9d, r9d; bSigned
0x18001111b  mov     edx, r14d; nIDDlgItem
0x18001111e  xor     r8d, r8d; lpTranslated
0x180011121  mov     rcx, rdi; hDlg
0x180011124  call    cs:__imp_GetDlgItemInt
0x18001112a  dec     eax
0x18001112c  cmp     eax, 62h ; 'b'
0x18001112f  jbe     loc_180011299
0x180011135  mov     edx, r14d; nIDDlgItem
0x180011138  mov     rcx, rdi; hDlg
0x18001113b  call    cs:__imp_GetDlgItem
0x180011141  xor     r9d, r9d; unsigned int
0x180011144  mov     r8d, 1238h; unsigned int
0x18001114a  mov     rdx, rdi; HWND
0x18001114d  mov     rcx, rsi; this
0x180011150  mov     rbx, rax
0x180011153  call    ?DisplayErrorDialog@CPage@@QEBAHPEAUHWND__@@KK@Z; CPage::DisplayErrorDialog(HWND__ *,ulong,ulong)
0x180011158  mov     r8d, [rsi+64h]; uValue
0x18001115c  xor     r9d, r9d; bSigned
0x18001115f  mov     edx, r14d; nIDDlgItem
0x180011162  mov     rcx, rdi; hDlg
0x180011165  call    cs:__imp_SetDlgItemInt
0x18001116b  or      r9, 0FFFFFFFFFFFFFFFFh; lParam
0x18001116f  xor     r8d, r8d; wParam
0x180011172  mov     edx, 0B1h; Msg
0x180011177  mov     rcx, rbx; hWnd
0x18001117a  call    cs:__imp_SendMessageW
0x180011180  mov     rcx, rbx; hWnd
0x180011183  call    cs:__imp_SetFocus
0x180011189  mov     rcx, rbx; hWnd
0x18001118c  call    cs:__imp_SetActiveWindow
0x180011192  jmp     loc_180011299
0x180011197  test    bx, bx
0x18001119a  jnz     loc_1800112F3
0x1800111a0  mov     edx, 119Dh; nIDButton
0x1800111a5  mov     rcx, rdi; hDlg
0x1800111a8  call    cs:__imp_IsDlgButtonChecked
0x1800111ae  mov     r8d, r15d
0x1800111b1  mov     rdx, rdi; HWND
0x1800111b4  cmp     eax, 1
0x1800111b7  setz    r8b; int
0x1800111bb  call    ?EnableRingsAndSpinControls@CConfigGeneralPage@@AEBAKPEAUHWND__@@H@Z; CConfigGeneralPage::EnableRingsAndSpinControls(HWND__ *,int)
0x1800111c0  jmp     loc_180011299
0x1800111c5  test    bx, bx
0x1800111c8  jnz     loc_1800112F3
0x1800111ce  mov     edx, 119Bh; nIDButton
0x1800111d3  mov     rcx, rdi; hDlg
0x1800111d6  call    cs:__imp_IsDlgButtonChecked
0x1800111dc  mov     r8d, r15d
0x1800111df  mov     rdx, rdi; HWND
0x1800111e2  cmp     eax, 1
0x1800111e5  mov     ebx, eax
0x1800111e7  setz    r8b; int
0x1800111eb  call    ?EnableReceiveControls@CConfigGeneralPage@@AEBAKPEAUHWND__@@H@Z; CConfigGeneralPage::EnableReceiveControls(HWND__ *,int)
0x1800111f0  cmp     ebx, 1
0x1800111f3  jnz     short loc_18001122A
0x1800111f5  mov     edx, 119Dh; nIDButton
0x1800111fa  mov     rcx, rdi; hDlg
0x1800111fd  call    cs:__imp_IsDlgButtonChecked
0x180011203  cmp     eax, ebx
0x180011205  jz      short loc_18001122A
0x180011207  mov     edx, 119Ch; nIDButton
0x18001120c  mov     rcx, rdi; hDlg
0x18001120f  call    cs:__imp_IsDlgButtonChecked
0x180011215  cmp     eax, ebx
0x180011217  jz      short loc_18001122A
0x180011219  mov     edx, 119Dh; nIDButton
0x18001121e  mov     r8d, ebx; uCheck
0x180011221  mov     rcx, rdi; hDlg
0x180011224  call    cs:__imp_CheckDlgButton
0x18001122a  mov     rax, [rsi]
0x18001122d  mov     rdx, rdi
0x180011230  mov     rcx, rsi
0x180011233  mov     rax, [rax+50h]
0x180011237  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001123c  cmp     ebx, 1
0x18001123f  jnz     loc_1800112F3
0x180011245  xor     ecx, ecx; lpMachineName
0x180011247  call    SetServiceStartupType
0x18001124c  mov     ebp, eax
0x18001124e  test    eax, eax
0x180011250  jz      loc_1800112F3
0x180011256  mov     rcx, cs:WPP_GLOBAL_Control
0x18001125d  lea     rax, WPP_GLOBAL_Control
0x180011264  cmp     rcx, rax
0x180011267  jz      loc_1800112F3
0x18001126d  test    dword ptr [rcx+1Ch], 100h
0x180011274  jz      short loc_1800112F3
0x180011276  cmp     byte ptr [rcx+19h], 2
0x18001127a  jb      short loc_1800112F3
0x18001127c  mov     rcx, [rcx+10h]
0x180011280  lea     edx, [rbx+18h]
0x180011283  mov     r9d, ebp
0x180011286  lea     r8, WPP_f5b496eade1b3798203481970613ce29_Traceguids
0x18001128d  call    WPP_SF_d
0x180011292  jmp     short loc_1800112F3
0x180011294  test    bx, bx
0x180011297  jnz     short loc_1800112F3
0x180011299  mov     rax, [rsi]
0x18001129c  mov     rdx, rdi
0x18001129f  mov     rcx, rsi
0x1800112a2  mov     rax, [rax+50h]
0x1800112a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112ab  jmp     short loc_1800112F3
0x1800112ad  mov     rcx, [rsi+8]; hInstance
0x1800112b1  lea     r9, ?SelectDeviceDlgProc@CConfigGeneralPage@@SA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x1800112b8  mov     r8, rdi; hWndParent
0x1800112bb  mov     [rsp+68h+dwInitParam], rsi; dwInitParam
0x1800112c0  mov     edx, 11FDh; lpTemplateName
0x1800112c5  call    cs:__imp_DialogBoxParamW
0x1800112cb  test    rax, rax
0x1800112ce  jg      short loc_1800112DC
0x1800112d0  call    cs:__imp_GetLastError
0x1800112d6  test    eax, eax
0x1800112d8  jnz     short loc_1800112F3
0x1800112da  jmp     short loc_1800112E1
0x1800112dc  cmp     eax, 2
0x1800112df  jz      short loc_1800112F3
0x1800112e1  mov     r8, [rsi+38h]; lpString
0x1800112e5  mov     edx, 1198h; nIDDlgItem
0x1800112ea  mov     rcx, rdi; hDlg
0x1800112ed  call    cs:__imp_SetDlgItemTextW
0x1800112f3  mov     eax, ebp
0x1800112f5  add     rsp, 38h
0x1800112f9  pop     r15
0x1800112fb  pop     r14
0x1800112fd  pop     rdi
0x1800112fe  pop     rsi
0x1800112ff  pop     rbp
0x180011300  pop     rbx
0x180011301  retn
```
