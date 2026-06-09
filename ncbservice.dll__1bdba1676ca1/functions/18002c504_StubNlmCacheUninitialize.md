# StubNlmCacheUninitialize

- ea: `0x18002c504`
- end: `0x18002c5ea`
- name: `StubNlmCacheUninitialize`
- size: `230`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18001ae2c`
- `0x18001fce0`
- `0x18002d00c`

## callees

- `0x18001c500`
- `0x18002c0d8`
- `0x18002c504`
- `0x18002c8d8`
- `0x18002c924`
- `0x180033010`

## import_xrefs

- `ntdll!RtlDeleteHashTable` at `0x18002c59b`
- `ntdll!RtlDeleteHashTable` at `0x18002c59b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002c591`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002c591`

## pseudocode

```c
__int64 __fastcall StubNlmCacheUninitialize(LPCRITICAL_SECTION lpCriticalSection)
{
  __int64 result; // rax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids);
  }
  if ( *(_QWORD *)&lpCriticalSection[3].LockCount )
  {
    StopWorkQueue(&lpCriticalSection[3].OwningThread);
    UninitializeWorkQueue(&lpCriticalSection[3].OwningThread);
    (*(void (__fastcall **)(_QWORD))&lpCriticalSection[1].LockCount)(*(_QWORD *)&lpCriticalSection[3].LockCount);
    *(_QWORD *)&lpCriticalSection[3].LockCount = 0;
  }
  StubNlmCacheCleanupActiveStore(lpCriticalSection);
  DeleteCriticalSection(lpCriticalSection);
  RtlDeleteHashTable(&lpCriticalSection[2].LockCount);
  result = (*(__int64 (__fastcall **)(LPCRITICAL_SECTION))&lpCriticalSection[1].LockCount)(lpCriticalSection);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    return WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x18002c504  mov     [rsp+arg_0], rbx
0x18002c509  mov     [rsp+arg_8], rsi
0x18002c50e  push    rdi
0x18002c50f  sub     rsp, 20h
0x18002c513  mov     rdi, rcx
0x18002c516  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c51d  lea     rsi, WPP_GLOBAL_Control
0x18002c524  cmp     rcx, rsi
0x18002c527  jz      short loc_18002C54A
0x18002c529  test    byte ptr [rcx+1Ch], 4
0x18002c52d  jz      short loc_18002C54A
0x18002c52f  cmp     byte ptr [rcx+19h], 6
0x18002c533  jb      short loc_18002C54A
0x18002c535  mov     rcx, [rcx+10h]
0x18002c539  lea     r8, WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids
0x18002c540  mov     edx, 32h ; '2'
0x18002c545  call    WPP_SF_
0x18002c54a  cmp     qword ptr [rdi+80h], 0
0x18002c552  jz      short loc_18002C586
0x18002c554  lea     rbx, [rdi+88h]
0x18002c55b  mov     rcx, rbx
0x18002c55e  call    StopWorkQueue
0x18002c563  mov     rcx, rbx
0x18002c566  call    UninitializeWorkQueue
0x18002c56b  mov     rcx, [rdi+80h]
0x18002c572  mov     rax, [rdi+30h]
0x18002c576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c57b  mov     qword ptr [rdi+80h], 0
0x18002c586  mov     rcx, rdi
0x18002c589  call    StubNlmCacheCleanupActiveStore
0x18002c58e  mov     rcx, rdi; lpCriticalSection
0x18002c591  call    cs:__imp_DeleteCriticalSection
0x18002c597  lea     rcx, [rdi+58h]
0x18002c59b  call    cs:__imp_RtlDeleteHashTable
0x18002c5a1  mov     rax, [rdi+30h]
0x18002c5a5  mov     rcx, rdi
0x18002c5a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c5ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c5b4  cmp     rcx, rsi
0x18002c5b7  jz      short loc_18002C5DA
0x18002c5b9  test    byte ptr [rcx+1Ch], 4
0x18002c5bd  jz      short loc_18002C5DA
0x18002c5bf  cmp     byte ptr [rcx+19h], 6
0x18002c5c3  jb      short loc_18002C5DA
0x18002c5c5  mov     rcx, [rcx+10h]
0x18002c5c9  lea     r8, WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids
0x18002c5d0  mov     edx, 33h ; '3'
0x18002c5d5  call    WPP_SF_
0x18002c5da  mov     rbx, [rsp+28h+arg_0]
0x18002c5df  mov     rsi, [rsp+28h+arg_8]
0x18002c5e4  add     rsp, 20h
0x18002c5e8  pop     rdi
0x18002c5e9  retn
```
