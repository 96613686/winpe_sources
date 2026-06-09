# DriverPrint::PrivateFillDiagonalGradient(HDC__ *,BitmapData &,ulong,int,GpMatrix *,float)

- ea: `0x18013808c`
- end: `0x1801384e8`
- name: `?PrivateFillDiagonalGradient@DriverPrint@@AEAA?AW4Status@@PEAUHDC__@@AEAVBitmapData@@KHPEAVGpMatrix@@M@Z`
- size: `1116`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x1800f3b84`

## callees

- `0x180013ad0`
- `0x18004b4b0`
- `0x18004e87c`
- `0x18005bb48`
- `0x18005e53c`
- `0x180076f28`
- `0x1800e6c40`
- `0x1800fe680`
- `0x180137c38`
- `0x18013808c`
- `0x18013bd04`

## import_xrefs

- `GDI32!CreateSolidBrush` at `0x1801382e6`
- `GDI32!CreateSolidBrush` at `0x1801382e6`
- `GDI32!SetROP2` at `0x18013819c`
- `GDI32!SetROP2` at `0x1801384ab`
- `GDI32!SetROP2` at `0x18013819c`
- `GDI32!SetROP2` at `0x1801384ab`
- `GDI32!GetStockObject` at `0x18013816d`
- `GDI32!GetStockObject` at `0x18013816d`
- `GDI32!SelectObject` at `0x180138179`
- `GDI32!SelectObject` at `0x180138494`
- `GDI32!SelectObject` at `0x180138179`
- `GDI32!SelectObject` at `0x180138494`
- `GDI32!DeleteObject` at `0x180138433`
- `GDI32!DeleteObject` at `0x180138433`

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
0x18013808c  mov     rax, rsp
0x18013808f  mov     [rax+20h], rbx
0x180138093  push    rbp
0x180138094  push    rsi
0x180138095  push    rdi
0x180138096  push    r12
0x180138098  push    r13
0x18013809a  push    r14
0x18013809c  push    r15
0x18013809e  lea     rbp, [rax-3C8h]
0x1801380a5  sub     rsp, 490h
0x1801380ac  movaps  xmmword ptr [rax-48h], xmm6
0x1801380b0  mov     rax, cs:__security_cookie
0x1801380b7  xor     rax, rsp
0x1801380ba  mov     [rbp+3C0h+var_50], rax
0x1801380c1  mov     rsi, [r8+10h]
0x1801380c5  lea     rax, ??_7GpMatrix@@6B@; const GpMatrix::`vftable'
0x1801380cc  mov     [rsp+4C0h+var_448], rcx
0x1801380d1  mov     r14d, 1
0x1801380d7  mov     rcx, [rbp+3C0h+arg_28]
0x1801380de  mov     rdi, rdx
0x1801380e1  mov     [rsp+4C0h+var_464], r9d
0x1801380e6  lea     r9, ??0PointF@@QEAA@XZ; void *(*)(void *)
0x1801380ed  movzx   ebx, byte ptr [rsi]
0x1801380f0  movzx   r15d, byte ptr [rsi+1]
0x1801380f5  lea     edx, [r14+7]; unsigned __int64
0x1801380f9  movzx   r12d, byte ptr [rsi+2]
0x1801380fe  movzx   r13d, byte ptr [rsi+3]
0x180138103  mov     [rsp+4C0h+var_458], r8
0x180138108  lea     r8d, [r14+3]; unsigned __int64
0x18013810c  mov     [rsp+4C0h+var_450], rcx
0x180138111  lea     rcx, [rbp+3C0h+var_D0]; void *
0x180138118  mov     [rbp+3C0h+var_438], rax
0x18013811c  mov     [rbp+3C0h+var_42C], 0FFFFFFFFh
0x180138123  mov     [rbp+3C0h+var_41C], 3F800000h
0x18013812b  mov     [rbp+3C0h+var_428], 3F800000h
0x180138133  mov     [rbp+3C0h+var_414], 0
0x18013813b  mov     [rbp+3C0h+var_420], 0
0x180138142  mov     [rbp+3C0h+var_430], 74614D31h
0x180138149  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x18013814e  lea     r9, ??0PointF@@QEAA@XZ; void *(*)(void *)
0x180138155  lea     edx, [r14+7]; unsigned __int64
0x180138159  lea     r8d, [r14+9]; unsigned __int64
0x18013815d  lea     rcx, [rbp+3C0h+var_B0]; void *
0x180138164  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x180138169  lea     ecx, [r14+7]; i
0x18013816d  call    cs:__imp_GetStockObject
0x180138173  mov     rdx, rax; h
0x180138176  mov     rcx, rdi; hdc
0x180138179  call    cs:__imp_SelectObject
0x18013817f  cmp     [rsp+4C0h+var_464], 0F00021h
0x180138187  mov     [rbp+3C0h+h], rax
0x18013818b  mov     [rsp+4C0h+rop2], 0Dh
0x180138193  jz      short loc_1801381A6
0x180138195  lea     edx, [r14+6]; rop2
0x180138199  mov     rcx, rdi; hdc
0x18013819c  call    cs:__imp_SetROP2
0x1801381a2  mov     [rsp+4C0h+rop2], eax
0x1801381a6  mov     rax, [rsp+4C0h+var_458]
0x1801381ab  mov     ecx, [rax]
0x1801381ad  cmp     ecx, r14d
0x1801381b0  jb      loc_18013848D
0x1801381b6  movss   xmm6, [rbp+3C0h+arg_30]
0x1801381be  mov     edx, ebx
0x1801381c0  addss   xmm6, cs:__real@40800000
0x1801381c8  mov     ebx, r13d
0x1801381cb  mov     [rsp+4C0h+var_474], r15d
0x1801381d0  xor     eax, eax
0x1801381d2  mov     [rsp+4C0h+var_46C], r12d
0x1801381d7  add     rsi, 4
0x1801381db  mov     [rsp+4C0h+var_470], ebx
0x1801381df  mov     r13d, r12d
0x1801381e2  mov     [rsp+4C0h+var_480], eax
0x1801381e6  mov     r8d, r15d
0x1801381e9  mov     [rsp+4C0h+var_478], edx
0x1801381ed  mov     r9d, r12d
0x1801381f0  mov     [rsp+4C0h+var_468], 2
0x1801381f8  mov     r11d, r15d
0x1801381fb  mov     [rsp+4C0h+var_47C], eax
0x1801381ff  mov     r15d, ebx
0x180138202  mov     r12d, r14d
0x180138205  mov     r10d, edx
0x180138208  cmp     r14d, ecx
0x18013820b  jnz     short loc_180138227
0x18013820d  mov     ecx, 2
0x180138212  mov     r9d, r13d
0x180138215  mov     [rsp+4C0h+var_47C], ecx
0x180138219  mov     r8d, r11d
0x18013821c  mov     edx, r10d
0x18013821f  mov     ebx, r15d
0x180138222  jmp     loc_1801382AA
0x180138227  movzx   r13d, byte ptr [rsi+2]
0x18013822c  movzx   r10d, byte ptr [rsi]
0x180138230  mov     ecx, r13d
0x180138233  movzx   r11d, byte ptr [rsi+1]
0x180138238  sub     ecx, r9d
0x18013823b  movzx   r15d, byte ptr [rsi+3]
0x180138240  mov     eax, ecx
0x180138242  add     rsi, 4
0x180138246  mov     [rsp+4C0h+var_478], r10d
0x18013824b  neg     eax
0x18013824d  mov     [rsp+4C0h+var_474], r11d
0x180138252  mov     [rsp+4C0h+var_46C], r13d
0x180138257  cmovs   eax, ecx
0x18013825a  mov     [rsp+4C0h+var_470], r15d
0x18013825f  cmp     eax, 1
0x180138262  jge     short loc_1801382A2
0x180138264  mov     ecx, r11d
0x180138267  sub     ecx, r8d
0x18013826a  mov     eax, ecx
0x18013826c  neg     eax
0x18013826e  cmovs   eax, ecx
0x180138271  cmp     eax, 1
0x180138274  jge     short loc_1801382A2
0x180138276  mov     ecx, r10d
0x180138279  sub     ecx, edx
0x18013827b  mov     eax, ecx
0x18013827d  neg     eax
0x18013827f  cmovs   eax, ecx
0x180138282  cmp     eax, 1
0x180138285  jge     short loc_1801382A2
0x180138287  mov     ecx, r15d
0x18013828a  sub     ecx, ebx
0x18013828c  mov     eax, ecx
0x18013828e  neg     eax
0x180138290  cmovs   eax, ecx
0x180138293  cmp     eax, 1
0x180138296  mov     eax, [rsp+4C0h+var_480]
0x18013829a  jl      loc_18013847A
0x1801382a0  jmp     short loc_1801382A6
0x1801382a2  mov     eax, [rsp+4C0h+var_480]
0x1801382a6  mov     ecx, [rsp+4C0h+var_47C]
0x1801382aa  cmp     ebx, 2
0x1801382ad  jl      loc_180138467
0x1801382b3  mov     r13d, eax
0x1801382b6  mov     eax, ecx
0x1801382b8  sub     eax, [rsp+4C0h+var_480]
0x1801382bc  add     eax, [rsp+4C0h+var_468]
0x1801382c0  sub     r13d, [rsp+4C0h+var_468]
0x1801382c5  mov     [rsp+4C0h+var_480], eax
0x1801382c9  movzx   eax, dl
0x1801382cc  shl     eax, 10h
0x1801382cf  movzx   ecx, r8b
0x1801382d3  shl     ecx, 8
0x1801382d6  or      ecx, eax
0x1801382d8  mov     [rsp+4C0h+var_468], 0
0x1801382e0  movzx   eax, r9b
0x1801382e4  or      ecx, eax; color
0x1801382e6  call    cs:__imp_CreateSolidBrush
0x1801382ec  mov     r15, rax
0x1801382ef  test    rax, rax
0x1801382f2  jz      loc_180138450
0x1801382f8  mov     ecx, [rsp+4C0h+var_480]
0x1801382fc  lea     rdx, [rbp+3C0h+var_D0]; struct PointF *
0x180138303  add     ecx, r12d
0x180138306  movd    xmm2, r13d
0x18013830b  cvtdq2ps xmm2, xmm2
0x18013830e  mov     [rbp+3C0h+var_CC], 0C0000000h
0x180138318  mov     r8d, 4; int
0x18013831e  mov     [rbp+3C0h+var_C4], 0C0000000h
0x180138328  movd    xmm0, ecx
0x18013832c  movaps  xmm1, xmm6
0x18013832f  subss   xmm1, cs:__real@40000000
0x180138337  mov     rcx, [rsp+4C0h+var_450]; this
0x18013833c  cvtdq2ps xmm0, xmm0
0x18013833f  movss   [rbp+3C0h+var_D0], xmm2
0x180138347  addss   xmm0, xmm2
0x18013834b  movss   [rbp+3C0h+var_BC], xmm1
0x180138353  movss   [rbp+3C0h+var_B8], xmm2
0x18013835b  movss   [rbp+3C0h+var_B4], xmm1
0x180138363  movss   [rbp+3C0h+var_C8], xmm0
0x18013836b  movss   [rbp+3C0h+var_C0], xmm0
0x180138373  call    ?Transform@GpMatrix@@QEBAXPEAVPointF@@H@Z; GpMatrix::Transform(PointF *,int)
0x180138378  mov     [rsp+4C0h+var_488], 3
0x180138380  lea     rax, [rbp+3C0h+var_60]
0x180138387  xor     r13d, r13d
0x18013838a  lea     r9, [rbp+3C0h+var_B0]
0x180138391  mov     [rsp+4C0h+var_490], r13d
0x180138396  lea     rdx, [rbp+3C0h+var_D0]
0x18013839d  mov     [rsp+4C0h+var_498], 0Ah
0x1801383a5  lea     rcx, [rbp+3C0h+var_240]
0x1801383ac  mov     [rsp+4C0h+var_4A0], rax
0x1801383b1  lea     r8d, [r13+4]
0x1801383b5  call    ??0GpPath@@QEAA@PEBVPointF@@HPEAV1@PEAEHW4FillMode@@W4DpPathFlags@DpPath@@@Z; GpPath::GpPath(PointF const *,int,PointF *,uchar *,int,FillMode,DpPath::DpPathFlags)
0x1801383ba  lea     r9d, [r13+10h]; unsigned int
0x1801383be  mov     [rsp+4C0h+var_4A0], r13; struct GpRuntime::GpRect *
0x1801383c3  lea     r8, [rbp+3C0h+var_438]; struct GpMatrix *
0x1801383c7  lea     rdx, [rbp+3C0h+var_240]; struct DpPath *
0x1801383ce  lea     rcx, [rbp+3C0h+var_400]; this
0x1801383d2  call    ??0ConvertPathToGdi@@QEAA@PEBVDpPath@@PEAVGpMatrix@@KPEBVGpRect@GpRuntime@@@Z; ConvertPathToGdi::ConvertPathToGdi(DpPath const *,GpMatrix *,ulong,GpRuntime::GpRect const *)
0x1801383d7  cmp     [rbp+3C0h+var_400], 47764331h
0x1801383de  jnz     short loc_18013842D
0x1801383e0  cmp     [rbp+3C0h+arg_20], r13d
0x1801383e7  jnz     short loc_180138419
0x1801383e9  cmp     ebx, 0FDh
0x1801383ef  jg      short loc_180138419
0x1801383f1  mov     rcx, [rsp+4C0h+var_448]; this
0x1801383f6  xor     r8d, r8d; int
0x1801383f9  mov     edx, ebx; unsigned int
0x1801383fb  call    ?GetAlphaMaskBrush@DriverPrint@@IEBAPEAUHBRUSH__@@IH@Z; DriverPrint::GetAlphaMaskBrush(uint,int)
0x180138400  test    rax, rax
0x180138403  jz      short loc_180138419
0x180138405  mov     r9, rax; HBRUSH
0x180138408  lea     rcx, [rbp+3C0h+var_400]; this
0x18013840c  mov     r8, r15; h
0x18013840f  mov     rdx, rdi; HDC
0x180138412  call    ?AlphaFill@ConvertPathToGdi@@QEAAHPEAUHDC__@@PEAUHBRUSH__@@1@Z; ConvertPathToGdi::AlphaFill(HDC__ *,HBRUSH__ *,HBRUSH__ *)
0x180138417  jmp     short loc_180138428
0x180138419  mov     r8, r15; h
0x18013841c  lea     rcx, [rbp+3C0h+var_400]; this
0x180138420  mov     rdx, rdi; HDC
0x180138423  call    ?Fill@ConvertPathToGdi@@QEAAHPEAUHDC__@@PEAUHBRUSH__@@@Z; ConvertPathToGdi::Fill(HDC__ *,HBRUSH__ *)
0x180138428  and     r14d, eax
0x18013842b  jmp     short loc_180138430
0x18013842d  mov     r14d, r13d
0x180138430  mov     rcx, r15; ho
0x180138433  call    cs:__imp_DeleteObject
0x180138439  lea     rcx, [rbp+3C0h+var_400]; this
0x18013843d  call    ??1ConvertPathToGdi@@QEAA@XZ; ConvertPathToGdi::~ConvertPathToGdi(void)
0x180138442  lea     rcx, [rbp+3C0h+var_240]; this
0x180138449  call    ??1GpPath@@UEAA@XZ; GpPath::~GpPath(void)
0x18013844e  jmp     short loc_180138453
0x180138450  xor     r14d, r14d
0x180138453  mov     r13d, [rsp+4C0h+var_46C]
0x180138458  mov     r15d, [rsp+4C0h+var_470]
0x18013845d  mov     r11d, [rsp+4C0h+var_474]
0x180138462  mov     r10d, [rsp+4C0h+var_478]
0x180138467  mov     eax, r12d
0x18013846a  mov     r9d, r13d
0x18013846d  mov     [rsp+4C0h+var_480], eax
0x180138471  mov     r8d, r11d
0x180138474  mov     edx, r10d
0x180138477  mov     ebx, r15d
0x18013847a  mov     rcx, [rsp+4C0h+var_458]
0x18013847f  inc     r12d
0x180138482  mov     ecx, [rcx]
0x180138484  cmp     r12d, ecx
0x180138487  jbe     loc_18013820B
0x18013848d  mov     rdx, [rbp+3C0h+h]; h
0x180138491  mov     rcx, rdi; hdc
0x180138494  call    cs:__imp_SelectObject
0x18013849a  cmp     [rsp+4C0h+var_464], 0F00021h
0x1801384a2  jz      short loc_1801384B1
0x1801384a4  mov     edx, [rsp+4C0h+rop2]; rop2
0x1801384a8  mov     rcx, rdi; hdc
0x1801384ab  call    cs:__imp_SetROP2
0x1801384b1  xor     eax, eax
0x1801384b3  test    r14d, r14d
0x1801384b6  setz    al
0x1801384b9  mov     rcx, [rbp+3C0h+var_50]
0x1801384c0  xor     rcx, rsp; StackCookie
0x1801384c3  call    __security_check_cookie
0x1801384c8  lea     r11, [rsp+4C0h+var_30]
0x1801384d0  mov     rbx, [r11+58h]
0x1801384d4  movaps  xmm6, xmmword ptr [r11-10h]
0x1801384d9  mov     rsp, r11
0x1801384dc  pop     r15
0x1801384de  pop     r14
0x1801384e0  pop     r13
0x1801384e2  pop     r12
0x1801384e4  pop     rdi
0x1801384e5  pop     rsi
0x1801384e6  pop     rbp
0x1801384e7  retn
```
