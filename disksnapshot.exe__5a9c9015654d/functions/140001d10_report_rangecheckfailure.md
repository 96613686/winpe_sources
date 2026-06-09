# __report_rangecheckfailure

- ea: `0x140001d10`
- end: `0x140001d17`
- name: `__report_rangecheckfailure`
- size: `7`
- prototype: `void __noreturn()`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140006424`
- `0x14000ba74`

## pseudocode

```c
void __noreturn _report_rangecheckfailure()
{
  __fastfail(8u);
}

```

## disassembly

```asm
0x140001d10  mov     ecx, 8
0x140001d15  int     29h; Win8: RtlFailFast(ecx)
```
