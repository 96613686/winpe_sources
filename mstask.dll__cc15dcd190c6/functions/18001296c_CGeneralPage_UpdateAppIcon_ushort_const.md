# CGeneralPage::_UpdateAppIcon(ushort const *)

- ea: `0x18001296c`
- end: `0x1800129fd`
- name: `?_UpdateAppIcon@CGeneralPage@@AEAAXPEBG@Z`
- size: `145`
- prototype: `void __fastcall(CGeneralPage *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180011c90`
- `0x180011fc0`
- `0x180012a04`

## callees

- `0x180010b5c`
- `0x180010c38`
- `0x18001296c`

## import_xrefs

- `USER32!SendDlgItemMessageW` at `0x1800129f1`
- `USER32!SendDlgItemMessageW` at `0x1800129f1`
- `USER32!IsDlgButtonChecked` at `0x1800129b0`
- `USER32!IsDlgButtonChecked` at `0x1800129b0`

## pseudocode

```c
void __fastcall CGeneralPage::_UpdateAppIcon(CGeneralPage *this, unsigned __int16 *a2)
{
  CIconHelper *v3; // rcx
  int v4; // eax
  BOOL v5; // edx

  v3 = (CIconHelper *)*((_QWORD *)this + 88);
  if ( v3 )
  {
    v4 = *((_DWORD *)this + 174);
    if ( (v4 & 0x10) != 0 )
    {
      *((_DWORD *)this + 174) = v4 & 0xFFFFFFEF;
      if ( a2 )
        CIconHelper::SetAppIcon(v3, a2);
      if ( *((_DWORD *)this + 33) )
        v5 = IsDlgButtonChecked(*((HWND *)this + 14), 1664) == 1;
      else
        v5 = 0;
      CIconHelper::SetJobIcon(*((CIconHelper **)this + 88), v5);
      SendDlgItemMessageW(*((HWND *)this + 14), 500, 0x170u, *(_QWORD *)(*((_QWORD *)this + 88) + 40LL), 0);
    }
  }
}

```

## disassembly

```asm
0x18001296c  push    rbx
0x18001296e  sub     rsp, 30h
0x180012972  mov     rbx, rcx
0x180012975  mov     rcx, [rcx+2C0h]; this
0x18001297c  test    rcx, rcx
0x18001297f  jz      short loc_1800129F7
0x180012981  mov     eax, [rbx+2B8h]
0x180012987  test    al, 10h
0x180012989  jz      short loc_1800129F7
0x18001298b  and     eax, 0FFFFFFEFh
0x18001298e  mov     [rbx+2B8h], eax
0x180012994  test    rdx, rdx
0x180012997  jz      short loc_18001299E
0x180012999  call    ?SetAppIcon@CIconHelper@@QEAAXPEAG@Z; CIconHelper::SetAppIcon(ushort *)
0x18001299e  cmp     dword ptr [rbx+84h], 0
0x1800129a5  jz      short loc_1800129C0
0x1800129a7  mov     rcx, [rbx+70h]; hDlg
0x1800129ab  mov     edx, 680h; nIDButton
0x1800129b0  call    cs:__imp_IsDlgButtonChecked
0x1800129b6  xor     edx, edx
0x1800129b8  cmp     eax, 1
0x1800129bb  setz    dl
0x1800129be  jmp     short loc_1800129C2
0x1800129c0  xor     edx, edx; int
0x1800129c2  mov     rcx, [rbx+2C0h]; this
0x1800129c9  call    ?SetJobIcon@CIconHelper@@QEAAXH@Z; CIconHelper::SetJobIcon(int)
0x1800129ce  mov     r9, [rbx+2C0h]
0x1800129d5  mov     edx, 1F4h; nIDDlgItem
0x1800129da  mov     rcx, [rbx+70h]; hDlg
0x1800129de  mov     r8d, 170h; Msg
0x1800129e4  mov     [rsp+38h+lParam], 0; lParam
0x1800129ed  mov     r9, [r9+28h]; wParam
0x1800129f1  call    cs:__imp_SendDlgItemMessageW
0x1800129f7  add     rsp, 30h
0x1800129fb  pop     rbx
0x1800129fc  retn
```
