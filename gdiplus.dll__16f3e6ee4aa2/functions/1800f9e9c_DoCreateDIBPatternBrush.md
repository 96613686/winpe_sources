# DoCreateDIBPatternBrush

- ea: `0x1800f9e9c`
- end: `0x1800fa090`
- name: `DoCreateDIBPatternBrush`
- size: `500`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800f9dc0`

## callees

- `0x1800c27b0`
- `0x1800f9e9c`
- `0x1800fe680`
- `0x18013e810`
- `0x1801417a4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800f9ff5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800f9ff5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800fa067`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800fa067`
- `GDI32!CreateDIBitmap` at `0x1800f9f7c`
- `GDI32!CreateDIBitmap` at `0x1800f9f7c`
- `GDI32!CreateDIBPatternBrushPt` at `0x1800f9f0d`
- `GDI32!CreateDIBPatternBrushPt` at `0x1800f9f0d`
- `GDI32!GetDIBits` at `0x1800fa024`
- `GDI32!GetDIBits` at `0x1800fa024`
- `GDI32!DeleteObject` at `0x1800fa059`
- `GDI32!DeleteObject` at `0x1800fa059`

## pseudocode

```c
__int64 __fastcall DoCreateDIBPatternBrush(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        void *pjBits,
        int a6,
        UINT iUsage)
{
  unsigned int DIBPatternBrush; // r15d
  int W16Handle; // eax
  __int64 v11; // rbx
  HBITMAP DIBitmap; // rdi
  __int64 v13; // r8
  HLOCAL v14; // rbx
  LONG v15; // r10d
  __int64 v16; // rcx
  unsigned int CJScan; // eax
  int v18; // r10d
  __int64 v19; // rdx
  unsigned __int64 v20; // rdx
  int v21; // esi
  struct tagBITMAPINFO bmi; // [rsp+48h] [rbp-39h] BYREF

  DIBPatternBrush = 0;
  memset(&bmi, 0, sizeof(bmi));
  W16Handle = iAllocateW16Handle(a1, a2, 2);
  if ( W16Handle != -1 )
  {
    v11 = *(_QWORD *)(a1 + 416);
    *(_QWORD *)(32LL * W16Handle + v11 + 8) = CreateDIBPatternBrushPt((const void *)a3, iUsage);
    if ( *(_WORD *)(a3 + 12) == 1 && ((*(_WORD *)(a3 + 14) - 16) & 0xFFEF) != 0 )
    {
      return (unsigned int)bEmitWin16CreateDIBPatternBrush(a1, a3, a4, (_DWORD)pjBits, a6, iUsage, 5);
    }
    else
    {
      DIBitmap = CreateDIBitmap(
                   *(HDC *)(a1 + 40),
                   (const BITMAPINFOHEADER *)a3,
                   6u,
                   pjBits,
                   (const BITMAPINFO *)a3,
                   iUsage);
      if ( DIBitmap )
      {
        v13 = *(_QWORD *)(a3 + 24);
        v14 = 0;
        v15 = *(_DWORD *)(a3 + 8);
        bmi.bmiHeader.biSize = *(_DWORD *)a3;
        v16 = *(unsigned int *)(a3 + 4);
        *(_QWORD *)&bmi.bmiHeader.biXPelsPerMeter = v13;
        bmi.bmiHeader.biWidth = v16;
        bmi.bmiHeader.biHeight = v15;
        *(_QWORD *)&bmi.bmiHeader.biPlanes = 1572865;
        bmi.bmiHeader.biSizeImage = 0;
        *(_QWORD *)&bmi.bmiHeader.biClrUsed = 0;
        CJScan = GetCJScan(v16, 1, 24);
        if ( CJScan )
        {
          v19 = (unsigned int)-v18;
          if ( v18 > 0 )
            v19 = (unsigned int)v18;
          v20 = CJScan * v19;
          if ( v20 <= 0xFFFFFFFF )
          {
            v21 = v20;
            v14 = LocalAlloc(0, (unsigned int)v20);
            if ( v14 )
            {
              if ( GetDIBits(*(HDC *)(a1 + 40), DIBitmap, 0, bmi.bmiHeader.biHeight, v14, &bmi, 0) )
                DIBPatternBrush = bEmitWin16CreateDIBPatternBrush(a1, (unsigned int)&bmi, 40, (_DWORD)v14, v21, 0, 5);
            }
          }
        }
        DeleteObject(DIBitmap);
        if ( v14 )
          LocalFree(v14);
      }
    }
  }
  return DIBPatternBrush;
}

```

## disassembly

```asm
0x1800f9e9c  push    rbp
0x1800f9e9e  push    rbx
0x1800f9e9f  push    rsi
0x1800f9ea0  push    rdi
0x1800f9ea1  push    r12
0x1800f9ea3  push    r13
0x1800f9ea5  push    r14
0x1800f9ea7  push    r15
0x1800f9ea9  lea     rbp, [rsp-7]
0x1800f9eae  sub     rsp, 88h
0x1800f9eb5  mov     rax, cs:__security_cookie
0x1800f9ebc  xor     rax, rsp
0x1800f9ebf  mov     [rbp+3Fh+var_48], rax
0x1800f9ec3  mov     r13, [rbp+3Fh+pjBits]
0x1800f9ec7  xorps   xmm0, xmm0
0x1800f9eca  mov     r12d, [rbp+3Fh+iUsage]
0x1800f9ece  mov     rsi, r8
0x1800f9ed1  movups  xmmword ptr [rbp+3Fh+bmi.bmiHeader.biCompression], xmm0
0x1800f9ed5  xor     r15d, r15d
0x1800f9ed8  mov     [rbp+3Fh+var_80], r9d
0x1800f9edc  mov     r14, rcx
0x1800f9edf  movups  xmmword ptr [rbp+3Fh+bmi.bmiHeader.biSize], xmm0
0x1800f9ee3  lea     r8d, [r15+2]
0x1800f9ee7  movups  xmmword ptr [rbp+3Fh+bmi.bmiHeader.biYPelsPerMeter], xmm0
0x1800f9eeb  call    iAllocateW16Handle
0x1800f9ef0  cmp     eax, 0FFFFFFFFh
0x1800f9ef3  jz      loc_1800FA06D
0x1800f9ef9  mov     rbx, [r14+1A0h]
0x1800f9f00  mov     edx, r12d; iUsage
0x1800f9f03  movsxd  rdi, eax
0x1800f9f06  mov     rcx, rsi; lpPackedDIB
0x1800f9f09  shl     rdi, 5
0x1800f9f0d  call    cs:__imp_CreateDIBPatternBrushPt
0x1800f9f13  mov     [rdi+rbx+8], rax
0x1800f9f18  lea     eax, [r15+1]
0x1800f9f1c  cmp     [rsi+0Ch], ax
0x1800f9f20  jnz     short loc_1800F9F62
0x1800f9f22  movzx   eax, word ptr [rsi+0Eh]
0x1800f9f26  mov     ecx, 0FFEFh
0x1800f9f2b  sub     ax, 10h
0x1800f9f2f  test    cx, ax
0x1800f9f32  jz      short loc_1800F9F62
0x1800f9f34  mov     eax, [rbp+3Fh+arg_28]
0x1800f9f37  mov     r9, r13
0x1800f9f3a  mov     r8d, [rbp+3Fh+var_80]
0x1800f9f3e  mov     rdx, rsi
0x1800f9f41  mov     word ptr [rsp+0C0h+usage], 5
0x1800f9f48  mov     rcx, r14
0x1800f9f4b  mov     word ptr [rsp+0C0h+var_98], r12w
0x1800f9f51  mov     dword ptr [rsp+0C0h+pbmi], eax
0x1800f9f55  call    bEmitWin16CreateDIBPatternBrush
0x1800f9f5a  mov     r15d, eax
0x1800f9f5d  jmp     loc_1800FA06D
0x1800f9f62  mov     rcx, [r14+28h]; hdc
0x1800f9f66  mov     r9, r13; pjBits
0x1800f9f69  mov     [rsp+0C0h+var_98], r12d; iUsage
0x1800f9f6e  mov     r8d, 6; flInit
0x1800f9f74  mov     rdx, rsi; pbmih
0x1800f9f77  mov     [rsp+0C0h+pbmi], rsi; pbmi
0x1800f9f7c  call    cs:__imp_CreateDIBitmap
0x1800f9f82  xor     r12d, r12d
0x1800f9f85  mov     rdi, rax
0x1800f9f88  test    rax, rax
0x1800f9f8b  jz      loc_1800FA06D
0x1800f9f91  mov     ecx, [rsi]
0x1800f9f93  lea     edx, [r12+1]
0x1800f9f98  mov     r8, [rsi+18h]
0x1800f9f9c  mov     ebx, r12d
0x1800f9f9f  mov     r10d, [rsi+8]
0x1800f9fa3  mov     [rbp+3Fh+bmi.bmiHeader.biSize], ecx
0x1800f9fa6  mov     ecx, [rsi+4]
0x1800f9fa9  mov     qword ptr [rbp+3Fh+bmi.bmiHeader.biXPelsPerMeter], r8
0x1800f9fad  lea     r8d, [r12+18h]
0x1800f9fb2  mov     [rbp+3Fh+bmi.bmiHeader.biWidth], ecx
0x1800f9fb5  mov     [rbp+3Fh+bmi.bmiHeader.biHeight], r10d
0x1800f9fb9  mov     qword ptr [rbp+3Fh+bmi.bmiHeader.biPlanes], 180001h
0x1800f9fc1  mov     [rbp+3Fh+bmi.bmiHeader.biSizeImage], r12d
0x1800f9fc5  mov     qword ptr [rbp+3Fh+bmi.bmiHeader.biClrUsed], r12
0x1800f9fc9  call    GetCJScan
0x1800f9fce  test    eax, eax
0x1800f9fd0  jz      loc_1800FA056
0x1800f9fd6  mov     edx, r10d
0x1800f9fd9  mov     eax, eax
0x1800f9fdb  neg     edx
0x1800f9fdd  cmovs   edx, r10d
0x1800f9fe1  imul    rdx, rax
0x1800f9fe5  mov     eax, 0FFFFFFFFh
0x1800f9fea  cmp     rdx, rax
0x1800f9fed  ja      short loc_1800FA056
0x1800f9fef  mov     esi, edx
0x1800f9ff1  xor     ecx, ecx; uFlags
0x1800f9ff3  mov     edx, edx; uBytes
0x1800f9ff5  call    cs:__imp_LocalAlloc
0x1800f9ffb  mov     rbx, rax
0x1800f9ffe  test    rax, rax
0x1800fa001  jz      short loc_1800FA056
0x1800fa003  mov     r9d, [rbp+3Fh+bmi.bmiHeader.biHeight]; cLines
0x1800fa007  lea     rax, [rbp+3Fh+bmi]
0x1800fa00b  mov     rcx, [r14+28h]; hdc
0x1800fa00f  xor     r8d, r8d; start
0x1800fa012  mov     [rsp+0C0h+usage], r12d; usage
0x1800fa017  mov     rdx, rdi; hbm
0x1800fa01a  mov     qword ptr [rsp+0C0h+var_98], rax; lpbmi
0x1800fa01f  mov     [rsp+0C0h+pbmi], rbx; lpvBits
0x1800fa024  call    cs:__imp_GetDIBits
0x1800fa02a  test    eax, eax
0x1800fa02c  jz      short loc_1800FA056
0x1800fa02e  mov     word ptr [rsp+0C0h+usage], 5
0x1800fa035  lea     r8d, [r12+28h]
0x1800fa03a  mov     word ptr [rsp+0C0h+var_98], r12w
0x1800fa040  lea     rdx, [rbp+3Fh+bmi]
0x1800fa044  mov     r9, rbx
0x1800fa047  mov     dword ptr [rsp+0C0h+pbmi], esi
0x1800fa04b  mov     rcx, r14
0x1800fa04e  call    bEmitWin16CreateDIBPatternBrush
0x1800fa053  mov     r15d, eax
0x1800fa056  mov     rcx, rdi; ho
0x1800fa059  call    cs:__imp_DeleteObject
0x1800fa05f  test    rbx, rbx
0x1800fa062  jz      short loc_1800FA06D
0x1800fa064  mov     rcx, rbx; hMem
0x1800fa067  call    cs:__imp_LocalFree
0x1800fa06d  mov     eax, r15d
0x1800fa070  mov     rcx, [rbp+3Fh+var_48]
0x1800fa074  xor     rcx, rsp; StackCookie
0x1800fa077  call    __security_check_cookie
0x1800fa07c  add     rsp, 88h
0x1800fa083  pop     r15
0x1800fa085  pop     r14
0x1800fa087  pop     r13
0x1800fa089  pop     r12
0x1800fa08b  pop     rdi
0x1800fa08c  pop     rsi
0x1800fa08d  pop     rbx
0x1800fa08e  pop     rbp
0x1800fa08f  retn
```
