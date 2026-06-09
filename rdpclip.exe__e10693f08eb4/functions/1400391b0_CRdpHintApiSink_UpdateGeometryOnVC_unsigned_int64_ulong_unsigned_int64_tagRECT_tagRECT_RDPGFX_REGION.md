# CRdpHintApiSink::UpdateGeometryOnVC(unsigned __int64,ulong,unsigned __int64,tagRECT *,tagRECT *,_RDPGFX_REGION *)

- ea: `0x1400391b0`
- end: `0x140039602`
- name: `?UpdateGeometryOnVC@CRdpHintApiSink@@IEAAJ_KK0PEAUtagRECT@@1PEAU_RDPGFX_REGION@@@Z`
- size: `1106`
- prototype: `__int64 __fastcall(CRdpHintApiSink *__hidden this, unsigned __int64, unsigned int, unsigned __int64, struct tagRECT *, struct tagRECT *, struct _RDPGFX_REGION *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x140038b60`

## callees

- `0x1400030d3`
- `0x140004b1c`
- `0x140005750`
- `0x14000d350`
- `0x14000efb8`
- `0x140011054`
- `0x140032c8c`
- `0x1400391b0`
- `0x140039870`
- `0x14005a3ec`
- `0x14006a120`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003955f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003955f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003940d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003940d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400395ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400395ce`
- `WTSAPI32!WTSVirtualChannelWrite` at `0x140039555`
- `WTSAPI32!WTSVirtualChannelWrite` at `0x140039555`

## string_xrefs

- `0x140039331`: `UpdateGeometryOnVC: Geometry VC handle is NULL`
- `0x1400395a1`: `Failed to write on TSGEOMETRY_CHANNEL_NAME DVC`

## pseudocode

```c
__int64 __fastcall CRdpHintApiSink::UpdateGeometryOnVC(
        CRdpHintApiSink *this,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        struct tagRECT *a5,
        struct tagRECT *a6,
        struct _RDPGFX_REGION *a7)
{
  PVOID *v8; // rax
  int v9; // r14d
  WPP_RECTS *v10; // rsi
  WPP_RECTS *v11; // rdi
  WPP_RECTS *v12; // rbx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v14; // r8d
  signed int v15; // ebx
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // ebx
  unsigned int v19; // eax
  ULONG v20; // esi
  void *v21; // rax
  void *v22; // rdi
  unsigned int v23; // eax
  struct tagRECT *v24; // rcx
  int v25; // eax
  unsigned int v26; // eax
  int v27; // edx
  const char *v28; // rcx
  signed int LastError; // eax
  __int64 v31; // [rsp+28h] [rbp-D8h]
  unsigned int v32; // [rsp+50h] [rbp-B0h] BYREF
  ULONG pBytesWritten; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v34; // [rsp+58h] [rbp-A8h]
  __int64 v35; // [rsp+60h] [rbp-A0h]
  struct tagRECT v36; // [rsp+70h] [rbp-90h] BYREF
  struct tagRECT *v37; // [rsp+80h] [rbp-80h]
  char *v38; // [rsp+88h] [rbp-78h] BYREF
  wchar_t Buffer[72]; // [rsp+90h] [rbp-70h] BYREF
  wchar_t v40[72]; // [rsp+120h] [rbp+20h] BYREF
  wchar_t v41[72]; // [rsp+1B0h] [rbp+B0h] BYREF

  v38 = (char *)this + 56;
  v35 = a4;
  v34 = a2;
  v37 = a6;
  pBytesWritten = 0;
  CTSCriticalSection::Lock((CRdpHintApiSink *)((char *)this + 56));
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v9 = *(_DWORD *)a7;
    v36 = *(struct tagRECT *)((char *)a7 + 8);
    v10 = WPP_RECTS::WPP_RECTS(Buffer, &v36);
    v36 = *a6;
    v11 = WPP_RECTS::WPP_RECTS(v40, &v36);
    v36 = *a5;
    v12 = WPP_RECTS::WPP_RECTS(v41, &v36);
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dii_RECTS__RECTS__RECTS_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      41,
      v14,
      CurrentThreadActivityIdPrefix,
      v34,
      v35,
      (__int64)v12,
      (__int64)v11,
      (__int64)v10,
      v9);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !*((_QWORD *)this + 148) )
  {
    v15 = -2147467259;
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 8) != 0 && *((_BYTE *)v8 + 25) >= 2u )
    {
      v16 = RdpWppGetCurrentThreadActivityIdPrefix();
      LODWORD(v31) = -2147467259;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        42,
        (unsigned int)&WPP_831ea65fad7736bfdd6b23908d4018f5_Traceguids,
        v16,
        (__int64)"UpdateGeometryOnVC: Geometry VC handle is NULL",
        v31);
    }
    goto LABEL_44;
  }
  v32 = 0;
  v15 = TSMM_VIDEO_SerializeRdpGfxRegion(a7, &v32, 0);
  if ( v15 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v17 = RdpWppGetCurrentThreadActivityIdPrefix();
      LODWORD(v31) = v15;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        43,
        (unsigned int)&WPP_831ea65fad7736bfdd6b23908d4018f5_Traceguids,
        v17,
        (__int64)"TSMM_VIDEO_SerializeRdpGfxRegion() failed",
        v31);
    }
    goto LABEL_44;
  }
  v18 = v32;
  if ( v32 < 0x20 )
  {
    v15 = -2147418113;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v19 = RdpWppGetCurrentThreadActivityIdPrefix();
      LODWORD(v31) = -2147418113;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        44,
        (unsigned int)&WPP_831ea65fad7736bfdd6b23908d4018f5_Traceguids,
        v19,
        (__int64)"TSMM_VIDEO_SerializeRdpGfxRegion() returned an invalid size.",
        v31);
    }
    goto LABEL_44;
  }
  v20 = v32 + 73;
  v21 = CoTaskMemAlloc(v32 + 73);
  v22 = v21;
  if ( v21 )
  {
    memset_0(v21, 0, v18 + 73);
    v24 = v37;
    *((_QWORD *)v22 + 1) = v34;
    *((_QWORD *)v22 + 3) = v35;
    *(_DWORD *)v22 = v20;
    *((_DWORD *)v22 + 1) = 1;
    *((_QWORD *)v22 + 2) = 1;
    *((struct tagRECT *)v22 + 2) = *a5;
    *((_DWORD *)v22 + 12) = v24->left;
    *((_DWORD *)v22 + 13) = v24->top;
    *((_DWORD *)v22 + 14) = v24->right;
    *((_DWORD *)v22 + 15) = v24->bottom;
    *((_DWORD *)v22 + 16) = 2;
    *((_DWORD *)v22 + 17) = v18;
    v25 = TSMM_VIDEO_SerializeRdpGfxRegion(a7, &v32, (struct _RGNDATA *)v22 + 2);
    v15 = v25;
    if ( v25 == 1 )
    {
      v15 = -2147418113;
    }
    else if ( v25 >= 0 )
    {
      if ( WTSVirtualChannelWrite(*((HANDLE *)this + 148), (PCHAR)v22, v20, &pBytesWritten) )
        goto LABEL_43;
      LastError = GetLastError();
      v15 = LastError;
      if ( LastError > 0 )
        v15 = (unsigned __int16)LastError | 0x80070000;
      if ( v15 >= 0
        || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_43;
      }
      v26 = RdpWppGetCurrentThreadActivityIdPrefix();
      v27 = 47;
      v28 = "Failed to write on TSGEOMETRY_CHANNEL_NAME DVC";
      goto LABEL_42;
    }
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_43;
    }
    v26 = RdpWppGetCurrentThreadActivityIdPrefix();
    v27 = 46;
    v28 = "TSMM_VIDEO_SerializeBA() failed";
LABEL_42:
    LODWORD(v31) = v15;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v27,
      (unsigned int)&WPP_831ea65fad7736bfdd6b23908d4018f5_Traceguids,
      v26,
      (__int64)v28,
      v31);
LABEL_43:
    CoTaskMemFree(v22);
    goto LABEL_44;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v23 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      45,
      (unsigned int)&WPP_831ea65fad7736bfdd6b23908d4018f5_Traceguids,
      v23,
      (__int64)"\"MAPPED_WINDOW_GEOMETRY_PACKET*\"");
  }
  v15 = -2147024882;
LABEL_44:
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v38);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1400391b0  push    rbp
0x1400391b2  push    rbx
0x1400391b3  push    rsi
0x1400391b4  push    rdi
0x1400391b5  push    r12
0x1400391b7  push    r13
0x1400391b9  push    r14
0x1400391bb  push    r15
0x1400391bd  lea     rbp, [rsp-158h]
0x1400391c5  sub     rsp, 258h
0x1400391cc  mov     rax, cs:__security_cookie
0x1400391d3  xor     rax, rsp
0x1400391d6  mov     [rbp+190h+var_50], rax
0x1400391dd  mov     rbx, [rbp+190h+arg_28]
0x1400391e4  mov     r15, rcx
0x1400391e7  mov     r13, [rbp+190h+arg_20]
0x1400391ee  add     rcx, 38h ; '8'; this
0x1400391f2  mov     r12, [rbp+190h+arg_30]
0x1400391f9  mov     [rbp+190h+var_208], rcx
0x1400391fd  mov     [rsp+290h+var_230], r9
0x140039202  mov     [rsp+290h+var_238], rdx
0x140039207  mov     [rbp+190h+var_210], rbx
0x14003920b  mov     [rsp+290h+pBytesWritten], 0
0x140039213  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x140039218  mov     rax, cs:WPP_GLOBAL_Control
0x14003921f  lea     rdi, WPP_GLOBAL_Control
0x140039226  cmp     rax, rdi
0x140039229  jz      loc_1400392F3
0x14003922f  test    dword ptr [rax+1Ch], 200h
0x140039236  jz      loc_1400392F3
0x14003923c  cmp     byte ptr [rax+19h], 5
0x140039240  jb      loc_1400392F3
0x140039246  movups  xmm0, xmmword ptr [r12+8]
0x14003924c  mov     r14d, [r12]
0x140039250  lea     rdx, [rsp+290h+var_220]; struct tagRECT
0x140039255  lea     rcx, [rbp+190h+Buffer]; Buffer
0x140039259  movdqu  xmmword ptr [rsp+290h+var_220.left], xmm0
0x14003925f  call    ??0WPP_RECTS@@QEAA@UtagRECT@@@Z; WPP_RECTS::WPP_RECTS(tagRECT)
0x140039264  movups  xmm0, xmmword ptr [rbx]
0x140039267  lea     rdx, [rsp+290h+var_220]; struct tagRECT
0x14003926c  mov     rsi, rax
0x14003926f  lea     rcx, [rbp+190h+var_170]; Buffer
0x140039273  movdqu  xmmword ptr [rsp+290h+var_220.left], xmm0
0x140039279  call    ??0WPP_RECTS@@QEAA@UtagRECT@@@Z; WPP_RECTS::WPP_RECTS(tagRECT)
0x14003927e  movups  xmm0, xmmword ptr [r13+0]
0x140039283  lea     rdx, [rsp+290h+var_220]; struct tagRECT
0x140039288  mov     rdi, rax
0x14003928b  lea     rcx, [rbp+190h+var_E0]; Buffer
0x140039292  movdqu  xmmword ptr [rsp+290h+var_220.left], xmm0
0x140039298  call    ??0WPP_RECTS@@QEAA@UtagRECT@@@Z; WPP_RECTS::WPP_RECTS(tagRECT)
0x14003929d  mov     rbx, rax
0x1400392a0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400392a5  mov     rcx, [rsp+290h+var_230]
0x1400392aa  mov     edx, 29h ; ')'
0x1400392af  mov     [rsp+290h+var_248], r14d
0x1400392b4  mov     r9d, eax
0x1400392b7  mov     [rsp+290h+var_250], rsi
0x1400392bc  mov     [rsp+290h+var_258], rdi
0x1400392c1  mov     [rsp+290h+var_260], rbx
0x1400392c6  mov     [rsp+290h+var_268], rcx
0x1400392cb  mov     rcx, [rsp+290h+var_238]
0x1400392d0  mov     [rsp+290h+var_270], rcx
0x1400392d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400392dc  mov     rcx, [rcx+10h]
0x1400392e0  call    WPP_SF_Dii_RECTS__RECTS__RECTS_d
0x1400392e5  mov     rax, cs:WPP_GLOBAL_Control
0x1400392ec  lea     rdi, WPP_GLOBAL_Control
0x1400392f3  cmp     qword ptr [r15+4A0h], 0
0x1400392fb  jnz     short loc_14003935C
0x1400392fd  mov     ebx, 80004005h
0x140039302  cmp     rax, rdi
0x140039305  jz      loc_1400395D4
0x14003930b  test    byte ptr [rax+1Ch], 8
0x14003930f  jz      loc_1400395D4
0x140039315  cmp     byte ptr [rax+19h], 2
0x140039319  jb      loc_1400395D4
0x14003931f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140039324  mov     edx, 2Ah ; '*'
0x140039329  mov     dword ptr [rsp+290h+var_268], 80004005h
0x140039331  lea     rcx, aUpdategeometry; "UpdateGeometryOnVC: Geometry VC handle "...
0x140039338  mov     [rsp+290h+var_270], rcx
0x14003933d  lea     r8, WPP_831ea65fad7736bfdd6b23908d4018f5_Traceguids
0x140039344  mov     rcx, cs:WPP_GLOBAL_Control
0x14003934b  mov     r9d, eax
0x14003934e  mov     rcx, [rcx+10h]
0x140039352  call    WPP_SF_DsD
0x140039357  jmp     loc_1400395D4
0x14003935c  xor     r8d, r8d; struct _RGNDATA *
0x14003935f  mov     [rsp+290h+var_240], 0
0x140039367  lea     rdx, [rsp+290h+var_240]; unsigned int *
0x14003936c  mov     rcx, r12; struct _RDPGFX_REGION *
0x14003936f  call    ?TSMM_VIDEO_SerializeRdpGfxRegion@@YAJPEAU_RDPGFX_REGION@@PEAKPEAU_RGNDATA@@@Z; TSMM_VIDEO_SerializeRdpGfxRegion(_RDPGFX_REGION *,ulong *,_RGNDATA *)
0x140039374  mov     ebx, eax
0x140039376  test    eax, eax
0x140039378  jns     short loc_1400393B5
0x14003937a  mov     rax, cs:WPP_GLOBAL_Control
0x140039381  cmp     rax, rdi
0x140039384  jz      loc_1400395D4
0x14003938a  test    byte ptr [rax+1Ch], 8
0x14003938e  jz      loc_1400395D4
0x140039394  cmp     byte ptr [rax+19h], 2
0x140039398  jb      loc_1400395D4
0x14003939e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400393a3  mov     edx, 2Bh ; '+'
0x1400393a8  mov     dword ptr [rsp+290h+var_268], ebx
0x1400393ac  lea     rcx, aTsmmVideoSeria_1; "TSMM_VIDEO_SerializeRdpGfxRegion() fail"...
0x1400393b3  jmp     short loc_140039338
0x1400393b5  mov     ebx, [rsp+290h+var_240]
0x1400393b9  cmp     ebx, 20h ; ' '
0x1400393bc  jnb     short loc_140039405
0x1400393be  mov     ebx, 8000FFFFh
0x1400393c3  mov     rax, cs:WPP_GLOBAL_Control
0x1400393ca  cmp     rax, rdi
0x1400393cd  jz      loc_1400395D4
0x1400393d3  test    byte ptr [rax+1Ch], 8
0x1400393d7  jz      loc_1400395D4
0x1400393dd  cmp     byte ptr [rax+19h], 2
0x1400393e1  jb      loc_1400395D4
0x1400393e7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400393ec  mov     edx, 2Ch ; ','
0x1400393f1  mov     dword ptr [rsp+290h+var_268], 8000FFFFh
0x1400393f9  lea     rcx, aTsmmVideoSeria; "TSMM_VIDEO_SerializeRdpGfxRegion() retu"...
0x140039400  jmp     loc_140039338
0x140039405  lea     esi, [rbx+49h]
0x140039408  mov     ecx, esi; cb
0x14003940a  mov     r14d, esi
0x14003940d  call    cs:__imp_CoTaskMemAlloc
0x140039413  mov     rdi, rax
0x140039416  test    rax, rax
0x140039419  jnz     short loc_140039472
0x14003941b  mov     rax, cs:WPP_GLOBAL_Control
0x140039422  lea     rcx, WPP_GLOBAL_Control
0x140039429  cmp     rax, rcx
0x14003942c  jz      short loc_140039468
0x14003942e  test    byte ptr [rax+1Ch], 8
0x140039432  jz      short loc_140039468
0x140039434  cmp     byte ptr [rax+19h], 2
0x140039438  jb      short loc_140039468
0x14003943a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003943f  lea     rcx, aMappedWindowGe; "\"MAPPED_WINDOW_GEOMETRY_PACKET*\""
0x140039446  mov     r9d, eax
0x140039449  mov     [rsp+290h+var_270], rcx
0x14003944e  lea     edx, [rdi+2Dh]
0x140039451  mov     rcx, cs:WPP_GLOBAL_Control
0x140039458  lea     r8, WPP_831ea65fad7736bfdd6b23908d4018f5_Traceguids
0x14003945f  mov     rcx, [rcx+10h]
0x140039463  call    WPP_SF_Ds
0x140039468  mov     ebx, 8007000Eh
0x14003946d  jmp     loc_1400395D4
0x140039472  mov     r8, r14; Size
0x140039475  xor     edx, edx; Val
0x140039477  mov     rcx, rdi; void *
0x14003947a  call    memset_0
0x14003947f  mov     rcx, [rbp+190h+var_210]
0x140039483  lea     r8, [rdi+48h]; struct _RGNDATA *
0x140039487  mov     rax, [rsp+290h+var_238]
0x14003948c  lea     rdx, [rsp+290h+var_240]; unsigned int *
0x140039491  mov     [rdi+8], rax
0x140039495  mov     r14d, 1
0x14003949b  mov     rax, [rsp+290h+var_230]
0x1400394a0  mov     [rdi+18h], rax
0x1400394a4  mov     [rdi], esi
0x1400394a6  mov     [rdi+4], r14d
0x1400394aa  mov     [rdi+10h], r14
0x1400394ae  mov     eax, [r13+0]
0x1400394b2  mov     [rdi+20h], eax
0x1400394b5  mov     eax, [r13+4]
0x1400394b9  mov     [rdi+24h], eax
0x1400394bc  mov     eax, [r13+8]
0x1400394c0  mov     [rdi+28h], eax
0x1400394c3  mov     eax, [r13+0Ch]
0x1400394c7  mov     [rdi+2Ch], eax
0x1400394ca  mov     eax, [rcx]
0x1400394cc  mov     [rdi+30h], eax
0x1400394cf  mov     eax, [rcx+4]
0x1400394d2  mov     [rdi+34h], eax
0x1400394d5  mov     eax, [rcx+8]
0x1400394d8  mov     [rdi+38h], eax
0x1400394db  mov     eax, [rcx+0Ch]
0x1400394de  mov     rcx, r12; struct _RDPGFX_REGION *
0x1400394e1  mov     [rdi+3Ch], eax
0x1400394e4  mov     dword ptr [rdi+40h], 2
0x1400394eb  mov     [rdi+44h], ebx
0x1400394ee  call    ?TSMM_VIDEO_SerializeRdpGfxRegion@@YAJPEAU_RDPGFX_REGION@@PEAKPEAU_RGNDATA@@@Z; TSMM_VIDEO_SerializeRdpGfxRegion(_RDPGFX_REGION *,ulong *,_RGNDATA *)
0x1400394f3  mov     ebx, eax
0x1400394f5  cmp     eax, r14d
0x1400394f8  jnz     short loc_140039501
0x1400394fa  mov     ebx, 8000FFFFh
0x1400394ff  jmp     short loc_140039505
0x140039501  test    eax, eax
0x140039503  jns     short loc_140039543
0x140039505  mov     rax, cs:WPP_GLOBAL_Control
0x14003950c  lea     rcx, WPP_GLOBAL_Control
0x140039513  cmp     rax, rcx
0x140039516  jz      loc_1400395CB
0x14003951c  test    byte ptr [rax+1Ch], 8
0x140039520  jz      loc_1400395CB
0x140039526  cmp     byte ptr [rax+19h], 2
0x14003952a  jb      loc_1400395CB
0x140039530  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140039535  mov     edx, 2Eh ; '.'
0x14003953a  lea     rcx, aTsmmVideoSeria_0; "TSMM_VIDEO_SerializeBA() failed"
0x140039541  jmp     short loc_1400395A8
0x140039543  mov     rcx, [r15+4A0h]; hChannelHandle
0x14003954a  lea     r9, [rsp+290h+pBytesWritten]; pBytesWritten
0x14003954f  mov     r8d, esi; Length
0x140039552  mov     rdx, rdi; Buffer
0x140039555  call    cs:__imp_WTSVirtualChannelWrite
0x14003955b  test    eax, eax
0x14003955d  jnz     short loc_1400395CB
0x14003955f  call    cs:__imp_GetLastError
0x140039565  mov     ebx, eax
0x140039567  test    eax, eax
0x140039569  jle     short loc_140039574
0x14003956b  movzx   ebx, ax
0x14003956e  or      ebx, 80070000h
0x140039574  test    ebx, ebx
0x140039576  jns     short loc_1400395CB
0x140039578  mov     rax, cs:WPP_GLOBAL_Control
0x14003957f  lea     rcx, WPP_GLOBAL_Control
0x140039586  cmp     rax, rcx
0x140039589  jz      short loc_1400395CB
0x14003958b  test    byte ptr [rax+1Ch], 8
0x14003958f  jz      short loc_1400395CB
0x140039591  cmp     byte ptr [rax+19h], 2
0x140039595  jb      short loc_1400395CB
0x140039597  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003959c  mov     edx, 2Fh ; '/'
0x1400395a1  lea     rcx, aFailedToWriteO; "Failed to write on TSGEOMETRY_CHANNEL_N"...
0x1400395a8  mov     dword ptr [rsp+290h+var_268], ebx
0x1400395ac  lea     r8, WPP_831ea65fad7736bfdd6b23908d4018f5_Traceguids
0x1400395b3  mov     [rsp+290h+var_270], rcx
0x1400395b8  mov     r9d, eax
0x1400395bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400395c2  mov     rcx, [rcx+10h]
0x1400395c6  call    WPP_SF_DsD
0x1400395cb  mov     rcx, rdi; pv
0x1400395ce  call    cs:__imp_CoTaskMemFree
0x1400395d4  lea     rcx, [rbp+190h+var_208]; this
0x1400395d8  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x1400395dd  mov     eax, ebx
0x1400395df  mov     rcx, [rbp+190h+var_50]
0x1400395e6  xor     rcx, rsp; StackCookie
0x1400395e9  call    __security_check_cookie
0x1400395ee  add     rsp, 258h
0x1400395f5  pop     r15
0x1400395f7  pop     r14
0x1400395f9  pop     r13
0x1400395fb  pop     r12
0x1400395fd  pop     rdi
0x1400395fe  pop     rsi
0x1400395ff  pop     rbx
0x140039600  pop     rbp
0x140039601  retn
```
