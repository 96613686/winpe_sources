# CClientUtilsWin32::UT_GetPaletteForBitmap(HDC__ *,HBITMAP__ *)

- ea: `0x1400a1fe0`
- end: `0x1400a2131`
- name: `?UT_GetPaletteForBitmap@CClientUtilsWin32@@SAPEAUHPALETTE__@@PEAUHDC__@@PEAUHBITMAP__@@@Z`
- size: `337`
- prototype: `static HPALETTE(HDC, HBITMAP)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14004d40c`

## callees

- `0x14000b7d8`
- `0x14000cf70`
- `0x1400a1fe0`
- `0x140113390`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x1400a2053`
- `KERNEL32!LocalAlloc` at `0x1400a2053`
- `KERNEL32!LocalFree` at `0x1400a20a1`
- `KERNEL32!LocalFree` at `0x1400a20a1`
- `GDI32!DeleteDC` at `0x1400a2100`
- `GDI32!DeleteDC` at `0x1400a2100`
- `GDI32!CreateCompatibleDC` at `0x1400a200c`
- `GDI32!CreateCompatibleDC` at `0x1400a200c`
- `GDI32!GetDIBColorTable` at `0x1400a2040`
- `GDI32!GetDIBColorTable` at `0x1400a2040`
- `GDI32!CreatePalette` at `0x1400a2095`
- `GDI32!CreatePalette` at `0x1400a2095`
- `GDI32!SelectObject` at `0x1400a2024`
- `GDI32!SelectObject` at `0x1400a20f7`
- `GDI32!SelectObject` at `0x1400a2024`
- `GDI32!SelectObject` at `0x1400a20f7`

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
0x1400a1fe0  mov     [rsp+arg_10], rbx
0x1400a1fe5  mov     [rsp+arg_18], rbp
0x1400a1fea  push    rsi
0x1400a1feb  push    rdi
0x1400a1fec  push    r14
0x1400a1fee  sub     rsp, 430h
0x1400a1ff5  mov     rax, cs:__security_cookie
0x1400a1ffc  xor     rax, rsp
0x1400a1fff  mov     [rsp+448h+var_28], rax
0x1400a2007  mov     rbx, rdx
0x1400a200a  xor     esi, esi
0x1400a200c  call    cs:__imp_CreateCompatibleDC
0x1400a2012  mov     rdi, rax
0x1400a2015  test    rax, rax
0x1400a2018  jz      loc_1400A2106
0x1400a201e  mov     rdx, rbx; h
0x1400a2021  mov     rcx, rax; hdc
0x1400a2024  call    cs:__imp_SelectObject
0x1400a202a  mov     r14d, 100h
0x1400a2030  lea     r9, [rsp+448h+prgbq]; prgbq
0x1400a2035  mov     r8d, r14d; cEntries
0x1400a2038  xor     edx, edx; iStart
0x1400a203a  mov     rcx, rdi; hdc
0x1400a203d  mov     rbp, rax
0x1400a2040  call    cs:__imp_GetDIBColorTable
0x1400a2046  cmp     eax, r14d
0x1400a2049  jnz     short loc_1400A20A9
0x1400a204b  mov     edx, 2000h; uBytes
0x1400a2050  lea     ecx, [rsi+40h]; uFlags
0x1400a2053  call    cs:__imp_LocalAlloc
0x1400a2059  mov     rbx, rax
0x1400a205c  test    rax, rax
0x1400a205f  jz      loc_1400A20EC
0x1400a2065  mov     dword ptr [rax], 1000300h
0x1400a206b  xor     ecx, ecx
0x1400a206d  mov     al, [rsp+rcx*4+448h+prgbq.rgbRed]
0x1400a2071  mov     [rbx+rcx*4+4], al
0x1400a2075  mov     al, [rsp+rcx*4+448h+prgbq.rgbGreen]
0x1400a2079  mov     [rbx+rcx*4+5], al
0x1400a207d  mov     al, [rsp+rcx*4+448h+prgbq.rgbBlue]
0x1400a2081  mov     [rbx+rcx*4+6], al
0x1400a2085  mov     [rbx+rcx*4+7], sil
0x1400a208a  inc     rcx
0x1400a208d  cmp     rcx, r14
0x1400a2090  jnz     short loc_1400A206D
0x1400a2092  mov     rcx, rbx; plpal
0x1400a2095  call    cs:__imp_CreatePalette
0x1400a209b  mov     rcx, rbx; hMem
0x1400a209e  mov     rsi, rax
0x1400a20a1  call    cs:__imp_LocalFree
0x1400a20a7  jmp     short loc_1400A20EC
0x1400a20a9  mov     rax, cs:WPP_GLOBAL_Control
0x1400a20b0  lea     rcx, WPP_GLOBAL_Control
0x1400a20b7  cmp     rax, rcx
0x1400a20ba  jz      short loc_1400A20EC
0x1400a20bc  test    byte ptr [rax+1Ch], 1
0x1400a20c0  jz      short loc_1400A20EC
0x1400a20c2  cmp     byte ptr [rax+19h], 3
0x1400a20c6  jb      short loc_1400A20EC
0x1400a20c8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a20cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a20d4  lea     r8, WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids
0x1400a20db  mov     edx, 2Fh ; '/'
0x1400a20e0  mov     r9d, eax
0x1400a20e3  mov     rcx, [rcx+10h]
0x1400a20e7  call    WPP_SF_d
0x1400a20ec  test    rbp, rbp
0x1400a20ef  jz      short loc_1400A20FD
0x1400a20f1  mov     rdx, rbp; h
0x1400a20f4  mov     rcx, rdi; hdc
0x1400a20f7  call    cs:__imp_SelectObject
0x1400a20fd  mov     rcx, rdi; hdc
0x1400a2100  call    cs:__imp_DeleteDC
0x1400a2106  mov     rax, rsi
0x1400a2109  mov     rcx, [rsp+448h+var_28]
0x1400a2111  xor     rcx, rsp; StackCookie
0x1400a2114  call    __security_check_cookie
0x1400a2119  lea     r11, [rsp+448h+var_18]
0x1400a2121  mov     rbx, [r11+30h]
0x1400a2125  mov     rbp, [r11+38h]
0x1400a2129  mov     rsp, r11
0x1400a212c  pop     r14
0x1400a212e  pop     rdi
0x1400a212f  pop     rsi
0x1400a2130  retn
```
