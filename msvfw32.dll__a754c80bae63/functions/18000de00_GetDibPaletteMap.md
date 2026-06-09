# GetDibPaletteMap

- ea: `0x18000de00`
- end: `0x18000df36`
- name: `GetDibPaletteMap`
- size: `310`
- prototype: `__int64 __fastcall(HDC hdc, BITMAPINFO *lpbmi, UINT ColorUse, LPVOID lpvBits)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000df3c`

## callees

- `0x180001d62`
- `0x18000de00`

## import_xrefs

- `GDI32!DeleteObject` at `0x18000deda`
- `GDI32!DeleteObject` at `0x18000deda`
- `GDI32!CreateCompatibleBitmap` at `0x18000de91`
- `GDI32!CreateCompatibleBitmap` at `0x18000de91`
- `GDI32!GetBitmapBits` at `0x18000ded1`
- `GDI32!GetBitmapBits` at `0x18000ded1`
- `GDI32!SetDIBits` at `0x18000dec3`
- `GDI32!SetDIBits` at `0x18000dec3`

## pseudocode

```c
_BOOL8 __fastcall GetDibPaletteMap(HDC hdc, BITMAPINFO *lpbmi, UINT ColorUse, _BYTE *lpvBits)
{
  signed int biClrUsed; // edi
  int v9; // ecx
  LONG biWidth; // r13d
  __int64 v11; // rdx
  HBITMAP CompatibleBitmap; // rbx
  signed int v14; // ecx
  int v15; // edx
  DWORD biSizeImage; // [rsp+40h] [rbp-58h]
  LONG biHeight; // [rsp+A8h] [rbp+10h]

  biClrUsed = lpbmi->bmiHeader.biClrUsed;
  if ( biClrUsed )
  {
    if ( biClrUsed > 256 )
      return 0;
  }
  else
  {
    biClrUsed = 256;
  }
  v9 = 0;
  biWidth = lpbmi->bmiHeader.biWidth;
  biHeight = lpbmi->bmiHeader.biHeight;
  biSizeImage = lpbmi->bmiHeader.biSizeImage;
  if ( biClrUsed <= 0 )
    goto LABEL_8;
  do
  {
    lpvBits[v9] = v9;
    ++v9;
  }
  while ( v9 < biClrUsed );
  if ( v9 < 256 )
  {
LABEL_8:
    v11 = v9;
    do
      ++v9;
    while ( v9 < 256 );
    memset_0(&lpvBits[v11], 0, 256 - (int)v11);
  }
  if ( lpbmi->bmiHeader.biBitCount != 8 )
    return 0;
  CompatibleBitmap = CreateCompatibleBitmap(hdc, 256, 1);
  lpbmi->bmiHeader.biSizeImage = 256;
  lpbmi->bmiHeader.biWidth = 256;
  lpbmi->bmiHeader.biHeight = 1;
  SetDIBits(hdc, CompatibleBitmap, 0, 1u, lpvBits, lpbmi, ColorUse);
  GetBitmapBits(CompatibleBitmap, 256, lpvBits);
  DeleteObject(CompatibleBitmap);
  v14 = 0;
  lpbmi->bmiHeader.biHeight = biHeight;
  lpbmi->bmiHeader.biSizeImage = biSizeImage;
  for ( lpbmi->bmiHeader.biWidth = biWidth; v14 < biClrUsed; ++v14 )
  {
    v15 = (unsigned __int8)lpvBits[v14];
    if ( v15 != v14 )
    {
      if ( v14 != 248 || (_BYTE)v15 != 7 )
        return v14 == biClrUsed;
      lpvBits[248] = -8;
    }
  }
  return v14 == biClrUsed;
}

```

## disassembly

```asm
0x18000de00  push    rbx
0x18000de02  push    rbp
0x18000de03  push    rsi
0x18000de04  push    rdi
0x18000de05  push    r12
0x18000de07  push    r13
0x18000de09  push    r14
0x18000de0b  push    r15
0x18000de0d  sub     rsp, 58h
0x18000de11  mov     edi, [rdx+20h]
0x18000de14  mov     r14, r9
0x18000de17  mov     r12d, r8d
0x18000de1a  mov     rbp, rdx
0x18000de1d  mov     r15, rcx
0x18000de20  mov     esi, 100h
0x18000de25  test    edi, edi
0x18000de27  jz      short loc_18000DE2F
0x18000de29  cmp     edi, esi
0x18000de2b  jg      short loc_18000DE7F
0x18000de2d  jmp     short loc_18000DE31
0x18000de2f  mov     edi, esi
0x18000de31  mov     eax, [rdx+8]
0x18000de34  xor     ecx, ecx
0x18000de36  mov     r13d, [rdx+4]
0x18000de3a  mov     [rsp+98h+arg_8], eax
0x18000de41  mov     eax, [rdx+14h]
0x18000de44  mov     [rsp+98h+var_58], eax
0x18000de48  test    edi, edi
0x18000de4a  jle     short loc_18000DE5D
0x18000de4c  movsxd  rax, ecx
0x18000de4f  mov     [rax+r9], cl
0x18000de53  inc     ecx
0x18000de55  cmp     ecx, edi
0x18000de57  jl      short loc_18000DE4C
0x18000de59  cmp     ecx, esi
0x18000de5b  jge     short loc_18000DE78
0x18000de5d  movsxd  rdx, ecx
0x18000de60  inc     ecx
0x18000de62  cmp     ecx, esi
0x18000de64  jl      short loc_18000DE60
0x18000de66  mov     eax, esi
0x18000de68  lea     rcx, [r9+rdx]; void *
0x18000de6c  sub     eax, edx
0x18000de6e  xor     edx, edx; Val
0x18000de70  movsxd  r8, eax; Size
0x18000de73  call    memset_0
0x18000de78  cmp     word ptr [rbp+0Eh], 8
0x18000de7d  jz      short loc_18000DE86
0x18000de7f  xor     eax, eax
0x18000de81  jmp     loc_18000DF25
0x18000de86  mov     r8d, 1; cy
0x18000de8c  mov     edx, esi; cx
0x18000de8e  mov     rcx, r15; hdc
0x18000de91  call    cs:__imp_CreateCompatibleBitmap
0x18000de97  mov     [rsp+98h+ColorUse], r12d; ColorUse
0x18000de9c  xor     r8d, r8d; start
0x18000de9f  mov     rbx, rax
0x18000dea2  mov     [rsp+98h+lpbmi], rbp; lpbmi
0x18000dea7  mov     eax, 1
0x18000deac  mov     [rbp+14h], esi
0x18000deaf  mov     r9d, eax; cLines
0x18000deb2  mov     [rbp+4], esi
0x18000deb5  mov     rdx, rbx; hbm
0x18000deb8  mov     [rbp+8], eax
0x18000debb  mov     rcx, r15; hdc
0x18000debe  mov     [rsp+98h+lpBits], r14; lpBits
0x18000dec3  call    cs:__imp_SetDIBits
0x18000dec9  mov     r8, r14; lpvBits
0x18000decc  mov     edx, esi; cb
0x18000dece  mov     rcx, rbx; hbit
0x18000ded1  call    cs:__imp_GetBitmapBits
0x18000ded7  mov     rcx, rbx; ho
0x18000deda  call    cs:__imp_DeleteObject
0x18000dee0  mov     eax, [rsp+98h+arg_8]
0x18000dee7  xor     ecx, ecx
0x18000dee9  mov     [rbp+8], eax
0x18000deec  mov     eax, [rsp+98h+var_58]
0x18000def0  mov     [rbp+14h], eax
0x18000def3  mov     [rbp+4], r13d
0x18000def7  test    edi, edi
0x18000def9  jle     short loc_18000DF1E
0x18000defb  movsxd  rax, ecx
0x18000defe  movzx   edx, byte ptr [rax+r14]
0x18000df03  cmp     edx, ecx
0x18000df05  jz      short loc_18000DF18
0x18000df07  cmp     ecx, 0F8h
0x18000df0d  jnz     short loc_18000DF1E
0x18000df0f  cmp     dl, 7
0x18000df12  jnz     short loc_18000DF1E
0x18000df14  mov     [rax+r14], cl
0x18000df18  inc     ecx
0x18000df1a  cmp     ecx, edi
0x18000df1c  jl      short loc_18000DEFB
0x18000df1e  xor     eax, eax
0x18000df20  cmp     ecx, edi
0x18000df22  setz    al
0x18000df25  add     rsp, 58h
0x18000df29  pop     r15
0x18000df2b  pop     r14
0x18000df2d  pop     r13
0x18000df2f  pop     r12
0x18000df31  pop     rdi
0x18000df32  pop     rsi
0x18000df33  pop     rbp
0x18000df34  pop     rbx
0x18000df35  retn
```
