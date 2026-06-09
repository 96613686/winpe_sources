# HTTP_COMPRESSION::Terminate(void)

- ea: `0x180006e14`
- end: `0x180006fb8`
- name: `?Terminate@HTTP_COMPRESSION@@SAXXZ`
- size: `420`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180001010`
- `0x180006470`

## callees

- `0x180004250`
- `0x1800064e8`
- `0x1800066b8`
- `0x180006e14`

## import_xrefs

- `iisutil!??1STRA@@QEAA@XZ` at `0x180006f4f`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180006f73`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180006f4f`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180006f73`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x180006e59`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x180006e59`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006f2b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006f2b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180006eed`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180006f0f`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180006eed`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180006f0f`

## pseudocode

```c
void HTTP_COMPRESSION::Terminate(void)
{
  void *v0; // rbx
  unsigned int v1; // edx
  unsigned int i; // ebx
  struct COMPRESSION_SCHEME * near *v3; // rdi
  void *v4; // rbx
  void *v5; // rbx
  void *v6; // rbx

  switch ( HTTP_COMPRESSION::sm_InitStatus )
  {
    case 0:
      goto LABEL_16;
    case 1:
      goto LABEL_12;
    case 2:
    case 3:
      goto LABEL_7;
    case 4:
      goto LABEL_4;
    case 5:
      v0 = COMPRESSION_BUFFER::allocHandler;
      if ( COMPRESSION_BUFFER::allocHandler )
      {
        ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER((ALLOC_CACHE_HANDLER *)COMPRESSION_BUFFER::allocHandler);
        operator delete(v0);
      }
LABEL_4:
      if ( _InterlockedExchangeAdd(&MIME_MAP_TABLE::sm_lInitializeCount, 0xFFFFFFFF) == 1
        && MIME_MAP_TABLE::sm_pGlobalTable )
      {
        MIME_MAP_TABLE::Dereference(MIME_MAP_TABLE::sm_pGlobalTable);
        MIME_MAP_TABLE::sm_pGlobalTable = 0;
      }
LABEL_7:
      v1 = HTTP_COMPRESSION::sm_dwNumberOfSchemes;
      for ( i = 0; i < v1; ++i )
      {
        v3 = (&HTTP_COMPRESSION::sm_pCompressionSchemes)[i];
        if ( v3 )
        {
          COMPRESSION_SCHEME::~COMPRESSION_SCHEME((COMPRESSION_SCHEME *)(&HTTP_COMPRESSION::sm_pCompressionSchemes)[i]);
          operator delete(v3);
          v1 = HTTP_COMPRESSION::sm_dwNumberOfSchemes;
        }
      }
      HTTP_COMPRESSION::sm_dwNumberOfSchemes = 0;
LABEL_12:
      if ( HTTP_COMPRESSION::sm_hCacheTimer )
      {
        DeleteTimerQueueTimer(0, HTTP_COMPRESSION::sm_hCacheTimer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
        HTTP_COMPRESSION::sm_hCacheTimer = 0;
      }
      if ( HTTP_COMPRESSION::sm_hCpuTimer )
      {
        DeleteTimerQueueTimer(0, HTTP_COMPRESSION::sm_hCpuTimer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
        HTTP_COMPRESSION::sm_hCpuTimer = 0;
      }
LABEL_16:
      v4 = HTTP_COMPRESSION::sm_pstrCompressionDirectory;
      if ( HTTP_COMPRESSION::sm_pstrCompressionDirectory )
      {
        STRU::~STRU((STRU *)HTTP_COMPRESSION::sm_pstrCompressionDirectory);
        operator delete(v4);
        HTTP_COMPRESSION::sm_pstrCompressionDirectory = 0;
      }
      v5 = HTTP_COMPRESSION::sm_pstrCacheControlHeader;
      if ( HTTP_COMPRESSION::sm_pstrCacheControlHeader )
      {
        STRA::~STRA((STRA *)HTTP_COMPRESSION::sm_pstrCacheControlHeader);
        operator delete(v5);
        HTTP_COMPRESSION::sm_pstrCacheControlHeader = 0;
      }
      v6 = HTTP_COMPRESSION::sm_pstrExpiresHeader;
      if ( HTTP_COMPRESSION::sm_pstrExpiresHeader )
      {
        STRA::~STRA((STRA *)HTTP_COMPRESSION::sm_pstrExpiresHeader);
        operator delete(v6);
        HTTP_COMPRESSION::sm_pstrExpiresHeader = 0;
      }
      break;
    default:
      break;
  }
  HTTP_COMPRESSION::sm_InitStatus = 0;
}

```

## disassembly

```asm
0x180006e14  push    rsi
0x180006e16  sub     rsp, 20h
0x180006e1a  movsxd  rax, cs:?sm_InitStatus@HTTP_COMPRESSION@@0W4COMP_INIT_STATUS@@A; COMP_INIT_STATUS HTTP_COMPRESSION::sm_InitStatus
0x180006e21  xor     esi, esi
0x180006e23  cmp     eax, 5; switch 6 cases
0x180006e26  ja      def_180006E48; jumptable 0000000180006E48 default case
0x180006e2c  mov     [rsp+28h+arg_18], r14
0x180006e31  lea     r14, cs:180000000h
0x180006e38  mov     [rsp+28h+arg_8], rbx
0x180006e3d  mov     ecx, ds:(jpt_180006E48 - 180000000h)[r14+rax*4]
0x180006e45  add     rcx, r14
0x180006e48  jmp     rcx; switch jump
0x180006e4a  mov     rbx, cs:?allocHandler@COMPRESSION_BUFFER@@2PEAVALLOC_CACHE_HANDLER@@EA; jumptable 0000000180006E48 case 5
0x180006e51  test    rbx, rbx
0x180006e54  jz      short loc_180006E67; jumptable 0000000180006E48 case 4
0x180006e56  mov     rcx, rbx
0x180006e59  call    cs:__imp_??1ALLOC_CACHE_HANDLER@@QEAA@XZ; ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER(void)
0x180006e5f  mov     rcx, rbx; Block
0x180006e62  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006e67  mov     eax, 0FFFFFFFFh; jumptable 0000000180006E48 case 4
0x180006e6c  lock xadd cs:?sm_lInitializeCount@MIME_MAP_TABLE@@0JA, eax; long MIME_MAP_TABLE::sm_lInitializeCount
0x180006e74  cmp     eax, 1
0x180006e77  jnz     short loc_180006E91; jumptable 0000000180006E48 cases 2,3
0x180006e79  mov     rcx, cs:?sm_pGlobalTable@MIME_MAP_TABLE@@0PEAV1@EA; this
0x180006e80  test    rcx, rcx
0x180006e83  jz      short loc_180006E91; jumptable 0000000180006E48 cases 2,3
0x180006e85  call    ?Dereference@MIME_MAP_TABLE@@QEAAXXZ; MIME_MAP_TABLE::Dereference(void)
0x180006e8a  mov     cs:?sm_pGlobalTable@MIME_MAP_TABLE@@0PEAV1@EA, rsi; MIME_MAP_TABLE * MIME_MAP_TABLE::sm_pGlobalTable
0x180006e91  mov     edx, cs:?sm_dwNumberOfSchemes@HTTP_COMPRESSION@@0KA; jumptable 0000000180006E48 cases 2,3
0x180006e97  mov     ebx, esi
0x180006e99  test    edx, edx
0x180006e9b  jz      short loc_180006ED2
0x180006e9d  mov     [rsp+28h+arg_10], rdi
0x180006ea2  mov     eax, ebx
0x180006ea4  mov     rdi, rva ?sm_pCompressionSchemes@HTTP_COMPRESSION@@0PAPEAVCOMPRESSION_SCHEME@@A[r14+rax*8]; COMPRESSION_SCHEME * near * HTTP_COMPRESSION::sm_pCompressionSchemes ...
0x180006eac  test    rdi, rdi
0x180006eaf  jz      short loc_180006EC7
0x180006eb1  mov     rcx, rdi; this
0x180006eb4  call    ??1COMPRESSION_SCHEME@@QEAA@XZ; COMPRESSION_SCHEME::~COMPRESSION_SCHEME(void)
0x180006eb9  mov     rcx, rdi; Block
0x180006ebc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006ec1  mov     edx, cs:?sm_dwNumberOfSchemes@HTTP_COMPRESSION@@0KA; ulong HTTP_COMPRESSION::sm_dwNumberOfSchemes
0x180006ec7  inc     ebx
0x180006ec9  cmp     ebx, edx
0x180006ecb  jb      short loc_180006EA2
0x180006ecd  mov     rdi, [rsp+28h+arg_10]
0x180006ed2  mov     cs:?sm_dwNumberOfSchemes@HTTP_COMPRESSION@@0KA, esi; ulong HTTP_COMPRESSION::sm_dwNumberOfSchemes
0x180006ed8  mov     rdx, cs:?sm_hCacheTimer@HTTP_COMPRESSION@@0PEAXEA; jumptable 0000000180006E48 case 1
0x180006edf  test    rdx, rdx
0x180006ee2  jz      short loc_180006EFA
0x180006ee4  xor     ecx, ecx; TimerQueue
0x180006ee6  mov     r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180006eed  call    cs:__imp_DeleteTimerQueueTimer
0x180006ef3  mov     cs:?sm_hCacheTimer@HTTP_COMPRESSION@@0PEAXEA, rsi; void * HTTP_COMPRESSION::sm_hCacheTimer
0x180006efa  mov     rdx, cs:?sm_hCpuTimer@HTTP_COMPRESSION@@0PEAXEA; Timer
0x180006f01  test    rdx, rdx
0x180006f04  jz      short loc_180006F1C; jumptable 0000000180006E48 case 0
0x180006f06  xor     ecx, ecx; TimerQueue
0x180006f08  mov     r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180006f0f  call    cs:__imp_DeleteTimerQueueTimer
0x180006f15  mov     cs:?sm_hCpuTimer@HTTP_COMPRESSION@@0PEAXEA, rsi; void * HTTP_COMPRESSION::sm_hCpuTimer
0x180006f1c  mov     rbx, cs:?sm_pstrCompressionDirectory@HTTP_COMPRESSION@@0PEAVSTRU@@EA; jumptable 0000000180006E48 case 0
0x180006f23  test    rbx, rbx
0x180006f26  jz      short loc_180006F40
0x180006f28  mov     rcx, rbx
0x180006f2b  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180006f31  mov     rcx, rbx; Block
0x180006f34  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006f39  mov     cs:?sm_pstrCompressionDirectory@HTTP_COMPRESSION@@0PEAVSTRU@@EA, rsi; STRU * HTTP_COMPRESSION::sm_pstrCompressionDirectory
0x180006f40  mov     rbx, cs:?sm_pstrCacheControlHeader@HTTP_COMPRESSION@@0PEAVSTRA@@EA; STRA * HTTP_COMPRESSION::sm_pstrCacheControlHeader
0x180006f47  test    rbx, rbx
0x180006f4a  jz      short loc_180006F64
0x180006f4c  mov     rcx, rbx
0x180006f4f  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180006f55  mov     rcx, rbx; Block
0x180006f58  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006f5d  mov     cs:?sm_pstrCacheControlHeader@HTTP_COMPRESSION@@0PEAVSTRA@@EA, rsi; STRA * HTTP_COMPRESSION::sm_pstrCacheControlHeader
0x180006f64  mov     rbx, cs:?sm_pstrExpiresHeader@HTTP_COMPRESSION@@0PEAVSTRA@@EA; STRA * HTTP_COMPRESSION::sm_pstrExpiresHeader
0x180006f6b  test    rbx, rbx
0x180006f6e  jz      short loc_180006F88
0x180006f70  mov     rcx, rbx
0x180006f73  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180006f79  mov     rcx, rbx; Block
0x180006f7c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006f81  mov     cs:?sm_pstrExpiresHeader@HTTP_COMPRESSION@@0PEAVSTRA@@EA, rsi; STRA * HTTP_COMPRESSION::sm_pstrExpiresHeader
0x180006f88  mov     rbx, [rsp+28h+arg_8]
0x180006f8d  mov     r14, [rsp+28h+arg_18]
0x180006f92  mov     cs:?sm_InitStatus@HTTP_COMPRESSION@@0W4COMP_INIT_STATUS@@A, esi; jumptable 0000000180006E48 default case
0x180006f98  add     rsp, 20h
0x180006f9c  pop     rsi
0x180006f9d  retn
```
