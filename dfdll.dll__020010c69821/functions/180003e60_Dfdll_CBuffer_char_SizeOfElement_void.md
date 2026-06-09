# Dfdll::CBuffer<char>::SizeOfElement(void)

- ea: `0x180003e60`
- end: `0x180003e66`
- name: `?SizeOfElement@?$CBuffer@D@Dfdll@@MEAAIXZ`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180012ccc`

## pseudocode

```c
__int64 Dfdll::CBuffer<char>::SizeOfElement()
{
  return 1;
}

```

## disassembly

```asm
0x180003e60  mov     eax, 1
0x180003e65  retn
```
