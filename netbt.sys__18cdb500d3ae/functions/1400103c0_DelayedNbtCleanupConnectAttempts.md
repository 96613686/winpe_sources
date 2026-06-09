# DelayedNbtCleanupConnectAttempts

- ea: `0x1400103c0`
- end: `0x1400103e2`
- name: `DelayedNbtCleanupConnectAttempts`
- size: `34`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140011640`

## callees

- `0x1400103e8`
- `0x1400104d8`

## pseudocode

```c
__int64 __fastcall DelayedNbtCleanupConnectAttempts(__int64 a1, void *a2)
{
  NbtQueryWfpAndCleanupConnection(a2);
  DoneDelayedNbtProcessConnect(a2);
  return 0;
}

```

## disassembly

```asm
0x1400103c0  push    rbx
0x1400103c2  sub     rsp, 20h
0x1400103c6  mov     rcx, rdx
0x1400103c9  mov     rbx, rdx
0x1400103cc  call    NbtQueryWfpAndCleanupConnection
0x1400103d1  mov     rcx, rbx; P
0x1400103d4  call    DoneDelayedNbtProcessConnect
0x1400103d9  xor     eax, eax
0x1400103db  add     rsp, 20h
0x1400103df  pop     rbx
0x1400103e0  retn
```
