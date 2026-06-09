# GpFont::GpFont(HDC__ *,tagLOGFONTA *)

- ea: `0x180089cd0`
- end: `0x180089d7b`
- name: `??0GpFont@@QEAA@PEAUHDC__@@PEAUtagLOGFONTA@@@Z`
- size: `171`
- prototype: `GpFont *__fastcall(GpFont *__hidden this, HDC, LOGFONTA *lplf)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180089b20`

## callees

- `0x180089cd0`
- `0x18008a244`

## import_xrefs

- `GDI32!CreateFontIndirectA` at `0x180089d22`
- `GDI32!CreateFontIndirectA` at `0x180089d22`
- `GDI32!SelectObject` at `0x180089d39`
- `GDI32!SelectObject` at `0x180089d5e`
- `GDI32!SelectObject` at `0x180089d39`
- `GDI32!SelectObject` at `0x180089d5e`
- `GDI32!DeleteObject` at `0x180089d6d`
- `GDI32!DeleteObject` at `0x180089d6d`

## pseudocode

```c
GpFont *__fastcall GpFont::GpFont(GpFont *this, HDC a2, LOGFONTA *lplf)
{
  HFONT FontIndirectA; // rax
  HGDIOBJ v7; // rsi
  HGDIOBJ v8; // rax

  *((_QWORD *)this + 2) = 0;
  *(_QWORD *)this = &GpFont::`vftable';
  *((_DWORD *)this + 2) = 1953383985;
  *((_QWORD *)this + 3) = 0;
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
0x180089cd0  mov     [rsp+arg_0], rbx
0x180089cd5  mov     [rsp+arg_8], rsi
0x180089cda  push    rdi
0x180089cdb  sub     rsp, 20h
0x180089cdf  mov     qword ptr [rcx+10h], 0
0x180089ce7  lea     rax, ??_7GpFont@@6B@; const GpFont::`vftable'
0x180089cee  mov     [rcx], rax
0x180089cf1  mov     rdi, rdx
0x180089cf4  mov     dword ptr [rcx+8], 746E4631h
0x180089cfb  mov     rbx, rcx
0x180089cfe  mov     qword ptr [rcx+18h], 0
0x180089d06  test    rdx, rdx
0x180089d09  jnz     short loc_180089D1F
0x180089d0b  mov     rsi, [rsp+28h+arg_8]
0x180089d10  mov     rax, rbx
0x180089d13  mov     rbx, [rsp+28h+arg_0]
0x180089d18  add     rsp, 20h
0x180089d1c  pop     rdi
0x180089d1d  retn
0x180089d1f  mov     rcx, r8; lplf
0x180089d22  call    cs:__imp_CreateFontIndirectA
0x180089d29  nop     dword ptr [rax+rax+00h]
0x180089d2e  test    rax, rax
0x180089d31  jz      short loc_180089D0B
0x180089d33  mov     rdx, rax; h
0x180089d36  mov     rcx, rdi; hdc
0x180089d39  call    cs:__imp_SelectObject
0x180089d40  nop     dword ptr [rax+rax+00h]
0x180089d45  mov     rdx, rdi; HDC
0x180089d48  mov     rcx, rbx; this
0x180089d4b  mov     rsi, rax
0x180089d4e  call    ?InitializeFromDc@GpFont@@AEAAXPEAUHDC__@@@Z; GpFont::InitializeFromDc(HDC__ *)
0x180089d53  test    rsi, rsi
0x180089d56  jz      short loc_180089D0B
0x180089d58  mov     rdx, rsi; h
0x180089d5b  mov     rcx, rdi; hdc
0x180089d5e  call    cs:__imp_SelectObject
0x180089d65  nop     dword ptr [rax+rax+00h]
0x180089d6a  mov     rcx, rax; ho
0x180089d6d  call    cs:__imp_DeleteObject
0x180089d74  nop     dword ptr [rax+rax+00h]
0x180089d79  jmp     short loc_180089D0B
```
