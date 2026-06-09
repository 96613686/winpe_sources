# ReferenceVc

- ea: `0x140001990`
- end: `0x140001995`
- name: `ReferenceVc`
- size: `5`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x14000fd0c`
- `0x1400109d0`
- `0x140011518`
- `0x1400154b8`
- `0x140015ebc`
- `0x1400175f0`
- `0x14001a640`
- `0x14001b8a0`
- `0x14001c050`
- `0x14001c470`

## pseudocode

```c
void __fastcall ReferenceVc(__int64 a1)
{
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 20));
}

```

## disassembly

```asm
0x140001990  lock inc dword ptr [rcx+14h]
0x140001994  retn
```
