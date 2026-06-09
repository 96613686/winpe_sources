# CImageList::_AddMasked(HBITMAP__ *,ulong,int *)

- ea: `0x18008373c`
- end: `0x180083a14`
- name: `?_AddMasked@CImageList@@QEAAJPEAUHBITMAP__@@KPEAH@Z`
- size: `728`
- prototype: `__int64 __fastcall(CImageList *__hidden this, HBITMAP, COLORREF color, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18007f470`

## callees

- `0x1800115f0`
- `0x180082a7c`
- `0x180082ad0`
- `0x1800835e8`
- `0x18008373c`

## import_xrefs

- `GDI32!SetDIBColorTable` at `0x1800838ac`
- `GDI32!SetDIBColorTable` at `0x1800839a3`
- `GDI32!SetDIBColorTable` at `0x1800838ac`
- `GDI32!SetDIBColorTable` at `0x1800839a3`
- `GDI32!BitBlt` at `0x180083904`
- `GDI32!BitBlt` at `0x18008396a`
- `GDI32!BitBlt` at `0x180083904`
- `GDI32!BitBlt` at `0x18008396a`
- `GDI32!DeleteObject` at `0x1800839dc`
- `GDI32!DeleteObject` at `0x1800839dc`
- `GDI32!GetObjectW` at `0x180083796`
- `GDI32!GetObjectW` at `0x180083796`
- `GDI32!GetDIBColorTable` at `0x180083845`
- `GDI32!GetDIBColorTable` at `0x180083845`
- `GDI32!SetBkColor` at `0x1800838bf`
- `GDI32!SetBkColor` at `0x180083916`
- `GDI32!SetBkColor` at `0x180083979`
- `GDI32!SetBkColor` at `0x1800838bf`
- `GDI32!SetBkColor` at `0x180083916`
- `GDI32!SetBkColor` at `0x180083979`
- `GDI32!SetTextColor` at `0x180083925`
- `GDI32!SetTextColor` at `0x180083988`
- `GDI32!SetTextColor` at `0x180083925`
- `GDI32!SetTextColor` at `0x180083988`
- `GDI32!CreateBitmap` at `0x1800837c7`
- `GDI32!CreateBitmap` at `0x1800837c7`
- `GDI32!GetPixel` at `0x180083812`
- `GDI32!GetPixel` at `0x180083812`
- `KERNEL32!EnterCriticalSection` at `0x1800837e8`
- `KERNEL32!EnterCriticalSection` at `0x1800837e8`
- `KERNEL32!LeaveCriticalSection` at `0x1800839e9`
- `KERNEL32!LeaveCriticalSection` at `0x1800839e9`

## pseudocode

```c
__int64 __fastcall CImageList::_AddMasked(CImageList *this, HBITMAP a2, COLORREF color, int *a4)
{
  HBITMAP Bitmap; // r14
  UINT v10; // esi
  int DIBColorTable; // eax
  __int64 v12; // r9
  RGBQUAD v13; // ecx
  COLORREF v14; // edi
  COLORREF v15; // ebx
  unsigned int v16; // ebx
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
  v10 = 0;
  EnterCriticalSection(&g_csDll);
  CImageList::SelectSrcBitmap(a2);
  CImageList::SelectDstBitmap(Bitmap);
  if ( color == -16777216 )
    color = GetPixel(g_hdcSrc, 0, 0);
  if ( *((_QWORD *)&v20 + 1) && WORD1(v20) <= 8u )
  {
    DIBColorTable = GetDIBColorTable(g_hdcSrc, 0, 0x100u, prgbq);
    v10 = DIBColorTable;
    if ( DIBColorTable <= 0 || (unsigned int)DIBColorTable > 0x100 )
    {
      v10 = 0;
    }
    else
    {
      v12 = 0;
      do
      {
        v13 = (RGBQUAD)0xFFFFFF;
        if ( *(_DWORD *)&prgbq[v12] != (((unsigned __int8)color << 16) | BYTE2(color) | color & 0xFF00) )
          v13 = 0;
        v22[v12] = v13;
        v12 = (unsigned int)(v12 + 1);
      }
      while ( (int)v12 < DIBColorTable );
      SetDIBColorTable(g_hdcSrc, 0, DIBColorTable, v22);
    }
  }
  v14 = SetBkColor(g_hdcSrc, color);
  BitBlt(g_hdcDst, 0, 0, SDWORD1(pv), SDWORD2(pv), g_hdcSrc, 0, 0, 0xCC0020u);
  SetBkColor(g_hdcSrc, 0xFFFFFFu);
  v15 = SetTextColor(g_hdcSrc, 0);
  BitBlt(g_hdcSrc, 0, 0, SDWORD1(pv), SDWORD2(pv), g_hdcDst, 0, 0, 0x220326u);
  SetBkColor(g_hdcSrc, v14);
  SetTextColor(g_hdcSrc, v15);
  if ( v10 )
    SetDIBColorTable(g_hdcSrc, 0, v10, prgbq);
  CImageList::SelectSrcBitmap(0);
  CImageList::SelectDstBitmap(0);
  v16 = CImageList::_Add(this, a2, Bitmap, SDWORD1(pv) / *((_DWORD *)this + 17), lpBits, hdcSrc, a4);
  DeleteObject(Bitmap);
  LeaveCriticalSection(&g_csDll);
  return v16;
}

```

## disassembly

```asm
0x18008373c  push    rbp
0x18008373e  push    rbx
0x18008373f  push    rsi
0x180083740  push    rdi
0x180083741  push    r12
0x180083743  push    r13
0x180083745  push    r14
0x180083747  push    r15
0x180083749  lea     rbp, [rsp-788h]
0x180083751  sub     rsp, 888h
0x180083758  mov     rax, cs:__security_cookie
0x18008375f  xor     rax, rsp
0x180083762  mov     [rbp+7C0h+var_50], rax
0x180083769  mov     r15, rdx
0x18008376c  mov     dword ptr [r9], 0FFFFFFFFh
0x180083773  xorps   xmm0, xmm0
0x180083776  mov     ebx, r8d
0x180083779  mov     r12, rcx
0x18008377c  lea     r8, [rsp+8C0h+pv]; pv
0x180083781  mov     rcx, r15; h
0x180083784  mov     edx, 20h ; ' '; c
0x180083789  mov     r13, r9
0x18008378c  movups  [rsp+8C0h+pv], xmm0
0x180083791  movups  [rsp+8C0h+var_860], xmm0
0x180083796  call    cs:__imp_GetObjectW
0x18008379c  cmp     eax, 20h ; ' '
0x18008379f  jz      short loc_1800837AB
0x1800837a1  mov     eax, 80070057h
0x1800837a6  jmp     loc_1800839F1
0x1800837ab  mov     edx, dword ptr [rsp+8C0h+pv+8]; nHeight
0x1800837af  mov     edi, 1
0x1800837b4  mov     ecx, dword ptr [rsp+8C0h+pv+4]; nWidth
0x1800837b8  mov     r9d, edi; nBitCount
0x1800837bb  mov     r8d, edi; nPlanes
0x1800837be  mov     [rsp+8C0h+lpBits], 0; lpBits
0x1800837c7  call    cs:__imp_CreateBitmap
0x1800837cd  mov     r14, rax
0x1800837d0  test    rax, rax
0x1800837d3  jnz     short loc_1800837DF
0x1800837d5  mov     eax, 8007000Eh
0x1800837da  jmp     loc_1800839F1
0x1800837df  lea     rcx, g_csDll; lpCriticalSection
0x1800837e6  xor     esi, esi
0x1800837e8  call    cs:__imp_EnterCriticalSection
0x1800837ee  mov     rcx, r15; HBITMAP
0x1800837f1  call    ?SelectSrcBitmap@CImageList@@SAXPEAUHBITMAP__@@@Z; CImageList::SelectSrcBitmap(HBITMAP__ *)
0x1800837f6  mov     rcx, r14; HBITMAP
0x1800837f9  call    ?SelectDstBitmap@CImageList@@SAXPEAUHBITMAP__@@@Z; CImageList::SelectDstBitmap(HBITMAP__ *)
0x1800837fe  cmp     ebx, 0FF000000h
0x180083804  jnz     short loc_18008381A
0x180083806  mov     rcx, cs:?g_hdcSrc@@3PEAUHDC__@@EA; hdc
0x18008380d  xor     r8d, r8d; y
0x180083810  xor     edx, edx; x
0x180083812  call    cs:__imp_GetPixel
0x180083818  mov     ebx, eax
0x18008381a  cmp     qword ptr [rsp+8C0h+var_860+8], rsi
0x18008381f  jz      loc_1800838B6
0x180083825  cmp     word ptr [rsp+8C0h+var_860+2], 8
0x18008382b  ja      loc_1800838B6
0x180083831  mov     rcx, cs:?g_hdcSrc@@3PEAUHDC__@@EA; hdc
0x180083838  lea     r9, [rsp+8C0h+prgbq]; prgbq
0x18008383d  xor     edx, edx; iStart
0x18008383f  mov     r8d, 100h; cEntries
0x180083845  call    cs:__imp_GetDIBColorTable
0x18008384b  mov     esi, eax
0x18008384d  test    eax, eax
0x18008384f  jle     short loc_1800838B4
0x180083851  cmp     eax, 100h
0x180083856  ja      short loc_1800838B4
0x180083858  mov     eax, ebx
0x18008385a  movzx   r8d, bx
0x18008385e  shr     eax, 10h
0x180083861  and     r8d, 0FFFFFF00h
0x180083868  movzx   ecx, al
0x18008386b  xor     r9d, r9d
0x18008386e  movzx   eax, bl
0x180083871  or      r8d, ecx
0x180083874  shl     eax, 10h
0x180083877  or      r8d, eax
0x18008387a  xor     eax, eax
0x18008387c  mov     ecx, 0FFFFFFh
0x180083881  cmp     dword ptr [rsp+r9*4+8C0h+prgbq.rgbBlue], r8d
0x180083886  cmovnz  ecx, eax
0x180083889  mov     dword ptr [rbp+r9*4+7C0h+var_450.rgbBlue], ecx
0x180083891  add     r9d, edi
0x180083894  cmp     r9d, esi
0x180083897  jl      short loc_18008387A
0x180083899  mov     rcx, cs:?g_hdcSrc@@3PEAUHDC__@@EA; hdc
0x1800838a0  lea     r9, [rbp+7C0h+var_450]; prgbq
0x1800838a7  mov     r8d, esi; cEntries
0x1800838aa  xor     edx, edx; iStart
0x1800838ac  call    cs:__imp_SetDIBColorTable
0x1800838b2  jmp     short loc_1800838B6
0x1800838b4  xor     esi, esi
0x1800838b6  mov     rcx, cs:?g_hdcSrc@@3PEAUHDC__@@EA; hdc
0x1800838bd  mov     edx, ebx; color
0x1800838bf  call    cs:__imp_SetBkColor
0x1800838c5  mov     rcx, cs:?g_hdcSrc@@3PEAUHDC__@@EA; HDC__ * g_hdcSrc
0x1800838cc  xor     r8d, r8d; y
0x1800838cf  mov     r9d, dword ptr [rsp+8C0h+pv+4]; cx
0x1800838d4  xor     edx, edx; x
0x1800838d6  mov     [rsp+8C0h+rop], 0CC0020h; rop
0x1800838de  mov     edi, eax
0x1800838e0  mov     [rsp+8C0h+y1], 0; y1
0x1800838e8  mov     [rsp+8C0h+x1], 0; x1
0x1800838f0  mov     [rsp+8C0h+hdcSrc], rcx; hdcSrc
0x1800838f5  mov     ecx, dword ptr [rsp+8C0h+pv+8]
0x1800838f9  mov     dword ptr [rsp+8C0h+lpBits], ecx; cy
0x1800838fd  mov     rcx, cs:?g_hdcDst@@3PEAUHDC__@@EA; hdc
0x180083904  call    cs:__imp_BitBlt
0x18008390a  mov     rcx, cs:?g_hdcSrc@@3PEAUHDC__@@EA; hdc
0x180083911  mov     edx, 0FFFFFFh; color
0x180083916  call    cs:__imp_SetBkColor
0x18008391c  mov     rcx, cs:?g_hdcSrc@@3PEAUHDC__@@EA; hdc
0x180083923  xor     edx, edx; color
0x180083925  call    cs:__imp_SetTextColor
0x18008392b  mov     rcx, cs:?g_hdcDst@@3PEAUHDC__@@EA; HDC__ * g_hdcDst
0x180083932  xor     r8d, r8d; y
0x180083935  mov     r9d, dword ptr [rsp+8C0h+pv+4]; cx
0x18008393a  xor     edx, edx; x
0x18008393c  mov     [rsp+8C0h+rop], 220326h; rop
0x180083944  mov     ebx, eax
0x180083946  mov     [rsp+8C0h+y1], 0; y1
0x18008394e  mov     [rsp+8C0h+x1], 0; x1
0x180083956  mov     [rsp+8C0h+hdcSrc], rcx; int
0x18008395b  mov     ecx, dword ptr [rsp+8C0h+pv+8]
0x18008395f  mov     dword ptr [rsp+8C0h+lpBits], ecx; int
0x180083963  mov     rcx, cs:?g_hdcSrc@@3PEAUHDC__@@EA; hdc
0x18008396a  call    cs:__imp_BitBlt
0x180083970  mov     rcx, cs:?g_hdcSrc@@3PEAUHDC__@@EA; hdc
0x180083977  mov     edx, edi; color
0x180083979  call    cs:__imp_SetBkColor
0x18008397f  mov     rcx, cs:?g_hdcSrc@@3PEAUHDC__@@EA; hdc
0x180083986  mov     edx, ebx; color
0x180083988  call    cs:__imp_SetTextColor
0x18008398e  test    esi, esi
0x180083990  jz      short loc_1800839A9
0x180083992  mov     rcx, cs:?g_hdcSrc@@3PEAUHDC__@@EA; hdc
0x180083999  lea     r9, [rsp+8C0h+prgbq]; prgbq
0x18008399e  mov     r8d, esi; cEntries
0x1800839a1  xor     edx, edx; iStart
0x1800839a3  call    cs:__imp_SetDIBColorTable
0x1800839a9  xor     ecx, ecx; HBITMAP
0x1800839ab  call    ?SelectSrcBitmap@CImageList@@SAXPEAUHBITMAP__@@@Z; CImageList::SelectSrcBitmap(HBITMAP__ *)
0x1800839b0  xor     ecx, ecx; HBITMAP
0x1800839b2  call    ?SelectDstBitmap@CImageList@@SAXPEAUHBITMAP__@@@Z; CImageList::SelectDstBitmap(HBITMAP__ *)
0x1800839b7  mov     eax, dword ptr [rsp+8C0h+pv+4]
0x1800839bb  mov     r8, r14; HBITMAP
0x1800839be  cdq
0x1800839bf  mov     qword ptr [rsp+8C0h+x1], r13; int *
0x1800839c4  idiv    dword ptr [r12+44h]
0x1800839c9  mov     rdx, r15; HBITMAP
0x1800839cc  mov     rcx, r12; this
0x1800839cf  mov     r9d, eax; int
0x1800839d2  call    ?_Add@CImageList@@QEAAJPEAUHBITMAP__@@0HHHPEAH@Z; CImageList::_Add(HBITMAP__ *,HBITMAP__ *,int,int,int,int *)
0x1800839d7  mov     rcx, r14; ho
0x1800839da  mov     ebx, eax
0x1800839dc  call    cs:__imp_DeleteObject
0x1800839e2  lea     rcx, g_csDll; lpCriticalSection
0x1800839e9  call    cs:__imp_LeaveCriticalSection
0x1800839ef  mov     eax, ebx
0x1800839f1  mov     rcx, [rbp+7C0h+var_50]
0x1800839f8  xor     rcx, rsp; StackCookie
0x1800839fb  call    __security_check_cookie
0x180083a00  add     rsp, 888h
0x180083a07  pop     r15
0x180083a09  pop     r14
0x180083a0b  pop     r13
0x180083a0d  pop     r12
0x180083a0f  pop     rdi
0x180083a10  pop     rsi
0x180083a11  pop     rbx
0x180083a12  pop     rbp
0x180083a13  retn
```
