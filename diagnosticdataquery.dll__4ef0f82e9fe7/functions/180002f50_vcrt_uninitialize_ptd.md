# __vcrt_uninitialize_ptd

- ea: `0x180002f50`
- end: `0x180002f76`
- name: `__vcrt_uninitialize_ptd`
- size: `38`
- prototype: `char()`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002c54`
- `0x180002c74`
- `0x180002f00`

## callees

- `0x180002f50`

## import_xrefs

- `api-ms-win-core-fibers-l1-1-0!FlsFree` at `0x180002f5f`
- `api-ms-win-core-fibers-l1-1-0!FlsFree` at `0x180002f5f`

## pseudocode

```c
char _vcrt_uninitialize_ptd()
{
  if ( dwFlsIndex != -1 )
  {
    FlsFree(dwFlsIndex);
    dwFlsIndex = -1;
  }
  return 1;
}

```

## disassembly

```asm
0x180002f50  sub     rsp, 28h
0x180002f54  mov     ecx, cs:dwFlsIndex; dwFlsIndex
0x180002f5a  cmp     ecx, 0FFFFFFFFh
0x180002f5d  jz      short loc_180002F6F
0x180002f5f  call    cs:__imp_FlsFree
0x180002f65  mov     cs:dwFlsIndex, 0FFFFFFFFh
0x180002f6f  mov     al, 1
0x180002f71  add     rsp, 28h
0x180002f75  retn
```
