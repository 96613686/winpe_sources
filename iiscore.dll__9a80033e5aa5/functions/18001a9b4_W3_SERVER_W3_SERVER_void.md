# W3_SERVER::~W3_SERVER(void)

- ea: `0x18001a9b4`
- end: `0x18001ab3a`
- name: `??1W3_SERVER@@QEAA@XZ`
- size: `390`
- prototype: `void __fastcall(W3_SERVER *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180030848`

## callees

- `0x18001a7a8`
- `0x18001a9b4`
- `0x18001eda4`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a9df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a9df`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x18001aa9e`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x18001aa9e`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x18001ab33`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18001aadf`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18001aadf`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001ab05`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001ab12`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001ab1f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001ab05`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001ab12`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001ab1f`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18001aaec`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18001aaec`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x18001aac5`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x18001aad2`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x18001aac5`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x18001aad2`
- `iisutil!??1TREE_HASH_TABLE@@QEAA@XZ` at `0x18001aaab`
- `iisutil!??1TREE_HASH_TABLE@@QEAA@XZ` at `0x18001aab8`
- `iisutil!??1TREE_HASH_TABLE@@QEAA@XZ` at `0x18001aaab`
- `iisutil!??1TREE_HASH_TABLE@@QEAA@XZ` at `0x18001aab8`

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
0x18001a9b4  mov     [rsp+arg_0], rbx
0x18001a9b9  push    rdi
0x18001a9ba  sub     rsp, 30h
0x18001a9be  lea     rax, ??_7W3_SERVER@@6BIHttpServer3@@@; const W3_SERVER::`vftable'{for `IHttpServer3'}
0x18001a9c5  mov     rdi, rcx
0x18001a9c8  mov     [rcx], rax
0x18001a9cb  lea     rax, ??_7W3_SERVER@@6BIHttpTraceContext@@@; const W3_SERVER::`vftable'{for `IHttpTraceContext'}
0x18001a9d2  mov     [rcx+8], rax
0x18001a9d6  mov     rcx, [rcx+38h]; hMem
0x18001a9da  test    rcx, rcx
0x18001a9dd  jz      short loc_18001A9ED
0x18001a9df  call    cs:__imp_LocalFree
0x18001a9e5  mov     qword ptr [rdi+38h], 0
0x18001a9ed  cmp     dword ptr [rdi+224h], 0
0x18001a9f4  jnz     short loc_18001AA6D
0x18001a9f6  mov     rbx, [rdi+608h]
0x18001a9fd  mov     rdx, rbx; struct IWPInstanceCountersManager *
0x18001aa00  call    ?UninitializeCounters@CACHE_PERF_COUNTERS@@QEAAXPEAVIWPInstanceCountersManager@@@Z; CACHE_PERF_COUNTERS::UninitializeCounters(IWPInstanceCountersManager *)
0x18001aa05  mov     rax, [rbx]
0x18001aa08  xor     r9d, r9d
0x18001aa0b  mov     rcx, rbx
0x18001aa0e  mov     rax, [rax+20h]
0x18001aa12  lea     edx, [r9+1]
0x18001aa16  lea     r8d, [r9+2Fh]
0x18001aa1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa1f  mov     rax, [rbx]
0x18001aa22  xor     r9d, r9d
0x18001aa25  mov     rcx, rbx
0x18001aa28  mov     rax, [rax+20h]
0x18001aa2c  lea     edx, [r9+1]
0x18001aa30  lea     r8d, [r9+30h]
0x18001aa34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa39  mov     rax, [rbx]
0x18001aa3c  xor     r9d, r9d
0x18001aa3f  mov     rcx, rbx
0x18001aa42  mov     rax, [rax+20h]
0x18001aa46  lea     edx, [r9+1]
0x18001aa4a  lea     r8d, [r9+31h]
0x18001aa4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa53  mov     rax, [rbx]
0x18001aa56  xor     r9d, r9d
0x18001aa59  mov     rcx, rbx
0x18001aa5c  mov     rax, [rax+20h]
0x18001aa60  lea     edx, [r9+1]
0x18001aa64  lea     r8d, [r9+32h]
0x18001aa68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa6d  mov     rcx, [rdi+608h]
0x18001aa74  test    rcx, rcx
0x18001aa77  jz      short loc_18001AA90
0x18001aa79  mov     rax, [rcx]
0x18001aa7c  mov     rax, [rax+8]
0x18001aa80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa85  mov     qword ptr [rdi+608h], 0
0x18001aa90  lea     rcx, [rdi+634h]
0x18001aa97  mov     dword ptr [rdi+10h], 66525357h
0x18001aa9e  call    cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
0x18001aaa4  lea     rcx, [rdi+590h]
0x18001aaab  call    cs:__imp_??1TREE_HASH_TABLE@@QEAA@XZ; TREE_HASH_TABLE::~TREE_HASH_TABLE(void)
0x18001aab1  lea     rcx, [rdi+568h]
0x18001aab8  call    cs:__imp_??1TREE_HASH_TABLE@@QEAA@XZ; TREE_HASH_TABLE::~TREE_HASH_TABLE(void)
0x18001aabe  lea     rcx, [rdi+520h]
0x18001aac5  call    cs:__imp_??1CLKRHashTable@@QEAA@XZ; CLKRHashTable::~CLKRHashTable(void)
0x18001aacb  lea     rcx, [rdi+4D8h]
0x18001aad2  call    cs:__imp_??1CLKRHashTable@@QEAA@XZ; CLKRHashTable::~CLKRHashTable(void)
0x18001aad8  lea     rcx, [rdi+420h]
0x18001aadf  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18001aae5  lea     rcx, [rdi+3E8h]
0x18001aaec  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x18001aaf2  lea     rcx, [rdi+230h]; this
0x18001aaf9  call    ??1CACHED_MODULE_LIST@@QEAA@XZ; CACHED_MODULE_LIST::~CACHED_MODULE_LIST(void)
0x18001aafe  lea     rcx, [rdi+1E0h]
0x18001ab05  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001ab0b  lea     rcx, [rdi+1A8h]
0x18001ab12  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001ab18  lea     rcx, [rdi+170h]
0x18001ab1f  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001ab25  lea     rcx, [rdi+2Ch]
0x18001ab29  mov     rbx, [rsp+38h+arg_0]
0x18001ab2e  add     rsp, 30h
0x18001ab32  pop     rdi
0x18001ab33  jmp     cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
```
