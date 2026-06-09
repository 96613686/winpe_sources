# _NLG_Notify

- ea: `0x180004ea0`
- end: `0x180004eb8`
- name: `_NLG_Notify`
- size: `24`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `5`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1800029f4`
- `0x180004fb0`
- `0x180005000`
- `0x180005030`
- `0x180005060`

## callees

- `0x180004ec0`

## pseudocode

```c
__int64 __fastcall NLG_Notify(__int64 a1, __int64 a2, __int64 a3)
{
  return _NLG_Dispatch2(a1, a2, a3, 429065504);
}

```

## disassembly

```asm
0x180004ea0  mov     [rsp+arg_0], rcx
0x180004ea5  mov     [rsp+arg_10], rdx
0x180004eaa  mov     [rsp+arg_8], r8d
0x180004eaf  mov     r9, 19930520h
0x180004eb6  jmp     short __NLG_Dispatch2
```
