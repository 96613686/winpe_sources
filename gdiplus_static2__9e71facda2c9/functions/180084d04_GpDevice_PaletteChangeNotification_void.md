# GpDevice::PaletteChangeNotification(void)

- ea: `0x180084d04`
- end: `0x180084eab`
- name: `?PaletteChangeNotification@GpDevice@@QEAAXXZ`
- size: `423`
- prototype: `void __fastcall(GpDevice *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180086350`
- `0x180086668`
- `0x18011c308`
- `0x180141bd0`

## callees

- `0x180063cd8`
- `0x180084d04`
- `0x180105d40`
- `0x18010673c`

## import_xrefs

- `GDI32!SetDIBColorTable` at `0x180084e79`
- `GDI32!SetDIBColorTable` at `0x180084e79`
- `GDI32!GetDeviceCaps` at `0x180084d37`
- `GDI32!GetDeviceCaps` at `0x180084d51`
- `GDI32!GetDeviceCaps` at `0x180084d6b`
- `GDI32!GetDeviceCaps` at `0x180084d37`
- `GDI32!GetDeviceCaps` at `0x180084d51`
- `GDI32!GetDeviceCaps` at `0x180084d6b`
- `GDI32!GetSystemPaletteEntries` at `0x180084de8`
- `GDI32!GetSystemPaletteEntries` at `0x180084de8`

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
0x180084d04  mov     [rsp+arg_8], rbx
0x180084d09  mov     [rsp+arg_10], rsi
0x180084d0e  push    rdi
0x180084d0f  sub     rsp, 830h
0x180084d16  mov     rax, cs:__security_cookie
0x180084d1d  xor     rax, rsp
0x180084d20  mov     [rsp+838h+var_18], rax
0x180084d28  mov     rbx, rcx
0x180084d2b  mov     edx, 0Eh; index
0x180084d30  mov     rcx, [rcx+5E0h]; hdc
0x180084d37  call    cs:__imp_GetDeviceCaps
0x180084d3e  nop     dword ptr [rax+rax+00h]
0x180084d43  mov     rcx, [rbx+5E0h]; hdc
0x180084d4a  mov     edx, 0Ch; index
0x180084d4f  mov     esi, eax
0x180084d51  call    cs:__imp_GetDeviceCaps
0x180084d58  nop     dword ptr [rax+rax+00h]
0x180084d5d  mov     rcx, [rbx+5E0h]; hdc
0x180084d64  mov     edx, 2; index
0x180084d69  mov     edi, eax
0x180084d6b  call    cs:__imp_GetDeviceCaps
0x180084d72  nop     dword ptr [rax+rax+00h]
0x180084d77  cmp     eax, 1
0x180084d7a  jnz     loc_180084E85
0x180084d80  imul    esi, edi
0x180084d83  mov     edi, eax
0x180084d85  mov     cl, sil
0x180084d88  shl     edi, cl
0x180084d8a  cmp     edi, 100h
0x180084d90  jg      loc_180084E85
0x180084d96  xor     esi, esi
0x180084d98  cmp     [rbx+628h], rsi
0x180084d9f  jnz     short loc_180084DBD
0x180084da1  xor     edx, edx
0x180084da3  mov     ecx, 40Ch
0x180084da8  call    GpMallocEx
0x180084dad  mov     [rbx+628h], rax
0x180084db4  test    rax, rax
0x180084db7  jz      loc_180084E85
0x180084dbd  xor     edx, edx; Val
0x180084dbf  mov     [rsp+838h+pPalEntries.peRed], sil
0x180084dc4  mov     r8d, 3FFh; Size
0x180084dca  lea     rcx, [rsp+838h+pPalEntries.peGreen]; void *
0x180084dcf  call    memset_0
0x180084dd4  mov     rcx, [rbx+5E0h]; hdc
0x180084ddb  lea     r9, [rsp+838h+pPalEntries]; pPalEntries
0x180084de0  xor     edx, edx; iStart
0x180084de2  mov     r8d, 100h; cEntries
0x180084de8  call    cs:__imp_GetSystemPaletteEntries
0x180084def  nop     dword ptr [rax+rax+00h]
0x180084df4  mov     rax, [rbx+628h]
0x180084dfb  mov     r9d, esi
0x180084dfe  mov     [rax+4], edi
0x180084e01  test    edi, edi
0x180084e03  jle     short loc_180084E63
0x180084e05  mov     edx, r9d
0x180084e08  inc     r9d
0x180084e0b  movzx   eax, [rsp+rdx*4+838h+pPalEntries.peGreen]
0x180084e10  movzx   ecx, [rsp+rdx*4+838h+pPalEntries.peRed]
0x180084e15  or      ecx, 0FFFFFF00h
0x180084e1b  shl     ecx, 8
0x180084e1e  or      ecx, eax
0x180084e20  movzx   eax, [rsp+rdx*4+838h+pPalEntries.peBlue]
0x180084e25  shl     ecx, 8
0x180084e28  or      ecx, eax
0x180084e2a  mov     rax, [rbx+628h]
0x180084e31  mov     [rax+rdx*4+8], ecx
0x180084e35  mov     al, [rsp+rdx*4+838h+pPalEntries.peRed]
0x180084e39  mov     [rsp+rdx*4+838h+prgbq.rgbRed], al
0x180084e40  mov     al, [rsp+rdx*4+838h+pPalEntries.peGreen]
0x180084e44  mov     [rsp+rdx*4+838h+prgbq.rgbGreen], al
0x180084e4b  mov     al, [rsp+rdx*4+838h+pPalEntries.peBlue]
0x180084e4f  mov     [rsp+rdx*4+838h+prgbq.rgbBlue], al
0x180084e56  mov     [rsp+rdx*4+838h+prgbq.rgbReserved], sil
0x180084e5e  cmp     r9d, edi
0x180084e61  jl      short loc_180084E05
0x180084e63  mov     rcx, [rbx+18h]; hdc
0x180084e67  test    rcx, rcx
0x180084e6a  jz      short loc_180084E85
0x180084e6c  lea     r9, [rsp+838h+prgbq]; prgbq
0x180084e74  mov     r8d, edi; cEntries
0x180084e77  xor     edx, edx; iStart
0x180084e79  call    cs:__imp_SetDIBColorTable
0x180084e80  nop     dword ptr [rax+rax+00h]
0x180084e85  mov     rcx, [rsp+838h+var_18]
0x180084e8d  xor     rcx, rsp; StackCookie
0x180084e90  call    __security_check_cookie
0x180084e95  lea     r11, [rsp+838h+var_8]
0x180084e9d  mov     rbx, [r11+18h]
0x180084ea1  mov     rsi, [r11+20h]
0x180084ea5  mov     rsp, r11
0x180084ea8  pop     rdi
0x180084ea9  retn
```
