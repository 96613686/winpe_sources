# _copysign

- ea: `0x18006ccb0`
- end: `0x18006cce4`
- name: `_copysign`
- size: `52`
- prototype: `double __cdecl(double Number, double Sign)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180073b10`

## callees

- `0x18006ccb0`

## pseudocode

```c
double __cdecl copysign(double Number, double Sign)
{
  if ( (__int64)(*(_QWORD *)&Number ^ *(_QWORD *)&Sign) < 0 )
    *(_QWORD *)&Number ^= 0x8000000000000000uLL;
  return Number;
}

```

## disassembly

```asm
0x18006ccb0  movsd   [rsp+arg_0], xmm0
0x18006ccb6  mov     rcx, [rsp+arg_0]
0x18006ccbb  movsd   [rsp+arg_0], xmm1
0x18006ccc1  mov     rax, [rsp+arg_0]
0x18006ccc6  xor     rax, rcx
0x18006ccc9  jge     short locret_18006CCE3
0x18006cccb  mov     rax, 8000000000000000h
0x18006ccd5  xor     rcx, rax
0x18006ccd8  mov     [rsp+arg_0], rcx
0x18006ccdd  movsd   xmm0, [rsp+arg_0]
0x18006cce3  retn
```
