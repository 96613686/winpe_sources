# HrHostEffect(IImageTransform *,GpBitmap * *,int,tagRECT *,tagRECT *,GpBitmap * *,int,void * *,int *)

- ea: `0x18014cf24`
- end: `0x18014d452`
- name: `?HrHostEffect@@YAJPEAUIImageTransform@@PEAPEAVGpBitmap@@HPEAUtagRECT@@21HPEAPEAXPEAH@Z`
- size: `1326`
- prototype: `__int64 __fastcall(struct IImageTransform *, struct GpBitmap **, int, struct tagRECT *, struct tagRECT *, struct GpBitmap **, int, void **, int *)`
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x180070f78`
- `0x1800f1190`

## callees

- `0x180011960`
- `0x1800126d0`
- `0x18001275c`
- `0x18001489c`
- `0x18001f950`
- `0x1800e5044`
- `0x1800e9380`
- `0x18014ce7c`
- `0x18014cf24`
- `0x18014d828`
- `0x180175010`

## import_xrefs

- `USER32!IsRectEmpty` at `0x18014d20f`
- `USER32!IsRectEmpty` at `0x18014d20f`
- `USER32!IntersectRect` at `0x18014d1ff`
- `USER32!IntersectRect` at `0x18014d1ff`

## pseudocode

```c
__int64 __fastcall HrHostEffect(
        struct IImageTransform *a1,
        struct GpBitmap **a2,
        int a3,
        struct tagRECT *a4,
        struct tagRECT *a5,
        struct GpBitmap **a6,
        int a7,
        void **a8,
        int *a9)
{
  __int64 v10; // rax
  __int64 (__fastcall *v11)(struct IImageTransform *, __int128 *); // rax
  int v12; // esi
  int AuxiliaryDataFromEffect; // edi
  unsigned int v14; // ebx
  __int64 v15; // r12
  __int64 i; // r14
  struct GpBitmap *v17; // rcx
  int v18; // edx
  __int64 v19; // r15
  __int64 v20; // r14
  __int64 v21; // rax
  __int64 v22; // rsi
  unsigned int v23; // eax
  int v24; // ecx
  __int64 v25; // r10
  int BestPixelFormatForEffect; // eax
  bool v27; // zf
  __int64 v28; // rdx
  float v29; // xmm0_4
  float v30; // xmm1_4
  struct IImageTransform *v31; // r12
  RECT *v32; // rax
  __int128 *v33; // rdi
  int v34; // edi
  GpBitmap *v35; // rax
  struct GpBitmap *v36; // rcx
  int v37; // eax
  __int64 v38; // r12
  struct GpBitmap **v39; // r14
  __int64 v40; // rsi
  int v42; // [rsp+30h] [rbp-D0h] BYREF
  int v43; // [rsp+34h] [rbp-CCh]
  int v44; // [rsp+38h] [rbp-C8h]
  int v45; // [rsp+3Ch] [rbp-C4h]
  int v46; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v47; // [rsp+48h] [rbp-B8h]
  struct GpBitmap **v48; // [rsp+50h] [rbp-B0h]
  __int64 v49; // [rsp+58h] [rbp-A8h]
  struct IImageTransform *v50; // [rsp+60h] [rbp-A0h]
  __int64 v51; // [rsp+68h] [rbp-98h]
  __int128 v52; // [rsp+70h] [rbp-90h] BYREF
  __int128 v53; // [rsp+80h] [rbp-80h]
  __int128 v54; // [rsp+90h] [rbp-70h] BYREF
  __int128 v55; // [rsp+A0h] [rbp-60h]
  RECT *lprcSrc2; // [rsp+B0h] [rbp-50h]
  void **v57; // [rsp+B8h] [rbp-48h]
  int *v58; // [rsp+C0h] [rbp-40h]
  struct tagRECT *v59; // [rsp+C8h] [rbp-38h]
  struct tagRECT rcDst; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v61; // [rsp+E0h] [rbp-20h] BYREF
  int v62; // [rsp+F0h] [rbp-10h]

  v59 = a5;
  v57 = a8;
  v58 = a9;
  v62 = 0;
  v10 = *(_QWORD *)a1;
  v48 = a2;
  lprcSrc2 = a4;
  v44 = a3;
  v11 = *(__int64 (__fastcall **)(struct IImageTransform *, __int128 *))(v10 + 24);
  v50 = a1;
  v61 = 0;
  v12 = v11(a1, &v61);
  AuxiliaryDataFromEffect = -2147024809;
  if ( (int)v61 > v44 || SDWORD1(v61) < v44 )
    v12 = -2147024809;
  v14 = 0;
  v15 = v44;
  for ( i = 0; i < v44; ++i )
  {
    v17 = a2[i];
    if ( !v17 || !(*(unsigned int (__fastcall **)(struct GpBitmap *))(*(_QWORD *)v17 + 8LL))(v17) )
      return (unsigned int)AuxiliaryDataFromEffect;
  }
  AuxiliaryDataFromEffect = v12;
  if ( v12 >= 0 )
  {
    v18 = v44;
    v19 = 0;
    v51 = 0;
    v20 = 0;
    if ( v44 > 0 )
    {
      if ( (unsigned __int64)v44 > 0x7FFFFFFFFFFFFFFLL || (v19 = GpMallocEx(32LL * v44, 0)) == 0 )
        AuxiliaryDataFromEffect = -2147024882;
      if ( (unsigned __int64)v44 > 0x7FFFFFFFFFFFFFFLL )
      {
        v20 = 0;
LABEL_17:
        AuxiliaryDataFromEffect = -2147024882;
LABEL_67:
        GpFree(v19);
        GpFree(v20);
        return (unsigned int)AuxiliaryDataFromEffect;
      }
      v21 = GpMallocEx(32LL * v44, 0);
      v20 = v21;
      if ( !v21 )
        goto LABEL_17;
      v51 = v21;
      if ( AuxiliaryDataFromEffect < 0 )
        goto LABEL_67;
      v18 = v44;
    }
    v45 = v18;
    v22 = v20 + 4;
    v42 = 0;
    v47 = 0;
    v49 = v19 - v20;
    v23 = 0;
    v24 = 0;
    v25 = 0;
    while ( 1 )
    {
      v43 = v24;
      if ( v25 >= v15 )
        break;
      v46 = 0;
      if ( HIDWORD(v61) || !v24 )
      {
        if ( (unsigned int)GpBitmap::GetPixelFormatID(v48[v25], &v46) )
          goto LABEL_31;
        BestPixelFormatForEffect = FindBestPixelFormatForEffect(v50, v46, v43, &v42);
        v24 = v43;
        AuxiliaryDataFromEffect = BestPixelFormatForEffect;
        v23 = v42;
        v25 = v47;
      }
      v27 = AuxiliaryDataFromEffect == 0;
      if ( AuxiliaryDataFromEffect >= 0 )
      {
        if ( (unsigned int)GpBitmap::LockBits(v48[v25], 0, 1u, v23, v19 + 32LL * v24) )
          goto LABEL_31;
        v28 = v49;
        v27 = AuxiliaryDataFromEffect == 0;
        v29 = Globals::DesktopDpiX;
        v30 = Globals::DesktopDpiY;
        *(_DWORD *)(v22 - 4) = *(_DWORD *)(v22 + v49 - 4);
        *(_DWORD *)v22 = *(_DWORD *)(v22 + v28);
        *(_DWORD *)(v22 + 4) = *(_DWORD *)(v28 + v22 + 4);
        *(_DWORD *)(v22 + 8) = *(_DWORD *)(v28 + v22 + 8);
        *(_QWORD *)(v22 + 12) = *(_QWORD *)(v28 + v22 + 12);
        *(float *)(v22 + 20) = v29;
        *(float *)(v22 + 24) = v30;
      }
      if ( !v27 )
      {
LABEL_31:
        AuxiliaryDataFromEffect = -2147467259;
        v45 = v43;
        break;
      }
      v25 = v47 + 1;
      v23 = v42;
      v24 = v43 + 1;
      ++v47;
      v22 += 32;
    }
    rcDst = 0;
    if ( AuxiliaryDataFromEffect < 0 )
      goto LABEL_63;
    v31 = v50;
    AuxiliaryDataFromEffect = (*(__int64 (__fastcall **)(struct IImageTransform *, _QWORD, __int64, _QWORD, struct tagRECT *))(*(_QWORD *)v50 + 40LL))(
                                v50,
                                (unsigned int)v44,
                                v20,
                                0,
                                &rcDst);
    if ( AuxiliaryDataFromEffect < 0 )
      goto LABEL_63;
    v32 = lprcSrc2;
    *a6 = 0;
    v33 = 0;
    v52 = 0;
    v53 = 0;
    v54 = 0;
    v55 = 0;
    if ( v32 )
      IntersectRect(&rcDst, &rcDst, v32);
    if ( !IsRectEmpty(&rcDst) )
    {
      if ( HIDWORD(v61) || (v34 = v42) == 0 )
      {
        AuxiliaryDataFromEffect = FindBestPixelFormatForEffect(v31, 0, -1, &v42);
        if ( AuxiliaryDataFromEffect < 0 )
        {
LABEL_57:
          v37 = (*(__int64 (__fastcall **)(struct IImageTransform *))(*(_QWORD *)v31 + 56LL))(v31);
          if ( v37 >= 0 )
          {
            if ( AuxiliaryDataFromEffect >= 0 )
            {
              if ( v59 )
                *v59 = rcDst;
              goto LABEL_63;
            }
          }
          else if ( AuxiliaryDataFromEffect >= 0 )
          {
            AuxiliaryDataFromEffect = v37;
          }
          if ( *a6 )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a6 + 56LL))(*a6);
          *a6 = 0;
LABEL_63:
          v38 = v45;
          if ( v45 > 0 )
          {
            v39 = v48;
            v40 = 0;
            do
              GpBitmap::UnlockBits(v39[v40++], v19 + 32LL * v14++);
            while ( v40 < v38 );
            v20 = v51;
          }
          goto LABEL_67;
        }
        v34 = v42;
      }
      v35 = (GpBitmap *)GpMallocEx(1504, 0);
      if ( v35 )
        v36 = GpBitmap::GpBitmap(v35, rcDst.right - rcDst.left, rcDst.bottom - rcDst.top, v34);
      else
        v36 = 0;
      *a6 = v36;
      if ( !v36 || !(*(unsigned int (__fastcall **)(struct GpBitmap *))(*(_QWORD *)v36 + 8LL))(v36) )
      {
        AuxiliaryDataFromEffect = -2147024882;
        if ( *a6 )
        {
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a6 + 56LL))(*a6);
          *a6 = 0;
        }
        goto LABEL_57;
      }
      if ( (unsigned int)GpBitmap::LockBits(*a6, 0, 2u, v34, (__int64)&v54) )
      {
        AuxiliaryDataFromEffect = -2147467259;
        goto LABEL_57;
      }
      v33 = &v52;
      v52 = v54;
      *(_QWORD *)&v53 = v55;
      *((_QWORD *)&v53 + 1) = __PAIR64__(LODWORD(Globals::DesktopDpiY), LODWORD(Globals::DesktopDpiX));
    }
    AuxiliaryDataFromEffect = (*(__int64 (__fastcall **)(struct IImageTransform *, struct tagRECT *, __int128 *))(*(_QWORD *)v31 + 48LL))(
                                v31,
                                &rcDst,
                                v33);
    if ( *a6 )
      GpBitmap::UnlockBits(*a6, (__int64)&v54);
    if ( AuxiliaryDataFromEffect >= 0 && v62 && a7 && v57 && v58 )
      AuxiliaryDataFromEffect = HrGetAuxiliaryDataFromEffect(v31, v57, v58);
    goto LABEL_57;
  }
  return (unsigned int)AuxiliaryDataFromEffect;
}

```

## disassembly

```asm
0x18014cf24  push    rbp
0x18014cf26  push    rbx
0x18014cf27  push    rsi
0x18014cf28  push    rdi
0x18014cf29  push    r12
0x18014cf2b  push    r13
0x18014cf2d  push    r14
0x18014cf2f  push    r15
0x18014cf31  lea     rbp, [rsp-8]
0x18014cf36  sub     rsp, 108h
0x18014cf3d  mov     rax, cs:__security_cookie
0x18014cf44  xor     rax, rsp
0x18014cf47  mov     [rbp+40h+var_48], rax
0x18014cf4b  mov     rax, [rbp+40h+arg_20]
0x18014cf4f  mov     r15, rdx
0x18014cf52  mov     r13, [rbp+40h+arg_28]
0x18014cf56  xorps   xmm0, xmm0
0x18014cf59  mov     [rbp+40h+var_78], rax
0x18014cf5d  mov     rax, [rbp+40h+arg_38]
0x18014cf64  mov     [rbp+40h+var_88], rax
0x18014cf68  mov     rax, [rbp+40h+arg_40]
0x18014cf6f  mov     [rbp+40h+var_80], rax
0x18014cf73  xor     eax, eax
0x18014cf75  mov     [rbp+40h+var_50], eax
0x18014cf78  mov     rax, [rcx]
0x18014cf7b  mov     [rsp+140h+var_F0], rdx
0x18014cf80  lea     rdx, [rbp+40h+var_60]
0x18014cf84  mov     [rbp+40h+lprcSrc2], r9
0x18014cf88  mov     [rsp+140h+var_108], r8d
0x18014cf8d  mov     rax, [rax+18h]
0x18014cf91  mov     [rsp+140h+var_E0], rcx
0x18014cf96  movups  [rbp+40h+var_60], xmm0
0x18014cf9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014cf9f  movsxd  rdx, [rsp+140h+var_108]
0x18014cfa4  mov     esi, eax
0x18014cfa6  mov     edi, 80070057h
0x18014cfab  cmp     dword ptr [rbp+40h+var_60], edx
0x18014cfae  jg      short loc_18014CFB5
0x18014cfb0  cmp     dword ptr [rbp+40h+var_60+4], edx
0x18014cfb3  jge     short loc_18014CFB7
0x18014cfb5  mov     esi, edi
0x18014cfb7  xor     ebx, ebx
0x18014cfb9  mov     r12, rdx
0x18014cfbc  mov     r14d, ebx
0x18014cfbf  cmp     r14, r12
0x18014cfc2  jge     short loc_18014CFEA
0x18014cfc4  mov     rcx, [r15+r14*8]
0x18014cfc8  test    rcx, rcx
0x18014cfcb  jz      loc_18014D3E6
0x18014cfd1  mov     rax, [rcx]
0x18014cfd4  mov     rax, [rax+8]
0x18014cfd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014cfdd  test    eax, eax
0x18014cfdf  jz      loc_18014D3E6
0x18014cfe5  inc     r14
0x18014cfe8  jmp     short loc_18014CFBF
0x18014cfea  mov     edi, esi
0x18014cfec  test    esi, esi
0x18014cfee  js      loc_18014D3E6
0x18014cff4  mov     edx, [rsp+140h+var_108]
0x18014cff8  mov     r15, rbx
0x18014cffb  mov     [rsp+140h+var_D8], rbx
0x18014d000  mov     r14, rbx
0x18014d003  test    edx, edx
0x18014d005  jle     short loc_18014D06C
0x18014d007  mov     r14, 7FFFFFFFFFFFFFFh
0x18014d011  cmp     r12, r14
0x18014d014  ja      short loc_18014D02C
0x18014d016  mov     rcx, r12
0x18014d019  xor     edx, edx
0x18014d01b  shl     rcx, 5
0x18014d01f  call    GpMallocEx
0x18014d024  mov     r15, rax
0x18014d027  test    rax, rax
0x18014d02a  jnz     short loc_18014D031
0x18014d02c  mov     edi, 8007000Eh
0x18014d031  cmp     r12, r14
0x18014d034  jbe     short loc_18014D03B
0x18014d036  mov     r14, rbx
0x18014d039  jmp     short loc_18014D051
0x18014d03b  mov     rcx, r12
0x18014d03e  xor     edx, edx
0x18014d040  shl     rcx, 5
0x18014d044  call    GpMallocEx
0x18014d049  mov     r14, rax
0x18014d04c  test    rax, rax
0x18014d04f  jnz     short loc_18014D05B
0x18014d051  mov     edi, 8007000Eh
0x18014d056  jmp     loc_18014D3D6
0x18014d05b  mov     [rsp+140h+var_D8], rax
0x18014d060  test    edi, edi
0x18014d062  js      loc_18014D3D6
0x18014d068  mov     edx, [rsp+140h+var_108]
0x18014d06c  mov     [rsp+140h+var_104], edx
0x18014d070  lea     rsi, [r14+4]
0x18014d074  mov     rdx, r15
0x18014d077  mov     [rsp+140h+var_110], ebx
0x18014d07b  sub     rdx, r14
0x18014d07e  mov     [rsp+140h+var_F8], rbx
0x18014d083  mov     [rsp+140h+var_E8], rdx
0x18014d088  mov     eax, ebx
0x18014d08a  mov     ecx, ebx
0x18014d08c  mov     r10, rbx
0x18014d08f  mov     [rsp+140h+var_10C], ecx
0x18014d093  cmp     r10, r12
0x18014d096  jge     loc_18014D18C
0x18014d09c  mov     [rsp+140h+var_100], ebx
0x18014d0a0  cmp     dword ptr [rbp+40h+var_60+0Ch], ebx
0x18014d0a3  jnz     short loc_18014D0A9
0x18014d0a5  test    ecx, ecx
0x18014d0a7  jnz     short loc_18014D0EB
0x18014d0a9  mov     rax, [rsp+140h+var_F0]
0x18014d0ae  lea     rdx, [rsp+140h+var_100]
0x18014d0b3  mov     rcx, [rax+r10*8]
0x18014d0b7  call    ?GetPixelFormatID@GpBitmap@@QEAA?AW4Status@@PEAH@Z; GpBitmap::GetPixelFormatID(int *)
0x18014d0bc  test    eax, eax
0x18014d0be  jnz     loc_18014D17F
0x18014d0c4  mov     r8d, [rsp+140h+var_10C]; int
0x18014d0c9  lea     r9, [rsp+140h+var_110]; int *
0x18014d0ce  mov     edx, [rsp+140h+var_100]; int
0x18014d0d2  mov     rcx, [rsp+140h+var_E0]; struct IImageTransform *
0x18014d0d7  call    ?FindBestPixelFormatForEffect@@YAJPEAUIImageTransform@@HHPEAH@Z; FindBestPixelFormatForEffect(IImageTransform *,int,int,int *)
0x18014d0dc  mov     ecx, [rsp+140h+var_10C]
0x18014d0e0  mov     edi, eax
0x18014d0e2  mov     eax, [rsp+140h+var_110]
0x18014d0e6  mov     r10, [rsp+140h+var_F8]
0x18014d0eb  test    edi, edi
0x18014d0ed  js      short loc_18014D15D
0x18014d0ef  movsxd  rcx, ecx
0x18014d0f2  mov     r9d, eax
0x18014d0f5  mov     rax, [rsp+140h+var_F0]
0x18014d0fa  xor     edx, edx
0x18014d0fc  shl     rcx, 5
0x18014d100  add     rcx, r15
0x18014d103  mov     [rsp+140h+var_120], rcx
0x18014d108  mov     rcx, [rax+r10*8]
0x18014d10c  lea     r8d, [rdx+1]
0x18014d110  call    ?LockBits@GpBitmap@@QEBA?AW4Status@@PEBVGpRect@GpRuntime@@IHPEAVBitmapData@@@Z; GpBitmap::LockBits(GpRuntime::GpRect const *,uint,int,BitmapData *)
0x18014d115  test    eax, eax
0x18014d117  jnz     short loc_18014D17F
0x18014d119  mov     rdx, [rsp+140h+var_E8]
0x18014d11e  test    edi, edi
0x18014d120  movss   xmm0, cs:?DesktopDpiX@Globals@@3MA; float Globals::DesktopDpiX
0x18014d128  movss   xmm1, cs:?DesktopDpiY@Globals@@3MA; float Globals::DesktopDpiY
0x18014d130  mov     eax, [rsi+rdx-4]
0x18014d134  mov     [rsi-4], eax
0x18014d137  mov     eax, [rsi+rdx]
0x18014d13a  mov     [rsi], eax
0x18014d13c  mov     eax, [rdx+rsi+4]
0x18014d140  mov     [rsi+4], eax
0x18014d143  mov     eax, [rdx+rsi+8]
0x18014d147  mov     [rsi+8], eax
0x18014d14a  mov     rax, [rdx+rsi+0Ch]
0x18014d14f  mov     [rsi+0Ch], rax
0x18014d153  movss   dword ptr [rsi+14h], xmm0
0x18014d158  movss   dword ptr [rsi+18h], xmm1
0x18014d15d  jnz     short loc_18014D17F
0x18014d15f  mov     r10, [rsp+140h+var_F8]
0x18014d164  mov     ecx, [rsp+140h+var_10C]
0x18014d168  inc     r10
0x18014d16b  mov     eax, [rsp+140h+var_110]
0x18014d16f  inc     ecx
0x18014d171  mov     [rsp+140h+var_F8], r10
0x18014d176  add     rsi, 20h ; ' '
0x18014d17a  jmp     loc_18014D08F
0x18014d17f  mov     eax, [rsp+140h+var_10C]
0x18014d183  mov     edi, 80004005h
0x18014d188  mov     [rsp+140h+var_104], eax
0x18014d18c  xorps   xmm0, xmm0
0x18014d18f  movups  xmmword ptr [rbp+40h+rcDst.left], xmm0
0x18014d193  test    edi, edi
0x18014d195  js      loc_18014D3A3
0x18014d19b  mov     r12, [rsp+140h+var_E0]
0x18014d1a0  lea     rcx, [rbp+40h+rcDst]
0x18014d1a4  mov     edx, [rsp+140h+var_108]
0x18014d1a8  xor     r9d, r9d
0x18014d1ab  mov     [rsp+140h+var_120], rcx
0x18014d1b0  mov     r8, r14
0x18014d1b3  mov     rcx, r12
0x18014d1b6  mov     rax, [r12]
0x18014d1ba  mov     rax, [rax+28h]
0x18014d1be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014d1c3  mov     edi, eax
0x18014d1c5  test    eax, eax
0x18014d1c7  js      loc_18014D3A3
0x18014d1cd  mov     rax, [rbp+40h+lprcSrc2]
0x18014d1d1  xorps   xmm0, xmm0
0x18014d1d4  mov     [r13+0], rbx
0x18014d1d8  xorps   xmm1, xmm1
0x18014d1db  mov     rdi, rbx
0x18014d1de  movups  [rsp+140h+var_D0], xmm0
0x18014d1e3  movups  [rbp+40h+var_C0], xmm0
0x18014d1e7  movups  [rbp+40h+var_B0], xmm1
0x18014d1eb  movups  [rbp+40h+var_A0], xmm1
0x18014d1ef  test    rax, rax
0x18014d1f2  jz      short loc_18014D20B
0x18014d1f4  mov     r8, rax; lprcSrc2
0x18014d1f7  lea     rdx, [rbp+40h+rcDst]; lprcSrc1
0x18014d1fb  lea     rcx, [rbp+40h+rcDst]; lprcDst
0x18014d1ff  call    cs:__imp_IntersectRect
0x18014d206  nop     dword ptr [rax+rax+00h]
0x18014d20b  lea     rcx, [rbp+40h+rcDst]; lprc
0x18014d20f  call    cs:__imp_IsRectEmpty
0x18014d216  nop     dword ptr [rax+rax+00h]
0x18014d21b  test    eax, eax
0x18014d21d  jnz     loc_18014D310
0x18014d223  cmp     dword ptr [rbp+40h+var_60+0Ch], ebx
0x18014d226  jnz     short loc_18014D230
0x18014d228  mov     edi, [rsp+140h+var_110]
0x18014d22c  test    edi, edi
0x18014d22e  jnz     short loc_18014D251
0x18014d230  lea     r9, [rsp+140h+var_110]; int *
0x18014d235  or      r8d, 0FFFFFFFFh; int
0x18014d239  xor     edx, edx; int
0x18014d23b  mov     rcx, r12; struct IImageTransform *
0x18014d23e  call    ?FindBestPixelFormatForEffect@@YAJPEAUIImageTransform@@HHPEAH@Z; FindBestPixelFormatForEffect(IImageTransform *,int,int,int *)
0x18014d243  mov     edi, eax
0x18014d245  test    eax, eax
0x18014d247  js      loc_18014D36C
0x18014d24d  mov     edi, [rsp+140h+var_110]
0x18014d251  xor     edx, edx
0x18014d253  mov     ecx, 5E0h
0x18014d258  call    GpMallocEx
0x18014d25d  test    rax, rax
0x18014d260  jz      short loc_18014D280
0x18014d262  mov     r8d, [rbp+40h+rcDst.bottom]
0x18014d266  mov     r9d, edi; int
0x18014d269  mov     edx, [rbp+40h+rcDst.right]
0x18014d26c  mov     rcx, rax; this
0x18014d26f  sub     r8d, [rbp+40h+rcDst.top]; int
0x18014d273  sub     edx, [rbp+40h+rcDst.left]; int
0x18014d276  call    ??0GpBitmap@@QEAA@HHH@Z; GpBitmap::GpBitmap(int,int,int)
0x18014d27b  mov     rcx, rax
0x18014d27e  jmp     short loc_18014D283
0x18014d280  mov     rcx, rbx
0x18014d283  mov     [r13+0], rcx
0x18014d287  test    rcx, rcx
0x18014d28a  jz      loc_18014D409
0x18014d290  mov     rax, [rcx]
0x18014d293  mov     rax, [rax+8]
0x18014d297  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014d29c  test    eax, eax
0x18014d29e  jz      loc_18014D409
0x18014d2a4  mov     rcx, [r13+0]
0x18014d2a8  lea     rax, [rbp+40h+var_B0]
0x18014d2ac  xor     edx, edx
0x18014d2ae  mov     [rsp+140h+var_120], rax
0x18014d2b3  mov     r9d, edi
0x18014d2b6  lea     r8d, [rdx+2]
0x18014d2ba  call    ?LockBits@GpBitmap@@QEBA?AW4Status@@PEBVGpRect@GpRuntime@@IHPEAVBitmapData@@@Z; GpBitmap::LockBits(GpRuntime::GpRect const *,uint,int,BitmapData *)
0x18014d2bf  test    eax, eax
0x18014d2c1  jz      short loc_18014D2CD
0x18014d2c3  mov     edi, 80004005h
0x18014d2c8  jmp     loc_18014D36C
0x18014d2cd  mov     eax, dword ptr [rbp+40h+var_B0]
0x18014d2d0  lea     rdi, [rsp+140h+var_D0]
0x18014d2d5  movss   xmm0, cs:?DesktopDpiX@Globals@@3MA; float Globals::DesktopDpiX
0x18014d2dd  movss   xmm1, cs:?DesktopDpiY@Globals@@3MA; float Globals::DesktopDpiY
0x18014d2e5  mov     dword ptr [rsp+140h+var_D0], eax
0x18014d2e9  mov     eax, dword ptr [rbp+40h+var_B0+4]
0x18014d2ec  mov     dword ptr [rsp+140h+var_D0+4], eax
0x18014d2f0  mov     eax, dword ptr [rbp+40h+var_B0+8]
0x18014d2f3  mov     dword ptr [rsp+140h+var_D0+8], eax
0x18014d2f7  mov     eax, dword ptr [rbp+40h+var_B0+0Ch]
0x18014d2fa  mov     dword ptr [rsp+140h+var_D0+0Ch], eax
0x18014d2fe  mov     rax, qword ptr [rbp+40h+var_A0]
0x18014d302  mov     qword ptr [rbp+40h+var_C0], rax
0x18014d306  movss   dword ptr [rbp+40h+var_C0+8], xmm0
0x18014d30b  movss   dword ptr [rbp+40h+var_C0+0Ch], xmm1
0x18014d310  mov     rax, [r12]
0x18014d314  lea     rdx, [rbp+40h+rcDst]
0x18014d318  mov     r8, rdi
0x18014d31b  mov     rcx, r12
0x18014d31e  mov     rax, [rax+30h]
0x18014d322  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014d327  mov     edi, eax
0x18014d329  cmp     [r13+0], rbx
0x18014d32d  jz      short loc_18014D33C
0x18014d32f  mov     rcx, [r13+0]
0x18014d333  lea     rdx, [rbp+40h+var_B0]
0x18014d337  call    ?UnlockBits@GpBitmap@@QEBA?AW4Status@@PEAVBitmapData@@@Z; GpBitmap::UnlockBits(BitmapData *)
0x18014d33c  test    edi, edi
0x18014d33e  js      short loc_18014D36C
0x18014d340  cmp     [rbp+40h+var_50], ebx
0x18014d343  jz      short loc_18014D36C
0x18014d345  cmp     [rbp+40h+arg_30], ebx
0x18014d34b  jz      short loc_18014D36C
0x18014d34d  mov     rax, [rbp+40h+var_88]
0x18014d351  test    rax, rax
0x18014d354  jz      short loc_18014D36C
0x18014d356  mov     r8, [rbp+40h+var_80]; int *
0x18014d35a  test    r8, r8
0x18014d35d  jz      short loc_18014D36C
0x18014d35f  mov     rdx, rax; void **
0x18014d362  mov     rcx, r12; struct IImageTransform *
0x18014d365  call    ?HrGetAuxiliaryDataFromEffect@@YAJPEAUIImageTransform@@PEAPEAXPEAH@Z; HrGetAuxiliaryDataFromEffect(IImageTransform *,void * *,int *)
0x18014d36a  mov     edi, eax
0x18014d36c  mov     rax, [r12]
0x18014d370  mov     rcx, r12
0x18014d373  mov     rax, [rax+38h]
  ... truncated ...
```
