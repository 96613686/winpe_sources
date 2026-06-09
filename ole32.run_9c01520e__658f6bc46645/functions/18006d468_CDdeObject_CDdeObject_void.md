# CDdeObject::~CDdeObject(void)

- ea: `0x18006d468`
- end: `0x18006d617`
- name: `??1CDdeObject@@AEAA@XZ`
- size: `431`
- prototype: `void __fastcall(CDdeObject *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18006d620`

## callees

- `0x180046854`
- `0x18006d468`
- `0x18006ddc0`
- `0x180070364`
- `0x1800d8010`

## import_xrefs

- `KERNELBASE!GlobalFree` at `0x18006d4c5`
- `KERNELBASE!GlobalFree` at `0x18006d5f2`
- `KERNELBASE!GlobalFree` at `0x18006d4c5`
- `KERNELBASE!GlobalFree` at `0x18006d5f2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006d48c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006d4ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006d48c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006d4ad`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18006d57b`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18006d593`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18006d5ab`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18006d5c3`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18006d57b`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18006d593`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18006d5ab`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18006d5c3`

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
0x18006d468  mov     [rsp+arg_0], rbx
0x18006d46d  push    rdi
0x18006d46e  sub     rsp, 20h
0x18006d472  mov     r8, [this+158h]; lpMem
0x18006d479  xor     edi, edi
0x18006d47b  mov     rbx, this
0x18006d47e  test    r8, r8
0x18006d481  jz      short loc_18006D498
0x18006d483  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x18006d48a  xor     edx, edx; dwFlags
0x18006d48c  call    cs:__imp_HeapFree
0x18006d493  nop     dword ptr [rax+rax+00h]
0x18006d498  mov     r8, [rbx+150h]; lpMem
0x18006d49f  test    r8, r8
0x18006d4a2  jz      short loc_18006D4B9
0x18006d4a4  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x18006d4ab  xor     edx, edx; dwFlags
0x18006d4ad  call    cs:__imp_HeapFree
0x18006d4b4  nop     dword ptr [rax+rax+00h]
0x18006d4b9  mov     this, [rbx+0C0h]; hMem
0x18006d4c0  test    this, this
0x18006d4c3  jz      short loc_18006D4D1
0x18006d4c5  call    cs:__imp_GlobalFree
0x18006d4cc  nop     dword ptr [rax+rax+00h]
0x18006d4d1  mov     this, [rbx+0C8h]; hData
0x18006d4d8  test    this, this
0x18006d4db  jz      short loc_18006D4E9
0x18006d4dd  movzx   edx, word ptr [rbx+0D8h]; cfFormat
0x18006d4e4  call    ?wFreeData@@YAXPEAXGH@Z; wFreeData(void *,ushort,int)
0x18006d4e9  mov     this, [rbx+0D0h]; hData
0x18006d4f0  test    this, this
0x18006d4f3  jz      short loc_18006D501
0x18006d4f5  movzx   edx, word ptr [rbx+0DAh]; cfFormat
0x18006d4fc  call    ?wFreeData@@YAXPEAXGH@Z; wFreeData(void *,ushort,int)
0x18006d501  cmp     [rbx+0A8h], rdi
0x18006d508  jz      short loc_18006D527
0x18006d50a  xor     edx, edx; f
0x18006d50c  mov     this, rbx; this
0x18006d50f  call    ?DeclareVisibility@CDdeObject@@AEAAJHH@Z; CDdeObject::DeclareVisibility(int,int)
0x18006d514  mov     this, [rbx+0A8h]
0x18006d51b  mov     rax, [this]
0x18006d51e  mov     rax, [rax+10h]
0x18006d522  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d527  mov     this, [rbx+130h]
0x18006d52e  test    this, this
0x18006d531  jz      short loc_18006D53F
0x18006d533  mov     rax, [this]
0x18006d536  mov     rax, [rax+10h]
0x18006d53a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d53f  mov     this, [rbx+138h]
0x18006d546  test    this, this
0x18006d549  jz      short loc_18006D557
0x18006d54b  mov     rax, [this]
0x18006d54e  mov     rax, [rax+10h]
0x18006d552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d557  mov     this, [rbx+0B0h]
0x18006d55e  test    this, this
0x18006d561  jz      short loc_18006D56F
0x18006d563  mov     rax, [this]
0x18006d566  mov     rax, [rax+10h]
0x18006d56a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d56f  movzx   ecx, word ptr [rbx+92h]; nAtom
0x18006d576  test    cx, cx
0x18006d579  jz      short loc_18006D587
0x18006d57b  call    cs:__imp_GlobalDeleteAtom
0x18006d582  nop     dword ptr [rax+rax+00h]
0x18006d587  movzx   ecx, word ptr [rbx+90h]; nAtom
0x18006d58e  test    cx, cx
0x18006d591  jz      short loc_18006D59F
0x18006d593  call    cs:__imp_GlobalDeleteAtom
0x18006d59a  nop     dword ptr [rax+rax+00h]
0x18006d59f  movzx   ecx, word ptr [rbx+94h]; nAtom
0x18006d5a6  test    cx, cx
0x18006d5a9  jz      short loc_18006D5B7
0x18006d5ab  call    cs:__imp_GlobalDeleteAtom
0x18006d5b2  nop     dword ptr [rax+rax+00h]
0x18006d5b7  movzx   ecx, word ptr [rbx+96h]; nAtom
0x18006d5be  test    cx, cx
0x18006d5c1  jz      short loc_18006D5CF
0x18006d5c3  call    cs:__imp_GlobalDeleteAtom
0x18006d5ca  nop     dword ptr [rax+rax+00h]
0x18006d5cf  mov     this, [rbx+110h]; block
0x18006d5d6  test    this, this
0x18006d5d9  jz      short loc_18006D5E5
0x18006d5db  mov     edx, 10h; __formal
0x18006d5e0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006d5e5  mov     [rbx+10Ch], edi
0x18006d5eb  mov     this, [rbx+140h]; hMem
0x18006d5f2  call    cs:__imp_GlobalFree
0x18006d5f9  nop     dword ptr [rax+rax+00h]
0x18006d5fe  mov     [rbx+140h], rax
0x18006d605  mov     [rbx+148h], edi
0x18006d60b  mov     rbx, [rsp+28h+arg_0]
0x18006d610  add     rsp, 20h
0x18006d614  pop     rdi
0x18006d615  retn
```
