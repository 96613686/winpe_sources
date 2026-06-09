# HTTP_COMPRESSION::Terminate(void)

- ea: `0x180008904`
- end: `0x180008aa8`
- name: `?Terminate@HTTP_COMPRESSION@@SAXXZ`
- size: `420`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180002bb0`
- `0x180007ef0`

## callees

- `0x1800054a0`
- `0x180007f68`
- `0x180008480`
- `0x180008904`

## import_xrefs

- `iisutil!??1STRA@@QEAA@XZ` at `0x180008a3f`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008a63`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008a3f`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008a63`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x180008949`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x180008949`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180008a1b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180008a1b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800089dd`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800089ff`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800089dd`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800089ff`

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
0x180008904  push    rsi
0x180008906  sub     rsp, 20h
0x18000890a  movsxd  rax, cs:?sm_InitStatus@HTTP_COMPRESSION@@0W4COMP_INIT_STATUS@@A; COMP_INIT_STATUS HTTP_COMPRESSION::sm_InitStatus
0x180008911  xor     esi, esi
0x180008913  cmp     eax, 5; switch 6 cases
0x180008916  ja      def_180008938; jumptable 0000000180008938 default case
0x18000891c  mov     [rsp+28h+arg_18], r14
0x180008921  lea     r14, cs:180000000h
0x180008928  mov     [rsp+28h+arg_8], rbx
0x18000892d  mov     ecx, ds:(jpt_180008938 - 180000000h)[r14+rax*4]
0x180008935  add     rcx, r14
0x180008938  jmp     rcx; switch jump
0x18000893a  mov     rbx, cs:?allocHandler@COMPRESSION_BUFFER@@2PEAVALLOC_CACHE_HANDLER@@EA; jumptable 0000000180008938 case 5
0x180008941  test    rbx, rbx
0x180008944  jz      short loc_180008957; jumptable 0000000180008938 case 4
0x180008946  mov     rcx, rbx
0x180008949  call    cs:__imp_??1ALLOC_CACHE_HANDLER@@QEAA@XZ; ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER(void)
0x18000894f  mov     rcx, rbx; Block
0x180008952  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008957  mov     eax, 0FFFFFFFFh; jumptable 0000000180008938 case 4
0x18000895c  lock xadd cs:?sm_lInitializeCount@MIME_MAP_TABLE@@0JA, eax; long MIME_MAP_TABLE::sm_lInitializeCount
0x180008964  cmp     eax, 1
0x180008967  jnz     short loc_180008981; jumptable 0000000180008938 cases 2,3
0x180008969  mov     rcx, cs:?sm_pGlobalTable@MIME_MAP_TABLE@@0PEAV1@EA; this
0x180008970  test    rcx, rcx
0x180008973  jz      short loc_180008981; jumptable 0000000180008938 cases 2,3
0x180008975  call    ?Dereference@MIME_MAP_TABLE@@QEAAXXZ; MIME_MAP_TABLE::Dereference(void)
0x18000897a  mov     cs:?sm_pGlobalTable@MIME_MAP_TABLE@@0PEAV1@EA, rsi; MIME_MAP_TABLE * MIME_MAP_TABLE::sm_pGlobalTable
0x180008981  mov     edx, cs:?sm_dwNumberOfSchemes@HTTP_COMPRESSION@@0KA; jumptable 0000000180008938 cases 2,3
0x180008987  mov     ebx, esi
0x180008989  test    edx, edx
0x18000898b  jz      short loc_1800089C2
0x18000898d  mov     [rsp+28h+arg_10], rdi
0x180008992  mov     eax, ebx
0x180008994  mov     rdi, rva ?sm_pCompressionSchemes@HTTP_COMPRESSION@@0PAPEAVCOMPRESSION_SCHEME@@A[r14+rax*8]; COMPRESSION_SCHEME * near * HTTP_COMPRESSION::sm_pCompressionSchemes ...
0x18000899c  test    rdi, rdi
0x18000899f  jz      short loc_1800089B7
0x1800089a1  mov     rcx, rdi; this
0x1800089a4  call    ??1COMPRESSION_SCHEME@@QEAA@XZ; COMPRESSION_SCHEME::~COMPRESSION_SCHEME(void)
0x1800089a9  mov     rcx, rdi; Block
0x1800089ac  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800089b1  mov     edx, cs:?sm_dwNumberOfSchemes@HTTP_COMPRESSION@@0KA; ulong HTTP_COMPRESSION::sm_dwNumberOfSchemes
0x1800089b7  inc     ebx
0x1800089b9  cmp     ebx, edx
0x1800089bb  jb      short loc_180008992
0x1800089bd  mov     rdi, [rsp+28h+arg_10]
0x1800089c2  mov     cs:?sm_dwNumberOfSchemes@HTTP_COMPRESSION@@0KA, esi; ulong HTTP_COMPRESSION::sm_dwNumberOfSchemes
0x1800089c8  mov     rdx, cs:?sm_hCacheTimer@HTTP_COMPRESSION@@0PEAXEA; jumptable 0000000180008938 case 1
0x1800089cf  test    rdx, rdx
0x1800089d2  jz      short loc_1800089EA
0x1800089d4  xor     ecx, ecx; TimerQueue
0x1800089d6  mov     r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800089dd  call    cs:__imp_DeleteTimerQueueTimer
0x1800089e3  mov     cs:?sm_hCacheTimer@HTTP_COMPRESSION@@0PEAXEA, rsi; void * HTTP_COMPRESSION::sm_hCacheTimer
0x1800089ea  mov     rdx, cs:?sm_hCpuTimer@HTTP_COMPRESSION@@0PEAXEA; Timer
0x1800089f1  test    rdx, rdx
0x1800089f4  jz      short loc_180008A0C; jumptable 0000000180008938 case 0
0x1800089f6  xor     ecx, ecx; TimerQueue
0x1800089f8  mov     r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800089ff  call    cs:__imp_DeleteTimerQueueTimer
0x180008a05  mov     cs:?sm_hCpuTimer@HTTP_COMPRESSION@@0PEAXEA, rsi; void * HTTP_COMPRESSION::sm_hCpuTimer
0x180008a0c  mov     rbx, cs:?sm_pstrCompressionDirectory@HTTP_COMPRESSION@@0PEAVSTRU@@EA; jumptable 0000000180008938 case 0
0x180008a13  test    rbx, rbx
0x180008a16  jz      short loc_180008A30
0x180008a18  mov     rcx, rbx
0x180008a1b  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180008a21  mov     rcx, rbx; Block
0x180008a24  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008a29  mov     cs:?sm_pstrCompressionDirectory@HTTP_COMPRESSION@@0PEAVSTRU@@EA, rsi; STRU * HTTP_COMPRESSION::sm_pstrCompressionDirectory
0x180008a30  mov     rbx, cs:?sm_pstrCacheControlHeader@HTTP_COMPRESSION@@0PEAVSTRA@@EA; STRA * HTTP_COMPRESSION::sm_pstrCacheControlHeader
0x180008a37  test    rbx, rbx
0x180008a3a  jz      short loc_180008A54
0x180008a3c  mov     rcx, rbx
0x180008a3f  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180008a45  mov     rcx, rbx; Block
0x180008a48  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008a4d  mov     cs:?sm_pstrCacheControlHeader@HTTP_COMPRESSION@@0PEAVSTRA@@EA, rsi; STRA * HTTP_COMPRESSION::sm_pstrCacheControlHeader
0x180008a54  mov     rbx, cs:?sm_pstrExpiresHeader@HTTP_COMPRESSION@@0PEAVSTRA@@EA; STRA * HTTP_COMPRESSION::sm_pstrExpiresHeader
0x180008a5b  test    rbx, rbx
0x180008a5e  jz      short loc_180008A78
0x180008a60  mov     rcx, rbx
0x180008a63  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180008a69  mov     rcx, rbx; Block
0x180008a6c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008a71  mov     cs:?sm_pstrExpiresHeader@HTTP_COMPRESSION@@0PEAVSTRA@@EA, rsi; STRA * HTTP_COMPRESSION::sm_pstrExpiresHeader
0x180008a78  mov     rbx, [rsp+28h+arg_8]
0x180008a7d  mov     r14, [rsp+28h+arg_18]
0x180008a82  mov     cs:?sm_InitStatus@HTTP_COMPRESSION@@0W4COMP_INIT_STATUS@@A, esi; jumptable 0000000180008938 default case
0x180008a88  add     rsp, 20h
0x180008a8c  pop     rsi
0x180008a8d  retn
```
