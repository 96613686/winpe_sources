# CBBar::RenderBorder(HDC__ *,tagRECT *)

- ea: `0x180506edc`
- end: `0x180506fea`
- name: `?RenderBorder@CBBar@@AEAAXPEAUHDC__@@PEAUtagRECT@@@Z`
- size: `270`
- prototype: `void(CBBar *__hidden this, HDC, struct tagRECT *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800c76f0`

## callees

- `0x18002a334`
- `0x180039ce4`
- `0x180506edc`

## import_xrefs

- `GDI32!DeleteObject` at `0x180506f96`
- `GDI32!DeleteObject` at `0x180506f96`
- `GDI32!SelectObject` at `0x180506f18`
- `GDI32!SelectObject` at `0x180506f8d`
- `GDI32!SelectObject` at `0x180506f18`
- `GDI32!SelectObject` at `0x180506f8d`
- `GDI32!MoveToEx` at `0x180506f2d`
- `GDI32!MoveToEx` at `0x180506f67`
- `GDI32!MoveToEx` at `0x180506f2d`
- `GDI32!MoveToEx` at `0x180506f67`
- `GDI32!LineTo` at `0x180506f3f`
- `GDI32!LineTo` at `0x180506f52`
- `GDI32!LineTo` at `0x180506f7c`
- `GDI32!LineTo` at `0x180506f3f`
- `GDI32!LineTo` at `0x180506f52`
- `GDI32!LineTo` at `0x180506f7c`
- `GDI32!CreatePen` at `0x180506f00`
- `GDI32!CreatePen` at `0x180506f00`
- `USER32!GetSysColor` at `0x180506ef0`
- `USER32!GetSysColor` at `0x180506ef0`

## pseudocode

```c
void __fastcall CBBar::RenderBorder(CBBar *this, HDC a2, struct tagRECT *a3)
{
  COLORREF SysColor; // eax
  HPEN Pen; // rax
  HPEN v7; // rbx
  HGDIOBJ v8; // rbp
  unsigned int CurrentThreadActivityIdPrefix; // eax

  SysColor = GetSysColor(8);
  Pen = CreatePen(0, 1, SysColor);
  v7 = Pen;
  if ( Pen )
  {
    v8 = SelectObject(a2, Pen);
    MoveToEx(a2, a3->left, a3->top, 0);
    LineTo(a2, a3->left, a3->bottom - 1);
    LineTo(a2, a3->right, a3->bottom - 1);
    MoveToEx(a2, a3->right - 1, a3->top, 0);
    LineTo(a2, a3->right - 1, a3->bottom - 1);
    if ( v8 )
      SelectObject(a2, v8);
    DeleteObject(v7);
  }
  else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
         && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      120,
      WPP_64713da2303033df4cd82e061e871de1_Traceguids,
      CurrentThreadActivityIdPrefix);
  }
}

```

## disassembly

```asm
0x180506edc  push    rbx
0x180506ede  push    rbp
0x180506edf  push    rsi
0x180506ee0  push    rdi
0x180506ee1  sub     rsp, 28h
0x180506ee5  mov     ecx, 8; nIndex
0x180506eea  mov     rsi, r8
0x180506eed  mov     rdi, rdx
0x180506ef0  call    cs:__imp_GetSysColor
0x180506ef6  mov     edx, 1; cWidth
0x180506efb  xor     ecx, ecx; iStyle
0x180506efd  mov     r8d, eax; color
0x180506f00  call    cs:__imp_CreatePen
0x180506f06  mov     rbx, rax
0x180506f09  test    rax, rax
0x180506f0c  jz      loc_180506F9E
0x180506f12  mov     rdx, rax; h
0x180506f15  mov     rcx, rdi; hdc
0x180506f18  call    cs:__imp_SelectObject
0x180506f1e  mov     r8d, [rsi+4]; y
0x180506f22  xor     r9d, r9d; lppt
0x180506f25  mov     edx, [rsi]; x
0x180506f27  mov     rcx, rdi; hdc
0x180506f2a  mov     rbp, rax
0x180506f2d  call    cs:__imp_MoveToEx
0x180506f33  mov     r8d, [rsi+0Ch]
0x180506f37  mov     rcx, rdi; hdc
0x180506f3a  mov     edx, [rsi]; x
0x180506f3c  dec     r8d; y
0x180506f3f  call    cs:__imp_LineTo
0x180506f45  mov     r8d, [rsi+0Ch]
0x180506f49  mov     rcx, rdi; hdc
0x180506f4c  mov     edx, [rsi+8]; x
0x180506f4f  dec     r8d; y
0x180506f52  call    cs:__imp_LineTo
0x180506f58  mov     edx, [rsi+8]
0x180506f5b  xor     r9d, r9d; lppt
0x180506f5e  mov     r8d, [rsi+4]; y
0x180506f62  dec     edx; x
0x180506f64  mov     rcx, rdi; hdc
0x180506f67  call    cs:__imp_MoveToEx
0x180506f6d  mov     r8d, [rsi+0Ch]
0x180506f71  mov     rcx, rdi; hdc
0x180506f74  mov     edx, [rsi+8]
0x180506f77  dec     r8d; y
0x180506f7a  dec     edx; x
0x180506f7c  call    cs:__imp_LineTo
0x180506f82  test    rbp, rbp
0x180506f85  jz      short loc_180506F93
0x180506f87  mov     rdx, rbp; h
0x180506f8a  mov     rcx, rdi; hdc
0x180506f8d  call    cs:__imp_SelectObject
0x180506f93  mov     rcx, rbx; ho
0x180506f96  call    cs:__imp_DeleteObject
0x180506f9c  jmp     short loc_180506FE1
0x180506f9e  mov     rax, cs:WPP_GLOBAL_Control
0x180506fa5  lea     rcx, WPP_GLOBAL_Control
0x180506fac  cmp     rax, rcx
0x180506faf  jz      short loc_180506FE1
0x180506fb1  test    byte ptr [rax+1Ch], 1
0x180506fb5  jz      short loc_180506FE1
0x180506fb7  cmp     byte ptr [rax+19h], 2
0x180506fbb  jb      short loc_180506FE1
0x180506fbd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180506fc2  mov     rcx, cs:WPP_GLOBAL_Control
0x180506fc9  lea     r8, WPP_64713da2303033df4cd82e061e871de1_Traceguids
0x180506fd0  mov     edx, 78h ; 'x'
0x180506fd5  mov     r9d, eax
0x180506fd8  mov     rcx, [rcx+10h]
0x180506fdc  call    WPP_SF_d
0x180506fe1  add     rsp, 28h
0x180506fe5  pop     rdi
0x180506fe6  pop     rsi
0x180506fe7  pop     rbp
0x180506fe8  pop     rbx
0x180506fe9  retn
```
