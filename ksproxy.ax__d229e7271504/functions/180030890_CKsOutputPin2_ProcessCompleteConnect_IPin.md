# CKsOutputPin2::ProcessCompleteConnect(IPin *)

- ea: `0x180030890`
- end: `0x180031133`
- name: `?ProcessCompleteConnect@CKsOutputPin2@@UEAAJPEAUIPin@@@Z`
- size: `2211`
- prototype: `__int64 __fastcall(CKsOutputPin2 *__hidden this, struct IPin *)`
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180002b58`
- `0x18000aaac`
- `0x18000df50`
- `0x180010b54`
- `0x18001bbf8`
- `0x18001e69c`
- `0x18001f1c4`
- `0x18001f1d0`
- `0x1800248d4`
- `0x180025860`
- `0x180028fc0`
- `0x180030890`
- `0x18003460c`
- `0x180035d90`
- `0x1800374f8`
- `0x18003755c`
- `0x18003b0a8`
- `0x180044850`
- `0x180045010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180030fb2`
- `KERNEL32!GetLastError` at `0x180031014`
- `KERNEL32!GetLastError` at `0x18003104a`
- `KERNEL32!GetLastError` at `0x180030fb2`
- `KERNEL32!GetLastError` at `0x180031014`
- `KERNEL32!GetLastError` at `0x18003104a`
- `KERNEL32!CreateEventW` at `0x180030dbf`
- `KERNEL32!CreateEventW` at `0x180030dbf`
- `KERNEL32!CloseHandle` at `0x180030f53`
- `KERNEL32!CloseHandle` at `0x180030fe4`
- `KERNEL32!CloseHandle` at `0x1800310b3`
- `KERNEL32!CloseHandle` at `0x180030f53`
- `KERNEL32!CloseHandle` at `0x180030fe4`
- `KERNEL32!CloseHandle` at `0x1800310b3`
- `KERNEL32!Sleep` at `0x180030b26`
- `KERNEL32!Sleep` at `0x180030b26`
- `ole32!CoTaskMemFree` at `0x180030b9b`
- `ole32!CoTaskMemFree` at `0x180030b9b`
- `ole32!CoCreateInstance` at `0x180030ca9`
- `ole32!CoCreateInstance` at `0x180030ca9`
- `ksuser!KsCreatePin` at `0x180030b0e`
- `ksuser!KsCreatePin` at `0x180030b0e`

## pseudocode

```c
__int64 __fastcall CKsOutputPin2::ProcessCompleteConnect(CKsOutputPin2 *this, struct IPin *a2)
{
  void **v2; // r12
  IPin_vtbl *v4; // rax
  void *v5; // r15
  unsigned __int64 v6; // rsi
  int Instance; // edi
  int CompatibleMedium; // eax
  __int64 result; // rax
  unsigned int *v10; // rdx
  CKsProxy **v11; // r14
  PKSPIN_CONNECT v12; // rsi
  int v13; // r15d
  void *v14; // rax
  bool v15; // sf
  int v16; // eax
  const IID *v17; // r15
  CKsProxy *v18; // rdx
  __int64 v19; // xmm1_8
  void *v20; // rcx
  __int128 v21; // xmm0
  __int64 v22; // xmm1_8
  _QWORD *v23; // r14
  char *v24; // r14
  __int64 v25; // rax
  int (__fastcall *v26)(char *, struct KSIDENTIFIER *, __int64); // rax
  struct _ASYNC_ITEM *v27; // rsi
  HANDLE EventW; // rax
  __int64 v29; // rax
  CAsyncItemHandler *v30; // rcx
  int (__fastcall ***v31)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v32; // rcx
  DWORD LastError; // eax
  DWORD v34; // eax
  signed int v35; // eax
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 *v38; // [rsp+28h] [rbp-58h]
  PKSPIN_CONNECT Connect; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v40[32]; // [rsp+48h] [rbp-38h] BYREF
  struct KSIDENTIFIER v41; // [rsp+68h] [rbp-18h] BYREF
  __int64 v42; // [rsp+C0h] [rbp+40h] BYREF
  struct IKsPin *v43; // [rsp+D0h] [rbp+50h] BYREF
  __int64 v44; // [rsp+D8h] [rbp+58h] BYREF

  v2 = (void **)((char *)this + 520);
  if ( *((_QWORD *)this + 65) )
  {
    Instance = 0;
    v17 = (const IID *)((char *)this + 600);
    v6 = (unsigned __int64)this + 384;
LABEL_36:
    v23 = (_QWORD *)((char *)this + 576);
    if ( !*((_QWORD *)this + 72) && *((_DWORD *)this + 148) != 4 )
    {
      Instance = CoCreateInstance(v17, 0, 0x401u, &GUID_d3abc7e0_9a61_11d0_a40d_00a0c9223196, (LPVOID *)this + 72);
      if ( *v23 )
      {
        (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v23 + 24LL))(
          *v23,
          v6 & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64));
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          0xBu,
          &WPP_4461f5f2318c3c9afea4e63d8c8a6ec1_Traceguids,
          *(const wchar_t **)(*((_QWORD *)this + 10) + 88LL),
          *((const wchar_t **)this + 5));
      }
      if ( Instance < 0 )
        goto LABEL_71;
    }
    if ( !*((_QWORD *)this + 121) )
    {
      LODWORD(v42) = 0;
      v24 = (char *)this + 448;
      v25 = *((_QWORD *)this + 56);
      v41.Id = 4;
      v41.Flags = 512;
      v38 = &v42;
      v26 = *(int (__fastcall **)(char *, struct KSIDENTIFIER *, __int64))(v25 + 40);
      memset(v40, 0, sizeof(v40));
      v41.Set = GUID_7f4bcbe0_9ea5_11cf_a5d6_28db04c10000;
      if ( v26((char *)this + 448, &v41, 24) >= 0 )
      {
        v27 = (struct _ASYNC_ITEM *)operator new(0x30u);
        if ( !v27 )
        {
          Instance = -2147024882;
          goto LABEL_71;
        }
        v41.Flags = 1;
        *(_DWORD *)v40 = 1;
        EventW = CreateEventW(0, 0, 0, 0);
        *((_QWORD *)this + 121) = EventW;
        if ( EventW )
        {
          v27->link.bLink = 0;
          v27->link.fLink = 0;
          v27->remove = 1;
          v27->event = (void *)*((_QWORD *)this + 121);
          v27->context = this;
          v27->itemRoutine = CKsOutputPin::EOSEventHandler;
          *(_QWORD *)&v40[8] = *((_QWORD *)this + 121);
          v29 = *(_QWORD *)v24;
          *(_OWORD *)&v40[16] = 0;
          Instance = (*(__int64 (__fastcall **)(char *, struct KSIDENTIFIER *, __int64, _BYTE *, int, __int64 *))(v29 + 40))(
                       (char *)this + 448,
                       &v41,
                       24,
                       v40,
                       32,
                       &v42);
          if ( Instance < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
            {
              LastError = GetLastError();
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                0xDu,
                &WPP_4461f5f2318c3c9afea4e63d8c8a6ec1_Traceguids,
                LastError);
            }
            CloseHandle(*((HANDLE *)this + 121));
            *((_QWORD *)this + 121) = 0;
            operator delete(v27);
            goto LABEL_71;
          }
          if ( !*((_QWORD *)this + 123) )
            Instance = (*(__int64 (__fastcall **)(CKsOutputPin2 *))(*(_QWORD *)this + 192LL))(this);
          if ( !*((_QWORD *)this + 140) )
            Instance = CKsOutputPin2::InitializePluginThread(this);
          if ( Instance >= 0 )
          {
            v30 = (CAsyncItemHandler *)*((_QWORD *)this + 123);
            if ( v30 )
            {
              CAsyncItemHandler::QueueAsyncItem(v30, v27);
              goto LABEL_56;
            }
          }
          (*(void (__fastcall **)(char *, _QWORD, _QWORD, _BYTE *, int, __int64 *))(*(_QWORD *)v24 + 40LL))(
            (char *)this + 448,
            0,
            0,
            v40,
            32,
            &v42);
          CloseHandle(*((HANDLE *)this + 121));
          *((_QWORD *)this + 121) = 0;
          operator delete(v27);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0xCu, &WPP_4461f5f2318c3c9afea4e63d8c8a6ec1_Traceguids);
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
          {
            v34 = GetLastError();
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 0xEu, &WPP_4461f5f2318c3c9afea4e63d8c8a6ec1_Traceguids, v34);
          }
          operator delete(v27);
          v35 = GetLastError();
          Instance = v35;
          if ( v35 > 0 )
            Instance = (unsigned __int16)v35 | 0x80070000;
        }
        if ( Instance < 0 )
          goto LABEL_71;
      }
    }
LABEL_56:
    if ( *((_QWORD *)this + 141) )
    {
      v31 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 142);
      v42 = 0;
      if ( (**v31)(v31, &GUID_6b3cf435_bf7e_4ae7_b420_8e84166353fa, &v42) >= 0 )
      {
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v42 + 24LL))(
          v42,
          ((unsigned __int64)this + 448) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64));
        v32 = v42;
        *((_DWORD *)this + 288) = 1;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
      }
    }
    return (unsigned int)Instance;
  }
  v43 = 0;
  v4 = a2->__vftable;
  memset(v40, 0, 24);
  memset(&v41, 0, sizeof(v41));
  if ( v4->QueryInterface(a2, &GUID_b61178d1_a2d9_11cf_9e53_00aa00a216a1, (void **)&v43) < 0 )
  {
    *((_DWORD *)this + 148) = 1;
    v6 = (unsigned __int64)this + 384;
    result = FindCompatibleInterface((struct IKsPin *)(((unsigned __int64)this + 384) & -(__int64)(this != 0)), 0, &v41);
    if ( (int)result < 0 )
      return result;
    v5 = 0;
    *(_QWORD *)&v40[4] = *(_QWORD *)&GUID_4747b320_62ce_11cf_a5d6_28db04c10000.Data2;
    *(_DWORD *)v40 = 1195881248;
    *(_DWORD *)&v40[12] = *(_DWORD *)&GUID_4747b320_62ce_11cf_a5d6_28db04c10000.Data4[4];
    *(_QWORD *)&v40[16] = 0;
  }
  else
  {
    v5 = 0;
    if ( *((_DWORD *)this + 147) == 3 )
      *((_DWORD *)this + 148) = ChooseCommunicationMethod((struct CBasePin *)this, v43);
    v6 = (unsigned __int64)this + 384;
    Instance = FindCompatibleInterface(
                 (struct IKsPin *)(((unsigned __int64)this + 384) & -(__int64)(this != 0)),
                 v43,
                 &v41);
    if ( Instance >= 0 )
    {
      CompatibleMedium = FindCompatibleMedium(
                           (struct IKsPin *)(((unsigned __int64)this + 384) & -(__int64)(this != 0)),
                           v43,
                           (struct KSIDENTIFIER *)v40);
      Instance = CompatibleMedium;
      if ( CompatibleMedium >= 0 )
      {
        if ( CompatibleMedium == 1 )
        {
          *((_DWORD *)this + 162) = 1;
        }
        else
        {
          if ( *((_DWORD *)this + 148) == 2 )
          {
            v44 = 0;
            Instance = v43->QueryInterface(v43, &GUID_423c13a2_2070_11d0_9ef7_00aa00a216a1, (void **)&v44);
            if ( Instance >= 0 )
            {
              Instance = v43->KsCreateSinkPinHandle(v43, &v41, (KSIDENTIFIER *)v40);
              v5 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v44 + 24LL))(v44);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
            }
          }
          *((_DWORD *)this + 162) = 0;
        }
      }
    }
    v43->Release(v43);
    if ( Instance < 0 )
      return (unsigned int)Instance;
  }
  if ( *((_DWORD *)this + 286) )
  {
    Connect = 0;
    LODWORD(v42) = 0;
    Instance = InitializeDataFormat(
                 (const struct CMediaType *)((char *)this + 104),
                 0x48u,
                 (void **)&Connect,
                 (unsigned int *)&v42);
    if ( Instance < 0 )
      goto LABEL_71;
    v10 = (unsigned int *)*((_QWORD *)this + 152);
    v11 = (CKsProxy **)((char *)this + 80);
    v12 = Connect;
    if ( v10 )
    {
      memcpy_0(&Connect[1], v10, *v10);
      v12->Interface = v41;
      v12->Medium.0 = *($BF1D6C6803037BEC0E57DD3D16D44AB2 *)v40;
      *(_QWORD *)&v12->Medium.Id = *(_QWORD *)&v40[16];
      v12->PinId = *((_DWORD *)this + 146);
      v12->PinToHandle = v5;
      v13 = 0;
      v12->Priority.PriorityClass = 0x40000000;
      v12->Priority.PrioritySubClass = 0x40000000;
      do
      {
        v14 = (*v11)->KsGetObjectHandle(&(*v11)->IKsObject);
        Instance = KsCreatePin(v14, v12, 0x80000000, v2);
        if ( Instance != 21 )
          break;
        Sleep(0x3E8u);
        ++v13;
      }
      while ( v13 < 5 );
      v15 = Instance < 0;
      if ( Instance > 0 )
      {
        Instance = (unsigned __int16)Instance | 0x80070000;
        v15 = Instance < 0;
      }
      if ( v15 )
      {
        *v2 = 0;
LABEL_30:
        CoTaskMemFree(v12);
        v6 = (unsigned __int64)this + 384;
        goto LABEL_32;
      }
      v16 = CKsProxy::SetPinSyncSource(*v11, (char *)*v2);
    }
    else
    {
      v16 = CreatePinHandle(
              &v41,
              (struct KSIDENTIFIER *)v40,
              v5,
              (struct CMediaType *)((char *)this + 104),
              *v11,
              *((_DWORD *)this + 146),
              0x80000000,
              v2);
    }
    Instance = v16;
    goto LABEL_30;
  }
  v11 = (CKsProxy **)((char *)this + 80);
  Instance = CreatePinHandle(
               &v41,
               (struct KSIDENTIFIER *)v40,
               v5,
               (struct CMediaType *)((char *)this + 104),
               *((struct CKsProxy **)this + 10),
               *((_DWORD *)this + 146),
               0x80000000,
               v2);
LABEL_32:
  if ( Instance >= 0 )
  {
    v17 = (const IID *)((char *)this + 600);
    v18 = *v11;
    v19 = *(_QWORD *)&v41.Id;
    v20 = *v2;
    *($BF1D6C6803037BEC0E57DD3D16D44AB2 *)((char *)this + 600) = v41.0;
    v21 = *(_OWORD *)v40;
    *((_QWORD *)this + 77) = v19;
    v22 = *(_QWORD *)&v40[16];
    *((_OWORD *)this + 39) = v21;
    *((_QWORD *)this + 80) = v22;
    AggregateSets(v20, v18->m_DeviceRegKey, (CBaseList *)this + 17, (IUnknown *)(v6 & -(__int64)(this != 0)));
    *((_DWORD *)this + 210) = VerifyQualitySupport(*v2);
    goto LABEL_36;
  }
LABEL_71:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    LODWORD(v38) = Instance;
    WPP_SF_SSD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      0xFu,
      &WPP_4461f5f2318c3c9afea4e63d8c8a6ec1_Traceguids,
      *(const wchar_t **)(*((_QWORD *)this + 10) + 88LL),
      *((const wchar_t **)this + 5),
      v38);
  }
  if ( *v2 )
  {
    CloseHandle(*v2);
    *v2 = 0;
    *((_DWORD *)this + 210) = 0;
  }
  v36 = *((_QWORD *)this + 72);
  if ( v36 )
  {
    *((_QWORD *)this + 72) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  }
  if ( *((_QWORD *)this + 70) )
  {
    v37 = *((_QWORD *)this + 71);
    *((_QWORD *)this + 70) = 0;
    if ( v37 )
    {
      *((_QWORD *)this + 71) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    }
  }
  *((_DWORD *)this + 148) = *((_DWORD *)this + 147);
  *((_DWORD *)this + 162) = 1;
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180030890  mov     [rsp-38h+arg_8], rbx
0x180030895  push    rbp
0x180030896  push    rsi
0x180030897  push    rdi
0x180030898  push    r12
0x18003089a  push    r13
0x18003089c  push    r14
0x18003089e  push    r15
0x1800308a0  mov     rbp, rsp
0x1800308a3  sub     rsp, 80h
0x1800308aa  lea     r12, [rcx+208h]
0x1800308b1  xor     r13d, r13d
0x1800308b4  mov     r9, rdx
0x1800308b7  mov     rbx, rcx
0x1800308ba  cmp     [r12], r13
0x1800308be  jnz     loc_180030C64
0x1800308c4  xor     eax, eax
0x1800308c6  mov     [rbp+arg_10], r13
0x1800308ca  mov     qword ptr [rbp+var_18.Id], rax
0x1800308ce  lea     r8, [rbp+arg_10]
0x1800308d2  mov     dword ptr [rbp+var_38+14h], eax
0x1800308d5  xorps   xmm0, xmm0
0x1800308d8  mov     rax, [rdx]
0x1800308db  mov     rcx, r9
0x1800308de  lea     rdx, _GUID_b61178d1_a2d9_11cf_9e53_00aa00a216a1
0x1800308e5  mov     dword ptr [rbp+var_38], r13d
0x1800308e9  movups  xmmword ptr [rbp+var_18.___u0], xmm0
0x1800308ed  mov     rax, [rax]
0x1800308f0  movups  xmmword ptr [rbp+var_38+4], xmm0
0x1800308f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800308f9  test    eax, eax
0x1800308fb  js      loc_1800309F9
0x180030901  cmp     dword ptr [rbx+24Ch], 3
0x180030908  mov     r15d, r13d
0x18003090b  jnz     short loc_18003091F
0x18003090d  mov     rdx, [rbp+arg_10]; struct IKsPin *
0x180030911  mov     rcx, rbx; struct CBasePin *
0x180030914  call    ?ChooseCommunicationMethod@@YA?AW4KSPIN_COMMUNICATION@@PEAVCBasePin@@PEAUIKsPin@@@Z; ChooseCommunicationMethod(CBasePin *,IKsPin *)
0x180030919  mov     [rbx+250h], eax
0x18003091f  mov     rdx, [rbp+arg_10]; struct IKsPin *
0x180030923  lea     rsi, [rbx+180h]
0x18003092a  mov     rax, rbx
0x18003092d  lea     r8, [rbp+var_18]; struct KSIDENTIFIER *
0x180030931  neg     rax
0x180030934  sbb     r14, r14
0x180030937  and     r14, rsi
0x18003093a  mov     rcx, r14; struct IKsPin *
0x18003093d  call    ?FindCompatibleInterface@@YAJPEAUIKsPin@@0PEAUKSIDENTIFIER@@@Z; FindCompatibleInterface(IKsPin *,IKsPin *,KSIDENTIFIER *)
0x180030942  mov     edi, eax
0x180030944  test    eax, eax
0x180030946  js      loc_1800309E0
0x18003094c  mov     rdx, [rbp+arg_10]; struct IKsPin *
0x180030950  lea     r8, [rbp+var_38]; struct KSIDENTIFIER *
0x180030954  mov     rcx, r14; struct IKsPin *
0x180030957  call    ?FindCompatibleMedium@@YAJPEAUIKsPin@@0PEAUKSIDENTIFIER@@@Z; FindCompatibleMedium(IKsPin *,IKsPin *,KSIDENTIFIER *)
0x18003095c  mov     edi, eax
0x18003095e  test    eax, eax
0x180030960  js      short loc_1800309E0
0x180030962  cmp     eax, 1
0x180030965  jnz     short loc_18003096F
0x180030967  mov     [rbx+288h], eax
0x18003096d  jmp     short loc_1800309E0
0x18003096f  cmp     dword ptr [rbx+250h], 2
0x180030976  jnz     short loc_1800309D9
0x180030978  mov     rcx, [rbp+arg_10]
0x18003097c  lea     r8, [rbp+arg_18]
0x180030980  mov     [rbp+arg_18], r13
0x180030984  lea     rdx, _GUID_423c13a2_2070_11d0_9ef7_00aa00a216a1
0x18003098b  mov     rax, [rcx]
0x18003098e  mov     rax, [rax]
0x180030991  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030996  mov     edi, eax
0x180030998  test    eax, eax
0x18003099a  js      short loc_1800309D9
0x18003099c  mov     rcx, [rbp+arg_10]
0x1800309a0  lea     r8, [rbp+var_38]
0x1800309a4  lea     rdx, [rbp+var_18]
0x1800309a8  mov     rax, [rcx]
0x1800309ab  mov     rax, [rax+28h]
0x1800309af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800309b4  mov     rcx, [rbp+arg_18]
0x1800309b8  mov     edi, eax
0x1800309ba  mov     rax, [rcx]
0x1800309bd  mov     rax, [rax+18h]
0x1800309c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800309c6  mov     rcx, [rbp+arg_18]
0x1800309ca  mov     r15, rax
0x1800309cd  mov     rdx, [rcx]
0x1800309d0  mov     rax, [rdx+10h]
0x1800309d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800309d9  mov     [rbx+288h], r13d
0x1800309e0  mov     rcx, [rbp+arg_10]
0x1800309e4  mov     rax, [rcx]
0x1800309e7  mov     rax, [rax+10h]
0x1800309eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800309f0  test    edi, edi
0x1800309f2  jns     short loc_180030A4D
0x1800309f4  jmp     loc_180030F05
0x1800309f9  mov     rax, rbx
0x1800309fc  mov     dword ptr [rbx+250h], 1
0x180030a06  neg     rax
0x180030a09  lea     rsi, [rbx+180h]
0x180030a10  lea     r8, [rbp+var_18]; struct KSIDENTIFIER *
0x180030a14  sbb     rcx, rcx
0x180030a17  xor     edx, edx; struct IKsPin *
0x180030a19  and     rcx, rsi; struct IKsPin *
0x180030a1c  call    ?FindCompatibleInterface@@YAJPEAUIKsPin@@0PEAUKSIDENTIFIER@@@Z; FindCompatibleInterface(IKsPin *,IKsPin *,KSIDENTIFIER *)
0x180030a21  test    eax, eax
0x180030a23  js      loc_180030F07
0x180030a29  movsd   xmm0, qword ptr cs:_GUID_4747b320_62ce_11cf_a5d6_28db04c10000.Data2
0x180030a31  mov     r15, r13
0x180030a34  mov     eax, dword ptr cs:_GUID_4747b320_62ce_11cf_a5d6_28db04c10000.Data4+4
0x180030a3a  movsd   qword ptr [rbp+var_38+4], xmm0
0x180030a3f  mov     dword ptr [rbp+var_38], 4747B320h
0x180030a46  mov     dword ptr [rbp+var_38+0Ch], eax
0x180030a49  mov     qword ptr [rbp+var_38+10h], r13
0x180030a4d  xor     r14d, r14d
0x180030a50  lea     r13, [rbx+68h]
0x180030a54  cmp     [rbx+478h], r14d
0x180030a5b  jz      loc_180030BB0
0x180030a61  lea     r9, [rbp+arg_0]; unsigned int *
0x180030a65  mov     [rbp+Connect], r14
0x180030a69  lea     r8, [rbp+Connect]; void **
0x180030a6d  mov     dword ptr [rbp+arg_0], r14d
0x180030a71  lea     edx, [r14+48h]; unsigned int
0x180030a75  mov     rcx, r13; struct CMediaType *
0x180030a78  call    ?InitializeDataFormat@@YAJPEBVCMediaType@@KPEAPEAXPEAK@Z; InitializeDataFormat(CMediaType const *,ulong,void * *,ulong *)
0x180030a7d  mov     edi, eax
0x180030a7f  test    eax, eax
0x180030a81  js      loc_180030C5C
0x180030a87  mov     rdx, [rbx+4C0h]; Src
0x180030a8e  lea     r14, [rbx+50h]
0x180030a92  mov     rsi, [rbp+Connect]
0x180030a96  test    rdx, rdx
0x180030a99  jz      loc_180030B64
0x180030a9f  mov     r8d, [rdx]; Size
0x180030aa2  lea     rcx, [rsi+48h]; void *
0x180030aa6  call    memcpy_0
0x180030aab  movups  xmm0, xmmword ptr [rbp+var_18.___u0]
0x180030aaf  movups  xmmword ptr [rsi], xmm0
0x180030ab2  movsd   xmm1, qword ptr [rbp+var_18.Id]
0x180030ab7  movsd   qword ptr [rsi+10h], xmm1
0x180030abc  movups  xmm0, xmmword ptr [rbp+var_38]
0x180030ac0  movups  xmmword ptr [rsi+18h], xmm0
0x180030ac4  movsd   xmm1, qword ptr [rbp-28h]
0x180030ac9  movsd   qword ptr [rsi+28h], xmm1
0x180030ace  mov     eax, [rbx+248h]
0x180030ad4  mov     [rsi+30h], eax
0x180030ad7  mov     eax, 40000000h
0x180030adc  mov     [rsi+38h], r15
0x180030ae0  xor     r15d, r15d
0x180030ae3  mov     [rsi+40h], eax
0x180030ae6  mov     [rsi+44h], eax
0x180030ae9  mov     rcx, [r14]
0x180030aec  add     rcx, 0A8h
0x180030af3  mov     rax, [rcx]
0x180030af6  mov     rax, [rax+18h]
0x180030afa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030aff  mov     r9, r12; ConnectionHandle
0x180030b02  mov     r8d, 80000000h; DesiredAccess
0x180030b08  mov     rdx, rsi; Connect
0x180030b0b  mov     rcx, rax; FilterHandle
0x180030b0e  call    cs:__imp_KsCreatePin
0x180030b15  nop     dword ptr [rax+rax+00h]
0x180030b1a  mov     edi, eax
0x180030b1c  cmp     eax, 15h
0x180030b1f  jnz     short loc_180030B3B
0x180030b21  mov     ecx, 3E8h; dwMilliseconds
0x180030b26  call    cs:__imp_Sleep
0x180030b2d  nop     dword ptr [rax+rax+00h]
0x180030b32  inc     r15d
0x180030b35  cmp     r15d, 5
0x180030b39  jl      short loc_180030AE9
0x180030b3b  test    edi, edi
0x180030b3d  jle     short loc_180030B4A
0x180030b3f  movzx   edi, di
0x180030b42  or      edi, 80070000h
0x180030b48  test    edi, edi
0x180030b4a  js      short loc_180030B5A
0x180030b4c  mov     rdx, [r12]; void *
0x180030b50  mov     rcx, [r14]; this
0x180030b53  call    ?SetPinSyncSource@CKsProxy@@QEAAJPEAX@Z; CKsProxy::SetPinSyncSource(void *)
0x180030b58  jmp     short loc_180030B96
0x180030b5a  mov     qword ptr [r12], 0
0x180030b62  jmp     short loc_180030B98
0x180030b64  mov     eax, [rbx+248h]
0x180030b6a  lea     rdx, [rbp+var_38]; struct KSIDENTIFIER *
0x180030b6e  mov     [rsp+80h+var_48], r12; void **
0x180030b73  lea     rcx, [rbp+var_18]; struct KSIDENTIFIER *
0x180030b77  mov     [rsp+80h+var_50], 80000000h; unsigned int
0x180030b7f  mov     r9, r13; struct CMediaType *
0x180030b82  mov     [rsp+80h+var_58], eax; unsigned int
0x180030b86  mov     r8, r15; void *
0x180030b89  mov     rax, [r14]
0x180030b8c  mov     [rsp+80h+ppv], rax; struct CKsProxy *
0x180030b91  call    ?CreatePinHandle@@YAJAEAUKSIDENTIFIER@@0PEAXPEAVCMediaType@@PEAVCKsProxy@@KKPEAPEAX@Z; CreatePinHandle(KSIDENTIFIER &,KSIDENTIFIER &,void *,CMediaType *,CKsProxy *,ulong,ulong,void * *)
0x180030b96  mov     edi, eax
0x180030b98  mov     rcx, rsi; pv
0x180030b9b  call    cs:__imp_CoTaskMemFree
0x180030ba2  nop     dword ptr [rax+rax+00h]
0x180030ba7  lea     rsi, [rbx+180h]
0x180030bae  jmp     short loc_180030BE8
0x180030bb0  mov     eax, [rbx+248h]
0x180030bb6  lea     r14, [rbx+50h]
0x180030bba  mov     [rsp+80h+var_48], r12; void **
0x180030bbf  lea     rdx, [rbp+var_38]; struct KSIDENTIFIER *
0x180030bc3  mov     [rsp+80h+var_50], 80000000h; unsigned int
0x180030bcb  lea     rcx, [rbp+var_18]; struct KSIDENTIFIER *
0x180030bcf  mov     [rsp+80h+var_58], eax; unsigned int
0x180030bd3  mov     r9, r13; struct CMediaType *
0x180030bd6  mov     rax, [r14]
0x180030bd9  mov     r8, r15; void *
0x180030bdc  mov     [rsp+80h+ppv], rax; struct CKsProxy *
0x180030be1  call    ?CreatePinHandle@@YAJAEAUKSIDENTIFIER@@0PEAXPEAVCMediaType@@PEAVCKsProxy@@KKPEAPEAX@Z; CreatePinHandle(KSIDENTIFIER &,KSIDENTIFIER &,void *,CMediaType *,CKsProxy *,ulong,ulong,void * *)
0x180030be6  mov     edi, eax
0x180030be8  xor     r13d, r13d
0x180030beb  test    edi, edi
0x180030bed  js      loc_18003106D
0x180030bf3  movups  xmm0, xmmword ptr [rbp+var_18.___u0]
0x180030bf7  lea     r15, [rbx+258h]
0x180030bfe  mov     rdx, [r14]
0x180030c01  movsd   xmm1, qword ptr [rbp+var_18.Id]
0x180030c06  lea     r8, [rbx+2A8h]; this
0x180030c0d  mov     rcx, [r12]; hFile
0x180030c11  mov     rax, rbx
0x180030c14  movups  xmmword ptr [r15], xmm0
0x180030c18  neg     rax
0x180030c1b  movups  xmm0, xmmword ptr [rbp+var_38]
0x180030c1f  sbb     r9, r9
0x180030c22  movsd   qword ptr [r15+10h], xmm1
0x180030c28  and     r9, rsi
0x180030c2b  movsd   xmm1, qword ptr [rbp-28h]
0x180030c30  movups  xmmword ptr [rbx+270h], xmm0
0x180030c37  movsd   qword ptr [rbx+280h], xmm1
0x180030c3f  mov     rdx, [rdx+1F8h]; hKey
0x180030c46  call    ?AggregateSets@@YAJPEAXPEAUHKEY__@@PEAV?$CGenericList@VCAggregateMarshaler@@@@PEAUIUnknown@@@Z; AggregateSets(void *,HKEY__ *,CGenericList<CAggregateMarshaler> *,IUnknown *)
0x180030c4b  mov     rcx, [r12]; void *
0x180030c4f  call    ?VerifyQualitySupport@@YAHPEAX@Z; VerifyQualitySupport(void *)
0x180030c54  mov     [rbx+348h], eax
0x180030c5a  jmp     short loc_180030C75
0x180030c5c  xor     r13d, r13d
0x180030c5f  jmp     loc_18003106D
0x180030c64  mov     edi, r13d
0x180030c67  lea     r15, [rcx+258h]
0x180030c6e  lea     rsi, [rcx+180h]
0x180030c75  lea     r14, [rbx+240h]
0x180030c7c  cmp     [r14], r13
0x180030c7f  jnz     loc_180030D1A
0x180030c85  cmp     dword ptr [rbx+250h], 4
0x180030c8c  jz      loc_180030D1A
0x180030c92  lea     r9, _GUID_d3abc7e0_9a61_11d0_a40d_00a0c9223196; riid
0x180030c99  mov     [rsp+80h+ppv], r14; ppv
0x180030c9e  xor     edx, edx; pUnkOuter
0x180030ca0  mov     r8d, 401h; dwClsContext
0x180030ca6  mov     rcx, r15; rclsid
0x180030ca9  call    cs:__imp_CoCreateInstance
0x180030cb0  nop     dword ptr [rax+rax+00h]
0x180030cb5  mov     rcx, [r14]
0x180030cb8  mov     edi, eax
0x180030cba  test    rcx, rcx
0x180030cbd  jz      short loc_180030CD9
0x180030cbf  mov     r8, [rcx]
0x180030cc2  mov     rax, rbx
0x180030cc5  neg     rax
0x180030cc8  sbb     rdx, rdx
0x180030ccb  mov     rax, [r8+18h]
0x180030ccf  and     rdx, rsi
0x180030cd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030cd7  jmp     short loc_180030D12
0x180030cd9  mov     rcx, cs:WPP_GLOBAL_Control
0x180030ce0  lea     rax, WPP_GLOBAL_Control
0x180030ce7  cmp     rcx, rax
0x180030cea  jz      short loc_180030D12
0x180030cec  mov     r9, [rbx+50h]
0x180030cf0  lea     r8, WPP_4461f5f2318c3c9afea4e63d8c8a6ec1_Traceguids
0x180030cf7  mov     rax, [rbx+28h]
0x180030cfb  mov     edx, 0Bh
0x180030d00  mov     rcx, [rcx+10h]
0x180030d04  mov     [rsp+80h+ppv], rax
0x180030d09  mov     r9, [r9+58h]
0x180030d0d  call    WPP_SF_SS
0x180030d12  test    edi, edi
0x180030d14  js      loc_18003106D
0x180030d1a  cmp     [rbx+3C8h], r13
0x180030d21  jnz     loc_180030E9A
0x180030d27  movups  xmm1, xmmword ptr cs:_GUID_7f4bcbe0_9ea5_11cf_a5d6_28db04c10000.Data1
0x180030d2e  mov     dword ptr [rbp+arg_0], r13d
0x180030d32  lea     r14, [rbx+1C0h]
0x180030d39  mov     rax, [r14]
0x180030d3c  xorps   xmm0, xmm0
0x180030d3f  xor     r9d, r9d
0x180030d42  mov     [rbp+var_18.Id], 4
0x180030d49  lea     rcx, [rbp+arg_0]
0x180030d4d  mov     [rbp+var_18.Flags], 200h
0x180030d54  mov     qword ptr [rsp+80h+var_58], rcx
0x180030d59  lea     rdx, [rbp+var_18]
0x180030d5d  mov     rax, [rax+28h]
0x180030d61  mov     rcx, r14
0x180030d64  lea     r8d, [r9+18h]
0x180030d68  mov     dword ptr [rsp+80h+ppv], r13d
  ... truncated ...
```
