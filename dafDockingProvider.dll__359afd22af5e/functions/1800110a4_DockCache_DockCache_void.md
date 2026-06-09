# DockCache::DockCache(void)

- ea: `0x1800110a4`
- end: `0x18001114b`
- name: `??0DockCache@@QEAA@XZ`
- size: `167`
- prototype: `DockCache *__fastcall(DockCache *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000ccdc`

## callees

- `0x180001484`
- `0x1800020bd`
- `0x1800110a4`
- `0x18001117c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800110b6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800110b6`

## pseudocode

```c
DockCache *__fastcall DockCache::DockCache(DockCache *this)
{
  _QWORD *v2; // rax
  const char *v3; // rdx
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  InitializeCriticalSection((LPCRITICAL_SECTION)this);
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 10) = 0;
  v2 = operator new(0x270u);
  if ( !v2 )
  {
    std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject, v3);
    throw (std::bad_alloc *)pExceptionObject;
  }
  *((_QWORD *)this + 9) = v2;
  *v2 = v2;
  *(_QWORD *)(*((_QWORD *)this + 9) + 8LL) = *((_QWORD *)this + 9);
  *((_DWORD *)this + 24) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  _InterlockedIncrement((volatile signed __int32 *)&g_cLockCount);
  return this;
}

```

## disassembly

```asm
0x1800110a4  mov     [rsp+arg_10], rbx
0x1800110a9  mov     [rsp+arg_0], rcx
0x1800110ae  push    rdi
0x1800110af  sub     rsp, 40h
0x1800110b3  mov     rbx, rcx
0x1800110b6  call    cs:__imp_InitializeCriticalSection
0x1800110bc  nop
0x1800110bd  mov     qword ptr [rbx+28h], 0
0x1800110c5  mov     qword ptr [rbx+30h], 0
0x1800110cd  mov     qword ptr [rbx+38h], 0
0x1800110d5  mov     qword ptr [rbx+50h], 0
0x1800110dd  mov     ecx, 270h; Size
0x1800110e2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800110e7  test    rax, rax
0x1800110ea  jz      short loc_18001112F
0x1800110ec  mov     [rbx+48h], rax
0x1800110f0  mov     [rax], rax
0x1800110f3  mov     rax, [rbx+48h]
0x1800110f7  mov     [rax+8], rax
0x1800110fb  mov     dword ptr [rbx+60h], 0
0x180011102  mov     qword ptr [rbx+68h], 0
0x18001110a  mov     qword ptr [rbx+70h], 0
0x180011112  mov     qword ptr [rbx+78h], 0
0x18001111a  lock inc cs:?g_cLockCount@@3KA; ulong g_cLockCount
0x180011121  mov     rax, rbx
0x180011124  mov     rbx, [rsp+48h+arg_10]
0x180011129  add     rsp, 40h
0x18001112d  pop     rdi
0x18001112e  retn
0x18001112f  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180011134  call    ??0bad_alloc@std@@QEAA@PEBD@Z; std::bad_alloc::bad_alloc(char const *)
0x180011139  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180011140  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180011145  call    _CxxThrowException_0
```
