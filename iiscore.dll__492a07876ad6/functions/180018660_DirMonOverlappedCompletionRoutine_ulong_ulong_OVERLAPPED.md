# DirMonOverlappedCompletionRoutine(ulong,ulong,_OVERLAPPED *)

- ea: `0x180018660`
- end: `0x180018693`
- name: `?DirMonOverlappedCompletionRoutine@@YAXKKPEAU_OVERLAPPED@@@Z`
- size: `51`
- prototype: `void(unsigned int, unsigned int, struct _OVERLAPPED *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001869c`

## import_xrefs

- `W3TP!ThreadPoolMapErrorCodeIfNecessary` at `0x18001866f`
- `W3TP!ThreadPoolMapErrorCodeIfNecessary` at `0x18001866f`

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
0x180018660  mov     [rsp+arg_0], rbx
0x180018665  push    rdi
0x180018666  sub     rsp, 20h
0x18001866a  mov     rbx, r8
0x18001866d  mov     edi, edx
0x18001866f  call    cs:__imp_?ThreadPoolMapErrorCodeIfNecessary@@YAKK@Z; ThreadPoolMapErrorCodeIfNecessary(ulong)
0x180018676  nop     dword ptr [rax+rax+00h]
0x18001867b  lea     rcx, [rbx-38h]; this
0x18001867f  mov     edx, edi; unsigned int
0x180018681  mov     r8d, eax; unsigned int
0x180018684  mov     rbx, [rsp+28h+arg_0]
0x180018689  add     rsp, 20h
0x18001868d  pop     rdi
0x18001868e  jmp     ?DirMonitorCompletionFunction@CDirMonitor@@SAXPEAXKKPEAU_OVERLAPPED@@@Z; CDirMonitor::DirMonitorCompletionFunction(void *,ulong,ulong,_OVERLAPPED *)
```
