# __CxxSetUnhandledExceptionFilter

- ea: `0x140001380`
- end: `0x140001398`
- name: `__CxxSetUnhandledExceptionFilter`
- size: `24`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x14000138b`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x14000138b`

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
0x140001380  sub     rsp, 28h
0x140001384  lea     rcx, ?__CxxUnhandledExceptionFilter@@YAJPEAU_EXCEPTION_POINTERS@@@Z; lpTopLevelExceptionFilter
0x14000138b  call    cs:__imp_SetUnhandledExceptionFilter
0x140001391  xor     eax, eax
0x140001393  add     rsp, 28h
0x140001397  retn
```
