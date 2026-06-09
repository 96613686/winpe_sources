# PpfScheduledTaskMain

- ea: `0x18001b900`
- end: `0x18001b928`
- name: `PpfScheduledTaskMain`
- size: `40`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x180015ff8`
- `0x18001b900`
- `0x180035678`

## string_xrefs

- `0x18001b913`: `Scheduled task`

## pseudocode

```c
__int64 PpfScheduledTaskMain()
{
  int v0; // eax
  unsigned int v1; // ebx

  v0 = PpfScheduledTaskMainInt();
  v1 = v0;
  if ( v0 < 0 )
    PpfhLogEventGenericActivityError(L"Scheduled task", v0);
  return v1;
}

```

## disassembly

```asm
0x18001b900  push    rbx
0x18001b902  sub     rsp, 20h
0x18001b906  call    ?PpfScheduledTaskMainInt@@YAJXZ; PpfScheduledTaskMainInt(void)
0x18001b90b  mov     ebx, eax
0x18001b90d  test    eax, eax
0x18001b90f  jns     short loc_18001B91F
0x18001b911  mov     edx, eax; int
0x18001b913  lea     rcx, aScheduledTask; "Scheduled task"
0x18001b91a  call    ?PpfhLogEventGenericActivityError@@YAJPEBGJ@Z; PpfhLogEventGenericActivityError(ushort const *,long)
0x18001b91f  mov     eax, ebx
0x18001b921  add     rsp, 20h
0x18001b925  pop     rbx
0x18001b926  retn
```
