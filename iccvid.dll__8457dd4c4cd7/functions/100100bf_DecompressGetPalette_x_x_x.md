# DecompressGetPalette(x,x,x)

- ea: `0x100100bf`
- end: `0x10010142`
- name: `_DecompressGetPalette@12`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x100093a0`

## callees

- `0x1000f82f`
- `0x1000f909`
- `0x100100bf`

## import_xrefs

- `USER32!ReleaseDC` at `0x10010123`
- `USER32!ReleaseDC` at `0x10010123`
- `USER32!GetDC` at `0x10010108`
- `USER32!GetDC` at `0x10010108`

## pseudocode

```c
int __fastcall DecompressGetPalette(int a1, int a2, int a3)
{
  int v3; // ebx
  HDC DC; // eax
  HDC v5; // edi

  if ( !a2 )
    return -2;
  v3 = ((*(_BYTE *)(a2 + 14) & 0x1F) == 8) + 1;
  if ( *(_DWORD *)(a2 + 16) != 1684633187 )
    v3 = 0;
  if ( !v3 )
    return -2;
  if ( !a3 )
    return 1064;
  if ( DecompressedDibType(a3) == -1 )
    return -2;
  if ( *(_WORD *)(a3 + 14) == 8 )
  {
    DC = GetDC(0);
    v5 = DC;
    if ( DC )
    {
      WritePalette(a1, DC, v3, (_DWORD *)a3);
      ReleaseDC(0, v5);
      return 0;
    }
  }
  return -100;
}

```

## disassembly

```asm
0x100100bf  mov     edi, edi
0x100100c1  push    ebp
0x100100c2  mov     ebp, esp
0x100100c4  push    ecx
0x100100c5  mov     [ebp+var_4], ecx
0x100100c8  push    ebx
0x100100c9  push    esi
0x100100ca  push    edi
0x100100cb  test    edx, edx
0x100100cd  jz      short loc_10010138
0x100100cf  mov     al, [edx+0Eh]
0x100100d2  xor     ebx, ebx
0x100100d4  and     al, 1Fh
0x100100d6  cmp     al, 8
0x100100d8  setz    bl
0x100100db  xor     eax, eax
0x100100dd  inc     ebx
0x100100de  cmp     dword ptr [edx+10h], 64697663h
0x100100e5  cmovnz  ebx, eax
0x100100e8  test    ebx, ebx
0x100100ea  jz      short loc_10010138
0x100100ec  mov     esi, [ebp+arg_0]
0x100100ef  test    esi, esi
0x100100f1  jz      short loc_10010131
0x100100f3  mov     ecx, esi
0x100100f5  call    _DecompressedDibType@4; DecompressedDibType(x)
0x100100fa  cmp     eax, 0FFFFFFFFh
0x100100fd  jz      short loc_10010138
0x100100ff  cmp     word ptr [esi+0Eh], 8
0x10010104  jnz     short loc_1001012D
0x10010106  push    0; hWnd
0x10010108  call    ds:__imp__GetDC@4; GetDC(x)
0x1001010e  mov     edi, eax
0x10010110  test    edi, edi
0x10010112  jz      short loc_1001012D
0x10010114  mov     ecx, [ebp+var_4]
0x10010117  mov     edx, edi
0x10010119  push    esi
0x1001011a  push    ebx
0x1001011b  call    _WritePalette@16; WritePalette(x,x,x,x)
0x10010120  push    edi; hDC
0x10010121  push    0; hWnd
0x10010123  call    ds:__imp__ReleaseDC@8; ReleaseDC(x,x)
0x10010129  xor     eax, eax
0x1001012b  jmp     short loc_1001013B
0x1001012d  push    0FFFFFF9Ch
0x1001012f  jmp     short loc_1001013A
0x10010131  mov     eax, 428h
0x10010136  jmp     short loc_1001013B
0x10010138  push    0FFFFFFFEh
0x1001013a  pop     eax
0x1001013b  pop     edi
0x1001013c  pop     esi
0x1001013d  pop     ebx
0x1001013e  leave
0x1001013f  retn    4
```
