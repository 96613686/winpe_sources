# Dfdll::CBuffer<char>::AllocateInternal(uint)

- ea: `0x180002040`
- end: `0x180002047`
- name: `?AllocateInternal@?$CBuffer@D@Dfdll@@MEAAPEAXI@Z`
- size: `7`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180012c08`

## pseudocode

```c
void *__fastcall Dfdll::CBuffer<char>::AllocateInternal(__int64 a1, unsigned int a2)
{
  return operator new[](a2);
}

```

## disassembly

```asm
0x180002040  mov     ecx, edx; unsigned __int64
0x180002042  jmp     ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
```
