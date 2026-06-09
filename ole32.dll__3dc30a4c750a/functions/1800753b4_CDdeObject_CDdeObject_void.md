# CDdeObject::~CDdeObject(void)

- ea: `0x1800753b4`
- end: `0x180075532`
- name: `??1CDdeObject@@AEAA@XZ`
- size: `382`
- prototype: `void __fastcall(CDdeObject *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180075538`

## callees

- `0x180052760`
- `0x1800753b4`
- `0x180075c40`
- `0x180077b54`
- `0x1800ce010`

## import_xrefs

- `KERNELBASE!GlobalFree` at `0x180075405`
- `KERNELBASE!GlobalFree` at `0x180075514`
- `KERNELBASE!GlobalFree` at `0x180075405`
- `KERNELBASE!GlobalFree` at `0x180075514`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800753d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800753f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800753d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800753f3`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x1800754b5`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x1800754c7`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x1800754d9`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x1800754eb`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x1800754b5`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x1800754c7`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x1800754d9`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x1800754eb`

## pseudocode

```c
void __fastcall CDdeObject::~CDdeObject(CDdeObject *this)
{
  DDE_CHANNEL *m_pDocChannel; // r8
  DDE_CHANNEL *m_pSysChannel; // r8
  void *m_hNative; // rcx
  void *m_hPict; // rcx
  void *m_hExtra; // rcx
  IDataAdviseHolder *m_pDataAdvHolder; // rcx
  IOleAdviseHolder *m_pOleAdvHolder; // rcx
  IStorage *m_pstg; // rcx
  ATOM m_aExeName; // cx
  ATOM m_aClass; // cx
  ATOM m_aTopic; // cx
  ATOM m_aItem; // cx
  tagDVTARGETDEVICE *m_ptd; // rcx

  m_pDocChannel = this->m_pDocChannel;
  if ( m_pDocChannel )
    HeapFree(g_hHeap, 0, m_pDocChannel);
  m_pSysChannel = this->m_pSysChannel;
  if ( m_pSysChannel )
    HeapFree(g_hHeap, 0, m_pSysChannel);
  m_hNative = this->m_hNative;
  if ( m_hNative )
    GlobalFree(m_hNative);
  m_hPict = this->m_hPict;
  if ( m_hPict )
    wFreeData(m_hPict, this->m_cfPict, (int)m_pSysChannel);
  m_hExtra = this->m_hExtra;
  if ( m_hExtra )
    wFreeData(m_hExtra, this->m_cfExtra, (int)m_pSysChannel);
  if ( this->m_pOleClientSite )
  {
    CDdeObject::DeclareVisibility(this, 0, (int)m_pSysChannel);
    ((void (__fastcall *)(IOleClientSite *))this->m_pOleClientSite->lpVtbl->Release)(this->m_pOleClientSite);
  }
  m_pDataAdvHolder = this->m_pDataAdvHolder;
  if ( m_pDataAdvHolder )
    ((void (__fastcall *)(IDataAdviseHolder *))m_pDataAdvHolder->lpVtbl->Release)(m_pDataAdvHolder);
  m_pOleAdvHolder = this->m_pOleAdvHolder;
  if ( m_pOleAdvHolder )
    ((void (__fastcall *)(IOleAdviseHolder *))m_pOleAdvHolder->lpVtbl->Release)(m_pOleAdvHolder);
  m_pstg = this->m_pstg;
  if ( m_pstg )
    ((void (__fastcall *)(IStorage *))m_pstg->lpVtbl->Release)(m_pstg);
  m_aExeName = this->m_aExeName;
  if ( m_aExeName )
    GlobalDeleteAtom(m_aExeName);
  m_aClass = this->m_aClass;
  if ( m_aClass )
    GlobalDeleteAtom(m_aClass);
  m_aTopic = this->m_aTopic;
  if ( m_aTopic )
    GlobalDeleteAtom(m_aTopic);
  m_aItem = this->m_aItem;
  if ( m_aItem )
    GlobalDeleteAtom(m_aItem);
  m_ptd = this->m_ptd;
  if ( m_ptd )
    operator delete(m_ptd, 0x10u);
  this->m_chk = 0;
  this->m_ConnectionTable.m_h = GlobalFree(this->m_ConnectionTable.m_h);
  this->m_ConnectionTable.m_cinfo = 0;
}

```

## disassembly

```asm
0x1800753b4  mov     [rsp+arg_0], rbx
0x1800753b9  push    rdi
0x1800753ba  sub     rsp, 20h
0x1800753be  mov     r8, [this+158h]; lpMem
0x1800753c5  xor     edi, edi
0x1800753c7  mov     rbx, this
0x1800753ca  test    r8, r8
0x1800753cd  jz      short loc_1800753DE
0x1800753cf  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800753d6  xor     edx, edx; dwFlags
0x1800753d8  call    cs:__imp_HeapFree
0x1800753de  mov     r8, [rbx+150h]; lpMem
0x1800753e5  test    r8, r8
0x1800753e8  jz      short loc_1800753F9
0x1800753ea  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800753f1  xor     edx, edx; dwFlags
0x1800753f3  call    cs:__imp_HeapFree
0x1800753f9  mov     this, [rbx+0C0h]; hMem
0x180075400  test    this, this
0x180075403  jz      short loc_18007540B
0x180075405  call    cs:__imp_GlobalFree
0x18007540b  mov     this, [rbx+0C8h]; hData
0x180075412  test    this, this
0x180075415  jz      short loc_180075423
0x180075417  movzx   edx, word ptr [rbx+0D8h]; cfFormat
0x18007541e  call    ?wFreeData@@YAXPEAXGH@Z; wFreeData(void *,ushort,int)
0x180075423  mov     this, [rbx+0D0h]; hData
0x18007542a  test    this, this
0x18007542d  jz      short loc_18007543B
0x18007542f  movzx   edx, word ptr [rbx+0DAh]; cfFormat
0x180075436  call    ?wFreeData@@YAXPEAXGH@Z; wFreeData(void *,ushort,int)
0x18007543b  cmp     [rbx+0A8h], rdi
0x180075442  jz      short loc_180075461
0x180075444  xor     edx, edx; f
0x180075446  mov     this, rbx; this
0x180075449  call    ?DeclareVisibility@CDdeObject@@AEAAJHH@Z; CDdeObject::DeclareVisibility(int,int)
0x18007544e  mov     this, [rbx+0A8h]
0x180075455  mov     rax, [this]
0x180075458  mov     rax, [rax+10h]
0x18007545c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075461  mov     this, [rbx+130h]
0x180075468  test    this, this
0x18007546b  jz      short loc_180075479
0x18007546d  mov     rax, [this]
0x180075470  mov     rax, [rax+10h]
0x180075474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075479  mov     this, [rbx+138h]
0x180075480  test    this, this
0x180075483  jz      short loc_180075491
0x180075485  mov     rax, [this]
0x180075488  mov     rax, [rax+10h]
0x18007548c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075491  mov     this, [rbx+0B0h]
0x180075498  test    this, this
0x18007549b  jz      short loc_1800754A9
0x18007549d  mov     rax, [this]
0x1800754a0  mov     rax, [rax+10h]
0x1800754a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800754a9  movzx   ecx, word ptr [rbx+92h]; nAtom
0x1800754b0  test    cx, cx
0x1800754b3  jz      short loc_1800754BB
0x1800754b5  call    cs:__imp_GlobalDeleteAtom
0x1800754bb  movzx   ecx, word ptr [rbx+90h]; nAtom
0x1800754c2  test    cx, cx
0x1800754c5  jz      short loc_1800754CD
0x1800754c7  call    cs:__imp_GlobalDeleteAtom
0x1800754cd  movzx   ecx, word ptr [rbx+94h]; nAtom
0x1800754d4  test    cx, cx
0x1800754d7  jz      short loc_1800754DF
0x1800754d9  call    cs:__imp_GlobalDeleteAtom
0x1800754df  movzx   ecx, word ptr [rbx+96h]; nAtom
0x1800754e6  test    cx, cx
0x1800754e9  jz      short loc_1800754F1
0x1800754eb  call    cs:__imp_GlobalDeleteAtom
0x1800754f1  mov     this, [rbx+110h]; block
0x1800754f8  test    this, this
0x1800754fb  jz      short loc_180075507
0x1800754fd  mov     edx, 10h; __formal
0x180075502  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180075507  mov     [rbx+10Ch], edi
0x18007550d  mov     this, [rbx+140h]; hMem
0x180075514  call    cs:__imp_GlobalFree
0x18007551a  mov     [rbx+140h], rax
0x180075521  mov     [rbx+148h], edi
0x180075527  mov     rbx, [rsp+28h+arg_0]
0x18007552c  add     rsp, 20h
0x180075530  pop     rdi
0x180075531  retn
```
