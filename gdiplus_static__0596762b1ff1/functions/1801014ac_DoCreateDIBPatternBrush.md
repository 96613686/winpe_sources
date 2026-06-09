# DoCreateDIBPatternBrush

- ea: `0x1801014ac`
- end: `0x1801016c5`
- name: `DoCreateDIBPatternBrush`
- size: `537`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1801013c0`

## callees

- `0x1800c6428`
- `0x1801014ac`
- `0x180105d40`
- `0x180146f88`
- `0x18014a0e0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180101611`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180101611`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180101695`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180101695`
- `GDI32!CreateDIBitmap` at `0x180101592`
- `GDI32!CreateDIBitmap` at `0x180101592`
- `GDI32!CreateDIBPatternBrushPt` at `0x18010151d`
- `GDI32!CreateDIBPatternBrushPt` at `0x18010151d`
- `GDI32!GetDIBits` at `0x180101646`
- `GDI32!GetDIBits` at `0x180101646`
- `GDI32!DeleteObject` at `0x180101681`
- `GDI32!DeleteObject` at `0x180101681`

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
0x1801014ac  push    rbp
0x1801014ae  push    rbx
0x1801014af  push    rsi
0x1801014b0  push    rdi
0x1801014b1  push    r12
0x1801014b3  push    r13
0x1801014b5  push    r14
0x1801014b7  push    r15
0x1801014b9  lea     rbp, [rsp-7]
0x1801014be  sub     rsp, 88h
0x1801014c5  mov     rax, cs:__security_cookie
0x1801014cc  xor     rax, rsp
0x1801014cf  mov     [rbp+3Fh+var_48], rax
0x1801014d3  mov     r13, [rbp+3Fh+pjBits]
0x1801014d7  xorps   xmm0, xmm0
0x1801014da  mov     r12d, [rbp+3Fh+iUsage]
0x1801014de  mov     rsi, r8
0x1801014e1  movups  xmmword ptr [rbp+3Fh+bmi.bmiHeader.biCompression], xmm0
0x1801014e5  xor     r15d, r15d
0x1801014e8  mov     [rbp+3Fh+var_80], r9d
0x1801014ec  mov     r14, rcx
0x1801014ef  movups  xmmword ptr [rbp+3Fh+bmi.bmiHeader.biSize], xmm0
0x1801014f3  lea     r8d, [r15+2]
0x1801014f7  movups  xmmword ptr [rbp+3Fh+bmi.bmiHeader.biYPelsPerMeter], xmm0
0x1801014fb  call    iAllocateW16Handle
0x180101500  cmp     eax, 0FFFFFFFFh
0x180101503  jz      loc_1801016A1
0x180101509  mov     rbx, [r14+1A0h]
0x180101510  mov     edx, r12d; iUsage
0x180101513  movsxd  rdi, eax
0x180101516  mov     rcx, rsi; lpPackedDIB
0x180101519  shl     rdi, 5
0x18010151d  call    cs:__imp_CreateDIBPatternBrushPt
0x180101524  nop     dword ptr [rax+rax+00h]
0x180101529  mov     [rdi+rbx+8], rax
0x18010152e  lea     eax, [r15+1]
0x180101532  cmp     [rsi+0Ch], ax
0x180101536  jnz     short loc_180101578
0x180101538  movzx   eax, word ptr [rsi+0Eh]
0x18010153c  mov     ecx, 0FFEFh
0x180101541  sub     ax, 10h
0x180101545  test    cx, ax
0x180101548  jz      short loc_180101578
0x18010154a  mov     eax, [rbp+3Fh+arg_28]
0x18010154d  mov     r9, r13
0x180101550  mov     r8d, [rbp+3Fh+var_80]
0x180101554  mov     rdx, rsi
0x180101557  mov     word ptr [rsp+0C0h+usage], 5
0x18010155e  mov     rcx, r14
0x180101561  mov     word ptr [rsp+0C0h+var_98], r12w
0x180101567  mov     dword ptr [rsp+0C0h+pbmi], eax
0x18010156b  call    bEmitWin16CreateDIBPatternBrush
0x180101570  mov     r15d, eax
0x180101573  jmp     loc_1801016A1
0x180101578  mov     rcx, [r14+28h]; hdc
0x18010157c  mov     r9, r13; pjBits
0x18010157f  mov     [rsp+0C0h+var_98], r12d; iUsage
0x180101584  mov     r8d, 6; flInit
0x18010158a  mov     rdx, rsi; pbmih
0x18010158d  mov     [rsp+0C0h+pbmi], rsi; pbmi
0x180101592  call    cs:__imp_CreateDIBitmap
0x180101599  nop     dword ptr [rax+rax+00h]
0x18010159e  xor     r12d, r12d
0x1801015a1  mov     rdi, rax
0x1801015a4  test    rax, rax
0x1801015a7  jz      loc_1801016A1
0x1801015ad  mov     ecx, [rsi]
0x1801015af  lea     edx, [r12+1]
0x1801015b4  mov     r8, [rsi+18h]
0x1801015b8  mov     ebx, r12d
0x1801015bb  mov     r10d, [rsi+8]
0x1801015bf  mov     [rbp+3Fh+bmi.bmiHeader.biSize], ecx
0x1801015c2  mov     ecx, [rsi+4]
0x1801015c5  mov     qword ptr [rbp+3Fh+bmi.bmiHeader.biXPelsPerMeter], r8
0x1801015c9  lea     r8d, [r12+18h]
0x1801015ce  mov     [rbp+3Fh+bmi.bmiHeader.biWidth], ecx
0x1801015d1  mov     [rbp+3Fh+bmi.bmiHeader.biHeight], r10d
0x1801015d5  mov     qword ptr [rbp+3Fh+bmi.bmiHeader.biPlanes], 180001h
0x1801015dd  mov     [rbp+3Fh+bmi.bmiHeader.biSizeImage], r12d
0x1801015e1  mov     qword ptr [rbp+3Fh+bmi.bmiHeader.biClrUsed], r12
0x1801015e5  call    GetCJScan
0x1801015ea  test    eax, eax
0x1801015ec  jz      loc_18010167E
0x1801015f2  mov     edx, r10d
0x1801015f5  mov     eax, eax
0x1801015f7  neg     edx
0x1801015f9  cmovs   edx, r10d
0x1801015fd  imul    rdx, rax
0x180101601  mov     eax, 0FFFFFFFFh
0x180101606  cmp     rdx, rax
0x180101609  ja      short loc_18010167E
0x18010160b  mov     esi, edx
0x18010160d  xor     ecx, ecx; uFlags
0x18010160f  mov     edx, edx; uBytes
0x180101611  call    cs:__imp_LocalAlloc
0x180101618  nop     dword ptr [rax+rax+00h]
0x18010161d  mov     rbx, rax
0x180101620  test    rax, rax
0x180101623  jz      short loc_18010167E
0x180101625  mov     r9d, [rbp+3Fh+bmi.bmiHeader.biHeight]; cLines
0x180101629  lea     rax, [rbp+3Fh+bmi]
0x18010162d  mov     rcx, [r14+28h]; hdc
0x180101631  xor     r8d, r8d; start
0x180101634  mov     [rsp+0C0h+usage], r12d; usage
0x180101639  mov     rdx, rdi; hbm
0x18010163c  mov     qword ptr [rsp+0C0h+var_98], rax; lpbmi
0x180101641  mov     [rsp+0C0h+pbmi], rbx; lpvBits
0x180101646  call    cs:__imp_GetDIBits
0x18010164d  nop     dword ptr [rax+rax+00h]
0x180101652  test    eax, eax
0x180101654  jz      short loc_18010167E
0x180101656  mov     word ptr [rsp+0C0h+usage], 5
0x18010165d  lea     r8d, [r12+28h]
0x180101662  mov     word ptr [rsp+0C0h+var_98], r12w
0x180101668  lea     rdx, [rbp+3Fh+bmi]
0x18010166c  mov     r9, rbx
0x18010166f  mov     dword ptr [rsp+0C0h+pbmi], esi
0x180101673  mov     rcx, r14
0x180101676  call    bEmitWin16CreateDIBPatternBrush
0x18010167b  mov     r15d, eax
0x18010167e  mov     rcx, rdi; ho
0x180101681  call    cs:__imp_DeleteObject
0x180101688  nop     dword ptr [rax+rax+00h]
0x18010168d  test    rbx, rbx
0x180101690  jz      short loc_1801016A1
0x180101692  mov     rcx, rbx; hMem
0x180101695  call    cs:__imp_LocalFree
0x18010169c  nop     dword ptr [rax+rax+00h]
0x1801016a1  mov     eax, r15d
0x1801016a4  mov     rcx, [rbp+3Fh+var_48]
0x1801016a8  xor     rcx, rsp; StackCookie
0x1801016ab  call    __security_check_cookie
0x1801016b0  add     rsp, 88h
0x1801016b7  pop     r15
0x1801016b9  pop     r14
0x1801016bb  pop     r13
0x1801016bd  pop     r12
0x1801016bf  pop     rdi
0x1801016c0  pop     rsi
0x1801016c1  pop     rbx
0x1801016c2  pop     rbp
0x1801016c3  retn
```
