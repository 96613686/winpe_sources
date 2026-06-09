# CDeviceSettingsDialog::OnCommand(HWND__ *,ushort,ushort,HWND__ *,int &)

- ea: `0x180011310`
- end: `0x1800114fe`
- name: `?OnCommand@CDeviceSettingsDialog@@UEAAKPEAUHWND__@@GG0AEAH@Z`
- size: `494`
- prototype: `unsigned int __usercall@<eax>(CDeviceSettingsDialog *__hidden this@<rcx>, HWND@<rdx>, unsigned __int16@<r8w>, unsigned __int16@<r9w>, HWND, int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005eac`
- `0x180005ed4`
- `0x18000edb0`
- `0x180010864`
- `0x180011310`
- `0x1800117e0`
- `0x180011b2c`
- `0x180013a08`

## import_xrefs

- `USER32!EnableWindow` at `0x180011436`
- `USER32!EnableWindow` at `0x180011436`
- `USER32!IsDlgButtonChecked` at `0x1800113e5`
- `USER32!IsDlgButtonChecked` at `0x180011415`
- `USER32!IsDlgButtonChecked` at `0x1800113e5`
- `USER32!IsDlgButtonChecked` at `0x180011415`
- `USER32!EndDialog` at `0x1800114e9`
- `USER32!EndDialog` at `0x1800114e9`
- `USER32!GetDlgItem` at `0x18001142b`
- `USER32!GetDlgItem` at `0x18001142b`

## pseudocode

```c
__int64 __fastcall CDeviceSettingsDialog::OnCommand(
        CDeviceSettingsDialog *this,
        HWND a2,
        __int16 a3,
        unsigned __int16 a4,
        HWND a5,
        int *a6)
{
  int v6; // r14d
  unsigned int v10; // esi
  UINT v11; // eax
  CDeviceSettingsDialog *v12; // rcx
  BOOL v13; // ebx
  HWND DlgItem; // rax
  INT_PTR v15; // rdx
  unsigned int v16; // eax

  v6 = a4;
  v10 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_f5b496eade1b3798203481970613ce29_Traceguids);
  }
  *a6 = 1;
  if ( v6 != 1 )
  {
    if ( v6 != 2 )
    {
      switch ( v6 )
      {
        case 4540:
          if ( !a3 )
          {
            v13 = IsDlgButtonChecked(a2, 4540) == 1;
            DlgItem = GetDlgItem(a2, 4547);
            EnableWindow(DlgItem, v13);
          }
          break;
        case 4548:
          if ( !a3 )
          {
            v11 = IsDlgButtonChecked(a2, 4548);
            CDeviceSettingsDialog::EnableStoreFolderControls(v12, a2, v11 == 1);
          }
          break;
        case 4549:
          if ( a3 == 512 )
            FaxPathMakePretty(a2, v6);
          break;
        case 4550:
          CDeviceSettingsDialog::OpenSelectFolderDialog(this, a2);
          break;
        default:
          *a6 = 0;
          break;
      }
      return v10;
    }
    v15 = 2;
LABEL_28:
    EndDialog(a2, v15);
    return v10;
  }
  v16 = CDeviceSettingsDialog::SaveDeviceSettings(this, a2);
  v10 = v16;
  if ( !v16 )
  {
    v15 = 1;
    goto LABEL_28;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_f5b496eade1b3798203481970613ce29_Traceguids, v16);
  }
  if ( v10 != 1003 )
    FaxMsgBox(a2, *((_QWORD *)this + 1), 4656);
  return v10;
}

```

## disassembly

```asm
0x180011310  push    rbx
0x180011312  push    rbp
0x180011313  push    rsi
0x180011314  push    rdi
0x180011315  push    r13
0x180011317  push    r14
0x180011319  sub     rsp, 38h
0x18001131d  movzx   r14d, r9w
0x180011321  movzx   ebx, r8w
0x180011325  mov     rdi, rdx
0x180011328  mov     rbp, rcx
0x18001132b  xor     esi, esi
0x18001132d  mov     rcx, cs:WPP_GLOBAL_Control
0x180011334  lea     r13, WPP_GLOBAL_Control
0x18001133b  cmp     rcx, r13
0x18001133e  jz      short loc_180011362
0x180011340  test    dword ptr [rcx+1Ch], 100h
0x180011347  jz      short loc_180011362
0x180011349  cmp     byte ptr [rcx+19h], 5
0x18001134d  jb      short loc_180011362
0x18001134f  mov     rcx, [rcx+10h]
0x180011353  lea     edx, [rsi+3Dh]
0x180011356  lea     r8, WPP_f5b496eade1b3798203481970613ce29_Traceguids
0x18001135d  call    WPP_SF_
0x180011362  mov     rdx, [rsp+68h+arg_28]
0x18001136a  mov     ecx, r14d
0x18001136d  mov     dword ptr [rdx], 1
0x180011373  sub     ecx, 1
0x180011376  jz      loc_18001144B
0x18001137c  sub     ecx, 1
0x18001137f  jz      loc_180011441
0x180011385  sub     ecx, 11BAh
0x18001138b  jz      short loc_180011402
0x18001138d  sub     ecx, 8
0x180011390  jz      short loc_1800113D2
0x180011392  sub     ecx, 1
0x180011395  jz      short loc_1800113B3
0x180011397  cmp     ecx, 1
0x18001139a  jz      short loc_1800113A3
0x18001139c  mov     [rdx], esi
0x18001139e  jmp     loc_1800114EF
0x1800113a3  mov     rdx, rdi; HWND
0x1800113a6  mov     rcx, rbp; this
0x1800113a9  call    ?OpenSelectFolderDialog@CDeviceSettingsDialog@@AEBAKPEAUHWND__@@@Z; CDeviceSettingsDialog::OpenSelectFolderDialog(HWND__ *)
0x1800113ae  jmp     loc_1800114EF
0x1800113b3  mov     eax, 200h
0x1800113b8  cmp     ax, bx
0x1800113bb  jnz     loc_1800114EF
0x1800113c1  movzx   edx, r14w; unsigned __int16
0x1800113c5  mov     rcx, rdi; hDlg
0x1800113c8  call    ?FaxPathMakePretty@@YAJPEAUHWND__@@G@Z; FaxPathMakePretty(HWND__ *,ushort)
0x1800113cd  jmp     loc_1800114EF
0x1800113d2  xor     eax, eax
0x1800113d4  cmp     ax, bx
0x1800113d7  jnz     loc_1800114EF
0x1800113dd  mov     edx, 11C4h; nIDButton
0x1800113e2  mov     rcx, rdi; hDlg
0x1800113e5  call    cs:__imp_IsDlgButtonChecked
0x1800113eb  xor     r8d, r8d
0x1800113ee  mov     rdx, rdi; HWND
0x1800113f1  cmp     eax, 1
0x1800113f4  setz    r8b; int
0x1800113f8  call    ?EnableStoreFolderControls@CDeviceSettingsDialog@@AEBAKPEAUHWND__@@H@Z; CDeviceSettingsDialog::EnableStoreFolderControls(HWND__ *,int)
0x1800113fd  jmp     loc_1800114EF
0x180011402  xor     eax, eax
0x180011404  cmp     ax, bx
0x180011407  jnz     loc_1800114EF
0x18001140d  mov     edx, 11BCh; nIDButton
0x180011412  mov     rcx, rdi; hDlg
0x180011415  call    cs:__imp_IsDlgButtonChecked
0x18001141b  xor     ebx, ebx
0x18001141d  mov     edx, 11C3h; nIDDlgItem
0x180011422  cmp     eax, 1
0x180011425  mov     rcx, rdi; hDlg
0x180011428  setz    bl
0x18001142b  call    cs:__imp_GetDlgItem
0x180011431  mov     rcx, rax; hWnd
0x180011434  mov     edx, ebx; bEnable
0x180011436  call    cs:__imp_EnableWindow
0x18001143c  jmp     loc_1800114EF
0x180011441  mov     edx, 2
0x180011446  jmp     loc_1800114E6
0x18001144b  mov     rdx, rdi; HWND
0x18001144e  mov     rcx, rbp; this
0x180011451  call    ?SaveDeviceSettings@CDeviceSettingsDialog@@AEAAKPEAUHWND__@@@Z; CDeviceSettingsDialog::SaveDeviceSettings(HWND__ *)
0x180011456  mov     esi, eax
0x180011458  test    eax, eax
0x18001145a  jz      loc_1800114E1
0x180011460  mov     rcx, cs:WPP_GLOBAL_Control
0x180011467  cmp     rcx, r13
0x18001146a  jz      short loc_180011493
0x18001146c  test    dword ptr [rcx+1Ch], 100h
0x180011473  jz      short loc_180011493
0x180011475  cmp     byte ptr [rcx+19h], 2
0x180011479  jb      short loc_180011493
0x18001147b  mov     rcx, [rcx+10h]
0x18001147f  lea     r8, WPP_f5b496eade1b3798203481970613ce29_Traceguids
0x180011486  mov     edx, 3Eh ; '>'
0x18001148b  mov     r9d, eax
0x18001148e  call    WPP_SF_d
0x180011493  cmp     esi, 3EBh
0x180011499  jz      short loc_1800114EF
0x18001149b  cmp     esi, 5
0x18001149e  jz      short loc_1800114BF
0x1800114a0  cmp     esi, 8
0x1800114a3  jz      short loc_1800114B7
0x1800114a5  mov     eax, 1236h
0x1800114aa  cmp     esi, 7Ah ; 'z'
0x1800114ad  lea     r9d, [rax-2]
0x1800114b1  cmovnz  r9d, eax
0x1800114b5  jmp     short loc_1800114C5
0x1800114b7  mov     r9d, 1237h
0x1800114bd  jmp     short loc_1800114C5
0x1800114bf  mov     r9d, 1235h
0x1800114c5  mov     rdx, [rbp+8]
0x1800114c9  mov     r8d, 1230h
0x1800114cf  mov     rcx, rdi
0x1800114d2  mov     [rsp+68h+var_48], 10h
0x1800114da  call    FaxMsgBox
0x1800114df  jmp     short loc_1800114EF
0x1800114e1  mov     edx, 1; nResult
0x1800114e6  mov     rcx, rdi; hDlg
0x1800114e9  call    cs:__imp_EndDialog
0x1800114ef  mov     eax, esi
0x1800114f1  add     rsp, 38h
0x1800114f5  pop     r14
0x1800114f7  pop     r13
0x1800114f9  pop     rdi
0x1800114fa  pop     rsi
0x1800114fb  pop     rbp
0x1800114fc  pop     rbx
0x1800114fd  retn
```
