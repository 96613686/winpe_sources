# PublicNetworkListManager::GetDataPlanStatusPerDestination(sockaddr_storage *,NLM_DATAPLAN_STATUS *)

- ea: `0x180025390`
- end: `0x1800256ac`
- name: `?GetDataPlanStatusPerDestination@PublicNetworkListManager@@AEAAJPEAUsockaddr_storage@@PEAUNLM_DATAPLAN_STATUS@@@Z`
- size: `796`
- prototype: `__int64 __fastcall(PublicNetworkListManager *__hidden this, struct sockaddr_storage *, struct NLM_DATAPLAN_STATUS *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800251b0`

## callees

- `0x180006770`
- `0x180006810`
- `0x1800086b0`
- `0x18000ad84`
- `0x1800120d0`
- `0x1800210b0`
- `0x180025390`
- `0x1800256b4`
- `0x180025b74`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025552`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025552`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800254c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800254c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PublicNetworkListManager::GetDataPlanStatusPerDestination(
        PublicNetworkListManager *this,
        struct sockaddr *a2,
        struct NLM_DATAPLAN_STATUS *a3)
{
  PVOID *v6; // rcx
  unsigned int InterfaceCostAndDataPlanStatus; // ebx
  __int64 v8; // rdx
  int InterfaceStackPerDestination; // eax
  int v10; // eax
  struct NLM_DATAPLAN_STATUS *v11; // rax
  PublicNetworkListManager *v12; // rcx
  struct NLM_DATAPLAN_STATUS *v13; // rsi
  unsigned int v14; // eax
  PVOID *v15; // rcx
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // r9
  unsigned int v20; // [rsp+40h] [rbp-69h] BYREF
  struct _GUID v21; // [rsp+44h] [rbp-65h] BYREF
  __int128 v22; // [rsp+54h] [rbp-55h]
  int v23; // [rsp+64h] [rbp-45h]
  struct IEnumNetworkConnections *v24; // [rsp+68h] [rbp-41h] BYREF
  struct IEnumNetworkConnections *v25; // [rsp+70h] [rbp-39h] BYREF
  struct NLM_DATAPLAN_STATUS v26; // [rsp+78h] [rbp-31h] BYREF
  struct _GUID v27; // [rsp+B0h] [rbp+7h] BYREF

  v20 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  LODWORD(v24) = 0;
  memset(&v26, 0, sizeof(v26));
  v27 = 0;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 146, &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a3 )
  {
    InterfaceCostAndDataPlanStatus = -2147467261;
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 )
    {
      v8 = 147;
LABEL_41:
      WPP_SF_d(v6[2], v8, &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids, InterfaceCostAndDataPlanStatus);
      return InterfaceCostAndDataPlanStatus;
    }
    return InterfaceCostAndDataPlanStatus;
  }
  a3->InterfaceGuid = GUID_NULL;
  a3->UsageData.UsageInMegabytes = -1;
  a3->UsageData.LastSyncTime = 0;
  a3->DataLimitInMegabytes = -1;
  a3->InboundBandwidthInKbps = -1;
  a3->OutboundBandwidthInKbps = -1;
  a3->NextBillingCycle = 0;
  a3->MaxTransferSizeInMegabytes = -1;
  a3->Reserved = 0;
  InterfaceStackPerDestination = PublicNetworkListManager::GetInterfaceStackPerDestination(
                                   this,
                                   a2,
                                   &v27,
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
          148,
          &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids,
          (unsigned int)v10);
    }
    else
    {
      v11 = (struct NLM_DATAPLAN_STATUS *)CoTaskMemAlloc(56LL * v20);
      v13 = v11;
      if ( v11 )
      {
        InterfaceCostAndDataPlanStatus = PublicNetworkListManager::GetInterfaceCostAndDataPlanStatus(
                                           v12,
                                           v24,
                                           v20,
                                           &v21,
                                           0,
                                           v11,
                                           0);
        if ( (InterfaceCostAndDataPlanStatus & 0x80000000) == 0 )
          GetFirstValidDataPlanStatus(v20, v13, a3);
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 149, &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids, v14);
      v15 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( (InterfaceCostAndDataPlanStatus & 0x80000000) != 0 )
    {
      if ( v15 == &WPP_GLOBAL_Control || (*((_BYTE *)v15 + 28) & 1) == 0 )
        goto LABEL_33;
      v17 = 151;
      v18 = InterfaceCostAndDataPlanStatus;
    }
    else
    {
      v16 = PublicNetworkListManager::ClientHandleUnderminedDestinationCost(
              (PublicNetworkListManager *)v15,
              v25,
              (struct INTERFACE_STACK *)&v20,
              (unsigned int *)&v24,
              &v26);
      InterfaceCostAndDataPlanStatus = v16;
      if ( v16 >= 0 )
      {
        *a3 = v26;
LABEL_33:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v25);
        goto LABEL_37;
      }
      v15 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_33;
      v17 = 150;
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
    152,
    &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids,
    (unsigned int)InterfaceStackPerDestination);
LABEL_37:
  v6 = (PVOID *)WPP_GLOBAL_Control;
LABEL_38:
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
  {
    v8 = 153;
    goto LABEL_41;
  }
  return InterfaceCostAndDataPlanStatus;
}

```

## disassembly

```asm
0x180025390  push    rbp
0x180025392  push    rbx
0x180025393  push    rsi
0x180025394  push    rdi
0x180025395  push    r12
0x180025397  push    r14
0x180025399  push    r15
0x18002539b  lea     rbp, [rsp-27h]
0x1800253a0  sub     rsp, 0D0h
0x1800253a7  mov     rax, cs:__security_cookie
0x1800253ae  xor     rax, rsp
0x1800253b1  mov     [rbp+57h+var_40], rax
0x1800253b5  mov     rdi, r8
0x1800253b8  mov     rbx, rdx
0x1800253bb  mov     rsi, rcx
0x1800253be  xor     r14d, r14d
0x1800253c1  mov     [rbp+57h+var_C0], r14d
0x1800253c5  xorps   xmm0, xmm0
0x1800253c8  movups  xmmword ptr [rbp+57h+var_BC.Data1], xmm0
0x1800253cc  movups  [rbp+57h+var_AC], xmm0
0x1800253d0  mov     [rbp+57h+var_9C], r14d
0x1800253d4  mov     dword ptr [rbp+57h+var_98], r14d
0x1800253d8  xor     eax, eax
0x1800253da  movups  xmmword ptr [rbp+57h+var_88.InterfaceGuid.Data1], xmm0
0x1800253de  movups  xmmword ptr [rbp+57h+var_88.UsageData.UsageInMegabytes], xmm0
0x1800253e2  movups  xmmword ptr [rbp+57h+var_88.InboundBandwidthInKbps], xmm0
0x1800253e6  mov     qword ptr [rbp+57h+var_88.MaxTransferSizeInMegabytes], rax
0x1800253ea  movups  xmmword ptr [rbp+57h+var_50.Data1], xmm0
0x1800253ee  lea     r15, WPP_GLOBAL_Control
0x1800253f5  lea     r12, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x1800253fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180025403  cmp     rcx, r15
0x180025406  jz      short loc_180025426
0x180025408  test    byte ptr [rcx+1Ch], 8
0x18002540c  jz      short loc_180025426
0x18002540e  mov     edx, 92h
0x180025413  mov     r8, r12
0x180025416  mov     rcx, [rcx+10h]
0x18002541a  call    WPP_SF_
0x18002541f  mov     rcx, cs:WPP_GLOBAL_Control
0x180025426  test    rdi, rdi
0x180025429  jnz     short loc_18002544D
0x18002542b  mov     ebx, 80004003h
0x180025430  cmp     rcx, r15
0x180025433  jz      loc_18002568C
0x180025439  test    byte ptr [rcx+1Ch], 1
0x18002543d  jz      loc_18002568C
0x180025443  mov     edx, 93h
0x180025448  jmp     loc_18002567D
0x18002544d  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180025454  movdqu  xmmword ptr [rdi], xmm0
0x180025458  or      eax, 0FFFFFFFFh
0x18002545b  mov     [rdi+10h], eax
0x18002545e  mov     [rdi+14h], r14
0x180025462  mov     [rdi+1Ch], eax
0x180025465  mov     [rdi+20h], eax
0x180025468  mov     [rdi+24h], eax
0x18002546b  mov     [rdi+28h], r14
0x18002546f  mov     [rdi+30h], eax
0x180025472  mov     [rdi+34h], r14d
0x180025476  lea     rax, [rbp+57h+var_C0]
0x18002547a  mov     [rsp+100h+var_D8], rax; struct INTERFACE_STACK *
0x18002547f  mov     dword ptr [rsp+100h+var_E0], r14d; int
0x180025484  xor     r9d, r9d; struct ADDRESS_INTERFACE_DATA *
0x180025487  lea     r8, [rbp+57h+var_50]; struct _GUID *
0x18002548b  mov     rdx, rbx; struct sockaddr_storage *
0x18002548e  mov     rcx, rsi; this
0x180025491  call    ?GetInterfaceStackPerDestination@PublicNetworkListManager@@AEAAJPEAUsockaddr_storage@@PEBU_GUID@@PEAUADDRESS_INTERFACE_DATA@@HPEAUINTERFACE_STACK@@@Z; PublicNetworkListManager::GetInterfaceStackPerDestination(sockaddr_storage *,_GUID const *,ADDRESS_INTERFACE_DATA *,int,INTERFACE_STACK *)
0x180025496  mov     ebx, eax
0x180025498  test    eax, eax
0x18002549a  js      loc_18002555D
0x1800254a0  mov     [rbp+57h+var_98], r14
0x1800254a4  lea     rcx, [rsi+80h]
0x1800254ab  mov     rax, [rcx]
0x1800254ae  lea     rdx, [rbp+57h+var_98]
0x1800254b2  mov     rax, [rax+48h]
0x1800254b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800254bb  mov     ebx, eax
0x1800254bd  test    eax, eax
0x1800254bf  js      short loc_180025513
0x1800254c1  mov     eax, [rbp+57h+var_C0]
0x1800254c4  imul    rcx, rax, 38h ; '8'; cb
0x1800254c8  call    cs:__imp_CoTaskMemAlloc
0x1800254ce  mov     rsi, rax
0x1800254d1  test    rax, rax
0x1800254d4  jz      short loc_18002550C
0x1800254d6  mov     [rsp+100h+var_D0], r14; void *
0x1800254db  mov     [rsp+100h+var_D8], rax; struct NLM_DATAPLAN_STATUS *
0x1800254e0  mov     [rsp+100h+var_E0], r14; unsigned int *
0x1800254e5  lea     r9, [rbp+57h+var_BC]; struct _GUID *
0x1800254e9  mov     r8d, [rbp+57h+var_C0]; unsigned int
0x1800254ed  mov     rdx, [rbp+57h+var_98]; struct IEnumNetworkConnections *
0x1800254f1  call    ?GetInterfaceCostAndDataPlanStatus@PublicNetworkListManager@@AEAAJPEAUIEnumNetworkConnections@@IPEAU_GUID@@PEAKPEAUNLM_DATAPLAN_STATUS@@PEAH@Z; PublicNetworkListManager::GetInterfaceCostAndDataPlanStatus(IEnumNetworkConnections *,uint,_GUID *,ulong *,NLM_DATAPLAN_STATUS *,int *)
0x1800254f6  mov     ebx, eax
0x1800254f8  test    eax, eax
0x1800254fa  js      short loc_18002553D
0x1800254fc  mov     r8, rdi; struct NLM_DATAPLAN_STATUS *
0x1800254ff  mov     rdx, rsi; struct NLM_DATAPLAN_STATUS *
0x180025502  mov     ecx, [rbp+57h+var_C0]; unsigned int
0x180025505  call    ?GetFirstValidDataPlanStatus@@YAXIPEAUNLM_DATAPLAN_STATUS@@0@Z; GetFirstValidDataPlanStatus(uint,NLM_DATAPLAN_STATUS *,NLM_DATAPLAN_STATUS *)
0x18002550a  jmp     short loc_18002553D
0x18002550c  mov     ebx, 8007000Eh
0x180025511  jmp     short loc_18002553D
0x180025513  mov     rsi, r14
0x180025516  mov     rcx, cs:WPP_GLOBAL_Control
0x18002551d  cmp     rcx, r15
0x180025520  jz      short loc_18002553D
0x180025522  test    byte ptr [rcx+1Ch], 1
0x180025526  jz      short loc_18002553D
0x180025528  mov     edx, 94h
0x18002552d  mov     r9d, eax
0x180025530  mov     r8, r12
0x180025533  mov     rcx, [rcx+10h]
0x180025537  call    WPP_SF_d
0x18002553c  nop
0x18002553d  lea     rcx, [rbp+57h+var_98]
0x180025541  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180025546  test    rsi, rsi
0x180025549  jz      loc_180025666
0x18002554f  mov     rcx, rsi; pv
0x180025552  call    cs:__imp_CoTaskMemFree
0x180025558  jmp     loc_180025666
0x18002555d  cmp     eax, 80070002h
0x180025562  jnz     loc_180025640
0x180025568  mov     [rbp+57h+var_90], r14
0x18002556c  lea     rcx, [rsi+80h]
0x180025573  mov     rax, [rcx]
0x180025576  lea     rdx, [rbp+57h+var_90]
0x18002557a  mov     rax, [rax+48h]
0x18002557e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025583  mov     ebx, eax
0x180025585  mov     rcx, cs:WPP_GLOBAL_Control
0x18002558c  cmp     rcx, r15
0x18002558f  jz      short loc_1800255B2
0x180025591  test    byte ptr [rcx+1Ch], 4
0x180025595  jz      short loc_1800255B2
0x180025597  mov     edx, 95h
0x18002559c  mov     r9d, eax
0x18002559f  mov     r8, r12
0x1800255a2  mov     rcx, [rcx+10h]
0x1800255a6  call    WPP_SF_d
0x1800255ab  mov     rcx, cs:WPP_GLOBAL_Control; this
0x1800255b2  test    ebx, ebx
0x1800255b4  js      short loc_180025615
0x1800255b6  lea     rax, [rbp+57h+var_88]
0x1800255ba  mov     [rsp+100h+var_E0], rax; struct NLM_DATAPLAN_STATUS *
0x1800255bf  lea     r9, [rbp+57h+var_98]; unsigned int *
0x1800255c3  lea     r8, [rbp+57h+var_C0]; struct INTERFACE_STACK *
0x1800255c7  mov     rdx, [rbp+57h+var_90]; struct IEnumNetworkConnections *
0x1800255cb  call    ?ClientHandleUnderminedDestinationCost@PublicNetworkListManager@@AEAAJPEAUIEnumNetworkConnections@@PEAUINTERFACE_STACK@@PEAKPEAUNLM_DATAPLAN_STATUS@@@Z; PublicNetworkListManager::ClientHandleUnderminedDestinationCost(IEnumNetworkConnections *,INTERFACE_STACK *,ulong *,NLM_DATAPLAN_STATUS *)
0x1800255d0  mov     ebx, eax
0x1800255d2  test    eax, eax
0x1800255d4  js      short loc_1800255F9
0x1800255d6  movups  xmm0, xmmword ptr [rbp+57h+var_88.InterfaceGuid.Data1]
0x1800255da  movups  xmmword ptr [rdi], xmm0
0x1800255dd  movups  xmm1, xmmword ptr [rbp+57h+var_88.UsageData.UsageInMegabytes]
0x1800255e1  movups  xmmword ptr [rdi+10h], xmm1
0x1800255e5  movups  xmm0, xmmword ptr [rbp+57h+var_88.InboundBandwidthInKbps]
0x1800255e9  movups  xmmword ptr [rdi+20h], xmm0
0x1800255ed  movsd   xmm1, qword ptr [rbp+57h+var_88.MaxTransferSizeInMegabytes]
0x1800255f2  movsd   qword ptr [rdi+30h], xmm1
0x1800255f7  jmp     short loc_180025635
0x1800255f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180025600  cmp     rcx, r15
0x180025603  jz      short loc_180025635
0x180025605  test    byte ptr [rcx+1Ch], 1
0x180025609  jz      short loc_180025635
0x18002560b  mov     edx, 96h
0x180025610  mov     r9d, eax
0x180025613  jmp     short loc_180025628
0x180025615  cmp     rcx, r15
0x180025618  jz      short loc_180025635
0x18002561a  test    byte ptr [rcx+1Ch], 1
0x18002561e  jz      short loc_180025635
0x180025620  mov     edx, 97h
0x180025625  mov     r9d, ebx
0x180025628  mov     r8, r12
0x18002562b  mov     rcx, [rcx+10h]
0x18002562f  call    WPP_SF_d
0x180025634  nop
0x180025635  lea     rcx, [rbp+57h+var_90]
0x180025639  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002563e  jmp     short loc_180025666
0x180025640  mov     rcx, cs:WPP_GLOBAL_Control
0x180025647  cmp     rcx, r15
0x18002564a  jz      short loc_18002568C
0x18002564c  test    byte ptr [rcx+1Ch], 1
0x180025650  jz      short loc_18002566D
0x180025652  mov     edx, 98h
0x180025657  mov     r9d, eax
0x18002565a  mov     r8, r12
0x18002565d  mov     rcx, [rcx+10h]
0x180025661  call    WPP_SF_d
0x180025666  mov     rcx, cs:WPP_GLOBAL_Control
0x18002566d  cmp     rcx, r15
0x180025670  jz      short loc_18002568C
0x180025672  test    byte ptr [rcx+1Ch], 8
0x180025676  jz      short loc_18002568C
0x180025678  mov     edx, 99h
0x18002567d  mov     r9d, ebx
0x180025680  mov     r8, r12
0x180025683  mov     rcx, [rcx+10h]
0x180025687  call    WPP_SF_d
0x18002568c  mov     eax, ebx
0x18002568e  mov     rcx, [rbp+57h+var_40]
0x180025692  xor     rcx, rsp; StackCookie
0x180025695  call    __security_check_cookie
0x18002569a  add     rsp, 0D0h
0x1800256a1  pop     r15
0x1800256a3  pop     r14
0x1800256a5  pop     r12
0x1800256a7  pop     rdi
0x1800256a8  pop     rsi
0x1800256a9  pop     rbx
0x1800256aa  pop     rbp
0x1800256ab  retn
```
