# CConfigGeneralPage::OnInitDialog(HWND__ *,HWND__ * &)

- ea: `0x1800115b0`
- end: `0x180011709`
- name: `?OnInitDialog@CConfigGeneralPage@@UEAAKPEAUHWND__@@AEAPEAU2@@Z`
- size: `345`
- prototype: `unsigned int __fastcall(CConfigGeneralPage *__hidden this, HWND, HWND *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x180005eac`
- `0x180005ed4`
- `0x18000edb0`
- `0x180010748`
- `0x180010a84`
- `0x1800115b0`
- `0x180017010`

## import_xrefs

- `USER32!EnableWindow` at `0x1800116d6`
- `USER32!EnableWindow` at `0x1800116d6`
- `USER32!SetDlgItemTextW` at `0x1800116ed`
- `USER32!SetDlgItemTextW` at `0x1800116ed`
- `USER32!EndDialog` at `0x1800116a7`
- `USER32!EndDialog` at `0x1800116a7`
- `USER32!GetDlgItem` at `0x1800116c8`
- `USER32!GetDlgItem` at `0x1800116c8`

## pseudocode

```c
__int64 __fastcall CConfigGeneralPage::OnInitDialog(CConfigGeneralPage *this, HWND a2, HWND *a3)
{
  unsigned int active; // eax
  CConfigGeneralPage *v6; // rcx
  int v7; // r8d
  INT_PTR v8; // rbx
  HWND DlgItem; // rax
  CConfigGeneralPage *v10; // rcx
  int v11; // r8d

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_f5b496eade1b3798203481970613ce29_Traceguids);
  }
  if ( *((_DWORD *)this + 13) )
  {
    active = CConfigGeneralPage::InitializeControlsForActiveDevice(this, a2);
    v8 = active;
    if ( active )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_f5b496eade1b3798203481970613ce29_Traceguids, active);
      }
      (*(__int64 (__fastcall **)(CConfigGeneralPage *, _QWORD))(*(_QWORD *)this + 48LL))(this, (unsigned int)v8);
      FaxMsgBox(a2, *((_QWORD *)this + 1), 4656);
      EndDialog(a2, v8);
    }
    else if ( !*((_DWORD *)this + 32) )
    {
      CConfigGeneralPage::EnableActiveControls(v6, a2, v7);
      DlgItem = GetDlgItem(a2, 4512);
      EnableWindow(DlgItem, 1);
    }
  }
  else
  {
    SetDlgItemTextW(a2, 4504, &String);
    CConfigGeneralPage::EnableActiveControls(v10, a2, v11);
    LODWORD(v8) = 0;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800115b0  push    rbx
0x1800115b2  push    rsi
0x1800115b3  push    rdi
0x1800115b4  push    r14
0x1800115b6  sub     rsp, 38h
0x1800115ba  mov     rdi, rdx
0x1800115bd  mov     rsi, rcx
0x1800115c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800115c7  lea     r14, WPP_GLOBAL_Control
0x1800115ce  cmp     rcx, r14
0x1800115d1  jz      short loc_1800115F7
0x1800115d3  test    dword ptr [rcx+1Ch], 100h
0x1800115da  jz      short loc_1800115F7
0x1800115dc  cmp     byte ptr [rcx+19h], 5
0x1800115e0  jb      short loc_1800115F7
0x1800115e2  mov     rcx, [rcx+10h]
0x1800115e6  lea     r8, WPP_f5b496eade1b3798203481970613ce29_Traceguids
0x1800115ed  mov     edx, 15h
0x1800115f2  call    WPP_SF_
0x1800115f7  cmp     dword ptr [rsi+34h], 0
0x1800115fb  jz      loc_1800116DE
0x180011601  mov     rdx, rdi; HWND
0x180011604  mov     rcx, rsi; this
0x180011607  call    ?InitializeControlsForActiveDevice@CConfigGeneralPage@@AEBAKPEAUHWND__@@@Z; CConfigGeneralPage::InitializeControlsForActiveDevice(HWND__ *)
0x18001160c  mov     ebx, eax
0x18001160e  test    eax, eax
0x180011610  jz      loc_1800116AF
0x180011616  mov     rcx, cs:WPP_GLOBAL_Control
0x18001161d  cmp     rcx, r14
0x180011620  jz      short loc_180011649
0x180011622  test    dword ptr [rcx+1Ch], 100h
0x180011629  jz      short loc_180011649
0x18001162b  cmp     byte ptr [rcx+19h], 2
0x18001162f  jb      short loc_180011649
0x180011631  mov     rcx, [rcx+10h]
0x180011635  lea     r8, WPP_f5b496eade1b3798203481970613ce29_Traceguids
0x18001163c  mov     edx, 16h
0x180011641  mov     r9d, ebx
0x180011644  call    WPP_SF_d
0x180011649  mov     rax, [rsi]
0x18001164c  mov     edx, ebx
0x18001164e  mov     rcx, rsi
0x180011651  mov     rax, [rax+30h]
0x180011655  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001165a  test    eax, eax
0x18001165c  jnz     short loc_180011684
0x18001165e  cmp     ebx, 5
0x180011661  jz      short loc_18001167F
0x180011663  cmp     ebx, 8
0x180011666  jz      short loc_180011678
0x180011668  mov     eax, 1234h
0x18001166d  cmp     ebx, 7Ah ; 'z'
0x180011670  lea     ecx, [rax+2]
0x180011673  cmovnz  eax, ecx
0x180011676  jmp     short loc_180011684
0x180011678  mov     eax, 1237h
0x18001167d  jmp     short loc_180011684
0x18001167f  mov     eax, 1235h
0x180011684  mov     rdx, [rsi+8]
0x180011688  mov     r9d, eax
0x18001168b  mov     r8d, 1230h
0x180011691  mov     [rsp+58h+var_38], 10h
0x180011699  mov     rcx, rdi
0x18001169c  call    FaxMsgBox
0x1800116a1  mov     rdx, rbx; nResult
0x1800116a4  mov     rcx, rdi; hDlg
0x1800116a7  call    cs:__imp_EndDialog
0x1800116ad  jmp     short loc_1800116FD
0x1800116af  cmp     dword ptr [rsi+80h], 0
0x1800116b6  jnz     short loc_1800116FD
0x1800116b8  mov     rdx, rdi; HWND
0x1800116bb  call    ?EnableActiveControls@CConfigGeneralPage@@AEBAXPEAUHWND__@@H@Z; CConfigGeneralPage::EnableActiveControls(HWND__ *,int)
0x1800116c0  mov     edx, 11A0h; nIDDlgItem
0x1800116c5  mov     rcx, rdi; hDlg
0x1800116c8  call    cs:__imp_GetDlgItem
0x1800116ce  mov     rcx, rax; hWnd
0x1800116d1  mov     edx, 1; bEnable
0x1800116d6  call    cs:__imp_EnableWindow
0x1800116dc  jmp     short loc_1800116FD
0x1800116de  lea     r8, String; lpString
0x1800116e5  mov     edx, 1198h; nIDDlgItem
0x1800116ea  mov     rcx, rdi; hDlg
0x1800116ed  call    cs:__imp_SetDlgItemTextW
0x1800116f3  mov     rdx, rdi; HWND
0x1800116f6  call    ?EnableActiveControls@CConfigGeneralPage@@AEBAXPEAUHWND__@@H@Z; CConfigGeneralPage::EnableActiveControls(HWND__ *,int)
0x1800116fb  xor     ebx, ebx
0x1800116fd  mov     eax, ebx
0x1800116ff  add     rsp, 38h
0x180011703  pop     r14
0x180011705  pop     rdi
0x180011706  pop     rsi
0x180011707  pop     rbx
0x180011708  retn
```
