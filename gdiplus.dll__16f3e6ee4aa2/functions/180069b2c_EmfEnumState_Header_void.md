# EmfEnumState::Header(void)

- ea: `0x180069b2c`
- end: `0x180069bde`
- name: `?Header@EmfEnumState@@QEAAXXZ`
- size: `178`
- prototype: `void __fastcall(EmfEnumState *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18006b1b0`

## callees

- `0x180069b2c`
- `0x18006a34c`
- `0x180169010`

## import_xrefs

- `GDI32!SelectClipRgn` at `0x180069bac`
- `GDI32!SelectClipRgn` at `0x180069bac`
- `GDI32!SetBrushOrgEx` at `0x180069b49`
- `GDI32!SetBrushOrgEx` at `0x180069b49`
- `GDI32!SelectObject` at `0x180069b8e`
- `GDI32!SelectObject` at `0x180069b8e`
- `GDI32!SelectPalette` at `0x180069bd6`
- `GDI32!SelectPalette` at `0x180069bd6`
- `GDI32!GetCurrentObject` at `0x180069b70`
- `GDI32!GetCurrentObject` at `0x180069b70`
- `GDI32!DeleteObject` at `0x180069bb9`
- `GDI32!DeleteObject` at `0x180069bb9`

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
0x180069b2c  push    rbx
0x180069b2e  sub     rsp, 20h
0x180069b32  mov     r8d, [rcx+954h]; y
0x180069b39  mov     rbx, rcx
0x180069b3c  mov     edx, [rcx+950h]; x
0x180069b42  xor     r9d, r9d; lppt
0x180069b45  mov     rcx, [rcx+10h]; hdc
0x180069b49  call    cs:__imp_SetBrushOrgEx
0x180069b4f  mov     rdx, [rbx+948h]; hrgn
0x180069b56  test    rdx, rdx
0x180069b59  jnz     short loc_180069BA8
0x180069b5b  mov     rdx, [rbx+958h]; hPal
0x180069b62  test    rdx, rdx
0x180069b65  jnz     short loc_180069BCC
0x180069b67  mov     rcx, [rbx+10h]; hdc
0x180069b6b  mov     edx, 6; type
0x180069b70  call    cs:__imp_GetCurrentObject
0x180069b76  mov     rcx, rax; h
0x180069b79  call    ?CreateTrueTypeFont@@YAPEAUHFONT__@@PEAU1@@Z; CreateTrueTypeFont(HFONT__ *)
0x180069b7e  test    rax, rax
0x180069b81  jz      short loc_180069B94
0x180069b83  mov     rcx, [rbx+10h]; hdc
0x180069b87  mov     rdx, rax; h
0x180069b8a  mov     [rbx+40h], rax
0x180069b8e  call    cs:__imp_SelectObject
0x180069b94  mov     rax, [rbx]
0x180069b97  mov     rcx, rbx
0x180069b9a  mov     rax, [rax+18h]
0x180069b9e  add     rsp, 20h
0x180069ba2  pop     rbx
0x180069ba3  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180069ba8  mov     rcx, [rbx+10h]; hdc
0x180069bac  call    cs:__imp_SelectClipRgn
0x180069bb2  mov     rcx, [rbx+948h]; ho
0x180069bb9  call    cs:__imp_DeleteObject
0x180069bbf  mov     qword ptr [rbx+948h], 0
0x180069bca  jmp     short loc_180069B5B
0x180069bcc  mov     rcx, [rbx+10h]; hdc
0x180069bd0  mov     r8d, 1; bForceBkgd
0x180069bd6  call    cs:__imp_SelectPalette
0x180069bdc  jmp     short loc_180069B67
```
