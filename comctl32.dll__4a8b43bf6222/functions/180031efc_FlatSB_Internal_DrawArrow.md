# FlatSB_Internal_DrawArrow

- ea: `0x180031efc`
- end: `0x1800321d6`
- name: `FlatSB_Internal_DrawArrow`
- size: `730`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18003272c`
- `0x18003286c`

## callees

- `0x1800115f0`
- `0x180031efc`
- `0x1800321dc`
- `0x180032464`

## import_xrefs

- `GDI32!SelectObject` at `0x18003215d`
- `GDI32!SelectObject` at `0x18003219c`
- `GDI32!SelectObject` at `0x18003215d`
- `GDI32!SelectObject` at `0x18003219c`
- `GDI32!DeleteObject` at `0x1800321a5`
- `GDI32!DeleteObject` at `0x1800321a5`
- `GDI32!SetBkMode` at `0x18003214f`
- `GDI32!SetBkMode` at `0x180032190`
- `GDI32!SetBkMode` at `0x18003214f`
- `GDI32!SetBkMode` at `0x180032190`
- `GDI32!SetTextColor` at `0x18003216b`
- `GDI32!SetTextColor` at `0x18003216b`
- `GDI32!CreateFontW` at `0x18003213a`
- `GDI32!CreateFontW` at `0x18003213a`
- `GDI32!TextOutW` at `0x180032185`
- `GDI32!TextOutW` at `0x180032185`
- `USER32!GetSysColor` at `0x1800320ec`
- `USER32!GetSysColor` at `0x1800320ec`
- `USER32!CopyRect` at `0x180032007`
- `USER32!CopyRect` at `0x180032007`
- `USER32!DrawFrameControl` at `0x18003202d`
- `USER32!DrawFrameControl` at `0x18003202d`

## pseudocode

```c
int __fastcall FlatSB_Internal_DrawArrow(_DWORD *a1, HDC a2, const RECT *a3, UINT a4, __int16 a5)
{
  int result; // eax
  UINT v7; // ebx
  int v9; // r15d
  int v10; // eax
  const WCHAR *v11; // r12
  bool v12; // zf
  int v13; // esi
  unsigned int v14; // ebx
  LONG left; // r9d
  LONG top; // r10d
  int v17; // r8d
  int v18; // ecx
  int v19; // edi
  int v20; // r13d
  unsigned int v21; // ebx
  unsigned int v22; // ebx
  DWORD SysColor; // ebp
  unsigned int v24; // ebx
  HFONT FontW; // rsi
  int v26; // edi
  HGDIOBJ v27; // rbx
  int y; // [rsp+70h] [rbp-58h]
  struct tagRECT rcDst; // [rsp+78h] [rbp-50h] BYREF

  result = a3->right;
  v7 = a4;
  if ( a3->left >= result )
    return result;
  result = a3->bottom;
  if ( a3->top >= result )
    return result;
  result = a4 - 2;
  if ( a4 - 2 <= 1 )
    v9 = a1[49];
  else
    v9 = a1[48];
  if ( a4 )
  {
    switch ( a4 )
    {
      case 1u:
        v10 = 0;
        v11 = L"6";
        v12 = a1[52] == 2;
        break;
      case 2u:
        v10 = 0;
        v11 = L"3";
        v12 = a1[52] == 5;
        break;
      case 3u:
        v10 = 0;
        v11 = L"4";
        v12 = a1[52] == 6;
        break;
      default:
        return result;
    }
  }
  else
  {
    v10 = 0;
    v11 = L"5";
    v12 = a1[52] == 1;
  }
  LOBYTE(v10) = v12;
  v13 = a5 & 0x200;
  if ( (a5 & 0x100) == 0 && v10 && a1[25] != (a5 & 0x100) )
    v13 = 1;
  if ( !v9 )
  {
    rcDst = 0;
    CopyRect(&rcDst, a3);
    if ( (a5 & 0x100) != 0 )
    {
      v7 |= 0x100u;
    }
    else if ( v13 )
    {
      v7 |= 0x4000u;
    }
    return DrawFrameControl(a2, &rcDst, 3u, v7);
  }
  if ( (a5 & 0x100) != 0 )
  {
    v14 = 3;
  }
  else if ( v13 )
  {
    v14 = 2;
  }
  else
  {
    v14 = v10 != 0;
  }
  if ( v9 == 1 )
    FlatSB_Internal_DrawEncartaBox(a2, a3, v14);
  else
    FlatSB_Internal_DrawBox(a2, a3, v14);
  left = a3->left;
  result = a3->right - a3->left;
  top = a3->top;
  v17 = result;
  v18 = a3->bottom - top;
  if ( result >= v18 )
    v17 = a3->bottom - top;
  if ( v17 >= 4 )
  {
    v19 = v17 - 4;
    v20 = (result - v17) / 2 + left;
    y = top + (v18 - v17) / 2 + 2;
    if ( v9 == 2 )
    {
      if ( !v14 )
        goto LABEL_45;
      v21 = v14 - 1;
      if ( !v21 || (v22 = v21 - 1) == 0 )
      {
        SysColor = 0xFFFFFF;
LABEL_46:
        FontW = CreateFontW(v19, 0, 0, 0, 400, 0, 0, 0, 2u, 0, 0, 0, 0, L"MARLETT");
        v26 = SetBkMode(a2, 1);
        v27 = SelectObject(a2, FontW);
        SetTextColor(a2, SysColor);
        TextOutW(a2, v20 + 2, y, v11, 1);
        SetBkMode(a2, v26);
        SelectObject(a2, v27);
        return DeleteObject(FontW);
      }
    }
    else
    {
      if ( !v14 )
        goto LABEL_45;
      v24 = v14 - 1;
      if ( !v24 )
        goto LABEL_45;
      v22 = v24 - 1;
      if ( !v22 )
        goto LABEL_45;
    }
    if ( v22 == 1 )
    {
      SysColor = GetSysColor(16);
      goto LABEL_46;
    }
LABEL_45:
    SysColor = 0;
    goto LABEL_46;
  }
  return result;
}

```

## disassembly

```asm
0x180031efc  mov     [rsp+arg_0], rbx
0x180031f01  push    rbp
0x180031f02  push    rsi
0x180031f03  push    rdi
0x180031f04  push    r12
0x180031f06  push    r13
0x180031f08  push    r14
0x180031f0a  push    r15
0x180031f0c  sub     rsp, 90h
0x180031f13  mov     rax, cs:__security_cookie
0x180031f1a  xor     rax, rsp
0x180031f1d  mov     [rsp+0C8h+var_40], rax
0x180031f25  mov     eax, [r8+8]
0x180031f29  mov     r14, rdx
0x180031f2c  mov     ebx, r9d
0x180031f2f  mov     rdi, r8
0x180031f32  mov     rdx, rcx
0x180031f35  cmp     [r8], eax
0x180031f38  jge     loc_1800321AB
0x180031f3e  mov     eax, [r8+0Ch]
0x180031f42  cmp     [r8+4], eax
0x180031f46  jge     loc_1800321AB
0x180031f4c  lea     eax, [r9-2]
0x180031f50  mov     r8d, 1
0x180031f56  cmp     eax, r8d
0x180031f59  jbe     short loc_180031F64
0x180031f5b  mov     r15d, [rcx+0C0h]
0x180031f62  jmp     short loc_180031F6B
0x180031f64  mov     r15d, [rcx+0C4h]
0x180031f6b  mov     ecx, ebx
0x180031f6d  test    ebx, ebx
0x180031f6f  jz      short loc_180031FBA
0x180031f71  sub     ecx, r8d
0x180031f74  jz      short loc_180031FA8
0x180031f76  sub     ecx, r8d
0x180031f79  jz      short loc_180031F96
0x180031f7b  cmp     ecx, r8d
0x180031f7e  jnz     loc_1800321AB
0x180031f84  xor     eax, eax
0x180031f86  lea     r12, a4; "4"
0x180031f8d  cmp     dword ptr [rdx+0D0h], 6
0x180031f94  jmp     short loc_180031FCA
0x180031f96  xor     eax, eax
0x180031f98  lea     r12, a3; "3"
0x180031f9f  cmp     dword ptr [rdx+0D0h], 5
0x180031fa6  jmp     short loc_180031FCA
0x180031fa8  xor     eax, eax
0x180031faa  lea     r12, a6; "6"
0x180031fb1  cmp     dword ptr [rdx+0D0h], 2
0x180031fb8  jmp     short loc_180031FCA
0x180031fba  xor     eax, eax
0x180031fbc  lea     r12, a5; "5"
0x180031fc3  cmp     [rdx+0D0h], r8d
0x180031fca  mov     esi, [rsp+0C8h+arg_20]
0x180031fd1  setz    al
0x180031fd4  mov     ebp, esi
0x180031fd6  mov     r13d, 100h
0x180031fdc  and     esi, 200h
0x180031fe2  and     ebp, r13d
0x180031fe5  jnz     short loc_180031FF2
0x180031fe7  test    eax, eax
0x180031fe9  jz      short loc_180031FF2
0x180031feb  cmp     [rdx+64h], ebp
0x180031fee  cmovnz  esi, r8d
0x180031ff2  test    r15d, r15d
0x180031ff5  jnz     short loc_180032038
0x180031ff7  xorps   xmm0, xmm0
0x180031ffa  lea     rcx, [rsp+0C8h+rcDst]; lprcDst
0x180031fff  mov     rdx, rdi; lprcSrc
0x180032002  movups  xmmword ptr [rsp+0C8h+rcDst.left], xmm0
0x180032007  call    cs:__imp_CopyRect
0x18003200d  lea     r8d, [r15+3]; UINT
0x180032011  mov     rcx, r14; HDC
0x180032014  lea     rdx, [rsp+0C8h+rcDst]; LPRECT
0x180032019  test    ebp, ebp
0x18003201b  jz      short loc_180032022
0x18003201d  or      ebx, r13d
0x180032020  jmp     short loc_18003202A
0x180032022  test    esi, esi
0x180032024  jz      short loc_18003202A
0x180032026  bts     ebx, 0Eh
0x18003202a  mov     r9d, ebx; UINT
0x18003202d  call    cs:__imp_DrawFrameControl
0x180032033  jmp     loc_1800321AB
0x180032038  test    ebp, ebp
0x18003203a  jz      short loc_180032043
0x18003203c  mov     ebx, 3
0x180032041  jmp     short loc_180032055
0x180032043  test    esi, esi
0x180032045  jz      short loc_18003204E
0x180032047  mov     ebx, 2
0x18003204c  jmp     short loc_180032055
0x18003204e  xor     ebx, ebx
0x180032050  test    eax, eax
0x180032052  setnz   bl
0x180032055  cmp     r15d, r8d
0x180032058  mov     rdx, rdi
0x18003205b  mov     r8d, ebx
0x18003205e  mov     rcx, r14
0x180032061  jnz     short loc_18003206A
0x180032063  call    FlatSB_Internal_DrawEncartaBox
0x180032068  jmp     short loc_18003206F
0x18003206a  call    FlatSB_Internal_DrawBox
0x18003206f  mov     eax, [rdi+8]
0x180032072  mov     ecx, [rdi+0Ch]
0x180032075  mov     r9d, [rdi]
0x180032078  sub     eax, r9d
0x18003207b  mov     r10d, [rdi+4]
0x18003207f  mov     r8d, eax
0x180032082  sub     ecx, r10d
0x180032085  cmp     eax, ecx
0x180032087  cmovge  r8d, ecx
0x18003208b  cmp     r8d, 4
0x18003208f  jl      loc_1800321AB
0x180032095  sub     eax, r8d
0x180032098  lea     edi, [r8-4]
0x18003209c  cdq
0x18003209d  sub     ecx, r8d
0x1800320a0  sub     eax, edx
0x1800320a2  xor     esi, esi
0x1800320a4  sar     eax, 1
0x1800320a6  lea     r13d, [rax+r9]
0x1800320aa  mov     eax, ecx
0x1800320ac  cdq
0x1800320ad  sub     eax, edx
0x1800320af  sar     eax, 1
0x1800320b1  add     eax, 2
0x1800320b4  add     eax, r10d
0x1800320b7  mov     [rsp+0C8h+y], eax
0x1800320bb  cmp     r15d, 2
0x1800320bf  jnz     short loc_1800320D6
0x1800320c1  test    ebx, ebx
0x1800320c3  jz      short loc_1800320F6
0x1800320c5  sub     ebx, 1
0x1800320c8  jz      short loc_1800320CF
0x1800320ca  sub     ebx, 1
0x1800320cd  jnz     short loc_1800320E4
0x1800320cf  mov     ebp, 0FFFFFFh
0x1800320d4  jmp     short loc_1800320F8
0x1800320d6  test    ebx, ebx
0x1800320d8  jz      short loc_1800320F6
0x1800320da  sub     ebx, 1
0x1800320dd  jz      short loc_1800320F6
0x1800320df  sub     ebx, 1
0x1800320e2  jz      short loc_1800320F6
0x1800320e4  cmp     ebx, 1
0x1800320e7  jnz     short loc_1800320F6
0x1800320e9  lea     ecx, [rbx+0Fh]; nIndex
0x1800320ec  call    cs:__imp_GetSysColor
0x1800320f2  mov     ebp, eax
0x1800320f4  jmp     short loc_1800320F8
0x1800320f6  mov     ebp, esi
0x1800320f8  lea     rax, pszFaceName; "MARLETT"
0x1800320ff  xor     r9d, r9d; cOrientation
0x180032102  mov     [rsp+0C8h+pszFaceName], rax; pszFaceName
0x180032107  xor     r8d, r8d; cEscapement
0x18003210a  mov     [rsp+0C8h+iPitchAndFamily], esi; iPitchAndFamily
0x18003210e  xor     edx, edx; cWidth
0x180032110  mov     [rsp+0C8h+iQuality], esi; iQuality
0x180032114  mov     ecx, edi; cHeight
0x180032116  mov     [rsp+0C8h+iClipPrecision], esi; iClipPrecision
0x18003211a  mov     [rsp+0C8h+iOutPrecision], esi; iOutPrecision
0x18003211e  mov     [rsp+0C8h+iCharSet], 2; iCharSet
0x180032126  mov     [rsp+0C8h+bStrikeOut], esi; bStrikeOut
0x18003212a  mov     [rsp+0C8h+bUnderline], esi; bUnderline
0x18003212e  mov     [rsp+0C8h+bItalic], esi; bItalic
0x180032132  mov     [rsp+0C8h+cWeight], 190h; cWeight
0x18003213a  call    cs:__imp_CreateFontW
0x180032140  mov     r15d, 1
0x180032146  mov     rcx, r14; hdc
0x180032149  mov     edx, r15d; mode
0x18003214c  mov     rsi, rax
0x18003214f  call    cs:__imp_SetBkMode
0x180032155  mov     rdx, rsi; h
0x180032158  mov     rcx, r14; hdc
0x18003215b  mov     edi, eax
0x18003215d  call    cs:__imp_SelectObject
0x180032163  mov     edx, ebp; color
0x180032165  mov     rcx, r14; hdc
0x180032168  mov     rbx, rax
0x18003216b  call    cs:__imp_SetTextColor
0x180032171  mov     r8d, [rsp+0C8h+y]; y
0x180032176  lea     edx, [r13+2]; x
0x18003217a  mov     r9, r12; lpString
0x18003217d  mov     [rsp+0C8h+cWeight], r15d; c
0x180032182  mov     rcx, r14; hdc
0x180032185  call    cs:__imp_TextOutW
0x18003218b  mov     edx, edi; mode
0x18003218d  mov     rcx, r14; hdc
0x180032190  call    cs:__imp_SetBkMode
0x180032196  mov     rdx, rbx; h
0x180032199  mov     rcx, r14; hdc
0x18003219c  call    cs:__imp_SelectObject
0x1800321a2  mov     rcx, rsi; ho
0x1800321a5  call    cs:__imp_DeleteObject
0x1800321ab  mov     rcx, [rsp+0C8h+var_40]
0x1800321b3  xor     rcx, rsp; StackCookie
0x1800321b6  call    __security_check_cookie
0x1800321bb  mov     rbx, [rsp+0C8h+arg_0]
0x1800321c3  add     rsp, 90h
0x1800321ca  pop     r15
0x1800321cc  pop     r14
0x1800321ce  pop     r13
0x1800321d0  pop     r12
0x1800321d2  pop     rdi
0x1800321d3  pop     rsi
0x1800321d4  pop     rbp
0x1800321d5  retn
```
