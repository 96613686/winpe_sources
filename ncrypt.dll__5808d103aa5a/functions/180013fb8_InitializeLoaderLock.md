# _InitializeLoaderLock

- ea: `0x180013fb8`
- end: `0x180013ff5`
- name: `_InitializeLoaderLock`
- size: `61`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180013f38`

## callees

- `0x18000e120`
- `0x180013fb8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180013fc7`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180013fc7`

## string_xrefs

- `0x180013fd7`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`

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
0x180013fb8  push    rbx
0x180013fba  sub     rsp, 20h
0x180013fbe  xor     ebx, ebx
0x180013fc0  lea     rcx, g_csLoaderLock; lpCriticalSection
0x180013fc7  call    cs:__imp_InitializeCriticalSection
0x180013fcd  jmp     short loc_180013FED
0x180013fcf  mov     ebx, eax
0x180013fd1  mov     r9d, 0D0h
0x180013fd7  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180013fde  lea     rdx, aSresult; "sResult"
0x180013fe5  mov     ecx, eax
0x180013fe7  call    DebugTraceError
0x180013fec  nop
0x180013fed  mov     eax, ebx
0x180013fef  add     rsp, 20h
0x180013ff3  pop     rbx
0x180013ff4  retn
```
