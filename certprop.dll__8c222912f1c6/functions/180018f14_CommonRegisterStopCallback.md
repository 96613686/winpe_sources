# CommonRegisterStopCallback

- ea: `0x180018f14`
- end: `0x180018f41`
- name: `CommonRegisterStopCallback`
- size: `45`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180017d90`
- `0x18001b5c0`

## callees

- `0x180026010`

## pseudocode

```c
__int64 __fastcall CommonRegisterStopCallback(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, __int64))(qword_180031540 + 192))(a1, a2);
}

```

## disassembly

```asm
0x180018f14  sub     rsp, 48h
0x180018f18  mov     rax, cs:qword_180031540
0x180018f1f  mov     [rsp+48h+var_20], 18h
0x180018f27  mov     [rsp+48h+var_28], 0
0x180018f30  mov     rax, [rax+0C0h]
0x180018f37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f3c  add     rsp, 48h
0x180018f40  retn
```
