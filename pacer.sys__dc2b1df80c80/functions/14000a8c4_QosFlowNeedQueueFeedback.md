# QosFlowNeedQueueFeedback

- ea: `0x14000a8c4`
- end: `0x14000a90a`
- name: `QosFlowNeedQueueFeedback`
- size: `70`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140005c10`
- `0x140007f90`
- `0x1400085c0`
- `0x14000cce0`

## callees

- `0x14000a8c4`
- `0x14001233c`

## pseudocode

```c
char __fastcall QosFlowNeedQueueFeedback(__int64 a1, __int64 a2, _QWORD *a3)
{
  *a3 = 0;
  a3[1] = 0;
  a3[2] = 0;
  a3[4] = 0;
  a3[3] = 0x7FFFFFFFFFFFFFFFLL;
  *(_DWORD *)a3 = *(_DWORD *)(a1 + 320);
  if ( *(_DWORD *)(a1 + 320) )
    return QosTbcAdjustBytesSent(a1, a2);
  else
    return 0;
}

```

## disassembly

```asm
0x14000a8c4  sub     rsp, 28h
0x14000a8c8  xor     r9d, r9d
0x14000a8cb  mov     rax, 7FFFFFFFFFFFFFFFh
0x14000a8d5  mov     [r8], r9
0x14000a8d8  mov     [r8+8], r9
0x14000a8dc  mov     [r8+10h], r9
0x14000a8e0  mov     [r8+20h], r9
0x14000a8e4  mov     [r8+18h], rax
0x14000a8e8  mov     eax, [rcx+140h]
0x14000a8ee  mov     [r8], eax
0x14000a8f1  cmp     [rcx+140h], r9d
0x14000a8f8  jnz     short loc_14000A903
0x14000a8fa  mov     al, r9b
0x14000a8fd  add     rsp, 28h
0x14000a901  retn
0x14000a903  call    QosTbcAdjustBytesSent
0x14000a908  jmp     short loc_14000A8FD
```
