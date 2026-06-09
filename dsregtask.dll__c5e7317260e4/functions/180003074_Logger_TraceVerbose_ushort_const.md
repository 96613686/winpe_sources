# Logger::TraceVerbose(ushort const *,...)

- ea: `0x180003074`
- end: `0x1800030a9`
- name: `?TraceVerbose@Logger@@SAJPEBGZZ`
- size: `53`
- prototype: `__int64(const unsigned __int16 *, ...)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180002190`
- `0x18000273c`
- `0x180002874`
- `0x1800029d0`

## callees

- `0x180002f28`

## pseudocode

```c
__int64 Logger::TraceVerbose(const unsigned __int16 *a1, ...)
{
  va_list va; // [rsp+48h] [rbp+10h] BYREF

  va_start(va, a1);
  return Logger::Trace(3, a1, va);
}

```

## disassembly

```asm
0x180003074  mov     rax, rsp
0x180003077  mov     [rax+8], rcx
0x18000307b  mov     [rax+10h], rdx
0x18000307f  mov     [rax+18h], r8
0x180003083  mov     [rax+20h], r9
0x180003087  sub     rsp, 38h
0x18000308b  mov     rdx, rcx
0x18000308e  mov     qword ptr [rax-18h], 0
0x180003096  mov     ecx, 3
0x18000309b  lea     r8, [rax+10h]
0x18000309f  call    ?Trace@Logger@@CAJW4_TRACE_LEVEL@@PEBGPEAD@Z; Logger::Trace(_TRACE_LEVEL,ushort const *,char *)
0x1800030a4  add     rsp, 38h
0x1800030a8  retn
```
