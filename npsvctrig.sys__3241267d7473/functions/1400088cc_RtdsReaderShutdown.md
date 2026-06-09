# RtdsReaderShutdown

- ea: `0x1400088cc`
- end: `0x140008918`
- name: `RtdsReaderShutdown`
- size: `76`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140008250`
- `0x14000b080`

## callees

- `0x1400088cc`
- `0x140008920`
- `0x140009890`

## pseudocode

```c
__int64 RtdsReaderShutdown()
{
  __int64 i; // rdi

  for ( i = 0; i != 2; ++i )
  {
    RtdsUnregisterUpdateCallback(RtdsProviderWnfState[7 * i + 1]);
    RtdspFreeEndpointList((_QWORD *)RtdsProviderWnfState[7 * i + 5]);
  }
  return 0;
}

```

## disassembly

```asm
0x1400088cc  mov     [rsp+arg_0], rbx
0x1400088d1  mov     [rsp+arg_8], rsi
0x1400088d6  push    rdi
0x1400088d7  sub     rsp, 20h
0x1400088db  xor     edi, edi
0x1400088dd  lea     rsi, RtdsProviderWnfState
0x1400088e4  imul    rbx, rdi, 38h ; '8'
0x1400088e8  mov     rcx, [rbx+rsi+8]
0x1400088ed  call    RtdsUnregisterUpdateCallback
0x1400088f2  mov     rcx, [rbx+rsi+28h]
0x1400088f7  call    RtdspFreeEndpointList
0x1400088fc  inc     rdi
0x1400088ff  cmp     rdi, 2
0x140008903  jnz     short loc_1400088E4
0x140008905  mov     rbx, [rsp+28h+arg_0]
0x14000890a  xor     eax, eax
0x14000890c  mov     rsi, [rsp+28h+arg_8]
0x140008911  add     rsp, 20h
0x140008915  pop     rdi
0x140008916  retn
```
