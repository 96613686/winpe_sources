# EVENT_LOG::Terminate(void)

- ea: `0x1800227a0`
- end: `0x180022845`
- name: `?Terminate@EVENT_LOG@@SAXXZ`
- size: `165`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180014ca0`

## callees

- `0x180022030`
- `0x1800227a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800227ba`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800227ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022818`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022818`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022804`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022804`

## pseudocode

```c
void EVENT_LOG::Terminate(void)
{
  char *v0; // rbx
  __int64 i; // rdi
  HANDLE ProcessHeap; // rax

  if ( EVENT_LOG::sm_fLockInitialized )
  {
    DeleteCriticalSection(&EVENT_LOG::sm_csLock);
    EVENT_LOG::sm_fLockInitialized = 0;
  }
  v0 = (char *)EVENT_LOG::sm_pEventLogSource;
  if ( EVENT_LOG::sm_pEventLogSource )
  {
    for ( i = 0; (unsigned int)i < EVENT_LOG::sm_cEventLogSource; i = (unsigned int)(i + 1) )
    {
      EVENT_LOG::DestroyEventLogSource((struct _EVENT_LOG_SOURCE *)&v0[24 * i]);
      v0 = (char *)EVENT_LOG::sm_pEventLogSource;
    }
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v0);
    EVENT_LOG::sm_pEventLogSource = 0;
    EVENT_LOG::sm_cEventLogSource = 0;
  }
}

```

## disassembly

```asm
0x1800227a0  mov     [rsp+arg_0], rbx
0x1800227a5  push    rdi
0x1800227a6  sub     rsp, 20h
0x1800227aa  cmp     cs:?sm_fLockInitialized@EVENT_LOG@@0HA, 0; int EVENT_LOG::sm_fLockInitialized
0x1800227b1  jz      short loc_1800227D0
0x1800227b3  lea     rcx, ?sm_csLock@EVENT_LOG@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800227ba  call    cs:__imp_DeleteCriticalSection
0x1800227c1  nop     dword ptr [rax+rax+00h]
0x1800227c6  mov     cs:?sm_fLockInitialized@EVENT_LOG@@0HA, 0; int EVENT_LOG::sm_fLockInitialized
0x1800227d0  mov     rbx, cs:?sm_pEventLogSource@EVENT_LOG@@0PEAU_EVENT_LOG_SOURCE@@EA; _EVENT_LOG_SOURCE * EVENT_LOG::sm_pEventLogSource
0x1800227d7  test    rbx, rbx
0x1800227da  jz      short loc_180022839
0x1800227dc  xor     edi, edi
0x1800227de  cmp     cs:?sm_cEventLogSource@EVENT_LOG@@0KA, edi; ulong EVENT_LOG::sm_cEventLogSource
0x1800227e4  jbe     short loc_180022804
0x1800227e6  lea     rcx, [rdi+rdi*2]
0x1800227ea  lea     rcx, [rbx+rcx*8]; struct _EVENT_LOG_SOURCE *
0x1800227ee  call    ?DestroyEventLogSource@EVENT_LOG@@CAXPEAU_EVENT_LOG_SOURCE@@@Z; EVENT_LOG::DestroyEventLogSource(_EVENT_LOG_SOURCE *)
0x1800227f3  mov     rbx, cs:?sm_pEventLogSource@EVENT_LOG@@0PEAU_EVENT_LOG_SOURCE@@EA; _EVENT_LOG_SOURCE * EVENT_LOG::sm_pEventLogSource
0x1800227fa  inc     edi
0x1800227fc  cmp     edi, cs:?sm_cEventLogSource@EVENT_LOG@@0KA; ulong EVENT_LOG::sm_cEventLogSource
0x180022802  jb      short loc_1800227E6
0x180022804  call    cs:__imp_GetProcessHeap
0x18002280b  nop     dword ptr [rax+rax+00h]
0x180022810  mov     r8, rbx; lpMem
0x180022813  xor     edx, edx; dwFlags
0x180022815  mov     rcx, rax; hHeap
0x180022818  call    cs:__imp_HeapFree
0x18002281f  nop     dword ptr [rax+rax+00h]
0x180022824  mov     cs:?sm_pEventLogSource@EVENT_LOG@@0PEAU_EVENT_LOG_SOURCE@@EA, 0; _EVENT_LOG_SOURCE * EVENT_LOG::sm_pEventLogSource
0x18002282f  mov     cs:?sm_cEventLogSource@EVENT_LOG@@0KA, 0; ulong EVENT_LOG::sm_cEventLogSource
0x180022839  mov     rbx, [rsp+28h+arg_0]
0x18002283e  add     rsp, 20h
0x180022842  pop     rdi
0x180022843  retn
```
