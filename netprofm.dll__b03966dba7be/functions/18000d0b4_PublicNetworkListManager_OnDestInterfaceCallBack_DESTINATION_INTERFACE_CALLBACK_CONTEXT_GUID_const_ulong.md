# PublicNetworkListManager::OnDestInterfaceCallBack(DESTINATION_INTERFACE_CALLBACK_CONTEXT *,_GUID const *,ulong)

- ea: `0x18000d0b4`
- end: `0x18000d586`
- name: `?OnDestInterfaceCallBack@PublicNetworkListManager@@QEAAXPEAUDESTINATION_INTERFACE_CALLBACK_CONTEXT@@PEBU_GUID@@K@Z`
- size: `1234`
- prototype: `void __fastcall(PublicNetworkListManager *__hidden this, struct DESTINATION_INTERFACE_CALLBACK_CONTEXT *, const struct _GUID *, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d070`

## callees

- `0x180006810`
- `0x1800086b0`
- `0x180009d28`
- `0x18000a894`
- `0x18000ad84`
- `0x18000d0b4`
- `0x1800120d0`
- `0x180013fa1`
- `0x1800210b0`
- `0x1800256b4`
- `0x180028738`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d49f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d49f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d1ac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d1ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d541`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d54f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d541`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d54f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d2a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d2bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d2a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d2bc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall PublicNetworkListManager::OnDestInterfaceCallBack(
        PublicNetworkListManager *this,
        struct DESTINATION_INTERFACE_CALLBACK_CONTEXT *a2,
        const struct _GUID *a3,
        unsigned int a4)
{
  unsigned int v6; // r12d
  unsigned int v7; // r14d
  int v8; // eax
  unsigned int *v9; // r13
  struct NLM_DATAPLAN_STATUS *v10; // r15
  _QWORD *v11; // rdx
  _QWORD *i; // rax
  __int64 v13; // rbx
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rcx
  struct NLM_DATAPLAN_STATUS *v17; // rax
  PublicNetworkListManager *v18; // rcx
  int InterfaceCostAndDataPlanStatus; // eax
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // r9
  unsigned int v23; // ecx
  int v24; // eax
  __int64 v25; // r8
  PublicNetworkListManager *v26; // rsi
  unsigned int v27; // [rsp+44h] [rbp-BCh] BYREF
  int v28; // [rsp+48h] [rbp-B8h]
  unsigned int v29; // [rsp+4Ch] [rbp-B4h]
  PublicNetworkListManager *v30; // [rsp+50h] [rbp-B0h]
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+60h] [rbp-A0h] BYREF
  const struct _GUID *v32; // [rsp+70h] [rbp-90h]
  _BYTE v33[40]; // [rsp+78h] [rbp-88h] BYREF
  __int128 Buf1; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v35; // [rsp+B0h] [rbp-50h]
  __int128 v36; // [rsp+C0h] [rbp-40h]
  __int64 v37; // [rsp+D0h] [rbp-30h]
  struct IEnumNetworkConnections *v38; // [rsp+D8h] [rbp-28h] BYREF
  struct NLM_DATAPLAN_STATUS Buf2; // [rsp+E0h] [rbp-20h] BYREF

  v29 = a4;
  v32 = a3;
  v30 = this;
  v6 = 0;
  v7 = 0;
  v27 = 0;
  Buf1 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  memset(&Buf2, 0, sizeof(Buf2));
  memset(v33, 0, sizeof(v33));
  v38 = 0;
  v8 = (*(__int64 (__fastcall **)(char *, struct IEnumNetworkConnections **))(*((_QWORD *)this + 16) + 72LL))(
         (char *)this + 128,
         &v38);
  if ( v8 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        168,
        &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids,
        (unsigned int)v8);
    goto LABEL_50;
  }
  v9 = 0;
  v10 = 0;
  v28 = 0;
  lpCriticalSection[0] = (LPCRITICAL_SECTION)((char *)this + 560);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 14);
  v11 = (_QWORD *)*((_QWORD *)this + 75);
  for ( i = (_QWORD *)*v11; ; i = (_QWORD *)*i )
  {
    if ( i == v11 )
      goto LABEL_38;
    v13 = i[2];
    if ( *(_QWORD *)a2 == *(_QWORD *)(v13 + 248)
      && *((_QWORD *)a2 + 1) == *(_QWORD *)(v13 + 256)
      && *((_QWORD *)a2 + 2) == *(_QWORD *)v13 )
    {
      v14 = *((_QWORD *)a2 + 3);
      if ( v14 == *(_QWORD *)(v13 + 8) )
        break;
    }
  }
  v6 = *(_DWORD *)(v13 + 184);
  Buf1 = *(_OWORD *)(v13 + 188);
  v35 = *(_OWORD *)(v13 + 204);
  v36 = *(_OWORD *)(v13 + 220);
  v37 = *(_QWORD *)(v13 + 236);
  if ( v29 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      v14 = 2;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 171, &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids, v29);
    }
    v24 = PublicNetworkListManager::ClientHandleUnderminedDestinationCost(
            (PublicNetworkListManager *)v14,
            v38,
            (struct INTERFACE_STACK *)v33,
            &v27,
            &Buf2);
    if ( v24 >= 0 )
    {
      *(_OWORD *)(v13 + 144) = *(_OWORD *)v33;
      *(_OWORD *)(v13 + 160) = *(_OWORD *)&v33[16];
      *(_QWORD *)(v13 + 176) = *(_QWORD *)&v33[32];
      v7 = v27;
      *(_DWORD *)(v13 + 184) = v27;
      *(struct NLM_DATAPLAN_STATUS *)(v13 + 188) = Buf2;
      v28 = 1;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          172,
          &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids,
          (unsigned int)v24);
      v7 = v27;
    }
  }
  else
  {
    *(_DWORD *)(v13 + 144) = 1;
    *(_OWORD *)(v13 + 148) = *(_OWORD *)((char *)a2 + 36);
    v15 = *(_QWORD *)&v32->Data1 - *(_QWORD *)(v13 + 148);
    if ( *(_QWORD *)&v32->Data1 == *(_QWORD *)(v13 + 148) )
      v15 = *(_QWORD *)v32->Data4 - *(_QWORD *)(v13 + 156);
    v16 = 1;
    if ( v15 )
    {
      *(struct _GUID *)(v13 + 164) = *v32;
      v16 = 2;
      *(_DWORD *)(v13 + 144) = 2;
    }
    *(_DWORD *)(v13 + 180) = 1;
    v9 = (unsigned int *)CoTaskMemAlloc(4 * v16);
    v17 = (struct NLM_DATAPLAN_STATUS *)CoTaskMemAlloc(56LL * *(unsigned int *)(v13 + 144));
    v10 = v17;
    if ( v9 && v17 )
    {
      InterfaceCostAndDataPlanStatus = PublicNetworkListManager::GetInterfaceCostAndDataPlanStatus(
                                         v18,
                                         v38,
                                         *(_DWORD *)(v13 + 144),
                                         (struct _GUID *)(v13 + 148),
                                         v9,
                                         v17,
                                         0);
      if ( InterfaceCostAndDataPlanStatus >= 0 )
      {
        v7 = DERIVE_COST_FROM_COST_ARRAY(*(_DWORD *)(v13 + 144), v9);
        GetFirstValidDataPlanStatus(v23, v10, &Buf2);
        *(_DWORD *)(v13 + 184) = v7;
        *(struct NLM_DATAPLAN_STATUS *)(v13 + 188) = Buf2;
        v28 = 1;
      }
      else
      {
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v21 = 170;
          v22 = (unsigned int)InterfaceCostAndDataPlanStatus;
LABEL_23:
          WPP_SF_d(v20[2], v21, &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids, v22);
        }
      }
    }
    else
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v21 = 169;
        v22 = 2147942414LL;
        goto LABEL_23;
      }
    }
  }
LABEL_38:
  LeaveCriticalSection(lpCriticalSection[0]);
  if ( v28 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 173, v25, v6, v7);
    v26 = v30;
    if ( v6 != v7 )
    {
      *(_OWORD *)lpCriticalSection = *((_OWORD *)a2 + 1);
      PublicNetworkListManager::PostNetworkCostManagerEvent(v30, (struct _GUID *)lpCriticalSection, 0x801u, v7);
    }
    if ( memcmp_0(&Buf1, &Buf2, 0x38u) )
    {
      *(_OWORD *)lpCriticalSection = *((_OWORD *)a2 + 1);
      PublicNetworkListManager::PostNetworkCostManagerEvent(v26, (struct _GUID *)lpCriticalSection, 0x802u, 0);
    }
  }
  if ( v9 )
    CoTaskMemFree(v9);
  if ( v10 )
    CoTaskMemFree(v10);
LABEL_50:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v38);
}

```

## disassembly

```asm
0x18000d0b4  mov     [rsp-8+arg_8], rbx
0x18000d0b9  push    rbp
0x18000d0ba  push    rsi
0x18000d0bb  push    rdi
0x18000d0bc  push    r12
0x18000d0be  push    r13
0x18000d0c0  push    r14
0x18000d0c2  push    r15
0x18000d0c4  lea     rbp, [rsp-20h]
0x18000d0c9  sub     rsp, 120h
0x18000d0d0  mov     rax, cs:__security_cookie
0x18000d0d7  xor     rax, rsp
0x18000d0da  mov     [rbp+50h+var_38], rax
0x18000d0de  mov     [rsp+150h+var_104], r9d
0x18000d0e3  mov     [rsp+150h+var_E0], r8
0x18000d0e8  mov     rdi, rdx
0x18000d0eb  mov     rbx, rcx
0x18000d0ee  mov     [rsp+150h+var_100], rcx
0x18000d0f3  xor     r12d, r12d
0x18000d0f6  mov     r14d, r12d
0x18000d0f9  mov     [rsp+150h+var_10C], r12d
0x18000d0fe  xorps   xmm0, xmm0
0x18000d101  xor     eax, eax
0x18000d103  movups  [rbp+50h+Buf1], xmm0
0x18000d107  movups  [rbp+50h+var_A0], xmm0
0x18000d10b  movups  [rbp+50h+var_90], xmm0
0x18000d10f  mov     [rbp+50h+var_80], rax
0x18000d113  xorps   xmm1, xmm1
0x18000d116  movups  [rbp+50h+Buf2], xmm1
0x18000d11a  movups  [rbp+50h+var_60], xmm1
0x18000d11e  movups  [rbp+50h+var_50], xmm1
0x18000d122  mov     [rbp+50h+var_40], rax
0x18000d126  mov     dword ptr [rsp+150h+var_D8], r12d
0x18000d12b  movups  [rsp+150h+var_D8+4], xmm0
0x18000d130  movups  [rbp+50h+var_C4], xmm0
0x18000d134  mov     [rbp+50h+var_B4], r12d
0x18000d138  mov     [rbp+50h+var_78], r12
0x18000d13c  sub     rcx, 0FFFFFFFFFFFFFF80h
0x18000d140  mov     rax, [rcx]
0x18000d143  lea     rdx, [rbp+50h+var_78]
0x18000d147  mov     rax, [rax+48h]
0x18000d14b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d150  test    eax, eax
0x18000d152  jns     short loc_18000D192
0x18000d154  lea     rsi, WPP_GLOBAL_Control
0x18000d15b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d162  cmp     rcx, rsi
0x18000d165  jz      loc_18000D556
0x18000d16b  test    byte ptr [rcx+1Ch], 1
0x18000d16f  jz      loc_18000D556
0x18000d175  mov     edx, 0A8h
0x18000d17a  mov     r9d, eax
0x18000d17d  lea     r8, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x18000d184  mov     rcx, [rcx+10h]
0x18000d188  call    WPP_SF_d
0x18000d18d  jmp     loc_18000D556
0x18000d192  mov     r13, r12
0x18000d195  mov     r15, r12
0x18000d198  mov     [rsp+150h+var_108], r12d
0x18000d19d  lea     rax, [rbx+230h]
0x18000d1a4  mov     [rsp+150h+lpCriticalSection], rax
0x18000d1a9  mov     rcx, rax; lpCriticalSection
0x18000d1ac  call    cs:__imp_EnterCriticalSection
0x18000d1b2  mov     rdx, [rbx+258h]
0x18000d1b9  mov     rax, [rdx]
0x18000d1bc  lea     rsi, WPP_GLOBAL_Control
0x18000d1c3  cmp     rax, rdx
0x18000d1c6  jz      loc_18000D495
0x18000d1cc  mov     rbx, [rax+10h]
0x18000d1d0  mov     rcx, [rdi]
0x18000d1d3  cmp     rcx, [rbx+0F8h]
0x18000d1da  jnz     short loc_18000D1FC
0x18000d1dc  mov     rcx, [rdi+8]
0x18000d1e0  cmp     rcx, [rbx+100h]
0x18000d1e7  jnz     short loc_18000D1FC
0x18000d1e9  mov     rcx, [rdi+10h]
0x18000d1ed  cmp     rcx, [rbx]
0x18000d1f0  jnz     short loc_18000D1FC
0x18000d1f2  mov     rcx, [rdi+18h]
0x18000d1f6  cmp     rcx, [rbx+8]
0x18000d1fa  jz      short loc_18000D201
0x18000d1fc  mov     rax, [rax]
0x18000d1ff  jmp     short loc_18000D1BC
0x18000d201  mov     r12d, [rbx+0B8h]
0x18000d208  mov     [rsp+150h+var_110], r12d
0x18000d20d  movups  xmm0, xmmword ptr [rbx+0BCh]
0x18000d214  movups  [rbp+50h+Buf1], xmm0
0x18000d218  movups  xmm1, xmmword ptr [rbx+0CCh]
0x18000d21f  movups  [rbp+50h+var_A0], xmm1
0x18000d223  movups  xmm0, xmmword ptr [rbx+0DCh]
0x18000d22a  movups  [rbp+50h+var_90], xmm0
0x18000d22e  movsd   xmm1, qword ptr [rbx+0ECh]
0x18000d236  movsd   [rbp+50h+var_80], xmm1
0x18000d23b  mov     r9d, [rsp+150h+var_104]
0x18000d240  test    r9d, r9d
0x18000d243  jnz     loc_18000D3B3
0x18000d249  mov     dword ptr [rbx+90h], 1
0x18000d253  lea     r12, [rbx+94h]
0x18000d25a  movups  xmm0, xmmword ptr [rdi+24h]
0x18000d25e  movdqu  xmmword ptr [r12], xmm0
0x18000d264  mov     rdx, [rsp+150h+var_E0]
0x18000d269  mov     rax, [rdx]
0x18000d26c  sub     rax, [r12]
0x18000d270  jnz     short loc_18000D27B
0x18000d272  mov     rax, [rdx+8]
0x18000d276  sub     rax, [r12+8]
0x18000d27b  mov     ecx, 1
0x18000d280  test    rax, rax
0x18000d283  jz      short loc_18000D29B
0x18000d285  movups  xmm0, xmmword ptr [rdx]
0x18000d288  movdqu  xmmword ptr [rbx+0A4h], xmm0
0x18000d290  mov     ecx, 2
0x18000d295  mov     [rbx+90h], ecx
0x18000d29b  mov     dword ptr [rbx+0B4h], 1
0x18000d2a5  shl     rcx, 2; cb
0x18000d2a9  call    cs:__imp_CoTaskMemAlloc
0x18000d2af  mov     r13, rax
0x18000d2b2  mov     eax, [rbx+90h]
0x18000d2b8  imul    rcx, rax, 38h ; '8'; cb
0x18000d2bc  call    cs:__imp_CoTaskMemAlloc
0x18000d2c2  mov     r15, rax
0x18000d2c5  test    r13, r13
0x18000d2c8  jz      loc_18000D391
0x18000d2ce  test    rax, rax
0x18000d2d1  jz      loc_18000D391
0x18000d2d7  mov     [rsp+150h+var_120], 0; void *
0x18000d2e0  mov     [rsp+150h+var_128], rax; struct NLM_DATAPLAN_STATUS *
0x18000d2e5  mov     [rsp+150h+var_130], r13; unsigned int *
0x18000d2ea  mov     r9, r12; struct _GUID *
0x18000d2ed  mov     r8d, [rbx+90h]; unsigned int
0x18000d2f4  mov     rdx, [rbp+50h+var_78]; struct IEnumNetworkConnections *
0x18000d2f8  call    ?GetInterfaceCostAndDataPlanStatus@PublicNetworkListManager@@AEAAJPEAUIEnumNetworkConnections@@IPEAU_GUID@@PEAKPEAUNLM_DATAPLAN_STATUS@@PEAH@Z; PublicNetworkListManager::GetInterfaceCostAndDataPlanStatus(IEnumNetworkConnections *,uint,_GUID *,ulong *,NLM_DATAPLAN_STATUS *,int *)
0x18000d2fd  test    eax, eax
0x18000d2ff  jns     short loc_18000D335
0x18000d301  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d308  cmp     rcx, rsi
0x18000d30b  jz      short loc_18000D32B
0x18000d30d  test    byte ptr [rcx+1Ch], 1
0x18000d311  jz      short loc_18000D32B
0x18000d313  mov     edx, 0AAh
0x18000d318  mov     r9d, eax
0x18000d31b  lea     r8, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x18000d322  mov     rcx, [rcx+10h]
0x18000d326  call    WPP_SF_d
0x18000d32b  mov     r12d, [rsp+150h+var_110]
0x18000d330  jmp     loc_18000D495
0x18000d335  mov     ecx, [rbx+90h]; unsigned int
0x18000d33b  mov     rdx, r13; unsigned int *
0x18000d33e  call    ?DERIVE_COST_FROM_COST_ARRAY@@YAKIPEBK@Z; DERIVE_COST_FROM_COST_ARRAY(uint,ulong const *)
0x18000d343  mov     r14d, eax
0x18000d346  lea     r8, [rbp+50h+Buf2]; struct NLM_DATAPLAN_STATUS *
0x18000d34a  mov     rdx, r15; struct NLM_DATAPLAN_STATUS *
0x18000d34d  call    ?GetFirstValidDataPlanStatus@@YAXIPEAUNLM_DATAPLAN_STATUS@@0@Z; GetFirstValidDataPlanStatus(uint,NLM_DATAPLAN_STATUS *,NLM_DATAPLAN_STATUS *)
0x18000d352  mov     [rbx+0B8h], r14d
0x18000d359  movups  xmm0, [rbp+50h+Buf2]
0x18000d35d  movups  xmmword ptr [rbx+0BCh], xmm0
0x18000d364  movups  xmm1, [rbp+50h+var_60]
0x18000d368  movups  xmmword ptr [rbx+0CCh], xmm1
0x18000d36f  movups  xmm0, [rbp+50h+var_50]
0x18000d373  movups  xmmword ptr [rbx+0DCh], xmm0
0x18000d37a  movsd   xmm1, [rbp+50h+var_40]
0x18000d37f  movsd   qword ptr [rbx+0ECh], xmm1
0x18000d387  mov     [rsp+150h+var_108], 1
0x18000d38f  jmp     short loc_18000D32B
0x18000d391  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d398  cmp     rcx, rsi
0x18000d39b  jz      short loc_18000D32B
0x18000d39d  test    byte ptr [rcx+1Ch], 1
0x18000d3a1  jz      short loc_18000D32B
0x18000d3a3  mov     edx, 0A9h
0x18000d3a8  mov     r9d, 8007000Eh
0x18000d3ae  jmp     loc_18000D31B
0x18000d3b3  mov     rax, cs:WPP_GLOBAL_Control
0x18000d3ba  cmp     rax, rsi
0x18000d3bd  jz      short loc_18000D3DE
0x18000d3bf  mov     ecx, 2
0x18000d3c4  test    [rax+1Ch], cl
0x18000d3c7  jz      short loc_18000D3DE
0x18000d3c9  mov     edx, 0ABh
0x18000d3ce  lea     r8, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x18000d3d5  mov     rcx, [rax+10h]
0x18000d3d9  call    WPP_SF_d
0x18000d3de  lea     rax, [rbp+50h+Buf2]
0x18000d3e2  mov     [rsp+150h+var_130], rax; struct NLM_DATAPLAN_STATUS *
0x18000d3e7  lea     r9, [rsp+150h+var_10C]; unsigned int *
0x18000d3ec  lea     r8, [rsp+150h+var_D8]; struct INTERFACE_STACK *
0x18000d3f1  mov     rdx, [rbp+50h+var_78]; struct IEnumNetworkConnections *
0x18000d3f5  call    ?ClientHandleUnderminedDestinationCost@PublicNetworkListManager@@AEAAJPEAUIEnumNetworkConnections@@PEAUINTERFACE_STACK@@PEAKPEAUNLM_DATAPLAN_STATUS@@@Z; PublicNetworkListManager::ClientHandleUnderminedDestinationCost(IEnumNetworkConnections *,INTERFACE_STACK *,ulong *,NLM_DATAPLAN_STATUS *)
0x18000d3fa  test    eax, eax
0x18000d3fc  jns     short loc_18000D42F
0x18000d3fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d405  cmp     rcx, rsi
0x18000d408  jz      short loc_18000D428
0x18000d40a  test    byte ptr [rcx+1Ch], 1
0x18000d40e  jz      short loc_18000D428
0x18000d410  mov     edx, 0ACh
0x18000d415  mov     r9d, eax
0x18000d418  lea     r8, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x18000d41f  mov     rcx, [rcx+10h]
0x18000d423  call    WPP_SF_d
0x18000d428  mov     r14d, [rsp+150h+var_10C]
0x18000d42d  jmp     short loc_18000D495
0x18000d42f  movups  xmm0, [rsp+150h+var_D8]
0x18000d434  movups  xmmword ptr [rbx+90h], xmm0
0x18000d43b  movups  xmm1, xmmword ptr [rbp-78h]
0x18000d43f  movups  xmmword ptr [rbx+0A0h], xmm1
0x18000d446  movsd   xmm0, qword ptr [rbp+50h+var_C4+0Ch]
0x18000d44b  movsd   qword ptr [rbx+0B0h], xmm0
0x18000d453  mov     r14d, [rsp+150h+var_10C]
0x18000d458  mov     [rbx+0B8h], r14d
0x18000d45f  movups  xmm0, [rbp+50h+Buf2]
0x18000d463  movups  xmmword ptr [rbx+0BCh], xmm0
0x18000d46a  movups  xmm1, [rbp+50h+var_60]
0x18000d46e  movups  xmmword ptr [rbx+0CCh], xmm1
0x18000d475  movups  xmm0, [rbp+50h+var_50]
0x18000d479  movups  xmmword ptr [rbx+0DCh], xmm0
0x18000d480  movsd   xmm1, [rbp+50h+var_40]
0x18000d485  movsd   qword ptr [rbx+0ECh], xmm1
0x18000d48d  mov     [rsp+150h+var_108], 1
0x18000d495  mov     ebx, 10h
0x18000d49a  mov     rcx, [rsp+150h+lpCriticalSection]; lpCriticalSection
0x18000d49f  call    cs:__imp_LeaveCriticalSection
0x18000d4a5  cmp     [rsp+150h+var_108], 0
0x18000d4aa  jz      loc_18000D539
0x18000d4b0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d4b7  cmp     rcx, rsi
0x18000d4ba  jz      short loc_18000D4D8
0x18000d4bc  test    byte ptr [rcx+1Ch], 4
0x18000d4c0  jz      short loc_18000D4D8
0x18000d4c2  mov     edx, 0ADh
0x18000d4c7  mov     dword ptr [rsp+150h+var_130], r14d
0x18000d4cc  mov     r9d, r12d
0x18000d4cf  mov     rcx, [rcx+10h]
0x18000d4d3  call    WPP_SF_DD
0x18000d4d8  mov     rsi, [rsp+150h+var_100]
0x18000d4dd  cmp     r12d, r14d
0x18000d4e0  jz      short loc_18000D502
0x18000d4e2  movups  xmm0, xmmword ptr [rbx+rdi]
0x18000d4e6  movdqu  xmmword ptr [rsp+150h+lpCriticalSection], xmm0
0x18000d4ec  mov     r9d, r14d; unsigned int
0x18000d4ef  mov     r8d, 801h; unsigned int
0x18000d4f5  lea     rdx, [rsp+150h+lpCriticalSection]; struct _GUID
0x18000d4fa  mov     rcx, rsi; this
0x18000d4fd  call    ?PostNetworkCostManagerEvent@PublicNetworkListManager@@IEAAJU_GUID@@KK@Z; PublicNetworkListManager::PostNetworkCostManagerEvent(_GUID,ulong,ulong)
0x18000d502  mov     r8d, 38h ; '8'; Size
0x18000d508  lea     rdx, [rbp+50h+Buf2]; Buf2
0x18000d50c  lea     rcx, [rbp+50h+Buf1]; Buf1
0x18000d510  call    memcmp_0
0x18000d515  test    eax, eax
0x18000d517  jz      short loc_18000D539
0x18000d519  movups  xmm0, xmmword ptr [rbx+rdi]
0x18000d51d  movdqu  xmmword ptr [rsp+150h+lpCriticalSection], xmm0
0x18000d523  xor     r9d, r9d; unsigned int
0x18000d526  mov     r8d, 802h; unsigned int
0x18000d52c  lea     rdx, [rsp+150h+lpCriticalSection]; struct _GUID
0x18000d531  mov     rcx, rsi; this
0x18000d534  call    ?PostNetworkCostManagerEvent@PublicNetworkListManager@@IEAAJU_GUID@@KK@Z; PublicNetworkListManager::PostNetworkCostManagerEvent(_GUID,ulong,ulong)
0x18000d539  test    r13, r13
0x18000d53c  jz      short loc_18000D547
0x18000d53e  mov     rcx, r13; pv
0x18000d541  call    cs:__imp_CoTaskMemFree
0x18000d547  test    r15, r15
0x18000d54a  jz      short loc_18000D556
0x18000d54c  mov     rcx, r15; pv
0x18000d54f  call    cs:__imp_CoTaskMemFree
0x18000d555  nop
0x18000d556  lea     rcx, [rbp+50h+var_78]
0x18000d55a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000d55f  mov     rcx, [rbp+50h+var_38]
0x18000d563  xor     rcx, rsp; StackCookie
0x18000d566  call    __security_check_cookie
0x18000d56b  mov     rbx, [rsp+150h+arg_8]
0x18000d573  add     rsp, 120h
0x18000d57a  pop     r15
0x18000d57c  pop     r14
0x18000d57e  pop     r13
0x18000d580  pop     r12
0x18000d582  pop     rdi
0x18000d583  pop     rsi
0x18000d584  pop     rbp
0x18000d585  retn
```
