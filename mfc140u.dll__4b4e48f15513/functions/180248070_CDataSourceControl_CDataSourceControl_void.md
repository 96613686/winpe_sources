# CDataSourceControl::~CDataSourceControl(void)

- ea: `0x180248070`
- end: `0x1802483b1`
- name: `??1CDataSourceControl@@UEAA@XZ`
- size: `833`
- prototype: `void __fastcall(CDataSourceControl *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x180244090`

## callees

- `0x180008410`
- `0x180243298`
- `0x180248070`
- `0x18024bcac`
- `0x1802c49fc`
- `0x1802c7020`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x1802481c4`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1802481d1`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1802482ce`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1802482dc`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180248316`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180248324`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1802481c4`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1802481d1`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1802482ce`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1802482dc`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180248316`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180248324`
- `ole32!CoTaskMemFree` at `0x180248277`
- `ole32!CoTaskMemFree` at `0x180248286`
- `ole32!CoTaskMemFree` at `0x1802482b2`
- `ole32!CoTaskMemFree` at `0x1802482c0`
- `ole32!CoTaskMemFree` at `0x1802482fa`
- `ole32!CoTaskMemFree` at `0x180248308`
- `ole32!CoTaskMemFree` at `0x180248277`
- `ole32!CoTaskMemFree` at `0x180248286`
- `ole32!CoTaskMemFree` at `0x1802482b2`
- `ole32!CoTaskMemFree` at `0x1802482c0`
- `ole32!CoTaskMemFree` at `0x1802482fa`
- `ole32!CoTaskMemFree` at `0x180248308`
- `OLEAUT32!__imp_VariantClear` at `0x1802481a7`
- `OLEAUT32!__imp_VariantClear` at `0x1802481a7`

## pseudocode

```c
void __fastcall CDataSourceControl::~CDataSourceControl(CDataSourceControl *this)
{
  ATL::CRowset<ATL::CAccessorBase> *m_pRowset; // rcx
  unsigned int *data; // rbx
  int v4; // ebx
  __int64 m_nBindings; // rax
  bool v6; // zf
  __int64 v7; // rcx
  __int64 v8; // rax
  ICursorMove *m_pCursorMove; // rcx
  ICursorUpdateARow *m_pCursorUpdateARow; // rcx
  int v11; // esi
  __int64 v12; // rbx
  CPtrList::CNode *m_pNodeHead; // rdx
  _QWORD *v14; // rax
  CPtrList *m_pClientList; // rcx
  void *m_pVarData; // rcx
  ATL::CDynamicAccessor *m_pDynamicAccessor; // rcx
  ATL::CDynamicAccessor *v18; // rbx
  ATL::CDynamicAccessor *v19; // rbx
  ATL::CRowset<ATL::CAccessorBase> *v20; // rbx
  IRowPosition *m_pRowPosition; // rcx
  IDataSource *m_pDataSource; // rcx
  IConnectionPoint *pConnPt; // [rsp+40h] [rbp+8h] BYREF
  IConnectionPointContainer *pConnPtCont; // [rsp+48h] [rbp+10h] BYREF

  this->__vftable = (CDataSourceControl_vtbl *)CDataSourceControl::`vftable';
  if ( this->m_dwRowsetNotify )
  {
    m_pRowset = this->m_pRowset;
    if ( m_pRowset )
    {
      if ( ((__int64 (__fastcall *)(IRowset *, GUID *, IConnectionPointContainer **))m_pRowset->m_spRowset.p->QueryInterface)(
             m_pRowset->m_spRowset.p,
             &IID_IConnectionPointContainer,
             &pConnPtCont) >= 0
        && pConnPtCont )
      {
        pConnPt = 0;
        if ( pConnPtCont->FindConnectionPoint(pConnPtCont, &IID_IRowsetNotify, &pConnPt) >= 0 && pConnPt )
        {
          pConnPt->Unadvise(pConnPt, this->m_dwRowsetNotify);
          pConnPt->Release(pConnPt);
        }
        pConnPtCont->Release(pConnPtCont);
      }
    }
  }
  while ( this->m_CursorBoundProps.m_nCount )
  {
    data = (unsigned int *)this->m_CursorBoundProps.m_pNodeHead->data;
    if ( !data || !*(_QWORD *)data )
      break;
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**(_QWORD **)data + 392LL))(*(_QWORD *)data, data[3], 0);
    *(_QWORD *)(*(_QWORD *)data + 232LL) = 0;
  }
  CList<CMFCPropertyPage *,CMFCPropertyPage *>::RemoveAll((CList<IControlSiteFactory *,IControlSiteFactory *> *)&this->m_CursorBoundProps);
  if ( this->m_pValues )
  {
    v4 = 0;
    m_nBindings = this->m_nBindings;
    v6 = m_nBindings == 0;
    if ( m_nBindings > 0 )
    {
      v7 = 0;
      do
      {
        VariantClear(&this->m_pValues[v7]);
        v7 = ++v4;
        v8 = this->m_nBindings;
      }
      while ( v4 < v8 );
      v6 = v8 == 0;
    }
    if ( !v6 )
    {
      free(this->m_pColumnBindings);
      free(this->m_pValues);
    }
  }
  m_pCursorMove = this->m_pCursorMove;
  if ( m_pCursorMove )
    m_pCursorMove->Release(m_pCursorMove);
  m_pCursorUpdateARow = this->m_pCursorUpdateARow;
  if ( m_pCursorUpdateARow )
    m_pCursorUpdateARow->Release(m_pCursorUpdateARow);
  if ( this->m_pMetaRowData )
  {
    v11 = 0;
    if ( this->m_nColumns > 0 )
    {
      v12 = 0;
      do
      {
        m_pNodeHead = this->m_pMetaRowData[v12].m_pClientList->m_pNodeHead;
        while ( m_pNodeHead )
        {
          v14 = m_pNodeHead->data;
          m_pNodeHead = m_pNodeHead->pNext;
          v14[29] = 0;
        }
        CList<CMFCPropertyPage *,CMFCPropertyPage *>::RemoveAll((CList<IControlSiteFactory *,IControlSiteFactory *> *)this->m_pMetaRowData[v12].m_pClientList);
        m_pClientList = this->m_pMetaRowData[v12].m_pClientList;
        if ( m_pClientList )
          ((void (__fastcall *)(CPtrList *, __int64))m_pClientList->~CObject)(m_pClientList, 1);
        ++v11;
        ++v12;
      }
      while ( v11 < this->m_nColumns );
    }
    CoTaskMemFree(this->m_pMetaRowData);
  }
  m_pVarData = this->m_pVarData;
  if ( m_pVarData )
    CoTaskMemFree(m_pVarData);
  m_pDynamicAccessor = this->m_pDynamicAccessor;
  if ( m_pDynamicAccessor )
  {
    ATL::CDynamicAccessor::ReleaseAccessors(m_pDynamicAccessor, this->m_pRowset->m_spRowset.p);
    v18 = this->m_pDynamicAccessor;
    CoTaskMemFree(v18->m_pColumnInfo);
    v18->m_pColumnInfo = 0;
    CoTaskMemFree(v18->m_pStringsBuffer);
    v18->m_pStringsBuffer = 0;
    free(v18->m_pBuffer);
    v18->m_pBuffer = 0;
    free(v18->m_pfClientOwnedMemRef);
    v18->m_pfClientOwnedMemRef = 0;
    v18->m_nColumns = 0;
  }
  v19 = this->m_pDynamicAccessor;
  if ( v19 )
  {
    CoTaskMemFree(v19->m_pColumnInfo);
    v19->m_pColumnInfo = 0;
    CoTaskMemFree(v19->m_pStringsBuffer);
    v19->m_pStringsBuffer = 0;
    free(v19->m_pBuffer);
    v19->m_pBuffer = 0;
    free(v19->m_pfClientOwnedMemRef);
    v19->m_pfClientOwnedMemRef = 0;
    v19->m_nColumns = 0;
    operator delete(v19, 0x48u);
  }
  v20 = this->m_pRowset;
  if ( v20 )
  {
    ATL::CRowset<ATL::CAccessorBase>::~CRowset<ATL::CAccessorBase>(this->m_pRowset);
    operator delete(v20, 0x28u);
  }
  m_pRowPosition = this->m_pRowPosition;
  if ( m_pRowPosition )
    m_pRowPosition->Release(m_pRowPosition);
  m_pDataSource = this->m_pDataSource;
  if ( m_pDataSource )
    m_pDataSource->Release(m_pDataSource);
  this->m_CursorBoundProps.__vftable = (CPtrList_vtbl *)CPtrList::`vftable';
  CList<CMFCPropertyPage *,CMFCPropertyPage *>::RemoveAll((CList<IControlSiteFactory *,IControlSiteFactory *> *)&this->m_CursorBoundProps);
}

```

## disassembly

```asm
0x180248070  mov     [rsp+arg_10], rbx
0x180248075  push    rbp
0x180248076  push    rsi
0x180248077  push    rdi
0x180248078  sub     rsp, 20h
0x18024807c  mov     rdi, this
0x18024807f  lea     rax, ??_7CDataSourceControl@@6B@; const CDataSourceControl::`vftable'
0x180248086  mov     [this], rax
0x180248089  xor     ebp, ebp
0x18024808b  cmp     [this+0B0h], ebp
0x180248091  jz      loc_180248172
0x180248097  mov     this, [this+0A0h]
0x18024809e  test    this, this
0x1802480a1  jz      loc_180248172
0x1802480a7  mov     this, [this]
0x1802480aa  mov     rax, [this]
0x1802480ad  lea     r8, [rsp+38h+pConnPtCont]
0x1802480b2  lea     rdx, IID_IConnectionPointContainer
0x1802480b9  mov     rax, [rax]
0x1802480bc  call    cs:__guard_dispatch_icall_fptr
0x1802480c2  test    eax, eax
0x1802480c4  js      loc_180248172
0x1802480ca  mov     this, [rsp+38h+pConnPtCont]
0x1802480cf  test    this, this
0x1802480d2  jz      loc_180248172
0x1802480d8  mov     [rsp+38h+pConnPt], rbp
0x1802480dd  mov     rax, [this]
0x1802480e0  lea     r8, [rsp+38h+pConnPt]
0x1802480e5  lea     rdx, IID_IRowsetNotify
0x1802480ec  mov     rax, [rax+20h]
0x1802480f0  call    cs:__guard_dispatch_icall_fptr
0x1802480f6  test    eax, eax
0x1802480f8  js      short loc_180248129
0x1802480fa  mov     this, [rsp+38h+pConnPt]
0x1802480ff  test    this, this
0x180248102  jz      short loc_180248129
0x180248104  mov     rax, [this]
0x180248107  mov     edx, [rdi+0B0h]
0x18024810d  mov     rax, [rax+30h]
0x180248111  call    cs:__guard_dispatch_icall_fptr
0x180248117  mov     this, [rsp+38h+pConnPt]
0x18024811c  mov     rax, [this]
0x18024811f  mov     rax, [rax+10h]
0x180248123  call    cs:__guard_dispatch_icall_fptr
0x180248129  mov     this, [rsp+38h+pConnPtCont]
0x18024812e  mov     rax, [this]
0x180248131  mov     rax, [rax+10h]
0x180248135  call    cs:__guard_dispatch_icall_fptr
0x18024813b  jmp     short loc_180248172
0x18024813d  mov     rax, [rdi+38h]
0x180248141  mov     rbx, [rax+10h]
0x180248145  test    rbx, rbx
0x180248148  jz      short loc_180248178
0x18024814a  mov     this, [rbx]
0x18024814d  test    this, this
0x180248150  jz      short loc_180248178
0x180248152  mov     rax, [this]
0x180248155  xor     r8d, r8d
0x180248158  mov     edx, [rbx+0Ch]
0x18024815b  mov     rax, [rax+188h]
0x180248162  call    cs:__guard_dispatch_icall_fptr
0x180248168  mov     rax, [rbx]
0x18024816b  mov     [rax+0E8h], rbp
0x180248172  cmp     [rdi+48h], rbp
0x180248176  jnz     short loc_18024813D
0x180248178  lea     this, [rdi+30h]; this
0x18024817c  call    ?RemoveAll@?$CList@PEAVCMFCPropertyPage@@PEAV1@@@QEAAXXZ; CList<CMFCPropertyPage *,CMFCPropertyPage *>::RemoveAll(void)
0x180248181  cmp     [rdi+80h], rbp
0x180248188  jz      short loc_1802481D7
0x18024818a  mov     ebx, ebp
0x18024818c  mov     rax, [rdi+70h]
0x180248190  test    rax, rax
0x180248193  jle     short loc_1802481BE
0x180248195  mov     this, rbp
0x180248198  lea     this, [this+this*2]
0x18024819c  mov     rax, [rdi+80h]
0x1802481a3  lea     this, [rax+this*8]; pvarg
0x1802481a7  call    cs:__imp_VariantClear
0x1802481ad  inc     ebx
0x1802481af  movsxd  this, ebx
0x1802481b2  mov     rax, [rdi+70h]
0x1802481b6  cmp     this, rax
0x1802481b9  jl      short loc_180248198
0x1802481bb  test    rax, rax
0x1802481be  jz      short loc_1802481D7
0x1802481c0  mov     this, [rdi+78h]; Block
0x1802481c4  call    cs:__imp_free
0x1802481ca  mov     this, [rdi+80h]; Block
0x1802481d1  call    cs:__imp_free
0x1802481d7  mov     this, [rdi+10h]
0x1802481db  test    this, this
0x1802481de  jz      short loc_1802481ED
0x1802481e0  mov     rax, [this]
0x1802481e3  mov     rax, [rax+10h]
0x1802481e7  call    cs:__guard_dispatch_icall_fptr
0x1802481ed  mov     this, [rdi+18h]
0x1802481f1  test    this, this
0x1802481f4  jz      short loc_180248203
0x1802481f6  mov     rax, [this]
0x1802481f9  mov     rax, [rax+10h]
0x1802481fd  call    cs:__guard_dispatch_icall_fptr
0x180248203  cmp     [rdi+28h], rbp
0x180248207  jz      short loc_18024827D
0x180248209  mov     esi, ebp
0x18024820b  cmp     [rdi+20h], rbp
0x18024820f  jle     short loc_180248273
0x180248211  mov     rbx, rbp
0x180248214  mov     rax, [rdi+28h]
0x180248218  mov     this, [rbx+rax+38h]
0x18024821d  mov     rdx, [this+8]
0x180248221  jmp     short loc_180248231
0x180248223  mov     rax, [rdx+10h]
0x180248227  mov     rdx, [rdx]
0x18024822a  mov     [rax+0E8h], rbp
0x180248231  test    rdx, rdx
0x180248234  jnz     short loc_180248223
0x180248236  mov     this, [rdi+28h]
0x18024823a  mov     this, [rbx+this+38h]; this
0x18024823f  call    ?RemoveAll@?$CList@PEAVCMFCPropertyPage@@PEAV1@@@QEAAXXZ; CList<CMFCPropertyPage *,CMFCPropertyPage *>::RemoveAll(void)
0x180248244  mov     rax, [rdi+28h]
0x180248248  mov     this, [rbx+rax+38h]
0x18024824d  test    this, this
0x180248250  jz      short loc_180248264
0x180248252  mov     rax, [this]
0x180248255  mov     edx, 1
0x18024825a  mov     rax, [rax+8]
0x18024825e  call    cs:__guard_dispatch_icall_fptr
0x180248264  inc     esi
0x180248266  add     rbx, 40h ; '@'
0x18024826a  movsxd  rax, esi
0x18024826d  cmp     rax, [rdi+20h]
0x180248271  jl      short loc_180248214
0x180248273  mov     this, [rdi+28h]; pv
0x180248277  call    cs:__imp_CoTaskMemFree
0x18024827d  mov     this, [rdi+68h]; pv
0x180248281  test    this, this
0x180248284  jz      short loc_18024828C
0x180248286  call    cs:__imp_CoTaskMemFree
0x18024828c  mov     this, [rdi+0A8h]; this
0x180248293  test    this, this
0x180248296  jz      short loc_1802482EA
0x180248298  mov     rdx, [rdi+0A0h]
0x18024829f  mov     rdx, [rdx]; pUnk
0x1802482a2  call    ?ReleaseAccessors@CDynamicAccessor@ATL@@QEAAJPEAUIUnknown@@@Z; ATL::CDynamicAccessor::ReleaseAccessors(IUnknown *)
0x1802482a7  mov     rbx, [rdi+0A8h]
0x1802482ae  mov     this, [rbx+28h]; pv
0x1802482b2  call    cs:__imp_CoTaskMemFree
0x1802482b8  mov     [rbx+28h], rbp
0x1802482bc  mov     this, [rbx+30h]; pv
0x1802482c0  call    cs:__imp_CoTaskMemFree
0x1802482c6  mov     [rbx+30h], rbp
0x1802482ca  mov     this, [rbx+10h]; Block
0x1802482ce  call    cs:__imp_free
0x1802482d4  mov     [rbx+10h], rbp
0x1802482d8  mov     this, [rbx+20h]; Block
0x1802482dc  call    cs:__imp_free
0x1802482e2  mov     [rbx+20h], rbp
0x1802482e6  mov     [rbx+18h], rbp
0x1802482ea  mov     rbx, [rdi+0A8h]
0x1802482f1  test    rbx, rbx
0x1802482f4  jz      short loc_18024833F
0x1802482f6  mov     this, [rbx+28h]; pv
0x1802482fa  call    cs:__imp_CoTaskMemFree
0x180248300  mov     [rbx+28h], rbp
0x180248304  mov     this, [rbx+30h]; pv
0x180248308  call    cs:__imp_CoTaskMemFree
0x18024830e  mov     [rbx+30h], rbp
0x180248312  mov     this, [rbx+10h]; Block
0x180248316  call    cs:__imp_free
0x18024831c  mov     [rbx+10h], rbp
0x180248320  mov     this, [rbx+20h]; Block
0x180248324  call    cs:__imp_free
0x18024832a  mov     [rbx+20h], rbp
0x18024832e  mov     [rbx+18h], rbp
0x180248332  mov     edx, 48h ; 'H'; __formal
0x180248337  mov     this, rbx; block
0x18024833a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18024833f  mov     rbx, [rdi+0A0h]
0x180248346  test    rbx, rbx
0x180248349  jz      short loc_180248360
0x18024834b  mov     this, rbx; this
0x18024834e  call    ??1?$CRowset@VCAccessorBase@ATL@@@ATL@@QEAA@XZ; ATL::CRowset<ATL::CAccessorBase>::~CRowset<ATL::CAccessorBase>(void)
0x180248353  mov     edx, 28h ; '('; __formal
0x180248358  mov     this, rbx; block
0x18024835b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180248360  mov     this, [rdi+98h]
0x180248367  test    this, this
0x18024836a  jz      short loc_180248379
0x18024836c  mov     rax, [this]
0x18024836f  mov     rax, [rax+10h]
0x180248373  call    cs:__guard_dispatch_icall_fptr
0x180248379  mov     this, [rdi+90h]
0x180248380  test    this, this
0x180248383  jz      short loc_180248392
0x180248385  mov     rax, [this]
0x180248388  mov     rax, [rax+10h]
0x18024838c  call    cs:__guard_dispatch_icall_fptr
0x180248392  lea     this, [rdi+30h]
0x180248396  lea     rax, ??_7CPtrList@@6B@; const CPtrList::`vftable'
0x18024839d  mov     [this], rax
0x1802483a0  mov     rbx, [rsp+38h+arg_10]
0x1802483a5  add     rsp, 20h
0x1802483a9  pop     rdi
0x1802483aa  pop     rsi
0x1802483ab  pop     rbp
0x1802483ac  jmp     ?RemoveAll@?$CList@PEAVCMFCPropertyPage@@PEAV1@@@QEAAXXZ; CList<CMFCPropertyPage *,CMFCPropertyPage *>::RemoveAll(void)
```
