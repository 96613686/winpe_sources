# GpFont::GpFont(HDC__ *,tagLOGFONTW *)

- ea: `0x180060830`
- end: `0x1800608d5`
- name: `??0GpFont@@QEAA@PEAUHDC__@@PEAUtagLOGFONTW@@@Z`
- size: `165`
- prototype: `GpFont *__fastcall(GpFont *__hidden this, HDC, LOGFONTW *lplf)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800603cc`
- `0x180060690`

## callees

- `0x180034494`
- `0x180060830`

## import_xrefs

- `GDI32!CreateFontIndirectW` at `0x18006087c`
- `GDI32!CreateFontIndirectW` at `0x18006087c`
- `GDI32!SelectObject` at `0x180060893`
- `GDI32!SelectObject` at `0x1800608b8`
- `GDI32!SelectObject` at `0x180060893`
- `GDI32!SelectObject` at `0x1800608b8`
- `GDI32!DeleteObject` at `0x1800608c7`
- `GDI32!DeleteObject` at `0x1800608c7`

## pseudocode

```c
GpFont *__fastcall GpFont::GpFont(GpFont *this, HDC a2, LOGFONTW *lplf)
{
  HFONT FontIndirectW; // rax
  HGDIOBJ v7; // rsi
  HGDIOBJ v8; // rax

  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *(_QWORD *)this = &GpFont::`vftable';
  *((_DWORD *)this + 2) = 1953383985;
  if ( a2 )
  {
    FontIndirectW = CreateFontIndirectW(lplf);
    if ( FontIndirectW )
    {
      v7 = SelectObject(a2, FontIndirectW);
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
0x180060830  mov     [rsp+arg_0], rbx
0x180060835  mov     [rsp+arg_8], rsi
0x18006083a  push    rdi
0x18006083b  sub     rsp, 20h
0x18006083f  and     qword ptr [rcx+10h], 0
0x180060844  lea     rax, ??_7GpFont@@6B@; const GpFont::`vftable'
0x18006084b  and     qword ptr [rcx+18h], 0
0x180060850  mov     rdi, rdx
0x180060853  mov     [rcx], rax
0x180060856  mov     rbx, rcx
0x180060859  mov     dword ptr [rcx+8], 746E4631h
0x180060860  test    rdx, rdx
0x180060863  jnz     short loc_180060879
0x180060865  mov     rsi, [rsp+28h+arg_8]
0x18006086a  mov     rax, rbx
0x18006086d  mov     rbx, [rsp+28h+arg_0]
0x180060872  add     rsp, 20h
0x180060876  pop     rdi
0x180060877  retn
0x180060879  mov     rcx, r8; lplf
0x18006087c  call    cs:__imp_CreateFontIndirectW
0x180060883  nop     dword ptr [rax+rax+00h]
0x180060888  test    rax, rax
0x18006088b  jz      short loc_180060865
0x18006088d  mov     rdx, rax; h
0x180060890  mov     rcx, rdi; hdc
0x180060893  call    cs:__imp_SelectObject
0x18006089a  nop     dword ptr [rax+rax+00h]
0x18006089f  mov     rdx, rdi; HDC
0x1800608a2  mov     rcx, rbx; this
0x1800608a5  mov     rsi, rax
0x1800608a8  call    ?InitializeFromDc@GpFont@@AEAAXPEAUHDC__@@@Z; GpFont::InitializeFromDc(HDC__ *)
0x1800608ad  test    rsi, rsi
0x1800608b0  jz      short loc_180060865
0x1800608b2  mov     rdx, rsi; h
0x1800608b5  mov     rcx, rdi; hdc
0x1800608b8  call    cs:__imp_SelectObject
0x1800608bf  nop     dword ptr [rax+rax+00h]
0x1800608c4  mov     rcx, rax; ho
0x1800608c7  call    cs:__imp_DeleteObject
0x1800608ce  nop     dword ptr [rax+rax+00h]
0x1800608d3  jmp     short loc_180060865
```
