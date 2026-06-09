# GpBitmap::DrawAndHalftoneForStretchBlt(HDC__ *,tagBITMAPINFO *,uchar *,int,int,int,int,int,int,tagBITMAPINFO * *,uchar * *,HBITMAP__ * *,InterpolationMode)

- ea: `0x18011dbe0`
- end: `0x18011def4`
- name: `?DrawAndHalftoneForStretchBlt@GpBitmap@@SA?AW4Status@@PEAUHDC__@@PEAUtagBITMAPINFO@@PEAEHHHHHHPEAPEAU4@PEAPEAEPEAPEAUHBITMAP__@@W4InterpolationMode@@@Z`
- size: `788`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18006b37c`
- `0x180144d94`

## callees

- `0x180010bd0`
- `0x180019610`
- `0x18002c2c8`
- `0x1800458f4`
- `0x1800599b0`
- `0x180063cd8`
- `0x1800659ec`
- `0x180086a60`
- `0x180086ab0`
- `0x180086cc0`
- `0x18010673c`
- `0x18011dbe0`
- `0x180172010`

## import_xrefs

- `GDI32!RealizePalette` at `0x18011dd42`
- `GDI32!RealizePalette` at `0x18011dd42`
- `GDI32!GetPaletteEntries` at `0x18011dca5`
- `GDI32!GetPaletteEntries` at `0x18011dca5`
- `GDI32!CreateDIBSection` at `0x18011dceb`
- `GDI32!CreateDIBSection` at `0x18011dceb`
- `GDI32!DeleteDC` at `0x18011de8f`
- `GDI32!DeleteDC` at `0x18011de8f`
- `GDI32!SelectObject` at `0x18011dd1a`
- `GDI32!SelectObject` at `0x18011dd1a`
- `GDI32!CreateCompatibleDC` at `0x18011dcbb`
- `GDI32!CreateCompatibleDC` at `0x18011dcbb`
- `GDI32!SelectPalette` at `0x18011dd33`
- `GDI32!SelectPalette` at `0x18011dd33`
- `GDI32!GetObjectA` at `0x18011dc8b`
- `GDI32!GetObjectA` at `0x18011dc8b`
- `GDI32!GetCurrentObject` at `0x18011dc65`
- `GDI32!GetCurrentObject` at `0x18011dc65`
- `GDI32!DeleteObject` at `0x18011deb7`
- `GDI32!DeleteObject` at `0x18011deb7`

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
  __int64 pv; // [rsp+30h] [rbp-40h] BYREF
  float v30; // [rsp+38h] [rbp-38h]
  float v31; // [rsp+3Ch] [rbp-34h]
  float v32; // [rsp+40h] [rbp-30h]
  __int64 v33; // [rsp+44h] [rbp-2Ch] BYREF
  float v34; // [rsp+4Ch] [rbp-24h]
  float v35; // [rsp+50h] [rbp-20h]
  _BYTE v36[8]; // [rsp+58h] [rbp-18h] BYREF
  volatile signed __int32 *v37; // [rsp+60h] [rbp-10h]
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
  LOWORD(pv) = 0;
  GetObjectA(hPala, 2, &pv);
  GetPaletteEntries(hPala, 0, (unsigned __int16)pv, (LPPALETTEENTRY)(v17 + 40));
  *(_DWORD *)(v17 + 32) = (unsigned __int16)pv;
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
          GpRuntime::GpLock::GpLock((GpRuntime::GpLock *)v36, (struct GpGraphics *)((char *)v23 + 16));
          GpGraphics::SetCompositingMode(v23, 1);
          GpGraphics::SetInterpolationMode(v23, a13);
          GpGraphics::SetPixelOffsetMode(v23, 4);
          v33 = 0;
          *((float *)&pv + 1) = (float)a4;
          v30 = (float)a5;
          v31 = (float)a6;
          v32 = (float)a7;
          v34 = (float)a8;
          v35 = (float)a9;
          v19 = ((__int64 (__fastcall *)(struct GpGraphics *, GpBitmap *, __int64 *, char *, int, _QWORD, __int64))GpGraphics::DrawImage)(
                  v23,
                  v28,
                  &v33,
                  (char *)&pv + 4,
                  2,
                  0,
                  pv);
          _InterlockedDecrement(v37);
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
0x18011dbe0  mov     [rsp-38h+arg_0], rbx
0x18011dbe5  mov     [rsp-38h+arg_18], r9d
0x18011dbea  mov     [rsp-38h+arg_8], rdx
0x18011dbef  push    rbp
0x18011dbf0  push    rsi
0x18011dbf1  push    rdi
0x18011dbf2  push    r12
0x18011dbf4  push    r13
0x18011dbf6  push    r14
0x18011dbf8  push    r15
0x18011dbfa  mov     rbp, rsp
0x18011dbfd  sub     rsp, 70h
0x18011dc01  mov     r14, rcx
0x18011dc04  xor     edx, edx
0x18011dc06  mov     ecx, 428h
0x18011dc0b  mov     r13, r8
0x18011dc0e  call    GpMallocEx
0x18011dc13  mov     r15, [rbp+hPal]
0x18011dc1a  mov     rbx, rax
0x18011dc1d  mov     [r15], rax
0x18011dc20  test    rax, rax
0x18011dc23  jnz     short loc_18011DC2D
0x18011dc25  lea     eax, [rbx+3]
0x18011dc28  jmp     loc_18011DEDB
0x18011dc2d  lea     rcx, [rax+10h]; void *
0x18011dc31  xor     edx, edx; Val
0x18011dc33  mov     r8d, 418h; Size
0x18011dc39  call    memset_0
0x18011dc3e  mov     eax, [rbp+arg_38]
0x18011dc41  mov     esi, 1
0x18011dc46  mov     [rbx+4], eax
0x18011dc49  mov     rcx, r14; hdc
0x18011dc4c  mov     eax, [rbp+arg_40]
0x18011dc52  mov     dword ptr [rbx], 28h ; '('
0x18011dc58  lea     edx, [rsi+4]; type
0x18011dc5b  mov     dword ptr [rbx+0Ch], 80001h
0x18011dc62  mov     [rbx+8], eax
0x18011dc65  call    cs:__imp_GetCurrentObject
0x18011dc6c  nop     dword ptr [rax+rax+00h]
0x18011dc71  xor     ecx, ecx
0x18011dc73  lea     r8, [rbp+pv]; pv
0x18011dc77  lea     edx, [rsi+1]; c
0x18011dc7a  mov     [rbp+hPal], rax
0x18011dc81  mov     [rbp+pv], cx
0x18011dc85  mov     rdi, rax
0x18011dc88  mov     rcx, rax; h
0x18011dc8b  call    cs:__imp_GetObjectA
0x18011dc92  nop     dword ptr [rax+rax+00h]
0x18011dc97  movzx   r8d, [rbp+pv]; cEntries
0x18011dc9c  lea     r9, [rbx+28h]; pPalEntries
0x18011dca0  xor     edx, edx; iStart
0x18011dca2  mov     rcx, rdi; hpal
0x18011dca5  call    cs:__imp_GetPaletteEntries
0x18011dcac  nop     dword ptr [rax+rax+00h]
0x18011dcb1  movzx   ecx, [rbp+pv]
0x18011dcb5  mov     [rbx+20h], ecx
0x18011dcb8  mov     rcx, r14; hdc
0x18011dcbb  call    cs:__imp_CreateCompatibleDC
0x18011dcc2  nop     dword ptr [rax+rax+00h]
0x18011dcc7  mov     r9, [rbp+ppvBits]; ppvBits
0x18011dcce  xor     r8d, r8d; usage
0x18011dcd1  mov     rdx, rbx; pbmi
0x18011dcd4  mov     [rsp+70h+offset], 0; offset
0x18011dcdc  mov     rcx, r14; hdc
0x18011dcdf  mov     [rsp+70h+hSection], 0; hSection
0x18011dce8  mov     rdi, rax
0x18011dceb  call    cs:__imp_CreateDIBSection
0x18011dcf2  nop     dword ptr [rax+rax+00h]
0x18011dcf7  mov     r12, [rbp+arg_58]
0x18011dcfe  mov     [r12], rax
0x18011dd02  test    rax, rax
0x18011dd05  jz      loc_18011DE87
0x18011dd0b  test    rdi, rdi
0x18011dd0e  jz      loc_18011DE9F
0x18011dd14  mov     rdx, rax; h
0x18011dd17  mov     rcx, rdi; hdc
0x18011dd1a  call    cs:__imp_SelectObject
0x18011dd21  nop     dword ptr [rax+rax+00h]
0x18011dd26  mov     rdx, [rbp+hPal]; hPal
0x18011dd2d  xor     r8d, r8d; bForceBkgd
0x18011dd30  mov     rcx, rdi; hdc
0x18011dd33  call    cs:__imp_SelectPalette
0x18011dd3a  nop     dword ptr [rax+rax+00h]
0x18011dd3f  mov     rcx, rdi; hdc
0x18011dd42  call    cs:__imp_RealizePalette
0x18011dd49  nop     dword ptr [rax+rax+00h]
0x18011dd4e  xor     edx, edx; void *
0x18011dd50  mov     rcx, rdi; HDC
0x18011dd53  call    ?GetFromHdc@GpGraphics@@SAPEAV1@PEAUHDC__@@PEAX@Z; GpGraphics::GetFromHdc(HDC__ *,void *)
0x18011dd58  mov     r14, rax
0x18011dd5b  test    rax, rax
0x18011dd5e  jz      loc_18011DE8C
0x18011dd64  cmp     dword ptr [rax+8], 61724731h
0x18011dd6b  jnz     loc_18011DE8C
0x18011dd71  xor     edx, edx
0x18011dd73  mov     ecx, 5E0h
0x18011dd78  call    GpMallocEx
0x18011dd7d  test    rax, rax
0x18011dd80  jz      loc_18011DE7D
0x18011dd86  mov     rdx, [rbp+arg_8]; struct tagBITMAPINFO *
0x18011dd8a  mov     r8, r13; void *
0x18011dd8d  mov     rcx, rax; this
0x18011dd90  call    ??0GpBitmap@@QEAA@PEAUtagBITMAPINFO@@PEAXH@Z; GpBitmap::GpBitmap(tagBITMAPINFO *,void *,int)
0x18011dd95  mov     rbx, rax
0x18011dd98  test    rax, rax
0x18011dd9b  jz      loc_18011DE7D
0x18011dda1  mov     rcx, [rax]
0x18011dda4  mov     rax, [rcx+8]
0x18011dda8  mov     rcx, rbx
0x18011ddab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011ddb0  test    eax, eax
0x18011ddb2  jz      loc_18011DE6E
0x18011ddb8  lea     rdx, [r14+10h]; struct GpRuntime::GpLockable *
0x18011ddbc  lea     rcx, [rbp+var_18]; this
0x18011ddc0  call    ??0GpLock@GpRuntime@@QEAA@PEAVGpLockable@1@@Z; GpRuntime::GpLock::GpLock(GpRuntime::GpLockable *)
0x18011ddc5  mov     edx, esi
0x18011ddc7  mov     rcx, r14
0x18011ddca  call    ?SetCompositingMode@GpGraphics@@QEAAXW4CompositingMode@@@Z; GpGraphics::SetCompositingMode(CompositingMode)
0x18011ddcf  mov     edx, [rbp+arg_60]
0x18011ddd5  mov     rcx, r14
0x18011ddd8  call    ?SetInterpolationMode@GpGraphics@@QEAAXW4InterpolationMode@@@Z; GpGraphics::SetInterpolationMode(InterpolationMode)
0x18011dddd  lea     edx, [rsi+3]
0x18011dde0  mov     rcx, r14
0x18011dde3  call    ?SetPixelOffsetMode@GpGraphics@@QEAAXW4PixelOffsetMode@@@Z; GpGraphics::SetPixelOffsetMode(PixelOffsetMode)
0x18011dde8  movd    xmm0, [rbp+arg_18]
0x18011dded  lea     r9, [rbp+var_3C]
0x18011ddf1  movd    xmm1, [rbp+arg_20]
0x18011ddf6  lea     r8, [rbp+var_2C]
0x18011ddfa  cvtdq2ps xmm0, xmm0
0x18011ddfd  mov     qword ptr [rsp+70h+offset], 0
0x18011de06  mov     rdx, rbx
0x18011de09  mov     rcx, r14
0x18011de0c  mov     [rbp+var_2C], 0
0x18011de14  mov     dword ptr [rsp+70h+hSection], 2
0x18011de1c  cvtdq2ps xmm1, xmm1
0x18011de1f  movss   [rbp+var_3C], xmm0
0x18011de24  movd    xmm0, [rbp+arg_28]
0x18011de29  movss   [rbp+var_38], xmm1
0x18011de2e  movd    xmm1, [rbp+arg_30]
0x18011de33  cvtdq2ps xmm0, xmm0
0x18011de36  cvtdq2ps xmm1, xmm1
0x18011de39  movss   [rbp+var_34], xmm0
0x18011de3e  movd    xmm0, [rbp+arg_40]
0x18011de46  movss   [rbp+var_30], xmm1
0x18011de4b  movd    xmm1, [rbp+arg_38]
0x18011de50  cvtdq2ps xmm1, xmm1
0x18011de53  cvtdq2ps xmm0, xmm0
0x18011de56  movss   [rbp+var_24], xmm1
0x18011de5b  movss   [rbp+var_20], xmm0
0x18011de60  call    ?DrawImage@GpGraphics@@QEAA?AW4Status@@PEAVGpImage@@AEBVRectF@@1W4Unit@@PEBVGpImageAttributes@@@Z; GpGraphics::DrawImage(GpImage *,RectF const &,RectF const &,Unit,GpImageAttributes const *)
0x18011de65  mov     rcx, [rbp+var_10]
0x18011de69  mov     esi, eax
0x18011de6b  lock dec dword ptr [rcx]
0x18011de6e  mov     rcx, [rbx]
0x18011de71  mov     rax, [rcx+38h]
0x18011de75  mov     rcx, rbx
0x18011de78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011de7d  mov     rcx, r14; this
0x18011de80  call    ??_GGpGraphics@@QEAAPEAXI@Z; GpGraphics::`scalar deleting destructor'(uint)
0x18011de85  jmp     short loc_18011DE8C
0x18011de87  test    rdi, rdi
0x18011de8a  jz      short loc_18011DE9F
0x18011de8c  mov     rcx, rdi; hdc
0x18011de8f  call    cs:__imp_DeleteDC
0x18011de96  nop     dword ptr [rax+rax+00h]
0x18011de9b  test    esi, esi
0x18011de9d  jz      short loc_18011DED9
0x18011de9f  mov     rcx, [r15]
0x18011dea2  call    GpFree
0x18011dea7  mov     qword ptr [r15], 0
0x18011deae  mov     rcx, [r12]; ho
0x18011deb2  test    rcx, rcx
0x18011deb5  jz      short loc_18011DECB
0x18011deb7  call    cs:__imp_DeleteObject
0x18011debe  nop     dword ptr [rax+rax+00h]
0x18011dec3  mov     qword ptr [r12], 0
0x18011decb  mov     rax, [rbp+ppvBits]
0x18011ded2  mov     qword ptr [rax], 0
0x18011ded9  mov     eax, esi
0x18011dedb  mov     rbx, [rsp+70h+arg_0]
0x18011dee3  add     rsp, 70h
0x18011dee7  pop     r15
0x18011dee9  pop     r14
0x18011deeb  pop     r13
0x18011deed  pop     r12
0x18011deef  pop     rdi
0x18011def0  pop     rsi
0x18011def1  pop     rbp
0x18011def2  retn
```
