# CEffect::_InitRunning(HDC__ *,HDC__ * *)

- ea: `0x180162ec0`
- end: `0x180162fb2`
- name: `?_InitRunning@CEffect@@MEAAJPEAUHDC__@@PEAPEAU2@@Z`
- size: `242`
- prototype: `int(CEffect *__hidden this, HDC, HDC *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180114520`
- `0x180162ec0`

## import_xrefs

- `GDI32!DeleteObject` at `0x180162f6c`
- `GDI32!DeleteObject` at `0x180162f7b`
- `GDI32!DeleteObject` at `0x180162f6c`
- `GDI32!DeleteObject` at `0x180162f7b`
- `GDI32!SelectClipRgn` at `0x180162f63`
- `GDI32!SelectClipRgn` at `0x180162f92`
- `GDI32!SelectClipRgn` at `0x180162f63`
- `GDI32!SelectClipRgn` at `0x180162f92`
- `GDI32!CreateRectRgn` at `0x180162f25`
- `GDI32!CreateRectRgn` at `0x180162f25`
- `GDI32!GetClipBox` at `0x180162ef6`
- `GDI32!GetClipBox` at `0x180162ef6`
- `GDI32!GetClipRgn` at `0x180162f3e`
- `GDI32!GetClipRgn` at `0x180162f3e`
- `GDI32!CreateRectRgnIndirect` at `0x180162f4e`
- `GDI32!CreateRectRgnIndirect` at `0x180162f4e`
- `USER32!OffsetRect` at `0x180162f15`
- `USER32!OffsetRect` at `0x180162f15`

## pseudocode

```c
__int64 __fastcall CEffect::_InitRunning(CEffect *this, HDC a2, HDC *a3)
{
  HRGN RectRgn; // rax
  HRGN v5; // rax
  HRGN v6; // rdi
  struct tagRECT rect; // [rsp+20h] [rbp-28h] BYREF

  *a3 = (HDC)*((_QWORD *)this + 8);
  rect = 0;
  if ( !GetClipBox(a2, &rect) )
    goto LABEL_7;
  OffsetRect(&rect, -*((_DWORD *)this + 24), -*((_DWORD *)this + 25));
  RectRgn = CreateRectRgn(0, 0, 0, 0);
  *((_QWORD *)this + 18) = RectRgn;
  if ( !RectRgn )
    goto LABEL_7;
  if ( GetClipRgn(*((HDC *)this + 8), RectRgn) == -1 )
  {
    DeleteObject(*((HGDIOBJ *)this + 18));
    *((_QWORD *)this + 18) = 0;
    goto LABEL_7;
  }
  v5 = CreateRectRgnIndirect(&rect);
  v6 = v5;
  if ( !v5 )
  {
LABEL_7:
    SelectClipRgn(*((HDC *)this + 8), 0);
    return 0;
  }
  SelectClipRgn(*((HDC *)this + 8), v5);
  DeleteObject(v6);
  return 0;
}

```

## disassembly

```asm
0x180162ec0  mov     [rsp+arg_18], rbx
0x180162ec5  push    rdi
0x180162ec6  sub     rsp, 40h
0x180162eca  mov     rax, cs:__security_cookie
0x180162ed1  xor     rax, rsp
0x180162ed4  mov     [rsp+48h+var_18], rax
0x180162ed9  mov     rax, [rcx+40h]
0x180162edd  mov     r9, rdx
0x180162ee0  mov     rbx, rcx
0x180162ee3  mov     [r8], rax
0x180162ee6  xorps   xmm0, xmm0
0x180162ee9  lea     rdx, [rsp+48h+rect]; lprect
0x180162eee  mov     rcx, r9; hdc
0x180162ef1  movups  xmmword ptr [rsp+48h+rect.left], xmm0
0x180162ef6  call    cs:__imp_GetClipBox
0x180162efc  test    eax, eax
0x180162efe  jz      loc_180162F8C
0x180162f04  mov     r8d, [rbx+64h]
0x180162f08  lea     rcx, [rsp+48h+rect]; lprc
0x180162f0d  mov     edx, [rbx+60h]
0x180162f10  neg     r8d; dy
0x180162f13  neg     edx; dx
0x180162f15  call    cs:__imp_OffsetRect
0x180162f1b  xor     r9d, r9d; y2
0x180162f1e  xor     r8d, r8d; x2
0x180162f21  xor     edx, edx; y1
0x180162f23  xor     ecx, ecx; x1
0x180162f25  call    cs:__imp_CreateRectRgn
0x180162f2b  mov     [rbx+90h], rax
0x180162f32  test    rax, rax
0x180162f35  jz      short loc_180162F8C
0x180162f37  mov     rcx, [rbx+40h]; hdc
0x180162f3b  mov     rdx, rax; hrgn
0x180162f3e  call    cs:__imp_GetClipRgn
0x180162f44  cmp     eax, 0FFFFFFFFh
0x180162f47  jz      short loc_180162F74
0x180162f49  lea     rcx, [rsp+48h+rect]; lprect
0x180162f4e  call    cs:__imp_CreateRectRgnIndirect
0x180162f54  mov     rdi, rax
0x180162f57  test    rax, rax
0x180162f5a  jz      short loc_180162F8C
0x180162f5c  mov     rcx, [rbx+40h]; hdc
0x180162f60  mov     rdx, rax; hrgn
0x180162f63  call    cs:__imp_SelectClipRgn
0x180162f69  mov     rcx, rdi; ho
0x180162f6c  call    cs:__imp_DeleteObject
0x180162f72  jmp     short loc_180162F98
0x180162f74  mov     rcx, [rbx+90h]; ho
0x180162f7b  call    cs:__imp_DeleteObject
0x180162f81  mov     qword ptr [rbx+90h], 0
0x180162f8c  mov     rcx, [rbx+40h]; hdc
0x180162f90  xor     edx, edx; hrgn
0x180162f92  call    cs:__imp_SelectClipRgn
0x180162f98  xor     eax, eax
0x180162f9a  mov     rcx, [rsp+48h+var_18]
0x180162f9f  xor     rcx, rsp; StackCookie
0x180162fa2  call    __security_check_cookie
0x180162fa7  mov     rbx, [rsp+48h+arg_18]
0x180162fac  add     rsp, 40h
0x180162fb0  pop     rdi
0x180162fb1  retn
```
