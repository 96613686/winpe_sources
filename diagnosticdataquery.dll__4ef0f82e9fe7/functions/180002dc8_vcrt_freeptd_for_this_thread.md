# __vcrt_freeptd_for_this_thread

- ea: `0x180002dc8`
- end: `0x180002e0f`
- name: `__vcrt_freeptd_for_this_thread`
- size: `71`
- prototype: `void()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002c3c`

## callees

- `0x180002dc8`
- `0x180005176`

## import_xrefs

- `api-ms-win-core-fibers-l1-1-0!FlsSetValue` at `0x180002dea`
- `api-ms-win-core-fibers-l1-1-0!FlsSetValue` at `0x180002dea`
- `api-ms-win-core-fibers-l1-1-0!FlsGetValue` at `0x180002dd9`
- `api-ms-win-core-fibers-l1-1-0!FlsGetValue` at `0x180002dd9`

## pseudocode

```c
void _vcrt_freeptd_for_this_thread()
{
  __int64 *Value; // rbx

  if ( dwFlsIndex != -1 )
  {
    Value = (__int64 *)FlsGetValue(dwFlsIndex);
    FlsSetValue(dwFlsIndex, 0);
    if ( Value )
    {
      if ( Value != qword_1800142B0 )
        free_base_0(Value);
    }
  }
}

```

## disassembly

```asm
0x180002dc8  push    rbx
0x180002dca  sub     rsp, 20h
0x180002dce  mov     ecx, cs:dwFlsIndex; dwFlsIndex
0x180002dd4  cmp     ecx, 0FFFFFFFFh
0x180002dd7  jz      short loc_180002E09
0x180002dd9  call    cs:__imp_FlsGetValue
0x180002ddf  mov     ecx, cs:dwFlsIndex; dwFlsIndex
0x180002de5  xor     edx, edx; lpFlsData
0x180002de7  mov     rbx, rax
0x180002dea  call    cs:__imp_FlsSetValue
0x180002df0  test    rbx, rbx
0x180002df3  jz      short loc_180002E09
0x180002df5  lea     rax, qword_1800142B0
0x180002dfc  cmp     rbx, rax
0x180002dff  jz      short loc_180002E09
0x180002e01  mov     rcx, rbx; Block
0x180002e04  call    _free_base_0
0x180002e09  add     rsp, 20h
0x180002e0d  pop     rbx
0x180002e0e  retn
```
