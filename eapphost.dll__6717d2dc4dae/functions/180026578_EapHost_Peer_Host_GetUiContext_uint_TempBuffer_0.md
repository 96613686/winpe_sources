# EapHost::Peer::Host::GetUiContext(uint,TempBuffer<0> &)

- ea: `0x180026578`
- end: `0x1800267c7`
- name: `?GetUiContext@Host@Peer@EapHost@@QEAAXIAEAV?$TempBuffer@$0A@@@@Z`
- size: `591`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: ``

## callers

- `0x180006db0`

## callees

- `0x1800049d8`
- `0x1800072cc`
- `0x180009dc4`
- `0x18000a050`
- `0x18001dcbc`
- `0x180022274`
- `0x180022a44`
- `0x180022c58`
- `0x180023f04`
- `0x180026578`
- `0x1800267d0`
- `0x18002adb8`
- `0x18002f93c`
- `0x18002fcc8`
- `0x180032c08`
- `0x180032da8`
- `0x180038010`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall EapHost::Peer::Host::GetUiContext(__int64 a1, unsigned int a2, __int64 a3)
{
  struct EapHost::Peer::PeerSession *v5; // rsi
  EapHost::Peer::Host *v6; // rcx
  __int64 v7; // rax
  volatile signed __int32 *v8; // rbx
  __int64 v9; // rax
  volatile signed __int32 *v10; // rdi
  __int64 v11; // rdx
  volatile signed __int32 *v12; // rdi
  __int64 v13; // rbx
  __int64 v14; // rdx
  bool v15; // r8
  void *v16; // [rsp+30h] [rbp-50h] BYREF
  __int64 v17; // [rsp+38h] [rbp-48h]
  void *v18[2]; // [rsp+40h] [rbp-40h] BYREF
  struct EapHost::Peer::PeerSession *v19[2]; // [rsp+50h] [rbp-30h] BYREF
  _QWORD v20[3]; // [rsp+60h] [rbp-20h] BYREF
  int v21; // [rsp+78h] [rbp-8h]
  volatile signed __int32 *v22; // [rsp+A0h] [rbp+20h] BYREF
  volatile signed __int32 *v23; // [rsp+B8h] [rbp+38h]

  EapHost::SessionAccessor<EapHost::Peer::PeerSession>::SessionAccessor<EapHost::Peer::PeerSession>(
    v19,
    (CacheEngine *)(a1 + 64),
    a2,
    0);
  v5 = v19[0];
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      26,
      WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids,
      a2,
      *((_DWORD *)v19[0] + 67));
    v6 = WPP_GLOBAL_Control;
  }
  if ( *((_DWORD *)v5 + 65) != 2 )
  {
    if ( v6 != (EapHost::Peer::Host *)&WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)v6 + 2), 27, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids);
    WriteEapThrowExceptionTelemetry(v5, (wchar_t *)L"Unexpected call to GetUiContext.");
    EapHost::EapException::Throw(L"Host::GetUiContext", L"Unexpected", -2147024809);
  }
  EapHost::Peer::Host::GetUiEapAuthenticationTipTest(v6, v5);
  v16 = 0;
  v17 = 0;
  if ( *((_DWORD *)v5 + 67) == 1 )
  {
    v22 = 0;
    v7 = EapLm::Peer::IdentityInfoMarshaller::Marshal(
           v18,
           *((unsigned int *)v5 + 32),
           *((_QWORD *)v5 + 25),
           (char *)v5 + 208,
           (char *)v5 + 224,
           &v22,
           v16,
           v17);
    TempBuffer<0>::Assign((__int64)&v16, v7);
    HeapAllocator::Free(v18[0]);
    HeapAllocator::Free(0);
  }
  else
  {
    v8 = (volatile signed __int32 *)*((_QWORD *)v5 + 36);
    v22 = v8;
    if ( v8 )
      _InterlockedIncrement(v8 + 2);
    v9 = *(_QWORD *)v8;
    v10 = (volatile signed __int32 *)*((_QWORD *)v5 + 35);
    v23 = v10;
    if ( v10 )
      _InterlockedIncrement(v10 + 2);
    (*(void (__fastcall **)(volatile signed __int32 *, volatile signed __int32 *, void **))(v9 + 72))(v8, v10, &v16);
    if ( v10 )
      ReferenceCounted::Release((ReferenceCounted *)v10);
    if ( v8 )
      ReferenceCounted::Release((ReferenceCounted *)v8);
  }
  EapLm::Peer::InteractiveUiMarshaller::Marshal(v18, *((unsigned int *)v5 + 67), &v16);
  EapHost::EapType::EapType((EapHost::EapType *)v20, (const struct _EAP_TYPE *)v5 + 11);
  v20[0] = &EapHost::EapMethodType::`vftable';
  v21 = *(_DWORD *)(v11 + 12);
  EapHost::DataWrapper::CreateInstance((unsigned int **)&v22, (__int64)v18, (__int64)v20);
  v12 = v22;
  v13 = *(unsigned int *)v22;
  v22 = 0;
  HeapAllocator::Free(*(void **)a3);
  *(_QWORD *)a3 = v12;
  *(_QWORD *)(a3 + 8) = v13;
  *((_DWORD *)v5 + 65) = 3;
  std::unique_ptr<EapHost::DataWrapper>::~unique_ptr<EapHost::DataWrapper>((void **)&v22);
  HeapAllocator::Free(v18[0]);
  HeapAllocator::Free(v16);
  EapHost::SessionAccessor<EapHost::Peer::PeerSession>::~SessionAccessor<EapHost::Peer::PeerSession>(v19, v14, v15);
}

```

## disassembly

```asm
0x180026578  mov     [rsp-18h+arg_8], rbx
0x18002657d  mov     [rsp-18h+arg_10], rsi
0x180026582  push    rbp
0x180026583  push    rdi
0x180026584  push    r14
0x180026586  mov     rbp, rsp
0x180026589  sub     rsp, 80h
0x180026590  mov     r14, r8
0x180026593  mov     ebx, edx
0x180026595  lea     rdx, [rcx+40h]
0x180026599  xor     r9d, r9d
0x18002659c  mov     r8d, ebx
0x18002659f  lea     rcx, [rbp+var_30]
0x1800265a3  call    ??0?$SessionAccessor@VPeerSession@Peer@EapHost@@@EapHost@@QEAA@AEAV?$Cache@V?$SessionTableOperation@VPeerSession@Peer@EapHost@@@EapHost@@@@I_N@Z; EapHost::SessionAccessor<EapHost::Peer::PeerSession>::SessionAccessor<EapHost::Peer::PeerSession>(Cache<EapHost::SessionTableOperation<EapHost::Peer::PeerSession>> &,uint,bool)
0x1800265a8  nop
0x1800265a9  mov     rsi, [rbp+var_30]
0x1800265ad  lea     rdi, WPP_GLOBAL_Control
0x1800265b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800265bb  cmp     rcx, rdi
0x1800265be  jz      short loc_1800265EF
0x1800265c0  test    byte ptr [rcx+1Ch], 4
0x1800265c4  jz      short loc_1800265EF
0x1800265c6  mov     edx, 1Ah
0x1800265cb  mov     eax, [rsi+10Ch]
0x1800265d1  mov     dword ptr [rsp+80h+var_60], eax
0x1800265d5  mov     r9d, ebx
0x1800265d8  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x1800265df  mov     rcx, [rcx+10h]
0x1800265e3  call    WPP_SF_dd
0x1800265e8  mov     rcx, cs:WPP_GLOBAL_Control; this
0x1800265ef  cmp     dword ptr [rsi+104h], 2
0x1800265f6  jnz     loc_18002677E
0x1800265fc  mov     rdx, rsi; struct EapHost::Peer::PeerSession *
0x1800265ff  call    ?GetUiEapAuthenticationTipTest@Host@Peer@EapHost@@AEBAXAEBVPeerSession@23@@Z; EapHost::Peer::Host::GetUiEapAuthenticationTipTest(EapHost::Peer::PeerSession const &)
0x180026604  mov     [rbp+var_50], 0
0x18002660c  mov     [rbp+var_48], 0
0x180026614  cmp     dword ptr [rsi+10Ch], 1
0x18002661b  jnz     short loc_180026678
0x18002661d  mov     [rbp+arg_0], 0
0x180026625  lea     rax, [rsi+0E0h]
0x18002662c  lea     r9, [rsi+0D0h]
0x180026633  lea     rcx, [rbp+arg_0]
0x180026637  mov     [rsp+80h+var_58], rcx
0x18002663c  mov     [rsp+80h+var_60], rax
0x180026641  mov     r8, [rsi+0C8h]
0x180026648  mov     edx, [rsi+80h]
0x18002664e  lea     rcx, [rbp+var_40]
0x180026652  call    ?Marshal@IdentityInfoMarshaller@Peer@EapLm@@SA?AV?$TempBuffer@$0A@@@I_JAEBUConstBuffer@@1AEBV?$BasicSimpleString@_W@@@Z; EapLm::Peer::IdentityInfoMarshaller::Marshal(uint,__int64,ConstBuffer const &,ConstBuffer const &,BasicSimpleString<wchar_t> const &)
0x180026657  nop
0x180026658  mov     rdx, rax
0x18002665b  lea     rcx, [rbp+var_50]
0x18002665f  call    ?Assign@?$TempBuffer@$0A@@@AEAAXAEBV1@@Z; TempBuffer<0>::Assign(TempBuffer<0> const &)
0x180026664  nop
0x180026665  mov     rcx, [rbp+var_40]; void *
0x180026669  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18002666e  nop
0x18002666f  xor     ecx, ecx; void *
0x180026671  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180026676  jmp     short loc_1800266D2
0x180026678  mov     rbx, [rsi+120h]
0x18002667f  mov     [rbp+arg_0], rbx
0x180026683  test    rbx, rbx
0x180026686  jz      short loc_18002668C
0x180026688  lock inc dword ptr [rbx+8]
0x18002668c  mov     rax, [rbx]
0x18002668f  mov     rdi, [rsi+118h]
0x180026696  mov     [rbp+arg_18], rdi
0x18002669a  test    rdi, rdi
0x18002669d  jz      short loc_1800266A3
0x18002669f  lock inc dword ptr [rdi+8]
0x1800266a3  lea     r8, [rbp+var_50]
0x1800266a7  mov     rdx, rdi
0x1800266aa  mov     rcx, rbx
0x1800266ad  mov     rax, [rax+48h]
0x1800266b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800266b6  nop
0x1800266b7  test    rdi, rdi
0x1800266ba  jz      short loc_1800266C5
0x1800266bc  mov     rcx, rdi; this
0x1800266bf  call    ?Release@ReferenceCounted@@QEAAXXZ; ReferenceCounted::Release(void)
0x1800266c4  nop
0x1800266c5  test    rbx, rbx
0x1800266c8  jz      short loc_1800266D2
0x1800266ca  mov     rcx, rbx; this
0x1800266cd  call    ?Release@ReferenceCounted@@QEAAXXZ; ReferenceCounted::Release(void)
0x1800266d2  lea     r8, [rbp+var_50]
0x1800266d6  mov     edx, [rsi+10Ch]
0x1800266dc  lea     rcx, [rbp+var_40]
0x1800266e0  call    ?Marshal@InteractiveUiMarshaller@Peer@EapLm@@SA?AV?$TempBuffer@$0A@@@IAEBUConstBuffer@@@Z; EapLm::Peer::InteractiveUiMarshaller::Marshal(uint,ConstBuffer const &)
0x1800266e5  nop
0x1800266e6  lea     rdx, [rsi+84h]; struct _EAP_TYPE *
0x1800266ed  lea     rcx, [rbp+var_20]; this
0x1800266f1  call    ??0EapType@EapHost@@QEAA@AEBU_EAP_TYPE@@@Z; EapHost::EapType::EapType(_EAP_TYPE const &)
0x1800266f6  lea     rcx, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x1800266fd  mov     [rbp+var_20], rcx
0x180026701  mov     eax, [rdx+0Ch]
0x180026704  mov     [rbp+var_8], eax
0x180026707  lea     r8, [rbp+var_20]
0x18002670b  lea     rdx, [rbp+var_40]
0x18002670f  lea     rcx, [rbp+arg_0]
0x180026713  call    ?CreateInstance@DataWrapper@EapHost@@SA?AV?$unique_ptr@UDataWrapper@EapHost@@U?$default_delete@UDataWrapper@EapHost@@@std@@@std@@AEBUBuffer@@AEAVEapMethodType@2@@Z; EapHost::DataWrapper::CreateInstance(Buffer const &,EapHost::EapMethodType &)
0x180026718  mov     rdi, [rbp+arg_0]
0x18002671c  mov     ebx, [rdi]
0x18002671e  mov     [rbp+arg_0], 0
0x180026726  mov     rcx, [r14]; void *
0x180026729  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18002672e  mov     [r14], rdi
0x180026731  mov     [r14+8], rbx
0x180026735  mov     dword ptr [rsi+104h], 3
0x18002673f  lea     rcx, [rbp+arg_0]
0x180026743  call    ??1?$unique_ptr@UDataWrapper@EapHost@@U?$default_delete@UDataWrapper@EapHost@@@std@@@std@@QEAA@XZ; std::unique_ptr<EapHost::DataWrapper>::~unique_ptr<EapHost::DataWrapper>(void)
0x180026748  nop
0x180026749  mov     rcx, [rbp+var_40]; void *
0x18002674d  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180026752  nop
0x180026753  mov     rcx, [rbp+var_50]; void *
0x180026757  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18002675c  nop
0x18002675d  lea     rcx, [rbp+var_30]
0x180026761  call    ??1?$SessionAccessor@VPeerSession@Peer@EapHost@@@EapHost@@QEAA@XZ; EapHost::SessionAccessor<EapHost::Peer::PeerSession>::~SessionAccessor<EapHost::Peer::PeerSession>(void)
0x180026766  lea     r11, [rsp+80h+var_s0]
0x18002676e  mov     rbx, [r11+28h]
0x180026772  mov     rsi, [r11+30h]
0x180026776  mov     rsp, r11
0x180026779  pop     r14
0x18002677b  pop     rdi
0x18002677c  pop     rbp
0x18002677d  retn
0x18002677e  cmp     rcx, rdi
0x180026781  jz      short loc_18002679E
0x180026783  test    byte ptr [rcx+1Ch], 1
0x180026787  jz      short loc_18002679E
0x180026789  mov     edx, 1Bh
0x18002678e  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x180026795  mov     rcx, [rcx+10h]
0x180026799  call    WPP_SF_
0x18002679e  lea     rdx, aUnexpectedCall_5; "Unexpected call to GetUiContext."
0x1800267a5  mov     rcx, rsi; struct EapHost::Peer::PeerSession *
0x1800267a8  call    ?WriteEapThrowExceptionTelemetry@@YAXAEAVPeerSession@Peer@EapHost@@PEA_W@Z; WriteEapThrowExceptionTelemetry(EapHost::Peer::PeerSession &,wchar_t *)
0x1800267ad  mov     r8d, 80070057h; int
0x1800267b3  lea     rdx, aUnexpected; "Unexpected"
0x1800267ba  lea     rcx, aHostGetuiconte; "Host::GetUiContext"
0x1800267c1  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
```
