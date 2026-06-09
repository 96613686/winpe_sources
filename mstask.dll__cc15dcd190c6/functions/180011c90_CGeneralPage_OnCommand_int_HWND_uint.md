# CGeneralPage::_OnCommand(int,HWND__ *,uint)

- ea: `0x180011c90`
- end: `0x180011f86`
- name: `?_OnCommand@CGeneralPage@@EEAA_JHPEAUHWND__@@I@Z`
- size: `758`
- prototype: `__int64 __fastcall(CGeneralPage *__hidden this, int, HWND, unsigned int)`
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800082f4`
- `0x18000cd0c`
- `0x1800110c4`
- `0x18001140c`
- `0x180011568`
- `0x180011c90`
- `0x18001296c`
- `0x18001aa9a`
- `0x18001aac0`
- `0x18001b010`

## import_xrefs

- `msvcrt!wcschr` at `0x180011d05`
- `msvcrt!wcschr` at `0x180011d05`
- `USER32!SendMessageW` at `0x180011d56`
- `USER32!SendMessageW` at `0x180011d56`
- `USER32!EnableWindow` at `0x180011e2e`
- `USER32!EnableWindow` at `0x180011f46`
- `USER32!EnableWindow` at `0x180011e2e`
- `USER32!EnableWindow` at `0x180011f46`
- `USER32!DialogBoxParamW` at `0x180011da4`
- `USER32!DialogBoxParamW` at `0x180011da4`
- `USER32!GetDlgItem` at `0x180011d3c`
- `USER32!GetDlgItem` at `0x180011e1a`
- `USER32!GetDlgItem` at `0x180011f13`
- `USER32!GetDlgItem` at `0x180011d3c`
- `USER32!GetDlgItem` at `0x180011e1a`
- `USER32!GetDlgItem` at `0x180011f13`
- `USER32!SetDlgItemTextW` at `0x180011d2d`
- `USER32!SetDlgItemTextW` at `0x180011d2d`
- `USER32!IsDlgButtonChecked` at `0x180011f2a`
- `USER32!IsDlgButtonChecked` at `0x180011f2a`

## pseudocode

```c
__int64 __fastcall CGeneralPage::_OnCommand(CGeneralPage *this, __int64 a2, HWND a3, int a4)
{
  HWND v5; // rax
  int v6; // edx
  int v7; // edx
  int v8; // edx
  bool v10; // zf
  HWND v11; // rax
  int v12; // eax
  unsigned int v13; // eax
  unsigned __int64 v14; // r8
  __int64 v15; // rcx
  wchar_t *v16; // rax
  unsigned __int64 v17; // r8
  wchar_t *v18; // rdx
  HWND DlgItem; // rdi
  BOOL v20; // edx
  wchar_t Str[264]; // [rsp+30h] [rbp-228h] BYREF

  if ( (_DWORD)a2 != 1655 )
  {
    if ( (_DWORD)a2 == 1000 && !a4 )
    {
      DialogBoxParamW(g_hInstance, (LPCWSTR)0x66, *((HWND *)this + 14), (DLGPROC)SetPasswordDlgProc, (LPARAM)this + 664);
      *((_DWORD *)this + 196) = 1;
      goto LABEL_47;
    }
LABEL_13:
    if ( a4 != 768 )
    {
      if ( a4 == 512 && (_DWORD)a2 == 1654 )
      {
        if ( (*((_BYTE *)this + 696) & 2) == 0 )
          return 1;
        memset_0(Str, 0, 0x20Au);
        v15 = 261;
        v16 = Str;
        do
        {
          *(_BYTE *)v16 = 0;
          v16 = (wchar_t *)((char *)v16 + 1);
          --v15;
        }
        while ( v15 );
        CGeneralPage::_GetAppAndArgs(this, Str, v14, 0);
        if ( IsLocalFilename((const unsigned __int16 *)this + 70) )
          CGeneralPage::_ExpandAppName(this, Str, v17);
        v18 = Str;
      }
      else
      {
        if ( (_DWORD)a2 != 1664 )
        {
          if ( (_DWORD)a2 != 1668 )
            return 1;
          DlgItem = GetDlgItem(*((HWND *)this + 14), 1000);
          if ( !DlgItem )
            return 1;
          if ( IsDlgButtonChecked(*((HWND *)this + 14), 1668) == 1 )
          {
            v20 = 0;
          }
          else
          {
            if ( !*((_DWORD *)this + 182) )
              goto LABEL_47;
            v20 = 1;
          }
          EnableWindow(DlgItem, v20);
          goto LABEL_47;
        }
        (*(void (__fastcall **)(CGeneralPage *, __int64, HWND))(*(_QWORD *)this + 144LL))(this, a2, a3);
        *((_DWORD *)this + 174) |= 0x10u;
        v18 = 0;
      }
      CGeneralPage::_UpdateAppIcon(this, v18);
      return 1;
    }
    v6 = a2 - 1652;
    if ( v6 )
    {
      v7 = v6 - 2;
      if ( v7 )
      {
        v8 = v7 - 5;
        if ( v8 )
        {
          if ( v8 != 8 )
            return 0;
          *((_DWORD *)this + 174) |= 4u;
          goto LABEL_47;
        }
        if ( *((_DWORD *)this + 193) )
        {
          *((_DWORD *)this + 174) |= 8u;
          v10 = *((_DWORD *)this + 181) == 0;
          *((_DWORD *)this + 182) = 1;
          if ( v10 )
          {
            v11 = GetDlgItem(*((HWND *)this + 14), 1000);
            if ( v11 )
              EnableWindow(v11, 1);
          }
          goto LABEL_47;
        }
        return 1;
      }
      v12 = *((_DWORD *)this + 174);
      if ( (v12 & 0x20) != 0 )
        v13 = v12 & 0xFFFFFFDF;
      else
        v13 = v12 | 0x12;
      *((_DWORD *)this + 174) = v13;
    }
    else
    {
      *((_DWORD *)this + 174) |= 1u;
    }
LABEL_47:
    (*(void (__fastcall **)(CGeneralPage *))(*(_QWORD *)this + 144LL))(this);
    return 1;
  }
  if ( a4 )
    goto LABEL_13;
  memset_0(Str, 0, 0x20Au);
  if ( CGeneralPage::_Browse(this, Str) )
  {
    if ( wcschr(Str, 0x20u) )
      AddQuotes(Str, 0x104u);
    SetDlgItemTextW(*((HWND *)this + 14), 1654, Str);
    v5 = GetDlgItem(*((HWND *)this + 14), 1667);
    if ( v5 )
      SendMessageW(*((HWND *)this + 14), 0x28u, (WPARAM)v5, 1);
    CGeneralPage::_UpdateAppIcon(this, Str);
    goto LABEL_47;
  }
  return 1;
}

```

## disassembly

```asm
0x180011c90  mov     [rsp+arg_8], rbx
0x180011c95  mov     [rsp+arg_10], rbp
0x180011c9a  push    rdi
0x180011c9b  sub     rsp, 250h
0x180011ca2  mov     rax, cs:__security_cookie
0x180011ca9  xor     rax, rsp
0x180011cac  mov     [rsp+258h+var_18], rax
0x180011cb4  mov     rbx, rcx
0x180011cb7  mov     ecx, 3E8h
0x180011cbc  mov     ebp, 1
0x180011cc1  cmp     edx, 677h
0x180011cc7  jnz     loc_180011D78
0x180011ccd  test    r9d, r9d
0x180011cd0  jnz     loc_180011DB2
0x180011cd6  xor     edx, edx; Val
0x180011cd8  lea     rcx, [rsp+258h+Str]; void *
0x180011cdd  mov     r8d, 20Ah; Size
0x180011ce3  call    memset_0
0x180011ce8  lea     rdx, [rsp+258h+Str]; unsigned __int16 *
0x180011ced  mov     rcx, rbx; this
0x180011cf0  call    ?_Browse@CGeneralPage@@AEAAHQEAG_K@Z; CGeneralPage::_Browse(ushort * const,unsigned __int64)
0x180011cf5  test    eax, eax
0x180011cf7  jz      loc_180011F5E
0x180011cfd  lea     edx, [rbp+1Fh]; Ch
0x180011d00  lea     rcx, [rsp+258h+Str]; Str
0x180011d05  call    cs:__imp_wcschr
0x180011d0b  test    rax, rax
0x180011d0e  jz      short loc_180011D1F
0x180011d10  mov     edx, 104h; unsigned int
0x180011d15  lea     rcx, [rsp+258h+Str]; Src
0x180011d1a  call    ?AddQuotes@@YAXPEAGK@Z; AddQuotes(ushort *,ulong)
0x180011d1f  mov     rcx, [rbx+70h]; hDlg
0x180011d23  lea     r8, [rsp+258h+Str]; lpString
0x180011d28  mov     edx, 676h; nIDDlgItem
0x180011d2d  call    cs:__imp_SetDlgItemTextW
0x180011d33  mov     rcx, [rbx+70h]; hDlg
0x180011d37  mov     edx, 683h; nIDDlgItem
0x180011d3c  call    cs:__imp_GetDlgItem
0x180011d42  test    rax, rax
0x180011d45  jz      short loc_180011D5C
0x180011d47  mov     rcx, [rbx+70h]; hWnd
0x180011d4b  mov     r9, rbp; lParam
0x180011d4e  mov     r8, rax; wParam
0x180011d51  mov     edx, 28h ; '('; Msg
0x180011d56  call    cs:__imp_SendMessageW
0x180011d5c  lea     rdx, [rsp+258h+Str]; unsigned __int16 *
0x180011d61  mov     rcx, rbx; this
0x180011d64  call    ?_UpdateAppIcon@CGeneralPage@@AEAAXPEBG@Z; CGeneralPage::_UpdateAppIcon(ushort const *)
0x180011d69  mov     rax, [rbx]
0x180011d6c  mov     rax, [rax+90h]
0x180011d73  jmp     loc_180011F56
0x180011d78  cmp     edx, ecx
0x180011d7a  jnz     short loc_180011DB2
0x180011d7c  test    r9d, r9d
0x180011d7f  jnz     short loc_180011DB2
0x180011d81  mov     r8, [rbx+70h]; hWndParent
0x180011d85  lea     rax, [rbx+298h]
0x180011d8c  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180011d93  lea     r9, ?SetPasswordDlgProc@@YA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x180011d9a  mov     edx, 66h ; 'f'; lpTemplateName
0x180011d9f  mov     [rsp+258h+dwInitParam], rax; dwInitParam
0x180011da4  call    cs:__imp_DialogBoxParamW
0x180011daa  mov     [rbx+310h], ebp
0x180011db0  jmp     short loc_180011D69
0x180011db2  cmp     r9d, 300h
0x180011db9  jnz     loc_180011E61
0x180011dbf  sub     edx, 674h
0x180011dc5  jz      loc_180011E56
0x180011dcb  sub     edx, 2
0x180011dce  jz      short loc_180011E39
0x180011dd0  sub     edx, 5
0x180011dd3  jz      short loc_180011DED
0x180011dd5  cmp     edx, 8
0x180011dd8  jz      short loc_180011DE1
0x180011dda  xor     eax, eax
0x180011ddc  jmp     loc_180011F61
0x180011de1  or      dword ptr [rbx+2B8h], 4
0x180011de8  jmp     loc_180011D69
0x180011ded  cmp     dword ptr [rbx+304h], 0
0x180011df4  jz      loc_180011F5E
0x180011dfa  or      dword ptr [rbx+2B8h], 8
0x180011e01  cmp     dword ptr [rbx+2D4h], 0
0x180011e08  mov     [rbx+2D8h], ebp
0x180011e0e  jnz     loc_180011D69
0x180011e14  mov     edx, ecx; nIDDlgItem
0x180011e16  mov     rcx, [rbx+70h]; hDlg
0x180011e1a  call    cs:__imp_GetDlgItem
0x180011e20  test    rax, rax
0x180011e23  jz      loc_180011D69
0x180011e29  mov     edx, ebp; bEnable
0x180011e2b  mov     rcx, rax; hWnd
0x180011e2e  call    cs:__imp_EnableWindow
0x180011e34  jmp     loc_180011D69
0x180011e39  mov     eax, [rbx+2B8h]
0x180011e3f  test    al, 20h
0x180011e41  jz      short loc_180011E48
0x180011e43  and     eax, 0FFFFFFDFh
0x180011e46  jmp     short loc_180011E4B
0x180011e48  or      eax, 12h
0x180011e4b  mov     [rbx+2B8h], eax
0x180011e51  jmp     loc_180011D69
0x180011e56  or      [rbx+2B8h], ebp
0x180011e5c  jmp     loc_180011D69
0x180011e61  cmp     r9d, 200h
0x180011e68  jnz     short loc_180011ED8
0x180011e6a  cmp     edx, 676h
0x180011e70  jnz     short loc_180011ED8
0x180011e72  test    byte ptr [rbx+2B8h], 2
0x180011e79  jz      loc_180011F5E
0x180011e7f  xor     edx, edx; Val
0x180011e81  lea     r8d, [r9+0Ah]; Size
0x180011e85  lea     rcx, [rsp+258h+Str]; void *
0x180011e8a  call    memset_0
0x180011e8f  mov     ecx, 105h
0x180011e94  lea     rax, [rsp+258h+Str]
0x180011e99  mov     byte ptr [rax], 0
0x180011e9c  add     rax, rbp
0x180011e9f  sub     rcx, rbp
0x180011ea2  jnz     short loc_180011E99
0x180011ea4  xor     r9d, r9d; unsigned __int16 **
0x180011ea7  lea     rdx, [rsp+258h+Str]; unsigned __int16 *
0x180011eac  mov     rcx, rbx; this
0x180011eaf  call    ?_GetAppAndArgs@CGeneralPage@@AEAAXPEAG_KPEAPEAG@Z; CGeneralPage::_GetAppAndArgs(ushort *,unsigned __int64,ushort * *)
0x180011eb4  lea     rcx, [rbx+8Ch]; unsigned __int16 *
0x180011ebb  call    ?IsLocalFilename@@YAHPEBG@Z; IsLocalFilename(ushort const *)
0x180011ec0  test    eax, eax
0x180011ec2  jz      short loc_180011ED1
0x180011ec4  lea     rdx, [rsp+258h+Str]; unsigned __int16 *
0x180011ec9  mov     rcx, rbx; this
0x180011ecc  call    ?_ExpandAppName@CGeneralPage@@AEAAXPEAG_K@Z; CGeneralPage::_ExpandAppName(ushort *,unsigned __int64)
0x180011ed1  lea     rdx, [rsp+258h+Str]
0x180011ed6  jmp     short loc_180011EFB
0x180011ed8  cmp     edx, 680h
0x180011ede  jnz     short loc_180011F05
0x180011ee0  mov     rax, [rbx]
0x180011ee3  mov     rcx, rbx
0x180011ee6  mov     rax, [rax+90h]
0x180011eed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ef2  or      dword ptr [rbx+2B8h], 10h
0x180011ef9  xor     edx, edx; unsigned __int16 *
0x180011efb  mov     rcx, rbx; this
0x180011efe  call    ?_UpdateAppIcon@CGeneralPage@@AEAAXPEBG@Z; CGeneralPage::_UpdateAppIcon(ushort const *)
0x180011f03  jmp     short loc_180011F5E
0x180011f05  cmp     edx, 684h
0x180011f0b  jnz     short loc_180011F5E
0x180011f0d  mov     edx, ecx; nIDDlgItem
0x180011f0f  mov     rcx, [rbx+70h]; hDlg
0x180011f13  call    cs:__imp_GetDlgItem
0x180011f19  mov     rdi, rax
0x180011f1c  test    rax, rax
0x180011f1f  jz      short loc_180011F5E
0x180011f21  mov     rcx, [rbx+70h]; hDlg
0x180011f25  mov     edx, 684h; nIDButton
0x180011f2a  call    cs:__imp_IsDlgButtonChecked
0x180011f30  cmp     eax, ebp
0x180011f32  jnz     short loc_180011F38
0x180011f34  xor     edx, edx
0x180011f36  jmp     short loc_180011F43
0x180011f38  cmp     dword ptr [rbx+2D8h], 0
0x180011f3f  jz      short loc_180011F4C
0x180011f41  mov     edx, ebp; bEnable
0x180011f43  mov     rcx, rdi; hWnd
0x180011f46  call    cs:__imp_EnableWindow
0x180011f4c  mov     rcx, [rbx]
0x180011f4f  mov     rax, [rcx+90h]
0x180011f56  mov     rcx, rbx
0x180011f59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f5e  mov     rax, rbp
0x180011f61  mov     rcx, [rsp+258h+var_18]
0x180011f69  xor     rcx, rsp; StackCookie
0x180011f6c  call    __security_check_cookie
0x180011f71  lea     r11, [rsp+258h+var_8]
0x180011f79  mov     rbx, [r11+18h]
0x180011f7d  mov     rbp, [r11+20h]
0x180011f81  mov     rsp, r11
0x180011f84  pop     rdi
0x180011f85  retn
```
