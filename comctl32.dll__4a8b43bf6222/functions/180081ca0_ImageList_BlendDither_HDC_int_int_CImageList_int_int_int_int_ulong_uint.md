# ImageList_BlendDither(HDC__ *,int,int,CImageList *,int,int,int,int,ulong,uint)

- ea: `0x180081ca0`
- end: `0x180081da9`
- name: `?ImageList_BlendDither@@YAXPEAUHDC__@@HHPEAVCImageList@@HHHHKI@Z`
- size: `265`
- prototype: `void __usercall(HDC hdc@<rcx>, int@<edx>, int@<r8d>, struct CImageList *@<r9>, int, int, int, int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180081960`

## callees

- `0x180081ca0`

## import_xrefs

- `GDI32!SelectObject` at `0x180081cf4`
- `GDI32!SelectObject` at `0x180081d2c`
- `GDI32!SelectObject` at `0x180081d38`
- `GDI32!SelectObject` at `0x180081d88`
- `GDI32!SelectObject` at `0x180081cf4`
- `GDI32!SelectObject` at `0x180081d2c`
- `GDI32!SelectObject` at `0x180081d38`
- `GDI32!SelectObject` at `0x180081d88`
- `GDI32!BitBlt` at `0x180081d7c`
- `GDI32!BitBlt` at `0x180081d7c`
- `GDI32!DeleteObject` at `0x180081d96`
- `GDI32!DeleteObject` at `0x180081d96`
- `GDI32!CreateSolidBrush` at `0x180081cdc`
- `GDI32!CreateSolidBrush` at `0x180081cdc`
- `GDI32!PatBlt` at `0x180081d20`
- `GDI32!PatBlt` at `0x180081d20`

## pseudocode

```c
void __fastcall ImageList_BlendDither(
        HDC hdc,
        __int64 a2,
        __int64 a3,
        struct CImageList *a4,
        int x1,
        int y1,
        int w,
        int cy,
        COLORREF color)
{
  HGDIOBJ v9; // r15
  HBRUSH SolidBrush; // rbp
  HBRUSH v13; // rdx
  HGDIOBJ v14; // rbx
  HGDIOBJ v15; // rbx

  v9 = g_hbrMonoDither;
  SolidBrush = 0;
  if ( color == -16777216 )
  {
    v13 = g_hbrHighlight;
  }
  else if ( color == -1 || color == *((_DWORD *)a4 + 22) )
  {
    v13 = (HBRUSH)*((_QWORD *)a4 + 12);
  }
  else
  {
    SolidBrush = CreateSolidBrush(color);
    v13 = SolidBrush;
  }
  v14 = SelectObject(hdc, v13);
  PatBlt(hdc, 0, 0, w, cy, 0xF00021u);
  SelectObject(hdc, v14);
  v15 = SelectObject(hdc, v9);
  BitBlt(hdc, 0, 0, w, cy, *((HDC *)a4 + 15), x1, y1, 0xAC0744u);
  SelectObject(hdc, v15);
  if ( SolidBrush )
    DeleteObject(SolidBrush);
}

```

## disassembly

```asm
0x180081ca0  push    rbx
0x180081ca2  push    rbp
0x180081ca3  push    rsi
0x180081ca4  push    rdi
0x180081ca5  push    r14
0x180081ca7  push    r15
0x180081ca9  sub     rsp, 58h
0x180081cad  mov     r15, cs:g_hbrMonoDither
0x180081cb4  mov     r14, rcx
0x180081cb7  mov     ecx, [rsp+88h+color]; color
0x180081cbe  xor     ebp, ebp
0x180081cc0  mov     rsi, r9
0x180081cc3  cmp     ecx, 0FF000000h
0x180081cc9  jz      short loc_180081CEA
0x180081ccb  cmp     ecx, 0FFFFFFFFh
0x180081cce  jz      short loc_180081CD6
0x180081cd0  cmp     ecx, [r9+58h]
0x180081cd4  jnz     short loc_180081CDC
0x180081cd6  mov     rdx, [r9+60h]
0x180081cda  jmp     short loc_180081CF1
0x180081cdc  call    cs:__imp_CreateSolidBrush
0x180081ce2  mov     rbp, rax
0x180081ce5  mov     rdx, rax
0x180081ce8  jmp     short loc_180081CF1
0x180081cea  mov     rdx, cs:g_hbrHighlight; h
0x180081cf1  mov     rcx, r14; hdc
0x180081cf4  call    cs:__imp_SelectObject
0x180081cfa  mov     r9d, [rsp+88h+w]; w
0x180081d02  xor     r8d, r8d; y
0x180081d05  mov     edi, [rsp+88h+cy]
0x180081d0c  xor     edx, edx; x
0x180081d0e  mov     rcx, r14; hdc
0x180081d11  mov     [rsp+88h+rop], 0F00021h; rop
0x180081d19  mov     rbx, rax
0x180081d1c  mov     [rsp+88h+h], edi; h
0x180081d20  call    cs:__imp_PatBlt
0x180081d26  mov     rdx, rbx; h
0x180081d29  mov     rcx, r14; hdc
0x180081d2c  call    cs:__imp_SelectObject
0x180081d32  mov     rdx, r15; h
0x180081d35  mov     rcx, r14; hdc
0x180081d38  call    cs:__imp_SelectObject
0x180081d3e  mov     ecx, [rsp+88h+arg_28]
0x180081d45  xor     r8d, r8d; y
0x180081d48  mov     r9d, [rsp+88h+w]; cx
0x180081d50  xor     edx, edx; x
0x180081d52  mov     [rsp+88h+var_48], 0AC0744h; rop
0x180081d5a  mov     rbx, rax
0x180081d5d  mov     [rsp+88h+y1], ecx; y1
0x180081d61  mov     ecx, [rsp+88h+arg_20]
0x180081d68  mov     [rsp+88h+x1], ecx; x1
0x180081d6c  mov     rcx, [rsi+78h]
0x180081d70  mov     qword ptr [rsp+88h+rop], rcx; hdcSrc
0x180081d75  mov     rcx, r14; hdc
0x180081d78  mov     [rsp+88h+h], edi; cy
0x180081d7c  call    cs:__imp_BitBlt
0x180081d82  mov     rdx, rbx; h
0x180081d85  mov     rcx, r14; hdc
0x180081d88  call    cs:__imp_SelectObject
0x180081d8e  test    rbp, rbp
0x180081d91  jz      short loc_180081D9C
0x180081d93  mov     rcx, rbp; ho
0x180081d96  call    cs:__imp_DeleteObject
0x180081d9c  add     rsp, 58h
0x180081da0  pop     r15
0x180081da2  pop     r14
0x180081da4  pop     rdi
0x180081da5  pop     rsi
0x180081da6  pop     rbp
0x180081da7  pop     rbx
0x180081da8  retn
```
