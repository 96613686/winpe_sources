# Logger::TraceInformation(ushort const *,...)

- ea: `0x18000303c`
- end: `0x18000306e`
- name: `?TraceInformation@Logger@@SAJPEBGZZ`
- size: `50`
- prototype: `__int64(const unsigned __int16 *, ...)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002190`
- `0x18000273c`

## callees

- `0x180002f28`

## pseudocode

```c
__int64 Logger::TraceInformation(const unsigned __int16 *a1, ...)
{
  va_list va; // [rsp+48h] [rbp+10h] BYREF

  va_start(va, a1);
  return Logger::Trace(0, a1, va);
}

```

## disassembly

```asm
0x18000303c  mov     rax, rsp
0x18000303f  mov     [rax+8], rcx
0x180003043  mov     [rax+10h], rdx
0x180003047  mov     [rax+18h], r8
0x18000304b  mov     [rax+20h], r9
0x18000304f  sub     rsp, 38h
0x180003053  mov     rdx, rcx
0x180003056  mov     qword ptr [rax-18h], 0
0x18000305e  xor     ecx, ecx
0x180003060  lea     r8, [rax+10h]
0x180003064  call    ?Trace@Logger@@CAJW4_TRACE_LEVEL@@PEBGPEAD@Z; Logger::Trace(_TRACE_LEVEL,ushort const *,char *)
0x180003069  add     rsp, 38h
0x18000306d  retn
```
