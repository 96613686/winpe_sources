# __report_rangecheckfailure

- ea: `0x140001380`
- end: `0x140001387`
- name: `__report_rangecheckfailure`
- size: `7`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1400050fc`
- `0x140005680`

## pseudocode

```c
void __noreturn _report_rangecheckfailure()
{
  __fastfail(8u);
}

```

## disassembly

```asm
0x140001380  mov     ecx, 8
0x140001385  int     29h; Win8: RtlFailFast(ecx)
```
