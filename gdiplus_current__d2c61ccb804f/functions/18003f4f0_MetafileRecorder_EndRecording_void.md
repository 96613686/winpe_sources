# MetafileRecorder::EndRecording(void)

- ea: `0x18003f4f0`
- end: `0x18003f942`
- name: `?EndRecording@MetafileRecorder@@UEAAXXZ`
- size: `1106`
- prototype: `void __fastcall(MetafileRecorder *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update`

## callees

- `0x180035ac0`
- `0x18003f4f0`
- `0x18003f948`
- `0x180089ad0`
- `0x180105d40`
- `0x1801066d0`
- `0x18010673c`
- `0x180172010`

## import_xrefs

- `GDI32!GetEnhMetaFileHeader` at `0x18003f67b`
- `GDI32!GetEnhMetaFileHeader` at `0x18003f67b`
- `GDI32!CloseEnhMetaFile` at `0x18003f59b`
- `GDI32!CloseEnhMetaFile` at `0x18003f63d`
- `GDI32!CloseEnhMetaFile` at `0x18003f59b`
- `GDI32!CloseEnhMetaFile` at `0x18003f63d`
- `GDI32!DeleteEnhMetaFile` at `0x18003f64c`
- `GDI32!DeleteEnhMetaFile` at `0x18003f8fa`
- `GDI32!DeleteEnhMetaFile` at `0x18003f64c`
- `GDI32!DeleteEnhMetaFile` at `0x18003f8fa`
- `GDI32!EnumEnhMetaFile` at `0x18003f8e7`
- `GDI32!EnumEnhMetaFile` at `0x18003f8e7`

## pseudocode

```c
void __fastcall MetafileRecorder::EndRecording(MetafileRecorder *this)
{
  int v1; // r14d
  char *v2; // rbx
  __int64 v4; // rcx
  HENHMETAFILE v5; // rsi
  HENHMETAFILE v6; // rcx
  __int64 v7; // r15
  bool v8; // r12
  int v9; // edx
  float v10; // xmm2_4
  float v11; // xmm1_4
  __m128 v12; // xmm7
  __m128 v13; // xmm6
  __m128 v14; // xmm8
  __m128 v15; // xmm1
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // r12d
  int v21; // r15d
  int v22; // esi
  int v23; // eax
  void *v24; // r9
  tagENHMETAHEADER EnhMetaHeader; // [rsp+38h] [rbp-69h] BYREF

  v1 = 0;
  v2 = (char *)this + 32;
  if ( *((_DWORD *)this + 2) != 1666338097 || *(_DWORD *)(*(_QWORD *)v2 + 176LL) != 2 )
  {
    v6 = CloseEnhMetaFile(*((HDC *)this + 9));
LABEL_9:
    DeleteEnhMetaFile(v6);
    goto LABEL_7;
  }
  v4 = *((_QWORD *)this + 3);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 144LL))(v4);
    if ( *((_DWORD *)this + 15) )
    {
      v20 = RasterizerCeiling(*((float *)this + 11));
      v21 = RasterizerCeiling(*((float *)this + 12));
      v22 = RasterizerCeiling(*((float *)this + 13));
      v23 = RasterizerCeiling(*((float *)this + 14));
      if ( v22 > v20 && v23 > v21 )
        GpGraphics::NoOpPatBlt(*(GpGraphics **)(*(_QWORD *)v2 + 208LL), v20, v21, v22 - v20, v23 - v21);
    }
    (*(void (__fastcall **)(MetafileRecorder *))(*(_QWORD *)this + 416LL))(this);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 144LL))(*((_QWORD *)this + 3));
  }
  v5 = CloseEnhMetaFile(*((HDC *)this + 9));
  if ( !v5 )
    goto LABEL_7;
  memset_0(&EnhMetaHeader, 0, 0x58u);
  if ( !GetEnhMetaFileHeader(v5, 0x58u, &EnhMetaHeader)
    || !(unsigned int)EmfHeaderIsValid((struct ENHMETAHEADER3 *)&EnhMetaHeader) )
  {
    v6 = v5;
    goto LABEL_9;
  }
  v7 = *(_QWORD *)v2;
  v8 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
  v9 = *(_DWORD *)(*(_QWORD *)v2 + 44LL);
  *(_QWORD *)(v7 + 184) = v5;
  *(_DWORD *)(*(_QWORD *)v2 + 224LL) = *((_DWORD *)this + 17);
  v10 = *(float *)(v7 + 48) / 2540.0;
  *(_DWORD *)(v7 + 44) = v9;
  *(_OWORD *)(v7 + 72) = *(_OWORD *)&EnhMetaHeader.iType;
  *(_OWORD *)(v7 + 88) = *(_OWORD *)&EnhMetaHeader.rclBounds.right;
  *(_OWORD *)(v7 + 104) = *(_OWORD *)&EnhMetaHeader.rclFrame.right;
  *(_OWORD *)(v7 + 120) = *(_OWORD *)&EnhMetaHeader.nBytes;
  *(_OWORD *)(v7 + 136) = *(_OWORD *)&EnhMetaHeader.offDescription;
  *(SIZEL *)(v7 + 152) = EnhMetaHeader.szlMillimeters;
  v11 = *(float *)(v7 + 52) / 2540.0;
  *(_DWORD *)(v7 + 36) = EnhMetaHeader.nBytes;
  v12 = (__m128)COERCE_UNSIGNED_INT((float)(EnhMetaHeader.rclFrame.right - EnhMetaHeader.rclFrame.left));
  v13 = (__m128)COERCE_UNSIGNED_INT((float)(EnhMetaHeader.rclFrame.bottom - EnhMetaHeader.rclFrame.top));
  v12.m128_f32[0] = (float)(v12.m128_f32[0] * v10) + 1.0;
  v14 = (__m128)COERCE_UNSIGNED_INT((float)EnhMetaHeader.rclFrame.top);
  v13.m128_f32[0] = (float)(v13.m128_f32[0] * v11) + 1.0;
  v14.m128_f32[0] = v14.m128_f32[0] * v11;
  v15 = (__m128)COERCE_UNSIGNED_INT((float)EnhMetaHeader.rclFrame.left);
  v15.m128_f32[0] = (float)(v15.m128_f32[0] * v10) + 0.5;
  if ( v8 )
    v16 = (int)_mm_round_ss(v15, v15, 9).m128_f32[0];
  else
    v16 = (int)floor(v15.m128_f32[0]);
  *(_DWORD *)(v7 + 56) = v16;
  v14.m128_f32[0] = v14.m128_f32[0] + 0.5;
  if ( v8 )
    v17 = (int)_mm_round_ss(v14, v14, 9).m128_f32[0];
  else
    v17 = (int)floor(v14.m128_f32[0]);
  *(_DWORD *)(v7 + 60) = v17;
  v12.m128_f32[0] = v12.m128_f32[0] + 0.5;
  if ( v8 )
    v18 = (int)_mm_round_ss(v12, v12, 9).m128_f32[0];
  else
    v18 = (int)floor(v12.m128_f32[0]);
  *(_DWORD *)(v7 + 64) = v18;
  v13.m128_f32[0] = v13.m128_f32[0] + 0.5;
  if ( v8 )
    v19 = (int)_mm_round_ss(v13, v13, 9).m128_f32[0];
  else
    v19 = (int)floor(v13.m128_f32[0]);
  *(_DWORD *)(v7 + 68) = v19;
  if ( !*(_QWORD *)(*(_QWORD *)v2 + 192LL) )
  {
    v24 = *(void **)(*(_QWORD *)v2 + 200LL);
    if ( v24 )
    {
      if ( !EnumEnhMetaFile(0, v5, EnumEmfToStream, v24, 0) )
      {
        DeleteEnhMetaFile(v5);
        *(_QWORD *)(*(_QWORD *)v2 + 184LL) = 0;
        goto LABEL_7;
      }
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)v2 + 200LL) + 16LL))(*(_QWORD *)(*(_QWORD *)v2 + 200LL));
      *(_QWORD *)(*(_QWORD *)v2 + 200LL) = 0;
    }
  }
  v1 = 3;
LABEL_7:
  *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v2 + 208LL) + 56LL) = 0;
  *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v2 + 208LL) + 8LL) = 1279869254;
  *(_QWORD *)(*(_QWORD *)v2 + 208LL) = 0;
  *(_DWORD *)(*(_QWORD *)v2 + 176LL) = v1;
  (**(void (__fastcall ***)(MetafileRecorder *, __int64))this)(this, 1);
}

```

## disassembly

```asm
0x18003f4f0  mov     rax, rsp
0x18003f4f3  mov     [rax+10h], rbx
0x18003f4f7  mov     [rax+18h], rsi
0x18003f4fb  push    rbp
0x18003f4fc  push    rdi
0x18003f4fd  push    r12
0x18003f4ff  push    r14
0x18003f501  push    r15
0x18003f503  lea     rbp, [rax-5Fh]
0x18003f507  sub     rsp, 0D0h
0x18003f50e  movaps  xmmword ptr [rax-38h], xmm6
0x18003f512  movaps  xmmword ptr [rax-48h], xmm7
0x18003f516  movaps  xmmword ptr [rax-58h], xmm8
0x18003f51b  mov     rax, cs:__security_cookie
0x18003f522  xor     rax, rsp
0x18003f525  mov     qword ptr [rbp+57h+EnhMetaHeader.bOpenGL], rax
0x18003f529  xor     r14d, r14d
0x18003f52c  lea     rbx, [rcx+20h]
0x18003f530  cmp     dword ptr [rcx+8], 63524D31h
0x18003f537  mov     rdi, rcx
0x18003f53a  jnz     loc_18003F639
0x18003f540  mov     rax, [rbx]
0x18003f543  cmp     dword ptr [rax+0B0h], 2
0x18003f54a  jnz     loc_18003F639
0x18003f550  mov     rcx, [rcx+18h]
0x18003f554  test    rcx, rcx
0x18003f557  jz      short loc_18003F597
0x18003f559  mov     rax, [rcx]
0x18003f55c  mov     rax, [rax+90h]
0x18003f563  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f568  cmp     [rdi+3Ch], r14d
0x18003f56c  jnz     loc_18003F814
0x18003f572  mov     rax, [rdi]
0x18003f575  mov     rcx, rdi
0x18003f578  mov     rax, [rax+1A0h]
0x18003f57f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f584  mov     rcx, [rdi+18h]
0x18003f588  mov     rax, [rcx]
0x18003f58b  mov     rax, [rax+90h]
0x18003f592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f597  mov     rcx, [rdi+48h]; hdc
0x18003f59b  call    cs:__imp_CloseEnhMetaFile
0x18003f5a2  nop     dword ptr [rax+rax+00h]
0x18003f5a7  mov     rsi, rax
0x18003f5aa  test    rax, rax
0x18003f5ad  jnz     loc_18003F65D
0x18003f5b3  mov     rax, [rbx]
0x18003f5b6  mov     rcx, rdi
0x18003f5b9  mov     rdx, [rax+0D0h]
0x18003f5c0  mov     qword ptr [rdx+38h], 0
0x18003f5c8  mov     rax, [rbx]
0x18003f5cb  mov     rdx, [rax+0D0h]
0x18003f5d2  mov     dword ptr [rdx+8], 4C494146h
0x18003f5d9  mov     edx, 1
0x18003f5de  mov     rax, [rbx]
0x18003f5e1  mov     qword ptr [rax+0D0h], 0
0x18003f5ec  mov     rax, [rbx]
0x18003f5ef  mov     [rax+0B0h], r14d
0x18003f5f6  mov     rax, [rdi]
0x18003f5f9  mov     rax, [rax]
0x18003f5fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f601  mov     rcx, qword ptr [rbp+57h+EnhMetaHeader.bOpenGL]
0x18003f605  xor     rcx, rsp; StackCookie
0x18003f608  call    __security_check_cookie
0x18003f60d  lea     r11, [rsp+0F0h+var_20]
0x18003f615  mov     rbx, [r11+38h]
0x18003f619  mov     rsi, [r11+40h]
0x18003f61d  movaps  xmm6, xmmword ptr [r11-10h]
0x18003f622  movaps  xmm7, xmmword ptr [r11-20h]
0x18003f627  movaps  xmm8, xmmword ptr [r11-30h]
0x18003f62c  mov     rsp, r11
0x18003f62f  pop     r15
0x18003f631  pop     r14
0x18003f633  pop     r12
0x18003f635  pop     rdi
0x18003f636  pop     rbp
0x18003f637  retn
0x18003f639  mov     rcx, [rcx+48h]; hdc
0x18003f63d  call    cs:__imp_CloseEnhMetaFile
0x18003f644  nop     dword ptr [rax+rax+00h]
0x18003f649  mov     rcx, rax; hmf
0x18003f64c  call    cs:__imp_DeleteEnhMetaFile
0x18003f653  nop     dword ptr [rax+rax+00h]
0x18003f658  jmp     loc_18003F5B3
0x18003f65d  mov     r15d, 58h ; 'X'
0x18003f663  lea     rcx, [rbp+57h+EnhMetaHeader]; void *
0x18003f667  mov     r8d, r15d; Size
0x18003f66a  xor     edx, edx; Val
0x18003f66c  call    memset_0
0x18003f671  lea     r8, [rbp+57h+EnhMetaHeader]; lpEnhMetaHeader
0x18003f675  mov     edx, r15d; nSize
0x18003f678  mov     rcx, rsi; hemf
0x18003f67b  call    cs:__imp_GetEnhMetaFileHeader
0x18003f682  nop     dword ptr [rax+rax+00h]
0x18003f687  test    eax, eax
0x18003f689  jz      loc_18003F93A
0x18003f68f  lea     rcx, [rbp+57h+EnhMetaHeader]; struct ENHMETAHEADER3 *
0x18003f693  call    ?EmfHeaderIsValid@@YAHAEAUENHMETAHEADER3@@@Z; EmfHeaderIsValid(ENHMETAHEADER3 &)
0x18003f698  test    eax, eax
0x18003f69a  jz      loc_18003F93A
0x18003f6a0  mov     r15, [rbx]
0x18003f6a3  mov     r12b, cs:?Feature_GdiPlusOptimizations_Misc_IsEnabled@@3_NA; bool Feature_GdiPlusOptimizations_Misc_IsEnabled
0x18003f6aa  mov     edx, [r15+2Ch]
0x18003f6ae  mov     [r15+0B8h], rsi
0x18003f6b5  mov     eax, [rdi+44h]
0x18003f6b8  mov     rcx, [rbx]
0x18003f6bb  mov     [rcx+0E0h], eax
0x18003f6c1  movss   xmm2, dword ptr [r15+30h]
0x18003f6c7  divss   xmm2, cs:__real@451ec000
0x18003f6cf  mov     [r15+2Ch], edx
0x18003f6d3  movups  xmm0, xmmword ptr [rbp+57h+EnhMetaHeader.iType]
0x18003f6d7  movups  xmmword ptr [r15+48h], xmm0
0x18003f6dc  movups  xmm1, xmmword ptr [rbp+57h+EnhMetaHeader.rclBounds.right]
0x18003f6e0  movups  xmmword ptr [r15+58h], xmm1
0x18003f6e5  movups  xmm0, xmmword ptr [rbp+57h+EnhMetaHeader.rclFrame.right]
0x18003f6e9  movups  xmmword ptr [r15+68h], xmm0
0x18003f6ee  movups  xmm1, xmmword ptr [rbp+57h+EnhMetaHeader.nBytes]
0x18003f6f2  movups  xmmword ptr [r15+78h], xmm1
0x18003f6f7  movups  xmm0, xmmword ptr [rbp+57h+EnhMetaHeader.offDescription]
0x18003f6fb  movups  xmmword ptr [r15+88h], xmm0
0x18003f703  movsd   xmm1, qword ptr [rbp+57h+EnhMetaHeader.szlMillimeters.cx]
0x18003f708  movsd   qword ptr [r15+98h], xmm1
0x18003f711  movss   xmm1, dword ptr [r15+34h]
0x18003f717  divss   xmm1, cs:__real@451ec000
0x18003f71f  mov     eax, [rbp+57h+EnhMetaHeader.nBytes]
0x18003f722  mov     [r15+24h], eax
0x18003f726  mov     eax, [rbp+57h+EnhMetaHeader.rclFrame.right]
0x18003f729  sub     eax, [rbp+57h+EnhMetaHeader.rclFrame.left]
0x18003f72c  movd    xmm8, [rbp+57h+EnhMetaHeader.rclFrame.top]
0x18003f732  movd    xmm7, eax
0x18003f736  mov     eax, [rbp+57h+EnhMetaHeader.rclFrame.bottom]
0x18003f739  sub     eax, [rbp+57h+EnhMetaHeader.rclFrame.top]
0x18003f73c  cvtdq2ps xmm7, xmm7
0x18003f73f  movd    xmm6, eax
0x18003f743  mulss   xmm7, xmm2
0x18003f747  cvtdq2ps xmm6, xmm6
0x18003f74a  addss   xmm7, cs:__real@3f800000
0x18003f752  mulss   xmm6, xmm1
0x18003f756  cvtdq2ps xmm8, xmm8
0x18003f75a  addss   xmm6, cs:__real@3f800000
0x18003f762  mulss   xmm8, xmm1
0x18003f767  movd    xmm1, [rbp+57h+EnhMetaHeader.rclFrame.left]
0x18003f76c  cvtdq2ps xmm1, xmm1
0x18003f76f  mulss   xmm1, xmm2
0x18003f773  addss   xmm1, cs:__real@3f000000
0x18003f77b  test    r12b, r12b
0x18003f77e  jnz     loc_18003F87D
0x18003f784  cvtps2pd xmm0, xmm1; X
0x18003f787  call    floor
0x18003f78c  cvttsd2si eax, xmm0
0x18003f790  mov     [r15+38h], eax
0x18003f794  addss   xmm8, cs:__real@3f000000
0x18003f79d  test    r12b, r12b
0x18003f7a0  jnz     loc_18003F88F
0x18003f7a6  cvtps2pd xmm0, xmm8; X
0x18003f7aa  call    floor
0x18003f7af  cvttsd2si eax, xmm0
0x18003f7b3  mov     [r15+3Ch], eax
0x18003f7b7  addss   xmm7, cs:__real@3f000000
0x18003f7bf  test    r12b, r12b
0x18003f7c2  jnz     loc_18003F8A2
0x18003f7c8  cvtps2pd xmm0, xmm7; X
0x18003f7cb  call    floor
0x18003f7d0  cvttsd2si eax, xmm0
0x18003f7d4  mov     [r15+40h], eax
0x18003f7d8  addss   xmm6, cs:__real@3f000000
0x18003f7e0  test    r12b, r12b
0x18003f7e3  jnz     loc_18003F8B4
0x18003f7e9  cvtps2pd xmm0, xmm6; X
0x18003f7ec  call    floor
0x18003f7f1  cvttsd2si eax, xmm0
0x18003f7f5  mov     [r15+44h], eax
0x18003f7f9  mov     rax, [rbx]
0x18003f7fc  cmp     [rax+0C0h], r14
0x18003f803  jz      loc_18003F8C6
0x18003f809  mov     r14d, 3
0x18003f80f  jmp     loc_18003F5B3
0x18003f814  movss   xmm0, dword ptr [rdi+2Ch]; float
0x18003f819  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x18003f81e  movss   xmm0, dword ptr [rdi+30h]; float
0x18003f823  mov     r12d, eax
0x18003f826  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x18003f82b  movss   xmm0, dword ptr [rdi+34h]; float
0x18003f830  mov     r15d, eax
0x18003f833  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x18003f838  movss   xmm0, dword ptr [rdi+38h]; float
0x18003f83d  mov     esi, eax
0x18003f83f  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x18003f844  cmp     esi, r12d
0x18003f847  jle     loc_18003F572
0x18003f84d  cmp     eax, r15d
0x18003f850  jle     loc_18003F572
0x18003f856  mov     rcx, [rbx]
0x18003f859  sub     esi, r12d
0x18003f85c  sub     eax, r15d
0x18003f85f  mov     r9d, esi; int
0x18003f862  mov     r8d, r15d; int
0x18003f865  mov     dword ptr [rsp+0F0h+lpRect], eax; int
0x18003f869  mov     edx, r12d; int
0x18003f86c  mov     rcx, [rcx+0D0h]; this
0x18003f873  call    ?NoOpPatBlt@GpGraphics@@IEAAXHHHH@Z; GpGraphics::NoOpPatBlt(int,int,int,int)
0x18003f878  jmp     loc_18003F572
0x18003f87d  movaps  xmm0, xmm1
0x18003f880  roundss xmm0, xmm0, 9
0x18003f886  cvttss2si eax, xmm0
0x18003f88a  jmp     loc_18003F790
0x18003f88f  movaps  xmm0, xmm8
0x18003f893  roundss xmm0, xmm0, 9
0x18003f899  cvttss2si eax, xmm0
0x18003f89d  jmp     loc_18003F7B3
0x18003f8a2  movaps  xmm0, xmm7
0x18003f8a5  roundss xmm0, xmm0, 9
0x18003f8ab  cvttss2si eax, xmm0
0x18003f8af  jmp     loc_18003F7D4
0x18003f8b4  movaps  xmm0, xmm6
0x18003f8b7  roundss xmm0, xmm0, 9
0x18003f8bd  cvttss2si eax, xmm0
0x18003f8c1  jmp     loc_18003F7F5
0x18003f8c6  mov     r9, [rax+0C8h]; param
0x18003f8cd  test    r9, r9
0x18003f8d0  jz      loc_18003F809
0x18003f8d6  lea     r8, EnumEmfToStream; proc
0x18003f8dd  mov     [rsp+0F0h+lpRect], r14; lpRect
0x18003f8e2  mov     rdx, rsi; hmf
0x18003f8e5  xor     ecx, ecx; hdc
0x18003f8e7  call    cs:__imp_EnumEnhMetaFile
0x18003f8ee  nop     dword ptr [rax+rax+00h]
0x18003f8f3  test    eax, eax
0x18003f8f5  jnz     short loc_18003F915
0x18003f8f7  mov     rcx, rsi; hmf
0x18003f8fa  call    cs:__imp_DeleteEnhMetaFile
0x18003f901  nop     dword ptr [rax+rax+00h]
0x18003f906  mov     rax, [rbx]
0x18003f909  mov     [rax+0B8h], r14
0x18003f910  jmp     loc_18003F5B3
0x18003f915  mov     rax, [rbx]
0x18003f918  mov     rcx, [rax+0C8h]
0x18003f91f  mov     rax, [rcx]
0x18003f922  mov     rax, [rax+10h]
0x18003f926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f92b  mov     rax, [rbx]
0x18003f92e  mov     [rax+0C8h], r14
0x18003f935  jmp     loc_18003F809
0x18003f93a  mov     rcx, rsi
0x18003f93d  jmp     loc_18003F64C
```
