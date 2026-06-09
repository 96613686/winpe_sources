# GpMetafile::InitForRecording(HDC__ *,EmfType,RectF const *,MetafileFrameUnit,ushort const *,GpMetafile *)

- ea: `0x1800096b0`
- end: `0x180009ad9`
- name: `?InitForRecording@GpMetafile@@IEAAHPEAUHDC__@@W4EmfType@@PEBVRectF@@W4MetafileFrameUnit@@PEBGPEAV1@@Z`
- size: `1065`
- prototype: `int __high(HDC, enum EmfType, const struct RectF *, enum MetafileFrameUnit, const unsigned __int16 *, struct GpMetafile *)`
- caller_count: `3`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x180009ae0`
- `0x18010e6e0`
- `0x18010e79c`

## callees

- `0x1800096b0`
- `0x18000e6d0`
- `0x180094a24`
- `0x1800c7d34`
- `0x1800cf06c`
- `0x1800d61dc`
- `0x1800e5044`
- `0x1800e9380`
- `0x1800ea080`
- `0x180175010`

## import_xrefs

- `GDI32!CreateEnhMetaFileW` at `0x18000984a`
- `GDI32!CreateEnhMetaFileW` at `0x18000984a`
- `GDI32!CloseEnhMetaFile` at `0x180009a8d`
- `GDI32!CloseEnhMetaFile` at `0x180009a8d`
- `GDI32!DeleteEnhMetaFile` at `0x180009a9c`
- `GDI32!DeleteEnhMetaFile` at `0x180009a9c`
- `GDI32!GetDeviceCaps` at `0x18000986a`
- `GDI32!GetDeviceCaps` at `0x180009881`
- `GDI32!GetDeviceCaps` at `0x18000989a`
- `GDI32!GetDeviceCaps` at `0x1800098b2`
- `GDI32!GetDeviceCaps` at `0x18000986a`
- `GDI32!GetDeviceCaps` at `0x180009881`
- `GDI32!GetDeviceCaps` at `0x18000989a`
- `GDI32!GetDeviceCaps` at `0x1800098b2`

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
  __m128 v11; // xmm7
  bool v12; // di
  __m128 v13; // xmm0
  int v14; // r12d
  __m128 v15; // xmm6
  __m128 v16; // xmm0
  int v17; // r15d
  int v18; // r14d
  int v19; // eax
  HDC EnhMetaFileW; // rax
  HDC v21; // rdi
  int DeviceCaps; // r13d
  unsigned int v23; // ebx
  int v24; // r12d
  int v25; // r15d
  int v26; // eax
  float v27; // xmm3_4
  float v28; // xmm4_4
  float v29; // xmm4_4
  float v30; // xmm3_4
  __int64 v31; // rax
  __int64 v32; // r15
  bool v33; // zf
  unsigned int v34; // r14d
  __int64 v35; // rdx
  __int64 v36; // rbx
  __int64 v37; // rax
  unsigned int v38; // edx
  GpGraphics *v40; // rcx
  HENHMETAFILE v41; // rax
  __int64 v43; // [rsp+60h] [rbp-59h] BYREF
  float v44; // [rsp+68h] [rbp-51h] BYREF
  float v45; // [rsp+6Ch] [rbp-4Dh]
  float v46; // [rsp+70h] [rbp-49h]
  float v47; // [rsp+74h] [rbp-45h]
  _DWORD v48[2]; // [rsp+78h] [rbp-41h] BYREF
  __int128 v49; // [rsp+80h] [rbp-39h] BYREF

  v7 = 0;
  v43 = a7;
  v49 = 0;
  if ( a4 )
  {
    if ( a4[2] < 0.0 || a4[3] < 0.0 )
      return 0;
    if ( a5 == 7 )
    {
      v11 = (__m128)*(unsigned int *)a4;
      v12 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
      v13 = v11;
      v13.m128_f32[0] = v11.m128_f32[0] + 0.5;
      if ( Feature_GdiPlusOptimizations_Misc_IsEnabled )
        v14 = (int)_mm_round_ss(v13, v13, 9).m128_f32[0];
      else
        v14 = (int)floor(v13.m128_f32[0]);
      v15 = (__m128)*((unsigned int *)a4 + 1);
      LODWORD(v49) = v14;
      v16 = v15;
      v16.m128_f32[0] = v15.m128_f32[0] + 0.5;
      if ( v12 )
        v17 = (int)_mm_round_ss(v16, v16, 9).m128_f32[0];
      else
        v17 = (int)floor(v16.m128_f32[0]);
      DWORD1(v49) = v17;
      v11.m128_f32[0] = (float)(v11.m128_f32[0] + a4[2]) + 0.5;
      if ( v12 )
        v18 = (int)_mm_round_ss(v11, v11, 9).m128_f32[0];
      else
        v18 = (int)floor(v11.m128_f32[0]);
      DWORD2(v49) = v18;
      v15.m128_f32[0] = (float)(v15.m128_f32[0] + a4[3]) + 0.5;
      if ( v12 )
        v19 = (int)_mm_round_ss(v15, v15, 9).m128_f32[0];
      else
        v19 = (int)floor(v15.m128_f32[0]);
      HIDWORD(v49) = v19;
      if ( v14 > v18 || v17 > v19 )
        return 0;
    }
    else if ( !(unsigned int)GetFrameRectInMM100Units(a2) )
    {
      return 0;
    }
    v7 = (const RECT *)&v49;
  }
  EnhMetaFileW = CreateEnhMetaFileW(a2, *(LPCWSTR *)(a1 + 192), v7, 0);
  v21 = EnhMetaFileW;
  if ( EnhMetaFileW )
  {
    DeviceCaps = GetDeviceCaps(EnhMetaFileW, 8);
    v23 = 4;
    v24 = GetDeviceCaps(v21, 10);
    v25 = GetDeviceCaps(v21, 4);
    v48[0] = v25;
    v26 = GetDeviceCaps(v21, 6);
    v48[1] = v26;
    if ( DeviceCaps > 0 && v24 > 0 && v25 > 0 && v26 > 0 )
    {
      v27 = (float)DeviceCaps / (float)v25;
      *(float *)(a1 + 48) = v27 * 25.4;
      v28 = (float)v24 / (float)v26;
      *(float *)(a1 + 52) = v28 * 25.4;
      if ( v7 )
      {
        v29 = v28 * 0.0099999998;
        v30 = v27 * 0.0099999998;
        v45 = (float)SDWORD1(v49) * v29;
        v44 = (float)(int)v49 * v30;
        v46 = (float)(DWORD2(v49) - v49) * v30;
        v47 = (float)(HIDWORD(v49) - DWORD1(v49)) * v29;
      }
      else
      {
        v44 = 0.0;
        v45 = 0.0;
        v46 = (float)DeviceCaps - 1.0;
        v47 = (float)v24 - 1.0;
      }
      v31 = GpMallocEx(1752, 0);
      v32 = v43;
      if ( v31 )
      {
        v33 = v7 == 0;
        v34 = a3;
        v31 = MetafileRecorder::MetafileRecorder(v31, a1, a3, v21, !v33, v48, &v44);
      }
      else
      {
        v34 = a3;
      }
      v43 = v31;
      if ( (unsigned int)CheckValid<MetafileRecorder>(&v43) )
      {
        if ( !v32 )
          v23 = v34;
        v35 = v23;
        v36 = v43;
        v37 = GpGraphics::GetForMetafile(v43, v35, v21);
        *(_QWORD *)(a1 + 208) = v37;
        if ( v37 )
        {
          if ( *(_DWORD *)(v37 + 8) == 1634879281 )
            return 1;
          *(_DWORD *)(v36 + 8) = 1279869254;
          v40 = *(GpGraphics **)(a1 + 208);
          if ( v40 )
            GpGraphics::`scalar deleting destructor'(v40, v38);
          *(_QWORD *)(a1 + 208) = 0;
        }
        else if ( v36 )
        {
          (**(void (__fastcall ***)(__int64, __int64))v36)(v36, 1);
        }
      }
    }
    v41 = CloseEnhMetaFile(v21);
    DeleteEnhMetaFile(v41);
  }
  return 0;
}

```

## disassembly

```asm
0x1800096b0  mov     rax, rsp
0x1800096b3  push    rbp
0x1800096b4  push    rbx
0x1800096b5  push    rsi
0x1800096b6  push    rdi
0x1800096b7  push    r12
0x1800096b9  push    r13
0x1800096bb  push    r14
0x1800096bd  push    r15
0x1800096bf  lea     rbp, [rax-47h]
0x1800096c3  sub     rsp, 0B8h
0x1800096ca  movaps  xmmword ptr [rax-58h], xmm6
0x1800096ce  movaps  xmmword ptr [rax-68h], xmm7
0x1800096d2  mov     rax, cs:__security_cookie
0x1800096d9  xor     rax, rsp
0x1800096dc  mov     [rbp+3Fh+var_68], rax
0x1800096e0  mov     rax, [rbp+3Fh+arg_30]
0x1800096e4  xor     r14d, r14d
0x1800096e7  mov     [rbp+3Fh+var_A0], r8d
0x1800096eb  xorps   xmm0, xmm0
0x1800096ee  mov     [rbp+3Fh+var_98], rax
0x1800096f2  mov     rbx, r9
0x1800096f5  mov     r13, rdx
0x1800096f8  mov     rsi, rcx
0x1800096fb  xorps   xmm1, xmm1
0x1800096fe  movups  [rbp+3Fh+var_78], xmm0
0x180009702  test    r9, r9
0x180009705  jz      loc_18000983A
0x18000970b  comiss  xmm1, dword ptr [r9+8]
0x180009710  ja      loc_180009AA8
0x180009716  comiss  xmm1, dword ptr [r9+0Ch]
0x18000971b  ja      loc_180009AA8
0x180009721  mov     r8d, [rbp+3Fh+arg_20]
0x180009725  cmp     r8d, 7
0x180009729  jnz     loc_18000981F
0x18000972f  movss   xmm7, dword ptr [r9]
0x180009734  mov     dil, cs:?Feature_GdiPlusOptimizations_Misc_IsEnabled@@3_NA; bool Feature_GdiPlusOptimizations_Misc_IsEnabled
0x18000973b  movaps  xmm0, xmm7
0x18000973e  addss   xmm0, cs:__real@3f000000
0x180009746  test    dil, dil
0x180009749  jz      short loc_18000975B
0x18000974b  movaps  xmm1, xmm0
0x18000974e  roundss xmm1, xmm1, 9
0x180009754  cvttss2si r12d, xmm1
0x180009759  jmp     short loc_180009768
0x18000975b  cvtps2pd xmm0, xmm0; X
0x18000975e  call    floor
0x180009763  cvttsd2si r12d, xmm0
0x180009768  movss   xmm6, dword ptr [rbx+4]
0x18000976d  mov     dword ptr [rbp+3Fh+var_78], r12d
0x180009771  movaps  xmm0, xmm6
0x180009774  addss   xmm0, cs:__real@3f000000
0x18000977c  test    dil, dil
0x18000977f  jz      short loc_180009791
0x180009781  movaps  xmm1, xmm0
0x180009784  roundss xmm1, xmm1, 9
0x18000978a  cvttss2si r15d, xmm1
0x18000978f  jmp     short loc_18000979E
0x180009791  cvtps2pd xmm0, xmm0; X
0x180009794  call    floor
0x180009799  cvttsd2si r15d, xmm0
0x18000979e  mov     dword ptr [rbp+3Fh+var_78+4], r15d
0x1800097a2  addss   xmm7, dword ptr [rbx+8]
0x1800097a7  addss   xmm7, cs:__real@3f000000
0x1800097af  test    dil, dil
0x1800097b2  jz      short loc_1800097C7
0x1800097b4  movaps  xmm0, xmm7
0x1800097b7  movaps  xmm1, xmm0
0x1800097ba  roundss xmm1, xmm1, 9
0x1800097c0  cvttss2si r14d, xmm1
0x1800097c5  jmp     short loc_1800097D4
0x1800097c7  cvtps2pd xmm0, xmm7; X
0x1800097ca  call    floor
0x1800097cf  cvttsd2si r14d, xmm0
0x1800097d4  mov     dword ptr [rbp+3Fh+var_78+8], r14d
0x1800097d8  addss   xmm6, dword ptr [rbx+0Ch]
0x1800097dd  addss   xmm6, cs:__real@3f000000
0x1800097e5  test    dil, dil
0x1800097e8  jz      short loc_1800097FC
0x1800097ea  movaps  xmm0, xmm6
0x1800097ed  movaps  xmm1, xmm0
0x1800097f0  roundss xmm1, xmm1, 9
0x1800097f6  cvttss2si eax, xmm1
0x1800097fa  jmp     short loc_180009808
0x1800097fc  cvtps2pd xmm0, xmm6; X
0x1800097ff  call    floor
0x180009804  cvttsd2si eax, xmm0
0x180009808  mov     dword ptr [rbp+3Fh+var_78+0Ch], eax
0x18000980b  cmp     r12d, r14d
0x18000980e  jg      loc_180009AA8
0x180009814  cmp     r15d, eax
0x180009817  jg      loc_180009AA8
0x18000981d  jmp     short loc_180009836
0x18000981f  lea     r9, [rbp+3Fh+var_78]
0x180009823  mov     rdx, rbx
0x180009826  mov     rcx, r13; hdc
0x180009829  call    GetFrameRectInMM100Units
0x18000982e  test    eax, eax
0x180009830  jz      loc_180009AA8
0x180009836  lea     r14, [rbp+3Fh+var_78]
0x18000983a  mov     rdx, [rsi+0C0h]; lpFilename
0x180009841  xor     r9d, r9d; lpDesc
0x180009844  mov     r8, r14; lprc
0x180009847  mov     rcx, r13; hdc
0x18000984a  call    cs:__imp_CreateEnhMetaFileW
0x180009851  nop     dword ptr [rax+rax+00h]
0x180009856  mov     rdi, rax
0x180009859  test    rax, rax
0x18000985c  jz      loc_180009AA8
0x180009862  mov     edx, 8; index
0x180009867  mov     rcx, rax; hdc
0x18000986a  call    cs:__imp_GetDeviceCaps
0x180009871  nop     dword ptr [rax+rax+00h]
0x180009876  mov     edx, 0Ah; index
0x18000987b  mov     rcx, rdi; hdc
0x18000987e  mov     r13d, eax
0x180009881  call    cs:__imp_GetDeviceCaps
0x180009888  nop     dword ptr [rax+rax+00h]
0x18000988d  mov     ebx, 4
0x180009892  mov     rcx, rdi; hdc
0x180009895  mov     edx, ebx; index
0x180009897  mov     r12d, eax
0x18000989a  call    cs:__imp_GetDeviceCaps
0x1800098a1  nop     dword ptr [rax+rax+00h]
0x1800098a6  lea     edx, [rbx+2]; index
0x1800098a9  mov     rcx, rdi; hdc
0x1800098ac  mov     r15d, eax
0x1800098af  mov     [rbp+3Fh+var_80], eax
0x1800098b2  call    cs:__imp_GetDeviceCaps
0x1800098b9  nop     dword ptr [rax+rax+00h]
0x1800098be  mov     [rbp+3Fh+var_7C], eax
0x1800098c1  test    r13d, r13d
0x1800098c4  jle     loc_180009A8A
0x1800098ca  test    r12d, r12d
0x1800098cd  jle     loc_180009A8A
0x1800098d3  test    r15d, r15d
0x1800098d6  jle     loc_180009A8A
0x1800098dc  test    eax, eax
0x1800098de  jle     loc_180009A8A
0x1800098e4  movd    xmm5, r13d
0x1800098e9  movd    xmm0, r15d
0x1800098ee  movd    xmm6, r12d
0x1800098f3  cvtdq2ps xmm0, xmm0
0x1800098f6  cvtdq2ps xmm5, xmm5
0x1800098f9  cvtdq2ps xmm6, xmm6
0x1800098fc  movaps  xmm3, xmm5
0x1800098ff  movaps  xmm4, xmm6
0x180009902  divss   xmm3, xmm0
0x180009906  movd    xmm0, eax
0x18000990a  movaps  xmm1, xmm3
0x18000990d  mulss   xmm1, cs:__real@41cb3333
0x180009915  cvtdq2ps xmm0, xmm0
0x180009918  movss   dword ptr [rsi+30h], xmm1
0x18000991d  divss   xmm4, xmm0
0x180009921  movaps  xmm0, xmm4
0x180009924  mulss   xmm0, cs:__real@41cb3333
0x18000992c  movss   dword ptr [rsi+34h], xmm0
0x180009931  test    r14, r14
0x180009934  jz      short loc_180009996
0x180009936  mulss   xmm4, cs:__real@3c23d70a
0x18000993e  mov     eax, dword ptr [rbp+3Fh+var_78+8]
0x180009941  sub     eax, dword ptr [rbp+3Fh+var_78]
0x180009944  mulss   xmm3, cs:__real@3c23d70a
0x18000994c  movd    xmm0, dword ptr [rbp+3Fh+var_78+4]
0x180009951  movd    xmm1, dword ptr [rbp+3Fh+var_78]
0x180009956  cvtdq2ps xmm0, xmm0
0x180009959  cvtdq2ps xmm1, xmm1
0x18000995c  mulss   xmm0, xmm4
0x180009960  mulss   xmm1, xmm3
0x180009964  movss   [rbp+3Fh+var_8C], xmm0
0x180009969  movd    xmm0, eax
0x18000996d  mov     eax, dword ptr [rbp+3Fh+var_78+0Ch]
0x180009970  sub     eax, dword ptr [rbp+3Fh+var_78+4]
0x180009973  cvtdq2ps xmm0, xmm0
0x180009976  movss   [rbp+3Fh+var_90], xmm1
0x18000997b  mulss   xmm0, xmm3
0x18000997f  movss   [rbp+3Fh+var_88], xmm0
0x180009984  movd    xmm0, eax
0x180009988  cvtdq2ps xmm0, xmm0
0x18000998b  mulss   xmm0, xmm4
0x18000998f  movss   [rbp+3Fh+var_84], xmm0
0x180009994  jmp     short loc_1800099B8
0x180009996  subss   xmm5, cs:__real@3f800000
0x18000999e  subss   xmm6, cs:__real@3f800000
0x1800099a6  and     [rbp+3Fh+var_90], 0
0x1800099aa  and     [rbp+3Fh+var_8C], 0
0x1800099ae  movss   [rbp+3Fh+var_88], xmm5
0x1800099b3  movss   [rbp+3Fh+var_84], xmm6
0x1800099b8  xor     edx, edx
0x1800099ba  mov     ecx, 6D8h
0x1800099bf  call    GpMallocEx
0x1800099c4  mov     r15, [rbp+3Fh+var_98]
0x1800099c8  test    rax, rax
0x1800099cb  jz      short loc_180009A07
0x1800099cd  xor     ecx, ecx
0x1800099cf  mov     [rsp+0F0h+var_B0], r15
0x1800099d4  test    r14, r14
0x1800099d7  lea     rdx, [rbp+3Fh+var_90]
0x1800099db  mov     r14d, [rbp+3Fh+var_A0]
0x1800099df  mov     r9, rdi
0x1800099e2  mov     [rsp+0F0h+var_C0], rdx
0x1800099e7  setnz   cl
0x1800099ea  lea     rdx, [rbp+3Fh+var_80]
0x1800099ee  mov     r8d, r14d
0x1800099f1  mov     [rsp+0F0h+var_C8], rdx
0x1800099f6  mov     rdx, rsi
0x1800099f9  mov     dword ptr [rsp+0F0h+var_D0], ecx
0x1800099fd  mov     rcx, rax
0x180009a00  call    ??0MetafileRecorder@@QEAA@PEAVGpMetafile@@W4EmfType@@PEAUHDC__@@HAEAUtagSIZE@@AEAVRectF@@K0@Z; MetafileRecorder::MetafileRecorder(GpMetafile *,EmfType,HDC__ *,int,tagSIZE &,RectF &,ulong,GpMetafile *)
0x180009a05  jmp     short loc_180009A0B
0x180009a07  mov     r14d, [rbp+3Fh+var_A0]
0x180009a0b  lea     rcx, [rbp+3Fh+var_98]
0x180009a0f  mov     [rbp+3Fh+var_98], rax
0x180009a13  call    ??$CheckValid@VMetafileRecorder@@@@YAHAEAPEAVMetafileRecorder@@@Z; CheckValid<MetafileRecorder>(MetafileRecorder * &)
0x180009a18  test    eax, eax
0x180009a1a  jz      short loc_180009A8A
0x180009a1c  test    r15, r15
0x180009a1f  mov     r8, rdi
0x180009a22  cmovz   ebx, r14d
0x180009a26  mov     edx, ebx
0x180009a28  mov     rbx, [rbp+3Fh+var_98]
0x180009a2c  mov     rcx, rbx
0x180009a2f  call    ?GetForMetafile@GpGraphics@@KAPEAV1@PEAVIMetafileRecord@@W4EmfType@@PEAUHDC__@@@Z; GpGraphics::GetForMetafile(IMetafileRecord *,EmfType,HDC__ *)
0x180009a34  mov     [rsi+0D0h], rax
0x180009a3b  test    rax, rax
0x180009a3e  jz      short loc_180009A72
0x180009a40  cmp     dword ptr [rax+8], 61724731h
0x180009a47  jnz     short loc_180009A50
0x180009a49  mov     eax, 1
0x180009a4e  jmp     short loc_180009AAA
0x180009a50  mov     dword ptr [rbx+8], 4C494146h
0x180009a57  mov     rcx, [rsi+0D0h]; this
0x180009a5e  test    rcx, rcx
0x180009a61  jz      short loc_180009A68
0x180009a63  call    ??_GGpGraphics@@QEAAPEAXI@Z; GpGraphics::`scalar deleting destructor'(uint)
0x180009a68  and     qword ptr [rsi+0D0h], 0
0x180009a70  jmp     short loc_180009A8A
0x180009a72  test    rbx, rbx
0x180009a75  jz      short loc_180009A8A
0x180009a77  mov     rax, [rbx]
0x180009a7a  mov     edx, 1
0x180009a7f  mov     rcx, rbx
0x180009a82  mov     rax, [rax]
0x180009a85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a8a  mov     rcx, rdi; hdc
0x180009a8d  call    cs:__imp_CloseEnhMetaFile
0x180009a94  nop     dword ptr [rax+rax+00h]
0x180009a99  mov     rcx, rax; hmf
0x180009a9c  call    cs:__imp_DeleteEnhMetaFile
0x180009aa3  nop     dword ptr [rax+rax+00h]
0x180009aa8  xor     eax, eax
0x180009aaa  mov     rcx, [rbp+3Fh+var_68]
0x180009aae  xor     rcx, rsp; StackCookie
0x180009ab1  call    __security_check_cookie
0x180009ab6  lea     r11, [rsp+0F0h+var_38]
0x180009abe  movaps  xmm6, xmmword ptr [r11-18h]
0x180009ac3  movaps  xmm7, xmmword ptr [r11-28h]
0x180009ac8  mov     rsp, r11
0x180009acb  pop     r15
0x180009acd  pop     r14
0x180009acf  pop     r13
0x180009ad1  pop     r12
0x180009ad3  pop     rdi
0x180009ad4  pop     rsi
0x180009ad5  pop     rbx
0x180009ad6  pop     rbp
0x180009ad7  retn
```
