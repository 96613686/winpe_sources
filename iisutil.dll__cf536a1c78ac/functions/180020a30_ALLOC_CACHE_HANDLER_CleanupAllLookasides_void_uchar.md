# ALLOC_CACHE_HANDLER::CleanupAllLookasides(void *,uchar)

- ea: `0x180020a30`
- end: `0x180020ae5`
- name: `?CleanupAllLookasides@ALLOC_CACHE_HANDLER@@SAXPEAXE@Z`
- size: `181`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002c060`

## callees

- `0x180008000`
- `0x18000ff70`
- `0x180020a30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020ad9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020a46`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020a46`

## string_xrefs

- `0x180020a8a`: `servercommon\inetsrv\iis\iisrearc\core\common\util\acache.cxx`
- `0x180020a9c`: `Cleaning lookaside list for '%s' handler\n`
- `0x180020a7c`: `ALLOC_CACHE_HANDLER::CleanupAllLookasides`

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
0x180020a30  mov     [rsp+arg_0], rbx
0x180020a35  mov     [rsp+arg_8], rsi
0x180020a3a  push    rdi
0x180020a3b  sub     rsp, 30h
0x180020a3f  lea     rcx, ?sm_csItems@ALLOC_CACHE_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180020a46  call    cs:__imp_EnterCriticalSection
0x180020a4d  nop     dword ptr [rax+rax+00h]
0x180020a52  mov     rbx, cs:?sm_lItemsHead@ALLOC_CACHE_HANDLER@@0U_LIST_ENTRY@@A; _LIST_ENTRY ALLOC_CACHE_HANDLER::sm_lItemsHead
0x180020a59  lea     rsi, ?sm_lItemsHead@ALLOC_CACHE_HANDLER@@0U_LIST_ENTRY@@A; _LIST_ENTRY ALLOC_CACHE_HANDLER::sm_lItemsHead
0x180020a60  jmp     short loc_180020ABE
0x180020a62  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180020a68  test    al, 3
0x180020a6a  setnz   cl
0x180020a6d  bt      eax, 18h
0x180020a71  setb    al
0x180020a74  test    al, cl
0x180020a76  jz      short loc_180020AAD
0x180020a78  mov     rax, [rbx-8]
0x180020a7c  lea     r9, aAllocCacheHand; "ALLOC_CACHE_HANDLER::CleanupAllLookasid"...
0x180020a83  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180020a8a  lea     rdx, aServercommonIn_11; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180020a91  mov     qword ptr [rsp+38h+var_10], rax; char
0x180020a96  mov     r8d, 1ECh; unsigned int
0x180020a9c  lea     rax, aCleaningLookas; "Cleaning lookaside list for '%s' handle"...
0x180020aa3  mov     [rsp+38h+var_18], rax; char *
0x180020aa8  call    PuDbgPrint
0x180020aad  xor     edx, edx; int
0x180020aaf  lea     rcx, [rbx-0D0h]; this
0x180020ab6  call    ?CleanupLookaside@ALLOC_CACHE_HANDLER@@QEAAXH@Z; ALLOC_CACHE_HANDLER::CleanupLookaside(int)
0x180020abb  mov     rbx, [rbx]
0x180020abe  cmp     rbx, rsi
0x180020ac1  jnz     short loc_180020A62
0x180020ac3  lea     rcx, ?sm_csItems@ALLOC_CACHE_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION ALLOC_CACHE_HANDLER::sm_csItems
0x180020aca  mov     rbx, [rsp+38h+arg_0]
0x180020acf  mov     rsi, [rsp+38h+arg_8]
0x180020ad4  add     rsp, 30h
0x180020ad8  pop     rdi
0x180020ad9  jmp     cs:__imp_LeaveCriticalSection
```
