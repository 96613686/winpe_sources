# ATL::CAxHostWindow::GetDC(tagRECT const *,ulong,HDC__ * *)

- ea: `0x140010690`
- end: `0x1400107fe`
- name: `?GetDC@CAxHostWindow@ATL@@UEAAJPEBUtagRECT@@KPEAPEAUHDC__@@@Z`
- size: `366`
- prototype: `__int64 __fastcall(ATL::CAxHostWindow *__hidden this, const struct tagRECT *, unsigned int, HDC *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140010690`
- `0x14004ad80`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x140010727`
- `GDI32!CreateCompatibleDC` at `0x140010727`
- `GDI32!CreateCompatibleBitmap` at `0x140010750`
- `GDI32!CreateCompatibleBitmap` at `0x140010750`
- `GDI32!SelectObject` at `0x14001076a`
- `GDI32!SelectObject` at `0x14001076a`
- `GDI32!DeleteDC` at `0x14001078d`
- `GDI32!DeleteDC` at `0x14001078d`
- `GDI32!DeleteObject` at `0x14001077e`
- `GDI32!DeleteObject` at `0x14001079e`
- `GDI32!DeleteObject` at `0x14001077e`
- `GDI32!DeleteObject` at `0x14001079e`
- `USER32!GetDC` at `0x1400106d7`
- `USER32!GetDC` at `0x1400106d7`
- `USER32!FillRect` at `0x1400107c8`
- `USER32!FillRect` at `0x1400107c8`
- `USER32!GetClientRect` at `0x14001070e`
- `USER32!GetClientRect` at `0x14001070e`

## pseudocode

```c
__int64 __fastcall ATL::CAxHostWindow::GetDC(HWND *this, const struct tagRECT *a2, char a3, HDC *a4)
{
  HDC DC; // rax
  HWND v9; // rcx
  HDC CompatibleDC; // rdi
  HBITMAP CompatibleBitmap; // rax
  HBITMAP v12; // r14
  HDC v13; // rcx
  HGDIOBJ v14; // rax
  tagRECT Rect; // [rsp+20h] [rbp-38h] BYREF

  if ( !a4 )
    return 2147500035LL;
  if ( *((_BYTE *)this + 96) )
  {
    DC = GetDC(*(this - 10));
    *a4 = DC;
    if ( DC )
    {
      *((_BYTE *)this + 96) = 0;
      if ( (a3 & 1) != 0 )
        return 0;
      v9 = *(this - 10);
      Rect = 0;
      GetClientRect(v9, &Rect);
      if ( (a3 & 4) != 0 )
      {
        CompatibleDC = CreateCompatibleDC(*a4);
        if ( CompatibleDC )
        {
          CompatibleBitmap = CreateCompatibleBitmap(*a4, Rect.right - Rect.left, Rect.bottom - Rect.top);
          v12 = CompatibleBitmap;
          v13 = CompatibleDC;
          if ( !CompatibleBitmap )
          {
LABEL_11:
            DeleteDC(v13);
            goto LABEL_13;
          }
          v14 = SelectObject(CompatibleDC, CompatibleBitmap);
          if ( !v14 )
          {
            DeleteObject(v12);
            v13 = CompatibleDC;
            goto LABEL_11;
          }
          DeleteObject(v14);
          this[11] = (HWND)*a4;
          *a4 = CompatibleDC;
        }
      }
LABEL_13:
      if ( (a3 & 2) != 0 )
        FillRect(*a4, &Rect, (HBRUSH)6);
      return 0;
    }
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x140010690  mov     [rsp+arg_8], rbx
0x140010695  mov     [rsp+arg_10], rbp
0x14001069a  push    rsi
0x14001069b  push    rdi
0x14001069c  push    r14
0x14001069e  sub     rsp, 40h
0x1400106a2  mov     rax, cs:__security_cookie
0x1400106a9  xor     rax, rsp
0x1400106ac  mov     [rsp+58h+var_28], rax
0x1400106b1  mov     rbx, r9
0x1400106b4  mov     ebp, r8d
0x1400106b7  mov     rsi, rcx
0x1400106ba  test    r9, r9
0x1400106bd  jnz     short loc_1400106C9
0x1400106bf  mov     eax, 80004003h
0x1400106c4  jmp     loc_1400107DD
0x1400106c9  cmp     byte ptr [rcx+60h], 0
0x1400106cd  jz      loc_1400107D8
0x1400106d3  mov     rcx, [rcx-50h]; hWnd
0x1400106d7  call    cs:__imp_GetDC
0x1400106de  nop     dword ptr [rax+rax+00h]
0x1400106e3  mov     [rbx], rax
0x1400106e6  test    rax, rax
0x1400106e9  jz      loc_1400107D8
0x1400106ef  mov     byte ptr [rsi+60h], 0
0x1400106f3  test    bpl, 1
0x1400106f7  jnz     loc_1400107D4
0x1400106fd  mov     rcx, [rsi-50h]; hWnd
0x140010701  lea     rdx, [rsp+58h+Rect]; lpRect
0x140010706  xorps   xmm0, xmm0
0x140010709  movups  xmmword ptr [rsp+58h+Rect.left], xmm0
0x14001070e  call    cs:__imp_GetClientRect
0x140010715  nop     dword ptr [rax+rax+00h]
0x14001071a  test    bpl, 4
0x14001071e  jz      loc_1400107B4
0x140010724  mov     rcx, [rbx]; hdc
0x140010727  call    cs:__imp_CreateCompatibleDC
0x14001072e  nop     dword ptr [rax+rax+00h]
0x140010733  mov     rdi, rax
0x140010736  test    rax, rax
0x140010739  jz      short loc_1400107B4
0x14001073b  mov     r8d, [rsp+58h+Rect.bottom]
0x140010740  mov     edx, [rsp+58h+Rect.right]
0x140010744  sub     r8d, [rsp+58h+Rect.top]; cy
0x140010749  sub     edx, [rsp+58h+Rect.left]; cx
0x14001074d  mov     rcx, [rbx]; hdc
0x140010750  call    cs:__imp_CreateCompatibleBitmap
0x140010757  nop     dword ptr [rax+rax+00h]
0x14001075c  mov     r14, rax
0x14001075f  mov     rcx, rdi; hdc
0x140010762  test    rax, rax
0x140010765  jz      short loc_14001078D
0x140010767  mov     rdx, rax; h
0x14001076a  call    cs:__imp_SelectObject
0x140010771  nop     dword ptr [rax+rax+00h]
0x140010776  test    rax, rax
0x140010779  jnz     short loc_14001079B
0x14001077b  mov     rcx, r14; ho
0x14001077e  call    cs:__imp_DeleteObject
0x140010785  nop     dword ptr [rax+rax+00h]
0x14001078a  mov     rcx, rdi; hdc
0x14001078d  call    cs:__imp_DeleteDC
0x140010794  nop     dword ptr [rax+rax+00h]
0x140010799  jmp     short loc_1400107B4
0x14001079b  mov     rcx, rax; ho
0x14001079e  call    cs:__imp_DeleteObject
0x1400107a5  nop     dword ptr [rax+rax+00h]
0x1400107aa  mov     rax, [rbx]
0x1400107ad  mov     [rsi+58h], rax
0x1400107b1  mov     [rbx], rdi
0x1400107b4  test    bpl, 2
0x1400107b8  jz      short loc_1400107D4
0x1400107ba  mov     rcx, [rbx]; hDC
0x1400107bd  lea     rdx, [rsp+58h+Rect]; lprc
0x1400107c2  mov     r8d, 6; hbr
0x1400107c8  call    cs:__imp_FillRect
0x1400107cf  nop     dword ptr [rax+rax+00h]
0x1400107d4  xor     eax, eax
0x1400107d6  jmp     short loc_1400107DD
0x1400107d8  mov     eax, 80004005h
0x1400107dd  mov     rcx, [rsp+58h+var_28]
0x1400107e2  xor     rcx, rsp; StackCookie
0x1400107e5  call    __security_check_cookie
0x1400107ea  mov     rbx, [rsp+58h+arg_8]
0x1400107ef  mov     rbp, [rsp+58h+arg_10]
0x1400107f4  add     rsp, 40h
0x1400107f8  pop     r14
0x1400107fa  pop     rdi
0x1400107fb  pop     rsi
0x1400107fc  retn
```
