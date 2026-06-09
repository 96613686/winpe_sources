# CDockInterface::~CDockInterface(void)

- ea: `0x18001a8f0`
- end: `0x18001a954`
- name: `??1CDockInterface@@QEAA@XZ`
- size: `100`
- prototype: `void __fastcall(CDockInterface *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001bf70`

## callees

- `0x180016e2c`
- `0x18001a66c`
- `0x18001a6d4`
- `0x18001a884`
- `0x18001a8f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001a92d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001a92d`

## pseudocode

```c
void __fastcall CDockInterface::~CDockInterface(CDockInterface *this)
{
  DockingProviders *v2; // rcx

  *(_QWORD *)this = &CDockInterface::`vftable';
  WorkItems::Close((CDockInterface *)((char *)this + 96));
  _InterlockedDecrement((volatile signed __int32 *)&g_cLockCount);
  WorkItems::~WorkItems((CDockInterface *)((char *)this + 96));
  std::list<CDockInterface::Listener>::~list<CDockInterface::Listener>((char *)this + 64);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v2 = (DockingProviders *)*((_QWORD *)this + 2);
  if ( v2 )
  {
    DockingProviders::Release(v2);
    *((_QWORD *)this + 2) = 0;
  }
}

```

## disassembly

```asm
0x18001a8f0  mov     [rsp+arg_0], rbx
0x18001a8f5  push    rdi
0x18001a8f6  sub     rsp, 20h
0x18001a8fa  lea     rax, ??_7CDockInterface@@6B@; const CDockInterface::`vftable'
0x18001a901  mov     rdi, rcx
0x18001a904  mov     [rcx], rax
0x18001a907  add     rcx, 60h ; '`'; this
0x18001a90b  call    ?Close@WorkItems@@QEAAXXZ; WorkItems::Close(void)
0x18001a910  lock dec cs:?g_cLockCount@@3KA; ulong g_cLockCount
0x18001a917  lea     rcx, [rdi+60h]; this
0x18001a91b  call    ??1WorkItems@@QEAA@XZ; WorkItems::~WorkItems(void)
0x18001a920  lea     rcx, [rdi+40h]
0x18001a924  call    ??1?$list@VListener@CDockInterface@@V?$allocator@VListener@CDockInterface@@@std@@@std@@QEAA@XZ; std::list<CDockInterface::Listener>::~list<CDockInterface::Listener>(void)
0x18001a929  lea     rcx, [rdi+18h]; lpCriticalSection
0x18001a92d  call    cs:__imp_DeleteCriticalSection
0x18001a933  mov     rcx, [rdi+10h]; this
0x18001a937  test    rcx, rcx
0x18001a93a  jz      short loc_18001A949
0x18001a93c  call    ?Release@DockingProviders@@QEAAKXZ; DockingProviders::Release(void)
0x18001a941  mov     qword ptr [rdi+10h], 0
0x18001a949  mov     rbx, [rsp+28h+arg_0]
0x18001a94e  add     rsp, 20h
0x18001a952  pop     rdi
0x18001a953  retn
```
