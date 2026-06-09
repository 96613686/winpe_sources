# __CxxSetUnhandledExceptionFilter

- ea: `0x1400013d0`
- end: `0x1400013e8`
- name: `__CxxSetUnhandledExceptionFilter`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNEL32!SetUnhandledExceptionFilter` at `0x1400013db`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1400013db`

## pseudocode

```c
__int64 _CxxSetUnhandledExceptionFilter()
{
  SetUnhandledExceptionFilter((LPTOP_LEVEL_EXCEPTION_FILTER)__CxxUnhandledExceptionFilter);
  return 0;
}

```

## disassembly

```asm
0x1400013d0  sub     rsp, 28h
0x1400013d4  lea     rcx, ?__CxxUnhandledExceptionFilter@@YAJPEAU_EXCEPTION_POINTERS@@@Z; lpTopLevelExceptionFilter
0x1400013db  call    cs:__imp_SetUnhandledExceptionFilter
0x1400013e1  xor     eax, eax
0x1400013e3  add     rsp, 28h
0x1400013e7  retn
```
