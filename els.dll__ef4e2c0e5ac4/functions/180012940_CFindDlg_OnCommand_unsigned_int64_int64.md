# CFindDlg::_OnCommand(unsigned __int64,__int64)

- ea: `0x180012940`
- end: `0x180012b8e`
- name: `?_OnCommand@CFindDlg@@MEAAH_K_J@Z`
- size: `590`
- prototype: `__int64 __fastcall(CFindDlg *__hidden this, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180012940`
- `0x180012da4`
- `0x18001edf0`
- `0x180020c08`
- `0x180020ce4`
- `0x1800222d0`

## import_xrefs

- `USER32!GetDlgItem` at `0x180012a03`
- `USER32!GetDlgItem` at `0x180012ac3`
- `USER32!GetDlgItem` at `0x180012a03`
- `USER32!GetDlgItem` at `0x180012ac3`
- `USER32!GetWindowTextW` at `0x180012a17`
- `USER32!GetWindowTextW` at `0x180012a17`
- `USER32!CheckRadioButton` at `0x180012b23`
- `USER32!CheckRadioButton` at `0x180012b23`
- `USER32!EnableWindow` at `0x180012ace`
- `USER32!EnableWindow` at `0x180012ace`
- `USER32!SetDlgItemTextW` at `0x180012b0c`
- `USER32!SetDlgItemTextW` at `0x180012b0c`
- `USER32!DestroyWindow` at `0x180012a5f`
- `USER32!DestroyWindow` at `0x180012a5f`

## pseudocode

```c
__int64 __fastcall CFindDlg::_OnCommand(CFindDlg *this, int a2, BOOL a3)
{
  unsigned int v4; // esi
  HWND v6; // rcx
  HWND v7; // rax
  __int64 v8; // rbx
  HWND DlgItem; // rax
  __int64 v10; // rax
  HWND v11; // rcx
  WCHAR String[264]; // [rsp+20h] [rbp-228h] BYREF

  v4 = 0;
  if ( (unsigned __int16)a2 > 0x81u )
  {
    if ( (unsigned __int16)a2 != 131 && (unsigned __int16)a2 != 133 )
    {
      if ( (unsigned __int16)a2 == 207 )
      {
        if ( HIWORD(a2) == 768 )
          *((_DWORD *)this + 5) = 1;
        return v4;
      }
      if ( (unsigned __int16)a2 != 209 && (unsigned __int16)a2 != 210 )
      {
        switch ( (unsigned __int16)a2 )
        {
          case 0xD3u:
            CFindDlg::_OnNext(this);
            return v4;
          case 0xD4u:
            v10 = *((_QWORD *)this + 3);
            v11 = (HWND)*((_QWORD *)this + 1);
            *((_DWORD *)this + 4) = 1;
            ClearFindOrFilterDlg(v11, (struct CSources *)(*(_QWORD *)(v10 + 2136) + 4784LL));
            SetDlgItemTextW(*((HWND *)this + 1), 207, &::String);
            CheckRadioButton(*((HWND *)this + 1), 209, 210, 210);
            *((_DWORD *)this + 4) = 1;
            *((_DWORD *)this + 5) = 1;
            return v4;
          case 0x7E9u:
            DlgItem = GetDlgItem(*((HWND *)this + 1), 211);
            EnableWindow(DlgItem, a3);
            return v4;
        }
        return 1;
      }
LABEL_32:
      *((_DWORD *)this + 4) = 1;
      return v4;
    }
LABEL_31:
    if ( HIWORD(a2) != 768 )
      return v4;
    goto LABEL_32;
  }
  switch ( (unsigned __int16)a2 )
  {
    case 0x81u:
      goto LABEL_31;
    case 2u:
    case 8u:
      DestroyWindow(*((HWND *)this + 1));
      return v4;
    case 0x77u:
    case 0x78u:
    case 0x79u:
    case 0x7Au:
    case 0x7Bu:
      goto LABEL_32;
  }
  if ( (unsigned __int16)a2 != 125 )
  {
    if ( (unsigned __int16)a2 == 127 )
    {
      if ( HIWORD(a2) == 1 )
        *((_DWORD *)this + 4) = 1;
      return v4;
    }
    return 1;
  }
  if ( HIWORD(a2) == 1 )
  {
    v6 = (HWND)*((_QWORD *)this + 1);
    *((_DWORD *)this + 4) = 1;
    v7 = GetDlgItem(v6, 125);
    GetWindowTextW(v7, String, 260);
    v8 = *(_QWORD *)(*((_QWORD *)this + 3) + 2136LL);
    SetCategoryCombobox(*((HWND *)this + 1), (struct CSources *)(v8 + 4784), String, 0);
    SetTypesCheckboxes(*((HWND *)this + 1), (struct CSources *)(v8 + 4784), 0x1Fu);
  }
  return v4;
}

```

## disassembly

```asm
0x180012940  mov     [rsp+arg_8], rbx
0x180012945  mov     [rsp+arg_18], rsi
0x18001294a  push    rdi
0x18001294b  sub     rsp, 240h
0x180012952  mov     rax, cs:__security_cookie
0x180012959  xor     rax, rsp
0x18001295c  mov     [rsp+248h+var_18], rax
0x180012964  mov     rdi, rcx
0x180012967  xor     esi, esi
0x180012969  movzx   ecx, dx
0x18001296c  mov     eax, 81h
0x180012971  mov     rbx, r8
0x180012974  cmp     ecx, eax
0x180012976  ja      loc_180012A6A
0x18001297c  jz      loc_180012B52
0x180012982  sub     ecx, 2
0x180012985  jz      loc_180012A5B
0x18001298b  sub     ecx, 6
0x18001298e  jz      loc_180012A5B
0x180012994  sub     ecx, 6Fh ; 'o'
0x180012997  jz      loc_180012B60
0x18001299d  sub     ecx, 1
0x1800129a0  jz      loc_180012B60
0x1800129a6  sub     ecx, 1
0x1800129a9  jz      loc_180012B60
0x1800129af  sub     ecx, 1
0x1800129b2  jz      loc_180012B60
0x1800129b8  sub     ecx, 1
0x1800129bb  jz      loc_180012B60
0x1800129c1  sub     ecx, 2
0x1800129c4  jz      short loc_1800129E7
0x1800129c6  cmp     ecx, 2
0x1800129c9  jnz     loc_180012AB0
0x1800129cf  shr     rdx, 10h
0x1800129d3  lea     ebx, [rsi+1]
0x1800129d6  cmp     dx, bx
0x1800129d9  jnz     loc_180012B67
0x1800129df  mov     [rdi+10h], ebx
0x1800129e2  jmp     loc_180012B67
0x1800129e7  shr     rdx, 10h
0x1800129eb  mov     ebx, 1
0x1800129f0  cmp     dx, bx
0x1800129f3  jnz     loc_180012B67
0x1800129f9  mov     rcx, [rdi+8]; hDlg
0x1800129fd  lea     edx, [rbx+7Ch]; nIDDlgItem
0x180012a00  mov     [rdi+10h], ebx
0x180012a03  call    cs:__imp_GetDlgItem
0x180012a09  mov     r8d, 104h; nMaxCount
0x180012a0f  lea     rdx, [rsp+248h+String]; lpString
0x180012a14  mov     rcx, rax; hWnd
0x180012a17  call    cs:__imp_GetWindowTextW
0x180012a1d  mov     rax, [rdi+18h]
0x180012a21  lea     r8, [rsp+248h+String]; unsigned __int16 *
0x180012a26  mov     rcx, [rdi+8]; HWND
0x180012a2a  xor     r9d, r9d; unsigned __int16
0x180012a2d  mov     rbx, [rax+858h]
0x180012a34  lea     rdx, [rbx+12B0h]; struct CSources *
0x180012a3b  call    ?SetCategoryCombobox@@YAXPEAUHWND__@@PEAVCSources@@PEBGG@Z; SetCategoryCombobox(HWND__ *,CSources *,ushort const *,ushort)
0x180012a40  mov     rcx, [rdi+8]; hDlg
0x180012a44  lea     rdx, [rbx+12B0h]; this
0x180012a4b  mov     r8d, 1Fh; unsigned int
0x180012a51  call    ?SetTypesCheckboxes@@YAXPEAUHWND__@@PEAVCSources@@K@Z; SetTypesCheckboxes(HWND__ *,CSources *,ulong)
0x180012a56  jmp     loc_180012B67
0x180012a5b  mov     rcx, [rdi+8]; hWnd
0x180012a5f  call    cs:__imp_DestroyWindow
0x180012a65  jmp     loc_180012B67
0x180012a6a  sub     ecx, 83h
0x180012a70  jz      loc_180012B52
0x180012a76  sub     ecx, 2
0x180012a79  jz      loc_180012B52
0x180012a7f  sub     ecx, 4Ah ; 'J'
0x180012a82  jz      loc_180012B3B
0x180012a88  sub     ecx, 2
0x180012a8b  jz      loc_180012B60
0x180012a91  sub     ecx, 1
0x180012a94  jz      loc_180012B60
0x180012a9a  sub     ecx, 1
0x180012a9d  jz      loc_180012B31
0x180012aa3  sub     ecx, 1
0x180012aa6  jz      short loc_180012AD9
0x180012aa8  cmp     ecx, 715h
0x180012aae  jz      short loc_180012ABA
0x180012ab0  mov     esi, 1
0x180012ab5  jmp     loc_180012B67
0x180012aba  mov     rcx, [rdi+8]; hDlg
0x180012abe  mov     edx, 0D3h; nIDDlgItem
0x180012ac3  call    cs:__imp_GetDlgItem
0x180012ac9  mov     rcx, rax; hWnd
0x180012acc  mov     edx, ebx; bEnable
0x180012ace  call    cs:__imp_EnableWindow
0x180012ad4  jmp     loc_180012B67
0x180012ad9  mov     rax, [rdi+18h]
0x180012add  mov     ebx, 1
0x180012ae2  mov     rcx, [rdi+8]; HWND
0x180012ae6  mov     [rdi+10h], ebx
0x180012ae9  mov     rdx, [rax+858h]
0x180012af0  add     rdx, 12B0h; struct CSources *
0x180012af7  call    ?ClearFindOrFilterDlg@@YAXPEAUHWND__@@PEAVCSources@@@Z; ClearFindOrFilterDlg(HWND__ *,CSources *)
0x180012afc  mov     rcx, [rdi+8]; hDlg
0x180012b00  lea     r8, String; lpString
0x180012b07  mov     edx, 0CFh; nIDDlgItem
0x180012b0c  call    cs:__imp_SetDlgItemTextW
0x180012b12  mov     rcx, [rdi+8]; hDlg
0x180012b16  mov     r8d, 0D2h; nIDLastButton
0x180012b1c  mov     r9d, r8d; nIDCheckButton
0x180012b1f  lea     edx, [r8-1]; nIDFirstButton
0x180012b23  call    cs:__imp_CheckRadioButton
0x180012b29  mov     [rdi+10h], ebx
0x180012b2c  mov     [rdi+14h], ebx
0x180012b2f  jmp     short loc_180012B67
0x180012b31  mov     rcx, rdi; this
0x180012b34  call    ?_OnNext@CFindDlg@@IEAAXXZ; CFindDlg::_OnNext(void)
0x180012b39  jmp     short loc_180012B67
0x180012b3b  shr     rdx, 10h
0x180012b3f  mov     eax, 300h
0x180012b44  cmp     dx, ax
0x180012b47  jnz     short loc_180012B67
0x180012b49  mov     dword ptr [rdi+14h], 1
0x180012b50  jmp     short loc_180012B67
0x180012b52  shr     rdx, 10h
0x180012b56  mov     eax, 300h
0x180012b5b  cmp     dx, ax
0x180012b5e  jnz     short loc_180012B67
0x180012b60  mov     dword ptr [rdi+10h], 1
0x180012b67  mov     eax, esi
0x180012b69  mov     rcx, [rsp+248h+var_18]
0x180012b71  xor     rcx, rsp; StackCookie
0x180012b74  call    __security_check_cookie
0x180012b79  lea     r11, [rsp+248h+var_8]
0x180012b81  mov     rbx, [r11+18h]
0x180012b85  mov     rsi, [r11+28h]
0x180012b89  mov     rsp, r11
0x180012b8c  pop     rdi
0x180012b8d  retn
```
