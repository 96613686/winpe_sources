# RBInitPaletteHack

- ea: `0x18003c184`
- end: `0x18003c1ed`
- name: `RBInitPaletteHack`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18003eff0`

## callees

- `0x18003c184`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x18003c19c`
- `GDI32!CreateCompatibleDC` at `0x18003c19c`
- `GDI32!DeleteObject` at `0x18003c1c6`
- `GDI32!DeleteObject` at `0x18003c1c6`
- `GDI32!GetDeviceCaps` at `0x18003c1b2`
- `GDI32!GetDeviceCaps` at `0x18003c1b2`
- `GDI32!DeleteDC` at `0x18003c1dc`
- `GDI32!DeleteDC` at `0x18003c1dc`
- `GDI32!CreateHalftonePalette` at `0x18003c1cf`
- `GDI32!CreateHalftonePalette` at `0x18003c1cf`

## pseudocode

```c
void __fastcall RBInitPaletteHack(__int64 a1)
{
  HDC CompatibleDC; // rax
  HDC v3; // rbx
  void *v4; // rcx

  if ( (*(_DWORD *)(a1 + 64) & 0x200) == 0 )
  {
    CompatibleDC = CreateCompatibleDC(0);
    v3 = CompatibleDC;
    if ( CompatibleDC )
    {
      if ( GetDeviceCaps(CompatibleDC, 12) <= 8 )
      {
        v4 = *(void **)(a1 + 56);
        if ( v4 )
          DeleteObject(v4);
        *(_QWORD *)(a1 + 56) = CreateHalftonePalette(v3);
      }
      DeleteDC(v3);
    }
  }
}

```

## disassembly

```asm
0x18003c184  mov     [rsp+arg_0], rbx
0x18003c189  push    rdi
0x18003c18a  sub     rsp, 20h
0x18003c18e  test    dword ptr [rcx+40h], 200h
0x18003c195  mov     rdi, rcx
0x18003c198  jnz     short loc_18003C1E2
0x18003c19a  xor     ecx, ecx; hdc
0x18003c19c  call    cs:__imp_CreateCompatibleDC
0x18003c1a2  mov     rbx, rax
0x18003c1a5  test    rax, rax
0x18003c1a8  jz      short loc_18003C1E2
0x18003c1aa  mov     edx, 0Ch; index
0x18003c1af  mov     rcx, rax; hdc
0x18003c1b2  call    cs:__imp_GetDeviceCaps
0x18003c1b8  cmp     eax, 8
0x18003c1bb  jg      short loc_18003C1D9
0x18003c1bd  mov     rcx, [rdi+38h]; ho
0x18003c1c1  test    rcx, rcx
0x18003c1c4  jz      short loc_18003C1CC
0x18003c1c6  call    cs:__imp_DeleteObject
0x18003c1cc  mov     rcx, rbx; hdc
0x18003c1cf  call    cs:__imp_CreateHalftonePalette
0x18003c1d5  mov     [rdi+38h], rax
0x18003c1d9  mov     rcx, rbx; hdc
0x18003c1dc  call    cs:__imp_DeleteDC
0x18003c1e2  mov     rbx, [rsp+28h+arg_0]
0x18003c1e7  add     rsp, 20h
0x18003c1eb  pop     rdi
0x18003c1ec  retn
```
