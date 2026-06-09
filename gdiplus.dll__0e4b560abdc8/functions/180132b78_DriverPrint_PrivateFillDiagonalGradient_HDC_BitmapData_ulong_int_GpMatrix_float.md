# DriverPrint::PrivateFillDiagonalGradient(HDC__ *,BitmapData &,ulong,int,GpMatrix *,float)

- ea: `0x180132b78`
- end: `0x180132fed`
- name: `?PrivateFillDiagonalGradient@DriverPrint@@AEAA?AW4Status@@PEAUHDC__@@AEAVBitmapData@@KHPEAVGpMatrix@@M@Z`
- size: `1141`
- prototype: `__int64 __fastcall(DriverPrint *, HDC, __int64, int, int, GpMatrix *, float)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x1801331f0`

## callees

- `0x180029450`
- `0x180040ee0`
- `0x180048724`
- `0x18004bb6c`
- `0x1800d5f10`
- `0x1800dc7c8`
- `0x1800e4fc0`
- `0x1800e9380`
- `0x180132694`
- `0x180132b78`
- `0x18013a6b4`

## import_xrefs

- `GDI32!CreateSolidBrush` at `0x180132dd9`
- `GDI32!CreateSolidBrush` at `0x180132dd9`
- `GDI32!SetROP2` at `0x180132cb0`
- `GDI32!SetROP2` at `0x180132f9f`
- `GDI32!SetROP2` at `0x180132cb0`
- `GDI32!SetROP2` at `0x180132f9f`
- `GDI32!GetStockObject` at `0x180132c77`
- `GDI32!GetStockObject` at `0x180132c77`
- `GDI32!SelectObject` at `0x180132c89`
- `GDI32!SelectObject` at `0x180132f82`
- `GDI32!SelectObject` at `0x180132c89`
- `GDI32!SelectObject` at `0x180132f82`
- `GDI32!DeleteObject` at `0x180132f18`
- `GDI32!DeleteObject` at `0x180132f18`

## pseudocode

```c
__int64 __fastcall DriverPrint::PrivateFillDiagonalGradient(
        DriverPrint *a1,
        HDC a2,
        __int64 a3,
        int a4,
        int a5,
        GpMatrix *a6,
        float a7)
{
  unsigned __int8 *v7; // rdi
  unsigned int v8; // ebx
  int v11; // eax
  int v12; // r13d
  int v13; // r15d
  signed int v14; // esi
  HGDIOBJ StockObject; // rax
  unsigned __int8 *v16; // rdi
  float v17; // xmm8_4
  int v18; // r11d
  unsigned int i; // r12d
  int v20; // r9d
  unsigned int v21; // r10d
  unsigned __int8 v22; // r8
  unsigned __int8 v23; // dl
  int v24; // eax
  int v25; // edx
  int v26; // ecx
  int v27; // eax
  int v28; // ecx
  int v29; // ecx
  int v30; // eax
  int v31; // eax
  int v32; // eax
  __m128i v33; // xmm6
  int v34; // eax
  float v35; // xmm6_4
  float v36; // xmm7_4
  HBRUSH SolidBrush; // r13
  HBRUSH AlphaMaskBrush; // rax
  int v39; // eax
  int v41; // [rsp+48h] [rbp-C0h]
  unsigned int v42; // [rsp+4Ch] [rbp-BCh]
  int v43; // [rsp+50h] [rbp-B8h]
  int v44; // [rsp+54h] [rbp-B4h]
  int v45; // [rsp+58h] [rbp-B0h]
  int v46; // [rsp+5Ch] [rbp-ACh]
  unsigned int v47; // [rsp+60h] [rbp-A8h]
  int v48; // [rsp+64h] [rbp-A4h]
  int v49; // [rsp+68h] [rbp-A0h]
  int rop2; // [rsp+6Ch] [rbp-9Ch]
  HGDIOBJ h; // [rsp+90h] [rbp-78h]
  void **v55; // [rsp+98h] [rbp-70h] BYREF
  int v56; // [rsp+A0h] [rbp-68h]
  int v57; // [rsp+A4h] [rbp-64h]
  int v58; // [rsp+A8h] [rbp-60h]
  int v59; // [rsp+ACh] [rbp-5Ch]
  int v60; // [rsp+B0h] [rbp-58h]
  int v61; // [rsp+B4h] [rbp-54h]
  int v62; // [rsp+B8h] [rbp-50h]
  int v63; // [rsp+BCh] [rbp-4Ch]
  int v64; // [rsp+C0h] [rbp-48h]
  _DWORD v65[112]; // [rsp+C8h] [rbp-40h] BYREF
  _BYTE v66[368]; // [rsp+288h] [rbp+180h] BYREF
  _DWORD v67[8]; // [rsp+3F8h] [rbp+2F0h] BYREF
  _BYTE v68[80]; // [rsp+418h] [rbp+310h] BYREF
  _BYTE v69[16]; // [rsp+468h] [rbp+360h] BYREF

  v7 = *(unsigned __int8 **)(a3 + 16);
  v8 = 0;
  v57 = -1;
  v63 = 0;
  v62 = 0;
  v11 = v7[1];
  v12 = *v7;
  v13 = 1;
  v14 = v7[3];
  v60 = 0;
  v59 = 0;
  v45 = v11;
  v44 = v11;
  v48 = v7[2];
  v43 = v48;
  v55 = &GpMatrix::`vftable';
  v47 = 0;
  v41 = v12;
  v42 = v14;
  v61 = 1065353216;
  v58 = 1065353216;
  v64 = 0;
  v56 = 1952533809;
  `vector constructor iterator'(v67, 8u, 4u, (void *(*)(void *))PointF::PointF);
  `vector constructor iterator'(v68, 8u, 0xAu, (void *(*)(void *))PointF::PointF);
  StockObject = GetStockObject(8);
  rop2 = 13;
  h = SelectObject(a2, StockObject);
  if ( a4 != 15728673 )
    rop2 = SetROP2(a2, 7);
  v16 = v7 + 4;
  v17 = a7 + 4.0;
  v46 = 2;
  v18 = 0;
  v49 = 0;
  for ( i = 1; i <= *(_DWORD *)a3; ++i )
  {
    if ( i == *(_DWORD *)a3 )
    {
      v20 = v41;
      v18 = 2;
      v21 = v42;
      LOBYTE(v12) = v41;
      v22 = v43;
      v14 = v42;
      v23 = v44;
      v49 = 2;
LABEL_20:
      if ( v14 >= 2 )
      {
        v33 = _mm_cvtsi32_si128(v47 - v46);
        v34 = i + v46 + v18 - v47;
        v46 = 0;
        LODWORD(v35) = _mm_cvtepi32_ps(v33).m128_u32[0];
        v36 = (float)v34;
        SolidBrush = CreateSolidBrush(v22 | ((unsigned __int8)v12 << 16) | (v23 << 8));
        if ( SolidBrush )
        {
          *(float *)v67 = v35;
          *(float *)&v67[6] = v35;
          v67[1] = -1073741824;
          v67[3] = -1073741824;
          *(float *)&v67[2] = v35 + v36;
          *(float *)&v67[4] = v35 + v36;
          *(float *)&v67[5] = v17 - 2.0;
          *(float *)&v67[7] = v17 - 2.0;
          GpMatrix::Transform(a6, (struct PointF *)v67, 4);
          GpPath::GpPath(v66, v67, 4, v68, v69, 10, 0, 3);
          ConvertPathToGdi::ConvertPathToGdi(
            (ConvertPathToGdi *)v65,
            (const struct DpPath *)v66,
            (struct GpMatrix *)&v55,
            0x10u,
            0);
          if ( v65[0] == 1198932785 )
          {
            if ( a5 || v14 > 253 || (AlphaMaskBrush = DriverPrint::GetAlphaMaskBrush(a1, v14, 0)) == 0 )
              v39 = ConvertPathToGdi::Fill((ConvertPathToGdi *)v65, a2, SolidBrush);
            else
              v39 = ConvertPathToGdi::AlphaFill((ConvertPathToGdi *)v65, a2, SolidBrush, AlphaMaskBrush);
            v13 &= v39;
          }
          else
          {
            v13 = 0;
          }
          DeleteObject(SolidBrush);
          ConvertPathToGdi::~ConvertPathToGdi((ConvertPathToGdi *)v65);
          GpPath::~GpPath((GpPath *)v66);
        }
        else
        {
          v13 = 0;
        }
        v21 = v42;
        v20 = v41;
      }
      v12 = v20;
      v14 = v21;
      v18 = v49;
      v48 = v43;
      v45 = v44;
      v47 = i;
      continue;
    }
    v24 = v16[2];
    v20 = *v16;
    v25 = v16[1];
    v21 = v16[3];
    v16 += 4;
    v22 = v48;
    v26 = v24 - v48;
    v43 = v24;
    v27 = v48 - v24;
    v41 = v20;
    v44 = v25;
    if ( v26 > 0 )
      v27 = v26;
    v42 = v21;
    if ( v27 >= 1 )
    {
      v23 = v45;
      goto LABEL_20;
    }
    v28 = v25;
    v23 = v45;
    v29 = v28 - v45;
    v30 = -v29;
    if ( v29 > 0 )
      v30 = v29;
    if ( v30 < 1 )
    {
      v31 = v12 - v20;
      if ( v12 - v20 < 0 )
        v31 = v20 - v12;
      if ( v31 < 1 )
      {
        v32 = v14 - v21;
        if ( (int)(v14 - v21) < 0 )
          v32 = v21 - v14;
        if ( v32 < 1 )
          continue;
      }
    }
    goto LABEL_20;
  }
  SelectObject(a2, h);
  if ( a4 != 15728673 )
    SetROP2(a2, rop2);
  LOBYTE(v8) = v13 == 0;
  return v8;
}

```

## disassembly

```asm
0x180132b78  mov     rax, rsp
0x180132b7b  mov     [rax+20h], rbx
0x180132b7f  push    rbp
0x180132b80  push    rsi
0x180132b81  push    rdi
0x180132b82  push    r12
0x180132b84  push    r13
0x180132b86  push    r14
0x180132b88  push    r15
0x180132b8a  lea     rbp, [rax-3E8h]
0x180132b91  sub     rsp, 4B0h
0x180132b98  movaps  xmmword ptr [rax-48h], xmm6
0x180132b9c  movaps  xmmword ptr [rax-58h], xmm7
0x180132ba0  movaps  xmmword ptr [rax-68h], xmm8
0x180132ba5  mov     rax, cs:__security_cookie
0x180132bac  xor     rax, rsp
0x180132baf  mov     [rbp+3E0h+var_70], rax
0x180132bb6  mov     rdi, [r8+10h]
0x180132bba  xor     ebx, ebx
0x180132bbc  or      [rbp+3E0h+var_444], 0FFFFFFFFh
0x180132bc0  mov     r12d, r9d
0x180132bc3  and     [rbp+3E0h+var_42C], ebx
0x180132bc6  mov     r14, rdx
0x180132bc9  and     [rbp+3E0h+var_430], ebx
0x180132bcc  movzx   eax, byte ptr [rdi+1]
0x180132bd0  lea     edx, [rbx+8]; unsigned __int64
0x180132bd3  movzx   r13d, byte ptr [rdi]
0x180132bd7  lea     r15d, [rbx+1]
0x180132bdb  movzx   esi, byte ptr [rdi+3]
0x180132bdf  and     [rbp+3E0h+var_438], ebx
0x180132be2  and     [rbp+3E0h+var_43C], ebx
0x180132be5  mov     [rbp+3E0h+var_460], rcx
0x180132be9  mov     rcx, [rbp+3E0h+arg_28]
0x180132bf0  mov     [rsp+4E0h+var_468], rcx
0x180132bf5  movzx   ecx, byte ptr [rdi+2]
0x180132bf9  mov     [rsp+4E0h+var_490], eax
0x180132bfd  mov     [rsp+4E0h+var_494], eax
0x180132c01  lea     rax, ??_7GpMatrix@@6B@; const GpMatrix::`vftable'
0x180132c08  mov     dword ptr [rsp+4E0h+var_478], r9d
0x180132c0d  lea     r9, ??0PointF@@QEAA@XZ; void *(*)(void *)
0x180132c14  mov     [rsp+4E0h+var_470], r8
0x180132c19  lea     r8d, [rbx+4]; unsigned __int64
0x180132c1d  mov     [rsp+4E0h+var_484], ecx
0x180132c21  mov     [rsp+4E0h+var_498], ecx
0x180132c25  lea     rcx, [rbp+3E0h+var_F0]; void *
0x180132c2c  mov     [rbp+3E0h+var_450], rax
0x180132c30  mov     [rsp+4E0h+var_488], ebx
0x180132c34  mov     [rsp+4E0h+var_4A0], r13d
0x180132c39  mov     [rsp+4E0h+var_49C], esi
0x180132c3d  mov     [rbp+3E0h+var_434], 3F800000h
0x180132c44  mov     [rbp+3E0h+var_440], 3F800000h
0x180132c4b  mov     [rbp+3E0h+var_428], ebx
0x180132c4e  mov     [rbp+3E0h+var_448], 74614D31h
0x180132c55  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x180132c5a  lea     r9, ??0PointF@@QEAA@XZ; void *(*)(void *)
0x180132c61  lea     edx, [rbx+8]; unsigned __int64
0x180132c64  lea     r8d, [rbx+0Ah]; unsigned __int64
0x180132c68  lea     rcx, [rbp+3E0h+var_D0]; void *
0x180132c6f  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x180132c74  lea     ecx, [rbx+8]; i
0x180132c77  call    cs:__imp_GetStockObject
0x180132c7e  nop     dword ptr [rax+rax+00h]
0x180132c83  mov     rdx, rax; h
0x180132c86  mov     rcx, r14; hdc
0x180132c89  call    cs:__imp_SelectObject
0x180132c90  nop     dword ptr [rax+rax+00h]
0x180132c95  mov     [rsp+4E0h+rop2], 0Dh
0x180132c9d  mov     [rbp+3E0h+h], rax
0x180132ca1  cmp     r12d, 0F00021h
0x180132ca8  jz      short loc_180132CC0
0x180132caa  lea     edx, [rbx+7]; rop2
0x180132cad  mov     rcx, r14; hdc
0x180132cb0  call    cs:__imp_SetROP2
0x180132cb7  nop     dword ptr [rax+rax+00h]
0x180132cbc  mov     [rsp+4E0h+rop2], eax
0x180132cc0  movss   xmm8, [rbp+3E0h+arg_30]
0x180132cc9  add     rdi, 4
0x180132ccd  addss   xmm8, cs:__real@40800000
0x180132cd6  mov     [rsp+4E0h+var_48C], 2
0x180132cde  mov     r11d, ebx
0x180132ce1  mov     [rsp+4E0h+var_480], ebx
0x180132ce5  mov     r12d, r15d
0x180132ce8  jmp     loc_180132F6B
0x180132ced  jnz     short loc_180132D15
0x180132cef  mov     r9d, [rsp+4E0h+var_4A0]
0x180132cf4  mov     r11d, 2
0x180132cfa  mov     r10d, [rsp+4E0h+var_49C]
0x180132cff  mov     r13d, r9d
0x180132d02  mov     r8d, [rsp+4E0h+var_498]
0x180132d07  mov     esi, r10d
0x180132d0a  mov     edx, [rsp+4E0h+var_494]
0x180132d0e  mov     [rsp+4E0h+var_480], r11d
0x180132d13  jmp     short loc_180132D93
0x180132d15  movzx   eax, byte ptr [rdi+2]
0x180132d19  movzx   r9d, byte ptr [rdi]
0x180132d1d  mov     ecx, eax
0x180132d1f  movzx   edx, byte ptr [rdi+1]
0x180132d23  movzx   r10d, byte ptr [rdi+3]
0x180132d28  add     rdi, 4
0x180132d2c  mov     r8d, [rsp+4E0h+var_484]
0x180132d31  sub     ecx, r8d
0x180132d34  mov     [rsp+4E0h+var_498], eax
0x180132d38  mov     eax, ecx
0x180132d3a  neg     eax
0x180132d3c  mov     [rsp+4E0h+var_4A0], r9d
0x180132d41  mov     [rsp+4E0h+var_494], edx
0x180132d45  cmovs   eax, ecx
0x180132d48  mov     [rsp+4E0h+var_49C], r10d
0x180132d4d  cmp     eax, 1
0x180132d50  jge     short loc_180132D8F
0x180132d52  mov     ecx, edx
0x180132d54  mov     edx, [rsp+4E0h+var_490]
0x180132d58  sub     ecx, edx
0x180132d5a  mov     eax, ecx
0x180132d5c  neg     eax
0x180132d5e  cmovs   eax, ecx
0x180132d61  cmp     eax, 1
0x180132d64  jge     short loc_180132D93
0x180132d66  mov     ecx, r9d
0x180132d69  sub     ecx, r13d
0x180132d6c  mov     eax, ecx
0x180132d6e  neg     eax
0x180132d70  cmovs   eax, ecx
0x180132d73  cmp     eax, 1
0x180132d76  jge     short loc_180132D93
0x180132d78  mov     ecx, r10d
0x180132d7b  sub     ecx, esi
0x180132d7d  mov     eax, ecx
0x180132d7f  neg     eax
0x180132d81  cmovs   eax, ecx
0x180132d84  cmp     eax, 1
0x180132d87  jl      loc_180132F68
0x180132d8d  jmp     short loc_180132D93
0x180132d8f  mov     edx, [rsp+4E0h+var_490]
0x180132d93  cmp     esi, 2
0x180132d96  jl      loc_180132F48
0x180132d9c  mov     eax, [rsp+4E0h+var_488]
0x180132da0  sub     eax, [rsp+4E0h+var_48C]
0x180132da4  movzx   ecx, dl
0x180132da7  shl     ecx, 8
0x180132daa  movd    xmm6, eax
0x180132dae  mov     eax, r11d
0x180132db1  sub     eax, [rsp+4E0h+var_488]
0x180132db5  add     eax, [rsp+4E0h+var_48C]
0x180132db9  add     eax, r12d
0x180132dbc  mov     [rsp+4E0h+var_48C], ebx
0x180132dc0  cvtdq2ps xmm6, xmm6
0x180132dc3  movd    xmm7, eax
0x180132dc7  movzx   eax, r13b
0x180132dcb  shl     eax, 10h
0x180132dce  or      ecx, eax
0x180132dd0  movzx   eax, r8b
0x180132dd4  or      ecx, eax; color
0x180132dd6  cvtdq2ps xmm7, xmm7
0x180132dd9  call    cs:__imp_CreateSolidBrush
0x180132de0  nop     dword ptr [rax+rax+00h]
0x180132de5  mov     r13, rax
0x180132de8  test    rax, rax
0x180132deb  jz      loc_180132F3B
0x180132df1  mov     rcx, [rsp+4E0h+var_468]; this
0x180132df6  lea     rdx, [rbp+3E0h+var_F0]; struct PointF *
0x180132dfd  movaps  xmm0, xmm6
0x180132e00  movss   [rbp+3E0h+var_F0], xmm6
0x180132e08  addss   xmm0, xmm7
0x180132e0c  movss   [rbp+3E0h+var_D8], xmm6
0x180132e14  movaps  xmm1, xmm8
0x180132e18  mov     [rbp+3E0h+var_EC], 0C0000000h
0x180132e22  subss   xmm1, cs:__real@40000000
0x180132e2a  mov     r8d, 4; int
0x180132e30  mov     [rbp+3E0h+var_E4], 0C0000000h
0x180132e3a  movss   [rbp+3E0h+var_E8], xmm0
0x180132e42  movss   [rbp+3E0h+var_E0], xmm0
0x180132e4a  movss   [rbp+3E0h+var_DC], xmm1
0x180132e52  movss   [rbp+3E0h+var_D4], xmm1
0x180132e5a  call    ?Transform@GpMatrix@@QEBAXPEAVPointF@@H@Z; GpMatrix::Transform(PointF *,int)
0x180132e5f  mov     [rsp+4E0h+var_4A8], 3
0x180132e67  lea     rax, [rbp+3E0h+var_80]
0x180132e6e  mov     [rsp+4E0h+var_4B0], ebx
0x180132e72  lea     r9, [rbp+3E0h+var_D0]
0x180132e79  mov     [rsp+4E0h+var_4B8], 0Ah
0x180132e81  lea     rdx, [rbp+3E0h+var_F0]
0x180132e88  mov     r8d, 4
0x180132e8e  mov     [rsp+4E0h+var_4C0], rax
0x180132e93  lea     rcx, [rbp+3E0h+var_260]
0x180132e9a  call    ??0GpPath@@QEAA@PEBVPointF@@HPEAV1@PEAEHW4FillMode@@W4DpPathFlags@DpPath@@@Z; GpPath::GpPath(PointF const *,int,PointF *,uchar *,int,FillMode,DpPath::DpPathFlags)
0x180132e9f  mov     r9d, 10h; unsigned int
0x180132ea5  mov     [rsp+4E0h+var_4C0], rbx; struct GpRuntime::GpRect *
0x180132eaa  lea     r8, [rbp+3E0h+var_450]; struct GpMatrix *
0x180132eae  lea     rdx, [rbp+3E0h+var_260]; struct DpPath *
0x180132eb5  lea     rcx, [rbp+3E0h+var_420]; this
0x180132eb9  call    ??0ConvertPathToGdi@@QEAA@PEBVDpPath@@PEAVGpMatrix@@KPEBVGpRect@GpRuntime@@@Z; ConvertPathToGdi::ConvertPathToGdi(DpPath const *,GpMatrix *,ulong,GpRuntime::GpRect const *)
0x180132ebe  cmp     [rbp+3E0h+var_420], 47764331h
0x180132ec5  jnz     short loc_180132F12
0x180132ec7  cmp     [rbp+3E0h+arg_20], ebx
0x180132ecd  jnz     short loc_180132EFE
0x180132ecf  cmp     esi, 0FDh
0x180132ed5  jg      short loc_180132EFE
0x180132ed7  mov     rcx, [rbp+3E0h+var_460]; this
0x180132edb  xor     r8d, r8d; int
0x180132ede  mov     edx, esi; unsigned int
0x180132ee0  call    ?GetAlphaMaskBrush@DriverPrint@@IEBAPEAUHBRUSH__@@IH@Z; DriverPrint::GetAlphaMaskBrush(uint,int)
0x180132ee5  test    rax, rax
0x180132ee8  jz      short loc_180132EFE
0x180132eea  mov     r9, rax; HBRUSH
0x180132eed  lea     rcx, [rbp+3E0h+var_420]; this
0x180132ef1  mov     r8, r13; h
0x180132ef4  mov     rdx, r14; HDC
0x180132ef7  call    ?AlphaFill@ConvertPathToGdi@@QEAAHPEAUHDC__@@PEAUHBRUSH__@@1@Z; ConvertPathToGdi::AlphaFill(HDC__ *,HBRUSH__ *,HBRUSH__ *)
0x180132efc  jmp     short loc_180132F0D
0x180132efe  mov     r8, r13; h
0x180132f01  lea     rcx, [rbp+3E0h+var_420]; this
0x180132f05  mov     rdx, r14; HDC
0x180132f08  call    ?Fill@ConvertPathToGdi@@QEAAHPEAUHDC__@@PEAUHBRUSH__@@@Z; ConvertPathToGdi::Fill(HDC__ *,HBRUSH__ *)
0x180132f0d  and     r15d, eax
0x180132f10  jmp     short loc_180132F15
0x180132f12  mov     r15d, ebx
0x180132f15  mov     rcx, r13; ho
0x180132f18  call    cs:__imp_DeleteObject
0x180132f1f  nop     dword ptr [rax+rax+00h]
0x180132f24  lea     rcx, [rbp+3E0h+var_420]; this
0x180132f28  call    ??1ConvertPathToGdi@@QEAA@XZ; ConvertPathToGdi::~ConvertPathToGdi(void)
0x180132f2d  lea     rcx, [rbp+3E0h+var_260]; this
0x180132f34  call    ??1GpPath@@UEAA@XZ; GpPath::~GpPath(void)
0x180132f39  jmp     short loc_180132F3E
0x180132f3b  mov     r15d, ebx
0x180132f3e  mov     r10d, [rsp+4E0h+var_49C]
0x180132f43  mov     r9d, [rsp+4E0h+var_4A0]
0x180132f48  mov     ecx, [rsp+4E0h+var_498]
0x180132f4c  mov     r13d, r9d
0x180132f4f  mov     eax, [rsp+4E0h+var_494]
0x180132f53  mov     esi, r10d
0x180132f56  mov     r11d, [rsp+4E0h+var_480]
0x180132f5b  mov     [rsp+4E0h+var_484], ecx
0x180132f5f  mov     [rsp+4E0h+var_490], eax
0x180132f63  mov     [rsp+4E0h+var_488], r12d
0x180132f68  inc     r12d
0x180132f6b  mov     rax, [rsp+4E0h+var_470]
0x180132f70  mov     eax, [rax]
0x180132f72  cmp     r12d, eax
0x180132f75  jbe     loc_180132CED
0x180132f7b  mov     rdx, [rbp+3E0h+h]; h
0x180132f7f  mov     rcx, r14; hdc
0x180132f82  call    cs:__imp_SelectObject
0x180132f89  nop     dword ptr [rax+rax+00h]
0x180132f8e  cmp     dword ptr [rsp+4E0h+var_478], 0F00021h
0x180132f96  jz      short loc_180132FAB
0x180132f98  mov     edx, [rsp+4E0h+rop2]; rop2
0x180132f9c  mov     rcx, r14; hdc
0x180132f9f  call    cs:__imp_SetROP2
0x180132fa6  nop     dword ptr [rax+rax+00h]
0x180132fab  test    r15d, r15d
0x180132fae  setz    bl
0x180132fb1  mov     eax, ebx
0x180132fb3  mov     rcx, [rbp+3E0h+var_70]
0x180132fba  xor     rcx, rsp; StackCookie
0x180132fbd  call    __security_check_cookie
0x180132fc2  lea     r11, [rsp+4E0h+var_30]
0x180132fca  mov     rbx, [r11+58h]
0x180132fce  movaps  xmm6, xmmword ptr [r11-10h]
0x180132fd3  movaps  xmm7, xmmword ptr [r11-20h]
0x180132fd8  movaps  xmm8, xmmword ptr [r11-30h]
0x180132fdd  mov     rsp, r11
0x180132fe0  pop     r15
0x180132fe2  pop     r14
0x180132fe4  pop     r13
0x180132fe6  pop     r12
0x180132fe8  pop     rdi
0x180132fe9  pop     rsi
0x180132fea  pop     rbp
0x180132feb  retn
```
