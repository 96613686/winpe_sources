# ReleaseReadLock

- ea: `0x180028d84`
- end: `0x180028db2`
- name: `ReleaseReadLock`
- size: `46`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180027f2c`
- `0x180028078`
- `0x180028398`
- `0x1800284fc`
- `0x180028b5c`
- `0x180028c70`

## callees

- `0x180028d84`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028dab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028d8d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028d8d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180028d9d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180028d9d`

## pseudocode

```c
void __fastcall ReleaseReadLock(struct _RTL_CRITICAL_SECTION *a1)
{
  EnterCriticalSection(a1);
  if ( a1[1].LockCount-- == 1 )
    SetEvent(a1[1].DebugInfo);
  LeaveCriticalSection(a1);
}

```

## disassembly

```asm
0x180028d84  push    rbx
0x180028d86  sub     rsp, 20h
0x180028d8a  mov     rbx, rcx
0x180028d8d  call    cs:__imp_EnterCriticalSection
0x180028d93  add     dword ptr [rbx+30h], 0FFFFFFFFh
0x180028d97  jnz     short loc_180028DA3
0x180028d99  mov     rcx, [rbx+28h]; hEvent
0x180028d9d  call    cs:__imp_SetEvent
0x180028da3  mov     rcx, rbx
0x180028da6  add     rsp, 20h
0x180028daa  pop     rbx
0x180028dab  jmp     cs:__imp_LeaveCriticalSection
```
