# Logger::TraceWarning(ushort const *,...)

- ea: `0x1800030b0`
- end: `0x1800030e5`
- name: `?TraceWarning@Logger@@SAJPEBGZZ`
- size: `53`
- prototype: `__int64(const unsigned __int16 *, ...)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002190`
- `0x180002874`

## callees

- `0x180002f28`

## pseudocode

```c
__int64 Logger::TraceWarning(const unsigned __int16 *a1, ...)
{
  va_list va; // [rsp+48h] [rbp+10h] BYREF

  va_start(va, a1);
  return Logger::Trace(1, a1, va);
}

```

## disassembly

```asm
0x1800030b0  mov     rax, rsp
0x1800030b3  mov     [rax+8], rcx
0x1800030b7  mov     [rax+10h], rdx
0x1800030bb  mov     [rax+18h], r8
0x1800030bf  mov     [rax+20h], r9
0x1800030c3  sub     rsp, 38h
0x1800030c7  mov     rdx, rcx
0x1800030ca  mov     qword ptr [rax-18h], 0
0x1800030d2  mov     ecx, 1
0x1800030d7  lea     r8, [rax+10h]
0x1800030db  call    ?Trace@Logger@@CAJW4_TRACE_LEVEL@@PEBGPEAD@Z; Logger::Trace(_TRACE_LEVEL,ushort const *,char *)
0x1800030e0  add     rsp, 38h
0x1800030e4  retn
```
