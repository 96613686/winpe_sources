# RtdsInternalUpdateCallback

- ea: `0x140009210`
- end: `0x140009227`
- name: `RtdsInternalUpdateCallback`
- size: `23`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int, int, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x140009230`

## pseudocode

```c
__int64 __fastcall RtdsInternalUpdateCallback(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, int a5, __int64 a6)
{
  return RtdsInternalUpdateCallbackWorker(a4, a6);
}

```

## disassembly

```asm
0x140009210  sub     rsp, 28h
0x140009214  mov     rdx, [rsp+28h+arg_28]
0x140009219  mov     ecx, r9d
0x14000921c  call    RtdsInternalUpdateCallbackWorker
0x140009221  add     rsp, 28h
0x140009225  retn
```
