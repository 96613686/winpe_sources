# Database::GetSessionFromPool(tlx::smart_ptr<DbSession,&tlx::_delete<DbSession>(DbSession *),utl::allocator<int>> &)

- ea: `0x1800107c4`
- end: `0x18001083c`
- name: `?GetSessionFromPool@Database@@QEAAJAEAV?$smart_ptr@VDbSession@@$1??$_delete@VDbSession@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@Z`
- size: `120`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *, _QWORD *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180010500`
- `0x180015da4`
- `0x180015e68`
- `0x180015f2c`

## callees

- `0x180006f78`
- `0x18000bf80`
- `0x1800105bc`
- `0x1800107c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010824`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010824`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800107e0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800107e0`

## pseudocode

```c
__int64 __fastcall Database::GetSessionFromPool(RTL_SRWLOCK *a1, _QWORD *a2)
{
  RTL_SRWLOCK *v2; // rsi
  __int64 v5; // rcx
  int v6; // ebx
  int *v7; // rax
  int v9; // [rsp+20h] [rbp-18h]

  v2 = a1 + 13;
  AcquireSRWLockExclusive(a1 + 13);
  v6 = SharedObjectPool<DbSession>::Get((__int64)a1, a2);
  if ( v6 < 0 )
  {
    v7 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v5);
    v9 = v6;
    DSLogger::LogError(
      (DSLogger *)v7,
      L"Database::GetSessionFromPool",
      0x179u,
      L"Database::GetSessionFromPool failed! hr=0x%x.",
      v9);
  }
  if ( v2 )
    ReleaseSRWLockExclusive(v2);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800107c4  mov     [rsp+arg_0], rbx
0x1800107c9  mov     [rsp+arg_8], rsi
0x1800107ce  push    rdi
0x1800107cf  sub     rsp, 30h
0x1800107d3  lea     rsi, [rcx+68h]
0x1800107d7  mov     rdi, rcx
0x1800107da  mov     rcx, rsi; SRWLock
0x1800107dd  mov     rbx, rdx
0x1800107e0  call    cs:__imp_AcquireSRWLockExclusive
0x1800107e6  mov     rdx, rbx
0x1800107e9  mov     rcx, rdi
0x1800107ec  call    ?Get@?$SharedObjectPool@VDbSession@@@@IEAAJAEAV?$smart_ptr@VDbSession@@$1??$_delete@VDbSession@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@Z; SharedObjectPool<DbSession>::Get(tlx::smart_ptr<DbSession,&tlx::_delete<DbSession>(DbSession *),utl::allocator<int>> &)
0x1800107f1  mov     ebx, eax
0x1800107f3  test    eax, eax
0x1800107f5  jns     short loc_18001081C
0x1800107f7  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x1800107fc  lea     r9, aDatabaseGetses_0; "Database::GetSessionFromPool failed! hr"...
0x180010803  mov     [rsp+38h+var_18], ebx
0x180010807  mov     r8d, 179h; unsigned int
0x18001080d  lea     rdx, aDatabaseGetses; "Database::GetSessionFromPool"
0x180010814  mov     rcx, rax; this
0x180010817  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x18001081c  test    rsi, rsi
0x18001081f  jz      short loc_18001082A
0x180010821  mov     rcx, rsi; SRWLock
0x180010824  call    cs:__imp_ReleaseSRWLockExclusive
0x18001082a  mov     rsi, [rsp+38h+arg_8]
0x18001082f  mov     eax, ebx
0x180010831  mov     rbx, [rsp+38h+arg_0]
0x180010836  add     rsp, 30h
0x18001083a  pop     rdi
0x18001083b  retn
```
