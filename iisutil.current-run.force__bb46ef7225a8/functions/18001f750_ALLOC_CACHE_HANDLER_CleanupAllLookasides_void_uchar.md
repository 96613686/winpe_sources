# ALLOC_CACHE_HANDLER::CleanupAllLookasides(void *,uchar)

- ea: `0x18001f750`
- end: `0x18001f7fa`
- name: `?CleanupAllLookasides@ALLOC_CACHE_HANDLER@@SAXPEAXE@Z`
- size: `170`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002a1b0`

## callees

- `0x180007300`
- `0x18000ecf0`
- `0x18001f750`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f7f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f766`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f766`

## string_xrefs

- `0x18001f7a4`: `servercommon\inetsrv\iis\iisrearc\core\common\util\acache.cxx`
- `0x18001f7b6`: `Cleaning lookaside list for '%s' handler\n`
- `0x18001f796`: `ALLOC_CACHE_HANDLER::CleanupAllLookasides`

## pseudocode

```c
void __fastcall ALLOC_CACHE_HANDLER::CleanupAllLookasides(PVOID a1)
{
  struct _LIST_ENTRY *i; // rbx

  EnterCriticalSection(&ALLOC_CACHE_HANDLER::sm_csItems);
  for ( i = ALLOC_CACHE_HANDLER::sm_lItemsHead.Flink; i != &ALLOC_CACHE_HANDLER::sm_lItemsHead; i = i->Flink )
  {
    if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 0x1000000) != 0 )
      PuDbgPrint(
        (struct _DEBUG_PRINTS *)g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\acache.cxx",
        0x1ECu,
        "ALLOC_CACHE_HANDLER::CleanupAllLookasides",
        "Cleaning lookaside list for '%s' handler\n",
        (char)i[-1].Blink);
    ALLOC_CACHE_HANDLER::CleanupLookaside((ALLOC_CACHE_HANDLER *)&i[-13], 0);
  }
  LeaveCriticalSection(&ALLOC_CACHE_HANDLER::sm_csItems);
}

```

## disassembly

```asm
0x18001f750  mov     [rsp+arg_0], rbx
0x18001f755  mov     [rsp+arg_8], rsi
0x18001f75a  push    rdi
0x18001f75b  sub     rsp, 30h
0x18001f75f  lea     rcx, ?sm_csItems@ALLOC_CACHE_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001f766  call    cs:__imp_EnterCriticalSection
0x18001f76c  mov     rbx, cs:?sm_lItemsHead@ALLOC_CACHE_HANDLER@@0U_LIST_ENTRY@@A; _LIST_ENTRY ALLOC_CACHE_HANDLER::sm_lItemsHead
0x18001f773  lea     rsi, ?sm_lItemsHead@ALLOC_CACHE_HANDLER@@0U_LIST_ENTRY@@A; _LIST_ENTRY ALLOC_CACHE_HANDLER::sm_lItemsHead
0x18001f77a  jmp     short loc_18001F7D8
0x18001f77c  mov     eax, cs:g_dwDebugFlagsIISUtil
0x18001f782  test    al, 3
0x18001f784  setnz   cl
0x18001f787  bt      eax, 18h
0x18001f78b  setb    al
0x18001f78e  test    al, cl
0x18001f790  jz      short loc_18001F7C7
0x18001f792  mov     rax, [rbx-8]
0x18001f796  lea     r9, aAllocCacheHand; "ALLOC_CACHE_HANDLER::CleanupAllLookasid"...
0x18001f79d  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18001f7a4  lea     rdx, aServercommonIn_11; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18001f7ab  mov     qword ptr [rsp+38h+var_10], rax; char
0x18001f7b0  mov     r8d, 1ECh; unsigned int
0x18001f7b6  lea     rax, aCleaningLookas; "Cleaning lookaside list for '%s' handle"...
0x18001f7bd  mov     [rsp+38h+var_18], rax; char *
0x18001f7c2  call    PuDbgPrint
0x18001f7c7  xor     edx, edx; int
0x18001f7c9  lea     rcx, [rbx-0D0h]; this
0x18001f7d0  call    ?CleanupLookaside@ALLOC_CACHE_HANDLER@@QEAAXH@Z; ALLOC_CACHE_HANDLER::CleanupLookaside(int)
0x18001f7d5  mov     rbx, [rbx]
0x18001f7d8  cmp     rbx, rsi
0x18001f7db  jnz     short loc_18001F77C
0x18001f7dd  lea     rcx, ?sm_csItems@ALLOC_CACHE_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION ALLOC_CACHE_HANDLER::sm_csItems
0x18001f7e4  mov     rbx, [rsp+38h+arg_0]
0x18001f7e9  mov     rsi, [rsp+38h+arg_8]
0x18001f7ee  add     rsp, 30h
0x18001f7f2  pop     rdi
0x18001f7f3  jmp     cs:__imp_LeaveCriticalSection
```
