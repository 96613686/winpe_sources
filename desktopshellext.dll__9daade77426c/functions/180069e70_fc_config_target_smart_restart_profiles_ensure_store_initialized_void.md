# fc::config_target<smart_restart_profiles>::ensure_store_initialized(void)

- ea: `0x180069e70`
- end: `0x180069ebc`
- name: `?ensure_store_initialized@?$config_target@Usmart_restart_profiles@@@fc@@MEAA_NXZ`
- size: `76`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180069e70`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180069e84`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180069e84`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180069ea6`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180069ea6`

## pseudocode

```c
char __fastcall fc::config_target<smart_restart_profiles>::ensure_store_initialized(PVOID Parameter)
{
  if ( !_InterlockedCompareExchange((volatile signed __int32 *)Parameter + 27, 0, 0) )
  {
    if ( *((_DWORD *)Parameter + 28) == GetCurrentThreadId() )
      return 0;
    InitOnceExecuteOnce(
      (PINIT_ONCE)Parameter + 15,
      (PINIT_ONCE_FN)fc::config_target<smart_restart_profiles>::init_once_static,
      Parameter,
      0);
    _InterlockedExchange((volatile __int32 *)Parameter + 27, 1);
  }
  return 1;
}

```

## disassembly

```asm
0x180069e70  push    rbx
0x180069e72  sub     rsp, 20h
0x180069e76  mov     rbx, rcx
0x180069e79  xor     ecx, ecx
0x180069e7b  xor     eax, eax
0x180069e7d  lock cmpxchg [rbx+6Ch], ecx
0x180069e82  jnz     short loc_180069EB4
0x180069e84  call    cs:__imp_GetCurrentThreadId
0x180069e8a  mov     edx, [rbx+70h]
0x180069e8d  cmp     edx, eax
0x180069e8f  jnz     short loc_180069E95
0x180069e91  xor     al, al
0x180069e93  jmp     short loc_180069EB6
0x180069e95  lea     rcx, [rbx+78h]; InitOnce
0x180069e99  xor     r9d, r9d; Context
0x180069e9c  mov     r8, rbx; Parameter
0x180069e9f  lea     rdx, ?init_once_static@?$config_target@Usmart_restart_profiles@@@fc@@KAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180069ea6  call    cs:__imp_InitOnceExecuteOnce
0x180069eac  mov     ecx, 1
0x180069eb1  xchg    ecx, [rbx+6Ch]
0x180069eb4  mov     al, 1
0x180069eb6  add     rsp, 20h
0x180069eba  pop     rbx
0x180069ebb  retn
```
