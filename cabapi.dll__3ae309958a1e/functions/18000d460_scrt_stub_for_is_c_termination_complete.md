# __scrt_stub_for_is_c_termination_complete

- ea: `0x18000d460`
- end: `0x18000d463`
- name: `__scrt_stub_for_is_c_termination_complete`
- size: `3`
- prototype: `__int64 __fastcall(PCCAB pccab, LPSTR pszFile, int cbFile, BOOL fContinuation)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800016dc`

## pseudocode

```c
__int64 __fastcall _scrt_stub_for_is_c_termination_complete(PCCAB pccab, LPSTR pszFile, int cbFile, BOOL fContinuation)
{
  return 0;
}

```

## disassembly

```asm
0x18000d460  xor     eax, eax
0x18000d462  retn
```
