# GpBitmap::DrawAndHalftoneForStretchBlt(HDC__ *,tagBITMAPINFO *,uchar *,int,int,int,int,int,int,tagBITMAPINFO * *,uchar * *,HBITMAP__ * *,InterpolationMode)

- ea: `0x180115cf0`
- end: `0x180115fc7`
- name: `?DrawAndHalftoneForStretchBlt@GpBitmap@@SA?AW4Status@@PEAUHDC__@@PEAUtagBITMAPINFO@@PEAEHHHHHHPEAPEAU4@PEAPEAEPEAPEAUHBITMAP__@@W4InterpolationMode@@@Z`
- size: `727`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180068f60`
- `0x18013c704`

## callees

- `0x1800067bc`
- `0x1800067dc`
- `0x180009eb8`
- `0x18001ec80`
- `0x18002739c`
- `0x18005e5c0`
- `0x18008e8c0`
- `0x180099e90`
- `0x180099ee0`
- `0x18009a0c0`
- `0x1800ff04c`
- `0x180115cf0`
- `0x180169010`

## import_xrefs

- `GDI32!RealizePalette` at `0x180115e28`
- `GDI32!RealizePalette` at `0x180115e28`
- `GDI32!GetPaletteEntries` at `0x180115da9`
- `GDI32!GetPaletteEntries` at `0x180115da9`
- `GDI32!CreateDIBSection` at `0x180115de3`
- `GDI32!CreateDIBSection` at `0x180115de3`
- `GDI32!DeleteDC` at `0x180115f6f`
- `GDI32!DeleteDC` at `0x180115f6f`
- `GDI32!SelectObject` at `0x180115e0c`
- `GDI32!SelectObject` at `0x180115e0c`
- `GDI32!CreateCompatibleDC` at `0x180115db9`
- `GDI32!CreateCompatibleDC` at `0x180115db9`
- `GDI32!SelectPalette` at `0x180115e1f`
- `GDI32!SelectPalette` at `0x180115e1f`
- `GDI32!GetObjectA` at `0x180115d95`
- `GDI32!GetObjectA` at `0x180115d95`
- `GDI32!GetCurrentObject` at `0x180115d75`
- `GDI32!GetCurrentObject` at `0x180115d75`
- `GDI32!DeleteObject` at `0x180115f91`
- `GDI32!DeleteObject` at `0x180115f91`

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
  __int64 v15; // rax
  __int64 v17; // rbx
  unsigned int v19; // esi
  HDC CompatibleDC; // rdi
  HBITMAP DIBSection; // rax
  struct GpGraphics *v22; // rax
  struct GpGraphics *v23; // r14
  GpBitmap *v24; // rax
  unsigned int v25; // edx
  int v26; // r9d
  GpBitmap *v27; // rax
  GpBitmap *v28; // rbx
  _WORD pv[2]; // [rsp+30h] [rbp-40h] BYREF
  float v30[4]; // [rsp+34h] [rbp-3Ch] BYREF
  __int64 v31; // [rsp+44h] [rbp-2Ch] BYREF
  float v32; // [rsp+4Ch] [rbp-24h]
  float v33; // [rsp+50h] [rbp-20h]
  _BYTE v34[8]; // [rsp+58h] [rbp-18h] BYREF
  volatile signed __int32 *v35; // [rsp+60h] [rbp-10h]
  HPALETTE hPala; // [rsp+F8h] [rbp+88h]

  v15 = GpMallocEx(1064, 0);
  v17 = v15;
  *(_QWORD *)hPal = v15;
  if ( !v15 )
    return 3;
  memset_0((void *)(v15 + 16), 0, 0x418u);
  v19 = 1;
  *(_DWORD *)(v17 + 4) = a8;
  *(_DWORD *)v17 = 40;
  *(_DWORD *)(v17 + 12) = 524289;
  *(_DWORD *)(v17 + 8) = a9;
  hPala = (HPALETTE)GetCurrentObject(a1, 5u);
  pv[0] = 0;
  GetObjectA(hPala, 2, pv);
  GetPaletteEntries(hPala, 0, pv[0], (LPPALETTEENTRY)(v17 + 40));
  *(_DWORD *)(v17 + 32) = pv[0];
  CompatibleDC = CreateCompatibleDC(a1);
  DIBSection = CreateDIBSection(a1, (const BITMAPINFO *)v17, 0, ppvBits, 0, 0);
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
    return v19;
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
      v27 = GpBitmap::GpBitmap(v24, a2, a3, v26);
      v28 = v27;
      if ( v27 )
      {
        if ( (*(unsigned int (__fastcall **)(GpBitmap *))(*(_QWORD *)v27 + 8LL))(v27) )
        {
          GpRuntime::GpLock::GpLock((GpRuntime::GpLock *)v34, (struct GpGraphics *)((char *)v23 + 16));
          GpGraphics::SetCompositingMode(v23, 1);
          GpGraphics::SetInterpolationMode(v23, a13);
          GpGraphics::SetPixelOffsetMode(v23, 4);
          v31 = 0;
          v30[0] = (float)a4;
          v30[1] = (float)a5;
          v30[2] = (float)a6;
          v30[3] = (float)a7;
          v32 = (float)a8;
          v33 = (float)a9;
          v19 = GpGraphics::DrawImage(v23, v28, &v31, v30, 2, 0);
          _InterlockedDecrement(v35);
        }
        (*(void (__fastcall **)(GpBitmap *))(*(_QWORD *)v28 + 56LL))(v28);
      }
    }
    GpGraphics::`scalar deleting destructor'(v23, v25);
  }
LABEL_14:
  DeleteDC(CompatibleDC);
  if ( v19 )
    goto LABEL_15;
  return v19;
}

```

## disassembly

```asm
0x180115cf0  mov     [rsp-38h+arg_0], rbx
0x180115cf5  mov     [rsp-38h+arg_18], r9d
0x180115cfa  mov     [rsp-38h+arg_8], rdx
0x180115cff  push    rbp
0x180115d00  push    rsi
0x180115d01  push    rdi
0x180115d02  push    r12
0x180115d04  push    r13
0x180115d06  push    r14
0x180115d08  push    r15
0x180115d0a  mov     rbp, rsp
0x180115d0d  sub     rsp, 70h
0x180115d11  mov     r14, rcx
0x180115d14  xor     edx, edx
0x180115d16  mov     ecx, 428h
0x180115d1b  mov     r13, r8
0x180115d1e  call    GpMallocEx
0x180115d23  mov     r15, [rbp+hPal]
0x180115d2a  mov     rbx, rax
0x180115d2d  mov     [r15], rax
0x180115d30  test    rax, rax
0x180115d33  jnz     short loc_180115D3D
0x180115d35  lea     eax, [rbx+3]
0x180115d38  jmp     loc_180115FAF
0x180115d3d  lea     rcx, [rax+10h]; void *
0x180115d41  xor     edx, edx; Val
0x180115d43  mov     r8d, 418h; Size
0x180115d49  call    memset_0
0x180115d4e  mov     eax, [rbp+arg_38]
0x180115d51  mov     esi, 1
0x180115d56  mov     [rbx+4], eax
0x180115d59  mov     rcx, r14; hdc
0x180115d5c  mov     eax, [rbp+arg_40]
0x180115d62  mov     dword ptr [rbx], 28h ; '('
0x180115d68  lea     edx, [rsi+4]; type
0x180115d6b  mov     dword ptr [rbx+0Ch], 80001h
0x180115d72  mov     [rbx+8], eax
0x180115d75  call    cs:__imp_GetCurrentObject
0x180115d7b  xor     ecx, ecx
0x180115d7d  lea     r8, [rbp+pv]; pv
0x180115d81  lea     edx, [rsi+1]; c
0x180115d84  mov     [rbp+hPal], rax
0x180115d8b  mov     [rbp+pv], cx
0x180115d8f  mov     rdi, rax
0x180115d92  mov     rcx, rax; h
0x180115d95  call    cs:__imp_GetObjectA
0x180115d9b  movzx   r8d, [rbp+pv]; cEntries
0x180115da0  lea     r9, [rbx+28h]; pPalEntries
0x180115da4  xor     edx, edx; iStart
0x180115da6  mov     rcx, rdi; hpal
0x180115da9  call    cs:__imp_GetPaletteEntries
0x180115daf  movzx   ecx, [rbp+pv]
0x180115db3  mov     [rbx+20h], ecx
0x180115db6  mov     rcx, r14; hdc
0x180115db9  call    cs:__imp_CreateCompatibleDC
0x180115dbf  mov     r9, [rbp+ppvBits]; ppvBits
0x180115dc6  xor     r8d, r8d; usage
0x180115dc9  mov     rdx, rbx; pbmi
0x180115dcc  mov     [rsp+70h+offset], 0; offset
0x180115dd4  mov     rcx, r14; hdc
0x180115dd7  mov     [rsp+70h+hSection], 0; hSection
0x180115de0  mov     rdi, rax
0x180115de3  call    cs:__imp_CreateDIBSection
0x180115de9  mov     r12, [rbp+arg_58]
0x180115df0  mov     [r12], rax
0x180115df4  test    rax, rax
0x180115df7  jz      loc_180115F67
0x180115dfd  test    rdi, rdi
0x180115e00  jz      loc_180115F79
0x180115e06  mov     rdx, rax; h
0x180115e09  mov     rcx, rdi; hdc
0x180115e0c  call    cs:__imp_SelectObject
0x180115e12  mov     rdx, [rbp+hPal]; hPal
0x180115e19  xor     r8d, r8d; bForceBkgd
0x180115e1c  mov     rcx, rdi; hdc
0x180115e1f  call    cs:__imp_SelectPalette
0x180115e25  mov     rcx, rdi; hdc
0x180115e28  call    cs:__imp_RealizePalette
0x180115e2e  xor     edx, edx; void *
0x180115e30  mov     rcx, rdi; hdc
0x180115e33  call    ?GetFromHdc@GpGraphics@@SAPEAV1@PEAUHDC__@@PEAX@Z; GpGraphics::GetFromHdc(HDC__ *,void *)
0x180115e38  mov     r14, rax
0x180115e3b  test    rax, rax
0x180115e3e  jz      loc_180115F6C
0x180115e44  cmp     dword ptr [rax+8], 61724731h
0x180115e4b  jnz     loc_180115F6C
0x180115e51  xor     edx, edx
0x180115e53  mov     ecx, 5E0h
0x180115e58  call    GpMallocEx
0x180115e5d  test    rax, rax
0x180115e60  jz      loc_180115F5D
0x180115e66  mov     rdx, [rbp+arg_8]; struct tagBITMAPINFO *
0x180115e6a  mov     r8, r13; void *
0x180115e6d  mov     rcx, rax; this
0x180115e70  call    ??0GpBitmap@@QEAA@PEAUtagBITMAPINFO@@PEAXH@Z; GpBitmap::GpBitmap(tagBITMAPINFO *,void *,int)
0x180115e75  mov     rbx, rax
0x180115e78  test    rax, rax
0x180115e7b  jz      loc_180115F5D
0x180115e81  mov     rcx, [rax]
0x180115e84  mov     rax, [rcx+8]
0x180115e88  mov     rcx, rbx
0x180115e8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180115e90  test    eax, eax
0x180115e92  jz      loc_180115F4E
0x180115e98  lea     rdx, [r14+10h]; struct GpRuntime::GpLockable *
0x180115e9c  lea     rcx, [rbp+var_18]; this
0x180115ea0  call    ??0GpLock@GpRuntime@@QEAA@PEAVGpLockable@1@@Z; GpRuntime::GpLock::GpLock(GpRuntime::GpLockable *)
0x180115ea5  mov     edx, esi
0x180115ea7  mov     rcx, r14
0x180115eaa  call    ?SetCompositingMode@GpGraphics@@QEAAXW4CompositingMode@@@Z; GpGraphics::SetCompositingMode(CompositingMode)
0x180115eaf  mov     edx, [rbp+arg_60]
0x180115eb5  mov     rcx, r14
0x180115eb8  call    ?SetInterpolationMode@GpGraphics@@QEAAXW4InterpolationMode@@@Z; GpGraphics::SetInterpolationMode(InterpolationMode)
0x180115ebd  lea     edx, [rsi+3]
0x180115ec0  mov     rcx, r14
0x180115ec3  call    ?SetPixelOffsetMode@GpGraphics@@QEAAXW4PixelOffsetMode@@@Z; GpGraphics::SetPixelOffsetMode(PixelOffsetMode)
0x180115ec8  movd    xmm0, [rbp+arg_18]
0x180115ecd  lea     r9, [rbp+var_3C]
0x180115ed1  movd    xmm1, [rbp+arg_20]
0x180115ed6  lea     r8, [rbp+var_2C]
0x180115eda  cvtdq2ps xmm0, xmm0
0x180115edd  mov     qword ptr [rsp+70h+offset], 0
0x180115ee6  mov     rdx, rbx
0x180115ee9  mov     rcx, r14
0x180115eec  mov     [rbp+var_2C], 0
0x180115ef4  mov     dword ptr [rsp+70h+hSection], 2
0x180115efc  cvtdq2ps xmm1, xmm1
0x180115eff  movss   [rbp+var_3C], xmm0
0x180115f04  movd    xmm0, [rbp+arg_28]
0x180115f09  movss   [rbp+var_38], xmm1
0x180115f0e  movd    xmm1, [rbp+arg_30]
0x180115f13  cvtdq2ps xmm0, xmm0
0x180115f16  cvtdq2ps xmm1, xmm1
0x180115f19  movss   [rbp+var_34], xmm0
0x180115f1e  movd    xmm0, [rbp+arg_40]
0x180115f26  movss   [rbp+var_30], xmm1
0x180115f2b  movd    xmm1, [rbp+arg_38]
0x180115f30  cvtdq2ps xmm1, xmm1
0x180115f33  cvtdq2ps xmm0, xmm0
0x180115f36  movss   [rbp+var_24], xmm1
0x180115f3b  movss   [rbp+var_20], xmm0
0x180115f40  call    ?DrawImage@GpGraphics@@QEAA?AW4Status@@PEAVGpImage@@AEBVRectF@@1W4Unit@@PEBVGpImageAttributes@@@Z; GpGraphics::DrawImage(GpImage *,RectF const &,RectF const &,Unit,GpImageAttributes const *)
0x180115f45  mov     rcx, [rbp+var_10]
0x180115f49  mov     esi, eax
0x180115f4b  lock dec dword ptr [rcx]
0x180115f4e  mov     rcx, [rbx]
0x180115f51  mov     rax, [rcx+38h]
0x180115f55  mov     rcx, rbx
0x180115f58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180115f5d  mov     rcx, r14; this
0x180115f60  call    ??_GGpGraphics@@QEAAPEAXI@Z; GpGraphics::`scalar deleting destructor'(uint)
0x180115f65  jmp     short loc_180115F6C
0x180115f67  test    rdi, rdi
0x180115f6a  jz      short loc_180115F79
0x180115f6c  mov     rcx, rdi; hdc
0x180115f6f  call    cs:__imp_DeleteDC
0x180115f75  test    esi, esi
0x180115f77  jz      short loc_180115FAD
0x180115f79  mov     rcx, [r15]
0x180115f7c  call    GpFree
0x180115f81  mov     qword ptr [r15], 0
0x180115f88  mov     rcx, [r12]; ho
0x180115f8c  test    rcx, rcx
0x180115f8f  jz      short loc_180115F9F
0x180115f91  call    cs:__imp_DeleteObject
0x180115f97  mov     qword ptr [r12], 0
0x180115f9f  mov     rax, [rbp+ppvBits]
0x180115fa6  mov     qword ptr [rax], 0
0x180115fad  mov     eax, esi
0x180115faf  mov     rbx, [rsp+70h+arg_0]
0x180115fb7  add     rsp, 70h
0x180115fbb  pop     r15
0x180115fbd  pop     r14
0x180115fbf  pop     r13
0x180115fc1  pop     r12
0x180115fc3  pop     rdi
0x180115fc4  pop     rsi
0x180115fc5  pop     rbp
0x180115fc6  retn
```
