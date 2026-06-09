# CPlatformPools::~CPlatformPools(void)

- ea: `0x18007d038`
- end: `0x18007d18d`
- name: `??1CPlatformPools@@QEAA@XZ`
- size: `341`
- prototype: `void __fastcall(CPlatformPools *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x1801b1ae0`

## callees

- `0x180007f10`
- `0x18007d038`
- `0x18007d194`
- `0x18007d2c8`
- `0x18007d328`
- `0x180120030`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007d10a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007d117`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007d10a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007d117`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007d064`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007d064`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007d08d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007d08d`

## pseudocode

```c
void __fastcall CPlatformPools::~CPlatformPools(CPlatformPools *this)
{
  HANDLE ProcessHeap; // rax
  __int64 v3; // rdx
  _QWORD *v4; // r8
  void *v5; // rbp
  _QWORD *v6; // rdi
  void *v7; // rcx

  *(_QWORD *)this = &CPlatformPools::`vftable'{for `IRtwqPlatformEvents'};
  *((_QWORD *)this + 1) = &CPlatformPools::`vftable'{for `IRtwqItemNotification'};
  *((_QWORD *)this + 2) = &CPlatformPools::`vftable'{for `IRtwqPlatformConfiguration'};
  ProcessHeap = GetProcessHeap();
  v4 = (_QWORD *)*((_QWORD *)this + 368);
  v5 = ProcessHeap;
  if ( v4 )
  {
    do
    {
      v6 = (_QWORD *)*v4;
      if ( v4 != (_QWORD *)((char *)this + 2960) )
        HeapFree(v5, 0, v4);
      *((_QWORD *)this + 368) = v6;
      v4 = v6;
    }
    while ( v6 );
  }
  if ( *((int *)this + 730) >= 0 )
  {
    v7 = (void *)*((_QWORD *)this + 364);
    if ( v7 )
    {
      operator delete(v7);
      *((_QWORD *)this + 364) = 0;
    }
  }
  *((_DWORD *)this + 730) &= 0x80000000;
  *(_QWORD *)((char *)this + 2924) = 0;
  CFreeList<CallStackContextNode,128>::~CFreeList<CallStackContextNode,128>((char *)this + 2840, v3, v4);
  TracingFailureCache::~TracingFailureCache((CPlatformPools *)((char *)this + 2720));
  CallStackTracing::~CallStackTracing((CallStackTracing *)((char *)this + 480));
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 11);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 384));
  *((_QWORD *)this + 39) = &CObjectPoolT<CMFMediaBufferWrapper,400>::`vftable';
  CObjectPool::~CObjectPool((CObjectPool *)((char *)this + 312));
  *((_QWORD *)this + 30) = &CObjectPoolT<CMFMediaBufferWrapper,400>::`vftable';
  CObjectPool::~CObjectPool((CObjectPool *)((char *)this + 240));
  *((_QWORD *)this + 21) = &CObjectPoolT<CMFMediaBufferWrapper,400>::`vftable';
  CObjectPool::~CObjectPool((CObjectPool *)((char *)this + 168));
  *((_QWORD *)this + 12) = &CObjectPoolT<CMFMediaBufferWrapper,400>::`vftable';
  CObjectPool::~CObjectPool((CObjectPool *)((char *)this + 96));
  *((_QWORD *)this + 3) = &CObjectPoolT<CMFMediaBufferWrapper,400>::`vftable';
  CObjectPool::~CObjectPool((CObjectPool *)((char *)this + 24));
}

```

## disassembly

```asm
0x18007d038  push    rbx
0x18007d03a  push    rbp
0x18007d03b  push    rsi
0x18007d03c  push    rdi
0x18007d03d  sub     rsp, 28h
0x18007d041  lea     rax, ??_7CPlatformPools@@6BIRtwqPlatformEvents@@@; const CPlatformPools::`vftable'{for `IRtwqPlatformEvents'}
0x18007d048  mov     rbx, rcx
0x18007d04b  mov     [rcx], rax
0x18007d04e  lea     rax, ??_7CPlatformPools@@6BIRtwqItemNotification@@@; const CPlatformPools::`vftable'{for `IRtwqItemNotification'}
0x18007d055  mov     [rcx+8], rax
0x18007d059  lea     rax, ??_7CPlatformPools@@6BIRtwqPlatformConfiguration@@@; const CPlatformPools::`vftable'{for `IRtwqPlatformConfiguration'}
0x18007d060  mov     [rcx+10h], rax
0x18007d064  call    cs:__imp_GetProcessHeap
0x18007d06a  mov     r8, [rbx+0B80h]; lpMem
0x18007d071  mov     rbp, rax
0x18007d074  test    r8, r8
0x18007d077  jz      short loc_18007D0A2
0x18007d079  lea     rsi, [rbx+0B90h]
0x18007d080  mov     rdi, [r8]
0x18007d083  cmp     r8, rsi
0x18007d086  jz      short loc_18007D093
0x18007d088  xor     edx, edx; dwFlags
0x18007d08a  mov     rcx, rbp; hHeap
0x18007d08d  call    cs:__imp_HeapFree
0x18007d093  mov     [rbx+0B80h], rdi
0x18007d09a  mov     r8, rdi
0x18007d09d  test    rdi, rdi
0x18007d0a0  jnz     short loc_18007D080
0x18007d0a2  test    dword ptr [rbx+0B68h], 80000000h
0x18007d0ac  jnz     short loc_18007D0CA
0x18007d0ae  mov     rcx, [rbx+0B60h]; void *
0x18007d0b5  test    rcx, rcx
0x18007d0b8  jz      short loc_18007D0CA
0x18007d0ba  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007d0bf  mov     qword ptr [rbx+0B60h], 0
0x18007d0ca  and     dword ptr [rbx+0B68h], 80000000h
0x18007d0d4  lea     rcx, [rbx+0B18h]
0x18007d0db  mov     qword ptr [rbx+0B6Ch], 0
0x18007d0e6  call    ??1?$CFreeList@VCallStackContextNode@@$0IA@@@UEAA@XZ; CFreeList<CallStackContextNode,128>::~CFreeList<CallStackContextNode,128>(void)
0x18007d0eb  lea     rcx, [rbx+0AA0h]; this
0x18007d0f2  call    ??1TracingFailureCache@@QEAA@XZ; TracingFailureCache::~TracingFailureCache(void)
0x18007d0f7  lea     rcx, [rbx+1E0h]; this
0x18007d0fe  call    ??1CallStackTracing@@QEAA@XZ; CallStackTracing::~CallStackTracing(void)
0x18007d103  lea     rcx, [rbx+1B8h]; lpCriticalSection
0x18007d10a  call    cs:__imp_DeleteCriticalSection
0x18007d110  lea     rcx, [rbx+180h]; lpCriticalSection
0x18007d117  call    cs:__imp_DeleteCriticalSection
0x18007d11d  lea     rcx, [rbx+138h]; this
0x18007d124  lea     rax, ??_7?$CObjectPoolT@VCMFMediaBufferWrapper@@$0BJA@@@6B@; const CObjectPoolT<CMFMediaBufferWrapper,400>::`vftable'
0x18007d12b  mov     [rcx], rax
0x18007d12e  call    ??1CObjectPool@@UEAA@XZ; CObjectPool::~CObjectPool(void)
0x18007d133  lea     rcx, [rbx+0F0h]; this
0x18007d13a  lea     rax, ??_7?$CObjectPoolT@VCMFMediaBufferWrapper@@$0BJA@@@6B@; const CObjectPoolT<CMFMediaBufferWrapper,400>::`vftable'
0x18007d141  mov     [rcx], rax
0x18007d144  call    ??1CObjectPool@@UEAA@XZ; CObjectPool::~CObjectPool(void)
0x18007d149  lea     rcx, [rbx+0A8h]; this
0x18007d150  lea     rax, ??_7?$CObjectPoolT@VCMFMediaBufferWrapper@@$0BJA@@@6B@; const CObjectPoolT<CMFMediaBufferWrapper,400>::`vftable'
0x18007d157  mov     [rcx], rax
0x18007d15a  call    ??1CObjectPool@@UEAA@XZ; CObjectPool::~CObjectPool(void)
0x18007d15f  lea     rcx, [rbx+60h]; this
0x18007d163  lea     rax, ??_7?$CObjectPoolT@VCMFMediaBufferWrapper@@$0BJA@@@6B@; const CObjectPoolT<CMFMediaBufferWrapper,400>::`vftable'
0x18007d16a  mov     [rcx], rax
0x18007d16d  call    ??1CObjectPool@@UEAA@XZ; CObjectPool::~CObjectPool(void)
0x18007d172  lea     rcx, [rbx+18h]; this
0x18007d176  lea     rax, ??_7?$CObjectPoolT@VCMFMediaBufferWrapper@@$0BJA@@@6B@; const CObjectPoolT<CMFMediaBufferWrapper,400>::`vftable'
0x18007d17d  mov     [rcx], rax
0x18007d180  add     rsp, 28h
0x18007d184  pop     rdi
0x18007d185  pop     rsi
0x18007d186  pop     rbp
0x18007d187  pop     rbx
0x18007d188  jmp     ??1CObjectPool@@UEAA@XZ; CObjectPool::~CObjectPool(void)
```
