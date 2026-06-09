# CopyOnWriteBitmap::CreateHBITMAP(HBITMAP__ * *,ulong)

- ea: `0x180063964`
- end: `0x180063cd0`
- name: `?CreateHBITMAP@CopyOnWriteBitmap@@AEAA?AW4Status@@PEAPEAUHBITMAP__@@K@Z`
- size: `876`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180061eec`
- `0x18006369c`

## callees

- `0x180019610`
- `0x18002c2c8`
- `0x180063964`
- `0x1800659ec`
- `0x18008efec`
- `0x1800d72b8`
- `0x180105d40`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!fesetround` at `0x180063b31`
- `api-ms-win-crt-runtime-l1-1-0!fesetround` at `0x180063c7c`
- `api-ms-win-crt-runtime-l1-1-0!fesetround` at `0x180063b31`
- `api-ms-win-crt-runtime-l1-1-0!fesetround` at `0x180063c7c`
- `api-ms-win-crt-runtime-l1-1-0!fegetround` at `0x180063b1a`
- `api-ms-win-crt-runtime-l1-1-0!fegetround` at `0x180063bba`
- `api-ms-win-crt-runtime-l1-1-0!fegetround` at `0x180063b1a`
- `api-ms-win-crt-runtime-l1-1-0!fegetround` at `0x180063bba`
- `GDI32!PatBlt` at `0x180063acf`
- `GDI32!PatBlt` at `0x180063acf`
- `GDI32!CreateBrushIndirect` at `0x180063a78`
- `GDI32!CreateBrushIndirect` at `0x180063a78`
- `GDI32!CreateDIBSection` at `0x180063a10`
- `GDI32!CreateDIBSection` at `0x180063a10`
- `GDI32!DeleteDC` at `0x180063c04`
- `GDI32!DeleteDC` at `0x180063c04`
- `GDI32!SelectObject` at `0x180063a2e`
- `GDI32!SelectObject` at `0x180063a96`
- `GDI32!SelectObject` at `0x180063bde`
- `GDI32!SelectObject` at `0x180063bf5`
- `GDI32!SelectObject` at `0x180063a2e`
- `GDI32!SelectObject` at `0x180063a96`
- `GDI32!SelectObject` at `0x180063bde`
- `GDI32!SelectObject` at `0x180063bf5`
- `GDI32!CreateCompatibleDC` at `0x1800639a1`
- `GDI32!CreateCompatibleDC` at `0x1800639a1`
- `GDI32!DeleteObject` at `0x180063c21`
- `GDI32!DeleteObject` at `0x180063cbf`
- `GDI32!DeleteObject` at `0x180063c21`
- `GDI32!DeleteObject` at `0x180063cbf`

## pseudocode

```c
void __fastcall __noreturn CopyOnWriteBitmap::CreateHBITMAP(LONG *a1, HBITMAP *a2, int a3)
{
  HGDIOBJ v5; // r13
  HDC CompatibleDC; // r15
  HBRUSH v7; // r12
  GpGraphics *v8; // r14
  HBITMAP v9; // rax
  HBITMAP v10; // rsi
  HBRUSH v11; // rax
  struct GpGraphics *v12; // rax
  signed __int32 v13; // eax
  int v14; // ebx
  int v15; // eax
  float v16; // xmm1_4
  unsigned int v17; // edx
  __int64 v18; // [rsp+30h] [rbp-D0h] BYREF
  float v19; // [rsp+38h] [rbp-C8h]
  float v20; // [rsp+3Ch] [rbp-C4h]
  signed __int32 v21; // [rsp+40h] [rbp-C0h] BYREF
  volatile signed __int32 *v22; // [rsp+48h] [rbp-B8h]
  void *ppvBits; // [rsp+50h] [rbp-B0h] BYREF
  HBITMAP *v24; // [rsp+58h] [rbp-A8h]
  HGDIOBJ h; // [rsp+60h] [rbp-A0h]
  LOGBRUSH plbrush; // [rsp+68h] [rbp-98h] BYREF
  BITMAPINFO pbmi; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v28[1504]; // [rsp+B0h] [rbp-50h] BYREF

  v24 = a2;
  v5 = 0;
  CompatibleDC = CreateCompatibleDC(0);
  if ( CompatibleDC )
  {
    pbmi.bmiHeader.biWidth = a1[41];
    pbmi.bmiHeader.biHeight = a1[42];
    v7 = 0;
    ppvBits = 0;
    v8 = 0;
    memset(&pbmi.bmiHeader.biSizeImage, 0, 24);
    pbmi.bmiHeader.biSize = 40;
    *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
    v9 = CreateDIBSection(CompatibleDC, &pbmi, 0, &ppvBits, 0, 0);
    v10 = v9;
    if ( v9 )
    {
      h = SelectObject(CompatibleDC, v9);
      if ( h )
      {
        HIDWORD(plbrush.lbHatch) = 0;
        plbrush.lbStyle = 0;
        *(_QWORD *)&plbrush.lbColor = ((unsigned __int8)a3 << 16) | BYTE2(a3) | (BYTE1(a3) << 8);
        v11 = CreateBrushIndirect(&plbrush);
        v7 = v11;
        if ( v11 )
        {
          v5 = SelectObject(CompatibleDC, v11);
          if ( v5 )
          {
            PatBlt(CompatibleDC, 0, 0, a1[41], a1[42], 0xF00021u);
            v12 = GpGraphics::GetFromHdc(CompatibleDC, 0);
            v8 = v12;
            if ( v12 )
            {
              if ( v12 == (struct GpGraphics *)-16LL )
              {
                v13 = 0;
                v22 = &v21;
              }
              else
              {
                v22 = (volatile signed __int32 *)((char *)v12 + 16);
                v13 = _InterlockedIncrement((volatile signed __int32 *)v12 + 4);
              }
              v21 = v13;
              if ( !v13 )
              {
                v14 = fegetround();
                if ( v14 != 256 )
                  fesetround(256);
                v15 = a1[41];
                v18 = 0;
                v16 = (float)a1[42];
                v19 = (float)v15;
                v20 = v16;
                GpBitmap::GpBitmap((GpBitmap *)v28, (const struct CopyOnWriteBitmap *)a1);
                if ( !(unsigned int)((__int64 (__fastcall *)(GpGraphics *, _BYTE *, __int64 *, __int64 *, int, _QWORD))GpGraphics::DrawImage)(
                                      v8,
                                      v28,
                                      &v18,
                                      &v18,
                                      2,
                                      0) )
                {
                  *v24 = v10;
                  v10 = 0;
                }
                GpBitmap::~GpBitmap((GpBitmap *)v28);
                if ( v14 != fegetround() )
                  fesetround(v14);
              }
              _InterlockedDecrement(v22);
            }
          }
        }
        SelectObject(CompatibleDC, h);
        if ( v5 )
          SelectObject(CompatibleDC, v5);
      }
    }
    DeleteDC(CompatibleDC);
    if ( v10 )
      DeleteObject(v10);
    if ( v7 )
      DeleteObject(v7);
    if ( v8 )
      GpGraphics::`scalar deleting destructor'(v8, v17);
  }
}

```

## disassembly

```asm
0x180063964  mov     [rsp-8+arg_18], rbx
0x180063969  push    rbp
0x18006396a  push    rsi
0x18006396b  push    rdi
0x18006396c  push    r12
0x18006396e  push    r13
0x180063970  push    r14
0x180063972  push    r15
0x180063974  lea     rbp, [rsp-5A0h]
0x18006397c  sub     rsp, 6A0h
0x180063983  mov     rax, cs:__security_cookie
0x18006398a  xor     rax, rsp
0x18006398d  mov     [rbp+5D0h+var_40], rax
0x180063994  mov     rdi, rcx
0x180063997  mov     [rsp+6D0h+var_678], rdx
0x18006399c  xor     ecx, ecx; hdc
0x18006399e  mov     ebx, r8d
0x1800639a1  call    cs:__imp_CreateCompatibleDC
0x1800639a8  nop     dword ptr [rax+rax+00h]
0x1800639ad  xor     r13d, r13d
0x1800639b0  mov     r15, rax
0x1800639b3  test    rax, rax
0x1800639b6  jz      loc_180063CB2
0x1800639bc  mov     eax, [rdi+0A4h]
0x1800639c2  lea     r9, [rsp+6D0h+ppvBits]; ppvBits
0x1800639c7  mov     [rsp+6D0h+pbmi.bmiHeader.biWidth], eax
0x1800639cb  lea     rdx, [rsp+6D0h+pbmi]; pbmi
0x1800639d0  mov     eax, [rdi+0A8h]
0x1800639d6  xorps   xmm0, xmm0
0x1800639d9  mov     [rsp+6D0h+offset], r13d; offset
0x1800639de  xor     r8d, r8d; usage
0x1800639e1  mov     rcx, r15; hdc
0x1800639e4  mov     [rbp+5D0h+pbmi.bmiHeader.biHeight], eax
0x1800639e7  mov     r12d, r13d
0x1800639ea  mov     [rsp+6D0h+ppvBits], r13
0x1800639ef  mov     r14d, r13d
0x1800639f2  mov     qword ptr [rbp+5D0h+pbmi.bmiHeader.biClrImportant], r13
0x1800639f6  movdqu  xmmword ptr [rbp+5D0h+pbmi.bmiHeader.biSizeImage], xmm0
0x1800639fb  mov     [rsp+6D0h+pbmi.bmiHeader.biSize], 28h ; '('
0x180063a03  mov     qword ptr [rbp+5D0h+pbmi.bmiHeader.biPlanes], 200001h
0x180063a0b  mov     [rsp+6D0h+hSection], r13; hSection
0x180063a10  call    cs:__imp_CreateDIBSection
0x180063a17  nop     dword ptr [rax+rax+00h]
0x180063a1c  mov     rsi, rax
0x180063a1f  test    rax, rax
0x180063a22  jz      loc_180063C5F
0x180063a28  mov     rdx, rax; h
0x180063a2b  mov     rcx, r15; hdc
0x180063a2e  call    cs:__imp_SelectObject
0x180063a35  nop     dword ptr [rax+rax+00h]
0x180063a3a  mov     [rsp+6D0h+h], rax
0x180063a3f  test    rax, rax
0x180063a42  jz      loc_180063C5F
0x180063a48  mov     eax, ebx
0x180063a4a  mov     [rsp+6D0h+plbrush.lbHatch], r13
0x180063a4f  shr     eax, 8
0x180063a52  movzx   edx, al
0x180063a55  mov     eax, ebx
0x180063a57  shr     eax, 10h
0x180063a5a  movzx   ecx, al
0x180063a5d  shl     edx, 8
0x180063a60  or      edx, ecx
0x180063a62  movzx   eax, bl
0x180063a65  shl     eax, 10h
0x180063a68  lea     rcx, [rsp+6D0h+plbrush]; plbrush
0x180063a6d  or      edx, eax
0x180063a6f  mov     [rsp+6D0h+plbrush.lbStyle], r13d
0x180063a74  mov     [rsp+6D0h+plbrush.lbColor], edx
0x180063a78  call    cs:__imp_CreateBrushIndirect
0x180063a7f  nop     dword ptr [rax+rax+00h]
0x180063a84  mov     r12, rax
0x180063a87  test    rax, rax
0x180063a8a  jz      loc_180063C8D
0x180063a90  mov     rdx, rax; h
0x180063a93  mov     rcx, r15; hdc
0x180063a96  call    cs:__imp_SelectObject
0x180063a9d  nop     dword ptr [rax+rax+00h]
0x180063aa2  mov     r13, rax
0x180063aa5  test    rax, rax
0x180063aa8  jz      loc_180063C8D
0x180063aae  mov     eax, [rdi+0A8h]
0x180063ab4  xor     r8d, r8d; y
0x180063ab7  mov     r9d, [rdi+0A4h]; w
0x180063abe  xor     edx, edx; x
0x180063ac0  mov     [rsp+6D0h+offset], 0F00021h; rop
0x180063ac8  mov     rcx, r15; hdc
0x180063acb  mov     dword ptr [rsp+6D0h+hSection], eax; h
0x180063acf  call    cs:__imp_PatBlt
0x180063ad6  nop     dword ptr [rax+rax+00h]
0x180063adb  xor     edx, edx; void *
0x180063add  mov     rcx, r15; HDC
0x180063ae0  call    ?GetFromHdc@GpGraphics@@SAPEAV1@PEAUHDC__@@PEAX@Z
0x180063ae5  mov     r14, rax
0x180063ae8  test    rax, rax
0x180063aeb  jz      loc_180063CA8
0x180063af1  lea     rcx, [rax+10h]
0x180063af5  test    rcx, rcx
0x180063af8  jz      loc_180063C97
0x180063afe  mov     [rsp+6D0h+var_688], rcx
0x180063b03  mov     eax, 1
0x180063b08  lock xadd [rcx], eax
0x180063b0c  inc     eax
0x180063b0e  mov     [rsp+6D0h+var_690], eax
0x180063b12  test    eax, eax
0x180063b14  jnz     loc_180063C70
0x180063b1a  call    cs:__imp_fegetround
0x180063b21  nop     dword ptr [rax+rax+00h]
0x180063b26  mov     ecx, 100h; Round
0x180063b2b  mov     ebx, eax
0x180063b2d  cmp     eax, ecx
0x180063b2f  jz      short loc_180063B3D
0x180063b31  call    cs:__imp_fesetround
0x180063b38  nop     dword ptr [rax+rax+00h]
0x180063b3d  mov     eax, [rdi+0A4h]
0x180063b43  lea     rcx, [rbp+5D0h+var_620]; this
0x180063b47  xorps   xmm0, xmm0
0x180063b4a  mov     [rsp+6D0h+var_6A0], 0
0x180063b53  xorps   xmm1, xmm1
0x180063b56  mov     rdx, rdi; struct CopyOnWriteBitmap *
0x180063b59  cvtsi2ss xmm0, rax
0x180063b5e  mov     eax, [rdi+0A8h]
0x180063b64  cvtsi2ss xmm1, rax
0x180063b69  movss   [rsp+6D0h+var_698], xmm0
0x180063b6f  movss   [rsp+6D0h+var_694], xmm1
0x180063b75  call    ??0GpBitmap@@AEAA@PEBVCopyOnWriteBitmap@@@Z
0x180063b7a  lea     r9, [rsp+6D0h+var_6A0]
0x180063b7f  mov     qword ptr [rsp+6D0h+offset], 0
0x180063b88  lea     r8, [rsp+6D0h+var_6A0]
0x180063b8d  mov     dword ptr [rsp+6D0h+hSection], 2
0x180063b95  lea     rdx, [rbp+5D0h+var_620]
0x180063b99  mov     rcx, r14
0x180063b9c  call    ?DrawImage@GpGraphics@@QEAA?AW4Status@@PEAVGpImage@@AEBVRectF@@1W4Unit@@PEBVGpImageAttributes@@@Z
0x180063ba1  mov     edi, eax
0x180063ba3  test    eax, eax
0x180063ba5  jnz     short loc_180063BB1
0x180063ba7  mov     rax, [rsp+6D0h+var_678]
0x180063bac  mov     [rax], rsi
0x180063baf  xor     esi, esi
0x180063bb1  lea     rcx, [rbp+5D0h+var_620]; this
0x180063bb5  call    ??1GpBitmap@@EEAA@XZ
0x180063bba  call    cs:__imp_fegetround
0x180063bc1  nop     dword ptr [rax+rax+00h]
0x180063bc6  cmp     ebx, eax
0x180063bc8  jnz     loc_180063C7A
0x180063bce  mov     rax, [rsp+6D0h+var_688]
0x180063bd3  lock dec dword ptr [rax]
0x180063bd6  mov     rdx, [rsp+6D0h+h]; h
0x180063bdb  mov     rcx, r15; hdc
0x180063bde  call    cs:__imp_SelectObject
0x180063be5  nop     dword ptr [rax+rax+00h]
0x180063bea  test    r13, r13
0x180063bed  jz      short loc_180063C01
0x180063bef  mov     rdx, r13; h
0x180063bf2  mov     rcx, r15; hdc
0x180063bf5  call    cs:__imp_SelectObject
0x180063bfc  nop     dword ptr [rax+rax+00h]
0x180063c01  mov     rcx, r15; hdc
0x180063c04  call    cs:__imp_DeleteDC
0x180063c0b  nop     dword ptr [rax+rax+00h]
0x180063c10  test    rsi, rsi
0x180063c13  jnz     loc_180063CBC
0x180063c19  test    r12, r12
0x180063c1c  jz      short loc_180063C2D
0x180063c1e  mov     rcx, r12; ho
0x180063c21  call    cs:__imp_DeleteObject
0x180063c28  nop     dword ptr [rax+rax+00h]
0x180063c2d  test    r14, r14
0x180063c30  jnz     short loc_180063C66
0x180063c32  mov     eax, edi
0x180063c34  mov     rcx, [rbp+5D0h+var_40]
0x180063c3b  xor     rcx, rsp; StackCookie
0x180063c3e  call    __security_check_cookie
0x180063c43  mov     rbx, [rsp+6D0h+arg_18]
0x180063c4b  add     rsp, 6A0h
0x180063c52  pop     r15
0x180063c54  pop     r14
0x180063c56  pop     r13
0x180063c58  pop     r12
0x180063c5a  pop     rdi
0x180063c5b  pop     rsi
0x180063c5c  pop     rbp
0x180063c5d  retn
0x180063c5f  mov     edi, 7
0x180063c64  jmp     short loc_180063C01
0x180063c66  mov     rcx, r14; this
0x180063c69  call    ??_GGpGraphics@@QEAAPEAXI@Z
0x180063c6e  jmp     short loc_180063C32
0x180063c70  mov     edi, 4
0x180063c75  jmp     loc_180063BCE
0x180063c7a  mov     ecx, ebx; Round
0x180063c7c  call    cs:__imp_fesetround
0x180063c83  nop     dword ptr [rax+rax+00h]
0x180063c88  jmp     loc_180063BCE
0x180063c8d  mov     edi, 7
0x180063c92  jmp     loc_180063BD6
0x180063c97  lea     rcx, [rsp+6D0h+var_690]
0x180063c9c  xor     eax, eax
0x180063c9e  mov     [rsp+6D0h+var_688], rcx
0x180063ca3  jmp     loc_180063B0E
0x180063ca8  mov     edi, 3
0x180063cad  jmp     loc_180063BD6
0x180063cb2  mov     edi, 7
0x180063cb7  jmp     loc_180063C32
0x180063cbc  mov     rcx, rsi; ho
0x180063cbf  call    cs:__imp_DeleteObject
0x180063cc6  nop     dword ptr [rax+rax+00h]
0x180063ccb  jmp     loc_180063C19
```
