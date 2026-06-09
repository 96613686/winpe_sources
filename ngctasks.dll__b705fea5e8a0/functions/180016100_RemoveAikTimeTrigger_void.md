# RemoveAikTimeTrigger(void)

- ea: `0x180016100`
- end: `0x18001613b`
- name: `?RemoveAikTimeTrigger@@YAJXZ`
- size: `59`
- prototype: `int(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001417c`

## callees

- `0x18000cc34`
- `0x180016100`
- `0x180016570`

## string_xrefs

- `0x18001611b`: `onecore\ds\security\ngc\ngctask\dll\reschedule.cpp`

## pseudocode

```c
__int64 RemoveAikTimeTrigger(void)
{
  int v0; // eax
  unsigned int v1; // ebx
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v0 = reschedRemoveTrigger(1u);
  v1 = v0;
  if ( v0 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x20E,
    (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\reschedule.cpp",
    (const char *)(unsigned int)v0,
    v3);
  return v1;
}

```

## disassembly

```asm
0x180016100  push    rbx; int
0x180016102  sub     rsp, 20h
0x180016106  mov     ecx, 1; enum _TASK_TRIGGER_TYPE2
0x18001610b  call    ?reschedRemoveTrigger@@YAJW4_TASK_TRIGGER_TYPE2@@@Z; reschedRemoveTrigger(_TASK_TRIGGER_TYPE2)
0x180016110  mov     ebx, eax
0x180016112  test    eax, eax
0x180016114  jns     short loc_180016133
0x180016116  mov     rcx, [rsp+28h]; this
0x18001611b  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180016122  mov     r9d, eax; char *
0x180016125  mov     edx, 20Eh; void *
0x18001612a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001612f  mov     eax, ebx
0x180016131  jmp     short loc_180016135
0x180016133  xor     eax, eax
0x180016135  add     rsp, 20h
0x180016139  pop     rbx
0x18001613a  retn
```
