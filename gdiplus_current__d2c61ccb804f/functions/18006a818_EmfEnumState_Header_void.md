# EmfEnumState::Header(void)

- ea: `0x18006a818`
- end: `0x18006a8f8`
- name: `?Header@EmfEnumState@@QEAAXXZ`
- size: `224`
- prototype: `void __fastcall(EmfEnumState *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180068a30`

## callees

- `0x18006a818`
- `0x18006b070`
- `0x180172010`

## import_xrefs

- `GDI32!SelectClipRgn` at `0x18006a8ae`
- `GDI32!SelectClipRgn` at `0x18006a8ae`
- `GDI32!SetBrushOrgEx` at `0x18006a835`
- `GDI32!SetBrushOrgEx` at `0x18006a835`
- `GDI32!SelectObject` at `0x18006a88a`
- `GDI32!SelectObject` at `0x18006a88a`
- `GDI32!SelectPalette` at `0x18006a8e7`
- `GDI32!SelectPalette` at `0x18006a8e7`
- `GDI32!GetCurrentObject` at `0x18006a866`
- `GDI32!GetCurrentObject` at `0x18006a866`
- `GDI32!DeleteObject` at `0x18006a8c1`
- `GDI32!DeleteObject` at `0x18006a8c1`

## pseudocode

```c
void __fastcall EmfEnumState::Header(EmfEnumState *this)
{
  HRGN v2; // rdx
  HPALETTE v3; // rdx
  HFONT CurrentObject; // rax
  HFONT TrueTypeFont; // rax
  HDC v6; // rcx

  SetBrushOrgEx(*((HDC *)this + 2), *((_DWORD *)this + 596), *((_DWORD *)this + 597), 0);
  v2 = (HRGN)*((_QWORD *)this + 297);
  if ( v2 )
  {
    SelectClipRgn(*((HDC *)this + 2), v2);
    DeleteObject(*((HGDIOBJ *)this + 297));
    *((_QWORD *)this + 297) = 0;
  }
  v3 = (HPALETTE)*((_QWORD *)this + 299);
  if ( v3 )
    SelectPalette(*((HDC *)this + 2), v3, 1);
  CurrentObject = (HFONT)GetCurrentObject(*((HDC *)this + 2), 6u);
  TrueTypeFont = CreateTrueTypeFont(CurrentObject);
  if ( TrueTypeFont )
  {
    v6 = (HDC)*((_QWORD *)this + 2);
    *((_QWORD *)this + 8) = TrueTypeFont;
    SelectObject(v6, TrueTypeFont);
  }
  (*(void (__fastcall **)(EmfEnumState *))(*(_QWORD *)this + 24LL))(this);
}

```

## disassembly

```asm
0x18006a818  push    rbx
0x18006a81a  sub     rsp, 20h
0x18006a81e  mov     r8d, [rcx+954h]; y
0x18006a825  mov     rbx, rcx
0x18006a828  mov     edx, [rcx+950h]; x
0x18006a82e  xor     r9d, r9d; lppt
0x18006a831  mov     rcx, [rcx+10h]; hdc
0x18006a835  call    cs:__imp_SetBrushOrgEx
0x18006a83c  nop     dword ptr [rax+rax+00h]
0x18006a841  mov     rdx, [rbx+948h]; hrgn
0x18006a848  test    rdx, rdx
0x18006a84b  jnz     short loc_18006A8AA
0x18006a84d  mov     rdx, [rbx+958h]; hPal
0x18006a854  test    rdx, rdx
0x18006a857  jnz     loc_18006A8DD
0x18006a85d  mov     rcx, [rbx+10h]; hdc
0x18006a861  mov     edx, 6; type
0x18006a866  call    cs:__imp_GetCurrentObject
0x18006a86d  nop     dword ptr [rax+rax+00h]
0x18006a872  mov     rcx, rax; h
0x18006a875  call    ?CreateTrueTypeFont@@YAPEAUHFONT__@@PEAU1@@Z; CreateTrueTypeFont(HFONT__ *)
0x18006a87a  test    rax, rax
0x18006a87d  jz      short loc_18006A896
0x18006a87f  mov     rcx, [rbx+10h]; hdc
0x18006a883  mov     rdx, rax; h
0x18006a886  mov     [rbx+40h], rax
0x18006a88a  call    cs:__imp_SelectObject
0x18006a891  nop     dword ptr [rax+rax+00h]
0x18006a896  mov     rax, [rbx]
0x18006a899  mov     rcx, rbx
0x18006a89c  mov     rax, [rax+18h]
0x18006a8a0  add     rsp, 20h
0x18006a8a4  pop     rbx
0x18006a8a5  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18006a8aa  mov     rcx, [rbx+10h]; hdc
0x18006a8ae  call    cs:__imp_SelectClipRgn
0x18006a8b5  nop     dword ptr [rax+rax+00h]
0x18006a8ba  mov     rcx, [rbx+948h]; ho
0x18006a8c1  call    cs:__imp_DeleteObject
0x18006a8c8  nop     dword ptr [rax+rax+00h]
0x18006a8cd  mov     qword ptr [rbx+948h], 0
0x18006a8d8  jmp     loc_18006A84D
0x18006a8dd  mov     rcx, [rbx+10h]; hdc
0x18006a8e1  mov     r8d, 1; bForceBkgd
0x18006a8e7  call    cs:__imp_SelectPalette
0x18006a8ee  nop     dword ptr [rax+rax+00h]
0x18006a8f3  jmp     loc_18006A85D
```
