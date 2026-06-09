# CResourceManager::~CResourceManager(void)

- ea: `0x180059864`
- end: `0x1800598e9`
- name: `??1CResourceManager@@QEAA@XZ`
- size: `133`
- prototype: `void __fastcall(CResourceManager *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180055fac`

## callees

- `0x180059a6c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005988c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800598a1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800598b6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005988c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800598a1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800598b6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CResourceManager::~CResourceManager(CResourceManager *this)
{
  CResourceManager::EmptyLists(this);
  *((_QWORD *)this + 32) = &CSemExclusive::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 264));
  *((_QWORD *)this + 25) = &CSemExclusive::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 208));
  *((_QWORD *)this + 18) = &CSemExclusive::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  *((_QWORD *)this + 14) = &UTStaticList<CPartnerPair *>::`vftable';
  *((_QWORD *)this + 10) = &UTStaticList<CPartnerPair *>::`vftable';
  *((_QWORD *)this + 6) = &UTStaticList<CPartnerPair *>::`vftable';
}

```

## disassembly

```asm
0x180059864  mov     [rsp+arg_0], rbx
0x180059869  push    rdi
0x18005986a  sub     rsp, 20h
0x18005986e  mov     rbx, rcx
0x180059871  call    ?EmptyLists@CResourceManager@@AEAAXXZ; CResourceManager::EmptyLists(void)
0x180059876  nop
0x180059877  lea     rdi, ??_7CSemExclusive@@6B@; const CSemExclusive::`vftable'
0x18005987e  mov     [rbx+100h], rdi
0x180059885  lea     rcx, [rbx+108h]; lpCriticalSection
0x18005988c  call    cs:__imp_DeleteCriticalSection
0x180059892  nop
0x180059893  mov     [rbx+0C8h], rdi
0x18005989a  lea     rcx, [rbx+0D0h]; lpCriticalSection
0x1800598a1  call    cs:__imp_DeleteCriticalSection
0x1800598a7  nop
0x1800598a8  mov     [rbx+90h], rdi
0x1800598af  lea     rcx, [rbx+98h]; lpCriticalSection
0x1800598b6  call    cs:__imp_DeleteCriticalSection
0x1800598bc  nop
0x1800598bd  lea     rax, ??_7?$UTStaticList@PEAVCPartnerPair@@@@6B@; const UTStaticList<CPartnerPair *>::`vftable'
0x1800598c4  mov     [rbx+70h], rax
0x1800598c8  lea     rax, ??_7?$UTStaticList@PEAVCPartnerPair@@@@6B@; const UTStaticList<CPartnerPair *>::`vftable'
0x1800598cf  mov     [rbx+50h], rax
0x1800598d3  lea     rax, ??_7?$UTStaticList@PEAVCPartnerPair@@@@6B@; const UTStaticList<CPartnerPair *>::`vftable'
0x1800598da  mov     [rbx+30h], rax
0x1800598de  mov     rbx, [rsp+28h+arg_0]
0x1800598e3  add     rsp, 20h
0x1800598e7  pop     rdi
0x1800598e8  retn
```
