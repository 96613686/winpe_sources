# CDefClient::~CDefClient(void)

- ea: `0x1800796c4`
- end: `0x180079816`
- name: `??1CDefClient@@AEAA@XZ`
- size: `338`
- prototype: `void __fastcall(CDefClient *this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180075790`

## callees

- `0x180074770`
- `0x180074894`
- `0x180076570`
- `0x180078848`
- `0x1800796c4`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800797c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800797c3`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180079723`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180079772`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180079723`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180079772`
- `USER32!IsWindow` at `0x1800797e0`
- `USER32!IsWindow` at `0x1800797e0`
- `USER32!DestroyWindow` at `0x1800797f4`
- `USER32!DestroyWindow` at `0x1800797f4`

## pseudocode

```c
void __fastcall CDefClient::~CDefClient(CDefClient *this)
{
  CDefClient *m_pdoc; // rsi
  CDefClient *v3; // rcx
  CDefClient *i; // rdi
  ATOM m_aItem; // cx
  CDDEServer *m_psrvrParent; // rcx
  ATOM v7; // cx
  ILockBytes *m_plkbytNative; // rcx
  IStorage *m_pstgNative; // rcx
  tagDVTARGETDEVICE *m_ptd; // r8

  m_pdoc = this->m_pdoc;
  CDefClient::ReleaseObjPtrs(this);
  v3 = this->m_pdoc;
  if ( v3 )
  {
    if ( m_pdoc != this )
    {
      ((void (__fastcall *)(IUnknown *))v3->m_pUnkOuter->lpVtbl->Release)(v3->m_pUnkOuter);
      goto LABEL_14;
    }
  }
  else if ( m_pdoc != this )
  {
    goto LABEL_14;
  }
  for ( i = this->m_lpNextItem; i; i = i->m_lpNextItem )
  {
    m_aItem = i->m_aItem;
    if ( m_aItem >= 0xC000u )
      GlobalDeleteAtom(m_aItem);
    CDefClient::DeleteAdviseInfo(i);
  }
  if ( this->m_fRunningInSDI )
  {
    m_psrvrParent = this->m_psrvrParent;
    if ( m_psrvrParent )
    {
      if ( CDDEServer::QueryRevokeClassFactory(m_psrvrParent) )
        CDDEServer::Revoke(this->m_psrvrParent);
    }
  }
LABEL_14:
  v7 = this->m_aItem;
  if ( v7 >= 0xC000u )
    GlobalDeleteAtom(v7);
  m_plkbytNative = this->m_plkbytNative;
  if ( m_plkbytNative )
    ((void (__fastcall *)(ILockBytes *))m_plkbytNative->lpVtbl->Release)(m_plkbytNative);
  m_pstgNative = this->m_pstgNative;
  if ( m_pstgNative )
    ((void (__fastcall *)(IStorage *))m_pstgNative->lpVtbl->Release)(m_pstgNative);
  m_ptd = this->m_ptd;
  if ( m_ptd )
    HeapFree(g_hHeap, 0, m_ptd);
  CDefClient::DeleteAdviseInfo(this);
  if ( m_pdoc == this )
  {
    if ( IsWindow(this->m_hwnd) )
      DestroyWindow(this->m_hwnd);
  }
}

```

## disassembly

```asm
0x1800796c4  mov     [rsp+arg_0], rbx
0x1800796c9  mov     [rsp+arg_8], rbp
0x1800796ce  mov     [rsp+arg_10], rsi
0x1800796d3  push    rdi
0x1800796d4  sub     rsp, 20h
0x1800796d8  mov     rsi, [this+110h]
0x1800796df  mov     rbx, this
0x1800796e2  call    ?ReleaseObjPtrs@CDefClient@@QEAAJXZ; CDefClient::ReleaseObjPtrs(void)
0x1800796e7  mov     this, [rbx+110h]
0x1800796ee  mov     ebp, 0C000h
0x1800796f3  test    this, this
0x1800796f6  jz      short loc_18007970F
0x1800796f8  cmp     rsi, rbx
0x1800796fb  jz      short loc_180079714
0x1800796fd  mov     this, [this+38h]
0x180079701  mov     rax, [this]
0x180079704  mov     rax, [rax+10h]
0x180079708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007970d  jmp     short loc_180079769
0x18007970f  cmp     rsi, rbx
0x180079712  jnz     short loc_180079769
0x180079714  mov     rdi, [rbx+68h]
0x180079718  jmp     short loc_18007973B
0x18007971a  movzx   ecx, word ptr [rdi+5Ch]; nAtom
0x18007971e  cmp     cx, bp
0x180079721  jb      short loc_18007972F
0x180079723  call    cs:__imp_GlobalDeleteAtom
0x18007972a  nop     dword ptr [rax+rax+00h]
0x18007972f  mov     this, rdi; this
0x180079732  call    ?DeleteAdviseInfo@CDefClient@@QEAAXXZ; CDefClient::DeleteAdviseInfo(void)
0x180079737  mov     rdi, [rdi+68h]
0x18007973b  test    rdi, rdi
0x18007973e  jnz     short loc_18007971A
0x180079740  cmp     [rbx+0E0h], edi
0x180079746  jz      short loc_180079769
0x180079748  mov     this, [rbx+0E8h]; this
0x18007974f  test    this, this
0x180079752  jz      short loc_180079769
0x180079754  call    ?QueryRevokeClassFactory@CDDEServer@@QEAAHXZ; CDDEServer::QueryRevokeClassFactory(void)
0x180079759  test    eax, eax
0x18007975b  jz      short loc_180079769
0x18007975d  mov     this, [rbx+0E8h]; this
0x180079764  call    ?Revoke@CDDEServer@@QEAAJXZ; CDDEServer::Revoke(void)
0x180079769  movzx   ecx, word ptr [rbx+5Ch]; nAtom
0x18007976d  cmp     cx, bp
0x180079770  jb      short loc_18007977E
0x180079772  call    cs:__imp_GlobalDeleteAtom
0x180079779  nop     dword ptr [rax+rax+00h]
0x18007977e  mov     this, [rbx+0D0h]
0x180079785  test    this, this
0x180079788  jz      short loc_180079796
0x18007978a  mov     rax, [this]
0x18007978d  mov     rax, [rax+10h]
0x180079791  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079796  mov     this, [rbx+0D8h]
0x18007979d  test    this, this
0x1800797a0  jz      short loc_1800797AE
0x1800797a2  mov     rax, [this]
0x1800797a5  mov     rax, [rax+10h]
0x1800797a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800797ae  mov     r8, [rbx+0F0h]; lpMem
0x1800797b5  test    r8, r8
0x1800797b8  jz      short loc_1800797CF
0x1800797ba  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800797c1  xor     edx, edx; dwFlags
0x1800797c3  call    cs:__imp_HeapFree
0x1800797ca  nop     dword ptr [rax+rax+00h]
0x1800797cf  mov     this, rbx; this
0x1800797d2  call    ?DeleteAdviseInfo@CDefClient@@QEAAXXZ; CDefClient::DeleteAdviseInfo(void)
0x1800797d7  cmp     rsi, rbx
0x1800797da  jnz     short loc_180079800
0x1800797dc  mov     this, [rbx+78h]; hWnd
0x1800797e0  call    cs:__imp_IsWindow
0x1800797e7  nop     dword ptr [rax+rax+00h]
0x1800797ec  test    eax, eax
0x1800797ee  jz      short loc_180079800
0x1800797f0  mov     this, [rbx+78h]; hWnd
0x1800797f4  call    cs:__imp_DestroyWindow
0x1800797fb  nop     dword ptr [rax+rax+00h]
0x180079800  mov     rbx, [rsp+28h+arg_0]
0x180079805  mov     rbp, [rsp+28h+arg_8]
0x18007980a  mov     rsi, [rsp+28h+arg_10]
0x18007980f  add     rsp, 20h
0x180079813  pop     rdi
0x180079814  retn
```
