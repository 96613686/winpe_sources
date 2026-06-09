# DirectUI::CreateDibBrush(HDC__ *,int,int,int,int,int)

- ea: `0x18018cb3c`
- end: `0x18018cc6e`
- name: `?CreateDibBrush@DirectUI@@YAPEAUHBRUSH__@@PEAUHDC__@@HHHHH@Z`
- size: `306`
- prototype: `HBRUSH __usercall@<rax>(HDC hdcSrc@<rcx>, HDC@<rdx>, int@<r8d>, int@<r9d>, int, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18018dec4`

## callees

- `0x18018cb3c`

## import_xrefs

- `GDI32!DeleteObject` at `0x18018cc4b`
- `GDI32!DeleteObject` at `0x18018cc4b`
- `GDI32!SelectObject` at `0x18018cbc5`
- `GDI32!SelectObject` at `0x18018cc18`
- `GDI32!SelectObject` at `0x18018cbc5`
- `GDI32!SelectObject` at `0x18018cc18`
- `GDI32!DeleteDC` at `0x18018cc42`
- `GDI32!DeleteDC` at `0x18018cc42`
- `GDI32!CreateCompatibleDC` at `0x18018cb84`
- `GDI32!CreateCompatibleDC` at `0x18018cb84`
- `GDI32!SetLayout` at `0x18018cbb9`
- `GDI32!SetLayout` at `0x18018cc39`
- `GDI32!SetLayout` at `0x18018cbb9`
- `GDI32!SetLayout` at `0x18018cc39`
- `GDI32!CreateCompatibleBitmap` at `0x18018cb6f`
- `GDI32!CreateCompatibleBitmap` at `0x18018cb6f`
- `GDI32!BitBlt` at `0x18018cc0c`
- `GDI32!BitBlt` at `0x18018cc0c`
- `GDI32!CreatePatternBrush` at `0x18018cc21`
- `GDI32!CreatePatternBrush` at `0x18018cc21`
- `GDI32!GetLayout` at `0x18018cba4`
- `GDI32!GetLayout` at `0x18018cba4`

## pseudocode

```c
HBRUSH __fastcall DirectUI::CreateDibBrush(HDC hdcSrc, HDC a2, int a3, int a4, int cy, int a6)
{
  HBRUSH PatternBrush; // r15
  HBITMAP CompatibleBitmap; // rsi
  HDC CompatibleDC; // rax
  HDC v11; // rbx
  DWORD Layout; // edi
  HGDIOBJ v13; // r12
  int x1; // [rsp+88h] [rbp+10h]

  x1 = (int)a2;
  PatternBrush = 0;
  CompatibleBitmap = CreateCompatibleBitmap(hdcSrc, a4, cy);
  if ( CompatibleBitmap )
  {
    CompatibleDC = CreateCompatibleDC(hdcSrc);
    v11 = CompatibleDC;
    if ( CompatibleDC )
    {
      Layout = 0;
      if ( a6 )
      {
        Layout = GetLayout(CompatibleDC);
        SetLayout(v11, (Layout & 1) == 0);
      }
      v13 = SelectObject(v11, CompatibleBitmap);
      if ( v13 )
      {
        BitBlt(v11, 0, 0, a4, cy, hdcSrc, x1, a3, 0xCC0020u);
        SelectObject(v11, v13);
        PatternBrush = CreatePatternBrush(CompatibleBitmap);
      }
      if ( a6 )
        SetLayout(v11, Layout);
      DeleteDC(v11);
    }
    DeleteObject(CompatibleBitmap);
  }
  return PatternBrush;
}

```

## disassembly

```asm
0x18018cb3c  mov     rax, rsp
0x18018cb3f  mov     [rax+8], rbx
0x18018cb43  mov     [rax+20h], rsi
0x18018cb47  mov     [rax+18h], r8d
0x18018cb4b  mov     [rax+10h], edx
0x18018cb4e  push    rdi
0x18018cb4f  push    r12
0x18018cb51  push    r13
0x18018cb53  push    r14
0x18018cb55  push    r15
0x18018cb57  sub     rsp, 50h
0x18018cb5b  mov     r8d, [rsp+78h+cy]; cy
0x18018cb63  mov     edx, r9d; cx
0x18018cb66  mov     r13d, r9d
0x18018cb69  mov     r14, rcx
0x18018cb6c  xor     r15d, r15d
0x18018cb6f  call    cs:__imp_CreateCompatibleBitmap
0x18018cb75  mov     rsi, rax
0x18018cb78  test    rax, rax
0x18018cb7b  jz      loc_18018CC51
0x18018cb81  mov     rcx, r14; hdc
0x18018cb84  call    cs:__imp_CreateCompatibleDC
0x18018cb8a  mov     rbx, rax
0x18018cb8d  test    rax, rax
0x18018cb90  jz      loc_18018CC48
0x18018cb96  xor     edi, edi
0x18018cb98  cmp     [rsp+78h+arg_28], edi
0x18018cb9f  jz      short loc_18018CBBF
0x18018cba1  mov     rcx, rax; hdc
0x18018cba4  call    cs:__imp_GetLayout
0x18018cbaa  lea     edx, [r15+1]
0x18018cbae  mov     rcx, rbx; hdc
0x18018cbb1  mov     edi, eax
0x18018cbb3  test    dl, al
0x18018cbb5  jz      short loc_18018CBB9
0x18018cbb7  xor     edx, edx; l
0x18018cbb9  call    cs:__imp_SetLayout
0x18018cbbf  mov     rdx, rsi; h
0x18018cbc2  mov     rcx, rbx; hdc
0x18018cbc5  call    cs:__imp_SelectObject
0x18018cbcb  mov     r12, rax
0x18018cbce  test    rax, rax
0x18018cbd1  jz      short loc_18018CC2A
0x18018cbd3  mov     eax, [rsp+78h+arg_10]
0x18018cbda  mov     r9d, r13d; cx
0x18018cbdd  mov     [rsp+78h+rop], 0CC0020h; rop
0x18018cbe5  xor     r8d, r8d; y
0x18018cbe8  mov     [rsp+78h+y1], eax; y1
0x18018cbec  xor     edx, edx; x
0x18018cbee  mov     eax, [rsp+78h+arg_8]
0x18018cbf5  mov     rcx, rbx; hdc
0x18018cbf8  mov     [rsp+78h+x1], eax; x1
0x18018cbfc  mov     eax, [rsp+78h+cy]
0x18018cc03  mov     [rsp+78h+hdcSrc], r14; hdcSrc
0x18018cc08  mov     [rsp+78h+var_58], eax; cy
0x18018cc0c  call    cs:__imp_BitBlt
0x18018cc12  mov     rdx, r12; h
0x18018cc15  mov     rcx, rbx; hdc
0x18018cc18  call    cs:__imp_SelectObject
0x18018cc1e  mov     rcx, rsi; hbm
0x18018cc21  call    cs:__imp_CreatePatternBrush
0x18018cc27  mov     r15, rax
0x18018cc2a  cmp     [rsp+78h+arg_28], 0
0x18018cc32  jz      short loc_18018CC3F
0x18018cc34  mov     edx, edi; l
0x18018cc36  mov     rcx, rbx; hdc
0x18018cc39  call    cs:__imp_SetLayout
0x18018cc3f  mov     rcx, rbx; hdc
0x18018cc42  call    cs:__imp_DeleteDC
0x18018cc48  mov     rcx, rsi; ho
0x18018cc4b  call    cs:__imp_DeleteObject
0x18018cc51  lea     r11, [rsp+78h+var_28]
0x18018cc56  mov     rax, r15
0x18018cc59  mov     rbx, [r11+30h]
0x18018cc5d  mov     rsi, [r11+48h]
0x18018cc61  mov     rsp, r11
0x18018cc64  pop     r15
0x18018cc66  pop     r14
0x18018cc68  pop     r13
0x18018cc6a  pop     r12
0x18018cc6c  pop     rdi
0x18018cc6d  retn
```
