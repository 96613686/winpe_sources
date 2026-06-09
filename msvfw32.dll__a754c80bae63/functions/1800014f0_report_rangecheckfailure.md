# __report_rangecheckfailure

- ea: `0x1800014f0`
- end: `0x1800014f7`
- name: `__report_rangecheckfailure`
- size: `7`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1800031d0`
- `0x180010884`
- `0x180010aa4`
- `0x1800129a0`

## pseudocode

```c
void __noreturn _report_rangecheckfailure()
{
  __fastfail(8u);
}

```

## disassembly

```asm
0x1800014f0  mov     ecx, 8
0x1800014f5  int     29h; Win8: RtlFailFast(ecx)
```
