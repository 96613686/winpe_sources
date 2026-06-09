# GdipCreateHalftonePalette

- ea: `0x1800f1ef0`
- end: `0x1800f1fe1`
- name: `GdipCreateHalftonePalette`
- size: `241`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800105b0`
- `0x180065eb0`
- `0x1800f1ef0`

## import_xrefs

- `USER32!GetDC` at `0x1800f1f07`
- `USER32!GetDC` at `0x1800f1f07`
- `USER32!ReleaseDC` at `0x1800f1fab`
- `USER32!ReleaseDC` at `0x1800f1fab`
- `GDI32!GetDeviceCaps` at `0x1800f1f27`
- `GDI32!GetDeviceCaps` at `0x1800f1f53`
- `GDI32!GetDeviceCaps` at `0x1800f1f27`
- `GDI32!GetDeviceCaps` at `0x1800f1f53`
- `GDI32!GetSystemPaletteEntries` at `0x1800f1f79`
- `GDI32!GetSystemPaletteEntries` at `0x1800f1f9a`
- `GDI32!GetSystemPaletteEntries` at `0x1800f1f79`
- `GDI32!GetSystemPaletteEntries` at `0x1800f1f9a`
- `GDI32!CreatePalette` at `0x1800f1fbe`
- `GDI32!CreatePalette` at `0x1800f1fbe`
- `GDI32!GetSystemPaletteUse` at `0x1800f1f3c`
- `GDI32!GetSystemPaletteUse` at `0x1800f1f3c`

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
      GetSystemPaletteEntries(v1, 0xF6u, 3u, &stru_1801B274C);
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
0x1800f1ef0  push    rbx
0x1800f1ef2  sub     rsp, 20h
0x1800f1ef6  mov     edx, 1; int
0x1800f1efb  lea     rcx, [rsp+28h+arg_0]; this
0x1800f1f00  call    ??0FPUStateSaver@@QEAA@H@Z; FPUStateSaver::FPUStateSaver(int)
0x1800f1f05  xor     ecx, ecx; hWnd
0x1800f1f07  call    cs:__imp_GetDC
0x1800f1f0e  nop     dword ptr [rax+rax+00h]
0x1800f1f13  mov     rbx, rax
0x1800f1f16  test    rax, rax
0x1800f1f19  jz      loc_1800F1FB7
0x1800f1f1f  mov     edx, 26h ; '&'; index
0x1800f1f24  mov     rcx, rax; hdc
0x1800f1f27  call    cs:__imp_GetDeviceCaps
0x1800f1f2e  nop     dword ptr [rax+rax+00h]
0x1800f1f33  bt      eax, 8
0x1800f1f37  jnb     short loc_1800F1FA6
0x1800f1f39  mov     rcx, rbx; hdc
0x1800f1f3c  call    cs:__imp_GetSystemPaletteUse
0x1800f1f43  nop     dword ptr [rax+rax+00h]
0x1800f1f48  cmp     eax, 1
0x1800f1f4b  jnz     short loc_1800F1FA6
0x1800f1f4d  lea     edx, [rax+67h]; index
0x1800f1f50  mov     rcx, rbx; hdc
0x1800f1f53  call    cs:__imp_GetDeviceCaps
0x1800f1f5a  nop     dword ptr [rax+rax+00h]
0x1800f1f5f  cmp     eax, 100h
0x1800f1f64  jnz     short loc_1800F1FA6
0x1800f1f66  mov     edx, 1; iStart
0x1800f1f6b  lea     r9, pPalEntries; pPalEntries
0x1800f1f72  mov     rcx, rbx; hdc
0x1800f1f75  lea     r8d, [rdx+8]; cEntries
0x1800f1f79  call    cs:__imp_GetSystemPaletteEntries
0x1800f1f80  nop     dword ptr [rax+rax+00h]
0x1800f1f85  lea     r9, stru_1801B274C; pPalEntries
0x1800f1f8c  mov     edx, 0F6h; iStart
0x1800f1f91  mov     r8d, 3; cEntries
0x1800f1f97  mov     rcx, rbx; hdc
0x1800f1f9a  call    cs:__imp_GetSystemPaletteEntries
0x1800f1fa1  nop     dword ptr [rax+rax+00h]
0x1800f1fa6  mov     rdx, rbx; hDC
0x1800f1fa9  xor     ecx, ecx; hWnd
0x1800f1fab  call    cs:__imp_ReleaseDC
0x1800f1fb2  nop     dword ptr [rax+rax+00h]
0x1800f1fb7  lea     rcx, ?Win9xHalftonePalette@@3UGDIP_LOGPALETTE256@@A; plpal
0x1800f1fbe  call    cs:__imp_CreatePalette
0x1800f1fc5  nop     dword ptr [rax+rax+00h]
0x1800f1fca  lea     rcx, [rsp+28h+arg_0]; this
0x1800f1fcf  mov     rbx, rax
0x1800f1fd2  call    ??1FPUStateSaver@@QEAA@XZ; FPUStateSaver::~FPUStateSaver(void)
0x1800f1fd7  mov     rax, rbx
0x1800f1fda  add     rsp, 20h
0x1800f1fde  pop     rbx
0x1800f1fdf  retn
```
