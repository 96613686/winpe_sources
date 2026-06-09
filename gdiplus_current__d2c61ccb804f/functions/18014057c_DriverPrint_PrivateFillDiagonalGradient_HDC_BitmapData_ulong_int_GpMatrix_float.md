# DriverPrint::PrivateFillDiagonalGradient(HDC__ *,BitmapData &,ulong,int,GpMatrix *,float)

- ea: `0x18014057c`
- end: `0x180140a03`
- name: `?PrivateFillDiagonalGradient@DriverPrint@@AEAA?AW4Status@@PEAUHDC__@@AEAVBitmapData@@KHPEAVGpMatrix@@M@Z`
- size: `1159`
- prototype: `enum Status __high(HDC, struct BitmapData *, unsigned int, int, struct GpMatrix *, float)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x1800fafbc`

## callees

- `0x1800058d0`
- `0x18003d7d0`
- `0x180052140`
- `0x180054c7c`
- `0x180080604`
- `0x1800e83e8`
- `0x1800e869c`
- `0x180105d40`
- `0x180140118`
- `0x18014057c`
- `0x180144294`

## import_xrefs

- `GDI32!CreateSolidBrush` at `0x1801407e8`
- `GDI32!CreateSolidBrush` at `0x1801407e8`
- `GDI32!SetROP2` at `0x180140698`
- `GDI32!SetROP2` at `0x1801409bf`
- `GDI32!SetROP2` at `0x180140698`
- `GDI32!SetROP2` at `0x1801409bf`
- `GDI32!GetStockObject` at `0x18014065d`
- `GDI32!GetStockObject` at `0x18014065d`
- `GDI32!SelectObject` at `0x18014066f`
- `GDI32!SelectObject` at `0x1801409a2`
- `GDI32!SelectObject` at `0x18014066f`
- `GDI32!SelectObject` at `0x1801409a2`
- `GDI32!DeleteObject` at `0x18014093b`
- `GDI32!DeleteObject` at `0x18014093b`

## pseudocode

```c
_BOOL8 __fastcall DriverPrint::PrivateFillDiagonalGradient(
        DriverPrint *a1,
        HDC a2,
        __int64 a3,
        int a4,
        int a5,
        GpMatrix *a6,
        float a7)
{
  unsigned __int8 *v7; // rsi
  int v8; // r14d
  int v10; // ebx
  int v11; // r15d
  int v12; // r12d
  signed int v13; // r13d
  HGDIOBJ StockObject; // rax
  int v15; // edx
  float v16; // xmm6_4
  signed int v17; // ebx
  unsigned int v18; // eax
  unsigned __int8 *v19; // rsi
  int v20; // r13d
  int v21; // r8d
  int v22; // r9d
  int v23; // r11d
  signed int v24; // r15d
  unsigned int v25; // r12d
  int v26; // r10d
  bool v27; // zf
  int v28; // ecx
  int v29; // eax
  int v30; // eax
  int v31; // eax
  int v32; // eax
  bool v33; // cc
  int v34; // r13d
  HBRUSH SolidBrush; // r15
  HBRUSH AlphaMaskBrush; // rax
  int v37; // eax
  unsigned int v39; // [rsp+48h] [rbp-C0h]
  int v40; // [rsp+48h] [rbp-C0h]
  int v41; // [rsp+4Ch] [rbp-BCh]
  int v42; // [rsp+50h] [rbp-B8h]
  int v43; // [rsp+54h] [rbp-B4h]
  signed int v44; // [rsp+58h] [rbp-B0h]
  int v45; // [rsp+5Ch] [rbp-ACh]
  int v46; // [rsp+60h] [rbp-A8h]
  int rop2; // [rsp+68h] [rbp-A0h]
  HGDIOBJ h; // [rsp+88h] [rbp-80h]
  void **v52; // [rsp+90h] [rbp-78h] BYREF
  int v53; // [rsp+98h] [rbp-70h]
  int v54; // [rsp+9Ch] [rbp-6Ch]
  __int64 v55; // [rsp+A0h] [rbp-68h]
  int v56; // [rsp+A8h] [rbp-60h]
  __int64 v57; // [rsp+ACh] [rbp-5Ch]
  __int64 v58; // [rsp+B4h] [rbp-54h]
  _DWORD v59[112]; // [rsp+C8h] [rbp-40h] BYREF
  _BYTE v60[368]; // [rsp+288h] [rbp+180h] BYREF
  float v61[2]; // [rsp+3F8h] [rbp+2F0h] BYREF
  float v62; // [rsp+400h] [rbp+2F8h]
  int v63; // [rsp+404h] [rbp+2FCh]
  float v64; // [rsp+408h] [rbp+300h]
  float v65; // [rsp+40Ch] [rbp+304h]
  float v66; // [rsp+410h] [rbp+308h]
  float v67; // [rsp+414h] [rbp+30Ch]
  _BYTE v68[80]; // [rsp+418h] [rbp+310h] BYREF
  char v69[16]; // [rsp+468h] [rbp+360h] BYREF

  v7 = *(unsigned __int8 **)(a3 + 16);
  v8 = 1;
  v10 = *v7;
  v11 = v7[1];
  v12 = v7[2];
  v13 = v7[3];
  v52 = &GpMatrix::`vftable';
  v54 = -1;
  v57 = 1065353216;
  v55 = 1065353216;
  v58 = 0;
  v56 = 0;
  v53 = 1952533809;
  `vector constructor iterator'(v61, 8u, 4u, (void *(*)(void *))PointF::PointF);
  `vector constructor iterator'(v68, 8u, 0xAu, (void *(*)(void *))PointF::PointF);
  StockObject = GetStockObject(8);
  h = SelectObject(a2, StockObject);
  rop2 = 13;
  if ( a4 != 15728673 )
    rop2 = SetROP2(a2, 7);
  if ( *(_DWORD *)a3 )
  {
    v15 = v10;
    v16 = a7 + 4.0;
    v17 = v13;
    v43 = v11;
    v18 = 0;
    v45 = v12;
    v19 = v7 + 4;
    v44 = v13;
    v20 = v12;
    v39 = 0;
    v21 = v11;
    v42 = v15;
    v22 = v12;
    v46 = 2;
    v23 = v11;
    v41 = 0;
    v24 = v44;
    v25 = 1;
    v26 = v15;
    v27 = *(_DWORD *)a3 == 1;
    do
    {
      if ( v27 )
      {
        v28 = 2;
        LOBYTE(v22) = v20;
        v41 = 2;
        LOBYTE(v21) = v23;
        LOBYTE(v15) = v26;
        v17 = v24;
      }
      else
      {
        v20 = v19[2];
        v26 = *v19;
        v23 = v19[1];
        v24 = v19[3];
        v19 += 4;
        v42 = v26;
        v29 = v22 - v20;
        v43 = v23;
        v45 = v20;
        if ( v22 - v20 < 0 )
          v29 = v20 - v22;
        v44 = v24;
        if ( v29 >= 1 )
          goto LABEL_20;
        v30 = v21 - v23;
        if ( v21 - v23 < 0 )
          v30 = v23 - v21;
        if ( v30 >= 1 )
          goto LABEL_20;
        v31 = v15 - v26;
        if ( v15 - v26 < 0 )
          v31 = v26 - v15;
        if ( v31 >= 1 )
        {
LABEL_20:
          v18 = v39;
        }
        else
        {
          v32 = v17 - v24;
          if ( v17 - v24 < 0 )
            v32 = v24 - v17;
          v33 = v32 < 1;
          v18 = v39;
          if ( v33 )
            goto LABEL_36;
        }
        v28 = v41;
      }
      if ( v17 >= 2 )
      {
        v34 = v18 - v46;
        v40 = v46 + v28 - v39;
        v46 = 0;
        SolidBrush = CreateSolidBrush((unsigned __int8)v22 | ((unsigned __int8)v15 << 16) | ((unsigned __int8)v21 << 8));
        if ( SolidBrush )
        {
          v61[1] = -2.0;
          v63 = -1073741824;
          v61[0] = (float)v34;
          v65 = v16 - 2.0;
          v66 = (float)v34;
          v67 = v16 - 2.0;
          v62 = (float)(int)(v25 + v40) + (float)v34;
          v64 = v62;
          GpMatrix::Transform(a6, (struct PointF *)v61, 4);
          GpPath::GpPath(v60, v61, 4, v68, v69, 10, 0, 3);
          ConvertPathToGdi::ConvertPathToGdi(
            (ConvertPathToGdi *)v59,
            (const struct DpPath *)v60,
            (struct GpMatrix *)&v52,
            0x10u,
            0);
          if ( v59[0] == 1198932785 )
          {
            if ( a5 || v17 > 253 || (AlphaMaskBrush = DriverPrint::GetAlphaMaskBrush(a1, v17, 0)) == 0 )
              v37 = ConvertPathToGdi::Fill((ConvertPathToGdi *)v59, a2, SolidBrush);
            else
              v37 = ConvertPathToGdi::AlphaFill((ConvertPathToGdi *)v59, a2, SolidBrush, AlphaMaskBrush);
            v8 &= v37;
          }
          else
          {
            v8 = 0;
          }
          DeleteObject(SolidBrush);
          ConvertPathToGdi::~ConvertPathToGdi((ConvertPathToGdi *)v59);
          GpPath::~GpPath((GpPath *)v60);
        }
        else
        {
          v8 = 0;
        }
        v20 = v45;
        v24 = v44;
        v23 = v43;
        v26 = v42;
      }
      v18 = v25;
      v22 = v20;
      v39 = v25;
      v21 = v23;
      v15 = v26;
      v17 = v24;
LABEL_36:
      v27 = ++v25 == *(_DWORD *)a3;
    }
    while ( v25 <= *(_DWORD *)a3 );
  }
  SelectObject(a2, h);
  if ( a4 != 15728673 )
    SetROP2(a2, rop2);
  return v8 == 0;
}

```

## disassembly

```asm
0x18014057c  mov     rax, rsp
0x18014057f  mov     [rax+20h], rbx
0x180140583  push    rbp
0x180140584  push    rsi
0x180140585  push    rdi
0x180140586  push    r12
0x180140588  push    r13
0x18014058a  push    r14
0x18014058c  push    r15
0x18014058e  lea     rbp, [rax-3C8h]
0x180140595  sub     rsp, 490h
0x18014059c  movaps  xmmword ptr [rax-48h], xmm6
0x1801405a0  mov     rax, cs:__security_cookie
0x1801405a7  xor     rax, rsp
0x1801405aa  mov     [rbp+3C0h+var_50], rax
0x1801405b1  mov     rsi, [r8+10h]
0x1801405b5  lea     rax, ??_7GpMatrix@@6B@; const GpMatrix::`vftable'
0x1801405bc  mov     [rsp+4C0h+var_448], rcx
0x1801405c1  mov     r14d, 1
0x1801405c7  mov     rcx, [rbp+3C0h+arg_28]
0x1801405ce  mov     rdi, rdx
0x1801405d1  mov     [rsp+4C0h+var_464], r9d
0x1801405d6  lea     r9, ??0PointF@@QEAA@XZ; void *(*)(void *)
0x1801405dd  movzx   ebx, byte ptr [rsi]
0x1801405e0  movzx   r15d, byte ptr [rsi+1]
0x1801405e5  lea     edx, [r14+7]; unsigned __int64
0x1801405e9  movzx   r12d, byte ptr [rsi+2]
0x1801405ee  movzx   r13d, byte ptr [rsi+3]
0x1801405f3  mov     [rsp+4C0h+var_458], r8
0x1801405f8  lea     r8d, [r14+3]; unsigned __int64
0x1801405fc  mov     [rsp+4C0h+var_450], rcx
0x180140601  lea     rcx, [rbp+3C0h+var_D0]; void *
0x180140608  mov     [rbp+3C0h+var_438], rax
0x18014060c  mov     [rbp+3C0h+var_42C], 0FFFFFFFFh
0x180140613  mov     [rbp+3C0h+var_41C], 3F800000h
0x18014061b  mov     [rbp+3C0h+var_428], 3F800000h
0x180140623  mov     [rbp+3C0h+var_414], 0
0x18014062b  mov     [rbp+3C0h+var_420], 0
0x180140632  mov     [rbp+3C0h+var_430], 74614D31h
0x180140639  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x18014063e  lea     r9, ??0PointF@@QEAA@XZ; void *(*)(void *)
0x180140645  lea     edx, [r14+7]; unsigned __int64
0x180140649  lea     r8d, [r14+9]; unsigned __int64
0x18014064d  lea     rcx, [rbp+3C0h+var_B0]; void *
0x180140654  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x180140659  lea     ecx, [r14+7]; i
0x18014065d  call    cs:__imp_GetStockObject
0x180140664  nop     dword ptr [rax+rax+00h]
0x180140669  mov     rdx, rax; h
0x18014066c  mov     rcx, rdi; hdc
0x18014066f  call    cs:__imp_SelectObject
0x180140676  nop     dword ptr [rax+rax+00h]
0x18014067b  cmp     [rsp+4C0h+var_464], 0F00021h
0x180140683  mov     [rbp+3C0h+h], rax
0x180140687  mov     [rsp+4C0h+rop2], 0Dh
0x18014068f  jz      short loc_1801406A8
0x180140691  lea     edx, [r14+6]; rop2
0x180140695  mov     rcx, rdi; hdc
0x180140698  call    cs:__imp_SetROP2
0x18014069f  nop     dword ptr [rax+rax+00h]
0x1801406a4  mov     [rsp+4C0h+rop2], eax
0x1801406a8  mov     rax, [rsp+4C0h+var_458]
0x1801406ad  mov     ecx, [rax]
0x1801406af  cmp     ecx, r14d
0x1801406b2  jb      loc_18014099B
0x1801406b8  movss   xmm6, [rbp+3C0h+arg_30]
0x1801406c0  mov     edx, ebx
0x1801406c2  addss   xmm6, cs:__real@40800000
0x1801406ca  mov     ebx, r13d
0x1801406cd  mov     [rsp+4C0h+var_474], r15d
0x1801406d2  xor     eax, eax
0x1801406d4  mov     [rsp+4C0h+var_46C], r12d
0x1801406d9  add     rsi, 4
0x1801406dd  mov     [rsp+4C0h+var_470], ebx
0x1801406e1  mov     r13d, r12d
0x1801406e4  mov     [rsp+4C0h+var_480], eax
0x1801406e8  mov     r8d, r15d
0x1801406eb  mov     [rsp+4C0h+var_478], edx
0x1801406ef  mov     r9d, r12d
0x1801406f2  mov     [rsp+4C0h+var_468], 2
0x1801406fa  mov     r11d, r15d
0x1801406fd  mov     [rsp+4C0h+var_47C], eax
0x180140701  mov     r15d, ebx
0x180140704  mov     r12d, r14d
0x180140707  mov     r10d, edx
0x18014070a  cmp     r14d, ecx
0x18014070d  jnz     short loc_180140729
0x18014070f  mov     ecx, 2
0x180140714  mov     r9d, r13d
0x180140717  mov     [rsp+4C0h+var_47C], ecx
0x18014071b  mov     r8d, r11d
0x18014071e  mov     edx, r10d
0x180140721  mov     ebx, r15d
0x180140724  jmp     loc_1801407AC
0x180140729  movzx   r13d, byte ptr [rsi+2]
0x18014072e  movzx   r10d, byte ptr [rsi]
0x180140732  mov     ecx, r13d
0x180140735  movzx   r11d, byte ptr [rsi+1]
0x18014073a  sub     ecx, r9d
0x18014073d  movzx   r15d, byte ptr [rsi+3]
0x180140742  mov     eax, ecx
0x180140744  add     rsi, 4
0x180140748  mov     [rsp+4C0h+var_478], r10d
0x18014074d  neg     eax
0x18014074f  mov     [rsp+4C0h+var_474], r11d
0x180140754  mov     [rsp+4C0h+var_46C], r13d
0x180140759  cmovs   eax, ecx
0x18014075c  mov     [rsp+4C0h+var_470], r15d
0x180140761  cmp     eax, 1
0x180140764  jge     short loc_1801407A4
0x180140766  mov     ecx, r11d
0x180140769  sub     ecx, r8d
0x18014076c  mov     eax, ecx
0x18014076e  neg     eax
0x180140770  cmovs   eax, ecx
0x180140773  cmp     eax, 1
0x180140776  jge     short loc_1801407A4
0x180140778  mov     ecx, r10d
0x18014077b  sub     ecx, edx
0x18014077d  mov     eax, ecx
0x18014077f  neg     eax
0x180140781  cmovs   eax, ecx
0x180140784  cmp     eax, 1
0x180140787  jge     short loc_1801407A4
0x180140789  mov     ecx, r15d
0x18014078c  sub     ecx, ebx
0x18014078e  mov     eax, ecx
0x180140790  neg     eax
0x180140792  cmovs   eax, ecx
0x180140795  cmp     eax, 1
0x180140798  mov     eax, [rsp+4C0h+var_480]
0x18014079c  jl      loc_180140988
0x1801407a2  jmp     short loc_1801407A8
0x1801407a4  mov     eax, [rsp+4C0h+var_480]
0x1801407a8  mov     ecx, [rsp+4C0h+var_47C]
0x1801407ac  cmp     ebx, 2
0x1801407af  jl      loc_180140975
0x1801407b5  mov     r13d, eax
0x1801407b8  mov     eax, ecx
0x1801407ba  sub     eax, [rsp+4C0h+var_480]
0x1801407be  add     eax, [rsp+4C0h+var_468]
0x1801407c2  sub     r13d, [rsp+4C0h+var_468]
0x1801407c7  mov     [rsp+4C0h+var_480], eax
0x1801407cb  movzx   eax, dl
0x1801407ce  shl     eax, 10h
0x1801407d1  movzx   ecx, r8b
0x1801407d5  shl     ecx, 8
0x1801407d8  or      ecx, eax
0x1801407da  mov     [rsp+4C0h+var_468], 0
0x1801407e2  movzx   eax, r9b
0x1801407e6  or      ecx, eax; color
0x1801407e8  call    cs:__imp_CreateSolidBrush
0x1801407ef  nop     dword ptr [rax+rax+00h]
0x1801407f4  mov     r15, rax
0x1801407f7  test    rax, rax
0x1801407fa  jz      loc_18014095E
0x180140800  mov     ecx, [rsp+4C0h+var_480]
0x180140804  lea     rdx, [rbp+3C0h+var_D0]; struct PointF *
0x18014080b  add     ecx, r12d
0x18014080e  movd    xmm2, r13d
0x180140813  cvtdq2ps xmm2, xmm2
0x180140816  mov     [rbp+3C0h+var_CC], 0C0000000h
0x180140820  mov     r8d, 4; int
0x180140826  mov     [rbp+3C0h+var_C4], 0C0000000h
0x180140830  movd    xmm0, ecx
0x180140834  movaps  xmm1, xmm6
0x180140837  subss   xmm1, cs:__real@40000000
0x18014083f  mov     rcx, [rsp+4C0h+var_450]; this
0x180140844  cvtdq2ps xmm0, xmm0
0x180140847  movss   [rbp+3C0h+var_D0], xmm2
0x18014084f  addss   xmm0, xmm2
0x180140853  movss   [rbp+3C0h+var_BC], xmm1
0x18014085b  movss   [rbp+3C0h+var_B8], xmm2
0x180140863  movss   [rbp+3C0h+var_B4], xmm1
0x18014086b  movss   [rbp+3C0h+var_C8], xmm0
0x180140873  movss   [rbp+3C0h+var_C0], xmm0
0x18014087b  call    ?Transform@GpMatrix@@QEBAXPEAVPointF@@H@Z; GpMatrix::Transform(PointF *,int)
0x180140880  mov     [rsp+4C0h+var_488], 3
0x180140888  lea     rax, [rbp+3C0h+var_60]
0x18014088f  xor     r13d, r13d
0x180140892  lea     r9, [rbp+3C0h+var_B0]
0x180140899  mov     [rsp+4C0h+var_490], r13d
0x18014089e  lea     rdx, [rbp+3C0h+var_D0]
0x1801408a5  mov     [rsp+4C0h+var_498], 0Ah
0x1801408ad  lea     rcx, [rbp+3C0h+var_240]
0x1801408b4  mov     [rsp+4C0h+var_4A0], rax
0x1801408b9  lea     r8d, [r13+4]
0x1801408bd  call    ??0GpPath@@QEAA@PEBVPointF@@HPEAV1@PEAEHW4FillMode@@W4DpPathFlags@DpPath@@@Z; GpPath::GpPath(PointF const *,int,PointF *,uchar *,int,FillMode,DpPath::DpPathFlags)
0x1801408c2  lea     r9d, [r13+10h]; unsigned int
0x1801408c6  mov     [rsp+4C0h+var_4A0], r13; struct GpRuntime::GpRect *
0x1801408cb  lea     r8, [rbp+3C0h+var_438]; struct GpMatrix *
0x1801408cf  lea     rdx, [rbp+3C0h+var_240]; struct DpPath *
0x1801408d6  lea     rcx, [rbp+3C0h+var_400]; this
0x1801408da  call    ??0ConvertPathToGdi@@QEAA@PEBVDpPath@@PEAVGpMatrix@@KPEBVGpRect@GpRuntime@@@Z; ConvertPathToGdi::ConvertPathToGdi(DpPath const *,GpMatrix *,ulong,GpRuntime::GpRect const *)
0x1801408df  cmp     [rbp+3C0h+var_400], 47764331h
0x1801408e6  jnz     short loc_180140935
0x1801408e8  cmp     [rbp+3C0h+arg_20], r13d
0x1801408ef  jnz     short loc_180140921
0x1801408f1  cmp     ebx, 0FDh
0x1801408f7  jg      short loc_180140921
0x1801408f9  mov     rcx, [rsp+4C0h+var_448]; this
0x1801408fe  xor     r8d, r8d; int
0x180140901  mov     edx, ebx; unsigned int
0x180140903  call    ?GetAlphaMaskBrush@DriverPrint@@IEBAPEAUHBRUSH__@@IH@Z; DriverPrint::GetAlphaMaskBrush(uint,int)
0x180140908  test    rax, rax
0x18014090b  jz      short loc_180140921
0x18014090d  mov     r9, rax; HBRUSH
0x180140910  lea     rcx, [rbp+3C0h+var_400]; this
0x180140914  mov     r8, r15; h
0x180140917  mov     rdx, rdi; HDC
0x18014091a  call    ?AlphaFill@ConvertPathToGdi@@QEAAHPEAUHDC__@@PEAUHBRUSH__@@1@Z; ConvertPathToGdi::AlphaFill(HDC__ *,HBRUSH__ *,HBRUSH__ *)
0x18014091f  jmp     short loc_180140930
0x180140921  mov     r8, r15; h
0x180140924  lea     rcx, [rbp+3C0h+var_400]; this
0x180140928  mov     rdx, rdi; HDC
0x18014092b  call    ?Fill@ConvertPathToGdi@@QEAAHPEAUHDC__@@PEAUHBRUSH__@@@Z; ConvertPathToGdi::Fill(HDC__ *,HBRUSH__ *)
0x180140930  and     r14d, eax
0x180140933  jmp     short loc_180140938
0x180140935  mov     r14d, r13d
0x180140938  mov     rcx, r15; ho
0x18014093b  call    cs:__imp_DeleteObject
0x180140942  nop     dword ptr [rax+rax+00h]
0x180140947  lea     rcx, [rbp+3C0h+var_400]; this
0x18014094b  call    ??1ConvertPathToGdi@@QEAA@XZ; ConvertPathToGdi::~ConvertPathToGdi(void)
0x180140950  lea     rcx, [rbp+3C0h+var_240]; this
0x180140957  call    ??1GpPath@@UEAA@XZ; GpPath::~GpPath(void)
0x18014095c  jmp     short loc_180140961
0x18014095e  xor     r14d, r14d
0x180140961  mov     r13d, [rsp+4C0h+var_46C]
0x180140966  mov     r15d, [rsp+4C0h+var_470]
0x18014096b  mov     r11d, [rsp+4C0h+var_474]
0x180140970  mov     r10d, [rsp+4C0h+var_478]
0x180140975  mov     eax, r12d
0x180140978  mov     r9d, r13d
0x18014097b  mov     [rsp+4C0h+var_480], eax
0x18014097f  mov     r8d, r11d
0x180140982  mov     edx, r10d
0x180140985  mov     ebx, r15d
0x180140988  mov     rcx, [rsp+4C0h+var_458]
0x18014098d  inc     r12d
0x180140990  mov     ecx, [rcx]
0x180140992  cmp     r12d, ecx
0x180140995  jbe     loc_18014070D
0x18014099b  mov     rdx, [rbp+3C0h+h]; h
0x18014099f  mov     rcx, rdi; hdc
0x1801409a2  call    cs:__imp_SelectObject
0x1801409a9  nop     dword ptr [rax+rax+00h]
0x1801409ae  cmp     [rsp+4C0h+var_464], 0F00021h
0x1801409b6  jz      short loc_1801409CB
0x1801409b8  mov     edx, [rsp+4C0h+rop2]; rop2
0x1801409bc  mov     rcx, rdi; hdc
0x1801409bf  call    cs:__imp_SetROP2
0x1801409c6  nop     dword ptr [rax+rax+00h]
0x1801409cb  xor     eax, eax
0x1801409cd  test    r14d, r14d
0x1801409d0  setz    al
0x1801409d3  mov     rcx, [rbp+3C0h+var_50]
0x1801409da  xor     rcx, rsp; StackCookie
0x1801409dd  call    __security_check_cookie
0x1801409e2  lea     r11, [rsp+4C0h+var_30]
0x1801409ea  mov     rbx, [r11+58h]
0x1801409ee  movaps  xmm6, xmmword ptr [r11-10h]
0x1801409f3  mov     rsp, r11
0x1801409f6  pop     r15
0x1801409f8  pop     r14
0x1801409fa  pop     r13
0x1801409fc  pop     r12
0x1801409fe  pop     rdi
0x1801409ff  pop     rsi
0x180140a00  pop     rbp
0x180140a01  retn
```
