# HrOnCommandCreateBridge(std::vector<CPConFoldPidl<ConFoldPidl_v3>,std::allocator<CPConFoldPidl<ConFoldPidl_v3>>> const &,HWND__ *,IShellFolder *)

- ea: `0x180018970`
- end: `0x180018d6c`
- name: `?HrOnCommandCreateBridge@@YAJAEBV?$vector@V?$CPConFoldPidl@VConFoldPidl_v3@@@@V?$allocator@V?$CPConFoldPidl@VConFoldPidl_v3@@@@@std@@@std@@PEAUHWND__@@PEAUIShellFolder@@@Z`
- size: `1020`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180018970`
- `0x180018d74`
- `0x18001bc10`
- `0x18001c91c`
- `0x18001ce7c`
- `0x18001d580`
- `0x18001e1e0`
- `0x18002bf6c`
- `0x18002c0a8`
- `0x180034cc8`
- `0x180034fbc`
- `0x180040a5c`
- `0x180043f6c`
- `0x180043fe0`
- `0x1800443ac`
- `0x18004449c`
- `0x180046e90`
- `0x18004cee0`
- `0x180065010`

## import_xrefs

- `ntdll!WinSqmSetDWORD` at `0x180018ada`
- `ntdll!WinSqmSetDWORD` at `0x180018c48`
- `ntdll!WinSqmSetDWORD` at `0x180018c6a`
- `ntdll!WinSqmSetDWORD` at `0x180018ada`
- `ntdll!WinSqmSetDWORD` at `0x180018c48`
- `ntdll!WinSqmSetDWORD` at `0x180018c6a`
- `USER32!SendMessageW` at `0x180018d3c`
- `USER32!SendMessageW` at `0x180018d3c`
- `ole32!CoCreateInstance` at `0x1800189e5`
- `ole32!CoCreateInstance` at `0x1800189e5`

## string_xrefs

- `0x180018ae2`: `ConfigureInterfaceBridging`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall HrOnCommandCreateBridge(__int64 **a1, HWND a2)
{
  HICON v4; // rdi
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rsi
  bool v8; // bl
  __int64 *i; // rbx
  __int64 v10; // rax
  unsigned int v11; // ebx
  __int64 v12; // r8
  unsigned int v13; // r9d
  struct IUnknown *v15; // [rsp+30h] [rbp-D0h] BYREF
  struct IUnknown *v16; // [rsp+38h] [rbp-C8h] BYREF
  struct IUnknown *ppv; // [rsp+40h] [rbp-C0h] BYREF
  struct IUnknown *v18; // [rsp+48h] [rbp-B8h] BYREF
  struct IUnknown *v19; // [rsp+50h] [rbp-B0h] BYREF
  int v20; // [rsp+58h] [rbp-A8h] BYREF
  struct IUnknown *v21; // [rsp+60h] [rbp-A0h] BYREF
  struct IUnknown *v22[3]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v23[42]; // [rsp+80h] [rbp-80h] BYREF

  ppv = 0;
  v4 = BeginWaitCursor();
  v22[1] = (struct IUnknown *)v4;
  if ( (unsigned int)FCheckGroupMembershipInternal(v6, v5, 0x220u, 0) )
  {
    LODWORD(v7) = CoCreateInstance(&CLSID_HNetCfgMgr, 0, 3u, &IID_IHNetCfgMgr, (LPVOID *)&ppv);
  }
  else
  {
    LODWORD(v7) = CoCreateInstanceAsAdmin(a2, &CLSID_HNetCfgMgr, &IID_IHNetCfgMgr, (void **)&ppv);
    if ( (unsigned int)HR_CANCELLED(v7) )
      goto LABEL_46;
  }
  if ( (int)v7 < 0 )
    goto LABEL_49;
  v19 = 0;
  LODWORD(v7) = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))ppv->lpVtbl->QueryInterface)(
                  ppv,
                  &IID_IHNetBridgeSettings,
                  &v19);
  if ( (int)v7 >= 0 )
  {
    v18 = 0;
    v21 = 0;
    LODWORD(v7) = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v19->lpVtbl[1].QueryInterface)(
                    v19,
                    &v21);
    if ( (int)v7 >= 0 )
    {
      v20 = 0;
      LODWORD(v7) = ((__int64 (__fastcall *)(struct IUnknown *, __int64, struct IUnknown **, int *))v21->lpVtbl[1].QueryInterface)(
                      v21,
                      1,
                      &v18,
                      &v20);
      v8 = 0;
      if ( (_DWORD)v7 == 1 )
      {
        v7 = ((unsigned int (__fastcall *)(struct IUnknown *, struct IUnknown **, _QWORD))v19->lpVtbl[1].AddRef)(
               v19,
               &v18,
               0);
        WinSqmSetDWORD(0, 1894, v7);
        v8 = 1;
      }
      wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(
        v23,
        "ConfigureInterfaceBridging");
      v23[0] = &NetworkLegacyUxTelemetry::ConfigureInterfaceBridging::`vftable';
      NetworkLegacyUxTelemetry::ConfigureInterfaceBridging::StartActivity(
        (NetworkLegacyUxTelemetry::ConfigureInterfaceBridging *)v23,
        v8);
      if ( !(_DWORD)v7 )
      {
        for ( i = *a1; i != a1[1] && (int)v7 >= 0; ++i )
        {
          v10 = *i;
          if ( *i )
          {
            if ( *(_DWORD *)(v10 + 48) == 3 && (*(_DWORD *)(v10 + 44) & 0x2300) == 0 )
            {
              v15 = 0;
              LODWORD(v7) = HrNetConFromPidl(i, &v15, 1);
              if ( (int)v7 >= 0 )
              {
                SetLUAParent(v15, a2);
                v16 = 0;
                LODWORD(v7) = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown *, struct IUnknown **))ppv->lpVtbl[1].QueryInterface)(
                                ppv,
                                v15,
                                &v16);
                if ( (int)v7 >= 0 )
                {
                  v22[0] = 0;
                  LODWORD(v7) = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown *, struct IUnknown **, _QWORD))v18->lpVtbl[1].AddRef)(
                                  v18,
                                  v16,
                                  v22,
                                  0);
                  if ( (int)v7 >= 0 )
                    ReleaseObj(v22[0]);
                  ReleaseObj(v16);
                }
                ReleaseObj(v15);
              }
            }
          }
        }
        LODWORD(v15) = 0;
        LODWORD(v16) = 0;
        GetAdapterCount((unsigned int *)&v16, (unsigned int *)&v15);
        v11 = (unsigned int)v15;
        if ( (unsigned int)v15 > 0xFF )
          v11 = 255;
        LODWORD(v15) = v11;
        v12 = (unsigned int)v16;
        if ( (unsigned int)v16 > 0xFF )
          v12 = 255;
        LODWORD(v16) = v12;
        if ( (_DWORD)v12 )
        {
          WinSqmSetDWORD(0, 1887, v12);
          NetworkLegacyUxTelemetry::ConfigureInterfaceBridging::AdapterCount<unsigned long &>((__int64)v23, (int *)&v16);
        }
        if ( v11 )
        {
          WinSqmSetDWORD(0, 1886, v11);
          NetworkLegacyUxTelemetry::ConfigureInterfaceBridging::BridgeCount<unsigned long &>((__int64)v23, (int *)&v15);
        }
        ReleaseObj(v18);
      }
      ReleaseObj(v21);
      wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        v23,
        (unsigned int)v7);
      NetworkLegacyUxTelemetry::ConfigureInterfaceBridging::~ConfigureInterfaceBridging((NetworkLegacyUxTelemetry::ConfigureInterfaceBridging *)v23);
    }
    ReleaseObj(v19);
  }
  ReleaseObj(ppv);
  if ( (int)v7 < 0 )
  {
LABEL_49:
    if ( !(unsigned int)HR_CANCELLED(v7) )
    {
      if ( (_DWORD)v7 != -2147220764 )
      {
        if ( (_DWORD)v7 == -2147180508 )
        {
          v13 = 10603;
          goto LABEL_45;
        }
        if ( (_DWORD)v7 != -2147024891 )
        {
          if ( (_DWORD)v7 == -2147024882 )
          {
            v13 = 1101;
            goto LABEL_45;
          }
          if ( (_DWORD)v7 != -2147024156 )
          {
            v13 = 10605;
LABEL_45:
            NcMsgBox(hInst, a2, 0x424u, v13, 0x30u);
            goto LABEL_46;
          }
        }
      }
      v13 = 1096;
      goto LABEL_45;
    }
  }
LABEL_46:
  SendMessageW(a2, 0x111u, 2u, 0);
  EndWaitCursor(v4);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180018970  push    rbp
0x180018972  push    rbx
0x180018973  push    rsi
0x180018974  push    rdi
0x180018975  push    r14
0x180018977  push    r15
0x180018979  lea     rbp, [rsp-0E8h]
0x180018981  sub     rsp, 1E8h
0x180018988  mov     rax, cs:__security_cookie
0x18001898f  xor     rax, rsp
0x180018992  mov     [rbp+110h+var_40], rax
0x180018999  mov     r14, rdx
0x18001899c  mov     r15, rcx
0x18001899f  mov     [rsp+210h+var_1D0], 0
0x1800189a8  call    ?BeginWaitCursor@@YAPEAUHICON__@@XZ; BeginWaitCursor(void)
0x1800189ad  mov     rdi, rax
0x1800189b0  mov     [rsp+210h+var_1A0], rax
0x1800189b5  xor     r9d, r9d; int
0x1800189b8  mov     r8d, 220h; unsigned int
0x1800189be  call    ?FCheckGroupMembershipInternal@@YAHEKKH@Z; FCheckGroupMembershipInternal(uchar,ulong,ulong,int)
0x1800189c3  test    eax, eax
0x1800189c5  jz      short loc_1800189EF
0x1800189c7  lea     rax, [rsp+210h+var_1D0]
0x1800189cc  mov     [rsp+210h+ppv], rax; ppv
0x1800189d1  lea     r9, IID_IHNetCfgMgr; riid
0x1800189d8  xor     edx, edx; pUnkOuter
0x1800189da  lea     r8d, [rdx+3]; dwClsContext
0x1800189de  lea     rcx, CLSID_HNetCfgMgr; rclsid
0x1800189e5  call    cs:__imp_CoCreateInstance
0x1800189eb  mov     esi, eax
0x1800189ed  jmp     short loc_180018A1B
0x1800189ef  lea     r9, [rsp+210h+var_1D0]; void **
0x1800189f4  lea     r8, IID_IHNetCfgMgr; struct _GUID *
0x1800189fb  lea     rdx, CLSID_HNetCfgMgr; struct _GUID *
0x180018a02  mov     rcx, r14; HWND
0x180018a05  call    ?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z; CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)
0x180018a0a  mov     esi, eax
0x180018a0c  mov     ecx, eax; int
0x180018a0e  call    ?HR_CANCELLED@@YAHJ@Z; HR_CANCELLED(long)
0x180018a13  test    eax, eax
0x180018a15  jnz     loc_180018D2D
0x180018a1b  test    esi, esi
0x180018a1d  js      loc_180018CBF
0x180018a23  mov     [rsp+210h+var_1C0], 0
0x180018a2c  mov     rcx, [rsp+210h+var_1D0]
0x180018a31  mov     rax, [rcx]
0x180018a34  lea     r8, [rsp+210h+var_1C0]
0x180018a39  lea     rdx, IID_IHNetBridgeSettings
0x180018a40  mov     rax, [rax]
0x180018a43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a48  mov     esi, eax
0x180018a4a  test    eax, eax
0x180018a4c  js      loc_180018CB1
0x180018a52  mov     [rsp+210h+var_1C8], 0
0x180018a5b  mov     [rsp+210h+var_1B0], 0
0x180018a64  mov     rcx, [rsp+210h+var_1C0]
0x180018a69  mov     rax, [rcx]
0x180018a6c  lea     rdx, [rsp+210h+var_1B0]
0x180018a71  mov     rax, [rax+18h]
0x180018a75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a7a  mov     esi, eax
0x180018a7c  test    eax, eax
0x180018a7e  js      loc_180018CA7
0x180018a84  mov     [rsp+210h+var_1B8], 0
0x180018a8c  mov     rcx, [rsp+210h+var_1B0]
0x180018a91  mov     rax, [rcx]
0x180018a94  lea     r9, [rsp+210h+var_1B8]
0x180018a99  lea     r8, [rsp+210h+var_1C8]
0x180018a9e  mov     edx, 1
0x180018aa3  mov     rax, [rax+18h]
0x180018aa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018aac  mov     esi, eax
0x180018aae  xor     bl, bl
0x180018ab0  cmp     eax, 1
0x180018ab3  jnz     short loc_180018AE2
0x180018ab5  mov     rcx, [rsp+210h+var_1C0]
0x180018aba  mov     rax, [rcx]
0x180018abd  xor     r8d, r8d
0x180018ac0  lea     rdx, [rsp+210h+var_1C8]
0x180018ac5  mov     rax, [rax+20h]
0x180018ac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ace  mov     esi, eax
0x180018ad0  mov     r8d, eax
0x180018ad3  mov     edx, 766h
0x180018ad8  xor     ecx, ecx
0x180018ada  call    cs:__imp_WinSqmSetDWORD
0x180018ae0  mov     bl, 1
0x180018ae2  lea     rdx, aConfigureinter; "ConfigureInterfaceBridging"
0x180018ae9  lea     rcx, [rbp+110h+var_190]
0x180018aed  call    ??0?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180018af2  lea     rax, ??_7ConfigureInterfaceBridging@NetworkLegacyUxTelemetry@@6B@; const NetworkLegacyUxTelemetry::ConfigureInterfaceBridging::`vftable'
0x180018af9  mov     [rbp+110h+var_190], rax
0x180018afd  mov     dl, bl; bool
0x180018aff  lea     rcx, [rbp+110h+var_190]; this
0x180018b03  call    ?StartActivity@ConfigureInterfaceBridging@NetworkLegacyUxTelemetry@@QEAAX_N@Z; NetworkLegacyUxTelemetry::ConfigureInterfaceBridging::StartActivity(bool)
0x180018b08  nop
0x180018b09  test    esi, esi
0x180018b0b  jnz     loc_180018C88
0x180018b11  mov     rbx, [r15]
0x180018b14  cmp     rbx, [r15+8]
0x180018b18  jz      loc_180018BFA
0x180018b1e  test    esi, esi
0x180018b20  js      loc_180018BFA
0x180018b26  mov     rax, [rbx]
0x180018b29  test    rax, rax
0x180018b2c  jz      loc_180018BF1
0x180018b32  cmp     dword ptr [rax+30h], 3
0x180018b36  jnz     loc_180018BF1
0x180018b3c  test    dword ptr [rax+2Ch], 2300h
0x180018b43  jnz     loc_180018BF1
0x180018b49  mov     [rsp+210h+var_1E0], 0
0x180018b52  mov     r8d, 1
0x180018b58  lea     rdx, [rsp+210h+var_1E0]
0x180018b5d  mov     rcx, rbx
0x180018b60  call    ?HrNetConFromPidl@@YAJAEBV?$CPConFoldPidl@VConFoldPidl_v3@@@@PEAPEAUINetConnection@@H@Z; HrNetConFromPidl(CPConFoldPidl<ConFoldPidl_v3> const &,INetConnection * *,int)
0x180018b65  mov     esi, eax
0x180018b67  test    eax, eax
0x180018b69  js      loc_180018BF1
0x180018b6f  mov     rdx, r14; HWND
0x180018b72  mov     rcx, [rsp+210h+var_1E0]; struct IUnknown *
0x180018b77  call    ?SetLUAParent@@YAXPEAUIUnknown@@PEAUHWND__@@@Z; SetLUAParent(IUnknown *,HWND__ *)
0x180018b7c  mov     [rsp+210h+var_1D8], 0
0x180018b85  mov     rcx, [rsp+210h+var_1D0]
0x180018b8a  mov     rax, [rcx]
0x180018b8d  lea     r8, [rsp+210h+var_1D8]
0x180018b92  mov     rdx, [rsp+210h+var_1E0]
0x180018b97  mov     rax, [rax+18h]
0x180018b9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ba0  mov     esi, eax
0x180018ba2  test    eax, eax
0x180018ba4  js      short loc_180018BE7
0x180018ba6  mov     [rsp+210h+var_1A8], 0
0x180018baf  mov     rcx, [rsp+210h+var_1C8]
0x180018bb4  mov     rax, [rcx]
0x180018bb7  xor     r9d, r9d
0x180018bba  lea     r8, [rsp+210h+var_1A8]
0x180018bbf  mov     rdx, [rsp+210h+var_1D8]
0x180018bc4  mov     rax, [rax+20h]
0x180018bc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018bcd  mov     esi, eax
0x180018bcf  test    eax, eax
0x180018bd1  js      short loc_180018BDD
0x180018bd3  mov     rcx, [rsp+210h+var_1A8]; struct IUnknown *
0x180018bd8  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x180018bdd  mov     rcx, [rsp+210h+var_1D8]; struct IUnknown *
0x180018be2  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x180018be7  mov     rcx, [rsp+210h+var_1E0]; struct IUnknown *
0x180018bec  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x180018bf1  add     rbx, 8
0x180018bf5  jmp     loc_180018B14
0x180018bfa  mov     dword ptr [rsp+210h+var_1E0], 0
0x180018c02  mov     dword ptr [rsp+210h+var_1D8], 0
0x180018c0a  lea     rdx, [rsp+210h+var_1E0]; unsigned int *
0x180018c0f  lea     rcx, [rsp+210h+var_1D8]; unsigned int *
0x180018c14  call    ?GetAdapterCount@@YAJPEAK0@Z; GetAdapterCount(ulong *,ulong *)
0x180018c19  mov     ebx, dword ptr [rsp+210h+var_1E0]
0x180018c1d  mov     eax, 0FFh
0x180018c22  cmp     ebx, eax
0x180018c24  cmova   ebx, eax
0x180018c27  mov     dword ptr [rsp+210h+var_1E0], ebx
0x180018c2b  mov     r8d, dword ptr [rsp+210h+var_1D8]
0x180018c30  cmp     r8d, eax
0x180018c33  cmova   r8d, eax
0x180018c37  mov     dword ptr [rsp+210h+var_1D8], r8d
0x180018c3c  test    r8d, r8d
0x180018c3f  jz      short loc_180018C5C
0x180018c41  mov     edx, 75Fh
0x180018c46  xor     ecx, ecx
0x180018c48  call    cs:__imp_WinSqmSetDWORD
0x180018c4e  lea     rdx, [rsp+210h+var_1D8]
0x180018c53  lea     rcx, [rbp+110h+var_190]
0x180018c57  call    ??$AdapterCount@AEAK@ConfigureInterfaceBridging@NetworkLegacyUxTelemetry@@QEAAXAEAK@Z; NetworkLegacyUxTelemetry::ConfigureInterfaceBridging::AdapterCount<ulong &>(ulong &)
0x180018c5c  test    ebx, ebx
0x180018c5e  jz      short loc_180018C7E
0x180018c60  mov     r8d, ebx
0x180018c63  mov     edx, 75Eh
0x180018c68  xor     ecx, ecx
0x180018c6a  call    cs:__imp_WinSqmSetDWORD
0x180018c70  lea     rdx, [rsp+210h+var_1E0]
0x180018c75  lea     rcx, [rbp+110h+var_190]
0x180018c79  call    ??$BridgeCount@AEAK@ConfigureInterfaceBridging@NetworkLegacyUxTelemetry@@QEAAXAEAK@Z; NetworkLegacyUxTelemetry::ConfigureInterfaceBridging::BridgeCount<ulong &>(ulong &)
0x180018c7e  mov     rcx, [rsp+210h+var_1C8]; struct IUnknown *
0x180018c83  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x180018c88  mov     rcx, [rsp+210h+var_1B0]; struct IUnknown *
0x180018c8d  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x180018c92  mov     edx, esi
0x180018c94  lea     rcx, [rbp+110h+var_190]
0x180018c98  call    ?Stop@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180018c9d  nop
0x180018c9e  lea     rcx, [rbp+110h+var_190]; this
0x180018ca2  call    ??1ConfigureInterfaceBridging@NetworkLegacyUxTelemetry@@QEAA@XZ; NetworkLegacyUxTelemetry::ConfigureInterfaceBridging::~ConfigureInterfaceBridging(void)
0x180018ca7  mov     rcx, [rsp+210h+var_1C0]; struct IUnknown *
0x180018cac  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x180018cb1  mov     rcx, [rsp+210h+var_1D0]; struct IUnknown *
0x180018cb6  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x180018cbb  test    esi, esi
0x180018cbd  jns     short loc_180018D2D
0x180018cbf  mov     ecx, esi; int
0x180018cc1  call    ?HR_CANCELLED@@YAHJ@Z; HR_CANCELLED(long)
0x180018cc6  test    eax, eax
0x180018cc8  jnz     short loc_180018D2D
0x180018cca  cmp     esi, 800402E4h
0x180018cd0  jz      short loc_180018D0A
0x180018cd2  cmp     esi, 8004A024h
0x180018cd8  jz      short loc_180018D02
0x180018cda  cmp     esi, 80070005h
0x180018ce0  jz      short loc_180018D0A
0x180018ce2  cmp     esi, 8007000Eh
0x180018ce8  jz      short loc_180018CFA
0x180018cea  cmp     esi, 800702E4h
0x180018cf0  jz      short loc_180018D0A
0x180018cf2  mov     r9d, 296Dh
0x180018cf8  jmp     short loc_180018D10
0x180018cfa  mov     r9d, 44Dh
0x180018d00  jmp     short loc_180018D10
0x180018d02  mov     r9d, 296Bh
0x180018d08  jmp     short loc_180018D10
0x180018d0a  mov     r9d, 448h; unsigned int
0x180018d10  mov     dword ptr [rsp+210h+ppv], 30h ; '0'; uType
0x180018d18  mov     r8d, 424h; unsigned int
0x180018d1e  mov     rdx, r14; hWnd
0x180018d21  mov     rcx, cs:hInst; hModule
0x180018d28  call    ?NcMsgBox@@YAHPEAUHINSTANCE__@@PEAUHWND__@@IIIZZ; NcMsgBox(HINSTANCE__ *,HWND__ *,uint,uint,uint,...)
0x180018d2d  xor     r9d, r9d; lParam
0x180018d30  lea     r8d, [r9+2]; wParam
0x180018d34  mov     edx, 111h; Msg
0x180018d39  mov     rcx, r14; hWnd
0x180018d3c  call    cs:__imp_SendMessageW
0x180018d42  nop
0x180018d43  mov     rcx, rdi; HICON
0x180018d46  call    ?EndWaitCursor@@YAXPEAUHICON__@@@Z; EndWaitCursor(HICON__ *)
0x180018d4b  mov     eax, esi
0x180018d4d  mov     rcx, [rbp+110h+var_40]
0x180018d54  xor     rcx, rsp; StackCookie
0x180018d57  call    __security_check_cookie
0x180018d5c  add     rsp, 1E8h
0x180018d63  pop     r15
0x180018d65  pop     r14
0x180018d67  pop     rdi
0x180018d68  pop     rsi
0x180018d69  pop     rbx
0x180018d6a  pop     rbp
0x180018d6b  retn
```
