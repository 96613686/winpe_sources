# CdSingleSyncCompletionRoutine

- ea: `0x140001ca0`
- end: `0x140001cd2`
- name: `CdSingleSyncCompletionRoutine`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140001ca0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140001cbb`
- `ntoskrnl!KeSetEvent` at `0x140001cbb`

## pseudocode

```c
__int64 __fastcall CdSingleSyncCompletionRoutine(__int64 a1, __int64 a2, struct _KEVENT *a3)
{
  if ( *(int *)(a2 + 48) < 0 )
    *(_QWORD *)(a2 + 56) = 0;
  KeSetEvent(a3 + 1, 0, 0);
  return 3221225494LL;
}

```

## disassembly

```asm
0x140001ca0  sub     rsp, 28h
0x140001ca4  cmp     dword ptr [rdx+30h], 0
0x140001ca8  jge     short loc_140001CB2
0x140001caa  mov     qword ptr [rdx+38h], 0
0x140001cb2  lea     rcx, [r8+18h]; Event
0x140001cb6  xor     edx, edx; Increment
0x140001cb8  xor     r8d, r8d; Wait
0x140001cbb  call    cs:__imp_KeSetEvent
0x140001cc2  nop     dword ptr [rax+rax+00h]
0x140001cc7  mov     eax, 0C0000016h
0x140001ccc  add     rsp, 28h
0x140001cd0  retn
```
