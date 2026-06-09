# WDigestCompleteToken

- ea: `0x140021500`
- end: `0x140021517`
- name: `WDigestCompleteToken`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140028e50`

## pseudocode

```c
__int64 __fastcall WDigestCompleteToken(unsigned __int64 a1)
{
  return WDigestVerifySignature(a1);
}

```

## disassembly

```asm
0x140021500  sub     rsp, 28h
0x140021504  lea     r9, [rsp+28h+arg_10]
0x140021509  xor     r8d, r8d
0x14002150c  call    WDigestVerifySignature
0x140021511  add     rsp, 28h
0x140021515  retn
```
