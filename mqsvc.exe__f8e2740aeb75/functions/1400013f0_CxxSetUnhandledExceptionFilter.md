# __CxxSetUnhandledExceptionFilter

- ea: `0x1400013f0`
- end: `0x140001408`
- name: `__CxxSetUnhandledExceptionFilter`
- size: `24`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNEL32!SetUnhandledExceptionFilter` at `0x1400013fb`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1400013fb`

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
0x1400013f0  sub     rsp, 28h
0x1400013f4  lea     rcx, ?__CxxUnhandledExceptionFilter@@YAJPEAU_EXCEPTION_POINTERS@@@Z; lpTopLevelExceptionFilter
0x1400013fb  call    cs:__imp_SetUnhandledExceptionFilter
0x140001401  xor     eax, eax
0x140001403  add     rsp, 28h
0x140001407  retn
```
