# DoMaskBlt

- ea: `0x180141ed8`
- end: `0x1801425be`
- name: `DoMaskBlt`
- size: `1766`
- prototype: `__int64 __fastcall(int, int, int, int, int cy, int, int x, int y, __int64, int, BITMAPINFO *, SIZE_T, __int64, int, __int16, __int16, UINT, BITMAPINFO *, int, void *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18013feb0`
- `0x1801427e0`

## callees

- `0x1800b1afc`
- `0x1800b1ee8`
- `0x1800e9380`
- `0x180141ed8`
- `0x1801425c4`
- `0x180143a78`
- `0x1801440d0`

## import_xrefs

- `GDI32!BitBlt` at `0x180142271`
- `GDI32!BitBlt` at `0x180142304`
- `GDI32!BitBlt` at `0x18014240f`
- `GDI32!BitBlt` at `0x1801424a2`
- `GDI32!BitBlt` at `0x180142271`
- `GDI32!BitBlt` at `0x180142304`
- `GDI32!BitBlt` at `0x18014240f`
- `GDI32!BitBlt` at `0x1801424a2`
- `GDI32!CreateDIBitmap` at `0x180142212`
- `GDI32!CreateDIBitmap` at `0x180142212`
- `GDI32!StretchDIBits` at `0x1801421ac`
- `GDI32!StretchDIBits` at `0x1801421ac`
- `GDI32!SetWorldTransform` at `0x1801421c7`
- `GDI32!SetWorldTransform` at `0x1801421c7`
- `GDI32!SetGraphicsMode` at `0x180142073`
- `GDI32!SetGraphicsMode` at `0x180142073`
- `GDI32!SetDIBits` at `0x1801423b8`
- `GDI32!SetDIBits` at `0x1801423b8`
- `GDI32!CreateBitmap` at `0x180142097`
- `GDI32!CreateBitmap` at `0x180142097`
- `GDI32!PatBlt` at `0x1801420ee`
- `GDI32!PatBlt` at `0x1801420ee`
- `GDI32!DeleteDC` at `0x18014254f`
- `GDI32!DeleteDC` at `0x18014258e`
- `GDI32!DeleteDC` at `0x18014254f`
- `GDI32!DeleteDC` at `0x18014258e`
- `GDI32!SelectObject` at `0x1801420b9`
- `GDI32!SelectObject` at `0x180142230`
- `GDI32!SelectObject` at `0x180142378`
- `GDI32!SelectObject` at `0x1801423d2`
- `GDI32!SelectObject` at `0x180142531`
- `GDI32!SelectObject` at `0x180142566`
- `GDI32!SelectObject` at `0x1801420b9`
- `GDI32!SelectObject` at `0x180142230`
- `GDI32!SelectObject` at `0x180142378`
- `GDI32!SelectObject` at `0x1801423d2`
- `GDI32!SelectObject` at `0x180142531`
- `GDI32!SelectObject` at `0x180142566`
- `GDI32!CreateCompatibleDC` at `0x180142053`
- `GDI32!CreateCompatibleDC` at `0x180142053`
- `GDI32!DeleteObject` at `0x180142540`
- `GDI32!DeleteObject` at `0x18014257a`
- `GDI32!DeleteObject` at `0x180142540`
- `GDI32!DeleteObject` at `0x18014257a`

## pseudocode

```c
__int64 __fastcall DoMaskBlt(
        __int64 a1,
        int a2,
        int a3,
        int a4,
        int cy,
        unsigned int a6,
        int x,
        int y,
        XFORM *a9,
        UINT a10,
        BITMAPINFO *a11,
        SIZE_T a12,
        const void *a13,
        int a14,
        int a15,
        int a16,
        UINT a17,
        BITMAPINFO *lpbmi,
        int a19,
        void *lpBits)
{
  void *v20; // r15
  HDC v22; // rbx
  HBITMAP v23; // r12
  HDC CompatibleDC; // rax
  HDC v26; // rsi
  HBITMAP Bitmap; // rax
  HBITMAP v28; // r13
  int v29; // edx
  int v30; // r8d
  HBITMAP DIBitmap; // rax
  int iUsage; // [rsp+58h] [rbp-A8h]
  SIZE_T v33; // [rsp+68h] [rbp-98h]
  HGDIOBJ v34; // [rsp+80h] [rbp-80h]
  HBITMAP v35; // [rsp+88h] [rbp-78h]
  BOOL v36; // [rsp+9Ch] [rbp-64h]
  unsigned int v38; // [rsp+B4h] [rbp-4Ch]
  HGDIOBJ v39; // [rsp+D8h] [rbp-28h]
  int v40; // [rsp+E0h] [rbp-20h] BYREF
  int v41; // [rsp+E4h] [rbp-1Ch]
  int v42; // [rsp+E8h] [rbp-18h]
  int v43; // [rsp+ECh] [rbp-14h]

  v36 = 0;
  v20 = 0;
  v22 = 0;
  v23 = 0;
  v34 = 0;
  v38 = a6 >> 8;
  if ( !a19 )
  {
    LODWORD(v33) = a12;
    return DoStretchBlt(a1, cy, a6 & 0xFF0000, x, y, a4, cy, (__int64)a9, a10, a11, v33, (__int64)a13, a14);
  }
  if ( ((a6 ^ (4 * a6)) & 0xCCCC0000) == 0 )
    return DoMaskBltNoSrc(a1, a2, a3, a4, cy, a6, (__int64)a9, a15, a16, a17, lpbmi, iUsage, lpBits);
  CompatibleDC = CreateCompatibleDC(0);
  v26 = CompatibleDC;
  if ( CompatibleDC )
  {
    SetGraphicsMode(CompatibleDC, 2);
    Bitmap = CreateBitmap(a11->bmiHeader.biWidth, a11->bmiHeader.biHeight, 1u, 1u, 0);
    v35 = Bitmap;
    v28 = Bitmap;
    if ( !Bitmap )
    {
LABEL_37:
      DeleteDC(v26);
      if ( v20 )
        SelectObject(v22, v20);
      if ( v23 )
        DeleteObject(v23);
      if ( v22 )
        DeleteDC(v22);
      return v36;
    }
    v39 = SelectObject(v26, Bitmap);
    if ( !v39 )
    {
LABEL_36:
      DeleteObject(v28);
      goto LABEL_37;
    }
    if ( !PatBlt(v26, 0, 0, a11->bmiHeader.biWidth, a11->bmiHeader.biHeight, 0x42u) )
    {
LABEL_35:
      SelectObject(v26, v39);
      goto LABEL_36;
    }
    v40 = x;
    v42 = a4 + x;
    v41 = y;
    v43 = y + cy;
    if ( !(unsigned int)bXformWorkhorse(&v40, 2, a9) )
      goto LABEL_33;
    v29 = v40;
    v30 = v41;
    if ( v40 > v42 )
      v29 = v42;
    if ( v41 > v43 )
      v30 = v43;
    if ( !StretchDIBits(
            v26,
            v29 - a15,
            v30 - a16,
            lpbmi->bmiHeader.biWidth,
            lpbmi->bmiHeader.biHeight,
            0,
            0,
            lpbmi->bmiHeader.biWidth,
            lpbmi->bmiHeader.biHeight,
            lpBits,
            lpbmi,
            a17,
            0xCC0020u)
      || !SetWorldTransform(v26, a9) )
    {
LABEL_33:
      v20 = 0;
      goto LABEL_34;
    }
    v22 = (HDC)hdcMakeCompatibleDC(a9);
    if ( !v22 )
    {
      v20 = 0;
      goto LABEL_34;
    }
    DIBitmap = CreateDIBitmap(*(HDC *)(a1 + 40), &a11->bmiHeader, 4u, a13, a11, a10);
    v23 = DIBitmap;
    if ( DIBitmap )
    {
      v34 = SelectObject(v22, DIBitmap);
      if ( !v34 )
      {
        v20 = 0;
        goto LABEL_34;
      }
      if ( BitBlt(v22, x, y, a4, cy, v26, x, y, 0x8800C6u)
        && (unsigned int)DoStretchBltAlt(a1, cy, a6 & 0xCC0000 | 0x220000, x, y, a4, cy, v22, v23, (__int64)a9)
        && BitBlt(v22, x, y, a4, cy, v26, x, y, 0xBB0226u)
        && (unsigned int)DoStretchBltAlt(a1, cy, a6 & 0x330000 | 0x880000, x, y, a4, cy, v22, v23, (__int64)a9)
        && SelectObject(v22, v34)
        && SetDIBits(*(HDC *)(a1 + 40), v23, 0, a11->bmiHeader.biHeight, a13, a11, a10)
        && SelectObject(v22, v23)
        && BitBlt(v22, x, y, a4, cy, v26, x, y, 0x220326u)
        && (unsigned int)DoStretchBltAlt(a1, cy, v38 & 0xCC0000 | 0x220000, x, y, a4, cy, v22, v23, (__int64)a9)
        && BitBlt(v22, x, y, a4, cy, v26, x, y, 0xEE0086u) )
      {
        v36 = DoStretchBltAlt(a1, cy, v38 & 0x330000 | 0x880000, x, y, a4, cy, v22, v23, (__int64)a9) != 0;
      }
    }
    v20 = v34;
LABEL_34:
    v28 = v35;
    goto LABEL_35;
  }
  return v36;
}

```

## disassembly

```asm
0x180141ed8  push    rbp
0x180141eda  push    rbx
0x180141edb  push    rsi
0x180141edc  push    rdi
0x180141edd  push    r12
0x180141edf  push    r13
0x180141ee1  push    r14
0x180141ee3  push    r15
0x180141ee5  lea     rbp, [rsp-8]
0x180141eea  sub     rsp, 108h
0x180141ef1  mov     rax, cs:__security_cookie
0x180141ef8  xor     rax, rsp
0x180141efb  mov     [rbp+40h+var_50], rax
0x180141eff  mov     eax, [rbp+40h+arg_48]
0x180141f05  mov     r13d, r8d
0x180141f08  and     [rbp+40h+var_A4], 0
0x180141f0c  xor     r15d, r15d
0x180141f0f  mov     r14, [rbp+40h+arg_50]
0x180141f16  mov     esi, edx
0x180141f18  mov     r10, [rbp+40h+arg_98]
0x180141f1f  mov     edi, r9d
0x180141f22  mov     r9, [rbp+40h+arg_88]
0x180141f29  mov     r11, rcx
0x180141f2c  mov     [rbp+40h+ColorUse], eax
0x180141f2f  xor     ebx, ebx
0x180141f31  mov     rax, [rbp+40h+arg_60]
0x180141f38  xor     r12d, r12d
0x180141f3b  mov     [rbp+40h+pjBits], rax
0x180141f3f  mov     [rbp+40h+var_B0], r8d
0x180141f43  mov     [rbp+40h+var_AC], edx
0x180141f46  mov     edx, [rbp+40h+arg_28]
0x180141f49  mov     eax, edx
0x180141f4b  shr     eax, 8
0x180141f4e  mov     r8d, edx
0x180141f51  and     r8d, 0FF0000h
0x180141f58  mov     qword ptr [rbp+40h+var_98], rcx
0x180141f5c  mov     rcx, [rbp+40h+arg_40]
0x180141f63  mov     [rbp+40h+lpxf], rcx
0x180141f67  mov     [rbp+40h+pbmi], r14
0x180141f6b  mov     [rbp+40h+var_78], r9
0x180141f6f  mov     [rbp+40h+var_70], r10
0x180141f73  mov     [rbp+40h+var_C0], r15
0x180141f77  mov     [rbp+40h+var_8C], eax
0x180141f7a  mov     [rbp+40h+var_90], r8d
0x180141f7e  cmp     [rbp+40h+arg_90], ebx
0x180141f84  jnz     short loc_180141FF4
0x180141f86  mov     eax, [rbp+40h+arg_68]
0x180141f8c  mov     r9d, edi
0x180141f8f  mov     rdx, [rbp+40h+pjBits]
0x180141f93  mov     r10d, [rbp+40h+cy]
0x180141f97  mov     [rsp+140h+var_C8], eax; int
0x180141f9b  mov     eax, dword ptr [rbp+40h+arg_58]
0x180141fa1  mov     [rsp+140h+var_D0], rdx; __int64
0x180141fa6  mov     edx, esi
0x180141fa8  mov     dword ptr [rsp+140h+var_D8], eax; SIZE_T
0x180141fac  mov     eax, [rbp+40h+ColorUse]
0x180141faf  mov     qword ptr [rsp+140h+var_E0], r14; BITMAPINFO *
0x180141fb4  mov     [rsp+140h+iUsage], eax; UINT
0x180141fb8  mov     eax, [rbp+40h+y]
0x180141fbe  mov     [rsp+140h+lpbmi], rcx; __int64
0x180141fc3  mov     rcx, r11; int
0x180141fc6  mov     dword ptr [rsp+140h+lpBits], r10d; int
0x180141fcb  mov     [rsp+140h+SrcHeight], edi; int
0x180141fcf  mov     [rsp+140h+SrcWidth], eax; __int16
0x180141fd3  mov     eax, [rbp+40h+x]
0x180141fd9  mov     [rsp+140h+x1], eax; __int16
0x180141fdd  mov     [rsp+140h+rop], r8d; int
0x180141fe2  mov     r8d, r13d
0x180141fe5  mov     [rsp+140h+h], r10d; hDest
0x180141fea  call    DoStretchBlt
0x180141fef  jmp     loc_18014259D
0x180141ff4  lea     eax, ds:0[rdx*4]
0x180141ffb  xor     eax, edx
0x180141ffd  test    eax, 0CCCC0000h
0x180142002  jnz     short loc_180142051
0x180142004  mov     eax, [rbp+40h+arg_80]
0x18014200a  mov     r8d, r13d; int
0x18014200d  mov     qword ptr [rsp+140h+var_E0], r10; lpBits
0x180142012  mov     [rsp+140h+lpbmi], r9; lpbmi
0x180142017  mov     r9d, edi; int
0x18014201a  mov     dword ptr [rsp+140h+lpBits], eax; ColorUse
0x18014201e  mov     eax, dword ptr [rbp+40h+arg_78]
0x180142024  mov     [rsp+140h+SrcHeight], eax; __int16
0x180142028  mov     eax, dword ptr [rbp+40h+arg_70]
0x18014202e  mov     [rsp+140h+SrcWidth], eax; __int16
0x180142032  mov     eax, [rbp+40h+cy]
0x180142035  mov     qword ptr [rsp+140h+x1], rcx; __int64
0x18014203a  mov     rcx, r11; int
0x18014203d  mov     [rsp+140h+rop], edx; int
0x180142041  mov     edx, esi; int
0x180142043  mov     [rsp+140h+h], eax; int
0x180142047  call    DoMaskBltNoSrc
0x18014204c  jmp     loc_18014259D
0x180142051  xor     ecx, ecx; hdc
0x180142053  call    cs:__imp_CreateCompatibleDC
0x18014205a  nop     dword ptr [rax+rax+00h]
0x18014205f  mov     rsi, rax
0x180142062  test    rax, rax
0x180142065  jz      loc_18014259A
0x18014206b  mov     edx, 2; iMode
0x180142070  mov     rcx, rax; hdc
0x180142073  call    cs:__imp_SetGraphicsMode
0x18014207a  nop     dword ptr [rax+rax+00h]
0x18014207f  mov     edx, [r14+8]; nHeight
0x180142083  mov     eax, 1
0x180142088  mov     ecx, [r14+4]; nWidth
0x18014208c  mov     r9d, eax; nBitCount
0x18014208f  and     qword ptr [rsp+140h+h], rbx
0x180142094  mov     r8d, eax; nPlanes
0x180142097  call    cs:__imp_CreateBitmap
0x18014209e  nop     dword ptr [rax+rax+00h]
0x1801420a3  mov     [rbp+40h+var_B8], rax
0x1801420a7  mov     r13, rax
0x1801420aa  test    rax, rax
0x1801420ad  jz      loc_18014254C
0x1801420b3  mov     rdx, rax; h
0x1801420b6  mov     rcx, rsi; hdc
0x1801420b9  call    cs:__imp_SelectObject
0x1801420c0  nop     dword ptr [rax+rax+00h]
0x1801420c5  mov     [rbp+40h+var_68], rax
0x1801420c9  test    rax, rax
0x1801420cc  jz      loc_18014253D
0x1801420d2  mov     eax, [r14+8]
0x1801420d6  xor     r8d, r8d; y
0x1801420d9  mov     r9d, [r14+4]; w
0x1801420dd  xor     edx, edx; x
0x1801420df  mov     [rsp+140h+rop], 42h ; 'B'; xSrc
0x1801420e7  mov     rcx, rsi; hdc
0x1801420ea  mov     [rsp+140h+h], eax; h
0x1801420ee  call    cs:__imp_PatBlt
0x1801420f5  nop     dword ptr [rax+rax+00h]
0x1801420fa  test    eax, eax
0x1801420fc  jz      loc_18014252A
0x180142102  mov     r14d, [rbp+40h+x]
0x180142109  lea     rcx, [rbp+40h+var_60]
0x18014210d  mov     r15d, [rbp+40h+y]
0x180142114  mov     edx, 2
0x180142119  mov     r13d, [rbp+40h+cy]
0x18014211d  mov     r8, [rbp+40h+lpxf]
0x180142121  lea     eax, [rdi+r14]
0x180142125  mov     [rbp+40h+var_60], r14d
0x180142129  mov     [rbp+40h+var_58], eax
0x18014212c  lea     eax, [r15+r13]
0x180142130  mov     [rbp+40h+var_5C], r15d
0x180142134  mov     [rbp+40h+var_54], eax
0x180142137  call    bXformWorkhorse
0x18014213c  test    eax, eax
0x18014213e  jz      loc_180142523
0x180142144  mov     r10, [rbp+40h+var_78]
0x180142148  mov     edx, [rbp+40h+var_60]
0x18014214b  cmp     edx, [rbp+40h+var_58]
0x18014214e  mov     r8d, [rbp+40h+var_5C]
0x180142152  cmovg   edx, [rbp+40h+var_58]
0x180142156  mov     ecx, [r10+8]
0x18014215a  cmp     r8d, [rbp+40h+var_54]
0x18014215e  mov     eax, [rbp+40h+arg_80]
0x180142164  cmovg   r8d, [rbp+40h+var_54]
0x180142169  mov     r9d, [r10+4]; DestWidth
0x18014216d  sub     r8d, dword ptr [rbp+40h+arg_78]; yDest
0x180142174  sub     edx, dword ptr [rbp+40h+arg_70]; xDest
0x18014217a  mov     [rsp+140h+var_E0], 0CC0020h; rop
0x180142182  mov     [rsp+140h+iUsage], eax; iUsage
0x180142186  mov     rax, [rbp+40h+var_70]
0x18014218a  mov     [rsp+140h+lpbmi], r10; lpbmi
0x18014218f  mov     [rsp+140h+lpBits], rax; lpBits
0x180142194  mov     [rsp+140h+SrcHeight], ecx; SrcHeight
0x180142198  mov     [rsp+140h+SrcWidth], r9d; SrcWidth
0x18014219d  and     [rsp+140h+x1], ebx
0x1801421a1  and     [rsp+140h+rop], ebx
0x1801421a5  mov     [rsp+140h+h], ecx; DestHeight
0x1801421a9  mov     rcx, rsi; hdc
0x1801421ac  call    cs:__imp_StretchDIBits
0x1801421b3  nop     dword ptr [rax+rax+00h]
0x1801421b8  test    eax, eax
0x1801421ba  jz      loc_180142523
0x1801421c0  mov     rdx, [rbp+40h+lpxf]; lpxf
0x1801421c4  mov     rcx, rsi; hdc
0x1801421c7  call    cs:__imp_SetWorldTransform
0x1801421ce  nop     dword ptr [rax+rax+00h]
0x1801421d3  test    eax, eax
0x1801421d5  jz      loc_180142523
0x1801421db  mov     rcx, [rbp+40h+lpxf]; lpxf
0x1801421df  call    hdcMakeCompatibleDC
0x1801421e4  mov     rbx, rax
0x1801421e7  test    rax, rax
0x1801421ea  jz      loc_18014251E
0x1801421f0  mov     eax, [rbp+40h+ColorUse]
0x1801421f3  mov     r8d, 4; flInit
0x1801421f9  mov     rdx, [rbp+40h+pbmi]; pbmih
0x1801421fd  mov     rcx, qword ptr [rbp+40h+var_98]
0x180142201  mov     r9, [rbp+40h+pjBits]; pjBits
0x180142205  mov     [rsp+140h+rop], eax; iUsage
0x180142209  mov     qword ptr [rsp+140h+h], rdx; pbmi
0x18014220e  mov     rcx, [rcx+28h]; hdc
0x180142212  call    cs:__imp_CreateDIBitmap
0x180142219  nop     dword ptr [rax+rax+00h]
0x18014221e  mov     r12, rax
0x180142221  test    rax, rax
0x180142224  jz      loc_180142513
0x18014222a  mov     rdx, rax; h
0x18014222d  mov     rcx, rbx; hdc
0x180142230  call    cs:__imp_SelectObject
0x180142237  nop     dword ptr [rax+rax+00h]
0x18014223c  mov     [rbp+40h+var_C0], rax
0x180142240  test    rax, rax
0x180142243  jz      loc_180142519
0x180142249  mov     [rsp+140h+SrcHeight], 8800C6h; rop
0x180142251  mov     r9d, edi; cx
0x180142254  mov     [rsp+140h+SrcWidth], r15d; y1
0x180142259  mov     r8d, r15d; y
0x18014225c  mov     [rsp+140h+x1], r14d; x1
0x180142261  mov     edx, r14d; x
0x180142264  mov     qword ptr [rsp+140h+rop], rsi; hdcSrc
0x180142269  mov     rcx, rbx; hdc
0x18014226c  mov     [rsp+140h+h], r13d; cy
0x180142271  call    cs:__imp_BitBlt
0x180142278  nop     dword ptr [rax+rax+00h]
0x18014227d  test    eax, eax
0x18014227f  jz      loc_180142513
0x180142285  mov     rcx, [rbp+40h+lpxf]
0x180142289  mov     r9d, edi
0x18014228c  mov     eax, [rbp+40h+var_90]
0x18014228f  mov     r8d, [rbp+40h+var_B0]
0x180142293  and     eax, 0CC0000h
0x180142298  mov     edx, [rbp+40h+var_AC]
0x18014229b  or      eax, 220000h
0x1801422a0  mov     qword ptr [rsp+140h+var_E0], rcx; __int64
0x1801422a5  mov     rcx, qword ptr [rbp+40h+var_98]; int
0x1801422a9  mov     qword ptr [rsp+140h+iUsage], r12; hbm
0x1801422ae  mov     [rsp+140h+lpbmi], rbx; hdc
0x1801422b3  mov     dword ptr [rsp+140h+lpBits], r13d; int
0x1801422b8  mov     [rsp+140h+SrcHeight], edi; int
0x1801422bc  mov     [rsp+140h+SrcWidth], r15d; __int16
0x1801422c1  mov     [rsp+140h+x1], r14d; __int16
0x1801422c6  mov     [rsp+140h+rop], eax; int
0x1801422ca  mov     [rsp+140h+h], r13d; hDest
0x1801422cf  call    DoStretchBltAlt
0x1801422d4  test    eax, eax
0x1801422d6  jz      loc_180142513
0x1801422dc  mov     [rsp+140h+SrcHeight], 0BB0226h; rop
0x1801422e4  mov     r9d, edi; cx
0x1801422e7  mov     [rsp+140h+SrcWidth], r15d; y1
0x1801422ec  mov     r8d, r15d; y
0x1801422ef  mov     [rsp+140h+x1], r14d; x1
0x1801422f4  mov     edx, r14d; x
0x1801422f7  mov     qword ptr [rsp+140h+rop], rsi; hdcSrc
0x1801422fc  mov     rcx, rbx; hdc
0x1801422ff  mov     [rsp+140h+h], r13d; cy
0x180142304  call    cs:__imp_BitBlt
0x18014230b  nop     dword ptr [rax+rax+00h]
0x180142310  test    eax, eax
0x180142312  jz      loc_180142513
0x180142318  mov     rax, [rbp+40h+lpxf]
0x18014231c  mov     r9d, edi
0x18014231f  mov     ecx, [rbp+40h+var_90]
0x180142322  mov     r8d, [rbp+40h+var_B0]
0x180142326  and     ecx, 330000h
0x18014232c  mov     edx, [rbp+40h+var_AC]
0x18014232f  or      ecx, 880000h
0x180142335  mov     qword ptr [rsp+140h+var_E0], rax; __int64
0x18014233a  mov     qword ptr [rsp+140h+iUsage], r12; hbm
0x18014233f  mov     [rsp+140h+lpbmi], rbx; hdc
0x180142344  mov     dword ptr [rsp+140h+lpBits], r13d; int
0x180142349  mov     [rsp+140h+SrcHeight], edi; int
0x18014234d  mov     [rsp+140h+SrcWidth], r15d; __int16
0x180142352  mov     [rsp+140h+x1], r14d; __int16
0x180142357  mov     [rsp+140h+rop], ecx; int
0x18014235b  mov     rcx, qword ptr [rbp+40h+var_98]; int
0x18014235f  mov     [rsp+140h+h], r13d; hDest
0x180142364  call    DoStretchBltAlt
0x180142369  test    eax, eax
0x18014236b  jz      loc_180142513
0x180142371  mov     rdx, [rbp+40h+var_C0]; h
0x180142375  mov     rcx, rbx; hdc
0x180142378  call    cs:__imp_SelectObject
0x18014237f  nop     dword ptr [rax+rax+00h]
0x180142384  test    rax, rax
0x180142387  jz      loc_180142513
0x18014238d  mov     eax, [rbp+40h+ColorUse]
0x180142390  xor     r8d, r8d; start
0x180142393  mov     rdx, [rbp+40h+pjBits]
0x180142397  mov     [rsp+140h+x1], eax; ColorUse
0x18014239b  mov     rax, [rbp+40h+pbmi]
0x18014239f  mov     qword ptr [rsp+140h+rop], rax; lpbmi
0x1801423a4  mov     qword ptr [rsp+140h+h], rdx; lpBits
0x1801423a9  mov     rdx, r12; hbm
0x1801423ac  mov     r9d, [rax+8]; cLines
0x1801423b0  mov     rax, qword ptr [rbp+40h+var_98]
0x1801423b4  mov     rcx, [rax+28h]; hdc
0x1801423b8  call    cs:__imp_SetDIBits
0x1801423bf  nop     dword ptr [rax+rax+00h]
0x1801423c4  test    eax, eax
0x1801423c6  jz      loc_180142513
0x1801423cc  mov     rdx, r12; h
0x1801423cf  mov     rcx, rbx; hdc
0x1801423d2  call    cs:__imp_SelectObject
0x1801423d9  nop     dword ptr [rax+rax+00h]
0x1801423de  test    rax, rax
0x1801423e1  jz      loc_180142513
0x1801423e7  mov     [rsp+140h+SrcHeight], 220326h; rop
  ... truncated ...
```
