# DtlAddNodeLast

- ea: `0x18000aad0`
- end: `0x18000ab09`
- name: `DtlAddNodeLast`
- size: `57`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180009588`
- `0x180009784`
- `0x18000a0c4`
- `0x18000aca4`

## callees

- `0x18000aad0`

## pseudocode

```c
_QWORD *__fastcall DtlAddNodeLast(__int64 a1, _QWORD *a2)
{
  if ( a1 && a2 )
  {
    if ( *(_DWORD *)(a1 + 16) )
    {
      *a2 = *(_QWORD *)(a1 + 8);
      *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) = a2;
    }
    else
    {
      *a2 = 0;
      *(_QWORD *)a1 = a2;
    }
    *(_QWORD *)(a1 + 8) = a2;
    a2[1] = 0;
    ++*(_DWORD *)(a1 + 16);
  }
  return a2;
}

```

## disassembly

```asm
0x18000aad0  xor     r8d, r8d
0x18000aad3  test    rcx, rcx
0x18000aad6  jz      short loc_18000AB05
0x18000aad8  test    rdx, rdx
0x18000aadb  jz      short loc_18000AB05
0x18000aadd  cmp     [rcx+10h], r8d
0x18000aae1  jz      short loc_18000AAF4
0x18000aae3  mov     rax, [rcx+8]
0x18000aae7  mov     [rdx], rax
0x18000aaea  mov     rax, [rcx+8]
0x18000aaee  mov     [rax+8], rdx
0x18000aaf2  jmp     short loc_18000AAFA
0x18000aaf4  mov     [rdx], r8
0x18000aaf7  mov     [rcx], rdx
0x18000aafa  mov     [rcx+8], rdx
0x18000aafe  mov     [rdx+8], r8
0x18000ab02  inc     dword ptr [rcx+10h]
0x18000ab05  mov     rax, rdx
0x18000ab08  retn
```
