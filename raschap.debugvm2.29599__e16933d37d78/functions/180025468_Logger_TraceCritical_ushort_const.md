# Logger::TraceCritical(ushort const *,...)

- ea: `0x180025468`
- end: `0x18002549d`
- name: `?TraceCritical@Logger@@SAJPEBGZZ`
- size: `53`
- prototype: `__int64(const unsigned __int16 *, ...)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ff18`
- `0x1800241c0`
- `0x180024398`
- `0x180024c04`
- `0x180024ea8`
- `0x180025030`
- `0x1800251e8`
- `0x18002594c`

## callees

- `0x18000e548`

## pseudocode

```c
__int64 Logger::TraceCritical(const unsigned __int16 *a1, ...)
{
  va_list va; // [rsp+48h] [rbp+10h] BYREF

  va_start(va, a1);
  return Logger::Trace(4, a1, (__int64 *)va);
}

```

## disassembly

```asm
0x180025468  mov     rax, rsp
0x18002546b  mov     [rax+8], rcx
0x18002546f  mov     [rax+10h], rdx
0x180025473  mov     [rax+18h], r8
0x180025477  mov     [rax+20h], r9
0x18002547b  sub     rsp, 38h
0x18002547f  mov     rdx, rcx
0x180025482  mov     qword ptr [rax-18h], 0
0x18002548a  mov     ecx, 4
0x18002548f  lea     r8, [rax+10h]
0x180025493  call    ?Trace@Logger@@CAJW4_TRACE_LEVEL@@PEBGPEAD@Z; Logger::Trace(_TRACE_LEVEL,ushort const *,char *)
0x180025498  add     rsp, 38h
0x18002549c  retn
```
