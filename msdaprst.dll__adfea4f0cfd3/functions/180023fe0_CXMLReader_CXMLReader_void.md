# CXMLReader::~CXMLReader(void)

- ea: `0x180023fe0`
- end: `0x180024141`
- name: `??1CXMLReader@@QEAA@XZ`
- size: `353`
- prototype: `void __fastcall(CXMLReader *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013dec`

## callees

- `0x1800213b8`
- `0x180023ea4`
- `0x180023f54`
- `0x180023fe0`
- `0x180024188`
- `0x1800286bc`
- `0x1800294d4`
- `0x180031010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800240f6`
- `OLEAUT32!__imp_SysFreeString` at `0x180024109`
- `OLEAUT32!__imp_SysFreeString` at `0x1800240f6`
- `OLEAUT32!__imp_SysFreeString` at `0x180024109`
- `MSDART!MPDeleteCriticalSection` at `0x180024135`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CXMLReader::~CXMLReader(CXMLReader *this)
{
  unsigned int v2; // edx
  CNodePool *v3; // rcx

  *(_QWORD *)this = &CXMLReader::`vftable';
  ReleaseDataConvert(*((struct IDataConvert **)this + 61));
  if ( *((_DWORD *)this + 108) )
    CXMLReader::ReduceStack(this, **((struct CParseNode ***)this + 53));
  v3 = (CNodePool *)*((_QWORD *)this + 51);
  if ( v3 )
  {
    if ( !*((_QWORD *)v3 + 1) )
      goto LABEL_7;
    do
    {
      v3 = (CNodePool *)*((_QWORD *)v3 + 1);
      *((_QWORD *)this + 51) = v3;
    }
    while ( *((_QWORD *)v3 + 1) );
    if ( v3 )
LABEL_7:
      CNodePool::`scalar deleting destructor'(v3, v2);
  }
  *((_QWORD *)this + 62) = &CXMLReader::CNotUpdt_BidGeneric::`vftable';
  if ( *((_DWORD *)this + 126) && bidID != -1 )
    ((void (__fastcall *)(__int64, wchar_t *, __int64, _QWORD, _QWORD))off_180043128)(
      bidID,
      `CXMLReader::CNotUpdt_BidGeneric::BidRecycleID'::`7'::_bidPtrSA_053_477[0],
      7,
      *((int *)this + 126),
      0);
  *((_DWORD *)this + 126) = 0;
  CDynamicArray::~CDynamicArray((CXMLReader *)((char *)this + 416));
  CCollectionList::~CCollectionList((CXMLReader *)((char *)this + 352));
  CCollectionList::~CCollectionList((CXMLReader *)((char *)this + 304));
  CCollectionList::~CCollectionList((CXMLReader *)((char *)this + 256));
  CCollectionList::~CCollectionList((CXMLReader *)((char *)this + 208));
  CCollectionList::~CCollectionList((CXMLReader *)((char *)this + 160));
  SysFreeString(*((BSTR *)this + 19));
  SysFreeString(*((BSTR *)this + 18));
  CScope::~CScope((CXMLReader *)((char *)this + 80));
  CScope::~CScope((CXMLReader *)((char *)this + 24));
  MPDeleteCriticalSection((char *)this + 16);
}

```

## disassembly

```asm
0x180023fe0  mov     [rsp+arg_0], rbx
0x180023fe5  push    rdi
0x180023fe6  sub     rsp, 30h
0x180023fea  mov     rbx, rcx
0x180023fed  lea     rax, ??_7CXMLReader@@6B@; const CXMLReader::`vftable'
0x180023ff4  mov     [rcx], rax
0x180023ff7  mov     rcx, [rcx+1E8h]; struct IDataConvert *
0x180023ffe  call    ?ReleaseDataConvert@@YAXPEAUIDataConvert@@@Z; ReleaseDataConvert(IDataConvert *)
0x180024003  lea     rdi, [rbx+1A0h]
0x18002400a  cmp     dword ptr [rdi+10h], 0
0x18002400e  jz      short loc_180024022
0x180024010  mov     rdx, [rbx+1A8h]
0x180024017  mov     rdx, [rdx]; struct CParseNode *
0x18002401a  mov     rcx, rbx; this
0x18002401d  call    ?ReduceStack@CXMLReader@@AEAAXPEAVCParseNode@@@Z; CXMLReader::ReduceStack(CParseNode *)
0x180024022  mov     rcx, [rbx+198h]
0x180024029  test    rcx, rcx
0x18002402c  jz      short loc_180024052
0x18002402e  cmp     qword ptr [rcx+8], 0
0x180024033  jz      short loc_18002404C
0x180024035  mov     rcx, [rcx+8]; this
0x180024039  mov     [rbx+198h], rcx
0x180024040  cmp     qword ptr [rcx+8], 0
0x180024045  jnz     short loc_180024035
0x180024047  test    rcx, rcx
0x18002404a  jz      short loc_180024052
0x18002404c  call    ??_GCNodePool@@QEAAPEAXI@Z; CNodePool::`scalar deleting destructor'(uint)
0x180024051  nop
0x180024052  lea     rax, ??_7CNotUpdt_BidGeneric@CXMLReader@@6B@; const CXMLReader::CNotUpdt_BidGeneric::`vftable'
0x180024059  mov     [rbx+1F0h], rax
0x180024060  movsxd  rdx, dword ptr [rbx+1F8h]
0x180024067  test    edx, edx
0x180024069  jz      short loc_1800240A1
0x18002406b  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x180024073  jz      short loc_1800240A1
0x180024075  mov     rax, cs:off_180043128
0x18002407c  mov     r9, rdx
0x18002407f  mov     [rsp+38h+var_18], 0
0x180024088  mov     r8d, 7
0x18002408e  mov     rdx, cs:?_bidPtrSA_053_477@?6??BidRecycleID@CNotUpdt_BidGeneric@CXMLReader@@AEAAHXZ@4REBGEB; ushort const * const `CXMLReader::CNotUpdt_BidGeneric::BidRecycleID(void)'::`7'::_bidPtrSA_053_477
0x180024095  mov     rcx, cs:_bidID
0x18002409c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800240a1  mov     dword ptr [rbx+1F8h], 0
0x1800240ab  mov     rcx, rdi; this
0x1800240ae  call    ??1CDynamicArray@@QEAA@XZ; CDynamicArray::~CDynamicArray(void)
0x1800240b3  lea     rcx, [rbx+160h]; this
0x1800240ba  call    ??1CCollectionList@@QEAA@XZ; CCollectionList::~CCollectionList(void)
0x1800240bf  lea     rcx, [rbx+130h]; this
0x1800240c6  call    ??1CCollectionList@@QEAA@XZ; CCollectionList::~CCollectionList(void)
0x1800240cb  lea     rcx, [rbx+100h]; this
0x1800240d2  call    ??1CCollectionList@@QEAA@XZ; CCollectionList::~CCollectionList(void)
0x1800240d7  lea     rcx, [rbx+0D0h]; this
0x1800240de  call    ??1CCollectionList@@QEAA@XZ; CCollectionList::~CCollectionList(void)
0x1800240e3  lea     rcx, [rbx+0A0h]; this
0x1800240ea  call    ??1CCollectionList@@QEAA@XZ; CCollectionList::~CCollectionList(void)
0x1800240ef  mov     rcx, [rbx+98h]; bstrString
0x1800240f6  call    cs:__imp_SysFreeString
0x1800240fd  nop     dword ptr [rax+rax+00h]
0x180024102  mov     rcx, [rbx+90h]; bstrString
0x180024109  call    cs:__imp_SysFreeString
0x180024110  nop     dword ptr [rax+rax+00h]
0x180024115  lea     rcx, [rbx+50h]; this
0x180024119  call    ??1CScope@@QEAA@XZ; CScope::~CScope(void)
0x18002411e  lea     rcx, [rbx+18h]; this
0x180024122  call    ??1CScope@@QEAA@XZ; CScope::~CScope(void)
0x180024127  lea     rcx, [rbx+10h]
0x18002412b  mov     rbx, [rsp+38h+arg_0]
0x180024130  add     rsp, 30h
0x180024134  pop     rdi
0x180024135  jmp     cs:__imp_MPDeleteCriticalSection
```
