# HacOrphanStaleEntry

- ea: `0x1400145f0`
- end: `0x140014647`
- name: `HacOrphanStaleEntry`
- size: `87`
- prototype: `LONG __fastcall(__int64, __int64)`
- caller_count: `18`
- callee_count: `4`
- tags: ``

## callers

- `0x1400029d0`
- `0x140003bd0`
- `0x140004530`
- `0x14000c8d8`
- `0x14000cf04`
- `0x14000da84`
- `0x14000e4ec`
- `0x14000e940`
- `0x14000f274`
- `0x14000fbc0`
- `0x140011298`
- `0x1400132cc`
- `0x14001c694`
- `0x14002a9e0`
- `0x14002b138`
- `0x140030b60`
- `0x140030ef0`
- `0x1400316d0`

## callees

- `0x140008140`
- `0x1400145f0`
- `0x140014650`
- `0x140020154`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x14001462f`
- `ntoskrnl!KeReleaseMutex` at `0x14001462f`

## pseudocode

```c
LONG __fastcall HacOrphanStaleEntry(__int64 a1, __int64 a2)
{
  HacAcquireLock(a2);
  HacOrphanEntry(a2);
  *(_WORD *)(a2 + 48) |= 2u;
  if ( *(_DWORD *)(a2 + 128) == 2 )
    HacPurgePostfix(a1, a2);
  return KeReleaseMutex(*(PRKMUTEX *)(a2 + 40), 0);
}

```

## disassembly

```asm
0x1400145f0  mov     [rsp+arg_0], rbx
0x1400145f5  push    rdi
0x1400145f6  sub     rsp, 20h
0x1400145fa  mov     rdi, rcx
0x1400145fd  mov     rbx, rdx
0x140014600  mov     rcx, rdx
0x140014603  call    HacAcquireLock
0x140014608  mov     rcx, rbx
0x14001460b  call    HacOrphanEntry
0x140014610  or      word ptr [rbx+30h], 2
0x140014615  cmp     dword ptr [rbx+80h], 2
0x14001461c  jnz     short loc_140014629
0x14001461e  mov     rdx, rbx
0x140014621  mov     rcx, rdi
0x140014624  call    HacPurgePostfix
0x140014629  mov     rcx, [rbx+28h]; Mutex
0x14001462d  xor     edx, edx; Wait
0x14001462f  call    cs:__imp_KeReleaseMutex
0x140014636  nop     dword ptr [rax+rax+00h]
0x14001463b  mov     rbx, [rsp+28h+arg_0]
0x140014640  add     rsp, 20h
0x140014644  pop     rdi
0x140014645  retn
```
