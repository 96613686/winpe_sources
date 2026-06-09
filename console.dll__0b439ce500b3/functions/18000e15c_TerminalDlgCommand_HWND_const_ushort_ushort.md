# TerminalDlgCommand(HWND__ * const,ushort,ushort)

- ea: `0x18000e15c`
- end: `0x18000e418`
- name: `?TerminalDlgCommand@@YA_NQEAUHWND__@@GG@Z`
- size: `700`
- prototype: `bool __fastcall(HWND hDlg, unsigned __int16, unsigned __int16)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000e420`

## callees

- `0x18000705c`
- `0x18000b294`
- `0x18000db24`
- `0x18000e15c`
- `0x18000e804`
- `0x18000ebac`
- `0x18000ed40`
- `0x18000eed4`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18000e353`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18000e376`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18000e353`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18000e376`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18000e336`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18000e336`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x18000e202`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x18000e235`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x18000e253`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x18000e2a0`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x18000e202`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x18000e235`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x18000e253`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x18000e2a0`

## pseudocode

```c
char __fastcall TerminalDlgCommand(HWND hDlg, unsigned __int16 a2, __int16 a3)
{
  char v4; // di
  UINT v5; // eax
  UINT v6; // eax
  UINT v7; // eax
  HWND DlgItem; // rbx
  int v9; // eax
  LRESULT v10; // rax
  void (__fastcall *v11)(HWND, unsigned __int16); // rax
  _QWORD v13[8]; // [rsp+20h] [rbp-40h] BYREF

  v4 = 0;
  if ( a2 > 0x26Fu )
  {
    if ( a2 != 624 && a2 != 625 )
    {
      if ( a2 == 626 || a2 == 627 || a2 == 628 )
      {
        v13[0] = ___7___Func_impl_no_alloc_P6AXPEAUHWND____G__EXPEAU1_G_std__6B_;
        v11 = _ChangeBackgroundRGB;
      }
      else
      {
        if ( a2 != 629 && a2 != 630 && a2 != 631 )
        {
          if ( a2 == 641 && a3 == 1 )
          {
            DlgItem = GetDlgItem(hDlg, 641);
            v9 = SendMessageW(DlgItem, 0x147u, 0, 0);
            if ( v9 != -1 )
            {
              v10 = SendMessageW(DlgItem, 0x150u, v9, 0);
              g_selectedPackage = *(_OWORD *)v10;
              xmmword_180023290 = *(_OWORD *)(v10 + 16);
              dword_1800232A0 = *(_DWORD *)(v10 + 32);
              DelegationConfig::PackageInfo::operator=(qword_1800232A8, v10 + 40);
            }
          }
          return v4;
        }
        v13[0] = ___7___Func_impl_no_alloc_P6AXPEAUHWND____G__EXPEAU1_G_std__6B_;
        v11 = _ChangeCursorRGB;
      }
LABEL_37:
      v13[1] = v11;
      v13[7] = v13;
      return _CommandColorInput(hDlg);
    }
LABEL_36:
    v13[0] = ___7___Func_impl_no_alloc_P6AXPEAUHWND____G__EXPEAU1_G_std__6B_;
    v11 = _ChangeForegroundRGB;
    goto LABEL_37;
  }
  if ( a2 == 623 )
    goto LABEL_36;
  if ( a2 > 0x26Au )
  {
    if ( a2 != 619 && a2 != 620 && a2 != 621 )
    {
      if ( a2 != 622 )
        return v4;
      *((_DWORD *)gpStateInfo + 65) = IsDlgButtonChecked(hDlg, 622);
      UpdateApplyButton(hDlg);
      return 1;
    }
LABEL_10:
    *((_DWORD *)gpStateInfo + 60) = a2 - 617;
    UpdateApplyButton(hDlg);
    if ( g_hOptionsDlg != HWND_MESSAGE|0x2LL )
      InitializeCursorSize(g_hOptionsDlg);
    return 1;
  }
  switch ( a2 )
  {
    case 0x26Au:
      goto LABEL_10;
    case 0x259u:
      v7 = IsDlgButtonChecked(hDlg, 601);
      _UseForeground(hDlg, v7 != 0);
      goto LABEL_14;
    case 0x25Du:
      v6 = IsDlgButtonChecked(hDlg, 605);
      _UseBackground(hDlg, v6 != 0);
      goto LABEL_14;
    case 0x263u:
    case 0x264u:
      v5 = IsDlgButtonChecked(hDlg, 612);
      _UseCursorColor(hDlg, v5 != 0);
LABEL_14:
      v4 = 1;
      UpdateApplyButton(hDlg);
      return v4;
    case 0x269u:
      goto LABEL_10;
  }
  return v4;
}

```

## disassembly

```asm
0x18000e15c  mov     [rsp-8+arg_0], rbx
0x18000e161  mov     [rsp-8+arg_8], rdi
0x18000e166  push    rbp
0x18000e167  mov     rbp, rsp
0x18000e16a  sub     rsp, 60h
0x18000e16e  mov     rbx, rcx
0x18000e171  xor     dil, dil
0x18000e174  movzx   r9d, dx
0x18000e178  mov     eax, 26Fh
0x18000e17d  cmp     r9d, eax
0x18000e180  ja      loc_18000E2C6
0x18000e186  jz      loc_18000E3DA
0x18000e18c  mov     eax, 26Ah
0x18000e191  cmp     r9d, eax
0x18000e194  ja      loc_18000E26E
0x18000e19a  jz      short loc_18000E1C2
0x18000e19c  mov     ecx, r9d
0x18000e19f  lea     edx, [rax-11h]; nIDButton
0x18000e1a2  sub     ecx, edx
0x18000e1a4  jz      loc_18000E250
0x18000e1aa  sub     ecx, 4
0x18000e1ad  jz      short loc_18000E22D
0x18000e1af  sub     ecx, 6
0x18000e1b2  jz      short loc_18000E1FA
0x18000e1b4  sub     ecx, 1
0x18000e1b7  jz      short loc_18000E1FA
0x18000e1b9  cmp     ecx, 5
0x18000e1bc  jnz     loc_18000E404
0x18000e1c2  lea     ecx, [r9-269h]
0x18000e1c9  mov     rax, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x18000e1d0  mov     [rax+0F0h], ecx
0x18000e1d6  mov     rcx, rbx; wParam
0x18000e1d9  call    ?UpdateApplyButton@@YAXQEAUHWND__@@@Z; UpdateApplyButton(HWND__ * const)
0x18000e1de  mov     rcx, cs:?g_hOptionsDlg@@3PEAUHWND__@@EA; HWND
0x18000e1e5  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000e1e9  jz      short loc_18000E1F0
0x18000e1eb  call    ?InitializeCursorSize@@YAXQEAUHWND__@@@Z; InitializeCursorSize(HWND__ * const)
0x18000e1f0  mov     edi, 1
0x18000e1f5  jmp     loc_18000E404
0x18000e1fa  mov     edx, 264h; nIDButton
0x18000e1ff  mov     rcx, rbx; hDlg
0x18000e202  call    cs:__imp_IsDlgButtonChecked
0x18000e209  nop     dword ptr [rax+rax+00h]
0x18000e20e  test    eax, eax
0x18000e210  setnz   dl; bool
0x18000e213  mov     rcx, rbx; hDlg
0x18000e216  call    ?_UseCursorColor@@YAXQEAUHWND__@@_N@Z; _UseCursorColor(HWND__ * const,bool)
0x18000e21b  mov     edi, 1
0x18000e220  mov     rcx, rbx; wParam
0x18000e223  call    ?UpdateApplyButton@@YAXQEAUHWND__@@@Z; UpdateApplyButton(HWND__ * const)
0x18000e228  jmp     loc_18000E404
0x18000e22d  mov     edx, 25Dh; nIDButton
0x18000e232  mov     rcx, rbx; hDlg
0x18000e235  call    cs:__imp_IsDlgButtonChecked
0x18000e23c  nop     dword ptr [rax+rax+00h]
0x18000e241  test    eax, eax
0x18000e243  setnz   dl; bool
0x18000e246  mov     rcx, rbx; hDlg
0x18000e249  call    ?_UseBackground@@YAXQEAUHWND__@@_N@Z; _UseBackground(HWND__ * const,bool)
0x18000e24e  jmp     short loc_18000E21B
0x18000e250  mov     rcx, rbx; hDlg
0x18000e253  call    cs:__imp_IsDlgButtonChecked
0x18000e25a  nop     dword ptr [rax+rax+00h]
0x18000e25f  test    eax, eax
0x18000e261  setnz   dl; bool
0x18000e264  mov     rcx, rbx; hDlg
0x18000e267  call    ?_UseForeground@@YAXQEAUHWND__@@_N@Z; _UseForeground(HWND__ * const,bool)
0x18000e26c  jmp     short loc_18000E21B
0x18000e26e  mov     ecx, r9d
0x18000e271  sub     ecx, 26Bh
0x18000e277  jz      loc_18000E1C2
0x18000e27d  sub     ecx, 1
0x18000e280  jz      loc_18000E1C2
0x18000e286  sub     ecx, 1
0x18000e289  jz      loc_18000E1C2
0x18000e28f  cmp     ecx, 1
0x18000e292  jnz     loc_18000E404
0x18000e298  mov     edx, 26Eh; nIDButton
0x18000e29d  mov     rcx, rbx; hDlg
0x18000e2a0  call    cs:__imp_IsDlgButtonChecked
0x18000e2a7  nop     dword ptr [rax+rax+00h]
0x18000e2ac  mov     rcx, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x18000e2b3  mov     [rcx+104h], eax
0x18000e2b9  mov     rcx, rbx; wParam
0x18000e2bc  call    ?UpdateApplyButton@@YAXQEAUHWND__@@@Z; UpdateApplyButton(HWND__ * const)
0x18000e2c1  jmp     loc_18000E1F0
0x18000e2c6  sub     r9d, 270h
0x18000e2cd  jz      loc_18000E3DA
0x18000e2d3  sub     r9d, 1
0x18000e2d7  jz      loc_18000E3DA
0x18000e2dd  sub     r9d, 1
0x18000e2e1  jz      loc_18000E3C6
0x18000e2e7  sub     r9d, 1
0x18000e2eb  jz      loc_18000E3C6
0x18000e2f1  sub     r9d, 1
0x18000e2f5  jz      loc_18000E3C6
0x18000e2fb  sub     r9d, 1
0x18000e2ff  jz      loc_18000E3B2
0x18000e305  sub     r9d, 1
0x18000e309  jz      loc_18000E3B2
0x18000e30f  sub     r9d, 1
0x18000e313  jz      loc_18000E3B2
0x18000e319  cmp     r9d, 0Ah
0x18000e31d  jnz     loc_18000E404
0x18000e323  lea     eax, [r9-9]
0x18000e327  cmp     ax, r8w
0x18000e32b  jnz     loc_18000E404
0x18000e331  mov     edx, 281h; nIDDlgItem
0x18000e336  call    cs:__imp_GetDlgItem
0x18000e33d  nop     dword ptr [rax+rax+00h]
0x18000e342  mov     rbx, rax
0x18000e345  xor     r9d, r9d; lParam
0x18000e348  xor     r8d, r8d; wParam
0x18000e34b  mov     edx, 147h; Msg
0x18000e350  mov     rcx, rax; hWnd
0x18000e353  call    cs:__imp_SendMessageW
0x18000e35a  nop     dword ptr [rax+rax+00h]
0x18000e35f  cmp     eax, 0FFFFFFFFh
0x18000e362  jz      loc_18000E404
0x18000e368  movsxd  r8, eax; wParam
0x18000e36b  xor     r9d, r9d; lParam
0x18000e36e  mov     edx, 150h; Msg
0x18000e373  mov     rcx, rbx; hWnd
0x18000e376  call    cs:__imp_SendMessageW
0x18000e37d  nop     dword ptr [rax+rax+00h]
0x18000e382  movups  xmm0, xmmword ptr [rax]
0x18000e385  movaps  cs:?g_selectedPackage@@3UDelegationPackage@DelegationConfig@@A, xmm0; DelegationConfig::DelegationPackage g_selectedPackage
0x18000e38c  movups  xmm1, xmmword ptr [rax+10h]
0x18000e390  movaps  cs:xmmword_180023290, xmm1
0x18000e397  mov     ecx, [rax+20h]
0x18000e39a  mov     cs:dword_1800232A0, ecx
0x18000e3a0  lea     rdx, [rax+28h]
0x18000e3a4  lea     rcx, qword_1800232A8
0x18000e3ab  call    ??4PackageInfo@DelegationConfig@@QEAAAEAU01@AEBU01@@Z; DelegationConfig::PackageInfo::operator=(DelegationConfig::PackageInfo const &)
0x18000e3b0  jmp     short loc_18000E404
0x18000e3b2  lea     rax, ??_7?$_Func_impl_no_alloc@P6AXPEAUHWND__@@G@_EXPEAU1@G@std@@6B@
0x18000e3b9  mov     [rbp+var_40], rax
0x18000e3bd  lea     rax, ?_ChangeCursorRGB@@YAXQEAUHWND__@@G@Z; _ChangeCursorRGB(HWND__ * const,ushort)
0x18000e3c4  jmp     short loc_18000E3EC
0x18000e3c6  lea     rax, ??_7?$_Func_impl_no_alloc@P6AXPEAUHWND__@@G@_EXPEAU1@G@std@@6B@
0x18000e3cd  mov     [rbp+var_40], rax
0x18000e3d1  lea     rax, ?_ChangeBackgroundRGB@@YAXQEAUHWND__@@G@Z; _ChangeBackgroundRGB(HWND__ * const,ushort)
0x18000e3d8  jmp     short loc_18000E3EC
0x18000e3da  lea     rax, ??_7?$_Func_impl_no_alloc@P6AXPEAUHWND__@@G@_EXPEAU1@G@std@@6B@
0x18000e3e1  mov     [rbp+var_40], rax
0x18000e3e5  lea     rax, ?_ChangeForegroundRGB@@YAXQEAUHWND__@@G@Z; _ChangeForegroundRGB(HWND__ * const,ushort)
0x18000e3ec  mov     [rbp+var_38], rax
0x18000e3f0  lea     rax, [rbp+var_40]
0x18000e3f4  mov     [rbp+var_8], rax
0x18000e3f8  lea     r9, [rbp+var_40]
0x18000e3fc  call    ?_CommandColorInput@@YA_NQEAUHWND__@@GGV?$function@$$A6AXPEAUHWND__@@G@Z@std@@@Z; _CommandColorInput(HWND__ * const,ushort,ushort,std::function<void (HWND__ *,ushort)>)
0x18000e401  mov     dil, al
0x18000e404  mov     al, dil
0x18000e407  mov     rbx, [rsp+60h+arg_0]
0x18000e40c  mov     rdi, [rsp+60h+arg_8]
0x18000e411  add     rsp, 60h
0x18000e415  pop     rbp
0x18000e416  retn
```
