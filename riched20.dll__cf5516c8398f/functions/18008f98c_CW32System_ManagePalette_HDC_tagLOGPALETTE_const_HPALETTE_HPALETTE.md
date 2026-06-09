# CW32System::ManagePalette(HDC__ *,tagLOGPALETTE const *,HPALETTE__ * &,HPALETTE__ * &)

- ea: `0x18008f98c`
- end: `0x18008fa18`
- name: `?ManagePalette@CW32System@@SAPEAUHPALETTE__@@PEAUHDC__@@PEBUtagLOGPALETTE@@AEAPEAU2@2@Z`
- size: `140`
- prototype: `HPALETTE __fastcall(HDC hdc, LOGPALETTE *plpal, HPALETTE *, HPALETTE *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800208d8`

## callees

- `0x18008f98c`

## import_xrefs

- `GDI32!CreatePalette` at `0x18008f9ad`
- `GDI32!CreatePalette` at `0x18008f9ad`
- `GDI32!DeleteObject` at `0x18008f9f9`
- `GDI32!DeleteObject` at `0x18008f9f9`
- `GDI32!RealizePalette` at `0x18008f9d3`
- `GDI32!RealizePalette` at `0x18008f9f0`
- `GDI32!RealizePalette` at `0x18008f9d3`
- `GDI32!RealizePalette` at `0x18008f9f0`
- `GDI32!SelectPalette` at `0x18008f9c7`
- `GDI32!SelectPalette` at `0x18008f9e7`
- `GDI32!SelectPalette` at `0x18008f9c7`
- `GDI32!SelectPalette` at `0x18008f9e7`

## pseudocode

```c
HPALETTE __fastcall CW32System::ManagePalette(HDC hdc, LOGPALETTE *plpal, HPALETTE *a3, HPALETTE *a4)
{
  HPALETTE Palette; // rax

  if ( *a4 )
  {
    SelectPalette(hdc, *a3, 1);
    RealizePalette(hdc);
    DeleteObject(*a4);
    *a4 = 0;
  }
  else
  {
    Palette = CreatePalette(plpal);
    *a4 = Palette;
    if ( Palette )
    {
      *a3 = SelectPalette(hdc, Palette, 1);
      RealizePalette(hdc);
      return *a4;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18008f98c  mov     [rsp+arg_0], rbx
0x18008f991  mov     [rsp+arg_8], rsi
0x18008f996  push    rdi
0x18008f997  sub     rsp, 20h
0x18008f99b  cmp     qword ptr [r9], 0
0x18008f99f  mov     rbx, r9
0x18008f9a2  mov     rsi, r8
0x18008f9a5  mov     rdi, rcx
0x18008f9a8  jnz     short loc_18008F9DE
0x18008f9aa  mov     rcx, rdx; plpal
0x18008f9ad  call    cs:__imp_CreatePalette
0x18008f9b3  mov     [rbx], rax
0x18008f9b6  test    rax, rax
0x18008f9b9  jz      short loc_18008FA06
0x18008f9bb  mov     r8d, 1; bForceBkgd
0x18008f9c1  mov     rdx, rax; hPal
0x18008f9c4  mov     rcx, rdi; hdc
0x18008f9c7  call    cs:__imp_SelectPalette
0x18008f9cd  mov     rcx, rdi; hdc
0x18008f9d0  mov     [rsi], rax
0x18008f9d3  call    cs:__imp_RealizePalette
0x18008f9d9  mov     rax, [rbx]
0x18008f9dc  jmp     short loc_18008FA08
0x18008f9de  mov     rdx, [rsi]; hPal
0x18008f9e1  mov     r8d, 1; bForceBkgd
0x18008f9e7  call    cs:__imp_SelectPalette
0x18008f9ed  mov     rcx, rdi; hdc
0x18008f9f0  call    cs:__imp_RealizePalette
0x18008f9f6  mov     rcx, [rbx]; ho
0x18008f9f9  call    cs:__imp_DeleteObject
0x18008f9ff  mov     qword ptr [rbx], 0
0x18008fa06  xor     eax, eax
0x18008fa08  mov     rbx, [rsp+28h+arg_0]
0x18008fa0d  mov     rsi, [rsp+28h+arg_8]
0x18008fa12  add     rsp, 20h
0x18008fa16  pop     rdi
0x18008fa17  retn
```
