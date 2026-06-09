# CStdMarshal::CreateChannel(OXIDEntry *,CCtxComChnl * *)

- ea: `0x180037540`
- end: `0x180037d02`
- name: `?CreateChannel@CStdMarshal@@AEAAJPEAVOXIDEntry@@PEAPEAVCCtxComChnl@@@Z`
- size: `1986`
- prototype: `HRESULT __fastcall(CStdMarshal *this, OXIDEntry *pOXIDEntry, CCtxComChnl **ppChnl)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18009a0a4`
- `0x1801410d0`

## callees

- `0x180006534`
- `0x18000712c`
- `0x180036038`
- `0x180037540`
- `0x180037eb0`
- `0x18003a8bc`
- `0x18006ed00`
- `0x18007b734`
- `0x1800cc570`
- `0x18016e734`
- `0x180187688`
- `0x1801b9af0`
- `0x1801b9b00`
- `0x180255010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800376a6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003785e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180037a2f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800376a6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003785e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180037a2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180037839`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180037a0a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180037839`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180037a0a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800375bd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800375bd`

## string_xrefs

- `0x180037ba8`: `onecore\com\combase\dcomrem\marshal.cxx`
- `0x180037c62`: `onecore\com\combase\dcomrem\ctxchnl.cxx`
- `0x180037caa`: `onecore\com\combase\dcomrem\ctxchnl.cxx`

## pseudocode

```c
__int64 __fastcall CStdMarshal::CreateChannel(CStdMarshal *this, OXIDEntry *pOXIDEntry, CCtxComChnl **ppChnl)
{
  bool v3; // zf
  unsigned int v4; // eax
  OXIDEntry *v6; // r14
  _DWORD *ReservedForOle; // rdi
  int v9; // ebx
  CStdMarshal::CreateChannel::__l2::<lambda_81d99cb5f16d3e5c5bc1d1ead17aed05> *v10; // rdx
  CStdIdentity *pStdId; // rbx
  unsigned int Value; // eax
  CStdIdentity *v13; // rbx
  unsigned int v14; // eax
  bool v15; // r12
  CDestObject_vtbl *v16; // r8
  void *v17; // rcx
  CObjectContext *v18; // rdi
  char *v19; // rbx
  CStdIdentity *v20; // rax
  char Flags; // al
  CDestObject_vtbl *v22; // r8
  CCtxComChnl *pChnl; // rbx
  CStdIdentity *v25; // rdi
  unsigned int dwFlags; // eax
  unsigned int dwPid; // ebx
  DWORD CurrentProcessId; // eax
  unsigned int v29; // ecx
  char *v30; // rax
  CONTAINER_EXTENT_ARRAY *extensions; // xmm1_8
  __int128 v32; // xmm0
  bool bFreeThreaded; // di
  CStdIdentity *v34; // rsi
  unsigned int v35; // eax
  unsigned int v36; // ebx
  DWORD v37; // eax
  unsigned int v38; // ecx
  CCtxComChnl *v39; // rax
  CONTAINER_EXTENT_ARRAY *v40; // xmm1_8
  __int128 v41; // xmm0
  HRESULT LocalOXIDEntry; // ebx
  unsigned int v43; // edx
  tagCOMVERSION dcomVersion; // edx
  tagCOMVERSION v45; // edx
  unsigned int v46; // edx
  unsigned int v47; // edx
  CDestObject v48; // [rsp+38h] [rbp-28h] BYREF
  void *retaddr; // [rsp+98h] [rbp+38h]
  wil::details::lambda_call<<lambda_81d99cb5f16d3e5c5bc1d1ead17aed05> > reacquireLock; // [rsp+A0h] [rbp+40h] BYREF
  OXIDEntry *ppOXIDEntry; // [rsp+A8h] [rbp+48h] BYREF

  ppOXIDEntry = pOXIDEntry;
  v3 = gIPIDLock._cLocks == 1;
  v4 = gIPIDLock._cLocks - 1;
  *ppChnl = 0;
  gIPIDLock._cLocks = v4;
  v6 = pOXIDEntry;
  if ( v3 && gIPIDLock._lockOrder != Highest )
  {
    ReservedForOle = NtCurrentTeb()->ReservedForOle;
    if ( ReservedForOle )
    {
      v9 = 1 << gIPIDLock._lockOrder;
      if ( ((1 << gIPIDLock._lockOrder) & ReservedForOle[144]) == 0 )
        MicrosoftTelemetryAssertTriggeredNoArgs((unsigned __int8)gIPIDLock._lockOrder);
      ReservedForOle[144] &= ~v9;
    }
  }
  LeaveCriticalSection(&gIPIDLock._cs);
  wil::scope_exit__lambda_81d99cb5f16d3e5c5bc1d1ead17aed05___(&reacquireLock, v10);
  pStdId = this->_pStdId;
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixNonAtomicAccessInIpidtbl>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_FixNonAtomicAccessInIpidtbl>::GetImpl'::`2'::impl) )
    Value = pStdId->m_stdIdFlags._Storage._Value;
  else
    Value = pStdId->m_flags;
  v15 = 1;
  if ( (Value & 2) == 0 )
  {
    v13 = this->_pStdId;
    v14 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixNonAtomicAccessInIpidtbl>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_FixNonAtomicAccessInIpidtbl>::GetImpl'::`2'::impl)
        ? v13->m_stdIdFlags._Storage._Value
        : v13->m_flags;
    if ( (v14 & 0x40000) == 0 && !gEnableAgileProxies )
      v15 = 0;
  }
  if ( !v6 )
  {
    LocalOXIDEntry = GetLocalOXIDEntry(&ppOXIDEntry);
    if ( LocalOXIDEntry < 0 )
    {
      v43 = 7360;
      goto LABEL_46;
    }
    v6 = ppOXIDEntry;
  }
  if ( this->_pChnl )
    goto LABEL_30;
  if ( (CStdMarshal::GetFlags(this) & 1) != 0 )
  {
    v25 = this->_pStdId;
    v48._dcomVersion = DcomProtocolVersion_Current;
    dwFlags = v6->_info.dwFlags;
    v48.__vftable = v16;
    v48._containerVersion.extensions = 0;
    *(_OWORD *)&v48._containerVersion.version = 3u;
    if ( (dwFlags & 1) != 0 )
    {
      dwPid = v6->_info.dwPid;
      CurrentProcessId = GetCurrentProcessId();
      v29 = 0;
      if ( dwPid == CurrentProcessId )
        v29 = 3;
      v48._dwDestCtx = v29;
    }
    else if ( (dwFlags & 4) != 0 )
    {
      v48._dwDestCtx = 5;
      LocalOXIDEntry = CDestObject::SetContainerVersion(&v48, &v6->_info.containerVersion);
      if ( LocalOXIDEntry < 0 )
      {
        v46 = 321;
LABEL_57:
        wil::details::in1diag3::Return_Hr(retaddr, v46, "onecore\\com\\combase\\dcomrem\\ctxchnl.cxx", LocalOXIDEntry);
        ClearContainerVersion(&v48._containerVersion);
        v43 = 7371;
        goto LABEL_46;
      }
    }
    else
    {
      dcomVersion = v6->_info.dcomVersion;
      v48._dwDestCtx = 2;
      CDestObject::SetDcomVersion(&v48, dcomVersion);
    }
    v30 = (char *)HeapAlloc(g_hHeap, 0, 0xB8u);
    v19 = v30;
    if ( v30 )
    {
      *((_QWORD *)v30 + 6) = v25;
      *(_QWORD *)v30 = ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CCtxComChnl,>>::`vftable'{for `IRpcChannelBuffer3'};
      *((_QWORD *)v30 + 1) = CCtxComChnl::`vftable'{for `IAsyncRpcChannelBuffer'};
      *((_QWORD *)v30 + 2) = ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CCtxComChnl,>>::`vftable'{for `IRpcChannelBufferMarshalingContext'};
      *((_QWORD *)v30 + 3) = ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CCtxComChnl,>>::`vftable'{for `IChannelHandleMarshal'};
      *((_QWORD *)v30 + 4) = CCtxComChnl::`vftable'{for `IChannelCallObjectInitialization'};
      *((_QWORD *)v30 + 5) = CCtxComChnl::`vftable'{for `IChannelProtocolBehavior'};
      *((_QWORD *)v30 + 7) = v6;
      v30[64] = v15;
      *((_DWORD *)v30 + 17) = GetCurrentApartmentId();
      extensions = v48._containerVersion.extensions;
      *((_QWORD *)v19 + 1) = CCtxComChnl::`vftable'{for `IAsyncRpcChannelBuffer'};
      *((_QWORD *)v19 + 2) = ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CCtxComChnl,>>::`vftable'{for `IRpcChannelBufferMarshalingContext'};
      *((_QWORD *)v19 + 3) = ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CCtxComChnl,>>::`vftable'{for `IChannelHandleMarshal'};
      *((_QWORD *)v19 + 4) = CCtxComChnl::`vftable'{for `IChannelCallObjectInitialization'};
      *((_QWORD *)v19 + 5) = CCtxComChnl::`vftable'{for `IChannelProtocolBehavior'};
      *((_QWORD *)v19 + 9) = ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IAsyncRpcChannelBuffer,IRpcSyntaxNegotiate,ICancelMethodCalls,IClientSecurity,IChannelWrapper,IMessageParam>>::`vftable'{for `IChannelWrapper'};
      *(_QWORD *)v19 = ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CCtxComChnl,IRpcSyntaxNegotiate>>::`vftable'{for `IRpcChannelBuffer3'};
      *(_QWORD *)v19 = CClientChannel::`vftable'{for `IRpcChannelBuffer3'};
      *((_QWORD *)v19 + 1) = CClientChannel::`vftable'{for `IAsyncRpcChannelBuffer'};
      *((_QWORD *)v19 + 2) = CClientChannel::`vftable'{for `IRpcChannelBufferMarshalingContext'};
      *((_QWORD *)v19 + 3) = CClientChannel::`vftable'{for `IChannelHandleMarshal'};
      *((_QWORD *)v19 + 4) = CClientChannel::`vftable'{for `IChannelCallObjectInitialization'};
      *((_QWORD *)v19 + 5) = CClientChannel::`vftable'{for `IChannelProtocolBehavior'};
      *((_QWORD *)v19 + 9) = CClientChannel::`vftable';
      *(_GUID *)(v19 + 88) = guidCClientChannelSignature;
      *((_DWORD *)v19 + 20) = 1;
      v32 = *(_OWORD *)&v48._containerVersion.version;
      *((_DWORD *)v19 + 26) = v6->_info.dwTid;
      *((_QWORD *)v19 + 14) = CDestObject::`vftable';
      *((_DWORD *)v19 + 30) = v48._dwDestCtx;
      *((_DWORD *)v19 + 31) = v48._dcomVersion;
      *((_OWORD *)v19 + 8) = v32;
      *((_QWORD *)v19 + 18) = extensions;
      *((_QWORD *)v19 + 19) = 0;
      *(_OWORD *)&v48._containerVersion.version = 0;
      *((_QWORD *)v19 + 20) = 0;
      *((_QWORD *)v19 + 21) = 0;
      *((_QWORD *)v19 + 22) = 0;
LABEL_28:
      if ( _InterlockedCompareExchange64((volatile signed __int64 *)&this->_pChnl, (signed __int64)v19, 0) )
        (*(void (__fastcall **)(char *))(*(_QWORD *)v19 + 16LL))(v19);
LABEL_30:
      Flags = CStdMarshal::GetFlags(this);
      pChnl = this->_pChnl;
      if ( (Flags & 1) == 0 )
      {
LABEL_31:
        *ppChnl = pChnl;
        wil::details::lambda_call__lambda_81d99cb5f16d3e5c5bc1d1ead17aed05___::_lambda_call__lambda_81d99cb5f16d3e5c5bc1d1ead17aed05___(&reacquireLock);
        return 0;
      }
      bFreeThreaded = pChnl->_bFreeThreaded;
      v34 = pChnl->_pStdId;
      v48._dcomVersion = DcomProtocolVersion_Current;
      v35 = v6->_info.dwFlags;
      v48.__vftable = v22;
      v48._containerVersion.extensions = 0;
      *(_OWORD *)&v48._containerVersion.version = 3u;
      if ( (v35 & 1) != 0 )
      {
        v36 = v6->_info.dwPid;
        v37 = GetCurrentProcessId();
        v38 = 0;
        if ( v36 == v37 )
          v38 = 3;
        v48._dwDestCtx = v38;
      }
      else if ( (v35 & 4) != 0 )
      {
        v48._dwDestCtx = 5;
        LocalOXIDEntry = CDestObject::SetContainerVersion(&v48, &v6->_info.containerVersion);
        if ( LocalOXIDEntry < 0 )
        {
          v47 = 321;
LABEL_60:
          wil::details::in1diag3::Return_Hr(retaddr, v47, "onecore\\com\\combase\\dcomrem\\ctxchnl.cxx", LocalOXIDEntry);
          ClearContainerVersion(&v48._containerVersion);
          v43 = 7393;
          goto LABEL_46;
        }
      }
      else
      {
        v45 = v6->_info.dcomVersion;
        v48._dwDestCtx = 2;
        CDestObject::SetDcomVersion(&v48, v45);
      }
      v39 = (CCtxComChnl *)HeapAlloc(g_hHeap, 0, 0xB8u);
      pChnl = v39;
      if ( v39 )
      {
        v39->_pStdId = v34;
        v39->ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ComReferenceCountingOptions<4>,ObjectLibrary::ObjectNoAllocation,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::ObjectNoDebugging,ObjectLibrary::ObjectNoAssociations>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<4>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::Details::AddComReferenceCounting_DeclareOnlyLayer<CCtxComChnl,ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > > >::ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > >::ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::IRpcChannelBuffer3::IRpcChannelBuffer2::IRpcChannelBuffer::IUnknown::__vftable = (CCtxComChnl_vtbl *)ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CCtxComChnl,>>::`vftable'{for `IRpcChannelBuffer3'};
        v39->ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ComReferenceCountingOptions<4>,ObjectLibrary::ObjectNoAllocation,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::ObjectNoDebugging,ObjectLibrary::ObjectNoAssociations>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<4>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::Details::AddComReferenceCounting_DeclareOnlyLayer<CCtxComChnl,ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > > >::ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > >::ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::IAsyncRpcChannelBuffer::IRpcChannelBuffer2::IRpcChannelBuffer::IUnknown::__vftable = (IAsyncRpcChannelBuffer_vtbl *)CCtxComChnl::`vftable'{for `IAsyncRpcChannelBuffer'};
        v39->ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ComReferenceCountingOptions<4>,ObjectLibrary::ObjectNoAllocation,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::ObjectNoDebugging,ObjectLibrary::ObjectNoAssociations>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<4>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::Details::AddComReferenceCounting_DeclareOnlyLayer<CCtxComChnl,ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > > >::ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > >::ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::IRpcChannelBufferMarshalingContext::IUnknown::__vftable = (IRpcChannelBufferMarshalingContext_vtbl *)ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CCtxComChnl,>>::`vftable'{for `IRpcChannelBufferMarshalingContext'};
        v39->ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ComReferenceCountingOptions<4>,ObjectLibrary::ObjectNoAllocation,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::ObjectNoDebugging,ObjectLibrary::ObjectNoAssociations>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<4>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::Details::AddComReferenceCounting_DeclareOnlyLayer<CCtxComChnl,ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > > >::ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > >::ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::IChannelHandleMarshal::IUnknown::__vftable = (IChannelHandleMarshal_vtbl *)ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CCtxComChnl,>>::`vftable'{for `IChannelHandleMarshal'};
        v39->ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ComReferenceCountingOptions<4>,ObjectLibrary::ObjectNoAllocation,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::ObjectNoDebugging,ObjectLibrary::ObjectNoAssociations>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<4>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::Details::AddComReferenceCounting_DeclareOnlyLayer<CCtxComChnl,ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > > >::ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > >::ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::IChannelCallObjectInitialization::IUnknown::__vftable = (IChannelCallObjectInitialization_vtbl *)CCtxComChnl::`vftable'{for `IChannelCallObjectInitialization'};
        v39->ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ComReferenceCountingOptions<4>,ObjectLibrary::ObjectNoAllocation,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::ObjectNoDebugging,ObjectLibrary::ObjectNoAssociations>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<4>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::Details::AddComReferenceCounting_DeclareOnlyLayer<CCtxComChnl,ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > > >::ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > >::ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::IChannelProtocolBehavior::IUnknown::__vftable = (IChannelProtocolBehavior_vtbl *)CCtxComChnl::`vftable'{for `IChannelProtocolBehavior'};
        v39->_pOXIDEntry = v6;
        v39->_bFreeThreaded = bFreeThreaded;
        v39->_dwAptId = GetCurrentApartmentId();
        v40 = v48._containerVersion.extensions;
        pChnl->ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ComReferenceCountingOptions<4>,ObjectLibrary::ObjectNoAllocation,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::ObjectNoDebugging,ObjectLibrary::ObjectNoAssociations>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<4>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::Details::AddComReferenceCounting_DeclareOnlyLayer<CCtxComChnl,ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > > >::ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > >::ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::IAsyncRpcChannelBuffer::IRpcChannelBuffer2::IRpcChannelBuffer::IUnknown::__vftable = (IAsyncRpcChannelBuffer_vtbl *)CCtxComChnl::`vftable'{for `IAsyncRpcChannelBuffer'};
        pChnl->ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ComReferenceCountingOptions<4>,ObjectLibrary::ObjectNoAllocation,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::ObjectNoDebugging,ObjectLibrary::ObjectNoAssociations>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<4>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::Details::AddComReferenceCounting_DeclareOnlyLayer<CCtxComChnl,ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > > >::ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > >::ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::IRpcChannelBufferMarshalingContext::IUnknown::__vftable = (IRpcChannelBufferMarshalingContext_vtbl *)ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CCtxComChnl,>>::`vftable'{for `IRpcChannelBufferMarshalingContext'};
        pChnl->ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ComReferenceCountingOptions<4>,ObjectLibrary::ObjectNoAllocation,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::ObjectNoDebugging,ObjectLibrary::ObjectNoAssociations>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<4>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::Details::AddComReferenceCounting_DeclareOnlyLayer<CCtxComChnl,ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > > >::ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > >::ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::IChannelHandleMarshal::IUnknown::__vftable = (IChannelHandleMarshal_vtbl *)ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CCtxComChnl,>>::`vftable'{for `IChannelHandleMarshal'};
        pChnl->ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ComReferenceCountingOptions<4>,ObjectLibrary::ObjectNoAllocation,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::ObjectNoDebugging,ObjectLibrary::ObjectNoAssociations>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<4>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::Details::AddComReferenceCounting_DeclareOnlyLayer<CCtxComChnl,ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > > >::ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > >::ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::IChannelCallObjectInitialization::IUnknown::__vftable = (IChannelCallObjectInitialization_vtbl *)CCtxComChnl::`vftable'{for `IChannelCallObjectInitialization'};
        pChnl->ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ComReferenceCountingOptions<4>,ObjectLibrary::ObjectNoAllocation,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::ObjectNoDebugging,ObjectLibrary::ObjectNoAssociations>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<4>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::Details::AddComReferenceCounting_DeclareOnlyLayer<CCtxComChnl,ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > > >::ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > >::ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::IChannelProtocolBehavior::IUnknown::__vftable = (IChannelProtocolBehavior_vtbl *)CCtxComChnl::`vftable'{for `IChannelProtocolBehavior'};
        pChnl[1].ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ComReferenceCountingOptions<4>,ObjectLibrary::ObjectNoAllocation,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::ObjectNoDebugging,ObjectLibrary::ObjectNoAssociations>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<4>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::Details::AddComReferenceCounting_DeclareOnlyLayer<CCtxComChnl,ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > > >::ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > >::ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::IRpcChannelBuffer3::IRpcChannelBuffer2::IRpcChannelBuffer::IUnknown::__vftable = (CCtxComChnl_vtbl *)ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IAsyncRpcChannelBuffer,IRpcSyntaxNegotiate,ICancelMethodCalls,IClientSecurity,IChannelWrapper,IMessageParam>>::`vftable'{for `IChannelWrapper'};
        pChnl->ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ComReferenceCountingOptions<4>,ObjectLibrary::ObjectNoAllocation,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::ObjectNoDebugging,ObjectLibrary::ObjectNoAssociations>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<4>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::Details::AddComReferenceCounting_DeclareOnlyLayer<CCtxComChnl,ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > > >::ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > >::ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::IRpcChannelBuffer3::IRpcChannelBuffer2::IRpcChannelBuffer::IUnknown::__vftable = (CCtxComChnl_vtbl *)ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CCtxComChnl,IRpcSyntaxNegotiate>>::`vftable'{for `IRpcChannelBuffer3'};
        pChnl->ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ComReferenceCountingOptions<4>,ObjectLibrary::ObjectNoAllocation,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::ObjectNoDebugging,ObjectLibrary::ObjectNoAssociations>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<4>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::Details::AddComReferenceCounting_DeclareOnlyLayer<CCtxComChnl,ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > > >::ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > >::ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::IRpcChannelBuffer3::IRpcChannelBuffer2::IRpcChannelBuffer::IUnknown::__vftable = (CCtxComChnl_vtbl *)CClientChannel::`vftable'{for `IRpcChannelBuffer3'};
        pChnl->ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ComReferenceCountingOptions<4>,ObjectLibrary::ObjectNoAllocation,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::ObjectNoDebugging,ObjectLibrary::ObjectNoAssociations>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<4>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::Details::AddComReferenceCounting_DeclareOnlyLayer<CCtxComChnl,ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > > >::ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > >::ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::IAsyncRpcChannelBuffer::IRpcChannelBuffer2::IRpcChannelBuffer::IUnknown::__vftable = (IAsyncRpcChannelBuffer_vtbl *)CClientChannel::`vftable'{for `IAsyncRpcChannelBuffer'};
        pChnl->ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ComReferenceCountingOptions<4>,ObjectLibrary::ObjectNoAllocation,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::ObjectNoDebugging,ObjectLibrary::ObjectNoAssociations>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<4>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::Details::AddComReferenceCounting_DeclareOnlyLayer<CCtxComChnl,ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > > >::ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > >::ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::IRpcChannelBufferMarshalingContext::IUnknown::__vftable = (IRpcChannelBufferMarshalingContext_vtbl *)CClientChannel::`vftable'{for `IRpcChannelBufferMarshalingContext'};
        pChnl->ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ComReferenceCountingOptions<4>,ObjectLibrary::ObjectNoAllocation,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::ObjectNoDebugging,ObjectLibrary::ObjectNoAssociations>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<4>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::Details::AddComReferenceCounting_DeclareOnlyLayer<CCtxComChnl,ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > > >::ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > >::ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::IChannelHandleMarshal::IUnknown::__vftable = (IChannelHandleMarshal_vtbl *)CClientChannel::`vftable'{for `IChannelHandleMarshal'};
        pChnl->ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ComReferenceCountingOptions<4>,ObjectLibrary::ObjectNoAllocation,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::ObjectNoDebugging,ObjectLibrary::ObjectNoAssociations>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<4>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::Details::AddComReferenceCounting_DeclareOnlyLayer<CCtxComChnl,ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > > >::ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > >::ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::IChannelCallObjectInitialization::IUnknown::__vftable = (IChannelCallObjectInitialization_vtbl *)CClientChannel::`vftable'{for `IChannelCallObjectInitialization'};
        pChnl->ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ComReferenceCountingOptions<4>,ObjectLibrary::ObjectNoAllocation,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::ObjectNoDebugging,ObjectLibrary::ObjectNoAssociations>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<4>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::Details::AddComReferenceCounting_DeclareOnlyLayer<CCtxComChnl,ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > > >::ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > >::ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::IChannelProtocolBehavior::IUnknown::__vftable = (IChannelProtocolBehavior_vtbl *)CClientChannel::`vftable'{for `IChannelProtocolBehavior'};
        pChnl[1].ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ComReferenceCountingOptions<4>,ObjectLibrary::ObjectNoAllocation,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::ObjectNoDebugging,ObjectLibrary::ObjectNoAssociations>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<4>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::Details::AddComReferenceCounting_DeclareOnlyLayer<CCtxComChnl,ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > > >::ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > >::ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::IRpcChannelBuffer3::IRpcChannelBuffer2::IRpcChannelBuffer::IUnknown::__vftable = (CCtxComChnl_vtbl *)CClientChannel::`vftable';
        *(_GUID *)&pChnl[1].ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ComReferenceCountingOptions<4>,ObjectLibrary::ObjectNoAllocation,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::ObjectNoDebugging,ObjectLibrary::ObjectNoAssociations>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<4>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::Details::AddComReferenceCounting_DeclareOnlyLayer<CCtxComChnl,ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > > >::ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > >::ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::IRpcChannelBufferMarshalingContext::IUnknown::__vftable = guidCClientChannelSignature;
        LODWORD(pChnl[1].ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ComReferenceCountingOptions<4>,ObjectLibrary::ObjectNoAllocation,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::ObjectNoDebugging,ObjectLibrary::ObjectNoAssociations>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<4>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::Details::AddComReferenceCounting_DeclareOnlyLayer<CCtxComChnl,ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > > >::ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > >::ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::IAsyncRpcChannelBuffer::IRpcChannelBuffer2::IRpcChannelBuffer::IUnknown::__vftable) = 1;
        v41 = *(_OWORD *)&v48._containerVersion.version;
        LODWORD(pChnl[1].ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ComReferenceCountingOptions<4>,ObjectLibrary::ObjectNoAllocation,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::ObjectNoDebugging,ObjectLibrary::ObjectNoAssociations>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<4>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::Details::AddComReferenceCounting_DeclareOnlyLayer<CCtxComChnl,ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > > >::ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > >::ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::IChannelCallObjectInitialization::IUnknown::__vftable) = v6->_info.dwTid;
        pChnl[1].ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ComReferenceCountingOptions<4>,ObjectLibrary::ObjectNoAllocation,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::ObjectNoDebugging,ObjectLibrary::ObjectNoAssociations>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<4>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::Details::AddComReferenceCounting_DeclareOnlyLayer<CCtxComChnl,ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > > >::ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > >::ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::IChannelProtocolBehavior::IUnknown::__vftable = (IChannelProtocolBehavior_vtbl *)CDestObject::`vftable';
        LODWORD(pChnl[1]._pStdId) = v48._dwDestCtx;
        HIDWORD(pChnl[1]._pStdId) = v48._dcomVersion;
        *(_OWORD *)&pChnl[1]._pOXIDEntry = v41;
        pChnl[2].ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ComReferenceCountingOptions<4>,ObjectLibrary::ObjectNoAllocation,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::ObjectNoDebugging,ObjectLibrary::ObjectNoAssociations>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<4>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::Details::AddComReferenceCounting_DeclareOnlyLayer<CCtxComChnl,ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > > >::ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > >::ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::IRpcChannelBuffer3::IRpcChannelBuffer2::IRpcChannelBuffer::IUnknown::__vftable = (CCtxComChnl_vtbl *)v40;
        pChnl[2].ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ComReferenceCountingOptions<4>,ObjectLibrary::ObjectNoAllocation,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::ObjectNoDebugging,ObjectLibrary::ObjectNoAssociations>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<4>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::Details::AddComReferenceCounting_DeclareOnlyLayer<CCtxComChnl,ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > > >::ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > >::ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::IAsyncRpcChannelBuffer::IRpcChannelBuffer2::IRpcChannelBuffer::IUnknown::__vftable = 0;
        pChnl[2].ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ComReferenceCountingOptions<4>,ObjectLibrary::ObjectNoAllocation,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::ObjectNoDebugging,ObjectLibrary::ObjectNoAssociations>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<4>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::Details::AddComReferenceCounting_DeclareOnlyLayer<CCtxComChnl,ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > > >::ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > >::ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::IRpcChannelBufferMarshalingContext::IUnknown::__vftable = 0;
        pChnl[2].ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ComReferenceCountingOptions<4>,ObjectLibrary::ObjectNoAllocation,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::ObjectNoDebugging,ObjectLibrary::ObjectNoAssociations>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<4>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::Details::AddComReferenceCounting_DeclareOnlyLayer<CCtxComChnl,ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > > >::ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > >::ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::IChannelHandleMarshal::IUnknown::__vftable = 0;
        pChnl[2].ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ComReferenceCountingOptions<4>,ObjectLibrary::ObjectNoAllocation,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::ObjectNoDebugging,ObjectLibrary::ObjectNoAssociations>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<4>,CCtxComChnl,ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::ObjectLibrary::Details::AddComReferenceCounting_DeclareOnlyLayer<CCtxComChnl,ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > > >::ObjectLibrary::Details::MixinBase<CCtxComChnl,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> > >::ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IRpcChannelBuffer3,IAsyncRpcChannelBuffer,IRpcChannelBufferMarshalingContext,IChannelHandleMarshal,IChannelCallObjectInitialization,IChannelProtocolBehavior> >::IChannelCallObjectInitialization::IUnknown::__vftable = 0;
        goto LABEL_31;
      }
      LocalOXIDEntry = -2147024882;
      v47 = 330;
      goto LABEL_60;
    }
    LocalOXIDEntry = -2147024882;
    v46 = 330;
    goto LABEL_57;
  }
  v17 = NtCurrentTeb()->ReservedForOle;
  if ( v17 )
  {
    v18 = (CObjectContext *)*((_QWORD *)v17 + 13);
    if ( !v18 )
      v18 = g_pMTAEmptyCtx;
    *((_QWORD *)v17 + 12) = v18;
  }
  else
  {
    v18 = g_pMTAEmptyCtx;
  }
  if ( !v18 || (CObjectContext::GetFlags(v18) & 0x100) == 0 )
    v18 = 0;
  v19 = (char *)HeapAlloc(g_hHeap, 0, 0x58u);
  if ( v19 )
  {
    v20 = this->_pStdId;
    *(_QWORD *)v19 = ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CCtxComChnl,>>::`vftable'{for `IRpcChannelBuffer3'};
    *((_QWORD *)v19 + 1) = CCtxComChnl::`vftable'{for `IAsyncRpcChannelBuffer'};
    *((_QWORD *)v19 + 2) = ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CCtxComChnl,>>::`vftable'{for `IRpcChannelBufferMarshalingContext'};
    *((_QWORD *)v19 + 3) = ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CCtxComChnl,>>::`vftable'{for `IChannelHandleMarshal'};
    *((_QWORD *)v19 + 4) = CCtxComChnl::`vftable'{for `IChannelCallObjectInitialization'};
    *((_QWORD *)v19 + 5) = CCtxComChnl::`vftable'{for `IChannelProtocolBehavior'};
    *((_QWORD *)v19 + 6) = v20;
    *((_QWORD *)v19 + 7) = v6;
    v19[64] = v15;
    *((_DWORD *)v19 + 17) = GetCurrentApartmentId();
    *((_QWORD *)v19 + 10) = v18;
    *(_QWORD *)v19 = ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CCtxComChnl,>>::`vftable'{for `IRpcChannelBuffer3'};
    *((_QWORD *)v19 + 1) = CCtxComChnl::`vftable'{for `IAsyncRpcChannelBuffer'};
    *((_QWORD *)v19 + 2) = ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CCtxComChnl,>>::`vftable'{for `IRpcChannelBufferMarshalingContext'};
    *((_QWORD *)v19 + 3) = ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CCtxComChnl,>>::`vftable'{for `IChannelHandleMarshal'};
    *((_QWORD *)v19 + 4) = CCtxComChnl::`vftable'{for `IChannelCallObjectInitialization'};
    *((_QWORD *)v19 + 5) = CCtxComChnl::`vftable'{for `IChannelProtocolBehavior'};
    *(_QWORD *)v19 = CServerChannel::`vftable'{for `IRpcChannelBuffer3'};
    *((_QWORD *)v19 + 1) = CServerChannel::`vftable'{for `IAsyncRpcChannelBuffer'};
    *((_QWORD *)v19 + 2) = CServerChannel::`vftable'{for `IRpcChannelBufferMarshalingContext'};
    *((_QWORD *)v19 + 3) = CServerChannel::`vftable'{for `IChannelHandleMarshal'};
    *((_QWORD *)v19 + 4) = CServerChannel::`vftable'{for `IChannelCallObjectInitialization'};
    *((_QWORD *)v19 + 5) = CServerChannel::`vftable'{for `IChannelProtocolBehavior'};
    *((_DWORD *)v19 + 18) = 1;
    goto LABEL_28;
  }
  LocalOXIDEntry = -2147024882;
  v43 = 7380;
LABEL_46:
  wil::details::in1diag3::Return_Hr(retaddr, v43, "onecore\\com\\combase\\dcomrem\\marshal.cxx", LocalOXIDEntry);
  wil::details::lambda_call__lambda_81d99cb5f16d3e5c5bc1d1ead17aed05___::_lambda_call__lambda_81d99cb5f16d3e5c5bc1d1ead17aed05___(&reacquireLock);
  return (unsigned int)LocalOXIDEntry;
}

```

## disassembly

```asm
0x180037540  mov     [rsp-38h+ppOXIDEntry], pOXIDEntry
0x180037545  push    rbp
0x180037546  push    rbx
0x180037547  push    rsi
0x180037548  push    rdi
0x180037549  push    r13
0x18003754b  push    r14
0x18003754d  push    r15
0x18003754f  mov     rbp, rsp
0x180037552  sub     rsp, 60h
0x180037556  mov     eax, cs:?gIPIDLock@@3VCOleStaticMutexSem@@A._cLocks; COleStaticMutexSem gIPIDLock ...
0x18003755c  xor     r13d, r13d
0x18003755f  add     eax, 0FFFFFFFFh
0x180037562  mov     [ppChnl], r13
0x180037565  mov     cs:?gIPIDLock@@3VCOleStaticMutexSem@@A._cLocks, eax; COleStaticMutexSem gIPIDLock ...
0x18003756b  mov     r15, ppChnl
0x18003756e  mov     r14, pOXIDEntry
0x180037571  mov     rsi, this
0x180037574  jnz     short loc_1800375B6
0x180037576  cmp     cs:?gIPIDLock@@3VCOleStaticMutexSem@@A._lockOrder, 13h; COleStaticMutexSem gIPIDLock ...
0x18003757d  jz      short loc_1800375B6
0x18003757f  mov     rax, gs:30h
0x180037588  mov     rdi, [rax+1758h]
0x18003758f  test    rdi, rdi
0x180037592  jz      short loc_1800375B6
0x180037594  movzx   ecx, cs:?gIPIDLock@@3VCOleStaticMutexSem@@A._lockOrder; COleStaticMutexSem gIPIDLock ...
0x18003759b  mov     ebx, 1
0x1800375a0  shl     ebx, cl
0x1800375a2  test    [rdi+240h], ebx
0x1800375a8  jz      loc_180037C35
0x1800375ae  not     ebx
0x1800375b0  and     [rdi+240h], ebx
0x1800375b6  lea     this, ?gIPIDLock@@3VCOleStaticMutexSem@@A._cs; lpCriticalSection
0x1800375bd  call    cs:__imp_LeaveCriticalSection
0x1800375c3  lea     this, [rbp+reacquireLock]; result
0x1800375c7  call    wil__scope_exit__lambda_81d99cb5f16d3e5c5bc1d1ead17aed05___
0x1800375cc  mov     rbx, [rsi+18h]
0x1800375d0  lea     this, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FixNonAtomicAccessInIpidtbl@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FixNonAtomicAccessInIpidtbl@@@details@3@XZ@4V453@A; __annotation("WILSTG:|58977763|Feature_FixNonAtomicAccessInIpidtbl|EnabledByDefault")
0x1800375d7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FixNonAtomicAccessInIpidtbl@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixNonAtomicAccessInIpidtbl>::__private_IsEnabled(void)
0x1800375dc  test    al, al
0x1800375de  jnz     loc_180037CCF
0x1800375e4  mov     eax, [rbx+14Ch]
0x1800375ea  mov     [rsp+60h+arg_10], r12
0x1800375f2  test    al, 2
0x1800375f4  jnz     short loc_180037628
0x1800375f6  mov     rbx, [rsi+18h]
0x1800375fa  lea     this, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FixNonAtomicAccessInIpidtbl@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FixNonAtomicAccessInIpidtbl@@@details@3@XZ@4V453@A; __annotation("WILSTG:|58977763|Feature_FixNonAtomicAccessInIpidtbl|EnabledByDefault")
0x180037601  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FixNonAtomicAccessInIpidtbl@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixNonAtomicAccessInIpidtbl>::__private_IsEnabled(void)
0x180037606  test    al, al
0x180037608  jnz     loc_180037CDB
0x18003760e  mov     eax, [rbx+14Ch]
0x180037614  bt      eax, 12h
0x180037618  jb      short loc_180037628
0x18003761a  cmp     cs:?gEnableAgileProxies@@3HA, r13d; int gEnableAgileProxies
0x180037621  jnz     short loc_180037628
0x180037623  xor     r12b, r12b
0x180037626  jmp     short loc_18003762B
0x180037628  mov     r12b, 1
0x18003762b  test    r14, r14
0x18003762e  jz      loc_180037B90
0x180037634  lea     ppChnl, ??_7CDestObject@@6B@; const CDestObject::`vftable'
0x18003763b  cmp     [rsi+20h], r13
0x18003763f  jnz     loc_180037C05
0x180037645  mov     this, rsi; this
0x180037648  call    ?GetFlags@CStdMarshal@@IEBAKXZ; CStdMarshal::GetFlags(void)
0x18003764d  test    al, 1
0x18003764f  jnz     loc_180037800
0x180037655  mov     rax, gs:30h
0x18003765e  mov     this, [rax+1758h]
0x180037665  test    this, this
0x180037668  jz      loc_180037C1A
0x18003766e  mov     rdi, [this+68h]
0x180037672  test    rdi, rdi
0x180037675  cmovz   rdi, cs:?g_pMTAEmptyCtx@@3PEAVCObjectContext@@EA; CObjectContext * g_pMTAEmptyCtx
0x18003767d  mov     [this+60h], rdi
0x180037681  test    rdi, rdi
0x180037684  jz      short loc_180037694
0x180037686  mov     this, rdi; this
0x180037689  call    ?GetFlags@CObjectContext@@QEBAKXZ; CObjectContext::GetFlags(void)
0x18003768e  bt      eax, 8
0x180037692  jb      short loc_180037697
0x180037694  mov     rdi, r13
0x180037697  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x18003769e  xor     edx, edx; dwFlags
0x1800376a0  mov     r8d, 58h ; 'X'; dwBytes
0x1800376a6  call    cs:__imp_HeapAlloc
0x1800376ac  mov     rbx, rax
0x1800376af  test    rax, rax
0x1800376b2  jz      loc_180037C26
0x1800376b8  mov     rax, [rsi+18h]
0x1800376bc  lea     this, ??_7?$Mixins_BaseForwarderLayer@U?$ForwardedBases@VCCtxComChnl@@$$V@ObjectLibrary@@@Details@ObjectLibrary@@6BIRpcChannelBuffer3@@@; const ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CCtxComChnl,>>::`vftable'{for `IRpcChannelBuffer3'}
0x1800376c3  mov     [rbx], this
0x1800376c6  lea     this, ??_7CCtxComChnl@@6BIAsyncRpcChannelBuffer@@@; const CCtxComChnl::`vftable'{for `IAsyncRpcChannelBuffer'}
0x1800376cd  mov     [rbx+8], this
0x1800376d1  lea     this, ??_7?$Mixins_BaseForwarderLayer@U?$ForwardedBases@VCCtxComChnl@@$$V@ObjectLibrary@@@Details@ObjectLibrary@@6BIRpcChannelBufferMarshalingContext@@@; const ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CCtxComChnl,>>::`vftable'{for `IRpcChannelBufferMarshalingContext'}
0x1800376d8  mov     [rbx+10h], this
0x1800376dc  lea     this, ??_7?$Mixins_BaseForwarderLayer@U?$ForwardedBases@VCCtxComChnl@@$$V@ObjectLibrary@@@Details@ObjectLibrary@@6BIChannelHandleMarshal@@@; const ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CCtxComChnl,>>::`vftable'{for `IChannelHandleMarshal'}
0x1800376e3  mov     [rbx+18h], this
0x1800376e7  lea     this, ??_7CCtxComChnl@@6BIChannelCallObjectInitialization@@@; const CCtxComChnl::`vftable'{for `IChannelCallObjectInitialization'}
0x1800376ee  mov     [rbx+20h], this
0x1800376f2  lea     this, ??_7CCtxComChnl@@6BIChannelProtocolBehavior@@@; const CCtxComChnl::`vftable'{for `IChannelProtocolBehavior'}
0x1800376f9  mov     [rbx+28h], this
0x1800376fd  mov     [rbx+30h], rax
0x180037701  mov     [rbx+38h], r14
0x180037705  mov     [rbx+40h], r12b
0x180037709  call    ?GetCurrentApartmentId@@YAKXZ; GetCurrentApartmentId(void)
0x18003770e  mov     [rbx+44h], eax
0x180037711  lea     r12, ??_7?$Mixins_BaseForwarderLayer@U?$ForwardedBases@VCCtxComChnl@@UIRpcSyntaxNegotiate@@@ObjectLibrary@@@Details@ObjectLibrary@@6BIRpcChannelBuffer3@@@; const ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CCtxComChnl,IRpcSyntaxNegotiate>>::`vftable'{for `IRpcChannelBuffer3'}
0x180037718  lea     rax, ??_7?$Mixins_BaseForwarderLayer@U?$ForwardedBases@VCCtxComChnl@@$$V@ObjectLibrary@@@Details@ObjectLibrary@@6BIRpcChannelBuffer3@@@; const ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CCtxComChnl,>>::`vftable'{for `IRpcChannelBuffer3'}
0x18003771f  mov     [rbx+50h], rdi
0x180037723  mov     [rbx], rax
0x180037726  lea     rax, ??_7CCtxComChnl@@6BIAsyncRpcChannelBuffer@@@; const CCtxComChnl::`vftable'{for `IAsyncRpcChannelBuffer'}
0x18003772d  mov     [rbx+8], rax
0x180037731  lea     rax, ??_7?$Mixins_BaseForwarderLayer@U?$ForwardedBases@VCCtxComChnl@@$$V@ObjectLibrary@@@Details@ObjectLibrary@@6BIRpcChannelBufferMarshalingContext@@@; const ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CCtxComChnl,>>::`vftable'{for `IRpcChannelBufferMarshalingContext'}
0x180037738  mov     [rbx+10h], rax
0x18003773c  lea     rax, ??_7?$Mixins_BaseForwarderLayer@U?$ForwardedBases@VCCtxComChnl@@$$V@ObjectLibrary@@@Details@ObjectLibrary@@6BIChannelHandleMarshal@@@; const ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CCtxComChnl,>>::`vftable'{for `IChannelHandleMarshal'}
0x180037743  mov     [rbx+18h], rax
0x180037747  lea     rax, ??_7CCtxComChnl@@6BIChannelCallObjectInitialization@@@; const CCtxComChnl::`vftable'{for `IChannelCallObjectInitialization'}
0x18003774e  mov     [rbx+20h], rax
0x180037752  lea     rax, ??_7CCtxComChnl@@6BIChannelProtocolBehavior@@@; const CCtxComChnl::`vftable'{for `IChannelProtocolBehavior'}
0x180037759  mov     [rbx+28h], rax
0x18003775d  lea     rax, ??_7CServerChannel@@6BIRpcChannelBuffer3@@@; const CServerChannel::`vftable'{for `IRpcChannelBuffer3'}
0x180037764  mov     [rbx], rax
0x180037767  lea     rax, ??_7CServerChannel@@6BIAsyncRpcChannelBuffer@@@; const CServerChannel::`vftable'{for `IAsyncRpcChannelBuffer'}
0x18003776e  mov     [rbx+8], rax
0x180037772  lea     rax, ??_7CServerChannel@@6BIRpcChannelBufferMarshalingContext@@@; const CServerChannel::`vftable'{for `IRpcChannelBufferMarshalingContext'}
0x180037779  mov     [rbx+10h], rax
0x18003777d  lea     rax, ??_7CServerChannel@@6BIChannelHandleMarshal@@@; const CServerChannel::`vftable'{for `IChannelHandleMarshal'}
0x180037784  mov     [rbx+18h], rax
0x180037788  lea     rax, ??_7CServerChannel@@6BIChannelCallObjectInitialization@@@; const CServerChannel::`vftable'{for `IChannelCallObjectInitialization'}
0x18003778f  mov     [rbx+20h], rax
0x180037793  lea     rax, ??_7CServerChannel@@6BIChannelProtocolBehavior@@@; const CServerChannel::`vftable'{for `IChannelProtocolBehavior'}
0x18003779a  mov     [rbx+28h], rax
0x18003779e  mov     dword ptr [rbx+48h], 1
0x1800377a5  xor     eax, eax
0x1800377a7  lock cmpxchg [rsi+20h], rbx
0x1800377ad  jz      short loc_1800377BE
0x1800377af  mov     rax, [rbx]
0x1800377b2  mov     this, rbx
0x1800377b5  mov     rax, [rax+10h]
0x1800377b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800377be  lea     ppChnl, ??_7CDestObject@@6B@; const CDestObject::`vftable'
0x1800377c5  mov     this, rsi; this
0x1800377c8  call    ?GetFlags@CStdMarshal@@IEBAKXZ; CStdMarshal::GetFlags(void)
0x1800377cd  mov     rbx, [rsi+20h]
0x1800377d1  bt      eax, 0
0x1800377d5  jb      loc_1800379CD
0x1800377db  lea     this, [rbp+reacquireLock]
0x1800377df  mov     [r15], rbx
0x1800377e2  call    wil__details__lambda_call__lambda_81d99cb5f16d3e5c5bc1d1ead17aed05______lambda_call__lambda_81d99cb5f16d3e5c5bc1d1ead17aed05___
0x1800377e7  xor     eax, eax
0x1800377e9  mov     r12, [rsp+60h+arg_10]
0x1800377f1  add     rsp, 60h
0x1800377f5  pop     r15
0x1800377f7  pop     r14
0x1800377f9  pop     r13
0x1800377fb  pop     rdi
0x1800377fc  pop     rsi
0x1800377fd  pop     rbx
0x1800377fe  pop     rbp
0x1800377ff  retn
0x180037800  mov     eax, dword ptr cs:?DcomProtocolVersion_Current@@3UtagCOMVERSION@@B.MajorVersion; tagCOMVERSION const DcomProtocolVersion_Current ...
0x180037806  mov     rdi, [rsi+18h]
0x18003780a  mov     qword ptr [rbp+var_40], 3
0x180037812  mov     qword ptr [rbp+var_40+8], r13
0x180037816  movups  xmm0, [rbp+var_40]
0x18003781a  mov     dword ptr [rbp+var_28._dcomVersion.MajorVersion], eax
0x18003781d  mov     eax, [r14+50h]
0x180037821  mov     [rbp+var_28.__vftable], ppChnl
0x180037825  mov     [rbp+var_28._containerVersion.extensions], r13
0x180037829  movups  xmmword ptr [rbp+var_28._containerVersion.version], xmm0
0x18003782d  test    al, 1
0x18003782f  jz      loc_180037BC7
0x180037835  mov     ebx, [r14+1Ch]
0x180037839  call    cs:__imp_GetCurrentProcessId
0x18003783f  cmp     ebx, eax
0x180037841  mov     ecx, r13d
0x180037844  mov     eax, 3
0x180037849  cmovz   ecx, eax
0x18003784c  mov     [rbp+var_28._dwDestCtx], ecx
0x18003784f  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x180037856  xor     edx, edx; dwFlags
0x180037858  mov     r8d, 0B8h; dwBytes
0x18003785e  call    cs:__imp_HeapAlloc
0x180037864  mov     rbx, rax
0x180037867  test    rax, rax
0x18003786a  jz      loc_180037CE7
0x180037870  lea     this, ??_7?$Mixins_BaseForwarderLayer@U?$ForwardedBases@VCCtxComChnl@@$$V@ObjectLibrary@@@Details@ObjectLibrary@@6BIRpcChannelBuffer3@@@; const ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CCtxComChnl,>>::`vftable'{for `IRpcChannelBuffer3'}
0x180037877  mov     [rax+30h], rdi
0x18003787b  mov     [rax], this
0x18003787e  lea     this, ??_7CCtxComChnl@@6BIAsyncRpcChannelBuffer@@@; const CCtxComChnl::`vftable'{for `IAsyncRpcChannelBuffer'}
0x180037885  mov     [rax+8], this
0x180037889  lea     this, ??_7?$Mixins_BaseForwarderLayer@U?$ForwardedBases@VCCtxComChnl@@$$V@ObjectLibrary@@@Details@ObjectLibrary@@6BIRpcChannelBufferMarshalingContext@@@; const ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CCtxComChnl,>>::`vftable'{for `IRpcChannelBufferMarshalingContext'}
0x180037890  mov     [rax+10h], this
0x180037894  lea     this, ??_7?$Mixins_BaseForwarderLayer@U?$ForwardedBases@VCCtxComChnl@@$$V@ObjectLibrary@@@Details@ObjectLibrary@@6BIChannelHandleMarshal@@@; const ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CCtxComChnl,>>::`vftable'{for `IChannelHandleMarshal'}
0x18003789b  mov     [rax+18h], this
0x18003789f  lea     this, ??_7CCtxComChnl@@6BIChannelCallObjectInitialization@@@; const CCtxComChnl::`vftable'{for `IChannelCallObjectInitialization'}
0x1800378a6  mov     [rax+20h], this
0x1800378aa  lea     this, ??_7CCtxComChnl@@6BIChannelProtocolBehavior@@@; const CCtxComChnl::`vftable'{for `IChannelProtocolBehavior'}
0x1800378b1  mov     [rax+28h], this
0x1800378b5  mov     [rax+38h], r14
0x1800378b9  mov     [rax+40h], r12b
0x1800378bd  call    ?GetCurrentApartmentId@@YAKXZ; GetCurrentApartmentId(void)
0x1800378c2  movups  xmm0, xmmword ptr cs:guidCClientChannelSignature.Data1
0x1800378c9  lea     r12, ??_7?$Mixins_BaseForwarderLayer@U?$ForwardedBases@VCCtxComChnl@@UIRpcSyntaxNegotiate@@@ObjectLibrary@@@Details@ObjectLibrary@@6BIRpcChannelBuffer3@@@; const ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CCtxComChnl,IRpcSyntaxNegotiate>>::`vftable'{for `IRpcChannelBuffer3'}
0x1800378d0  mov     [rbx+44h], eax
0x1800378d3  movsd   xmm1, [rbp+var_28._containerVersion.extensions]
0x1800378d8  lea     rax, ??_7CCtxComChnl@@6BIAsyncRpcChannelBuffer@@@; const CCtxComChnl::`vftable'{for `IAsyncRpcChannelBuffer'}
0x1800378df  mov     [rbx+8], rax
0x1800378e3  lea     rax, ??_7?$Mixins_BaseForwarderLayer@U?$ForwardedBases@VCCtxComChnl@@$$V@ObjectLibrary@@@Details@ObjectLibrary@@6BIRpcChannelBufferMarshalingContext@@@; const ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CCtxComChnl,>>::`vftable'{for `IRpcChannelBufferMarshalingContext'}
0x1800378ea  mov     [rbx+10h], rax
0x1800378ee  lea     rax, ??_7?$Mixins_BaseForwarderLayer@U?$ForwardedBases@VCCtxComChnl@@$$V@ObjectLibrary@@@Details@ObjectLibrary@@6BIChannelHandleMarshal@@@; const ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CCtxComChnl,>>::`vftable'{for `IChannelHandleMarshal'}
0x1800378f5  mov     [rbx+18h], rax
0x1800378f9  lea     rax, ??_7CCtxComChnl@@6BIChannelCallObjectInitialization@@@; const CCtxComChnl::`vftable'{for `IChannelCallObjectInitialization'}
0x180037900  mov     [rbx+20h], rax
0x180037904  lea     rax, ??_7CCtxComChnl@@6BIChannelProtocolBehavior@@@; const CCtxComChnl::`vftable'{for `IChannelProtocolBehavior'}
0x18003790b  mov     [rbx+28h], rax
0x18003790f  lea     rax, ??_7?$Mixins_BaseForwarderLayer@U?$ForwardedBases@UIAsyncRpcChannelBuffer@@UIRpcSyntaxNegotiate@@UICancelMethodCalls@@UIClientSecurity@@UIChannelWrapper@@VIMessageParam@@@ObjectLibrary@@@Details@ObjectLibrary@@6BIChannelWrapper@@@; const ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IAsyncRpcChannelBuffer,IRpcSyntaxNegotiate,ICancelMethodCalls,IClientSecurity,IChannelWrapper,IMessageParam>>::`vftable'{for `IChannelWrapper'}
0x180037916  mov     [rbx+48h], rax
0x18003791a  lea     rax, ??_7CClientChannel@@6BIRpcChannelBuffer3@@@; const CClientChannel::`vftable'{for `IRpcChannelBuffer3'}
0x180037921  mov     [rbx], r12
0x180037924  mov     [rbx], rax
0x180037927  lea     rax, ??_7CClientChannel@@6BIAsyncRpcChannelBuffer@@@; const CClientChannel::`vftable'{for `IAsyncRpcChannelBuffer'}
0x18003792e  mov     [rbx+8], rax
0x180037932  lea     rax, ??_7CClientChannel@@6BIRpcChannelBufferMarshalingContext@@@; const CClientChannel::`vftable'{for `IRpcChannelBufferMarshalingContext'}
0x180037939  mov     [rbx+10h], rax
0x18003793d  lea     rax, ??_7CClientChannel@@6BIChannelHandleMarshal@@@; const CClientChannel::`vftable'{for `IChannelHandleMarshal'}
0x180037944  mov     [rbx+18h], rax
0x180037948  lea     rax, ??_7CClientChannel@@6BIChannelCallObjectInitialization@@@; const CClientChannel::`vftable'{for `IChannelCallObjectInitialization'}
0x18003794f  mov     [rbx+20h], rax
0x180037953  lea     rax, ??_7CClientChannel@@6BIChannelProtocolBehavior@@@; const CClientChannel::`vftable'{for `IChannelProtocolBehavior'}
0x18003795a  mov     [rbx+28h], rax
0x18003795e  lea     rax, ??_7CClientChannel@@6B@; const CClientChannel::`vftable'
0x180037965  mov     [rbx+48h], rax
0x180037969  movups  xmmword ptr [rbx+58h], xmm0
0x18003796d  mov     dword ptr [rbx+50h], 1
0x180037974  mov     eax, [r14+18h]
0x180037978  movups  xmm0, xmmword ptr [rbp+var_28._containerVersion.version]
0x18003797c  mov     [rbx+68h], eax
0x18003797f  lea     rax, ??_7CDestObject@@6B@; const CDestObject::`vftable'
0x180037986  mov     [rbx+70h], rax
0x18003798a  mov     eax, [rbp+var_28._dwDestCtx]
0x18003798d  mov     [rbx+78h], eax
0x180037990  mov     eax, dword ptr [rbp+var_28._dcomVersion.MajorVersion]
0x180037993  mov     [rbx+7Ch], eax
0x180037996  movups  xmmword ptr [rbx+80h], xmm0
0x18003799d  movsd   qword ptr [rbx+90h], xmm1
0x1800379a5  xorps   xmm0, xmm0
0x1800379a8  mov     [rbx+98h], r13
0x1800379af  movups  xmmword ptr [rbp+var_28._containerVersion.version], xmm0
0x1800379b3  mov     [rbx+0A0h], r13
0x1800379ba  mov     [rbx+0A8h], r13
0x1800379c1  mov     [rbx+0B0h], r13
0x1800379c8  jmp     loc_1800377A5
0x1800379cd  mov     eax, dword ptr cs:?DcomProtocolVersion_Current@@3UtagCOMVERSION@@B.MajorVersion; tagCOMVERSION const DcomProtocolVersion_Current ...
0x1800379d3  movzx   edi, byte ptr [rbx+40h]
0x1800379d7  mov     rsi, [rbx+30h]
0x1800379db  mov     qword ptr [rbp+var_40], 3
0x1800379e3  mov     qword ptr [rbp+var_40+8], r13
0x1800379e7  movups  xmm0, [rbp+var_40]
0x1800379eb  mov     dword ptr [rbp+var_28._dcomVersion.MajorVersion], eax
0x1800379ee  mov     eax, [r14+50h]
0x1800379f2  mov     [rbp+var_28.__vftable], ppChnl
0x1800379f6  mov     [rbp+var_28._containerVersion.extensions], r13
0x1800379fa  movups  xmmword ptr [rbp+var_28._containerVersion.version], xmm0
0x1800379fe  test    al, 1
0x180037a00  jz      loc_180037BE4
0x180037a06  mov     ebx, [r14+1Ch]
0x180037a0a  call    cs:__imp_GetCurrentProcessId
0x180037a10  cmp     ebx, eax
0x180037a12  mov     ecx, r13d
0x180037a15  mov     eax, 3
0x180037a1a  cmovz   ecx, eax
0x180037a1d  mov     [rbp+var_28._dwDestCtx], ecx
0x180037a20  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x180037a27  xor     edx, edx; dwFlags
0x180037a29  mov     r8d, 0B8h; dwBytes
0x180037a2f  call    cs:__imp_HeapAlloc
0x180037a35  mov     rbx, rax
0x180037a38  test    rax, rax
0x180037a3b  jz      loc_180037CF6
0x180037a41  lea     rax, ??_7?$Mixins_BaseForwarderLayer@U?$ForwardedBases@VCCtxComChnl@@$$V@ObjectLibrary@@@Details@ObjectLibrary@@6BIRpcChannelBuffer3@@@; const ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CCtxComChnl,>>::`vftable'{for `IRpcChannelBuffer3'}
0x180037a48  mov     [rbx+30h], rsi
0x180037a4c  mov     [rbx], rax
0x180037a4f  lea     rax, ??_7CCtxComChnl@@6BIAsyncRpcChannelBuffer@@@; const CCtxComChnl::`vftable'{for `IAsyncRpcChannelBuffer'}
0x180037a56  mov     [rbx+8], rax
0x180037a5a  lea     rax, ??_7?$Mixins_BaseForwarderLayer@U?$ForwardedBases@VCCtxComChnl@@$$V@ObjectLibrary@@@Details@ObjectLibrary@@6BIRpcChannelBufferMarshalingContext@@@; const ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CCtxComChnl,>>::`vftable'{for `IRpcChannelBufferMarshalingContext'}
0x180037a61  mov     [rbx+10h], rax
0x180037a65  lea     rax, ??_7?$Mixins_BaseForwarderLayer@U?$ForwardedBases@VCCtxComChnl@@$$V@ObjectLibrary@@@Details@ObjectLibrary@@6BIChannelHandleMarshal@@@; const ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CCtxComChnl,>>::`vftable'{for `IChannelHandleMarshal'}
0x180037a6c  mov     [rbx+18h], rax
0x180037a70  lea     rax, ??_7CCtxComChnl@@6BIChannelCallObjectInitialization@@@; const CCtxComChnl::`vftable'{for `IChannelCallObjectInitialization'}
0x180037a77  mov     [rbx+20h], rax
0x180037a7b  lea     rax, ??_7CCtxComChnl@@6BIChannelProtocolBehavior@@@; const CCtxComChnl::`vftable'{for `IChannelProtocolBehavior'}
0x180037a82  mov     [rbx+28h], rax
0x180037a86  mov     [rbx+38h], r14
0x180037a8a  mov     [rbx+40h], dil
0x180037a8e  call    ?GetCurrentApartmentId@@YAKXZ; GetCurrentApartmentId(void)
0x180037a93  movups  xmm0, xmmword ptr cs:guidCClientChannelSignature.Data1
0x180037a9a  mov     [rbx+44h], eax
0x180037a9d  lea     rax, ??_7CCtxComChnl@@6BIAsyncRpcChannelBuffer@@@; const CCtxComChnl::`vftable'{for `IAsyncRpcChannelBuffer'}
  ... truncated ...
```
