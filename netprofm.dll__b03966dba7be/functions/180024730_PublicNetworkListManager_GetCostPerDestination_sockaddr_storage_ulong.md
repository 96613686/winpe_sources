# PublicNetworkListManager::GetCostPerDestination(sockaddr_storage *,ulong *)

- ea: `0x180024730`
- end: `0x180024a2a`
- name: `?GetCostPerDestination@PublicNetworkListManager@@AEAAJPEAUsockaddr_storage@@PEAK@Z`
- size: `762`
- prototype: `__int64 __fastcall(PublicNetworkListManager *__hidden this, struct sockaddr_storage *, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800245a0`

## callees

- `0x180006770`
- `0x180006810`
- `0x1800086b0`
- `0x18000a894`
- `0x1800120d0`
- `0x1800210b0`
- `0x180024730`
- `0x1800256b4`
- `0x180025b74`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800248e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800248e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024853`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024853`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PublicNetworkListManager::GetCostPerDestination(
        PublicNetworkListManager *this,
        struct sockaddr *a2,
        unsigned int *a3)
{
  PVOID *v6; // rcx
  unsigned int InterfaceCostAndDataPlanStatus; // ebx
  __int64 v8; // rdx
  int InterfaceStackPerDestination; // eax
  int v10; // eax
  unsigned int *v11; // rax
  PublicNetworkListManager *v12; // rcx
  unsigned int *v13; // rdi
  unsigned int v14; // eax
  PVOID *v15; // rcx
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // r9
  unsigned int v20; // [rsp+40h] [rbp-59h] BYREF
  struct _GUID v21; // [rsp+44h] [rbp-55h] BYREF
  __int128 v22; // [rsp+54h] [rbp-45h]
  int v23; // [rsp+64h] [rbp-35h]
  struct IEnumNetworkConnections *v24; // [rsp+68h] [rbp-31h] BYREF
  struct IEnumNetworkConnections *v25; // [rsp+70h] [rbp-29h] BYREF
  struct _GUID v26; // [rsp+78h] [rbp-21h] BYREF
  struct NLM_DATAPLAN_STATUS v27; // [rsp+88h] [rbp-11h] BYREF

  v20 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  LODWORD(v24) = 0;
  memset(&v27, 0, sizeof(v27));
  v26 = 0;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 138, &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a3 )
  {
    InterfaceCostAndDataPlanStatus = -2147467261;
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 )
    {
      v8 = 139;
LABEL_41:
      WPP_SF_d(v6[2], v8, &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids, InterfaceCostAndDataPlanStatus);
      return InterfaceCostAndDataPlanStatus;
    }
    return InterfaceCostAndDataPlanStatus;
  }
  *a3 = 0;
  InterfaceStackPerDestination = PublicNetworkListManager::GetInterfaceStackPerDestination(
                                   this,
                                   a2,
                                   &v26,
                                   0,
                                   0,
                                   (struct INTERFACE_STACK *)&v20);
  InterfaceCostAndDataPlanStatus = InterfaceStackPerDestination;
  if ( InterfaceStackPerDestination >= 0 )
  {
    v24 = 0;
    v10 = (*(__int64 (__fastcall **)(char *, struct IEnumNetworkConnections **))(*((_QWORD *)this + 16) + 72LL))(
            (char *)this + 128,
            &v24);
    InterfaceCostAndDataPlanStatus = v10;
    if ( v10 < 0 )
    {
      v13 = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          140,
          &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids,
          (unsigned int)v10);
    }
    else
    {
      v11 = (unsigned int *)CoTaskMemAlloc(4LL * v20);
      v13 = v11;
      if ( v11 )
      {
        InterfaceCostAndDataPlanStatus = PublicNetworkListManager::GetInterfaceCostAndDataPlanStatus(
                                           v12,
                                           v24,
                                           v20,
                                           &v21,
                                           v11,
                                           0,
                                           0);
        if ( (InterfaceCostAndDataPlanStatus & 0x80000000) == 0 )
          *a3 = DERIVE_COST_FROM_COST_ARRAY(v20, v13);
      }
      else
      {
        InterfaceCostAndDataPlanStatus = -2147024882;
      }
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v24);
    if ( v13 )
      CoTaskMemFree(v13);
    goto LABEL_37;
  }
  if ( InterfaceStackPerDestination == -2147024894 )
  {
    v25 = 0;
    v14 = (*(__int64 (__fastcall **)(char *, struct IEnumNetworkConnections **))(*((_QWORD *)this + 16) + 72LL))(
            (char *)this + 128,
            &v25);
    InterfaceCostAndDataPlanStatus = v14;
    v15 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 141, &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids, v14);
      v15 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( (InterfaceCostAndDataPlanStatus & 0x80000000) != 0 )
    {
      if ( v15 == &WPP_GLOBAL_Control || (*((_BYTE *)v15 + 28) & 1) == 0 )
        goto LABEL_33;
      v17 = 143;
      v18 = InterfaceCostAndDataPlanStatus;
    }
    else
    {
      v16 = PublicNetworkListManager::ClientHandleUnderminedDestinationCost(
              (PublicNetworkListManager *)v15,
              v25,
              (struct INTERFACE_STACK *)&v20,
              (unsigned int *)&v24,
              &v27);
      InterfaceCostAndDataPlanStatus = v16;
      if ( v16 >= 0 )
      {
        *a3 = (unsigned int)v24;
LABEL_33:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v25);
        goto LABEL_37;
      }
      v15 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_33;
      v17 = 142;
      v18 = (unsigned int)v16;
    }
    WPP_SF_d(v15[2], v17, &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids, v18);
    goto LABEL_33;
  }
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return InterfaceCostAndDataPlanStatus;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    goto LABEL_38;
  WPP_SF_d(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    144,
    &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids,
    (unsigned int)InterfaceStackPerDestination);
LABEL_37:
  v6 = (PVOID *)WPP_GLOBAL_Control;
LABEL_38:
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
  {
    v8 = 145;
    goto LABEL_41;
  }
  return InterfaceCostAndDataPlanStatus;
}

```

## disassembly

```asm
0x180024730  mov     [rsp-8+arg_18], rbx
0x180024735  push    rbp
0x180024736  push    rsi
0x180024737  push    rdi
0x180024738  push    r12
0x18002473a  push    r15
0x18002473c  lea     rbp, [rsp-37h]
0x180024741  sub     rsp, 0D0h
0x180024748  mov     rax, cs:__security_cookie
0x18002474f  xor     rax, rsp
0x180024752  mov     [rbp+57h+var_30], rax
0x180024756  mov     rsi, r8
0x180024759  mov     rbx, rdx
0x18002475c  mov     rdi, rcx
0x18002475f  mov     [rbp+57h+var_B0], 0
0x180024766  xorps   xmm0, xmm0
0x180024769  movups  xmmword ptr [rbp+57h+var_AC.Data1], xmm0
0x18002476d  movups  [rbp+57h+var_9C], xmm0
0x180024771  mov     [rbp+57h+var_8C], 0
0x180024778  mov     dword ptr [rbp+57h+var_88], 0
0x18002477f  xor     eax, eax
0x180024781  movups  xmmword ptr [rbp+57h+var_68.InterfaceGuid.Data1], xmm0
0x180024785  movups  xmmword ptr [rbp+57h+var_68.UsageData.UsageInMegabytes], xmm0
0x180024789  movups  xmmword ptr [rbp+57h+var_68.InboundBandwidthInKbps], xmm0
0x18002478d  mov     qword ptr [rbp+57h+var_68.MaxTransferSizeInMegabytes], rax
0x180024791  movups  xmmword ptr [rbp+57h+var_78.Data1], xmm0
0x180024795  lea     r15, WPP_GLOBAL_Control
0x18002479c  lea     r12, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x1800247a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800247aa  cmp     rcx, r15
0x1800247ad  jz      short loc_1800247CD
0x1800247af  test    byte ptr [rcx+1Ch], 8
0x1800247b3  jz      short loc_1800247CD
0x1800247b5  mov     edx, 8Ah
0x1800247ba  mov     r8, r12
0x1800247bd  mov     rcx, [rcx+10h]
0x1800247c1  call    WPP_SF_
0x1800247c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800247cd  test    rsi, rsi
0x1800247d0  jnz     short loc_1800247F4
0x1800247d2  mov     ebx, 80004003h
0x1800247d7  cmp     rcx, r15
0x1800247da  jz      loc_180024A05
0x1800247e0  test    byte ptr [rcx+1Ch], 1
0x1800247e4  jz      loc_180024A05
0x1800247ea  mov     edx, 8Bh
0x1800247ef  jmp     loc_1800249F6
0x1800247f4  mov     dword ptr [rsi], 0
0x1800247fa  lea     rax, [rbp+57h+var_B0]
0x1800247fe  mov     [rsp+0F0h+var_C8], rax; struct INTERFACE_STACK *
0x180024803  mov     dword ptr [rsp+0F0h+var_D0], 0; int
0x18002480b  xor     r9d, r9d; struct ADDRESS_INTERFACE_DATA *
0x18002480e  lea     r8, [rbp+57h+var_78]; struct _GUID *
0x180024812  mov     rdx, rbx; struct sockaddr_storage *
0x180024815  mov     rcx, rdi; this
0x180024818  call    ?GetInterfaceStackPerDestination@PublicNetworkListManager@@AEAAJPEAUsockaddr_storage@@PEBU_GUID@@PEAUADDRESS_INTERFACE_DATA@@HPEAUINTERFACE_STACK@@@Z; PublicNetworkListManager::GetInterfaceStackPerDestination(sockaddr_storage *,_GUID const *,ADDRESS_INTERFACE_DATA *,int,INTERFACE_STACK *)
0x18002481d  mov     ebx, eax
0x18002481f  test    eax, eax
0x180024821  js      loc_1800248EE
0x180024827  mov     [rbp+57h+var_88], 0
0x18002482f  lea     rcx, [rdi+80h]
0x180024836  mov     rax, [rcx]
0x180024839  lea     rdx, [rbp+57h+var_88]
0x18002483d  mov     rax, [rax+48h]
0x180024841  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024846  mov     ebx, eax
0x180024848  test    eax, eax
0x18002484a  js      short loc_1800248A5
0x18002484c  mov     ecx, [rbp+57h+var_B0]
0x18002484f  shl     rcx, 2; cb
0x180024853  call    cs:__imp_CoTaskMemAlloc
0x180024859  mov     rdi, rax
0x18002485c  test    rax, rax
0x18002485f  jz      short loc_18002489E
0x180024861  mov     [rsp+0F0h+var_C0], 0; void *
0x18002486a  mov     [rsp+0F0h+var_C8], 0; struct NLM_DATAPLAN_STATUS *
0x180024873  mov     [rsp+0F0h+var_D0], rax; unsigned int *
0x180024878  lea     r9, [rbp+57h+var_AC]; struct _GUID *
0x18002487c  mov     r8d, [rbp+57h+var_B0]; unsigned int
0x180024880  mov     rdx, [rbp+57h+var_88]; struct IEnumNetworkConnections *
0x180024884  call    ?GetInterfaceCostAndDataPlanStatus@PublicNetworkListManager@@AEAAJPEAUIEnumNetworkConnections@@IPEAU_GUID@@PEAKPEAUNLM_DATAPLAN_STATUS@@PEAH@Z; PublicNetworkListManager::GetInterfaceCostAndDataPlanStatus(IEnumNetworkConnections *,uint,_GUID *,ulong *,NLM_DATAPLAN_STATUS *,int *)
0x180024889  mov     ebx, eax
0x18002488b  test    eax, eax
0x18002488d  js      short loc_1800248CE
0x18002488f  mov     rdx, rdi; unsigned int *
0x180024892  mov     ecx, [rbp+57h+var_B0]; unsigned int
0x180024895  call    ?DERIVE_COST_FROM_COST_ARRAY@@YAKIPEBK@Z; DERIVE_COST_FROM_COST_ARRAY(uint,ulong const *)
0x18002489a  mov     [rsi], eax
0x18002489c  jmp     short loc_1800248CE
0x18002489e  mov     ebx, 8007000Eh
0x1800248a3  jmp     short loc_1800248CE
0x1800248a5  xor     edi, edi
0x1800248a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800248ae  cmp     rcx, r15
0x1800248b1  jz      short loc_1800248CE
0x1800248b3  test    byte ptr [rcx+1Ch], 1
0x1800248b7  jz      short loc_1800248CE
0x1800248b9  mov     edx, 8Ch
0x1800248be  mov     r9d, eax
0x1800248c1  mov     r8, r12
0x1800248c4  mov     rcx, [rcx+10h]
0x1800248c8  call    WPP_SF_d
0x1800248cd  nop
0x1800248ce  lea     rcx, [rbp+57h+var_88]
0x1800248d2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800248d7  test    rdi, rdi
0x1800248da  jz      loc_1800249DF
0x1800248e0  mov     rcx, rdi; pv
0x1800248e3  call    cs:__imp_CoTaskMemFree
0x1800248e9  jmp     loc_1800249DF
0x1800248ee  cmp     eax, 80070002h
0x1800248f3  jnz     loc_1800249B9
0x1800248f9  mov     [rbp+57h+var_80], 0
0x180024901  lea     rcx, [rdi+80h]
0x180024908  mov     rax, [rcx]
0x18002490b  lea     rdx, [rbp+57h+var_80]
0x18002490f  mov     rax, [rax+48h]
0x180024913  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024918  mov     ebx, eax
0x18002491a  mov     rcx, cs:WPP_GLOBAL_Control
0x180024921  cmp     rcx, r15
0x180024924  jz      short loc_180024947
0x180024926  test    byte ptr [rcx+1Ch], 4
0x18002492a  jz      short loc_180024947
0x18002492c  mov     edx, 8Dh
0x180024931  mov     r9d, eax
0x180024934  mov     r8, r12
0x180024937  mov     rcx, [rcx+10h]
0x18002493b  call    WPP_SF_d
0x180024940  mov     rcx, cs:WPP_GLOBAL_Control; this
0x180024947  test    ebx, ebx
0x180024949  js      short loc_18002498E
0x18002494b  lea     rax, [rbp+57h+var_68]
0x18002494f  mov     [rsp+0F0h+var_D0], rax; struct NLM_DATAPLAN_STATUS *
0x180024954  lea     r9, [rbp+57h+var_88]; unsigned int *
0x180024958  lea     r8, [rbp+57h+var_B0]; struct INTERFACE_STACK *
0x18002495c  mov     rdx, [rbp+57h+var_80]; struct IEnumNetworkConnections *
0x180024960  call    ?ClientHandleUnderminedDestinationCost@PublicNetworkListManager@@AEAAJPEAUIEnumNetworkConnections@@PEAUINTERFACE_STACK@@PEAKPEAUNLM_DATAPLAN_STATUS@@@Z; PublicNetworkListManager::ClientHandleUnderminedDestinationCost(IEnumNetworkConnections *,INTERFACE_STACK *,ulong *,NLM_DATAPLAN_STATUS *)
0x180024965  mov     ebx, eax
0x180024967  test    eax, eax
0x180024969  js      short loc_180024972
0x18002496b  mov     eax, dword ptr [rbp+57h+var_88]
0x18002496e  mov     [rsi], eax
0x180024970  jmp     short loc_1800249AE
0x180024972  mov     rcx, cs:WPP_GLOBAL_Control
0x180024979  cmp     rcx, r15
0x18002497c  jz      short loc_1800249AE
0x18002497e  test    byte ptr [rcx+1Ch], 1
0x180024982  jz      short loc_1800249AE
0x180024984  mov     edx, 8Eh
0x180024989  mov     r9d, eax
0x18002498c  jmp     short loc_1800249A1
0x18002498e  cmp     rcx, r15
0x180024991  jz      short loc_1800249AE
0x180024993  test    byte ptr [rcx+1Ch], 1
0x180024997  jz      short loc_1800249AE
0x180024999  mov     edx, 8Fh
0x18002499e  mov     r9d, ebx
0x1800249a1  mov     r8, r12
0x1800249a4  mov     rcx, [rcx+10h]
0x1800249a8  call    WPP_SF_d
0x1800249ad  nop
0x1800249ae  lea     rcx, [rbp+57h+var_80]
0x1800249b2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800249b7  jmp     short loc_1800249DF
0x1800249b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800249c0  cmp     rcx, r15
0x1800249c3  jz      short loc_180024A05
0x1800249c5  test    byte ptr [rcx+1Ch], 1
0x1800249c9  jz      short loc_1800249E6
0x1800249cb  mov     edx, 90h
0x1800249d0  mov     r9d, eax
0x1800249d3  mov     r8, r12
0x1800249d6  mov     rcx, [rcx+10h]
0x1800249da  call    WPP_SF_d
0x1800249df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800249e6  cmp     rcx, r15
0x1800249e9  jz      short loc_180024A05
0x1800249eb  test    byte ptr [rcx+1Ch], 8
0x1800249ef  jz      short loc_180024A05
0x1800249f1  mov     edx, 91h
0x1800249f6  mov     r9d, ebx
0x1800249f9  mov     r8, r12
0x1800249fc  mov     rcx, [rcx+10h]
0x180024a00  call    WPP_SF_d
0x180024a05  mov     eax, ebx
0x180024a07  mov     rcx, [rbp+57h+var_30]
0x180024a0b  xor     rcx, rsp; StackCookie
0x180024a0e  call    __security_check_cookie
0x180024a13  mov     rbx, [rsp+0F0h+arg_18]
0x180024a1b  add     rsp, 0D0h
0x180024a22  pop     r15
0x180024a24  pop     r12
0x180024a26  pop     rdi
0x180024a27  pop     rsi
0x180024a28  pop     rbp
0x180024a29  retn
```
