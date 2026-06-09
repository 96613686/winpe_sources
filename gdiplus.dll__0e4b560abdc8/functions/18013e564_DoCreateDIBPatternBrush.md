# DoCreateDIBPatternBrush

- ea: `0x18013e564`
- end: `0x18013e77f`
- name: `DoCreateDIBPatternBrush`
- size: `539`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18013f7c0`

## callees

- `0x1800b18f0`
- `0x1800e9380`
- `0x18013e564`
- `0x18013eb4c`
- `0x180143e38`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18013e6cb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18013e6cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013e74f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013e74f`
- `GDI32!CreateDIBitmap` at `0x18013e656`
- `GDI32!CreateDIBitmap` at `0x18013e656`
- `GDI32!CreateDIBPatternBrushPt` at `0x18013e5cf`
- `GDI32!CreateDIBPatternBrushPt` at `0x18013e5cf`
- `GDI32!GetDIBits` at `0x18013e700`
- `GDI32!GetDIBits` at `0x18013e700`
- `GDI32!DeleteObject` at `0x18013e73b`
- `GDI32!DeleteObject` at `0x18013e73b`

## pseudocode

```c
__int64 __fastcall DoCreateDIBPatternBrush(
        __int64 a1,
        __int64 a2,
        const BITMAPINFO *a3,
        int a4,
        void *pjBits,
        int a6,
        UINT iUsage)
{
  unsigned int DIBPatternBrush; // r15d
  HLOCAL v10; // rbx
  int W16Handle; // eax
  HBITMAP DIBitmap; // r14
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  unsigned int CJScan; // eax
  __int64 biHeight; // rdi
  unsigned __int64 v17; // rdi
  struct tagBITMAPINFO bmi; // [rsp+48h] [rbp-39h] BYREF

  DIBPatternBrush = 0;
  *(_QWORD *)&bmi.bmiHeader.biSize = 0;
  v10 = 0;
  bmi.bmiHeader.biHeight = 0;
  *(_QWORD *)&bmi.bmiHeader.biXPelsPerMeter = 0;
  bmi.bmiColors[0] = 0;
  W16Handle = iAllocateW16Handle(a1, a2, 2);
  if ( W16Handle != -1 )
  {
    *(_QWORD *)(32LL * W16Handle + *(_QWORD *)(a1 + 416) + 8) = CreateDIBPatternBrushPt(a3, iUsage);
    if ( a3->bmiHeader.biPlanes == 1 && ((a3->bmiHeader.biBitCount - 16) & 0xFFEF) != 0 )
    {
      return (unsigned int)bEmitWin16CreateDIBPatternBrush(a1, (_DWORD)a3, a4, (_DWORD)pjBits, a6, iUsage, 5);
    }
    else
    {
      DIBitmap = CreateDIBitmap(*(HDC *)(a1 + 40), &a3->bmiHeader, 6u, pjBits, a3, iUsage);
      if ( DIBitmap )
      {
        v13 = *(_OWORD *)&a3->bmiHeader.biSize;
        v14 = *(_OWORD *)&a3->bmiHeader.biCompression;
        *(_QWORD *)&bmi.bmiHeader.biClrUsed = 0;
        *(_OWORD *)&bmi.bmiHeader.biSize = v13;
        *(_QWORD *)&bmi.bmiHeader.biXPelsPerMeter = *((_QWORD *)&v14 + 1);
        *(_QWORD *)&bmi.bmiHeader.biPlanes = 1572865;
        bmi.bmiHeader.biSizeImage = 0;
        CJScan = GetCJScan(DWORD1(v13), 1, 24);
        if ( CJScan )
        {
          biHeight = (unsigned int)-bmi.bmiHeader.biHeight;
          if ( bmi.bmiHeader.biHeight > 0 )
            biHeight = (unsigned int)bmi.bmiHeader.biHeight;
          v17 = CJScan * biHeight;
          if ( v17 <= 0xFFFFFFFF )
          {
            v10 = LocalAlloc(0, (unsigned int)v17);
            if ( v10 )
            {
              if ( GetDIBits(*(HDC *)(a1 + 40), DIBitmap, 0, bmi.bmiHeader.biHeight, v10, &bmi, 0) )
                DIBPatternBrush = bEmitWin16CreateDIBPatternBrush(a1, (unsigned int)&bmi, 40, (_DWORD)v10, v17, 0, 5);
            }
          }
        }
        DeleteObject(DIBitmap);
        if ( v10 )
          LocalFree(v10);
      }
    }
  }
  return DIBPatternBrush;
}

```

## disassembly

```asm
0x18013e564  push    rbp
0x18013e566  push    rbx
0x18013e567  push    rsi
0x18013e568  push    rdi
0x18013e569  push    r12
0x18013e56b  push    r13
0x18013e56d  push    r14
0x18013e56f  push    r15
0x18013e571  lea     rbp, [rsp-7]
0x18013e576  sub     rsp, 88h
0x18013e57d  mov     rax, cs:__security_cookie
0x18013e584  xor     rax, rsp
0x18013e587  mov     [rbp+3Fh+var_48], rax
0x18013e58b  mov     r12, [rbp+3Fh+pjBits]
0x18013e58f  xor     r15d, r15d
0x18013e592  mov     r14d, [rbp+3Fh+iUsage]
0x18013e596  mov     rdi, r8
0x18013e599  mov     [rbp+3Fh+var_80], r9d
0x18013e59d  mov     rsi, rcx
0x18013e5a0  mov     qword ptr [rbp+3Fh+bmi.bmiHeader.biSize], r15
0x18013e5a4  mov     ebx, r15d
0x18013e5a7  lea     r8d, [r15+2]
0x18013e5ab  mov     [rbp+3Fh+bmi.bmiHeader.biHeight], r15d
0x18013e5af  mov     qword ptr [rbp+3Fh+bmi.bmiHeader.biXPelsPerMeter], r15
0x18013e5b3  mov     dword ptr [rbp+3Fh+bmi.bmiColors.rgbBlue], r15d
0x18013e5b7  call    iAllocateW16Handle
0x18013e5bc  movsxd  r13, eax
0x18013e5bf  cmp     r13d, 0FFFFFFFFh
0x18013e5c3  jz      loc_18013E75B
0x18013e5c9  mov     edx, r14d; iUsage
0x18013e5cc  mov     rcx, rdi; lpPackedDIB
0x18013e5cf  call    cs:__imp_CreateDIBPatternBrushPt
0x18013e5d6  nop     dword ptr [rax+rax+00h]
0x18013e5db  mov     rcx, r13
0x18013e5de  mov     rdx, rax
0x18013e5e1  mov     rax, [rsi+1A0h]
0x18013e5e8  lea     r13d, [r15+1]
0x18013e5ec  shl     rcx, 5
0x18013e5f0  mov     [rcx+rax+8], rdx
0x18013e5f5  cmp     [rdi+0Ch], r13w
0x18013e5fa  jnz     short loc_18013E63C
0x18013e5fc  movzx   eax, word ptr [rdi+0Eh]
0x18013e600  mov     ecx, 0FFEFh
0x18013e605  sub     ax, 10h
0x18013e609  test    cx, ax
0x18013e60c  jz      short loc_18013E63C
0x18013e60e  mov     eax, [rbp+3Fh+arg_28]
0x18013e611  mov     r9, r12
0x18013e614  mov     r8d, [rbp+3Fh+var_80]
0x18013e618  mov     rdx, rdi
0x18013e61b  mov     word ptr [rsp+0C0h+usage], 5
0x18013e622  mov     rcx, rsi
0x18013e625  mov     word ptr [rsp+0C0h+var_98], r14w
0x18013e62b  mov     dword ptr [rsp+0C0h+pbmi], eax
0x18013e62f  call    bEmitWin16CreateDIBPatternBrush
0x18013e634  mov     r15d, eax
0x18013e637  jmp     loc_18013E75B
0x18013e63c  mov     rcx, [rsi+28h]; hdc
0x18013e640  mov     r9, r12; pjBits
0x18013e643  mov     [rsp+0C0h+var_98], r14d; iUsage
0x18013e648  mov     r8d, 6; flInit
0x18013e64e  mov     rdx, rdi; pbmih
0x18013e651  mov     [rsp+0C0h+pbmi], rdi; pbmi
0x18013e656  call    cs:__imp_CreateDIBitmap
0x18013e65d  nop     dword ptr [rax+rax+00h]
0x18013e662  xor     r12d, r12d
0x18013e665  mov     r14, rax
0x18013e668  test    rax, rax
0x18013e66b  jz      loc_18013E75B
0x18013e671  movups  xmm0, xmmword ptr [rdi]
0x18013e674  lea     r8d, [r12+18h]
0x18013e679  mov     edx, r13d
0x18013e67c  movups  xmm1, xmmword ptr [rdi+10h]
0x18013e680  mov     qword ptr [rbp+3Fh+bmi.bmiHeader.biClrUsed], r12
0x18013e684  movups  xmmword ptr [rbp+3Fh+bmi.bmiHeader.biSize], xmm0
0x18013e688  mov     rcx, qword ptr [rbp+3Fh+bmi.bmiHeader.biSize]
0x18013e68c  movups  xmmword ptr [rbp-29h], xmm1
0x18013e690  shr     rcx, 20h
0x18013e694  mov     qword ptr [rbp+3Fh+bmi.bmiHeader.biPlanes], 180001h
0x18013e69c  mov     [rbp+3Fh+bmi.bmiHeader.biSizeImage], r12d
0x18013e6a0  call    GetCJScan
0x18013e6a5  mov     r8d, eax
0x18013e6a8  test    eax, eax
0x18013e6aa  jz      loc_18013E738
0x18013e6b0  mov     edi, [rbp+3Fh+bmi.bmiHeader.biHeight]
0x18013e6b3  mov     eax, 0FFFFFFFFh
0x18013e6b8  neg     edi
0x18013e6ba  cmovs   edi, [rbp+3Fh+bmi.bmiHeader.biHeight]
0x18013e6be  imul    rdi, r8
0x18013e6c2  cmp     rdi, rax
0x18013e6c5  ja      short loc_18013E738
0x18013e6c7  mov     edx, edi; uBytes
0x18013e6c9  xor     ecx, ecx; uFlags
0x18013e6cb  call    cs:__imp_LocalAlloc
0x18013e6d2  nop     dword ptr [rax+rax+00h]
0x18013e6d7  mov     rbx, rax
0x18013e6da  test    rax, rax
0x18013e6dd  jz      short loc_18013E738
0x18013e6df  mov     r9d, [rbp+3Fh+bmi.bmiHeader.biHeight]; cLines
0x18013e6e3  lea     rax, [rbp+3Fh+bmi]
0x18013e6e7  mov     rcx, [rsi+28h]; hdc
0x18013e6eb  xor     r8d, r8d; start
0x18013e6ee  mov     [rsp+0C0h+usage], r12d; usage
0x18013e6f3  mov     rdx, r14; hbm
0x18013e6f6  mov     qword ptr [rsp+0C0h+var_98], rax; lpbmi
0x18013e6fb  mov     [rsp+0C0h+pbmi], rbx; lpvBits
0x18013e700  call    cs:__imp_GetDIBits
0x18013e707  nop     dword ptr [rax+rax+00h]
0x18013e70c  test    eax, eax
0x18013e70e  jz      short loc_18013E738
0x18013e710  mov     word ptr [rsp+0C0h+usage], 5
0x18013e717  lea     r8d, [r12+28h]
0x18013e71c  mov     word ptr [rsp+0C0h+var_98], r12w
0x18013e722  lea     rdx, [rbp+3Fh+bmi]
0x18013e726  mov     r9, rbx
0x18013e729  mov     dword ptr [rsp+0C0h+pbmi], edi
0x18013e72d  mov     rcx, rsi
0x18013e730  call    bEmitWin16CreateDIBPatternBrush
0x18013e735  mov     r15d, eax
0x18013e738  mov     rcx, r14; ho
0x18013e73b  call    cs:__imp_DeleteObject
0x18013e742  nop     dword ptr [rax+rax+00h]
0x18013e747  test    rbx, rbx
0x18013e74a  jz      short loc_18013E75B
0x18013e74c  mov     rcx, rbx; hMem
0x18013e74f  call    cs:__imp_LocalFree
0x18013e756  nop     dword ptr [rax+rax+00h]
0x18013e75b  mov     eax, r15d
0x18013e75e  mov     rcx, [rbp+3Fh+var_48]
0x18013e762  xor     rcx, rsp; StackCookie
0x18013e765  call    __security_check_cookie
0x18013e76a  add     rsp, 88h
0x18013e771  pop     r15
0x18013e773  pop     r14
0x18013e775  pop     r13
0x18013e777  pop     r12
0x18013e779  pop     rdi
0x18013e77a  pop     rsi
0x18013e77b  pop     rbx
0x18013e77c  pop     rbp
0x18013e77d  retn
```
