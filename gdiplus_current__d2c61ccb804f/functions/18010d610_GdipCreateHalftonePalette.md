# GdipCreateHalftonePalette

- ea: `0x18010d610`
- end: `0x18010d701`
- name: `GdipCreateHalftonePalette`
- size: `241`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180017b68`
- `0x1800eacb0`
- `0x18010d610`

## import_xrefs

- `USER32!GetDC` at `0x18010d627`
- `USER32!GetDC` at `0x18010d627`
- `USER32!ReleaseDC` at `0x18010d6cb`
- `USER32!ReleaseDC` at `0x18010d6cb`
- `GDI32!GetDeviceCaps` at `0x18010d647`
- `GDI32!GetDeviceCaps` at `0x18010d673`
- `GDI32!GetDeviceCaps` at `0x18010d647`
- `GDI32!GetDeviceCaps` at `0x18010d673`
- `GDI32!GetSystemPaletteEntries` at `0x18010d699`
- `GDI32!GetSystemPaletteEntries` at `0x18010d6ba`
- `GDI32!GetSystemPaletteEntries` at `0x18010d699`
- `GDI32!GetSystemPaletteEntries` at `0x18010d6ba`
- `GDI32!CreatePalette` at `0x18010d6de`
- `GDI32!CreatePalette` at `0x18010d6de`
- `GDI32!GetSystemPaletteUse` at `0x18010d65c`
- `GDI32!GetSystemPaletteUse` at `0x18010d65c`

## pseudocode

```c
HPALETTE GdipCreateHalftonePalette()
{
  HDC DC; // rax
  HDC v1; // rbx
  HPALETTE Palette; // rbx
  char v4; // [rsp+30h] [rbp+8h] BYREF

  FPUStateSaver::FPUStateSaver((FPUStateSaver *)&v4, 1);
  DC = GetDC(0);
  v1 = DC;
  if ( DC )
  {
    if ( (GetDeviceCaps(DC, 38) & 0x100) != 0 && GetSystemPaletteUse(v1) == 1 && GetDeviceCaps(v1, 104) == 256 )
    {
      GetSystemPaletteEntries(v1, 1u, 9u, &pPalEntries);
      GetSystemPaletteEntries(v1, 0xF6u, 3u, &stru_1801AD75C);
    }
    ReleaseDC(0, v1);
  }
  Palette = CreatePalette(&Win9xHalftonePalette);
  FPUStateSaver::~FPUStateSaver((FPUStateSaver *)&v4);
  return Palette;
}

```

## disassembly

```asm
0x18010d610  push    rbx
0x18010d612  sub     rsp, 20h
0x18010d616  mov     edx, 1; int
0x18010d61b  lea     rcx, [rsp+28h+arg_0]; this
0x18010d620  call    ??0FPUStateSaver@@QEAA@H@Z; FPUStateSaver::FPUStateSaver(int)
0x18010d625  xor     ecx, ecx; hWnd
0x18010d627  call    cs:__imp_GetDC
0x18010d62e  nop     dword ptr [rax+rax+00h]
0x18010d633  mov     rbx, rax
0x18010d636  test    rax, rax
0x18010d639  jz      loc_18010D6D7
0x18010d63f  mov     edx, 26h ; '&'; index
0x18010d644  mov     rcx, rax; hdc
0x18010d647  call    cs:__imp_GetDeviceCaps
0x18010d64e  nop     dword ptr [rax+rax+00h]
0x18010d653  bt      eax, 8
0x18010d657  jnb     short loc_18010D6C6
0x18010d659  mov     rcx, rbx; hdc
0x18010d65c  call    cs:__imp_GetSystemPaletteUse
0x18010d663  nop     dword ptr [rax+rax+00h]
0x18010d668  cmp     eax, 1
0x18010d66b  jnz     short loc_18010D6C6
0x18010d66d  lea     edx, [rax+67h]; index
0x18010d670  mov     rcx, rbx; hdc
0x18010d673  call    cs:__imp_GetDeviceCaps
0x18010d67a  nop     dword ptr [rax+rax+00h]
0x18010d67f  cmp     eax, 100h
0x18010d684  jnz     short loc_18010D6C6
0x18010d686  mov     edx, 1; iStart
0x18010d68b  lea     r9, pPalEntries; pPalEntries
0x18010d692  mov     rcx, rbx; hdc
0x18010d695  lea     r8d, [rdx+8]; cEntries
0x18010d699  call    cs:__imp_GetSystemPaletteEntries
0x18010d6a0  nop     dword ptr [rax+rax+00h]
0x18010d6a5  lea     r9, stru_1801AD75C; pPalEntries
0x18010d6ac  mov     edx, 0F6h; iStart
0x18010d6b1  mov     r8d, 3; cEntries
0x18010d6b7  mov     rcx, rbx; hdc
0x18010d6ba  call    cs:__imp_GetSystemPaletteEntries
0x18010d6c1  nop     dword ptr [rax+rax+00h]
0x18010d6c6  mov     rdx, rbx; hDC
0x18010d6c9  xor     ecx, ecx; hWnd
0x18010d6cb  call    cs:__imp_ReleaseDC
0x18010d6d2  nop     dword ptr [rax+rax+00h]
0x18010d6d7  lea     rcx, ?Win9xHalftonePalette@@3UGDIP_LOGPALETTE256@@A; plpal
0x18010d6de  call    cs:__imp_CreatePalette
0x18010d6e5  nop     dword ptr [rax+rax+00h]
0x18010d6ea  lea     rcx, [rsp+28h+arg_0]; this
0x18010d6ef  mov     rbx, rax
0x18010d6f2  call    ??1FPUStateSaver@@QEAA@XZ; FPUStateSaver::~FPUStateSaver(void)
0x18010d6f7  mov     rax, rbx
0x18010d6fa  add     rsp, 20h
0x18010d6fe  pop     rbx
0x18010d6ff  retn
```
