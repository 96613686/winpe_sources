# CIDObject::SetZombie(ulong)

- ea: `0x1800357a8`
- end: `0x180035bf1`
- name: `?SetZombie@CIDObject@@AEAAXK@Z`
- size: `1097`
- prototype: `void __fastcall(CIDObject *this, unsigned int dwIDFlag)`
- caller_count: `4`
- callee_count: `10`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180034ec0`
- `0x180095924`
- `0x180109740`
- `0x180139208`

## callees

- `0x180006250`
- `0x180006390`
- `0x18000712c`
- `0x1800357a8`
- `0x180036038`
- `0x180036044`
- `0x180093c90`
- `0x180179024`
- `0x180199d80`
- `0x180255010`

## import_xrefs

- `ntdll!RtlDelete` at `0x180035b8a`
- `ntdll!RtlDelete` at `0x180035be2`
- `ntdll!RtlDelete` at `0x180035b8a`
- `ntdll!RtlDelete` at `0x180035be2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035abd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035abd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035896`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003596c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035896`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003596c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180035b08`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180035b08`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180035a66`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180035a66`

## string_xrefs

- `0x1800357be`: `onecore\com\combase\dcomrem\idobj.cxx`
- `0x180035b62`: `onecore\com\combase\verifier\tracking.cxx`
- `0x1800358fd`: `onecore\com\combase\dcomrem\ctxconnmgr.cxx`

## pseudocode

```c
void __fastcall CIDObject::SetZombie(CIDObject *this, unsigned int dwIDFlag, __int64 a3, const char *a4)
{
  const char *v6; // r9
  unsigned int dwState; // ecx
  _RTL_SPLAY_LINKS *pvObjectTrackCookie; // rdi
  SHashChain *pNext; // rcx
  bool v10; // zf
  _DWORD *ReservedForOle; // rdi
  int v12; // ebx
  CObjectContext *v13; // rcx
  CObjectContext *v14; // rcx
  IUnknown *pServer; // r12
  _DWORD *v16; // r14
  int v17; // edi
  CObjectContext *pServerCtx; // rdi
  CObjectContext *v19; // rcx
  int iFirst; // ebx
  _tagSCtxListIndex *pIndex; // rdx
  __int64 idx; // rax
  __int64 v23; // rcx
  IUnknown *v24; // rbx
  CCtxConnectionManager *pConnectionMgr; // rdi
  utl::set<IUnknown *,utl::less<IUnknown *>,utl::allocator<IUnknown *> > *p_objects; // r14
  utl::_TreeNode<IUnknown *> *MyEncodedParentAndColor; // rax
  utl::_TreeNode<IUnknown *> *v28; // r15
  __int64 v29; // rcx
  HANDLE v30; // rcx
  _RTL_SPLAY_LINKS *v31; // r14
  _RTL_SPLAY_LINKS *LeftChild; // rbx
  void *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v34; // [rsp+50h] [rbp+8h] BYREF

  COleStaticMutexSem::Request(&gComLock, "onecore\\com\\combase\\dcomrem\\idobj.cxx", 0x1A8u, a4);
  if ( dwIDFlag == 4096 )
  {
    if ( !this->_pStdWrapper )
      this->_dwState |= 0x1000u;
  }
  else if ( !this->_pStdID )
  {
    this->_dwState |= dwIDFlag;
  }
  dwState = this->_dwState;
  if ( (dwState & 0x3000) != 0x3000 || this->_cLocks || (dwState & 0x10000) != 0 )
  {
    COleStaticMutexSem::Release(&gComLock);
  }
  else
  {
    pvObjectTrackCookie = (_RTL_SPLAY_LINKS *)this->_pvObjectTrackCookie;
    pNext = (SHashChain *)(dwState | 0x10000);
    this->_dwState = (unsigned int)pNext;
    if ( pvObjectTrackCookie )
    {
      v31 = 0;
      COleStaticMutexSem::Request(&gObjectTrackingLock, "onecore\\com\\combase\\verifier\\tracking.cxx", 0x1BAu, v6);
      LeftChild = pvObjectTrackCookie[1].LeftChild;
      if ( LeftChild )
      {
        v10 = LODWORD(LeftChild[1].LeftChild)-- == 1;
        if ( v10 )
        {
          gpVtblRoot = (VtblSplayNode *)RtlDelete(LeftChild);
          v31 = LeftChild;
        }
      }
      if ( ComVerifierSettings::s_singleton._pSettingsState
        && ComVerifierSettings::s_singleton._pSettingsState->_fEnableObjectTracking )
      {
        gpObjectRoot = (ObjectSplayNode *)RtlDelete(pvObjectTrackCookie);
      }
      COleStaticMutexSem::Release(&gObjectTrackingLock);
      operator delete(pvObjectTrackCookie, 0x28u);
      if ( v31 )
        operator delete(v31, 0x28u);
    }
    v10 = (this->_dwState & 2) == 0;
    this->_pvObjectTrackCookie = 0;
    if ( v10 )
    {
      if ( !--gComLock._cLocks && gComLock._lockOrder != Highest )
      {
        ReservedForOle = NtCurrentTeb()->ReservedForOle;
        if ( ReservedForOle )
        {
          LOBYTE(pNext) = gComLock._lockOrder;
          v12 = 1 << gComLock._lockOrder;
          if ( ((1 << gComLock._lockOrder) & ReservedForOle[144]) == 0 )
            MicrosoftTelemetryAssertTriggeredNoArgs(pNext);
          ReservedForOle[144] &= ~v12;
        }
      }
      LeaveCriticalSection(&gComLock._cs);
    }
    else
    {
      if ( (this->_dwState & 0x10) != 0 )
      {
        this->_pidChain.pPrev->pNext = this->_pidChain.pNext;
        pNext = this->_pidChain.pNext;
        pNext->pPrev = this->_pidChain.pPrev;
        --CPIDTable::s_PIDHashTbl._cCurEntries;
        this->_dwState &= ~0x10u;
      }
      if ( !--gComLock._cLocks && gComLock._lockOrder != Highest )
      {
        v16 = NtCurrentTeb()->ReservedForOle;
        if ( v16 )
        {
          LOBYTE(pNext) = gComLock._lockOrder;
          v17 = 1 << gComLock._lockOrder;
          if ( ((1 << gComLock._lockOrder) & v16[144]) == 0 )
            MicrosoftTelemetryAssertTriggeredNoArgs(pNext);
          v16[144] &= ~v17;
        }
      }
      LeaveCriticalSection(&gComLock._cs);
      if ( (this->_dwState & 0x400000) == 0 )
      {
        pServerCtx = this->_pServerCtx;
        v34 = 0;
        if ( (CObjectContext::GetFlags(pServerCtx) & 1) != 0 )
          iFirst = pServerCtx->_properties._iFirst;
        else
          iFirst = -1;
        CObjectContext::GetFlags(v19);
        while ( pServerCtx->_properties._Count && iFirst != -1 )
        {
          pIndex = pServerCtx->_properties._pIndex;
          idx = pIndex[iFirst].idx;
          iFirst = iFirst == pServerCtx->_properties._iLast ? -1 : pIndex[iFirst].next;
          v23 = (__int64)&pServerCtx->_properties._pProps[idx];
          if ( !v23 )
            break;
          if ( (*(_BYTE *)(v23 + 16) & 8) != 0
            && !(***(unsigned int (__fastcall ****)(_QWORD, GUID *, __int64 *))(v23 + 24))(
                  *(_QWORD *)(v23 + 24),
                  &IID_IPolicyMaker,
                  &v34) )
          {
            (*(void (__fastcall **)(__int64, CIDObject *))(*(_QWORD *)v34 + 64LL))(v34, this);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
          }
        }
      }
    }
    if ( this->_pServer )
    {
      v14 = this->_pServerCtx;
      if ( v14 )
      {
        if ( (CObjectContext::GetFlags(v14) & 0x100) != 0 )
        {
          pServer = this->_pServer;
          if ( !pServer )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              0x48u,
              "onecore\\com\\combase\\dcomrem\\ctxconnmgr.cxx");
          v24 = 0;
          pConnectionMgr = this->_pServerCtx->_pConnectionMgr;
          AcquireSRWLockExclusive(&pConnectionMgr->_pUnkList._lock.SRWLock_);
          p_objects = &pConnectionMgr->_pUnkList._objects;
          if ( (utl::set<IUnknown *,utl::less<IUnknown *>,utl::allocator<IUnknown *> > *)pConnectionMgr->_pUnkList._objects._MyHead._MyChild[1] != &pConnectionMgr->_pUnkList._objects )
          {
            MyEncodedParentAndColor = p_objects->_MyHead._MyEncodedParentAndColor;
            v28 = (utl::_TreeNode<IUnknown *> *)&pConnectionMgr->_pUnkList._objects;
            do
            {
              if ( MyEncodedParentAndColor->_MyVal >= pServer )
              {
                v28 = MyEncodedParentAndColor;
                v29 = 8;
              }
              else
              {
                v29 = 16;
              }
              MyEncodedParentAndColor = *(utl::_TreeNode<IUnknown *> **)((char *)&MyEncodedParentAndColor->_MyEncodedParentAndColor
                                                                       + v29);
            }
            while ( MyEncodedParentAndColor != (utl::_TreeNode<IUnknown *> *)&utl::_TreeSentinel );
            if ( v28 != (utl::_TreeNode<IUnknown *> *)p_objects && pServer >= v28->_MyVal )
            {
              utl::_TreeNodeHeader<IUnknown *>::_HeadUnlinkNode(&pConnectionMgr->_pUnkList._objects._MyHead, v28);
              v30 = g_hHeap;
              --pConnectionMgr->_pUnkList._objects._MyInfo._MyRealVal;
              HeapFree(v30, 0, v28);
              v24 = pServer;
            }
          }
          if ( pConnectionMgr )
            ReleaseSRWLockExclusive(&pConnectionMgr->_pUnkList._lock.SRWLock_);
          if ( v24 )
            v24->Release(v24);
        }
      }
    }
    v13 = this->_pServerCtx;
    if ( v13 )
    {
      _InterlockedDecrement(&v13->_cInternalRefs);
      CObjectContext::CommonRelease(v13);
    }
    this->_pServerCtx = 0;
    this->_pServer = 0;
  }
}

```

## disassembly

```asm
0x1800357a8  mov     [rsp+arg_10], rbx
0x1800357ad  push    rbp
0x1800357ae  push    rdi
0x1800357af  push    r12
0x1800357b1  push    r14
0x1800357b3  push    r15
0x1800357b5  sub     rsp, 20h
0x1800357b9  mov     ebx, dwIDFlag
0x1800357bb  mov     rbp, this
0x1800357be  lea     rdx, aOnecoreComComb_136; "onecore\\com\\combase\\dcomrem\\idobj.c"...
0x1800357c5  mov     r8d, 1A8h; dwLine
0x1800357cb  lea     this, ?gComLock@@3VCOleStaticMutexSem@@A; this
0x1800357d2  call    ?Request@COleStaticMutexSem@@QEAAXPEBDK0@Z; COleStaticMutexSem::Request(char const *,ulong,char const *)
0x1800357d7  mov     eax, 1000h
0x1800357dc  cmp     ebx, eax
0x1800357de  jz      loc_180035AF2
0x1800357e4  cmp     qword ptr [rbp+60h], 0
0x1800357e9  jnz     short loc_1800357EE
0x1800357eb  or      [rbp+28h], ebx
0x1800357ee  mov     ecx, [rbp+28h]
0x1800357f1  mov     dwIDFlag, 3000h
0x1800357f6  mov     eax, ecx
0x1800357f8  and     eax, dwIDFlag
0x1800357fa  cmp     eax, dwIDFlag
0x1800357fc  jnz     loc_180035A45
0x180035802  cmp     dword ptr [rbp+6Ch], 0
0x180035806  jnz     loc_180035A45
0x18003580c  mov     eax, 10000h
0x180035811  test    eax, ecx
0x180035813  jnz     loc_180035A45
0x180035819  mov     rdi, [rbp+88h]
0x180035820  or      ecx, eax
0x180035822  or      r15d, 0FFFFFFFFh
0x180035826  mov     [rbp+28h], ecx
0x180035829  test    rdi, rdi
0x18003582c  jnz     loc_180035B5C
0x180035832  test    byte ptr [rbp+28h], 2
0x180035836  mov     qword ptr [rbp+88h], 0
0x180035841  jnz     loc_18003590F
0x180035847  add     cs:?gComLock@@3VCOleStaticMutexSem@@A._cLocks, r15d; COleStaticMutexSem gComLock ...
0x18003584e  jnz     short loc_18003588F
0x180035850  cmp     cs:?gComLock@@3VCOleStaticMutexSem@@A._lockOrder, 13h; COleStaticMutexSem gComLock ...
0x180035857  jz      short loc_18003588F
0x180035859  mov     rax, gs:30h
0x180035862  mov     rdi, [rax+1758h]
0x180035869  test    rdi, rdi
0x18003586c  jz      short loc_18003588F
0x18003586e  mov     cl, cs:?gComLock@@3VCOleStaticMutexSem@@A._lockOrder; COleStaticMutexSem gComLock ...
0x180035874  mov     ebx, 1
0x180035879  shl     ebx, cl
0x18003587b  test    [rdi+240h], ebx
0x180035881  jz      loc_180035B48
0x180035887  not     ebx
0x180035889  and     [rdi+240h], ebx
0x18003588f  lea     this, ?gComLock@@3VCOleStaticMutexSem@@A._cs; lpCriticalSection
0x180035896  call    cs:__imp_LeaveCriticalSection
0x18003589c  cmp     qword ptr [rbp+30h], 0
0x1800358a1  jnz     short loc_1800358D7
0x1800358a3  mov     this, [rbp+38h]; this
0x1800358a7  test    this, this
0x1800358aa  jz      short loc_1800358B5
0x1800358ac  lock dec dword ptr [this+40h]
0x1800358b0  call    ?CommonRelease@CObjectContext@@QEAAKXZ; CObjectContext::CommonRelease(void)
0x1800358b5  mov     qword ptr [rbp+38h], 0
0x1800358bd  mov     qword ptr [rbp+30h], 0
0x1800358c5  mov     rbx, [rsp+48h+arg_10]
0x1800358ca  add     rsp, 20h
0x1800358ce  pop     r15
0x1800358d0  pop     r14
0x1800358d2  pop     r12
0x1800358d4  pop     rdi
0x1800358d5  pop     rbp
0x1800358d6  retn
0x1800358d7  mov     this, [rbp+38h]; this
0x1800358db  test    this, this
0x1800358de  jz      short loc_1800358A3
0x1800358e0  call    ?GetFlags@CObjectContext@@QEBAKXZ; CObjectContext::GetFlags(void)
0x1800358e5  bt      eax, 8
0x1800358e9  jnb     short loc_1800358A3
0x1800358eb  mov     r12, [rbp+30h]
0x1800358ef  test    r12, r12
0x1800358f2  jnz     loc_180035A56
0x1800358f8  mov     this, [rsp+48h]; callerReturnAddress
0x1800358fd  lea     r8, aOnecoreComComb_110; "onecore\\com\\combase\\dcomrem\\ctxconn"...
0x180035904  lea     dwIDFlag, [r12+48h]; lineNumber
0x180035909  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18003590f  test    byte ptr [rbp+28h], 10h
0x180035913  jnz     loc_180035B10
0x180035919  add     cs:?gComLock@@3VCOleStaticMutexSem@@A._cLocks, r15d; COleStaticMutexSem gComLock ...
0x180035920  mov     ebx, 1
0x180035925  jnz     short loc_180035965
0x180035927  cmp     cs:?gComLock@@3VCOleStaticMutexSem@@A._lockOrder, 13h; COleStaticMutexSem gComLock ...
0x18003592e  jz      short loc_180035965
0x180035930  mov     rax, gs:30h
0x180035939  mov     r14, [rax+1758h]
0x180035940  test    r14, r14
0x180035943  jz      short loc_180035965
0x180035945  mov     cl, cs:?gComLock@@3VCOleStaticMutexSem@@A._lockOrder; COleStaticMutexSem gComLock ...
0x18003594b  mov     edi, ebx
0x18003594d  shl     edi, cl
0x18003594f  test    [r14+240h], edi
0x180035956  jz      loc_180035B52
0x18003595c  not     edi
0x18003595e  and     [r14+240h], edi
0x180035965  lea     this, ?gComLock@@3VCOleStaticMutexSem@@A._cs; lpCriticalSection
0x18003596c  call    cs:__imp_LeaveCriticalSection
0x180035972  test    dword ptr [rbp+28h], 400000h
0x180035979  jnz     loc_18003589C
0x18003597f  mov     rdi, [rbp+38h]
0x180035983  mov     this, rdi; this
0x180035986  mov     [rsp+48h+arg_0], 0
0x18003598f  call    ?GetFlags@CObjectContext@@QEBAKXZ; CObjectContext::GetFlags(void)
0x180035994  test    bl, al
0x180035996  jz      loc_180035B40
0x18003599c  mov     ebx, [rdi+0D4h]
0x1800359a2  call    ?GetFlags@CObjectContext@@QEBAKXZ; CObjectContext::GetFlags(void)
0x1800359a7  cmp     dword ptr [rdi+0DCh], 0
0x1800359ae  jz      loc_18003589C
0x1800359b4  cmp     ebx, 0FFFFFFFFh
0x1800359b7  jz      loc_18003589C
0x1800359bd  mov     rdx, [rdi+108h]
0x1800359c4  mov     r8, [rdi+0F0h]
0x1800359cb  movsxd  rax, ebx
0x1800359ce  lea     this, [rax+rax*2]
0x1800359d2  movsxd  rax, dword ptr [rdx+this*4]
0x1800359d6  cmp     ebx, [rdi+0D8h]
0x1800359dc  jnz     loc_180035B37
0x1800359e2  or      ebx, 0FFFFFFFFh
0x1800359e5  shl     rax, 5
0x1800359e9  lea     this, [rax+r8]
0x1800359ed  test    this, this
0x1800359f0  jz      loc_18003589C
0x1800359f6  test    byte ptr [this+10h], 8
0x1800359fa  jz      short loc_1800359A7
0x1800359fc  mov     this, [this+18h]
0x180035a00  lea     r8, [rsp+48h+arg_0]
0x180035a05  lea     rdx, IID_IPolicyMaker
0x180035a0c  mov     rax, [this]
0x180035a0f  mov     rax, [rax]
0x180035a12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035a17  test    eax, eax
0x180035a19  jnz     short loc_1800359A7
0x180035a1b  mov     this, [rsp+48h+arg_0]
0x180035a20  mov     rdx, rbp
0x180035a23  mov     rax, [this]
0x180035a26  mov     rax, [rax+40h]
0x180035a2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035a2f  mov     this, [rsp+48h+arg_0]
0x180035a34  mov     rax, [this]
0x180035a37  mov     rax, [rax+10h]
0x180035a3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035a40  jmp     loc_1800359A7
0x180035a45  lea     this, ?gComLock@@3VCOleStaticMutexSem@@A; this
0x180035a4c  call    ?Release@COleStaticMutexSem@@QEAAXXZ; COleStaticMutexSem::Release(void)
0x180035a51  jmp     loc_1800358C5
0x180035a56  mov     rdi, [rbp+38h]
0x180035a5a  xor     ebx, ebx
0x180035a5c  mov     rdi, [rdi+120h]
0x180035a63  mov     this, rdi; SRWLock
0x180035a66  call    cs:__imp_AcquireSRWLockExclusive
0x180035a6c  lea     r14, [rdi+8]
0x180035a70  cmp     [r14+10h], r14
0x180035a74  jz      short loc_180035AC6
0x180035a76  mov     rax, [r14]
0x180035a79  mov     r15, r14
0x180035a7c  cmp     [rax+18h], r12
0x180035a80  jnb     short loc_180035AE8
0x180035a82  mov     ecx, 10h
0x180035a87  mov     rax, [rax+this]
0x180035a8b  lea     this, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x180035a92  cmp     rax, this
0x180035a95  jnz     short loc_180035A7C
0x180035a97  cmp     r15, r14
0x180035a9a  jz      short loc_180035AC6
0x180035a9c  cmp     r12, [r15+18h]
0x180035aa0  jb      short loc_180035AC6
0x180035aa2  mov     rdx, r15; _DeadPtr
0x180035aa5  mov     this, r14; this
0x180035aa8  call    ?_HeadUnlinkNode@?$_TreeNodeHeader@PEAUIUnknown@@@utl@@QEAAXPEAU?$_TreeNode@PEAUIUnknown@@@2@@Z; utl::_TreeNodeHeader<IUnknown *>::_HeadUnlinkNode(utl::_TreeNode<IUnknown *> *)
0x180035aad  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x180035ab4  mov     r8, r15; lpMem
0x180035ab7  dec     qword ptr [r14+18h]
0x180035abb  xor     dwIDFlag, dwIDFlag; dwFlags
0x180035abd  call    cs:__imp_HeapFree
0x180035ac3  mov     rbx, r12
0x180035ac6  test    rdi, rdi
0x180035ac9  jnz     short loc_180035B05
0x180035acb  test    rbx, rbx
0x180035ace  jz      loc_1800358A3
0x180035ad4  mov     rax, [rbx]
0x180035ad7  mov     this, rbx
0x180035ada  mov     rax, [rax+10h]
0x180035ade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035ae3  jmp     loc_1800358A3
0x180035ae8  mov     r15, rax
0x180035aeb  mov     ecx, 8
0x180035af0  jmp     short loc_180035A87
0x180035af2  cmp     qword ptr [rbp+58h], 0
0x180035af7  jnz     loc_1800357EE
0x180035afd  or      [rbp+28h], eax
0x180035b00  jmp     loc_1800357EE
0x180035b05  mov     this, rdi; SRWLock
0x180035b08  call    cs:__imp_ReleaseSRWLockExclusive
0x180035b0e  jmp     short loc_180035ACB
0x180035b10  mov     this, [rbp+10h]
0x180035b14  mov     rax, [rbp+8]
0x180035b18  mov     [this], rax
0x180035b1b  mov     this, [rbp+8]
0x180035b1f  mov     rax, [rbp+10h]
0x180035b23  mov     [this+8], rax
0x180035b27  add     cs:?s_PIDHashTbl@CPIDTable@@0VCPIDHashTable@@A._cCurEntries, r15d; CPIDHashTable CPIDTable::s_PIDHashTbl ...
0x180035b2e  and     dword ptr [rbp+28h], 0FFFFFFEFh
0x180035b32  jmp     loc_180035919
0x180035b37  mov     ebx, [rdx+this*4+4]
0x180035b3b  jmp     loc_1800359E5
0x180035b40  or      ebx, 0FFFFFFFFh
0x180035b43  jmp     loc_1800359A2
0x180035b48  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "lockFlag & _locksHeldByThread")
0x180035b4d  jmp     loc_180035887
0x180035b52  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "lockFlag & _locksHeldByThread")
0x180035b57  jmp     loc_18003595C
0x180035b5c  mov     r8d, 1BAh; dwLine
0x180035b62  lea     rdx, aOnecoreComComb_32; "onecore\\com\\combase\\verifier\\tracki"...
0x180035b69  lea     this, ?gObjectTrackingLock@@3VCOleStaticMutexSem@@A; this
0x180035b70  xor     r14d, r14d
0x180035b73  call    ?Request@COleStaticMutexSem@@QEAAXPEBDK0@Z; COleStaticMutexSem::Request(char const *,ulong,char const *)
0x180035b78  mov     rbx, [rdi+20h]
0x180035b7c  test    rbx, rbx
0x180035b7f  jz      short loc_180035B9A
0x180035b81  add     [rbx+20h], r15d
0x180035b85  jnz     short loc_180035B9A
0x180035b87  mov     this, rbx; Links
0x180035b8a  call    cs:__imp_RtlDelete
0x180035b90  mov     cs:?gpVtblRoot@@3PEAUVtblSplayNode@@EA, rax; VtblSplayNode * gpVtblRoot
0x180035b97  mov     r14, rbx
0x180035b9a  mov     rax, cs:?s_singleton@ComVerifierSettings@@0V1@A._pSettingsState; ComVerifierSettings ComVerifierSettings::s_singleton ...
0x180035ba1  test    rax, rax
0x180035ba4  jnz     short loc_180035BD9
0x180035ba6  lea     this, ?gObjectTrackingLock@@3VCOleStaticMutexSem@@A; this
0x180035bad  call    ?Release@COleStaticMutexSem@@QEAAXXZ; COleStaticMutexSem::Release(void)
0x180035bb2  mov     ebx, 28h ; '('
0x180035bb7  mov     this, rdi; block
0x180035bba  mov     dwIDFlag, ebx; __formal
0x180035bbc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180035bc1  test    r14, r14
0x180035bc4  jz      loc_180035832
0x180035bca  mov     dwIDFlag, ebx; __formal
0x180035bcc  mov     this, r14; block
0x180035bcf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180035bd4  jmp     loc_180035832
0x180035bd9  cmp     byte ptr [rax+0Ah], 0
0x180035bdd  jz      short loc_180035BA6
0x180035bdf  mov     this, rdi; Links
0x180035be2  call    cs:__imp_RtlDelete
0x180035be8  mov     cs:?gpObjectRoot@@3PEAUObjectSplayNode@@EA, rax; ObjectSplayNode * gpObjectRoot
0x180035bef  jmp     short loc_180035BA6
```
