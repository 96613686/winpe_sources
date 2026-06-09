# ResolvePipeDimensions(IKsPin *,ulong,ulong)

- ea: `0x18000f7e0`
- end: `0x18000fbb1`
- name: `?ResolvePipeDimensions@@YAJPEAUIKsPin@@KK@Z`
- size: `977`
- prototype: `__int64 __fastcall(struct IKsPin *, int)`
- caller_count: `12`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001de40`
- `0x1800320a8`
- `0x180033074`
- `0x180033c0c`
- `0x180036064`
- `0x180036330`
- `0x180036dbc`
- `0x180038c78`
- `0x180038f1c`
- `0x18003a580`
- `0x18003a684`
- `0x18003aa30`

## callees

- `0x18000f7e0`
- `0x18000fc1c`
- `0x18001042c`
- `0x18001dd14`
- `0x18001f620`
- `0x18001ffb0`
- `0x180034a68`
- `0x180034adc`
- `0x180037b64`
- `0x1800381bc`
- `0x18003a894`
- `0x18003a8e8`
- `0x18003b214`
- `0x18003b578`
- `0x180045010`

## pseudocode

```c
__int64 __fastcall ResolvePipeDimensions(struct IKsPin *a1, int a2)
{
  __int64 v4; // rcx
  __int64 v5; // r14
  _DWORD *v6; // rbx
  __int128 v7; // xmm0
  int v8; // edi
  __int64 v9; // xmm0_8
  __int64 v10; // xmm1_8
  __int64 v11; // xmm0_8
  unsigned int Stepping; // eax
  unsigned int v13; // ecx
  int v14; // eax
  __int64 v15; // r8
  unsigned int v16; // edi
  int v18; // [rsp+20h] [rbp-E0h]
  unsigned int v19[4]; // [rsp+70h] [rbp-90h] BYREF
  struct KS_FRAMING_RANGE v20; // [rsp+80h] [rbp-80h] BYREF
  struct _GUID Buf1; // [rsp+90h] [rbp-70h] BYREF
  __int64 v22; // [rsp+A0h] [rbp-60h] BYREF
  struct KS_FRAMING_RANGE v23; // [rsp+B0h] [rbp-50h] BYREF
  struct KS_FRAMING_RANGE v24; // [rsp+C0h] [rbp-40h] BYREF
  void *v25[2]; // [rsp+D0h] [rbp-30h] BYREF
  int v26; // [rsp+E0h] [rbp-20h]
  __int64 v27; // [rsp+E4h] [rbp-1Ch]
  int v28; // [rsp+ECh] [rbp-14h]
  __int64 v29; // [rsp+F0h] [rbp-10h]
  int v30; // [rsp+F8h] [rbp-8h]
  __int64 v31; // [rsp+FCh] [rbp-4h]
  unsigned int v32; // [rsp+104h] [rbp+4h]
  unsigned int v33; // [rsp+108h] [rbp+8h]
  __int64 v34; // [rsp+10Ch] [rbp+Ch]
  int v35; // [rsp+114h] [rbp+14h]
  __int64 v36; // [rsp+118h] [rbp+18h]
  __int64 v37; // [rsp+120h] [rbp+20h]
  unsigned int v38; // [rsp+128h] [rbp+28h]
  int v39; // [rsp+12Ch] [rbp+2Ch]
  unsigned __int16 v40[16]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 v41[16]; // [rsp+150h] [rbp+50h] BYREF

  v22 = 0;
  memset_0(v25, 0, 0x60u);
  v19[0] = 0;
  *(_QWORD *)&v24.MinFrameSize = 0;
  v24.Stepping = 0;
  if ( a1->QueryInterface(a1, &GUID_e539cd90_a8b4_11d1_8189_00a0c9062802, (void **)&v22) >= 0 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    v4 = v22;
  }
  else
  {
    v4 = 0;
    v22 = 0;
  }
  v5 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v4 + 48LL))(v4, 0);
  v6 = (_DWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 56LL))(v5);
  *(_QWORD *)&v20.MinFrameSize = a1;
  v7 = *((_OWORD *)v6 + 1);
  v32 = 0;
  v26 = 1;
  *(_OWORD *)v25 = v7;
  v27 = 1;
  v28 = 1;
  v29 = 1;
  v30 = 1;
  v31 = 1;
  v33 = -1;
  v34 = 1;
  v35 = -1;
  v36 = 1;
  v37 = 0;
  v39 = 0;
  v38 = 0x80000000;
  while ( (unsigned int)FindNextPinOnPipe(a1, a2, 0, 0, v18, (struct IKsPin **)&v20) )
  {
    a1 = *(struct IKsPin **)&v20.MinFrameSize;
    a2 = 5 - (a2 != 4);
  }
  v8 = WalkPipeAndProcess(
         a1,
         a2,
         0,
         (int (*)(struct IKsPin *, unsigned int, void **, void **, int *))DimensionsCallback,
         v25,
         0);
  if ( v8 )
  {
    v6[46] = v26;
    *(_QWORD *)(v6 + 47) = v27;
    v6[49] = v28;
    *((_QWORD *)v6 + 25) = v29;
    v9 = *(_QWORD *)(v6 + 49);
    v6[52] = v30;
    *(_QWORD *)(v6 + 53) = v31;
    *v6 = HIDWORD(v37);
    v6[2] = v39;
    v6[42] = v38;
    v6[19] = HIDWORD(v34);
    v6[20] = v35;
    v6[21] = v36;
    v6[57] = v34;
    v23.Stepping = v6[51];
    v20.MinFrameSize = v32;
    v20.MaxFrameSize = v33;
    v20.Stepping = v34;
    *(_QWORD *)&v23.MinFrameSize = v9;
    ComputeRangeBasedOnCompression(&v20, (struct KS_COMPRESSION *)&v23, (struct KS_FRAMING_RANGE *)(v6 + 55));
    ResolvePhysicalRangesBasedOnDimensions((struct _ALLOCATOR_PROPERTIES_EX *)v6);
    v10 = *((_QWORD *)v6 + 8);
    v11 = *(_QWORD *)(v6 + 19);
    v23.Stepping = v6[18];
    *(_DWORD *)Buf1.Data4 = v6[21];
    *(_QWORD *)&v23.MinFrameSize = v10;
    *(_QWORD *)&Buf1.Data1 = v11;
    if ( (unsigned int)FrameRangeIntersection(
                         (struct KS_FRAMING_RANGE *)&Buf1,
                         &v23,
                         &v24,
                         (enum KS_OBJECTS_INTERSECTION *)&v20) )
    {
      Stepping = v24.Stepping;
      *(_QWORD *)(v6 + 19) = *(_QWORD *)&v24.MinFrameSize;
    }
    else
    {
      Stepping = v6[18];
      *(_QWORD *)(v6 + 19) = v10;
    }
    v6[21] = Stepping;
    *(_QWORD *)&Buf1.Data1 = *(_QWORD *)(v6 + 19);
    *(_DWORD *)Buf1.Data4 = Stepping;
    ResolveOptimalRangesBasedOnDimensions((struct _ALLOCATOR_PROPERTIES_EX *)v6, (struct KS_FRAMING_RANGE *)&Buf1);
    v13 = v6[20];
    if ( v13 == -1 )
    {
      v6[1] = 0;
      v15 = 0;
    }
    else
    {
      v14 = v6[51];
      *(_QWORD *)&Buf1.Data1 = *(_QWORD *)(v6 + 49);
      *(_DWORD *)Buf1.Data4 = v14;
      ComputeUlongBasedOnCompression(v13, (struct KS_COMPRESSION *)&Buf1, v19);
      v15 = v19[0];
      v6[1] = v19[0];
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_qddddddddd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        148,
        v15,
        v5,
        v6[46],
        v6[47],
        v6[49],
        v6[50],
        v6[52],
        v6[53],
        *v6,
        v15,
        v6[2]);
    GetFriendlyLogicalMemoryTypeNameFromId(v6[44], v41);
    Buf1 = (struct _GUID)*((_OWORD *)v6 + 2);
    GetFriendlyBusNameFromBusId(&Buf1, v40);
  }
  v16 = v8 == 0 ? 0x80004005 : 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_DSSddD(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v41, (__int64)v40, v6[18], v6[21], v6[42]);
  return v16;
}

```

## disassembly

```asm
0x18000f7e0  push    rbp
0x18000f7e2  push    rbx
0x18000f7e3  push    rsi
0x18000f7e4  push    rdi
0x18000f7e5  push    r14
0x18000f7e7  push    r15
0x18000f7e9  lea     rbp, [rsp-88h]
0x18000f7f1  sub     rsp, 188h
0x18000f7f8  mov     rax, cs:__security_cookie
0x18000f7ff  xor     rax, rsp
0x18000f802  mov     [rbp+0B0h+var_40], rax
0x18000f806  xor     r15d, r15d
0x18000f809  mov     edi, edx
0x18000f80b  mov     rsi, rcx
0x18000f80e  mov     [rbp+0B0h+var_110], r15
0x18000f812  xor     edx, edx; Val
0x18000f814  lea     rcx, [rbp+0B0h+var_E0]; void *
0x18000f818  lea     r8d, [r15+60h]; Size
0x18000f81c  call    memset_0
0x18000f821  xor     eax, eax
0x18000f823  mov     [rsp+1B0h+var_140], r15d
0x18000f828  mov     qword ptr [rbp+0B0h+var_F0.MinFrameSize], rax
0x18000f82c  lea     r8, [rbp+0B0h+var_110]
0x18000f830  mov     [rbp+0B0h+var_F0.Stepping], eax
0x18000f833  lea     rdx, _GUID_e539cd90_a8b4_11d1_8189_00a0c9062802
0x18000f83a  mov     rax, [rsi]
0x18000f83d  mov     rcx, rsi
0x18000f840  mov     rax, [rax]
0x18000f843  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f848  test    eax, eax
0x18000f84a  jns     short loc_18000F855
0x18000f84c  mov     ecx, r15d
0x18000f84f  mov     [rbp+0B0h+var_110], rcx
0x18000f853  jmp     short loc_18000F869
0x18000f855  mov     rcx, [rbp+0B0h+var_110]
0x18000f859  mov     rax, [rcx]
0x18000f85c  mov     rax, [rax+10h]
0x18000f860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f865  mov     rcx, [rbp+0B0h+var_110]
0x18000f869  mov     rax, [rcx]
0x18000f86c  xor     edx, edx
0x18000f86e  mov     rax, [rax+30h]
0x18000f872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f877  mov     r14, rax
0x18000f87a  mov     rcx, [rax]
0x18000f87d  mov     rax, [rcx+38h]
0x18000f881  mov     rcx, r14
0x18000f884  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f889  mov     rbx, rax
0x18000f88c  mov     qword ptr [rbp+0B0h+var_130.MinFrameSize], rsi
0x18000f890  movups  xmm0, xmmword ptr [rax+10h]
0x18000f894  mov     eax, 1
0x18000f899  mov     [rbp+0B0h+var_AC], r15d
0x18000f89d  mov     [rbp+0B0h+var_D0], eax
0x18000f8a0  movdqu  xmmword ptr [rbp+0B0h+var_E0], xmm0
0x18000f8a5  mov     [rbp+0B0h+var_CC], rax
0x18000f8a9  mov     [rbp+0B0h+var_C4], eax
0x18000f8ac  mov     [rbp+0B0h+var_C0], rax
0x18000f8b0  mov     [rbp+0B0h+var_B8], eax
0x18000f8b3  mov     [rbp+0B0h+var_B4], rax
0x18000f8b7  mov     [rbp+0B0h+var_A8], 0FFFFFFFFh
0x18000f8be  mov     [rbp+0B0h+var_A4], rax
0x18000f8c2  mov     [rbp+0B0h+var_9C], 0FFFFFFFFh
0x18000f8c9  mov     [rbp+0B0h+var_98], rax
0x18000f8cd  mov     [rbp+0B0h+var_90], r15
0x18000f8d1  mov     [rbp+0B0h+var_84], r15d
0x18000f8d5  mov     [rbp+0B0h+var_88], 80000000h
0x18000f8dc  jmp     short loc_18000F8EC
0x18000f8de  mov     rsi, qword ptr [rbp+0B0h+var_130.MinFrameSize]
0x18000f8e2  sub     edi, 4
0x18000f8e5  neg     edi
0x18000f8e7  sbb     edi, edi
0x18000f8e9  add     edi, 5
0x18000f8ec  lea     rax, [rbp+0B0h+var_130]
0x18000f8f0  xor     r9d, r9d; struct IKsAllocatorEx *
0x18000f8f3  xor     r8d, r8d; unsigned int
0x18000f8f6  mov     [rsp+1B0h+var_188], rax; struct IKsPin **
0x18000f8fb  mov     edx, edi; unsigned int
0x18000f8fd  mov     rcx, rsi; struct IKsPin *
0x18000f900  call    ?FindNextPinOnPipe@@YAHPEAUIKsPin@@KKPEAUIKsAllocatorEx@@HPEAPEAU1@@Z; FindNextPinOnPipe(IKsPin *,ulong,ulong,IKsAllocatorEx *,int,IKsPin * *)
0x18000f905  test    eax, eax
0x18000f907  jnz     short loc_18000F8DE
0x18000f909  lea     rax, [rbp+0B0h+var_E0]
0x18000f90d  mov     [rsp+1B0h+var_188], r15; void **
0x18000f912  lea     r9, ?DimensionsCallback@@YAHPEAUIKsPin@@KPEAPEAX1PEAH@Z; int (*)(struct IKsPin *, unsigned int, void **, void **, int *)
0x18000f919  mov     [rsp+1B0h+var_190], rax; void **
0x18000f91e  xor     r8d, r8d; struct IKsPin *
0x18000f921  mov     edx, edi; unsigned int
0x18000f923  mov     rcx, rsi; struct IKsPin *
0x18000f926  call    ?WalkPipeAndProcess@@YAHPEAUIKsPin@@K0P6AH0KPEAPEAX1PEAH@Z11@Z; WalkPipeAndProcess(IKsPin *,ulong,IKsPin *,int (*)(IKsPin *,ulong,void * *,void * *,int *),void * *,void * *)
0x18000f92b  lea     rsi, WPP_GLOBAL_Control
0x18000f932  mov     edi, eax
0x18000f934  test    eax, eax
0x18000f936  jz      loc_18000FB3E
0x18000f93c  mov     ecx, [rbp+0B0h+var_D0]
0x18000f93f  lea     r8, [rbx+0DCh]; struct KS_FRAMING_RANGE *
0x18000f946  mov     [rbx+0B8h], ecx
0x18000f94c  lea     rdx, [rbp+0B0h+var_100]; struct KS_COMPRESSION
0x18000f950  mov     ecx, dword ptr [rbp+0B0h+var_CC]
0x18000f953  mov     [rbx+0BCh], ecx
0x18000f959  mov     ecx, dword ptr [rbp+0B0h+var_CC+4]
0x18000f95c  mov     [rbx+0C0h], ecx
0x18000f962  mov     ecx, [rbp+0B0h+var_C4]
0x18000f965  mov     [rbx+0C4h], ecx
0x18000f96b  lea     rcx, [rbp+0B0h+var_130]; struct KS_FRAMING_RANGE
0x18000f96f  mov     eax, dword ptr [rbp+0B0h+var_C0]
0x18000f972  mov     [rbx+0C8h], eax
0x18000f978  mov     eax, dword ptr [rbp+0B0h+var_C0+4]
0x18000f97b  mov     [rbx+0CCh], eax
0x18000f981  mov     eax, [rbp+0B0h+var_B8]
0x18000f984  movsd   xmm0, qword ptr [rbx+0C4h]
0x18000f98c  mov     [rbx+0D0h], eax
0x18000f992  mov     eax, dword ptr [rbp+0B0h+var_B4]
0x18000f995  mov     [rbx+0D4h], eax
0x18000f99b  mov     eax, dword ptr [rbp+0B0h+var_B4+4]
0x18000f99e  mov     [rbx+0D8h], eax
0x18000f9a4  mov     eax, dword ptr [rbp+0B0h+var_90+4]
0x18000f9a7  mov     [rbx], eax
0x18000f9a9  mov     eax, [rbp+0B0h+var_84]
0x18000f9ac  mov     [rbx+8], eax
0x18000f9af  mov     eax, [rbp+0B0h+var_88]
0x18000f9b2  mov     [rbx+0A8h], eax
0x18000f9b8  mov     eax, dword ptr [rbp+0B0h+var_A4+4]
0x18000f9bb  mov     [rbx+4Ch], eax
0x18000f9be  mov     eax, [rbp+0B0h+var_9C]
0x18000f9c1  mov     [rbx+50h], eax
0x18000f9c4  mov     eax, dword ptr [rbp+0B0h+var_98]
0x18000f9c7  mov     [rbx+54h], eax
0x18000f9ca  mov     eax, dword ptr [rbp+0B0h+var_A4]
0x18000f9cd  mov     [r8+8], eax
0x18000f9d1  mov     eax, [rbx+0CCh]
0x18000f9d7  mov     [rbp+0B0h+var_100.Stepping], eax
0x18000f9da  mov     eax, [rbp+0B0h+var_AC]
0x18000f9dd  mov     [rbp+0B0h+var_130.MinFrameSize], eax
0x18000f9e0  mov     eax, [rbp+0B0h+var_A8]
0x18000f9e3  mov     [rbp+0B0h+var_130.MaxFrameSize], eax
0x18000f9e6  mov     eax, dword ptr [rbp+0B0h+var_A4]
0x18000f9e9  mov     [rbp+0B0h+var_130.Stepping], eax
0x18000f9ec  movsd   qword ptr [rbp+0B0h+var_100.MinFrameSize], xmm0
0x18000f9f1  call    ?ComputeRangeBasedOnCompression@@YAHUKS_FRAMING_RANGE@@UKS_COMPRESSION@@PEAU1@@Z; ComputeRangeBasedOnCompression(KS_FRAMING_RANGE,KS_COMPRESSION,KS_FRAMING_RANGE *)
0x18000f9f6  mov     rcx, rbx; struct _ALLOCATOR_PROPERTIES_EX *
0x18000f9f9  call    ?ResolvePhysicalRangesBasedOnDimensions@@YAHPEAU_ALLOCATOR_PROPERTIES_EX@@@Z; ResolvePhysicalRangesBasedOnDimensions(_ALLOCATOR_PROPERTIES_EX *)
0x18000f9fe  mov     eax, [rbx+48h]
0x18000fa01  lea     r9, [rbp+0B0h+var_130]; enum KS_OBJECTS_INTERSECTION *
0x18000fa05  movsd   xmm1, qword ptr [rbx+40h]
0x18000fa0a  lea     r8, [rbp+0B0h+var_F0]; struct KS_FRAMING_RANGE *
0x18000fa0e  movsd   xmm0, qword ptr [rbx+4Ch]
0x18000fa13  lea     rdx, [rbp+0B0h+var_100]; struct KS_FRAMING_RANGE
0x18000fa17  mov     [rbp+0B0h+var_100.Stepping], eax
0x18000fa1a  lea     rcx, [rbp+0B0h+Buf1]; struct KS_FRAMING_RANGE
0x18000fa1e  mov     eax, [rbx+54h]
0x18000fa21  mov     dword ptr [rbp+0B0h+Buf1.Data4], eax
0x18000fa24  movsd   qword ptr [rbp+0B0h+var_100.MinFrameSize], xmm1
0x18000fa29  movsd   qword ptr [rbp+0B0h+Buf1.Data1], xmm0
0x18000fa2e  call    ?FrameRangeIntersection@@YAHUKS_FRAMING_RANGE@@0PEAU1@PEAW4KS_OBJECTS_INTERSECTION@@@Z; FrameRangeIntersection(KS_FRAMING_RANGE,KS_FRAMING_RANGE,KS_FRAMING_RANGE *,KS_OBJECTS_INTERSECTION *)
0x18000fa33  test    eax, eax
0x18000fa35  jnz     short loc_18000FA41
0x18000fa37  mov     eax, [rbx+48h]
0x18000fa3a  movsd   qword ptr [rbx+4Ch], xmm1
0x18000fa3f  jmp     short loc_18000FA4E
0x18000fa41  movsd   xmm0, qword ptr [rbp+0B0h+var_F0.MinFrameSize]
0x18000fa46  mov     eax, [rbp+0B0h+var_F0.Stepping]
0x18000fa49  movsd   qword ptr [rbx+4Ch], xmm0
0x18000fa4e  mov     [rbx+54h], eax
0x18000fa51  lea     rdx, [rbp+0B0h+Buf1]; struct KS_FRAMING_RANGE
0x18000fa55  movsd   xmm0, qword ptr [rbx+4Ch]
0x18000fa5a  mov     rcx, rbx; struct _ALLOCATOR_PROPERTIES_EX *
0x18000fa5d  movsd   qword ptr [rbp+0B0h+Buf1.Data1], xmm0
0x18000fa62  mov     dword ptr [rbp+0B0h+Buf1.Data4], eax
0x18000fa65  call    ?ResolveOptimalRangesBasedOnDimensions@@YAHPEAU_ALLOCATOR_PROPERTIES_EX@@UKS_FRAMING_RANGE@@K@Z; ResolveOptimalRangesBasedOnDimensions(_ALLOCATOR_PROPERTIES_EX *,KS_FRAMING_RANGE,ulong)
0x18000fa6a  mov     ecx, [rbx+50h]; unsigned int
0x18000fa6d  cmp     ecx, 0FFFFFFFFh
0x18000fa70  jz      short loc_18000FAA1
0x18000fa72  mov     eax, [rbx+0CCh]
0x18000fa78  lea     r8, [rsp+1B0h+var_140]; unsigned int *
0x18000fa7d  movsd   xmm0, qword ptr [rbx+0C4h]
0x18000fa85  lea     rdx, [rbp+0B0h+Buf1]; struct KS_COMPRESSION
0x18000fa89  movsd   qword ptr [rbp+0B0h+Buf1.Data1], xmm0
0x18000fa8e  mov     dword ptr [rbp+0B0h+Buf1.Data4], eax
0x18000fa91  call    ?ComputeUlongBasedOnCompression@@YAHKUKS_COMPRESSION@@PEAK@Z; ComputeUlongBasedOnCompression(ulong,KS_COMPRESSION,ulong *)
0x18000fa96  mov     r8d, [rsp+1B0h+var_140]
0x18000fa9b  mov     [rbx+4], r8d
0x18000fa9f  jmp     short loc_18000FAA8
0x18000faa1  mov     [rbx+4], r15d
0x18000faa5  mov     r8d, r15d
0x18000faa8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000faaf  cmp     rcx, rsi
0x18000fab2  jz      short loc_18000FB19
0x18000fab4  cmp     byte ptr [rcx+19h], 2
0x18000fab8  jb      short loc_18000FB19
0x18000faba  mov     eax, [rbx+8]
0x18000fabd  mov     edx, 94h
0x18000fac2  mov     rcx, [rcx+10h]
0x18000fac6  mov     r9, r14
0x18000fac9  mov     [rsp+1B0h+var_150], eax
0x18000facd  mov     eax, [rbx]
0x18000facf  mov     [rsp+1B0h+var_158], r8d
0x18000fad4  mov     [rsp+1B0h+var_160], eax
0x18000fad8  mov     eax, [rbx+0D4h]
0x18000fade  mov     [rsp+1B0h+var_168], eax
0x18000fae2  mov     eax, [rbx+0D0h]
0x18000fae8  mov     dword ptr [rsp+1B0h+var_170], eax
0x18000faec  mov     eax, [rbx+0C8h]
0x18000faf2  mov     dword ptr [rsp+1B0h+var_178], eax
0x18000faf6  mov     eax, [rbx+0C4h]
0x18000fafc  mov     dword ptr [rsp+1B0h+var_180], eax
0x18000fb00  mov     eax, [rbx+0BCh]
0x18000fb06  mov     dword ptr [rsp+1B0h+var_188], eax
0x18000fb0a  mov     eax, [rbx+0B8h]
0x18000fb10  mov     dword ptr [rsp+1B0h+var_190], eax
0x18000fb14  call    WPP_SF_qddddddddd
0x18000fb19  mov     ecx, [rbx+0B0h]; unsigned int
0x18000fb1f  lea     rdx, [rbp+0B0h+var_60]; unsigned __int16 *
0x18000fb23  call    ?GetFriendlyLogicalMemoryTypeNameFromId@@YAHKPEAG@Z; GetFriendlyLogicalMemoryTypeNameFromId(ulong,ushort *)
0x18000fb28  movups  xmm0, xmmword ptr [rbx+20h]
0x18000fb2c  lea     rdx, [rbp+0B0h+var_80]; unsigned __int16 *
0x18000fb30  lea     rcx, [rbp+0B0h+Buf1]; Buf1
0x18000fb34  movdqu  xmmword ptr [rbp+0B0h+Buf1.Data1], xmm0
0x18000fb39  call    ?GetFriendlyBusNameFromBusId@@YAHU_GUID@@PEAG@Z; GetFriendlyBusNameFromBusId(_GUID,ushort *)
0x18000fb3e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb45  neg     edi
0x18000fb47  sbb     edi, edi
0x18000fb49  not     edi
0x18000fb4b  and     edi, 80004005h
0x18000fb51  cmp     rcx, rsi
0x18000fb54  jz      short loc_18000FB92
0x18000fb56  cmp     byte ptr [rcx+19h], 2
0x18000fb5a  jb      short loc_18000FB92
0x18000fb5c  mov     edx, [rbx+0A8h]
0x18000fb62  lea     rax, [rbp+0B0h+var_80]
0x18000fb66  mov     rcx, [rcx+10h]; LoggerHandle
0x18000fb6a  mov     r9d, edi
0x18000fb6d  mov     dword ptr [rsp+1B0h+var_170], edx; char
0x18000fb71  mov     edx, [rbx+54h]
0x18000fb74  mov     dword ptr [rsp+1B0h+var_178], edx; char
0x18000fb78  mov     edx, [rbx+48h]
0x18000fb7b  mov     dword ptr [rsp+1B0h+var_180], edx; char
0x18000fb7f  mov     [rsp+1B0h+var_188], rax; __int64
0x18000fb84  lea     rax, [rbp+0B0h+var_60]
0x18000fb88  mov     [rsp+1B0h+var_190], rax; __int64
0x18000fb8d  call    WPP_SF_DSSddD
0x18000fb92  mov     eax, edi
0x18000fb94  mov     rcx, [rbp+0B0h+var_40]
0x18000fb98  xor     rcx, rsp; StackCookie
0x18000fb9b  call    __security_check_cookie
0x18000fba0  add     rsp, 188h
0x18000fba7  pop     r15
0x18000fba9  pop     r14
0x18000fbab  pop     rdi
0x18000fbac  pop     rsi
0x18000fbad  pop     rbx
0x18000fbae  pop     rbp
0x18000fbaf  retn
```
