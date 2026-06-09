# EVENT_LOG::Terminate(void)

- ea: `0x1800211e0`
- end: `0x180021272`
- name: `?Terminate@EVENT_LOG@@SAXXZ`
- size: `146`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180014240`

## callees

- `0x180020b20`
- `0x1800211e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800211fa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800211fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002124c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002124c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002123e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002123e`

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
0x1800211e0  mov     [rsp+arg_0], rbx
0x1800211e5  push    rdi
0x1800211e6  sub     rsp, 20h
0x1800211ea  cmp     cs:?sm_fLockInitialized@EVENT_LOG@@0HA, 0; int EVENT_LOG::sm_fLockInitialized
0x1800211f1  jz      short loc_18002120A
0x1800211f3  lea     rcx, ?sm_csLock@EVENT_LOG@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800211fa  call    cs:__imp_DeleteCriticalSection
0x180021200  mov     cs:?sm_fLockInitialized@EVENT_LOG@@0HA, 0; int EVENT_LOG::sm_fLockInitialized
0x18002120a  mov     rbx, cs:?sm_pEventLogSource@EVENT_LOG@@0PEAU_EVENT_LOG_SOURCE@@EA; _EVENT_LOG_SOURCE * EVENT_LOG::sm_pEventLogSource
0x180021211  test    rbx, rbx
0x180021214  jz      short loc_180021267
0x180021216  xor     edi, edi
0x180021218  cmp     cs:?sm_cEventLogSource@EVENT_LOG@@0KA, edi; ulong EVENT_LOG::sm_cEventLogSource
0x18002121e  jbe     short loc_18002123E
0x180021220  lea     rcx, [rdi+rdi*2]
0x180021224  lea     rcx, [rbx+rcx*8]; struct _EVENT_LOG_SOURCE *
0x180021228  call    ?DestroyEventLogSource@EVENT_LOG@@CAXPEAU_EVENT_LOG_SOURCE@@@Z; EVENT_LOG::DestroyEventLogSource(_EVENT_LOG_SOURCE *)
0x18002122d  mov     rbx, cs:?sm_pEventLogSource@EVENT_LOG@@0PEAU_EVENT_LOG_SOURCE@@EA; _EVENT_LOG_SOURCE * EVENT_LOG::sm_pEventLogSource
0x180021234  inc     edi
0x180021236  cmp     edi, cs:?sm_cEventLogSource@EVENT_LOG@@0KA; ulong EVENT_LOG::sm_cEventLogSource
0x18002123c  jb      short loc_180021220
0x18002123e  call    cs:__imp_GetProcessHeap
0x180021244  mov     r8, rbx; lpMem
0x180021247  xor     edx, edx; dwFlags
0x180021249  mov     rcx, rax; hHeap
0x18002124c  call    cs:__imp_HeapFree
0x180021252  mov     cs:?sm_pEventLogSource@EVENT_LOG@@0PEAU_EVENT_LOG_SOURCE@@EA, 0; _EVENT_LOG_SOURCE * EVENT_LOG::sm_pEventLogSource
0x18002125d  mov     cs:?sm_cEventLogSource@EVENT_LOG@@0KA, 0; ulong EVENT_LOG::sm_cEventLogSource
0x180021267  mov     rbx, [rsp+28h+arg_0]
0x18002126c  add     rsp, 20h
0x180021270  pop     rdi
0x180021271  retn
```
