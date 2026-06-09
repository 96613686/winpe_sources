# ModifyDlgItemStatic(HWND__ *,int,int,int)

- ea: `0x18003bfe8`
- end: `0x18003c0bd`
- name: `?ModifyDlgItemStatic@@YAPEAUHFONT__@@PEAUHWND__@@HHH@Z`
- size: `213`
- prototype: `HFONT __fastcall(HWND, int, int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18003d7ec`

## callees

- `0x18003bfe8`
- `0x18003e582`
- `0x18003e5c0`

## import_xrefs

- `GDI32!CreateFontIndirectW` at `0x18003c078`
- `GDI32!CreateFontIndirectW` at `0x18003c078`
- `GDI32!GetObjectW` at `0x18003c065`
- `GDI32!GetObjectW` at `0x18003c065`
- `USER32!GetParent` at `0x18003c04a`
- `USER32!GetParent` at `0x18003c04a`
- `USER32!SendMessageA` at `0x18003c03e`
- `USER32!SendMessageA` at `0x18003c091`
- `USER32!SendMessageA` at `0x18003c03e`
- `USER32!SendMessageA` at `0x18003c091`
- `USER32!GetDlgItem` at `0x18003c00b`
- `USER32!GetDlgItem` at `0x18003c00b`

## pseudocode

```c
HFONT __fastcall ModifyDlgItemStatic(HWND a1, int a2)
{
  HFONT v2; // rdi
  HWND DlgItem; // rsi
  HWND Parent; // rbx
  void *v5; // rbp
  LOGFONTW pv; // [rsp+20h] [rbp-88h] BYREF

  v2 = 0;
  DlgItem = GetDlgItem(a1, a2);
  if ( DlgItem )
  {
    memset_0(&pv, 0, sizeof(pv));
    Parent = DlgItem;
    while ( Parent )
    {
      v5 = (void *)SendMessageA(Parent, 0x31u, 0, 0);
      Parent = GetParent(Parent);
      if ( v5 )
      {
        GetObjectW(v5, 92, &pv);
        pv.lfWeight = 700;
        v2 = CreateFontIndirectW(&pv);
        SendMessageA(DlgItem, 0x30u, (WPARAM)v2, 1);
        return v2;
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18003bfe8  mov     [rsp+arg_10], rbx
0x18003bfed  push    rbp
0x18003bfee  push    rsi
0x18003bfef  push    rdi
0x18003bff0  sub     rsp, 90h
0x18003bff7  mov     rax, cs:__security_cookie
0x18003bffe  xor     rax, rsp
0x18003c001  mov     [rsp+0A8h+var_28], rax
0x18003c009  xor     edi, edi
0x18003c00b  call    cs:__imp_GetDlgItem
0x18003c011  mov     rsi, rax
0x18003c014  test    rax, rax
0x18003c017  jz      short loc_18003C097
0x18003c019  xor     edx, edx; Val
0x18003c01b  lea     r8d, [rdi+5Ch]; Size
0x18003c01f  lea     rcx, [rsp+0A8h+pv]; void *
0x18003c024  call    memset_0
0x18003c029  mov     rbx, rsi
0x18003c02c  test    rbx, rbx
0x18003c02f  jz      short loc_18003C097
0x18003c031  xor     r9d, r9d; lParam
0x18003c034  xor     r8d, r8d; wParam
0x18003c037  mov     rcx, rbx; hWnd
0x18003c03a  lea     edx, [r9+31h]; Msg
0x18003c03e  call    cs:__imp_SendMessageA
0x18003c044  mov     rcx, rbx; hWnd
0x18003c047  mov     rbp, rax
0x18003c04a  call    cs:__imp_GetParent
0x18003c050  mov     rbx, rax
0x18003c053  test    rbp, rbp
0x18003c056  jz      short loc_18003C02C
0x18003c058  lea     r8, [rsp+0A8h+pv]; pv
0x18003c05d  mov     edx, 5Ch ; '\'; c
0x18003c062  mov     rcx, rbp; h
0x18003c065  call    cs:__imp_GetObjectW
0x18003c06b  lea     rcx, [rsp+0A8h+pv]; lplf
0x18003c070  mov     [rsp+0A8h+var_78], 2BCh
0x18003c078  call    cs:__imp_CreateFontIndirectW
0x18003c07e  mov     r9d, 1; lParam
0x18003c084  mov     rcx, rsi; hWnd
0x18003c087  mov     r8, rax; wParam
0x18003c08a  mov     rdi, rax
0x18003c08d  lea     edx, [r9+2Fh]; Msg
0x18003c091  call    cs:__imp_SendMessageA
0x18003c097  mov     rax, rdi
0x18003c09a  mov     rcx, [rsp+0A8h+var_28]
0x18003c0a2  xor     rcx, rsp; StackCookie
0x18003c0a5  call    __security_check_cookie
0x18003c0aa  mov     rbx, [rsp+0A8h+arg_10]
0x18003c0b2  add     rsp, 90h
0x18003c0b9  pop     rdi
0x18003c0ba  pop     rsi
0x18003c0bb  pop     rbp
0x18003c0bc  retn
```
