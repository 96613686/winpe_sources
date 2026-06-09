# InitTimerQ

- ea: `0x140044008`
- end: `0x14004405f`
- name: `InitTimerQ`
- size: `87`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x1400533a4`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14004404b`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14004404b`

## pseudocode

```c
__int64 InitTimerQ()
{
  qword_140038448 = (__int64)&TimerQ;
  TimerQ = &TimerQ;
  ExInitializeNPagedLookasideList(&Lookaside, 0, 0, 0x200u, 0x108u, 0x3631624Eu, 0);
  return 0;
}

```

## disassembly

```asm
0x140044008  sub     rsp, 48h
0x14004400c  lea     rax, TimerQ
0x140044013  mov     r9d, 200h; Flags
0x140044019  mov     cs:qword_140038448, rax
0x140044020  lea     rcx, Lookaside; Lookaside
0x140044027  mov     cs:TimerQ, rax
0x14004402e  xor     r8d, r8d; Free
0x140044031  xor     eax, eax
0x140044033  xor     edx, edx; Allocate
0x140044035  mov     [rsp+48h+Depth], ax; Depth
0x14004403a  mov     [rsp+48h+Tag], 3631624Eh; Tag
0x140044042  mov     [rsp+48h+Size], 108h; Size
0x14004404b  call    cs:__imp_ExInitializeNPagedLookasideList
0x140044052  nop     dword ptr [rax+rax+00h]
0x140044057  xor     eax, eax
0x140044059  add     rsp, 48h
0x14004405d  retn
```
