# CWiGigDAFProviderQuery::~CWiGigDAFProviderQuery(void)

- ea: `0x180018420`
- end: `0x1800184ef`
- name: `??1CWiGigDAFProviderQuery@@QEAA@XZ`
- size: `207`
- prototype: `void __fastcall(CWiGigDAFProviderQuery *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180018f80`

## callees

- `0x1800014d0`
- `0x18001134c`
- `0x180016e2c`
- `0x180018310`
- `0x180018420`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001847d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001847d`

## pseudocode

```c
void __fastcall CWiGigDAFProviderQuery::~CWiGigDAFProviderQuery(CWiGigDAFProviderQuery *this)
{
  void *v2; // rcx
  volatile signed __int32 *v3; // rdi
  DockingProviders *v4; // rcx
  __int64 v5; // rcx

  *(_QWORD *)this = &CWiGigDAFProviderQuery::`vftable';
  _InterlockedDecrement((volatile signed __int32 *)&g_cLockCount);
  v2 = (void *)*((_QWORD *)this + 18);
  if ( v2 )
    operator delete(v2);
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 0;
  std::list<std::pair<HardwareAddress const,VisibleDock>>::~list<std::pair<HardwareAddress const,VisibleDock>>((char *)this + 120);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  v3 = (volatile signed __int32 *)*((_QWORD *)this + 6);
  if ( v3 )
  {
    if ( _InterlockedExchangeAdd(v3 + 24, 0xFFFFFFFF) == 1 )
    {
      DockCache::~DockCache((DockCache *)v3);
      operator delete((void *)v3);
    }
    *((_QWORD *)this + 6) = 0;
  }
  v4 = (DockingProviders *)*((_QWORD *)this + 5);
  if ( v4 )
  {
    DockingProviders::Release(v4);
    *((_QWORD *)this + 5) = 0;
  }
  v5 = *((_QWORD *)this + 4);
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    *((_QWORD *)this + 4) = 0;
  }
}

```

## disassembly

```asm
0x180018420  mov     [rsp+arg_8], rbx
0x180018425  push    rdi
0x180018426  sub     rsp, 20h
0x18001842a  mov     rbx, rcx
0x18001842d  lea     rax, ??_7CWiGigDAFProviderQuery@@6B@; const CWiGigDAFProviderQuery::`vftable'
0x180018434  mov     [rcx], rax
0x180018437  lock dec cs:?g_cLockCount@@3KA; ulong g_cLockCount
0x18001843e  mov     rcx, [rcx+90h]; Block
0x180018445  test    rcx, rcx
0x180018448  jz      short loc_18001844F
0x18001844a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001844f  mov     qword ptr [rbx+90h], 0
0x18001845a  mov     qword ptr [rbx+98h], 0
0x180018465  mov     qword ptr [rbx+0A0h], 0
0x180018470  lea     rcx, [rbx+78h]
0x180018474  call    ??1?$list@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@QEAA@XZ; std::list<std::pair<HardwareAddress const,VisibleDock>>::~list<std::pair<HardwareAddress const,VisibleDock>>(void)
0x180018479  lea     rcx, [rbx+40h]; lpCriticalSection
0x18001847d  call    cs:__imp_DeleteCriticalSection
0x180018483  mov     rdi, [rbx+30h]
0x180018487  test    rdi, rdi
0x18001848a  jz      short loc_1800184B1
0x18001848c  or      eax, 0FFFFFFFFh
0x18001848f  lock xadd [rdi+60h], eax
0x180018494  cmp     eax, 1
0x180018497  jnz     short loc_1800184A9
0x180018499  mov     rcx, rdi; this
0x18001849c  call    ??1DockCache@@AEAA@XZ; DockCache::~DockCache(void)
0x1800184a1  mov     rcx, rdi; Block
0x1800184a4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800184a9  mov     qword ptr [rbx+30h], 0
0x1800184b1  mov     rcx, [rbx+28h]; this
0x1800184b5  test    rcx, rcx
0x1800184b8  jz      short loc_1800184C7
0x1800184ba  call    ?Release@DockingProviders@@QEAAKXZ; DockingProviders::Release(void)
0x1800184bf  mov     qword ptr [rbx+28h], 0
0x1800184c7  mov     rcx, [rbx+20h]
0x1800184cb  test    rcx, rcx
0x1800184ce  jz      short loc_1800184E4
0x1800184d0  mov     rax, [rcx]
0x1800184d3  mov     rax, [rax+10h]
0x1800184d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800184dc  mov     qword ptr [rbx+20h], 0
0x1800184e4  mov     rbx, [rsp+28h+arg_8]
0x1800184e9  add     rsp, 20h
0x1800184ed  pop     rdi
0x1800184ee  retn
```
