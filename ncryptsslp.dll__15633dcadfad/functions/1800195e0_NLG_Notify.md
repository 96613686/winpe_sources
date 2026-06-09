# _NLG_Notify

- ea: `0x1800195e0`
- end: `0x1800195f8`
- name: `_NLG_Notify`
- size: `24`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180018ca4`
- `0x18001acf0`
- `0x18001ad40`
- `0x18001ad70`
- `0x18001ada0`

## callees

- `0x180019600`

## pseudocode

```c
__int64 __fastcall NLG_Notify(__int64 a1, __int64 a2, __int64 a3)
{
  return _NLG_Dispatch2(a1, a2, a3, 429065504);
}

```

## disassembly

```asm
0x1800195e0  mov     [rsp+arg_0], rcx
0x1800195e5  mov     [rsp+arg_10], rdx
0x1800195ea  mov     [rsp+arg_8], r8d
0x1800195ef  mov     r9, 19930520h
0x1800195f6  jmp     short __NLG_Dispatch2
```
