# ApplyAdapterConfiguration(HMONITOR__ *,AdapterGammaConfiguration *,float,float)

- ea: `0x180019c48`
- end: `0x180019f06`
- name: `?ApplyAdapterConfiguration@@YAJPEAUHMONITOR__@@PEAUAdapterGammaConfiguration@@MM@Z`
- size: `702`
- prototype: `__int64 __fastcall(HMONITOR, struct AdapterGammaConfiguration *, float, float)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x180019a3c`

## callees

- `0x180019c48`
- `0x180019f0c`
- `0x18001a060`
- `0x18001ede4`
- `0x180026090`
- `0x18002e614`
- `0x18002e670`
- `0x18005c044`

## import_xrefs

- `api-ms-win-crt-math-l1-1-0!_finite` at `0x180019d87`
- `api-ms-win-crt-math-l1-1-0!_finite` at `0x180019daa`
- `api-ms-win-crt-math-l1-1-0!_finite` at `0x180019dd0`
- `api-ms-win-crt-math-l1-1-0!_finite` at `0x180019df0`
- `api-ms-win-crt-math-l1-1-0!_finite` at `0x180019e11`
- `api-ms-win-crt-math-l1-1-0!_finite` at `0x180019e27`
- `api-ms-win-crt-math-l1-1-0!_finite` at `0x180019e3d`
- `api-ms-win-crt-math-l1-1-0!_finite` at `0x180019e4f`
- `api-ms-win-crt-math-l1-1-0!_finite` at `0x180019d87`
- `api-ms-win-crt-math-l1-1-0!_finite` at `0x180019daa`
- `api-ms-win-crt-math-l1-1-0!_finite` at `0x180019dd0`
- `api-ms-win-crt-math-l1-1-0!_finite` at `0x180019df0`
- `api-ms-win-crt-math-l1-1-0!_finite` at `0x180019e11`
- `api-ms-win-crt-math-l1-1-0!_finite` at `0x180019e27`
- `api-ms-win-crt-math-l1-1-0!_finite` at `0x180019e3d`
- `api-ms-win-crt-math-l1-1-0!_finite` at `0x180019e4f`

## pseudocode

```c
__int64 __fastcall ApplyAdapterConfiguration(HMONITOR a1, struct AdapterGammaConfiguration *a2, float a3, float a4)
{
  int v6; // ebx
  int v7; // eax
  char *v8; // rdi
  struct ICalibrationCurve *v10; // [rsp+20h] [rbp-48h] BYREF
  struct ICalibrationCurve *v11; // [rsp+28h] [rbp-40h] BYREF
  struct ICalibrationCurve *v12; // [rsp+90h] [rbp+28h] BYREF

  v12 = 0;
  v10 = 0;
  v11 = 0;
  if ( !a1 || !a2 || a3 >= a4 )
    goto LABEL_33;
  if ( !*(_DWORD *)a2 )
  {
    v8 = (char *)a2 + 8;
    if ( a2 != (struct AdapterGammaConfiguration *)-8LL
      && _finite(a3)
      && a3 <= 0.0
      && _finite(a4)
      && a4 >= 1.0
      && _finite(*(float *)v8)
      && *(float *)v8 > 0.0
      && _finite(*((float *)v8 + 2))
      && *((float *)v8 + 2) > 0.0
      && _finite(*((float *)v8 + 1))
      && _finite(*((float *)v8 + 3))
      && _finite(*((float *)v8 + 5))
      && _finite(*((float *)v8 + 4))
      && *((float *)v8 + 4) >= 0.0 )
    {
      v12 = (struct ICalibrationCurve *)operator new(0x30u);
      v12 = ParameterizedCalibrationCurve::ParameterizedCalibrationCurve(v12, (struct ParameterizedCurve *)v8, a3, a4);
      if ( !v12 )
      {
        v6 = -2147024882;
        goto LABEL_34;
      }
      v6 = ParameterizedCalibrationCurve::Create((struct ParameterizedCurve *)(v8 + 24), a3, a4, &v10);
      if ( v6 < 0 )
        goto LABEL_34;
      v7 = ParameterizedCalibrationCurve::Create((struct ParameterizedCurve *)(v8 + 48), a3, a4, &v11);
LABEL_13:
      v6 = v7;
      if ( v7 >= 0 )
        goto LABEL_14;
      goto LABEL_34;
    }
LABEL_33:
    v6 = -2147024809;
    goto LABEL_34;
  }
  if ( *(_DWORD *)a2 == 1 )
  {
    v6 = UniformPointListCurve::Create(*((_DWORD *)a2 + 2), *((float **)a2 + 2), &v12);
    if ( v6 < 0 )
      goto LABEL_34;
    v6 = UniformPointListCurve::Create(*((_DWORD *)a2 + 2), *((float **)a2 + 3), &v10);
    if ( v6 < 0 )
      goto LABEL_34;
    v7 = UniformPointListCurve::Create(*((_DWORD *)a2 + 2), *((float **)a2 + 4), &v11);
    goto LABEL_13;
  }
  if ( *(_DWORD *)a2 != 2 )
  {
LABEL_14:
    v6 = ApplyCalibrationCurvesThroughGDI(a1, v12, v10, v11);
    goto LABEL_34;
  }
  v6 = HDRToneResponseCurve::Create(*((_DWORD *)a2 + 2), *((float **)a2 + 2), *((float **)a2 + 3), &v12);
  if ( v6 >= 0 )
  {
    v6 = HDRToneResponseCurve::Create(*((_DWORD *)a2 + 2), *((float **)a2 + 4), *((float **)a2 + 5), &v10);
    if ( v6 >= 0 )
    {
      v7 = HDRToneResponseCurve::Create(*((_DWORD *)a2 + 2), *((float **)a2 + 6), *((float **)a2 + 7), &v11);
      goto LABEL_13;
    }
  }
LABEL_34:
  operator delete(v12);
  operator delete(v10);
  operator delete(v11);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180019c48  push    rbp
0x180019c4a  push    rbx
0x180019c4b  push    rsi
0x180019c4c  push    rdi
0x180019c4d  mov     rbp, rsp
0x180019c50  sub     rsp, 68h
0x180019c54  movaps  [rsp+68h+var_18], xmm6
0x180019c59  movaps  xmm6, xmm2
0x180019c5c  movaps  [rsp+68h+var_28], xmm7
0x180019c61  movaps  xmm7, xmm3
0x180019c64  movaps  [rsp+68h+var_38], xmm8
0x180019c6a  mov     rdi, rdx
0x180019c6d  mov     [rbp+arg_0], 0
0x180019c75  mov     rsi, rcx
0x180019c78  mov     [rbp+var_48], 0
0x180019c80  mov     [rbp+var_40], 0
0x180019c88  test    rcx, rcx
0x180019c8b  jz      loc_180019EC0
0x180019c91  test    rdx, rdx
0x180019c94  jz      loc_180019EC0
0x180019c9a  comiss  xmm6, xmm7
0x180019c9d  jnb     loc_180019EC0
0x180019ca3  mov     ecx, [rdx]
0x180019ca5  test    ecx, ecx
0x180019ca7  jz      loc_180019D76
0x180019cad  sub     ecx, 1
0x180019cb0  jz      short loc_180019D0D
0x180019cb2  cmp     ecx, 1
0x180019cb5  jnz     loc_180019D5B
0x180019cbb  mov     r8, [rdx+18h]; float *
0x180019cbf  lea     r9, [rbp+arg_0]; struct ICalibrationCurve **
0x180019cc3  mov     rdx, [rdx+10h]; float *
0x180019cc7  mov     ecx, [rdi+8]; unsigned int
0x180019cca  call    ?Create@HDRToneResponseCurve@@SAJIPEAM0PEAPEAVICalibrationCurve@@@Z; HDRToneResponseCurve::Create(uint,float *,float *,ICalibrationCurve * *)
0x180019ccf  mov     ebx, eax
0x180019cd1  test    eax, eax
0x180019cd3  js      loc_180019EC5
0x180019cd9  mov     r8, [rdi+28h]; float *
0x180019cdd  lea     r9, [rbp+var_48]; struct ICalibrationCurve **
0x180019ce1  mov     rdx, [rdi+20h]; float *
0x180019ce5  mov     ecx, [rdi+8]; unsigned int
0x180019ce8  call    ?Create@HDRToneResponseCurve@@SAJIPEAM0PEAPEAVICalibrationCurve@@@Z; HDRToneResponseCurve::Create(uint,float *,float *,ICalibrationCurve * *)
0x180019ced  mov     ebx, eax
0x180019cef  test    eax, eax
0x180019cf1  js      loc_180019EC5
0x180019cf7  mov     r8, [rdi+38h]; float *
0x180019cfb  lea     r9, [rbp+var_40]; struct ICalibrationCurve **
0x180019cff  mov     rdx, [rdi+30h]; float *
0x180019d03  mov     ecx, [rdi+8]; unsigned int
0x180019d06  call    ?Create@HDRToneResponseCurve@@SAJIPEAM0PEAPEAVICalibrationCurve@@@Z; HDRToneResponseCurve::Create(uint,float *,float *,ICalibrationCurve * *)
0x180019d0b  jmp     short loc_180019D51
0x180019d0d  mov     rdx, [rdx+10h]; float *
0x180019d11  lea     r8, [rbp+arg_0]; struct ICalibrationCurve **
0x180019d15  mov     ecx, [rdi+8]; unsigned int
0x180019d18  call    ?Create@UniformPointListCurve@@SAJIPEAMPEAPEAVICalibrationCurve@@@Z; UniformPointListCurve::Create(uint,float *,ICalibrationCurve * *)
0x180019d1d  mov     ebx, eax
0x180019d1f  test    eax, eax
0x180019d21  js      loc_180019EC5
0x180019d27  mov     rdx, [rdi+18h]; float *
0x180019d2b  lea     r8, [rbp+var_48]; struct ICalibrationCurve **
0x180019d2f  mov     ecx, [rdi+8]; unsigned int
0x180019d32  call    ?Create@UniformPointListCurve@@SAJIPEAMPEAPEAVICalibrationCurve@@@Z; UniformPointListCurve::Create(uint,float *,ICalibrationCurve * *)
0x180019d37  mov     ebx, eax
0x180019d39  test    eax, eax
0x180019d3b  js      loc_180019EC5
0x180019d41  mov     rdx, [rdi+20h]; float *
0x180019d45  lea     r8, [rbp+var_40]; struct ICalibrationCurve **
0x180019d49  mov     ecx, [rdi+8]; unsigned int
0x180019d4c  call    ?Create@UniformPointListCurve@@SAJIPEAMPEAPEAVICalibrationCurve@@@Z; UniformPointListCurve::Create(uint,float *,ICalibrationCurve * *)
0x180019d51  mov     ebx, eax
0x180019d53  test    eax, eax
0x180019d55  js      loc_180019EC5
0x180019d5b  mov     r9, [rbp+var_40]; struct ICalibrationCurve *
0x180019d5f  mov     rcx, rsi; hMonitor
0x180019d62  mov     r8, [rbp+var_48]; struct ICalibrationCurve *
0x180019d66  mov     rdx, [rbp+arg_0]; struct ICalibrationCurve *
0x180019d6a  call    ?ApplyCalibrationCurvesThroughGDI@@YAJPEAUHMONITOR__@@PEAVICalibrationCurve@@11@Z; ApplyCalibrationCurvesThroughGDI(HMONITOR__ *,ICalibrationCurve *,ICalibrationCurve *,ICalibrationCurve *)
0x180019d6f  mov     ebx, eax
0x180019d71  jmp     loc_180019EC5
0x180019d76  add     rdi, 8
0x180019d7a  jz      loc_180019EC0
0x180019d80  xorps   xmm0, xmm0
0x180019d83  cvtss2sd xmm0, xmm6; X
0x180019d87  call    cs:__imp__finite
0x180019d8d  test    eax, eax
0x180019d8f  jz      loc_180019EC0
0x180019d95  xorps   xmm8, xmm8
0x180019d99  comiss  xmm6, xmm8
0x180019d9d  ja      loc_180019EC0
0x180019da3  xorps   xmm0, xmm0
0x180019da6  cvtss2sd xmm0, xmm7; X
0x180019daa  call    cs:__imp__finite
0x180019db0  test    eax, eax
0x180019db2  jz      loc_180019EC0
0x180019db8  movss   xmm0, cs:__real@3f800000
0x180019dc0  comiss  xmm0, xmm7
0x180019dc3  ja      loc_180019EC0
0x180019dc9  movss   xmm0, dword ptr [rdi]
0x180019dcd  cvtps2pd xmm0, xmm0; X
0x180019dd0  call    cs:__imp__finite
0x180019dd6  test    eax, eax
0x180019dd8  jz      loc_180019EC0
0x180019dde  comiss  xmm8, dword ptr [rdi]
0x180019de2  jnb     loc_180019EC0
0x180019de8  movss   xmm0, dword ptr [rdi+8]
0x180019ded  cvtps2pd xmm0, xmm0; X
0x180019df0  call    cs:__imp__finite
0x180019df6  test    eax, eax
0x180019df8  jz      loc_180019EC0
0x180019dfe  comiss  xmm8, dword ptr [rdi+8]
0x180019e03  jnb     loc_180019EC0
0x180019e09  movss   xmm0, dword ptr [rdi+4]
0x180019e0e  cvtps2pd xmm0, xmm0; X
0x180019e11  call    cs:__imp__finite
0x180019e17  test    eax, eax
0x180019e19  jz      loc_180019EC0
0x180019e1f  movss   xmm0, dword ptr [rdi+0Ch]
0x180019e24  cvtps2pd xmm0, xmm0; X
0x180019e27  call    cs:__imp__finite
0x180019e2d  test    eax, eax
0x180019e2f  jz      loc_180019EC0
0x180019e35  movss   xmm0, dword ptr [rdi+14h]
0x180019e3a  cvtps2pd xmm0, xmm0; X
0x180019e3d  call    cs:__imp__finite
0x180019e43  test    eax, eax
0x180019e45  jz      short loc_180019EC0
0x180019e47  movss   xmm0, dword ptr [rdi+10h]
0x180019e4c  cvtps2pd xmm0, xmm0; X
0x180019e4f  call    cs:__imp__finite
0x180019e55  test    eax, eax
0x180019e57  jz      short loc_180019EC0
0x180019e59  comiss  xmm8, dword ptr [rdi+10h]
0x180019e5e  ja      short loc_180019EC0
0x180019e60  mov     ecx, 30h ; '0'; Size
0x180019e65  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019e6a  movaps  xmm3, xmm7; float
0x180019e6d  mov     [rbp+arg_0], rax
0x180019e71  movaps  xmm2, xmm6; float
0x180019e74  mov     rdx, rdi; struct ParameterizedCurve *
0x180019e77  mov     rcx, rax; this
0x180019e7a  call    ??0ParameterizedCalibrationCurve@@AEAA@PEAUParameterizedCurve@@MM@Z; ParameterizedCalibrationCurve::ParameterizedCalibrationCurve(ParameterizedCurve *,float,float)
0x180019e7f  mov     [rbp+arg_0], rax
0x180019e83  test    rax, rax
0x180019e86  jnz     short loc_180019E8F
0x180019e88  mov     ebx, 8007000Eh
0x180019e8d  jmp     short loc_180019EC5
0x180019e8f  lea     rcx, [rdi+18h]; struct ParameterizedCurve *
0x180019e93  movaps  xmm2, xmm7; float
0x180019e96  lea     r9, [rbp+var_48]; struct ICalibrationCurve **
0x180019e9a  movaps  xmm1, xmm6; float
0x180019e9d  call    ?Create@ParameterizedCalibrationCurve@@SAJPEAUParameterizedCurve@@MMPEAPEAVICalibrationCurve@@@Z; ParameterizedCalibrationCurve::Create(ParameterizedCurve *,float,float,ICalibrationCurve * *)
0x180019ea2  mov     ebx, eax
0x180019ea4  test    eax, eax
0x180019ea6  js      short loc_180019EC5
0x180019ea8  lea     rcx, [rdi+30h]; struct ParameterizedCurve *
0x180019eac  movaps  xmm2, xmm7; float
0x180019eaf  lea     r9, [rbp+var_40]; struct ICalibrationCurve **
0x180019eb3  movaps  xmm1, xmm6; float
0x180019eb6  call    ?Create@ParameterizedCalibrationCurve@@SAJPEAUParameterizedCurve@@MMPEAPEAVICalibrationCurve@@@Z; ParameterizedCalibrationCurve::Create(ParameterizedCurve *,float,float,ICalibrationCurve * *)
0x180019ebb  jmp     loc_180019D51
0x180019ec0  mov     ebx, 80070057h
0x180019ec5  mov     rcx, [rbp+arg_0]; void *
0x180019ec9  mov     edi, 8
0x180019ece  mov     edx, edi; unsigned __int64
0x180019ed0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180019ed5  mov     rcx, [rbp+var_48]; void *
0x180019ed9  mov     edx, edi; unsigned __int64
0x180019edb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180019ee0  mov     rcx, [rbp+var_40]; void *
0x180019ee4  mov     edx, edi; unsigned __int64
0x180019ee6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180019eeb  movaps  xmm6, [rsp+68h+var_18]
0x180019ef0  mov     eax, ebx
0x180019ef2  movaps  xmm7, [rsp+68h+var_28]
0x180019ef7  movaps  xmm8, [rsp+68h+var_38]
0x180019efd  add     rsp, 68h
0x180019f01  pop     rdi
0x180019f02  pop     rsi
0x180019f03  pop     rbx
0x180019f04  pop     rbp
0x180019f05  retn
```
