# EpScanEngine::Start(DpDriver *,DpContext *,DpBitmap *,void * (EpScan::**)(int,int,int,int,int,unsigned __int64 *),EpScanType,int,int,ulong)

- ea: `0x1800902e0`
- end: `0x1800906cd`
- name: `?Start@EpScanEngine@@UEAAHPEAVDpDriver@@PEAVDpContext@@PEAVDpBitmap@@PEAP8EpScan@@EAAPEAXHHHHHPEA_K@ZW4EpScanType@@HHK@Z`
- size: `1005`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, void *(**)(EpScanEngine *__hidden this, int, int, int, int, int, unsigned __int64 *), int, int, int, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180016660`
- `0x180017b00`
- `0x18001f950`
- `0x1800902e0`
- `0x1800e5044`
- `0x1800e9380`
- `0x1800ea0ec`
- `0x180175010`

## import_xrefs

- `GDI32!SelectObject` at `0x18009063d`
- `GDI32!SelectObject` at `0x18009063d`
- `GDI32!DeleteObject` at `0x1800905eb`
- `GDI32!DeleteObject` at `0x1800905eb`

## pseudocode

```c
__int64 __fastcall EpScanEngine::Start(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        void *(**a5)(EpScanEngine *__hidden this, int, int, int, int, int, unsigned __int64 *),
        int a6,
        int a7,
        int a8,
        int a9)
{
  bool v13; // zf
  void *(*v14)(EpScanEngine *__hidden, int, int, int, int, int, unsigned __int64 *); // rax
  __int64 v15; // r8
  __int64 v16; // rbx
  unsigned __int64 v17; // r15
  _DWORD *v18; // rsi
  __int64 v19; // rax
  __m128i si128; // xmm0
  __int64 v21; // r9
  __int64 v22; // rdx
  __m128i v23; // xmm0
  int v24; // edx
  __int64 v25; // r9
  __int64 v26; // rdx
  __int64 result; // rax
  _QWORD *v28; // rcx
  __int64 v29; // rbx
  __int64 v30; // rdx
  void *v31; // rcx
  HBITMAP SemiCompatibleDIB; // rax
  HDC v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rax
  _QWORD *v36; // rdx
  __int64 v37; // r8
  void **v38; // [rsp+20h] [rbp-E0h]
  void **v39; // [rsp+20h] [rbp-E0h]
  int v40; // [rsp+28h] [rbp-D8h]
  int v41; // [rsp+28h] [rbp-D8h]
  int v42; // [rsp+30h] [rbp-D0h]
  int v43; // [rsp+30h] [rbp-D0h]
  int v44; // [rsp+38h] [rbp-C8h]
  int v45; // [rsp+38h] [rbp-C8h]
  __int64 v46; // [rsp+40h] [rbp-C0h]
  __int64 v47; // [rsp+40h] [rbp-C0h]
  unsigned int v48; // [rsp+80h] [rbp-80h]
  __int64 v49; // [rsp+88h] [rbp-78h] BYREF
  __int64 v50; // [rsp+90h] [rbp-70h]
  int v51; // [rsp+98h] [rbp-68h]
  __m128i v52; // [rsp+A0h] [rbp-60h]
  int v53; // [rsp+B0h] [rbp-50h]
  int v54; // [rsp+B4h] [rbp-4Ch]
  int v55; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v56[12]; // [rsp+C4h] [rbp-3Ch] BYREF
  int v57; // [rsp+D0h] [rbp-30h]
  __int64 v58; // [rsp+E8h] [rbp-18h]

  *(_DWORD *)(a1 + 8) = 0;
  *(_DWORD *)(a1 + 12) = 0;
  *(_DWORD *)(a1 + 652) = a6;
  *(_DWORD *)(a1 + 648) = a7;
  *(_DWORD *)(a1 + 1280) = a8;
  *(_DWORD *)(a1 + 1284) = 1;
  *(_DWORD *)(a1 + 16) = *(_DWORD *)(a3 + 36);
  *(_DWORD *)(a1 + 20) = *(_DWORD *)(a3 + 40);
  *(_QWORD *)(a1 + 1320) = a4;
  if ( *(_DWORD *)(a4 + 88) == 3 )
  {
    memset_0(v56, 0, 0x84u);
    v55 = 136;
    if ( (*(int (__fastcall **)(_QWORD, _QWORD, int *, __int64, _QWORD))(**(_QWORD **)(a4 + 72) + 200LL))(
           *(_QWORD *)(a4 + 72),
           0,
           &v55,
           1,
           0) < 0 )
      return 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 1320) + 104LL) = v58;
    *(_DWORD *)(*(_QWORD *)(a1 + 1320) + 120LL) = v57;
  }
  *(_QWORD *)(a1 + 1296) = 0;
  *(_DWORD *)(a1 + 1312) = *(_DWORD *)(a4 + 120);
  *(_QWORD *)(a1 + 1304) = *(_QWORD *)(a4 + 104);
  v13 = *(_DWORD *)(a1 + 1328) == 0;
  *(_DWORD *)(a1 + 1316) = ((*(int *)(a4 + 12) >> 8) & 0xF8u) >> 3;
  v14 = EpScanEngine::NextBufferWithBounds;
  v15 = *(unsigned int *)(a4 + 12);
  if ( v13 )
    v14 = (void *(*)(EpScanEngine *__hidden, int, int, int, int, int, unsigned __int64 *))EpScanEngine::NextBuffer;
  *a5 = v14;
  v16 = *(_QWORD *)(a2 + 32);
  v17 = *(int *)(a4 + 4);
  v48 = v15;
  v18 = (_DWORD *)(v16 + 12);
  if ( (int)v17 > *(_DWORD *)(v16 + 12) )
  {
    v31 = *(void **)(v16 + 16);
    if ( v31 )
      DeleteObject(v31);
    SemiCompatibleDIB = CreateSemiCompatibleDIB(
                          *(HDC *)(v16 + 1504),
                          v17,
                          1,
                          *(struct ColorPalette **)(v16 + 1576),
                          (void **)(v16 + 32),
                          (int *)(v16 + 80),
                          0);
    *(_QWORD *)(v16 + 16) = SemiCompatibleDIB;
    if ( SemiCompatibleDIB )
    {
      v33 = *(HDC *)(v16 + 24);
      *v18 = v17;
      SelectObject(v33, SemiCompatibleDIB);
    }
    else
    {
      *v18 = 0;
    }
    v34 = *(_QWORD *)(v16 + 40);
    if ( v34 )
      GpFree(v34);
    if ( is_mul_ok(0x28u, v17)
      && (v35 = GpMallocEx(40 * v17, (0x28 * (unsigned __int128)v17) >> 64), (*(_QWORD *)(v16 + 40) = v35) != 0) )
    {
      v36 = (_QWORD *)(v16 + 48);
      v37 = 4;
      do
      {
        *v36 = *(v36 - 1) + 8 * v17;
        ++v36;
        --v37;
      }
      while ( v37 );
    }
    else
    {
      *v18 = 0;
    }
    v15 = v48;
  }
  if ( a1 != -1352 )
  {
    v28 = (_QWORD *)(a1 + 1352);
    v29 = v16 - (a1 + 1352);
    v30 = 5;
    do
    {
      *v28 = *(_QWORD *)((char *)v28 + v29 + 40);
      ++v28;
      --v30;
    }
    while ( v30 );
  }
  if ( *v18 )
  {
    v19 = *(int *)(a4 + 4);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v51 = 0;
    *(_QWORD *)(a1 + 1392) = 16 * v19;
    v21 = *(unsigned int *)(a1 + 648);
    v22 = *(unsigned int *)(a1 + 652);
    v49 = a1 + 168;
    v46 = *(_QWORD *)(a3 + 664);
    v44 = *(_DWORD *)(a3 + 44);
    v42 = *(_DWORD *)(a3 + 32);
    v40 = *(_DWORD *)(a3 + 28);
    v38 = *(void ***)(a3 + 672);
    v50 = a1 + 1352;
    v52 = si128;
    v53 = 1;
    v54 = 2;
    EpAlphaBlender::BuildPipeline(a1 + 24, v22, v15, v21, v38, v40, v42, v44, v46, a1 + 1352, 1, 0, a9, &v49, 1);
    v23 = _mm_load_si128((const __m128i *)&_xmm);
    *(_QWORD *)(v49 - 8) = 0;
    v24 = *(_DWORD *)(a3 + 44);
    v25 = *(unsigned int *)(a1 + 1280);
    v49 = a1 + 800;
    v47 = *(_QWORD *)(a3 + 664);
    v45 = v24;
    v43 = *(_DWORD *)(a3 + 32);
    v41 = *(_DWORD *)(a3 + 28);
    v39 = *(void ***)(a3 + 672);
    v26 = *(unsigned int *)(a1 + 1284);
    v50 = a1 + 1352;
    v52 = v23;
    v51 = 0;
    v53 = 1;
    v54 = 2;
    EpAlphaBlender::BuildPipeline(a1 + 656, v26, v48, v25, v39, v41, v43, v45, v47, a1 + 1352, 1, 0, a9, &v49, 1);
    result = 1;
    *(_QWORD *)(v49 - 8) = 0;
    return result;
  }
  return 0;
}

```

## disassembly

```asm
0x1800902e0  mov     [rsp-8+arg_10], rbx
0x1800902e5  push    rbp
0x1800902e6  push    rsi
0x1800902e7  push    rdi
0x1800902e8  push    r12
0x1800902ea  push    r13
0x1800902ec  push    r14
0x1800902ee  push    r15
0x1800902f0  lea     rbp, [rsp-60h]
0x1800902f5  sub     rsp, 160h
0x1800902fc  mov     rax, cs:__security_cookie
0x180090303  xor     rax, rsp
0x180090306  mov     [rbp+90h+var_40], rax
0x18009030a  and     dword ptr [rcx+8], 0
0x18009030e  mov     r14, r9
0x180090311  and     dword ptr [rcx+0Ch], 0
0x180090315  mov     r13, r8
0x180090318  mov     eax, [rbp+90h+arg_28]
0x18009031e  mov     rsi, rdx
0x180090321  mov     rbx, [rbp+90h+arg_20]
0x180090328  mov     rdi, rcx
0x18009032b  mov     [rcx+28Ch], eax
0x180090331  mov     eax, [rbp+90h+arg_30]
0x180090337  mov     [rcx+288h], eax
0x18009033d  mov     eax, [rbp+90h+arg_38]
0x180090343  mov     [rcx+500h], eax
0x180090349  mov     dword ptr [rcx+504h], 1
0x180090353  mov     eax, [r8+24h]
0x180090357  mov     [rcx+10h], eax
0x18009035a  mov     eax, [r8+28h]
0x18009035e  mov     [rcx+14h], eax
0x180090361  mov     [rcx+528h], r9
0x180090368  cmp     dword ptr [r9+58h], 3
0x18009036d  jz      loc_180090551
0x180090373  and     qword ptr [rdi+510h], 0
0x18009037b  lea     rcx, ?NextBuffer@EpScanEngine@@AEAAPEAXHHHHHPEA_K@Z; EpScanEngine::NextBuffer(int,int,int,int,int,unsigned __int64 *)
0x180090382  mov     eax, [r14+78h]
0x180090386  lea     r12, [rdi+548h]
0x18009038d  mov     [rdi+520h], eax
0x180090393  mov     rax, [r14+68h]
0x180090397  mov     [rdi+518h], rax
0x18009039e  mov     eax, [r14+0Ch]
0x1800903a2  sar     eax, 8
0x1800903a5  and     eax, 0F8h
0x1800903aa  shr     eax, 3
0x1800903ad  cmp     dword ptr [rdi+530h], 0
0x1800903b4  mov     [rdi+524h], eax
0x1800903ba  lea     rax, ?NextBufferWithBounds@EpScanEngine@@AEAAPEAXHHHHHPEA_K@Z; EpScanEngine::NextBufferWithBounds(int,int,int,int,int,unsigned __int64 *)
0x1800903c1  mov     r8d, [r14+0Ch]
0x1800903c5  cmovz   rax, rcx
0x1800903c9  mov     [rbx], rax
0x1800903cc  mov     rbx, [rsi+20h]
0x1800903d0  movsxd  r15, dword ptr [r14+4]
0x1800903d4  mov     [rbp+90h+var_110], r8d
0x1800903d8  lea     rsi, [rbx+0Ch]
0x1800903dc  cmp     r15d, [rsi]
0x1800903df  jg      loc_1800905E2
0x1800903e5  test    r12, r12
0x1800903e8  jnz     loc_1800905C0
0x1800903ee  cmp     dword ptr [rsi], 0
0x1800903f1  jz      loc_180090596
0x1800903f7  movsxd  rax, dword ptr [r14+4]
0x1800903fb  lea     rcx, [rdi+18h]
0x1800903ff  movdqa  xmm0, cs:__xmm@00000000000000010000000000000000
0x180090407  mov     r14d, 1
0x18009040d  mov     ebx, [rbp+90h+arg_40]
0x180090413  and     [rbp+90h+var_F8], 0
0x180090417  mov     [rsp+190h+var_120], r14d
0x18009041c  shl     rax, 4
0x180090420  lea     esi, [r14+1]
0x180090424  mov     [rdi+570h], rax
0x18009042b  lea     rax, [rcx+90h]
0x180090432  mov     r9d, [rcx+270h]
0x180090439  mov     edx, [rcx+274h]
0x18009043f  mov     [rbp+90h+var_108], rax
0x180090443  lea     rax, [rbp+90h+var_108]
0x180090447  mov     [rsp+190h+var_128], rax
0x18009044c  mov     rax, [r13+298h]
0x180090453  mov     [rsp+190h+var_130], ebx
0x180090457  and     [rsp+190h+var_138], 0
0x18009045c  mov     [rsp+190h+var_140], r14d
0x180090461  mov     [rsp+190h+var_148], r12
0x180090466  mov     [rsp+190h+var_150], rax
0x18009046b  mov     eax, [r13+2Ch]
0x18009046f  mov     [rsp+190h+var_158], eax
0x180090473  mov     eax, [r13+20h]
0x180090477  mov     [rsp+190h+var_160], eax
0x18009047b  mov     eax, [r13+1Ch]
0x18009047f  mov     dword ptr [rsp+190h+var_168], eax
0x180090483  mov     rax, [r13+2A0h]
0x18009048a  mov     [rsp+190h+var_170], rax
0x18009048f  mov     [rbp+90h+var_100], r12
0x180090493  movdqu  [rbp+90h+var_F0], xmm0
0x180090498  mov     [rbp+90h+var_E0], r14d
0x18009049c  mov     [rbp+90h+var_DC], esi
0x18009049f  call    ?BuildPipeline@EpAlphaBlender@@AEAAXW4EpScanType@@HHPEBVEpPaletteMap@@W4CompositingMode@@W4CompositingQuality@@IPEBUColorPalette@@PEAPEAXHHKAEAVBuilder@1@H@Z; EpAlphaBlender::BuildPipeline(EpScanType,int,int,EpPaletteMap const *,CompositingMode,CompositingQuality,uint,ColorPalette const *,void * *,int,int,ulong,EpAlphaBlender::Builder &,int)
0x1800904a4  mov     rax, [rbp+90h+var_108]
0x1800904a8  lea     rcx, [rdi+290h]
0x1800904af  movdqa  xmm0, cs:__xmm@00000000000000010000000000000000
0x1800904b7  xor     r15d, r15d
0x1800904ba  mov     r8d, [rbp+90h+var_110]
0x1800904be  mov     [rsp+190h+var_120], r14d
0x1800904c3  mov     [rax-8], r15
0x1800904c7  lea     rax, [rcx+90h]
0x1800904ce  mov     edx, [r13+2Ch]
0x1800904d2  mov     r9d, [rcx+270h]
0x1800904d9  mov     [rbp+90h+var_108], rax
0x1800904dd  lea     rax, [rbp+90h+var_108]
0x1800904e1  mov     [rsp+190h+var_128], rax
0x1800904e6  mov     rax, [r13+298h]
0x1800904ed  mov     [rsp+190h+var_130], ebx
0x1800904f1  mov     [rsp+190h+var_138], r15d
0x1800904f6  mov     [rsp+190h+var_140], r14d
0x1800904fb  mov     [rsp+190h+var_148], r12
0x180090500  mov     [rsp+190h+var_150], rax
0x180090505  mov     [rsp+190h+var_158], edx
0x180090509  mov     edx, [r13+20h]
0x18009050d  mov     [rsp+190h+var_160], edx
0x180090511  mov     edx, [r13+1Ch]
0x180090515  mov     dword ptr [rsp+190h+var_168], edx
0x180090519  mov     rdx, [r13+2A0h]
0x180090520  mov     [rsp+190h+var_170], rdx
0x180090525  mov     edx, [rcx+274h]
0x18009052b  mov     [rbp+90h+var_100], r12
0x18009052f  movdqu  [rbp+90h+var_F0], xmm0
0x180090534  mov     [rbp+90h+var_F8], r15d
0x180090538  mov     [rbp+90h+var_E0], r14d
0x18009053c  mov     [rbp+90h+var_DC], esi
0x18009053f  call    ?BuildPipeline@EpAlphaBlender@@AEAAXW4EpScanType@@HHPEBVEpPaletteMap@@W4CompositingMode@@W4CompositingQuality@@IPEBUColorPalette@@PEAPEAXHHKAEAVBuilder@1@H@Z; EpAlphaBlender::BuildPipeline(EpScanType,int,int,EpPaletteMap const *,CompositingMode,CompositingQuality,uint,ColorPalette const *,void * *,int,int,ulong,EpAlphaBlender::Builder &,int)
0x180090544  mov     rcx, [rbp+90h+var_108]
0x180090548  mov     eax, r14d
0x18009054b  mov     [rcx-8], r15
0x18009054f  jmp     short loc_180090598
0x180090551  xor     edx, edx; Val
0x180090553  lea     rcx, [rbp+90h+var_CC]; void *
0x180090557  mov     r8d, 84h; Size
0x18009055d  call    memset_0
0x180090562  mov     [rbp+90h+var_D0], 88h
0x180090569  lea     r8, [rbp+90h+var_D0]
0x18009056d  mov     rcx, [r14+48h]
0x180090571  xor     r15d, r15d
0x180090574  xor     edx, edx
0x180090576  mov     [rsp+190h+var_170], r15
0x18009057b  mov     rax, [rcx]
0x18009057e  lea     r9d, [r15+1]
0x180090582  mov     rax, [rax+0C8h]
0x180090589  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009058e  test    eax, eax
0x180090590  jns     loc_1800906AC
0x180090596  xor     eax, eax
0x180090598  mov     rcx, [rbp+90h+var_40]
0x18009059c  xor     rcx, rsp; StackCookie
0x18009059f  call    __security_check_cookie
0x1800905a4  mov     rbx, [rsp+190h+arg_10]
0x1800905ac  add     rsp, 160h
0x1800905b3  pop     r15
0x1800905b5  pop     r14
0x1800905b7  pop     r13
0x1800905b9  pop     r12
0x1800905bb  pop     rdi
0x1800905bc  pop     rsi
0x1800905bd  pop     rbp
0x1800905be  retn
0x1800905c0  mov     rcx, r12
0x1800905c3  sub     rbx, r12
0x1800905c6  mov     edx, 5
0x1800905cb  mov     rax, [rbx+rcx+28h]
0x1800905d0  mov     [rcx], rax
0x1800905d3  lea     rcx, [rcx+8]
0x1800905d7  sub     rdx, 1
0x1800905db  jnz     short loc_1800905CB
0x1800905dd  jmp     loc_1800903EE
0x1800905e2  mov     rcx, [rbx+10h]; ho
0x1800905e6  test    rcx, rcx
0x1800905e9  jz      short loc_1800905F7
0x1800905eb  call    cs:__imp_DeleteObject
0x1800905f2  nop     dword ptr [rax+rax+00h]
0x1800905f7  and     [rsp+190h+var_160], 0
0x1800905fc  lea     rax, [rbx+50h]
0x180090600  mov     r9, [rbx+628h]; struct ColorPalette *
0x180090607  lea     rcx, [rbx+20h]
0x18009060b  mov     [rsp+190h+var_168], rax; int *
0x180090610  mov     r8d, 1; unsigned int
0x180090616  mov     [rsp+190h+var_170], rcx; void **
0x18009061b  mov     edx, r15d; unsigned int
0x18009061e  mov     rcx, [rbx+5E0h]; hdc
0x180090625  call    ?CreateSemiCompatibleDIB@@YAPEAUHBITMAP__@@PEAUHDC__@@KKPEAUColorPalette@@PEAPEAXPEAHH@Z; CreateSemiCompatibleDIB(HDC__ *,ulong,ulong,ColorPalette *,void * *,int *,int)
0x18009062a  mov     [rbx+10h], rax
0x18009062e  test    rax, rax
0x180090631  jz      short loc_1800906A0
0x180090633  mov     rcx, [rbx+18h]; hdc
0x180090637  mov     rdx, rax; h
0x18009063a  mov     [rsi], r15d
0x18009063d  call    cs:__imp_SelectObject
0x180090644  nop     dword ptr [rax+rax+00h]
0x180090649  mov     rcx, [rbx+28h]
0x18009064d  test    rcx, rcx
0x180090650  jnz     short loc_1800906A5
0x180090652  mov     ecx, 28h ; '('
0x180090657  mov     rax, r15
0x18009065a  mul     rcx
0x18009065d  test    rdx, rdx
0x180090660  jz      short loc_18009066E
0x180090662  and     dword ptr [rsi], 0
0x180090665  mov     r8d, [rbp+90h+var_110]
0x180090669  jmp     loc_1800903E5
0x18009066e  mov     rcx, rax
0x180090671  call    GpMallocEx
0x180090676  mov     [rbx+28h], rax
0x18009067a  test    rax, rax
0x18009067d  jz      short loc_180090662
0x18009067f  lea     rdx, [rbx+30h]
0x180090683  mov     r8d, 4
0x180090689  mov     rax, [rdx-8]
0x18009068d  lea     rcx, [rax+r15*8]
0x180090691  mov     [rdx], rcx
0x180090694  lea     rdx, [rdx+8]
0x180090698  sub     r8, 1
0x18009069c  jnz     short loc_180090689
0x18009069e  jmp     short loc_180090665
0x1800906a0  and     dword ptr [rsi], 0
0x1800906a3  jmp     short loc_180090649
0x1800906a5  call    GpFree
0x1800906aa  jmp     short loc_180090652
0x1800906ac  mov     rcx, [rdi+528h]
0x1800906b3  mov     rax, [rbp+90h+var_A8]
0x1800906b7  mov     [rcx+68h], rax
0x1800906bb  mov     rcx, [rdi+528h]
0x1800906c2  mov     eax, [rbp+90h+var_C0]
0x1800906c5  mov     [rcx+78h], eax
0x1800906c8  jmp     loc_180090373
```
