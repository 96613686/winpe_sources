# CSyncItemProgress::~CSyncItemProgress(void)

- ea: `0x1800401f8`
- end: `0x1800402a1`
- name: `??1CSyncItemProgress@@AEAA@XZ`
- size: `169`
- prototype: `void __fastcall(CSyncItemProgress *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800406d0`

## callees

- `0x180003c20`
- `0x180006500`
- `0x1800401f8`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004026e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004026e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040254`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040254`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180040264`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180040264`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004023a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004023a`

## pseudocode

```c
void __fastcall CSyncItemProgress::~CSyncItemProgress(CSyncItemProgress *this)
{
  void *v2; // rdx
  void *v3; // rdx
  __int64 v4; // rbx
  CRefCounted *v6; // rcx

  *(_QWORD *)this = &CSyncItemProgress::`vftable';
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 10) + 16LL))(*((_QWORD *)this + 10));
  CscUtil_HeapFree(*((void **)this + 5), v2);
  CscUtil_HeapFree(*((void **)this + 8), v3);
  CoTaskMemFree(*((LPVOID *)this + 4));
  v4 = **((_QWORD **)this + 11);
  if ( v4 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v4 + 8));
    EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 32));
    if ( (*(_DWORD *)(v4 + 24))-- == 1 )
      SetEvent(*(HANDLE *)(v4 + 16));
    LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 32));
    CRefCounted::ReleaseReference((CRefCounted *)v4);
  }
  v6 = (CRefCounted *)*((_QWORD *)this + 14);
  if ( v6 )
    CRefCounted::ReleaseReference(v6);
  _InterlockedDecrement(&g_cRefCount);
}

```

## disassembly

```asm
0x1800401f8  mov     [rsp+arg_8], rbx
0x1800401fd  mov     [rsp+arg_10], rsi
0x180040202  push    rdi
0x180040203  sub     rsp, 20h
0x180040207  lea     rax, ??_7CSyncItemProgress@@6B@; const CSyncItemProgress::`vftable'
0x18004020e  mov     rdi, rcx
0x180040211  mov     [rcx], rax
0x180040214  mov     rcx, [rcx+50h]
0x180040218  mov     rax, [rcx]
0x18004021b  mov     rax, [rax+10h]
0x18004021f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040224  mov     rcx, [rdi+28h]; lpMem
0x180040228  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x18004022d  mov     rcx, [rdi+40h]; lpMem
0x180040231  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x180040236  mov     rcx, [rdi+20h]; pv
0x18004023a  call    cs:__imp_CoTaskMemFree
0x180040240  mov     rax, [rdi+58h]
0x180040244  mov     rbx, [rax]
0x180040247  test    rbx, rbx
0x18004024a  jz      short loc_18004027C
0x18004024c  lock inc dword ptr [rbx+8]
0x180040250  lea     rcx, [rbx+20h]; lpCriticalSection
0x180040254  call    cs:__imp_EnterCriticalSection
0x18004025a  sub     dword ptr [rbx+18h], 1
0x18004025e  jnz     short loc_18004026A
0x180040260  mov     rcx, [rbx+10h]; hEvent
0x180040264  call    cs:__imp_SetEvent
0x18004026a  lea     rcx, [rbx+20h]; lpCriticalSection
0x18004026e  call    cs:__imp_LeaveCriticalSection
0x180040274  mov     rcx, rbx; this
0x180040277  call    ?ReleaseReference@CRefCounted@@QEAAXXZ; CRefCounted::ReleaseReference(void)
0x18004027c  mov     rcx, [rdi+70h]; this
0x180040280  test    rcx, rcx
0x180040283  jz      short loc_18004028A
0x180040285  call    ?ReleaseReference@CRefCounted@@QEAAXXZ; CRefCounted::ReleaseReference(void)
0x18004028a  lock dec cs:?g_cRefCount@@3JA; long g_cRefCount
0x180040291  mov     rbx, [rsp+28h+arg_8]
0x180040296  mov     rsi, [rsp+28h+arg_10]
0x18004029b  add     rsp, 20h
0x18004029f  pop     rdi
0x1800402a0  retn
```
