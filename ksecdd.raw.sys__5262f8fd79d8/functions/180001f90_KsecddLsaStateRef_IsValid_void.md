# KsecddLsaStateRef::IsValid(void)

- ea: `0x180001f90`
- end: `0x180001f98`
- name: `?IsValid@KsecddLsaStateRef@@QEAA_NXZ`
- size: `8`
- prototype: `bool __fastcall(KsecddLsaStateRef *__hidden this)`
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
bool __fastcall KsecddLsaStateRef::IsValid(KsecddLsaStateRef *this)
{
  return *(_QWORD *)this != 0;
}

```

## disassembly

```asm
0x180001f90  cmp     qword ptr [rcx], 0
0x180001f94  setnz   al
0x180001f97  retn
```
