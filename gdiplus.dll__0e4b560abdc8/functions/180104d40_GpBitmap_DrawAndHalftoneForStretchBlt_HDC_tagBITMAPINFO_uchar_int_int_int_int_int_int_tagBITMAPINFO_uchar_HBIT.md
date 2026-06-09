# GpBitmap::DrawAndHalftoneForStretchBlt(HDC__ *,tagBITMAPINFO *,uchar *,int,int,int,int,int,int,tagBITMAPINFO * *,uchar * *,HBITMAP__ * *,InterpolationMode)

- ea: `0x180104d40`
- end: `0x18010504a`
- name: `?DrawAndHalftoneForStretchBlt@GpBitmap@@SA?AW4Status@@PEAUHDC__@@PEAUtagBITMAPINFO@@PEAEHHHHHHPEAPEAU4@PEAPEAEPEAPEAUHBITMAP__@@W4InterpolationMode@@@Z`
- size: `778`
- prototype: `__int64 __fastcall(HDC, struct tagBITMAPINFO *, void *, int, int, int, int, int, int, HPALETTE hPal, void **ppvBits, HGDIOBJ *, unsigned int)`
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1800526b8`
- `0x18013b240`

## callees

- `0x180003b38`
- `0x1800082c4`
- `0x1800083a4`
- `0x1800083f8`
- `0x18000e6d0`
- `0x18001f950`
- `0x180064e70`
- `0x18006f7c4`
- `0x180070dd4`
- `0x1800e5044`
- `0x1800ea0ec`
- `0x180104d40`
- `0x180175010`

## import_xrefs

- `GDI32!RealizePalette` at `0x180104ea3`
- `GDI32!RealizePalette` at `0x180104ea3`
- `GDI32!GetPaletteEntries` at `0x180104e0b`
- `GDI32!GetPaletteEntries` at `0x180104e0b`
- `GDI32!CreateDIBSection` at `0x180104e4a`
- `GDI32!CreateDIBSection` at `0x180104e4a`
- `GDI32!DeleteDC` at `0x180104ff1`
- `GDI32!DeleteDC` at `0x180104ff1`
- `GDI32!SelectObject` at `0x180104e7b`
- `GDI32!SelectObject` at `0x180104e7b`
- `GDI32!CreateCompatibleDC` at `0x180104e21`
- `GDI32!CreateCompatibleDC` at `0x180104e21`
- `GDI32!SelectPalette` at `0x180104e94`
- `GDI32!SelectPalette` at `0x180104e94`
- `GDI32!GetObjectA` at `0x180104df1`
- `GDI32!GetObjectA` at `0x180104df1`
- `GDI32!GetCurrentObject` at `0x180104dca`
- `GDI32!GetCurrentObject` at `0x180104dca`
- `GDI32!DeleteObject` at `0x180105015`
- `GDI32!DeleteObject` at `0x180105015`

## pseudocode

```c
__int64 __fastcall GpBitmap::DrawAndHalftoneForStretchBlt(
        HDC a1,
        struct tagBITMAPINFO *a2,
        void *a3,
        int a4,
        int a5,
        int a6,
        int a7,
        int a8,
        int a9,
        HPALETTE hPal,
        void **ppvBits,
        HGDIOBJ *a12,
        unsigned int a13)
{
  unsigned int v15; // ebx
  __int64 v16; // rax
  __int64 v18; // rsi
  HDC CompatibleDC; // rdi
  HBITMAP DIBSection; // rax
  struct GpGraphics *v22; // rax
  struct GpGraphics *v23; // r14
  GpBitmap *v24; // rax
  unsigned int v25; // edx
  GpBitmap *v26; // rax
  GpBitmap *v27; // rsi
  HANDLE hSection; // [rsp+20h] [rbp-50h]
  _WORD pv[2]; // [rsp+30h] [rbp-40h] BYREF
  float v30[4]; // [rsp+34h] [rbp-3Ch] BYREF
  _DWORD v31[5]; // [rsp+44h] [rbp-2Ch] BYREF
  _BYTE v32[8]; // [rsp+58h] [rbp-18h] BYREF
  volatile signed __int32 *v33; // [rsp+60h] [rbp-10h]
  HPALETTE hPala; // [rsp+F8h] [rbp+88h]

  v15 = 1;
  v16 = GpMallocEx(1064, 0);
  v18 = v16;
  *(_QWORD *)hPal = v16;
  if ( !v16 )
    return 3;
  memset_0((void *)(v16 + 16), 0, 0x418u);
  *(_DWORD *)(v18 + 4) = a8;
  *(_DWORD *)(v18 + 8) = a9;
  *(_DWORD *)v18 = 40;
  *(_DWORD *)(v18 + 12) = 524289;
  pv[0] = 0;
  hPala = (HPALETTE)GetCurrentObject(a1, 5u);
  GetObjectA(hPala, 2, pv);
  GetPaletteEntries(hPala, 0, pv[0], (LPPALETTEENTRY)(v18 + 40));
  *(_DWORD *)(v18 + 32) = pv[0];
  CompatibleDC = CreateCompatibleDC(a1);
  DIBSection = CreateDIBSection(a1, (const BITMAPINFO *)v18, 0, ppvBits, 0, 0);
  *a12 = DIBSection;
  if ( !DIBSection )
  {
    if ( CompatibleDC )
      goto LABEL_14;
LABEL_15:
    GpFree(*(_QWORD *)hPal);
    *(_QWORD *)hPal = 0;
    if ( *a12 )
    {
      DeleteObject(*a12);
      *a12 = 0;
    }
    *ppvBits = 0;
    return v15;
  }
  if ( !CompatibleDC )
    goto LABEL_15;
  SelectObject(CompatibleDC, DIBSection);
  SelectPalette(CompatibleDC, hPala, 0);
  RealizePalette(CompatibleDC);
  v22 = GpGraphics::GetFromHdc(CompatibleDC, 0);
  v23 = v22;
  if ( v22 && *((_DWORD *)v22 + 2) == 1634879281 )
  {
    v24 = (GpBitmap *)GpMallocEx(1504, 0);
    if ( v24 )
    {
      v26 = GpBitmap::GpBitmap(v24, a2, a3);
      v27 = v26;
      if ( v26 )
      {
        if ( (*(unsigned int (__fastcall **)(GpBitmap *))(*(_QWORD *)v26 + 8LL))(v26) )
        {
          GpRuntime::GpLock::GpLock((GpRuntime::GpLock *)v32, (struct GpGraphics *)((char *)v23 + 16));
          GpGraphics::SetCompositingMode(v23, 1);
          GpGraphics::SetInterpolationMode(v23, a13);
          GpGraphics::SetPixelOffsetMode(v23, 4);
          v31[0] = 0;
          v31[1] = 0;
          LODWORD(hSection) = 2;
          v30[0] = (float)a4;
          v30[1] = (float)a5;
          v30[2] = (float)a6;
          v30[3] = (float)a7;
          *(float *)&v31[2] = (float)a8;
          *(float *)&v31[3] = (float)a9;
          v15 = GpGraphics::DrawImage(v23, v27, v31, v30, hSection, 0);
          _InterlockedDecrement(v33);
        }
        (*(void (__fastcall **)(GpBitmap *))(*(_QWORD *)v27 + 56LL))(v27);
      }
    }
    GpGraphics::`scalar deleting destructor'(v23, v25);
  }
LABEL_14:
  DeleteDC(CompatibleDC);
  if ( v15 )
    goto LABEL_15;
  return v15;
}

```

## disassembly

```asm
0x180104d40  mov     [rsp-38h+arg_0], rbx
0x180104d45  mov     [rsp-38h+arg_18], r9d
0x180104d4a  mov     [rsp-38h+arg_8], rdx
0x180104d4f  push    rbp
0x180104d50  push    rsi
0x180104d51  push    rdi
0x180104d52  push    r12
0x180104d54  push    r13
0x180104d56  push    r14
0x180104d58  push    r15
0x180104d5a  mov     rbp, rsp
0x180104d5d  sub     rsp, 70h
0x180104d61  mov     r14, rcx
0x180104d64  xor     edx, edx
0x180104d66  mov     ecx, 428h
0x180104d6b  mov     r13, r8
0x180104d6e  mov     ebx, 1
0x180104d73  call    GpMallocEx
0x180104d78  mov     r15, [rbp+hPal]
0x180104d7f  xor     r12d, r12d
0x180104d82  mov     rsi, rax
0x180104d85  mov     [r15], rax
0x180104d88  test    rax, rax
0x180104d8b  jnz     short loc_180104D95
0x180104d8d  lea     eax, [rbx+2]
0x180104d90  jmp     loc_180105031
0x180104d95  lea     rcx, [rax+10h]; void *
0x180104d99  xor     edx, edx; Val
0x180104d9b  mov     r8d, 418h; Size
0x180104da1  call    memset_0
0x180104da6  mov     eax, [rbp+arg_38]
0x180104da9  mov     edx, 5; type
0x180104dae  mov     [rsi+4], eax
0x180104db1  mov     rcx, r14; hdc
0x180104db4  mov     eax, [rbp+arg_40]
0x180104dba  mov     [rsi+8], eax
0x180104dbd  mov     dword ptr [rsi], 28h ; '('
0x180104dc3  mov     dword ptr [rsi+0Ch], 80001h
0x180104dca  call    cs:__imp_GetCurrentObject
0x180104dd1  nop     dword ptr [rax+rax+00h]
0x180104dd6  lea     r8, [rbp+pv]; pv
0x180104dda  mov     [rbp+pv], r12w
0x180104ddf  mov     rcx, rax; h
0x180104de2  mov     [rbp+hPal], rax
0x180104de9  mov     edx, 2; c
0x180104dee  mov     rdi, rax
0x180104df1  call    cs:__imp_GetObjectA
0x180104df8  nop     dword ptr [rax+rax+00h]
0x180104dfd  movzx   r8d, [rbp+pv]; cEntries
0x180104e02  lea     r9, [rsi+28h]; pPalEntries
0x180104e06  xor     edx, edx; iStart
0x180104e08  mov     rcx, rdi; hpal
0x180104e0b  call    cs:__imp_GetPaletteEntries
0x180104e12  nop     dword ptr [rax+rax+00h]
0x180104e17  movzx   eax, [rbp+pv]
0x180104e1b  mov     rcx, r14; hdc
0x180104e1e  mov     [rsi+20h], eax
0x180104e21  call    cs:__imp_CreateCompatibleDC
0x180104e28  nop     dword ptr [rax+rax+00h]
0x180104e2d  mov     r9, [rbp+ppvBits]; ppvBits
0x180104e34  xor     r8d, r8d; usage
0x180104e37  mov     rdx, rsi; pbmi
0x180104e3a  mov     [rsp+70h+offset], r12d; offset
0x180104e3f  mov     rcx, r14; hdc
0x180104e42  mov     [rsp+70h+hSection], r12; hSection
0x180104e47  mov     rdi, rax
0x180104e4a  call    cs:__imp_CreateDIBSection
0x180104e51  nop     dword ptr [rax+rax+00h]
0x180104e56  mov     r12, [rbp+arg_58]
0x180104e5d  xor     esi, esi
0x180104e5f  mov     [r12], rax
0x180104e63  test    rax, rax
0x180104e66  jz      loc_180104FE9
0x180104e6c  test    rdi, rdi
0x180104e6f  jz      loc_180105001
0x180104e75  mov     rdx, rax; h
0x180104e78  mov     rcx, rdi; hdc
0x180104e7b  call    cs:__imp_SelectObject
0x180104e82  nop     dword ptr [rax+rax+00h]
0x180104e87  mov     rdx, [rbp+hPal]; hPal
0x180104e8e  xor     r8d, r8d; bForceBkgd
0x180104e91  mov     rcx, rdi; hdc
0x180104e94  call    cs:__imp_SelectPalette
0x180104e9b  nop     dword ptr [rax+rax+00h]
0x180104ea0  mov     rcx, rdi; hdc
0x180104ea3  call    cs:__imp_RealizePalette
0x180104eaa  nop     dword ptr [rax+rax+00h]
0x180104eaf  xor     edx, edx; void *
0x180104eb1  mov     rcx, rdi; hdc
0x180104eb4  call    ?GetFromHdc@GpGraphics@@SAPEAV1@PEAUHDC__@@PEAX@Z; GpGraphics::GetFromHdc(HDC__ *,void *)
0x180104eb9  mov     r14, rax
0x180104ebc  test    rax, rax
0x180104ebf  jz      loc_180104FEE
0x180104ec5  cmp     dword ptr [rax+8], 61724731h
0x180104ecc  jnz     loc_180104FEE
0x180104ed2  xor     edx, edx
0x180104ed4  mov     ecx, 5E0h
0x180104ed9  call    GpMallocEx
0x180104ede  test    rax, rax
0x180104ee1  jz      loc_180104FDF
0x180104ee7  mov     rdx, [rbp+arg_8]; struct tagBITMAPINFO *
0x180104eeb  mov     r8, r13; void *
0x180104eee  mov     rcx, rax; this
0x180104ef1  call    ??0GpBitmap@@QEAA@PEAUtagBITMAPINFO@@PEAXH@Z; GpBitmap::GpBitmap(tagBITMAPINFO *,void *,int)
0x180104ef6  mov     rsi, rax
0x180104ef9  test    rax, rax
0x180104efc  jz      loc_180104FDD
0x180104f02  mov     rax, [rax]
0x180104f05  mov     rcx, rsi
0x180104f08  mov     rax, [rax+8]
0x180104f0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180104f11  test    eax, eax
0x180104f13  jz      loc_180104FCE
0x180104f19  lea     rdx, [r14+10h]; struct GpRuntime::GpLockable *
0x180104f1d  lea     rcx, [rbp+var_18]; this
0x180104f21  call    ??0GpLock@GpRuntime@@QEAA@PEAVGpLockable@1@@Z; GpRuntime::GpLock::GpLock(GpRuntime::GpLockable *)
0x180104f26  mov     edx, ebx
0x180104f28  mov     rcx, r14
0x180104f2b  call    ?SetCompositingMode@GpGraphics@@QEAAXW4CompositingMode@@@Z; GpGraphics::SetCompositingMode(CompositingMode)
0x180104f30  mov     edx, [rbp+arg_60]
0x180104f36  mov     rcx, r14
0x180104f39  call    ?SetInterpolationMode@GpGraphics@@QEAAXW4InterpolationMode@@@Z; GpGraphics::SetInterpolationMode(InterpolationMode)
0x180104f3e  mov     edx, 4
0x180104f43  mov     rcx, r14
0x180104f46  call    ?SetPixelOffsetMode@GpGraphics@@QEAAXW4PixelOffsetMode@@@Z; GpGraphics::SetPixelOffsetMode(PixelOffsetMode)
0x180104f4b  movd    xmm0, [rbp+arg_18]
0x180104f50  lea     r9, [rbp+var_3C]
0x180104f54  movd    xmm1, [rbp+arg_20]
0x180104f59  lea     r8, [rbp+var_2C]
0x180104f5d  and     qword ptr [rsp+70h+offset], 0
0x180104f63  mov     rdx, rsi
0x180104f66  and     [rbp+var_2C], 0
0x180104f6a  mov     rcx, r14
0x180104f6d  and     [rbp+var_28], 0
0x180104f71  cvtdq2ps xmm0, xmm0
0x180104f74  mov     dword ptr [rsp+70h+hSection], 2
0x180104f7c  cvtdq2ps xmm1, xmm1
0x180104f7f  movss   [rbp+var_3C], xmm0
0x180104f84  movd    xmm0, [rbp+arg_28]
0x180104f89  movss   [rbp+var_38], xmm1
0x180104f8e  movd    xmm1, [rbp+arg_30]
0x180104f93  cvtdq2ps xmm0, xmm0
0x180104f96  cvtdq2ps xmm1, xmm1
0x180104f99  movss   [rbp+var_34], xmm0
0x180104f9e  movd    xmm0, [rbp+arg_40]
0x180104fa6  movss   [rbp+var_30], xmm1
0x180104fab  movd    xmm1, [rbp+arg_38]
0x180104fb0  cvtdq2ps xmm1, xmm1
0x180104fb3  cvtdq2ps xmm0, xmm0
0x180104fb6  movss   [rbp+var_24], xmm1
0x180104fbb  movss   [rbp+var_20], xmm0
0x180104fc0  call    ?DrawImage@GpGraphics@@QEAA?AW4Status@@PEAVGpImage@@AEBVRectF@@1W4Unit@@PEBVGpImageAttributes@@@Z; GpGraphics::DrawImage(GpImage *,RectF const &,RectF const &,Unit,GpImageAttributes const *)
0x180104fc5  mov     rcx, [rbp+var_10]
0x180104fc9  mov     ebx, eax
0x180104fcb  lock dec dword ptr [rcx]
0x180104fce  mov     rcx, [rsi]
0x180104fd1  mov     rax, [rcx+38h]
0x180104fd5  mov     rcx, rsi
0x180104fd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180104fdd  xor     esi, esi
0x180104fdf  mov     rcx, r14; this
0x180104fe2  call    ??_GGpGraphics@@QEAAPEAXI@Z; GpGraphics::`scalar deleting destructor'(uint)
0x180104fe7  jmp     short loc_180104FEE
0x180104fe9  test    rdi, rdi
0x180104fec  jz      short loc_180105001
0x180104fee  mov     rcx, rdi; hdc
0x180104ff1  call    cs:__imp_DeleteDC
0x180104ff8  nop     dword ptr [rax+rax+00h]
0x180104ffd  test    ebx, ebx
0x180104fff  jz      short loc_18010502F
0x180105001  mov     rcx, [r15]
0x180105004  call    GpFree
0x180105009  mov     [r15], rsi
0x18010500c  mov     rcx, [r12]; ho
0x180105010  test    rcx, rcx
0x180105013  jz      short loc_180105025
0x180105015  call    cs:__imp_DeleteObject
0x18010501c  nop     dword ptr [rax+rax+00h]
0x180105021  mov     [r12], rsi
0x180105025  mov     rax, [rbp+ppvBits]
0x18010502c  mov     [rax], rsi
0x18010502f  mov     eax, ebx
0x180105031  mov     rbx, [rsp+70h+arg_0]
0x180105039  add     rsp, 70h
0x18010503d  pop     r15
0x18010503f  pop     r14
0x180105041  pop     r13
0x180105043  pop     r12
0x180105045  pop     rdi
0x180105046  pop     rsi
0x180105047  pop     rbp
0x180105048  retn
```
