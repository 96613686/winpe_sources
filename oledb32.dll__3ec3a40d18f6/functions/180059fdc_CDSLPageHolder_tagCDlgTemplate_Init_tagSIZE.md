# CDSLPageHolder::tagCDlgTemplate::Init(tagSIZE *)

- ea: `0x180059fdc`
- end: `0x18005a17c`
- name: `?Init@tagCDlgTemplate@CDSLPageHolder@@QEAA_NPEAUtagSIZE@@@Z`
- size: `416`
- prototype: `bool __fastcall(CDSLPageHolder::tagCDlgTemplate *__hidden this, struct tagSIZE *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18005a7c4`

## callees

- `0x180059e30`
- `0x180059fdc`
- `0x18007e700`

## import_xrefs

- `KERNEL32!MulDiv` at `0x18005a134`
- `KERNEL32!MulDiv` at `0x18005a14e`
- `KERNEL32!MulDiv` at `0x18005a134`
- `KERNEL32!MulDiv` at `0x18005a14e`
- `USER32!GetDialogBaseUnits` at `0x18005a0fe`
- `USER32!GetDialogBaseUnits` at `0x18005a0fe`
- `USER32!ReleaseDC` at `0x18005a11f`
- `USER32!ReleaseDC` at `0x18005a11f`
- `USER32!GetDC` at `0x18005a064`
- `USER32!GetDC` at `0x18005a064`
- `GDI32!GetTextMetricsW` at `0x18005a095`
- `GDI32!GetTextMetricsW` at `0x18005a095`
- `GDI32!DeleteObject` at `0x18005a0f6`
- `GDI32!DeleteObject` at `0x18005a0f6`
- `GDI32!SelectObject` at `0x18005a084`
- `GDI32!SelectObject` at `0x18005a0ed`
- `GDI32!SelectObject` at `0x18005a084`
- `GDI32!SelectObject` at `0x18005a0ed`
- `GDI32!GetTextExtentPointW` at `0x18005a0b0`
- `GDI32!GetTextExtentPointW` at `0x18005a0b0`

## pseudocode

```c
char __fastcall CDSLPageHolder::tagCDlgTemplate::Init(CDSLPageHolder::tagCDlgTemplate *this, struct tagSIZE *a2)
{
  int v4; // r8d
  HDC DC; // rdi
  void *PropSheetFont; // rax
  void *v7; // rsi
  HGDIOBJ v8; // rbp
  int DialogBaseUnits; // eax
  __int16 v10; // ax
  int v11; // r8d
  tagSIZE sz; // [rsp+20h] [rbp-68h] BYREF
  tagTEXTMETRICW tm; // [rsp+28h] [rbp-60h] BYREF

  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 6) = 0;
  v4 = nDenominator;
  *(_DWORD *)this = 1073808384;
  *((_DWORD *)this + 1) = 0x10000;
  if ( !__PAIR64__(v4, dword_1800C0560) )
  {
    sz = 0;
    memset(&tm, 0, sizeof(tm));
    DC = GetDC(0);
    PropSheetFont = (void *)GetPropSheetFont();
    v7 = PropSheetFont;
    if ( PropSheetFont )
    {
      v8 = SelectObject(DC, PropSheetFont);
      GetTextMetricsW(DC, &tm);
      GetTextExtentPointW(DC, L"ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz", 52, &sz);
      dword_1800C0560 = tm.tmExternalLeading + tm.tmHeight;
      nDenominator = (sz.cx + 26) / 52;
      if ( v8 )
      {
        SelectObject(DC, v8);
        DeleteObject(v7);
      }
    }
    else
    {
      DialogBaseUnits = GetDialogBaseUnits();
      dword_1800C0560 = HIWORD(DialogBaseUnits);
      nDenominator = (unsigned __int16)DialogBaseUnits;
    }
    ReleaseDC(0, DC);
    v4 = nDenominator;
  }
  v10 = MulDiv(a2->cx, 4, v4);
  v11 = dword_1800C0560;
  *((_WORD *)this + 7) = v10;
  *((_WORD *)this + 8) = MulDiv(a2->cy, 8, v11);
  return 1;
}

```

## disassembly

```asm
0x180059fdc  mov     [rsp+arg_10], rbx
0x180059fe1  mov     [rsp+arg_18], rbp
0x180059fe6  push    rsi
0x180059fe7  push    rdi
0x180059fe8  push    r14
0x180059fea  sub     rsp, 70h
0x180059fee  mov     rax, cs:__security_cookie
0x180059ff5  xor     rax, rsp
0x180059ff8  mov     [rsp+88h+var_20], rax
0x180059ffd  mov     qword ptr [rcx+8], 0
0x18005a005  mov     r14, rdx
0x18005a008  mov     qword ptr [rcx+10h], 0
0x18005a010  mov     rbx, rcx
0x18005a013  mov     dword ptr [rcx+18h], 0
0x18005a01a  mov     r8d, cs:nDenominator
0x18005a021  mov     dword ptr [rcx], 40010400h
0x18005a027  mov     dword ptr [rcx+4], 10000h
0x18005a02e  test    r8d, r8d
0x18005a031  jnz     loc_18005A12C
0x18005a037  cmp     cs:dword_1800C0560, r8d
0x18005a03e  jnz     loc_18005A12C
0x18005a044  xorps   xmm0, xmm0
0x18005a047  xor     eax, eax
0x18005a049  movups  xmmword ptr [rsp+88h+tm.tmOverhang], xmm0
0x18005a04e  xor     ecx, ecx; hWnd
0x18005a050  mov     qword ptr [rsp+88h+sz.cx], rax
0x18005a055  movups  xmmword ptr [rsp+88h+tm.tmFirstChar], xmm0
0x18005a05a  movups  xmmword ptr [rsp+88h+tm.tmHeight], xmm0
0x18005a05f  movups  xmmword ptr [rsp+88h+tm.tmExternalLeading], xmm0
0x18005a064  call    cs:__imp_GetDC
0x18005a06a  mov     rdi, rax
0x18005a06d  call    GetPropSheetFont
0x18005a072  mov     rsi, rax
0x18005a075  test    rax, rax
0x18005a078  jz      loc_18005A0FE
0x18005a07e  mov     rdx, rax; h
0x18005a081  mov     rcx, rdi; hdc
0x18005a084  call    cs:__imp_SelectObject
0x18005a08a  lea     rdx, [rsp+88h+tm]; lptm
0x18005a08f  mov     rcx, rdi; hdc
0x18005a092  mov     rbp, rax
0x18005a095  call    cs:__imp_GetTextMetricsW
0x18005a09b  lea     r9, [rsp+88h+sz]; lpsz
0x18005a0a0  mov     r8d, 34h ; '4'; c
0x18005a0a6  lea     rdx, aAbcdefghijklmn; "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklm"...
0x18005a0ad  mov     rcx, rdi; hdc
0x18005a0b0  call    cs:__imp_GetTextExtentPointW
0x18005a0b6  mov     ecx, [rsp+88h+sz.cx]
0x18005a0ba  mov     eax, 4EC4EC4Fh
0x18005a0bf  add     ecx, 1Ah
0x18005a0c2  imul    ecx
0x18005a0c4  mov     ecx, [rsp+88h+tm.tmHeight]
0x18005a0c8  add     ecx, [rsp+88h+tm.tmExternalLeading]
0x18005a0cc  sar     edx, 4
0x18005a0cf  mov     eax, edx
0x18005a0d1  mov     cs:dword_1800C0560, ecx
0x18005a0d7  shr     eax, 1Fh
0x18005a0da  add     edx, eax
0x18005a0dc  mov     cs:nDenominator, edx
0x18005a0e2  test    rbp, rbp
0x18005a0e5  jz      short loc_18005A11A
0x18005a0e7  mov     rdx, rbp; h
0x18005a0ea  mov     rcx, rdi; hdc
0x18005a0ed  call    cs:__imp_SelectObject
0x18005a0f3  mov     rcx, rsi; ho
0x18005a0f6  call    cs:__imp_DeleteObject
0x18005a0fc  jmp     short loc_18005A11A
0x18005a0fe  call    cs:__imp_GetDialogBaseUnits
0x18005a104  movzx   ecx, ax
0x18005a107  shr     rax, 10h
0x18005a10b  movzx   eax, ax
0x18005a10e  mov     cs:dword_1800C0560, eax
0x18005a114  mov     cs:nDenominator, ecx
0x18005a11a  mov     rdx, rdi; hDC
0x18005a11d  xor     ecx, ecx; hWnd
0x18005a11f  call    cs:__imp_ReleaseDC
0x18005a125  mov     r8d, cs:nDenominator; nDenominator
0x18005a12c  mov     ecx, [r14]; nNumber
0x18005a12f  mov     edx, 4; nNumerator
0x18005a134  call    cs:__imp_MulDiv
0x18005a13a  mov     r8d, cs:dword_1800C0560; nDenominator
0x18005a141  mov     edx, 8; nNumerator
0x18005a146  mov     [rbx+0Eh], ax
0x18005a14a  mov     ecx, [r14+4]; nNumber
0x18005a14e  call    cs:__imp_MulDiv
0x18005a154  mov     [rbx+10h], ax
0x18005a158  mov     al, 1
0x18005a15a  mov     rcx, [rsp+88h+var_20]
0x18005a15f  xor     rcx, rsp; StackCookie
0x18005a162  call    __security_check_cookie
0x18005a167  lea     r11, [rsp+88h+var_18]
0x18005a16c  mov     rbx, [r11+30h]
0x18005a170  mov     rbp, [r11+38h]
0x18005a174  mov     rsp, r11
0x18005a177  pop     r14
0x18005a179  pop     rdi
0x18005a17a  pop     rsi
0x18005a17b  retn
```
