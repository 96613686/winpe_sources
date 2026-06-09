# MetafileRecorder::EndRecording(void)

- ea: `0x1800c62c0`
- end: `0x1800c66da`
- name: `?EndRecording@MetafileRecorder@@UEAAXXZ`
- size: `1050`
- prototype: `void __fastcall(MetafileRecorder *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update`

## callees

- `0x18000be4c`
- `0x180019204`
- `0x1800c62c0`
- `0x1800d4ec0`
- `0x1800e9380`
- `0x1800ea080`
- `0x1800ea0ec`
- `0x180175010`

## import_xrefs

- `GDI32!GetEnhMetaFileHeader` at `0x1800c63fa`
- `GDI32!GetEnhMetaFileHeader` at `0x1800c63fa`
- `GDI32!CloseEnhMetaFile` at `0x1800c63c4`
- `GDI32!CloseEnhMetaFile` at `0x1800c663b`
- `GDI32!CloseEnhMetaFile` at `0x1800c63c4`
- `GDI32!CloseEnhMetaFile` at `0x1800c663b`
- `GDI32!DeleteEnhMetaFile` at `0x1800c65f0`
- `GDI32!DeleteEnhMetaFile` at `0x1800c664a`
- `GDI32!DeleteEnhMetaFile` at `0x1800c65f0`
- `GDI32!DeleteEnhMetaFile` at `0x1800c664a`
- `GDI32!EnumEnhMetaFile` at `0x1800c65dd`
- `GDI32!EnumEnhMetaFile` at `0x1800c65dd`

## pseudocode

```c
void __fastcall MetafileRecorder::EndRecording(MetafileRecorder *this)
{
  int v1; // esi
  __int64 v3; // rcx
  int v4; // r15d
  int v5; // r14d
  int v6; // edi
  int v7; // eax
  HENHMETAFILE v8; // rdi
  __int64 v9; // r14
  bool v10; // r15
  int v11; // edx
  float v12; // xmm2_4
  float v13; // xmm1_4
  __m128 v14; // xmm7
  __m128 v15; // xmm6
  __m128 v16; // xmm8
  __m128 v17; // xmm1
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  __int64 v22; // rax
  void *v23; // r9
  HENHMETAFILE v24; // rcx
  struct tagENHMETAHEADER EnhMetaHeader; // [rsp+38h] [rbp-59h] BYREF

  v1 = 0;
  if ( *((_DWORD *)this + 2) != 1666338097 || *(_DWORD *)(*((_QWORD *)this + 4) + 176LL) != 2 )
  {
    v24 = CloseEnhMetaFile(*((HDC *)this + 9));
    goto LABEL_32;
  }
  v3 = *((_QWORD *)this + 3);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 144LL))(v3);
    if ( *((_DWORD *)this + 15) )
    {
      v4 = RasterizerCeiling(*((float *)this + 11));
      v5 = RasterizerCeiling(*((float *)this + 12));
      v6 = RasterizerCeiling(*((float *)this + 13));
      v7 = RasterizerCeiling(*((float *)this + 14));
      if ( v6 > v4 && v7 > v5 )
        GpGraphics::NoOpPatBlt(*(GpGraphics **)(*((_QWORD *)this + 4) + 208LL), v4, v5, v6 - v4, v7 - v5);
    }
    (*(void (__fastcall **)(MetafileRecorder *))(*(_QWORD *)this + 416LL))(this);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 144LL))(*((_QWORD *)this + 3));
  }
  v8 = CloseEnhMetaFile(*((HDC *)this + 9));
  if ( v8 )
  {
    memset_0(&EnhMetaHeader, 0, 0x58u);
    if ( GetEnhMetaFileHeader(v8, 0x58u, &EnhMetaHeader)
      && (unsigned int)EmfHeaderIsValid((struct ENHMETAHEADER3 *)&EnhMetaHeader) )
    {
      v9 = *((_QWORD *)this + 4);
      v10 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
      v11 = *(_DWORD *)(v9 + 44);
      *(_QWORD *)(v9 + 184) = v8;
      *(_DWORD *)(*((_QWORD *)this + 4) + 224LL) = *((_DWORD *)this + 17);
      v12 = *(float *)(v9 + 48) / 2540.0;
      *(_DWORD *)(v9 + 44) = v11;
      *(_OWORD *)(v9 + 72) = *(_OWORD *)&EnhMetaHeader.iType;
      *(_OWORD *)(v9 + 88) = *(_OWORD *)&EnhMetaHeader.rclBounds.right;
      *(_OWORD *)(v9 + 104) = *(_OWORD *)&EnhMetaHeader.rclFrame.right;
      *(_OWORD *)(v9 + 120) = *(_OWORD *)&EnhMetaHeader.nBytes;
      *(_OWORD *)(v9 + 136) = *(_OWORD *)&EnhMetaHeader.offDescription;
      *(SIZEL *)(v9 + 152) = EnhMetaHeader.szlMillimeters;
      v13 = *(float *)(v9 + 52) / 2540.0;
      *(_DWORD *)(v9 + 36) = EnhMetaHeader.nBytes;
      v14 = (__m128)COERCE_UNSIGNED_INT((float)(EnhMetaHeader.rclFrame.right - EnhMetaHeader.rclFrame.left));
      v15 = (__m128)COERCE_UNSIGNED_INT((float)(EnhMetaHeader.rclFrame.bottom - EnhMetaHeader.rclFrame.top));
      v14.m128_f32[0] = (float)(v14.m128_f32[0] * v12) + 1.0;
      v16 = (__m128)COERCE_UNSIGNED_INT((float)EnhMetaHeader.rclFrame.top);
      v15.m128_f32[0] = (float)(v15.m128_f32[0] * v13) + 1.0;
      v16.m128_f32[0] = v16.m128_f32[0] * v13;
      v17 = (__m128)COERCE_UNSIGNED_INT((float)EnhMetaHeader.rclFrame.left);
      v17.m128_f32[0] = (float)(v17.m128_f32[0] * v12) + 0.5;
      if ( v10 )
        v18 = (int)_mm_round_ss(v17, v17, 9).m128_f32[0];
      else
        v18 = (int)floor(v17.m128_f32[0]);
      *(_DWORD *)(v9 + 56) = v18;
      v16.m128_f32[0] = v16.m128_f32[0] + 0.5;
      if ( v10 )
        v19 = (int)_mm_round_ss(v16, v16, 9).m128_f32[0];
      else
        v19 = (int)floor(v16.m128_f32[0]);
      *(_DWORD *)(v9 + 60) = v19;
      v14.m128_f32[0] = v14.m128_f32[0] + 0.5;
      if ( v10 )
        v20 = (int)_mm_round_ss(v14, v14, 9).m128_f32[0];
      else
        v20 = (int)floor(v14.m128_f32[0]);
      *(_DWORD *)(v9 + 64) = v20;
      v15.m128_f32[0] = v15.m128_f32[0] + 0.5;
      if ( v10 )
        v21 = (int)_mm_round_ss(v15, v15, 9).m128_f32[0];
      else
        v21 = (int)floor(v15.m128_f32[0]);
      *(_DWORD *)(v9 + 68) = v21;
      v22 = *((_QWORD *)this + 4);
      if ( !*(_QWORD *)(v22 + 192) )
      {
        v23 = *(void **)(v22 + 200);
        if ( v23 )
        {
          if ( !EnumEnhMetaFile(0, v8, EnumEmfToStream, v23, 0) )
          {
            DeleteEnhMetaFile(v8);
            *(_QWORD *)(*((_QWORD *)this + 4) + 184LL) = 0;
            goto LABEL_33;
          }
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 4) + 200LL) + 16LL))(*(_QWORD *)(*((_QWORD *)this + 4) + 200LL));
          *(_QWORD *)(*((_QWORD *)this + 4) + 200LL) = 0;
        }
      }
      v1 = 3;
      goto LABEL_33;
    }
    v24 = v8;
LABEL_32:
    DeleteEnhMetaFile(v24);
  }
LABEL_33:
  *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 4) + 208LL) + 56LL) = 0;
  *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 4) + 208LL) + 8LL) = 1279869254;
  *(_QWORD *)(*((_QWORD *)this + 4) + 208LL) = 0;
  *(_DWORD *)(*((_QWORD *)this + 4) + 176LL) = v1;
  (**(void (__fastcall ***)(MetafileRecorder *, __int64))this)(this, 1);
}

```

## disassembly

```asm
0x1800c62c0  mov     rax, rsp
0x1800c62c3  mov     [rax+10h], rbx
0x1800c62c7  mov     [rax+18h], rsi
0x1800c62cb  mov     [rax+20h], rdi
0x1800c62cf  push    rbp
0x1800c62d0  push    r14
0x1800c62d2  push    r15
0x1800c62d4  lea     rbp, [rax-5Fh]
0x1800c62d8  sub     rsp, 0D0h
0x1800c62df  movaps  xmmword ptr [rax-28h], xmm6
0x1800c62e3  movaps  xmmword ptr [rax-38h], xmm7
0x1800c62e7  movaps  xmmword ptr [rax-48h], xmm8
0x1800c62ec  mov     rax, cs:__security_cookie
0x1800c62f3  xor     rax, rsp
0x1800c62f6  mov     qword ptr [rbp+57h+EnhMetaHeader.bOpenGL], rax
0x1800c62fa  xor     esi, esi
0x1800c62fc  mov     rbx, rcx
0x1800c62ff  cmp     dword ptr [rcx+8], 63524D31h
0x1800c6306  jnz     loc_1800C6637
0x1800c630c  mov     rax, [rcx+20h]
0x1800c6310  cmp     dword ptr [rax+0B0h], 2
0x1800c6317  jnz     loc_1800C6637
0x1800c631d  mov     rcx, [rcx+18h]
0x1800c6321  test    rcx, rcx
0x1800c6324  jz      loc_1800C63C0
0x1800c632a  mov     rax, [rcx]
0x1800c632d  mov     rax, [rax+90h]
0x1800c6334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6339  cmp     [rbx+3Ch], esi
0x1800c633c  jz      short loc_1800C639B
0x1800c633e  movss   xmm0, dword ptr [rbx+2Ch]; float
0x1800c6343  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x1800c6348  movss   xmm0, dword ptr [rbx+30h]; float
0x1800c634d  mov     r15d, eax
0x1800c6350  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x1800c6355  movss   xmm0, dword ptr [rbx+34h]; float
0x1800c635a  mov     r14d, eax
0x1800c635d  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x1800c6362  movss   xmm0, dword ptr [rbx+38h]; float
0x1800c6367  mov     edi, eax
0x1800c6369  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x1800c636e  cmp     edi, r15d
0x1800c6371  jle     short loc_1800C639B
0x1800c6373  cmp     eax, r14d
0x1800c6376  jle     short loc_1800C639B
0x1800c6378  mov     rcx, [rbx+20h]
0x1800c637c  sub     edi, r15d
0x1800c637f  sub     eax, r14d
0x1800c6382  mov     r9d, edi; int
0x1800c6385  mov     r8d, r14d; int
0x1800c6388  mov     dword ptr [rsp+0E0h+lpRect], eax; int
0x1800c638c  mov     edx, r15d; int
0x1800c638f  mov     rcx, [rcx+0D0h]; this
0x1800c6396  call    ?NoOpPatBlt@GpGraphics@@IEAAXHHHH@Z; GpGraphics::NoOpPatBlt(int,int,int,int)
0x1800c639b  mov     rax, [rbx]
0x1800c639e  mov     rcx, rbx
0x1800c63a1  mov     rax, [rax+1A0h]
0x1800c63a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c63ad  mov     rcx, [rbx+18h]
0x1800c63b1  mov     rax, [rcx]
0x1800c63b4  mov     rax, [rax+90h]
0x1800c63bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c63c0  mov     rcx, [rbx+48h]; hdc
0x1800c63c4  call    cs:__imp_CloseEnhMetaFile
0x1800c63cb  nop     dword ptr [rax+rax+00h]
0x1800c63d0  mov     rdi, rax
0x1800c63d3  test    rax, rax
0x1800c63d6  jz      loc_1800C6656
0x1800c63dc  mov     r14d, 58h ; 'X'
0x1800c63e2  lea     rcx, [rbp+57h+EnhMetaHeader]; void *
0x1800c63e6  mov     r8d, r14d; Size
0x1800c63e9  xor     edx, edx; Val
0x1800c63eb  call    memset_0
0x1800c63f0  lea     r8, [rbp+57h+EnhMetaHeader]; lpEnhMetaHeader
0x1800c63f4  mov     edx, r14d; nSize
0x1800c63f7  mov     rcx, rdi; hemf
0x1800c63fa  call    cs:__imp_GetEnhMetaFileHeader
0x1800c6401  nop     dword ptr [rax+rax+00h]
0x1800c6406  test    eax, eax
0x1800c6408  jz      loc_1800C6632
0x1800c640e  lea     rcx, [rbp+57h+EnhMetaHeader]; struct ENHMETAHEADER3 *
0x1800c6412  call    ?EmfHeaderIsValid@@YAHAEAUENHMETAHEADER3@@@Z; EmfHeaderIsValid(ENHMETAHEADER3 &)
0x1800c6417  test    eax, eax
0x1800c6419  jz      loc_1800C6632
0x1800c641f  mov     r14, [rbx+20h]
0x1800c6423  mov     r15b, cs:?Feature_GdiPlusOptimizations_Misc_IsEnabled@@3_NA; bool Feature_GdiPlusOptimizations_Misc_IsEnabled
0x1800c642a  mov     edx, [r14+2Ch]
0x1800c642e  mov     [r14+0B8h], rdi
0x1800c6435  mov     eax, [rbx+44h]
0x1800c6438  mov     rcx, [rbx+20h]
0x1800c643c  mov     [rcx+0E0h], eax
0x1800c6442  movss   xmm2, dword ptr [r14+30h]
0x1800c6448  divss   xmm2, cs:__real@451ec000
0x1800c6450  mov     [r14+2Ch], edx
0x1800c6454  movups  xmm0, xmmword ptr [rbp+57h+EnhMetaHeader.iType]
0x1800c6458  movups  xmmword ptr [r14+48h], xmm0
0x1800c645d  movups  xmm1, xmmword ptr [rbp+57h+EnhMetaHeader.rclBounds.right]
0x1800c6461  movups  xmmword ptr [r14+58h], xmm1
0x1800c6466  movups  xmm0, xmmword ptr [rbp+57h+EnhMetaHeader.rclFrame.right]
0x1800c646a  movups  xmmword ptr [r14+68h], xmm0
0x1800c646f  movups  xmm1, xmmword ptr [rbp+57h+EnhMetaHeader.nBytes]
0x1800c6473  movups  xmmword ptr [r14+78h], xmm1
0x1800c6478  movups  xmm0, xmmword ptr [rbp+57h+EnhMetaHeader.offDescription]
0x1800c647c  movups  xmmword ptr [r14+88h], xmm0
0x1800c6484  movsd   xmm1, qword ptr [rbp+57h+EnhMetaHeader.szlMillimeters.cx]
0x1800c6489  movss   xmm0, cs:__real@3f800000
0x1800c6491  movsd   qword ptr [r14+98h], xmm1
0x1800c649a  movss   xmm1, dword ptr [r14+34h]
0x1800c64a0  divss   xmm1, cs:__real@451ec000
0x1800c64a8  mov     eax, [rbp+57h+EnhMetaHeader.nBytes]
0x1800c64ab  mov     [r14+24h], eax
0x1800c64af  mov     eax, [rbp+57h+EnhMetaHeader.rclFrame.right]
0x1800c64b2  sub     eax, [rbp+57h+EnhMetaHeader.rclFrame.left]
0x1800c64b5  movd    xmm8, [rbp+57h+EnhMetaHeader.rclFrame.top]
0x1800c64bb  movd    xmm7, eax
0x1800c64bf  mov     eax, [rbp+57h+EnhMetaHeader.rclFrame.bottom]
0x1800c64c2  sub     eax, [rbp+57h+EnhMetaHeader.rclFrame.top]
0x1800c64c5  cvtdq2ps xmm7, xmm7
0x1800c64c8  movd    xmm6, eax
0x1800c64cc  mulss   xmm7, xmm2
0x1800c64d0  cvtdq2ps xmm6, xmm6
0x1800c64d3  addss   xmm7, xmm0
0x1800c64d7  mulss   xmm6, xmm1
0x1800c64db  cvtdq2ps xmm8, xmm8
0x1800c64df  addss   xmm6, xmm0
0x1800c64e3  mulss   xmm8, xmm1
0x1800c64e8  movd    xmm1, [rbp+57h+EnhMetaHeader.rclFrame.left]
0x1800c64ed  cvtdq2ps xmm1, xmm1
0x1800c64f0  mulss   xmm1, xmm2
0x1800c64f4  addss   xmm1, cs:__real@3f000000
0x1800c64fc  test    r15b, r15b
0x1800c64ff  jz      short loc_1800C6513
0x1800c6501  movaps  xmm0, xmm1
0x1800c6504  movaps  xmm1, xmm0
0x1800c6507  roundss xmm1, xmm1, 9
0x1800c650d  cvttss2si eax, xmm1
0x1800c6511  jmp     short loc_1800C651F
0x1800c6513  cvtps2pd xmm0, xmm1; X
0x1800c6516  call    floor
0x1800c651b  cvttsd2si eax, xmm0
0x1800c651f  mov     [r14+38h], eax
0x1800c6523  addss   xmm8, cs:__real@3f000000
0x1800c652c  test    r15b, r15b
0x1800c652f  jz      short loc_1800C6544
0x1800c6531  movaps  xmm0, xmm8
0x1800c6535  movaps  xmm1, xmm0
0x1800c6538  roundss xmm1, xmm1, 9
0x1800c653e  cvttss2si eax, xmm1
0x1800c6542  jmp     short loc_1800C6551
0x1800c6544  cvtps2pd xmm0, xmm8; X
0x1800c6548  call    floor
0x1800c654d  cvttsd2si eax, xmm0
0x1800c6551  mov     [r14+3Ch], eax
0x1800c6555  addss   xmm7, cs:__real@3f000000
0x1800c655d  test    r15b, r15b
0x1800c6560  jz      short loc_1800C6574
0x1800c6562  movaps  xmm0, xmm7
0x1800c6565  movaps  xmm1, xmm0
0x1800c6568  roundss xmm1, xmm1, 9
0x1800c656e  cvttss2si eax, xmm1
0x1800c6572  jmp     short loc_1800C6580
0x1800c6574  cvtps2pd xmm0, xmm7; X
0x1800c6577  call    floor
0x1800c657c  cvttsd2si eax, xmm0
0x1800c6580  mov     [r14+40h], eax
0x1800c6584  addss   xmm6, cs:__real@3f000000
0x1800c658c  test    r15b, r15b
0x1800c658f  jz      short loc_1800C65A3
0x1800c6591  movaps  xmm0, xmm6
0x1800c6594  movaps  xmm1, xmm0
0x1800c6597  roundss xmm1, xmm1, 9
0x1800c659d  cvttss2si eax, xmm1
0x1800c65a1  jmp     short loc_1800C65AF
0x1800c65a3  cvtps2pd xmm0, xmm6; X
0x1800c65a6  call    floor
0x1800c65ab  cvttsd2si eax, xmm0
0x1800c65af  mov     [r14+44h], eax
0x1800c65b3  mov     rax, [rbx+20h]
0x1800c65b7  cmp     [rax+0C0h], rsi
0x1800c65be  jnz     short loc_1800C662B
0x1800c65c0  mov     r9, [rax+0C8h]; param
0x1800c65c7  test    r9, r9
0x1800c65ca  jz      short loc_1800C662B
0x1800c65cc  and     [rsp+0E0h+lpRect], rsi
0x1800c65d1  lea     r8, EnumEmfToStream; proc
0x1800c65d8  mov     rdx, rdi; hmf
0x1800c65db  xor     ecx, ecx; hdc
0x1800c65dd  call    cs:__imp_EnumEnhMetaFile
0x1800c65e4  nop     dword ptr [rax+rax+00h]
0x1800c65e9  test    eax, eax
0x1800c65eb  jnz     short loc_1800C6609
0x1800c65ed  mov     rcx, rdi; hmf
0x1800c65f0  call    cs:__imp_DeleteEnhMetaFile
0x1800c65f7  nop     dword ptr [rax+rax+00h]
0x1800c65fc  mov     rax, [rbx+20h]
0x1800c6600  and     [rax+0B8h], rsi
0x1800c6607  jmp     short loc_1800C6656
0x1800c6609  mov     rax, [rbx+20h]
0x1800c660d  mov     rcx, [rax+0C8h]
0x1800c6614  mov     rax, [rcx]
0x1800c6617  mov     rax, [rax+10h]
0x1800c661b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6620  mov     rax, [rbx+20h]
0x1800c6624  and     [rax+0C8h], rsi
0x1800c662b  mov     esi, 3
0x1800c6630  jmp     short loc_1800C6656
0x1800c6632  mov     rcx, rdi
0x1800c6635  jmp     short loc_1800C664A
0x1800c6637  mov     rcx, [rcx+48h]; hdc
0x1800c663b  call    cs:__imp_CloseEnhMetaFile
0x1800c6642  nop     dword ptr [rax+rax+00h]
0x1800c6647  mov     rcx, rax; hmf
0x1800c664a  call    cs:__imp_DeleteEnhMetaFile
0x1800c6651  nop     dword ptr [rax+rax+00h]
0x1800c6656  mov     rax, [rbx+20h]
0x1800c665a  mov     rcx, rbx
0x1800c665d  mov     rdx, [rax+0D0h]
0x1800c6664  and     qword ptr [rdx+38h], 0
0x1800c6669  mov     rax, [rbx+20h]
0x1800c666d  mov     rdx, [rax+0D0h]
0x1800c6674  mov     dword ptr [rdx+8], 4C494146h
0x1800c667b  mov     edx, 1
0x1800c6680  mov     rax, [rbx+20h]
0x1800c6684  and     qword ptr [rax+0D0h], 0
0x1800c668c  mov     rax, [rbx+20h]
0x1800c6690  mov     [rax+0B0h], esi
0x1800c6696  mov     rax, [rbx]
0x1800c6699  mov     rax, [rax]
0x1800c669c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c66a1  mov     rcx, qword ptr [rbp+57h+EnhMetaHeader.bOpenGL]
0x1800c66a5  xor     rcx, rsp; StackCookie
0x1800c66a8  call    __security_check_cookie
0x1800c66ad  lea     r11, [rsp+0E0h+var_10]
0x1800c66b5  mov     rbx, [r11+28h]
0x1800c66b9  mov     rsi, [r11+30h]
0x1800c66bd  mov     rdi, [r11+38h]
0x1800c66c1  movaps  xmm6, xmmword ptr [r11-10h]
0x1800c66c6  movaps  xmm7, xmmword ptr [r11-20h]
0x1800c66cb  movaps  xmm8, xmmword ptr [r11-30h]
0x1800c66d0  mov     rsp, r11
0x1800c66d3  pop     r15
0x1800c66d5  pop     r14
0x1800c66d7  pop     rbp
0x1800c66d8  retn
```
