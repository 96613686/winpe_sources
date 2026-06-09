# CGhostWindow::PaintGhost(HDC__ *,tagRECT const *)

- ea: `0x180007444`
- end: `0x18000751b`
- name: `?PaintGhost@CGhostWindow@@AEAAXPEAUHDC__@@PEBUtagRECT@@@Z`
- size: `215`
- prototype: `void(CGhostWindow *__hidden this, HDC, const struct tagRECT *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180006bb8`

## callees

- `0x180007444`

## import_xrefs

- `GDI32!BitBlt` at `0x1800074d8`
- `GDI32!BitBlt` at `0x1800074d8`
- `GDI32!SelectObject` at `0x180007499`
- `GDI32!SelectObject` at `0x1800074e6`
- `GDI32!SelectObject` at `0x180007499`
- `GDI32!SelectObject` at `0x1800074e6`
- `GDI32!CreateCompatibleDC` at `0x180007481`
- `GDI32!CreateCompatibleDC` at `0x180007481`
- `GDI32!GetStockObject` at `0x1800074fb`
- `GDI32!GetStockObject` at `0x1800074fb`
- `GDI32!DeleteDC` at `0x1800074ef`
- `GDI32!DeleteDC` at `0x1800074ef`
- `ext-ms-win-ntuser-gui-l1-1-0!FillRect` at `0x18000750a`
- `ext-ms-win-ntuser-gui-l1-1-0!FillRect` at `0x18000750a`

## pseudocode

```c
void __fastcall CGhostWindow::PaintGhost(CGhostWindow *this, HDC a2, const struct tagRECT *a3)
{
  HDC CompatibleDC; // rax
  HDC hdcSrc; // rbp
  HGDIOBJ v8; // rdi
  BOOL v9; // ebx
  HBRUSH StockObject; // rax

  if ( *((_QWORD *)this + 18) )
  {
    if ( !*((_DWORD *)this + 53) )
      return;
    goto LABEL_7;
  }
  if ( !*((_QWORD *)this + 17)
    || (CompatibleDC = CreateCompatibleDC(a2), (hdcSrc = CompatibleDC) == 0)
    || (v8 = SelectObject(CompatibleDC, *((HGDIOBJ *)this + 17)),
        v9 = BitBlt(a2, 0, 0, *((_DWORD *)this + 43), *((_DWORD *)this + 44), hdcSrc, 0, 0, 0xCC0020u),
        SelectObject(hdcSrc, v8),
        DeleteDC(hdcSrc),
        !v9) )
  {
LABEL_7:
    StockObject = (HBRUSH)GetStockObject(0);
    FillRect(a2, a3, StockObject);
  }
}

```

## disassembly

```asm
0x180007444  push    rbx
0x180007446  push    rbp
0x180007447  push    rsi
0x180007448  push    rdi
0x180007449  push    r14
0x18000744b  sub     rsp, 50h
0x18000744f  cmp     qword ptr [rcx+90h], 0
0x180007457  mov     r14, r8
0x18000745a  mov     rsi, rdx
0x18000745d  mov     rbx, rcx
0x180007460  jz      short loc_180007474
0x180007462  cmp     dword ptr [rcx+0D4h], 0
0x180007469  jz      loc_180007510
0x18000746f  jmp     loc_1800074F9
0x180007474  cmp     qword ptr [rcx+88h], 0
0x18000747c  jz      short loc_1800074F9
0x18000747e  mov     rcx, rsi; hdc
0x180007481  call    cs:__imp_CreateCompatibleDC
0x180007487  mov     rbp, rax
0x18000748a  test    rax, rax
0x18000748d  jz      short loc_1800074F9
0x18000748f  mov     rdx, [rbx+88h]; h
0x180007496  mov     rcx, rax; hdc
0x180007499  call    cs:__imp_SelectObject
0x18000749f  mov     ecx, [rbx+0B0h]
0x1800074a5  xor     r8d, r8d; y
0x1800074a8  mov     r9d, [rbx+0ACh]; cx
0x1800074af  xor     edx, edx; x
0x1800074b1  mov     [rsp+78h+rop], 0CC0020h; rop
0x1800074b9  mov     rdi, rax
0x1800074bc  mov     [rsp+78h+y1], 0; y1
0x1800074c4  mov     [rsp+78h+x1], 0; x1
0x1800074cc  mov     [rsp+78h+hdcSrc], rbp; hdcSrc
0x1800074d1  mov     [rsp+78h+cy], ecx; cy
0x1800074d5  mov     rcx, rsi; hdc
0x1800074d8  call    cs:__imp_BitBlt
0x1800074de  mov     rdx, rdi; h
0x1800074e1  mov     rcx, rbp; hdc
0x1800074e4  mov     ebx, eax
0x1800074e6  call    cs:__imp_SelectObject
0x1800074ec  mov     rcx, rbp; hdc
0x1800074ef  call    cs:__imp_DeleteDC
0x1800074f5  test    ebx, ebx
0x1800074f7  jnz     short loc_180007510
0x1800074f9  xor     ecx, ecx; i
0x1800074fb  call    cs:__imp_GetStockObject
0x180007501  mov     rdx, r14; lprc
0x180007504  mov     rcx, rsi; hDC
0x180007507  mov     r8, rax; hbr
0x18000750a  call    cs:__imp_FillRect
0x180007510  add     rsp, 50h
0x180007514  pop     r14
0x180007516  pop     rdi
0x180007517  pop     rsi
0x180007518  pop     rbp
0x180007519  pop     rbx
0x18000751a  retn
```
