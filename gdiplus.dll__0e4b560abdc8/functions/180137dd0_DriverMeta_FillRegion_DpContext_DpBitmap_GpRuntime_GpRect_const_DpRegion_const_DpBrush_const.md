# DriverMeta::FillRegion(DpContext *,DpBitmap *,GpRuntime::GpRect const *,DpRegion const *,DpBrush const *)

- ea: `0x180137dd0`
- end: `0x1801381ba`
- name: `?FillRegion@DriverMeta@@UEAA?AW4Status@@PEAVDpContext@@PEAVDpBitmap@@PEBVGpRect@GpRuntime@@PEBVDpRegion@@PEBUDpBrush@@@Z`
- size: `1002`
- prototype: `__int64 __fastcall(_DWORD *, __int64, struct DpBitmap *, __int64, struct DpRegion *, unsigned int *)`
- caller_count: `0`
- callee_count: `23`
- tags: ``

## callees

- `0x18001e464`
- `0x180022450`
- `0x180029450`
- `0x18003b634`
- `0x18004bb6c`
- `0x18008392c`
- `0x180084de8`
- `0x1800a20c0`
- `0x1800aeca0`
- `0x1800c1c50`
- `0x1800cd174`
- `0x1800dc7c8`
- `0x1800debd4`
- `0x1800e6db4`
- `0x1800e8f30`
- `0x1800e9380`
- `0x180107eec`
- `0x180137dd0`
- `0x1801389d8`
- `0x180138a00`
- `0x180138b98`
- `0x18013a938`
- `0x180175010`

## import_xrefs

- `GDI32!FillRgn` at `0x180138145`
- `GDI32!FillRgn` at `0x180138145`
- `GDI32!DeleteObject` at `0x18013815e`
- `GDI32!DeleteObject` at `0x18013815e`

## pseudocode

```c
__int64 __fastcall DriverMeta::FillRegion(
        _DWORD *a1,
        __int64 a2,
        struct DpBitmap *a3,
        __int64 a4,
        struct DpRegion *a5,
        unsigned int *a6)
{
  struct DpRegion *v6; // rbx
  unsigned int v10; // r11d
  struct DpRegion *v11; // rax
  __int64 v12; // rcx
  int v13; // edx
  int v14; // eax
  bool v15; // zf
  int v16; // r12d
  __int64 v17; // rax
  HBRUSH Brush; // rsi
  unsigned int v20; // r15d
  unsigned int v21; // eax
  CopyOnWriteBitmap *Hdc; // rax
  HDC v23; // rbx
  __int64 v24; // rcx
  HBRUSH AlphaMaskBrush; // rax
  int v26; // r15d
  unsigned int v27; // [rsp+40h] [rbp-C0h] BYREF
  int v28; // [rsp+44h] [rbp-BCh] BYREF
  struct DpBitmap *v29; // [rsp+48h] [rbp-B8h] BYREF
  __m128i v30; // [rsp+50h] [rbp-B0h] BYREF
  int v31; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v32[20]; // [rsp+64h] [rbp-9Ch] BYREF
  HRGN hrgn; // [rsp+78h] [rbp-88h]
  _DWORD v34[10]; // [rsp+80h] [rbp-80h] BYREF
  void **v35; // [rsp+A8h] [rbp-58h] BYREF
  int v36; // [rsp+B0h] [rbp-50h]
  int v37; // [rsp+B4h] [rbp-4Ch]
  int v38; // [rsp+B8h] [rbp-48h]
  int v39; // [rsp+BCh] [rbp-44h]
  int v40; // [rsp+C0h] [rbp-40h]
  int v41; // [rsp+C4h] [rbp-3Ch]
  int v42; // [rsp+C8h] [rbp-38h]
  int v43; // [rsp+CCh] [rbp-34h]
  int v44; // [rsp+D0h] [rbp-30h]
  _BYTE v45[8]; // [rsp+E0h] [rbp-20h] BYREF
  int v46; // [rsp+E8h] [rbp-18h]
  _DWORD v47[112]; // [rsp+250h] [rbp+150h] BYREF

  v6 = a5;
  v29 = a3;
  DpRegion::DpRegion((DpRegion *)v34, 0);
  v10 = 0;
  if ( a1[28] )
  {
    DpRegion::Set(
      (DpRegion *)v34,
      *(_DWORD *)(a2 + 312),
      *(_DWORD *)(a2 + 316),
      *(_DWORD *)(a2 + 320) - *(_DWORD *)(a2 + 312),
      *(_DWORD *)(a2 + 324) - *(_DWORD *)(a2 + 316));
    DpRegion::And(v34, a5);
    v11 = (struct DpRegion *)v34;
    if ( v34[0] != 1733452849 )
      v11 = a5;
    v10 = 0;
    v6 = v11;
  }
  v12 = *((unsigned int *)v6 + 3);
  v13 = *((_DWORD *)v6 + 4) - *((_DWORD *)v6 + 2);
  v30.m128i_i32[0] = *((_DWORD *)v6 + 2);
  v14 = *((_DWORD *)v6 + 5) - v12;
  *(__int64 *)((char *)v30.m128i_i64 + 4) = __PAIR64__(v13, v12);
  v15 = (*((_BYTE *)v6 + 4) & 2) == 0;
  v30.m128i_i32[3] = v14;
  if ( !v15 || v13 <= 0 || v14 <= 0 )
    goto LABEL_20;
  v16 = 0;
  if ( a1[28] )
  {
    if ( (*((_DWORD *)a3 + 3) & 0xFF00u) <= 0x800 )
    {
      v17 = *(_QWORD *)(a2 + 672);
      if ( v17 )
      {
        if ( !*(_DWORD *)(v17 + 264) && (*a6 || !(unsigned int)DriverMeta::IsVGAOrSystemColor(v12, a6[1])) )
          v16 = 1;
      }
    }
  }
  v27 = v10;
  v28 = v10;
  Brush = DriverMeta::GetBrush((DriverMeta *)a1, (const struct DpBrush *)a6, &v27, &v28, v16);
  if ( !Brush )
  {
    GpPath::GpPath((GpPath *)v45, v6);
    if ( v46 == 1752453169 )
    {
      v37 = -1;
      v43 = 0;
      v42 = 0;
      v40 = 0;
      v39 = 0;
      v44 = 0;
      v35 = &GpMatrix::`vftable';
      v41 = 1065353216;
      v38 = 1065353216;
      v36 = 1952533809;
      ConvertPathToGdi::ConvertPathToGdi(
        (ConvertPathToGdi *)v47,
        (const struct DpPath *)v45,
        (struct GpMatrix *)&v35,
        0x10u,
        0);
      if ( v47[0] == 1198932785
        && !(unsigned int)DriverMeta::BrushFillUsingBitmap(
                            (DriverMeta *)a1,
                            (DpContext *)a2,
                            a3,
                            a6,
                            &v30,
                            (ConvertPathToGdi *)v47,
                            v16) )
      {
        ConvertPathToGdi::~ConvertPathToGdi((ConvertPathToGdi *)v47);
        GpPath::~GpPath((GpPath *)v45);
LABEL_20:
        DpRegion::~DpRegion((DpRegion *)v34);
        return 0;
      }
      ConvertPathToGdi::~ConvertPathToGdi((ConvertPathToGdi *)v47);
    }
    GpPath::~GpPath((GpPath *)v45);
  }
  ConvertRegionToGdi::ConvertRegionToGdi((ConvertRegionToGdi *)&v31, v6);
  if ( v31 == 1198932785 )
  {
    v20 = v27;
    if ( v27 < 2 )
      goto LABEL_25;
    if ( !Brush )
    {
      v21 = ToCOLORREF((const struct DpBrush *)a6);
      ConvertBrushToGdi::SetColor((ConvertBrushToGdi *)(a1 + 10), v21, v16, 0);
      Brush = ConvertBrushToGdi::GetGdiBrush((ConvertBrushToGdi *)(a1 + 10));
    }
    Hdc = DpContext::GetHdc((DpContext *)a2, v29);
    v23 = (HDC)Hdc;
    if ( Hdc )
    {
      v24 = *(_QWORD *)a1;
      LODWORD(v29) = 0;
      v27 = 1;
      (*(void (__fastcall **)(_DWORD *, CopyOnWriteBitmap *, __int64, _BYTE *, struct DpBitmap **, unsigned int *, _DWORD))(v24 + 40))(
        a1,
        Hdc,
        a2,
        v32,
        &v29,
        &v27,
        0);
      if ( v20 <= 0xFD && (AlphaMaskBrush = DriverMeta::GetAlphaMaskBrush((DriverMeta *)a1, v20, 1)) != 0 )
      {
        v26 = ConvertRegionToGdi::AlphaFill((ConvertRegionToGdi *)&v31, v23, Brush, AlphaMaskBrush);
      }
      else
      {
        v26 = FillRgn(v23, hrgn, Brush);
        if ( v28 )
          DeleteObject(Brush);
      }
      (*(void (__fastcall **)(_DWORD *, HDC, _QWORD, _QWORD))(*(_QWORD *)a1 + 48LL))(a1, v23, (unsigned int)v29, v27);
      DpContext::ReleaseHdc((HWND *)a2, v23, 0);
      if ( v26 )
      {
LABEL_25:
        ConvertRegionToGdi::~ConvertRegionToGdi((ConvertRegionToGdi *)&v31);
        goto LABEL_20;
      }
    }
  }
  ConvertRegionToGdi::~ConvertRegionToGdi((ConvertRegionToGdi *)&v31);
  DpRegion::~DpRegion((DpRegion *)v34);
  return 1;
}

```

## disassembly

```asm
0x180137dd0  mov     [rsp-8+arg_18], rbx
0x180137dd5  push    rbp
0x180137dd6  push    rsi
0x180137dd7  push    rdi
0x180137dd8  push    r12
0x180137dda  push    r13
0x180137ddc  push    r14
0x180137dde  push    r15
0x180137de0  lea     rbp, [rsp-320h]
0x180137de8  sub     rsp, 420h
0x180137def  mov     rax, cs:__security_cookie
0x180137df6  xor     rax, rsp
0x180137df9  mov     [rbp+350h+var_40], rax
0x180137e00  mov     rbx, [rbp+350h+arg_20]
0x180137e07  mov     r14, rdx
0x180137e0a  mov     r13, [rbp+350h+arg_28]
0x180137e11  mov     rdi, rcx
0x180137e14  xor     edx, edx; int
0x180137e16  mov     [rsp+450h+var_408], r8
0x180137e1b  lea     rcx, [rbp+350h+var_3D0]; this
0x180137e1f  mov     r15, r8
0x180137e22  call    ??0DpRegion@@QEAA@H@Z; DpRegion::DpRegion(int)
0x180137e27  xor     r11d, r11d
0x180137e2a  cmp     [rdi+70h], r11d
0x180137e2e  jz      short loc_180137E80
0x180137e30  mov     eax, [r14+144h]
0x180137e37  lea     rcx, [rbp+350h+var_3D0]; this
0x180137e3b  mov     r8d, [r14+13Ch]; int
0x180137e42  sub     eax, r8d
0x180137e45  mov     r9d, [r14+140h]
0x180137e4c  mov     edx, [r14+138h]; int
0x180137e53  sub     r9d, edx; int
0x180137e56  mov     dword ptr [rsp+450h+var_430], eax; int
0x180137e5a  call    ?Set@DpRegion@@QEAAXHHHH@Z; DpRegion::Set(int,int,int,int)
0x180137e5f  mov     rdx, rbx
0x180137e62  lea     rcx, [rbp+350h+var_3D0]
0x180137e66  call    ?And@DpRegion@@QEAA?AW4Status@@PEBV1@@Z; DpRegion::And(DpRegion const *)
0x180137e6b  cmp     [rbp+350h+var_3D0], 67526431h
0x180137e72  lea     rax, [rbp+350h+var_3D0]
0x180137e76  cmovnz  rax, rbx
0x180137e7a  xor     r11d, r11d
0x180137e7d  mov     rbx, rax
0x180137e80  mov     eax, [rbx+8]
0x180137e83  mov     ecx, [rbx+0Ch]
0x180137e86  mov     edx, [rbx+10h]
0x180137e89  sub     edx, eax
0x180137e8b  mov     dword ptr [rsp+450h+var_400], eax
0x180137e8f  mov     eax, [rbx+14h]
0x180137e92  sub     eax, ecx
0x180137e94  mov     dword ptr [rsp+450h+var_400+4], ecx
0x180137e98  test    byte ptr [rbx+4], 2
0x180137e9c  mov     dword ptr [rsp+450h+var_400+8], edx
0x180137ea0  mov     dword ptr [rsp+450h+var_400+0Ch], eax
0x180137ea4  jnz     loc_180138001
0x180137eaa  test    edx, edx
0x180137eac  jle     loc_180138001
0x180137eb2  test    eax, eax
0x180137eb4  jle     loc_180138001
0x180137eba  mov     r12d, r11d
0x180137ebd  cmp     [rdi+70h], r11d
0x180137ec1  jz      short loc_180137F01
0x180137ec3  mov     eax, [r15+0Ch]
0x180137ec7  and     eax, 0FF00h
0x180137ecc  cmp     eax, 800h
0x180137ed1  ja      short loc_180137F01
0x180137ed3  mov     rax, [r14+2A0h]
0x180137eda  test    rax, rax
0x180137edd  jz      short loc_180137F01
0x180137edf  cmp     [rax+108h], r11d
0x180137ee6  jnz     short loc_180137F01
0x180137ee8  cmp     [r13+0], r11d
0x180137eec  jnz     short loc_180137EFB
0x180137eee  mov     edx, [r13+4]
0x180137ef2  call    ?IsVGAOrSystemColor@DriverMeta@@AEAAHVGpColor@GpRuntime@@@Z; DriverMeta::IsVGAOrSystemColor(GpRuntime::GpColor)
0x180137ef7  test    eax, eax
0x180137ef9  jnz     short loc_180137F01
0x180137efb  mov     r12d, 1
0x180137f01  lea     r9, [rsp+450h+var_40C]; int *
0x180137f06  mov     [rsp+450h+var_410], r11d
0x180137f0b  lea     r8, [rsp+450h+var_410]; unsigned int *
0x180137f10  mov     [rsp+450h+var_40C], r11d
0x180137f15  mov     rdx, r13; struct DpBrush *
0x180137f18  mov     dword ptr [rsp+450h+var_430], r12d; struct GpRuntime::GpRect *
0x180137f1d  mov     rcx, rdi; this
0x180137f20  call    ?GetBrush@DriverMeta@@AEBAPEAUHBRUSH__@@PEBUDpBrush@@PEAIPEAHH@Z; DriverMeta::GetBrush(DpBrush const *,uint *,int *,int)
0x180137f25  mov     rsi, rax
0x180137f28  test    rax, rax
0x180137f2b  jnz     loc_18013804C
0x180137f31  mov     rdx, rbx; struct DpRegion *
0x180137f34  lea     rcx, [rbp+350h+var_370]; this
0x180137f38  call    ??0GpPath@@QEAA@PEBVDpRegion@@@Z; GpPath::GpPath(DpRegion const *)
0x180137f3d  xor     ecx, ecx
0x180137f3f  cmp     [rbp+350h+var_368], 68745031h
0x180137f46  setz    cl
0x180137f49  test    ecx, ecx
0x180137f4b  jz      loc_180138043
0x180137f51  or      [rbp+350h+var_39C], 0FFFFFFFFh
0x180137f55  lea     rax, ??_7GpMatrix@@6B@; const GpMatrix::`vftable'
0x180137f5c  and     [rbp+350h+var_384], esi
0x180137f5f  lea     r9d, [rsi+10h]; unsigned int
0x180137f63  and     [rbp+350h+var_388], esi
0x180137f66  lea     r8, [rbp+350h+var_3A8]; struct GpMatrix *
0x180137f6a  and     [rbp+350h+var_390], esi
0x180137f6d  lea     rdx, [rbp+350h+var_370]; struct DpPath *
0x180137f71  and     [rbp+350h+var_394], esi
0x180137f74  lea     rcx, [rbp+350h+var_200]; this
0x180137f7b  and     [rbp+350h+var_380], esi
0x180137f7e  and     [rsp+450h+var_430], rsi
0x180137f83  mov     [rbp+350h+var_3A8], rax
0x180137f87  mov     [rbp+350h+var_38C], 3F800000h
0x180137f8e  mov     [rbp+350h+var_398], 3F800000h
0x180137f95  mov     [rbp+350h+var_3A0], 74614D31h
0x180137f9c  call    ??0ConvertPathToGdi@@QEAA@PEBVDpPath@@PEAVGpMatrix@@KPEBVGpRect@GpRuntime@@@Z; ConvertPathToGdi::ConvertPathToGdi(DpPath const *,GpMatrix *,ulong,GpRuntime::GpRect const *)
0x180137fa1  cmp     [rbp+350h+var_200], 47764331h
0x180137fab  jnz     loc_180138037
0x180137fb1  movaps  xmm0, [rsp+450h+var_400]
0x180137fb6  lea     rax, [rbp+350h+var_200]
0x180137fbd  mov     [rsp+450h+var_420], r12d
0x180137fc2  mov     r9, r13
0x180137fc5  mov     [rsp+450h+var_428], rax
0x180137fca  mov     r8, r15
0x180137fcd  lea     rax, [rsp+450h+var_400]
0x180137fd2  movdqa  [rsp+450h+var_400], xmm0
0x180137fd8  mov     rdx, r14
0x180137fdb  mov     [rsp+450h+var_430], rax
0x180137fe0  mov     rcx, rdi
0x180137fe3  call    ?BrushFillUsingBitmap@DriverMeta@@QEAA?AW4Status@@PEAVDpContext@@PEAVDpBitmap@@PEBUDpBrush@@AEAVGpRect@GpRuntime@@PEAVConvertPathToGdi@@H@Z; DriverMeta::BrushFillUsingBitmap(DpContext *,DpBitmap *,DpBrush const *,GpRuntime::GpRect &,ConvertPathToGdi *,int)
0x180137fe8  test    eax, eax
0x180137fea  jnz     short loc_180138037
0x180137fec  lea     rcx, [rbp+350h+var_200]; this
0x180137ff3  call    ??1ConvertPathToGdi@@QEAA@XZ; ConvertPathToGdi::~ConvertPathToGdi(void)
0x180137ff8  lea     rcx, [rbp+350h+var_370]; this
0x180137ffc  call    ??1GpPath@@UEAA@XZ; GpPath::~GpPath(void)
0x180138001  lea     rcx, [rbp+350h+var_3D0]; this
0x180138005  call    ??1DpRegion@@QEAA@XZ; DpRegion::~DpRegion(void)
0x18013800a  xor     eax, eax
0x18013800c  mov     rcx, [rbp+350h+var_40]
0x180138013  xor     rcx, rsp; StackCookie
0x180138016  call    __security_check_cookie
0x18013801b  mov     rbx, [rsp+450h+arg_18]
0x180138023  add     rsp, 420h
0x18013802a  pop     r15
0x18013802c  pop     r14
0x18013802e  pop     r13
0x180138030  pop     r12
0x180138032  pop     rdi
0x180138033  pop     rsi
0x180138034  pop     rbp
0x180138035  retn
0x180138037  lea     rcx, [rbp+350h+var_200]; this
0x18013803e  call    ??1ConvertPathToGdi@@QEAA@XZ; ConvertPathToGdi::~ConvertPathToGdi(void)
0x180138043  lea     rcx, [rbp+350h+var_370]; this
0x180138047  call    ??1GpPath@@UEAA@XZ; GpPath::~GpPath(void)
0x18013804c  mov     rdx, rbx; struct DpRegion *
0x18013804f  lea     rcx, [rsp+450h+var_3F0]; this
0x180138054  call    ??0ConvertRegionToGdi@@QEAA@PEBVDpRegion@@@Z; ConvertRegionToGdi::ConvertRegionToGdi(DpRegion const *)
0x180138059  cmp     [rsp+450h+var_3F0], 47764331h
0x180138061  jnz     loc_18013819D
0x180138067  mov     r15d, [rsp+450h+var_410]
0x18013806c  cmp     r15d, 2
0x180138070  jnb     short loc_18013807E
0x180138072  lea     rcx, [rsp+450h+var_3F0]; this
0x180138077  call    ??1ConvertRegionToGdi@@QEAA@XZ; ConvertRegionToGdi::~ConvertRegionToGdi(void)
0x18013807c  jmp     short loc_180138001
0x18013807e  test    rsi, rsi
0x180138081  jnz     short loc_1801380A8
0x180138083  mov     rcx, r13; struct DpBrush *
0x180138086  call    ?ToCOLORREF@@YAKPEBUDpBrush@@@Z; ToCOLORREF(DpBrush const *)
0x18013808b  mov     edx, eax; unsigned int
0x18013808d  lea     rcx, [rdi+28h]; this
0x180138091  xor     r9d, r9d; int
0x180138094  mov     r8d, r12d; int
0x180138097  call    ?SetColor@ConvertBrushToGdi@@QEAAXKHH@Z; ConvertBrushToGdi::SetColor(ulong,int,int)
0x18013809c  lea     rcx, [rdi+28h]; this
0x1801380a0  call    ?GetGdiBrush@ConvertBrushToGdi@@QEAAPEAUHBRUSH__@@XZ; ConvertBrushToGdi::GetGdiBrush(void)
0x1801380a5  mov     rsi, rax
0x1801380a8  mov     rdx, [rsp+450h+var_408]; struct DpBitmap *
0x1801380ad  mov     rcx, r14; this
0x1801380b0  call    ?GetHdc@DpContext@@QEAAPEAUHDC__@@PEAVDpBitmap@@@Z; DpContext::GetHdc(DpBitmap *)
0x1801380b5  xor     r12d, r12d
0x1801380b8  mov     rbx, rax
0x1801380bb  test    rax, rax
0x1801380be  jz      loc_18013819D
0x1801380c4  mov     rcx, [rdi]
0x1801380c7  lea     r9, [rsp+450h+var_3EC]
0x1801380cc  mov     [rsp+450h+var_420], r12d
0x1801380d1  mov     r8, r14
0x1801380d4  mov     rdx, rbx
0x1801380d7  mov     dword ptr [rsp+450h+var_408], r12d
0x1801380dc  mov     [rsp+450h+var_410], 1
0x1801380e4  mov     rax, [rcx+28h]
0x1801380e8  lea     rcx, [rsp+450h+var_410]
0x1801380ed  mov     [rsp+450h+var_428], rcx
0x1801380f2  lea     rcx, [rsp+450h+var_408]
0x1801380f7  mov     [rsp+450h+var_430], rcx
0x1801380fc  mov     rcx, rdi
0x1801380ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180138104  cmp     r15d, 0FDh
0x18013810b  ja      short loc_18013813A
0x18013810d  lea     r8d, [r12+1]; int
0x180138112  mov     edx, r15d; unsigned int
0x180138115  mov     rcx, rdi; this
0x180138118  call    ?GetAlphaMaskBrush@DriverMeta@@AEBAPEAUHBRUSH__@@IH@Z; DriverMeta::GetAlphaMaskBrush(uint,int)
0x18013811d  test    rax, rax
0x180138120  jz      short loc_18013813A
0x180138122  mov     r9, rax; HBRUSH
0x180138125  lea     rcx, [rsp+450h+var_3F0]; this
0x18013812a  mov     r8, rsi; HBRUSH
0x18013812d  mov     rdx, rbx; HDC
0x180138130  call    ?AlphaFill@ConvertRegionToGdi@@QEAAHPEAUHDC__@@PEAUHBRUSH__@@1@Z; ConvertRegionToGdi::AlphaFill(HDC__ *,HBRUSH__ *,HBRUSH__ *)
0x180138135  mov     r15d, eax
0x180138138  jmp     short loc_18013816A
0x18013813a  mov     rdx, [rsp+450h+hrgn]; hrgn
0x18013813f  mov     r8, rsi; hbr
0x180138142  mov     rcx, rbx; hdc
0x180138145  call    cs:__imp_FillRgn
0x18013814c  nop     dword ptr [rax+rax+00h]
0x180138151  mov     r15d, eax
0x180138154  cmp     [rsp+450h+var_40C], r12d
0x180138159  jz      short loc_18013816A
0x18013815b  mov     rcx, rsi; ho
0x18013815e  call    cs:__imp_DeleteObject
0x180138165  nop     dword ptr [rax+rax+00h]
0x18013816a  mov     rax, [rdi]
0x18013816d  mov     rdx, rbx
0x180138170  mov     r9d, [rsp+450h+var_410]
0x180138175  mov     rcx, rdi
0x180138178  mov     r8d, dword ptr [rsp+450h+var_408]
0x18013817d  mov     rax, [rax+30h]
0x180138181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180138186  xor     r8d, r8d; struct DpBitmap *
0x180138189  mov     rdx, rbx; HDC
0x18013818c  mov     rcx, r14; this
0x18013818f  call    ?ReleaseHdc@DpContext@@QEAAXPEAUHDC__@@PEAVDpBitmap@@@Z; DpContext::ReleaseHdc(HDC__ *,DpBitmap *)
0x180138194  test    r15d, r15d
0x180138197  jnz     loc_180138072
0x18013819d  lea     rcx, [rsp+450h+var_3F0]; this
0x1801381a2  call    ??1ConvertRegionToGdi@@QEAA@XZ; ConvertRegionToGdi::~ConvertRegionToGdi(void)
0x1801381a7  lea     rcx, [rbp+350h+var_3D0]; this
0x1801381ab  call    ??1DpRegion@@QEAA@XZ; DpRegion::~DpRegion(void)
0x1801381b0  mov     eax, 1
0x1801381b5  jmp     loc_18013800C
```
