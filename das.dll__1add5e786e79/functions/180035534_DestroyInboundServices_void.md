# DestroyInboundServices(void)

- ea: `0x180035534`
- end: `0x1800355d8`
- name: `?DestroyInboundServices@@YAXXZ`
- size: `164`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180049300`

## callees

- `0x180035534`
- `0x1800355e0`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035553`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035553`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800355ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800355ba`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800355c7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800355c7`

## pseudocode

```c
void DestroyInboundServices(void)
{
  RTL_SRWLOCK *v0; // rbx
  __int64 v1; // rax

  if ( g_bInboundListInitialized )
  {
    EnterCriticalSection(&g_csInboundList);
    while ( 1 )
    {
      v0 = *(RTL_SRWLOCK **)&g_InboundList;
      if ( *(int **)&g_InboundList == &g_InboundList )
        break;
      if ( *(int **)(*(_QWORD *)&g_InboundList + 8LL) != &g_InboundList
        || (v1 = **(_QWORD **)&g_InboundList, *(_QWORD *)(**(_QWORD **)&g_InboundList + 8LL) != *(_QWORD *)&g_InboundList) )
      {
        __fastfail(3u);
      }
      *(_QWORD *)&g_InboundList = **(_QWORD **)&g_InboundList;
      *(_QWORD *)(v1 + 8) = &g_InboundList;
      DAS::ProviderManagement::InboundOps::Deactivate(v0 + 14);
      (*((void (__fastcall **)(RTL_SRWLOCK *))v0[-3].Ptr + 2))(v0 - 3);
    }
    g_bInboundListInitialized = 0;
    LeaveCriticalSection(&g_csInboundList);
    DeleteCriticalSection(&g_csInboundList);
  }
}

```

## disassembly

```asm
0x180035534  mov     [rsp+arg_0], rbx
0x180035539  push    rsi
0x18003553a  sub     rsp, 20h
0x18003553e  mov     eax, cs:?g_bInboundListInitialized@@3HC; int volatile g_bInboundListInitialized
0x180035544  test    eax, eax
0x180035546  jz      loc_1800355CD
0x18003554c  lea     rcx, ?g_csInboundList@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180035553  call    cs:__imp_EnterCriticalSection
0x180035559  lea     rsi, ?g_InboundList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_InboundList
0x180035560  mov     rbx, cs:?g_InboundList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_InboundList
0x180035567  cmp     rbx, rsi
0x18003556a  jz      short loc_1800355A9
0x18003556c  cmp     [rbx+8], rsi
0x180035570  jnz     short loc_1800355A2
0x180035572  mov     rax, [rbx]
0x180035575  cmp     [rax+8], rbx
0x180035579  jnz     short loc_1800355A2
0x18003557b  mov     cs:?g_InboundList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY g_InboundList
0x180035582  lea     rcx, [rbx+70h]; SRWLock
0x180035586  mov     [rax+8], rsi
0x18003558a  call    ?Deactivate@InboundOps@ProviderManagement@DAS@@QEAAJXZ; DAS::ProviderManagement::InboundOps::Deactivate(void)
0x18003558f  mov     rax, [rbx-18h]
0x180035593  lea     rcx, [rbx-18h]
0x180035597  mov     rax, [rax+10h]
0x18003559b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800355a0  jmp     short loc_180035560
0x1800355a2  mov     ecx, 3
0x1800355a7  int     29h; Win8: RtlFailFast(ecx)
0x1800355a9  lea     rcx, ?g_csInboundList@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800355b0  mov     cs:?g_bInboundListInitialized@@3HC, 0; int volatile g_bInboundListInitialized
0x1800355ba  call    cs:__imp_LeaveCriticalSection
0x1800355c0  lea     rcx, ?g_csInboundList@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800355c7  call    cs:__imp_DeleteCriticalSection
0x1800355cd  mov     rbx, [rsp+28h+arg_0]
0x1800355d2  add     rsp, 20h
0x1800355d6  pop     rsi
0x1800355d7  retn
```
