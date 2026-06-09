# RdpDWMDirectWindowContext::DrawUnInitializedSurfaceDebugRects(void)

- ea: `0x18000e014`
- end: `0x18000e0e0`
- name: `?DrawUnInitializedSurfaceDebugRects@RdpDWMDirectWindowContext@@IEAAXXZ`
- size: `204`
- prototype: `void __fastcall(RdpDWMDirectWindowContext *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d788`

## callees

- `0x18000e014`

## import_xrefs

- `GDI32!MoveToEx` at `0x18000e04e`
- `GDI32!MoveToEx` at `0x18000e0b2`
- `GDI32!MoveToEx` at `0x18000e04e`
- `GDI32!MoveToEx` at `0x18000e0b2`
- `GDI32!LineTo` at `0x18000e05e`
- `GDI32!LineTo` at `0x18000e06f`
- `GDI32!LineTo` at `0x18000e07f`
- `GDI32!LineTo` at `0x18000e08e`
- `GDI32!LineTo` at `0x18000e09f`
- `GDI32!LineTo` at `0x18000e0c2`
- `GDI32!LineTo` at `0x18000e05e`
- `GDI32!LineTo` at `0x18000e06f`
- `GDI32!LineTo` at `0x18000e07f`
- `GDI32!LineTo` at `0x18000e08e`
- `GDI32!LineTo` at `0x18000e09f`
- `GDI32!LineTo` at `0x18000e0c2`
- `GDI32!SelectObject` at `0x18000e039`
- `GDI32!SelectObject` at `0x18000e0cf`
- `GDI32!SelectObject` at `0x18000e039`
- `GDI32!SelectObject` at `0x18000e0cf`

## pseudocode

```c
void __fastcall RdpDWMDirectWindowContext::DrawUnInitializedSurfaceDebugRects(RdpDWMDirectWindowContext *this)
{
  HGDIOBJ v2; // rbx

  if ( *((_DWORD *)this + 192) )
  {
    v2 = SelectObject(*((HDC *)this + 7), *((HGDIOBJ *)this + 88));
    MoveToEx(*((HDC *)this + 7), 0, 0, 0);
    LineTo(*((HDC *)this + 7), *((_DWORD *)this + 22), 0);
    LineTo(*((HDC *)this + 7), *((_DWORD *)this + 22), *((_DWORD *)this + 23));
    LineTo(*((HDC *)this + 7), 0, *((_DWORD *)this + 23));
    LineTo(*((HDC *)this + 7), 0, 0);
    LineTo(*((HDC *)this + 7), *((_DWORD *)this + 22), *((_DWORD *)this + 23));
    MoveToEx(*((HDC *)this + 7), 0, *((_DWORD *)this + 23), 0);
    LineTo(*((HDC *)this + 7), *((_DWORD *)this + 22), 0);
    SelectObject(*((HDC *)this + 7), v2);
  }
}

```

## disassembly

```asm
0x18000e014  mov     [rsp+arg_0], rbx
0x18000e019  push    rdi
0x18000e01a  sub     rsp, 20h
0x18000e01e  cmp     dword ptr [rcx+300h], 0
0x18000e025  mov     rdi, rcx
0x18000e028  jz      loc_18000E0D5
0x18000e02e  mov     rdx, [rcx+2C0h]; h
0x18000e035  mov     rcx, [rcx+38h]; hdc
0x18000e039  call    cs:__imp_SelectObject
0x18000e03f  mov     rcx, [rdi+38h]; hdc
0x18000e043  xor     r9d, r9d; lppt
0x18000e046  xor     r8d, r8d; y
0x18000e049  xor     edx, edx; x
0x18000e04b  mov     rbx, rax
0x18000e04e  call    cs:__imp_MoveToEx
0x18000e054  mov     edx, [rdi+58h]; x
0x18000e057  xor     r8d, r8d; y
0x18000e05a  mov     rcx, [rdi+38h]; hdc
0x18000e05e  call    cs:__imp_LineTo
0x18000e064  mov     r8d, [rdi+5Ch]; y
0x18000e068  mov     edx, [rdi+58h]; x
0x18000e06b  mov     rcx, [rdi+38h]; hdc
0x18000e06f  call    cs:__imp_LineTo
0x18000e075  mov     r8d, [rdi+5Ch]; y
0x18000e079  xor     edx, edx; x
0x18000e07b  mov     rcx, [rdi+38h]; hdc
0x18000e07f  call    cs:__imp_LineTo
0x18000e085  mov     rcx, [rdi+38h]; hdc
0x18000e089  xor     r8d, r8d; y
0x18000e08c  xor     edx, edx; x
0x18000e08e  call    cs:__imp_LineTo
0x18000e094  mov     r8d, [rdi+5Ch]; y
0x18000e098  mov     edx, [rdi+58h]; x
0x18000e09b  mov     rcx, [rdi+38h]; hdc
0x18000e09f  call    cs:__imp_LineTo
0x18000e0a5  mov     r8d, [rdi+5Ch]; y
0x18000e0a9  xor     r9d, r9d; lppt
0x18000e0ac  mov     rcx, [rdi+38h]; hdc
0x18000e0b0  xor     edx, edx; x
0x18000e0b2  call    cs:__imp_MoveToEx
0x18000e0b8  mov     edx, [rdi+58h]; x
0x18000e0bb  xor     r8d, r8d; y
0x18000e0be  mov     rcx, [rdi+38h]; hdc
0x18000e0c2  call    cs:__imp_LineTo
0x18000e0c8  mov     rcx, [rdi+38h]; hdc
0x18000e0cc  mov     rdx, rbx; h
0x18000e0cf  call    cs:__imp_SelectObject
0x18000e0d5  mov     rbx, [rsp+28h+arg_0]
0x18000e0da  add     rsp, 20h
0x18000e0de  pop     rdi
0x18000e0df  retn
```
