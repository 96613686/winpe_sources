# ATL::SafeDecrementReferenceMultiThread(long volatile *)

- ea: `0x18000ea44`
- end: `0x18000ea66`
- name: `?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z`
- size: `34`
- prototype: `unsigned int __fastcall(volatile int *)`
- caller_count: `39`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005bf8`
- `0x180005dd4`
- `0x180005ea4`
- `0x18000aec0`
- `0x18000b000`
- `0x18000b380`
- `0x18000b4c0`
- `0x18000d350`
- `0x18000d910`
- `0x18000e130`
- `0x18000e210`
- `0x18000f278`
- `0x1800163e0`
- `0x18001649c`
- `0x180016680`
- `0x1800166f0`
- `0x180017910`
- `0x1800179cc`
- `0x18001c870`
- `0x18001c940`
- `0x18001c9b0`
- `0x1800272b0`
- `0x180028208`
- `0x180028940`
- `0x18002de28`
- `0x18002fbc0`
- `0x18002fc80`
- `0x1800327e8`
- `0x180033a20`
- `0x180033ad0`
- `0x1800378e8`
- `0x180039250`
- `0x18003cc58`
- `0x18003cd90`
- `0x18003ce6c`
- `0x18003dc30`
- `0x18003dcb0`
- `0x1800432c0`
- `0x180046a30`

## callees

- `0x18000ea44`

## pseudocode

```c
__int64 __fastcall ATL::SafeDecrementReferenceMultiThread(volatile int *a1)
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
0x18000ea44  mov     r9d, 7FFFFFFFh
0x18000ea4a  jmp     short loc_18000EA59
0x18000ea4c  lea     edx, [r8-1]
0x18000ea50  mov     eax, r8d
0x18000ea53  lock cmpxchg [rcx], edx
0x18000ea57  jz      short loc_18000EA61
0x18000ea59  mov     r8d, [rcx]
0x18000ea5c  cmp     r8d, r9d
0x18000ea5f  jnz     short loc_18000EA4C
0x18000ea61  lea     eax, [r8-1]
0x18000ea65  retn
```
