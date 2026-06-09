# GpFont::GpFont(HDC__ *,tagLOGFONTA *)

- ea: `0x180035664`
- end: `0x180035709`
- name: `??0GpFont@@QEAA@PEAUHDC__@@PEAUtagLOGFONTA@@@Z`
- size: `165`
- prototype: `GpFont *__fastcall(GpFont *__hidden this, HDC, LOGFONTA *lplf)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800354c0`

## callees

- `0x180034494`
- `0x180035664`

## import_xrefs

- `GDI32!CreateFontIndirectA` at `0x1800356b0`
- `GDI32!CreateFontIndirectA` at `0x1800356b0`
- `GDI32!SelectObject` at `0x1800356c7`
- `GDI32!SelectObject` at `0x1800356ec`
- `GDI32!SelectObject` at `0x1800356c7`
- `GDI32!SelectObject` at `0x1800356ec`
- `GDI32!DeleteObject` at `0x1800356fb`
- `GDI32!DeleteObject` at `0x1800356fb`

## pseudocode

```c
GpFont *__fastcall GpFont::GpFont(GpFont *this, HDC a2, LOGFONTA *lplf)
{
  HFONT FontIndirectA; // rax
  HGDIOBJ v7; // rsi
  HGDIOBJ v8; // rax

  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *(_QWORD *)this = &GpFont::`vftable';
  *((_DWORD *)this + 2) = 1953383985;
  if ( a2 )
  {
    FontIndirectA = CreateFontIndirectA(lplf);
    if ( FontIndirectA )
    {
      v7 = SelectObject(a2, FontIndirectA);
      GpFont::InitializeFromDc(this, a2);
      if ( v7 )
      {
        v8 = SelectObject(a2, v7);
        DeleteObject(v8);
      }
    }
  }
  return this;
}

```

## disassembly

```asm
0x180035664  mov     [rsp+arg_0], rbx
0x180035669  mov     [rsp+arg_8], rsi
0x18003566e  push    rdi
0x18003566f  sub     rsp, 20h
0x180035673  and     qword ptr [rcx+10h], 0
0x180035678  lea     rax, ??_7GpFont@@6B@; const GpFont::`vftable'
0x18003567f  and     qword ptr [rcx+18h], 0
0x180035684  mov     rdi, rdx
0x180035687  mov     [rcx], rax
0x18003568a  mov     rbx, rcx
0x18003568d  mov     dword ptr [rcx+8], 746E4631h
0x180035694  test    rdx, rdx
0x180035697  jnz     short loc_1800356AD
0x180035699  mov     rsi, [rsp+28h+arg_8]
0x18003569e  mov     rax, rbx
0x1800356a1  mov     rbx, [rsp+28h+arg_0]
0x1800356a6  add     rsp, 20h
0x1800356aa  pop     rdi
0x1800356ab  retn
0x1800356ad  mov     rcx, r8; lplf
0x1800356b0  call    cs:__imp_CreateFontIndirectA
0x1800356b7  nop     dword ptr [rax+rax+00h]
0x1800356bc  test    rax, rax
0x1800356bf  jz      short loc_180035699
0x1800356c1  mov     rdx, rax; h
0x1800356c4  mov     rcx, rdi; hdc
0x1800356c7  call    cs:__imp_SelectObject
0x1800356ce  nop     dword ptr [rax+rax+00h]
0x1800356d3  mov     rdx, rdi; HDC
0x1800356d6  mov     rcx, rbx; this
0x1800356d9  mov     rsi, rax
0x1800356dc  call    ?InitializeFromDc@GpFont@@AEAAXPEAUHDC__@@@Z; GpFont::InitializeFromDc(HDC__ *)
0x1800356e1  test    rsi, rsi
0x1800356e4  jz      short loc_180035699
0x1800356e6  mov     rdx, rsi; h
0x1800356e9  mov     rcx, rdi; hdc
0x1800356ec  call    cs:__imp_SelectObject
0x1800356f3  nop     dword ptr [rax+rax+00h]
0x1800356f8  mov     rcx, rax; ho
0x1800356fb  call    cs:__imp_DeleteObject
0x180035702  nop     dword ptr [rax+rax+00h]
0x180035707  jmp     short loc_180035699
```
