# DrawScrollArrow

- ea: `0x180089960`
- end: `0x180089aec`
- name: `DrawScrollArrow`
- size: `396`
- prototype: `__int64 __fastcall(HDC hdc, RECT *lprcSrc, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800243a4`
- `0x180087cf0`

## callees

- `0x1800115f0`
- `0x1800877b4`
- `0x180087884`
- `0x180089960`

## import_xrefs

- `GDI32!SelectObject` at `0x180089a27`
- `GDI32!SelectObject` at `0x180089ab2`
- `GDI32!SelectObject` at `0x180089a27`
- `GDI32!SelectObject` at `0x180089ab2`
- `GDI32!DeleteObject` at `0x180089abb`
- `GDI32!DeleteObject` at `0x180089abb`
- `GDI32!SetBkMode` at `0x180089a85`
- `GDI32!SetBkMode` at `0x180089aa6`
- `GDI32!SetBkMode` at `0x180089a85`
- `GDI32!SetBkMode` at `0x180089aa6`
- `GDI32!GetLayout` at `0x1800899a8`
- `GDI32!GetLayout` at `0x1800899a8`
- `GDI32!CreateFontW` at `0x180089a18`
- `GDI32!CreateFontW` at `0x180089a18`
- `USER32!CopyRect` at `0x180089a52`
- `USER32!CopyRect` at `0x180089a52`

## pseudocode

```c
BOOL __fastcall DrawScrollArrow(HDC hdc, RECT *lprcSrc, unsigned int a3)
{
  unsigned int v3; // esi
  int v4; // ebx
  int v7; // ecx
  HFONT FontW; // r15
  HGDIOBJ v9; // r12
  unsigned __int16 v10; // r14
  int v11; // ebx
  unsigned int cWeight; // [rsp+20h] [rbp-A8h]
  DWORD bItalic; // [rsp+28h] [rbp-A0h]
  DWORD bUnderline; // [rsp+30h] [rbp-98h]
  struct tagRECT rcDst; // [rsp+70h] [rbp-58h] BYREF

  v3 = a3;
  v4 = a3 & 4;
  if ( (GetLayout(hdc) & 1) != 0 && v4 )
    v3 ^= 0x20u;
  v7 = lprcSrc->right - lprcSrc->left;
  if ( v7 >= lprcSrc->bottom - lprcSrc->top )
    v7 = lprcSrc->bottom - lprcSrc->top;
  FontW = CreateFontW(v7 - 2 * g_cxBorder, 0, 0, 0, 400, 0, 0, 0, 2u, 0, 0, 0, 0, L"MARLETT");
  v9 = SelectObject(hdc, FontW);
  rcDst = 0;
  v10 = v4 != 0 ? 52 : 54;
  if ( (v3 & 0x20) == 0 )
    v10 = v4 != 0 ? 51 : 53;
  CopyRect(&rcDst, lprcSrc);
  DrawBlankButton(hdc, &rcDst, v3);
  if ( rcDst.right - rcDst.left > 0 && rcDst.bottom - rcDst.top > 0 )
  {
    v11 = SetBkMode(hdc, 1);
    DrawChar(hdc, &rcDst, v3, v10, cWeight, bItalic, bUnderline);
    SetBkMode(hdc, v11);
  }
  SelectObject(hdc, v9);
  return DeleteObject(FontW);
}

```

## disassembly

```asm
0x180089960  mov     [rsp+arg_18], rbx
0x180089965  push    rbp
0x180089966  push    rsi
0x180089967  push    rdi
0x180089968  push    r12
0x18008996a  push    r13
0x18008996c  push    r14
0x18008996e  push    r15
0x180089970  sub     rsp, 90h
0x180089977  mov     rax, cs:__security_cookie
0x18008997e  xor     rax, rsp
0x180089981  mov     [rsp+0C8h+var_48], rax
0x180089989  mov     ebx, r8d
0x18008998c  mov     esi, r8d
0x18008998f  and     ebx, 4
0x180089992  mov     r13, rdx
0x180089995  mov     eax, ebx
0x180089997  mov     rdi, rcx
0x18008999a  neg     eax
0x18008999c  sbb     bp, bp
0x18008999f  and     bp, 0FFFEh
0x1800899a4  add     bp, 35h ; '5'
0x1800899a8  call    cs:__imp_GetLayout
0x1800899ae  xor     edx, edx; cWidth
0x1800899b0  test    al, 1
0x1800899b2  jz      short loc_1800899BB
0x1800899b4  test    ebx, ebx
0x1800899b6  jz      short loc_1800899BB
0x1800899b8  xor     esi, 20h
0x1800899bb  mov     eax, [r13+0Ch]
0x1800899bf  sub     eax, [r13+4]
0x1800899c3  mov     ecx, [r13+8]
0x1800899c7  sub     ecx, [r13+0]
0x1800899cb  cmp     ecx, eax
0x1800899cd  cmovge  ecx, eax
0x1800899d0  mov     eax, cs:g_cxBorder
0x1800899d6  add     eax, eax
0x1800899d8  xor     r9d, r9d; cOrientation
0x1800899db  sub     ecx, eax; cHeight
0x1800899dd  xor     r8d, r8d; cEscapement
0x1800899e0  lea     rax, pszFaceName; "MARLETT"
0x1800899e7  mov     [rsp+0C8h+pszFaceName], rax; pszFaceName
0x1800899ec  mov     [rsp+0C8h+iPitchAndFamily], edx; iPitchAndFamily
0x1800899f0  mov     [rsp+0C8h+iQuality], edx; iQuality
0x1800899f4  mov     [rsp+0C8h+iClipPrecision], edx; iClipPrecision
0x1800899f8  mov     [rsp+0C8h+iOutPrecision], edx; iOutPrecision
0x1800899fc  mov     [rsp+0C8h+iCharSet], 2; iCharSet
0x180089a04  mov     [rsp+0C8h+bStrikeOut], edx; bStrikeOut
0x180089a08  mov     [rsp+0C8h+bUnderline], edx; int
0x180089a0c  mov     [rsp+0C8h+bItalic], edx; int
0x180089a10  mov     [rsp+0C8h+cWeight], 190h; unsigned int
0x180089a18  call    cs:__imp_CreateFontW
0x180089a1e  mov     rdx, rax; h
0x180089a21  mov     rcx, rdi; hdc
0x180089a24  mov     r15, rax
0x180089a27  call    cs:__imp_SelectObject
0x180089a2d  xorps   xmm0, xmm0
0x180089a30  lea     rcx, [rsp+0C8h+rcDst]; lprcDst
0x180089a35  mov     ebx, 1
0x180089a3a  test    sil, 20h
0x180089a3e  mov     rdx, r13; lprcSrc
0x180089a41  mov     r12, rax
0x180089a44  movups  xmmword ptr [rsp+0C8h+rcDst.left], xmm0
0x180089a49  lea     r14d, [rbx+rbp]
0x180089a4d  cmovz   r14w, bp
0x180089a52  call    cs:__imp_CopyRect
0x180089a58  mov     r8d, esi; unsigned int
0x180089a5b  lea     rdx, [rsp+0C8h+rcDst]; lprcDst
0x180089a60  mov     rcx, rdi; hdc
0x180089a63  call    ?DrawBlankButton@@YAXPEAUHDC__@@PEAUtagRECT@@K@Z; DrawBlankButton(HDC__ *,tagRECT *,ulong)
0x180089a68  mov     eax, [rsp+0C8h+rcDst.right]
0x180089a6c  sub     eax, [rsp+0C8h+rcDst.left]
0x180089a70  test    eax, eax
0x180089a72  jle     short loc_180089AAC
0x180089a74  mov     eax, [rsp+0C8h+rcDst.bottom]
0x180089a78  sub     eax, [rsp+0C8h+rcDst.top]
0x180089a7c  test    eax, eax
0x180089a7e  jle     short loc_180089AAC
0x180089a80  mov     edx, ebx; mode
0x180089a82  mov     rcx, rdi; hdc
0x180089a85  call    cs:__imp_SetBkMode
0x180089a8b  movzx   r9d, r14w; unsigned __int16
0x180089a8f  lea     rdx, [rsp+0C8h+rcDst]; struct tagRECT *
0x180089a94  mov     r8d, esi; unsigned int
0x180089a97  mov     rcx, rdi; hdc
0x180089a9a  mov     ebx, eax
0x180089a9c  call    ?DrawChar@@YAHPEAUHDC__@@PEBUtagRECT@@IGIHH@Z; DrawChar(HDC__ *,tagRECT const *,uint,ushort,uint,int,int)
0x180089aa1  mov     edx, ebx; mode
0x180089aa3  mov     rcx, rdi; hdc
0x180089aa6  call    cs:__imp_SetBkMode
0x180089aac  mov     rdx, r12; h
0x180089aaf  mov     rcx, rdi; hdc
0x180089ab2  call    cs:__imp_SelectObject
0x180089ab8  mov     rcx, r15; ho
0x180089abb  call    cs:__imp_DeleteObject
0x180089ac1  mov     rcx, [rsp+0C8h+var_48]
0x180089ac9  xor     rcx, rsp; StackCookie
0x180089acc  call    __security_check_cookie
0x180089ad1  mov     rbx, [rsp+0C8h+arg_18]
0x180089ad9  add     rsp, 90h
0x180089ae0  pop     r15
0x180089ae2  pop     r14
0x180089ae4  pop     r13
0x180089ae6  pop     r12
0x180089ae8  pop     rdi
0x180089ae9  pop     rsi
0x180089aea  pop     rbp
0x180089aeb  retn
```
