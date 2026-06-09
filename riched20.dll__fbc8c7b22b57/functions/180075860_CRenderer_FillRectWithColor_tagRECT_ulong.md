# CRenderer::FillRectWithColor(tagRECT *,ulong)

- ea: `0x180075860`
- end: `0x180075914`
- name: `?FillRectWithColor@CRenderer@@QEAAXPEAUtagRECT@@K@Z`
- size: `180`
- prototype: `void(CRenderer *__hidden this, struct tagRECT *, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180075e04`
- `0x180076180`

## callees

- `0x180075860`

## import_xrefs

- `GDI32!DeleteObject` at `0x1800758fd`
- `GDI32!DeleteObject` at `0x1800758fd`
- `GDI32!SelectObject` at `0x1800758a1`
- `GDI32!SelectObject` at `0x1800758ee`
- `GDI32!SelectObject` at `0x1800758a1`
- `GDI32!SelectObject` at `0x1800758ee`
- `GDI32!PatBlt` at `0x1800758d8`
- `GDI32!PatBlt` at `0x1800758d8`
- `GDI32!CreateSolidBrush` at `0x180075883`
- `GDI32!CreateSolidBrush` at `0x180075883`

## pseudocode

```c
void __fastcall CRenderer::FillRectWithColor(CRenderer *this, struct tagRECT *a2, COLORREF a3)
{
  HBRUSH SolidBrush; // rax
  HBRUSH v6; // rsi
  HGDIOBJ v7; // rbx

  if ( (*((_BYTE *)this + 288) & 1) != 0 )
    a3 = *((_DWORD *)this + 57);
  SolidBrush = CreateSolidBrush(a3);
  v6 = SolidBrush;
  if ( SolidBrush )
  {
    v7 = SelectObject(*((HDC *)this + 35), SolidBrush);
    PatBlt(*((HDC *)this + 35), a2->left, a2->top, a2->right - a2->left, a2->bottom - a2->top, 0xF00021u);
    SelectObject(*((HDC *)this + 35), v7);
    DeleteObject(v6);
  }
}

```

## disassembly

```asm
0x180075860  push    rbx
0x180075862  push    rsi
0x180075863  push    rdi
0x180075864  push    r14
0x180075866  sub     rsp, 38h
0x18007586a  test    byte ptr [rcx+120h], 1
0x180075871  mov     r14, rdx
0x180075874  mov     rdi, rcx
0x180075877  jz      short loc_180075880
0x180075879  mov     r8d, [rcx+0E4h]
0x180075880  mov     ecx, r8d; color
0x180075883  call    cs:__imp_CreateSolidBrush
0x18007588a  nop     dword ptr [rax+rax+00h]
0x18007588f  mov     rsi, rax
0x180075892  test    rax, rax
0x180075895  jz      short loc_180075909
0x180075897  mov     rcx, [rdi+118h]; hdc
0x18007589e  mov     rdx, rax; h
0x1800758a1  call    cs:__imp_SelectObject
0x1800758a8  nop     dword ptr [rax+rax+00h]
0x1800758ad  mov     ecx, [r14+0Ch]
0x1800758b1  mov     rbx, rax
0x1800758b4  mov     r8d, [r14+4]; y
0x1800758b8  sub     ecx, r8d
0x1800758bb  mov     r9d, [r14+8]
0x1800758bf  sub     r9d, [r14]; w
0x1800758c2  mov     edx, [r14]; x
0x1800758c5  mov     [rsp+58h+rop], 0F00021h; rop
0x1800758cd  mov     [rsp+58h+h], ecx; h
0x1800758d1  mov     rcx, [rdi+118h]; hdc
0x1800758d8  call    cs:__imp_PatBlt
0x1800758df  nop     dword ptr [rax+rax+00h]
0x1800758e4  mov     rcx, [rdi+118h]; hdc
0x1800758eb  mov     rdx, rbx; h
0x1800758ee  call    cs:__imp_SelectObject
0x1800758f5  nop     dword ptr [rax+rax+00h]
0x1800758fa  mov     rcx, rsi; ho
0x1800758fd  call    cs:__imp_DeleteObject
0x180075904  nop     dword ptr [rax+rax+00h]
0x180075909  add     rsp, 38h
0x18007590d  pop     r14
0x18007590f  pop     rdi
0x180075910  pop     rsi
0x180075911  pop     rbx
0x180075912  retn
```
