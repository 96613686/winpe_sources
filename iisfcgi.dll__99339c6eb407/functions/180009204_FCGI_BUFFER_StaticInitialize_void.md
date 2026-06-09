# FCGI_BUFFER::StaticInitialize(void)

- ea: `0x180009204`
- end: `0x1800092cb`
- name: `?StaticInitialize@FCGI_BUFFER@@SAJXZ`
- size: `199`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000b088`

## callees

- `0x180009204`
- `0x18000edde`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009224`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009224`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000924e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000924e`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x180009212`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x180009212`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800092af`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800092af`

## string_xrefs

- `0x18000929c`: `verifier.dll`

## pseudocode

```c
__int64 FCGI_BUFFER::StaticInitialize(void)
{
  signed int LastError; // eax
  unsigned int v1; // ebx
  __int64 v2; // rdx
  __int64 v3; // rcx
  struct _LIST_ENTRY near **v4; // rax

  FCGI_BUFFER::sm_hHeap = HeapCreate(1u, 0, 0);
  if ( FCGI_BUFFER::sm_hHeap && InitializeCriticalSectionAndSpinCount(&FCGI_BUFFER::sm_csLock, 0x3E8u) )
  {
    FCGI_BUFFER::sm_fLockInited = 1;
    v1 = 0;
    memset_0(&FCGI_BUFFER::sm_cFreeEntries, 0, 0x118u);
    v2 = 0;
    v3 = 0;
    do
    {
      v4 = &(&FCGI_BUFFER::sm_FreeList)[v3];
      ++v2;
      *(&FCGI_BUFFER::sm_FreeList + v3 + 1) = (struct _LIST_ENTRY near *)&(&FCGI_BUFFER::sm_FreeList)[v3];
      v3 += 2;
      *v4 = (struct _LIST_ENTRY near *)v4;
    }
    while ( v2 != 70 );
    FCGI_BUFFER::sm_cTotalFreeEntries = 0;
    FCGI_BUFFER::sm_cTotalAllocEntries = 0;
    FCGI_BUFFER::sm_fPageheap = GetModuleHandleW(L"verifier.dll") != 0;
  }
  else
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v1;
}

```

## disassembly

```asm
0x180009204  push    rbx
0x180009206  sub     rsp, 20h
0x18000920a  xor     edx, edx; dwInitialSize
0x18000920c  xor     r8d, r8d; dwMaximumSize
0x18000920f  lea     ecx, [rdx+1]; flOptions
0x180009212  call    cs:__imp_HeapCreate
0x180009218  mov     cs:?sm_hHeap@FCGI_BUFFER@@0PEAXEA, rax; void * FCGI_BUFFER::sm_hHeap
0x18000921f  test    rax, rax
0x180009222  jnz     short loc_180009242
0x180009224  call    cs:__imp_GetLastError
0x18000922a  mov     ebx, eax
0x18000922c  test    eax, eax
0x18000922e  jle     loc_1800092C3
0x180009234  movzx   ebx, ax
0x180009237  or      ebx, 80070000h
0x18000923d  jmp     loc_1800092C3
0x180009242  mov     edx, 3E8h; dwSpinCount
0x180009247  lea     rcx, ?sm_csLock@FCGI_BUFFER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000924e  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180009254  test    eax, eax
0x180009256  jz      short loc_180009224
0x180009258  xor     edx, edx; Val
0x18000925a  mov     cs:?sm_fLockInited@FCGI_BUFFER@@0HA, 1; int FCGI_BUFFER::sm_fLockInited
0x180009264  mov     r8d, 118h; Size
0x18000926a  lea     rcx, ?sm_cFreeEntries@FCGI_BUFFER@@0PAKA; void *
0x180009271  xor     ebx, ebx
0x180009273  call    memset_0
0x180009278  xor     edx, edx
0x18000927a  lea     r8, ?sm_FreeList@FCGI_BUFFER@@0PAU_LIST_ENTRY@@A; _LIST_ENTRY near * FCGI_BUFFER::sm_FreeList
0x180009281  xor     ecx, ecx
0x180009283  lea     rax, [rcx+r8]
0x180009287  inc     rdx
0x18000928a  mov     [rcx+r8+8], rax
0x18000928f  lea     rcx, [rcx+10h]
0x180009293  mov     [rax], rax
0x180009296  cmp     rdx, 46h ; 'F'
0x18000929a  jnz     short loc_180009283
0x18000929c  lea     rcx, ModuleName; "verifier.dll"
0x1800092a3  mov     cs:?sm_cTotalFreeEntries@FCGI_BUFFER@@0KA, ebx; ulong FCGI_BUFFER::sm_cTotalFreeEntries
0x1800092a9  mov     cs:?sm_cTotalAllocEntries@FCGI_BUFFER@@0KA, ebx; ulong FCGI_BUFFER::sm_cTotalAllocEntries
0x1800092af  call    cs:__imp_GetModuleHandleW
0x1800092b5  xor     ecx, ecx
0x1800092b7  test    rax, rax
0x1800092ba  setnz   cl
0x1800092bd  mov     cs:?sm_fPageheap@FCGI_BUFFER@@0HA, ecx; int FCGI_BUFFER::sm_fPageheap
0x1800092c3  mov     eax, ebx
0x1800092c5  add     rsp, 20h
0x1800092c9  pop     rbx
0x1800092ca  retn
```
