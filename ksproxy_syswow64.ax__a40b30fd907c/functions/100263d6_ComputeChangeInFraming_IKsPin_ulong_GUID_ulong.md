# ComputeChangeInFraming(IKsPin *,ulong,_GUID,ulong *)

- ea: `0x100263d6`
- end: `0x100266df`
- name: `?ComputeChangeInFraming@@YGHPAUIKsPin@@KU_GUID@@PAK@Z`
- size: `777`
- prototype: `int __userpurge@<eax>(int@<edx>, _DWORD **@<ecx>, struct IKsPin *, struct KSALLOCATOR_FRAMING_EX *, struct _GUID, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x10023d3c`

## callees

- `0x10025d1d`
- `0x1002628c`
- `0x100262a9`
- `0x100263d6`
- `0x10026beb`
- `0x10026d76`
- `0x1002d510`
- `0x1003aba0`

## pseudocode

```c
int __userpurge ComputeChangeInFraming@<eax>(
        int a1@<edx>,
        _DWORD **a2@<ecx>,
        struct IKsPin *a3,
        struct KSALLOCATOR_FRAMING_EX *a4,
        struct _GUID a5,
        unsigned int *a6)
{
  int v8; // eax
  KS_FRAMING_RANGE_WEIGHTED *p_FramingRange; // esi
  int v10; // eax
  int v11; // eax
  int v12; // ecx
  struct _GUID v13; // [esp-Ch] [ebp-128h]
  struct _GUID v14; // [esp-Ch] [ebp-128h]
  enum FRAMING_PROP *v15; // [esp+0h] [ebp-11Ch]
  enum FRAMING_PROP *v16; // [esp+0h] [ebp-11Ch]
  unsigned int v17; // [esp+0h] [ebp-11Ch]
  unsigned int v18; // [esp+0h] [ebp-11Ch]
  unsigned int v19; // [esp+0h] [ebp-11Ch]
  enum FRAMING_CACHE_OPS v20; // [esp+4h] [ebp-118h]
  enum FRAMING_CACHE_OPS v21; // [esp+4h] [ebp-118h]
  struct KS_FRAMING_FIXED *v22; // [esp+4h] [ebp-118h]
  struct KS_FRAMING_FIXED *v23; // [esp+4h] [ebp-118h]
  struct KS_FRAMING_FIXED *v24; // [esp+4h] [ebp-118h]
  struct KS_FRAMING_FIXED *v25; // [esp+4h] [ebp-118h]
  struct KS_FRAMING_FIXED *v26; // [esp+4h] [ebp-118h]
  struct IKsPin v27; // [esp+Ch] [ebp-110h] BYREF
  struct IKsPin v28; // [esp+10h] [ebp-10Ch] BYREF
  int v29; // [esp+14h] [ebp-108h] BYREF
  int v30; // [esp+18h] [ebp-104h]
  void *v31; // [esp+1Ch] [ebp-100h] BYREF
  void *v32; // [esp+20h] [ebp-FCh] BYREF
  struct KSALLOCATOR_FRAMING_EX v33; // [esp+24h] [ebp-F8h] BYREF
  struct KSALLOCATOR_FRAMING_EX v34; // [esp+9Ch] [ebp-80h] BYREF

  v30 = a1;
  v31 = 0;
  v32 = 0;
  if ( ((int (__thiscall *)(_DWORD, _DWORD **, GUID *, int *))**a2)(
         **a2,
         a2,
         &_GUID_e539cd90_a8b4_11d1_8189_00a0c9062802,
         &v29) < 0 )
  {
    v29 = 0;
    return 0;
  }
  (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v29 + 8))(*(_DWORD *)(*(_DWORD *)v29 + 8), v29);
  a3->__vftable = 0;
  if ( !GetPinFramingFromCache(
          &v31,
          (int (__thiscall ***)(_DWORD, _DWORD, GUID *, int *))a2,
          &v27,
          (struct KSALLOCATOR_FRAMING_EX **)2,
          v15,
          v20)
    || !GetPinFramingFromCache(&v32, (int (__thiscall ***)(_DWORD, _DWORD, GUID *, int *))a2, &v28, 0, v16, v21) )
  {
    return 0;
  }
  if ( v27.__vftable == (IKsPin_vtbl *)1 )
  {
    if ( v28.__vftable == (IKsPin_vtbl *)1 )
      goto LABEL_53;
    *(_QWORD *)&v13.Data1 = *(_QWORD *)&a5.Data1;
    *(_DWORD *)v13.Data4 = *(_DWORD *)a5.Data4;
    if ( !GetFramingFixedFromFramingByMemoryType(a4, v13, v22) )
    {
      a3->__vftable = (IKsPin_vtbl *)((int)a3->__vftable | 1);
      GetFramingFixedFromFramingByIndex(&v33, v17, v23);
    }
    if ( (v33.FramingItem[0].MemoryFlags & 8) != 0 )
      a3->__vftable = (IKsPin_vtbl *)((int)a3->__vftable | 2);
    if ( v30 != 4 && !IsCompressionDontCare((struct KS_COMPRESSION)v33.FramingItem[0].PhysicalRange) )
      a3->__vftable = (IKsPin_vtbl *)((int)a3->__vftable | 4);
    LOBYTE(v8) = IsFramingRangeDontCare(*(struct KS_FRAMING_RANGE *)&v33.FramingItem[0].Frames);
    if ( !v8 )
      a3->__vftable = (IKsPin_vtbl *)((int)a3->__vftable | 8);
    p_FramingRange = &v33.FramingItem[0].FramingRange;
  }
  else
  {
    *(_QWORD *)&v13.Data1 = *(_QWORD *)&a5.Data1;
    *(_DWORD *)v13.Data4 = *(_DWORD *)a5.Data4;
    if ( v28.__vftable != (IKsPin_vtbl *)1 )
    {
      if ( !GetFramingFixedFromFramingByMemoryType(a4, v13, v22) )
        GetFramingFixedFromFramingByIndex(&v34, *(unsigned int *)&v14.Data4[4], v25);
      *(_QWORD *)&v14.Data1 = *(_QWORD *)&a5.Data1;
      *(_DWORD *)v14.Data4 = *(_DWORD *)a5.Data4;
      if ( !GetFramingFixedFromFramingByMemoryType(a4, v14, v25) )
        GetFramingFixedFromFramingByIndex(&v33, v19, v26);
      v12 = 0;
      while ( *(&v34.CountItems + v12) == *(&v33.CountItems + v12) )
      {
        if ( ++v12 == 4 )
          goto LABEL_40;
      }
      a3->__vftable = (IKsPin_vtbl *)((int)a3->__vftable | 1);
LABEL_40:
      if ( ((LOBYTE(v33.FramingItem[0].MemoryFlags) ^ LOBYTE(v34.FramingItem[0].MemoryFlags)) & 8) != 0 )
        a3->__vftable = (IKsPin_vtbl *)((int)a3->__vftable | 2);
      if ( v30 != 4
        && (v34.FramingItem[0].PhysicalRange.MinFrameSize != v33.FramingItem[0].PhysicalRange.MinFrameSize
         || v34.FramingItem[0].PhysicalRange.MaxFrameSize != v33.FramingItem[0].PhysicalRange.MaxFrameSize
         || v34.FramingItem[0].PhysicalRange.Stepping != v33.FramingItem[0].PhysicalRange.Stepping) )
      {
        a3->__vftable = (IKsPin_vtbl *)((int)a3->__vftable | 4);
      }
      if ( v34.FramingItem[0].Frames != v33.FramingItem[0].Frames
        || v34.FramingItem[0].FileAlignment != v33.FramingItem[0].FileAlignment )
      {
        a3->__vftable = (IKsPin_vtbl *)((int)a3->__vftable | 8);
      }
      if ( v34.FramingItem[0].FramingRange.Range.MinFrameSize == v33.FramingItem[0].FramingRange.Range.MinFrameSize
        && v34.FramingItem[0].FramingRange.Range.MaxFrameSize == v33.FramingItem[0].FramingRange.Range.MaxFrameSize )
      {
        goto LABEL_53;
      }
      goto LABEL_52;
    }
    if ( !GetFramingFixedFromFramingByMemoryType(a4, v13, v22) )
    {
      a3->__vftable = (IKsPin_vtbl *)((int)a3->__vftable | 1);
      GetFramingFixedFromFramingByIndex(&v34, v18, v24);
    }
    if ( (v34.FramingItem[0].MemoryFlags & 8) != 0 )
      a3->__vftable = (IKsPin_vtbl *)((int)a3->__vftable | 2);
    if ( v30 != 4 && !IsCompressionDontCare((struct KS_COMPRESSION)v34.FramingItem[0].PhysicalRange) )
      a3->__vftable = (IKsPin_vtbl *)((int)a3->__vftable | 4);
    LOBYTE(v11) = IsFramingRangeDontCare(*(struct KS_FRAMING_RANGE *)&v34.FramingItem[0].Frames);
    if ( !v11 )
      a3->__vftable = (IKsPin_vtbl *)((int)a3->__vftable | 8);
    p_FramingRange = &v34.FramingItem[0].FramingRange;
  }
  LOBYTE(v10) = IsFramingRangeDontCare(p_FramingRange->Range);
  if ( !v10 )
LABEL_52:
    a3->__vftable = (IKsPin_vtbl *)((int)a3->__vftable | 0x10);
LABEL_53:
  (*(void (__thiscall **)(_DWORD, int, void *, struct IKsPin *, int))(*(_DWORD *)v29 + 16))(
    *(_DWORD *)(*(_DWORD *)v29 + 16),
    v29,
    v32,
    &v28,
    2);
  return 1;
}

```

## disassembly

```asm
0x100263d6  mov     edi, edi
0x100263d8  push    ebp
0x100263d9  mov     ebp, esp
0x100263db  sub     esp, 110h
0x100263e1  mov     eax, ___security_cookie
0x100263e6  xor     eax, ebp
0x100263e8  mov     [ebp+var_4], eax
0x100263eb  push    ebx
0x100263ec  mov     ebx, [ebp+arg_0]
0x100263ef  push    esi; struct KS_FRAMING_FIXED *
0x100263f0  push    edi; unsigned int
0x100263f1  mov     edi, ecx
0x100263f3  mov     [ebp+var_104], edx
0x100263f9  mov     [ebp+var_100], 0
0x10026403  mov     [ebp+var_FC], 0
0x1002640d  mov     eax, [edi]
0x1002640f  mov     esi, [eax]
0x10026411  lea     eax, [ebp+var_108]
0x10026417  push    eax
0x10026418  push    offset __GUID_e539cd90_a8b4_11d1_8189_00a0c9062802
0x1002641d  push    edi; struct _GUID
0x1002641e  mov     ecx, esi; this
0x10026420  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10026426  call    esi
0x10026428  test    eax, eax
0x1002642a  jns     short loc_10026449
0x1002642c  mov     [ebp+var_108], 0
0x10026436  xor     eax, eax
0x10026438  mov     ecx, [ebp+var_4]
0x1002643b  pop     edi
0x1002643c  pop     esi
0x1002643d  xor     ecx, ebp; StackCookie
0x1002643f  pop     ebx
0x10026440  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10026445  leave
0x10026446  retn    14h
0x10026449  mov     eax, [ebp+var_108]
0x1002644f  push    eax
0x10026450  mov     ecx, [eax]
0x10026452  mov     esi, [ecx+8]
0x10026455  mov     ecx, esi; this
0x10026457  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1002645d  call    esi
0x1002645f  push    2; struct KSALLOCATOR_FRAMING_EX **
0x10026461  lea     eax, [ebp+var_110]
0x10026467  mov     dword ptr [ebx], 0
0x1002646d  push    eax; struct IKsPin *
0x1002646e  lea     edx, [ebp+var_100]
0x10026474  mov     ecx, edi
0x10026476  call    ?GetPinFramingFromCache@@YGHPAUIKsPin@@PAPAUKSALLOCATOR_FRAMING_EX@@PAW4FRAMING_PROP@@W4FRAMING_CACHE_OPS@@@Z; GetPinFramingFromCache(IKsPin *,KSALLOCATOR_FRAMING_EX * *,FRAMING_PROP *,FRAMING_CACHE_OPS)
0x1002647b  test    eax, eax
0x1002647d  jz      short loc_10026436
0x1002647f  push    0; struct KSALLOCATOR_FRAMING_EX **
0x10026481  lea     eax, [ebp+var_10C]
0x10026487  mov     ecx, edi
0x10026489  push    eax; struct IKsPin *
0x1002648a  lea     edx, [ebp+var_FC]
0x10026490  call    ?GetPinFramingFromCache@@YGHPAUIKsPin@@PAPAUKSALLOCATOR_FRAMING_EX@@PAW4FRAMING_PROP@@W4FRAMING_CACHE_OPS@@@Z; GetPinFramingFromCache(IKsPin *,KSALLOCATOR_FRAMING_EX * *,FRAMING_PROP *,FRAMING_CACHE_OPS)
0x10026495  test    eax, eax
0x10026497  jz      short loc_10026436
0x10026499  cmp     [ebp+var_110.__vftable], 1
0x100264a0  jnz     loc_10026554
0x100264a6  cmp     [ebp+var_10C.__vftable], 1
0x100264ad  jz      loc_100266B3
0x100264b3  mov     ecx, [ebp+var_FC]
0x100264b9  lea     esi, [ebp+arg_4]
0x100264bc  sub     esp, 10h
0x100264bf  lea     edx, [ebp+var_F8]
0x100264c5  mov     edi, esp
0x100264c7  movsd
0x100264c8  movsd
0x100264c9  movsd
0x100264ca  movsd
0x100264cb  call    ?GetFramingFixedFromFramingByMemoryType@@YGHPAUKSALLOCATOR_FRAMING_EX@@U_GUID@@PAUKS_FRAMING_FIXED@@@Z; GetFramingFixedFromFramingByMemoryType(KSALLOCATOR_FRAMING_EX *,_GUID,KS_FRAMING_FIXED *)
0x100264d0  test    eax, eax
0x100264d2  jnz     short loc_100264EB
0x100264d4  mov     ecx, [ebp+var_FC]
0x100264da  lea     eax, [ebp+var_F8]
0x100264e0  or      dword ptr [ebx], 1
0x100264e3  xor     edx, edx
0x100264e5  push    eax; struct KSALLOCATOR_FRAMING_EX *
0x100264e6  call    ?GetFramingFixedFromFramingByIndex@@YGHPAUKSALLOCATOR_FRAMING_EX@@KPAUKS_FRAMING_FIXED@@@Z; GetFramingFixedFromFramingByIndex(KSALLOCATOR_FRAMING_EX *,ulong,KS_FRAMING_FIXED *)
0x100264eb  test    byte ptr [ebp+var_F8.FramingItem.MemoryFlags], 8
0x100264f2  jz      short loc_100264F7
0x100264f4  or      dword ptr [ebx], 2
0x100264f7  cmp     [ebp+var_104], 4
0x100264fe  jz      short loc_1002651A
0x10026500  sub     esp, 0Ch
0x10026503  lea     esi, [ebp+var_F8.FramingItem.PhysicalRange]
0x10026509  mov     edi, esp
0x1002650b  movsd
0x1002650c  movsd
0x1002650d  movsd
0x1002650e  call    ?IsCompressionDontCare@@YGHUKS_COMPRESSION@@@Z; IsCompressionDontCare(KS_COMPRESSION)
0x10026513  test    eax, eax
0x10026515  jnz     short loc_1002651A
0x10026517  or      dword ptr [ebx], 4
0x1002651a  sub     esp, 0Ch
0x1002651d  lea     esi, [ebp+var_F8.FramingItem.Frames]
0x10026523  mov     edi, esp
0x10026525  movsd
0x10026526  movsd
0x10026527  movsd
0x10026528  call    ?IsFramingRangeDontCare@@YGHUKS_FRAMING_RANGE@@@Z; IsFramingRangeDontCare(KS_FRAMING_RANGE)
0x1002652d  test    eax, eax
0x1002652f  jnz     short loc_10026534
0x10026531  or      dword ptr [ebx], 8
0x10026534  lea     esi, [ebp+var_F8.FramingItem.FramingRange]
0x1002653a  sub     esp, 0Ch
0x1002653d  mov     edi, esp
0x1002653f  movsd
0x10026540  movsd
0x10026541  movsd
0x10026542  call    ?IsFramingRangeDontCare@@YGHUKS_FRAMING_RANGE@@@Z; IsFramingRangeDontCare(KS_FRAMING_RANGE)
0x10026547  test    eax, eax
0x10026549  jnz     loc_100266B3
0x1002654f  jmp     loc_100266B0
0x10026554  mov     ecx, [ebp+var_100]
0x1002655a  lea     esi, [ebp+arg_4]
0x1002655d  sub     esp, 10h
0x10026560  lea     edx, [ebp+var_80]
0x10026563  cmp     [ebp+var_10C.__vftable], 1
0x1002656a  mov     edi, esp
0x1002656c  movsd
0x1002656d  movsd
0x1002656e  movsd
0x1002656f  movsd
0x10026570  jnz     short loc_100265D7
0x10026572  call    ?GetFramingFixedFromFramingByMemoryType@@YGHPAUKSALLOCATOR_FRAMING_EX@@U_GUID@@PAUKS_FRAMING_FIXED@@@Z; GetFramingFixedFromFramingByMemoryType(KSALLOCATOR_FRAMING_EX *,_GUID,KS_FRAMING_FIXED *)
0x10026577  test    eax, eax
0x10026579  jnz     short loc_1002658F
0x1002657b  mov     ecx, [ebp+var_100]
0x10026581  lea     eax, [ebp+var_80]
0x10026584  or      dword ptr [ebx], 1
0x10026587  xor     edx, edx
0x10026589  push    eax; struct KSALLOCATOR_FRAMING_EX *
0x1002658a  call    ?GetFramingFixedFromFramingByIndex@@YGHPAUKSALLOCATOR_FRAMING_EX@@KPAUKS_FRAMING_FIXED@@@Z; GetFramingFixedFromFramingByIndex(KSALLOCATOR_FRAMING_EX *,ulong,KS_FRAMING_FIXED *)
0x1002658f  test    byte ptr [ebp+var_80.FramingItem.MemoryFlags], 8
0x10026593  jz      short loc_10026598
0x10026595  or      dword ptr [ebx], 2
0x10026598  cmp     [ebp+var_104], 4
0x1002659f  jz      short loc_100265B8
0x100265a1  sub     esp, 0Ch
0x100265a4  lea     esi, [ebp+var_80.FramingItem.PhysicalRange]
0x100265a7  mov     edi, esp
0x100265a9  movsd
0x100265aa  movsd
0x100265ab  movsd
0x100265ac  call    ?IsCompressionDontCare@@YGHUKS_COMPRESSION@@@Z; IsCompressionDontCare(KS_COMPRESSION)
0x100265b1  test    eax, eax
0x100265b3  jnz     short loc_100265B8
0x100265b5  or      dword ptr [ebx], 4
0x100265b8  sub     esp, 0Ch
0x100265bb  lea     esi, [ebp+var_80.FramingItem.Frames]
0x100265be  mov     edi, esp
0x100265c0  movsd
0x100265c1  movsd
0x100265c2  movsd
0x100265c3  call    ?IsFramingRangeDontCare@@YGHUKS_FRAMING_RANGE@@@Z; IsFramingRangeDontCare(KS_FRAMING_RANGE)
0x100265c8  test    eax, eax
0x100265ca  jnz     short loc_100265CF
0x100265cc  or      dword ptr [ebx], 8
0x100265cf  lea     esi, [ebp+var_80.FramingItem.FramingRange]
0x100265d2  jmp     loc_1002653A
0x100265d7  call    ?GetFramingFixedFromFramingByMemoryType@@YGHPAUKSALLOCATOR_FRAMING_EX@@U_GUID@@PAUKS_FRAMING_FIXED@@@Z; GetFramingFixedFromFramingByMemoryType(KSALLOCATOR_FRAMING_EX *,_GUID,KS_FRAMING_FIXED *)
0x100265dc  test    eax, eax
0x100265de  jnz     short loc_100265F1
0x100265e0  mov     ecx, [ebp+var_100]
0x100265e6  lea     eax, [ebp+var_80]
0x100265e9  push    eax; struct KSALLOCATOR_FRAMING_EX *
0x100265ea  xor     edx, edx
0x100265ec  call    ?GetFramingFixedFromFramingByIndex@@YGHPAUKSALLOCATOR_FRAMING_EX@@KPAUKS_FRAMING_FIXED@@@Z; GetFramingFixedFromFramingByIndex(KSALLOCATOR_FRAMING_EX *,ulong,KS_FRAMING_FIXED *)
0x100265f1  mov     ecx, [ebp+var_FC]
0x100265f7  lea     esi, [ebp+arg_4]
0x100265fa  sub     esp, 10h
0x100265fd  lea     edx, [ebp+var_F8]
0x10026603  mov     edi, esp
0x10026605  movsd
0x10026606  movsd
0x10026607  movsd
0x10026608  movsd
0x10026609  call    ?GetFramingFixedFromFramingByMemoryType@@YGHPAUKSALLOCATOR_FRAMING_EX@@U_GUID@@PAUKS_FRAMING_FIXED@@@Z; GetFramingFixedFromFramingByMemoryType(KSALLOCATOR_FRAMING_EX *,_GUID,KS_FRAMING_FIXED *)
0x1002660e  test    eax, eax
0x10026610  jnz     short loc_10026626
0x10026612  mov     ecx, [ebp+var_FC]
0x10026618  lea     eax, [ebp+var_F8]
0x1002661e  push    eax; struct KSALLOCATOR_FRAMING_EX *
0x1002661f  xor     edx, edx
0x10026621  call    ?GetFramingFixedFromFramingByIndex@@YGHPAUKSALLOCATOR_FRAMING_EX@@KPAUKS_FRAMING_FIXED@@@Z; GetFramingFixedFromFramingByIndex(KSALLOCATOR_FRAMING_EX *,ulong,KS_FRAMING_FIXED *)
0x10026626  lea     edx, [ebp+var_80]
0x10026629  xor     ecx, ecx
0x1002662b  lea     esi, [ebp+var_F8]
0x10026631  mov     eax, [edx+ecx*4]
0x10026634  cmp     eax, [esi+ecx*4]
0x10026637  jnz     short loc_10026641
0x10026639  inc     ecx
0x1002663a  cmp     ecx, 4
0x1002663d  jnz     short loc_10026631
0x1002663f  jmp     short loc_10026644
0x10026641  or      dword ptr [ebx], 1
0x10026644  mov     eax, [ebp+var_80.FramingItem.MemoryFlags]
0x10026647  xor     eax, [ebp+var_F8.FramingItem.MemoryFlags]
0x1002664d  test    al, 8
0x1002664f  jz      short loc_10026654
0x10026651  or      dword ptr [ebx], 2
0x10026654  cmp     [ebp+var_104], 4
0x1002665b  jz      short loc_10026681
0x1002665d  mov     eax, [ebp+var_80.FramingItem.PhysicalRange.MinFrameSize]
0x10026660  cmp     eax, [ebp+var_F8.FramingItem.PhysicalRange.MinFrameSize]
0x10026666  jnz     short loc_1002667E
0x10026668  mov     eax, [ebp+var_80.FramingItem.PhysicalRange.MaxFrameSize]
0x1002666b  cmp     eax, [ebp+var_F8.FramingItem.PhysicalRange.MaxFrameSize]
0x10026671  jnz     short loc_1002667E
0x10026673  mov     eax, [ebp+var_80.FramingItem.PhysicalRange.Stepping]
0x10026676  cmp     eax, [ebp+var_F8.FramingItem.PhysicalRange.Stepping]
0x1002667c  jz      short loc_10026681
0x1002667e  or      dword ptr [ebx], 4
0x10026681  mov     eax, [ebp+var_80.FramingItem.Frames]
0x10026684  cmp     eax, [ebp+var_F8.FramingItem.Frames]
0x1002668a  jnz     short loc_10026697
0x1002668c  mov     eax, dword ptr [ebp+var_80.FramingItem.___u6]
0x1002668f  cmp     eax, dword ptr [ebp+var_F8.FramingItem.___u6]
0x10026695  jz      short loc_1002669A
0x10026697  or      dword ptr [ebx], 8
0x1002669a  mov     eax, [ebp+var_80.FramingItem.FramingRange.Range.MinFrameSize]
0x1002669d  cmp     eax, [ebp+var_F8.FramingItem.FramingRange.Range.MinFrameSize]
0x100266a3  jnz     short loc_100266B0
0x100266a5  mov     eax, [ebp+var_80.FramingItem.FramingRange.Range.MaxFrameSize]
0x100266a8  cmp     eax, [ebp+var_F8.FramingItem.FramingRange.Range.MaxFrameSize]
0x100266ae  jz      short loc_100266B3
0x100266b0  or      dword ptr [ebx], 10h
0x100266b3  mov     ecx, [ebp+var_108]
0x100266b9  lea     edx, [ebp+var_10C]
0x100266bf  push    2
0x100266c1  push    edx
0x100266c2  push    [ebp+var_FC]
0x100266c8  mov     esi, [ecx]
0x100266ca  push    ecx
0x100266cb  mov     ecx, [esi+10h]; this
0x100266ce  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x100266d4  call    dword ptr [esi+10h]
0x100266d7  xor     eax, eax
0x100266d9  inc     eax
0x100266da  jmp     loc_10026438
```
