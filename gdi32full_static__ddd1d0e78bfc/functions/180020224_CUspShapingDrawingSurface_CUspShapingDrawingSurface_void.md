# CUspShapingDrawingSurface::~CUspShapingDrawingSurface(void)

- ea: `0x180020224`
- end: `0x1800202a1`
- name: `??1CUspShapingDrawingSurface@@QEAA@XZ`
- size: `125`
- prototype: `void __fastcall(CUspShapingDrawingSurface *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180020a90`
- `0x1800215b0`

## callees

- `0x180020224`

## import_xrefs

- `GDI32!SelectObject` at `0x18002025d`
- `GDI32!SelectObject` at `0x180020283`
- `GDI32!SelectObject` at `0x18002025d`
- `GDI32!SelectObject` at `0x180020283`
- `GDI32!DeleteObject` at `0x18002026d`
- `GDI32!DeleteObject` at `0x180020293`
- `GDI32!DeleteObject` at `0x18002026d`
- `GDI32!DeleteObject` at `0x180020293`

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
0x180020224  mov     [rsp+arg_0], rbx
0x180020229  push    rdi
0x18002022a  sub     rsp, 20h
0x18002022e  cmp     qword ptr [rcx+20h], 0
0x180020233  lea     rax, ??_7CUspShapingDrawingSurface@@6B@; const CUspShapingDrawingSurface::`vftable'
0x18002023a  mov     [rcx], rax
0x18002023d  mov     rbx, rcx
0x180020240  jnz     short loc_180020255
0x180020242  cmp     qword ptr [rbx+30h], 0
0x180020247  jnz     short loc_18002027B
0x180020249  mov     rbx, [rsp+28h+arg_0]
0x18002024e  add     rsp, 20h
0x180020252  pop     rdi
0x180020253  retn
0x180020255  mov     rdx, [rcx+28h]; h
0x180020259  mov     rcx, [rcx+8]; hdc
0x18002025d  call    cs:__imp_SelectObject
0x180020264  nop     dword ptr [rax+rax+00h]
0x180020269  mov     rcx, [rbx+20h]; ho
0x18002026d  call    cs:__imp_DeleteObject
0x180020274  nop     dword ptr [rax+rax+00h]
0x180020279  jmp     short loc_180020242
0x18002027b  mov     rdx, [rbx+38h]; h
0x18002027f  mov     rcx, [rbx+8]; hdc
0x180020283  call    cs:__imp_SelectObject
0x18002028a  nop     dword ptr [rax+rax+00h]
0x18002028f  mov     rcx, [rbx+30h]; ho
0x180020293  call    cs:__imp_DeleteObject
0x18002029a  nop     dword ptr [rax+rax+00h]
0x18002029f  jmp     short loc_180020249
```
