# CPalDC::~CPalDC(void)

- ea: `0x18001d570`
- end: `0x18001d5b6`
- name: `??1CPalDC@@QEAA@XZ`
- size: `70`
- prototype: `void __fastcall(CPalDC *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1800124b8`
- `0x18001d040`
- `0x18001ec9c`
- `0x18002cab4`
- `0x180058e00`
- `0x18006ccc0`
- `0x18007695a`

## callees

- `0x18001d570`

## import_xrefs

- `GDI32!DeleteDC` at `0x18001d5aa`
- `GDI32!DeleteDC` at `0x18001d5aa`
- `GDI32!SelectObject` at `0x18001d5a1`
- `GDI32!SelectObject` at `0x18001d5a1`
- `GDI32!SelectPalette` at `0x18001d58f`
- `GDI32!SelectPalette` at `0x18001d58f`

## pseudocode

```c
void __fastcall CPalDC::~CPalDC(HPALETTE *this)
{
  HPALETTE v2; // rcx
  HPALETTE v3; // rdx

  v2 = *this;
  if ( v2 )
  {
    if ( this[1] )
      SelectPalette((HDC)v2, this[2], 0);
    v3 = this[3];
    if ( v3 )
      SelectObject((HDC)*this, v3);
    DeleteDC((HDC)*this);
  }
}

```

## disassembly

```asm
0x18001d570  push    rbx
0x18001d572  sub     rsp, 20h
0x18001d576  mov     rbx, rcx
0x18001d579  mov     rcx, [rcx]; hdc
0x18001d57c  test    rcx, rcx
0x18001d57f  jz      short loc_18001D5B0
0x18001d581  cmp     qword ptr [rbx+8], 0
0x18001d586  jz      short loc_18001D595
0x18001d588  mov     rdx, [rbx+10h]; hPal
0x18001d58c  xor     r8d, r8d; bForceBkgd
0x18001d58f  call    cs:__imp_SelectPalette
0x18001d595  mov     rdx, [rbx+18h]; h
0x18001d599  test    rdx, rdx
0x18001d59c  jz      short loc_18001D5A7
0x18001d59e  mov     rcx, [rbx]; hdc
0x18001d5a1  call    cs:__imp_SelectObject
0x18001d5a7  mov     rcx, [rbx]; hdc
0x18001d5aa  call    cs:__imp_DeleteDC
0x18001d5b0  add     rsp, 20h
0x18001d5b4  pop     rbx
0x18001d5b5  retn
```
