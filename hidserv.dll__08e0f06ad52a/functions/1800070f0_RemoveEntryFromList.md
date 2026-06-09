# RemoveEntryFromList

- ea: `0x1800070f0`
- end: `0x180007127`
- name: `RemoveEntryFromList`
- size: `55`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800026b4`
- `0x18000351c`
- `0x180006460`

## callees

- `0x1800070f0`

## pseudocode

```c
__int64 __fastcall RemoveEntryFromList(__int64 a1, __int64 *a2)
{
  __int64 *v2; // rcx
  __int64 *v3; // r8

  v2 = (__int64 *)HidDeviceList;
  if ( (__int64 *)HidDeviceList == a2 )
  {
    v3 = &HidDeviceList;
LABEL_7:
    *v3 = *a2;
    return 1;
  }
  else
  {
    while ( v2 )
    {
      v3 = v2;
      v2 = (__int64 *)*v2;
      if ( v2 == a2 )
        goto LABEL_7;
    }
    return 0;
  }
}

```

## disassembly

```asm
0x1800070f0  mov     rcx, cs:HidDeviceList
0x1800070f7  cmp     rcx, rdx
0x1800070fa  jz      short loc_180007114
0x1800070fc  test    rcx, rcx
0x1800070ff  jz      short loc_180007111
0x180007101  mov     rax, [rcx]
0x180007104  mov     r8, rcx
0x180007107  mov     rcx, rax
0x18000710a  cmp     rax, rdx
0x18000710d  jnz     short loc_1800070FC
0x18000710f  jmp     short loc_18000711B
0x180007111  xor     eax, eax
0x180007113  retn
0x180007114  lea     r8, HidDeviceList
0x18000711b  mov     rax, [rdx]
0x18000711e  mov     [r8], rax
0x180007121  mov     eax, 1
0x180007126  retn
```
