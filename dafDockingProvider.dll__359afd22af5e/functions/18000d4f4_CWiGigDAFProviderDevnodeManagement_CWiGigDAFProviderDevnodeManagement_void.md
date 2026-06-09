# CWiGigDAFProviderDevnodeManagement::~CWiGigDAFProviderDevnodeManagement(void)

- ea: `0x18000d4f4`
- end: `0x18000d5cc`
- name: `??1CWiGigDAFProviderDevnodeManagement@@AEAA@XZ`
- size: `216`
- prototype: `void __fastcall(CWiGigDAFProviderDevnodeManagement *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18000f160`

## callees

- `0x1800014d0`
- `0x18000d4f4`
- `0x18000d5d4`
- `0x18001134c`
- `0x180016e2c`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d525`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d525`

## pseudocode

```c
void __fastcall CWiGigDAFProviderDevnodeManagement::~CWiGigDAFProviderDevnodeManagement(
        CWiGigDAFProviderDevnodeManagement *this)
{
  volatile signed __int32 *v2; // rdi
  DockingProviders *v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx

  *(_QWORD *)this = &CWiGigDAFProviderDevnodeManagement::`vftable';
  _InterlockedDecrement((volatile signed __int32 *)&g_cLockCount);
  StartManagementTimer::~StartManagementTimer((CWiGigDAFProviderDevnodeManagement *)((char *)this + 680));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 632));
  v2 = (volatile signed __int32 *)*((_QWORD *)this + 78);
  if ( v2 )
  {
    if ( _InterlockedExchangeAdd(v2 + 24, 0xFFFFFFFF) == 1 )
    {
      DockCache::~DockCache((DockCache *)v2);
      operator delete((void *)v2);
    }
    *((_QWORD *)this + 78) = 0;
  }
  v3 = (DockingProviders *)*((_QWORD *)this + 77);
  if ( v3 )
  {
    DockingProviders::Release(v3);
    *((_QWORD *)this + 77) = 0;
  }
  v4 = *((_QWORD *)this + 76);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    *((_QWORD *)this + 76) = 0;
  }
  v5 = *((_QWORD *)this + 75);
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    *((_QWORD *)this + 75) = 0;
  }
}

```

## disassembly

```asm
0x18000d4f4  mov     [rsp+arg_8], rbx
0x18000d4f9  push    rdi
0x18000d4fa  sub     rsp, 20h
0x18000d4fe  mov     rbx, rcx
0x18000d501  lea     rax, ??_7CWiGigDAFProviderDevnodeManagement@@6B@; const CWiGigDAFProviderDevnodeManagement::`vftable'
0x18000d508  mov     [rcx], rax
0x18000d50b  lock dec cs:?g_cLockCount@@3KA; ulong g_cLockCount
0x18000d512  add     rcx, 2A8h; this
0x18000d519  call    ??1StartManagementTimer@@QEAA@XZ; StartManagementTimer::~StartManagementTimer(void)
0x18000d51e  lea     rcx, [rbx+278h]; lpCriticalSection
0x18000d525  call    cs:__imp_DeleteCriticalSection
0x18000d52b  mov     rdi, [rbx+270h]
0x18000d532  test    rdi, rdi
0x18000d535  jz      short loc_18000D55F
0x18000d537  or      eax, 0FFFFFFFFh
0x18000d53a  lock xadd [rdi+60h], eax
0x18000d53f  cmp     eax, 1
0x18000d542  jnz     short loc_18000D554
0x18000d544  mov     rcx, rdi; this
0x18000d547  call    ??1DockCache@@AEAA@XZ; DockCache::~DockCache(void)
0x18000d54c  mov     rcx, rdi; Block
0x18000d54f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d554  mov     qword ptr [rbx+270h], 0
0x18000d55f  mov     rcx, [rbx+268h]; this
0x18000d566  test    rcx, rcx
0x18000d569  jz      short loc_18000D57B
0x18000d56b  call    ?Release@DockingProviders@@QEAAKXZ; DockingProviders::Release(void)
0x18000d570  mov     qword ptr [rbx+268h], 0
0x18000d57b  mov     rcx, [rbx+260h]
0x18000d582  test    rcx, rcx
0x18000d585  jz      short loc_18000D59E
0x18000d587  mov     rax, [rcx]
0x18000d58a  mov     rax, [rax+10h]
0x18000d58e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d593  mov     qword ptr [rbx+260h], 0
0x18000d59e  mov     rcx, [rbx+258h]
0x18000d5a5  test    rcx, rcx
0x18000d5a8  jz      short loc_18000D5C1
0x18000d5aa  mov     rax, [rcx]
0x18000d5ad  mov     rax, [rax+10h]
0x18000d5b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5b6  mov     qword ptr [rbx+258h], 0
0x18000d5c1  mov     rbx, [rsp+28h+arg_8]
0x18000d5c6  add     rsp, 20h
0x18000d5ca  pop     rdi
0x18000d5cb  retn
```
