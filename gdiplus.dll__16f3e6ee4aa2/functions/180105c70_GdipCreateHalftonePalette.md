# GdipCreateHalftonePalette

- ea: `0x180105c70`
- end: `0x180105d2c`
- name: `GdipCreateHalftonePalette`
- size: `188`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180025c0c`
- `0x1800e36d0`
- `0x180105c70`

## import_xrefs

- `USER32!GetDC` at `0x180105c87`
- `USER32!GetDC` at `0x180105c87`
- `USER32!ReleaseDC` at `0x180105d03`
- `USER32!ReleaseDC` at `0x180105d03`
- `GDI32!GetDeviceCaps` at `0x180105c9d`
- `GDI32!GetDeviceCaps` at `0x180105cbd`
- `GDI32!GetDeviceCaps` at `0x180105c9d`
- `GDI32!GetDeviceCaps` at `0x180105cbd`
- `GDI32!GetSystemPaletteEntries` at `0x180105cdd`
- `GDI32!GetSystemPaletteEntries` at `0x180105cf8`
- `GDI32!GetSystemPaletteEntries` at `0x180105cdd`
- `GDI32!GetSystemPaletteEntries` at `0x180105cf8`
- `GDI32!CreatePalette` at `0x180105d10`
- `GDI32!CreatePalette` at `0x180105d10`
- `GDI32!GetSystemPaletteUse` at `0x180105cac`
- `GDI32!GetSystemPaletteUse` at `0x180105cac`

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
      GetSystemPaletteEntries(v1, 0xF6u, 3u, &stru_1801A465C);
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
0x180105c70  push    rbx
0x180105c72  sub     rsp, 20h
0x180105c76  mov     edx, 1; int
0x180105c7b  lea     rcx, [rsp+28h+arg_0]; this
0x180105c80  call    ??0FPUStateSaver@@QEAA@H@Z; FPUStateSaver::FPUStateSaver(int)
0x180105c85  xor     ecx, ecx; hWnd
0x180105c87  call    cs:__imp_GetDC
0x180105c8d  mov     rbx, rax
0x180105c90  test    rax, rax
0x180105c93  jz      short loc_180105D09
0x180105c95  mov     edx, 26h ; '&'; index
0x180105c9a  mov     rcx, rax; hdc
0x180105c9d  call    cs:__imp_GetDeviceCaps
0x180105ca3  bt      eax, 8
0x180105ca7  jnb     short loc_180105CFE
0x180105ca9  mov     rcx, rbx; hdc
0x180105cac  call    cs:__imp_GetSystemPaletteUse
0x180105cb2  cmp     eax, 1
0x180105cb5  jnz     short loc_180105CFE
0x180105cb7  lea     edx, [rax+67h]; index
0x180105cba  mov     rcx, rbx; hdc
0x180105cbd  call    cs:__imp_GetDeviceCaps
0x180105cc3  cmp     eax, 100h
0x180105cc8  jnz     short loc_180105CFE
0x180105cca  mov     edx, 1; iStart
0x180105ccf  lea     r9, pPalEntries; pPalEntries
0x180105cd6  mov     rcx, rbx; hdc
0x180105cd9  lea     r8d, [rdx+8]; cEntries
0x180105cdd  call    cs:__imp_GetSystemPaletteEntries
0x180105ce3  lea     r9, stru_1801A465C; pPalEntries
0x180105cea  mov     edx, 0F6h; iStart
0x180105cef  mov     r8d, 3; cEntries
0x180105cf5  mov     rcx, rbx; hdc
0x180105cf8  call    cs:__imp_GetSystemPaletteEntries
0x180105cfe  mov     rdx, rbx; hDC
0x180105d01  xor     ecx, ecx; hWnd
0x180105d03  call    cs:__imp_ReleaseDC
0x180105d09  lea     rcx, ?Win9xHalftonePalette@@3UGDIP_LOGPALETTE256@@A; plpal
0x180105d10  call    cs:__imp_CreatePalette
0x180105d16  lea     rcx, [rsp+28h+arg_0]; this
0x180105d1b  mov     rbx, rax
0x180105d1e  call    ??1FPUStateSaver@@QEAA@XZ; FPUStateSaver::~FPUStateSaver(void)
0x180105d23  mov     rax, rbx
0x180105d26  add     rsp, 20h
0x180105d2a  pop     rbx
0x180105d2b  retn
```
