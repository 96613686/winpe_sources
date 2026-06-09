# DirMonOverlappedCompletionRoutine(ulong,ulong,_OVERLAPPED *)

- ea: `0x180017280`
- end: `0x1800172ad`
- name: `?DirMonOverlappedCompletionRoutine@@YAXKKPEAU_OVERLAPPED@@@Z`
- size: `45`
- prototype: `void(unsigned int, unsigned int, struct _OVERLAPPED *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800172b4`

## import_xrefs

- `W3TP!ThreadPoolMapErrorCodeIfNecessary` at `0x18001728f`
- `W3TP!ThreadPoolMapErrorCodeIfNecessary` at `0x18001728f`

## pseudocode

```c
void __fastcall DirMonOverlappedCompletionRoutine(unsigned int a1, unsigned int a2, struct _OVERLAPPED *a3)
{
  unsigned int v5; // eax
  struct _OVERLAPPED *v6; // r9

  v5 = ThreadPoolMapErrorCodeIfNecessary(a1);
  CDirMonitor::DirMonitorCompletionFunction((CDirMonitorEntry *)&a3[-2].InternalHigh, a2, v5, v6);
}

```

## disassembly

```asm
0x180017280  mov     [rsp+arg_0], rbx
0x180017285  push    rdi
0x180017286  sub     rsp, 20h
0x18001728a  mov     rbx, r8
0x18001728d  mov     edi, edx
0x18001728f  call    cs:__imp_?ThreadPoolMapErrorCodeIfNecessary@@YAKK@Z; ThreadPoolMapErrorCodeIfNecessary(ulong)
0x180017295  lea     rcx, [rbx-38h]; this
0x180017299  mov     edx, edi; unsigned int
0x18001729b  mov     r8d, eax; unsigned int
0x18001729e  mov     rbx, [rsp+28h+arg_0]
0x1800172a3  add     rsp, 20h
0x1800172a7  pop     rdi
0x1800172a8  jmp     ?DirMonitorCompletionFunction@CDirMonitor@@SAXPEAXKKPEAU_OVERLAPPED@@@Z; CDirMonitor::DirMonitorCompletionFunction(void *,ulong,ulong,_OVERLAPPED *)
```
