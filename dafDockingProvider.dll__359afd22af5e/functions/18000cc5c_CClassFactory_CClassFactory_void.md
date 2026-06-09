# CClassFactory::~CClassFactory(void)

- ea: `0x18000cc5c`
- end: `0x18000ccd3`
- name: `??1CClassFactory@@IEAA@XZ`
- size: `119`
- prototype: `void __fastcall(CClassFactory *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000d400`

## callees

- `0x1800014d0`
- `0x18000cc5c`
- `0x18001134c`
- `0x180016e2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000cccc`

## pseudocode

```c
void __fastcall CClassFactory::~CClassFactory(CClassFactory *this)
{
  volatile signed __int32 *v2; // rdi
  DockingProviders *v3; // rcx

  *(_QWORD *)this = &CClassFactory::`vftable';
  _InterlockedDecrement((volatile signed __int32 *)&g_cLockCount);
  v2 = (volatile signed __int32 *)*((_QWORD *)this + 9);
  if ( v2 )
  {
    if ( _InterlockedExchangeAdd(v2 + 24, 0xFFFFFFFF) == 1 )
    {
      DockCache::~DockCache((DockCache *)v2);
      operator delete((void *)v2);
    }
    *((_QWORD *)this + 9) = 0;
  }
  v3 = (DockingProviders *)*((_QWORD *)this + 8);
  if ( v3 )
  {
    DockingProviders::Release(v3);
    *((_QWORD *)this + 8) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
}

```

## disassembly

```asm
0x18000cc5c  mov     [rsp+arg_8], rbx
0x18000cc61  push    rdi
0x18000cc62  sub     rsp, 20h
0x18000cc66  lea     rax, ??_7CClassFactory@@6B@; const CClassFactory::`vftable'
0x18000cc6d  mov     rbx, rcx
0x18000cc70  mov     [rcx], rax
0x18000cc73  lock dec cs:?g_cLockCount@@3KA; ulong g_cLockCount
0x18000cc7a  mov     rdi, [rcx+48h]
0x18000cc7e  test    rdi, rdi
0x18000cc81  jz      short loc_18000CCA8
0x18000cc83  or      eax, 0FFFFFFFFh
0x18000cc86  lock xadd [rdi+60h], eax
0x18000cc8b  cmp     eax, 1
0x18000cc8e  jnz     short loc_18000CCA0
0x18000cc90  mov     rcx, rdi; this
0x18000cc93  call    ??1DockCache@@AEAA@XZ; DockCache::~DockCache(void)
0x18000cc98  mov     rcx, rdi; Block
0x18000cc9b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000cca0  mov     qword ptr [rbx+48h], 0
0x18000cca8  mov     rcx, [rbx+40h]; this
0x18000ccac  test    rcx, rcx
0x18000ccaf  jz      short loc_18000CCBE
0x18000ccb1  call    ?Release@DockingProviders@@QEAAKXZ; DockingProviders::Release(void)
0x18000ccb6  mov     qword ptr [rbx+40h], 0
0x18000ccbe  lea     rcx, [rbx+18h]
0x18000ccc2  mov     rbx, [rsp+28h+arg_8]
0x18000ccc7  add     rsp, 20h
0x18000cccb  pop     rdi
0x18000cccc  jmp     cs:__imp_DeleteCriticalSection
```
