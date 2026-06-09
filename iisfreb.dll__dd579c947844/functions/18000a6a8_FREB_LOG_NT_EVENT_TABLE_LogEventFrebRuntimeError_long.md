# FREB_LOG_NT_EVENT_TABLE::LogEventFrebRuntimeError(long)

- ea: `0x18000a6a8`
- end: `0x18000a6d0`
- name: `?LogEventFrebRuntimeError@FREB_LOG_NT_EVENT_TABLE@@QEAAXJ@Z`
- size: `40`
- prototype: `void(FREB_LOG_NT_EVENT_TABLE *__hidden this, int)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000209c`
- `0x180002798`
- `0x180003d0c`
- `0x180005210`
- `0x180005588`

## callees

- `0x18000a4dc`

## pseudocode

```c
void __fastcall FREB_LOG_NT_EVENT_TABLE::LogEventFrebRuntimeError(FREB_LOG_NT_EVENT_TABLE *this, unsigned int a2)
{
  unsigned __int16 *v2[2]; // [rsp+20h] [rbp-18h] BYREF

  *(_OWORD *)v2 = 0;
  FREB_LOG_NT_EVENT_TABLE::LogEvent(0x800008F2, 2u, (const unsigned __int16 **const)v2, a2);
}

```

## disassembly

```asm
0x18000a6a8  sub     rsp, 38h
0x18000a6ac  mov     r9d, edx; unsigned int
0x18000a6af  lea     r8, [rsp+38h+var_18]; unsigned __int16 **
0x18000a6b4  xorps   xmm0, xmm0
0x18000a6b7  mov     edx, 2; unsigned __int16
0x18000a6bc  mov     ecx, 800008F2h; unsigned int
0x18000a6c1  movups  xmmword ptr [rsp+38h+var_18], xmm0
0x18000a6c6  call    ?LogEvent@FREB_LOG_NT_EVENT_TABLE@@SAXKGQEAPEBGK@Z; FREB_LOG_NT_EVENT_TABLE::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x18000a6cb  add     rsp, 38h
0x18000a6cf  retn
```
