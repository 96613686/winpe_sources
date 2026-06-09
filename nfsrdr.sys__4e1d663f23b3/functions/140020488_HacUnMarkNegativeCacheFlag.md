# HacUnMarkNegativeCacheFlag

- ea: `0x140020488`
- end: `0x1400204b8`
- name: `HacUnMarkNegativeCacheFlag`
- size: `48`
- prototype: `LONG __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140004530`
- `0x140020af4`

## callees

- `0x140008140`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1400204a5`
- `ntoskrnl!KeReleaseMutex` at `0x1400204a5`

## pseudocode

```c
LONG __fastcall HacUnMarkNegativeCacheFlag(__int64 a1)
{
  struct _KMUTANT *v2; // rcx

  HacAcquireLock(a1);
  v2 = *(struct _KMUTANT **)(a1 + 40);
  *(_WORD *)(a1 + 48) &= ~8u;
  return KeReleaseMutex(v2, 0);
}

```

## disassembly

```asm
0x140020488  push    rbx
0x14002048a  sub     rsp, 20h
0x14002048e  mov     rbx, rcx
0x140020491  call    HacAcquireLock
0x140020496  mov     rcx, [rbx+28h]; Mutex
0x14002049a  mov     eax, 0FFF7h
0x14002049f  and     [rbx+30h], ax
0x1400204a3  xor     edx, edx; Wait
0x1400204a5  call    cs:__imp_KeReleaseMutex
0x1400204ac  nop     dword ptr [rax+rax+00h]
0x1400204b1  add     rsp, 20h
0x1400204b5  pop     rbx
0x1400204b6  retn
```
