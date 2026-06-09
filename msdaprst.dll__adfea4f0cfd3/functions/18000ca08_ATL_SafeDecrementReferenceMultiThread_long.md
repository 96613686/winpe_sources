# ATL::SafeDecrementReferenceMultiThread(long *)

- ea: `0x18000ca08`
- end: `0x18000ca2a`
- name: `?SafeDecrementReferenceMultiThread@ATL@@YAKPEAJ@Z`
- size: `34`
- prototype: `unsigned int __fastcall(int *)`
- caller_count: `21`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000c6a0`
- `0x18000c6e0`
- `0x18000c720`
- `0x18000c760`
- `0x18000c7a0`
- `0x18000c7e0`
- `0x18000c820`
- `0x18000c860`
- `0x18000c8a0`
- `0x18000c8e0`
- `0x18000c920`
- `0x18000c980`
- `0x180015330`
- `0x180015370`
- `0x1800153f0`
- `0x180015430`
- `0x180019660`
- `0x180019c70`
- `0x180019d80`
- `0x180023000`
- `0x180023040`

## callees

- `0x18000ca08`

## pseudocode

```c
__int64 __fastcall ATL::SafeDecrementReferenceMultiThread(int *a1)
{
  signed __int32 v1; // r8d

  do
    v1 = *a1;
  while ( *a1 != 0x7FFFFFFF && v1 != _InterlockedCompareExchange(a1, v1 - 1, v1) );
  return (unsigned int)(v1 - 1);
}

```

## disassembly

```asm
0x18000ca08  mov     r9d, 7FFFFFFFh
0x18000ca0e  jmp     short loc_18000CA1D
0x18000ca10  lea     edx, [r8-1]
0x18000ca14  mov     eax, r8d
0x18000ca17  lock cmpxchg [rcx], edx
0x18000ca1b  jz      short loc_18000CA25
0x18000ca1d  mov     r8d, [rcx]
0x18000ca20  cmp     r8d, r9d
0x18000ca23  jnz     short loc_18000CA10
0x18000ca25  lea     eax, [r8-1]
0x18000ca29  retn
```
