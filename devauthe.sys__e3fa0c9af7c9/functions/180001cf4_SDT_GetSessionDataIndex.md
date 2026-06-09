# _SDT_GetSessionDataIndex

- ea: `0x180001cf4`
- end: `0x180001d2f`
- name: `_SDT_GetSessionDataIndex`
- size: `59`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1800013a0`
- `0x180001450`
- `0x1800015f0`
- `0x1800016a0`
- `0x1800018f0`
- `0x180001980`
- `0x180001b10`

## callees

- `0x180001cf4`

## pseudocode

```c
__int64 __fastcall SDT_GetSessionDataIndex(__int64 a1, _QWORD *a2)
{
  unsigned int v2; // r9d
  __int64 v3; // r10
  __int64 v4; // r8
  _QWORD *v5; // rcx

  v2 = *(_DWORD *)a1;
  if ( !*(_DWORD *)a1 )
    return 0xFFFFFFFFLL;
  v3 = *(_QWORD *)(a1 + 8);
  v4 = 0;
  while ( 1 )
  {
    v5 = *(_QWORD **)(v3 + 8 * v4);
    if ( v5 )
    {
      if ( *v5 == *a2 && v5[1] == a2[1] )
        break;
    }
    v4 = (unsigned int)(v4 + 1);
    if ( (unsigned int)v4 >= v2 )
      return 0xFFFFFFFFLL;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180001cf4  mov     r9d, [rcx]
0x180001cf7  test    r9d, r9d
0x180001cfa  jz      short loc_180001D26
0x180001cfc  mov     r10, [rcx+8]
0x180001d00  xor     r8d, r8d
0x180001d03  mov     rcx, [r10+r8*8]
0x180001d07  test    rcx, rcx
0x180001d0a  jz      short loc_180001D1E
0x180001d0c  mov     rax, [rcx]
0x180001d0f  cmp     rax, [rdx]
0x180001d12  jnz     short loc_180001D1E
0x180001d14  mov     rax, [rcx+8]
0x180001d18  cmp     rax, [rdx+8]
0x180001d1c  jz      short loc_180001D2B
0x180001d1e  inc     r8d
0x180001d21  cmp     r8d, r9d
0x180001d24  jb      short loc_180001D03
0x180001d26  or      eax, 0FFFFFFFFh
0x180001d29  retn
0x180001d2b  mov     eax, r8d
0x180001d2e  retn
```
