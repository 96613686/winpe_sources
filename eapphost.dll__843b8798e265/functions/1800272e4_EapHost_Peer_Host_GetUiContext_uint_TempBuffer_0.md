# EapHost::Peer::Host::GetUiContext(uint,TempBuffer<0> &)

- ea: `0x1800272e4`
- end: `0x180027534`
- name: `?GetUiContext@Host@Peer@EapHost@@QEAAXIAEAV?$TempBuffer@$0A@@@@Z`
- size: `592`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: ``

## callers

- `0x180007040`

## callees

- `0x180004b4c`
- `0x180007564`
- `0x18000a21c`
- `0x18000a4d4`
- `0x18001e7c0`
- `0x180022ee4`
- `0x1800236d4`
- `0x180023890`
- `0x180024bd4`
- `0x1800272e4`
- `0x18002753c`
- `0x18002bbf4`
- `0x180030b08`
- `0x180030ed8`
- `0x180033fa4`
- `0x180034144`
- `0x180039010`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall EapHost::Peer::Host::GetUiContext(__int64 a1, unsigned int a2, __int64 a3)
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
  void *v15; // [rsp+30h] [rbp-50h] BYREF
  __int64 v16; // [rsp+38h] [rbp-48h]
  void *v17[2]; // [rsp+40h] [rbp-40h] BYREF
  struct EapHost::Peer::PeerSession *v18[2]; // [rsp+50h] [rbp-30h] BYREF
  _QWORD v19[3]; // [rsp+60h] [rbp-20h] BYREF
  int v20; // [rsp+78h] [rbp-8h]
  volatile signed __int32 *v21; // [rsp+A0h] [rbp+20h] BYREF
  volatile signed __int32 *v22; // [rsp+B8h] [rbp+38h]

  EapHost::SessionAccessor<EapHost::Peer::PeerSession>::SessionAccessor<EapHost::Peer::PeerSession>(
    v18,
    (CacheEngine *)(a1 + 64),
    a2,
    0);
  v5 = v18[0];
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      26,
      WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids,
      a2,
      *((_DWORD *)v18[0] + 67));
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
  v15 = 0;
  v16 = 0;
  if ( *((_DWORD *)v5 + 67) == 1 )
  {
    v21 = 0;
    v7 = EapLm::Peer::IdentityInfoMarshaller::Marshal(
           v17,
           *((unsigned int *)v5 + 32),
           *((_QWORD *)v5 + 25),
           (char *)v5 + 208,
           (char *)v5 + 224,
           &v21,
           v15,
           v16);
    TempBuffer<0>::Assign(&v15, v7);
    HeapAllocator::Free(v17[0]);
    HeapAllocator::Free(0);
  }
  else
  {
    v8 = (volatile signed __int32 *)*((_QWORD *)v5 + 36);
    v21 = v8;
    if ( v8 )
      _InterlockedIncrement(v8 + 2);
    v9 = *(_QWORD *)v8;
    v10 = (volatile signed __int32 *)*((_QWORD *)v5 + 35);
    v22 = v10;
    if ( v10 )
      _InterlockedIncrement(v10 + 2);
    (*(void (__fastcall **)(volatile signed __int32 *, volatile signed __int32 *, void **))(v9 + 72))(v8, v10, &v15);
    if ( v10 )
      ReferenceCounted::Release((ReferenceCounted *)v10);
    if ( v8 )
      ReferenceCounted::Release((ReferenceCounted *)v8);
  }
  EapLm::Peer::InteractiveUiMarshaller::Marshal(v17, *((unsigned int *)v5 + 67), &v15);
  EapHost::EapType::EapType((EapHost::EapType *)v19, (const struct _EAP_TYPE *)v5 + 11);
  v19[0] = &EapHost::EapMethodType::`vftable';
  v20 = *(_DWORD *)(v11 + 12);
  EapHost::DataWrapper::CreateInstance(&v21, v17, v19);
  v12 = v21;
  v13 = *(unsigned int *)v21;
  v21 = 0;
  HeapAllocator::Free(*(void **)a3);
  *(_QWORD *)a3 = v12;
  *(_QWORD *)(a3 + 8) = v13;
  *((_DWORD *)v5 + 65) = 3;
  std::unique_ptr<EapHost::DataWrapper>::~unique_ptr<EapHost::DataWrapper>(&v21);
  HeapAllocator::Free(v17[0]);
  HeapAllocator::Free(v15);
  return EapHost::SessionAccessor<EapHost::Peer::PeerSession>::~SessionAccessor<EapHost::Peer::PeerSession>(v18);
}

```

## disassembly

```asm
0x1800272e4  mov     [rsp-18h+arg_8], rbx
0x1800272e9  mov     [rsp-18h+arg_10], rsi
0x1800272ee  push    rbp
0x1800272ef  push    rdi
0x1800272f0  push    r14
0x1800272f2  mov     rbp, rsp
0x1800272f5  sub     rsp, 80h
0x1800272fc  mov     r14, r8
0x1800272ff  mov     ebx, edx
0x180027301  lea     rdx, [rcx+40h]
0x180027305  xor     r9d, r9d
0x180027308  mov     r8d, ebx
0x18002730b  lea     rcx, [rbp+var_30]
0x18002730f  call    ??0?$SessionAccessor@VPeerSession@Peer@EapHost@@@EapHost@@QEAA@AEAV?$Cache@V?$SessionTableOperation@VPeerSession@Peer@EapHost@@@EapHost@@@@I_N@Z; EapHost::SessionAccessor<EapHost::Peer::PeerSession>::SessionAccessor<EapHost::Peer::PeerSession>(Cache<EapHost::SessionTableOperation<EapHost::Peer::PeerSession>> &,uint,bool)
0x180027314  nop
0x180027315  mov     rsi, [rbp+var_30]
0x180027319  lea     rdi, WPP_GLOBAL_Control
0x180027320  mov     rcx, cs:WPP_GLOBAL_Control
0x180027327  cmp     rcx, rdi
0x18002732a  jz      short loc_18002735B
0x18002732c  test    byte ptr [rcx+1Ch], 4
0x180027330  jz      short loc_18002735B
0x180027332  mov     edx, 1Ah
0x180027337  mov     eax, [rsi+10Ch]
0x18002733d  mov     dword ptr [rsp+80h+var_60], eax
0x180027341  mov     r9d, ebx
0x180027344  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x18002734b  mov     rcx, [rcx+10h]
0x18002734f  call    WPP_SF_dd
0x180027354  mov     rcx, cs:WPP_GLOBAL_Control; this
0x18002735b  cmp     dword ptr [rsi+104h], 2
0x180027362  jnz     loc_1800274EB
0x180027368  mov     rdx, rsi; struct EapHost::Peer::PeerSession *
0x18002736b  call    ?GetUiEapAuthenticationTipTest@Host@Peer@EapHost@@AEBAXAEBVPeerSession@23@@Z; EapHost::Peer::Host::GetUiEapAuthenticationTipTest(EapHost::Peer::PeerSession const &)
0x180027370  mov     [rbp+var_50], 0
0x180027378  mov     [rbp+var_48], 0
0x180027380  cmp     dword ptr [rsi+10Ch], 1
0x180027387  jnz     short loc_1800273E4
0x180027389  mov     [rbp+arg_0], 0
0x180027391  lea     rax, [rsi+0E0h]
0x180027398  lea     r9, [rsi+0D0h]
0x18002739f  lea     rcx, [rbp+arg_0]
0x1800273a3  mov     [rsp+80h+var_58], rcx
0x1800273a8  mov     [rsp+80h+var_60], rax
0x1800273ad  mov     r8, [rsi+0C8h]
0x1800273b4  mov     edx, [rsi+80h]
0x1800273ba  lea     rcx, [rbp+var_40]
0x1800273be  call    ?Marshal@IdentityInfoMarshaller@Peer@EapLm@@SA?AV?$TempBuffer@$0A@@@I_JAEBUConstBuffer@@1AEBV?$BasicSimpleString@_W@@@Z; EapLm::Peer::IdentityInfoMarshaller::Marshal(uint,__int64,ConstBuffer const &,ConstBuffer const &,BasicSimpleString<wchar_t> const &)
0x1800273c3  nop
0x1800273c4  mov     rdx, rax
0x1800273c7  lea     rcx, [rbp+var_50]
0x1800273cb  call    ?Assign@?$TempBuffer@$0A@@@AEAAXAEBV1@@Z; TempBuffer<0>::Assign(TempBuffer<0> const &)
0x1800273d0  nop
0x1800273d1  mov     rcx, [rbp+var_40]; void *
0x1800273d5  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x1800273da  nop
0x1800273db  xor     ecx, ecx; void *
0x1800273dd  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x1800273e2  jmp     short loc_18002743E
0x1800273e4  mov     rbx, [rsi+120h]
0x1800273eb  mov     [rbp+arg_0], rbx
0x1800273ef  test    rbx, rbx
0x1800273f2  jz      short loc_1800273F8
0x1800273f4  lock inc dword ptr [rbx+8]
0x1800273f8  mov     rax, [rbx]
0x1800273fb  mov     rdi, [rsi+118h]
0x180027402  mov     [rbp+arg_18], rdi
0x180027406  test    rdi, rdi
0x180027409  jz      short loc_18002740F
0x18002740b  lock inc dword ptr [rdi+8]
0x18002740f  lea     r8, [rbp+var_50]
0x180027413  mov     rdx, rdi
0x180027416  mov     rcx, rbx
0x180027419  mov     rax, [rax+48h]
0x18002741d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027422  nop
0x180027423  test    rdi, rdi
0x180027426  jz      short loc_180027431
0x180027428  mov     rcx, rdi; this
0x18002742b  call    ?Release@ReferenceCounted@@QEAAXXZ; ReferenceCounted::Release(void)
0x180027430  nop
0x180027431  test    rbx, rbx
0x180027434  jz      short loc_18002743E
0x180027436  mov     rcx, rbx; this
0x180027439  call    ?Release@ReferenceCounted@@QEAAXXZ; ReferenceCounted::Release(void)
0x18002743e  lea     r8, [rbp+var_50]
0x180027442  mov     edx, [rsi+10Ch]
0x180027448  lea     rcx, [rbp+var_40]
0x18002744c  call    ?Marshal@InteractiveUiMarshaller@Peer@EapLm@@SA?AV?$TempBuffer@$0A@@@IAEBUConstBuffer@@@Z; EapLm::Peer::InteractiveUiMarshaller::Marshal(uint,ConstBuffer const &)
0x180027451  nop
0x180027452  lea     rdx, [rsi+84h]; struct _EAP_TYPE *
0x180027459  lea     rcx, [rbp+var_20]; this
0x18002745d  call    ??0EapType@EapHost@@QEAA@AEBU_EAP_TYPE@@@Z; EapHost::EapType::EapType(_EAP_TYPE const &)
0x180027462  lea     rcx, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x180027469  mov     [rbp+var_20], rcx
0x18002746d  mov     eax, [rdx+0Ch]
0x180027470  mov     [rbp+var_8], eax
0x180027473  lea     r8, [rbp+var_20]
0x180027477  lea     rdx, [rbp+var_40]
0x18002747b  lea     rcx, [rbp+arg_0]
0x18002747f  call    ?CreateInstance@DataWrapper@EapHost@@SA?AV?$unique_ptr@UDataWrapper@EapHost@@U?$default_delete@UDataWrapper@EapHost@@@std@@@std@@AEBUBuffer@@AEAVEapMethodType@2@@Z; EapHost::DataWrapper::CreateInstance(Buffer const &,EapHost::EapMethodType &)
0x180027484  mov     rdi, [rbp+arg_0]
0x180027488  mov     ebx, [rdi]
0x18002748a  mov     [rbp+arg_0], 0
0x180027492  mov     rcx, [r14]; void *
0x180027495  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18002749a  mov     [r14], rdi
0x18002749d  mov     [r14+8], rbx
0x1800274a1  mov     dword ptr [rsi+104h], 3
0x1800274ab  lea     rcx, [rbp+arg_0]
0x1800274af  call    ??1?$unique_ptr@UDataWrapper@EapHost@@U?$default_delete@UDataWrapper@EapHost@@@std@@@std@@QEAA@XZ; std::unique_ptr<EapHost::DataWrapper>::~unique_ptr<EapHost::DataWrapper>(void)
0x1800274b4  nop
0x1800274b5  mov     rcx, [rbp+var_40]; void *
0x1800274b9  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x1800274be  nop
0x1800274bf  mov     rcx, [rbp+var_50]; void *
0x1800274c3  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x1800274c8  nop
0x1800274c9  lea     rcx, [rbp+var_30]
0x1800274cd  call    ??1?$SessionAccessor@VPeerSession@Peer@EapHost@@@EapHost@@QEAA@XZ; EapHost::SessionAccessor<EapHost::Peer::PeerSession>::~SessionAccessor<EapHost::Peer::PeerSession>(void)
0x1800274d2  lea     r11, [rsp+80h+var_s0]
0x1800274da  mov     rbx, [r11+28h]
0x1800274de  mov     rsi, [r11+30h]
0x1800274e2  mov     rsp, r11
0x1800274e5  pop     r14
0x1800274e7  pop     rdi
0x1800274e8  pop     rbp
0x1800274e9  retn
0x1800274eb  cmp     rcx, rdi
0x1800274ee  jz      short loc_18002750B
0x1800274f0  test    byte ptr [rcx+1Ch], 1
0x1800274f4  jz      short loc_18002750B
0x1800274f6  mov     edx, 1Bh
0x1800274fb  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x180027502  mov     rcx, [rcx+10h]
0x180027506  call    WPP_SF_
0x18002750b  lea     rdx, aUnexpectedCall_5; "Unexpected call to GetUiContext."
0x180027512  mov     rcx, rsi; struct EapHost::Peer::PeerSession *
0x180027515  call    ?WriteEapThrowExceptionTelemetry@@YAXAEAVPeerSession@Peer@EapHost@@PEA_W@Z; WriteEapThrowExceptionTelemetry(EapHost::Peer::PeerSession &,wchar_t *)
0x18002751a  mov     r8d, 80070057h; int
0x180027520  lea     rdx, aUnexpected; "Unexpected"
0x180027527  lea     rcx, aHostGetuiconte; "Host::GetUiContext"
0x18002752e  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
```
