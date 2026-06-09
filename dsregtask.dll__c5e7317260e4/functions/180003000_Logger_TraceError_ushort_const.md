# Logger::TraceError(ushort const *,...)

- ea: `0x180003000`
- end: `0x180003035`
- name: `?TraceError@Logger@@SAJPEBGZZ`
- size: `53`
- prototype: `__int64(const unsigned __int16 *, ...)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180002190`
- `0x18000273c`
- `0x180002874`
- `0x1800029d0`
- `0x1800030ec`
- `0x180003454`
- `0x1800035d8`

## callees

- `0x180002f28`

## pseudocode

```c
__int64 Logger::TraceError(const unsigned __int16 *a1, ...)
{
  va_list va; // [rsp+48h] [rbp+10h] BYREF

  va_start(va, a1);
  return Logger::Trace(2, a1, va);
}

```

## disassembly

```asm
0x180003000  mov     rax, rsp
0x180003003  mov     [rax+8], rcx
0x180003007  mov     [rax+10h], rdx
0x18000300b  mov     [rax+18h], r8
0x18000300f  mov     [rax+20h], r9
0x180003013  sub     rsp, 38h
0x180003017  mov     rdx, rcx
0x18000301a  mov     qword ptr [rax-18h], 0
0x180003022  mov     ecx, 2
0x180003027  lea     r8, [rax+10h]
0x18000302b  call    ?Trace@Logger@@CAJW4_TRACE_LEVEL@@PEBGPEAD@Z; Logger::Trace(_TRACE_LEVEL,ushort const *,char *)
0x180003030  add     rsp, 38h
0x180003034  retn
```
