# HvStatspLookupMapping

- ea: `0x1400102f0`
- end: `0x140010319`
- name: `HvStatspLookupMapping`
- size: `41`
- prototype: `__int64 *__fastcall(__int64, int, int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000fee8`
- `0x14001006c`

## callees

- `0x1400102f0`

## pseudocode

```c
__int64 *__fastcall HvStatspLookupMapping(__int64 a1, int a2, int a3)
{
  __int64 *result; // rax

  result = *(__int64 **)(a1 + 8);
  if ( result == (__int64 *)(a1 + 8) )
    return 0;
  while ( *((_DWORD *)result + 4) != a2 || *((_DWORD *)result + 5) != a3 )
  {
    result = (__int64 *)*result;
    if ( result == (__int64 *)(a1 + 8) )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400102f0  mov     rax, [rcx+8]
0x1400102f4  lea     r9, [rcx+8]
0x1400102f8  xor     ecx, ecx
0x1400102fa  cmp     rax, r9
0x1400102fd  jz      short loc_140010315
0x1400102ff  nop
0x140010300  cmp     [rax+10h], edx
0x140010303  jnz     short loc_14001030B
0x140010305  cmp     [rax+14h], r8d
0x140010309  jz      short locret_140010318
0x14001030b  mov     rax, [rax]
0x14001030e  xor     ecx, ecx
0x140010310  cmp     rax, r9
0x140010313  jnz     short loc_140010300
0x140010315  mov     rax, rcx
0x140010318  retn
```
