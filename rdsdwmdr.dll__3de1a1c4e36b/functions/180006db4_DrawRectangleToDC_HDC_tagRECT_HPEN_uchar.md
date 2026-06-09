# DrawRectangleToDC(HDC__ *,tagRECT,HPEN__ *,uchar)

- ea: `0x180006db4`
- end: `0x180006eca`
- name: `?DrawRectangleToDC@@YAXPEAUHDC__@@UtagRECT@@PEAUHPEN__@@E@Z`
- size: `278`
- prototype: `void __fastcall(HDC hdc, struct tagRECT *, HPEN, char)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180004480`
- `0x180004728`
- `0x18000df3c`
- `0x18000ea10`

## callees

- `0x180006db4`
- `0x18002b960`

## import_xrefs

- `GDI32!MoveToEx` at `0x180006e4b`
- `GDI32!MoveToEx` at `0x180006e7e`
- `GDI32!MoveToEx` at `0x180006e4b`
- `GDI32!MoveToEx` at `0x180006e7e`
- `GDI32!LineTo` at `0x180006e59`
- `GDI32!LineTo` at `0x180006e8c`
- `GDI32!LineTo` at `0x180006e59`
- `GDI32!LineTo` at `0x180006e8c`
- `GDI32!Polyline` at `0x180006e2e`
- `GDI32!Polyline` at `0x180006e2e`
- `GDI32!SelectObject` at `0x180006e17`
- `GDI32!SelectObject` at `0x180006e9f`
- `GDI32!SelectObject` at `0x180006e17`
- `GDI32!SelectObject` at `0x180006e9f`

## pseudocode

```c
void __fastcall DrawRectangleToDC(HDC hdc, struct tagRECT *a2, HPEN a3, char a4)
{
  LONG left; // r15d
  LONG top; // r14d
  LONG right; // ebp
  LONG bottom; // esi
  HGDIOBJ v10; // r13
  int i; // ebx
  int j; // ebx
  POINT apt; // [rsp+20h] [rbp-68h] BYREF
  LONG v14; // [rsp+28h] [rbp-60h]
  LONG v15; // [rsp+2Ch] [rbp-5Ch]
  LONG v16; // [rsp+30h] [rbp-58h]
  LONG v17; // [rsp+34h] [rbp-54h]
  LONG v18; // [rsp+38h] [rbp-50h]
  LONG v19; // [rsp+3Ch] [rbp-4Ch]
  LONG v20; // [rsp+40h] [rbp-48h]
  LONG v21; // [rsp+44h] [rbp-44h]

  left = a2->left;
  top = a2->top;
  right = a2->right;
  bottom = a2->bottom;
  apt.x = left;
  apt.y = top;
  v14 = right;
  v15 = top;
  v16 = right;
  v17 = bottom;
  v18 = left;
  v19 = bottom;
  v20 = left;
  v21 = top;
  v10 = SelectObject(hdc, a3);
  Polyline(hdc, &apt, 5);
  if ( a4 == 1 )
    goto LABEL_6;
  for ( i = left + 15; i < right; i += 15 )
  {
    MoveToEx(hdc, i, top, 0);
    LineTo(hdc, i, bottom);
  }
  if ( a4 )
  {
LABEL_6:
    for ( j = top + 15; j < bottom; j += 15 )
    {
      MoveToEx(hdc, left, j, 0);
      LineTo(hdc, right, j);
    }
  }
  SelectObject(hdc, v10);
}

```

## disassembly

```asm
0x180006db4  mov     r11, rsp
0x180006db7  mov     [r11+20h], rbx
0x180006dbb  push    rbp
0x180006dbc  push    rsi
0x180006dbd  push    rdi
0x180006dbe  push    r12
0x180006dc0  push    r13
0x180006dc2  push    r14
0x180006dc4  push    r15
0x180006dc6  sub     rsp, 50h
0x180006dca  mov     rax, cs:__security_cookie
0x180006dd1  xor     rax, rsp
0x180006dd4  mov     [rsp+88h+var_40], rax
0x180006dd9  mov     r15d, [rdx]
0x180006ddc  mov     r12b, r9b
0x180006ddf  mov     r14d, [rdx+4]
0x180006de3  mov     rdi, rcx
0x180006de6  mov     ebp, [rdx+8]
0x180006de9  mov     esi, [rdx+0Ch]
0x180006dec  mov     rdx, r8; h
0x180006def  mov     [r11-68h], r15d
0x180006df3  mov     [r11-64h], r14d
0x180006df7  mov     [rsp+88h+var_60], ebp
0x180006dfb  mov     [r11-5Ch], r14d
0x180006dff  mov     [rsp+88h+var_58], ebp
0x180006e03  mov     [rsp+88h+var_54], esi
0x180006e07  mov     [r11-50h], r15d
0x180006e0b  mov     [rsp+88h+var_4C], esi
0x180006e0f  mov     [r11-48h], r15d
0x180006e13  mov     [r11-44h], r14d
0x180006e17  call    cs:__imp_SelectObject
0x180006e1d  mov     r8d, 5; cpt
0x180006e23  lea     rdx, [rsp+88h+apt]; apt
0x180006e28  mov     rcx, rdi; hdc
0x180006e2b  mov     r13, rax
0x180006e2e  call    cs:__imp_Polyline
0x180006e34  cmp     r12b, 1
0x180006e38  jz      short loc_180006E6C
0x180006e3a  lea     ebx, [r15+0Fh]
0x180006e3e  jmp     short loc_180006E62
0x180006e40  xor     r9d, r9d; lppt
0x180006e43  mov     r8d, r14d; y
0x180006e46  mov     edx, ebx; x
0x180006e48  mov     rcx, rdi; hdc
0x180006e4b  call    cs:__imp_MoveToEx
0x180006e51  mov     r8d, esi; y
0x180006e54  mov     edx, ebx; x
0x180006e56  mov     rcx, rdi; hdc
0x180006e59  call    cs:__imp_LineTo
0x180006e5f  add     ebx, 0Fh
0x180006e62  cmp     ebx, ebp
0x180006e64  jl      short loc_180006E40
0x180006e66  cmp     r12b, 1
0x180006e6a  jb      short loc_180006E99
0x180006e6c  lea     ebx, [r14+0Fh]
0x180006e70  jmp     short loc_180006E95
0x180006e72  xor     r9d, r9d; lppt
0x180006e75  mov     r8d, ebx; y
0x180006e78  mov     edx, r15d; x
0x180006e7b  mov     rcx, rdi; hdc
0x180006e7e  call    cs:__imp_MoveToEx
0x180006e84  mov     r8d, ebx; y
0x180006e87  mov     edx, ebp; x
0x180006e89  mov     rcx, rdi; hdc
0x180006e8c  call    cs:__imp_LineTo
0x180006e92  add     ebx, 0Fh
0x180006e95  cmp     ebx, esi
0x180006e97  jl      short loc_180006E72
0x180006e99  mov     rdx, r13; h
0x180006e9c  mov     rcx, rdi; hdc
0x180006e9f  call    cs:__imp_SelectObject
0x180006ea5  mov     rcx, [rsp+88h+var_40]
0x180006eaa  xor     rcx, rsp; StackCookie
0x180006ead  call    __security_check_cookie
0x180006eb2  mov     rbx, [rsp+88h+arg_18]
0x180006eba  add     rsp, 50h
0x180006ebe  pop     r15
0x180006ec0  pop     r14
0x180006ec2  pop     r13
0x180006ec4  pop     r12
0x180006ec6  pop     rdi
0x180006ec7  pop     rsi
0x180006ec8  pop     rbp
0x180006ec9  retn
```
