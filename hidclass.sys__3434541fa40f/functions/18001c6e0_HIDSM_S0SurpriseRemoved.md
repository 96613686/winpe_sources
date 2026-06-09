# HIDSM_S0SurpriseRemoved

- ea: `0x18001c6e0`
- end: `0x18001c6fb`
- name: `HIDSM_S0SurpriseRemoved`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001c704`

## pseudocode

```c
__int64 __fastcall HIDSM_S0SurpriseRemoved(__int64 a1)
{
  HidpFdoCompletePendingS0IrpIfFastResumeDisabled(*(_QWORD **)(a1 + 960));
  return 2013;
}

```

## disassembly

```asm
0x18001c6e0  sub     rsp, 28h
0x18001c6e4  mov     rcx, [rcx+3C0h]
0x18001c6eb  call    HidpFdoCompletePendingS0IrpIfFastResumeDisabled
0x18001c6f0  mov     eax, 7DDh
0x18001c6f5  add     rsp, 28h
0x18001c6f9  retn
```
