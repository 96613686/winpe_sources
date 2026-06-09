# CUspShapingDrawingSurface::~CUspShapingDrawingSurface(void)

- ea: `0x18004140c`
- end: `0x180041470`
- name: `??1CUspShapingDrawingSurface@@QEAA@XZ`
- size: `100`
- prototype: `void __fastcall(CUspShapingDrawingSurface *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180014710`
- `0x180015190`

## callees

- `0x18004140c`

## import_xrefs

- `GDI32!SelectObject` at `0x180041444`
- `GDI32!SelectObject` at `0x18004145e`
- `GDI32!SelectObject` at `0x180041444`
- `GDI32!SelectObject` at `0x18004145e`
- `GDI32!DeleteObject` at `0x18004144e`
- `GDI32!DeleteObject` at `0x180041468`
- `GDI32!DeleteObject` at `0x18004144e`
- `GDI32!DeleteObject` at `0x180041468`

## pseudocode

```c
void __fastcall CUspShapingDrawingSurface::~CUspShapingDrawingSurface(CUspShapingDrawingSurface *this)
{
  bool v1; // zf

  v1 = *((_QWORD *)this + 4) == 0;
  *(_QWORD *)this = &CUspShapingDrawingSurface::`vftable';
  if ( !v1 )
  {
    SelectObject(*((HDC *)this + 1), *((HGDIOBJ *)this + 5));
    DeleteObject(*((HGDIOBJ *)this + 4));
  }
  if ( *((_QWORD *)this + 6) )
  {
    SelectObject(*((HDC *)this + 1), *((HGDIOBJ *)this + 7));
    DeleteObject(*((HGDIOBJ *)this + 6));
  }
}

```

## disassembly

```asm
0x18004140c  mov     [rsp+arg_0], rbx
0x180041411  push    rdi
0x180041412  sub     rsp, 20h
0x180041416  cmp     qword ptr [rcx+20h], 0
0x18004141b  lea     rax, ??_7CUspShapingDrawingSurface@@6B@; const CUspShapingDrawingSurface::`vftable'
0x180041422  mov     [rcx], rax
0x180041425  mov     rbx, rcx
0x180041428  jnz     short loc_18004143C
0x18004142a  cmp     qword ptr [rbx+30h], 0
0x18004142f  jnz     short loc_180041456
0x180041431  mov     rbx, [rsp+28h+arg_0]
0x180041436  add     rsp, 20h
0x18004143a  pop     rdi
0x18004143b  retn
0x18004143c  mov     rdx, [rcx+28h]; h
0x180041440  mov     rcx, [rcx+8]; hdc
0x180041444  call    cs:__imp_SelectObject
0x18004144a  mov     rcx, [rbx+20h]; ho
0x18004144e  call    cs:__imp_DeleteObject
0x180041454  jmp     short loc_18004142A
0x180041456  mov     rdx, [rbx+38h]; h
0x18004145a  mov     rcx, [rbx+8]; hdc
0x18004145e  call    cs:__imp_SelectObject
0x180041464  mov     rcx, [rbx+30h]; ho
0x180041468  call    cs:__imp_DeleteObject
0x18004146e  jmp     short loc_180041431
```
