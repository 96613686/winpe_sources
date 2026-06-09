# ResolvePipeDimensions(IKsPin *,ulong,ulong)

- ea: `0x1002861d`
- end: `0x1002892c`
- name: `?ResolvePipeDimensions@@YGJPAUIKsPin@@KK@Z`
- size: `783`
- prototype: `int __userpurge@<eax>(int@<edx>, IKsAllocatorEx_vtbl *@<ecx>, struct IKsPin *, unsigned int, unsigned int)`
- caller_count: `12`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x100224d5`
- `0x10022aae`
- `0x10023d3c`
- `0x10025160`
- `0x10025a94`
- `0x10028932`
- `0x10028ad1`
- `0x10028f55`
- `0x10029a5b`
- `0x1002a46f`
- `0x1002a5bd`
- `0x1002af02`

## callees

- `0x1001ee5c`
- `0x1001f081`
- `0x10025317`
- `0x100262d0`
- `0x1002631b`
- `0x10026359`
- `0x1002755f`
- `0x10027bdc`
- `0x1002861d`
- `0x1002b096`
- `0x1002b13b`
- `0x1002d510`
- `0x1003aba0`

## pseudocode

```c
int __userpurge ResolvePipeDimensions@<eax>(
        int a1@<edx>,
        IKsAllocatorEx_vtbl *a2@<ecx>,
        struct IKsPin *a3,
        unsigned int a4,
        unsigned int a5)
{
  int (__thiscall *v5)(_DWORD, IKsAllocatorEx_vtbl *, GUID *, int *); // esi
  int v6; // ecx
  int v7; // ebx
  unsigned int FirstPinOnPipe; // eax
  _DWORD *v9; // ecx
  _DWORD *v10; // esi
  _DWORD *v11; // esi
  int v12; // edx
  int v13; // ecx
  char v14; // cl
  int v15; // esi
  struct KS_COMPRESSION v17; // [esp-8h] [ebp-DCh]
  struct IKsPin **v18; // [esp+0h] [ebp-D4h]
  void **v19; // [esp+0h] [ebp-D4h]
  struct KS_FRAMING_RANGE *v20; // [esp+0h] [ebp-D4h]
  struct KS_FRAMING_RANGE *v21; // [esp+0h] [ebp-D4h]
  struct KS_FRAMING_RANGE *v22; // [esp+0h] [ebp-D4h]
  unsigned __int16 *v23; // [esp+0h] [ebp-D4h]
  unsigned int *v24; // [esp+4h] [ebp-D0h]
  void **v25; // [esp+4h] [ebp-D0h]
  enum KS_OBJECTS_INTERSECTION *v26; // [esp+4h] [ebp-D0h]
  unsigned int *v27; // [esp+4h] [ebp-D0h]
  unsigned int v28[3]; // [esp+Ch] [ebp-C8h] BYREF
  char v29[4]; // [esp+18h] [ebp-BCh]
  IKsAllocatorEx_vtbl *v30; // [esp+1Ch] [ebp-B8h]
  int v31; // [esp+20h] [ebp-B4h]
  unsigned int v32; // [esp+24h] [ebp-B0h] BYREF
  int v33; // [esp+28h] [ebp-ACh] BYREF
  struct IKsPin v34; // [esp+2Ch] [ebp-A8h] BYREF
  struct KS_COMPRESSION v35; // [esp+30h] [ebp-A4h] BYREF
  int v36; // [esp+3Ch] [ebp-98h]
  _DWORD v37[9]; // [esp+40h] [ebp-94h] BYREF
  struct KS_FRAMING_RANGE v38; // [esp+64h] [ebp-70h]
  int v39; // [esp+70h] [ebp-64h]
  int v40; // [esp+74h] [ebp-60h]
  int v41; // [esp+78h] [ebp-5Ch]
  int v42; // [esp+7Ch] [ebp-58h]
  int v43; // [esp+80h] [ebp-54h]
  int v44; // [esp+84h] [ebp-50h]
  unsigned int v45; // [esp+88h] [ebp-4Ch]
  int v46; // [esp+8Ch] [ebp-48h]
  int v47[7]; // [esp+94h] [ebp-40h] BYREF
  int v48[7]; // [esp+B0h] [ebp-24h] BYREF

  v5 = *(int (__thiscall **)(_DWORD, IKsAllocatorEx_vtbl *, GUID *, int *))a2->QueryInterface;
  v30 = a2;
  v31 = a1;
  if ( v5(v5, a2, &_GUID_e539cd90_a8b4_11d1_8189_00a0c9062802, &v33) >= 0 )
  {
    (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v33 + 8))(*(_DWORD *)(*(_DWORD *)v33 + 8), v33);
    v6 = v33;
  }
  else
  {
    v6 = 0;
    v33 = 0;
  }
  *(_DWORD *)v29 = (*(int (__thiscall **)(_DWORD, int, _DWORD))(*(_DWORD *)v6 + 24))(
                     *(_DWORD *)(*(_DWORD *)v6 + 24),
                     v6,
                     0);
  v7 = (*(int (__thiscall **)(_DWORD, _DWORD))(**(_DWORD **)v29 + 28))(
         *(_DWORD *)(**(_DWORD **)v29 + 28),
         *(_DWORD *)v29);
  v35 = *(struct KS_COMPRESSION *)(v7 + 16);
  v36 = *(_DWORD *)(v7 + 28);
  v37[0] = 1;
  v37[1] = 1;
  v37[3] = 1;
  v37[4] = 1;
  v37[6] = 1;
  v37[7] = 1;
  v41 = 1;
  v37[2] = 0;
  v37[5] = 0;
  v37[8] = 0;
  v38.MinFrameSize = 0;
  *(_QWORD *)&v38.MaxFrameSize = 0x1FFFFFFFFLL;
  v39 = 0;
  v40 = -1;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v46 = 0;
  v45 = 0x80000000;
  FirstPinOnPipe = FindFirstPinOnPipe(v31, v30, &v34, (int *)&v32, v18, v24);
  if ( FirstPinOnPipe )
  {
    FirstPinOnPipe = WalkPipeAndProcess(
                       v32,
                       (IKsAllocatorEx_vtbl *)v34.__vftable,
                       0,
                       (CD3DSurfaceAllocator *)DimensionsCallback,
                       (struct IKsPin *)&v35,
                       0,
                       v19,
                       v25);
    v32 = FirstPinOnPipe;
    if ( FirstPinOnPipe )
    {
      qmemcpy((void *)(v7 + 184), v37, 0x24u);
      *(_DWORD *)v7 = v44;
      *(_DWORD *)(v7 + 8) = v46;
      *(_DWORD *)(v7 + 168) = v45;
      *(_DWORD *)(v7 + 76) = v39;
      *(_DWORD *)(v7 + 80) = v40;
      *(_DWORD *)(v7 + 84) = v41;
      *(_DWORD *)(v7 + 228) = v38.Stepping;
      ComputeRangeBasedOnCompression(v7 + 220, v38, *(struct KS_COMPRESSION *)(v7 + 196), v20);
      ResolvePhysicalRangesBasedOnDimensions(v7);
      v10 = (_DWORD *)(v7 + 64);
      if ( FrameRangeIntersection(
             (BOOL *)&v34,
             v28,
             *(struct KS_FRAMING_RANGE *)(v7 + 76),
             *(struct KS_FRAMING_RANGE *)(v7 + 64),
             v21,
             v26) )
      {
        v10 = v9;
      }
      *(_DWORD *)(v7 + 76) = *v10;
      v11 = v10 + 1;
      *(_DWORD *)(v7 + 80) = *v11;
      *(_DWORD *)(v7 + 84) = v11[1];
      ComputeRangeBasedOnCompression(
        v7 + 132,
        *(struct KS_FRAMING_RANGE *)(v7 + 76),
        *(struct KS_COMPRESSION *)(v7 + 208),
        v22);
      v13 = *(_DWORD *)(v7 + 80);
      if ( v13 == -1 )
      {
        *(_DWORD *)(v7 + 4) = 0;
        v14 = 0;
      }
      else
      {
        *(_QWORD *)&v17.RatioNumerator = *(_QWORD *)(v7 + 200);
        ComputeUlongBasedOnCompression((unsigned int *)&v34, v13, *(_DWORD *)(v7 + 196), v17, v27);
        v14 = (char)v34.__vftable;
        *(struct IKsPin *)(v7 + 4) = v34;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_qddddddddd(
          0x94u,
          v12,
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v29[0],
          *(_DWORD *)(v7 + 184),
          *(_DWORD *)(v7 + 188),
          *(_DWORD *)(v7 + 196),
          *(_DWORD *)(v7 + 200),
          *(_DWORD *)(v7 + 208),
          *(_DWORD *)(v7 + 212),
          *(_DWORD *)v7,
          v14,
          *(_DWORD *)(v7 + 8));
      GetFriendlyLogicalMemoryTypeNameFromId(v17.RatioConstantMargin, (unsigned __int16 *)v27);
      GetFriendlyBusNameFromBusId(*(struct _GUID *)(v7 + 32), v23);
      FirstPinOnPipe = v32;
    }
  }
  v15 = 0;
  if ( !FirstPinOnPipe )
    v15 = -2147467259;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_DSSddD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v15,
      (const unsigned __int16 *)v47,
      (const unsigned __int16 *)v48,
      *(_DWORD *)(v7 + 72),
      *(_DWORD *)(v7 + 84),
      *(_DWORD *)(v7 + 168));
  return v15;
}

```

## disassembly

```asm
0x1002861d  mov     edi, edi
0x1002861f  push    ebp
0x10028620  mov     ebp, esp
0x10028622  sub     esp, 0C8h
0x10028628  mov     eax, ___security_cookie
0x1002862d  xor     eax, ebp
0x1002862f  mov     [ebp+var_8], eax
0x10028632  mov     eax, [ecx]
0x10028634  push    ebx
0x10028635  push    esi; unsigned __int16 *
0x10028636  push    edi; unsigned __int16 *
0x10028637  mov     esi, [eax]
0x10028639  lea     eax, [ebp+var_AC]
0x1002863f  push    eax
0x10028640  push    offset __GUID_e539cd90_a8b4_11d1_8189_00a0c9062802
0x10028645  mov     [ebp+var_B8], ecx
0x1002864b  push    ecx
0x1002864c  mov     ecx, esi; this
0x1002864e  mov     [ebp+var_B4], edx
0x10028654  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1002865a  call    esi
0x1002865c  test    eax, eax
0x1002865e  jns     short loc_1002866A
0x10028660  xor     ecx, ecx
0x10028662  mov     [ebp+var_AC], ecx
0x10028668  jmp     short loc_10028686
0x1002866a  mov     eax, [ebp+var_AC]
0x10028670  push    eax
0x10028671  mov     ecx, [eax]
0x10028673  mov     esi, [ecx+8]
0x10028676  mov     ecx, esi; this
0x10028678  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1002867e  call    esi
0x10028680  mov     ecx, [ebp+var_AC]
0x10028686  mov     eax, [ecx]
0x10028688  push    0
0x1002868a  push    ecx
0x1002868b  mov     esi, [eax+18h]
0x1002868e  mov     ecx, esi; this
0x10028690  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10028696  call    esi
0x10028698  push    eax
0x10028699  mov     dword ptr [ebp+var_BC], eax
0x1002869f  mov     ecx, [eax]
0x100286a1  mov     esi, [ecx+1Ch]
0x100286a4  mov     ecx, esi; this
0x100286a6  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x100286ac  call    esi
0x100286ae  mov     ebx, eax
0x100286b0  mov     edx, [ebp+var_B4]
0x100286b6  mov     ecx, [ebp+var_B8]
0x100286bc  lea     edi, [ebp+var_A4]
0x100286c2  xor     eax, eax
0x100286c4  inc     eax
0x100286c5  lea     esi, [ebx+10h]
0x100286c8  movsd
0x100286c9  movsd
0x100286ca  movsd
0x100286cb  movsd
0x100286cc  xor     esi, esi
0x100286ce  mov     [ebp+var_94], eax
0x100286d4  mov     [ebp+var_90], eax
0x100286da  mov     [ebp+var_88], eax
0x100286e0  mov     [ebp+var_84], eax
0x100286e6  mov     [ebp+var_7C], eax
0x100286e9  mov     [ebp+var_78], eax
0x100286ec  mov     dword ptr [ebp+var_6C+4], eax
0x100286ef  mov     [ebp+var_5C], eax
0x100286f2  lea     eax, [ebp+var_B0]
0x100286f8  push    eax; unsigned int
0x100286f9  lea     eax, [ebp+var_A8]
0x100286ff  mov     [ebp+var_8C], esi
0x10028705  push    eax; struct IKsPin *
0x10028706  mov     [ebp+var_80], esi
0x10028709  mov     [ebp+var_74], esi
0x1002870c  mov     [ebp+var_70], esi
0x1002870f  mov     dword ptr [ebp+var_6C], 0FFFFFFFFh
0x10028716  mov     [ebp+var_64], esi
0x10028719  mov     [ebp+var_60], 0FFFFFFFFh
0x10028720  mov     [ebp+var_58], esi
0x10028723  mov     [ebp+var_54], esi
0x10028726  mov     [ebp+var_50], esi
0x10028729  mov     [ebp+var_48], esi
0x1002872c  mov     [ebp+var_4C], 80000000h
0x10028733  call    ?FindFirstPinOnPipe@@YGHPAUIKsPin@@KPAPAU1@PAK@Z; FindFirstPinOnPipe(IKsPin *,ulong,IKsPin * *,ulong *)
0x10028738  test    eax, eax
0x1002873a  jz      loc_100288D9
0x10028740  mov     edx, [ebp+var_B0]
0x10028746  lea     eax, [ebp+var_A4]
0x1002874c  mov     ecx, [ebp+var_A8.__vftable]
0x10028752  push    esi; int (__stdcall *)(struct IKsPin *, unsigned int, void **, void **, int *)
0x10028753  push    eax; struct KS_COMPRESSION
0x10028754  push    offset ?DimensionsCallback@@YGHPAUIKsPin@@KPAPAX1PAH@Z; unsigned int
0x10028759  push    esi; struct IKsPin *
0x1002875a  call    ?WalkPipeAndProcess@@YGHPAUIKsPin@@K0P6GH0KPAPAX1PAH@Z11@Z; WalkPipeAndProcess(IKsPin *,ulong,IKsPin *,int (*)(IKsPin *,ulong,void * *,void * *,int *),void * *,void * *)
0x1002875f  mov     [ebp+var_B0], eax
0x10028765  test    eax, eax
0x10028767  jz      loc_100288D9
0x1002876d  push    9
0x1002876f  pop     ecx
0x10028770  lea     edi, [ebx+0B8h]
0x10028776  sub     esp, 0Ch
0x10028779  lea     esi, [ebp+var_94]
0x1002877f  rep movsd
0x10028781  mov     eax, [ebp+var_50]
0x10028784  lea     edi, [ebx+4Ch]
0x10028787  mov     [ebx], eax
0x10028789  lea     esi, [ebp+var_64]
0x1002878c  mov     eax, [ebp+var_48]
0x1002878f  lea     ecx, [ebx+0DCh]
0x10028795  mov     [ebx+8], eax
0x10028798  mov     eax, [ebp+var_4C]
0x1002879b  mov     [ebx+0A8h], eax
0x100287a1  movsd
0x100287a2  movsd
0x100287a3  movsd
0x100287a4  mov     eax, dword ptr [ebp+var_6C+4]
0x100287a7  lea     esi, [ebx+0C4h]
0x100287ad  mov     edi, esp
0x100287af  mov     [ebx+0E4h], eax
0x100287b5  sub     esp, 0Ch
0x100287b8  movsd
0x100287b9  movsd
0x100287ba  movsd
0x100287bb  mov     edi, esp
0x100287bd  lea     esi, [ebp+var_70]
0x100287c0  movsd
0x100287c1  movsd
0x100287c2  movsd
0x100287c3  call    ?ComputeRangeBasedOnCompression@@YGHUKS_FRAMING_RANGE@@UKS_COMPRESSION@@PAU1@@Z; ComputeRangeBasedOnCompression(KS_FRAMING_RANGE,KS_COMPRESSION,KS_FRAMING_RANGE *)
0x100287c8  mov     ecx, ebx
0x100287ca  call    ?ResolvePhysicalRangesBasedOnDimensions@@YGHPAU_ALLOCATOR_PROPERTIES_EX@@@Z; ResolvePhysicalRangesBasedOnDimensions(_ALLOCATOR_PROPERTIES_EX *)
0x100287cf  sub     esp, 0Ch
0x100287d2  lea     esi, [ebx+40h]
0x100287d5  mov     edi, esp
0x100287d7  lea     edx, [ebp+var_A8]
0x100287dd  sub     esp, 0Ch
0x100287e0  lea     ecx, [ebp+var_C8]
0x100287e6  movsd
0x100287e7  movsd
0x100287e8  movsd
0x100287e9  mov     edi, esp
0x100287eb  lea     esi, [ebx+4Ch]
0x100287ee  movsd
0x100287ef  movsd
0x100287f0  movsd
0x100287f1  call    ?FrameRangeIntersection@@YGHUKS_FRAMING_RANGE@@0PAU1@PAW4KS_OBJECTS_INTERSECTION@@@Z; FrameRangeIntersection(KS_FRAMING_RANGE,KS_FRAMING_RANGE,KS_FRAMING_RANGE *,KS_OBJECTS_INTERSECTION *)
0x100287f6  test    eax, eax
0x100287f8  lea     esi, [ebx+40h]
0x100287fb  lea     eax, [ebx+4Ch]
0x100287fe  mov     edi, eax
0x10028800  jz      short loc_10028804
0x10028802  mov     esi, ecx
0x10028804  movsd
0x10028805  lea     ecx, [ebx+84h]
0x1002880b  sub     esp, 0Ch
0x1002880e  movsd
0x1002880f  movsd
0x10028810  mov     edi, esp
0x10028812  lea     esi, [ebx+0D0h]
0x10028818  sub     esp, 0Ch
0x1002881b  movsd
0x1002881c  movsd
0x1002881d  movsd
0x1002881e  mov     esi, eax
0x10028820  mov     edi, esp
0x10028822  movsd
0x10028823  movsd
0x10028824  movsd
0x10028825  call    ?ComputeRangeBasedOnCompression@@YGHUKS_FRAMING_RANGE@@UKS_COMPRESSION@@PAU1@@Z; ComputeRangeBasedOnCompression(KS_FRAMING_RANGE,KS_COMPRESSION,KS_FRAMING_RANGE *)
0x1002882a  mov     ecx, [ebx+50h]
0x1002882d  cmp     ecx, 0FFFFFFFFh
0x10028830  jz      short loc_10028856
0x10028832  sub     esp, 0Ch
0x10028835  lea     esi, [ebx+0C4h]
0x1002883b  mov     edi, esp
0x1002883d  lea     edx, [ebp+var_A8]
0x10028843  movsd
0x10028844  movsd
0x10028845  movsd
0x10028846  call    ?ComputeUlongBasedOnCompression@@YGHKUKS_COMPRESSION@@PAK@Z; ComputeUlongBasedOnCompression(ulong,KS_COMPRESSION,ulong *)
0x1002884b  mov     ecx, [ebp+var_A8.__vftable]
0x10028851  mov     [ebx+4], ecx
0x10028854  jmp     short loc_1002885F
0x10028856  mov     dword ptr [ebx+4], 0
0x1002885d  xor     ecx, ecx
0x1002885f  mov     eax, _WPP_GLOBAL_Control
0x10028864  cmp     eax, offset _WPP_GLOBAL_Control
0x10028869  jz      short loc_100288B1
0x1002886b  cmp     byte ptr [eax+19h], 2
0x1002886f  jb      short loc_100288B1
0x10028871  push    dword ptr [ebx+8]; char
0x10028874  push    ecx; char
0x10028875  push    dword ptr [ebx]; char
0x10028877  mov     ecx, 94h; MessageNumber
0x1002887c  push    dword ptr [ebx+0D4h]; struct _GUID
0x10028882  push    dword ptr [ebx+0D0h]; char
0x10028888  push    dword ptr [ebx+0C8h]; char
0x1002888e  push    dword ptr [ebx+0C4h]; char
0x10028894  push    dword ptr [ebx+0BCh]; char
0x1002889a  push    dword ptr [ebx+0B8h]; char
0x100288a0  push    dword ptr [ebp+var_BC]; char
0x100288a6  push    dword ptr [eax+14h]
0x100288a9  push    dword ptr [eax+10h]; LoggerHandle
0x100288ac  call    _WPP_SF_qddddddddd@56; WPP_SF_qddddddddd(x,x,x,x,x,x,x,x,x,x,x,x,x,x)
0x100288b1  mov     ecx, [ebx+0B0h]
0x100288b7  lea     edx, [ebp+var_40]
0x100288ba  call    ?GetFriendlyLogicalMemoryTypeNameFromId@@YGHKPAG@Z; GetFriendlyLogicalMemoryTypeNameFromId(ulong,ushort *)
0x100288bf  sub     esp, 10h
0x100288c2  lea     esi, [ebx+20h]
0x100288c5  mov     edi, esp
0x100288c7  lea     ecx, [ebp+var_24]
0x100288ca  movsd
0x100288cb  movsd
0x100288cc  movsd
0x100288cd  movsd
0x100288ce  call    ?GetFriendlyBusNameFromBusId@@YGHU_GUID@@PAG@Z; GetFriendlyBusNameFromBusId(_GUID,ushort *)
0x100288d3  mov     eax, [ebp+var_B0]
0x100288d9  xor     esi, esi
0x100288db  mov     ecx, 80004005h
0x100288e0  test    eax, eax
0x100288e2  cmovz   esi, ecx
0x100288e5  mov     ecx, _WPP_GLOBAL_Control
0x100288eb  cmp     ecx, offset _WPP_GLOBAL_Control
0x100288f1  jz      short loc_10028919
0x100288f3  cmp     byte ptr [ecx+19h], 2
0x100288f7  jb      short loc_10028919
0x100288f9  push    dword ptr [ebx+0A8h]; char
0x100288ff  lea     eax, [ebp+var_24]
0x10028902  push    dword ptr [ebx+54h]; char
0x10028905  push    dword ptr [ebx+48h]; char
0x10028908  push    eax; int
0x10028909  lea     eax, [ebp+var_40]
0x1002890c  push    eax; int
0x1002890d  push    esi; char
0x1002890e  push    dword ptr [ecx+14h]
0x10028911  push    dword ptr [ecx+10h]; LoggerHandle
0x10028914  call    _WPP_SF_DSSddD@40; WPP_SF_DSSddD(x,x,x,x,x,x,x,x,x,x)
0x10028919  mov     ecx, [ebp+var_8]
0x1002891c  mov     eax, esi
0x1002891e  pop     edi
0x1002891f  pop     esi
0x10028920  xor     ecx, ebp; StackCookie
0x10028922  pop     ebx
0x10028923  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10028928  leave
0x10028929  retn    4
```
