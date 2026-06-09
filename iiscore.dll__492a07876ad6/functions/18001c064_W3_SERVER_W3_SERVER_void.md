# W3_SERVER::~W3_SERVER(void)

- ea: `0x18001c064`
- end: `0x18001c231`
- name: `??1W3_SERVER@@QEAA@XZ`
- size: `461`
- prototype: `void __fastcall(W3_SERVER *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180033514`

## callees

- `0x18001be2c`
- `0x18001c064`
- `0x180020918`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c08f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c08f`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x18001c154`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x18001c154`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x18001c225`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18001c1b3`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18001c1b3`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001c1e5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001c1f8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001c20b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001c1e5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001c1f8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001c20b`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18001c1c6`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18001c1c6`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x18001c18d`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x18001c1a0`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x18001c18d`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x18001c1a0`
- `iisutil!??1TREE_HASH_TABLE@@QEAA@XZ` at `0x18001c167`
- `iisutil!??1TREE_HASH_TABLE@@QEAA@XZ` at `0x18001c17a`
- `iisutil!??1TREE_HASH_TABLE@@QEAA@XZ` at `0x18001c167`
- `iisutil!??1TREE_HASH_TABLE@@QEAA@XZ` at `0x18001c17a`

## pseudocode

```c
void __fastcall W3_SERVER::~W3_SERVER(W3_SERVER *this)
{
  void *v2; // rcx
  struct IWPInstanceCountersManager *v3; // rbx
  __int64 v4; // rcx

  *(_QWORD *)this = &W3_SERVER::`vftable'{for `IHttpServer3'};
  *((_QWORD *)this + 1) = &W3_SERVER::`vftable'{for `IHttpTraceContext'};
  v2 = (void *)*((_QWORD *)this + 7);
  if ( v2 )
  {
    LocalFree(v2);
    *((_QWORD *)this + 7) = 0;
  }
  if ( !*((_DWORD *)this + 137) )
  {
    v3 = (struct IWPInstanceCountersManager *)*((_QWORD *)this + 193);
    CACHE_PERF_COUNTERS::UninitializeCounters((CACHE_PERF_COUNTERS *)v2, v3);
    (*(void (__fastcall **)(struct IWPInstanceCountersManager *, __int64, __int64))(*(_QWORD *)v3 + 32LL))(v3, 1, 47);
    (*(void (__fastcall **)(struct IWPInstanceCountersManager *, __int64, __int64))(*(_QWORD *)v3 + 32LL))(v3, 1, 48);
    (*(void (__fastcall **)(struct IWPInstanceCountersManager *, __int64, __int64))(*(_QWORD *)v3 + 32LL))(v3, 1, 49);
    (*(void (__fastcall **)(struct IWPInstanceCountersManager *, __int64, __int64))(*(_QWORD *)v3 + 32LL))(v3, 1, 50);
  }
  v4 = *((_QWORD *)this + 193);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
    *((_QWORD *)this + 193) = 0;
  }
  *((_DWORD *)this + 4) = 1716671319;
  CReaderWriterLock3::~CReaderWriterLock3((W3_SERVER *)((char *)this + 1588));
  TREE_HASH_TABLE::~TREE_HASH_TABLE((W3_SERVER *)((char *)this + 1424));
  TREE_HASH_TABLE::~TREE_HASH_TABLE((W3_SERVER *)((char *)this + 1384));
  CLKRHashTable::~CLKRHashTable((W3_SERVER *)((char *)this + 1312));
  CLKRHashTable::~CLKRHashTable((W3_SERVER *)((char *)this + 1240));
  BUFFER::~BUFFER((W3_SERVER *)((char *)this + 1056));
  MULTISZ::~MULTISZ((W3_SERVER *)((char *)this + 1000));
  CACHED_MODULE_LIST::~CACHED_MODULE_LIST((W3_SERVER *)((char *)this + 560));
  STRU::~STRU((W3_SERVER *)((char *)this + 480));
  STRU::~STRU((W3_SERVER *)((char *)this + 424));
  STRU::~STRU((W3_SERVER *)((char *)this + 368));
  CReaderWriterLock3::~CReaderWriterLock3((W3_SERVER *)((char *)this + 44));
}

```

## disassembly

```asm
0x18001c064  mov     [rsp+arg_0], rbx
0x18001c069  push    rdi
0x18001c06a  sub     rsp, 30h
0x18001c06e  lea     rax, ??_7W3_SERVER@@6BIHttpServer3@@@; const W3_SERVER::`vftable'{for `IHttpServer3'}
0x18001c075  mov     rdi, rcx
0x18001c078  mov     [rcx], rax
0x18001c07b  lea     rax, ??_7W3_SERVER@@6BIHttpTraceContext@@@; const W3_SERVER::`vftable'{for `IHttpTraceContext'}
0x18001c082  mov     [rcx+8], rax
0x18001c086  mov     rcx, [rcx+38h]; hMem
0x18001c08a  test    rcx, rcx
0x18001c08d  jz      short loc_18001C0A3
0x18001c08f  call    cs:__imp_LocalFree
0x18001c096  nop     dword ptr [rax+rax+00h]
0x18001c09b  mov     qword ptr [rdi+38h], 0
0x18001c0a3  cmp     dword ptr [rdi+224h], 0
0x18001c0aa  jnz     short loc_18001C123
0x18001c0ac  mov     rbx, [rdi+608h]
0x18001c0b3  mov     rdx, rbx; struct IWPInstanceCountersManager *
0x18001c0b6  call    ?UninitializeCounters@CACHE_PERF_COUNTERS@@QEAAXPEAVIWPInstanceCountersManager@@@Z; CACHE_PERF_COUNTERS::UninitializeCounters(IWPInstanceCountersManager *)
0x18001c0bb  mov     rax, [rbx]
0x18001c0be  xor     r9d, r9d
0x18001c0c1  mov     rcx, rbx
0x18001c0c4  mov     rax, [rax+20h]
0x18001c0c8  lea     edx, [r9+1]
0x18001c0cc  lea     r8d, [r9+2Fh]
0x18001c0d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c0d5  mov     rax, [rbx]
0x18001c0d8  xor     r9d, r9d
0x18001c0db  mov     rcx, rbx
0x18001c0de  mov     rax, [rax+20h]
0x18001c0e2  lea     edx, [r9+1]
0x18001c0e6  lea     r8d, [r9+30h]
0x18001c0ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c0ef  mov     rax, [rbx]
0x18001c0f2  xor     r9d, r9d
0x18001c0f5  mov     rcx, rbx
0x18001c0f8  mov     rax, [rax+20h]
0x18001c0fc  lea     edx, [r9+1]
0x18001c100  lea     r8d, [r9+31h]
0x18001c104  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c109  mov     rax, [rbx]
0x18001c10c  xor     r9d, r9d
0x18001c10f  mov     rcx, rbx
0x18001c112  mov     rax, [rax+20h]
0x18001c116  lea     edx, [r9+1]
0x18001c11a  lea     r8d, [r9+32h]
0x18001c11e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c123  mov     rcx, [rdi+608h]
0x18001c12a  test    rcx, rcx
0x18001c12d  jz      short loc_18001C146
0x18001c12f  mov     rax, [rcx]
0x18001c132  mov     rax, [rax+8]
0x18001c136  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c13b  mov     qword ptr [rdi+608h], 0
0x18001c146  lea     rcx, [rdi+634h]
0x18001c14d  mov     dword ptr [rdi+10h], 66525357h
0x18001c154  call    cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
0x18001c15b  nop     dword ptr [rax+rax+00h]
0x18001c160  lea     rcx, [rdi+590h]
0x18001c167  call    cs:__imp_??1TREE_HASH_TABLE@@QEAA@XZ; TREE_HASH_TABLE::~TREE_HASH_TABLE(void)
0x18001c16e  nop     dword ptr [rax+rax+00h]
0x18001c173  lea     rcx, [rdi+568h]
0x18001c17a  call    cs:__imp_??1TREE_HASH_TABLE@@QEAA@XZ; TREE_HASH_TABLE::~TREE_HASH_TABLE(void)
0x18001c181  nop     dword ptr [rax+rax+00h]
0x18001c186  lea     rcx, [rdi+520h]
0x18001c18d  call    cs:__imp_??1CLKRHashTable@@QEAA@XZ; CLKRHashTable::~CLKRHashTable(void)
0x18001c194  nop     dword ptr [rax+rax+00h]
0x18001c199  lea     rcx, [rdi+4D8h]
0x18001c1a0  call    cs:__imp_??1CLKRHashTable@@QEAA@XZ; CLKRHashTable::~CLKRHashTable(void)
0x18001c1a7  nop     dword ptr [rax+rax+00h]
0x18001c1ac  lea     rcx, [rdi+420h]
0x18001c1b3  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18001c1ba  nop     dword ptr [rax+rax+00h]
0x18001c1bf  lea     rcx, [rdi+3E8h]
0x18001c1c6  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x18001c1cd  nop     dword ptr [rax+rax+00h]
0x18001c1d2  lea     rcx, [rdi+230h]; this
0x18001c1d9  call    ??1CACHED_MODULE_LIST@@QEAA@XZ; CACHED_MODULE_LIST::~CACHED_MODULE_LIST(void)
0x18001c1de  lea     rcx, [rdi+1E0h]
0x18001c1e5  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001c1ec  nop     dword ptr [rax+rax+00h]
0x18001c1f1  lea     rcx, [rdi+1A8h]
0x18001c1f8  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001c1ff  nop     dword ptr [rax+rax+00h]
0x18001c204  lea     rcx, [rdi+170h]
0x18001c20b  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001c212  nop     dword ptr [rax+rax+00h]
0x18001c217  lea     rcx, [rdi+2Ch]
0x18001c21b  mov     rbx, [rsp+38h+arg_0]
0x18001c220  add     rsp, 30h
0x18001c224  pop     rdi
0x18001c225  jmp     cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
```
