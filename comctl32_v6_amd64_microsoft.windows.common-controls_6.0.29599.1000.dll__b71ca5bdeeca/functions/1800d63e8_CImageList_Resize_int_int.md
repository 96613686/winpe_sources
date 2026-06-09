# CImageList::_Resize(int,int)

- ea: `0x1800d63e8`
- end: `0x1800d6764`
- name: `?_Resize@CImageList@@IEAAJHH@Z`
- size: `892`
- prototype: `__int64 __fastcall(CImageList *__hidden this, int, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180128d80`

## callees

- `0x1800107ec`
- `0x180011bb8`
- `0x180011c10`
- `0x18008e034`
- `0x18008e190`
- `0x1800a8e1c`
- `0x1800d63e8`
- `0x180114520`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d6710`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d6710`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d65ce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d65ce`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x1800d6471`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x1800d648b`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x1800d64a4`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x1800d64be`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x1800d6508`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x1800d651a`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x1800d6471`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x1800d648b`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x1800d64a4`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x1800d64be`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x1800d6508`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x1800d651a`
- `GDI32!DeleteObject` at `0x1800d65b1`
- `GDI32!DeleteObject` at `0x1800d65ba`
- `GDI32!DeleteObject` at `0x1800d65b1`
- `GDI32!DeleteObject` at `0x1800d65ba`
- `GDI32!SelectObject` at `0x1800d66b5`
- `GDI32!SelectObject` at `0x1800d66cc`
- `GDI32!SelectObject` at `0x1800d66e1`
- `GDI32!SelectObject` at `0x1800d66b5`
- `GDI32!SelectObject` at `0x1800d66cc`
- `GDI32!SelectObject` at `0x1800d66e1`
- `GDI32!CreateBitmap` at `0x1800d656e`
- `GDI32!CreateBitmap` at `0x1800d656e`
- `GDI32!StretchBlt` at `0x1800d6633`
- `GDI32!StretchBlt` at `0x1800d6680`
- `GDI32!StretchBlt` at `0x1800d6633`
- `GDI32!StretchBlt` at `0x1800d6680`
- `GDI32!SetStretchBltMode` at `0x1800d65de`
- `GDI32!SetStretchBltMode` at `0x1800d6691`
- `GDI32!SetStretchBltMode` at `0x1800d65de`
- `GDI32!SetStretchBltMode` at `0x1800d6691`

## pseudocode

```c
__int64 __fastcall CImageList::_Resize(CImageList *this, int a2, int a3)
{
  int wSrc; // r13d
  int v7; // r14d
  __int64 v8; // rbx
  int hSrc; // r12d
  int v10; // r14d
  int v11; // eax
  int v12; // ecx
  int v13; // eax
  int v14; // ecx
  int v15; // eax
  int v16; // ecx
  int i; // ebp
  int v18; // ebx
  int v19; // eax
  bool v20; // zf
  HBITMAP Bitmap; // rbx
  unsigned int v22; // ebp
  HBITMAP v23; // r15
  int v24; // eax
  HDC v25; // rcx
  HBITMAP v26; // rcx
  HBITMAP v27; // rcx
  int mode; // [rsp+60h] [rbp-68h] BYREF
  int nNumber; // [rsp+64h] [rbp-64h] BYREF
  struct tagRGBQUAD *v30; // [rsp+68h] [rbp-60h] BYREF

  if ( a2 <= 0 || a3 <= 0 )
    return 2147942487LL;
  wSrc = *((_DWORD *)this + 32);
  if ( *((_QWORD *)this + 16) == __PAIR64__(a3, a2) )
    return 1;
  v7 = *((_DWORD *)this + 30);
  v8 = 0;
  *((_DWORD *)this + 32) = a2;
  hSrc = *((_DWORD *)this + 33) * v7;
  v10 = a3 * v7;
  *((_DWORD *)this + 33) = a3;
  do
  {
    v11 = MulDiv(*((_DWORD *)this + v8 + 67), a2, wSrc);
    v12 = *((_DWORD *)this + v8 + 82);
    *((_DWORD *)this + v8 + 67) = v11;
    v13 = MulDiv(v12, v10, hSrc);
    v14 = *((_DWORD *)this + v8 + 97);
    *((_DWORD *)this + v8 + 82) = v13;
    v15 = MulDiv(v14, a2, wSrc);
    v16 = *((_DWORD *)this + v8 + 112);
    *((_DWORD *)this + v8 + 97) = v15;
    *((_DWORD *)this + v8++ + 112) = MulDiv(v16, v10, hSrc);
  }
  while ( v8 != 15 );
  for ( i = 0; i < *((_DWORD *)this + 29); ++i )
  {
    nNumber = 0;
    mode = 0;
    if ( (int)CImageList::_GetOriginalSize(this, i, &nNumber, &mode) >= 0 )
    {
      v18 = MulDiv(nNumber, a2, wSrc);
      v19 = MulDiv(mode, v10, hSrc);
      CImageList::_SetOriginalSize(this, i, v18, v19);
    }
    CImageList::_SetItemMaskedFlags(this, i, 2u, 2u);
  }
  v20 = (*((_BYTE *)this + 136) & 1) == 0;
  Bitmap = 0;
  v30 = 0;
  if ( v20 || (Bitmap = CreateBitmap(a2, v10, 1u, 1u, 0)) != 0 )
  {
    v23 = CImageList::_CreateBitmap(this, a2, v10, &v30);
    if ( v23 )
    {
      v22 = 0;
      EnterCriticalSection(&g_csDll);
      v24 = SetStretchBltMode(g_hdcDst, 3);
      v20 = (*((_BYTE *)this + 136) & 1) == 0;
      mode = v24;
      if ( !v20 )
      {
        CImageList::SelectDstBitmap(Bitmap);
        StretchBlt(g_hdcDst, 0, 0, a2, v10, *((HDC *)this + 25), 0, 0, wSrc, hSrc, 0xCC0020u);
      }
      CImageList::SelectDstBitmap(v23);
      StretchBlt(g_hdcDst, 0, 0, a2, v10, *((HDC *)this + 24), 0, 0, wSrc, hSrc, 0xCC0020u);
      SetStretchBltMode(g_hdcDst, mode);
      CImageList::SelectDstBitmap(0);
      if ( g_hbmSrc )
      {
        SelectObject(g_hdcSrc, g_hbmDcDeselect);
        g_hbmSrc = 0;
      }
      SelectObject(*((HDC *)this + 24), v23);
      v25 = (HDC)*((_QWORD *)this + 25);
      if ( v25 )
        SelectObject(v25, Bitmap);
      v26 = (HBITMAP)*((_QWORD *)this + 21);
      if ( v26 )
        CImageList::_DeleteBitmap(v26);
      v27 = (HBITMAP)*((_QWORD *)this + 20);
      if ( v27 )
        CImageList::_DeleteBitmap(v27);
      LeaveCriticalSection(&g_csDll);
      *((_QWORD *)this + 23) = v30;
      *((_QWORD *)this + 21) = Bitmap;
      *((_QWORD *)this + 20) = v23;
      *((_DWORD *)this + 35) = -1;
    }
    else
    {
      v22 = -2147024882;
      if ( Bitmap )
      {
        DeleteObject(Bitmap);
        DeleteObject(Bitmap);
      }
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v22;
}

```

## disassembly

```asm
0x1800d63e8  push    rbx
0x1800d63ea  push    rbp
0x1800d63eb  push    rsi
0x1800d63ec  push    rdi
0x1800d63ed  push    r12
0x1800d63ef  push    r13
0x1800d63f1  push    r14
0x1800d63f3  push    r15
0x1800d63f5  sub     rsp, 88h
0x1800d63fc  mov     rax, cs:__security_cookie
0x1800d6403  xor     rax, rsp
0x1800d6406  mov     [rsp+0C8h+var_58], rax
0x1800d640b  xor     r15d, r15d
0x1800d640e  mov     esi, edx
0x1800d6410  mov     rdi, rcx
0x1800d6413  test    edx, edx
0x1800d6415  jle     loc_1800D673E
0x1800d641b  test    r8d, r8d
0x1800d641e  jle     loc_1800D673E
0x1800d6424  mov     r13d, [rcx+80h]
0x1800d642b  cmp     r13d, edx
0x1800d642e  jnz     short loc_1800D6442
0x1800d6430  cmp     [rcx+84h], r8d
0x1800d6437  jnz     short loc_1800D6442
0x1800d6439  lea     eax, [r15+1]
0x1800d643d  jmp     loc_1800D6743
0x1800d6442  mov     r14d, [rcx+78h]
0x1800d6446  mov     rbx, r15
0x1800d6449  mov     r12d, r14d
0x1800d644c  mov     [rcx+80h], esi
0x1800d6452  imul    r12d, [rcx+84h]
0x1800d645a  imul    r14d, r8d
0x1800d645e  mov     [rcx+84h], r8d
0x1800d6465  mov     ecx, [rdi+rbx*4+10Ch]; nNumber
0x1800d646c  mov     r8d, r13d; nDenominator
0x1800d646f  mov     edx, esi; nNumerator
0x1800d6471  call    cs:__imp_MulDiv
0x1800d6477  mov     ecx, [rdi+rbx*4+148h]; nNumber
0x1800d647e  mov     r8d, r12d; nDenominator
0x1800d6481  mov     edx, r14d; nNumerator
0x1800d6484  mov     [rdi+rbx*4+10Ch], eax
0x1800d648b  call    cs:__imp_MulDiv
0x1800d6491  mov     ecx, [rdi+rbx*4+184h]; nNumber
0x1800d6498  mov     r8d, r13d; nDenominator
0x1800d649b  mov     edx, esi; nNumerator
0x1800d649d  mov     [rdi+rbx*4+148h], eax
0x1800d64a4  call    cs:__imp_MulDiv
0x1800d64aa  mov     ecx, [rdi+rbx*4+1C0h]; nNumber
0x1800d64b1  mov     r8d, r12d; nDenominator
0x1800d64b4  mov     edx, r14d; nNumerator
0x1800d64b7  mov     [rdi+rbx*4+184h], eax
0x1800d64be  call    cs:__imp_MulDiv
0x1800d64c4  mov     [rdi+rbx*4+1C0h], eax
0x1800d64cb  inc     rbx
0x1800d64ce  cmp     rbx, 0Fh
0x1800d64d2  jnz     short loc_1800D6465
0x1800d64d4  mov     ebp, r15d
0x1800d64d7  cmp     [rdi+74h], r15d
0x1800d64db  jle     short loc_1800D654A
0x1800d64dd  lea     r9, [rsp+0C8h+mode]; int *
0x1800d64e2  mov     [rsp+0C8h+nNumber], r15d
0x1800d64e7  lea     r8, [rsp+0C8h+nNumber]; int *
0x1800d64ec  mov     [rsp+0C8h+mode], r15d
0x1800d64f1  mov     edx, ebp; int
0x1800d64f3  mov     rcx, rdi; this
0x1800d64f6  call    ?_GetOriginalSize@CImageList@@IEAAJHPEAH0@Z; CImageList::_GetOriginalSize(int,int *,int *)
0x1800d64fb  test    eax, eax
0x1800d64fd  js      short loc_1800D6530
0x1800d64ff  mov     ecx, [rsp+0C8h+nNumber]; nNumber
0x1800d6503  mov     r8d, r13d; nDenominator
0x1800d6506  mov     edx, esi; nNumerator
0x1800d6508  call    cs:__imp_MulDiv
0x1800d650e  mov     ecx, [rsp+0C8h+mode]; nNumber
0x1800d6512  mov     r8d, r12d; nDenominator
0x1800d6515  mov     edx, r14d; nNumerator
0x1800d6518  mov     ebx, eax
0x1800d651a  call    cs:__imp_MulDiv
0x1800d6520  mov     r8d, ebx; int
0x1800d6523  mov     edx, ebp; int
0x1800d6525  mov     r9d, eax; int
0x1800d6528  mov     rcx, rdi; this
0x1800d652b  call    ?_SetOriginalSize@CImageList@@IEAAJHHH@Z; CImageList::_SetOriginalSize(int,int,int)
0x1800d6530  mov     r9d, 2; unsigned int
0x1800d6536  mov     edx, ebp; int
0x1800d6538  mov     r8d, r9d; unsigned int
0x1800d653b  mov     rcx, rdi; this
0x1800d653e  call    ?_SetItemMaskedFlags@CImageList@@IEAAXHKK@Z; CImageList::_SetItemMaskedFlags(int,ulong,ulong)
0x1800d6543  inc     ebp
0x1800d6545  cmp     ebp, [rdi+74h]
0x1800d6548  jl      short loc_1800D64DD
0x1800d654a  test    byte ptr [rdi+88h], 1
0x1800d6551  mov     rbx, r15
0x1800d6554  mov     [rsp+0C8h+var_60], r15
0x1800d6559  jz      short loc_1800D6586
0x1800d655b  mov     r9d, 1; nBitCount
0x1800d6561  mov     [rsp+0C8h+lpBits], r15; lpBits
0x1800d6566  mov     r8d, r9d; nPlanes
0x1800d6569  mov     edx, r14d; nHeight
0x1800d656c  mov     ecx, esi; nWidth
0x1800d656e  call    cs:__imp_CreateBitmap
0x1800d6574  mov     rbx, rax
0x1800d6577  test    rax, rax
0x1800d657a  jnz     short loc_1800D6586
0x1800d657c  mov     ebp, 8007000Eh
0x1800d6581  jmp     loc_1800D673A
0x1800d6586  lea     r9, [rsp+0C8h+var_60]; struct tagRGBQUAD **
0x1800d658b  mov     r8d, r14d; int
0x1800d658e  mov     edx, esi; int
0x1800d6590  mov     rcx, rdi; this
0x1800d6593  call    ?_CreateBitmap@CImageList@@IEAAPEAUHBITMAP__@@HHPEAPEAUtagRGBQUAD@@@Z; CImageList::_CreateBitmap(int,int,tagRGBQUAD * *)
0x1800d6598  mov     r15, rax
0x1800d659b  test    rax, rax
0x1800d659e  jnz     short loc_1800D65C5
0x1800d65a0  mov     ebp, 8007000Eh
0x1800d65a5  test    rbx, rbx
0x1800d65a8  jz      loc_1800D673A
0x1800d65ae  mov     rcx, rbx; ho
0x1800d65b1  call    cs:__imp_DeleteObject
0x1800d65b7  mov     rcx, rbx; ho
0x1800d65ba  call    cs:__imp_DeleteObject
0x1800d65c0  jmp     loc_1800D673A
0x1800d65c5  lea     rcx, g_csDll; lpCriticalSection
0x1800d65cc  xor     ebp, ebp
0x1800d65ce  call    cs:__imp_EnterCriticalSection
0x1800d65d4  mov     rcx, cs:?g_hdcDst@@3PEAUHDC__@@EA; hdc
0x1800d65db  lea     edx, [rbp+3]; mode
0x1800d65de  call    cs:__imp_SetStretchBltMode
0x1800d65e4  test    byte ptr [rdi+88h], 1
0x1800d65eb  mov     [rsp+0C8h+mode], eax
0x1800d65ef  jz      short loc_1800D6639
0x1800d65f1  mov     rcx, rbx; HBITMAP
0x1800d65f4  call    ?SelectDstBitmap@CImageList@@KAXPEAUHBITMAP__@@@Z; CImageList::SelectDstBitmap(HBITMAP__ *)
0x1800d65f9  mov     rcx, [rdi+0C8h]
0x1800d6600  mov     r9d, esi; wDest
0x1800d6603  mov     [rsp+0C8h+rop], 0CC0020h; rop
0x1800d660b  xor     r8d, r8d; yDest
0x1800d660e  mov     [rsp+0C8h+hSrc], r12d; hSrc
0x1800d6613  xor     edx, edx; xDest
0x1800d6615  mov     [rsp+0C8h+wSrc], r13d; wSrc
0x1800d661a  mov     [rsp+0C8h+ySrc], ebp; ySrc
0x1800d661e  mov     [rsp+0C8h+xSrc], ebp; xSrc
0x1800d6622  mov     [rsp+0C8h+hdcSrc], rcx; hdcSrc
0x1800d6627  mov     rcx, cs:?g_hdcDst@@3PEAUHDC__@@EA; hdcDest
0x1800d662e  mov     dword ptr [rsp+0C8h+lpBits], r14d; hDest
0x1800d6633  call    cs:__imp_StretchBlt
0x1800d6639  mov     rcx, r15; HBITMAP
0x1800d663c  call    ?SelectDstBitmap@CImageList@@KAXPEAUHBITMAP__@@@Z; CImageList::SelectDstBitmap(HBITMAP__ *)
0x1800d6641  mov     rax, [rdi+0C0h]
0x1800d6648  mov     r9d, esi; wDest
0x1800d664b  mov     rcx, cs:?g_hdcDst@@3PEAUHDC__@@EA; hdcDest
0x1800d6652  xor     r8d, r8d; yDest
0x1800d6655  mov     [rsp+0C8h+rop], 0CC0020h; rop
0x1800d665d  xor     edx, edx; xDest
0x1800d665f  mov     [rsp+0C8h+hSrc], r12d; hSrc
0x1800d6664  xor     r12d, r12d
0x1800d6667  mov     [rsp+0C8h+wSrc], r13d; wSrc
0x1800d666c  mov     [rsp+0C8h+ySrc], r12d; ySrc
0x1800d6671  mov     [rsp+0C8h+xSrc], r12d; xSrc
0x1800d6676  mov     [rsp+0C8h+hdcSrc], rax; hdcSrc
0x1800d667b  mov     dword ptr [rsp+0C8h+lpBits], r14d; hDest
0x1800d6680  call    cs:__imp_StretchBlt
0x1800d6686  mov     edx, [rsp+0C8h+mode]; mode
0x1800d668a  mov     rcx, cs:?g_hdcDst@@3PEAUHDC__@@EA; hdc
0x1800d6691  call    cs:__imp_SetStretchBltMode
0x1800d6697  xor     ecx, ecx; HBITMAP
0x1800d6699  call    ?SelectDstBitmap@CImageList@@KAXPEAUHBITMAP__@@@Z; CImageList::SelectDstBitmap(HBITMAP__ *)
0x1800d669e  cmp     cs:?g_hbmSrc@@3PEAUHBITMAP__@@EA, r12; HBITMAP__ * g_hbmSrc
0x1800d66a5  jz      short loc_1800D66C2
0x1800d66a7  mov     rdx, cs:?g_hbmDcDeselect@@3PEAUHBITMAP__@@EA; h
0x1800d66ae  mov     rcx, cs:?g_hdcSrc@@3PEAUHDC__@@EA; hdc
0x1800d66b5  call    cs:__imp_SelectObject
0x1800d66bb  mov     cs:?g_hbmSrc@@3PEAUHBITMAP__@@EA, r12; HBITMAP__ * g_hbmSrc
0x1800d66c2  mov     rcx, [rdi+0C0h]; hdc
0x1800d66c9  mov     rdx, r15; h
0x1800d66cc  call    cs:__imp_SelectObject
0x1800d66d2  mov     rcx, [rdi+0C8h]; hdc
0x1800d66d9  test    rcx, rcx
0x1800d66dc  jz      short loc_1800D66E7
0x1800d66de  mov     rdx, rbx; h
0x1800d66e1  call    cs:__imp_SelectObject
0x1800d66e7  mov     rcx, [rdi+0A8h]; ho
0x1800d66ee  test    rcx, rcx
0x1800d66f1  jz      short loc_1800D66F8
0x1800d66f3  call    ?_DeleteBitmap@CImageList@@KAXPEAUHBITMAP__@@@Z; CImageList::_DeleteBitmap(HBITMAP__ *)
0x1800d66f8  mov     rcx, [rdi+0A0h]; ho
0x1800d66ff  test    rcx, rcx
0x1800d6702  jz      short loc_1800D6709
0x1800d6704  call    ?_DeleteBitmap@CImageList@@KAXPEAUHBITMAP__@@@Z; CImageList::_DeleteBitmap(HBITMAP__ *)
0x1800d6709  lea     rcx, g_csDll; lpCriticalSection
0x1800d6710  call    cs:__imp_LeaveCriticalSection
0x1800d6716  mov     rcx, [rsp+0C8h+var_60]
0x1800d671b  mov     [rdi+0B8h], rcx
0x1800d6722  mov     [rdi+0A8h], rbx
0x1800d6729  mov     [rdi+0A0h], r15
0x1800d6730  mov     dword ptr [rdi+8Ch], 0FFFFFFFFh
0x1800d673a  mov     eax, ebp
0x1800d673c  jmp     short loc_1800D6743
0x1800d673e  mov     eax, 80070057h
0x1800d6743  mov     rcx, [rsp+0C8h+var_58]
0x1800d6748  xor     rcx, rsp; StackCookie
0x1800d674b  call    __security_check_cookie
0x1800d6750  add     rsp, 88h
0x1800d6757  pop     r15
0x1800d6759  pop     r14
0x1800d675b  pop     r13
0x1800d675d  pop     r12
0x1800d675f  pop     rdi
0x1800d6760  pop     rsi
0x1800d6761  pop     rbp
0x1800d6762  pop     rbx
0x1800d6763  retn
```
