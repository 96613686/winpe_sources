# CWANCommonInterfaceConfigService::FinalConstruct(void)

- ea: `0x18004a634`
- end: `0x18004a92f`
- name: `?FinalConstruct@CWANCommonInterfaceConfigService@@QEAAJXZ`
- size: `763`
- prototype: `__int64 __fastcall(CWANCommonInterfaceConfigService *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18008b940`

## callees

- `0x18004a4fc`
- `0x18004a634`
- `0x18004a938`
- `0x18008c4b0`
- `0x18008c568`
- `0x18008c618`
- `0x18008c6b8`
- `0x18008c748`
- `0x18008d85c`
- `0x180090010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a889`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a8f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a889`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a8f8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004a8ce`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004a8ce`
- `ext-ms-win-net-netshell-l1-1-0!NcFreeNetconProperties` at `0x18004a86f`
- `ext-ms-win-net-netshell-l1-1-0!NcFreeNetconProperties` at `0x18004a86f`

## pseudocode

```c
__int64 __fastcall CWANCommonInterfaceConfigService::FinalConstruct(struct IStatisticsProvider **this)
{
  int Connections; // edi
  struct IHNetConnection *v3; // r14
  int v4; // eax
  struct IHNetConnection *v5; // r15
  NETCON_PROPERTIES *v6; // rcx
  DWORD v7; // eax
  NETCON_MEDIATYPE MediaType; // eax
  CLANStatisticsProvider *v9; // rbx
  int v10; // eax
  CWANConnectionBase **v11; // rbx
  int v12; // eax
  CWANConnectionBase **v13; // rbx
  _QWORD *v14; // rbx
  LPVOID *ppv; // rsi
  CLANStatisticsProvider *v17[2]; // [rsp+30h] [rbp-10h] BYREF
  LPVOID pv; // [rsp+78h] [rbp+38h] BYREF
  struct IHNetConnection *v19; // [rsp+80h] [rbp+40h] BYREF
  NETCON_PROPERTIES *pProps; // [rsp+88h] [rbp+48h] BYREF

  pv = 0;
  v19 = 0;
  Connections = CWANCommonInterfaceConfigService::GetConnections(
                  (CWANCommonInterfaceConfigService *)this,
                  (struct IHNetConnection **)&pv,
                  &v19);
  if ( Connections >= 0 )
  {
    v3 = (struct IHNetConnection *)pv;
    if ( pv )
    {
      pv = 0;
      v4 = (*(__int64 (__fastcall **)(struct IHNetConnection *, LPVOID *))(*(_QWORD *)v3 + 32LL))(v3, &pv);
      v5 = v19;
      Connections = v4;
      if ( v4 < 0 )
      {
LABEL_30:
        (*(void (__fastcall **)(struct IHNetConnection *))(*(_QWORD *)v3 + 16LL))(v3);
        (*(void (__fastcall **)(struct IHNetConnection *))(*(_QWORD *)v5 + 16LL))(v5);
        return (unsigned int)Connections;
      }
      v19 = 0;
      Connections = (*(__int64 (__fastcall **)(struct IHNetConnection *, struct IHNetConnection **))(*(_QWORD *)v3 + 24LL))(
                      v3,
                      &v19);
      if ( Connections < 0 || !v19 )
      {
LABEL_24:
        CoTaskMemFree(pv);
        if ( Connections >= 0 )
        {
          if ( v5 )
          {
            Connections = (*(__int64 (__fastcall **)(struct IHNetConnection *, LPVOID *))(*(_QWORD *)v5 + 32LL))(
                            v5,
                            &pv);
            if ( Connections >= 0 )
            {
              ppv = (LPVOID *)(this + 15);
              Connections = CoCreateInstance(
                              &CLSID_UPnPDeviceHostICSSupport,
                              0,
                              0x15u,
                              &IID_IUPnPDeviceHostICSSupport,
                              ppv);
              if ( Connections >= 0 )
                Connections = (*(__int64 (__fastcall **)(LPVOID, __int64, LPVOID))(*(_QWORD *)*ppv + 24LL))(*ppv, 1, pv);
              CoTaskMemFree(pv);
            }
          }
        }
        goto LABEL_30;
      }
      pProps = 0;
      Connections = (*(__int64 (__fastcall **)(struct IHNetConnection *, NETCON_PROPERTIES **))(*(_QWORD *)v19 + 56LL))(
                      v19,
                      &pProps);
      if ( Connections < 0 || (v6 = pProps) == 0 )
      {
LABEL_23:
        (*(void (__fastcall **)(struct IHNetConnection *))(*(_QWORD *)v19 + 16LL))(v19);
        goto LABEL_24;
      }
      v7 = (pProps->dwCharacter >> 10) & 1;
      v17[0] = 0;
      *((_DWORD *)this + 32) = v7;
      MediaType = v6->MediaType;
      *((_DWORD *)this + 26) = MediaType;
      if ( MediaType == NCM_LAN )
      {
        Connections = ATL::CComObject<CLANStatisticsProvider>::CreateInstance((char **)v17);
        if ( Connections < 0 )
          goto LABEL_22;
        v9 = v17[0];
        (*(void (__fastcall **)(CLANStatisticsProvider *))(*(_QWORD *)v17[0] + 8LL))(v17[0]);
        v10 = CLANStatisticsProvider::Initialize(v9, (struct _GUID *)pv);
      }
      else
      {
        Connections = ATL::CComObject<CRASStatisticsProvider>::CreateInstance((char **)v17);
        if ( Connections < 0 )
          goto LABEL_22;
        v9 = v17[0];
        (*(void (__fastcall **)(CLANStatisticsProvider *))(*(_QWORD *)v17[0] + 8LL))(v17[0]);
        v10 = (**(__int64 (__fastcall ***)(struct IHNetConnection *, GUID *, __int64))v19)(
                v19,
                &IID_INetRasConnection,
                (__int64)v9 + 64);
      }
      this[17] = v9;
      Connections = v10;
      if ( v10 >= 0 )
      {
        if ( *((_DWORD *)this + 26) != 3 )
        {
          v13 = this + 11;
          Connections = ATL::CComObject<CWANPPPConnectionService>::CreateInstance((volatile int **)this + 11);
          if ( Connections < 0 )
            goto LABEL_22;
          (*(void (__fastcall **)(CWANConnectionBase *))(*(_QWORD *)*v13 + 8LL))(*v13);
          Connections = CWANConnectionBase::Initialize(*v13, (struct _GUID *)pv, v3, this[17]);
          if ( Connections < 0 )
            goto LABEL_22;
          v14 = this + 12;
          Connections = ATL::CComObject<CWANPOTSLinkConfigService>::CreateInstance((volatile int **)this + 12);
          if ( Connections < 0 )
            goto LABEL_22;
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v14 + 8LL))(*v14);
          v12 = (**(__int64 (__fastcall ***)(struct IHNetConnection *, GUID *, __int64))v19)(
                  v19,
                  &IID_INetRasConnection,
                  *v14 + 88LL);
          goto LABEL_21;
        }
        v11 = this + 10;
        Connections = ATL::CComObject<CWANIPConnectionService>::CreateInstance((volatile int **)this + 10);
        if ( Connections >= 0 )
        {
          (*(void (__fastcall **)(CWANConnectionBase *))(*(_QWORD *)*v11 + 8LL))(*v11);
          v12 = CWANConnectionBase::Initialize(*v11, (struct _GUID *)pv, v3, this[17]);
LABEL_21:
          Connections = v12;
        }
      }
LABEL_22:
      NcFreeNetconProperties(pProps);
      goto LABEL_23;
    }
  }
  return (unsigned int)Connections;
}

```

## disassembly

```asm
0x18004a634  mov     [rsp-28h+arg_0], rbx
0x18004a639  push    rbp
0x18004a63a  push    rsi
0x18004a63b  push    rdi
0x18004a63c  push    r14
0x18004a63e  push    r15
0x18004a640  mov     rbp, rsp
0x18004a643  sub     rsp, 40h
0x18004a647  lea     r8, [rbp+arg_10]; struct IHNetConnection **
0x18004a64b  mov     [rbp+pv], 0
0x18004a653  lea     rdx, [rbp+pv]; struct IHNetConnection **
0x18004a657  mov     [rbp+arg_10], 0
0x18004a65f  mov     rsi, rcx
0x18004a662  call    ?GetConnections@CWANCommonInterfaceConfigService@@AEAAJPEAPEAUIHNetConnection@@0@Z; CWANCommonInterfaceConfigService::GetConnections(IHNetConnection * *,IHNetConnection * *)
0x18004a667  mov     edi, eax
0x18004a669  test    eax, eax
0x18004a66b  js      loc_18004A91C
0x18004a671  mov     r14, [rbp+pv]
0x18004a675  test    r14, r14
0x18004a678  jz      loc_18004A91C
0x18004a67e  mov     [rbp+pv], 0
0x18004a686  lea     rdx, [rbp+pv]
0x18004a68a  mov     rax, [r14]
0x18004a68d  mov     rcx, r14
0x18004a690  mov     rax, [rax+20h]
0x18004a694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a699  mov     r15, [rbp+arg_10]
0x18004a69d  mov     edi, eax
0x18004a69f  test    eax, eax
0x18004a6a1  js      loc_18004A8FE
0x18004a6a7  mov     [rbp+arg_10], 0
0x18004a6af  lea     rdx, [rbp+arg_10]
0x18004a6b3  mov     rax, [r14]
0x18004a6b6  mov     rcx, r14
0x18004a6b9  mov     rax, [rax+18h]
0x18004a6bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a6c2  mov     edi, eax
0x18004a6c4  test    eax, eax
0x18004a6c6  js      loc_18004A885
0x18004a6cc  mov     rcx, [rbp+arg_10]
0x18004a6d0  test    rcx, rcx
0x18004a6d3  jz      loc_18004A885
0x18004a6d9  mov     [rbp+pProps], 0
0x18004a6e1  lea     rdx, [rbp+pProps]
0x18004a6e5  mov     rax, [rcx]
0x18004a6e8  mov     rax, [rax+38h]
0x18004a6ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a6f1  mov     edi, eax
0x18004a6f3  test    eax, eax
0x18004a6f5  js      loc_18004A875
0x18004a6fb  mov     rcx, [rbp+pProps]
0x18004a6ff  test    rcx, rcx
0x18004a702  jz      loc_18004A875
0x18004a708  mov     eax, [rcx+28h]
0x18004a70b  shr     eax, 0Ah
0x18004a70e  and     eax, 1
0x18004a711  mov     [rbp+var_10], 0
0x18004a719  mov     [rsi+80h], eax
0x18004a71f  mov     eax, [rcx+24h]
0x18004a722  lea     rcx, [rbp+var_10]
0x18004a726  mov     [rsi+68h], eax
0x18004a729  cmp     eax, 3
0x18004a72c  jnz     short loc_18004A75E
0x18004a72e  call    ?CreateInstance@?$CComObject@VCLANStatisticsProvider@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CLANStatisticsProvider>::CreateInstance(ATL::CComObject<CLANStatisticsProvider> * *)
0x18004a733  mov     edi, eax
0x18004a735  test    eax, eax
0x18004a737  js      loc_18004A86B
0x18004a73d  mov     rbx, [rbp+var_10]
0x18004a741  mov     rcx, rbx
0x18004a744  mov     rax, [rbx]
0x18004a747  mov     rax, [rax+8]
0x18004a74b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a750  mov     rdx, [rbp+pv]; struct _GUID *
0x18004a754  mov     rcx, rbx; this
0x18004a757  call    ?Initialize@CLANStatisticsProvider@@QEAAJPEAU_GUID@@@Z; CLANStatisticsProvider::Initialize(_GUID *)
0x18004a75c  jmp     short loc_18004A79A
0x18004a75e  call    ?CreateInstance@?$CComObject@VCRASStatisticsProvider@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CRASStatisticsProvider>::CreateInstance(ATL::CComObject<CRASStatisticsProvider> * *)
0x18004a763  mov     edi, eax
0x18004a765  test    eax, eax
0x18004a767  js      loc_18004A86B
0x18004a76d  mov     rbx, [rbp+var_10]
0x18004a771  mov     rcx, rbx
0x18004a774  mov     rax, [rbx]
0x18004a777  mov     rax, [rax+8]
0x18004a77b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a780  mov     rcx, [rbp+arg_10]
0x18004a784  lea     r8, [rbx+40h]
0x18004a788  lea     rdx, IID_INetRasConnection
0x18004a78f  mov     rax, [rcx]
0x18004a792  mov     rax, [rax]
0x18004a795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a79a  mov     [rsi+88h], rbx
0x18004a7a1  mov     edi, eax
0x18004a7a3  test    eax, eax
0x18004a7a5  js      loc_18004A86B
0x18004a7ab  cmp     dword ptr [rsi+68h], 3
0x18004a7af  jnz     short loc_18004A7EE
0x18004a7b1  lea     rbx, [rsi+50h]
0x18004a7b5  mov     rcx, rbx
0x18004a7b8  call    ?CreateInstance@?$CComObject@VCWANIPConnectionService@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CWANIPConnectionService>::CreateInstance(ATL::CComObject<CWANIPConnectionService> * *)
0x18004a7bd  mov     edi, eax
0x18004a7bf  test    eax, eax
0x18004a7c1  js      loc_18004A86B
0x18004a7c7  mov     rcx, [rbx]
0x18004a7ca  mov     rax, [rcx]
0x18004a7cd  mov     rax, [rax+8]
0x18004a7d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a7d6  mov     r9, [rsi+88h]; struct IStatisticsProvider *
0x18004a7dd  mov     r8, r14; struct IHNetConnection *
0x18004a7e0  mov     rdx, [rbp+pv]; struct _GUID *
0x18004a7e4  mov     rcx, [rbx]; this
0x18004a7e7  call    ?Initialize@CWANConnectionBase@@QEAAJPEAU_GUID@@PEAUIHNetConnection@@PEAUIStatisticsProvider@@@Z; CWANConnectionBase::Initialize(_GUID *,IHNetConnection *,IStatisticsProvider *)
0x18004a7ec  jmp     short loc_18004A869
0x18004a7ee  lea     rbx, [rsi+58h]
0x18004a7f2  mov     rcx, rbx
0x18004a7f5  call    ?CreateInstance@?$CComObject@VCWANPPPConnectionService@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CWANPPPConnectionService>::CreateInstance(ATL::CComObject<CWANPPPConnectionService> * *)
0x18004a7fa  mov     edi, eax
0x18004a7fc  test    eax, eax
0x18004a7fe  js      short loc_18004A86B
0x18004a800  mov     rcx, [rbx]
0x18004a803  mov     rax, [rcx]
0x18004a806  mov     rax, [rax+8]
0x18004a80a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a80f  mov     r9, [rsi+88h]; struct IStatisticsProvider *
0x18004a816  mov     r8, r14; struct IHNetConnection *
0x18004a819  mov     rdx, [rbp+pv]; struct _GUID *
0x18004a81d  mov     rcx, [rbx]; this
0x18004a820  call    ?Initialize@CWANConnectionBase@@QEAAJPEAU_GUID@@PEAUIHNetConnection@@PEAUIStatisticsProvider@@@Z; CWANConnectionBase::Initialize(_GUID *,IHNetConnection *,IStatisticsProvider *)
0x18004a825  mov     edi, eax
0x18004a827  test    eax, eax
0x18004a829  js      short loc_18004A86B
0x18004a82b  lea     rbx, [rsi+60h]
0x18004a82f  mov     rcx, rbx
0x18004a832  call    ?CreateInstance@?$CComObject@VCWANPOTSLinkConfigService@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CWANPOTSLinkConfigService>::CreateInstance(ATL::CComObject<CWANPOTSLinkConfigService> * *)
0x18004a837  mov     edi, eax
0x18004a839  test    eax, eax
0x18004a83b  js      short loc_18004A86B
0x18004a83d  mov     rcx, [rbx]
0x18004a840  mov     rax, [rcx]
0x18004a843  mov     rax, [rax+8]
0x18004a847  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a84c  mov     rcx, [rbp+arg_10]
0x18004a850  lea     rdx, IID_INetRasConnection
0x18004a857  mov     r8, [rbx]
0x18004a85a  add     r8, 58h ; 'X'
0x18004a85e  mov     rax, [rcx]
0x18004a861  mov     rax, [rax]
0x18004a864  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a869  mov     edi, eax
0x18004a86b  mov     rcx, [rbp+pProps]; pProps
0x18004a86f  call    cs:__imp_NcFreeNetconProperties
0x18004a875  mov     rcx, [rbp+arg_10]
0x18004a879  mov     rax, [rcx]
0x18004a87c  mov     rax, [rax+10h]
0x18004a880  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a885  mov     rcx, [rbp+pv]; pv
0x18004a889  call    cs:__imp_CoTaskMemFree
0x18004a88f  test    edi, edi
0x18004a891  js      short loc_18004A8FE
0x18004a893  test    r15, r15
0x18004a896  jz      short loc_18004A8FE
0x18004a898  mov     rax, [r15]
0x18004a89b  lea     rdx, [rbp+pv]
0x18004a89f  mov     rcx, r15
0x18004a8a2  mov     rax, [rax+20h]
0x18004a8a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a8ab  mov     edi, eax
0x18004a8ad  test    eax, eax
0x18004a8af  js      short loc_18004A8FE
0x18004a8b1  xor     edx, edx; pUnkOuter
0x18004a8b3  lea     r9, IID_IUPnPDeviceHostICSSupport; riid
0x18004a8ba  add     rsi, 78h ; 'x'
0x18004a8be  lea     rcx, CLSID_UPnPDeviceHostICSSupport; rclsid
0x18004a8c5  mov     [rsp+40h+ppv], rsi; ppv
0x18004a8ca  lea     r8d, [rdx+15h]; dwClsContext
0x18004a8ce  call    cs:__imp_CoCreateInstance
0x18004a8d4  mov     edi, eax
0x18004a8d6  test    eax, eax
0x18004a8d8  js      short loc_18004A8F4
0x18004a8da  mov     rcx, [rsi]
0x18004a8dd  mov     edx, 1
0x18004a8e2  mov     r8, [rbp+pv]
0x18004a8e6  mov     rax, [rcx]
0x18004a8e9  mov     rax, [rax+18h]
0x18004a8ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a8f2  mov     edi, eax
0x18004a8f4  mov     rcx, [rbp+pv]; pv
0x18004a8f8  call    cs:__imp_CoTaskMemFree
0x18004a8fe  mov     rax, [r14]
0x18004a901  mov     rcx, r14
0x18004a904  mov     rax, [rax+10h]
0x18004a908  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a90d  mov     rax, [r15]
0x18004a910  mov     rcx, r15
0x18004a913  mov     rax, [rax+10h]
0x18004a917  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a91c  mov     rbx, [rsp+40h+arg_0]
0x18004a921  mov     eax, edi
0x18004a923  add     rsp, 40h
0x18004a927  pop     r15
0x18004a929  pop     r14
0x18004a92b  pop     rdi
0x18004a92c  pop     rsi
0x18004a92d  pop     rbp
0x18004a92e  retn
```
