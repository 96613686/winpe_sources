# GpDevice::PaletteChangeNotification(void)

- ea: `0x18009e37c`
- end: `0x18009e504`
- name: `?PaletteChangeNotification@GpDevice@@QEAAXXZ`
- size: `392`
- prototype: `void __fastcall(GpDevice *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x18009cfec`
- `0x18009d2dc`
- `0x1801144e8`
- `0x180139690`

## callees

- `0x1800067bc`
- `0x18009e37c`
- `0x1800fe680`
- `0x1800ff04c`

## import_xrefs

- `GDI32!SetDIBColorTable` at `0x18009e4d9`
- `GDI32!SetDIBColorTable` at `0x18009e4d9`
- `GDI32!GetDeviceCaps` at `0x18009e3af`
- `GDI32!GetDeviceCaps` at `0x18009e3c3`
- `GDI32!GetDeviceCaps` at `0x18009e3d7`
- `GDI32!GetDeviceCaps` at `0x18009e3af`
- `GDI32!GetDeviceCaps` at `0x18009e3c3`
- `GDI32!GetDeviceCaps` at `0x18009e3d7`
- `GDI32!GetSystemPaletteEntries` at `0x18009e44e`
- `GDI32!GetSystemPaletteEntries` at `0x18009e44e`

## pseudocode

```c
void __fastcall GpDevice::PaletteChangeNotification(HDC *this)
{
  char DeviceCaps; // si
  char v3; // di
  signed int v4; // edi
  __int64 v5; // rax
  signed int v6; // r9d
  __int64 v7; // rdx
  HDC v8; // rcx
  struct tagPALETTEENTRY pPalEntries[256]; // [rsp+20h] [rbp-818h] BYREF
  RGBQUAD prgbq[256]; // [rsp+420h] [rbp-418h] BYREF

  DeviceCaps = GetDeviceCaps(this[188], 14);
  v3 = GetDeviceCaps(this[188], 12);
  if ( GetDeviceCaps(this[188], 2) == 1 )
  {
    v4 = 1 << (v3 * DeviceCaps);
    if ( v4 <= 256 )
    {
      if ( this[197] || (v5 = GpMallocEx(1036, 0), (this[197] = (HDC)v5) != 0) )
      {
        pPalEntries[0].peRed = 0;
        memset_0(&pPalEntries[0].peGreen, 0, 0x3FFu);
        GetSystemPaletteEntries(this[188], 0, 0x100u, pPalEntries);
        v6 = 0;
        for ( *((_DWORD *)this[197] + 1) = v4; v6 < v4; prgbq[v7].rgbReserved = 0 )
        {
          v7 = (unsigned int)v6++;
          *((_DWORD *)this[197] + v7 + 2) = pPalEntries[v7].peBlue
                                          | ((pPalEntries[v7].peGreen | ((pPalEntries[v7].peRed | 0xFFFFFF00) << 8)) << 8);
          prgbq[v7].rgbRed = pPalEntries[v7].peRed;
          prgbq[v7].rgbGreen = pPalEntries[v7].peGreen;
          prgbq[v7].rgbBlue = pPalEntries[v7].peBlue;
        }
        v8 = this[3];
        if ( v8 )
          SetDIBColorTable(v8, 0, v4, prgbq);
      }
    }
  }
}

```

## disassembly

```asm
0x18009e37c  mov     [rsp+arg_8], rbx
0x18009e381  mov     [rsp+arg_10], rsi
0x18009e386  push    rdi
0x18009e387  sub     rsp, 830h
0x18009e38e  mov     rax, cs:__security_cookie
0x18009e395  xor     rax, rsp
0x18009e398  mov     [rsp+838h+var_18], rax
0x18009e3a0  mov     rbx, rcx
0x18009e3a3  mov     edx, 0Eh; index
0x18009e3a8  mov     rcx, [rcx+5E0h]; hdc
0x18009e3af  call    cs:__imp_GetDeviceCaps
0x18009e3b5  mov     rcx, [rbx+5E0h]; hdc
0x18009e3bc  mov     edx, 0Ch; index
0x18009e3c1  mov     esi, eax
0x18009e3c3  call    cs:__imp_GetDeviceCaps
0x18009e3c9  mov     rcx, [rbx+5E0h]; hdc
0x18009e3d0  mov     edx, 2; index
0x18009e3d5  mov     edi, eax
0x18009e3d7  call    cs:__imp_GetDeviceCaps
0x18009e3dd  cmp     eax, 1
0x18009e3e0  jnz     loc_18009E4DF
0x18009e3e6  imul    esi, edi
0x18009e3e9  mov     edi, eax
0x18009e3eb  mov     cl, sil
0x18009e3ee  shl     edi, cl
0x18009e3f0  cmp     edi, 100h
0x18009e3f6  jg      loc_18009E4DF
0x18009e3fc  xor     esi, esi
0x18009e3fe  cmp     [rbx+628h], rsi
0x18009e405  jnz     short loc_18009E423
0x18009e407  xor     edx, edx
0x18009e409  mov     ecx, 40Ch
0x18009e40e  call    GpMallocEx
0x18009e413  mov     [rbx+628h], rax
0x18009e41a  test    rax, rax
0x18009e41d  jz      loc_18009E4DF
0x18009e423  xor     edx, edx; Val
0x18009e425  mov     [rsp+838h+pPalEntries.peRed], sil
0x18009e42a  mov     r8d, 3FFh; Size
0x18009e430  lea     rcx, [rsp+838h+pPalEntries.peGreen]; void *
0x18009e435  call    memset_0
0x18009e43a  mov     rcx, [rbx+5E0h]; hdc
0x18009e441  lea     r9, [rsp+838h+pPalEntries]; pPalEntries
0x18009e446  xor     edx, edx; iStart
0x18009e448  mov     r8d, 100h; cEntries
0x18009e44e  call    cs:__imp_GetSystemPaletteEntries
0x18009e454  mov     rax, [rbx+628h]
0x18009e45b  mov     r9d, esi
0x18009e45e  mov     [rax+4], edi
0x18009e461  test    edi, edi
0x18009e463  jle     short loc_18009E4C3
0x18009e465  mov     edx, r9d
0x18009e468  inc     r9d
0x18009e46b  movzx   eax, [rsp+rdx*4+838h+pPalEntries.peGreen]
0x18009e470  movzx   ecx, [rsp+rdx*4+838h+pPalEntries.peRed]
0x18009e475  or      ecx, 0FFFFFF00h
0x18009e47b  shl     ecx, 8
0x18009e47e  or      ecx, eax
0x18009e480  movzx   eax, [rsp+rdx*4+838h+pPalEntries.peBlue]
0x18009e485  shl     ecx, 8
0x18009e488  or      ecx, eax
0x18009e48a  mov     rax, [rbx+628h]
0x18009e491  mov     [rax+rdx*4+8], ecx
0x18009e495  mov     al, [rsp+rdx*4+838h+pPalEntries.peRed]
0x18009e499  mov     [rsp+rdx*4+838h+prgbq.rgbRed], al
0x18009e4a0  mov     al, [rsp+rdx*4+838h+pPalEntries.peGreen]
0x18009e4a4  mov     [rsp+rdx*4+838h+prgbq.rgbGreen], al
0x18009e4ab  mov     al, [rsp+rdx*4+838h+pPalEntries.peBlue]
0x18009e4af  mov     [rsp+rdx*4+838h+prgbq.rgbBlue], al
0x18009e4b6  mov     [rsp+rdx*4+838h+prgbq.rgbReserved], sil
0x18009e4be  cmp     r9d, edi
0x18009e4c1  jl      short loc_18009E465
0x18009e4c3  mov     rcx, [rbx+18h]; hdc
0x18009e4c7  test    rcx, rcx
0x18009e4ca  jz      short loc_18009E4DF
0x18009e4cc  lea     r9, [rsp+838h+prgbq]; prgbq
0x18009e4d4  mov     r8d, edi; cEntries
0x18009e4d7  xor     edx, edx; iStart
0x18009e4d9  call    cs:__imp_SetDIBColorTable
0x18009e4df  mov     rcx, [rsp+838h+var_18]
0x18009e4e7  xor     rcx, rsp; StackCookie
0x18009e4ea  call    __security_check_cookie
0x18009e4ef  lea     r11, [rsp+838h+var_8]
0x18009e4f7  mov     rbx, [r11+18h]
0x18009e4fb  mov     rsi, [r11+20h]
0x18009e4ff  mov     rsp, r11
0x18009e502  pop     rdi
0x18009e503  retn
```
