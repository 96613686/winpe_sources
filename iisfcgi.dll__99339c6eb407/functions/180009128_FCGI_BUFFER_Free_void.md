# FCGI_BUFFER::Free(void)

- ea: `0x180009128`
- end: `0x1800091fd`
- name: `?Free@FCGI_BUFFER@@QEAAJXZ`
- size: `213`
- prototype: `__int64 __fastcall(FCGI_BUFFER *__hidden this)`
- caller_count: `21`
- callee_count: `2`
- tags: ``

## callers

- `0x180001d84`
- `0x180001e7c`
- `0x180002004`
- `0x180002eb4`
- `0x180002f60`
- `0x180003414`
- `0x1800035f8`
- `0x1800036b8`
- `0x1800039a0`
- `0x180003c08`
- `0x180005068`
- `0x18000621c`
- `0x180006670`
- `0x180006a0c`
- `0x180006bcc`
- `0x180009414`
- `0x18000b21c`
- `0x18000b3ac`
- `0x18000bac0`
- `0x18000bea0`
- `0x18000cfa0`

## callees

- `0x180008f50`
- `0x180009128`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000913f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000913f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800091ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800091ea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800091dd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800091dd`

## pseudocode

```c
__int64 __fastcall FCGI_BUFFER::Free(FCGI_BUFFER *this)
{
  __int64 v1; // rdi
  unsigned int v3; // ecx
  unsigned __int64 v4; // rax
  int *v5; // r9
  int v6; // r10d
  struct _LIST_ENTRY near **v7; // rdx
  struct _LIST_ENTRY near *v8; // r8

  v1 = *((unsigned int *)this + 2);
  EnterCriticalSection(&FCGI_BUFFER::sm_csLock);
  --FCGI_BUFFER::sm_cTotalAllocEntries;
  if ( FCGI_BUFFER::sm_fPageheap
    || (v3 = FCGI_BUFFER::sm_cTotalFreeEntries, FCGI_BUFFER::sm_cTotalFreeEntries >= 0xFA)
    || (v4 = (unsigned __int64)(v1 + 8) >> 10,
        v5 = (int *)&FCGI_BUFFER::sm_cFreeEntries + v4,
        v6 = *v5,
        (unsigned int)*v5 >= 0x19) )
  {
    FCGI_BUFFER::~FCGI_BUFFER(this);
    HeapFree(FCGI_BUFFER::sm_hHeap, 1u, this);
  }
  else
  {
    v7 = &(&FCGI_BUFFER::sm_FreeList)[2 * v4];
    v8 = *v7;
    if ( (struct _LIST_ENTRY near **)(*v7)->Blink != v7 )
      __fastfail(3u);
    *((_QWORD *)this + 4) = v8;
    *((_QWORD *)this + 5) = v7;
    v8->Blink = (struct _LIST_ENTRY *)((char *)this + 32);
    *v7 = (struct _LIST_ENTRY near *)((char *)this + 32);
    *v5 = v6 + 1;
    FCGI_BUFFER::sm_cTotalFreeEntries = v3 + 1;
  }
  LeaveCriticalSection(&FCGI_BUFFER::sm_csLock);
  return 0;
}

```

## disassembly

```asm
0x180009128  mov     [rsp+arg_0], rbx
0x18000912d  push    rdi
0x18000912e  sub     rsp, 20h
0x180009132  mov     edi, [rcx+8]
0x180009135  mov     rbx, rcx
0x180009138  lea     rcx, ?sm_csLock@FCGI_BUFFER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000913f  call    cs:__imp_EnterCriticalSection
0x180009145  dec     cs:?sm_cTotalAllocEntries@FCGI_BUFFER@@0KA; ulong FCGI_BUFFER::sm_cTotalAllocEntries
0x18000914b  cmp     cs:?sm_fPageheap@FCGI_BUFFER@@0HA, 0; int FCGI_BUFFER::sm_fPageheap
0x180009152  jnz     short loc_1800091C6
0x180009154  mov     ecx, cs:?sm_cTotalFreeEntries@FCGI_BUFFER@@0KA; ulong FCGI_BUFFER::sm_cTotalFreeEntries
0x18000915a  cmp     ecx, 0FAh
0x180009160  jnb     short loc_1800091C6
0x180009162  lea     rax, [rdi+8]
0x180009166  shr     rax, 0Ah
0x18000916a  lea     rdx, __ImageBase
0x180009171  lea     r9, rva ?sm_cFreeEntries@FCGI_BUFFER@@0PAKA[rdx]; ulong near * FCGI_BUFFER::sm_cFreeEntries ...
0x180009178  lea     r9, [r9+rax*4]
0x18000917c  mov     r10d, [r9]
0x18000917f  cmp     r10d, 19h
0x180009183  jnb     short loc_1800091C6
0x180009185  shl     rax, 4
0x180009189  lea     rdx, rva ?sm_FreeList@FCGI_BUFFER@@0PAU_LIST_ENTRY@@A[rdx]; _LIST_ENTRY near * FCGI_BUFFER::sm_FreeList ...
0x180009190  add     rdx, rax
0x180009193  mov     r8, [rdx]
0x180009196  cmp     [r8+8], rdx
0x18000919a  jz      short loc_1800091A3
0x18000919c  mov     ecx, 3
0x1800091a1  int     29h; Win8: RtlFailFast(ecx)
0x1800091a3  lea     rax, [rbx+20h]
0x1800091a7  inc     ecx
0x1800091a9  mov     [rax], r8
0x1800091ac  mov     [rax+8], rdx
0x1800091b0  mov     [r8+8], rax
0x1800091b4  mov     [rdx], rax
0x1800091b7  lea     eax, [r10+1]
0x1800091bb  mov     [r9], eax
0x1800091be  mov     cs:?sm_cTotalFreeEntries@FCGI_BUFFER@@0KA, ecx; ulong FCGI_BUFFER::sm_cTotalFreeEntries
0x1800091c4  jmp     short loc_1800091E3
0x1800091c6  mov     rcx, rbx; this
0x1800091c9  call    ??1FCGI_BUFFER@@AEAA@XZ; FCGI_BUFFER::~FCGI_BUFFER(void)
0x1800091ce  mov     rcx, cs:?sm_hHeap@FCGI_BUFFER@@0PEAXEA; hHeap
0x1800091d5  mov     r8, rbx; lpMem
0x1800091d8  mov     edx, 1; dwFlags
0x1800091dd  call    cs:__imp_HeapFree
0x1800091e3  lea     rcx, ?sm_csLock@FCGI_BUFFER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800091ea  call    cs:__imp_LeaveCriticalSection
0x1800091f0  mov     rbx, [rsp+28h+arg_0]
0x1800091f5  xor     eax, eax
0x1800091f7  add     rsp, 20h
0x1800091fb  pop     rdi
0x1800091fc  retn
```
