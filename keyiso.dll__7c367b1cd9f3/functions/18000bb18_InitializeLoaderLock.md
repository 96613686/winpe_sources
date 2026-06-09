# _InitializeLoaderLock

- ea: `0x18000bb18`
- end: `0x18000bb55`
- name: `_InitializeLoaderLock`
- size: `61`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009c20`

## callees

- `0x180003cf0`
- `0x18000bb18`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000bb27`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000bb27`

## string_xrefs

- `0x18000bb37`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`

## pseudocode

```c
__int64 InitializeLoaderLock()
{
  InitializeCriticalSection(&g_csLoaderLock);
  return 0;
}

```

## disassembly

```asm
0x18000bb18  push    rbx
0x18000bb1a  sub     rsp, 20h
0x18000bb1e  xor     ebx, ebx
0x18000bb20  lea     rcx, g_csLoaderLock; lpCriticalSection
0x18000bb27  call    cs:__imp_InitializeCriticalSection
0x18000bb2d  jmp     short loc_18000BB4D
0x18000bb2f  mov     ebx, eax
0x18000bb31  mov     r9d, 0D0h
0x18000bb37  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000bb3e  lea     rdx, aSresult; "sResult"
0x18000bb45  mov     ecx, eax
0x18000bb47  call    DebugTraceError
0x18000bb4c  nop
0x18000bb4d  mov     eax, ebx
0x18000bb4f  add     rsp, 20h
0x18000bb53  pop     rbx
0x18000bb54  retn
```
