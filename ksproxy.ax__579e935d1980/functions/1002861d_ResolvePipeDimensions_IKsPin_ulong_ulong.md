# ResolvePipeDimensions(IKsPin *,ulong,ulong)

- ea: `0x1002861d`
- end: `0x1002892c`
- name: `?ResolvePipeDimensions@@YGJPAUIKsPin@@KK@Z`
- size: `783`
- prototype: `int __stdcall(struct IKsPin *, unsigned int, unsigned int)`
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
int __userpurge ResolvePipeDimensions@<eax>(_DWORD **a1@<ecx>, struct IKsPin *a2, unsigned int a3, unsigned int a4)
{
  int v4; // ecx
  int v5; // ebx
  int FirstPinOnPipe; // eax
  _DWORD *v7; // ecx
  _DWORD *v8; // esi
  _DWORD *v9; // esi
  char v10; // cl
  int v11; // esi
  struct KS_COMPRESSION v13; // [esp-8h] [ebp-DCh]
  struct IKsPin **v14; // [esp+0h] [ebp-D4h]
  void **v15; // [esp+0h] [ebp-D4h]
  struct KS_FRAMING_RANGE *v16; // [esp+0h] [ebp-D4h]
  struct _ALLOCATOR_PROPERTIES_EX *v17; // [esp+0h] [ebp-D4h]
  struct KS_FRAMING_RANGE *v18; // [esp+0h] [ebp-D4h]
  struct KS_FRAMING_RANGE *v19; // [esp+0h] [ebp-D4h]
  unsigned __int16 *v20; // [esp+0h] [ebp-D4h]
  unsigned int *v21; // [esp+4h] [ebp-D0h]
  void **v22; // [esp+4h] [ebp-D0h]
  enum KS_OBJECTS_INTERSECTION *v23; // [esp+4h] [ebp-D0h]
  unsigned int *v24; // [esp+4h] [ebp-D0h]
  char v25[4]; // [esp+18h] [ebp-BCh]
  unsigned int v26; // [esp+24h] [ebp-B0h] BYREF
  int v27; // [esp+28h] [ebp-ACh] BYREF
  struct IKsPin v28; // [esp+2Ch] [ebp-A8h] BYREF
  struct KS_COMPRESSION v29; // [esp+30h] [ebp-A4h] BYREF
  int v30; // [esp+3Ch] [ebp-98h]
  _DWORD v31[9]; // [esp+40h] [ebp-94h] BYREF
  struct KS_FRAMING_RANGE v32; // [esp+64h] [ebp-70h]
  int v33; // [esp+70h] [ebp-64h]
  int v34; // [esp+74h] [ebp-60h]
  int v35; // [esp+78h] [ebp-5Ch]
  int v36; // [esp+7Ch] [ebp-58h]
  int v37; // [esp+80h] [ebp-54h]
  int v38; // [esp+84h] [ebp-50h]
  unsigned int v39; // [esp+88h] [ebp-4Ch]
  int v40; // [esp+8Ch] [ebp-48h]
  int v41[7]; // [esp+94h] [ebp-40h] BYREF
  int v42[7]; // [esp+B0h] [ebp-24h] BYREF

  if ( ((int (__thiscall *)(_DWORD, _DWORD **, GUID *, int *))**a1)(
         **a1,
         a1,
         &_GUID_e539cd90_a8b4_11d1_8189_00a0c9062802,
         &v27) >= 0 )
  {
    (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v27 + 8))(*(_DWORD *)(*(_DWORD *)v27 + 8), v27);
    v4 = v27;
  }
  else
  {
    v4 = 0;
    v27 = 0;
  }
  *(_DWORD *)v25 = (*(int (__thiscall **)(_DWORD, int, _DWORD))(*(_DWORD *)v4 + 24))(
                     *(_DWORD *)(*(_DWORD *)v4 + 24),
                     v4,
                     0);
  v5 = (*(int (__thiscall **)(_DWORD, char *))(**(_DWORD **)v25 + 28))(
         *(_DWORD *)(**(_DWORD **)v25 + 28),
         *(char **)v25);
  v29 = *(struct KS_COMPRESSION *)(v5 + 16);
  v30 = *(_DWORD *)(v5 + 28);
  v31[0] = 1;
  v31[1] = 1;
  v31[3] = 1;
  v31[4] = 1;
  v31[6] = 1;
  v31[7] = 1;
  v35 = 1;
  v31[2] = 0;
  v31[5] = 0;
  v31[8] = 0;
  v32.MinFrameSize = 0;
  *(_QWORD *)&v32.MaxFrameSize = 0x1FFFFFFFFLL;
  v33 = 0;
  v34 = -1;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v40 = 0;
  v39 = 0x80000000;
  FirstPinOnPipe = FindFirstPinOnPipe(&v28, (unsigned int)&v26, v14, v21);
  if ( FirstPinOnPipe )
  {
    FirstPinOnPipe = WalkPipeAndProcess(0, (unsigned int)DimensionsCallback, (struct IKsPin *)&v29, 0, v15, v22);
    v26 = FirstPinOnPipe;
    if ( FirstPinOnPipe )
    {
      qmemcpy((void *)(v5 + 184), v31, 0x24u);
      *(_DWORD *)v5 = v38;
      *(_DWORD *)(v5 + 8) = v40;
      *(_DWORD *)(v5 + 168) = v39;
      *(_DWORD *)(v5 + 76) = v33;
      *(_DWORD *)(v5 + 80) = v34;
      *(_DWORD *)(v5 + 84) = v35;
      *(_DWORD *)(v5 + 228) = v32.Stepping;
      ComputeRangeBasedOnCompression(v32, *(struct KS_COMPRESSION *)(v5 + 196), v16);
      ResolvePhysicalRangesBasedOnDimensions(v17);
      v8 = (_DWORD *)(v5 + 64);
      if ( FrameRangeIntersection(
             *(struct KS_FRAMING_RANGE *)(v5 + 76),
             *(struct KS_FRAMING_RANGE *)(v5 + 64),
             v18,
             v23) )
      {
        v8 = v7;
      }
      *(_DWORD *)(v5 + 76) = *v8;
      v9 = v8 + 1;
      *(_DWORD *)(v5 + 80) = *v9;
      *(_DWORD *)(v5 + 84) = v9[1];
      ComputeRangeBasedOnCompression(*(struct KS_FRAMING_RANGE *)(v5 + 76), *(struct KS_COMPRESSION *)(v5 + 208), v19);
      if ( *(_DWORD *)(v5 + 80) == -1 )
      {
        *(_DWORD *)(v5 + 4) = 0;
        v10 = 0;
      }
      else
      {
        *(_QWORD *)&v13.RatioNumerator = *(_QWORD *)(v5 + 200);
        ComputeUlongBasedOnCompression(*(_DWORD *)(v5 + 196), v13, v24);
        v10 = (char)v28.__vftable;
        *(struct IKsPin *)(v5 + 4) = v28;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_qddddddddd(
          0x94u,
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v25[0],
          *(_DWORD *)(v5 + 184),
          *(_DWORD *)(v5 + 188),
          *(_DWORD *)(v5 + 196),
          *(_DWORD *)(v5 + 200),
          *(_DWORD *)(v5 + 208),
          *(_DWORD *)(v5 + 212),
          *(_DWORD *)v5,
          v10,
          *(_DWORD *)(v5 + 8));
      GetFriendlyLogicalMemoryTypeNameFromId(v13.RatioConstantMargin, (unsigned __int16 *)v24);
      GetFriendlyBusNameFromBusId(*(struct _GUID *)(v5 + 32), v20);
      FirstPinOnPipe = v26;
    }
  }
  v11 = 0;
  if ( !FirstPinOnPipe )
    v11 = -2147467259;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_DSSddD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v11,
      (int)v41,
      (int)v42,
      *(_DWORD *)(v5 + 72),
      *(_DWORD *)(v5 + 84),
      *(_DWORD *)(v5 + 168));
  return v11;
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
