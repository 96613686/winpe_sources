# Dfdll::CBuffer<ushort>::AllocateInternal(uint)

- ea: `0x180002050`
- end: `0x18000206d`
- name: `?AllocateInternal@?$CBuffer@G@Dfdll@@MEAAPEAXI@Z`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180012c08`

## pseudocode

```c
void *__fastcall Dfdll::CBuffer<unsigned short>::AllocateInternal(__int64 a1, unsigned int a2)
{
  return operator new[](saturated_mul(a2, 2u));
}

```

## disassembly

```asm
0x180002050  mov     ecx, edx
0x180002052  mov     eax, 2
0x180002057  mul     rcx
0x18000205a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180002061  cmovo   rax, rcx
0x180002065  mov     rcx, rax; unsigned __int64
0x180002068  jmp     ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
```
