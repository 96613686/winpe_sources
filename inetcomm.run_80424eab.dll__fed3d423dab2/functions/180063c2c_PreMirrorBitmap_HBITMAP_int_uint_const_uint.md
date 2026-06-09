# PreMirrorBitmap(HBITMAP__ *,int,uint const *,uint)

- ea: `0x180063c2c`
- end: `0x180063e64`
- name: `?PreMirrorBitmap@@YAPEAUHBITMAP__@@PEAU1@HPEBII@Z`
- size: `568`
- prototype: `HBITMAP __fastcall(HBITMAP h, int wSrc, const unsigned int *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180063a70`

## callees

- `0x180063c2c`
- `0x1800cca00`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x180063ce7`
- `GDI32!CreateCompatibleDC` at `0x180063cf3`
- `GDI32!CreateCompatibleDC` at `0x180063ce7`
- `GDI32!CreateCompatibleDC` at `0x180063cf3`
- `GDI32!CreateDIBSection` at `0x180063d25`
- `GDI32!CreateDIBSection` at `0x180063d25`
- `GDI32!SelectObject` at `0x180063d41`
- `GDI32!SelectObject` at `0x180063d51`
- `GDI32!SelectObject` at `0x180063e06`
- `GDI32!SelectObject` at `0x180063e13`
- `GDI32!SelectObject` at `0x180063d41`
- `GDI32!SelectObject` at `0x180063d51`
- `GDI32!SelectObject` at `0x180063e06`
- `GDI32!SelectObject` at `0x180063e13`
- `GDI32!BitBlt` at `0x180063d88`
- `GDI32!BitBlt` at `0x180063d88`
- `GDI32!StretchBlt` at `0x180063de6`
- `GDI32!StretchBlt` at `0x180063de6`
- `GDI32!DeleteDC` at `0x180063e1c`
- `GDI32!DeleteDC` at `0x180063e25`
- `GDI32!DeleteDC` at `0x180063e1c`
- `GDI32!DeleteDC` at `0x180063e25`
- `GDI32!GetObjectA` at `0x180063c9d`
- `GDI32!GetObjectA` at `0x180063c9d`
- `USER32!GetDC` at `0x180063cd7`
- `USER32!GetDC` at `0x180063cd7`
- `USER32!ReleaseDC` at `0x180063e30`
- `USER32!ReleaseDC` at `0x180063e30`

## pseudocode

```c
HBITMAP __fastcall PreMirrorBitmap(HBITMAP h, int wSrc, const unsigned int *a3, unsigned int a4)
{
  HBITMAP v7; // rsi
  HDC v8; // r15
  HDC CompatibleDC; // rdi
  HDC v10; // rax
  HDC v11; // rbx
  const unsigned int *v12; // r15
  int v13; // edx
  unsigned int v14; // esi
  int x1; // [rsp+30h] [rbp-99h]
  void *ppvBits; // [rsp+68h] [rbp-61h] BYREF
  const unsigned int *v18; // [rsp+70h] [rbp-59h]
  HBITMAP v19; // [rsp+78h] [rbp-51h]
  HDC DC; // [rsp+80h] [rbp-49h]
  HGDIOBJ ha; // [rsp+88h] [rbp-41h]
  HGDIOBJ v22; // [rsp+90h] [rbp-39h]
  _OWORD pv[2]; // [rsp+98h] [rbp-31h] BYREF
  BITMAPINFO pbmi; // [rsp+B8h] [rbp-11h] BYREF

  ppvBits = 0;
  v18 = a3;
  memset(pv, 0, sizeof(pv));
  if ( !h || !a3 || !a4 || !GetObjectA(h, 32, pv) )
    return 0;
  *(_QWORD *)&pbmi.bmiHeader.biWidth = *(_QWORD *)((char *)pv + 4);
  v7 = 0;
  pbmi.bmiHeader.biSize = 40;
  *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
  memset(&pbmi.bmiHeader.biSizeImage, 0, 24);
  DC = GetDC(0);
  v8 = DC;
  CompatibleDC = CreateCompatibleDC(DC);
  v10 = CreateCompatibleDC(DC);
  v11 = v10;
  if ( CompatibleDC )
  {
    if ( v10 )
    {
      v19 = CreateDIBSection(DC, &pbmi, 0, &ppvBits, 0, 0);
      v7 = v19;
      if ( v19 )
      {
        ha = SelectObject(CompatibleDC, h);
        v22 = SelectObject(v11, v7);
        BitBlt(v11, 0, 0, SDWORD1(pv[0]), SDWORD2(pv[0]), CompatibleDC, 0, 0, 0xCC0020u);
        if ( a4 )
        {
          v12 = v18;
          v13 = wSrc - 1;
          v14 = 0;
          do
          {
            x1 = v12[v14] * wSrc;
            StretchBlt(v11, x1 + v13, 0, -wSrc, SDWORD2(pv[0]), CompatibleDC, x1, 0, wSrc, SDWORD2(pv[0]), 0xCC0020u);
            ++v14;
            v13 = wSrc - 1;
          }
          while ( v14 < a4 );
          v7 = v19;
          v8 = DC;
        }
        SelectObject(CompatibleDC, ha);
        SelectObject(v11, v22);
      }
    }
  }
  DeleteDC(v11);
  DeleteDC(CompatibleDC);
  ReleaseDC(0, v8);
  return v7;
}

```

## disassembly

```asm
0x180063c2c  mov     [rsp-8+arg_18], rbx
0x180063c31  push    rbp
0x180063c32  push    rsi
0x180063c33  push    rdi
0x180063c34  push    r12
0x180063c36  push    r13
0x180063c38  push    r14
0x180063c3a  push    r15
0x180063c3c  lea     rbp, [rsp-27h]
0x180063c41  sub     rsp, 0F0h
0x180063c48  mov     rax, cs:__security_cookie
0x180063c4f  xor     rax, rsp
0x180063c52  mov     [rbp+57h+var_38], rax
0x180063c56  mov     [rbp+57h+ppvBits], 0
0x180063c5e  xorps   xmm0, xmm0
0x180063c61  mov     rax, r8
0x180063c64  mov     r12d, r9d
0x180063c67  mov     [rbp+57h+var_B0], rax
0x180063c6b  mov     r13d, edx
0x180063c6e  mov     r14, rcx
0x180063c71  movups  [rbp+57h+pv], xmm0
0x180063c75  movups  [rbp+57h+var_78], xmm0
0x180063c79  test    rcx, rcx
0x180063c7c  jz      loc_180063E3B
0x180063c82  test    rax, rax
0x180063c85  jz      loc_180063E3B
0x180063c8b  test    r9d, r9d
0x180063c8e  jz      loc_180063E3B
0x180063c94  lea     r8, [rbp+57h+pv]; pv
0x180063c98  mov     edx, 20h ; ' '; c
0x180063c9d  call    cs:__imp_GetObjectA
0x180063ca3  test    eax, eax
0x180063ca5  jz      loc_180063E3B
0x180063cab  mov     eax, dword ptr [rbp+57h+pv+4]
0x180063cae  xorps   xmm0, xmm0
0x180063cb1  mov     [rbp+57h+pbmi.bmiHeader.biWidth], eax
0x180063cb4  xor     ecx, ecx; hWnd
0x180063cb6  mov     eax, dword ptr [rbp+57h+pv+8]
0x180063cb9  xor     esi, esi
0x180063cbb  mov     [rbp+57h+pbmi.bmiHeader.biHeight], eax
0x180063cbe  xor     eax, eax
0x180063cc0  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biClrImportant], rax
0x180063cc4  mov     [rbp+57h+pbmi.bmiHeader.biSize], 28h ; '('
0x180063ccb  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biPlanes], 200001h
0x180063cd3  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biSizeImage], xmm0
0x180063cd7  call    cs:__imp_GetDC
0x180063cdd  mov     rcx, rax; hdc
0x180063ce0  mov     [rbp+57h+var_A0], rax
0x180063ce4  mov     r15, rax
0x180063ce7  call    cs:__imp_CreateCompatibleDC
0x180063ced  mov     rcx, r15; hdc
0x180063cf0  mov     rdi, rax
0x180063cf3  call    cs:__imp_CreateCompatibleDC
0x180063cf9  mov     rbx, rax
0x180063cfc  test    rdi, rdi
0x180063cff  jz      loc_180063E19
0x180063d05  test    rax, rax
0x180063d08  jz      loc_180063E19
0x180063d0e  mov     [rsp+120h+offset], esi; offset
0x180063d12  lea     r9, [rbp+57h+ppvBits]; ppvBits
0x180063d16  xor     r8d, r8d; usage
0x180063d19  mov     [rsp+120h+hSection], rsi; hSection
0x180063d1e  lea     rdx, [rbp+57h+pbmi]; pbmi
0x180063d22  mov     rcx, r15; hdc
0x180063d25  call    cs:__imp_CreateDIBSection
0x180063d2b  mov     [rbp+57h+var_A8], rax
0x180063d2f  mov     rsi, rax
0x180063d32  test    rax, rax
0x180063d35  jz      loc_180063E19
0x180063d3b  mov     rdx, r14; h
0x180063d3e  mov     rcx, rdi; hdc
0x180063d41  call    cs:__imp_SelectObject
0x180063d47  mov     rdx, rsi; h
0x180063d4a  mov     rcx, rbx; hdc
0x180063d4d  mov     [rbp+57h+h], rax
0x180063d51  call    cs:__imp_SelectObject
0x180063d57  mov     ecx, dword ptr [rbp+57h+pv+8]
0x180063d5a  xor     r14d, r14d
0x180063d5d  mov     r9d, dword ptr [rbp+57h+pv+4]; cx
0x180063d61  xor     r8d, r8d; y
0x180063d64  mov     [rsp+120h+rop], 0CC0020h; rop
0x180063d6c  xor     edx, edx; x
0x180063d6e  mov     [rsp+120h+y1], r14d; y1
0x180063d73  mov     [rsp+120h+x1], r14d; x1
0x180063d78  mov     qword ptr [rsp+120h+offset], rdi; hdcSrc
0x180063d7d  mov     dword ptr [rsp+120h+hSection], ecx; cy
0x180063d81  mov     rcx, rbx; hdc
0x180063d84  mov     [rbp+57h+var_90], rax
0x180063d88  call    cs:__imp_BitBlt
0x180063d8e  mov     [rbp+57h+var_C0], r14d
0x180063d92  test    r12d, r12d
0x180063d95  jz      short loc_180063DFF
0x180063d97  mov     r15, [rbp+57h+var_B0]
0x180063d9b  lea     edx, [r13-1]
0x180063d9f  mov     esi, [rbp+57h+var_C0]
0x180063da2  mov     r14d, r13d
0x180063da5  neg     r14d
0x180063da8  mov     [rsp+120h+var_D0], 0CC0020h; rop
0x180063db0  mov     ecx, r13d
0x180063db3  mov     eax, esi
0x180063db5  mov     r9d, r14d; wDest
0x180063db8  xor     r8d, r8d; yDest
0x180063dbb  imul    ecx, [r15+rax*4]
0x180063dc0  mov     eax, dword ptr [rbp+57h+pv+8]
0x180063dc3  mov     [rsp+120h+hSrc], eax; hSrc
0x180063dc7  mov     [rsp+120h+rop], r13d; wSrc
0x180063dcc  mov     [rsp+120h+y1], 0; ySrc
0x180063dd4  mov     [rsp+120h+x1], ecx; xSrc
0x180063dd8  add     edx, ecx; xDest
0x180063dda  mov     qword ptr [rsp+120h+offset], rdi; hdcSrc
0x180063ddf  mov     rcx, rbx; hdcDest
0x180063de2  mov     dword ptr [rsp+120h+hSection], eax; hDest
0x180063de6  call    cs:__imp_StretchBlt
0x180063dec  inc     esi
0x180063dee  lea     edx, [r13-1]
0x180063df2  cmp     esi, r12d
0x180063df5  jb      short loc_180063DA8
0x180063df7  mov     rsi, [rbp+57h+var_A8]
0x180063dfb  mov     r15, [rbp+57h+var_A0]
0x180063dff  mov     rdx, [rbp+57h+h]; h
0x180063e03  mov     rcx, rdi; hdc
0x180063e06  call    cs:__imp_SelectObject
0x180063e0c  mov     rdx, [rbp+57h+var_90]; h
0x180063e10  mov     rcx, rbx; hdc
0x180063e13  call    cs:__imp_SelectObject
0x180063e19  mov     rcx, rbx; hdc
0x180063e1c  call    cs:__imp_DeleteDC
0x180063e22  mov     rcx, rdi; hdc
0x180063e25  call    cs:__imp_DeleteDC
0x180063e2b  mov     rdx, r15; hDC
0x180063e2e  xor     ecx, ecx; hWnd
0x180063e30  call    cs:__imp_ReleaseDC
0x180063e36  mov     rax, rsi
0x180063e39  jmp     short loc_180063E3D
0x180063e3b  xor     eax, eax
0x180063e3d  mov     rcx, [rbp+57h+var_38]
0x180063e41  xor     rcx, rsp; StackCookie
0x180063e44  call    __security_check_cookie
0x180063e49  mov     rbx, [rsp+120h+arg_18]
0x180063e51  add     rsp, 0F0h
0x180063e58  pop     r15
0x180063e5a  pop     r14
0x180063e5c  pop     r13
0x180063e5e  pop     r12
0x180063e60  pop     rdi
0x180063e61  pop     rsi
0x180063e62  pop     rbp
0x180063e63  retn
```
