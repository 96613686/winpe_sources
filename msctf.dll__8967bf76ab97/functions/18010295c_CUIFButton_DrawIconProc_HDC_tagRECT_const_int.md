# CUIFButton::DrawIconProc(HDC__ *,tagRECT const *,int)

- ea: `0x18010295c`
- end: `0x180102b36`
- name: `?DrawIconProc@CUIFButton@@IEAAXPEAUHDC__@@PEBUtagRECT@@H@Z`
- size: `474`
- prototype: `void(CUIFButton *__hidden this, HDC, const struct tagRECT *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180103a10`

## callees

- `0x1800d9a94`
- `0x18010295c`
- `0x180106a60`

## import_xrefs

- `USER32!DrawIconEx` at `0x180102aaf`
- `USER32!DrawIconEx` at `0x180102aaf`
- `USER32!FillRect` at `0x180102a43`
- `USER32!FillRect` at `0x180102a43`
- `GDI32!DeleteObject` at `0x180102b02`
- `GDI32!DeleteObject` at `0x180102b02`
- `GDI32!CreateCompatibleDC` at `0x1801029b5`
- `GDI32!CreateCompatibleDC` at `0x1801029b5`
- `GDI32!DeleteDC` at `0x180102b0b`
- `GDI32!DeleteDC` at `0x180102b0b`
- `GDI32!SelectObject` at `0x1801029e7`
- `GDI32!SelectObject` at `0x180102abd`
- `GDI32!SelectObject` at `0x1801029e7`
- `GDI32!SelectObject` at `0x180102abd`
- `GDI32!GetStockObject` at `0x180102a32`
- `GDI32!GetStockObject` at `0x180102a32`
- `GDI32!BitBlt` at `0x180102a28`
- `GDI32!BitBlt` at `0x180102a28`
- `GDI32!CreateCompatibleBitmap` at `0x1801029cf`
- `GDI32!CreateCompatibleBitmap` at `0x1801029cf`

## pseudocode

```c
void __fastcall CUIFButton::DrawIconProc(CUIFButton *this, HDC a2, const struct tagRECT *a3, int a4)
{
  LONG right; // edi
  LONG bottom; // esi
  BOOL v7; // r13d
  LONG v8; // edi
  LONG v10; // esi
  HDC CompatibleDC; // rbx
  HBITMAP CompatibleBitmap; // rax
  HBITMAP v14; // rbp
  HBRUSH StockObject; // rax
  HICON v16; // r9
  int (*v17)(HDC, __int64, unsigned __int64, int, int); // r8
  unsigned __int64 cy; // [rsp+20h] [rbp-88h]
  HGDIOBJ h; // [rsp+50h] [rbp-58h]
  RECT x; // [rsp+58h] [rbp-50h] BYREF

  right = a3->right;
  bottom = a3->bottom;
  *(_QWORD *)&x.left = 0;
  v7 = a4 != 0;
  v8 = right - a3->left;
  v10 = bottom - a3->top;
  x.right = v8;
  x.bottom = v10;
  CompatibleDC = CreateCompatibleDC(a2);
  if ( CompatibleDC )
  {
    CompatibleBitmap = CreateCompatibleBitmap(a2, v8, v10);
    v14 = CompatibleBitmap;
    if ( CompatibleBitmap )
    {
      h = SelectObject(CompatibleDC, CompatibleBitmap);
      if ( *((_DWORD *)this + 26) )
      {
        BitBlt(CompatibleDC, x.left, x.top, v8, v10, a2, a3->left, a3->top, 0xCC0020u);
      }
      else
      {
        StockObject = (HBRUSH)GetStockObject(0);
        FillRect(CompatibleDC, &x, StockObject);
      }
      v16 = (HICON)*((_QWORD *)this + 20);
      if ( (*((_DWORD *)this + 21) & 0x100) != 0 )
        DrawIconEx(CompatibleDC, v7 + 2, v7 + 2, v16, v8 - 4, v10 - 4, 0, 0, 3u);
      else
        DrawIconEx(CompatibleDC, (v8 - 16) / 2 + v7, (v10 - 16) / 2 + v7, v16, 16, 16, 0, 0, 3u);
      SelectObject(CompatibleDC, h);
      CUIDrawState(a2, 0, v17, (__int64)v14, cy, a3->left, a3->top, v8, v10, *((_DWORD *)this + 26) != 0 ? 4 : 164);
      DeleteObject(v14);
    }
    DeleteDC(CompatibleDC);
  }
}

```

## disassembly

```asm
0x18010295c  mov     [rsp+arg_18], rbx
0x180102961  push    rbp
0x180102962  push    rsi
0x180102963  push    rdi
0x180102964  push    r12
0x180102966  push    r13
0x180102968  push    r14
0x18010296a  push    r15
0x18010296c  sub     rsp, 70h
0x180102970  mov     rax, cs:__security_cookie
0x180102977  xor     rax, rsp
0x18010297a  mov     [rsp+0A8h+var_40], rax
0x18010297f  mov     edi, [r8+8]
0x180102983  xor     r13d, r13d
0x180102986  mov     esi, [r8+0Ch]
0x18010298a  test    r9d, r9d
0x18010298d  mov     r15, rcx
0x180102990  mov     qword ptr [rsp+0A8h+x], 0
0x180102999  setnz   r13b
0x18010299d  mov     rcx, rdx; hdc
0x1801029a0  sub     edi, [r8]
0x1801029a3  mov     r14, r8
0x1801029a6  sub     esi, [r8+4]
0x1801029aa  mov     r12, rdx
0x1801029ad  mov     [rsp+0A8h+var_48], edi
0x1801029b1  mov     [rsp+0A8h+var_44], esi
0x1801029b5  call    cs:__imp_CreateCompatibleDC
0x1801029bb  mov     rbx, rax
0x1801029be  test    rax, rax
0x1801029c1  jz      loc_180102B11
0x1801029c7  mov     r8d, esi; cy
0x1801029ca  mov     edx, edi; cx
0x1801029cc  mov     rcx, r12; hdc
0x1801029cf  call    cs:__imp_CreateCompatibleBitmap
0x1801029d5  mov     rbp, rax
0x1801029d8  test    rax, rax
0x1801029db  jz      loc_180102B08
0x1801029e1  mov     rdx, rax; h
0x1801029e4  mov     rcx, rbx; hdc
0x1801029e7  call    cs:__imp_SelectObject
0x1801029ed  cmp     dword ptr [r15+68h], 0
0x1801029f2  mov     [rsp+0A8h+h], rax
0x1801029f7  jz      short loc_180102A30
0x1801029f9  mov     ecx, [r14+4]
0x1801029fd  mov     r9d, edi; cx
0x180102a00  mov     r8d, [rsp+0A8h+x+4]; y
0x180102a05  mov     edx, [rsp+0A8h+x]; x
0x180102a09  mov     [rsp+0A8h+rop], 0CC0020h; rop
0x180102a11  mov     [rsp+0A8h+y1], ecx; y1
0x180102a15  mov     ecx, [r14]
0x180102a18  mov     [rsp+0A8h+x1], ecx; x1
0x180102a1c  mov     rcx, rbx; hdc
0x180102a1f  mov     [rsp+0A8h+hdcSrc], r12; hdcSrc
0x180102a24  mov     dword ptr [rsp+0A8h+cy], esi; cy
0x180102a28  call    cs:__imp_BitBlt
0x180102a2e  jmp     short loc_180102A49
0x180102a30  xor     ecx, ecx; i
0x180102a32  call    cs:__imp_GetStockObject
0x180102a38  lea     rdx, [rsp+0A8h+x]; lprc
0x180102a3d  mov     rcx, rbx; hDC
0x180102a40  mov     r8, rax; hbr
0x180102a43  call    cs:__imp_FillRect
0x180102a49  test    dword ptr [r15+54h], 100h
0x180102a51  mov     r9, [r15+0A0h]; hIcon
0x180102a58  mov     [rsp+0A8h+rop], 3; diFlags
0x180102a60  mov     qword ptr [rsp+0A8h+y1], 0; hbrFlickerFreeDraw
0x180102a69  mov     [rsp+0A8h+x1], 0; istepIfAniCur
0x180102a71  jz      short loc_180102A86
0x180102a73  lea     edx, [r13+2]
0x180102a77  lea     eax, [rsi-4]
0x180102a7a  mov     r8d, edx
0x180102a7d  mov     dword ptr [rsp+0A8h+hdcSrc], eax
0x180102a81  lea     ecx, [rdi-4]
0x180102a84  jmp     short loc_180102AA8
0x180102a86  mov     ecx, 2
0x180102a8b  lea     eax, [rsi-10h]
0x180102a8e  cdq
0x180102a8f  idiv    ecx
0x180102a91  lea     r8d, [rax+r13]; yTop
0x180102a95  lea     eax, [rdi-10h]
0x180102a98  cdq
0x180102a99  idiv    ecx
0x180102a9b  mov     ecx, 10h
0x180102aa0  mov     dword ptr [rsp+0A8h+hdcSrc], ecx; cyWidth
0x180102aa4  lea     edx, [rax+r13]; xLeft
0x180102aa8  mov     dword ptr [rsp+0A8h+cy], ecx; unsigned __int64
0x180102aac  mov     rcx, rbx; hdc
0x180102aaf  call    cs:__imp_DrawIconEx
0x180102ab5  mov     rdx, [rsp+0A8h+h]; h
0x180102aba  mov     rcx, rbx; hdc
0x180102abd  call    cs:__imp_SelectObject
0x180102ac3  mov     eax, [r15+68h]
0x180102ac7  mov     r9, rbp; __int64
0x180102aca  neg     eax
0x180102acc  mov     rcx, r12; hdc
0x180102acf  mov     eax, [r14+4]
0x180102ad3  sbb     edx, edx
0x180102ad5  and     edx, 0FFFFFF60h
0x180102adb  add     edx, 0A4h
0x180102ae1  mov     [rsp+0A8h+var_60], edx; unsigned int
0x180102ae5  xor     edx, edx; hbrFore
0x180102ae7  mov     [rsp+0A8h+rop], esi; int
0x180102aeb  mov     [rsp+0A8h+y1], edi; int
0x180102aef  mov     [rsp+0A8h+x1], eax; int
0x180102af3  mov     eax, [r14]
0x180102af6  mov     dword ptr [rsp+0A8h+hdcSrc], eax; int
0x180102afa  call    ?CUIDrawState@@YAHPEAUHDC__@@PEAUHBRUSH__@@P6AH0_J_KHH@Z23HHHHI@Z; CUIDrawState(HDC__ *,HBRUSH__ *,int (*)(HDC__ *,__int64,unsigned __int64,int,int),__int64,unsigned __int64,int,int,int,int,uint)
0x180102aff  mov     rcx, rbp; ho
0x180102b02  call    cs:__imp_DeleteObject
0x180102b08  mov     rcx, rbx; hdc
0x180102b0b  call    cs:__imp_DeleteDC
0x180102b11  mov     rcx, [rsp+0A8h+var_40]
0x180102b16  xor     rcx, rsp; StackCookie
0x180102b19  call    __security_check_cookie
0x180102b1e  mov     rbx, [rsp+0A8h+arg_18]
0x180102b26  add     rsp, 70h
0x180102b2a  pop     r15
0x180102b2c  pop     r14
0x180102b2e  pop     r13
0x180102b30  pop     r12
0x180102b32  pop     rdi
0x180102b33  pop     rsi
0x180102b34  pop     rbp
0x180102b35  retn
```
