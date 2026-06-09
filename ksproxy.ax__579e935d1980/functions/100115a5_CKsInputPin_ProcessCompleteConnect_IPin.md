# CKsInputPin::ProcessCompleteConnect(IPin *)

- ea: `0x100115a5`
- end: `0x10011887`
- name: `?ProcessCompleteConnect@CKsInputPin@@QAGJPAUIPin@@@Z`
- size: `738`
- prototype: `int(CKsInputPin *__hidden this, struct IPin *)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x10011920`
- `0x10012420`

## callees

- `0x100064e5`
- `0x100090c5`
- `0x1000def7`
- `0x100115a5`
- `0x1001fd03`
- `0x1001fe62`
- `0x1001feac`
- `0x10020525`
- `0x10020593`
- `0x10021163`
- `0x1002191f`
- `0x1002d510`

## import_xrefs

- `ole32!CoCreateInstance` at `0x10011801`
- `ole32!CoCreateInstance` at `0x10011801`

## pseudocode

```c
int __fastcall CKsInputPin::ProcessCompleteConnect(int a1, _DWORD *a2, CKsInputPin *this)
{
  _DWORD *v4; // eax
  _DWORD *v5; // esi
  int *v6; // eax
  int CompatibleInterface; // edi
  int *v8; // eax
  int result; // eax
  int v10; // edx
  int v11; // eax
  _DWORD *v12; // esi
  int v13; // eax
  int v14; // [esp-4h] [ebp-5Ch]
  struct CBasePin *v15; // [esp+0h] [ebp-58h]
  struct IKsPin *v16; // [esp+0h] [ebp-58h]
  void *v17; // [esp+0h] [ebp-58h]
  struct IKsPin *v18; // [esp+4h] [ebp-54h]
  struct KSIDENTIFIER *v19; // [esp+4h] [ebp-54h]
  struct CKsProxy *v20; // [esp+4h] [ebp-54h]
  struct IKsPin v21[6]; // [esp+10h] [ebp-48h] BYREF
  struct IKsPin v22[7]; // [esp+28h] [ebp-30h] BYREF
  int v23; // [esp+44h] [ebp-14h] BYREF
  int v24; // [esp+48h] [ebp-10h]
  int *v25; // [esp+4Ch] [ebp-Ch]
  struct KSIDENTIFIER *v26; // [esp+50h] [ebp-8h]
  _DWORD **v27; // [esp+54h] [ebp-4h] BYREF

  if ( *(_DWORD *)(a1 + 252) )
  {
    CompatibleInterface = 0;
    v24 = a1 + 220;
    goto LABEL_25;
  }
  v4 = (_DWORD *)*a2;
  v26 = 0;
  if ( ((int (__thiscall *)(_DWORD, _DWORD *, GUID *, _DWORD ***))*v4)(
         *v4,
         a2,
         &_GUID_b61178d1_a2d9_11cf_9e53_00aa00a216a1,
         &v27) >= 0 )
  {
    v5 = (_DWORD *)(a1 + 276);
    if ( *(_DWORD *)(a1 + 272) == 3 )
      *v5 = ChooseCommunicationMethod(v15, v18);
    v6 = (int *)(a1 + 220);
    v24 = a1 + 220;
    if ( !a1 )
      v6 = 0;
    v25 = v6;
    CompatibleInterface = FindCompatibleInterface(v21, (struct IKsPin *)v15, (struct KSIDENTIFIER *)v18);
    if ( CompatibleInterface >= 0 )
    {
      CompatibleInterface = FindCompatibleMedium(v22, v16, v19);
      if ( CompatibleInterface >= 0 )
      {
        if ( CompatibleInterface == 1 )
        {
          v26 = 0;
          *(_DWORD *)(a1 + 332) = 1;
        }
        else
        {
          if ( *v5 == 2 )
          {
            CompatibleInterface = ((int (__thiscall *)(_DWORD, _DWORD **, GUID *, int *))**v27)(
                                    **v27,
                                    v27,
                                    &_GUID_423c13a2_2070_11d0_9ef7_00aa00a216a1,
                                    &v23);
            if ( CompatibleInterface >= 0 )
            {
              CompatibleInterface = ((int (__thiscall *)(_DWORD, _DWORD **, struct IKsPin *, struct IKsPin *))(*v27)[5])(
                                      (*v27)[5],
                                      v27,
                                      v21,
                                      v22);
              v26 = (struct KSIDENTIFIER *)(*(int (__thiscall **)(_DWORD, int))(*(_DWORD *)v23 + 12))(
                                             *(_DWORD *)(*(_DWORD *)v23 + 12),
                                             v23);
              (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v23 + 8))(*(_DWORD *)(*(_DWORD *)v23 + 8), v23);
            }
          }
          else
          {
            v26 = 0;
          }
          *(_DWORD *)(a1 + 332) = 0;
        }
      }
    }
    ((void (__thiscall *)(_DWORD, _DWORD **))(*v27)[2])((*v27)[2], v27);
    if ( CompatibleInterface < 0 )
      return CompatibleInterface;
    goto LABEL_22;
  }
  *(_DWORD *)(a1 + 276) = 1;
  v8 = (int *)(a1 + 220);
  v24 = a1 + 220;
  if ( !a1 )
    v8 = 0;
  v25 = v8;
  result = FindCompatiblePinFactoryIdentifier(
             0,
             v8,
             (struct IKsPin *)5,
             v21,
             (unsigned int)v15,
             (struct KSIDENTIFIER *)v18);
  if ( result >= 0 )
  {
    v26 = 0;
    v22[0] = (struct IKsPin)_GUID_4747b320_62ce_11cf_a5d6_28db04c10000.Data1;
    v22[1] = *(struct IKsPin *)&_GUID_4747b320_62ce_11cf_a5d6_28db04c10000.Data2;
    v22[2] = *(struct IKsPin *)_GUID_4747b320_62ce_11cf_a5d6_28db04c10000.Data4;
    v22[3] = *(struct IKsPin *)&_GUID_4747b320_62ce_11cf_a5d6_28db04c10000.Data4[4];
    v22[4].__vftable = 0;
    v22[5].__vftable = 0;
LABEL_22:
    CompatibleInterface = CreatePinHandle(
                            v22,
                            v21,
                            v26,
                            (struct KSIDENTIFIER *)(a1 + 52),
                            *(_DWORD **)(a1 + 40),
                            *(struct CMediaType **)(a1 + 268),
                            (struct CKsProxy *)0x40000000,
                            (void **)(a1 + 252),
                            (unsigned int)v16,
                            (void **)v19);
    v23 = CompatibleInterface;
    if ( CompatibleInterface < 0 )
      return CompatibleInterface;
    v10 = *(_DWORD *)(a1 + 40);
    qmemcpy((void *)(a1 + 280), v21, 0x18u);
    v14 = (int)v25;
    qmemcpy((void *)(a1 + 304), v22, 0x18u);
    AggregateSets(*(_DWORD *)(a1 + 252), *(HKEY *)(v10 + 296), (_DWORD *)(a1 + 368), v14);
    v11 = EstablishQualitySupport(*(struct IKsPin **)(a1 + 40), v17, v20);
    CompatibleInterface = v23;
    *(_DWORD *)(a1 + 392) = v11;
LABEL_25:
    v12 = (_DWORD *)(a1 + 264);
    if ( *(_DWORD *)(a1 + 264) || *(_DWORD *)(a1 + 276) == 4 )
      goto LABEL_41;
    CompatibleInterface = CoCreateInstance(
                            (const IID *const)(a1 + 280),
                            0,
                            0x401u,
                            &_GUID_d3abc7e0_9a61_11d0_a40d_00a0c9223196,
                            (LPVOID *)(a1 + 264));
    if ( *v12 )
    {
      v13 = v24;
      if ( !a1 )
        v13 = 0;
      (*(void (__thiscall **)(_DWORD, _DWORD, int))(*(_DWORD *)*v12 + 12))(*(_DWORD *)(*(_DWORD *)*v12 + 12), *v12, v13);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), *(_DWORD *)(*(_DWORD *)(a1 + 40) + 60), *(_DWORD *)(a1 + 20));
    }
    if ( CompatibleInterface >= 0 )
    {
LABEL_41:
      if ( *(_DWORD *)(a1 + 332) )
        CompatibleInterface = CKsProxy::StartIoThread((CKsProxy *)v15);
      if ( CompatibleInterface >= 0 )
        return CKsProxy::InitiateEndOfStreamNotification((CKsProxy *)v15, v18);
    }
    return CompatibleInterface;
  }
  return result;
}

```

## disassembly

```asm
0x100115a5  mov     edi, edi
0x100115a7  push    ebp
0x100115a8  mov     ebp, esp
0x100115aa  sub     esp, 4Ch
0x100115ad  push    ebx
0x100115ae  mov     ebx, ecx
0x100115b0  push    esi; void *
0x100115b1  push    edi; this
0x100115b2  cmp     dword ptr [ebx+0FCh], 0
0x100115b9  jnz     loc_100117CC
0x100115bf  mov     eax, [edx]
0x100115c1  mov     [ebp+var_8], 0
0x100115c8  mov     esi, [eax]
0x100115ca  lea     eax, [ebp+var_4]
0x100115cd  push    eax
0x100115ce  push    offset __GUID_b61178d1_a2d9_11cf_9e53_00aa00a216a1
0x100115d3  push    edx
0x100115d4  mov     ecx, esi; this
0x100115d6  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x100115dc  call    esi
0x100115de  test    eax, eax
0x100115e0  js      loc_100116F6
0x100115e6  cmp     dword ptr [ebx+110h], 3
0x100115ed  lea     esi, [ebx+114h]
0x100115f3  jnz     short loc_10011601
0x100115f5  mov     edx, [ebp+var_4]
0x100115f8  mov     ecx, ebx
0x100115fa  call    ?ChooseCommunicationMethod@@YG?AW4KSPIN_COMMUNICATION@@PAVCBasePin@@PAUIKsPin@@@Z; ChooseCommunicationMethod(CBasePin *,IKsPin *)
0x100115ff  mov     [esi], eax
0x10011601  mov     edx, [ebp+var_4]
0x10011604  lea     eax, [ebx+0DCh]
0x1001160a  xor     ecx, ecx
0x1001160c  mov     [ebp+var_10], eax
0x1001160f  test    ebx, ebx
0x10011611  cmovz   eax, ecx
0x10011614  lea     ecx, [ebp+var_48]
0x10011617  push    ecx; struct IKsPin *
0x10011618  mov     ecx, eax
0x1001161a  mov     [ebp+var_C], eax
0x1001161d  call    ?FindCompatibleInterface@@YGJPAUIKsPin@@0PAUKSIDENTIFIER@@@Z; FindCompatibleInterface(IKsPin *,IKsPin *,KSIDENTIFIER *)
0x10011622  mov     edi, eax
0x10011624  test    edi, edi
0x10011626  js      loc_100116DA
0x1001162c  mov     edx, [ebp+var_4]
0x1001162f  lea     eax, [ebp+var_30]
0x10011632  mov     ecx, [ebp+var_C]
0x10011635  push    eax; struct IKsPin *
0x10011636  call    ?FindCompatibleMedium@@YGJPAUIKsPin@@0PAUKSIDENTIFIER@@@Z; FindCompatibleMedium(IKsPin *,IKsPin *,KSIDENTIFIER *)
0x1001163b  mov     edi, eax
0x1001163d  test    edi, edi
0x1001163f  js      loc_100116DA
0x10011645  xor     eax, eax
0x10011647  inc     eax
0x10011648  cmp     edi, eax
0x1001164a  jnz     short loc_1001165B
0x1001164c  mov     [ebp+var_8], 0
0x10011653  mov     [ebx+14Ch], eax
0x10011659  jmp     short loc_100116DA
0x1001165b  cmp     dword ptr [esi], 2
0x1001165e  jnz     short loc_100116C9
0x10011660  mov     ecx, [ebp+var_4]
0x10011663  mov     eax, [ecx]
0x10011665  mov     esi, [eax]
0x10011667  lea     eax, [ebp+var_14]
0x1001166a  push    eax
0x1001166b  push    offset __GUID_423c13a2_2070_11d0_9ef7_00aa00a216a1
0x10011670  push    ecx
0x10011671  mov     ecx, esi; this
0x10011673  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10011679  call    esi
0x1001167b  mov     edi, eax
0x1001167d  test    edi, edi
0x1001167f  js      short loc_100116D0
0x10011681  mov     ecx, [ebp+var_4]
0x10011684  mov     eax, [ecx]
0x10011686  mov     esi, [eax+14h]
0x10011689  lea     eax, [ebp+var_30]
0x1001168c  push    eax
0x1001168d  lea     eax, [ebp+var_48]
0x10011690  push    eax
0x10011691  push    ecx
0x10011692  mov     ecx, esi; this
0x10011694  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001169a  call    esi
0x1001169c  mov     edi, eax
0x1001169e  mov     eax, [ebp+var_14]
0x100116a1  push    eax
0x100116a2  mov     ecx, [eax]
0x100116a4  mov     esi, [ecx+0Ch]
0x100116a7  mov     ecx, esi; this
0x100116a9  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x100116af  call    esi
0x100116b1  mov     ecx, [ebp+var_14]
0x100116b4  push    ecx
0x100116b5  mov     [ebp+var_8], eax
0x100116b8  mov     edx, [ecx]
0x100116ba  mov     esi, [edx+8]
0x100116bd  mov     ecx, esi; this
0x100116bf  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x100116c5  call    esi
0x100116c7  jmp     short loc_100116D0
0x100116c9  mov     [ebp+var_8], 0
0x100116d0  mov     dword ptr [ebx+14Ch], 0
0x100116da  mov     eax, [ebp+var_4]
0x100116dd  push    eax
0x100116de  mov     ecx, [eax]
0x100116e0  mov     esi, [ecx+8]
0x100116e3  mov     ecx, esi; this
0x100116e5  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x100116eb  call    esi
0x100116ed  test    edi, edi
0x100116ef  jns     short loc_10011741
0x100116f1  jmp     loc_10011880
0x100116f6  xor     ecx, ecx
0x100116f8  mov     dword ptr [ebx+114h], 1
0x10011702  lea     eax, [ebx+0DCh]
0x10011708  test    ebx, ebx
0x1001170a  mov     [ebp+var_10], eax
0x1001170d  cmovz   eax, ecx
0x10011710  lea     ecx, [ebp+var_48]
0x10011713  push    ecx; struct IKsPin *
0x10011714  push    5; struct IKsPin *
0x10011716  xor     edx, edx
0x10011718  mov     [ebp+var_C], eax
0x1001171b  mov     ecx, eax
0x1001171d  call    ?FindCompatiblePinFactoryIdentifier@@YGJPAUIKsPin@@0KPAUKSIDENTIFIER@@@Z; FindCompatiblePinFactoryIdentifier(IKsPin *,IKsPin *,ulong,KSIDENTIFIER *)
0x10011722  test    eax, eax
0x10011724  js      loc_10011882
0x1001172a  mov     esi, offset __GUID_4747b320_62ce_11cf_a5d6_28db04c10000
0x1001172f  lea     edi, [ebp+var_30]
0x10011732  xor     eax, eax
0x10011734  mov     [ebp+var_8], eax
0x10011737  movsd
0x10011738  movsd
0x10011739  movsd
0x1001173a  movsd
0x1001173b  mov     [ebp+var_20], eax
0x1001173e  mov     [ebp+var_1C], eax
0x10011741  lea     eax, [ebx+0FCh]
0x10011747  push    eax; unsigned int
0x10011748  push    40000000h; struct CKsProxy *
0x1001174d  push    dword ptr [ebx+10Ch]; struct CMediaType *
0x10011753  lea     eax, [ebx+34h]
0x10011756  push    dword ptr [ebx+28h]; void *
0x10011759  lea     edx, [ebp+var_30]
0x1001175c  push    eax; struct KSIDENTIFIER *
0x1001175d  push    [ebp+var_8]; struct KSIDENTIFIER *
0x10011760  lea     ecx, [ebp+var_48]
0x10011763  call    ?CreatePinHandle@@YGJAAUKSIDENTIFIER@@0PAXPAVCMediaType@@PAVCKsProxy@@KKPAPAX@Z; CreatePinHandle(KSIDENTIFIER &,KSIDENTIFIER &,void *,CMediaType *,CKsProxy *,ulong,ulong,void * *)
0x10011768  mov     edi, eax
0x1001176a  mov     [ebp+var_14], edi
0x1001176d  test    edi, edi
0x1001176f  js      loc_10011880
0x10011775  mov     edx, [ebx+28h]
0x10011778  lea     edi, [ebx+118h]
0x1001177e  push    6
0x10011780  pop     ecx
0x10011781  push    6
0x10011783  lea     esi, [ebp+var_48]
0x10011786  rep movsd
0x10011788  pop     ecx
0x10011789  push    [ebp+var_C]
0x1001178c  lea     edi, [ebx+130h]
0x10011792  lea     esi, [ebp+var_30]
0x10011795  rep movsd
0x10011797  mov     edx, [edx+128h]
0x1001179d  lea     eax, [ebx+170h]
0x100117a3  lea     esi, [ebx+0FCh]
0x100117a9  mov     ecx, [esi]
0x100117ab  push    eax
0x100117ac  call    ?AggregateSets@@YGJPAXPAUHKEY__@@PAV?$CGenericList@VCAggregateMarshaler@@@@PAUIUnknown@@@Z; AggregateSets(void *,HKEY__ *,CGenericList<CAggregateMarshaler> *,IUnknown *)
0x100117b1  push    dword ptr [ebx+28h]; struct IKsPin *
0x100117b4  mov     edx, [esi]
0x100117b6  lea     ecx, [ebx+0DCh]
0x100117bc  call    ?EstablishQualitySupport@@YGHPAUIKsPin@@PAXPAVCKsProxy@@@Z; EstablishQualitySupport(IKsPin *,void *,CKsProxy *)
0x100117c1  mov     edi, [ebp+var_14]
0x100117c4  mov     [ebx+188h], eax
0x100117ca  jmp     short loc_100117D7
0x100117cc  lea     eax, [ebx+0DCh]
0x100117d2  xor     edi, edi
0x100117d4  mov     [ebp+var_10], eax
0x100117d7  lea     esi, [ebx+108h]
0x100117dd  cmp     dword ptr [esi], 0
0x100117e0  lea     eax, [ebx+114h]
0x100117e6  lea     ecx, [ebx+118h]
0x100117ec  jnz     short loc_10011859
0x100117ee  cmp     dword ptr [eax], 4
0x100117f1  jz      short loc_10011859
0x100117f3  push    esi; ppv
0x100117f4  push    offset __GUID_d3abc7e0_9a61_11d0_a40d_00a0c9223196; riid
0x100117f9  push    401h; dwClsContext
0x100117fe  push    0; pUnkOuter
0x10011800  push    ecx; rclsid
0x10011801  call    ds:__imp__CoCreateInstance@20; CoCreateInstance(x,x,x,x,x)
0x10011807  mov     ecx, [esi]
0x10011809  mov     edi, eax
0x1001180b  test    ecx, ecx
0x1001180d  jz      short loc_1001182B
0x1001180f  mov     eax, [ebp+var_10]
0x10011812  xor     edx, edx
0x10011814  mov     esi, [ecx]
0x10011816  test    ebx, ebx
0x10011818  cmovz   eax, edx
0x1001181b  push    eax
0x1001181c  push    ecx
0x1001181d  mov     ecx, [esi+0Ch]; this
0x10011820  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10011826  call    dword ptr [esi+0Ch]
0x10011829  jmp     short loc_10011855
0x1001182b  mov     ecx, _WPP_GLOBAL_Control
0x10011831  cmp     ecx, offset _WPP_GLOBAL_Control
0x10011837  jz      short loc_10011855
0x10011839  push    dword ptr [ebx+14h]; int
0x1001183c  mov     eax, [ebx+28h]
0x1001183f  mov     edx, offset _WPP_51c792051e8832a7f1dd74ffd1c33eda_Traceguids
0x10011844  push    dword ptr [eax+3Ch]; int
0x10011847  push    dword ptr [ecx+14h]
0x1001184a  push    dword ptr [ecx+10h]; LoggerHandle
0x1001184d  push    0Ch
0x1001184f  pop     ecx
0x10011850  call    _WPP_SF_SS@24; WPP_SF_SS(x,x,x,x,x,x)
0x10011855  test    edi, edi
0x10011857  js      short loc_10011880
0x10011859  cmp     dword ptr [ebx+14Ch], 0
0x10011860  jz      short loc_1001186C
0x10011862  mov     ecx, [ebx+28h]
0x10011865  call    ?StartIoThread@CKsProxy@@QAGJXZ; CKsProxy::StartIoThread(void)
0x1001186a  mov     edi, eax
0x1001186c  test    edi, edi
0x1001186e  js      short loc_10011880
0x10011870  mov     edx, [ebx+0FCh]
0x10011876  mov     ecx, [ebx+28h]
0x10011879  call    ?InitiateEndOfStreamNotification@CKsProxy@@QAGJPAX@Z; CKsProxy::InitiateEndOfStreamNotification(void *)
0x1001187e  mov     edi, eax
0x10011880  mov     eax, edi
0x10011882  pop     edi
0x10011883  pop     esi
0x10011884  pop     ebx
0x10011885  leave
0x10011886  retn
```
