# QosFlowProcessQueuedNetBufferLists

- ea: `0x140011904`
- end: `0x140011962`
- name: `QosFlowProcessQueuedNetBufferLists`
- size: `94`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140005c10`
- `0x140007f90`
- `0x1400085c0`
- `0x14000cce0`

## callees

- `0x140004fe0`
- `0x14000bdf4`
- `0x140011904`

## pseudocode

```c
char __fastcall QosFlowProcessQueuedNetBufferLists(__int64 a1, ULONG a2, int a3, __int64 a4, __int64 a5)
{
  char v7; // bl

  v7 = QosTbcProcessQueuedNetBufferLists(a1, a2, a3, 0, a4, a5, 0);
  if ( !v7 )
    *(_QWORD *)(a1 + 264) = QosTimerGetCurrentTime(a2, 0, 1);
  return v7;
}

```

## disassembly

```asm
0x140011904  mov     r11, rsp
0x140011907  mov     [r11+8], rbx
0x14001190b  mov     [r11+10h], rsi
0x14001190f  push    rdi
0x140011910  sub     rsp, 40h
0x140011914  mov     rax, [rsp+48h+arg_20]
0x140011919  mov     edi, edx
0x14001191b  mov     qword ptr [r11-18h], 0
0x140011923  mov     rsi, rcx
0x140011926  mov     [r11-20h], rax
0x14001192a  mov     [r11-28h], r9
0x14001192e  xor     r9d, r9d
0x140011931  call    QosTbcProcessQueuedNetBufferLists
0x140011936  mov     bl, al
0x140011938  test    al, al
0x14001193a  jnz     short loc_14001194F
0x14001193c  mov     r8b, 1
0x14001193f  xor     edx, edx
0x140011941  mov     ecx, edi
0x140011943  call    QosTimerGetCurrentTime
0x140011948  mov     [rsi+108h], rax
0x14001194f  mov     rsi, [rsp+48h+arg_8]
0x140011954  mov     al, bl
0x140011956  mov     rbx, [rsp+48h+arg_0]
0x14001195b  add     rsp, 40h
0x14001195f  pop     rdi
0x140011960  retn
```
