# ConvertPenToGdi::ConvertPenToGdi(HDC__ *,DpPen const *,GpMatrix const *,float,ulong &,tagLOGBRUSH *,int)

- ea: `0x180029a94`
- end: `0x180029df7`
- name: `??0ConvertPenToGdi@@QEAA@PEAUHDC__@@PEBUDpPen@@PEBVGpMatrix@@MAEAKPEAUtagLOGBRUSH@@H@Z`
- size: `867`
- prototype: `ConvertPenToGdi *(ConvertPenToGdi *__hidden this, HDC, const struct DpPen *, const struct GpMatrix *, float, unsigned int *, struct tagLOGBRUSH *, int)`
- caller_count: `3`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x180029070`
- `0x1800e6300`
- `0x180138be8`

## callees

- `0x180027ce8`
- `0x180029a94`
- `0x1800b34f4`
- `0x1800c3074`
- `0x1800e0a44`
- `0x1800e9380`
- `0x1800ea080`
- `0x1800ea0c8`

## import_xrefs

- `GDI32!SetMiterLimit` at `0x180029d1e`
- `GDI32!SetMiterLimit` at `0x180029d1e`
- `GDI32!ExtCreatePen` at `0x180029d7b`
- `GDI32!ExtCreatePen` at `0x180029dab`
- `GDI32!ExtCreatePen` at `0x180029d7b`
- `GDI32!ExtCreatePen` at `0x180029dab`

## pseudocode

```c
ConvertPenToGdi *__fastcall ConvertPenToGdi::ConvertPenToGdi(
        ConvertPenToGdi *this,
        HDC a2,
        const struct DpPen *a3,
        const struct GpMatrix *a4,
        float a5,
        unsigned int *a6,
        struct tagLOGBRUSH *a7,
        int a8)
{
  int v10; // r12d
  bool v11; // cc
  int v12; // ebp
  int v13; // ebx
  __int64 v14; // rdx
  float v15; // xmm0_4
  double DeviceWidth; // xmm0_8
  float v17; // xmm0_4
  __m128 v18; // xmm1
  signed int v19; // r15d
  float v20; // xmm0_4
  __m128 v21; // xmm1
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  int v27; // eax
  int v28; // ecx
  int v29; // ebp
  int v30; // ebp
  float v32; // [rsp+30h] [rbp-98h] BYREF
  float v33; // [rsp+34h] [rbp-94h]
  HDC hdc; // [rsp+38h] [rbp-90h]
  _DWORD v35[4]; // [rsp+40h] [rbp-88h] BYREF
  LOGBRUSH plbrush; // [rsp+50h] [rbp-78h] BYREF

  *((_QWORD *)this + 1) = 0;
  *((_DWORD *)this + 4) = 0;
  v10 = 0x10000;
  *(_DWORD *)this = 1279869254;
  *((_DWORD *)this + 6) = -2;
  *((_DWORD *)this + 7) = -2;
  *((_QWORD *)this + 4) = a2;
  v11 = *((_DWORD *)a3 + 28) <= 0;
  v12 = *((_DWORD *)a3 + 5);
  hdc = a2;
  if ( (!v11 || *((_DWORD *)a3 + 20)) && (*(_BYTE *)a6 & 1) == 0 )
    return this;
  v13 = 2;
  v14 = *((unsigned int *)a3 + 2);
  v15 = (float)a8 * *((float *)a3 + 1);
  if ( (_DWORD)v14 )
  {
    DeviceWidth = GetDeviceWidth(4294967294LL, v14);
    v17 = *(float *)&DeviceWidth + 0.5;
    if ( Feature_GdiPlusOptimizations_Misc_IsEnabled )
    {
      v18 = 0;
      v18.m128_f32[0] = v17;
      v19 = (int)_mm_round_ss(v18, v18, 9).m128_f32[0];
    }
    else
    {
      v19 = (int)floor(v17);
    }
    if ( v19 <= 1 )
    {
      v19 = 1;
LABEL_18:
      if ( (*a6 & 8) != 0 )
      {
        v12 = 2;
      }
      else
      {
        v10 = 0;
        *a6 |= 0x20u;
      }
    }
  }
  else
  {
    if ( *((_DWORD *)a4 + 10) )
    {
      v33 = 0.0;
      v32 = v15;
      GpMatrix::VectorTransform(a4, (struct PointF *)&v32, 1);
      v15 = sqrt((v33 - 0.0) * (v33 - 0.0) + (v32 - 0.0) * (v32 - 0.0));
    }
    v20 = v15 + 0.5;
    if ( Feature_GdiPlusOptimizations_Misc_IsEnabled )
    {
      v21 = 0;
      v21.m128_f32[0] = v20;
      v19 = (int)_mm_round_ss(v21, v21, 9).m128_f32[0];
    }
    else
    {
      v19 = (int)floor(v20);
    }
    if ( v19 <= 1 )
    {
      v19 = 1;
      if ( *((_DWORD *)a3 + 3) != 255 && *((_DWORD *)a3 + 4) != 255 )
        goto LABEL_18;
    }
  }
  v22 = *((_DWORD *)a3 + 22);
  if ( !v22 )
  {
LABEL_27:
    v13 = 0;
    goto LABEL_28;
  }
  v23 = v22 - 1;
  if ( v23 )
  {
    v24 = v23 - 1;
    if ( !v24 )
      goto LABEL_28;
    v25 = v24 - 1;
    if ( v25 )
    {
      if ( v25 != 1 )
      {
        if ( (*(_BYTE *)a6 & 1) == 0 )
          return this;
        goto LABEL_27;
      }
      v13 = 4;
    }
    else
    {
      v13 = 3;
    }
  }
  else
  {
    v13 = 1;
  }
LABEL_28:
  if ( v10 != 0x10000 )
    goto LABEL_55;
  if ( (*a6 & 2) != 0 )
  {
    if ( v13 && (*a6 & 2) != 0 )
      return this;
  }
  else if ( v13 )
  {
    if ( (*(_BYTE *)a6 & 1) == 0 )
      return this;
    v13 = 0;
  }
  v26 = *((_DWORD *)a3 + 3);
  v27 = v26;
  if ( v13 )
    v27 = *((_DWORD *)a3 + 23);
  if ( v26 == *((_DWORD *)a3 + 4) && *((_DWORD *)a3 + 4) == v27 && v27 == v26 || (*(_BYTE *)a6 & 1) != 0 )
  {
    if ( v26 )
    {
      v28 = v26 - 1;
      if ( !v28 )
      {
        v13 |= 0x100u;
        goto LABEL_49;
      }
      if ( v28 == 1 )
      {
LABEL_49:
        if ( !v12 )
          goto LABEL_54;
        v29 = v12 - 1;
        if ( !v29 )
        {
          v13 |= 0x1000u;
LABEL_55:
          if ( a7 )
          {
            *((_QWORD *)this + 1) = ExtCreatePen(v10 | (unsigned int)v13, v19, a7, 0, 0);
          }
          else
          {
            ConvertBrushToGdi::ConvertBrushToGdi((ConvertBrushToGdi *)v35, *((const struct DpBrush **)a3 + 4), *a6);
            if ( v35[0] != 1198932785 )
            {
              ConvertBrushToGdi::~ConvertBrushToGdi((ConvertBrushToGdi *)v35);
              return this;
            }
            *((_QWORD *)this + 1) = ExtCreatePen(v10 | (unsigned int)v13, v19, &plbrush, 0, 0);
            ConvertBrushToGdi::~ConvertBrushToGdi((ConvertBrushToGdi *)v35);
          }
          *(_DWORD *)this = *((_QWORD *)this + 1) != 0 ? 1198932785 : 1279869254;
          return this;
        }
        v30 = v29 - 1;
        if ( !v30 )
          goto LABEL_55;
        if ( v30 == 1 || (*(_BYTE *)a6 & 1) != 0 )
        {
LABEL_54:
          v13 |= 0x2000u;
          *((_DWORD *)this + 4) = SetMiterLimit(hdc, *((FLOAT *)a3 + 6), (PFLOAT)this + 5);
          goto LABEL_55;
        }
        return this;
      }
      if ( (*(_BYTE *)a6 & 1) == 0 )
        return this;
    }
    v13 |= 0x200u;
    goto LABEL_49;
  }
  return this;
}

```

## disassembly

```asm
0x180029a94  push    rbx
0x180029a96  push    rbp
0x180029a97  push    rsi
0x180029a98  push    rdi
0x180029a99  push    r12
0x180029a9b  push    r13
0x180029a9d  push    r14
0x180029a9f  push    r15
0x180029aa1  sub     rsp, 88h
0x180029aa8  mov     rax, cs:__security_cookie
0x180029aaf  xor     rax, rsp
0x180029ab2  mov     [rsp+0C8h+var_58], rax
0x180029ab7  and     qword ptr [rcx+8], 0
0x180029abc  mov     rsi, rcx
0x180029abf  and     dword ptr [rcx+10h], 0
0x180029ac3  mov     rdi, r8
0x180029ac6  mov     r14, [rsp+0C8h+arg_28]
0x180029ace  mov     r12d, 10000h
0x180029ad4  mov     r13, [rsp+0C8h+arg_30]
0x180029adc  mov     dword ptr [rcx], 4C494146h
0x180029ae2  mov     ecx, 0FFFFFFFEh
0x180029ae7  mov     [rsi+18h], ecx
0x180029aea  mov     [rsi+1Ch], ecx
0x180029aed  mov     [rsi+20h], rdx
0x180029af1  cmp     dword ptr [r8+70h], 0
0x180029af6  mov     ebp, [r8+14h]
0x180029afa  mov     [rsp+0C8h+hdc], rdx
0x180029aff  jg      short loc_180029B08
0x180029b01  cmp     dword ptr [r8+50h], 0
0x180029b06  jz      short loc_180029B12
0x180029b08  test    byte ptr [r14], 1
0x180029b0c  jz      loc_180029DD2
0x180029b12  movd    xmm0, [rsp+0C8h+arg_38]
0x180029b1b  mov     ebx, 2
0x180029b20  mov     edx, [r8+8]
0x180029b24  cvtdq2ps xmm0, xmm0
0x180029b27  mulss   xmm0, dword ptr [r8+4]
0x180029b2d  test    edx, edx
0x180029b2f  jz      short loc_180029B87
0x180029b31  movss   xmm2, [rsp+0C8h+arg_20]
0x180029b3a  call    ?GetDeviceWidth@@YAMMW4Unit@@M@Z; GetDeviceWidth(float,Unit,float)
0x180029b3f  cmp     cs:?Feature_GdiPlusOptimizations_Misc_IsEnabled@@3_NA, 0; bool Feature_GdiPlusOptimizations_Misc_IsEnabled
0x180029b46  addss   xmm0, cs:__real@3f000000
0x180029b4e  jz      short loc_180029B64
0x180029b50  xorps   xmm1, xmm1
0x180029b53  movss   xmm1, xmm0
0x180029b57  roundss xmm1, xmm1, 9
0x180029b5d  cvttss2si r15d, xmm1
0x180029b62  jmp     short loc_180029B72
0x180029b64  cvtss2sd xmm0, xmm0; X
0x180029b68  call    floor
0x180029b6d  cvttsd2si r15d, xmm0
0x180029b72  cmp     r15d, 1
0x180029b76  jg      loc_180029C40
0x180029b7c  mov     r15d, 1
0x180029b82  jmp     loc_180029C2C
0x180029b87  cmp     dword ptr [r9+28h], 0
0x180029b8c  jz      short loc_180029BDE
0x180029b8e  and     [rsp+0C8h+var_94], 0
0x180029b93  lea     rdx, [rsp+0C8h+var_98]; struct PointF *
0x180029b98  mov     r8d, 1; int
0x180029b9e  movss   [rsp+0C8h+var_98], xmm0
0x180029ba4  mov     rcx, r9; this
0x180029ba7  call    ?VectorTransform@GpMatrix@@QEBAXPEAVPointF@@H@Z; GpMatrix::VectorTransform(PointF *,int)
0x180029bac  movss   xmm5, [rsp+0C8h+var_98]
0x180029bb2  xorps   xmm4, xmm4
0x180029bb5  movss   xmm0, [rsp+0C8h+var_94]
0x180029bbb  cvtps2pd xmm0, xmm0
0x180029bbe  cvtps2pd xmm5, xmm5
0x180029bc1  subsd   xmm0, xmm4
0x180029bc5  subsd   xmm5, xmm4
0x180029bc9  mulsd   xmm0, xmm0
0x180029bcd  mulsd   xmm5, xmm5
0x180029bd1  addsd   xmm0, xmm5; X
0x180029bd5  call    sqrt
0x180029bda  cvtsd2ss xmm0, xmm0
0x180029bde  cmp     cs:?Feature_GdiPlusOptimizations_Misc_IsEnabled@@3_NA, 0; bool Feature_GdiPlusOptimizations_Misc_IsEnabled
0x180029be5  addss   xmm0, cs:__real@3f000000
0x180029bed  jz      short loc_180029C03
0x180029bef  xorps   xmm1, xmm1
0x180029bf2  movss   xmm1, xmm0
0x180029bf6  roundss xmm1, xmm1, 9
0x180029bfc  cvttss2si r15d, xmm1
0x180029c01  jmp     short loc_180029C11
0x180029c03  cvtss2sd xmm0, xmm0; X
0x180029c07  call    floor
0x180029c0c  cvttsd2si r15d, xmm0
0x180029c11  cmp     r15d, 1
0x180029c15  jg      short loc_180029C40
0x180029c17  mov     eax, 0FFh
0x180029c1c  mov     r15d, 1
0x180029c22  cmp     [rdi+0Ch], eax
0x180029c25  jz      short loc_180029C40
0x180029c27  cmp     [rdi+10h], eax
0x180029c2a  jz      short loc_180029C40
0x180029c2c  mov     eax, [r14]
0x180029c2f  test    al, 8
0x180029c31  jnz     short loc_180029C3E
0x180029c33  xor     r12d, r12d
0x180029c36  or      eax, 20h
0x180029c39  mov     [r14], eax
0x180029c3c  jmp     short loc_180029C40
0x180029c3e  mov     ebp, ebx
0x180029c40  mov     ecx, [rdi+58h]
0x180029c43  test    ecx, ecx
0x180029c45  jz      short loc_180029C65
0x180029c47  sub     ecx, 1
0x180029c4a  jz      short loc_180029C9C
0x180029c4c  sub     ecx, 1
0x180029c4f  jz      short loc_180029C67
0x180029c51  sub     ecx, 1
0x180029c54  jz      short loc_180029C95
0x180029c56  cmp     ecx, 1
0x180029c59  jz      short loc_180029C8E
0x180029c5b  test    byte ptr [r14], 1
0x180029c5f  jz      loc_180029DD2
0x180029c65  xor     ebx, ebx
0x180029c67  cmp     r12d, 10000h
0x180029c6e  jnz     loc_180029D2D
0x180029c74  mov     eax, [r14]
0x180029c77  and     eax, 2
0x180029c7a  jnz     short loc_180029CA3
0x180029c7c  test    ebx, ebx
0x180029c7e  jz      short loc_180029CAF
0x180029c80  test    byte ptr [r14], 1
0x180029c84  jz      loc_180029DD2
0x180029c8a  xor     ebx, ebx
0x180029c8c  jmp     short loc_180029CAF
0x180029c8e  mov     ebx, 4
0x180029c93  jmp     short loc_180029C67
0x180029c95  mov     ebx, 3
0x180029c9a  jmp     short loc_180029C67
0x180029c9c  mov     ebx, 1
0x180029ca1  jmp     short loc_180029C67
0x180029ca3  test    ebx, ebx
0x180029ca5  jz      short loc_180029CAF
0x180029ca7  test    eax, eax
0x180029ca9  jnz     loc_180029DD2
0x180029caf  mov     ecx, [rdi+0Ch]
0x180029cb2  mov     eax, ecx
0x180029cb4  test    ebx, ebx
0x180029cb6  jz      short loc_180029CBB
0x180029cb8  mov     eax, [rdi+5Ch]
0x180029cbb  cmp     ecx, [rdi+10h]
0x180029cbe  jnz     short loc_180029CC9
0x180029cc0  cmp     [rdi+10h], eax
0x180029cc3  jnz     short loc_180029CC9
0x180029cc5  cmp     eax, ecx
0x180029cc7  jz      short loc_180029CD3
0x180029cc9  test    byte ptr [r14], 1
0x180029ccd  jz      loc_180029DD2
0x180029cd3  test    ecx, ecx
0x180029cd5  jz      short loc_180029CEB
0x180029cd7  sub     ecx, 1
0x180029cda  jz      short loc_180029D59
0x180029cdc  cmp     ecx, 1
0x180029cdf  jz      short loc_180029CEF
0x180029ce1  test    byte ptr [r14], 1
0x180029ce5  jz      loc_180029DD2
0x180029ceb  bts     ebx, 9
0x180029cef  test    ebp, ebp
0x180029cf1  jz      short loc_180029D0C
0x180029cf3  sub     ebp, 1
0x180029cf6  jz      short loc_180029D5F
0x180029cf8  sub     ebp, 1
0x180029cfb  jz      short loc_180029D2D
0x180029cfd  cmp     ebp, 1
0x180029d00  jz      short loc_180029D0C
0x180029d02  test    byte ptr [r14], 1
0x180029d06  jz      loc_180029DD2
0x180029d0c  movss   xmm1, dword ptr [rdi+18h]; limit
0x180029d11  lea     r8, [rsi+14h]; old
0x180029d15  mov     rcx, [rsp+0C8h+hdc]; hdc
0x180029d1a  bts     ebx, 0Dh
0x180029d1e  call    cs:__imp_SetMiterLimit
0x180029d25  nop     dword ptr [rax+rax+00h]
0x180029d2a  mov     [rsi+10h], eax
0x180029d2d  test    r13, r13
0x180029d30  jnz     short loc_180029D97
0x180029d32  mov     r8d, [r14]; unsigned int
0x180029d35  lea     rcx, [rsp+0C8h+var_88]; this
0x180029d3a  mov     rdx, [rdi+20h]; struct DpBrush *
0x180029d3e  call    ??0ConvertBrushToGdi@@QEAA@PEBUDpBrush@@K@Z; ConvertBrushToGdi::ConvertBrushToGdi(DpBrush const *,ulong)
0x180029d43  cmp     [rsp+0C8h+var_88], 47764331h
0x180029d4b  jz      short loc_180029D65
0x180029d4d  lea     rcx, [rsp+0C8h+var_88]; this
0x180029d52  call    ??1ConvertBrushToGdi@@QEAA@XZ; ConvertBrushToGdi::~ConvertBrushToGdi(void)
0x180029d57  jmp     short loc_180029DD2
0x180029d59  bts     ebx, 8
0x180029d5d  jmp     short loc_180029CEF
0x180029d5f  bts     ebx, 0Ch
0x180029d63  jmp     short loc_180029D2D
0x180029d65  and     [rsp+0C8h+var_A8], 0
0x180029d6b  lea     r8, [rsp+0C8h+plbrush]; plbrush
0x180029d70  or      ebx, r12d
0x180029d73  xor     r9d, r9d; cStyle
0x180029d76  mov     ecx, ebx; iPenStyle
0x180029d78  mov     edx, r15d; cWidth
0x180029d7b  call    cs:__imp_ExtCreatePen
0x180029d82  nop     dword ptr [rax+rax+00h]
0x180029d87  lea     rcx, [rsp+0C8h+var_88]; this
0x180029d8c  mov     [rsi+8], rax
0x180029d90  call    ??1ConvertBrushToGdi@@QEAA@XZ; ConvertBrushToGdi::~ConvertBrushToGdi(void)
0x180029d95  jmp     short loc_180029DBB
0x180029d97  and     [rsp+0C8h+var_A8], 0
0x180029d9d  or      ebx, r12d
0x180029da0  mov     ecx, ebx; iPenStyle
0x180029da2  xor     r9d, r9d; cStyle
0x180029da5  mov     r8, r13; plbrush
0x180029da8  mov     edx, r15d; cWidth
0x180029dab  call    cs:__imp_ExtCreatePen
0x180029db2  nop     dword ptr [rax+rax+00h]
0x180029db7  mov     [rsi+8], rax
0x180029dbb  mov     rcx, [rsi+8]
0x180029dbf  neg     rcx
0x180029dc2  sbb     edx, edx
0x180029dc4  and     edx, 0FB2D01EBh
0x180029dca  add     edx, 4C494146h
0x180029dd0  mov     [rsi], edx
0x180029dd2  mov     rax, rsi
0x180029dd5  mov     rcx, [rsp+0C8h+var_58]
0x180029dda  xor     rcx, rsp; StackCookie
0x180029ddd  call    __security_check_cookie
0x180029de2  add     rsp, 88h
0x180029de9  pop     r15
0x180029deb  pop     r14
0x180029ded  pop     r13
0x180029def  pop     r12
0x180029df1  pop     rdi
0x180029df2  pop     rsi
0x180029df3  pop     rbp
0x180029df4  pop     rbx
0x180029df5  retn
```
