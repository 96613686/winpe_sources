# FindCommonMemoryTypeBasedOnPipeAndPin(IKsPin *,ulong,IKsPin *,ulong,int,_GUID *)

- ea: `0x1002a5bd`
- end: `0x1002aa99`
- name: `?FindCommonMemoryTypeBasedOnPipeAndPin@@YGHPAUIKsPin@@K0KHPAU_GUID@@@Z`
- size: `1244`
- prototype: `unsigned int __userpurge@<eax>(unsigned int@<edx>, _DWORD **@<ecx>, struct _GUID, unsigned int, struct IKsPin *, unsigned int, int, struct _GUID *)`
- caller_count: `3`
- callee_count: `16`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x10022cf8`
- `0x10023d3c`
- `0x1002aa9f`

## callees

- `0x1000665f`
- `0x10006689`
- `0x10025d1d`
- `0x100267ff`
- `0x10026992`
- `0x10026beb`
- `0x1002861d`
- `0x10029c63`
- `0x1002a5bd`
- `0x1002abaa`
- `0x1002ad94`
- `0x1002af02`
- `0x1002d510`
- `0x1003a6f2`
- `0x1003a72c`
- `0x1003aba0`

## pseudocode

```c
unsigned int __userpurge FindCommonMemoryTypeBasedOnPipeAndPin@<eax>(
        unsigned int a1@<edx>,
        _DWORD **a2@<ecx>,
        struct _GUID a3,
        unsigned int a4,
        struct IKsPin *a5,
        unsigned int a6,
        int a7,
        struct _GUID *a8)
{
  unsigned int PinFlags; // edi
  PVOID *v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // esi
  struct KSALLOCATOR_FRAMING_EX *v14; // eax
  int AllPinMemoryTypesBasedOnBus; // eax
  unsigned int v16; // eax
  int v17; // esi
  unsigned int v18; // ecx
  struct IKsPin *v19; // ecx
  struct _GUID v21; // [esp-18h] [ebp-F8h]
  struct _GUID v22; // [esp-14h] [ebp-F4h]
  struct _GUID v23; // [esp-Ch] [ebp-ECh]
  enum FRAMING_PROP *v24; // [esp+0h] [ebp-E0h]
  struct IKsPin *v25; // [esp+0h] [ebp-E0h]
  unsigned int *v26; // [esp+0h] [ebp-E0h]
  unsigned int *v27; // [esp+0h] [ebp-E0h]
  unsigned int *v28; // [esp+0h] [ebp-E0h]
  unsigned int v29; // [esp+0h] [ebp-E0h]
  enum FRAMING_CACHE_OPS v30; // [esp+4h] [ebp-DCh]
  struct KS_FRAMING_FIXED *v31; // [esp+4h] [ebp-DCh]
  struct _GUID *v32; // [esp+4h] [ebp-DCh]
  struct _GUID *v33; // [esp+4h] [ebp-DCh]
  struct _GUID *v34; // [esp+4h] [ebp-DCh]
  unsigned int v35; // [esp+4h] [ebp-DCh]
  unsigned int v36; // [esp+4h] [ebp-DCh]
  struct _GUID v37; // [esp+Ch] [ebp-D4h] BYREF
  struct _GUID v38; // [esp+1Ch] [ebp-C4h] BYREF
  char *v39; // [esp+2Ch] [ebp-B4h]
  unsigned int v40; // [esp+30h] [ebp-B0h]
  struct IKsPin v41; // [esp+34h] [ebp-ACh] BYREF
  struct IKsPin v42; // [esp+38h] [ebp-A8h] BYREF
  void *Block; // [esp+3Ch] [ebp-A4h]
  unsigned int v44; // [esp+40h] [ebp-A0h]
  int v45; // [esp+44h] [ebp-9Ch] BYREF
  void *v46; // [esp+48h] [ebp-98h] BYREF
  int v47; // [esp+4Ch] [ebp-94h] BYREF
  char v48[4]; // [esp+50h] [ebp-90h]
  _DWORD *v49; // [esp+54h] [ebp-8Ch] BYREF
  struct KSALLOCATOR_FRAMING_EX v50; // [esp+58h] [ebp-88h] BYREF

  v40 = a1;
  memset(&v37, 0, sizeof(v37));
  *(_DWORD *)v48 = a2;
  v49 = 0;
  v46 = 0;
  PinFlags = 1;
  v50.PinFlags = 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_qq(
      0xB7u,
      &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids,
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (char)a2,
      a3.Data1);
  GetPinFramingFromCache((void **)&v49, a3.Data1, &v42, (struct KSALLOCATOR_FRAMING_EX **)1, v24, v30);
  if ( v42.__vftable != (IKsPin_vtbl *)1 )
  {
    if ( ((int (__thiscall *)(_DWORD, _DWORD, GUID *, int *))**a2)(
           **a2,
           *(_DWORD *)v48,
           &_GUID_e539cd90_a8b4_11d1_8189_00a0c9062802,
           &v47) >= 0 )
      (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v47 + 8))(*(_DWORD *)(*(_DWORD *)v47 + 8), v47);
    else
      v47 = 0;
    if ( (**(int (__thiscall ***)(_DWORD, unsigned int, GUID *, int *))a3.Data1)(
           **(_DWORD **)a3.Data1,
           a3.Data1,
           &_GUID_e539cd90_a8b4_11d1_8189_00a0c9062802,
           &v45) >= 0 )
      (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v45 + 8))(*(_DWORD *)(*(_DWORD *)v45 + 8), v45);
    else
      v45 = 0;
    v11 = (*(int (__thiscall **)(_DWORD, int, _DWORD))(*(_DWORD *)v47 + 24))(*(_DWORD *)(*(_DWORD *)v47 + 24), v47, 0);
    v12 = (*(int (__thiscall **)(_DWORD, int))(*(_DWORD *)v11 + 28))(*(_DWORD *)(*(_DWORD *)v11 + 28), v11);
    *(_QWORD *)&v23.Data1 = *(_QWORD *)(v12 + 20);
    *(_DWORD *)v23.Data4 = *(_DWORD *)(v12 + 28);
    if ( GetFramingFixedFromFramingByMemoryType(
           (struct KSALLOCATOR_FRAMING_EX *)&v50.OutputCompression,
           v49,
           *(struct KSALLOCATOR_FRAMING_EX **)(v12 + 16),
           v23,
           v31) )
    {
      if ( *(_DWORD *)v48 != a3.Data1 )
        AddPinToPipeUnconditional((struct IKsPin *)a3.Data1, *(unsigned int *)&a3.Data2, v25, (unsigned int)v32);
      PinFlags = v50.PinFlags;
      goto LABEL_54;
    }
    GetBusForKsPin(a3.Data1, &v38.Data1);
    v13 = *(_DWORD *)v48;
    v50.CountItems = 0;
    if ( *(_DWORD *)v48 == a3.Data1 )
    {
      if ( FindAllPinMemoryTypesBasedOnBus(0, v38, (unsigned int *)v25, v32) )
        goto LABEL_35;
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_q(0xB9u, &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2), a3.Data1);
        v10 = (PVOID *)WPP_GLOBAL_Control;
      }
      PinFlags = 0;
      v50.PinFlags = 0;
    }
    else
    {
      GetPinFramingFromCache(
        &v46,
        *(int (__thiscall ****)(_DWORD, _DWORD, GUID *, int *))v48,
        &v41,
        (struct KSALLOCATOR_FRAMING_EX **)1,
        (enum FRAMING_PROP *)v25,
        (enum FRAMING_CACHE_OPS)v32);
      if ( v41.__vftable == (IKsPin_vtbl *)1 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_q(0xBAu, &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2), v13);
        v50.PinFlags = 0;
      }
      GetBusForKsPin(v13, &v37.Data1);
      if ( !FindCommonMemoryTypesBasedOnBuses(&v50, 0, v38, v37, v27, v34) )
      {
        v10 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_40;
        WPP_SF_q(0xBBu, &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2), a3.Data1);
        goto LABEL_39;
      }
      v10 = (PVOID *)WPP_GLOBAL_Control;
      PinFlags = v50.PinFlags;
    }
    if ( !PinFlags )
      goto LABEL_55;
LABEL_35:
    v14 = (struct KSALLOCATOR_FRAMING_EX *)operator new[](saturated_mul(0x10u, v50.CountItems));
    Block = v14;
    if ( !v14 )
    {
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_40;
      WPP_SF_q(
        0xBCu,
        &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids,
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v50.CountItems);
LABEL_39:
      v10 = (PVOID *)WPP_GLOBAL_Control;
LABEL_40:
      PinFlags = 0;
      goto LABEL_55;
    }
    if ( *(_DWORD *)v48 == a3.Data1 )
    {
      AllPinMemoryTypesBasedOnBus = FindAllPinMemoryTypesBasedOnBus(v14, v38, v26, v33);
      PinFlags = AllPinMemoryTypesBasedOnBus != 0 ? v50.PinFlags : 0;
      if ( PinFlags )
        goto LABEL_43;
    }
    else
    {
      if ( FindCommonMemoryTypesBasedOnBuses(&v50, v14, v38, v37, v26, v33) )
      {
LABEL_43:
        v16 = 0;
        PinFlags = 0;
        v50.PinFlags = 0;
        v44 = 0;
        if ( v50.CountItems )
        {
          while ( 1 )
          {
            v39 = (char *)Block + 16 * v16;
            v22.Data1 = 0;
            *(_DWORD *)&v22.Data2 = *(_DWORD *)v39;
            *(_QWORD *)v22.Data4 = *(_QWORD *)(v39 + 4);
            v17 = *(_DWORD *)v48;
            if ( CanPipeUseMemoryType(
                   v40,
                   *(_DWORD ***)v48,
                   (struct IKsPin *)4,
                   1u,
                   v22,
                   *((enum KS_LogicalMemoryType *)v39 + 3),
                   (unsigned int)v28,
                   v35) )
            {
              break;
            }
            v16 = v44 + 1;
            v44 = v16;
            if ( v16 >= v50.CountItems )
              goto LABEL_52;
          }
          if ( v17 == a3.Data1 )
          {
            *(_DWORD *)v21.Data4 = *(_DWORD *)v39;
            *(_QWORD *)&v21.Data1 = v18 | 0x100000000LL;
            *(_DWORD *)&v21.Data4[4] = *((_DWORD *)v39 + 1);
            AssignPipeAllocatorHandler(
              *(int *)&a3.Data2,
              (IKsAllocatorEx_vtbl *)a3.Data1,
              (struct IKsPin *)2,
              0,
              v21,
              *((_DWORD *)v39 + 2),
              *((struct IKsPin ***)v39 + 3),
              v28,
              v35);
            ResolvePipeDimensions(*(int *)&a3.Data2, (IKsAllocatorEx_vtbl *)a3.Data1, v19, v29, v36);
          }
          else
          {
            AddPinToPipeUnconditional((struct IKsPin *)a3.Data1, *(unsigned int *)&a3.Data2, (struct IKsPin *)v28, v35);
          }
LABEL_52:
          PinFlags = v50.PinFlags;
        }
        goto LABEL_53;
      }
      PinFlags = 0;
    }
LABEL_53:
    operator delete[](Block);
    goto LABEL_54;
  }
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return PinFlags;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_q(0xB8u, &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2), a3.Data1);
LABEL_54:
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_55:
  if ( v10 != &WPP_GLOBAL_Control && *((_BYTE *)v10 + 25) >= 2u )
    WPP_SF_q(0xBDu, &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids, *((_QWORD *)v10 + 2), PinFlags);
  return PinFlags;
}

```

## disassembly

```asm
0x1002a5bd  mov     edi, edi
0x1002a5bf  push    ebp
0x1002a5c0  mov     ebp, esp
0x1002a5c2  sub     esp, 0D4h
0x1002a5c8  mov     eax, ___security_cookie
0x1002a5cd  xor     eax, ebp
0x1002a5cf  mov     [ebp+var_4], eax
0x1002a5d2  push    ebx
0x1002a5d3  mov     ebx, [ebp+arg_0.Data1]
0x1002a5d6  xor     eax, eax
0x1002a5d8  push    esi; unsigned int
0x1002a5d9  push    edi; struct IKsPin *
0x1002a5da  lea     edi, [ebp+var_D4]
0x1002a5e0  mov     [ebp+var_B0], edx
0x1002a5e6  stosd
0x1002a5e7  mov     esi, ecx
0x1002a5e9  mov     dword ptr [ebp+var_90], esi
0x1002a5ef  mov     [ebp+var_8C], 0
0x1002a5f9  mov     [ebp+var_98], 0
0x1002a603  stosd
0x1002a604  stosd
0x1002a605  stosd
0x1002a606  xor     edi, edi
0x1002a608  inc     edi
0x1002a609  mov     [ebp+var_88.PinFlags], edi
0x1002a60f  mov     eax, _WPP_GLOBAL_Control
0x1002a614  cmp     eax, offset _WPP_GLOBAL_Control
0x1002a619  jz      short loc_1002A638
0x1002a61b  cmp     byte ptr [eax+19h], 2
0x1002a61f  jb      short loc_1002A638
0x1002a621  push    ebx; char
0x1002a622  push    esi; char
0x1002a623  push    dword ptr [eax+14h]
0x1002a626  mov     edx, offset _WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids; MessageGuid
0x1002a62b  mov     ecx, 0B7h; MessageNumber
0x1002a630  push    dword ptr [eax+10h]; struct _GUID
0x1002a633  call    _WPP_SF_qq@24; WPP_SF_qq(x,x,x,x,x,x)
0x1002a638  push    1; struct KSALLOCATOR_FRAMING_EX **
0x1002a63a  lea     eax, [ebp+var_A8]
0x1002a640  mov     ecx, ebx
0x1002a642  push    eax; struct IKsPin *
0x1002a643  lea     edx, [ebp+var_8C]
0x1002a649  call    ?GetPinFramingFromCache@@YGHPAUIKsPin@@PAPAUKSALLOCATOR_FRAMING_EX@@PAW4FRAMING_PROP@@W4FRAMING_CACHE_OPS@@@Z; GetPinFramingFromCache(IKsPin *,KSALLOCATOR_FRAMING_EX * *,FRAMING_PROP *,FRAMING_CACHE_OPS)
0x1002a64e  cmp     [ebp+var_A8.__vftable], 1
0x1002a655  jnz     short loc_1002A68C
0x1002a657  mov     eax, _WPP_GLOBAL_Control
0x1002a65c  cmp     eax, offset _WPP_GLOBAL_Control
0x1002a661  jz      loc_1002AA86
0x1002a667  cmp     byte ptr [eax+19h], 2
0x1002a66b  jb      loc_1002AA63
0x1002a671  push    ebx; char
0x1002a672  push    dword ptr [eax+14h]
0x1002a675  mov     edx, offset _WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids; MessageGuid
0x1002a67a  mov     ecx, 0B8h; MessageNumber
0x1002a67f  push    dword ptr [eax+10h]; LoggerHandle
0x1002a682  call    _WPP_SF_q@20; WPP_SF_q(x,x,x,x,x)
0x1002a687  jmp     loc_1002AA5E
0x1002a68c  mov     eax, [esi]
0x1002a68e  mov     edi, offset __GUID_e539cd90_a8b4_11d1_8189_00a0c9062802
0x1002a693  mov     esi, [eax]
0x1002a695  lea     eax, [ebp+var_94]
0x1002a69b  push    eax
0x1002a69c  push    edi
0x1002a69d  push    dword ptr [ebp+var_90]
0x1002a6a3  mov     ecx, esi; this
0x1002a6a5  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1002a6ab  call    esi
0x1002a6ad  test    eax, eax
0x1002a6af  jns     short loc_1002A6BD
0x1002a6b1  mov     [ebp+var_94], 0
0x1002a6bb  jmp     short loc_1002A6D3
0x1002a6bd  mov     eax, [ebp+var_94]
0x1002a6c3  push    eax
0x1002a6c4  mov     ecx, [eax]
0x1002a6c6  mov     esi, [ecx+8]
0x1002a6c9  mov     ecx, esi; this
0x1002a6cb  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1002a6d1  call    esi
0x1002a6d3  mov     eax, [ebx]
0x1002a6d5  mov     esi, [eax]
0x1002a6d7  lea     eax, [ebp+var_9C]
0x1002a6dd  push    eax
0x1002a6de  push    edi
0x1002a6df  push    ebx; struct _GUID
0x1002a6e0  mov     ecx, esi; this
0x1002a6e2  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1002a6e8  call    esi
0x1002a6ea  test    eax, eax
0x1002a6ec  jns     short loc_1002A6FA
0x1002a6ee  mov     [ebp+var_9C], 0
0x1002a6f8  jmp     short loc_1002A710
0x1002a6fa  mov     eax, [ebp+var_9C]
0x1002a700  push    eax
0x1002a701  mov     ecx, [eax]
0x1002a703  mov     esi, [ecx+8]
0x1002a706  mov     ecx, esi; this
0x1002a708  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1002a70e  call    esi
0x1002a710  mov     ecx, [ebp+var_94]
0x1002a716  push    0
0x1002a718  push    ecx
0x1002a719  mov     eax, [ecx]
0x1002a71b  mov     esi, [eax+18h]
0x1002a71e  mov     ecx, esi; this
0x1002a720  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1002a726  call    esi
0x1002a728  push    eax
0x1002a729  mov     ecx, [eax]
0x1002a72b  mov     esi, [ecx+1Ch]
0x1002a72e  mov     ecx, esi; this
0x1002a730  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1002a736  call    esi
0x1002a738  mov     ecx, [ebp+var_8C]
0x1002a73e  lea     edx, [ebp+var_88.OutputCompression]
0x1002a741  sub     esp, 10h
0x1002a744  mov     edi, esp
0x1002a746  lea     esi, [eax+10h]
0x1002a749  movsd
0x1002a74a  movsd
0x1002a74b  movsd
0x1002a74c  movsd
0x1002a74d  call    ?GetFramingFixedFromFramingByMemoryType@@YGHPAUKSALLOCATOR_FRAMING_EX@@U_GUID@@PAUKS_FRAMING_FIXED@@@Z; GetFramingFixedFromFramingByMemoryType(KSALLOCATOR_FRAMING_EX *,_GUID,KS_FRAMING_FIXED *)
0x1002a752  test    eax, eax
0x1002a754  jz      short loc_1002A776
0x1002a756  mov     eax, dword ptr [ebp+var_90]
0x1002a75c  cmp     eax, ebx
0x1002a75e  jz      short loc_1002A76B
0x1002a760  push    dword ptr [ebp+arg_0.Data2]; unsigned int
0x1002a763  mov     ecx, eax
0x1002a765  push    ebx; struct IKsPin *
0x1002a766  call    ?AddPinToPipeUnconditional@@YGHPAUIKsPin@@K0K@Z; AddPinToPipeUnconditional(IKsPin *,ulong,IKsPin *,ulong)
0x1002a76b  mov     edi, [ebp+var_88.PinFlags]
0x1002a771  jmp     loc_1002AA5E
0x1002a776  lea     edx, [ebp+var_C4]
0x1002a77c  mov     ecx, ebx
0x1002a77e  call    ?GetBusForKsPin@@YGHPAUIKsPin@@PAU_GUID@@@Z; GetBusForKsPin(IKsPin *,_GUID *)
0x1002a783  mov     esi, dword ptr [ebp+var_90]
0x1002a789  mov     [ebp+var_88.CountItems], 0
0x1002a793  cmp     esi, ebx
0x1002a795  jnz     short loc_1002A7FB
0x1002a797  mov     ecx, [ebp+var_8C]
0x1002a79d  lea     esi, [ebp+var_C4]
0x1002a7a3  sub     esp, 10h
0x1002a7a6  lea     edx, [ebp+var_88]
0x1002a7ac  mov     edi, esp
0x1002a7ae  push    0; Src
0x1002a7b0  movsd
0x1002a7b1  movsd
0x1002a7b2  movsd
0x1002a7b3  movsd
0x1002a7b4  call    ?FindAllPinMemoryTypesBasedOnBus@@YGHPAUKSALLOCATOR_FRAMING_EX@@U_GUID@@PAKPAU2@@Z; FindAllPinMemoryTypesBasedOnBus(KSALLOCATOR_FRAMING_EX *,_GUID,ulong *,_GUID *)
0x1002a7b9  test    eax, eax
0x1002a7bb  jnz     loc_1002A8D4
0x1002a7c1  mov     eax, _WPP_GLOBAL_Control
0x1002a7c6  cmp     eax, offset _WPP_GLOBAL_Control
0x1002a7cb  jz      short loc_1002A7EE
0x1002a7cd  cmp     byte ptr [eax+19h], 2
0x1002a7d1  jb      short loc_1002A7EE
0x1002a7d3  push    ebx; char
0x1002a7d4  push    dword ptr [eax+14h]
0x1002a7d7  mov     edx, offset _WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids; MessageGuid
0x1002a7dc  mov     ecx, 0B9h; MessageNumber
0x1002a7e1  push    dword ptr [eax+10h]; LoggerHandle
0x1002a7e4  call    _WPP_SF_q@20; WPP_SF_q(x,x,x,x,x)
0x1002a7e9  mov     eax, _WPP_GLOBAL_Control
0x1002a7ee  xor     edi, edi
0x1002a7f0  mov     [ebp+var_88.PinFlags], edi
0x1002a7f6  jmp     loc_1002A8CC
0x1002a7fb  push    1; struct KSALLOCATOR_FRAMING_EX **
0x1002a7fd  lea     eax, [ebp+var_AC]
0x1002a803  mov     ecx, esi
0x1002a805  push    eax; struct IKsPin *
0x1002a806  lea     edx, [ebp+var_98]
0x1002a80c  call    ?GetPinFramingFromCache@@YGHPAUIKsPin@@PAPAUKSALLOCATOR_FRAMING_EX@@PAW4FRAMING_PROP@@W4FRAMING_CACHE_OPS@@@Z; GetPinFramingFromCache(IKsPin *,KSALLOCATOR_FRAMING_EX * *,FRAMING_PROP *,FRAMING_CACHE_OPS)
0x1002a811  cmp     [ebp+var_AC.__vftable], 1
0x1002a818  jnz     short loc_1002A84A
0x1002a81a  mov     eax, _WPP_GLOBAL_Control
0x1002a81f  cmp     eax, offset _WPP_GLOBAL_Control
0x1002a824  jz      short loc_1002A842
0x1002a826  cmp     byte ptr [eax+19h], 2
0x1002a82a  jb      short loc_1002A842
0x1002a82c  push    esi; char
0x1002a82d  push    dword ptr [eax+14h]; unsigned int
0x1002a830  mov     edx, offset _WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids; MessageGuid
0x1002a835  mov     ecx, 0BAh; MessageNumber
0x1002a83a  push    dword ptr [eax+10h]; LoggerHandle
0x1002a83d  call    _WPP_SF_q@20; WPP_SF_q(x,x,x,x,x)
0x1002a842  xor     ecx, ecx
0x1002a844  mov     [ebp+var_88.PinFlags], ecx
0x1002a84a  lea     edx, [ebp+var_D4]
0x1002a850  mov     ecx, esi
0x1002a852  call    ?GetBusForKsPin@@YGHPAUIKsPin@@PAU_GUID@@@Z; GetBusForKsPin(IKsPin *,_GUID *)
0x1002a857  sub     esp, 10h
0x1002a85a  mov     edx, [ebp+var_98]
0x1002a860  mov     edi, esp
0x1002a862  mov     ecx, [ebp+var_8C]
0x1002a868  lea     esi, [ebp+var_D4]
0x1002a86e  sub     esp, 10h
0x1002a871  lea     eax, [ebp+var_88]
0x1002a877  movsd
0x1002a878  movsd
0x1002a879  movsd
0x1002a87a  movsd
0x1002a87b  mov     edi, esp
0x1002a87d  lea     esi, [ebp+var_C4]
0x1002a883  push    0; Block
0x1002a885  push    eax; struct KSALLOCATOR_FRAMING_EX *
0x1002a886  movsd
0x1002a887  movsd
0x1002a888  movsd
0x1002a889  movsd
0x1002a88a  call    ?FindCommonMemoryTypesBasedOnBuses@@YGHPAUKSALLOCATOR_FRAMING_EX@@0U_GUID@@1PAKPAU2@@Z; FindCommonMemoryTypesBasedOnBuses(KSALLOCATOR_FRAMING_EX *,KSALLOCATOR_FRAMING_EX *,_GUID,_GUID,ulong *,_GUID *)
0x1002a88f  test    eax, eax
0x1002a891  jnz     short loc_1002A8C1
0x1002a893  mov     eax, _WPP_GLOBAL_Control
0x1002a898  cmp     eax, offset _WPP_GLOBAL_Control
0x1002a89d  jz      loc_1002A928
0x1002a8a3  cmp     byte ptr [eax+19h], 2
0x1002a8a7  jb      short loc_1002A928
0x1002a8a9  push    ebx; char
0x1002a8aa  push    dword ptr [eax+14h]
0x1002a8ad  mov     edx, offset _WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids; MessageGuid
0x1002a8b2  mov     ecx, 0BBh; MessageNumber
0x1002a8b7  push    dword ptr [eax+10h]; LoggerHandle
0x1002a8ba  call    _WPP_SF_q@20; WPP_SF_q(x,x,x,x,x)
0x1002a8bf  jmp     short loc_1002A923
0x1002a8c1  mov     eax, _WPP_GLOBAL_Control
0x1002a8c6  mov     edi, [ebp+var_88.PinFlags]
0x1002a8cc  test    edi, edi
0x1002a8ce  jz      loc_1002AA63
0x1002a8d4  mov     eax, [ebp+var_88.CountItems]
0x1002a8da  push    10h
0x1002a8dc  pop     ecx
0x1002a8dd  mul     ecx
0x1002a8df  push    0FFFFFFFFh
0x1002a8e1  pop     ecx
0x1002a8e2  cmovb   eax, ecx
0x1002a8e5  push    eax; struct IKsPin **
0x1002a8e6  call    ??_U@YAPAXI@Z; operator new[](uint)
0x1002a8eb  mov     [ebp+Block], eax
0x1002a8f1  pop     ecx
0x1002a8f2  test    eax, eax
0x1002a8f4  jnz     short loc_1002A92F
0x1002a8f6  mov     eax, _WPP_GLOBAL_Control
0x1002a8fb  cmp     eax, offset _WPP_GLOBAL_Control
0x1002a900  jz      short loc_1002A928
0x1002a902  cmp     byte ptr [eax+19h], 2
0x1002a906  jb      short loc_1002A928
0x1002a908  push    [ebp+var_88.CountItems]; char
0x1002a90e  mov     edx, offset _WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids; MessageGuid
0x1002a913  mov     ecx, 0BCh; MessageNumber
0x1002a918  push    dword ptr [eax+14h]
0x1002a91b  push    dword ptr [eax+10h]; LoggerHandle
0x1002a91e  call    _WPP_SF_q@20; WPP_SF_q(x,x,x,x,x)
0x1002a923  mov     eax, _WPP_GLOBAL_Control
0x1002a928  xor     edi, edi
0x1002a92a  jmp     loc_1002AA63
0x1002a92f  mov     ecx, [ebp+var_8C]
0x1002a935  sub     esp, 10h
0x1002a938  mov     edi, esp
0x1002a93a  cmp     dword ptr [ebp+var_90], ebx
0x1002a940  jnz     loc_1002A9D8
0x1002a946  lea     esi, [ebp+var_C4]
0x1002a94c  movsd
0x1002a94d  lea     edx, [ebp+var_88]
0x1002a953  push    eax; Src
0x1002a954  movsd
0x1002a955  movsd
0x1002a956  movsd
0x1002a957  call    ?FindAllPinMemoryTypesBasedOnBus@@YGHPAUKSALLOCATOR_FRAMING_EX@@U_GUID@@PAKPAU2@@Z; FindAllPinMemoryTypesBasedOnBus(KSALLOCATOR_FRAMING_EX *,_GUID,ulong *,_GUID *)
0x1002a95c  mov     edi, [ebp+var_88.PinFlags]
0x1002a962  neg     eax
0x1002a964  sbb     eax, eax
0x1002a966  and     edi, eax
0x1002a968  jz      loc_1002AA52
0x1002a96e  xor     eax, eax
0x1002a970  xor     edi, edi
0x1002a972  mov     [ebp+var_88.PinFlags], edi
0x1002a978  mov     [ebp+var_A0], eax
0x1002a97e  cmp     [ebp+var_88.CountItems], eax
0x1002a984  jbe     loc_1002AA52
0x1002a98a  mov     edx, [ebp+var_B0]
0x1002a990  sub     esp, 10h
0x1002a993  shl     eax, 4
0x1002a996  mov     edi, esp
0x1002a998  add     eax, [ebp+Block]
0x1002a99e  mov     esi, eax
0x1002a9a0  mov     [ebp+var_B4], eax
0x1002a9a6  push    0; struct _GUID
0x1002a9a8  push    1; unsigned int
0x1002a9aa  push    4; struct IKsPin *
0x1002a9ac  movsd
0x1002a9ad  movsd
0x1002a9ae  movsd
0x1002a9af  movsd
0x1002a9b0  mov     esi, dword ptr [ebp+var_90]
0x1002a9b6  mov     ecx, esi
0x1002a9b8  call    ?CanPipeUseMemoryType@@YGHPAUIKsPin@@KU_GUID@@W4KS_LogicalMemoryType@@KK@Z; CanPipeUseMemoryType(IKsPin *,ulong,_GUID,KS_LogicalMemoryType,ulong,ulong)
0x1002a9bd  test    eax, eax
0x1002a9bf  jnz     short loc_1002AA10
  ... truncated ...
```
