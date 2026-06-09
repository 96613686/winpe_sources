# GpMetafile::InitForRecording(HDC__ *,EmfType,RectF const *,MetafileFrameUnit,ushort const *,GpMetafile *)

- ea: `0x180087df8`
- end: `0x18008824d`
- name: `?InitForRecording@GpMetafile@@IEAAHPEAUHDC__@@W4EmfType@@PEBVRectF@@W4MetafileFrameUnit@@PEBGPEAV1@@Z`
- size: `1109`
- prototype: `int __high(HDC, enum EmfType, const struct RectF *, enum MetafileFrameUnit, const unsigned __int16 *, struct GpMetafile *)`
- caller_count: `3`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x180088254`
- `0x180124cfc`
- `0x180124dac`

## callees

- `0x180019610`
- `0x180063cd8`
- `0x180085ff0`
- `0x180086ea4`
- `0x1800870cc`
- `0x180087df8`
- `0x180105d40`
- `0x1801066d0`
- `0x180172010`

## import_xrefs

- `GDI32!CreateEnhMetaFileW` at `0x180087e9e`
- `GDI32!CreateEnhMetaFileW` at `0x180087e9e`
- `GDI32!CloseEnhMetaFile` at `0x180088004`
- `GDI32!CloseEnhMetaFile` at `0x180088004`
- `GDI32!DeleteEnhMetaFile` at `0x180088013`
- `GDI32!DeleteEnhMetaFile` at `0x180088013`
- `GDI32!GetDeviceCaps` at `0x180087ebe`
- `GDI32!GetDeviceCaps` at `0x180087ed5`
- `GDI32!GetDeviceCaps` at `0x180087ef0`
- `GDI32!GetDeviceCaps` at `0x180087f08`
- `GDI32!GetDeviceCaps` at `0x180087ebe`
- `GDI32!GetDeviceCaps` at `0x180087ed5`
- `GDI32!GetDeviceCaps` at `0x180087ef0`
- `GDI32!GetDeviceCaps` at `0x180087f08`

## pseudocode

```c
__int64 __fastcall GpMetafile::InitForRecording(
        __int64 a1,
        HDC a2,
        unsigned int a3,
        float *a4,
        int a5,
        __int64 a6,
        __int64 a7)
{
  const RECT *v7; // r14
  HDC EnhMetaFileW; // rax
  HDC v12; // rdi
  int DeviceCaps; // r13d
  unsigned int v14; // r15d
  int v15; // r12d
  int v16; // ebx
  int v17; // eax
  float v18; // xmm5_4
  float v19; // xmm6_4
  float v20; // xmm5_4
  float v21; // xmm6_4
  __int64 v22; // rax
  HENHMETAFILE v23; // rax
  __m128 v25; // xmm7
  bool v26; // di
  __m128 v27; // xmm1
  int v28; // r12d
  __m128 v29; // xmm6
  __m128 v30; // xmm1
  int v31; // r15d
  int v32; // r14d
  int v33; // eax
  __int64 v34; // r12
  bool v35; // zf
  unsigned int v36; // r14d
  __int64 v37; // rax
  __int64 v38; // rbx
  __int64 v39; // rax
  unsigned int v40; // edx
  GpGraphics *v41; // rcx
  __int64 v42; // [rsp+58h] [rbp-61h] BYREF
  float v43; // [rsp+60h] [rbp-59h]
  float v44; // [rsp+64h] [rbp-55h]
  unsigned int v45; // [rsp+68h] [rbp-51h]
  _DWORD v46[2]; // [rsp+70h] [rbp-49h] BYREF
  __int64 v47; // [rsp+78h] [rbp-41h]
  __int128 v48; // [rsp+80h] [rbp-39h] BYREF

  v7 = 0;
  v45 = a3;
  v47 = a7;
  v48 = 0;
  if ( a4 )
  {
    if ( a4[2] < 0.0 || a4[3] < 0.0 )
      return 0;
    if ( a5 == 7 )
    {
      v25 = (__m128)*(unsigned int *)a4;
      v26 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
      v27 = v25;
      v27.m128_f32[0] = v25.m128_f32[0] + 0.5;
      if ( Feature_GdiPlusOptimizations_Misc_IsEnabled )
        v28 = (int)_mm_round_ss(v27, v27, 9).m128_f32[0];
      else
        v28 = (int)floor(v27.m128_f32[0]);
      v29 = (__m128)*((unsigned int *)a4 + 1);
      LODWORD(v48) = v28;
      v30 = v29;
      v30.m128_f32[0] = v29.m128_f32[0] + 0.5;
      if ( v26 )
        v31 = (int)_mm_round_ss(v30, v30, 9).m128_f32[0];
      else
        v31 = (int)floor(v30.m128_f32[0]);
      DWORD1(v48) = v31;
      v25.m128_f32[0] = (float)(v25.m128_f32[0] + a4[2]) + 0.5;
      if ( v26 )
        v32 = (int)_mm_round_ss(v25, v25, 9).m128_f32[0];
      else
        v32 = (int)floor(v25.m128_f32[0]);
      DWORD2(v48) = v32;
      v29.m128_f32[0] = (float)(v29.m128_f32[0] + a4[3]) + 0.5;
      if ( v26 )
        v33 = (int)_mm_round_ss(v29, v29, 9).m128_f32[0];
      else
        v33 = (int)floor(v29.m128_f32[0]);
      HIDWORD(v48) = v33;
      if ( v28 > v32 || v31 > v33 )
        return 0;
    }
    else if ( !(unsigned int)GetFrameRectInMM100Units(a2) )
    {
      return 0;
    }
    v7 = (const RECT *)&v48;
  }
  EnhMetaFileW = CreateEnhMetaFileW(a2, *(LPCWSTR *)(a1 + 192), v7, 0);
  v12 = EnhMetaFileW;
  if ( !EnhMetaFileW )
    return 0;
  DeviceCaps = GetDeviceCaps(EnhMetaFileW, 8);
  v14 = 4;
  v15 = GetDeviceCaps(v12, 10);
  v16 = GetDeviceCaps(v12, 4);
  v46[0] = v16;
  v17 = GetDeviceCaps(v12, 6);
  v46[1] = v17;
  if ( DeviceCaps <= 0 || v15 <= 0 || v16 <= 0 || v17 <= 0 )
    goto LABEL_15;
  v18 = (float)DeviceCaps / (float)v16;
  *(float *)(a1 + 48) = v18 * 25.4;
  v19 = (float)v15 / (float)v17;
  *(float *)(a1 + 52) = v19 * 25.4;
  if ( v7 )
  {
    v20 = v18 * 0.0099999998;
    v21 = v19 * 0.0099999998;
    *(float *)&v42 = (float)(int)v48 * v20;
    *((float *)&v42 + 1) = (float)SDWORD1(v48) * v21;
    v43 = (float)(DWORD2(v48) - v48) * v20;
    v44 = (float)(HIDWORD(v48) - DWORD1(v48)) * v21;
  }
  else
  {
    v42 = 0;
    v43 = (float)DeviceCaps - 1.0;
    v44 = (float)v15 - 1.0;
  }
  v22 = GpMallocEx(1752, 0);
  if ( !v22 )
    goto LABEL_15;
  v34 = v47;
  v35 = v7 == 0;
  v36 = v45;
  v37 = MetafileRecorder::MetafileRecorder(v22, a1, v45, v12, !v35, v46, &v42);
  v38 = v37;
  if ( !v37 )
    goto LABEL_15;
  if ( *(_DWORD *)(v37 + 8) != 1666338097 )
  {
    (**(void (__fastcall ***)(__int64, __int64))v37)(v37, 1);
    goto LABEL_15;
  }
  if ( !v34 )
    v14 = v36;
  v39 = GpGraphics::GetForMetafile(v37, v14, v12);
  *(_QWORD *)(a1 + 208) = v39;
  if ( !v39 )
  {
    (**(void (__fastcall ***)(__int64, __int64))v38)(v38, 1);
LABEL_15:
    v23 = CloseEnhMetaFile(v12);
    DeleteEnhMetaFile(v23);
    return 0;
  }
  if ( *(_DWORD *)(v39 + 8) != 1634879281 )
  {
    *(_DWORD *)(v38 + 8) = 1279869254;
    v41 = *(GpGraphics **)(a1 + 208);
    if ( v41 )
      GpGraphics::`scalar deleting destructor'(v41, v40);
    *(_QWORD *)(a1 + 208) = 0;
    goto LABEL_15;
  }
  return 1;
}

```

## disassembly

```asm
0x180087df8  mov     rax, rsp
0x180087dfb  push    rbp
0x180087dfc  push    rbx
0x180087dfd  push    rsi
0x180087dfe  push    rdi
0x180087dff  push    r12
0x180087e01  push    r13
0x180087e03  push    r14
0x180087e05  push    r15
0x180087e07  lea     rbp, [rax-47h]
0x180087e0b  sub     rsp, 0B8h
0x180087e12  movaps  xmmword ptr [rax-58h], xmm6
0x180087e16  movaps  xmmword ptr [rax-68h], xmm7
0x180087e1a  mov     rax, cs:__security_cookie
0x180087e21  xor     rax, rsp
0x180087e24  mov     [rbp+3Fh+var_68], rax
0x180087e28  mov     rax, [rbp+3Fh+arg_30]
0x180087e2c  xor     r14d, r14d
0x180087e2f  mov     [rbp+3Fh+var_90], r8d
0x180087e33  xorps   xmm0, xmm0
0x180087e36  mov     [rbp+3Fh+var_80], rax
0x180087e3a  mov     rbx, r9
0x180087e3d  mov     r13, rdx
0x180087e40  mov     rsi, rcx
0x180087e43  xorps   xmm1, xmm1
0x180087e46  movups  [rbp+3Fh+var_78], xmm0
0x180087e4a  test    r9, r9
0x180087e4d  jz      short loc_180087E8E
0x180087e4f  comiss  xmm1, dword ptr [r9+8]
0x180087e54  ja      loc_18008801F
0x180087e5a  comiss  xmm1, dword ptr [r9+0Ch]
0x180087e5f  ja      loc_18008801F
0x180087e65  mov     r8d, [rbp+3Fh+arg_20]
0x180087e69  cmp     r8d, 7
0x180087e6d  jz      loc_180088077
0x180087e73  lea     r9, [rbp+3Fh+var_78]
0x180087e77  mov     rdx, rbx
0x180087e7a  mov     rcx, r13; hdc
0x180087e7d  call    GetFrameRectInMM100Units
0x180087e82  test    eax, eax
0x180087e84  jz      loc_18008801F
0x180087e8a  lea     r14, [rbp+3Fh+var_78]
0x180087e8e  mov     rdx, [rsi+0C0h]; lpFilename
0x180087e95  xor     r9d, r9d; lpDesc
0x180087e98  mov     r8, r14; lprc
0x180087e9b  mov     rcx, r13; hdc
0x180087e9e  call    cs:__imp_CreateEnhMetaFileW
0x180087ea5  nop     dword ptr [rax+rax+00h]
0x180087eaa  mov     rdi, rax
0x180087ead  test    rax, rax
0x180087eb0  jz      loc_18008801F
0x180087eb6  mov     edx, 8; index
0x180087ebb  mov     rcx, rax; hdc
0x180087ebe  call    cs:__imp_GetDeviceCaps
0x180087ec5  nop     dword ptr [rax+rax+00h]
0x180087eca  mov     edx, 0Ah; index
0x180087ecf  mov     rcx, rdi; hdc
0x180087ed2  mov     r13d, eax
0x180087ed5  call    cs:__imp_GetDeviceCaps
0x180087edc  nop     dword ptr [rax+rax+00h]
0x180087ee1  mov     r15d, 4
0x180087ee7  mov     rcx, rdi; hdc
0x180087eea  mov     edx, r15d; index
0x180087eed  mov     r12d, eax
0x180087ef0  call    cs:__imp_GetDeviceCaps
0x180087ef7  nop     dword ptr [rax+rax+00h]
0x180087efc  lea     edx, [r15+2]; index
0x180087f00  mov     rcx, rdi; hdc
0x180087f03  mov     ebx, eax
0x180087f05  mov     [rbp+3Fh+var_88], eax
0x180087f08  call    cs:__imp_GetDeviceCaps
0x180087f0f  nop     dword ptr [rax+rax+00h]
0x180087f14  mov     [rbp+3Fh+var_84], eax
0x180087f17  test    r13d, r13d
0x180087f1a  jle     loc_180088001
0x180087f20  test    r12d, r12d
0x180087f23  jle     loc_180088001
0x180087f29  test    ebx, ebx
0x180087f2b  jle     loc_180088001
0x180087f31  test    eax, eax
0x180087f33  jle     loc_180088001
0x180087f39  movd    xmm3, r13d
0x180087f3e  movd    xmm0, ebx
0x180087f42  movd    xmm4, r12d
0x180087f47  cvtdq2ps xmm0, xmm0
0x180087f4a  cvtdq2ps xmm3, xmm3
0x180087f4d  cvtdq2ps xmm4, xmm4
0x180087f50  movaps  xmm5, xmm3
0x180087f53  movaps  xmm6, xmm4
0x180087f56  divss   xmm5, xmm0
0x180087f5a  movd    xmm0, eax
0x180087f5e  movaps  xmm1, xmm5
0x180087f61  mulss   xmm1, cs:__real@41cb3333
0x180087f69  cvtdq2ps xmm0, xmm0
0x180087f6c  movss   dword ptr [rsi+30h], xmm1
0x180087f71  divss   xmm6, xmm0
0x180087f75  movaps  xmm0, xmm6
0x180087f78  mulss   xmm0, cs:__real@41cb3333
0x180087f80  movss   dword ptr [rsi+34h], xmm0
0x180087f85  test    r14, r14
0x180087f88  jz      loc_180088050
0x180087f8e  mulss   xmm5, cs:__real@3c23d70a
0x180087f96  mov     eax, dword ptr [rbp+3Fh+var_78+8]
0x180087f99  sub     eax, dword ptr [rbp+3Fh+var_78]
0x180087f9c  movd    xmm0, dword ptr [rbp+3Fh+var_78]
0x180087fa1  mulss   xmm6, cs:__real@3c23d70a
0x180087fa9  movd    xmm1, dword ptr [rbp+3Fh+var_78+4]
0x180087fae  cvtdq2ps xmm0, xmm0
0x180087fb1  cvtdq2ps xmm1, xmm1
0x180087fb4  mulss   xmm0, xmm5
0x180087fb8  mulss   xmm1, xmm6
0x180087fbc  movss   dword ptr [rbp+3Fh+var_A0], xmm0
0x180087fc1  movd    xmm0, eax
0x180087fc5  mov     eax, dword ptr [rbp+3Fh+var_78+0Ch]
0x180087fc8  sub     eax, dword ptr [rbp+3Fh+var_78+4]
0x180087fcb  cvtdq2ps xmm0, xmm0
0x180087fce  movss   dword ptr [rbp+3Fh+var_A0+4], xmm1
0x180087fd3  mulss   xmm0, xmm5
0x180087fd7  movss   [rbp+3Fh+var_98], xmm0
0x180087fdc  movd    xmm0, eax
0x180087fe0  cvtdq2ps xmm0, xmm0
0x180087fe3  mulss   xmm0, xmm6
0x180087fe7  movss   [rbp+3Fh+var_94], xmm0
0x180087fec  xor     edx, edx
0x180087fee  mov     ecx, 6D8h
0x180087ff3  call    GpMallocEx
0x180087ff8  test    rax, rax
0x180087ffb  jnz     loc_180088135
0x180088001  mov     rcx, rdi; hdc
0x180088004  call    cs:__imp_CloseEnhMetaFile
0x18008800b  nop     dword ptr [rax+rax+00h]
0x180088010  mov     rcx, rax; hmf
0x180088013  call    cs:__imp_DeleteEnhMetaFile
0x18008801a  nop     dword ptr [rax+rax+00h]
0x18008801f  xor     eax, eax
0x180088021  mov     rcx, [rbp+3Fh+var_68]
0x180088025  xor     rcx, rsp; StackCookie
0x180088028  call    __security_check_cookie
0x18008802d  lea     r11, [rsp+0F0h+var_38]
0x180088035  movaps  xmm6, xmmword ptr [r11-18h]
0x18008803a  movaps  xmm7, xmmword ptr [r11-28h]
0x18008803f  mov     rsp, r11
0x180088042  pop     r15
0x180088044  pop     r14
0x180088046  pop     r13
0x180088048  pop     r12
0x18008804a  pop     rdi
0x18008804b  pop     rsi
0x18008804c  pop     rbx
0x18008804d  pop     rbp
0x18008804e  retn
0x180088050  subss   xmm3, cs:__real@3f800000
0x180088058  subss   xmm4, cs:__real@3f800000
0x180088060  mov     [rbp+3Fh+var_A0], 0
0x180088068  movss   [rbp+3Fh+var_98], xmm3
0x18008806d  movss   [rbp+3Fh+var_94], xmm4
0x180088072  jmp     loc_180087FEC
0x180088077  movss   xmm7, dword ptr [r9]
0x18008807c  mov     dil, cs:?Feature_GdiPlusOptimizations_Misc_IsEnabled@@3_NA; bool Feature_GdiPlusOptimizations_Misc_IsEnabled
0x180088083  movaps  xmm1, xmm7
0x180088086  addss   xmm1, cs:__real@3f000000
0x18008808e  test    dil, dil
0x180088091  jnz     loc_1800881DA
0x180088097  cvtps2pd xmm0, xmm1; X
0x18008809a  call    floor
0x18008809f  cvttsd2si r12d, xmm0
0x1800880a4  movss   xmm6, dword ptr [rbx+4]
0x1800880a9  mov     dword ptr [rbp+3Fh+var_78], r12d
0x1800880ad  movaps  xmm1, xmm6
0x1800880b0  addss   xmm1, cs:__real@3f000000
0x1800880b8  test    dil, dil
0x1800880bb  jnz     loc_1800881ED
0x1800880c1  cvtps2pd xmm0, xmm1; X
0x1800880c4  call    floor
0x1800880c9  cvttsd2si r15d, xmm0
0x1800880ce  mov     dword ptr [rbp+3Fh+var_78+4], r15d
0x1800880d2  addss   xmm7, dword ptr [rbx+8]
0x1800880d7  addss   xmm7, cs:__real@3f000000
0x1800880df  test    dil, dil
0x1800880e2  jnz     loc_180088200
0x1800880e8  cvtps2pd xmm0, xmm7; X
0x1800880eb  call    floor
0x1800880f0  cvttsd2si r14d, xmm0
0x1800880f5  mov     dword ptr [rbp+3Fh+var_78+8], r14d
0x1800880f9  addss   xmm6, dword ptr [rbx+0Ch]
0x1800880fe  addss   xmm6, cs:__real@3f000000
0x180088106  test    dil, dil
0x180088109  jnz     loc_180088213
0x18008810f  cvtps2pd xmm0, xmm6; X
0x180088112  call    floor
0x180088117  cvttsd2si eax, xmm0
0x18008811b  mov     dword ptr [rbp+3Fh+var_78+0Ch], eax
0x18008811e  cmp     r12d, r14d
0x180088121  jg      loc_18008801F
0x180088127  cmp     r15d, eax
0x18008812a  jg      loc_18008801F
0x180088130  jmp     loc_180087E8A
0x180088135  mov     r12, [rbp+3Fh+var_80]
0x180088139  lea     rdx, [rbp+3Fh+var_A0]
0x18008813d  xor     ecx, ecx
0x18008813f  mov     [rsp+0F0h+var_B0], r12
0x180088144  mov     [rsp+0F0h+var_C0], rdx
0x180088149  test    r14, r14
0x18008814c  mov     r14d, [rbp+3Fh+var_90]
0x180088150  lea     rdx, [rbp+3Fh+var_88]
0x180088154  setnz   cl
0x180088157  mov     [rsp+0F0h+var_C8], rdx
0x18008815c  mov     dword ptr [rsp+0F0h+var_D0], ecx
0x180088160  mov     r9, rdi
0x180088163  mov     rcx, rax
0x180088166  mov     r8d, r14d
0x180088169  mov     rdx, rsi
0x18008816c  call    ??0MetafileRecorder@@QEAA@PEAVGpMetafile@@W4EmfType@@PEAUHDC__@@HAEAUtagSIZE@@AEAVRectF@@K0@Z; MetafileRecorder::MetafileRecorder(GpMetafile *,EmfType,HDC__ *,int,tagSIZE &,RectF &,ulong,GpMetafile *)
0x180088171  mov     rbx, rax
0x180088174  test    rax, rax
0x180088177  jz      loc_180088001
0x18008817d  cmp     dword ptr [rax+8], 63524D31h
0x180088184  jnz     short loc_1800881BA
0x180088186  test    r12, r12
0x180088189  mov     r8, rdi
0x18008818c  mov     rcx, rax
0x18008818f  cmovz   r15d, r14d
0x180088193  mov     edx, r15d
0x180088196  call    ?GetForMetafile@GpGraphics@@KAPEAV1@PEAVIMetafileRecord@@W4EmfType@@PEAUHDC__@@@Z; GpGraphics::GetForMetafile(IMetafileRecord *,EmfType,HDC__ *)
0x18008819b  mov     [rsi+0D0h], rax
0x1800881a2  test    rax, rax
0x1800881a5  jz      short loc_1800881D2
0x1800881a7  cmp     dword ptr [rax+8], 61724731h
0x1800881ae  jnz     short loc_180088225
0x1800881b0  mov     eax, 1
0x1800881b5  jmp     loc_180088021
0x1800881ba  mov     rcx, [rax]
0x1800881bd  mov     rax, [rcx]
0x1800881c0  mov     edx, 1
0x1800881c5  mov     rcx, rbx
0x1800881c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800881cd  jmp     loc_180088001
0x1800881d2  mov     rax, [rbx]
0x1800881d5  mov     rax, [rax]
0x1800881d8  jmp     short loc_1800881C0
0x1800881da  movaps  xmm0, xmm1
0x1800881dd  roundss xmm0, xmm0, 9
0x1800881e3  cvttss2si r12d, xmm0
0x1800881e8  jmp     loc_1800880A4
0x1800881ed  movaps  xmm0, xmm1
0x1800881f0  roundss xmm0, xmm0, 9
0x1800881f6  cvttss2si r15d, xmm0
0x1800881fb  jmp     loc_1800880CE
0x180088200  movaps  xmm0, xmm7
0x180088203  roundss xmm0, xmm0, 9
0x180088209  cvttss2si r14d, xmm0
0x18008820e  jmp     loc_1800880F5
0x180088213  movaps  xmm0, xmm6
0x180088216  roundss xmm0, xmm0, 9
0x18008821c  cvttss2si eax, xmm0
0x180088220  jmp     loc_18008811B
0x180088225  mov     dword ptr [rbx+8], 4C494146h
0x18008822c  mov     rcx, [rsi+0D0h]; this
0x180088233  test    rcx, rcx
0x180088236  jz      short loc_18008823D
0x180088238  call    ??_GGpGraphics@@QEAAPEAXI@Z; GpGraphics::`scalar deleting destructor'(uint)
0x18008823d  mov     qword ptr [rsi+0D0h], 0
0x180088248  jmp     loc_180088001
```
