# __report_rangecheckfailure

- ea: `0x180001440`
- end: `0x180001447`
- name: `__report_rangecheckfailure`
- size: `7`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180004c24`
- `0x180005350`

## pseudocode

```c
void __noreturn _report_rangecheckfailure()
{
  __fastfail(8u);
}

```

## disassembly

```asm
0x180001440  mov     ecx, 8
0x180001445  int     29h; Win8: RtlFailFast(ecx)
```
