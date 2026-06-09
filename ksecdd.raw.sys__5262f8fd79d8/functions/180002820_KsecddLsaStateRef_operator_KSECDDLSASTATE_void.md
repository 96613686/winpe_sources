# KsecddLsaStateRef::operator _KSECDDLSASTATE *(void)

- ea: `0x180002820`
- end: `0x180002824`
- name: `??BKsecddLsaStateRef@@QEAAPEAU_KSECDDLSASTATE@@XZ`
- size: `4`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `24`
- callee_count: `0`
- tags: ``

## callers

- `0x180021a40`
- `0x180021b68`
- `0x18002267c`
- `0x1800230d0`
- `0x180024330`
- `0x180024910`
- `0x1800250e0`
- `0x180025220`
- `0x180025c20`
- `0x180025e00`
- `0x180026fb8`
- `0x180029008`
- `0x1800290c4`
- `0x180029180`
- `0x18002923c`
- `0x1800294a0`
- `0x180029570`
- `0x180029690`
- `0x1800297f0`
- `0x1800298e0`
- `0x180029aa0`
- `0x180029ba0`
- `0x180029c90`
- `0x180029d80`

## pseudocode

```c
__int64 __fastcall KsecddLsaStateRef::operator _KSECDDLSASTATE *(__int64 a1)
{
  return *(_QWORD *)a1;
}

```

## disassembly

```asm
0x180002820  mov     rax, [rcx]
0x180002823  retn
```
