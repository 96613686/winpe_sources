# FindCommonMemoryTypeBasedOnPipeAndPin(IKsPin *,ulong,IKsPin *,ulong,int,_GUID *)

- ea: `0x180036dbc`
- end: `0x180037293`
- name: `?FindCommonMemoryTypeBasedOnPipeAndPin@@YAHPEAUIKsPin@@K0KHPEAU_GUID@@@Z`
- size: `1239`
- prototype: `__int64 __fastcall(struct IKsPin *, unsigned int, struct IKsPin *, unsigned int)`
- caller_count: `3`
- callee_count: `18`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18001de40`
- `0x1800399ac`
- `0x18003af9c`

## callees

- `0x180002b58`
- `0x18000f7e0`
- `0x180016a28`
- `0x18001e328`
- `0x18001f1c4`
- `0x18001f210`
- `0x18001f620`
- `0x18001ffb0`
- `0x180025a74`
- `0x18002ca70`
- `0x1800320a8`
- `0x180032cf0`
- `0x1800342a8`
- `0x180036c38`
- `0x180036dbc`
- `0x18003729c`
- `0x1800380f8`
- `0x180045010`

## pseudocode

```c
__int64 __fastcall FindCommonMemoryTypeBasedOnPipeAndPin(
        struct IKsPin *a1,
        unsigned int a2,
        struct IKsPin *a3,
        unsigned int a4)
{
  unsigned int v4; // r15d
  struct _GUID v8; // xmm7
  unsigned int v9; // edi
  PVOID *v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rdx
  struct _GUID v13; // xmm6
  USHORT v14; // dx
  struct _GUID *v15; // rax
  struct _GUID *v16; // r14
  __int64 v17; // rdx
  struct _GUID *v19; // [rsp+28h] [rbp-D8h]
  unsigned int v20; // [rsp+40h] [rbp-C0h] BYREF
  struct KSALLOCATOR_FRAMING_EX *v21; // [rsp+48h] [rbp-B8h] BYREF
  struct _GUID v22; // [rsp+50h] [rbp-B0h] BYREF
  enum FRAMING_PROP v23; // [rsp+60h] [rbp-A0h] BYREF
  enum FRAMING_PROP v24; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v25; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v26; // [rsp+70h] [rbp-90h]
  __int64 v27; // [rsp+78h] [rbp-88h] BYREF
  struct KSALLOCATOR_FRAMING_EX *v28; // [rsp+80h] [rbp-80h] BYREF
  struct _GUID v29; // [rsp+90h] [rbp-70h] BYREF
  struct _GUID v30; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v31[128]; // [rsp+B0h] [rbp-50h] BYREF

  v4 = 0;
  v26 = a2;
  v21 = 0;
  v28 = 0;
  v23 = FramingProp_Uninitialized;
  v24 = FramingProp_Uninitialized;
  memset_0(v31, 0, 0x74u);
  v27 = 0;
  v8 = 0;
  v25 = 0;
  v29 = 0;
  v30 = 0;
  v9 = 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 0xB7u, &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids, a1, a3);
  GetPinFramingFromCache(a3, &v21, &v23, Framing_Cache_ReadLast);
  if ( v23 != FramingProp_None )
  {
    if ( a1->QueryInterface(a1, &GUID_e539cd90_a8b4_11d1_8189_00a0c9062802, (void **)&v25) >= 0 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    else
      v25 = 0;
    if ( a3->QueryInterface(a3, &GUID_e539cd90_a8b4_11d1_8189_00a0c9062802, (void **)&v27) >= 0 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    else
      v27 = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v25 + 48LL))(v25, 0);
    v22 = *(struct _GUID *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 56LL))(v11) + 16);
    if ( (unsigned int)GetFramingFixedFromFramingByMemoryType(v21, &v22, (struct KS_FRAMING_FIXED *)v31) )
    {
      if ( a1 != a3 )
        AddPinToPipeUnconditional(a1, v12, a3, a4);
      goto LABEL_52;
    }
    GetBusForKsPin(a3, &v30);
    v20 = 0;
    if ( a1 == a3 )
    {
      v13 = v30;
      v22 = v30;
      if ( !(unsigned int)FindAllPinMemoryTypesBasedOnBus(v21, (unsigned __int64)&v22, &v20, 0) )
      {
        v10 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_24;
        v14 = 185;
        goto LABEL_22;
      }
    }
    else
    {
      GetPinFramingFromCache(a1, &v28, &v24, Framing_Cache_ReadLast);
      if ( v24 == FramingProp_None )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 0xBAu, &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids, a1);
        v9 = 0;
      }
      GetBusForKsPin(a1, &v29);
      v8 = v29;
      v13 = v30;
      v22 = v29;
      v29 = v30;
      if ( !(unsigned int)FindCommonMemoryTypesBasedOnBuses(v21, (__int64)v28, &v29, &v22, &v20, 0) )
      {
        v10 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_24;
        v14 = 187;
LABEL_22:
        WPP_SF_q((TRACEHANDLE)v10[2], v14, &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids, a3);
LABEL_23:
        v10 = (PVOID *)WPP_GLOBAL_Control;
LABEL_24:
        v9 = 0;
        goto LABEL_53;
      }
      if ( !v9 )
        goto LABEL_52;
    }
    v15 = (struct _GUID *)operator new[](saturated_mul(v20, 0x10u));
    v16 = v15;
    if ( !v15 )
    {
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_24;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 0xBCu, &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids, v20);
      goto LABEL_23;
    }
    if ( a1 == a3 )
    {
      v22 = v13;
      v9 &= -((unsigned int)FindAllPinMemoryTypesBasedOnBus(v21, (unsigned __int64)&v22, &v20, (unsigned __int64)v15) != 0);
    }
    else
    {
      v22 = v8;
      v29 = v13;
      if ( !(unsigned int)FindCommonMemoryTypesBasedOnBuses(v21, (__int64)v28, &v29, &v22, &v20, v15) )
      {
        v9 = 0;
LABEL_51:
        operator delete(v16);
        goto LABEL_52;
      }
    }
    if ( v9 )
    {
      v9 = 0;
      while ( v4 < v20 )
      {
        v22 = v16[v4];
        if ( (unsigned int)CanPipeUseMemoryType(a1, v26, &v22, KS_MemoryTypeDeviceSpecific, 1u, 0) )
        {
          if ( a1 == a3 )
          {
            v22 = v16[v4];
            AssignPipeAllocatorHandler(a3, a4, &v22, 2, 0, &v19->Data1, 1);
            ResolvePipeDimensions(a3, a4);
          }
          else
          {
            AddPinToPipeUnconditional(a1, v17, a3, a4);
          }
          goto LABEL_51;
        }
        ++v4;
      }
    }
    goto LABEL_51;
  }
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v9;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 0xB8u, &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids, a3);
LABEL_52:
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_53:
  if ( v10 != &WPP_GLOBAL_Control && *((_BYTE *)v10 + 25) >= 2u )
    WPP_SF_d((TRACEHANDLE)v10[2], 0xBDu, &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x180036dbc  mov     rax, rsp
0x180036dbf  push    rbp
0x180036dc0  push    rbx
0x180036dc1  push    rsi
0x180036dc2  push    rdi
0x180036dc3  push    r12
0x180036dc5  push    r13
0x180036dc7  push    r14
0x180036dc9  push    r15
0x180036dcb  lea     rbp, [rsp-68h]
0x180036dd0  sub     rsp, 168h
0x180036dd7  movaps  xmmword ptr [rax-58h], xmm6
0x180036ddb  movaps  xmmword ptr [rax-68h], xmm7
0x180036ddf  mov     rax, cs:__security_cookie
0x180036de6  xor     rax, rsp
0x180036de9  mov     [rbp+0A0h+var_70], rax
0x180036ded  xor     r15d, r15d
0x180036df0  mov     [rsp+1A0h+var_130], edx
0x180036df4  mov     rbx, r8
0x180036df7  mov     [rsp+1A0h+var_158], r15
0x180036dfc  mov     rsi, rcx
0x180036dff  mov     [rbp+0A0h+var_120], r15
0x180036e03  xor     edx, edx; Val
0x180036e05  mov     [rsp+1A0h+var_140], r15d
0x180036e0a  lea     r8d, [r15+74h]; Size
0x180036e0e  mov     [rsp+1A0h+var_13C], r15d
0x180036e13  lea     rcx, [rbp+0A0h+var_F0]; void *
0x180036e17  mov     r13d, r9d
0x180036e1a  call    memset_0
0x180036e1f  xorps   xmm0, xmm0
0x180036e22  mov     [rsp+1A0h+var_128], r15
0x180036e27  xorps   xmm7, xmm7
0x180036e2a  mov     [rsp+1A0h+var_138], r15
0x180036e2f  lea     r14d, [r15+1]
0x180036e33  movaps  xmmword ptr [rbp+0A0h+var_110.Data1], xmm7
0x180036e37  movups  xmmword ptr [rbp+0A0h+var_100.Data1], xmm0
0x180036e3b  mov     edi, r14d
0x180036e3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180036e45  lea     r12, WPP_GLOBAL_Control
0x180036e4c  cmp     rcx, r12
0x180036e4f  jz      short loc_180036E74
0x180036e51  cmp     byte ptr [rcx+19h], 2
0x180036e55  jb      short loc_180036E74
0x180036e57  mov     rcx, [rcx+10h]
0x180036e5b  lea     r8, WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids
0x180036e62  mov     edx, 0B7h
0x180036e67  mov     [rsp+1A0h+var_180], rbx
0x180036e6c  mov     r9, rsi
0x180036e6f  call    WPP_SF_qq
0x180036e74  mov     r9d, r14d; enum FRAMING_CACHE_OPS
0x180036e77  lea     r8, [rsp+1A0h+var_140]; enum FRAMING_PROP *
0x180036e7c  lea     rdx, [rsp+1A0h+var_158]; struct KSALLOCATOR_FRAMING_EX **
0x180036e81  mov     rcx, rbx; struct IKsPin *
0x180036e84  call    ?GetPinFramingFromCache@@YAHPEAUIKsPin@@PEAPEAUKSALLOCATOR_FRAMING_EX@@PEAW4FRAMING_PROP@@W4FRAMING_CACHE_OPS@@@Z; GetPinFramingFromCache(IKsPin *,KSALLOCATOR_FRAMING_EX * *,FRAMING_PROP *,FRAMING_CACHE_OPS)
0x180036e89  cmp     [rsp+1A0h+var_140], r14d
0x180036e8e  jnz     short loc_180036EC7
0x180036e90  mov     rcx, cs:WPP_GLOBAL_Control
0x180036e97  cmp     rcx, r12
0x180036e9a  jz      loc_180037262
0x180036ea0  cmp     byte ptr [rcx+19h], 2
0x180036ea4  jb      loc_18003723F
0x180036eaa  mov     rcx, [rcx+10h]
0x180036eae  lea     r8, WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids
0x180036eb5  mov     edx, 0B8h
0x180036eba  mov     r9, rbx
0x180036ebd  call    WPP_SF_q
0x180036ec2  jmp     loc_180037238
0x180036ec7  mov     rax, [rsi]
0x180036eca  lea     r8, [rsp+1A0h+var_138]
0x180036ecf  lea     rdx, _GUID_e539cd90_a8b4_11d1_8189_00a0c9062802
0x180036ed6  mov     rcx, rsi
0x180036ed9  mov     rax, [rax]
0x180036edc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036ee1  test    eax, eax
0x180036ee3  jns     short loc_180036EEC
0x180036ee5  mov     [rsp+1A0h+var_138], r15
0x180036eea  jmp     short loc_180036EFD
0x180036eec  mov     rcx, [rsp+1A0h+var_138]
0x180036ef1  mov     rax, [rcx]
0x180036ef4  mov     rax, [rax+10h]
0x180036ef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036efd  mov     rax, [rbx]
0x180036f00  lea     r8, [rsp+1A0h+var_128]
0x180036f05  lea     rdx, _GUID_e539cd90_a8b4_11d1_8189_00a0c9062802
0x180036f0c  mov     rcx, rbx
0x180036f0f  mov     rax, [rax]
0x180036f12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036f17  test    eax, eax
0x180036f19  jns     short loc_180036F22
0x180036f1b  mov     [rsp+1A0h+var_128], r15
0x180036f20  jmp     short loc_180036F33
0x180036f22  mov     rcx, [rsp+1A0h+var_128]
0x180036f27  mov     rax, [rcx]
0x180036f2a  mov     rax, [rax+10h]
0x180036f2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036f33  mov     rcx, [rsp+1A0h+var_138]
0x180036f38  xor     edx, edx
0x180036f3a  mov     rax, [rcx]
0x180036f3d  mov     rax, [rax+30h]
0x180036f41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036f46  mov     rcx, rax
0x180036f49  mov     rax, [rax]
0x180036f4c  mov     rax, [rax+38h]
0x180036f50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036f55  mov     rcx, [rsp+1A0h+var_158]; struct KSALLOCATOR_FRAMING_EX *
0x180036f5a  lea     r8, [rbp+0A0h+var_F0]; struct KS_FRAMING_FIXED *
0x180036f5e  lea     rdx, [rsp+1A0h+var_150]; struct _GUID
0x180036f63  movups  xmm0, xmmword ptr [rax+10h]
0x180036f67  movdqu  xmmword ptr [rsp+1A0h+var_150.Data1], xmm0
0x180036f6d  call    ?GetFramingFixedFromFramingByMemoryType@@YAHPEAUKSALLOCATOR_FRAMING_EX@@U_GUID@@PEAUKS_FRAMING_FIXED@@@Z; GetFramingFixedFromFramingByMemoryType(KSALLOCATOR_FRAMING_EX *,_GUID,KS_FRAMING_FIXED *)
0x180036f72  test    eax, eax
0x180036f74  jz      short loc_180036F92
0x180036f76  cmp     rsi, rbx
0x180036f79  jz      loc_180037238
0x180036f7f  mov     r9d, r13d; unsigned int
0x180036f82  mov     r8, rbx; struct IKsPin *
0x180036f85  mov     rcx, rsi; struct IKsPin *
0x180036f88  call    ?AddPinToPipeUnconditional@@YAHPEAUIKsPin@@K0K@Z; AddPinToPipeUnconditional(IKsPin *,ulong,IKsPin *,ulong)
0x180036f8d  jmp     loc_180037238
0x180036f92  lea     rdx, [rbp+0A0h+var_100]; struct _GUID *
0x180036f96  mov     rcx, rbx; struct IKsPin *
0x180036f99  call    ?GetBusForKsPin@@YAHPEAUIKsPin@@PEAU_GUID@@@Z; GetBusForKsPin(IKsPin *,_GUID *)
0x180036f9e  mov     [rsp+1A0h+var_160], r15d
0x180036fa3  cmp     rsi, rbx
0x180036fa6  jnz     short loc_18003700A
0x180036fa8  movaps  xmm6, xmmword ptr [rbp+0A0h+var_100.Data1]
0x180036fac  lea     r8, [rsp+1A0h+var_160]; unsigned int *
0x180036fb1  mov     rcx, [rsp+1A0h+var_158]; struct KSALLOCATOR_FRAMING_EX *
0x180036fb6  lea     rdx, [rsp+1A0h+var_150]; struct _GUID
0x180036fbb  xor     r9d, r9d; struct _GUID *
0x180036fbe  movdqa  xmmword ptr [rsp+1A0h+var_150.Data1], xmm6
0x180036fc4  call    ?FindAllPinMemoryTypesBasedOnBus@@YAHPEAUKSALLOCATOR_FRAMING_EX@@U_GUID@@PEAKPEAU2@@Z; FindAllPinMemoryTypesBasedOnBus(KSALLOCATOR_FRAMING_EX *,_GUID,ulong *,_GUID *)
0x180036fc9  test    eax, eax
0x180036fcb  jnz     loc_1800370C7
0x180036fd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180036fd8  cmp     rcx, r12
0x180036fdb  jz      short loc_180037002
0x180036fdd  cmp     byte ptr [rcx+19h], 2
0x180036fe1  jb      short loc_180037002
0x180036fe3  mov     edx, 0B9h
0x180036fe8  mov     rcx, [rcx+10h]
0x180036fec  lea     r8, WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids
0x180036ff3  mov     r9, rbx
0x180036ff6  call    WPP_SF_q
0x180036ffb  mov     rcx, cs:WPP_GLOBAL_Control
0x180037002  mov     edi, r15d
0x180037005  jmp     loc_18003723F
0x18003700a  mov     r9d, r14d; enum FRAMING_CACHE_OPS
0x18003700d  lea     r8, [rsp+1A0h+var_13C]; enum FRAMING_PROP *
0x180037012  lea     rdx, [rbp+0A0h+var_120]; struct KSALLOCATOR_FRAMING_EX **
0x180037016  mov     rcx, rsi; struct IKsPin *
0x180037019  call    ?GetPinFramingFromCache@@YAHPEAUIKsPin@@PEAPEAUKSALLOCATOR_FRAMING_EX@@PEAW4FRAMING_PROP@@W4FRAMING_CACHE_OPS@@@Z; GetPinFramingFromCache(IKsPin *,KSALLOCATOR_FRAMING_EX * *,FRAMING_PROP *,FRAMING_CACHE_OPS)
0x18003701e  cmp     [rsp+1A0h+var_13C], r14d
0x180037023  jnz     short loc_180037052
0x180037025  mov     rcx, cs:WPP_GLOBAL_Control
0x18003702c  cmp     rcx, r12
0x18003702f  jz      short loc_18003704F
0x180037031  cmp     byte ptr [rcx+19h], 2
0x180037035  jb      short loc_18003704F
0x180037037  mov     rcx, [rcx+10h]
0x18003703b  lea     r8, WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids
0x180037042  mov     edx, 0BAh
0x180037047  mov     r9, rsi
0x18003704a  call    WPP_SF_q
0x18003704f  mov     edi, r15d
0x180037052  lea     rdx, [rbp+0A0h+var_110]; struct _GUID *
0x180037056  mov     rcx, rsi; struct IKsPin *
0x180037059  call    ?GetBusForKsPin@@YAHPEAUIKsPin@@PEAU_GUID@@@Z; GetBusForKsPin(IKsPin *,_GUID *)
0x18003705e  movaps  xmm7, xmmword ptr [rbp+0A0h+var_110.Data1]
0x180037062  lea     rax, [rsp+1A0h+var_160]
0x180037067  movaps  xmm6, xmmword ptr [rbp+0A0h+var_100.Data1]
0x18003706b  lea     r9, [rsp+1A0h+var_150]; struct _GUID *
0x180037070  mov     rdx, [rbp+0A0h+var_120]; struct KSALLOCATOR_FRAMING_EX *
0x180037074  lea     r8, [rbp+0A0h+var_110]; struct _GUID *
0x180037078  mov     rcx, [rsp+1A0h+var_158]; struct KSALLOCATOR_FRAMING_EX *
0x18003707d  mov     [rsp+1A0h+var_178], r15; struct _GUID *
0x180037082  mov     [rsp+1A0h+var_180], rax; unsigned int *
0x180037087  movdqa  xmmword ptr [rsp+1A0h+var_150.Data1], xmm7
0x18003708d  movdqa  xmmword ptr [rbp+0A0h+var_110.Data1], xmm6
0x180037092  call    ?FindCommonMemoryTypesBasedOnBuses@@YAHPEAUKSALLOCATOR_FRAMING_EX@@0U_GUID@@1PEAKPEAU2@@Z; FindCommonMemoryTypesBasedOnBuses(KSALLOCATOR_FRAMING_EX *,KSALLOCATOR_FRAMING_EX *,_GUID,_GUID,ulong *,_GUID *)
0x180037097  test    eax, eax
0x180037099  jnz     short loc_1800370BF
0x18003709b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800370a2  cmp     rcx, r12
0x1800370a5  jz      loc_180037002
0x1800370ab  cmp     byte ptr [rcx+19h], 2
0x1800370af  jb      loc_180037002
0x1800370b5  mov     edx, 0BBh
0x1800370ba  jmp     loc_180036FE8
0x1800370bf  test    edi, edi
0x1800370c1  jz      loc_180037238
0x1800370c7  mov     ecx, [rsp+1A0h+var_160]
0x1800370cb  mov     eax, 10h
0x1800370d0  mul     rcx
0x1800370d3  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800370da  cmovb   rax, rcx
0x1800370de  mov     rcx, rax; unsigned __int64
0x1800370e1  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800370e6  mov     r14, rax
0x1800370e9  test    rax, rax
0x1800370ec  jnz     short loc_180037127
0x1800370ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800370f5  cmp     rcx, r12
0x1800370f8  jz      loc_180037002
0x1800370fe  cmp     byte ptr [rcx+19h], 2
0x180037102  jb      loc_180037002
0x180037108  mov     r9d, [rsp+1A0h+var_160]
0x18003710d  lea     r8, WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids
0x180037114  mov     rcx, [rcx+10h]
0x180037118  mov     edx, 0BCh
0x18003711d  call    WPP_SF_d
0x180037122  jmp     loc_180036FFB
0x180037127  mov     rcx, [rsp+1A0h+var_158]; struct KSALLOCATOR_FRAMING_EX *
0x18003712c  cmp     rsi, rbx
0x18003712f  jnz     short loc_1800371A2
0x180037131  mov     r9, r14; struct _GUID *
0x180037134  movdqa  xmmword ptr [rsp+1A0h+var_150.Data1], xmm6
0x18003713a  lea     r8, [rsp+1A0h+var_160]; unsigned int *
0x18003713f  lea     rdx, [rsp+1A0h+var_150]; struct _GUID
0x180037144  call    ?FindAllPinMemoryTypesBasedOnBus@@YAHPEAUKSALLOCATOR_FRAMING_EX@@U_GUID@@PEAKPEAU2@@Z; FindAllPinMemoryTypesBasedOnBus(KSALLOCATOR_FRAMING_EX *,_GUID,ulong *,_GUID *)
0x180037149  neg     eax
0x18003714b  sbb     ecx, ecx
0x18003714d  and     edi, ecx
0x18003714f  test    edi, edi
0x180037151  jz      loc_180037230
0x180037157  mov     edi, r15d
0x18003715a  cmp     r15d, [rsp+1A0h+var_160]
0x18003715f  jnb     loc_180037229
0x180037165  mov     edx, [rsp+1A0h+var_130]; unsigned int
0x180037169  lea     r8, [rsp+1A0h+var_150]; struct _GUID
0x18003716e  mov     r12d, r15d
0x180037171  mov     r9d, 4; enum KS_LogicalMemoryType
0x180037177  add     r12, r12
0x18003717a  mov     dword ptr [rsp+1A0h+var_178], edi; unsigned int *
0x18003717e  mov     rcx, rsi; struct IKsPin *
0x180037181  mov     dword ptr [rsp+1A0h+var_180], 1; unsigned int
0x180037189  movups  xmm0, xmmword ptr [r14+r12*8]
0x18003718e  movdqu  xmmword ptr [rsp+1A0h+var_150.Data1], xmm0
0x180037194  call    ?CanPipeUseMemoryType@@YAHPEAUIKsPin@@KU_GUID@@W4KS_LogicalMemoryType@@KK@Z; CanPipeUseMemoryType(IKsPin *,ulong,_GUID,KS_LogicalMemoryType,ulong,ulong)
0x180037199  test    eax, eax
0x18003719b  jnz     short loc_1800371DB
0x18003719d  inc     r15d
0x1800371a0  jmp     short loc_18003715A
0x1800371a2  mov     rdx, [rbp+0A0h+var_120]; struct KSALLOCATOR_FRAMING_EX *
0x1800371a6  lea     rax, [rsp+1A0h+var_160]
0x1800371ab  mov     [rsp+1A0h+var_178], r14; struct _GUID *
0x1800371b0  lea     r9, [rsp+1A0h+var_150]; struct _GUID *
0x1800371b5  lea     r8, [rbp+0A0h+var_110]; struct _GUID *
0x1800371b9  mov     [rsp+1A0h+var_180], rax; unsigned int *
0x1800371be  movdqa  xmmword ptr [rsp+1A0h+var_150.Data1], xmm7
0x1800371c4  movdqa  xmmword ptr [rbp+0A0h+var_110.Data1], xmm6
0x1800371c9  call    ?FindCommonMemoryTypesBasedOnBuses@@YAHPEAUKSALLOCATOR_FRAMING_EX@@0U_GUID@@1PEAKPEAU2@@Z; FindCommonMemoryTypesBasedOnBuses(KSALLOCATOR_FRAMING_EX *,KSALLOCATOR_FRAMING_EX *,_GUID,_GUID,ulong *,_GUID *)
0x1800371ce  test    eax, eax
0x1800371d0  jnz     loc_18003714F
0x1800371d6  mov     edi, r15d
0x1800371d9  jmp     short loc_180037230
0x1800371db  cmp     rsi, rbx
0x1800371de  jnz     short loc_18003721B
0x1800371e0  movups  xmm0, xmmword ptr [r14+r12*8]
0x1800371e5  mov     [rsp+1A0h+var_170], 1; int
0x1800371ed  lea     r8, [rsp+1A0h+var_150]; struct _GUID
0x1800371f2  mov     r9d, 2; unsigned int
0x1800371f8  mov     [rsp+1A0h+var_180], rdi; struct IKsPin **
0x1800371fd  mov     edx, r13d; unsigned int
0x180037200  mov     rcx, rbx; struct IKsPin *
0x180037203  movdqu  xmmword ptr [rsp+1A0h+var_150.Data1], xmm0
0x180037209  call    ?AssignPipeAllocatorHandler@@YAHPEAUIKsPin@@KU_GUID@@KPEAPEAU1@PEAKH@Z; AssignPipeAllocatorHandler(IKsPin *,ulong,_GUID,ulong,IKsPin * *,ulong *,int)
0x18003720e  mov     edx, r13d; unsigned int
0x180037211  mov     rcx, rbx; struct IKsPin *
0x180037214  call    ?ResolvePipeDimensions@@YAJPEAUIKsPin@@KK@Z; ResolvePipeDimensions(IKsPin *,ulong,ulong)
0x180037219  jmp     short loc_180037229
0x18003721b  mov     r9d, r13d; unsigned int
0x18003721e  mov     r8, rbx; struct IKsPin *
0x180037221  mov     rcx, rsi; struct IKsPin *
0x180037224  call    ?AddPinToPipeUnconditional@@YAHPEAUIKsPin@@K0K@Z; AddPinToPipeUnconditional(IKsPin *,ulong,IKsPin *,ulong)
0x180037229  lea     r12, WPP_GLOBAL_Control
0x180037230  mov     rcx, r14; void *
0x180037233  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180037238  mov     rcx, cs:WPP_GLOBAL_Control
0x18003723f  cmp     rcx, r12
0x180037242  jz      short loc_180037262
0x180037244  cmp     byte ptr [rcx+19h], 2
0x180037248  jb      short loc_180037262
0x18003724a  mov     rcx, [rcx+10h]
0x18003724e  lea     r8, WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids
0x180037255  mov     edx, 0BDh
0x18003725a  mov     r9d, edi
0x18003725d  call    WPP_SF_d
0x180037262  mov     eax, edi
0x180037264  mov     rcx, [rbp+0A0h+var_70]
0x180037268  xor     rcx, rsp; StackCookie
0x18003726b  call    __security_check_cookie
0x180037270  lea     r11, [rsp+1A0h+var_38]
0x180037278  movaps  xmm6, xmmword ptr [r11-18h]
0x18003727d  movaps  xmm7, xmmword ptr [r11-28h]
0x180037282  mov     rsp, r11
0x180037285  pop     r15
0x180037287  pop     r14
0x180037289  pop     r13
0x18003728b  pop     r12
  ... truncated ...
```
