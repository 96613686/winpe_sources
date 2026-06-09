# DockCache::~DockCache(void)

- ea: `0x18001134c`
- end: `0x180011404`
- name: `??1DockCache@@AEAA@XZ`
- size: `184`
- prototype: `void __fastcall(DockCache *__hidden this)`
- caller_count: `7`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800086a4`
- `0x180008738`
- `0x18000c4cc`
- `0x18000cc5c`
- `0x18000ccdc`
- `0x18000d4f4`
- `0x180018420`

## callees

- `0x1800014d0`
- `0x1800111b4`
- `0x1800112b4`
- `0x18001134c`
- `0x180016e2c`
- `0x1800172d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800113fd`

## pseudocode

```c
void __fastcall DockCache::~DockCache(DockCache *this)
{
  DockingProviders *v2; // rcx
  DockingProviders *v3; // rcx
  DockingProviders *v4; // rcx
  Dock *v5; // rdi
  Dock *v6; // rbp

  v2 = (DockingProviders *)*((_QWORD *)this + 14);
  if ( v2 )
  {
    DockingProviders::UnregisterConnectionListener(v2, *((_QWORD *)this + 15));
    *((_QWORD *)this + 15) = 0;
  }
  v3 = (DockingProviders *)*((_QWORD *)this + 14);
  if ( v3 )
  {
    DockingProviders::Release(v3);
    *((_QWORD *)this + 14) = 0;
  }
  _InterlockedDecrement((volatile signed __int32 *)&g_cLockCount);
  v4 = (DockingProviders *)*((_QWORD *)this + 14);
  if ( v4 )
  {
    DockingProviders::Release(v4);
    *((_QWORD *)this + 14) = 0;
  }
  std::list<DeviceStatusNotif>::~list<DeviceStatusNotif>((char *)this + 72);
  v5 = (Dock *)*((_QWORD *)this + 5);
  if ( v5 )
  {
    v6 = (Dock *)*((_QWORD *)this + 6);
    while ( v5 != v6 )
    {
      Dock::~Dock(v5);
      v5 = (Dock *)((char *)v5 + 2936);
    }
    operator delete(*((void **)this + 5));
  }
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)this);
}

```

## disassembly

```asm
0x18001134c  push    rbx
0x18001134e  push    rbp
0x18001134f  push    rsi
0x180011350  push    rdi
0x180011351  sub     rsp, 28h
0x180011355  mov     rbx, rcx
0x180011358  mov     rcx, [rcx+70h]; this
0x18001135c  test    rcx, rcx
0x18001135f  jz      short loc_180011372
0x180011361  mov     rdx, [rbx+78h]; unsigned __int64
0x180011365  call    ?UnregisterConnectionListener@DockingProviders@@QEAAJ_K@Z; DockingProviders::UnregisterConnectionListener(unsigned __int64)
0x18001136a  mov     qword ptr [rbx+78h], 0
0x180011372  mov     rcx, [rbx+70h]; this
0x180011376  test    rcx, rcx
0x180011379  jz      short loc_180011388
0x18001137b  call    ?Release@DockingProviders@@QEAAKXZ; DockingProviders::Release(void)
0x180011380  mov     qword ptr [rbx+70h], 0
0x180011388  lock dec cs:?g_cLockCount@@3KA; ulong g_cLockCount
0x18001138f  mov     rcx, [rbx+70h]; this
0x180011393  test    rcx, rcx
0x180011396  jz      short loc_1800113A5
0x180011398  call    ?Release@DockingProviders@@QEAAKXZ; DockingProviders::Release(void)
0x18001139d  mov     qword ptr [rbx+70h], 0
0x1800113a5  lea     rcx, [rbx+48h]
0x1800113a9  call    ??1?$list@VDeviceStatusNotif@@V?$allocator@VDeviceStatusNotif@@@std@@@std@@QEAA@XZ; std::list<DeviceStatusNotif>::~list<DeviceStatusNotif>(void)
0x1800113ae  mov     rdi, [rbx+28h]
0x1800113b2  test    rdi, rdi
0x1800113b5  jz      short loc_1800113DA
0x1800113b7  mov     rbp, [rbx+30h]
0x1800113bb  jmp     short loc_1800113CC
0x1800113bd  mov     rcx, rdi; this
0x1800113c0  call    ??1Dock@@QEAA@XZ; Dock::~Dock(void)
0x1800113c5  add     rdi, 0B78h
0x1800113cc  cmp     rdi, rbp
0x1800113cf  jnz     short loc_1800113BD
0x1800113d1  mov     rcx, [rbx+28h]; Block
0x1800113d5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800113da  mov     qword ptr [rbx+28h], 0
0x1800113e2  mov     qword ptr [rbx+30h], 0
0x1800113ea  mov     qword ptr [rbx+38h], 0
0x1800113f2  mov     rcx, rbx
0x1800113f5  add     rsp, 28h
0x1800113f9  pop     rdi
0x1800113fa  pop     rsi
0x1800113fb  pop     rbp
0x1800113fc  pop     rbx
0x1800113fd  jmp     cs:__imp_DeleteCriticalSection
```
