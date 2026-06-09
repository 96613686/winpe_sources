# DecompressGetPalette

- ea: `0x180002b54`
- end: `0x180002ccc`
- name: `DecompressGetPalette`
- size: `376`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001cc0`

## callees

- `0x180001400`
- `0x1800023bc`
- `0x180002b54`

## import_xrefs

- `GDI32!GetSystemPaletteEntries` at `0x180002bbe`
- `GDI32!GetSystemPaletteEntries` at `0x180002bbe`
- `USER32!ReleaseDC` at `0x180002bd2`
- `USER32!ReleaseDC` at `0x180002bd2`
- `USER32!GetDesktopWindow` at `0x180002b97`
- `USER32!GetDesktopWindow` at `0x180002bc6`
- `USER32!GetDesktopWindow` at `0x180002b97`
- `USER32!GetDesktopWindow` at `0x180002bc6`
- `USER32!GetDC` at `0x180002ba0`
- `USER32!GetDC` at `0x180002ba0`

## pseudocode

```c
__int64 __fastcall DecompressGetPalette(__int64 a1, __int64 a2, int *a3)
{
  __int64 result; // rax
  UINT SystemPaletteEntries; // esi
  HWND DesktopWindow; // rax
  HDC DC; // rax
  HDC v8; // rdi
  HWND v9; // rax
  __int64 v10; // r9
  char *v11; // r8
  int v12; // r10d
  __int64 v13; // rdx
  BYTE peBlue; // al
  int v15; // edx
  __int64 v16; // rcx
  int v17; // r10d
  int v18; // r9d
  __int64 v19; // rdx
  __int64 v20; // rcx
  tagPALETTEENTRY pPalEntries[256]; // [rsp+20h] [rbp-428h] BYREF

  result = DecompressQuery(a1, a2, 0);
  if ( !(_DWORD)result )
  {
    if ( *((_WORD *)a3 + 7) == 8 )
    {
      SystemPaletteEntries = 0;
      DesktopWindow = GetDesktopWindow();
      DC = GetDC(DesktopWindow);
      v8 = DC;
      if ( DC )
      {
        SystemPaletteEntries = GetSystemPaletteEntries(DC, 0, 0x100u, pPalEntries);
        v9 = GetDesktopWindow();
        ReleaseDC(v9, v8);
      }
      a3[9] = 0;
      if ( SystemPaletteEntries )
      {
        v10 = 0;
        v11 = (char *)a3 + *a3;
        a3[8] = 256;
        v12 = 0;
        do
        {
          v13 = v12;
          v12 += 4;
          v11[v13] = pPalEntries[v10].peRed;
          v11[v13 + 1] = pPalEntries[v10].peGreen;
          peBlue = pPalEntries[v10].peBlue;
          v10 = (unsigned int)(v10 + 1);
          v11[v13 + 2] = peBlue;
          v11[v13 + 3] = 0;
        }
        while ( (int)v10 < 10 );
        v15 = 40;
        v16 = 40;
        v17 = 984;
        do
        {
          v15 += 4;
          v11[v16] = *((_BYTE *)PalTable + v16 + 2);
          v11[v16 + 1] = *((_BYTE *)PalTable + v16 + 1);
          v11[v16 + 2] = *((_BYTE *)PalTable + v16);
          v11[v16 + 3] = 0;
          v16 += 4;
        }
        while ( v15 != 984 );
        v18 = 246;
        do
        {
          v19 = v17;
          v17 += 4;
          v20 = (unsigned int)v18++;
          v11[v19] = pPalEntries[v20].peRed;
          v11[v19 + 1] = pPalEntries[v20].peGreen;
          v11[v19 + 2] = pPalEntries[v20].peBlue;
          v11[v19 + 3] = 0;
        }
        while ( v18 < 256 );
      }
      else
      {
        a3[8] = 0;
      }
      return 0;
    }
    else
    {
      return 4294967196LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002b54  push    rbx
0x180002b56  push    rsi
0x180002b57  push    rdi
0x180002b58  sub     rsp, 430h
0x180002b5f  mov     rax, cs:__security_cookie
0x180002b66  xor     rax, rsp
0x180002b69  mov     [rsp+448h+var_28], rax
0x180002b71  mov     rbx, r8
0x180002b74  xor     r8d, r8d
0x180002b77  call    DecompressQuery
0x180002b7c  test    eax, eax
0x180002b7e  jnz     loc_180002CB1
0x180002b84  cmp     word ptr [rbx+0Eh], 8
0x180002b89  jz      short loc_180002B95
0x180002b8b  mov     eax, 0FFFFFF9Ch
0x180002b90  jmp     loc_180002CB1
0x180002b95  xor     esi, esi
0x180002b97  call    cs:__imp_GetDesktopWindow
0x180002b9d  mov     rcx, rax; hWnd
0x180002ba0  call    cs:__imp_GetDC
0x180002ba6  mov     rdi, rax
0x180002ba9  test    rax, rax
0x180002bac  jz      short loc_180002BD8
0x180002bae  lea     r9, [rsp+448h+pPalEntries]; pPalEntries
0x180002bb3  xor     edx, edx; iStart
0x180002bb5  mov     r8d, 100h; cEntries
0x180002bbb  mov     rcx, rax; hdc
0x180002bbe  call    cs:__imp_GetSystemPaletteEntries
0x180002bc4  mov     esi, eax
0x180002bc6  call    cs:__imp_GetDesktopWindow
0x180002bcc  mov     rcx, rax; hWnd
0x180002bcf  mov     rdx, rdi; hDC
0x180002bd2  call    cs:__imp_ReleaseDC
0x180002bd8  mov     dword ptr [rbx+24h], 0
0x180002bdf  test    esi, esi
0x180002be1  jnz     short loc_180002BEB
0x180002be3  mov     [rbx+20h], esi
0x180002be6  jmp     loc_180002CAF
0x180002beb  movsxd  r8, dword ptr [rbx]
0x180002bee  xor     r9d, r9d
0x180002bf1  add     r8, rbx
0x180002bf4  mov     dword ptr [rbx+20h], 100h
0x180002bfb  xor     r10d, r10d
0x180002bfe  mov     al, [rsp+r9*4+448h+pPalEntries.peRed]
0x180002c03  movsxd  rdx, r10d
0x180002c06  add     r10d, 4
0x180002c0a  mov     [rdx+r8], al
0x180002c0e  mov     al, [rsp+r9*4+448h+pPalEntries.peGreen]
0x180002c13  mov     [rdx+r8+1], al
0x180002c18  mov     al, [rsp+r9*4+448h+pPalEntries.peBlue]
0x180002c1d  inc     r9d
0x180002c20  mov     [rdx+r8+2], al
0x180002c25  mov     byte ptr [rdx+r8+3], 0
0x180002c2b  cmp     r9d, 0Ah
0x180002c2f  jl      short loc_180002BFE
0x180002c31  mov     edx, 28h ; '('
0x180002c36  lea     r9, PalTable
0x180002c3d  mov     ecx, edx
0x180002c3f  mov     r10d, 3D8h
0x180002c45  mov     al, [rcx+r9+2]
0x180002c4a  add     edx, 4
0x180002c4d  mov     [r8+rcx], al
0x180002c51  mov     al, [rcx+r9+1]
0x180002c56  mov     [r8+rcx+1], al
0x180002c5b  mov     al, [rcx+r9]
0x180002c5f  mov     [r8+rcx+2], al
0x180002c64  mov     byte ptr [r8+rcx+3], 0
0x180002c6a  lea     rcx, [rcx+4]
0x180002c6e  cmp     edx, r10d
0x180002c71  jnz     short loc_180002C45
0x180002c73  mov     r9d, 0F6h
0x180002c79  movsxd  rdx, r10d
0x180002c7c  add     r10d, 4
0x180002c80  mov     ecx, r9d
0x180002c83  inc     r9d
0x180002c86  mov     al, [rsp+rcx*4+448h+pPalEntries.peRed]
0x180002c8a  mov     [rdx+r8], al
0x180002c8e  mov     al, [rsp+rcx*4+448h+pPalEntries.peGreen]
0x180002c92  mov     [rdx+r8+1], al
0x180002c97  mov     al, [rsp+rcx*4+448h+pPalEntries.peBlue]
0x180002c9b  mov     [rdx+r8+2], al
0x180002ca0  mov     byte ptr [rdx+r8+3], 0
0x180002ca6  cmp     r9d, 100h
0x180002cad  jl      short loc_180002C79
0x180002caf  xor     eax, eax
0x180002cb1  mov     rcx, [rsp+448h+var_28]
0x180002cb9  xor     rcx, rsp; StackCookie
0x180002cbc  call    __security_check_cookie
0x180002cc1  add     rsp, 430h
0x180002cc8  pop     rdi
0x180002cc9  pop     rsi
0x180002cca  pop     rbx
0x180002ccb  retn
```
