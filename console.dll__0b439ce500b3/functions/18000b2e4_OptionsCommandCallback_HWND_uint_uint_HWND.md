# OptionsCommandCallback(HWND__ *,uint,uint,HWND__ *)

- ea: `0x18000b2e4`
- end: `0x18000b598`
- name: `?OptionsCommandCallback@@YA_NPEAUHWND__@@II0@Z`
- size: `692`
- prototype: `bool __fastcall(HWND hDlg, unsigned int nIDButton, unsigned int, HWND)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000b5a0`

## callees

- `0x18000705c`
- `0x180007488`
- `0x1800082bc`
- `0x180008358`
- `0x18000b2e4`
- `0x18000bb2c`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18000b399`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18000b3b3`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18000b399`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18000b3b3`
- `ext-ms-win-ntuser-dialogbox-l1-1-2!GetDlgItemInt` at `0x18000b430`
- `ext-ms-win-ntuser-dialogbox-l1-1-2!GetDlgItemInt` at `0x18000b430`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18000b37c`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18000b37c`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x18000b44e`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x18000b4a1`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x18000b4cc`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x18000b4f0`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x18000b51b`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x18000b546`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x18000b571`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x18000b44e`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x18000b4a1`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x18000b4cc`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x18000b4f0`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x18000b51b`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x18000b546`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x18000b571`

## pseudocode

```c
char __fastcall OptionsCommandCallback(HWND hDlg, unsigned int nIDButton, int a3, HWND a4)
{
  bool v8; // zf
  HWND DlgItem; // rbx
  int v11; // eax
  int v12; // r8d
  unsigned int v13; // edx
  UINT DlgItemInt; // eax
  BOOL Translated; // [rsp+58h] [rbp+10h] BYREF

  Translated = 0;
  if ( nIDButton > 0x97 )
  {
    switch ( nIDButton )
    {
      case 0x98u:
        goto LABEL_10;
      case 0x1F5u:
        g_fForceV2 = IsDlgButtonChecked(hDlg, 501) != 1;
        ToggleV2OptionsControls(hDlg);
        goto LABEL_12;
      case 0x1F6u:
        *((_DWORD *)gpStateInfo + 57) = IsDlgButtonChecked(hDlg, 502) == 1;
        goto LABEL_12;
      case 0x1F7u:
        *((_DWORD *)gpStateInfo + 55) = IsDlgButtonChecked(hDlg, 503) == 1;
        goto LABEL_12;
      case 0x1F9u:
        *((_DWORD *)gpStateInfo + 56) = IsDlgButtonChecked(hDlg, 505) != 1;
        goto LABEL_12;
      case 0x1FBu:
        g_fEditKeys = IsDlgButtonChecked(hDlg, 507) == 1;
        goto LABEL_12;
      case 0x203u:
        *((_DWORD *)gpStateInfo + 62) = IsDlgButtonChecked(hDlg, 515) == 1;
        goto LABEL_12;
    }
    return 0;
  }
  switch ( nIDButton )
  {
    case 0x97u:
LABEL_10:
      UpdateStateInfo(hDlg, nIDButton, 0);
      v8 = a3 == 512;
      goto LABEL_11;
    case 0x67u:
    case 0x68u:
      goto LABEL_25;
    case 0x6Cu:
    case 0x6Eu:
      if ( a3 != 512 )
      {
        if ( a3 != 1024 )
          return 1;
        if ( !(unsigned int)CheckNum(hDlg, nIDButton) )
        {
          Undo(a4);
          return 1;
        }
        v8 = g_fSettingsDlgInitialized == 0;
LABEL_11:
        if ( v8 )
          return 1;
LABEL_12:
        UpdateApplyButton(hDlg);
        return 1;
      }
      DlgItemInt = GetDlgItemInt(hDlg, nIDButton, &Translated, 1);
      if ( !Translated )
        return 1;
      goto LABEL_24;
    case 0x70u:
LABEL_25:
      DlgItemInt = IsDlgButtonChecked(hDlg, nIDButton);
LABEL_24:
      v12 = DlgItemInt;
      v13 = nIDButton;
LABEL_17:
      UpdateStateInfo(hDlg, v13, v12);
      goto LABEL_12;
    case 0x71u:
      if ( a3 != 1 )
        return 1;
      DlgItem = GetDlgItem(hDlg, 113);
      v11 = SendMessageW(DlgItem, 0x147u, 0, 0);
      v12 = SendMessageW(DlgItem, 0x150u, v11, 0);
      if ( v12 == -1 )
        return 1;
      v13 = 113;
      fChangeCodePage = v12 != *((_DWORD *)gpStateInfo + 52);
      goto LABEL_17;
    case 0x96u:
      goto LABEL_10;
  }
  return 0;
}

```

## disassembly

```asm
0x18000b2e4  push    rbx
0x18000b2e6  push    rbp
0x18000b2e7  push    rsi
0x18000b2e8  push    rdi
0x18000b2e9  sub     rsp, 28h
0x18000b2ed  mov     eax, 97h
0x18000b2f2  mov     [rsp+48h+Translated], 0
0x18000b2fa  mov     rbp, r9
0x18000b2fd  mov     esi, r8d
0x18000b300  mov     ebx, edx
0x18000b302  mov     rdi, rcx
0x18000b305  cmp     edx, eax
0x18000b307  ja      loc_18000B45C
0x18000b30d  jz      short loc_18000B34C
0x18000b30f  mov     eax, edx
0x18000b311  sub     eax, 67h ; 'g'
0x18000b314  jz      loc_18000B44E
0x18000b31a  sub     eax, 1
0x18000b31d  jz      loc_18000B44E
0x18000b323  sub     eax, 4
0x18000b326  jz      loc_18000B3EF
0x18000b32c  sub     eax, 2
0x18000b32f  jz      loc_18000B3EF
0x18000b335  sub     eax, 2
0x18000b338  jz      loc_18000B44E
0x18000b33e  sub     eax, 1
0x18000b341  jz      short loc_18000B370
0x18000b343  cmp     eax, 25h ; '%'
0x18000b346  jnz     loc_18000B495
0x18000b34c  xor     r8d, r8d; int
0x18000b34f  call    ?UpdateStateInfo@@YAHPEAUHWND__@@IH@Z; UpdateStateInfo(HWND__ *,uint,int)
0x18000b354  cmp     esi, 200h
0x18000b35a  jz      short loc_18000B364
0x18000b35c  mov     rcx, rdi; wParam
0x18000b35f  call    ?UpdateApplyButton@@YAXQEAUHWND__@@@Z; UpdateApplyButton(HWND__ * const)
0x18000b364  mov     al, 1
0x18000b366  add     rsp, 28h
0x18000b36a  pop     rdi
0x18000b36b  pop     rsi
0x18000b36c  pop     rbp
0x18000b36d  pop     rbx
0x18000b36e  retn
0x18000b370  cmp     esi, 1
0x18000b373  jnz     short loc_18000B364
0x18000b375  mov     esi, 71h ; 'q'
0x18000b37a  mov     edx, esi; nIDDlgItem
0x18000b37c  call    cs:__imp_GetDlgItem
0x18000b383  nop     dword ptr [rax+rax+00h]
0x18000b388  xor     r9d, r9d; lParam
0x18000b38b  xor     r8d, r8d; wParam
0x18000b38e  mov     rcx, rax; hWnd
0x18000b391  mov     edx, 147h; Msg
0x18000b396  mov     rbx, rax
0x18000b399  call    cs:__imp_SendMessageW
0x18000b3a0  nop     dword ptr [rax+rax+00h]
0x18000b3a5  movsxd  r8, eax; wParam
0x18000b3a8  xor     r9d, r9d; lParam
0x18000b3ab  mov     edx, 150h; Msg
0x18000b3b0  mov     rcx, rbx; hWnd
0x18000b3b3  call    cs:__imp_SendMessageW
0x18000b3ba  nop     dword ptr [rax+rax+00h]
0x18000b3bf  mov     r8, rax; int
0x18000b3c2  cmp     eax, 0FFFFFFFFh
0x18000b3c5  jz      short loc_18000B364
0x18000b3c7  mov     rax, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x18000b3ce  xor     ecx, ecx
0x18000b3d0  mov     edx, esi; unsigned int
0x18000b3d2  cmp     r8d, [rax+0D0h]
0x18000b3d9  setnz   cl
0x18000b3dc  mov     cs:?fChangeCodePage@@3HA, ecx; int fChangeCodePage
0x18000b3e2  mov     rcx, rdi; hDlg
0x18000b3e5  call    ?UpdateStateInfo@@YAHPEAUHWND__@@IH@Z; UpdateStateInfo(HWND__ *,uint,int)
0x18000b3ea  jmp     loc_18000B35C
0x18000b3ef  cmp     esi, 200h
0x18000b3f5  jz      short loc_18000B425
0x18000b3f7  cmp     esi, 400h
0x18000b3fd  jnz     loc_18000B364
0x18000b403  call    ?CheckNum@@YAHPEAUHWND__@@I@Z; CheckNum(HWND__ *,uint)
0x18000b408  test    eax, eax
0x18000b40a  jnz     short loc_18000B419
0x18000b40c  mov     rcx, rbp; HWND
0x18000b40f  call    ?Undo@@YAXPEAUHWND__@@@Z; Undo(HWND__ *)
0x18000b414  jmp     loc_18000B364
0x18000b419  cmp     cs:?g_fSettingsDlgInitialized@@3HA, 0; int g_fSettingsDlgInitialized
0x18000b420  jmp     loc_18000B35A
0x18000b425  mov     r9d, 1; bSigned
0x18000b42b  lea     r8, [rsp+48h+Translated]; lpTranslated
0x18000b430  call    cs:__imp_GetDlgItemInt
0x18000b437  nop     dword ptr [rax+rax+00h]
0x18000b43c  cmp     [rsp+48h+Translated], 0
0x18000b441  jz      loc_18000B364
0x18000b447  mov     r8d, eax
0x18000b44a  mov     edx, ebx; nIDButton
0x18000b44c  jmp     short loc_18000B3E2
0x18000b44e  call    cs:__imp_IsDlgButtonChecked
0x18000b455  nop     dword ptr [rax+rax+00h]
0x18000b45a  jmp     short loc_18000B447
0x18000b45c  mov     eax, ebx
0x18000b45e  sub     eax, 98h
0x18000b463  jz      loc_18000B34C
0x18000b469  sub     eax, 15Dh
0x18000b46e  jz      loc_18000B56C
0x18000b474  sub     eax, 1
0x18000b477  jz      loc_18000B541
0x18000b47d  sub     eax, 1
0x18000b480  jz      loc_18000B516
0x18000b486  sub     eax, 2
0x18000b489  jz      short loc_18000B4EB
0x18000b48b  sub     eax, 2
0x18000b48e  jz      short loc_18000B4C7
0x18000b490  cmp     eax, 8
0x18000b493  jz      short loc_18000B49C
0x18000b495  xor     al, al
0x18000b497  jmp     loc_18000B366
0x18000b49c  mov     edx, 203h; nIDButton
0x18000b4a1  call    cs:__imp_IsDlgButtonChecked
0x18000b4a8  nop     dword ptr [rax+rax+00h]
0x18000b4ad  xor     ecx, ecx
0x18000b4af  cmp     eax, 1
0x18000b4b2  mov     rax, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x18000b4b9  setz    cl; hDlg
0x18000b4bc  mov     [rax+0F8h], ecx
0x18000b4c2  jmp     loc_18000B35C
0x18000b4c7  mov     edx, 1FBh; nIDButton
0x18000b4cc  call    cs:__imp_IsDlgButtonChecked
0x18000b4d3  nop     dword ptr [rax+rax+00h]
0x18000b4d8  xor     ecx, ecx
0x18000b4da  cmp     eax, 1
0x18000b4dd  setz    cl; hDlg
0x18000b4e0  mov     cs:?g_fEditKeys@@3HA, ecx; int g_fEditKeys
0x18000b4e6  jmp     loc_18000B35C
0x18000b4eb  mov     edx, 1F9h; nIDButton
0x18000b4f0  call    cs:__imp_IsDlgButtonChecked
0x18000b4f7  nop     dword ptr [rax+rax+00h]
0x18000b4fc  xor     ecx, ecx
0x18000b4fe  cmp     eax, 1
0x18000b501  mov     rax, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x18000b508  setnz   cl; hDlg
0x18000b50b  mov     [rax+0E0h], ecx
0x18000b511  jmp     loc_18000B35C
0x18000b516  mov     edx, 1F7h; nIDButton
0x18000b51b  call    cs:__imp_IsDlgButtonChecked
0x18000b522  nop     dword ptr [rax+rax+00h]
0x18000b527  xor     ecx, ecx
0x18000b529  cmp     eax, 1
0x18000b52c  mov     rax, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x18000b533  setz    cl; hDlg
0x18000b536  mov     [rax+0DCh], ecx
0x18000b53c  jmp     loc_18000B35C
0x18000b541  mov     edx, 1F6h; nIDButton
0x18000b546  call    cs:__imp_IsDlgButtonChecked
0x18000b54d  nop     dword ptr [rax+rax+00h]
0x18000b552  xor     ecx, ecx
0x18000b554  cmp     eax, 1
0x18000b557  mov     rax, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x18000b55e  setz    cl; hDlg
0x18000b561  mov     [rax+0E4h], ecx
0x18000b567  jmp     loc_18000B35C
0x18000b56c  mov     edx, 1F5h; nIDButton
0x18000b571  call    cs:__imp_IsDlgButtonChecked
0x18000b578  nop     dword ptr [rax+rax+00h]
0x18000b57d  xor     ecx, ecx
0x18000b57f  cmp     eax, 1
0x18000b582  setnz   cl
0x18000b585  mov     cs:?g_fForceV2@@3HA, ecx; int g_fForceV2
0x18000b58b  mov     rcx, rdi; hDlg
0x18000b58e  call    ?ToggleV2OptionsControls@@YAXQEAUHWND__@@@Z; ToggleV2OptionsControls(HWND__ * const)
0x18000b593  jmp     loc_18000B35C
```
