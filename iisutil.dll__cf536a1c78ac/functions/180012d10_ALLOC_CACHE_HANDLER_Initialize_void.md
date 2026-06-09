# ALLOC_CACHE_HANDLER::Initialize(void)

- ea: `0x180012d10`
- end: `0x180012d98`
- name: `?Initialize@ALLOC_CACHE_HANDLER@@SAHXZ`
- size: `136`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180012d10`
- `0x180015dbc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180012d55`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180012d55`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180012d8a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180012d8a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012d21`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012d21`

## pseudocode

```c
__int64 ALLOC_CACHE_HANDLER::Initialize(void)
{
  unsigned int v0; // ebx

  ALLOC_CACHE_HANDLER::sm_fPageHeapEnabled = IsPageheapEnabled();
  ALLOC_CACHE_HANDLER::sm_hHeap = GetProcessHeap();
  qword_18004F9C8 = (__int64)&ALLOC_CACHE_HANDLER::sm_lItemsHead;
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
0x180012d10  push    rbx
0x180012d12  sub     rsp, 20h
0x180012d16  call    ?IsPageheapEnabled@@YAHXZ; IsPageheapEnabled(void)
0x180012d1b  mov     cs:?sm_fPageHeapEnabled@ALLOC_CACHE_HANDLER@@0HA, eax; int ALLOC_CACHE_HANDLER::sm_fPageHeapEnabled
0x180012d21  call    cs:__imp_GetProcessHeap
0x180012d28  nop     dword ptr [rax+rax+00h]
0x180012d2d  mov     cs:?sm_hHeap@ALLOC_CACHE_HANDLER@@0PEAXEA, rax; void * ALLOC_CACHE_HANDLER::sm_hHeap
0x180012d34  mov     edx, 800003E8h; dwSpinCount
0x180012d39  lea     rcx, ?sm_csItems@ALLOC_CACHE_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180012d40  lea     rax, ?sm_lItemsHead@ALLOC_CACHE_HANDLER@@0U_LIST_ENTRY@@A; _LIST_ENTRY ALLOC_CACHE_HANDLER::sm_lItemsHead
0x180012d47  mov     cs:qword_18004F9C8, rax
0x180012d4e  mov     cs:?sm_lItemsHead@ALLOC_CACHE_HANDLER@@0U_LIST_ENTRY@@A, rax; _LIST_ENTRY ALLOC_CACHE_HANDLER::sm_lItemsHead
0x180012d55  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180012d5c  nop     dword ptr [rax+rax+00h]
0x180012d61  test    eax, eax
0x180012d63  jz      short loc_180012D79
0x180012d65  mov     ebx, 1
0x180012d6a  mov     cs:?sm_fInitCsItems@ALLOC_CACHE_HANDLER@@0HA, ebx; int ALLOC_CACHE_HANDLER::sm_fInitCsItems
0x180012d70  mov     eax, ebx
0x180012d72  add     rsp, 20h
0x180012d76  pop     rbx
0x180012d77  retn
0x180012d79  xor     ebx, ebx
0x180012d7b  cmp     cs:?sm_fInitCsItems@ALLOC_CACHE_HANDLER@@0HA, ebx; int ALLOC_CACHE_HANDLER::sm_fInitCsItems
0x180012d81  jz      short loc_180012D70
0x180012d83  lea     rcx, ?sm_csItems@ALLOC_CACHE_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180012d8a  call    cs:__imp_DeleteCriticalSection
0x180012d91  nop     dword ptr [rax+rax+00h]
0x180012d96  jmp     short loc_180012D6A
```
