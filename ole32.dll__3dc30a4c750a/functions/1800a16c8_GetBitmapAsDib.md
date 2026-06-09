# GetBitmapAsDib

- ea: `0x1800a16c8`
- end: `0x1800a185c`
- name: `GetBitmapAsDib`
- size: `404`
- prototype: `__int64 __fastcall(_OLESTREAM *pos, CData *pdata)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800a1c4c`

## callees

- `0x18000b2d4`
- `0x180040e18`
- `0x1800a16c8`
- `0x1800a220c`
- `0x1800ce010`

## import_xrefs

- `KERNELBASE!GlobalAlloc` at `0x1800a1759`
- `KERNELBASE!GlobalAlloc` at `0x1800a1759`
- `KERNELBASE!GlobalFree` at `0x1800a181f`
- `KERNELBASE!GlobalFree` at `0x1800a181f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x1800a1806`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x1800a1806`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800a1816`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800a1816`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800a1770`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800a17ed`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800a1770`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800a17ed`
- `GDI32!DeleteObject` at `0x1800a182d`
- `GDI32!DeleteObject` at `0x1800a182d`
- `GDI32!CreateBitmap` at `0x1800a17c3`
- `GDI32!CreateBitmap` at `0x1800a17c3`

## pseudocode

```c
__int64 __fastcall GetBitmapAsDib(_OLESTREAM *pos, CData *pdata)
{
  __int64 result; // rax
  unsigned int v5; // ebx
  unsigned int v6; // r12d
  unsigned __int64 v7; // rdi
  HGLOBAL v8; // rax
  void *v9; // rbp
  HBITMAP v10; // rdi
  const void *v11; // rax
  const void *lpBits; // r14
  HBITMAP Bitmap; // rax
  void *v14; // rax
  void *v15; // rsi
  void *v16; // rax
  tagWIN16BITMAP bm; // [rsp+30h] [rbp-48h] BYREF
  unsigned int ul; // [rsp+90h] [rbp+18h] BYREF

  ul = 0;
  memset(&bm, 0, sizeof(bm));
  result = OLE1StreamToUL(pos, &ul);
  v5 = result;
  if ( (int)result >= 0 )
  {
    if ( ((__int64 (__fastcall *)(_OLESTREAM *, tagWIN16BITMAP *, __int64))pos->lpstbl->Get)(pos, &bm, 18) < 0x12
      || ul < 0x12 )
    {
      return 2147746240LL;
    }
    else
    {
      v6 = ul - 18;
      v7 = ul - 18;
      if ( v7 < GetSafeAllocSize() && (v8 = GlobalAlloc(2u, (unsigned int)v7), (v9 = v8) != 0) )
      {
        v10 = 0;
        v11 = GlobalLock(v8);
        lpBits = v11;
        if ( v11 )
        {
          if ( ((__int64 (__fastcall *)(_OLESTREAM *, const void *, _QWORD))pos->lpstbl->Get)(pos, v11, v6) >= v6 )
          {
            Bitmap = CreateBitmap(bm.bmWidth, bm.bmHeight, bm.bmPlanes, bm.bmBitsPixel, lpBits);
            v10 = Bitmap;
            if ( Bitmap && (v14 = UtConvertBitmapToDib(Bitmap, 0), (v15 = v14) != 0) )
            {
              v16 = GlobalLock(v14);
              pdata->m_pv = v16;
              if ( v16 )
              {
                pdata->m_cbSize = GlobalSize(v15);
                pdata->m_h = v15;
              }
              else
              {
                v5 = -2147024882;
              }
            }
            else
            {
              v5 = -2147221053;
            }
          }
          else
          {
            v5 = -2147221056;
          }
          GlobalUnlock(v9);
        }
        else
        {
          v5 = -2147024882;
        }
        GlobalFree(v9);
        if ( v10 )
          DeleteObject(v10);
      }
      else
      {
        return (unsigned int)-2147024882;
      }
      return v5;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800a16c8  mov     r11, rsp
0x1800a16cb  mov     [r11+8], rbx
0x1800a16cf  mov     [r11+10h], rbp
0x1800a16d3  push    rsi
0x1800a16d4  push    rdi
0x1800a16d5  push    r12
0x1800a16d7  push    r14
0x1800a16d9  push    r15
0x1800a16db  sub     rsp, 50h
0x1800a16df  xor     eax, eax
0x1800a16e1  mov     r15, pdata
0x1800a16e4  xorps   xmm0, xmm0
0x1800a16e7  mov     word ptr [rsp+78h+bm.bmBits+6], ax
0x1800a16ec  lea     pdata, [r11+18h]; pul
0x1800a16f0  mov     [r11+18h], eax
0x1800a16f4  movups  xmmword ptr [rsp+78h+bm.bmType], xmm0
0x1800a16f9  mov     rsi, pos
0x1800a16fc  call    OLE1StreamToUL
0x1800a1701  mov     ebx, eax
0x1800a1703  test    eax, eax
0x1800a1705  js      loc_1800A1843
0x1800a170b  mov     rax, [rsi]
0x1800a170e  lea     pdata, [rsp+78h+bm]
0x1800a1713  mov     r8d, 12h
0x1800a1719  mov     pos, rsi
0x1800a171c  mov     rax, [rax]
0x1800a171f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1724  cmp     eax, 12h
0x1800a1727  jb      loc_1800A183E
0x1800a172d  mov     eax, [rsp+78h+ul]
0x1800a1734  cmp     eax, 12h
0x1800a1737  jb      loc_1800A183E
0x1800a173d  lea     r12d, [rax-12h]
0x1800a1741  mov     edi, r12d
0x1800a1744  call    GetSafeAllocSize
0x1800a1749  cmp     rdi, rax
0x1800a174c  jnb     loc_1800A1835
0x1800a1752  mov     edx, edi; dwBytes
0x1800a1754  mov     ecx, 2; uFlags
0x1800a1759  call    cs:__imp_GlobalAlloc
0x1800a175f  mov     rbp, rax
0x1800a1762  test    rax, rax
0x1800a1765  jz      loc_1800A1835
0x1800a176b  mov     pos, rax; hMem
0x1800a176e  xor     edi, edi
0x1800a1770  call    cs:__imp_GlobalLock
0x1800a1776  mov     r14, rax
0x1800a1779  test    rax, rax
0x1800a177c  jnz     short loc_1800A1788
0x1800a177e  mov     ebx, 8007000Eh
0x1800a1783  jmp     loc_1800A181C
0x1800a1788  mov     rax, [rsi]
0x1800a178b  mov     r8d, r12d
0x1800a178e  mov     pdata, r14
0x1800a1791  mov     pos, rsi
0x1800a1794  mov     rax, [rax]
0x1800a1797  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a179c  cmp     eax, r12d
0x1800a179f  jnb     short loc_1800A17A8
0x1800a17a1  mov     ebx, 800401C0h
0x1800a17a6  jmp     short $errRtn_165
0x1800a17a8  movzx   r9d, [rsp+78h+bm.bmBitsPixel]; nBitCount
0x1800a17ae  movzx   r8d, [rsp+78h+bm.bmPlanes]; nPlanes
0x1800a17b4  movsx   edx, [rsp+78h+bm.bmHeight]; nHeight
0x1800a17b9  movsx   ecx, [rsp+78h+bm.bmWidth]; nWidth
0x1800a17be  mov     [rsp+78h+lpBits], r14; lpBits
0x1800a17c3  call    cs:__imp_CreateBitmap
0x1800a17c9  mov     rdi, rax
0x1800a17cc  test    rax, rax
0x1800a17cf  jnz     short loc_1800A17D8
0x1800a17d1  mov     ebx, 800401C3h
0x1800a17d6  jmp     short $errRtn_165
0x1800a17d8  xor     edx, edx; hpal
0x1800a17da  mov     pos, rax; hBitmap
0x1800a17dd  call    ?UtConvertBitmapToDib@@YAPEAXPEAUHBITMAP__@@PEAUHPALETTE__@@@Z; UtConvertBitmapToDib(HBITMAP__ *,HPALETTE__ *)
0x1800a17e2  mov     rsi, rax
0x1800a17e5  test    rax, rax
0x1800a17e8  jz      short loc_1800A17D1
0x1800a17ea  mov     pos, rax; hMem
0x1800a17ed  call    cs:__imp_GlobalLock
0x1800a17f3  mov     [r15+8], rax
0x1800a17f7  test    rax, rax
0x1800a17fa  jnz     short loc_1800A1803
0x1800a17fc  mov     ebx, 8007000Eh
0x1800a1801  jmp     short $errRtn_165
0x1800a1803  mov     pos, rsi; hMem
0x1800a1806  call    cs:__imp_GlobalSize
0x1800a180c  mov     [r15], eax
0x1800a180f  mov     [r15+10h], rsi
0x1800a1813  mov     pos, rbp; hMem
0x1800a1816  call    cs:__imp_GlobalUnlock
0x1800a181c  mov     pos, rbp; hMem
0x1800a181f  call    cs:__imp_GlobalFree
0x1800a1825  test    rdi, rdi
0x1800a1828  jz      short loc_1800A183A
0x1800a182a  mov     pos, rdi; ho
0x1800a182d  call    cs:__imp_DeleteObject
0x1800a1833  jmp     short loc_1800A183A
0x1800a1835  mov     ebx, 8007000Eh
0x1800a183a  mov     eax, ebx
0x1800a183c  jmp     short loc_1800A1843
0x1800a183e  mov     eax, 800401C0h
0x1800a1843  lea     r11, [rsp+78h+var_28]
0x1800a1848  mov     rbx, [r11+30h]
0x1800a184c  mov     rbp, [r11+38h]
0x1800a1850  mov     rsp, r11
0x1800a1853  pop     r15
0x1800a1855  pop     r14
0x1800a1857  pop     r12
0x1800a1859  pop     rdi
0x1800a185a  pop     rsi
0x1800a185b  retn
```
