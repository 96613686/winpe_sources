# __GSHandlerCheck

- ea: `0x180003578`
- end: `0x180003595`
- name: `__GSHandlerCheck`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000359c`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheck(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  _GSHandlerCheckCommon(a2, a4);
  return 1;
}

```

## disassembly

```asm
0x180003578  sub     rsp, 28h
0x18000357c  mov     r8, [r9+38h]
0x180003580  mov     rcx, rdx
0x180003583  mov     rdx, r9
0x180003586  call    __GSHandlerCheckCommon
0x18000358b  mov     eax, 1
0x180003590  add     rsp, 28h
0x180003594  retn
```
