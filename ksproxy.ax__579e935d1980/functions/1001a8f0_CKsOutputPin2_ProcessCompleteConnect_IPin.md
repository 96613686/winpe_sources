# CKsOutputPin2::ProcessCompleteConnect(IPin *)

- ea: `0x1001a8f0`
- end: `0x1001b0fa`
- name: `?ProcessCompleteConnect@CKsOutputPin2@@UAGJPAUIPin@@@Z`
- size: `2058`
- prototype: `int(CKsOutputPin2 *__hidden this, struct IPin *)`
- caller_count: `0`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x100063f1`
- `0x100064e5`
- `0x1000665f`
- `0x10010c0e`
- `0x1001a8f0`
- `0x1001df3d`
- `0x1001f6ea`
- `0x1001fd03`
- `0x1001fe62`
- `0x1001feac`
- `0x10020525`
- `0x10020593`
- `0x10020b2b`
- `0x10021163`
- `0x100218b2`
- `0x1002bd71`
- `0x1002d510`
- `0x1003a6fd`
- `0x1003af9d`
- `0x1003bcf8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1001af25`
- `KERNEL32!GetLastError` at `0x1001af78`
- `KERNEL32!GetLastError` at `0x1001afa1`
- `KERNEL32!GetLastError` at `0x1001af25`
- `KERNEL32!GetLastError` at `0x1001af78`
- `KERNEL32!GetLastError` at `0x1001afa1`
- `KERNEL32!CreateEventW` at `0x1001adec`
- `KERNEL32!CreateEventW` at `0x1001adec`
- `KERNEL32!CloseHandle` at `0x1001aed2`
- `KERNEL32!CloseHandle` at `0x1001af4a`
- `KERNEL32!CloseHandle` at `0x1001aff5`
- `KERNEL32!CloseHandle` at `0x1001aed2`
- `KERNEL32!CloseHandle` at `0x1001af4a`
- `KERNEL32!CloseHandle` at `0x1001aff5`
- `KERNEL32!Sleep` at `0x1001ab90`
- `KERNEL32!Sleep` at `0x1001ab90`
- `ole32!CoTaskMemFree` at `0x1001ac17`
- `ole32!CoTaskMemFree` at `0x1001ac17`
- `ole32!CoCreateInstance` at `0x1001acfa`
- `ole32!CoCreateInstance` at `0x1001acfa`
- `ksuser!KsCreatePin` at `0x1001ab7c`
- `ksuser!KsCreatePin` at `0x1001ab7c`

## pseudocode

```c
int __stdcall CKsOutputPin2::ProcessCompleteConnect(CKsOutputPin2 *this, struct IPin *a2)
{
  signed int CompatibleInterface; // edi
  int CompatibleMedium; // eax
  struct KSIDENTIFIER *v4; // edi
  int result; // eax
  _DWORD *v6; // eax
  PKSPIN_CONNECT v7; // edx
  void *v8; // eax
  struct KSIDENTIFIER *Pin; // eax
  signed int PinHandle; // esi
  char *v11; // eax
  int v12; // edx
  int v13; // edx
  int v14; // eax
  PVOID *v15; // ecx
  HRESULT Instance; // eax
  int v17; // ecx
  PKSPIN_CONNECT v18; // eax
  int v19; // eax
  struct $58C2C1BF6568EE28BD9B872E6BA03976 *v20; // esi
  HANDLE EventW; // eax
  int v22; // eax
  char LastError; // al
  char v24; // al
  signed int v25; // eax
  int v26; // ecx
  int v27; // ecx
  int v28; // eax
  _DWORD **v29; // ecx
  PKSPIN_CONNECT v30; // eax
  PKSPIN_CONNECT v31; // [esp+28h] [ebp-58h]
  PKSPIN_CONNECT v32; // [esp+28h] [ebp-58h]
  struct CBasePin *v33; // [esp+30h] [ebp-50h]
  struct IKsPin *v34; // [esp+30h] [ebp-50h]
  void *v35; // [esp+30h] [ebp-50h]
  struct KSIDENTIFIER *v36; // [esp+34h] [ebp-4Ch]
  struct KSIDENTIFIER *v37; // [esp+34h] [ebp-4Ch]
  char v38[4]; // [esp+3Ch] [ebp-44h] BYREF
  _DWORD **v39; // [esp+40h] [ebp-40h] BYREF
  struct KSIDENTIFIER *v40; // [esp+44h] [ebp-3Ch]
  PKSPIN_CONNECT Connect; // [esp+48h] [ebp-38h] BYREF
  int v42; // [esp+4Ch] [ebp-34h] BYREF
  struct IKsPin v43[6]; // [esp+50h] [ebp-30h] BYREF
  struct IKsPin v44[6]; // [esp+68h] [ebp-18h] BYREF

  if ( *((_DWORD *)this + 89) )
  {
    CompatibleInterface = 0;
    *(_DWORD *)v38 = 0;
    Connect = (PKSPIN_CONNECT)((char *)this + 272);
    goto LABEL_42;
  }
  memset(v43, 0, sizeof(v43));
  v40 = 0;
  if ( ((int (__thiscall *)(HRESULT (__stdcall *)(IUnknown *, const _GUID *, void **), struct IPin *, GUID *, _DWORD ***))a2->QueryInterface)(
         a2->QueryInterface,
         a2,
         &_GUID_b61178d1_a2d9_11cf_9e53_00aa00a216a1,
         &v39) < 0 )
  {
    *((_DWORD *)this + 99) = 1;
    Connect = (PKSPIN_CONNECT)((char *)this + 272);
    result = FindCompatiblePinFactoryIdentifier((struct IKsPin *)5, v44, (unsigned int)v33, v36);
    if ( result < 0 )
      return result;
    v43[0] = (struct IKsPin)_GUID_4747b320_62ce_11cf_a5d6_28db04c10000.Data1;
    v43[1] = *(struct IKsPin *)&_GUID_4747b320_62ce_11cf_a5d6_28db04c10000.Data2;
    v43[2] = *(struct IKsPin *)_GUID_4747b320_62ce_11cf_a5d6_28db04c10000.Data4;
    v43[3] = *(struct IKsPin *)&_GUID_4747b320_62ce_11cf_a5d6_28db04c10000.Data4[4];
    v4 = 0;
    v43[4].__vftable = 0;
    v43[5].__vftable = 0;
    v40 = 0;
  }
  else
  {
    if ( *((_DWORD *)this + 98) == 3 )
      *((_DWORD *)this + 99) = ChooseCommunicationMethod(v33, (struct IKsPin *)v36);
    Connect = (PKSPIN_CONNECT)((char *)this + 272);
    CompatibleInterface = FindCompatibleInterface(v44, (struct IKsPin *)v33, v36);
    if ( CompatibleInterface >= 0 )
    {
      CompatibleMedium = FindCompatibleMedium(v43, v34, v37);
      CompatibleInterface = CompatibleMedium;
      if ( CompatibleMedium >= 0 )
      {
        if ( CompatibleMedium == 1 )
        {
          *((_DWORD *)this + 112) = 1;
          v40 = 0;
        }
        else
        {
          if ( *((_DWORD *)this + 99) == 2 )
          {
            CompatibleInterface = ((int (__thiscall *)(_DWORD, _DWORD **, GUID *, int *))**v39)(
                                    **v39,
                                    v39,
                                    &_GUID_423c13a2_2070_11d0_9ef7_00aa00a216a1,
                                    &v42);
            if ( CompatibleInterface >= 0 )
            {
              CompatibleInterface = ((int (__thiscall *)(_DWORD, _DWORD **, struct IKsPin *, struct IKsPin *))(*v39)[5])(
                                      (*v39)[5],
                                      v39,
                                      v44,
                                      v43);
              v40 = (struct KSIDENTIFIER *)(*(int (__thiscall **)(_DWORD, int))(*(_DWORD *)v42 + 12))(
                                             *(_DWORD *)(*(_DWORD *)v42 + 12),
                                             v42);
              (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v42 + 8))(*(_DWORD *)(*(_DWORD *)v42 + 8), v42);
            }
          }
          else
          {
            v40 = 0;
          }
          *((_DWORD *)this + 112) = 0;
        }
      }
    }
    ((void (__thiscall *)(_DWORD, _DWORD **))(*v39)[2])((*v39)[2], v39);
    if ( CompatibleInterface < 0 )
      return CompatibleInterface;
    v4 = v40;
  }
  if ( *((_DWORD *)this + 192) )
  {
    *(_DWORD *)v38 = InitializeDataFormat(
                       (const struct CMediaType *)&Connect,
                       (unsigned int)v38,
                       (void **)&v34->__vftable,
                       &v37->Set.Data1);
    if ( *(int *)v38 < 0 )
    {
LABEL_40:
      v15 = (PVOID *)WPP_GLOBAL_Control;
      CompatibleInterface = *(_DWORD *)v38;
      goto LABEL_77;
    }
    v6 = (_DWORD *)*((_DWORD *)this + 204);
    if ( v6 )
    {
      memcpy(&Connect[1], v6, *v6);
      v7 = Connect;
      v42 = 0;
      qmemcpy(Connect, v44, 0x18u);
      qmemcpy(&v7->Medium, v43, sizeof(v7->Medium));
      v7->PinId = *((_DWORD *)this + 97);
      v7->PinToHandle = v40;
      v7->Priority.PriorityClass = 0x40000000;
      v7->Priority.PrioritySubClass = 0x40000000;
      while ( 1 )
      {
        v8 = (void *)(*(int (__thiscall **)(_DWORD, int))(*(_DWORD *)(*((_DWORD *)this + 10) + 108) + 12))(
                       *(_DWORD *)(*(_DWORD *)(*((_DWORD *)this + 10) + 108) + 12),
                       *((_DWORD *)this + 10) + 108);
        Pin = (struct KSIDENTIFIER *)KsCreatePin(v8, Connect, 0x80000000, (PHANDLE)this + 89);
        v40 = Pin;
        if ( Pin != (struct KSIDENTIFIER *)21 )
          break;
        Sleep(0x3E8u);
        if ( ++v42 >= 5 )
        {
          Pin = v40;
          break;
        }
      }
      PinHandle = (unsigned __int16)Pin | 0x80070000;
      if ( (int)Pin <= 0 )
        PinHandle = (signed int)Pin;
      *(_DWORD *)v38 = PinHandle;
      if ( PinHandle < 0 )
      {
        *((_DWORD *)this + 89) = 0;
      }
      else
      {
        if ( *(_DWORD *)(*((_DWORD *)this + 10) + 224) )
          PinHandle = SetSyncSource(v35, v36);
        else
          PinHandle = 0;
        *(_DWORD *)v38 = PinHandle;
      }
    }
    else
    {
      PinHandle = CreatePinHandle(
                    v4,
                    (struct KSIDENTIFIER *)((char *)this + 52),
                    *((void **)this + 10),
                    *((struct CMediaType **)this + 97),
                    (struct CKsProxy *)0x80000000,
                    (unsigned int)this + 356,
                    (unsigned int)v35,
                    (void **)v36);
      *(_DWORD *)v38 = PinHandle;
    }
    CoTaskMemFree(Connect);
    v11 = (char *)this + 272;
    Connect = (PKSPIN_CONNECT)((char *)this + 272);
  }
  else
  {
    PinHandle = CreatePinHandle(
                  v4,
                  (struct KSIDENTIFIER *)((char *)this + 52),
                  *((void **)this + 10),
                  *((struct CMediaType **)this + 97),
                  (struct CKsProxy *)0x80000000,
                  (unsigned int)this + 356,
                  (unsigned int)v34,
                  (void **)v37);
    v11 = (char *)this + 272;
    *(_DWORD *)v38 = PinHandle;
  }
  if ( PinHandle < 0 )
    goto LABEL_40;
  v12 = *((_DWORD *)this + 10);
  qmemcpy((char *)this + 400, v44, 0x18u);
  qmemcpy((char *)this + 424, v43, 0x18u);
  v13 = *(_DWORD *)(v12 + 296);
  if ( !this )
    v11 = 0;
  AggregateSets(*((_DWORD *)this + 89), v13, (char *)this + 468, v11);
  v14 = VerifyQualitySupport(v35);
  CompatibleInterface = *(_DWORD *)v38;
  *((_DWORD *)this + 141) = v14;
LABEL_42:
  if ( *((_DWORD *)this + 96) || *((_DWORD *)this + 99) == 4 )
  {
LABEL_52:
    if ( *((_DWORD *)this + 164) )
      goto LABEL_88;
    v44[0] = (struct IKsPin)_GUID_7f4bcbe0_9ea5_11cf_a5d6_28db04c10000.Data1;
    v44[1] = *(struct IKsPin *)&_GUID_7f4bcbe0_9ea5_11cf_a5d6_28db04c10000.Data2;
    v44[2] = *(struct IKsPin *)_GUID_7f4bcbe0_9ea5_11cf_a5d6_28db04c10000.Data4;
    v44[3] = *(struct IKsPin *)&_GUID_7f4bcbe0_9ea5_11cf_a5d6_28db04c10000.Data4[4];
    v44[4].__vftable = (IKsPin_vtbl *)4;
    v19 = *((_DWORD *)this + 76);
    v44[5].__vftable = (IKsPin_vtbl *)512;
    if ( (*(int (__thiscall **)(_DWORD, char *, struct IKsPin *, int, _DWORD, _DWORD, int *))(v19 + 20))(
           *(_DWORD *)(v19 + 20),
           (char *)this + 304,
           v44,
           24,
           0,
           0,
           &v42) < 0 )
    {
      CompatibleInterface = *(_DWORD *)v38;
      goto LABEL_88;
    }
    v20 = (struct $58C2C1BF6568EE28BD9B872E6BA03976 *)operator new(0x18u);
    Connect = v20;
    if ( !v20 )
    {
      CompatibleInterface = -2147024882;
LABEL_56:
      v15 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_77;
    }
    v44[5].__vftable = (IKsPin_vtbl *)1;
    v43[0].__vftable = (IKsPin_vtbl *)1;
    EventW = CreateEventW(0, 0, 0, 0);
    *((_DWORD *)this + 164) = EventW;
    if ( EventW )
    {
      v20->Interface.Set.Data4[0] = 1;
      HIDWORD(v20->Interface.Alignment) = 0;
      v20->Interface.Set.Data1 = 0;
      *((_DWORD *)&v20->Interface.Alignment + 3) = *((_DWORD *)this + 164);
      v20->Interface.Id = (unsigned int)CKsOutputPin::EOSEventHandler;
      v20->Interface.Flags = (unsigned int)this;
      v43[1] = *(struct IKsPin *)((char *)this + 656);
      v22 = *((_DWORD *)this + 76);
      v43[2].__vftable = 0;
      v43[3].__vftable = 0;
      CompatibleInterface = (*(int (__thiscall **)(_DWORD, char *, struct IKsPin *, int, struct IKsPin *, int, int *))(v22 + 20))(
                              *(_DWORD *)(v22 + 20),
                              (char *)this + 304,
                              v44,
                              24,
                              v43,
                              16,
                              &v42);
      if ( CompatibleInterface < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          LastError = GetLastError();
          WPP_SF_q(
            0xDu,
            &WPP_4461f5f2318c3c9afea4e63d8c8a6ec1_Traceguids,
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            LastError);
        }
        CloseHandle(*((HANDLE *)this + 164));
        v32 = Connect;
        *((_DWORD *)this + 164) = 0;
        operator delete(v32, 0x18u);
        goto LABEL_56;
      }
      if ( !*((_DWORD *)this + 166) )
        CompatibleInterface = (*(int (__thiscall **)(CKsOutputPin2 *))(*(_DWORD *)this + 96))(this);
      if ( !*((_DWORD *)this + 189) )
        CompatibleInterface = CKsOutputPin2::InitializePluginThread(this);
      if ( CompatibleInterface >= 0 && *((_DWORD *)this + 166) )
      {
        CAsyncItemHandler::QueueAsyncItem((CAsyncItemHandler *)v33, (struct _ASYNC_ITEM *)v36);
        goto LABEL_88;
      }
      (*(void (__thiscall **)(_DWORD, char *, _DWORD, _DWORD, struct IKsPin *, int, int *))(*((_DWORD *)this + 76) + 20))(
        *(_DWORD *)(*((_DWORD *)this + 76) + 20),
        (char *)this + 304,
        0,
        0,
        v43,
        16,
        &v42);
      CloseHandle(*((HANDLE *)this + 164));
      v31 = Connect;
      *((_DWORD *)this + 164) = 0;
      operator delete(v31, 0x18u);
      v15 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_76;
      WPP_SF_(0xCu, &WPP_4461f5f2318c3c9afea4e63d8c8a6ec1_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2));
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        v24 = GetLastError();
        WPP_SF_q(0xEu, &WPP_4461f5f2318c3c9afea4e63d8c8a6ec1_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2), v24);
      }
      operator delete(v20, 0x18u);
      v25 = GetLastError();
      CompatibleInterface = (unsigned __int16)v25 | 0x80070000;
      if ( v25 <= 0 )
        CompatibleInterface = v25;
    }
    v15 = (PVOID *)WPP_GLOBAL_Control;
LABEL_76:
    if ( CompatibleInterface < 0 )
      goto LABEL_77;
LABEL_88:
    if ( *((_DWORD *)this + 190) )
    {
      v29 = (_DWORD **)*((_DWORD *)this + 191);
      Connect = 0;
      if ( ((int (__thiscall *)(_DWORD, _DWORD **, GUID *, PKSPIN_CONNECT *))**v29)(
             **v29,
             v29,
             &_GUID_6b3cf435_bf7e_4ae7_b420_8e84166353fa,
             &Connect) >= 0 )
      {
        (*(void (__thiscall **)(_DWORD, PKSPIN_CONNECT, char *))(Connect->Interface.Set.Data1 + 12))(
          *(_DWORD *)(Connect->Interface.Set.Data1 + 12),
          Connect,
          this != 0 ? (char *)this + 304 : 0);
        v30 = Connect;
        *((_DWORD *)this + 194) = 1;
        (*(void (__thiscall **)(_DWORD, PKSPIN_CONNECT))(v30->Interface.Set.Data1 + 8))(
          *(_DWORD *)(v30->Interface.Set.Data1 + 8),
          v30);
      }
    }
    return CompatibleInterface;
  }
  Instance = CoCreateInstance(
               (const IID *const)this + 25,
               0,
               0x401u,
               &_GUID_d3abc7e0_9a61_11d0_a40d_00a0c9223196,
               (LPVOID *)this + 96);
  v17 = *((_DWORD *)this + 96);
  CompatibleInterface = Instance;
  *(_DWORD *)v38 = Instance;
  if ( v17 )
  {
    v18 = Connect;
    if ( !this )
      v18 = 0;
    (*(void (__thiscall **)(_DWORD, int, PKSPIN_CONNECT))(*(_DWORD *)v17 + 12))(
      *(_DWORD *)(*(_DWORD *)v17 + 12),
      v17,
      v18);
  }
  else
  {
    v15 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_51;
    WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), *(_DWORD *)(*((_DWORD *)this + 10) + 60), *((_DWORD *)this + 5));
  }
  v15 = (PVOID *)WPP_GLOBAL_Control;
LABEL_51:
  if ( CompatibleInterface >= 0 )
    goto LABEL_52;
LABEL_77:
  if ( v15 != &WPP_GLOBAL_Control )
    WPP_SF_SSd(
      *((_QWORD *)v15 + 2),
      *(_DWORD *)(*((_DWORD *)this + 10) + 60),
      *((_DWORD *)this + 5),
      CompatibleInterface);
  if ( *((_DWORD *)this + 89) )
  {
    CloseHandle(*((HANDLE *)this + 89));
    *((_DWORD *)this + 89) = 0;
    *((_DWORD *)this + 141) = 0;
  }
  v26 = *((_DWORD *)this + 96);
  if ( v26 )
  {
    *((_DWORD *)this + 96) = 0;
    (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v26 + 8))(*(_DWORD *)(*(_DWORD *)v26 + 8), v26);
  }
  if ( *((_DWORD *)this + 94) )
  {
    v27 = *((_DWORD *)this + 95);
    *((_DWORD *)this + 94) = 0;
    if ( v27 )
    {
      *((_DWORD *)this + 95) = 0;
      (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v27 + 8))(*(_DWORD *)(*(_DWORD *)v27 + 8), v27);
    }
  }
  v28 = *((_DWORD *)this + 98);
  *((_DWORD *)this + 112) = 1;
  *((_DWORD *)this + 99) = v28;
  return CompatibleInterface;
}

```

## disassembly

```asm
0x1001a8f0  mov     edi, edi
0x1001a8f2  push    ebp
0x1001a8f3  mov     ebp, esp
0x1001a8f5  and     esp, 0FFFFFFF8h
0x1001a8f8  sub     esp, 44h
0x1001a8fb  push    ebx
0x1001a8fc  mov     ebx, [ebp+this]
0x1001a8ff  push    esi; struct _ASYNC_ITEM *
0x1001a900  push    edi; this
0x1001a901  cmp     dword ptr [ebx+164h], 0
0x1001a908  jnz     loc_1001ACC2
0x1001a90e  mov     ecx, [ebp+arg_4]
0x1001a911  lea     edi, [esp+50h+var_2C]
0x1001a915  xor     eax, eax
0x1001a917  mov     [esp+50h+var_30.__vftable], 0
0x1001a91f  stosd
0x1001a920  stosd
0x1001a921  stosd
0x1001a922  stosd
0x1001a923  stosd
0x1001a924  xor     eax, eax
0x1001a926  mov     [esp+50h+var_3C], eax
0x1001a92a  mov     eax, [ecx]
0x1001a92c  mov     esi, [eax]
0x1001a92e  lea     eax, [esp+50h+var_40]
0x1001a932  push    eax
0x1001a933  push    offset __GUID_b61178d1_a2d9_11cf_9e53_00aa00a216a1
0x1001a938  push    ecx
0x1001a939  mov     ecx, esi; this
0x1001a93b  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001a941  call    esi
0x1001a943  test    eax, eax
0x1001a945  js      loc_1001AA70
0x1001a94b  cmp     dword ptr [ebx+188h], 3
0x1001a952  jnz     short loc_1001A965
0x1001a954  mov     edx, [esp+50h+var_40]
0x1001a958  mov     ecx, ebx
0x1001a95a  call    ?ChooseCommunicationMethod@@YG?AW4KSPIN_COMMUNICATION@@PAVCBasePin@@PAUIKsPin@@@Z; ChooseCommunicationMethod(CBasePin *,IKsPin *)
0x1001a95f  mov     [ebx+18Ch], eax
0x1001a965  mov     edx, [esp+50h+var_40]
0x1001a969  lea     eax, [ebx+110h]
0x1001a96f  mov     esi, eax
0x1001a971  mov     [esp+50h+Connect], eax
0x1001a975  xor     eax, eax
0x1001a977  test    ebx, ebx
0x1001a979  cmovz   esi, eax
0x1001a97c  lea     eax, [esp+50h+var_18]
0x1001a980  push    eax; struct IKsPin *
0x1001a981  mov     ecx, esi
0x1001a983  call    ?FindCompatibleInterface@@YGJPAUIKsPin@@0PAUKSIDENTIFIER@@@Z; FindCompatibleInterface(IKsPin *,IKsPin *,KSIDENTIFIER *)
0x1001a988  mov     edi, eax
0x1001a98a  test    edi, edi
0x1001a98c  js      loc_1001AA4E
0x1001a992  mov     edx, [esp+50h+var_40]
0x1001a996  lea     eax, [esp+50h+var_30]
0x1001a99a  push    eax; struct IKsPin *
0x1001a99b  mov     ecx, esi
0x1001a99d  call    ?FindCompatibleMedium@@YGJPAUIKsPin@@0PAUKSIDENTIFIER@@@Z; FindCompatibleMedium(IKsPin *,IKsPin *,KSIDENTIFIER *)
0x1001a9a2  mov     edi, eax
0x1001a9a4  test    edi, edi
0x1001a9a6  js      loc_1001AA4E
0x1001a9ac  xor     ecx, ecx
0x1001a9ae  inc     ecx
0x1001a9af  cmp     edi, ecx
0x1001a9b1  jnz     short loc_1001A9C4
0x1001a9b3  xor     eax, eax
0x1001a9b5  mov     [ebx+1C0h], ecx
0x1001a9bb  mov     [esp+50h+var_3C], eax
0x1001a9bf  jmp     loc_1001AA4E
0x1001a9c4  cmp     dword ptr [ebx+18Ch], 2
0x1001a9cb  jnz     short loc_1001AA3E
0x1001a9cd  mov     ecx, [esp+50h+var_40]
0x1001a9d1  mov     eax, [ecx]
0x1001a9d3  mov     esi, [eax]
0x1001a9d5  lea     eax, [esp+50h+var_34]
0x1001a9d9  push    eax
0x1001a9da  push    offset __GUID_423c13a2_2070_11d0_9ef7_00aa00a216a1
0x1001a9df  push    ecx
0x1001a9e0  mov     ecx, esi; this
0x1001a9e2  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001a9e8  call    esi
0x1001a9ea  mov     edi, eax
0x1001a9ec  test    edi, edi
0x1001a9ee  js      short loc_1001AA44
0x1001a9f0  mov     ecx, [esp+50h+var_40]
0x1001a9f4  mov     eax, [ecx]
0x1001a9f6  mov     esi, [eax+14h]
0x1001a9f9  lea     eax, [esp+50h+var_30]
0x1001a9fd  push    eax
0x1001a9fe  lea     eax, [esp+54h+var_18]
0x1001aa02  push    eax
0x1001aa03  push    ecx
0x1001aa04  mov     ecx, esi; this
0x1001aa06  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001aa0c  call    esi
0x1001aa0e  mov     edi, eax
0x1001aa10  mov     eax, [esp+50h+var_34]
0x1001aa14  push    eax
0x1001aa15  mov     ecx, [eax]
0x1001aa17  mov     esi, [ecx+0Ch]
0x1001aa1a  mov     ecx, esi; this
0x1001aa1c  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001aa22  call    esi
0x1001aa24  mov     ecx, [esp+50h+var_34]
0x1001aa28  push    ecx
0x1001aa29  mov     [esp+54h+var_3C], eax
0x1001aa2d  mov     edx, [ecx]
0x1001aa2f  mov     esi, [edx+8]
0x1001aa32  mov     ecx, esi; this
0x1001aa34  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001aa3a  call    esi
0x1001aa3c  jmp     short loc_1001AA44
0x1001aa3e  xor     eax, eax
0x1001aa40  mov     [esp+50h+var_3C], eax
0x1001aa44  mov     dword ptr [ebx+1C0h], 0
0x1001aa4e  mov     eax, [esp+50h+var_40]
0x1001aa52  push    eax
0x1001aa53  mov     ecx, [eax]
0x1001aa55  mov     esi, [ecx+8]
0x1001aa58  mov     ecx, esi; this
0x1001aa5a  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001aa60  call    esi
0x1001aa62  test    edi, edi
0x1001aa64  js      loc_1001B0EF
0x1001aa6a  mov     edi, [esp+50h+var_3C]
0x1001aa6e  jmp     short loc_1001AAC6
0x1001aa70  lea     eax, [ebx+110h]
0x1001aa76  mov     dword ptr [ebx+18Ch], 1
0x1001aa80  lea     ecx, [esp+50h+var_18]
0x1001aa84  mov     [esp+50h+Connect], eax
0x1001aa88  push    ecx; struct IKsPin *
0x1001aa89  mov     ecx, eax
0x1001aa8b  xor     eax, eax
0x1001aa8d  test    ebx, ebx
0x1001aa8f  push    5; struct IKsPin *
0x1001aa91  cmovz   ecx, eax
0x1001aa94  xor     edx, edx
0x1001aa96  call    ?FindCompatiblePinFactoryIdentifier@@YGJPAUIKsPin@@0KPAUKSIDENTIFIER@@@Z; FindCompatiblePinFactoryIdentifier(IKsPin *,IKsPin *,ulong,KSIDENTIFIER *)
0x1001aa9b  test    eax, eax
0x1001aa9d  js      loc_1001B0F1
0x1001aaa3  mov     esi, offset __GUID_4747b320_62ce_11cf_a5d6_28db04c10000
0x1001aaa8  lea     edi, [esp+50h+var_30]
0x1001aaac  movsd
0x1001aaad  movsd
0x1001aaae  movsd
0x1001aaaf  movsd
0x1001aab0  xor     edi, edi
0x1001aab2  mov     [esp+50h+var_20], 0
0x1001aaba  mov     [esp+50h+var_1C], 0
0x1001aac2  mov     [esp+50h+var_3C], edi
0x1001aac6  cmp     dword ptr [ebx+300h], 0
0x1001aacd  lea     ecx, [ebx+34h]
0x1001aad0  jz      loc_1001AC29
0x1001aad6  lea     eax, [esp+50h+var_44]
0x1001aada  push    eax; unsigned int
0x1001aadb  lea     eax, [esp+54h+Connect]
0x1001aadf  push    eax; struct CMediaType *
0x1001aae0  push    40h ; '@'
0x1001aae2  pop     edx
0x1001aae3  call    ?InitializeDataFormat@@YGJPBVCMediaType@@KPAPAXPAK@Z; InitializeDataFormat(CMediaType const *,ulong,void * *,ulong *)
0x1001aae8  mov     esi, eax
0x1001aaea  mov     dword ptr [esp+50h+var_44], esi
0x1001aaee  test    esi, esi
0x1001aaf0  js      loc_1001ACB3
0x1001aaf6  mov     eax, [ebx+330h]
0x1001aafc  test    eax, eax
0x1001aafe  jz      loc_1001ABE6
0x1001ab04  push    dword ptr [eax]; Size
0x1001ab06  push    eax; Src
0x1001ab07  mov     eax, [esp+58h+Connect]
0x1001ab0b  add     eax, 40h ; '@'
0x1001ab0e  push    eax; void *
0x1001ab0f  call    _memcpy
0x1001ab14  mov     edx, [esp+5Ch+Connect]
0x1001ab18  lea     esi, [esp+5Ch+var_18]
0x1001ab1c  add     esp, 0Ch
0x1001ab1f  mov     [esp+50h+var_34], 0
0x1001ab27  mov     edi, edx
0x1001ab29  push    6
0x1001ab2b  pop     ecx
0x1001ab2c  rep movsd
0x1001ab2e  push    6
0x1001ab30  lea     edi, [edx+18h]
0x1001ab33  pop     ecx
0x1001ab34  lea     esi, [esp+50h+var_30]
0x1001ab38  rep movsd
0x1001ab3a  mov     eax, [ebx+184h]
0x1001ab40  lea     edi, [ebx+164h]
0x1001ab46  mov     [edx+30h], eax
0x1001ab49  mov     eax, [esp+50h+var_3C]
0x1001ab4d  mov     [edx+34h], eax
0x1001ab50  mov     eax, 40000000h
0x1001ab55  mov     [edx+38h], eax
0x1001ab58  mov     [edx+3Ch], eax
0x1001ab5b  mov     eax, [ebx+28h]
0x1001ab5e  add     eax, 6Ch ; 'l'
0x1001ab61  push    eax
0x1001ab62  mov     ecx, [eax]
0x1001ab64  mov     esi, [ecx+0Ch]
0x1001ab67  mov     ecx, esi; this
0x1001ab69  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001ab6f  call    esi
0x1001ab71  push    edi; ConnectionHandle
0x1001ab72  push    80000000h; DesiredAccess
0x1001ab77  push    [esp+58h+Connect]; Connect
0x1001ab7b  push    eax; FilterHandle
0x1001ab7c  call    ds:__imp__KsCreatePin@16; KsCreatePin(x,x,x,x)
0x1001ab82  mov     [esp+50h+var_3C], eax
0x1001ab86  cmp     eax, 15h
0x1001ab89  jnz     short loc_1001ABA8
0x1001ab8b  push    3E8h; dwMilliseconds
0x1001ab90  call    ds:__imp__Sleep@4; Sleep(x)
0x1001ab96  mov     eax, [esp+50h+var_34]
0x1001ab9a  inc     eax
0x1001ab9b  mov     [esp+50h+var_34], eax
0x1001ab9f  cmp     eax, 5
0x1001aba2  jl      short loc_1001AB5B
0x1001aba4  mov     eax, [esp+50h+var_3C]
0x1001aba8  movzx   esi, ax
0x1001abab  or      esi, 80070000h
0x1001abb1  test    eax, eax
0x1001abb3  cmovle  esi, eax
0x1001abb6  mov     dword ptr [esp+50h+var_44], esi
0x1001abba  test    esi, esi
0x1001abbc  js      short loc_1001ABDE
0x1001abbe  mov     eax, [ebx+28h]
0x1001abc1  mov     edx, [eax+0E0h]
0x1001abc7  test    edx, edx
0x1001abc9  jz      short loc_1001ABD6
0x1001abcb  mov     ecx, [edi]
0x1001abcd  call    ?SetSyncSource@@YGJPAX0@Z; SetSyncSource(void *,void *)
0x1001abd2  mov     esi, eax
0x1001abd4  jmp     short loc_1001ABD8
0x1001abd6  xor     esi, esi
0x1001abd8  mov     dword ptr [esp+50h+var_44], esi
0x1001abdc  jmp     short loc_1001AC13
0x1001abde  mov     dword ptr [edi], 0
0x1001abe4  jmp     short loc_1001AC13
0x1001abe6  lea     eax, [ebx+164h]
0x1001abec  push    eax; unsigned int
0x1001abed  push    80000000h; struct CKsProxy *
0x1001abf2  push    dword ptr [ebx+184h]; struct CMediaType *
0x1001abf8  lea     eax, [ebx+34h]
0x1001abfb  push    dword ptr [ebx+28h]; void *
0x1001abfe  lea     edx, [esp+60h+var_30]
0x1001ac02  push    eax; struct KSIDENTIFIER *
0x1001ac03  push    edi; struct KSIDENTIFIER *
0x1001ac04  lea     ecx, [esp+68h+var_18]
0x1001ac08  call    ?CreatePinHandle@@YGJAAUKSIDENTIFIER@@0PAXPAVCMediaType@@PAVCKsProxy@@KKPAPAX@Z; CreatePinHandle(KSIDENTIFIER &,KSIDENTIFIER &,void *,CMediaType *,CKsProxy *,ulong,ulong,void * *)
0x1001ac0d  mov     esi, eax
0x1001ac0f  mov     dword ptr [esp+50h+var_44], eax
0x1001ac13  push    [esp+50h+Connect]; pv
0x1001ac17  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x1001ac1d  lea     eax, [ebx+110h]
0x1001ac23  mov     [esp+50h+Connect], eax
0x1001ac27  jmp     short loc_1001AC59
0x1001ac29  lea     eax, [ebx+164h]
0x1001ac2f  push    eax; unsigned int
0x1001ac30  push    80000000h; struct CKsProxy *
0x1001ac35  push    dword ptr [ebx+184h]; struct CMediaType *
0x1001ac3b  lea     edx, [esp+5Ch+var_30]
0x1001ac3f  push    dword ptr [ebx+28h]; void *
0x1001ac42  push    ecx; struct KSIDENTIFIER *
0x1001ac43  push    edi; struct KSIDENTIFIER *
0x1001ac44  lea     ecx, [esp+68h+var_18]
0x1001ac48  call    ?CreatePinHandle@@YGJAAUKSIDENTIFIER@@0PAXPAVCMediaType@@PAVCKsProxy@@KKPAPAX@Z; CreatePinHandle(KSIDENTIFIER &,KSIDENTIFIER &,void *,CMediaType *,CKsProxy *,ulong,ulong,void * *)
0x1001ac4d  mov     esi, eax
0x1001ac4f  lea     eax, [ebx+110h]
0x1001ac55  mov     dword ptr [esp+50h+var_44], esi
0x1001ac59  test    esi, esi
0x1001ac5b  js      short loc_1001ACB3
0x1001ac5d  mov     edx, [ebx+28h]
0x1001ac60  lea     edi, [ebx+190h]
0x1001ac66  push    6
0x1001ac68  pop     ecx
0x1001ac69  push    6
0x1001ac6b  lea     esi, [esp+54h+var_18]
0x1001ac6f  rep movsd
0x1001ac71  pop     ecx
0x1001ac72  lea     edi, [ebx+1A8h]
0x1001ac78  lea     esi, [esp+50h+var_30]
0x1001ac7c  rep movsd
0x1001ac7e  mov     edx, [edx+128h]
0x1001ac84  lea     esi, [ebx+164h]
0x1001ac8a  xor     ecx, ecx
0x1001ac8c  test    ebx, ebx
0x1001ac8e  cmovz   eax, ecx
0x1001ac91  mov     ecx, [esi]
0x1001ac93  push    eax
0x1001ac94  lea     eax, [ebx+1D4h]
0x1001ac9a  push    eax
0x1001ac9b  call    ?AggregateSets@@YGJPAXPAUHKEY__@@PAV?$CGenericList@VCAggregateMarshaler@@@@PAUIUnknown@@@Z; AggregateSets(void *,HKEY__ *,CGenericList<CAggregateMarshaler> *,IUnknown *)
0x1001aca0  mov     ecx, [esi]
0x1001aca2  call    ?VerifyQualitySupport@@YGHPAX@Z; VerifyQualitySupport(void *)
0x1001aca7  mov     edi, dword ptr [esp+50h+var_44]
0x1001acab  mov     [ebx+234h], eax
0x1001acb1  jmp     short loc_1001ACD2
0x1001acb3  mov     ecx, _WPP_GLOBAL_Control
0x1001acb9  mov     edi, dword ptr [esp+50h+var_44]
0x1001acbd  jmp     loc_1001AFC3
  ... truncated ...
```
