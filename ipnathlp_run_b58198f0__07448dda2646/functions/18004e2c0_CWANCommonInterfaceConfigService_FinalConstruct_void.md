# CWANCommonInterfaceConfigService::FinalConstruct(void)

- ea: `0x18004e2c0`
- end: `0x18004e5d4`
- name: `?FinalConstruct@CWANCommonInterfaceConfigService@@QEAAJXZ`
- size: `788`
- prototype: `__int64 __fastcall(CWANCommonInterfaceConfigService *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800929a0`

## callees

- `0x18004e180`
- `0x18004e2c0`
- `0x18004e5dc`
- `0x180093554`
- `0x18009360c`
- `0x1800936bc`
- `0x18009375c`
- `0x1800937f0`
- `0x180094988`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e51b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e596`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e51b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e596`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004e566`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004e566`
- `ext-ms-win-net-netshell-l1-1-0!NcFreeNetconProperties` at `0x18004e4fb`
- `ext-ms-win-net-netshell-l1-1-0!NcFreeNetconProperties` at `0x18004e4fb`

## pseudocode

```c
__int64 __fastcall CWANCommonInterfaceConfigService::FinalConstruct(struct IStatisticsProvider **this)
{
  HRESULT Connections; // edi
  struct IHNetConnection *v3; // r14
  int v4; // eax
  struct IHNetConnection *v5; // r15
  NETCON_PROPERTIES *v6; // rcx
  DWORD v7; // eax
  NETCON_MEDIATYPE MediaType; // eax
  CLANStatisticsProvider *v9; // rbx
  int v10; // eax
  CWANConnectionBase **v11; // rbx
  HRESULT v12; // eax
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
        Connections = ATL::CComObject<CLANStatisticsProvider>::CreateInstance(v17);
        if ( Connections < 0 )
          goto LABEL_22;
        v9 = v17[0];
        (*(void (__fastcall **)(CLANStatisticsProvider *))(*(_QWORD *)v17[0] + 8LL))(v17[0]);
        v10 = CLANStatisticsProvider::Initialize(v9, (struct _GUID *)pv);
      }
      else
      {
        Connections = ATL::CComObject<CRASStatisticsProvider>::CreateInstance(v17);
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
          Connections = ATL::CComObject<CWANPPPConnectionService>::CreateInstance(this + 11);
          if ( Connections < 0 )
            goto LABEL_22;
          (*(void (__fastcall **)(CWANConnectionBase *))(*(_QWORD *)*v13 + 8LL))(*v13);
          Connections = CWANConnectionBase::Initialize(*v13, (struct _GUID *)pv, v3, this[17]);
          if ( Connections < 0 )
            goto LABEL_22;
          v14 = this + 12;
          Connections = ATL::CComObject<CWANPOTSLinkConfigService>::CreateInstance(this + 12);
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
        Connections = ATL::CComObject<CWANIPConnectionService>::CreateInstance(this + 10);
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
0x18004e2c0  mov     [rsp-28h+arg_0], rbx
0x18004e2c5  push    rbp
0x18004e2c6  push    rsi
0x18004e2c7  push    rdi
0x18004e2c8  push    r14
0x18004e2ca  push    r15
0x18004e2cc  mov     rbp, rsp
0x18004e2cf  sub     rsp, 40h
0x18004e2d3  lea     r8, [rbp+arg_10]; struct IHNetConnection **
0x18004e2d7  mov     [rbp+pv], 0
0x18004e2df  lea     rdx, [rbp+pv]; struct IHNetConnection **
0x18004e2e3  mov     [rbp+arg_10], 0
0x18004e2eb  mov     rsi, rcx
0x18004e2ee  call    ?GetConnections@CWANCommonInterfaceConfigService@@AEAAJPEAPEAUIHNetConnection@@0@Z; CWANCommonInterfaceConfigService::GetConnections(IHNetConnection * *,IHNetConnection * *)
0x18004e2f3  mov     edi, eax
0x18004e2f5  test    eax, eax
0x18004e2f7  js      loc_18004E5C0
0x18004e2fd  mov     r14, [rbp+pv]
0x18004e301  test    r14, r14
0x18004e304  jz      loc_18004E5C0
0x18004e30a  mov     [rbp+pv], 0
0x18004e312  lea     rdx, [rbp+pv]
0x18004e316  mov     rax, [r14]
0x18004e319  mov     rcx, r14
0x18004e31c  mov     rax, [rax+20h]
0x18004e320  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e325  mov     r15, [rbp+arg_10]
0x18004e329  mov     edi, eax
0x18004e32b  test    eax, eax
0x18004e32d  js      loc_18004E5A2
0x18004e333  mov     [rbp+arg_10], 0
0x18004e33b  lea     rdx, [rbp+arg_10]
0x18004e33f  mov     rax, [r14]
0x18004e342  mov     rcx, r14
0x18004e345  mov     rax, [rax+18h]
0x18004e349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e34e  mov     edi, eax
0x18004e350  test    eax, eax
0x18004e352  js      loc_18004E517
0x18004e358  mov     rcx, [rbp+arg_10]
0x18004e35c  test    rcx, rcx
0x18004e35f  jz      loc_18004E517
0x18004e365  mov     [rbp+pProps], 0
0x18004e36d  lea     rdx, [rbp+pProps]
0x18004e371  mov     rax, [rcx]
0x18004e374  mov     rax, [rax+38h]
0x18004e378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e37d  mov     edi, eax
0x18004e37f  test    eax, eax
0x18004e381  js      loc_18004E507
0x18004e387  mov     rcx, [rbp+pProps]
0x18004e38b  test    rcx, rcx
0x18004e38e  jz      loc_18004E507
0x18004e394  mov     eax, [rcx+28h]
0x18004e397  shr     eax, 0Ah
0x18004e39a  and     eax, 1
0x18004e39d  mov     [rbp+var_10], 0
0x18004e3a5  mov     [rsi+80h], eax
0x18004e3ab  mov     eax, [rcx+24h]
0x18004e3ae  lea     rcx, [rbp+var_10]
0x18004e3b2  mov     [rsi+68h], eax
0x18004e3b5  cmp     eax, 3
0x18004e3b8  jnz     short loc_18004E3EA
0x18004e3ba  call    ?CreateInstance@?$CComObject@VCLANStatisticsProvider@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CLANStatisticsProvider>::CreateInstance(ATL::CComObject<CLANStatisticsProvider> * *)
0x18004e3bf  mov     edi, eax
0x18004e3c1  test    eax, eax
0x18004e3c3  js      loc_18004E4F7
0x18004e3c9  mov     rbx, [rbp+var_10]
0x18004e3cd  mov     rcx, rbx
0x18004e3d0  mov     rax, [rbx]
0x18004e3d3  mov     rax, [rax+8]
0x18004e3d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e3dc  mov     rdx, [rbp+pv]; struct _GUID *
0x18004e3e0  mov     rcx, rbx; this
0x18004e3e3  call    ?Initialize@CLANStatisticsProvider@@QEAAJPEAU_GUID@@@Z; CLANStatisticsProvider::Initialize(_GUID *)
0x18004e3e8  jmp     short loc_18004E426
0x18004e3ea  call    ?CreateInstance@?$CComObject@VCRASStatisticsProvider@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CRASStatisticsProvider>::CreateInstance(ATL::CComObject<CRASStatisticsProvider> * *)
0x18004e3ef  mov     edi, eax
0x18004e3f1  test    eax, eax
0x18004e3f3  js      loc_18004E4F7
0x18004e3f9  mov     rbx, [rbp+var_10]
0x18004e3fd  mov     rcx, rbx
0x18004e400  mov     rax, [rbx]
0x18004e403  mov     rax, [rax+8]
0x18004e407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e40c  mov     rcx, [rbp+arg_10]
0x18004e410  lea     r8, [rbx+40h]
0x18004e414  lea     rdx, IID_INetRasConnection
0x18004e41b  mov     rax, [rcx]
0x18004e41e  mov     rax, [rax]
0x18004e421  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e426  mov     [rsi+88h], rbx
0x18004e42d  mov     edi, eax
0x18004e42f  test    eax, eax
0x18004e431  js      loc_18004E4F7
0x18004e437  cmp     dword ptr [rsi+68h], 3
0x18004e43b  jnz     short loc_18004E47A
0x18004e43d  lea     rbx, [rsi+50h]
0x18004e441  mov     rcx, rbx
0x18004e444  call    ?CreateInstance@?$CComObject@VCWANIPConnectionService@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CWANIPConnectionService>::CreateInstance(ATL::CComObject<CWANIPConnectionService> * *)
0x18004e449  mov     edi, eax
0x18004e44b  test    eax, eax
0x18004e44d  js      loc_18004E4F7
0x18004e453  mov     rcx, [rbx]
0x18004e456  mov     rax, [rcx]
0x18004e459  mov     rax, [rax+8]
0x18004e45d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e462  mov     r9, [rsi+88h]; struct IStatisticsProvider *
0x18004e469  mov     r8, r14; struct IHNetConnection *
0x18004e46c  mov     rdx, [rbp+pv]; struct _GUID *
0x18004e470  mov     rcx, [rbx]; this
0x18004e473  call    ?Initialize@CWANConnectionBase@@QEAAJPEAU_GUID@@PEAUIHNetConnection@@PEAUIStatisticsProvider@@@Z; CWANConnectionBase::Initialize(_GUID *,IHNetConnection *,IStatisticsProvider *)
0x18004e478  jmp     short loc_18004E4F5
0x18004e47a  lea     rbx, [rsi+58h]
0x18004e47e  mov     rcx, rbx
0x18004e481  call    ?CreateInstance@?$CComObject@VCWANPPPConnectionService@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CWANPPPConnectionService>::CreateInstance(ATL::CComObject<CWANPPPConnectionService> * *)
0x18004e486  mov     edi, eax
0x18004e488  test    eax, eax
0x18004e48a  js      short loc_18004E4F7
0x18004e48c  mov     rcx, [rbx]
0x18004e48f  mov     rax, [rcx]
0x18004e492  mov     rax, [rax+8]
0x18004e496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e49b  mov     r9, [rsi+88h]; struct IStatisticsProvider *
0x18004e4a2  mov     r8, r14; struct IHNetConnection *
0x18004e4a5  mov     rdx, [rbp+pv]; struct _GUID *
0x18004e4a9  mov     rcx, [rbx]; this
0x18004e4ac  call    ?Initialize@CWANConnectionBase@@QEAAJPEAU_GUID@@PEAUIHNetConnection@@PEAUIStatisticsProvider@@@Z; CWANConnectionBase::Initialize(_GUID *,IHNetConnection *,IStatisticsProvider *)
0x18004e4b1  mov     edi, eax
0x18004e4b3  test    eax, eax
0x18004e4b5  js      short loc_18004E4F7
0x18004e4b7  lea     rbx, [rsi+60h]
0x18004e4bb  mov     rcx, rbx
0x18004e4be  call    ?CreateInstance@?$CComObject@VCWANPOTSLinkConfigService@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CWANPOTSLinkConfigService>::CreateInstance(ATL::CComObject<CWANPOTSLinkConfigService> * *)
0x18004e4c3  mov     edi, eax
0x18004e4c5  test    eax, eax
0x18004e4c7  js      short loc_18004E4F7
0x18004e4c9  mov     rcx, [rbx]
0x18004e4cc  mov     rax, [rcx]
0x18004e4cf  mov     rax, [rax+8]
0x18004e4d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e4d8  mov     rcx, [rbp+arg_10]
0x18004e4dc  lea     rdx, IID_INetRasConnection
0x18004e4e3  mov     r8, [rbx]
0x18004e4e6  add     r8, 58h ; 'X'
0x18004e4ea  mov     rax, [rcx]
0x18004e4ed  mov     rax, [rax]
0x18004e4f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e4f5  mov     edi, eax
0x18004e4f7  mov     rcx, [rbp+pProps]; pProps
0x18004e4fb  call    cs:__imp_NcFreeNetconProperties
0x18004e502  nop     dword ptr [rax+rax+00h]
0x18004e507  mov     rcx, [rbp+arg_10]
0x18004e50b  mov     rax, [rcx]
0x18004e50e  mov     rax, [rax+10h]
0x18004e512  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e517  mov     rcx, [rbp+pv]; pv
0x18004e51b  call    cs:__imp_CoTaskMemFree
0x18004e522  nop     dword ptr [rax+rax+00h]
0x18004e527  test    edi, edi
0x18004e529  js      short loc_18004E5A2
0x18004e52b  test    r15, r15
0x18004e52e  jz      short loc_18004E5A2
0x18004e530  mov     rax, [r15]
0x18004e533  lea     rdx, [rbp+pv]
0x18004e537  mov     rcx, r15
0x18004e53a  mov     rax, [rax+20h]
0x18004e53e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e543  mov     edi, eax
0x18004e545  test    eax, eax
0x18004e547  js      short loc_18004E5A2
0x18004e549  xor     edx, edx; pUnkOuter
0x18004e54b  lea     r9, IID_IUPnPDeviceHostICSSupport; riid
0x18004e552  add     rsi, 78h ; 'x'
0x18004e556  lea     rcx, CLSID_UPnPDeviceHostICSSupport; rclsid
0x18004e55d  mov     [rsp+40h+ppv], rsi; ppv
0x18004e562  lea     r8d, [rdx+15h]; dwClsContext
0x18004e566  call    cs:__imp_CoCreateInstance
0x18004e56d  nop     dword ptr [rax+rax+00h]
0x18004e572  mov     edi, eax
0x18004e574  test    eax, eax
0x18004e576  js      short loc_18004E592
0x18004e578  mov     rcx, [rsi]
0x18004e57b  mov     edx, 1
0x18004e580  mov     r8, [rbp+pv]
0x18004e584  mov     rax, [rcx]
0x18004e587  mov     rax, [rax+18h]
0x18004e58b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e590  mov     edi, eax
0x18004e592  mov     rcx, [rbp+pv]; pv
0x18004e596  call    cs:__imp_CoTaskMemFree
0x18004e59d  nop     dword ptr [rax+rax+00h]
0x18004e5a2  mov     rax, [r14]
0x18004e5a5  mov     rcx, r14
0x18004e5a8  mov     rax, [rax+10h]
0x18004e5ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e5b1  mov     rax, [r15]
0x18004e5b4  mov     rcx, r15
0x18004e5b7  mov     rax, [rax+10h]
0x18004e5bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e5c0  mov     rbx, [rsp+40h+arg_0]
0x18004e5c5  mov     eax, edi
0x18004e5c7  add     rsp, 40h
0x18004e5cb  pop     r15
0x18004e5cd  pop     r14
0x18004e5cf  pop     rdi
0x18004e5d0  pop     rsi
0x18004e5d1  pop     rbp
0x18004e5d2  retn
```
