# fc::config_target<uf_props>::ensure_store_initialized(void)

- ea: `0x180043210`
- end: `0x180043268`
- name: `?ensure_store_initialized@?$config_target@Uuf_props@@@fc@@MEAA_NXZ`
- size: `88`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180043210`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043227`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043227`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18004324f`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18004324f`

## pseudocode

```c
char __fastcall fc::config_target<uf_props>::ensure_store_initialized(PVOID Parameter)
{
  if ( !_InterlockedCompareExchange((volatile signed __int32 *)Parameter + 43, 0, 0) )
  {
    if ( *((_DWORD *)Parameter + 44) == GetCurrentThreadId() )
      return 0;
    InitOnceExecuteOnce(
      (PINIT_ONCE)Parameter + 23,
      (PINIT_ONCE_FN)fc::config_target<uf_props>::init_once_static,
      Parameter,
      0);
    _InterlockedExchange((volatile __int32 *)Parameter + 43, 1);
  }
  return 1;
}

```

## disassembly

```asm
0x180043210  push    rbx
0x180043212  sub     rsp, 20h
0x180043216  mov     rbx, rcx
0x180043219  xor     ecx, ecx
0x18004321b  xor     eax, eax
0x18004321d  lock cmpxchg [rbx+0ACh], ecx
0x180043225  jnz     short loc_180043260
0x180043227  call    cs:__imp_GetCurrentThreadId
0x18004322d  mov     edx, [rbx+0B0h]
0x180043233  cmp     edx, eax
0x180043235  jnz     short loc_18004323B
0x180043237  xor     al, al
0x180043239  jmp     short loc_180043262
0x18004323b  lea     rcx, [rbx+0B8h]; InitOnce
0x180043242  xor     r9d, r9d; Context
0x180043245  mov     r8, rbx; Parameter
0x180043248  lea     rdx, ?init_once_static@?$config_target@Uuf_props@@@fc@@KAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18004324f  call    cs:__imp_InitOnceExecuteOnce
0x180043255  mov     ecx, 1
0x18004325a  xchg    ecx, [rbx+0ACh]
0x180043260  mov     al, 1
0x180043262  add     rsp, 20h
0x180043266  pop     rbx
0x180043267  retn
```
