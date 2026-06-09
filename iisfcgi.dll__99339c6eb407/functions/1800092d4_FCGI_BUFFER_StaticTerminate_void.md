# FCGI_BUFFER::StaticTerminate(void)

- ea: `0x1800092d4`
- end: `0x1800093ac`
- name: `?StaticTerminate@FCGI_BUFFER@@SAJXZ`
- size: `216`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b180`

## callees

- `0x180008f50`
- `0x1800092d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000936b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000936b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000933e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000933e`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x180009387`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x180009387`

## pseudocode

```c
__int64 FCGI_BUFFER::StaticTerminate(void)
{
  __int64 v0; // rbx
  struct _LIST_ENTRY near **v1; // rdi
  struct _LIST_ENTRY near *v2; // rax
  struct _LIST_ENTRY *Flink; // rcx
  struct _LIST_ENTRY *v4; // rsi

  v0 = 0;
  do
  {
    v1 = &(&FCGI_BUFFER::sm_FreeList)[2 * (unsigned int)v0];
    while ( 1 )
    {
      v2 = *v1;
      if ( *v1 == (struct _LIST_ENTRY near *)v1 )
        break;
      if ( (struct _LIST_ENTRY near **)v2->Blink != v1 || (Flink = v2->Flink, v2->Flink->Blink != v2) )
        __fastfail(3u);
      v4 = v2 - 2;
      *v1 = Flink;
      Flink->Blink = (struct _LIST_ENTRY *)v1;
      if ( v2 != (struct _LIST_ENTRY near *)32 )
      {
        FCGI_BUFFER::~FCGI_BUFFER((FCGI_BUFFER *)&v2[-2]);
        HeapFree(FCGI_BUFFER::sm_hHeap, 1u, v4);
      }
      --*((_DWORD *)&FCGI_BUFFER::sm_cFreeEntries + v0);
      --FCGI_BUFFER::sm_cTotalFreeEntries;
    }
    v0 = (unsigned int)(v0 + 1);
  }
  while ( (unsigned int)v0 < 0x46 );
  if ( FCGI_BUFFER::sm_fLockInited )
  {
    DeleteCriticalSection(&FCGI_BUFFER::sm_csLock);
    FCGI_BUFFER::sm_fLockInited = 0;
  }
  if ( FCGI_BUFFER::sm_hHeap )
  {
    HeapDestroy(FCGI_BUFFER::sm_hHeap);
    FCGI_BUFFER::sm_hHeap = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x1800092d4  push    rbx
0x1800092d6  push    rbp
0x1800092d7  push    rsi
0x1800092d8  push    rdi
0x1800092d9  push    r15
0x1800092db  sub     rsp, 20h
0x1800092df  xor     ebx, ebx
0x1800092e1  lea     r15, __ImageBase
0x1800092e8  mov     eax, ebx
0x1800092ea  lea     rdi, rva ?sm_FreeList@FCGI_BUFFER@@0PAU_LIST_ENTRY@@A[r15]; _LIST_ENTRY near * FCGI_BUFFER::sm_FreeList ...
0x1800092f1  shl     rax, 4
0x1800092f5  add     rdi, rax
0x1800092f8  mov     rax, [rdi]
0x1800092fb  cmp     rax, rdi
0x1800092fe  jz      short loc_180009354
0x180009300  cmp     [rax+8], rdi
0x180009304  jnz     loc_1800093A5
0x18000930a  mov     rcx, [rax]
0x18000930d  cmp     [rcx+8], rax
0x180009311  jnz     loc_1800093A5
0x180009317  lea     rsi, [rax-20h]
0x18000931b  mov     [rdi], rcx
0x18000931e  mov     [rcx+8], rdi
0x180009322  test    rsi, rsi
0x180009325  jz      short loc_180009344
0x180009327  mov     rcx, rsi; this
0x18000932a  call    ??1FCGI_BUFFER@@AEAA@XZ; FCGI_BUFFER::~FCGI_BUFFER(void)
0x18000932f  mov     rcx, cs:?sm_hHeap@FCGI_BUFFER@@0PEAXEA; hHeap
0x180009336  mov     r8, rsi; lpMem
0x180009339  mov     edx, 1; dwFlags
0x18000933e  call    cs:__imp_HeapFree
0x180009344  dec     rva ?sm_cFreeEntries@FCGI_BUFFER@@0PAKA[r15+rbx*4]; ulong near * FCGI_BUFFER::sm_cFreeEntries ...
0x18000934c  dec     cs:?sm_cTotalFreeEntries@FCGI_BUFFER@@0KA; ulong FCGI_BUFFER::sm_cTotalFreeEntries
0x180009352  jmp     short loc_1800092F8
0x180009354  inc     ebx
0x180009356  cmp     ebx, 46h ; 'F'
0x180009359  jb      short loc_1800092E8
0x18000935b  cmp     cs:?sm_fLockInited@FCGI_BUFFER@@0HA, 0; int FCGI_BUFFER::sm_fLockInited
0x180009362  jz      short loc_18000937B
0x180009364  lea     rcx, ?sm_csLock@FCGI_BUFFER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000936b  call    cs:__imp_DeleteCriticalSection
0x180009371  mov     cs:?sm_fLockInited@FCGI_BUFFER@@0HA, 0; int FCGI_BUFFER::sm_fLockInited
0x18000937b  mov     rcx, cs:?sm_hHeap@FCGI_BUFFER@@0PEAXEA; hHeap
0x180009382  test    rcx, rcx
0x180009385  jz      short loc_180009398
0x180009387  call    cs:__imp_HeapDestroy
0x18000938d  mov     cs:?sm_hHeap@FCGI_BUFFER@@0PEAXEA, 0; void * FCGI_BUFFER::sm_hHeap
0x180009398  xor     eax, eax
0x18000939a  add     rsp, 20h
0x18000939e  pop     r15
0x1800093a0  pop     rdi
0x1800093a1  pop     rsi
0x1800093a2  pop     rbp
0x1800093a3  pop     rbx
0x1800093a4  retn
0x1800093a5  mov     ecx, 3
0x1800093aa  int     29h; Win8: RtlFailFast(ecx)
```
