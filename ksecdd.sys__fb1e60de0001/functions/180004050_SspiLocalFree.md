# SspiLocalFree

- ea: `0x180004050`
- end: `0x18000406d`
- name: `SspiLocalFree`
- size: `29`
- prototype: `void __stdcall(PVOID DataBuffer)`
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x180002a84`
- `0x18000368c`
- `0x180003a54`
- `0x180003c38`
- `0x180003e20`
- `0x180007fc4`
- `0x1800081c4`
- `0x180008438`
- `0x180008a40`
- `0x1800092d0`
- `0x18000a070`
- `0x18000a6d0`
- `0x18000aa60`
- `0x180025220`
- `0x18002733c`

## callees

- `0x180004050`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18000405b`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000405b`

## pseudocode

```c
void __stdcall SspiLocalFree(PVOID DataBuffer)
{
  if ( DataBuffer )
    ExFreePoolWithTag(DataBuffer, 0);
}

```

## disassembly

```asm
0x180004050  sub     rsp, 28h
0x180004054  test    rcx, rcx
0x180004057  jz      short loc_180004067
0x180004059  xor     edx, edx; Tag
0x18000405b  call    cs:__imp_ExFreePoolWithTag
0x180004062  nop     dword ptr [rax+rax+00h]
0x180004067  add     rsp, 28h
0x18000406b  retn
```
