# HrHostEffectInPlace(GpBitmap *,IImageTransform *,tagRECT *,int,void * *,int *)

- ea: `0x18014d458`
- end: `0x18014d822`
- name: `?HrHostEffectInPlace@@YAJPEAVGpBitmap@@PEAUIImageTransform@@PEAUtagRECT@@HPEAPEAXPEAH@Z`
- size: `970`
- prototype: `__int64 __fastcall(struct GpBitmap *, struct IImageTransform *, struct tagRECT *, int, void **, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800f0f80`

## callees

- `0x180011960`
- `0x1800126d0`
- `0x18001275c`
- `0x1800e9380`
- `0x18014ce7c`
- `0x18014d458`
- `0x18014d828`
- `0x180175010`

## import_xrefs

- `USER32!IsRectEmpty` at `0x18014d71d`
- `USER32!IsRectEmpty` at `0x18014d71d`
- `USER32!IntersectRect` at `0x18014d6f5`
- `USER32!IntersectRect` at `0x18014d70d`
- `USER32!IntersectRect` at `0x18014d6f5`
- `USER32!IntersectRect` at `0x18014d70d`

## pseudocode

```c
__int64 __fastcall HrHostEffectInPlace(
        struct GpBitmap *a1,
        struct IImageTransform *a2,
        struct tagRECT *a3,
        int a4,
        void **a5,
        int *a6)
{
  __int64 v8; // rax
  int AuxiliaryDataFromEffect; // ebx
  unsigned int v11; // r15d
  int BestPixelFormatForEffect; // eax
  __int64 v13; // rax
  GpBitmap *v14; // rdi
  __int64 (__fastcall *v15)(struct IImageTransform *, __int64, __int128 *); // rax
  int v16; // eax
  int v18; // [rsp+30h] [rbp-D0h] BYREF
  int v19; // [rsp+34h] [rbp-CCh] BYREF
  __int128 v20; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v21; // [rsp+48h] [rbp-B8h]
  int v22; // [rsp+58h] [rbp-A8h]
  __int128 v23; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v24; // [rsp+70h] [rbp-90h]
  __int128 v25; // [rsp+80h] [rbp-80h] BYREF
  __int128 v26; // [rsp+90h] [rbp-70h]
  __int128 v27; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v28; // [rsp+B0h] [rbp-50h]
  int *v29; // [rsp+C0h] [rbp-40h]
  struct tagRECT rcDst; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v31; // [rsp+D8h] [rbp-28h] BYREF
  int v32; // [rsp+E8h] [rbp-18h]
  RECT rcSrc2; // [rsp+F0h] [rbp-10h] BYREF

  v29 = a6;
  v22 = a4;
  v32 = 0;
  v8 = *(_QWORD *)a2;
  v31 = 0;
  AuxiliaryDataFromEffect = (*(__int64 (__fastcall **)(struct IImageTransform *, __int128 *))(v8 + 24))(a2, &v31);
  if ( (int)v31 > 1 || SDWORD1(v31) < 1 )
    AuxiliaryDataFromEffect = -2147024809;
  if ( !a1 || !(*(unsigned int (__fastcall **)(struct GpBitmap *))(*(_QWORD *)a1 + 8LL))(a1) )
    return (unsigned int)-2147024809;
  v11 = 0;
  v18 = 0;
  if ( AuxiliaryDataFromEffect < 0 )
    return (unsigned int)AuxiliaryDataFromEffect;
  v19 = 0;
  if ( (unsigned int)GpBitmap::GetPixelFormatID(a1, &v19) )
  {
    AuxiliaryDataFromEffect = -2147467259;
  }
  else
  {
    BestPixelFormatForEffect = FindBestPixelFormatForEffect(a2, v19, -1, &v18);
    v11 = v18;
    AuxiliaryDataFromEffect = BestPixelFormatForEffect;
  }
  if ( AuxiliaryDataFromEffect < 0 )
    return (unsigned int)AuxiliaryDataFromEffect;
  v27 = 0;
  v28 = 0;
  v25 = 0;
  v26 = 0;
  v23 = 0;
  v24 = 0;
  v20 = 0;
  v21 = 0;
  if ( DWORD2(v31) )
  {
    v14 = 0;
  }
  else
  {
    v13 = (*(__int64 (__fastcall **)(struct GpBitmap *))(*(_QWORD *)a1 + 64LL))(a1);
    v14 = (GpBitmap *)v13;
    if ( !v13 || !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13) )
    {
      AuxiliaryDataFromEffect = -2147024882;
      goto LABEL_19;
    }
    if ( (unsigned int)GpBitmap::LockBits(v14, 0, 1u, v11, (__int64)&v27) )
      AuxiliaryDataFromEffect = -2147467259;
    if ( AuxiliaryDataFromEffect < 0 )
    {
LABEL_19:
      if ( v14 )
      {
LABEL_20:
        (*(void (__fastcall **)(GpBitmap *))(*(_QWORD *)v14 + 56LL))(v14);
        return (unsigned int)AuxiliaryDataFromEffect;
      }
      return (unsigned int)AuxiliaryDataFromEffect;
    }
  }
  if ( (unsigned int)GpBitmap::LockBits(a1, 0, 3u, v11, (__int64)&v25) )
  {
    AuxiliaryDataFromEffect = -2147467259;
  }
  else
  {
    v20 = v25;
    *(_QWORD *)&v21 = v26;
    *((_QWORD *)&v21 + 1) = __PAIR64__(LODWORD(Globals::DesktopDpiY), LODWORD(Globals::DesktopDpiX));
    if ( DWORD2(v31) )
    {
      v23 = v20;
      v24 = v21;
    }
    else
    {
      v23 = v27;
      *(_QWORD *)&v24 = v28;
      *((_QWORD *)&v24 + 1) = __PAIR64__(LODWORD(Globals::DesktopDpiY), LODWORD(Globals::DesktopDpiX));
    }
    v15 = *(__int64 (__fastcall **)(struct IImageTransform *, __int64, __int128 *))(*(_QWORD *)a2 + 40LL);
    rcDst = 0;
    AuxiliaryDataFromEffect = v15(a2, 1, &v23);
    if ( AuxiliaryDataFromEffect >= 0 )
    {
      *(_QWORD *)&rcSrc2.right = v20;
      *(_QWORD *)&rcSrc2.left = 0;
      if ( a3 )
        IntersectRect(&rcDst, &rcDst, a3);
      IntersectRect(&rcDst, &rcDst, &rcSrc2);
      if ( IsRectEmpty(&rcDst)
        || (LODWORD(v20) = rcDst.right - rcDst.left,
            DWORD1(v20) = rcDst.bottom - rcDst.top,
            *(_QWORD *)&v21 = rcDst.left * (((SHIDWORD(v20) >> 8) & 0xF8u) >> 3) + v21 + rcDst.top * DWORD2(v20),
            AuxiliaryDataFromEffect = (*(__int64 (__fastcall **)(struct IImageTransform *, struct tagRECT *, __int128 *))(*(_QWORD *)a2 + 48LL))(
                                        a2,
                                        &rcDst,
                                        &v20),
            AuxiliaryDataFromEffect >= 0) )
      {
        if ( v32 && v22 && a5 && v29 )
          AuxiliaryDataFromEffect = HrGetAuxiliaryDataFromEffect(a2, a5, v29);
      }
      v16 = (*(__int64 (__fastcall **)(struct IImageTransform *))(*(_QWORD *)a2 + 56LL))(a2);
      if ( v16 < 0 && AuxiliaryDataFromEffect >= 0 )
        AuxiliaryDataFromEffect = v16;
    }
    GpBitmap::UnlockBits(a1, (__int64)&v25);
  }
  if ( v14 )
  {
    GpBitmap::UnlockBits(v14, (__int64)&v27);
    goto LABEL_20;
  }
  return (unsigned int)AuxiliaryDataFromEffect;
}

```

## disassembly

```asm
0x18014d458  mov     [rsp-8+arg_18], rbx
0x18014d45d  push    rbp
0x18014d45e  push    rsi
0x18014d45f  push    rdi
0x18014d460  push    r12
0x18014d462  push    r13
0x18014d464  push    r14
0x18014d466  push    r15
0x18014d468  lea     rbp, [rsp-10h]
0x18014d46d  sub     rsp, 110h
0x18014d474  mov     rax, cs:__security_cookie
0x18014d47b  xor     rax, rsp
0x18014d47e  mov     [rbp+40h+var_40], rax
0x18014d482  mov     rax, [rbp+40h+arg_28]
0x18014d486  mov     r14, rdx
0x18014d489  mov     r13, [rbp+40h+arg_20]
0x18014d48d  mov     rsi, rcx
0x18014d490  mov     [rbp+40h+var_80], rax
0x18014d494  xorps   xmm0, xmm0
0x18014d497  xor     eax, eax
0x18014d499  mov     [rsp+140h+var_E8], r9d
0x18014d49e  mov     [rbp+40h+var_58], eax
0x18014d4a1  mov     rcx, r14
0x18014d4a4  mov     rax, [rdx]
0x18014d4a7  mov     r12, r8
0x18014d4aa  lea     rdx, [rbp+40h+var_68]
0x18014d4ae  movups  [rbp+40h+var_68], xmm0
0x18014d4b2  mov     rax, [rax+18h]
0x18014d4b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014d4bb  cmp     dword ptr [rbp+40h+var_68], 1
0x18014d4bf  mov     ebx, eax
0x18014d4c1  mov     edi, 80070057h
0x18014d4c6  jg      short loc_18014D4CE
0x18014d4c8  cmp     dword ptr [rbp+40h+var_68+4], 1
0x18014d4cc  jge     short loc_18014D4D0
0x18014d4ce  mov     ebx, edi
0x18014d4d0  test    rsi, rsi
0x18014d4d3  jz      loc_18014D7F6
0x18014d4d9  mov     rax, [rsi]
0x18014d4dc  mov     rcx, rsi
0x18014d4df  mov     rax, [rax+8]
0x18014d4e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014d4e8  test    eax, eax
0x18014d4ea  jz      loc_18014D7F6
0x18014d4f0  xor     r15d, r15d
0x18014d4f3  mov     [rsp+140h+var_110], r15d
0x18014d4f8  test    ebx, ebx
0x18014d4fa  js      loc_18014D7F8
0x18014d500  and     [rsp+140h+var_10C], r15d
0x18014d505  lea     rdx, [rsp+140h+var_10C]
0x18014d50a  mov     rcx, rsi
0x18014d50d  call    ?GetPixelFormatID@GpBitmap@@QEAA?AW4Status@@PEAH@Z; GpBitmap::GetPixelFormatID(int *)
0x18014d512  mov     ecx, 80004005h
0x18014d517  test    eax, eax
0x18014d519  jnz     short loc_18014D539
0x18014d51b  mov     edx, [rsp+140h+var_10C]; int
0x18014d51f  lea     r9, [rsp+140h+var_110]; int *
0x18014d524  or      r8d, 0FFFFFFFFh; int
0x18014d528  mov     rcx, r14; struct IImageTransform *
0x18014d52b  call    ?FindBestPixelFormatForEffect@@YAJPEAUIImageTransform@@HHPEAH@Z; FindBestPixelFormatForEffect(IImageTransform *,int,int,int *)
0x18014d530  mov     r15d, [rsp+140h+var_110]
0x18014d535  mov     ebx, eax
0x18014d537  jmp     short loc_18014D53B
0x18014d539  mov     ebx, ecx
0x18014d53b  test    ebx, ebx
0x18014d53d  js      loc_18014D7F8
0x18014d543  cmp     dword ptr [rbp+40h+var_68+8], 0
0x18014d547  xorps   xmm0, xmm0
0x18014d54a  xorps   xmm1, xmm1
0x18014d54d  movups  [rbp+40h+var_A0], xmm0
0x18014d551  movups  [rbp+40h+var_90], xmm0
0x18014d555  movups  [rbp+40h+var_C0], xmm1
0x18014d559  movups  [rbp+40h+var_B0], xmm1
0x18014d55d  movups  [rsp+140h+var_E0], xmm0
0x18014d562  movups  [rsp+140h+var_D0], xmm0
0x18014d567  movups  [rsp+140h+var_108], xmm1
0x18014d56c  movups  [rsp+140h+var_F8], xmm1
0x18014d571  jnz     short loc_18014D5E9
0x18014d573  mov     rax, [rsi]
0x18014d576  mov     rcx, rsi
0x18014d579  mov     rax, [rax+40h]
0x18014d57d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014d582  mov     rdi, rax
0x18014d585  test    rax, rax
0x18014d588  jz      short loc_18014D5C7
0x18014d58a  mov     rcx, [rax]
0x18014d58d  mov     rax, [rcx+8]
0x18014d591  mov     rcx, rdi
0x18014d594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014d599  test    eax, eax
0x18014d59b  jz      short loc_18014D5C7
0x18014d59d  xor     edx, edx
0x18014d59f  lea     rax, [rbp+40h+var_A0]
0x18014d5a3  mov     r9d, r15d
0x18014d5a6  mov     [rsp+140h+var_120], rax
0x18014d5ab  mov     rcx, rdi
0x18014d5ae  lea     r8d, [rdx+1]
0x18014d5b2  call    ?LockBits@GpBitmap@@QEBA?AW4Status@@PEBVGpRect@GpRuntime@@IHPEAVBitmapData@@@Z; GpBitmap::LockBits(GpRuntime::GpRect const *,uint,int,BitmapData *)
0x18014d5b7  test    eax, eax
0x18014d5b9  mov     eax, 80004005h
0x18014d5be  cmovnz  ebx, eax
0x18014d5c1  test    ebx, ebx
0x18014d5c3  jns     short loc_18014D5EB
0x18014d5c5  jmp     short loc_18014D5CC
0x18014d5c7  mov     ebx, 8007000Eh
0x18014d5cc  test    rdi, rdi
0x18014d5cf  jz      loc_18014D7F8
0x18014d5d5  mov     rax, [rdi]
0x18014d5d8  mov     rcx, rdi
0x18014d5db  mov     rax, [rax+38h]
0x18014d5df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014d5e4  jmp     loc_18014D7F8
0x18014d5e9  xor     edi, edi
0x18014d5eb  xor     edx, edx
0x18014d5ed  lea     rax, [rbp+40h+var_C0]
0x18014d5f1  mov     r9d, r15d
0x18014d5f4  mov     [rsp+140h+var_120], rax
0x18014d5f9  mov     rcx, rsi
0x18014d5fc  lea     r8d, [rdx+3]
0x18014d600  call    ?LockBits@GpBitmap@@QEBA?AW4Status@@PEBVGpRect@GpRuntime@@IHPEAVBitmapData@@@Z; GpBitmap::LockBits(GpRuntime::GpRect const *,uint,int,BitmapData *)
0x18014d605  xor     r15d, r15d
0x18014d608  test    eax, eax
0x18014d60a  jnz     loc_18014D7DB
0x18014d610  mov     eax, dword ptr [rbp+40h+var_C0]
0x18014d613  movss   xmm0, cs:?DesktopDpiX@Globals@@3MA; float Globals::DesktopDpiX
0x18014d61b  movss   xmm1, cs:?DesktopDpiY@Globals@@3MA; float Globals::DesktopDpiY
0x18014d623  mov     dword ptr [rsp+140h+var_108], eax
0x18014d627  mov     eax, dword ptr [rbp+40h+var_C0+4]
0x18014d62a  mov     dword ptr [rsp+140h+var_108+4], eax
0x18014d62e  mov     eax, dword ptr [rbp+40h+var_C0+8]
0x18014d631  mov     dword ptr [rsp+140h+var_108+8], eax
0x18014d635  mov     eax, dword ptr [rbp+40h+var_C0+0Ch]
0x18014d638  mov     dword ptr [rsp+140h+var_108+0Ch], eax
0x18014d63c  mov     rax, qword ptr [rbp+40h+var_B0]
0x18014d640  mov     qword ptr [rsp+140h+var_F8], rax
0x18014d645  movss   dword ptr [rsp+140h+var_F8+8], xmm0
0x18014d64b  movss   dword ptr [rsp+140h+var_F8+0Ch], xmm1
0x18014d651  cmp     dword ptr [rbp+40h+var_68+8], r15d
0x18014d655  jz      short loc_18014D66D
0x18014d657  movups  xmm0, [rsp+140h+var_108]
0x18014d65c  movups  xmm1, [rsp+140h+var_F8]
0x18014d661  movups  [rsp+140h+var_E0], xmm0
0x18014d666  movups  [rsp+140h+var_D0], xmm1
0x18014d66b  jmp     short loc_18014D69E
0x18014d66d  mov     eax, dword ptr [rbp+40h+var_A0]
0x18014d670  mov     dword ptr [rsp+140h+var_E0], eax
0x18014d674  mov     eax, dword ptr [rbp+40h+var_A0+4]
0x18014d677  mov     dword ptr [rsp+140h+var_E0+4], eax
0x18014d67b  mov     eax, dword ptr [rbp+40h+var_A0+8]
0x18014d67e  mov     dword ptr [rsp+140h+var_E0+8], eax
0x18014d682  mov     eax, dword ptr [rbp+40h+var_A0+0Ch]
0x18014d685  mov     dword ptr [rsp+140h+var_E0+0Ch], eax
0x18014d689  mov     rax, qword ptr [rbp+40h+var_90]
0x18014d68d  mov     qword ptr [rsp+140h+var_D0], rax
0x18014d692  movss   dword ptr [rsp+140h+var_D0+8], xmm0
0x18014d698  movss   dword ptr [rsp+140h+var_D0+0Ch], xmm1
0x18014d69e  mov     rax, [r14]
0x18014d6a1  lea     rcx, [rbp+40h+rcDst]
0x18014d6a5  xor     r9d, r9d
0x18014d6a8  mov     [rsp+140h+var_120], rcx
0x18014d6ad  xorps   xmm0, xmm0
0x18014d6b0  lea     r8, [rsp+140h+var_E0]
0x18014d6b5  mov     rcx, r14
0x18014d6b8  mov     rax, [rax+28h]
0x18014d6bc  lea     edx, [r9+1]
0x18014d6c0  movups  xmmword ptr [rbp+40h+rcDst.left], xmm0
0x18014d6c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014d6c9  mov     ebx, eax
0x18014d6cb  test    eax, eax
0x18014d6cd  js      loc_18014D7CD
0x18014d6d3  mov     eax, dword ptr [rsp+140h+var_108]
0x18014d6d7  mov     [rbp+40h+rcSrc2.right], eax
0x18014d6da  mov     eax, dword ptr [rsp+140h+var_108+4]
0x18014d6de  mov     [rbp+40h+rcSrc2.bottom], eax
0x18014d6e1  mov     qword ptr [rbp+40h+rcSrc2.left], r15
0x18014d6e5  test    r12, r12
0x18014d6e8  jz      short loc_18014D701
0x18014d6ea  mov     r8, r12; lprcSrc2
0x18014d6ed  lea     rdx, [rbp+40h+rcDst]; lprcSrc1
0x18014d6f1  lea     rcx, [rbp+40h+rcDst]; lprcDst
0x18014d6f5  call    cs:__imp_IntersectRect
0x18014d6fc  nop     dword ptr [rax+rax+00h]
0x18014d701  lea     r8, [rbp+40h+rcSrc2]; lprcSrc2
0x18014d705  lea     rdx, [rbp+40h+rcDst]; lprcSrc1
0x18014d709  lea     rcx, [rbp+40h+rcDst]; lprcDst
0x18014d70d  call    cs:__imp_IntersectRect
0x18014d714  nop     dword ptr [rax+rax+00h]
0x18014d719  lea     rcx, [rbp+40h+rcDst]; lprc
0x18014d71d  call    cs:__imp_IsRectEmpty
0x18014d724  nop     dword ptr [rax+rax+00h]
0x18014d729  test    eax, eax
0x18014d72b  jnz     short loc_18014D78A
0x18014d72d  mov     edx, dword ptr [rsp+140h+var_108+0Ch]
0x18014d731  lea     r8, [rsp+140h+var_108]
0x18014d736  mov     eax, [rbp+40h+rcDst.right]
0x18014d739  mov     rcx, r14
0x18014d73c  sub     eax, [rbp+40h+rcDst.left]
0x18014d73f  mov     dword ptr [rsp+140h+var_108], eax
0x18014d743  mov     eax, [rbp+40h+rcDst.bottom]
0x18014d746  sub     eax, [rbp+40h+rcDst.top]
0x18014d749  mov     dword ptr [rsp+140h+var_108+4], eax
0x18014d74d  mov     eax, dword ptr [rsp+140h+var_108+8]
0x18014d751  imul    eax, [rbp+40h+rcDst.top]
0x18014d755  sar     edx, 8
0x18014d758  and     edx, 0F8h
0x18014d75e  shr     edx, 3
0x18014d761  imul    edx, [rbp+40h+rcDst.left]
0x18014d765  cdqe
0x18014d767  add     rax, qword ptr [rsp+140h+var_F8]
0x18014d76c  add     rax, rdx
0x18014d76f  lea     rdx, [rbp+40h+rcDst]
0x18014d773  mov     qword ptr [rsp+140h+var_F8], rax
0x18014d778  mov     rax, [r14]
0x18014d77b  mov     rax, [rax+30h]
0x18014d77f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014d784  mov     ebx, eax
0x18014d786  test    eax, eax
0x18014d788  js      short loc_18014D7B5
0x18014d78a  cmp     [rbp+40h+var_58], r15d
0x18014d78e  jz      short loc_18014D7B5
0x18014d790  cmp     [rsp+140h+var_E8], r15d
0x18014d795  jz      short loc_18014D7B5
0x18014d797  test    r13, r13
0x18014d79a  jz      short loc_18014D7B5
0x18014d79c  mov     rax, [rbp+40h+var_80]
0x18014d7a0  test    rax, rax
0x18014d7a3  jz      short loc_18014D7B5
0x18014d7a5  mov     r8, rax; int *
0x18014d7a8  mov     rdx, r13; void **
0x18014d7ab  mov     rcx, r14; struct IImageTransform *
0x18014d7ae  call    ?HrGetAuxiliaryDataFromEffect@@YAJPEAUIImageTransform@@PEAPEAXPEAH@Z; HrGetAuxiliaryDataFromEffect(IImageTransform *,void * *,int *)
0x18014d7b3  mov     ebx, eax
0x18014d7b5  mov     rax, [r14]
0x18014d7b8  mov     rcx, r14
0x18014d7bb  mov     rax, [rax+38h]
0x18014d7bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014d7c4  test    eax, eax
0x18014d7c6  jns     short loc_18014D7CD
0x18014d7c8  test    ebx, ebx
0x18014d7ca  cmovns  ebx, eax
0x18014d7cd  lea     rdx, [rbp+40h+var_C0]
0x18014d7d1  mov     rcx, rsi
0x18014d7d4  call    ?UnlockBits@GpBitmap@@QEBA?AW4Status@@PEAVBitmapData@@@Z; GpBitmap::UnlockBits(BitmapData *)
0x18014d7d9  jmp     short loc_18014D7E0
0x18014d7db  mov     ebx, 80004005h
0x18014d7e0  test    rdi, rdi
0x18014d7e3  jz      short loc_18014D7F8
0x18014d7e5  lea     rdx, [rbp+40h+var_A0]
0x18014d7e9  mov     rcx, rdi
0x18014d7ec  call    ?UnlockBits@GpBitmap@@QEBA?AW4Status@@PEAVBitmapData@@@Z; GpBitmap::UnlockBits(BitmapData *)
0x18014d7f1  jmp     loc_18014D5D5
0x18014d7f6  mov     ebx, edi
0x18014d7f8  mov     eax, ebx
0x18014d7fa  mov     rcx, [rbp+40h+var_40]
0x18014d7fe  xor     rcx, rsp; StackCookie
0x18014d801  call    __security_check_cookie
0x18014d806  mov     rbx, [rsp+140h+arg_18]
0x18014d80e  add     rsp, 110h
0x18014d815  pop     r15
0x18014d817  pop     r14
0x18014d819  pop     r13
0x18014d81b  pop     r12
0x18014d81d  pop     rdi
0x18014d81e  pop     rsi
0x18014d81f  pop     rbp
0x18014d820  retn
```
