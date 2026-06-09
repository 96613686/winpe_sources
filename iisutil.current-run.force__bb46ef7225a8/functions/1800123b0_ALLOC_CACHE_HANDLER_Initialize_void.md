# ALLOC_CACHE_HANDLER::Initialize(void)

- ea: `0x1800123b0`
- end: `0x180012425`
- name: `?Initialize@ALLOC_CACHE_HANDLER@@SAHXZ`
- size: `117`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800123b0`
- `0x18001527c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800123ef`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800123ef`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001241d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001241d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800123c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800123c1`

## pseudocode

```c
__int64 ALLOC_CACHE_HANDLER::Initialize(void)
{
  unsigned int v0; // ebx

  ALLOC_CACHE_HANDLER::sm_fPageHeapEnabled = IsPageheapEnabled();
  ALLOC_CACHE_HANDLER::sm_hHeap = GetProcessHeap();
  qword_18004D9C8 = (__int64)&ALLOC_CACHE_HANDLER::sm_lItemsHead;
  ALLOC_CACHE_HANDLER::sm_lItemsHead.Flink = &ALLOC_CACHE_HANDLER::sm_lItemsHead;
  if ( InitializeCriticalSectionAndSpinCount(&ALLOC_CACHE_HANDLER::sm_csItems, 0x800003E8) )
  {
    v0 = 1;
  }
  else
  {
    v0 = 0;
    if ( !ALLOC_CACHE_HANDLER::sm_fInitCsItems )
      return v0;
    DeleteCriticalSection(&ALLOC_CACHE_HANDLER::sm_csItems);
  }
  ALLOC_CACHE_HANDLER::sm_fInitCsItems = v0;
  return v0;
}

```

## disassembly

```asm
0x1800123b0  push    rbx
0x1800123b2  sub     rsp, 20h
0x1800123b6  call    ?IsPageheapEnabled@@YAHXZ; IsPageheapEnabled(void)
0x1800123bb  mov     cs:?sm_fPageHeapEnabled@ALLOC_CACHE_HANDLER@@0HA, eax; int ALLOC_CACHE_HANDLER::sm_fPageHeapEnabled
0x1800123c1  call    cs:__imp_GetProcessHeap
0x1800123c7  mov     cs:?sm_hHeap@ALLOC_CACHE_HANDLER@@0PEAXEA, rax; void * ALLOC_CACHE_HANDLER::sm_hHeap
0x1800123ce  mov     edx, 800003E8h; dwSpinCount
0x1800123d3  lea     rcx, ?sm_csItems@ALLOC_CACHE_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800123da  lea     rax, ?sm_lItemsHead@ALLOC_CACHE_HANDLER@@0U_LIST_ENTRY@@A; _LIST_ENTRY ALLOC_CACHE_HANDLER::sm_lItemsHead
0x1800123e1  mov     cs:qword_18004D9C8, rax
0x1800123e8  mov     cs:?sm_lItemsHead@ALLOC_CACHE_HANDLER@@0U_LIST_ENTRY@@A, rax; _LIST_ENTRY ALLOC_CACHE_HANDLER::sm_lItemsHead
0x1800123ef  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800123f5  test    eax, eax
0x1800123f7  jz      short loc_18001240C
0x1800123f9  mov     ebx, 1
0x1800123fe  mov     cs:?sm_fInitCsItems@ALLOC_CACHE_HANDLER@@0HA, ebx; int ALLOC_CACHE_HANDLER::sm_fInitCsItems
0x180012404  mov     eax, ebx
0x180012406  add     rsp, 20h
0x18001240a  pop     rbx
0x18001240b  retn
0x18001240c  xor     ebx, ebx
0x18001240e  cmp     cs:?sm_fInitCsItems@ALLOC_CACHE_HANDLER@@0HA, ebx; int ALLOC_CACHE_HANDLER::sm_fInitCsItems
0x180012414  jz      short loc_180012404
0x180012416  lea     rcx, ?sm_csItems@ALLOC_CACHE_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001241d  call    cs:__imp_DeleteCriticalSection
0x180012423  jmp     short loc_1800123FE
```
