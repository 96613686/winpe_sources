# CClientUtilsWin32::UT_GetPaletteForBitmap(HDC__ *,HBITMAP__ *)

- ea: `0x14009fe70`
- end: `0x14009ffc1`
- name: `?UT_GetPaletteForBitmap@CClientUtilsWin32@@SAPEAUHPALETTE__@@PEAUHDC__@@PEAUHBITMAP__@@@Z`
- size: `337`
- prototype: `static HPALETTE(HDC, HBITMAP)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14004b29c`

## callees

- `0x14000b7d8`
- `0x14000cf70`
- `0x14009fe70`
- `0x140111220`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x14009fee3`
- `KERNEL32!LocalAlloc` at `0x14009fee3`
- `KERNEL32!LocalFree` at `0x14009ff31`
- `KERNEL32!LocalFree` at `0x14009ff31`
- `GDI32!DeleteDC` at `0x14009ff90`
- `GDI32!DeleteDC` at `0x14009ff90`
- `GDI32!CreateCompatibleDC` at `0x14009fe9c`
- `GDI32!CreateCompatibleDC` at `0x14009fe9c`
- `GDI32!GetDIBColorTable` at `0x14009fed0`
- `GDI32!GetDIBColorTable` at `0x14009fed0`
- `GDI32!CreatePalette` at `0x14009ff25`
- `GDI32!CreatePalette` at `0x14009ff25`
- `GDI32!SelectObject` at `0x14009feb4`
- `GDI32!SelectObject` at `0x14009ff87`
- `GDI32!SelectObject` at `0x14009feb4`
- `GDI32!SelectObject` at `0x14009ff87`

## pseudocode

```c
HPALETTE __fastcall CClientUtilsWin32::UT_GetPaletteForBitmap(HDC a1, HBITMAP a2)
{
  HPALETTE Palette; // rsi
  HDC CompatibleDC; // rax
  HDC v5; // rdi
  HGDIOBJ v6; // rbp
  LOGPALETTE *v7; // rax
  LOGPALETTE *v8; // rbx
  __int64 i; // rcx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  RGBQUAD prgbq[256]; // [rsp+20h] [rbp-428h] BYREF

  Palette = 0;
  CompatibleDC = CreateCompatibleDC(a1);
  v5 = CompatibleDC;
  if ( CompatibleDC )
  {
    v6 = SelectObject(CompatibleDC, a2);
    if ( GetDIBColorTable(v5, 0, 0x100u, prgbq) == 256 )
    {
      v7 = (LOGPALETTE *)LocalAlloc(0x40u, 0x2000u);
      v8 = v7;
      if ( v7 )
      {
        *(_DWORD *)&v7->palVersion = 16777984;
        for ( i = 0; i != 256; ++i )
        {
          v7->palPalEntry[i].peRed = prgbq[i].rgbRed;
          v7->palPalEntry[i].peGreen = prgbq[i].rgbGreen;
          v7->palPalEntry[i].peBlue = prgbq[i].rgbBlue;
          v7->palPalEntry[i].peFlags = 0;
        }
        Palette = CreatePalette(v7);
        LocalFree(v8);
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        47,
        &WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids,
        CurrentThreadActivityIdPrefix);
    }
    if ( v6 )
      SelectObject(v5, v6);
    DeleteDC(v5);
  }
  return Palette;
}

```

## disassembly

```asm
0x14009fe70  mov     [rsp+arg_10], rbx
0x14009fe75  mov     [rsp+arg_18], rbp
0x14009fe7a  push    rsi
0x14009fe7b  push    rdi
0x14009fe7c  push    r14
0x14009fe7e  sub     rsp, 430h
0x14009fe85  mov     rax, cs:__security_cookie
0x14009fe8c  xor     rax, rsp
0x14009fe8f  mov     [rsp+448h+var_28], rax
0x14009fe97  mov     rbx, rdx
0x14009fe9a  xor     esi, esi
0x14009fe9c  call    cs:__imp_CreateCompatibleDC
0x14009fea2  mov     rdi, rax
0x14009fea5  test    rax, rax
0x14009fea8  jz      loc_14009FF96
0x14009feae  mov     rdx, rbx; h
0x14009feb1  mov     rcx, rax; hdc
0x14009feb4  call    cs:__imp_SelectObject
0x14009feba  mov     r14d, 100h
0x14009fec0  lea     r9, [rsp+448h+prgbq]; prgbq
0x14009fec5  mov     r8d, r14d; cEntries
0x14009fec8  xor     edx, edx; iStart
0x14009feca  mov     rcx, rdi; hdc
0x14009fecd  mov     rbp, rax
0x14009fed0  call    cs:__imp_GetDIBColorTable
0x14009fed6  cmp     eax, r14d
0x14009fed9  jnz     short loc_14009FF39
0x14009fedb  mov     edx, 2000h; uBytes
0x14009fee0  lea     ecx, [rsi+40h]; uFlags
0x14009fee3  call    cs:__imp_LocalAlloc
0x14009fee9  mov     rbx, rax
0x14009feec  test    rax, rax
0x14009feef  jz      loc_14009FF7C
0x14009fef5  mov     dword ptr [rax], 1000300h
0x14009fefb  xor     ecx, ecx
0x14009fefd  mov     al, [rsp+rcx*4+448h+prgbq.rgbRed]
0x14009ff01  mov     [rbx+rcx*4+4], al
0x14009ff05  mov     al, [rsp+rcx*4+448h+prgbq.rgbGreen]
0x14009ff09  mov     [rbx+rcx*4+5], al
0x14009ff0d  mov     al, [rsp+rcx*4+448h+prgbq.rgbBlue]
0x14009ff11  mov     [rbx+rcx*4+6], al
0x14009ff15  mov     [rbx+rcx*4+7], sil
0x14009ff1a  inc     rcx
0x14009ff1d  cmp     rcx, r14
0x14009ff20  jnz     short loc_14009FEFD
0x14009ff22  mov     rcx, rbx; plpal
0x14009ff25  call    cs:__imp_CreatePalette
0x14009ff2b  mov     rcx, rbx; hMem
0x14009ff2e  mov     rsi, rax
0x14009ff31  call    cs:__imp_LocalFree
0x14009ff37  jmp     short loc_14009FF7C
0x14009ff39  mov     rax, cs:WPP_GLOBAL_Control
0x14009ff40  lea     rcx, WPP_GLOBAL_Control
0x14009ff47  cmp     rax, rcx
0x14009ff4a  jz      short loc_14009FF7C
0x14009ff4c  test    byte ptr [rax+1Ch], 1
0x14009ff50  jz      short loc_14009FF7C
0x14009ff52  cmp     byte ptr [rax+19h], 3
0x14009ff56  jb      short loc_14009FF7C
0x14009ff58  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14009ff5d  mov     rcx, cs:WPP_GLOBAL_Control
0x14009ff64  lea     r8, WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids
0x14009ff6b  mov     edx, 2Fh ; '/'
0x14009ff70  mov     r9d, eax
0x14009ff73  mov     rcx, [rcx+10h]
0x14009ff77  call    WPP_SF_d
0x14009ff7c  test    rbp, rbp
0x14009ff7f  jz      short loc_14009FF8D
0x14009ff81  mov     rdx, rbp; h
0x14009ff84  mov     rcx, rdi; hdc
0x14009ff87  call    cs:__imp_SelectObject
0x14009ff8d  mov     rcx, rdi; hdc
0x14009ff90  call    cs:__imp_DeleteDC
0x14009ff96  mov     rax, rsi
0x14009ff99  mov     rcx, [rsp+448h+var_28]
0x14009ffa1  xor     rcx, rsp; StackCookie
0x14009ffa4  call    __security_check_cookie
0x14009ffa9  lea     r11, [rsp+448h+var_18]
0x14009ffb1  mov     rbx, [r11+30h]
0x14009ffb5  mov     rbp, [r11+38h]
0x14009ffb9  mov     rsp, r11
0x14009ffbc  pop     r14
0x14009ffbe  pop     rdi
0x14009ffbf  pop     rsi
0x14009ffc0  retn
```
