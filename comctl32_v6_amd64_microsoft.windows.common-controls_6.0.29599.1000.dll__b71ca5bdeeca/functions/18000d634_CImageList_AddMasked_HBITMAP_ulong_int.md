# CImageList::_AddMasked(HBITMAP__ *,ulong,int *)

- ea: `0x18000d634`
- end: `0x18000d94f`
- name: `?_AddMasked@CImageList@@IEAAJPEAUHBITMAP__@@KPEAH@Z`
- size: `795`
- prototype: `int(CImageList *__hidden this, HBITMAP, unsigned int, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000cc70`

## callees

- `0x18000d634`
- `0x18000ddcc`
- `0x18000e35c`
- `0x180011bb8`
- `0x180114520`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d83c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d83c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d6d2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d6d2`
- `GDI32!DeleteObject` at `0x18000d845`
- `GDI32!DeleteObject` at `0x18000d845`
- `GDI32!SetBkColor` at `0x18000d708`
- `GDI32!SetBkColor` at `0x18000d75f`
- `GDI32!SetBkColor` at `0x18000d7c2`
- `GDI32!SetBkColor` at `0x18000d708`
- `GDI32!SetBkColor` at `0x18000d75f`
- `GDI32!SetBkColor` at `0x18000d7c2`
- `GDI32!GetObjectW` at `0x18000d68e`
- `GDI32!GetObjectW` at `0x18000d68e`
- `GDI32!SetTextColor` at `0x18000d76e`
- `GDI32!SetTextColor` at `0x18000d7d1`
- `GDI32!SetTextColor` at `0x18000d76e`
- `GDI32!SetTextColor` at `0x18000d7d1`
- `GDI32!SelectObject` at `0x18000d7fc`
- `GDI32!SelectObject` at `0x18000d7fc`
- `GDI32!CreateBitmap` at `0x18000d6b7`
- `GDI32!CreateBitmap` at `0x18000d6b7`
- `GDI32!BitBlt` at `0x18000d74d`
- `GDI32!BitBlt` at `0x18000d7b3`
- `GDI32!BitBlt` at `0x18000d74d`
- `GDI32!BitBlt` at `0x18000d7b3`
- `GDI32!GetDIBColorTable` at `0x18000d890`
- `GDI32!GetDIBColorTable` at `0x18000d890`
- `GDI32!GetPixel` at `0x18000d92e`
- `GDI32!GetPixel` at `0x18000d92e`
- `GDI32!SetDIBColorTable` at `0x18000d8f0`
- `GDI32!SetDIBColorTable` at `0x18000d917`
- `GDI32!SetDIBColorTable` at `0x18000d8f0`
- `GDI32!SetDIBColorTable` at `0x18000d917`

## pseudocode

```c
__int64 __fastcall CImageList::_AddMasked(CImageList *this, HBITMAP a2, COLORREF Pixel, int *a4)
{
  HBITMAP Bitmap; // r14
  UINT i; // esi
  COLORREF v10; // edi
  COLORREF v11; // ebx
  unsigned int v12; // ebx
  int DIBColorTable; // eax
  __int64 v15; // r9
  RGBQUAD v16; // ecx
  int lpBits; // [rsp+20h] [rbp-E0h]
  int hdcSrc; // [rsp+28h] [rbp-D8h]
  __int128 pv; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v20; // [rsp+60h] [rbp-A0h]
  RGBQUAD prgbq[256]; // [rsp+70h] [rbp-90h] BYREF
  RGBQUAD v22[256]; // [rsp+470h] [rbp+370h] BYREF

  *a4 = -1;
  pv = 0;
  v20 = 0;
  if ( GetObjectW(a2, 32, &pv) != 32 )
    return 2147942487LL;
  Bitmap = CreateBitmap(SDWORD1(pv), SDWORD2(pv), 1u, 1u, 0);
  if ( !Bitmap )
    return 2147942414LL;
  i = 0;
  EnterCriticalSection(&g_csDll);
  CImageList::SelectSrcBitmap(a2);
  CImageList::SelectDstBitmap(Bitmap);
  if ( Pixel == -16777216 )
    Pixel = GetPixel(g_hdcSrc, 0, 0);
  if ( *((_QWORD *)&v20 + 1) && WORD1(v20) <= 8u )
  {
    DIBColorTable = GetDIBColorTable(g_hdcSrc, 0, 0x100u, prgbq);
    v15 = 0;
    for ( i = DIBColorTable; (int)v15 < DIBColorTable; v15 = (unsigned int)(v15 + 1) )
    {
      v16 = (RGBQUAD)0xFFFFFF;
      if ( *(_DWORD *)&prgbq[v15] != (((unsigned __int8)Pixel << 16) | BYTE2(Pixel) | Pixel & 0xFF00) )
        v16 = 0;
      v22[v15] = v16;
    }
    SetDIBColorTable(g_hdcSrc, 0, DIBColorTable, v22);
  }
  v10 = SetBkColor(g_hdcSrc, Pixel);
  BitBlt(g_hdcDst, 0, 0, SDWORD1(pv), SDWORD2(pv), g_hdcSrc, 0, 0, 0xCC0020u);
  SetBkColor(g_hdcSrc, 0xFFFFFFu);
  v11 = SetTextColor(g_hdcSrc, 0);
  BitBlt(g_hdcSrc, 0, 0, SDWORD1(pv), SDWORD2(pv), g_hdcDst, 0, 0, 0x220326u);
  SetBkColor(g_hdcSrc, v10);
  SetTextColor(g_hdcSrc, v11);
  if ( WORD1(v20) <= 8u && *((_QWORD *)&v20 + 1) )
    SetDIBColorTable(g_hdcSrc, 0, i, prgbq);
  if ( g_hbmSrc )
  {
    SelectObject(g_hdcSrc, g_hbmDcDeselect);
    g_hbmSrc = 0;
  }
  CImageList::SelectDstBitmap(0);
  v12 = CImageList::_Add(this, a2, Bitmap, SDWORD1(pv) / *((_DWORD *)this + 32), lpBits, hdcSrc, a4);
  LeaveCriticalSection(&g_csDll);
  DeleteObject(Bitmap);
  return v12;
}

```

## disassembly

```asm
0x18000d634  push    rbp
0x18000d636  push    rbx
0x18000d637  push    rsi
0x18000d638  push    rdi
0x18000d639  push    r12
0x18000d63b  push    r13
0x18000d63d  push    r14
0x18000d63f  push    r15
0x18000d641  lea     rbp, [rsp-788h]
0x18000d649  sub     rsp, 888h
0x18000d650  mov     rax, cs:__security_cookie
0x18000d657  xor     rax, rsp
0x18000d65a  mov     [rbp+7C0h+var_50], rax
0x18000d661  mov     r15, rdx
0x18000d664  mov     dword ptr [r9], 0FFFFFFFFh
0x18000d66b  xorps   xmm0, xmm0
0x18000d66e  mov     ebx, r8d
0x18000d671  mov     r12, rcx
0x18000d674  lea     r8, [rsp+8C0h+pv]; pv
0x18000d679  mov     rcx, r15; h
0x18000d67c  mov     edx, 20h ; ' '; c
0x18000d681  mov     r13, r9
0x18000d684  movups  [rsp+8C0h+pv], xmm0
0x18000d689  movups  [rsp+8C0h+var_860], xmm0
0x18000d68e  call    cs:__imp_GetObjectW
0x18000d694  cmp     eax, 20h ; ' '
0x18000d697  jnz     loc_18000D93B
0x18000d69d  mov     edx, dword ptr [rsp+8C0h+pv+8]; nHeight
0x18000d6a1  lea     edi, [rax-1Fh]
0x18000d6a4  mov     ecx, dword ptr [rsp+8C0h+pv+4]; nWidth
0x18000d6a8  mov     r9d, edi; nBitCount
0x18000d6ab  mov     r8d, edi; nPlanes
0x18000d6ae  mov     [rsp+8C0h+lpBits], 0; lpBits
0x18000d6b7  call    cs:__imp_CreateBitmap
0x18000d6bd  mov     r14, rax
0x18000d6c0  test    rax, rax
0x18000d6c3  jz      loc_18000D945
0x18000d6c9  lea     rcx, g_csDll; lpCriticalSection
0x18000d6d0  xor     esi, esi
0x18000d6d2  call    cs:__imp_EnterCriticalSection
0x18000d6d8  mov     rcx, r15; h
0x18000d6db  call    ?SelectSrcBitmap@CImageList@@KAXPEAUHBITMAP__@@@Z; CImageList::SelectSrcBitmap(HBITMAP__ *)
0x18000d6e0  mov     rcx, r14; HBITMAP
0x18000d6e3  call    ?SelectDstBitmap@CImageList@@KAXPEAUHBITMAP__@@@Z; CImageList::SelectDstBitmap(HBITMAP__ *)
0x18000d6e8  cmp     ebx, 0FF000000h
0x18000d6ee  jz      loc_18000D922
0x18000d6f4  cmp     qword ptr [rsp+8C0h+var_860+8], rsi
0x18000d6f9  jnz     loc_18000D870
0x18000d6ff  mov     rcx, cs:?g_hdcSrc@@3PEAUHDC__@@EA; hdc
0x18000d706  mov     edx, ebx; color
0x18000d708  call    cs:__imp_SetBkColor
0x18000d70e  mov     rcx, cs:?g_hdcSrc@@3PEAUHDC__@@EA; HDC__ * g_hdcSrc
0x18000d715  xor     r8d, r8d; y
0x18000d718  mov     r9d, dword ptr [rsp+8C0h+pv+4]; cx
0x18000d71d  xor     edx, edx; x
0x18000d71f  mov     [rsp+8C0h+rop], 0CC0020h; rop
0x18000d727  mov     edi, eax
0x18000d729  mov     [rsp+8C0h+y1], 0; y1
0x18000d731  mov     [rsp+8C0h+x1], 0; x1
0x18000d739  mov     [rsp+8C0h+hdcSrc], rcx; hdcSrc
0x18000d73e  mov     ecx, dword ptr [rsp+8C0h+pv+8]
0x18000d742  mov     dword ptr [rsp+8C0h+lpBits], ecx; cy
0x18000d746  mov     rcx, cs:?g_hdcDst@@3PEAUHDC__@@EA; hdc
0x18000d74d  call    cs:__imp_BitBlt
0x18000d753  mov     rcx, cs:?g_hdcSrc@@3PEAUHDC__@@EA; hdc
0x18000d75a  mov     edx, 0FFFFFFh; color
0x18000d75f  call    cs:__imp_SetBkColor
0x18000d765  mov     rcx, cs:?g_hdcSrc@@3PEAUHDC__@@EA; hdc
0x18000d76c  xor     edx, edx; color
0x18000d76e  call    cs:__imp_SetTextColor
0x18000d774  mov     rcx, cs:?g_hdcDst@@3PEAUHDC__@@EA; HDC__ * g_hdcDst
0x18000d77b  xor     r8d, r8d; y
0x18000d77e  mov     r9d, dword ptr [rsp+8C0h+pv+4]; cx
0x18000d783  xor     edx, edx; x
0x18000d785  mov     [rsp+8C0h+rop], 220326h; rop
0x18000d78d  mov     ebx, eax
0x18000d78f  mov     [rsp+8C0h+y1], 0; y1
0x18000d797  mov     [rsp+8C0h+x1], 0; x1
0x18000d79f  mov     [rsp+8C0h+hdcSrc], rcx; int
0x18000d7a4  mov     ecx, dword ptr [rsp+8C0h+pv+8]
0x18000d7a8  mov     dword ptr [rsp+8C0h+lpBits], ecx; int
0x18000d7ac  mov     rcx, cs:?g_hdcSrc@@3PEAUHDC__@@EA; hdc
0x18000d7b3  call    cs:__imp_BitBlt
0x18000d7b9  mov     rcx, cs:?g_hdcSrc@@3PEAUHDC__@@EA; hdc
0x18000d7c0  mov     edx, edi; color
0x18000d7c2  call    cs:__imp_SetBkColor
0x18000d7c8  mov     rcx, cs:?g_hdcSrc@@3PEAUHDC__@@EA; hdc
0x18000d7cf  mov     edx, ebx; color
0x18000d7d1  call    cs:__imp_SetTextColor
0x18000d7d7  xor     ebx, ebx
0x18000d7d9  cmp     word ptr [rsp+8C0h+var_860+2], 8
0x18000d7df  jbe     loc_18000D8FB
0x18000d7e5  cmp     cs:?g_hbmSrc@@3PEAUHBITMAP__@@EA, rbx; HBITMAP__ * g_hbmSrc
0x18000d7ec  jz      short loc_18000D809
0x18000d7ee  mov     rdx, cs:?g_hbmDcDeselect@@3PEAUHBITMAP__@@EA; h
0x18000d7f5  mov     rcx, cs:?g_hdcSrc@@3PEAUHDC__@@EA; hdc
0x18000d7fc  call    cs:__imp_SelectObject
0x18000d802  mov     cs:?g_hbmSrc@@3PEAUHBITMAP__@@EA, rbx; HBITMAP__ * g_hbmSrc
0x18000d809  xor     ecx, ecx; HBITMAP
0x18000d80b  call    ?SelectDstBitmap@CImageList@@KAXPEAUHBITMAP__@@@Z; CImageList::SelectDstBitmap(HBITMAP__ *)
0x18000d810  mov     eax, dword ptr [rsp+8C0h+pv+4]
0x18000d814  mov     r8, r14; HBITMAP
0x18000d817  cdq
0x18000d818  mov     qword ptr [rsp+8C0h+x1], r13; int *
0x18000d81d  idiv    dword ptr [r12+80h]
0x18000d825  mov     rdx, r15; HBITMAP
0x18000d828  mov     rcx, r12; this
0x18000d82b  mov     r9d, eax; int
0x18000d82e  call    ?_Add@CImageList@@IEAAJPEAUHBITMAP__@@0HHHPEAH@Z; CImageList::_Add(HBITMAP__ *,HBITMAP__ *,int,int,int,int *)
0x18000d833  lea     rcx, g_csDll; lpCriticalSection
0x18000d83a  mov     ebx, eax
0x18000d83c  call    cs:__imp_LeaveCriticalSection
0x18000d842  mov     rcx, r14; ho
0x18000d845  call    cs:__imp_DeleteObject
0x18000d84b  mov     eax, ebx
0x18000d84d  mov     rcx, [rbp+7C0h+var_50]
0x18000d854  xor     rcx, rsp; StackCookie
0x18000d857  call    __security_check_cookie
0x18000d85c  add     rsp, 888h
0x18000d863  pop     r15
0x18000d865  pop     r14
0x18000d867  pop     r13
0x18000d869  pop     r12
0x18000d86b  pop     rdi
0x18000d86c  pop     rsi
0x18000d86d  pop     rbx
0x18000d86e  pop     rbp
0x18000d86f  retn
0x18000d870  cmp     word ptr [rsp+8C0h+var_860+2], 8
0x18000d876  ja      loc_18000D6FF
0x18000d87c  mov     rcx, cs:?g_hdcSrc@@3PEAUHDC__@@EA; hdc
0x18000d883  lea     r9, [rsp+8C0h+prgbq]; prgbq
0x18000d888  xor     edx, edx; iStart
0x18000d88a  mov     r8d, 100h; cEntries
0x18000d890  call    cs:__imp_GetDIBColorTable
0x18000d896  xor     r9d, r9d
0x18000d899  mov     esi, eax
0x18000d89b  test    eax, eax
0x18000d89d  jle     short loc_18000D8DD
0x18000d89f  mov     ecx, ebx
0x18000d8a1  movzx   r8d, bx
0x18000d8a5  shr     ecx, 10h
0x18000d8a8  and     r8d, 0FFFFFF00h
0x18000d8af  movzx   edx, cl
0x18000d8b2  movzx   ecx, bl
0x18000d8b5  or      r8d, edx
0x18000d8b8  shl     ecx, 10h
0x18000d8bb  or      r8d, ecx
0x18000d8be  xor     eax, eax
0x18000d8c0  mov     ecx, 0FFFFFFh
0x18000d8c5  cmp     dword ptr [rsp+r9*4+8C0h+prgbq.rgbBlue], r8d
0x18000d8ca  cmovnz  ecx, eax
0x18000d8cd  mov     dword ptr [rbp+r9*4+7C0h+var_450.rgbBlue], ecx
0x18000d8d5  add     r9d, edi
0x18000d8d8  cmp     r9d, esi
0x18000d8db  jl      short loc_18000D8BE
0x18000d8dd  mov     rcx, cs:?g_hdcSrc@@3PEAUHDC__@@EA; hdc
0x18000d8e4  lea     r9, [rbp+7C0h+var_450]; prgbq
0x18000d8eb  mov     r8d, esi; cEntries
0x18000d8ee  xor     edx, edx; iStart
0x18000d8f0  call    cs:__imp_SetDIBColorTable
0x18000d8f6  jmp     loc_18000D6FF
0x18000d8fb  cmp     qword ptr [rsp+8C0h+var_860+8], rbx
0x18000d900  jz      loc_18000D7E5
0x18000d906  mov     rcx, cs:?g_hdcSrc@@3PEAUHDC__@@EA; hdc
0x18000d90d  lea     r9, [rsp+8C0h+prgbq]; prgbq
0x18000d912  mov     r8d, esi; cEntries
0x18000d915  xor     edx, edx; iStart
0x18000d917  call    cs:__imp_SetDIBColorTable
0x18000d91d  jmp     loc_18000D7E5
0x18000d922  mov     rcx, cs:?g_hdcSrc@@3PEAUHDC__@@EA; hdc
0x18000d929  xor     r8d, r8d; y
0x18000d92c  xor     edx, edx; x
0x18000d92e  call    cs:__imp_GetPixel
0x18000d934  mov     ebx, eax
0x18000d936  jmp     loc_18000D6F4
0x18000d93b  mov     eax, 80070057h
0x18000d940  jmp     loc_18000D84D
0x18000d945  mov     eax, 8007000Eh
0x18000d94a  jmp     loc_18000D84D
```
