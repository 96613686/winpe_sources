# ListBox_DrawItem(tagLBIV *,int,tagRECT const *,int,HBRUSH__ *)

- ea: `0x1800f698c`
- end: `0x1800f6cae`
- name: `?ListBox_DrawItem@@YAXPEAUtagLBIV@@HPEBUtagRECT@@HPEAUHBRUSH__@@@Z`
- size: `802`
- prototype: `void __usercall(struct tagLBIV *@<rcx>, int@<edx>, const struct tagRECT *@<r8>, int@<r9d>, HBRUSH)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1800a07cc`
- `0x1800a2eac`

## callees

- `0x180007fc4`
- `0x1800b33c4`
- `0x1800f698c`
- `0x180114520`
- `0x18013e3a8`

## import_xrefs

- `GDI32!SetTextAlign` at `0x1800f6bd5`
- `GDI32!SetTextAlign` at `0x1800f6c58`
- `GDI32!SetTextAlign` at `0x1800f6bd5`
- `GDI32!SetTextAlign` at `0x1800f6c58`
- `GDI32!CreateSolidBrush` at `0x1800f6bec`
- `GDI32!CreateSolidBrush` at `0x1800f6bec`
- `GDI32!DeleteObject` at `0x1800f6c45`
- `GDI32!DeleteObject` at `0x1800f6c45`
- `GDI32!SetBkColor` at `0x1800f6ae2`
- `GDI32!SetBkColor` at `0x1800f6b22`
- `GDI32!SetBkColor` at `0x1800f6c77`
- `GDI32!SetBkColor` at `0x1800f6ae2`
- `GDI32!SetBkColor` at `0x1800f6b22`
- `GDI32!SetBkColor` at `0x1800f6c77`
- `GDI32!SetBkMode` at `0x1800f6ad4`
- `GDI32!SetBkMode` at `0x1800f6b0c`
- `GDI32!SetBkMode` at `0x1800f6c83`
- `GDI32!SetBkMode` at `0x1800f6ad4`
- `GDI32!SetBkMode` at `0x1800f6b0c`
- `GDI32!SetBkMode` at `0x1800f6c83`
- `GDI32!SetTextColor` at `0x1800f6b3b`
- `GDI32!SetTextColor` at `0x1800f6ba3`
- `GDI32!SetTextColor` at `0x1800f6c6b`
- `GDI32!SetTextColor` at `0x1800f6b3b`
- `GDI32!SetTextColor` at `0x1800f6ba3`
- `GDI32!SetTextColor` at `0x1800f6c6b`
- `GDI32!GetTextAlign` at `0x1800f6bc6`
- `GDI32!GetTextAlign` at `0x1800f6bc6`
- `GDI32!GetBkColor` at `0x1800f6b80`
- `GDI32!GetBkColor` at `0x1800f6b80`
- `USER32!FillRect` at `0x1800f6b57`
- `USER32!FillRect` at `0x1800f6b57`
- `USER32!GetSysColor` at `0x1800f69f8`
- `USER32!GetSysColor` at `0x1800f6a02`
- `USER32!GetSysColor` at `0x1800f6a0e`
- `USER32!GetSysColor` at `0x1800f6af0`
- `USER32!GetSysColor` at `0x1800f6b17`
- `USER32!GetSysColor` at `0x1800f6b30`
- `USER32!GetSysColor` at `0x1800f6b8b`
- `USER32!GetSysColor` at `0x1800f6b98`
- `USER32!GetSysColor` at `0x1800f6be4`
- `USER32!GetSysColor` at `0x1800f69f8`
- `USER32!GetSysColor` at `0x1800f6a02`
- `USER32!GetSysColor` at `0x1800f6a0e`
- `USER32!GetSysColor` at `0x1800f6af0`
- `USER32!GetSysColor` at `0x1800f6b17`
- `USER32!GetSysColor` at `0x1800f6b30`
- `USER32!GetSysColor` at `0x1800f6b8b`
- `USER32!GetSysColor` at `0x1800f6b98`
- `USER32!GetSysColor` at `0x1800f6be4`
- `USER32!DrawStateW` at `0x1800f6c37`
- `USER32!DrawStateW` at `0x1800f6c37`
- `UxTheme!GetThemeColor` at `0x1800f6a62`
- `UxTheme!GetThemeColor` at `0x1800f6a89`
- `UxTheme!GetThemeColor` at `0x1800f6ab0`
- `UxTheme!GetThemeColor` at `0x1800f6a62`
- `UxTheme!GetThemeColor` at `0x1800f6a89`
- `UxTheme!GetThemeColor` at `0x1800f6ab0`

## pseudocode

```c
void __fastcall ListBox_DrawItem(struct tagLBIV *a1, int a2, struct tagRECT *a3, int a4, HBRUSH hbr)
{
  HDC v5; // rdi
  int v6; // r15d
  COLORREF SysColor; // ebp
  COLORREF v10; // ebx
  DWORD v11; // r13d
  void *v12; // rcx
  COLORREF v13; // r12d
  COLORREF v14; // edx
  COLORREF v15; // eax
  COLORREF v16; // eax
  COLORREF v17; // r13d
  int v18; // ebp
  COLORREF BkColor; // ebx
  COLORREF v20; // eax
  UINT uFlags; // ebx
  UINT TextAlign; // eax
  COLORREF v23; // eax
  HBRUSH SolidBrush; // rbp
  UINT align; // [rsp+50h] [rbp-58h]
  unsigned __int16 *lDataa; // [rsp+58h] [rbp-50h]
  COLORREF pColor; // [rsp+64h] [rbp-44h] BYREF

  v5 = (HDC)*((_QWORD *)a1 + 21);
  v6 = 0;
  align = 0;
  if ( a4 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59149161>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_59149161>::GetImpl'::`2'::impl) )
    {
      SysColor = GetSysColor(13);
      v10 = GetSysColor(13);
      v11 = GetSysColor(14);
      if ( *((_DWORD *)a1 + 63) )
      {
        v12 = (void *)*((_QWORD *)a1 + 2);
        if ( v12 )
        {
          if ( !*((_DWORD *)a1 + 62) )
          {
            pColor = 0;
            if ( GetThemeColor(v12, 5, 3, 3802, &pColor) >= 0 )
              SysColor = pColor;
            if ( GetThemeColor(*((HTHEME *)a1 + 2), 5, 3, 3801, &pColor) >= 0 )
              v10 = pColor;
            if ( GetThemeColor(*((HTHEME *)a1 + 2), 5, 3, 3803, &pColor) >= 0 )
              v11 = pColor;
          }
        }
      }
      FillRectClr(v5, a3, SysColor);
      v6 = SetBkMode(v5, 1);
      v13 = SetBkColor(v5, v10);
      v14 = v11;
    }
    else
    {
      v15 = GetSysColor(13);
      FillRectClr(v5, a3, v15);
      v6 = SetBkMode(v5, 1);
      v16 = GetSysColor(13);
      v13 = SetBkColor(v5, v16);
      v14 = GetSysColor(14);
    }
    v17 = SetTextColor(v5, v14);
  }
  else
  {
    v17 = 0;
    v13 = 0;
    if ( hbr )
      FillRect(v5, a3, hbr);
  }
  v18 = 0;
  lDataa = GetLpszItem(a1, a2);
  if ( (*(_DWORD *)(*((_QWORD *)a1 + 3) + 12LL) & 0x8000000) != 0 )
  {
    BkColor = GetBkColor(v5);
    if ( GetSysColor(17) == BkColor )
    {
      v18 = 16;
    }
    else
    {
      v20 = GetSysColor(17);
      SetTextColor(v5, v20);
    }
  }
  uFlags = v18 | 0x8000;
  if ( *((int *)a1 + 27) >= 0 )
    uFlags = v18;
  if ( (*((_BYTE *)a1 + 112) & 1) != 0 )
  {
    TextAlign = GetTextAlign(v5);
    align = SetTextAlign(v5, TextAlign | 0x100);
  }
  v23 = GetSysColor(8);
  SolidBrush = CreateSolidBrush(v23);
  DrawStateW(
    v5,
    SolidBrush,
    ListBox_PrintCallback,
    (LPARAM)lDataa,
    (WPARAM)a1,
    a3->left,
    a3->top,
    a3->right - a3->left,
    a3->bottom - a3->top,
    uFlags);
  if ( SolidBrush )
    DeleteObject(SolidBrush);
  if ( (*((_BYTE *)a1 + 112) & 1) != 0 )
    SetTextAlign(v5, align);
  if ( a4 )
  {
    SetTextColor(v5, v17);
    SetBkColor(v5, v13);
    SetBkMode(v5, v6);
  }
}

```

## disassembly

```asm
0x1800f698c  mov     [rsp+arg_18], rbx
0x1800f6991  push    rbp
0x1800f6992  push    rsi
0x1800f6993  push    rdi
0x1800f6994  push    r12
0x1800f6996  push    r13
0x1800f6998  push    r14
0x1800f699a  push    r15
0x1800f699c  sub     rsp, 70h
0x1800f69a0  mov     rax, cs:__security_cookie
0x1800f69a7  xor     rax, rsp
0x1800f69aa  mov     [rsp+0A8h+var_40], rax
0x1800f69af  mov     rdi, [rcx+0A8h]
0x1800f69b6  xor     r15d, r15d
0x1800f69b9  mov     [rsp+0A8h+var_48], r9d
0x1800f69be  mov     r14, r8
0x1800f69c1  mov     r8, [rsp+0A8h+hbr]; hbr
0x1800f69c9  mov     rsi, rcx
0x1800f69cc  mov     dword ptr [rsp+0A8h+lData], edx
0x1800f69d0  mov     [rsp+0A8h+align], r15d
0x1800f69d5  test    r9d, r9d
0x1800f69d8  jz      loc_1800F6B46
0x1800f69de  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59149161@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59149161@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59149161> `wil::Feature<__WilFeatureTraits_Feature_59149161>::GetImpl(void)'::`2'::impl
0x1800f69e5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59149161@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59149161>::__private_IsEnabled(wil::ReportingKind)
0x1800f69ea  lea     ebx, [r15+0Dh]
0x1800f69ee  mov     ecx, ebx; nIndex
0x1800f69f0  test    al, al
0x1800f69f2  jz      loc_1800F6AF0
0x1800f69f8  call    cs:__imp_GetSysColor
0x1800f69fe  mov     ecx, ebx; nIndex
0x1800f6a00  mov     ebp, eax
0x1800f6a02  call    cs:__imp_GetSysColor
0x1800f6a08  lea     ecx, [r15+0Eh]; nIndex
0x1800f6a0c  mov     ebx, eax
0x1800f6a0e  call    cs:__imp_GetSysColor
0x1800f6a14  mov     r13d, eax
0x1800f6a17  cmp     [rsi+0FCh], r15d
0x1800f6a1e  jz      loc_1800F6ABE
0x1800f6a24  mov     rcx, [rsi+10h]; hTheme
0x1800f6a28  test    rcx, rcx
0x1800f6a2b  jz      loc_1800F6ABE
0x1800f6a31  cmp     [rsi+0F8h], r15d
0x1800f6a38  jnz     loc_1800F6ABE
0x1800f6a3e  lea     r12d, [r15+3]
0x1800f6a42  mov     [rsp+0A8h+var_44], r15d
0x1800f6a47  lea     rax, [rsp+0A8h+var_44]
0x1800f6a4c  mov     r9d, 0EDAh; iPropId
0x1800f6a52  lea     r15d, [r12+2]
0x1800f6a57  mov     [rsp+0A8h+pColor], rax; pColor
0x1800f6a5c  mov     edx, r15d; iPartId
0x1800f6a5f  mov     r8d, r12d; iStateId
0x1800f6a62  call    cs:__imp_GetThemeColor
0x1800f6a68  mov     rcx, [rsi+10h]; hTheme
0x1800f6a6c  mov     r9d, 0ED9h; iPropId
0x1800f6a72  test    eax, eax
0x1800f6a74  mov     r8d, r12d; iStateId
0x1800f6a77  lea     rax, [rsp+0A8h+var_44]
0x1800f6a7c  mov     edx, r15d; iPartId
0x1800f6a7f  cmovns  ebp, [rsp+0A8h+var_44]
0x1800f6a84  mov     [rsp+0A8h+pColor], rax; pColor
0x1800f6a89  call    cs:__imp_GetThemeColor
0x1800f6a8f  mov     rcx, [rsi+10h]; hTheme
0x1800f6a93  mov     r9d, 0EDBh; iPropId
0x1800f6a99  test    eax, eax
0x1800f6a9b  mov     r8d, r12d; iStateId
0x1800f6a9e  lea     rax, [rsp+0A8h+var_44]
0x1800f6aa3  mov     edx, r15d; iPartId
0x1800f6aa6  cmovns  ebx, [rsp+0A8h+var_44]
0x1800f6aab  mov     [rsp+0A8h+pColor], rax; pColor
0x1800f6ab0  call    cs:__imp_GetThemeColor
0x1800f6ab6  test    eax, eax
0x1800f6ab8  cmovns  r13d, [rsp+0A8h+var_44]
0x1800f6abe  mov     r8d, ebp; color
0x1800f6ac1  mov     rdx, r14; lprect
0x1800f6ac4  mov     rcx, rdi; hdc
0x1800f6ac7  call    FillRectClr
0x1800f6acc  mov     edx, 1; mode
0x1800f6ad1  mov     rcx, rdi; hdc
0x1800f6ad4  call    cs:__imp_SetBkMode
0x1800f6ada  mov     edx, ebx; color
0x1800f6adc  mov     rcx, rdi; hdc
0x1800f6adf  mov     r15d, eax
0x1800f6ae2  call    cs:__imp_SetBkColor
0x1800f6ae8  mov     r12d, eax
0x1800f6aeb  mov     edx, r13d
0x1800f6aee  jmp     short loc_1800F6B38
0x1800f6af0  call    cs:__imp_GetSysColor
0x1800f6af6  mov     rdx, r14; lprect
0x1800f6af9  mov     rcx, rdi; hdc
0x1800f6afc  mov     r8d, eax; color
0x1800f6aff  call    FillRectClr
0x1800f6b04  mov     edx, 1; mode
0x1800f6b09  mov     rcx, rdi; hdc
0x1800f6b0c  call    cs:__imp_SetBkMode
0x1800f6b12  mov     ecx, ebx; nIndex
0x1800f6b14  mov     r15d, eax
0x1800f6b17  call    cs:__imp_GetSysColor
0x1800f6b1d  mov     edx, eax; color
0x1800f6b1f  mov     rcx, rdi; hdc
0x1800f6b22  call    cs:__imp_SetBkColor
0x1800f6b28  mov     ecx, 0Eh; nIndex
0x1800f6b2d  mov     r12d, eax
0x1800f6b30  call    cs:__imp_GetSysColor
0x1800f6b36  mov     edx, eax; color
0x1800f6b38  mov     rcx, rdi; hdc
0x1800f6b3b  call    cs:__imp_SetTextColor
0x1800f6b41  mov     r13d, eax
0x1800f6b44  jmp     short loc_1800F6B5D
0x1800f6b46  mov     r13d, r15d
0x1800f6b49  mov     r12d, r15d
0x1800f6b4c  test    r8, r8
0x1800f6b4f  jz      short loc_1800F6B5D
0x1800f6b51  mov     rdx, r14; lprc
0x1800f6b54  mov     rcx, rdi; hDC
0x1800f6b57  call    cs:__imp_FillRect
0x1800f6b5d  mov     edx, dword ptr [rsp+0A8h+lData]; int
0x1800f6b61  mov     rcx, rsi; struct tagLBIV *
0x1800f6b64  xor     ebp, ebp
0x1800f6b66  call    ?GetLpszItem@@YAPEAGPEBUtagLBIV@@H@Z; GetLpszItem(tagLBIV const *,int)
0x1800f6b6b  mov     rcx, [rsi+18h]
0x1800f6b6f  mov     [rsp+0A8h+lData], rax
0x1800f6b74  test    dword ptr [rcx+0Ch], 8000000h
0x1800f6b7b  jz      short loc_1800F6BB0
0x1800f6b7d  mov     rcx, rdi; hdc
0x1800f6b80  call    cs:__imp_GetBkColor
0x1800f6b86  lea     ecx, [rbp+11h]; nIndex
0x1800f6b89  mov     ebx, eax
0x1800f6b8b  call    cs:__imp_GetSysColor
0x1800f6b91  cmp     eax, ebx
0x1800f6b93  jz      short loc_1800F6BAB
0x1800f6b95  lea     ecx, [rbp+11h]; nIndex
0x1800f6b98  call    cs:__imp_GetSysColor
0x1800f6b9e  mov     edx, eax; color
0x1800f6ba0  mov     rcx, rdi; hdc
0x1800f6ba3  call    cs:__imp_SetTextColor
0x1800f6ba9  jmp     short loc_1800F6BB0
0x1800f6bab  mov     ebp, 10h
0x1800f6bb0  mov     ebx, ebp
0x1800f6bb2  bts     ebx, 0Fh
0x1800f6bb6  cmp     dword ptr [rsi+6Ch], 0
0x1800f6bba  cmovge  ebx, ebp
0x1800f6bbd  test    byte ptr [rsi+70h], 1
0x1800f6bc1  jz      short loc_1800F6BDF
0x1800f6bc3  mov     rcx, rdi; hdc
0x1800f6bc6  call    cs:__imp_GetTextAlign
0x1800f6bcc  bts     eax, 8
0x1800f6bd0  mov     rcx, rdi; hdc
0x1800f6bd3  mov     edx, eax; align
0x1800f6bd5  call    cs:__imp_SetTextAlign
0x1800f6bdb  mov     [rsp+0A8h+align], eax
0x1800f6bdf  mov     ecx, 8; nIndex
0x1800f6be4  call    cs:__imp_GetSysColor
0x1800f6bea  mov     ecx, eax; color
0x1800f6bec  call    cs:__imp_CreateSolidBrush
0x1800f6bf2  mov     r8d, [r14+4]
0x1800f6bf6  mov     rbp, rax
0x1800f6bf9  mov     r9d, [r14]
0x1800f6bfc  mov     edx, [r14+0Ch]
0x1800f6c00  mov     ecx, [r14+8]
0x1800f6c04  sub     edx, r8d
0x1800f6c07  mov     [rsp+0A8h+uFlags], ebx; uFlags
0x1800f6c0b  sub     ecx, r9d
0x1800f6c0e  mov     [rsp+0A8h+cy], edx; cy
0x1800f6c12  mov     rdx, rax; hbrFore
0x1800f6c15  mov     [rsp+0A8h+var_70], ecx; cx
0x1800f6c19  mov     rcx, rdi; hdc
0x1800f6c1c  mov     [rsp+0A8h+y], r8d; y
0x1800f6c21  lea     r8, ?ListBox_PrintCallback@@YAHPEAUHDC__@@_J_KHH@Z; qfnCallBack
0x1800f6c28  mov     [rsp+0A8h+x], r9d; x
0x1800f6c2d  mov     r9, [rsp+0A8h+lData]; lData
0x1800f6c32  mov     [rsp+0A8h+pColor], rsi; wData
0x1800f6c37  call    cs:__imp_DrawStateW
0x1800f6c3d  test    rbp, rbp
0x1800f6c40  jz      short loc_1800F6C4B
0x1800f6c42  mov     rcx, rbp; ho
0x1800f6c45  call    cs:__imp_DeleteObject
0x1800f6c4b  test    byte ptr [rsi+70h], 1
0x1800f6c4f  jz      short loc_1800F6C5E
0x1800f6c51  mov     edx, [rsp+0A8h+align]; align
0x1800f6c55  mov     rcx, rdi; hdc
0x1800f6c58  call    cs:__imp_SetTextAlign
0x1800f6c5e  cmp     [rsp+0A8h+var_48], 0
0x1800f6c63  jz      short loc_1800F6C89
0x1800f6c65  mov     edx, r13d; color
0x1800f6c68  mov     rcx, rdi; hdc
0x1800f6c6b  call    cs:__imp_SetTextColor
0x1800f6c71  mov     edx, r12d; color
0x1800f6c74  mov     rcx, rdi; hdc
0x1800f6c77  call    cs:__imp_SetBkColor
0x1800f6c7d  mov     edx, r15d; mode
0x1800f6c80  mov     rcx, rdi; hdc
0x1800f6c83  call    cs:__imp_SetBkMode
0x1800f6c89  mov     rcx, [rsp+0A8h+var_40]
0x1800f6c8e  xor     rcx, rsp; StackCookie
0x1800f6c91  call    __security_check_cookie
0x1800f6c96  mov     rbx, [rsp+0A8h+arg_18]
0x1800f6c9e  add     rsp, 70h
0x1800f6ca2  pop     r15
0x1800f6ca4  pop     r14
0x1800f6ca6  pop     r13
0x1800f6ca8  pop     r12
0x1800f6caa  pop     rdi
0x1800f6cab  pop     rsi
0x1800f6cac  pop     rbp
0x1800f6cad  retn
```
