# GpFont::GpFont(HDC__ *,tagLOGFONTW *)

- ea: `0x180005c20`
- end: `0x180005ccb`
- name: `??0GpFont@@QEAA@PEAUHDC__@@PEAUtagLOGFONTW@@@Z`
- size: `171`
- prototype: `GpFont *__fastcall(GpFont *__hidden this, HDC, LOGFONTW *lplf)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180005914`
- `0x180005a80`

## callees

- `0x180005c20`
- `0x18008a244`

## import_xrefs

- `GDI32!CreateFontIndirectW` at `0x180005c72`
- `GDI32!CreateFontIndirectW` at `0x180005c72`
- `GDI32!SelectObject` at `0x180005c89`
- `GDI32!SelectObject` at `0x180005cae`
- `GDI32!SelectObject` at `0x180005c89`
- `GDI32!SelectObject` at `0x180005cae`
- `GDI32!DeleteObject` at `0x180005cbd`
- `GDI32!DeleteObject` at `0x180005cbd`

## pseudocode

```c
GpFont *__fastcall GpFont::GpFont(GpFont *this, HDC a2, LOGFONTW *lplf)
{
  HFONT FontIndirectW; // rax
  HGDIOBJ v7; // rsi
  HGDIOBJ v8; // rax

  *((_QWORD *)this + 2) = 0;
  *(_QWORD *)this = &GpFont::`vftable';
  *((_DWORD *)this + 2) = 1953383985;
  *((_QWORD *)this + 3) = 0;
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
0x180005c20  mov     [rsp+arg_0], rbx
0x180005c25  mov     [rsp+arg_8], rsi
0x180005c2a  push    rdi
0x180005c2b  sub     rsp, 20h
0x180005c2f  mov     qword ptr [rcx+10h], 0
0x180005c37  lea     rax, ??_7GpFont@@6B@; const GpFont::`vftable'
0x180005c3e  mov     [rcx], rax
0x180005c41  mov     rdi, rdx
0x180005c44  mov     dword ptr [rcx+8], 746E4631h
0x180005c4b  mov     rbx, rcx
0x180005c4e  mov     qword ptr [rcx+18h], 0
0x180005c56  test    rdx, rdx
0x180005c59  jnz     short loc_180005C6F
0x180005c5b  mov     rsi, [rsp+28h+arg_8]
0x180005c60  mov     rax, rbx
0x180005c63  mov     rbx, [rsp+28h+arg_0]
0x180005c68  add     rsp, 20h
0x180005c6c  pop     rdi
0x180005c6d  retn
0x180005c6f  mov     rcx, r8; lplf
0x180005c72  call    cs:__imp_CreateFontIndirectW
0x180005c79  nop     dword ptr [rax+rax+00h]
0x180005c7e  test    rax, rax
0x180005c81  jz      short loc_180005C5B
0x180005c83  mov     rdx, rax; h
0x180005c86  mov     rcx, rdi; hdc
0x180005c89  call    cs:__imp_SelectObject
0x180005c90  nop     dword ptr [rax+rax+00h]
0x180005c95  mov     rdx, rdi; HDC
0x180005c98  mov     rcx, rbx; this
0x180005c9b  mov     rsi, rax
0x180005c9e  call    ?InitializeFromDc@GpFont@@AEAAXPEAUHDC__@@@Z; GpFont::InitializeFromDc(HDC__ *)
0x180005ca3  test    rsi, rsi
0x180005ca6  jz      short loc_180005C5B
0x180005ca8  mov     rdx, rsi; h
0x180005cab  mov     rcx, rdi; hdc
0x180005cae  call    cs:__imp_SelectObject
0x180005cb5  nop     dword ptr [rax+rax+00h]
0x180005cba  mov     rcx, rax; ho
0x180005cbd  call    cs:__imp_DeleteObject
0x180005cc4  nop     dword ptr [rax+rax+00h]
0x180005cc9  jmp     short loc_180005C5B
```
