# FDCopyMemory(void *,void *,unsigned __int64)

- ea: `0x140006e58`
- end: `0x140006e6d`
- name: `?FDCopyMemory@@YA_NPEAX0_K@Z`
- size: `21`
- prototype: `bool __fastcall(void *, void *, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140007104`

## callees

- `0x140006e58`
- `0x140076eea`

## pseudocode

```c
char __fastcall FDCopyMemory(void *a1, void *a2, size_t a3)
{
  memcpy_0(a1, a2, a3);
  return 1;
}

```

## disassembly

```asm
0x140006e58  sub     rsp, 28h
0x140006e5c  call    memcpy_0
0x140006e61  nop
0x140006e62  mov     al, 1
0x140006e64  jmp     short loc_140006E68
0x140006e66  xor     al, al
0x140006e68  add     rsp, 28h
0x140006e6c  retn
```
