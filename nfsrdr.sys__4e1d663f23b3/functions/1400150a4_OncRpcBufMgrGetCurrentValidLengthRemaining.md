# OncRpcBufMgrGetCurrentValidLengthRemaining

- ea: `0x1400150a4`
- end: `0x1400150c0`
- name: `OncRpcBufMgrGetCurrentValidLengthRemaining`
- size: `28`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `16`
- callee_count: `2`
- tags: ``

## callers

- `0x14000cdb8`
- `0x14000d4cc`
- `0x14000d99c`
- `0x14000d9f0`
- `0x140011f84`
- `0x140011fd4`
- `0x140014c64`
- `0x140014e1c`
- `0x140014ff4`
- `0x140020fa8`
- `0x140022414`
- `0x14002372c`
- `0x14002b7dc`
- `0x140038850`
- `0x14003896c`
- `0x140038a68`

## callees

- `0x1400150a4`
- `0x14001f834`

## pseudocode

```c
__int64 __fastcall OncRpcBufMgrGetCurrentValidLengthRemaining(__int64 a1)
{
  if ( *(_QWORD *)(a1 + 40) )
    return OncRpcBufMgrGetDescriptorValidLengthRemaining();
  else
    return 0;
}

```

## disassembly

```asm
0x1400150a4  sub     rsp, 28h
0x1400150a8  mov     rcx, [rcx+28h]
0x1400150ac  test    rcx, rcx
0x1400150af  jnz     short loc_1400150B5
0x1400150b1  xor     eax, eax
0x1400150b3  jmp     short loc_1400150BA
0x1400150b5  call    OncRpcBufMgrGetDescriptorValidLengthRemaining
0x1400150ba  add     rsp, 28h
0x1400150be  retn
```
