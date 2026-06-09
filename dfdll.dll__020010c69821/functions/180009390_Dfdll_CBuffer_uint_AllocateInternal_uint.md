# Dfdll::CBuffer<uint>::AllocateInternal(uint)

- ea: `0x180009390`
- end: `0x1800093ad`
- name: `?AllocateInternal@?$CBuffer@I@Dfdll@@MEAAPEAXI@Z`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180012c08`

## pseudocode

```c
void *__fastcall Dfdll::CBuffer<unsigned int>::AllocateInternal(__int64 a1, unsigned int a2)
{
  return operator new[](saturated_mul(a2, 4u));
}

```

## disassembly

```asm
0x180009390  mov     ecx, edx
0x180009392  mov     eax, 4
0x180009397  mul     rcx
0x18000939a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800093a1  cmovo   rax, rcx
0x1800093a5  mov     rcx, rax; unsigned __int64
0x1800093a8  jmp     ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
```
