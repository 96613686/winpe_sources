# EmfEnumState::Header(void)

- ea: `0x180058058`
- end: `0x180058131`
- name: `?Header@EmfEnumState@@QEAAXXZ`
- size: `217`
- prototype: `void __fastcall(EmfEnumState *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180054990`

## callees

- `0x1800567c0`
- `0x180058058`
- `0x180175010`

## import_xrefs

- `GDI32!SelectClipRgn` at `0x1800580ea`
- `GDI32!SelectClipRgn` at `0x1800580ea`
- `GDI32!SetBrushOrgEx` at `0x180058075`
- `GDI32!SetBrushOrgEx` at `0x180058075`
- `GDI32!SelectObject` at `0x1800580c6`
- `GDI32!SelectObject` at `0x1800580c6`
- `GDI32!SelectPalette` at `0x180058120`
- `GDI32!SelectPalette` at `0x180058120`
- `GDI32!GetCurrentObject` at `0x1800580a2`
- `GDI32!GetCurrentObject` at `0x1800580a2`
- `GDI32!DeleteObject` at `0x1800580fd`
- `GDI32!DeleteObject` at `0x1800580fd`

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
0x180058058  push    rbx
0x18005805a  sub     rsp, 20h
0x18005805e  mov     r8d, [rcx+954h]; y
0x180058065  mov     rbx, rcx
0x180058068  mov     edx, [rcx+950h]; x
0x18005806e  xor     r9d, r9d; lppt
0x180058071  mov     rcx, [rcx+10h]; hdc
0x180058075  call    cs:__imp_SetBrushOrgEx
0x18005807c  nop     dword ptr [rax+rax+00h]
0x180058081  mov     rdx, [rbx+948h]; hrgn
0x180058088  test    rdx, rdx
0x18005808b  jnz     short loc_1800580E6
0x18005808d  mov     rdx, [rbx+958h]; hPal
0x180058094  test    rdx, rdx
0x180058097  jnz     short loc_180058116
0x180058099  mov     rcx, [rbx+10h]; hdc
0x18005809d  mov     edx, 6; type
0x1800580a2  call    cs:__imp_GetCurrentObject
0x1800580a9  nop     dword ptr [rax+rax+00h]
0x1800580ae  mov     rcx, rax; h
0x1800580b1  call    ?CreateTrueTypeFont@@YAPEAUHFONT__@@PEAU1@@Z; CreateTrueTypeFont(HFONT__ *)
0x1800580b6  test    rax, rax
0x1800580b9  jz      short loc_1800580D2
0x1800580bb  mov     rcx, [rbx+10h]; hdc
0x1800580bf  mov     rdx, rax; h
0x1800580c2  mov     [rbx+40h], rax
0x1800580c6  call    cs:__imp_SelectObject
0x1800580cd  nop     dword ptr [rax+rax+00h]
0x1800580d2  mov     rax, [rbx]
0x1800580d5  mov     rcx, rbx
0x1800580d8  mov     rax, [rax+18h]
0x1800580dc  add     rsp, 20h
0x1800580e0  pop     rbx
0x1800580e1  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800580e6  mov     rcx, [rbx+10h]; hdc
0x1800580ea  call    cs:__imp_SelectClipRgn
0x1800580f1  nop     dword ptr [rax+rax+00h]
0x1800580f6  mov     rcx, [rbx+948h]; ho
0x1800580fd  call    cs:__imp_DeleteObject
0x180058104  nop     dword ptr [rax+rax+00h]
0x180058109  and     qword ptr [rbx+948h], 0
0x180058111  jmp     loc_18005808D
0x180058116  mov     rcx, [rbx+10h]; hdc
0x18005811a  mov     r8d, 1; bForceBkgd
0x180058120  call    cs:__imp_SelectPalette
0x180058127  nop     dword ptr [rax+rax+00h]
0x18005812c  jmp     loc_180058099
```
