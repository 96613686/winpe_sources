# CInfoPanel::RenderText(HDC__ *,tagRECT *,uint,ushort const *)

- ea: `0x18050c03c`
- end: `0x18050c1ab`
- name: `?RenderText@CInfoPanel@@AEAAXPEAUHDC__@@PEAUtagRECT@@IPEBG@Z`
- size: `367`
- prototype: `void __usercall(CInfoPanel *__hidden this@<rcx>, HDC hdc@<rdx>, struct tagRECT *@<r8>, unsigned int@<r9d>, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18050bea8`

## callees

- `0x18050c03c`
- `0x18050c44c`
- `0x180688f3e`
- `0x180688fc0`

## import_xrefs

- `GDI32!DeleteObject` at `0x18050c181`
- `GDI32!DeleteObject` at `0x18050c181`
- `GDI32!SelectObject` at `0x18050c11e`
- `GDI32!SelectObject` at `0x18050c173`
- `GDI32!SelectObject` at `0x18050c11e`
- `GDI32!SelectObject` at `0x18050c173`
- `GDI32!SetBkMode` at `0x18050c102`
- `GDI32!SetBkMode` at `0x18050c102`
- `GDI32!SetTextColor` at `0x18050c10d`
- `GDI32!SetTextColor` at `0x18050c10d`
- `GDI32!CreateFontIndirectW` at `0x18050c0f1`
- `GDI32!CreateFontIndirectW` at `0x18050c0f1`
- `USER32!DrawTextW` at `0x18050c162`
- `USER32!DrawTextW` at `0x18050c162`
- `USER32!SystemParametersInfoW` at `0x18050c0cd`
- `USER32!SystemParametersInfoW` at `0x18050c0cd`
- `USER32!GetSysColor` at `0x18050c0ac`
- `USER32!GetSysColor` at `0x18050c0ac`

## pseudocode

```c
void __fastcall CInfoPanel::RenderText(
        CInfoPanel *this,
        HDC hdc,
        struct tagRECT *a3,
        int a4,
        const unsigned __int16 *lpchText)
{
  HGDIOBJ v9; // rsi
  COLORREF SysColor; // ebp
  HFONT v11; // rbx
  __int64 v12; // r8
  struct tagRECT rc; // [rsp+30h] [rbp-268h] BYREF
  _DWORD pvParam[6]; // [rsp+40h] [rbp-258h] BYREF
  LOGFONTW lf; // [rsp+58h] [rbp-240h] BYREF

  memset_0(pvParam, 0, 0x1F8u);
  v9 = 0;
  rc = *a3;
  if ( *((_DWORD *)this + 731) )
    SysColor = GetSysColor(19);
  else
    SysColor = 0xFFFFFF;
  pvParam[0] = 504;
  SystemParametersInfoW(0x29u, 0x1F8u, pvParam, 0);
  lf.lfWeight = 500;
  lf.lfHeight = CInfoPanel::ScaleFontHeight(this, -12);
  v11 = CreateFontIndirectW(&lf);
  SetBkMode(hdc, 1);
  SetTextColor(hdc, SysColor);
  if ( v11 )
    v9 = SelectObject(hdc, v11);
  v12 = -1;
  do
    ++v12;
  while ( lpchText[v12] );
  DrawTextW(hdc, lpchText, v12, &rc, a4 | (*((_DWORD *)this + 730) != 0 ? 163876 : 32804));
  if ( v9 )
    SelectObject(hdc, v9);
  if ( v11 )
    DeleteObject(v11);
}

```

## disassembly

```asm
0x18050c03c  push    rbx
0x18050c03e  push    rbp
0x18050c03f  push    rsi
0x18050c040  push    rdi
0x18050c041  push    r12
0x18050c043  push    r13
0x18050c045  push    r14
0x18050c047  push    r15
0x18050c049  sub     rsp, 258h
0x18050c050  mov     rax, cs:__security_cookie
0x18050c057  xor     rax, rsp
0x18050c05a  mov     [rsp+298h+var_58], rax
0x18050c062  mov     r15, [rsp+298h+lpchText]
0x18050c06a  mov     rbx, r8
0x18050c06d  mov     rdi, rdx
0x18050c070  mov     r14, rcx
0x18050c073  xor     edx, edx; Val
0x18050c075  lea     rcx, [rsp+298h+pvParam]; void *
0x18050c07a  mov     r8d, 1F8h; Size
0x18050c080  mov     r12d, r9d
0x18050c083  call    memset_0
0x18050c088  movups  xmm0, xmmword ptr [rbx]
0x18050c08b  xor     r13d, r13d
0x18050c08e  mov     esi, r13d
0x18050c091  movdqu  xmmword ptr [rsp+298h+rc.left], xmm0
0x18050c097  cmp     [r14+0B6Ch], r13d
0x18050c09e  jnz     short loc_18050C0A7
0x18050c0a0  mov     ebp, 0FFFFFFh
0x18050c0a5  jmp     short loc_18050C0B4
0x18050c0a7  mov     ecx, 13h; nIndex
0x18050c0ac  call    cs:__imp_GetSysColor
0x18050c0b2  mov     ebp, eax
0x18050c0b4  xor     r9d, r9d; fWinIni
0x18050c0b7  mov     [rsp+298h+pvParam], 1F8h
0x18050c0bf  lea     r8, [rsp+298h+pvParam]; pvParam
0x18050c0c4  mov     edx, 1F8h; uiParam
0x18050c0c9  lea     ecx, [r9+29h]; uiAction
0x18050c0cd  call    cs:__imp_SystemParametersInfoW
0x18050c0d3  mov     edx, 0FFFFFFF4h; int
0x18050c0d8  mov     [rsp+298h+lf.lfWeight], 1F4h
0x18050c0e0  mov     rcx, r14; this
0x18050c0e3  call    ?ScaleFontHeight@CInfoPanel@@AEAAHH@Z; CInfoPanel::ScaleFontHeight(int)
0x18050c0e8  lea     rcx, [rsp+298h+lf]; lplf
0x18050c0ed  mov     [rsp+298h+lf.lfHeight], eax
0x18050c0f1  call    cs:__imp_CreateFontIndirectW
0x18050c0f7  mov     edx, 1; mode
0x18050c0fc  mov     rcx, rdi; hdc
0x18050c0ff  mov     rbx, rax
0x18050c102  call    cs:__imp_SetBkMode
0x18050c108  mov     edx, ebp; color
0x18050c10a  mov     rcx, rdi; hdc
0x18050c10d  call    cs:__imp_SetTextColor
0x18050c113  test    rbx, rbx
0x18050c116  jz      short loc_18050C127
0x18050c118  mov     rdx, rbx; h
0x18050c11b  mov     rcx, rdi; hdc
0x18050c11e  call    cs:__imp_SelectObject
0x18050c124  mov     rsi, rax
0x18050c127  mov     ecx, [r14+0B68h]
0x18050c12e  neg     ecx
0x18050c130  sbb     r9d, r9d
0x18050c133  and     r9d, 20000h
0x18050c13a  add     r9d, 8024h
0x18050c141  or      r9d, r12d
0x18050c144  or      r8, 0FFFFFFFFFFFFFFFFh
0x18050c148  inc     r8; cchText
0x18050c14b  cmp     [r15+r8*2], r13w
0x18050c150  jnz     short loc_18050C148
0x18050c152  mov     [rsp+298h+format], r9d; format
0x18050c157  mov     rdx, r15; lpchText
0x18050c15a  lea     r9, [rsp+298h+rc]; lprc
0x18050c15f  mov     rcx, rdi; hdc
0x18050c162  call    cs:__imp_DrawTextW
0x18050c168  test    rsi, rsi
0x18050c16b  jz      short loc_18050C179
0x18050c16d  mov     rdx, rsi; h
0x18050c170  mov     rcx, rdi; hdc
0x18050c173  call    cs:__imp_SelectObject
0x18050c179  test    rbx, rbx
0x18050c17c  jz      short loc_18050C187
0x18050c17e  mov     rcx, rbx; ho
0x18050c181  call    cs:__imp_DeleteObject
0x18050c187  mov     rcx, [rsp+298h+var_58]
0x18050c18f  xor     rcx, rsp; StackCookie
0x18050c192  call    __security_check_cookie
0x18050c197  add     rsp, 258h
0x18050c19e  pop     r15
0x18050c1a0  pop     r14
0x18050c1a2  pop     r13
0x18050c1a4  pop     r12
0x18050c1a6  pop     rdi
0x18050c1a7  pop     rsi
0x18050c1a8  pop     rbp
0x18050c1a9  pop     rbx
0x18050c1aa  retn
```
