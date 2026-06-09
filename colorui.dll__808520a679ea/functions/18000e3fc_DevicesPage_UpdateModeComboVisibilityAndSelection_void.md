# DevicesPage::UpdateModeComboVisibilityAndSelection(void)

- ea: `0x18000e3fc`
- end: `0x18000e550`
- name: `?UpdateModeComboVisibilityAndSelection@DevicesPage@@AEAAJXZ`
- size: `340`
- prototype: `__int64 __fastcall(DevicesPage *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000d67c`
- `0x18000e144`

## callees

- `0x18000ccc0`
- `0x18000cd08`
- `0x18000e3fc`
- `0x180011f4c`

## import_xrefs

- `USER32!SendMessageW` at `0x18000e4d3`
- `USER32!SendMessageW` at `0x18000e4fc`
- `USER32!SendMessageW` at `0x18000e524`
- `USER32!SendMessageW` at `0x18000e4d3`
- `USER32!SendMessageW` at `0x18000e4fc`
- `USER32!SendMessageW` at `0x18000e524`
- `USER32!ShowWindow` at `0x18000e466`
- `USER32!ShowWindow` at `0x18000e480`
- `USER32!ShowWindow` at `0x18000e466`
- `USER32!ShowWindow` at `0x18000e480`
- `USER32!GetDlgItem` at `0x18000e45b`
- `USER32!GetDlgItem` at `0x18000e475`
- `USER32!GetDlgItem` at `0x18000e45b`
- `USER32!GetDlgItem` at `0x18000e475`

## pseudocode

```c
__int64 __fastcall DevicesPage::UpdateModeComboVisibilityAndSelection(DevicesPage *this)
{
  __int64 result; // rax
  signed int PrinterConfigMode; // esi
  struct Device *v4; // r14
  int v5; // ebx
  int v6; // edi
  HWND DlgItem; // rax
  HWND v8; // rax
  unsigned int SettingsScope; // eax
  ColorDataController *v10; // rcx
  int v11; // eax
  int v12; // edi
  int v13; // ebx
  _DWORD *v14; // rax
  struct Device *v15; // [rsp+40h] [rbp+8h] BYREF

  v15 = 0;
  result = Combo<Device>::GetSelectedLParam(*((HWND **)this + 11), (LRESULT *)&v15);
  PrinterConfigMode = result;
  if ( (int)result >= 0 )
  {
    if ( (_DWORD)result == 1 )
    {
      return 0;
    }
    else
    {
      v4 = v15;
      v5 = 5;
      v6 = *(_DWORD *)v15;
      if ( *(_DWORD *)v15 != 1886549106 )
        v5 = 0;
      DlgItem = GetDlgItem(*((HWND *)this + 1), 1107);
      ShowWindow(DlgItem, v5);
      v8 = GetDlgItem(*((HWND *)this + 1), 1108);
      ShowWindow(v8, v5);
      if ( v6 == 1886549106 )
      {
        LODWORD(v15) = 1;
        SettingsScope = DevicesPage::GetReadSettingsScope(this);
        PrinterConfigMode = ColorDataController::GetPrinterConfigMode(v10, SettingsScope, v4, (int *)&v15);
        if ( PrinterConfigMode < 0 )
        {
          LODWORD(v15) = 0;
          PrinterConfigMode = 0;
        }
        v11 = SendMessageW(**((HWND **)this + 12), 0x146u, 0, 0);
        v12 = v11;
        if ( v11 == -1 )
          return 2147500037LL;
        v13 = 0;
        if ( v11 > 0 )
        {
          while ( 1 )
          {
            v14 = (_DWORD *)SendMessageW(**((HWND **)this + 12), 0x150u, v13, 0);
            if ( v14 == (_DWORD *)-1LL )
              break;
            PrinterConfigMode = 0;
            if ( *v14 == (_DWORD)v15 )
              SendMessageW(**((HWND **)this + 12), 0x14Eu, v13, 0);
            if ( ++v13 >= v12 )
              return (unsigned int)PrinterConfigMode;
          }
          return 2147500037LL;
        }
      }
    }
    return (unsigned int)PrinterConfigMode;
  }
  return result;
}

```

## disassembly

```asm
0x18000e3fc  mov     rax, rsp
0x18000e3ff  mov     [rax+10h], rbx
0x18000e403  mov     [rax+18h], rbp
0x18000e407  push    rsi
0x18000e408  push    rdi
0x18000e409  push    r14
0x18000e40b  sub     rsp, 20h
0x18000e40f  mov     rbp, rcx
0x18000e412  mov     qword ptr [rax+8], 0
0x18000e41a  mov     rcx, [rcx+58h]
0x18000e41e  lea     rdx, [rax+8]
0x18000e422  call    ?GetSelectedLParam@?$Combo@UDevice@@@@QEBAJPEAPEAUDevice@@@Z; Combo<Device>::GetSelectedLParam(Device * *)
0x18000e427  mov     esi, eax
0x18000e429  test    eax, eax
0x18000e42b  js      loc_18000E53D
0x18000e431  cmp     eax, 1
0x18000e434  jz      loc_18000E539
0x18000e43a  mov     r14, [rsp+38h+arg_0]
0x18000e43f  xor     eax, eax
0x18000e441  mov     rcx, [rbp+8]; hDlg
0x18000e445  mov     ebx, 5
0x18000e44a  mov     edx, 453h; nIDDlgItem
0x18000e44f  mov     edi, [r14]
0x18000e452  cmp     edi, 70727472h
0x18000e458  cmovnz  ebx, eax
0x18000e45b  call    cs:__imp_GetDlgItem
0x18000e461  mov     rcx, rax; hWnd
0x18000e464  mov     edx, ebx; nCmdShow
0x18000e466  call    cs:__imp_ShowWindow
0x18000e46c  mov     rcx, [rbp+8]; hDlg
0x18000e470  mov     edx, 454h; nIDDlgItem
0x18000e475  call    cs:__imp_GetDlgItem
0x18000e47b  mov     rcx, rax; hWnd
0x18000e47e  mov     edx, ebx; nCmdShow
0x18000e480  call    cs:__imp_ShowWindow
0x18000e486  cmp     edi, 70727472h
0x18000e48c  jnz     loc_18000E53B
0x18000e492  mov     rcx, rbp; this
0x18000e495  mov     dword ptr [rsp+38h+arg_0], 1
0x18000e49d  call    ?GetReadSettingsScope@DevicesPage@@AEAA?AW4WCS_PROFILE_MANAGEMENT_SCOPE@@XZ; DevicesPage::GetReadSettingsScope(void)
0x18000e4a2  lea     r9, [rsp+38h+arg_0]; int *
0x18000e4a7  mov     r8, r14; struct Device *
0x18000e4aa  mov     edx, eax; enum WCS_PROFILE_MANAGEMENT_SCOPE
0x18000e4ac  call    ?GetPrinterConfigMode@ColorDataController@@QEBAJW4WCS_PROFILE_MANAGEMENT_SCOPE@@AEBUDevice@@PEAH@Z; ColorDataController::GetPrinterConfigMode(WCS_PROFILE_MANAGEMENT_SCOPE,Device const &,int *)
0x18000e4b1  mov     esi, eax
0x18000e4b3  test    eax, eax
0x18000e4b5  jns     short loc_18000E4C1
0x18000e4b7  mov     dword ptr [rsp+38h+arg_0], 0
0x18000e4bf  xor     esi, esi
0x18000e4c1  mov     rcx, [rbp+60h]
0x18000e4c5  xor     r9d, r9d; lParam
0x18000e4c8  xor     r8d, r8d; wParam
0x18000e4cb  mov     edx, 146h; Msg
0x18000e4d0  mov     rcx, [rcx]; hWnd
0x18000e4d3  call    cs:__imp_SendMessageW
0x18000e4d9  mov     rdi, rax
0x18000e4dc  cmp     eax, 0FFFFFFFFh
0x18000e4df  jz      short loc_18000E532
0x18000e4e1  xor     ebx, ebx
0x18000e4e3  test    edi, edi
0x18000e4e5  jle     short loc_18000E53B
0x18000e4e7  mov     rcx, [rbp+60h]
0x18000e4eb  xor     r9d, r9d; lParam
0x18000e4ee  movsxd  r14, ebx
0x18000e4f1  mov     edx, 150h; Msg
0x18000e4f6  mov     r8, r14; wParam
0x18000e4f9  mov     rcx, [rcx]; hWnd
0x18000e4fc  call    cs:__imp_SendMessageW
0x18000e502  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000e506  jz      short loc_18000E532
0x18000e508  mov     ecx, dword ptr [rsp+38h+arg_0]
0x18000e50c  xor     esi, esi
0x18000e50e  cmp     [rax], ecx
0x18000e510  jnz     short loc_18000E52A
0x18000e512  mov     rcx, [rbp+60h]
0x18000e516  xor     r9d, r9d; lParam
0x18000e519  mov     r8, r14; wParam
0x18000e51c  mov     edx, 14Eh; Msg
0x18000e521  mov     rcx, [rcx]; hWnd
0x18000e524  call    cs:__imp_SendMessageW
0x18000e52a  inc     ebx
0x18000e52c  cmp     ebx, edi
0x18000e52e  jl      short loc_18000E4E7
0x18000e530  jmp     short loc_18000E53B
0x18000e532  mov     eax, 80004005h
0x18000e537  jmp     short loc_18000E53D
0x18000e539  xor     esi, esi
0x18000e53b  mov     eax, esi
0x18000e53d  mov     rbx, [rsp+38h+arg_8]
0x18000e542  mov     rbp, [rsp+38h+arg_10]
0x18000e547  add     rsp, 20h
0x18000e54b  pop     r14
0x18000e54d  pop     rdi
0x18000e54e  pop     rsi
0x18000e54f  retn
```
