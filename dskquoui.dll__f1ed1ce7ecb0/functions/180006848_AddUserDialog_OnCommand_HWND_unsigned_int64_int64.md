# AddUserDialog::OnCommand(HWND__ *,unsigned __int64,__int64)

- ea: `0x180006848`
- end: `0x180006a30`
- name: `?OnCommand@AddUserDialog@@AEAA_JPEAUHWND__@@_K_J@Z`
- size: `488`
- prototype: `__int64(AddUserDialog *__hidden this, HWND, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800067c0`

## callees

- `0x180006848`
- `0x180006c54`
- `0x18001b120`
- `0x18001b26c`
- `0x18001b3b0`
- `0x18001f010`

## import_xrefs

- `USER32!IsWindowEnabled` at `0x180006914`
- `USER32!IsWindowEnabled` at `0x18000695e`
- `USER32!IsWindowEnabled` at `0x180006914`
- `USER32!IsWindowEnabled` at `0x18000695e`
- `USER32!GetDlgItem` at `0x18000690b`
- `USER32!GetDlgItem` at `0x180006955`
- `USER32!GetDlgItem` at `0x18000690b`
- `USER32!GetDlgItem` at `0x180006955`
- `USER32!EndDialog` at `0x180006a17`
- `USER32!EndDialog` at `0x180006a17`

## pseudocode

```c
__int64 __fastcall AddUserDialog::OnCommand(XBytes **this, HWND a2, unsigned __int64 a3, __int64 a4)
{
  __int64 v5; // rdi
  XBytes *v7; // rcx
  HWND v8; // rax
  XBytes *v9; // rcx
  __int64 v10; // rdx
  HWND DlgItem; // rax
  XBytes *v12; // rcx
  __int64 v13; // rdx
  XBytes *v14; // rcx
  XBytes *v15; // rcx
  __int64 result; // rax
  __int64 v17; // [rsp+48h] [rbp+20h] BYREF

  v17 = a4;
  v5 = 0;
  switch ( (unsigned __int16)a3 )
  {
    case 1u:
      result = AddUserDialog::OnOk((AddUserDialog *)this, a2, a3, (unsigned __int16)a3);
      if ( !result )
        return result;
      goto LABEL_33;
    case 2u:
LABEL_33:
      EndDialog(a2, 0);
      return v5;
    case 0x402u:
    case 0x403u:
      if ( WORD1(a3) == 1024 )
      {
        if ( (unsigned __int16)a3 == 1026 )
        {
          v15 = this[20];
        }
        else
        {
          if ( (unsigned __int16)a3 != 1027 )
            return v5;
          v15 = this[21];
        }
        if ( v15 )
          XBytes::OnEditNotifyUpdate(v15, 1024);
        return v5;
      }
      return v5;
    case 0x404u:
      DlgItem = GetDlgItem(*((HWND *)this[21] + 1), *((_DWORD *)this[21] + 4));
      if ( IsWindowEnabled(DlgItem) )
        return v5;
      v12 = this[4];
      v17 = 0;
      (*(void (__fastcall **)(XBytes *, __int64 *))(*(_QWORD *)v12 + 112LL))(v12, &v17);
      v13 = v17;
      if ( v17 == -1 )
        v13 = 0;
      XBytes::SetBytes(this[20], v13);
      v14 = this[4];
      v17 = 0;
      (*(void (__fastcall **)(XBytes *, __int64 *))(*(_QWORD *)v14 + 88LL))(v14, &v17);
      v10 = v17;
      v9 = this[21];
      if ( v17 == -1 )
        v10 = 0;
      goto LABEL_18;
    case 0x405u:
      v8 = GetDlgItem(*((HWND *)this[21] + 1), *((_DWORD *)this[21] + 4));
      if ( !IsWindowEnabled(v8) )
        return v5;
      XBytes::SetBytes(this[21], -1);
      v9 = this[20];
      v10 = -1;
LABEL_18:
      XBytes::SetBytes(v9, v10);
      return v5;
  }
  if ( (unsigned int)(unsigned __int16)a3 - 1040 >= 2 )
    return 1;
  if ( WORD1(a3) == 1 )
  {
    if ( (unsigned __int16)a3 == 1040 )
    {
      v7 = this[20];
    }
    else
    {
      if ( (unsigned __int16)a3 != 1041 )
        return v5;
      v7 = this[21];
    }
    if ( v7 )
      XBytes::OnComboNotifySelChange(v7, 1024);
  }
  return v5;
}

```

## disassembly

```asm
0x180006848  mov     [rsp+arg_0], rbx
0x18000684d  mov     [rsp+arg_8], rsi
0x180006852  mov     [rsp+arg_18], r9
0x180006857  push    rdi
0x180006858  sub     rsp, 20h
0x18000685c  mov     rax, r8
0x18000685f  movzx   r9d, r8w; __int64
0x180006863  shr     rax, 10h
0x180006867  mov     rbx, rcx
0x18000686a  movzx   ecx, ax
0x18000686d  xor     edi, edi
0x18000686f  mov     eax, r9d
0x180006872  mov     rsi, rdx
0x180006875  sub     eax, 1
0x180006878  jz      loc_180006A05
0x18000687e  sub     eax, 1
0x180006881  jz      loc_180006A12
0x180006887  mov     edx, 400h; __int64
0x18000688c  sub     eax, edx
0x18000688e  jz      loc_1800069D6
0x180006894  sub     eax, 1
0x180006897  jz      loc_1800069D6
0x18000689d  sub     eax, 1
0x1800068a0  jz      loc_180006947
0x1800068a6  sub     eax, 1
0x1800068a9  jz      short loc_1800068FD
0x1800068ab  sub     eax, 0Bh
0x1800068ae  jz      short loc_1800068BF
0x1800068b0  cmp     eax, 1
0x1800068b3  jz      short loc_1800068BF
0x1800068b5  mov     edi, 1
0x1800068ba  jmp     loc_180006A1D
0x1800068bf  cmp     ecx, 1
0x1800068c2  jnz     loc_180006A1D
0x1800068c8  sub     r9d, 410h
0x1800068cf  jz      short loc_1800068E3
0x1800068d1  cmp     r9d, ecx
0x1800068d4  jnz     loc_180006A1D
0x1800068da  mov     rcx, [rbx+0A8h]
0x1800068e1  jmp     short loc_1800068EA
0x1800068e3  mov     rcx, [rbx+0A0h]; this
0x1800068ea  test    rcx, rcx
0x1800068ed  jz      loc_180006A1D
0x1800068f3  call    ?OnComboNotifySelChange@XBytes@@QEAAH_J@Z; XBytes::OnComboNotifySelChange(__int64)
0x1800068f8  jmp     loc_180006A1D
0x1800068fd  mov     rcx, [rbx+0A8h]
0x180006904  mov     edx, [rcx+10h]; nIDDlgItem
0x180006907  mov     rcx, [rcx+8]; hDlg
0x18000690b  call    cs:__imp_GetDlgItem
0x180006911  mov     rcx, rax; hWnd
0x180006914  call    cs:__imp_IsWindowEnabled
0x18000691a  test    eax, eax
0x18000691c  jz      loc_180006A1D
0x180006922  mov     rcx, [rbx+0A8h]; this
0x180006929  or      rdx, 0FFFFFFFFFFFFFFFFh; __int64
0x18000692d  call    ?SetBytes@XBytes@@QEAAX_J@Z; XBytes::SetBytes(__int64)
0x180006932  mov     rcx, [rbx+0A0h]; this
0x180006939  or      rdx, 0FFFFFFFFFFFFFFFFh; __int64
0x18000693d  call    ?SetBytes@XBytes@@QEAAX_J@Z; XBytes::SetBytes(__int64)
0x180006942  jmp     loc_180006A1D
0x180006947  mov     rcx, [rbx+0A8h]
0x18000694e  mov     edx, [rcx+10h]; nIDDlgItem
0x180006951  mov     rcx, [rcx+8]; hDlg
0x180006955  call    cs:__imp_GetDlgItem
0x18000695b  mov     rcx, rax; hWnd
0x18000695e  call    cs:__imp_IsWindowEnabled
0x180006964  test    eax, eax
0x180006966  jnz     loc_180006A1D
0x18000696c  mov     rcx, [rbx+20h]
0x180006970  lea     rdx, [rsp+28h+arg_18]
0x180006975  mov     [rsp+28h+arg_18], rdi
0x18000697a  mov     rax, [rcx]
0x18000697d  mov     rax, [rax+70h]
0x180006981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006986  mov     rdx, [rsp+28h+arg_18]
0x18000698b  xor     eax, eax
0x18000698d  mov     rcx, [rbx+0A0h]; this
0x180006994  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180006998  cmovz   rdx, rax; __int64
0x18000699c  call    ?SetBytes@XBytes@@QEAAX_J@Z; XBytes::SetBytes(__int64)
0x1800069a1  mov     rcx, [rbx+20h]
0x1800069a5  lea     rdx, [rsp+28h+arg_18]
0x1800069aa  mov     [rsp+28h+arg_18], rdi
0x1800069af  mov     rax, [rcx]
0x1800069b2  mov     rax, [rax+58h]
0x1800069b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069bb  mov     rdx, [rsp+28h+arg_18]
0x1800069c0  xor     eax, eax
0x1800069c2  mov     rcx, [rbx+0A8h]
0x1800069c9  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x1800069cd  cmovz   rdx, rax
0x1800069d1  jmp     loc_18000693D
0x1800069d6  cmp     ecx, edx
0x1800069d8  jnz     short loc_180006A1D
0x1800069da  sub     r9d, 402h
0x1800069e1  jz      short loc_1800069F2
0x1800069e3  cmp     r9d, 1
0x1800069e7  jnz     short loc_180006A1D
0x1800069e9  mov     rcx, [rbx+0A8h]
0x1800069f0  jmp     short loc_1800069F9
0x1800069f2  mov     rcx, [rbx+0A0h]; this
0x1800069f9  test    rcx, rcx
0x1800069fc  jz      short loc_180006A1D
0x1800069fe  call    ?OnEditNotifyUpdate@XBytes@@QEAAH_J@Z; XBytes::OnEditNotifyUpdate(__int64)
0x180006a03  jmp     short loc_180006A1D
0x180006a05  mov     rcx, rbx; this
0x180006a08  call    ?OnOk@AddUserDialog@@AEAA_JPEAUHWND__@@_K_J@Z; AddUserDialog::OnOk(HWND__ *,unsigned __int64,__int64)
0x180006a0d  test    rax, rax
0x180006a10  jz      short loc_180006A20
0x180006a12  xor     edx, edx; nResult
0x180006a14  mov     rcx, rsi; hDlg
0x180006a17  call    cs:__imp_EndDialog
0x180006a1d  mov     rax, rdi
0x180006a20  mov     rbx, [rsp+28h+arg_0]
0x180006a25  mov     rsi, [rsp+28h+arg_8]
0x180006a2a  add     rsp, 20h
0x180006a2e  pop     rdi
0x180006a2f  retn
```
