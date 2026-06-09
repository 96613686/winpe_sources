# operator delete(void *,std::nothrow_t const &)

- ea: `0x180012b30`
- end: `0x180012b35`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __fastcall(void *, const struct std::nothrow_t *)`
- caller_count: `71`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800010e0`
- `0x1800015d0`
- `0x180001874`
- `0x1800018b0`
- `0x18000190c`
- `0x1800019f8`
- `0x180001a64`
- `0x180001b80`
- `0x180001be0`
- `0x180001c40`
- `0x180001ca0`
- `0x180001cd0`
- `0x180001d10`
- `0x180001d80`
- `0x180001dd0`
- `0x180001e10`
- `0x1800020d4`
- `0x180002238`
- `0x180002988`
- `0x180002b80`
- `0x180002db0`
- `0x180002de0`
- `0x180002ff8`
- `0x180003168`
- `0x1800036c8`
- `0x1800037a0`
- `0x180003e88`
- `0x180004580`
- `0x180004e30`
- `0x180005230`
- `0x180005400`
- `0x180006180`
- `0x180006e60`
- `0x180007130`
- `0x1800072e0`
- `0x1800073d0`
- `0x180007550`
- `0x180007770`
- `0x1800077d0`
- `0x180007a7c`
- `0x180008b00`
- `0x180008c6c`
- `0x180008d34`
- `0x180009030`
- `0x1800090a0`
- `0x180009100`
- `0x180009160`
- `0x1800091d0`
- `0x180009210`
- `0x180009270`

## callees

- `0x180001b58`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *a1, const struct std::nothrow_t *a2)
{
  ??3@YAXPEAX@Z(a1);
}

```

## disassembly

```asm
0x180012b30  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
