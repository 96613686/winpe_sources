# CenterBitmapForImageList

- ea: `0x1803fe1f0`
- end: `0x1803fe42d`
- name: `CenterBitmapForImageList`
- size: `573`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1801e1b80`
- `0x180214868`
- `0x1802c5f90`

## callees

- `0x1803fe1f0`
- `0x18054e310`

## import_xrefs

- `GDI32!CreateSolidBrush` at `0x1803fe345`
- `GDI32!CreateSolidBrush` at `0x1803fe345`
- `GDI32!CreateDIBSection` at `0x1803fe2d1`
- `GDI32!CreateDIBSection` at `0x1803fe2d1`
- `GDI32!GetPixel` at `0x1803fe33d`
- `GDI32!GetPixel` at `0x1803fe33d`
- `GDI32!DeleteObject` at `0x1803fe366`
- `GDI32!DeleteObject` at `0x1803fe366`
- `GDI32!SelectObject` at `0x1803fe2ea`
- `GDI32!SelectObject` at `0x1803fe2fb`
- `GDI32!SelectObject` at `0x1803fe3e2`
- `GDI32!SelectObject` at `0x1803fe3ef`
- `GDI32!SelectObject` at `0x1803fe2ea`
- `GDI32!SelectObject` at `0x1803fe2fb`
- `GDI32!SelectObject` at `0x1803fe3e2`
- `GDI32!SelectObject` at `0x1803fe3ef`
- `GDI32!GetObjectW` at `0x1803fe240`
- `GDI32!GetObjectW` at `0x1803fe240`
- `GDI32!DeleteDC` at `0x1803fe3fb`
- `GDI32!DeleteDC` at `0x1803fe404`
- `GDI32!DeleteDC` at `0x1803fe3fb`
- `GDI32!DeleteDC` at `0x1803fe404`
- `GDI32!CreateCompatibleDC` at `0x1803fe267`
- `GDI32!CreateCompatibleDC` at `0x1803fe27c`
- `GDI32!CreateCompatibleDC` at `0x1803fe267`
- `GDI32!CreateCompatibleDC` at `0x1803fe27c`
- `GDI32!BitBlt` at `0x1803fe3ca`
- `GDI32!BitBlt` at `0x1803fe3ca`
- `USER32!FillRect` at `0x1803fe35d`
- `USER32!FillRect` at `0x1803fe35d`

## pseudocode

```c
__int64 __fastcall CenterBitmapForImageList(LONG *a1, void *a2, int a3, HGDIOBJ *a4)
{
  unsigned int v8; // r14d
  HDC CompatibleDC; // rax
  HDC v10; // rbx
  HDC v11; // rdi
  LONG v12; // eax
  HBITMAP v13; // rax
  HGDIOBJ v14; // rax
  LONG right; // r13d
  LONG v16; // r12d
  int v17; // r14d
  COLORREF Pixel; // eax
  HBRUSH SolidBrush; // rax
  HBRUSH v20; // rsi
  int v21; // esi
  int v22; // r8d
  int v23; // r12d
  int v25; // [rsp+50h] [rbp-69h]
  LONG cy; // [rsp+54h] [rbp-65h]
  HGDIOBJ h; // [rsp+58h] [rbp-61h]
  HGDIOBJ v28; // [rsp+60h] [rbp-59h]
  RECT pv[2]; // [rsp+68h] [rbp-51h] BYREF
  RECT rc; // [rsp+88h] [rbp-31h] BYREF
  BITMAPINFO pbmi; // [rsp+98h] [rbp-21h] BYREF

  v8 = -2147467259;
  memset(pv, 0, sizeof(pv));
  if ( GetObjectW(a2, 32, pv) )
  {
    if ( pv[0].top <= *a1 && pv[0].right <= a1[1] )
    {
      CompatibleDC = CreateCompatibleDC(0);
      v10 = CompatibleDC;
      if ( CompatibleDC )
      {
        v11 = CreateCompatibleDC(CompatibleDC);
        if ( v11 )
        {
          v12 = *a1;
          memset(&pbmi.bmiHeader.biWidth, 0, 40);
          pbmi.bmiHeader.biWidth = v12;
          pbmi.bmiHeader.biHeight = a1[1];
          pbmi.bmiHeader.biSize = 40;
          *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
          v13 = CreateDIBSection(v10, &pbmi, 0, 0, 0, 0);
          *a4 = v13;
          if ( v13 )
          {
            h = SelectObject(v11, a2);
            v14 = SelectObject(v10, *a4);
            right = pv[0].right;
            v16 = a1[1];
            v28 = v14;
            rc.right = *a1;
            cy = pv[0].right;
            v17 = pv[0].top / a3;
            *(_QWORD *)&rc.left = 0;
            rc.bottom = v16;
            v25 = rc.right / a3;
            Pixel = GetPixel(v11, 0, 0);
            SolidBrush = CreateSolidBrush(Pixel);
            v20 = SolidBrush;
            if ( SolidBrush )
            {
              FillRect(v10, &rc, SolidBrush);
              DeleteObject(v20);
            }
            v21 = 0;
            if ( a3 > 0 )
            {
              v22 = v25;
              v23 = (v16 - right) / 2;
              do
              {
                BitBlt(v10, (v25 - v17) / 2 + v22 * v21, v23, v17, cy, v11, v17 * v21, 0, 0xCC0020u);
                v22 = v25;
                ++v21;
              }
              while ( v21 < a3 );
            }
            SelectObject(v11, h);
            SelectObject(v10, v28);
            v8 = 0;
          }
          DeleteDC(v11);
        }
        DeleteDC(v10);
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x1803fe1f0  push    rbp
0x1803fe1f2  push    rbx
0x1803fe1f3  push    rsi
0x1803fe1f4  push    rdi
0x1803fe1f5  push    r12
0x1803fe1f7  push    r13
0x1803fe1f9  push    r14
0x1803fe1fb  push    r15
0x1803fe1fd  lea     rbp, [rsp-1Fh]
0x1803fe202  sub     rsp, 0D8h
0x1803fe209  mov     rax, cs:__security_cookie
0x1803fe210  xor     rax, rsp
0x1803fe213  mov     [rbp+57h+var_48], rax
0x1803fe217  mov     r13, rdx
0x1803fe21a  xorps   xmm0, xmm0
0x1803fe21d  mov     r15d, r8d
0x1803fe220  mov     rsi, rcx
0x1803fe223  mov     rcx, r13; h
0x1803fe226  lea     r8, [rbp+57h+pv]; pv
0x1803fe22a  mov     edx, 20h ; ' '; c
0x1803fe22f  mov     r12, r9
0x1803fe232  mov     r14d, 80004005h
0x1803fe238  movups  [rbp+57h+pv], xmm0
0x1803fe23c  movups  [rbp+57h+var_98], xmm0
0x1803fe240  call    cs:__imp_GetObjectW
0x1803fe246  test    eax, eax
0x1803fe248  jz      loc_1803FE40A
0x1803fe24e  mov     eax, [rsi]
0x1803fe250  cmp     dword ptr [rbp+57h+pv+4], eax
0x1803fe253  jg      loc_1803FE40A
0x1803fe259  mov     eax, [rsi+4]
0x1803fe25c  cmp     dword ptr [rbp+57h+pv+8], eax
0x1803fe25f  jg      loc_1803FE40A
0x1803fe265  xor     ecx, ecx; hdc
0x1803fe267  call    cs:__imp_CreateCompatibleDC
0x1803fe26d  mov     rbx, rax
0x1803fe270  test    rax, rax
0x1803fe273  jz      loc_1803FE40A
0x1803fe279  mov     rcx, rax; hdc
0x1803fe27c  call    cs:__imp_CreateCompatibleDC
0x1803fe282  xor     ecx, ecx
0x1803fe284  mov     rdi, rax
0x1803fe287  test    rax, rax
0x1803fe28a  jz      loc_1803FE401
0x1803fe290  xor     eax, eax
0x1803fe292  mov     [rsp+110h+offset], ecx; offset
0x1803fe296  xorps   xmm0, xmm0
0x1803fe299  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biClrImportant], rax
0x1803fe29d  mov     eax, [rsi]
0x1803fe29f  lea     rdx, [rbp+57h+pbmi]; pbmi
0x1803fe2a3  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biWidth], xmm0
0x1803fe2a7  mov     [rbp+57h+pbmi.bmiHeader.biWidth], eax
0x1803fe2aa  xor     r9d, r9d; ppvBits
0x1803fe2ad  mov     eax, [rsi+4]
0x1803fe2b0  xor     r8d, r8d; usage
0x1803fe2b3  mov     [rsp+110h+hSection], rcx; hSection
0x1803fe2b8  mov     rcx, rbx; hdc
0x1803fe2bb  mov     [rbp+57h+pbmi.bmiHeader.biHeight], eax
0x1803fe2be  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biSizeImage], xmm0
0x1803fe2c2  mov     [rbp+57h+pbmi.bmiHeader.biSize], 28h ; '('
0x1803fe2c9  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biPlanes], 200001h
0x1803fe2d1  call    cs:__imp_CreateDIBSection
0x1803fe2d7  mov     [r12], rax
0x1803fe2db  test    rax, rax
0x1803fe2de  jz      loc_1803FE3F8
0x1803fe2e4  mov     rdx, r13; h
0x1803fe2e7  mov     rcx, rdi; hdc
0x1803fe2ea  call    cs:__imp_SelectObject
0x1803fe2f0  mov     rdx, [r12]; h
0x1803fe2f4  mov     rcx, rbx; hdc
0x1803fe2f7  mov     [rbp+57h+h], rax
0x1803fe2fb  call    cs:__imp_SelectObject
0x1803fe301  mov     ecx, [rsi]
0x1803fe303  xor     r8d, r8d; y
0x1803fe306  mov     r13d, dword ptr [rbp+57h+pv+8]
0x1803fe30a  mov     r12d, [rsi+4]
0x1803fe30e  mov     [rbp+57h+var_B0], rax
0x1803fe312  mov     eax, dword ptr [rbp+57h+pv+4]
0x1803fe315  cdq
0x1803fe316  mov     [rbp+57h+rc.right], ecx
0x1803fe319  idiv    r15d
0x1803fe31c  mov     [rbp+57h+cy], r13d
0x1803fe320  mov     r14d, eax
0x1803fe323  mov     qword ptr [rbp+57h+rc.left], 0
0x1803fe32b  mov     eax, ecx
0x1803fe32d  mov     [rbp+57h+rc.bottom], r12d
0x1803fe331  cdq
0x1803fe332  mov     rcx, rdi; hdc
0x1803fe335  idiv    r15d
0x1803fe338  xor     edx, edx; x
0x1803fe33a  mov     [rbp+57h+var_C0], eax
0x1803fe33d  call    cs:__imp_GetPixel
0x1803fe343  mov     ecx, eax; color
0x1803fe345  call    cs:__imp_CreateSolidBrush
0x1803fe34b  mov     rsi, rax
0x1803fe34e  test    rax, rax
0x1803fe351  jz      short loc_1803FE36C
0x1803fe353  mov     r8, rax; hbr
0x1803fe356  lea     rdx, [rbp+57h+rc]; lprc
0x1803fe35a  mov     rcx, rbx; hDC
0x1803fe35d  call    cs:__imp_FillRect
0x1803fe363  mov     rcx, rsi; ho
0x1803fe366  call    cs:__imp_DeleteObject
0x1803fe36c  xor     esi, esi
0x1803fe36e  test    r15d, r15d
0x1803fe371  jle     short loc_1803FE3DB
0x1803fe373  mov     r8d, [rbp+57h+var_C0]
0x1803fe377  lea     ecx, [rsi+2]
0x1803fe37a  sub     r12d, r13d
0x1803fe37d  mov     eax, r12d
0x1803fe380  cdq
0x1803fe381  idiv    ecx
0x1803fe383  mov     r12d, eax
0x1803fe386  mov     eax, r8d
0x1803fe389  sub     eax, r14d
0x1803fe38c  cdq
0x1803fe38d  idiv    ecx
0x1803fe38f  mov     r13d, eax
0x1803fe392  mov     eax, [rbp+57h+cy]
0x1803fe395  mov     ecx, esi
0x1803fe397  mov     [rsp+110h+rop], 0CC0020h; rop
0x1803fe39f  mov     edx, esi
0x1803fe3a1  imul    ecx, r14d
0x1803fe3a5  mov     r9d, r14d; cx
0x1803fe3a8  imul    edx, r8d
0x1803fe3ac  mov     r8d, r12d; y
0x1803fe3af  mov     [rsp+110h+y1], 0; y1
0x1803fe3b7  mov     [rsp+110h+x1], ecx; x1
0x1803fe3bb  mov     rcx, rbx; hdc
0x1803fe3be  mov     qword ptr [rsp+110h+offset], rdi; hdcSrc
0x1803fe3c3  add     edx, r13d; x
0x1803fe3c6  mov     dword ptr [rsp+110h+hSection], eax; cy
0x1803fe3ca  call    cs:__imp_BitBlt
0x1803fe3d0  mov     r8d, [rbp+57h+var_C0]
0x1803fe3d4  inc     esi
0x1803fe3d6  cmp     esi, r15d
0x1803fe3d9  jl      short loc_1803FE392
0x1803fe3db  mov     rdx, [rbp+57h+h]; h
0x1803fe3df  mov     rcx, rdi; hdc
0x1803fe3e2  call    cs:__imp_SelectObject
0x1803fe3e8  mov     rdx, [rbp+57h+var_B0]; h
0x1803fe3ec  mov     rcx, rbx; hdc
0x1803fe3ef  call    cs:__imp_SelectObject
0x1803fe3f5  xor     r14d, r14d
0x1803fe3f8  mov     rcx, rdi; hdc
0x1803fe3fb  call    cs:__imp_DeleteDC
0x1803fe401  mov     rcx, rbx; hdc
0x1803fe404  call    cs:__imp_DeleteDC
0x1803fe40a  mov     eax, r14d
0x1803fe40d  mov     rcx, [rbp+57h+var_48]
0x1803fe411  xor     rcx, rsp; StackCookie
0x1803fe414  call    __security_check_cookie
0x1803fe419  add     rsp, 0D8h
0x1803fe420  pop     r15
0x1803fe422  pop     r14
0x1803fe424  pop     r13
0x1803fe426  pop     r12
0x1803fe428  pop     rdi
0x1803fe429  pop     rsi
0x1803fe42a  pop     rbx
0x1803fe42b  pop     rbp
0x1803fe42c  retn
```
