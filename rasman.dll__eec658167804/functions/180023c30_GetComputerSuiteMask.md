# GetComputerSuiteMask

- ea: `0x180023c30`
- end: `0x180023c5e`
- name: `GetComputerSuiteMask`
- size: `46`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800202a0`

## callees

- `0x180023c30`
- `0x180023c64`

## pseudocode

```c
__int64 __fastcall GetComputerSuiteMask(_DWORD *a1)
{
  unsigned int v1; // edx
  __int64 result; // rax

  v1 = 0;
  if ( dword_180030950 || (result = LoadSkuAndRole(), (v1 = result) == 0) )
  {
    *a1 = dword_180030920;
    return v1;
  }
  return result;
}

```

## disassembly

```asm
0x180023c30  push    rbx
0x180023c32  sub     rsp, 20h
0x180023c36  xor     edx, edx
0x180023c38  mov     rbx, rcx
0x180023c3b  cmp     cs:dword_180030950, edx
0x180023c41  jnz     short loc_180023C4E
0x180023c43  call    LoadSkuAndRole
0x180023c48  mov     edx, eax
0x180023c4a  test    eax, eax
0x180023c4c  jnz     short loc_180023C58
0x180023c4e  mov     eax, cs:dword_180030920
0x180023c54  mov     [rbx], eax
0x180023c56  mov     eax, edx
0x180023c58  add     rsp, 20h
0x180023c5c  pop     rbx
0x180023c5d  retn
```
