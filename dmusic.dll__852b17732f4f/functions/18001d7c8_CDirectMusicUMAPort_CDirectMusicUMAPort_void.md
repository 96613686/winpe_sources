# CDirectMusicUMAPort::~CDirectMusicUMAPort(void)

- ea: `0x18001d7c8`
- end: `0x18001d8ec`
- name: `??1CDirectMusicUMAPort@@UEAA@XZ`
- size: `292`
- prototype: `void __fastcall(CDirectMusicUMAPort *__hidden this)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001d900`
- `0x18001e008`
- `0x1800209f0`

## callees

- `0x1800012c4`
- `0x18000a56c`
- `0x18000f340`
- `0x18001baf4`
- `0x18001d7c8`
- `0x18001dd40`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001d84e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001d864`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001d871`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001d84e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001d864`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001d871`

## pseudocode

```c
void __fastcall CDirectMusicUMAPort::~CDirectMusicUMAPort(struct _RTL_CRITICAL_SECTION *this)
{
  CDirectMusicUMAPort *v2; // rcx
  __int64 v3; // rbp
  __int64 v4; // rbx

  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CDirectMusicUMAPort::`vftable'{for `CDirectMusicPortDownload'};
  this[9].OwningThread = &CDirectMusicUMAPort::`vftable'{for `IDirectMusicThru'};
  this[9].LockSemaphore = &CDirectMusicUMAPort::`vftable'{for `IDirectMusicPort'};
  this[9].SpinCount = (ULONG_PTR)&CDirectMusicUMAPort::`vftable'{for `IDirectMusicPortP'};
  v2 = (CDirectMusicUMAPort *)&this[10];
  *(_QWORD *)v2 = &CDirectMusicUMAPort::`vftable'{for `IDirectMusicPortPrivate'};
  *(_QWORD *)&this[10].LockCount = &CDirectMusicUMAPort::`vftable'{for `IKsControl'};
  if ( LODWORD(this[37].DebugInfo) )
  {
    if ( LODWORD(this[40].DebugInfo) )
      CDirectMusicUMAPort::Close(v2);
    if ( LODWORD(this[37].DebugInfo) )
      DeleteCriticalSection(this + 36);
  }
  if ( LODWORD(this[40].DebugInfo) )
    DeleteCriticalSection(this + 39);
  DeleteCriticalSection(this + 34);
  v3 = (*(__int64 (__fastcall **)(LONG *))(*(_QWORD *)&this[33].LockCount + 40LL))(&this[33].LockCount);
  if ( v3 )
  {
    do
    {
      v4 = *(_QWORD *)(v3 + 8);
      operator delete(*(void **)(v3 + 16), 0x2260u);
      (*(void (__fastcall **)(LONG *, __int64))(*(_QWORD *)&this[33].LockCount + 16LL))(&this[33].LockCount, v3);
      v3 = v4;
    }
    while ( v4 );
  }
  _InterlockedDecrement(&g_cComponent);
  CPool<DMQUEUEDEVENT>::~CPool<DMQUEUEDEVENT>(&this[37].SpinCount);
  CList<tagPORTDEST *>::~CList<tagPORTDEST *>(&this[33].LockCount);
  CDirectMusicPortDownload::~CDirectMusicPortDownload((CDirectMusicPortDownload *)this);
}

```

## disassembly

```asm
0x18001d7c8  push    rbx
0x18001d7ca  push    rbp
0x18001d7cb  push    rsi
0x18001d7cc  push    rdi
0x18001d7cd  sub     rsp, 28h
0x18001d7d1  mov     rdi, rcx
0x18001d7d4  lea     rax, ??_7CDirectMusicUMAPort@@6BCDirectMusicPortDownload@@@; const CDirectMusicUMAPort::`vftable'{for `CDirectMusicPortDownload'}
0x18001d7db  mov     [rcx], rax
0x18001d7de  lea     rax, ??_7CDirectMusicUMAPort@@6BIDirectMusicThru@@@; const CDirectMusicUMAPort::`vftable'{for `IDirectMusicThru'}
0x18001d7e5  mov     [rcx+178h], rax
0x18001d7ec  lea     rax, ??_7CDirectMusicUMAPort@@6BIDirectMusicPort@@@; const CDirectMusicUMAPort::`vftable'{for `IDirectMusicPort'}
0x18001d7f3  mov     [rcx+180h], rax
0x18001d7fa  lea     rax, ??_7CDirectMusicUMAPort@@6BIDirectMusicPortP@@@; const CDirectMusicUMAPort::`vftable'{for `IDirectMusicPortP'}
0x18001d801  mov     [rcx+188h], rax
0x18001d808  add     rcx, 190h; this
0x18001d80f  lea     rax, ??_7CDirectMusicUMAPort@@6BIDirectMusicPortPrivate@@@; const CDirectMusicUMAPort::`vftable'{for `IDirectMusicPortPrivate'}
0x18001d816  mov     [rcx], rax
0x18001d819  lea     rax, ??_7CDirectMusicUMAPort@@6BIKsControl@@@; const CDirectMusicUMAPort::`vftable'{for `IKsControl'}
0x18001d820  mov     [rdi+198h], rax
0x18001d827  cmp     dword ptr [rdi+5C8h], 0
0x18001d82e  jz      short loc_18001D854
0x18001d830  cmp     dword ptr [rdi+640h], 0
0x18001d837  jz      short loc_18001D83E
0x18001d839  call    ?Close@CDirectMusicUMAPort@@UEAAJXZ; CDirectMusicUMAPort::Close(void)
0x18001d83e  cmp     dword ptr [rdi+5C8h], 0
0x18001d845  jz      short loc_18001D854
0x18001d847  lea     rcx, [rdi+5A0h]; lpCriticalSection
0x18001d84e  call    cs:__imp_DeleteCriticalSection
0x18001d854  cmp     dword ptr [rdi+640h], 0
0x18001d85b  jz      short loc_18001D86A
0x18001d85d  lea     rcx, [rdi+618h]; lpCriticalSection
0x18001d864  call    cs:__imp_DeleteCriticalSection
0x18001d86a  lea     rcx, [rdi+550h]; lpCriticalSection
0x18001d871  call    cs:__imp_DeleteCriticalSection
0x18001d877  lea     rsi, [rdi+530h]
0x18001d87e  mov     rax, [rsi]
0x18001d881  mov     rcx, rsi
0x18001d884  mov     rax, [rax+28h]
0x18001d888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d88d  mov     rbp, rax
0x18001d890  test    rax, rax
0x18001d893  jz      short loc_18001D8C1
0x18001d895  mov     rbx, [rbp+8]
0x18001d899  mov     edx, 2260h; unsigned __int64
0x18001d89e  mov     rcx, [rbp+10h]; void *
0x18001d8a2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001d8a7  mov     rcx, [rsi]
0x18001d8aa  mov     rax, [rcx+10h]
0x18001d8ae  mov     rdx, rbp
0x18001d8b1  mov     rcx, rsi
0x18001d8b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d8b9  mov     rbp, rbx
0x18001d8bc  test    rbx, rbx
0x18001d8bf  jnz     short loc_18001D895
0x18001d8c1  lock dec cs:?g_cComponent@@3JA; long g_cComponent
0x18001d8c8  lea     rcx, [rdi+5E8h]
0x18001d8cf  call    ??1?$CPool@UDMQUEUEDEVENT@@@@QEAA@XZ; CPool<DMQUEUEDEVENT>::~CPool<DMQUEUEDEVENT>(void)
0x18001d8d4  mov     rcx, rsi
0x18001d8d7  call    ??1?$CList@PEAUtagPORTDEST@@@@UEAA@XZ; CList<tagPORTDEST *>::~CList<tagPORTDEST *>(void)
0x18001d8dc  mov     rcx, rdi; this
0x18001d8df  add     rsp, 28h
0x18001d8e3  pop     rdi
0x18001d8e4  pop     rsi
0x18001d8e5  pop     rbp
0x18001d8e6  pop     rbx
0x18001d8e7  jmp     ??1CDirectMusicPortDownload@@UEAA@XZ; CDirectMusicPortDownload::~CDirectMusicPortDownload(void)
```
