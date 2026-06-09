# DoMaskBlt

- ea: `0x1800ff3c0`
- end: `0x1800ffa94`
- name: `DoMaskBlt`
- size: `1748`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, int cy, int, int x1, int y1, __int64, UINT, BITMAPINFO *, SIZE_T, void *, int, int, int, UINT, BITMAPINFO *, int, void *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800ff170`
- `0x1800fff20`

## callees

- `0x1800c6990`
- `0x1800c790c`
- `0x1800ff3c0`
- `0x180105d40`
- `0x1801495cc`
- `0x180149e00`
- `0x18014a120`

## import_xrefs

- `GDI32!BitBlt` at `0x1800ff73c`
- `GDI32!BitBlt` at `0x1800ff7d2`
- `GDI32!BitBlt` at `0x1800ff8e0`
- `GDI32!BitBlt` at `0x1800ff97a`
- `GDI32!BitBlt` at `0x1800ff73c`
- `GDI32!BitBlt` at `0x1800ff7d2`
- `GDI32!BitBlt` at `0x1800ff8e0`
- `GDI32!BitBlt` at `0x1800ff97a`
- `GDI32!CreateDIBitmap` at `0x1800ff6db`
- `GDI32!CreateDIBitmap` at `0x1800ff6db`
- `GDI32!StretchDIBits` at `0x1800ff676`
- `GDI32!StretchDIBits` at `0x1800ff676`
- `GDI32!SetWorldTransform` at `0x1800ff691`
- `GDI32!SetWorldTransform` at `0x1800ff691`
- `GDI32!SetGraphicsMode` at `0x1800ff546`
- `GDI32!SetGraphicsMode` at `0x1800ff546`
- `GDI32!SetDIBits` at `0x1800ff887`
- `GDI32!SetDIBits` at `0x1800ff887`
- `GDI32!CreateBitmap` at `0x1800ff568`
- `GDI32!CreateBitmap` at `0x1800ff568`
- `GDI32!PatBlt` at `0x1800ff5bc`
- `GDI32!PatBlt` at `0x1800ff5bc`
- `GDI32!DeleteDC` at `0x1800ffa25`
- `GDI32!DeleteDC` at `0x1800ffa64`
- `GDI32!DeleteDC` at `0x1800ffa25`
- `GDI32!DeleteDC` at `0x1800ffa64`
- `GDI32!SelectObject` at `0x1800ff587`
- `GDI32!SelectObject` at `0x1800ff6f9`
- `GDI32!SelectObject` at `0x1800ff847`
- `GDI32!SelectObject` at `0x1800ff8a1`
- `GDI32!SelectObject` at `0x1800ffa06`
- `GDI32!SelectObject` at `0x1800ffa3c`
- `GDI32!SelectObject` at `0x1800ff587`
- `GDI32!SelectObject` at `0x1800ff6f9`
- `GDI32!SelectObject` at `0x1800ff847`
- `GDI32!SelectObject` at `0x1800ff8a1`
- `GDI32!SelectObject` at `0x1800ffa06`
- `GDI32!SelectObject` at `0x1800ffa3c`
- `GDI32!CreateCompatibleDC` at `0x1800ff51c`
- `GDI32!CreateCompatibleDC` at `0x1800ff51c`
- `GDI32!DeleteObject` at `0x1800ffa16`
- `GDI32!DeleteObject` at `0x1800ffa50`
- `GDI32!DeleteObject` at `0x1800ffa16`
- `GDI32!DeleteObject` at `0x1800ffa50`

## pseudocode

```c
__int64 __fastcall DoMaskBlt(
        __int64 a1,
        int a2,
        int a3,
        int a4,
        int cy,
        unsigned int a6,
        int x1,
        int y1,
        XFORM *a9,
        UINT a10,
        BITMAPINFO *a11,
        SIZE_T a12,
        void *lpBits,
        int a14,
        int a15,
        int a16,
        UINT a17,
        BITMAPINFO *lpbmi,
        int a19,
        void *a20)
{
  HDC CompatibleDC; // rax
  HDC v23; // rsi
  HDC v24; // rbx
  void *v25; // r15
  HBITMAP v26; // r12
  HBITMAP Bitmap; // rax
  int v28; // edx
  int v29; // r8d
  HBITMAP DIBitmap; // rax
  int iUsage; // [rsp+58h] [rbp-A8h]
  SIZE_T v32; // [rsp+68h] [rbp-98h]
  HGDIOBJ h; // [rsp+80h] [rbp-80h]
  BOOL v36; // [rsp+90h] [rbp-70h]
  HGDIOBJ v38; // [rsp+D0h] [rbp-30h]
  HBITMAP ho; // [rsp+D8h] [rbp-28h]
  int v40; // [rsp+E0h] [rbp-20h] BYREF
  int v41; // [rsp+E4h] [rbp-1Ch]
  int v42; // [rsp+E8h] [rbp-18h]
  int v43; // [rsp+ECh] [rbp-14h]

  if ( !a19 )
  {
    LODWORD(v32) = a12;
    return DoStretchBlt(a1, cy, a6 & 0xFF0000, x1, y1, a4, cy, (__int64)a9, a10, a11, v32, lpBits, a14);
  }
  if ( ((a6 ^ (4 * a6)) & 0xCCCC0000) == 0 )
    return DoMaskBltNoSrc(a1, a2, a3, a4, cy, a6, (__int64)a9, a15, a16, a17, lpbmi, iUsage, a20);
  v36 = 0;
  CompatibleDC = CreateCompatibleDC(0);
  v23 = CompatibleDC;
  if ( CompatibleDC )
  {
    v24 = 0;
    v25 = 0;
    h = 0;
    v26 = 0;
    SetGraphicsMode(CompatibleDC, 2);
    Bitmap = CreateBitmap(a11->bmiHeader.biWidth, a11->bmiHeader.biHeight, 1u, 1u, 0);
    ho = Bitmap;
    if ( !Bitmap )
    {
LABEL_36:
      DeleteDC(v23);
      if ( v25 )
        SelectObject(v24, v25);
      if ( v26 )
        DeleteObject(v26);
      if ( v24 )
        DeleteDC(v24);
      return v36;
    }
    v38 = SelectObject(v23, Bitmap);
    if ( !v38 )
    {
LABEL_35:
      DeleteObject(ho);
      goto LABEL_36;
    }
    if ( PatBlt(v23, 0, 0, a11->bmiHeader.biWidth, a11->bmiHeader.biHeight, 0x42u) )
    {
      v40 = x1;
      v41 = y1;
      v42 = a4 + x1;
      v43 = y1 + cy;
      if ( !(unsigned int)bXformWorkhorse(&v40, 2, a9) )
        goto LABEL_33;
      v28 = v40;
      v29 = v41;
      if ( v40 > v42 )
        v28 = v42;
      if ( v41 > v43 )
        v29 = v43;
      if ( !StretchDIBits(
              v23,
              v28 - a15,
              v29 - a16,
              lpbmi->bmiHeader.biWidth,
              lpbmi->bmiHeader.biHeight,
              0,
              0,
              lpbmi->bmiHeader.biWidth,
              lpbmi->bmiHeader.biHeight,
              a20,
              lpbmi,
              a17,
              0xCC0020u)
        || !SetWorldTransform(v23, a9) )
      {
LABEL_33:
        v25 = 0;
        goto LABEL_34;
      }
      v24 = (HDC)hdcMakeCompatibleDC(a9);
      if ( !v24 )
      {
        v25 = 0;
        goto LABEL_34;
      }
      DIBitmap = CreateDIBitmap(*(HDC *)(a1 + 40), &a11->bmiHeader, 4u, lpBits, a11, a10);
      v26 = DIBitmap;
      if ( DIBitmap )
      {
        h = SelectObject(v24, DIBitmap);
        if ( !h )
        {
          v25 = 0;
          goto LABEL_34;
        }
        if ( BitBlt(v24, x1, y1, a4, cy, v23, x1, y1, 0x8800C6u)
          && (unsigned int)DoStretchBltAlt(
                             a1,
                             a2,
                             a3,
                             a4,
                             cy,
                             a6 & 0xCC0000 | 0x220000,
                             x1,
                             y1,
                             a4,
                             cy,
                             v24,
                             v26,
                             (__int64)a9)
          && BitBlt(v24, x1, y1, a4, cy, v23, x1, y1, 0xBB0226u)
          && (unsigned int)DoStretchBltAlt(
                             a1,
                             a2,
                             a3,
                             a4,
                             cy,
                             a6 & 0x330000 | 0x880000,
                             x1,
                             y1,
                             a4,
                             cy,
                             v24,
                             v26,
                             (__int64)a9)
          && SelectObject(v24, h)
          && SetDIBits(*(HDC *)(a1 + 40), v26, 0, a11->bmiHeader.biHeight, lpBits, a11, a10)
          && SelectObject(v24, v26)
          && BitBlt(v24, x1, y1, a4, cy, v23, x1, y1, 0x220326u)
          && (unsigned int)DoStretchBltAlt(
                             a1,
                             a2,
                             a3,
                             a4,
                             cy,
                             (a6 >> 8) & 0xCC0000 | 0x220000,
                             x1,
                             y1,
                             a4,
                             cy,
                             v24,
                             v26,
                             (__int64)a9)
          && BitBlt(v24, x1, y1, a4, cy, v23, x1, y1, 0xEE0086u) )
        {
          v36 = DoStretchBltAlt(
                  a1,
                  a2,
                  a3,
                  a4,
                  cy,
                  (a6 >> 8) & 0x330000 | 0x880000,
                  x1,
                  y1,
                  a4,
                  cy,
                  v24,
                  v26,
                  (__int64)a9) != 0;
        }
      }
      v25 = h;
    }
LABEL_34:
    SelectObject(v23, v38);
    goto LABEL_35;
  }
  return v36;
}

```

## disassembly

```asm
0x1800ff3c0  push    rbp
0x1800ff3c2  push    rbx
0x1800ff3c3  push    rsi
0x1800ff3c4  push    rdi
0x1800ff3c5  push    r12
0x1800ff3c7  push    r13
0x1800ff3c9  push    r14
0x1800ff3cb  push    r15
0x1800ff3cd  lea     rbp, [rsp-8]
0x1800ff3d2  sub     rsp, 108h
0x1800ff3d9  mov     rax, cs:__security_cookie
0x1800ff3e0  xor     rax, rsp
0x1800ff3e3  mov     [rbp+40h+var_50], rax
0x1800ff3e7  mov     r13d, [rbp+40h+arg_28]
0x1800ff3eb  mov     ebx, edx
0x1800ff3ed  mov     r14, [rbp+40h+arg_50]
0x1800ff3f4  mov     edi, r9d
0x1800ff3f7  mov     r15, [rbp+40h+arg_60]
0x1800ff3fe  mov     r11, rcx
0x1800ff401  mov     r9, [rbp+40h+arg_88]
0x1800ff408  mov     r10, [rbp+40h+arg_98]
0x1800ff40f  mov     esi, [rbp+40h+arg_48]
0x1800ff415  mov     [rbp+40h+var_B4], edx
0x1800ff418  mov     edx, r13d
0x1800ff41b  and     edx, 0FF0000h
0x1800ff421  mov     qword ptr [rbp+40h+var_A0], rcx
0x1800ff425  cmp     [rbp+40h+arg_90], 0
0x1800ff42c  mov     rcx, [rbp+40h+arg_40]
0x1800ff433  mov     [rbp+40h+var_B8], r8d
0x1800ff437  mov     [rbp+40h+lpxf], rcx
0x1800ff43b  mov     [rbp+40h+ColorUse], esi
0x1800ff43e  mov     [rbp+40h+pbmi], r14
0x1800ff442  mov     [rbp+40h+pjBits], r15
0x1800ff446  mov     [rbp+40h+var_80], r9
0x1800ff44a  mov     [rbp+40h+var_78], r10
0x1800ff44e  mov     [rbp+40h+var_98], edx
0x1800ff451  jnz     short loc_1800FF4B6
0x1800ff453  mov     eax, [rbp+40h+arg_68]
0x1800ff459  mov     r9d, edi
0x1800ff45c  mov     r10d, [rbp+40h+cy]
0x1800ff460  mov     [rsp+140h+var_C8], eax; int
0x1800ff464  mov     eax, dword ptr [rbp+40h+arg_58]
0x1800ff46a  mov     [rsp+140h+var_D0], r15; pjBits
0x1800ff46f  mov     dword ptr [rsp+140h+var_D8], eax; SIZE_T
0x1800ff473  mov     eax, [rbp+40h+y1]
0x1800ff479  mov     qword ptr [rsp+140h+var_E0], r14; BITMAPINFO *
0x1800ff47e  mov     [rsp+140h+iUsage], esi; UINT
0x1800ff482  mov     [rsp+140h+lpbmi], rcx; __int64
0x1800ff487  mov     rcx, r11; int
0x1800ff48a  mov     [rsp+140h+var_F8], r10d; int
0x1800ff48f  mov     [rsp+140h+SrcHeight], edi; int
0x1800ff493  mov     [rsp+140h+SrcWidth], eax; int
0x1800ff497  mov     eax, [rbp+40h+x1]
0x1800ff49d  mov     [rsp+140h+ySrc], eax; int
0x1800ff4a1  mov     [rsp+140h+rop], edx; int
0x1800ff4a5  mov     edx, ebx
0x1800ff4a7  mov     dword ptr [rsp+140h+lpBits], r10d; hDest
0x1800ff4ac  call    DoStretchBlt
0x1800ff4b1  jmp     loc_1800FFA73
0x1800ff4b6  lea     eax, ds:0[r13*4]
0x1800ff4be  xor     eax, r13d
0x1800ff4c1  test    eax, 0CCCC0000h
0x1800ff4c6  jnz     short loc_1800FF513
0x1800ff4c8  mov     eax, [rbp+40h+arg_80]
0x1800ff4ce  mov     edx, ebx; int
0x1800ff4d0  mov     qword ptr [rsp+140h+var_E0], r10; lpBits
0x1800ff4d5  mov     [rsp+140h+lpbmi], r9; lpbmi
0x1800ff4da  mov     r9d, edi; int
0x1800ff4dd  mov     [rsp+140h+var_F8], eax; ColorUse
0x1800ff4e1  mov     eax, [rbp+40h+arg_78]
0x1800ff4e7  mov     [rsp+140h+SrcHeight], eax; int
0x1800ff4eb  mov     eax, [rbp+40h+arg_70]
0x1800ff4f1  mov     [rsp+140h+SrcWidth], eax; int
0x1800ff4f5  mov     eax, [rbp+40h+cy]
0x1800ff4f8  mov     qword ptr [rsp+140h+ySrc], rcx; __int64
0x1800ff4fd  mov     rcx, r11; int
0x1800ff500  mov     [rsp+140h+rop], r13d; int
0x1800ff505  mov     dword ptr [rsp+140h+lpBits], eax; int
0x1800ff509  call    DoMaskBltNoSrc
0x1800ff50e  jmp     loc_1800FFA73
0x1800ff513  xor     ecx, ecx; hdc
0x1800ff515  mov     [rbp+40h+var_B0], 0
0x1800ff51c  call    cs:__imp_CreateCompatibleDC
0x1800ff523  nop     dword ptr [rax+rax+00h]
0x1800ff528  mov     rsi, rax
0x1800ff52b  test    rax, rax
0x1800ff52e  jz      loc_1800FFA70
0x1800ff534  xor     ebx, ebx
0x1800ff536  xor     r15d, r15d
0x1800ff539  mov     rcx, rax; hdc
0x1800ff53c  mov     [rbp+40h+h], r15
0x1800ff540  xor     r12d, r12d
0x1800ff543  lea     edx, [rbx+2]; iMode
0x1800ff546  call    cs:__imp_SetGraphicsMode
0x1800ff54d  nop     dword ptr [rax+rax+00h]
0x1800ff552  mov     edx, [r14+8]; nHeight
0x1800ff556  lea     eax, [rbx+1]
0x1800ff559  mov     ecx, [r14+4]; nWidth
0x1800ff55d  mov     r9d, eax; nBitCount
0x1800ff560  mov     r8d, eax; nPlanes
0x1800ff563  mov     [rsp+140h+lpBits], rbx; lpBits
0x1800ff568  call    cs:__imp_CreateBitmap
0x1800ff56f  nop     dword ptr [rax+rax+00h]
0x1800ff574  mov     [rbp+40h+ho], rax
0x1800ff578  test    rax, rax
0x1800ff57b  jz      loc_1800FFA22
0x1800ff581  mov     rdx, rax; h
0x1800ff584  mov     rcx, rsi; hdc
0x1800ff587  call    cs:__imp_SelectObject
0x1800ff58e  nop     dword ptr [rax+rax+00h]
0x1800ff593  mov     [rbp+40h+var_70], rax
0x1800ff597  test    rax, rax
0x1800ff59a  jz      loc_1800FFA12
0x1800ff5a0  mov     ecx, [r14+8]
0x1800ff5a4  xor     r8d, r8d; y
0x1800ff5a7  mov     r9d, [r14+4]; w
0x1800ff5ab  xor     edx, edx; x
0x1800ff5ad  mov     [rsp+140h+rop], 42h ; 'B'; rop
0x1800ff5b5  mov     dword ptr [rsp+140h+lpBits], ecx; h
0x1800ff5b9  mov     rcx, rsi; hdc
0x1800ff5bc  call    cs:__imp_PatBlt
0x1800ff5c3  nop     dword ptr [rax+rax+00h]
0x1800ff5c8  test    eax, eax
0x1800ff5ca  jz      loc_1800FF9FF
0x1800ff5d0  mov     r14d, [rbp+40h+x1]
0x1800ff5d7  lea     edx, [rbx+2]
0x1800ff5da  mov     r15d, [rbp+40h+y1]
0x1800ff5e1  lea     rcx, [rbp+40h+var_60]
0x1800ff5e5  mov     r8, [rbp+40h+lpxf]
0x1800ff5e9  mov     [rbp+40h+var_60], r14d
0x1800ff5ed  lea     eax, [rdi+r14]
0x1800ff5f1  mov     [rbp+40h+var_5C], r15d
0x1800ff5f5  mov     [rbp+40h+var_58], eax
0x1800ff5f8  mov     eax, [rbp+40h+cy]
0x1800ff5fb  add     eax, r15d
0x1800ff5fe  mov     [rbp+40h+var_54], eax
0x1800ff601  call    bXformWorkhorse
0x1800ff606  test    eax, eax
0x1800ff608  jz      loc_1800FF9FC
0x1800ff60e  mov     r10, [rbp+40h+var_80]
0x1800ff612  mov     edx, [rbp+40h+var_60]
0x1800ff615  cmp     edx, [rbp+40h+var_58]
0x1800ff618  mov     r8d, [rbp+40h+var_5C]
0x1800ff61c  mov     ecx, [r10+8]
0x1800ff620  cmovg   edx, [rbp+40h+var_58]
0x1800ff624  cmp     r8d, [rbp+40h+var_54]
0x1800ff628  mov     eax, [rbp+40h+arg_80]
0x1800ff62e  cmovg   r8d, [rbp+40h+var_54]
0x1800ff633  mov     r9d, [r10+4]; DestWidth
0x1800ff637  sub     r8d, [rbp+40h+arg_78]; yDest
0x1800ff63e  sub     edx, [rbp+40h+arg_70]; xDest
0x1800ff644  mov     [rsp+140h+var_E0], 0CC0020h; rop
0x1800ff64c  mov     [rsp+140h+iUsage], eax; iUsage
0x1800ff650  mov     rax, [rbp+40h+var_78]
0x1800ff654  mov     [rsp+140h+lpbmi], r10; lpbmi
0x1800ff659  mov     qword ptr [rsp+140h+var_F8], rax; lpBits
0x1800ff65e  mov     [rsp+140h+SrcHeight], ecx; SrcHeight
0x1800ff662  mov     [rsp+140h+SrcWidth], r9d; SrcWidth
0x1800ff667  mov     [rsp+140h+ySrc], ebx; ySrc
0x1800ff66b  mov     [rsp+140h+rop], ebx; xSrc
0x1800ff66f  mov     dword ptr [rsp+140h+lpBits], ecx; DestHeight
0x1800ff673  mov     rcx, rsi; hdc
0x1800ff676  call    cs:__imp_StretchDIBits
0x1800ff67d  nop     dword ptr [rax+rax+00h]
0x1800ff682  test    eax, eax
0x1800ff684  jz      loc_1800FF9FC
0x1800ff68a  mov     rdx, [rbp+40h+lpxf]; lpxf
0x1800ff68e  mov     rcx, rsi; hdc
0x1800ff691  call    cs:__imp_SetWorldTransform
0x1800ff698  nop     dword ptr [rax+rax+00h]
0x1800ff69d  test    eax, eax
0x1800ff69f  jz      loc_1800FF9FC
0x1800ff6a5  mov     rcx, [rbp+40h+lpxf]; lpxf
0x1800ff6a9  call    hdcMakeCompatibleDC
0x1800ff6ae  mov     rbx, rax
0x1800ff6b1  test    rax, rax
0x1800ff6b4  jz      loc_1800FF9F7
0x1800ff6ba  mov     eax, [rbp+40h+ColorUse]
0x1800ff6bd  lea     r8d, [r12+4]; flInit
0x1800ff6c2  mov     rdx, [rbp+40h+pbmi]; pbmih
0x1800ff6c6  mov     rcx, qword ptr [rbp+40h+var_A0]
0x1800ff6ca  mov     r9, [rbp+40h+pjBits]; pjBits
0x1800ff6ce  mov     [rsp+140h+rop], eax; iUsage
0x1800ff6d2  mov     [rsp+140h+lpBits], rdx; pbmi
0x1800ff6d7  mov     rcx, [rcx+28h]; hdc
0x1800ff6db  call    cs:__imp_CreateDIBitmap
0x1800ff6e2  nop     dword ptr [rax+rax+00h]
0x1800ff6e7  mov     r12, rax
0x1800ff6ea  test    rax, rax
0x1800ff6ed  jz      loc_1800FF9EC
0x1800ff6f3  mov     rdx, rax; h
0x1800ff6f6  mov     rcx, rbx; hdc
0x1800ff6f9  call    cs:__imp_SelectObject
0x1800ff700  nop     dword ptr [rax+rax+00h]
0x1800ff705  mov     [rbp+40h+h], rax
0x1800ff709  test    rax, rax
0x1800ff70c  jz      loc_1800FF9F2
0x1800ff712  mov     eax, [rbp+40h+cy]
0x1800ff715  mov     r9d, edi; cx
0x1800ff718  mov     [rsp+140h+SrcHeight], 8800C6h; rop
0x1800ff720  mov     r8d, r15d; y
0x1800ff723  mov     [rsp+140h+SrcWidth], r15d; y1
0x1800ff728  mov     edx, r14d; x
0x1800ff72b  mov     [rsp+140h+ySrc], r14d; x1
0x1800ff730  mov     rcx, rbx; hdc
0x1800ff733  mov     qword ptr [rsp+140h+rop], rsi; hdcSrc
0x1800ff738  mov     dword ptr [rsp+140h+lpBits], eax; cy
0x1800ff73c  call    cs:__imp_BitBlt
0x1800ff743  nop     dword ptr [rax+rax+00h]
0x1800ff748  test    eax, eax
0x1800ff74a  jz      loc_1800FF9EC
0x1800ff750  mov     rcx, [rbp+40h+lpxf]
0x1800ff754  mov     r9d, edi; int
0x1800ff757  mov     eax, [rbp+40h+var_98]
0x1800ff75a  mov     r8d, [rbp+40h+var_B8]; int
0x1800ff75e  and     eax, 0CC0000h
0x1800ff763  mov     edx, [rbp+40h+var_B4]; int
0x1800ff766  or      eax, 220000h
0x1800ff76b  mov     qword ptr [rsp+140h+var_E0], rcx; __int64
0x1800ff770  mov     ecx, [rbp+40h+cy]
0x1800ff773  mov     qword ptr [rsp+140h+iUsage], r12; hbm
0x1800ff778  mov     [rsp+140h+lpbmi], rbx; hdc
0x1800ff77d  mov     [rsp+140h+var_F8], ecx; int
0x1800ff781  mov     [rsp+140h+SrcHeight], edi; int
0x1800ff785  mov     [rsp+140h+SrcWidth], r15d; int
0x1800ff78a  mov     [rsp+140h+ySrc], r14d; int
0x1800ff78f  mov     [rsp+140h+rop], eax; int
0x1800ff793  mov     dword ptr [rsp+140h+lpBits], ecx; hDest
0x1800ff797  mov     rcx, qword ptr [rbp+40h+var_A0]; int
0x1800ff79b  call    DoStretchBltAlt
0x1800ff7a0  test    eax, eax
0x1800ff7a2  jz      loc_1800FF9EC
0x1800ff7a8  mov     eax, [rbp+40h+cy]
0x1800ff7ab  mov     r9d, edi; cx
0x1800ff7ae  mov     [rsp+140h+SrcHeight], 0BB0226h; rop
0x1800ff7b6  mov     r8d, r15d; y
0x1800ff7b9  mov     [rsp+140h+SrcWidth], r15d; y1
0x1800ff7be  mov     edx, r14d; x
0x1800ff7c1  mov     [rsp+140h+ySrc], r14d; x1
0x1800ff7c6  mov     rcx, rbx; hdc
0x1800ff7c9  mov     qword ptr [rsp+140h+rop], rsi; hdcSrc
0x1800ff7ce  mov     dword ptr [rsp+140h+lpBits], eax; cy
0x1800ff7d2  call    cs:__imp_BitBlt
0x1800ff7d9  nop     dword ptr [rax+rax+00h]
0x1800ff7de  test    eax, eax
0x1800ff7e0  jz      loc_1800FF9EC
0x1800ff7e6  mov     rax, [rbp+40h+lpxf]
0x1800ff7ea  mov     r9d, edi; int
0x1800ff7ed  mov     ecx, [rbp+40h+var_98]
0x1800ff7f0  mov     r8d, [rbp+40h+var_B8]; int
0x1800ff7f4  and     ecx, 330000h
0x1800ff7fa  mov     edx, [rbp+40h+var_B4]; int
0x1800ff7fd  or      ecx, 880000h
0x1800ff803  mov     qword ptr [rsp+140h+var_E0], rax; __int64
0x1800ff808  mov     eax, [rbp+40h+cy]
0x1800ff80b  mov     qword ptr [rsp+140h+iUsage], r12; hbm
0x1800ff810  mov     [rsp+140h+lpbmi], rbx; hdc
0x1800ff815  mov     [rsp+140h+var_F8], eax; int
0x1800ff819  mov     [rsp+140h+SrcHeight], edi; int
0x1800ff81d  mov     [rsp+140h+SrcWidth], r15d; int
0x1800ff822  mov     [rsp+140h+ySrc], r14d; int
0x1800ff827  mov     [rsp+140h+rop], ecx; int
0x1800ff82b  mov     rcx, qword ptr [rbp+40h+var_A0]; int
0x1800ff82f  mov     dword ptr [rsp+140h+lpBits], eax; hDest
0x1800ff833  call    DoStretchBltAlt
0x1800ff838  test    eax, eax
0x1800ff83a  jz      loc_1800FF9EC
0x1800ff840  mov     rdx, [rbp+40h+h]; h
0x1800ff844  mov     rcx, rbx; hdc
0x1800ff847  call    cs:__imp_SelectObject
0x1800ff84e  nop     dword ptr [rax+rax+00h]
0x1800ff853  test    rax, rax
0x1800ff856  jz      loc_1800FF9EC
0x1800ff85c  mov     eax, [rbp+40h+ColorUse]
0x1800ff85f  xor     r8d, r8d; start
0x1800ff862  mov     rcx, [rbp+40h+pjBits]
0x1800ff866  mov     rdx, r12; hbm
0x1800ff869  mov     [rsp+140h+ySrc], eax; ColorUse
0x1800ff86d  mov     rax, [rbp+40h+pbmi]
0x1800ff871  mov     qword ptr [rsp+140h+rop], rax; lpbmi
0x1800ff876  mov     [rsp+140h+lpBits], rcx; lpBits
0x1800ff87b  mov     r9d, [rax+8]; cLines
0x1800ff87f  mov     rax, qword ptr [rbp+40h+var_A0]
0x1800ff883  mov     rcx, [rax+28h]; hdc
0x1800ff887  call    cs:__imp_SetDIBits
0x1800ff88e  nop     dword ptr [rax+rax+00h]
0x1800ff893  test    eax, eax
0x1800ff895  jz      loc_1800FF9EC
0x1800ff89b  mov     rdx, r12; h
0x1800ff89e  mov     rcx, rbx; hdc
0x1800ff8a1  call    cs:__imp_SelectObject
0x1800ff8a8  nop     dword ptr [rax+rax+00h]
0x1800ff8ad  test    rax, rax
0x1800ff8b0  jz      loc_1800FF9EC
0x1800ff8b6  mov     eax, [rbp+40h+cy]
0x1800ff8b9  mov     r9d, edi; cx
0x1800ff8bc  mov     [rsp+140h+SrcHeight], 220326h; rop
0x1800ff8c4  mov     r8d, r15d; y
0x1800ff8c7  mov     [rsp+140h+SrcWidth], r15d; y1
0x1800ff8cc  mov     edx, r14d; x
  ... truncated ...
```
