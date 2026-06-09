# DtlAddNodeLast

- ea: `0x180026f90`
- end: `0x180026fc9`
- name: `DtlAddNodeLast`
- size: `57`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800262d0`
- `0x180026640`
- `0x180026cf8`

## callees

- `0x180026f90`

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
0x180026f90  xor     r8d, r8d
0x180026f93  test    rcx, rcx
0x180026f96  jz      short loc_180026FC5
0x180026f98  test    rdx, rdx
0x180026f9b  jz      short loc_180026FC5
0x180026f9d  cmp     [rcx+10h], r8d
0x180026fa1  jz      short loc_180026FB4
0x180026fa3  mov     rax, [rcx+8]
0x180026fa7  mov     [rdx], rax
0x180026faa  mov     rax, [rcx+8]
0x180026fae  mov     [rax+8], rdx
0x180026fb2  jmp     short loc_180026FBA
0x180026fb4  mov     [rdx], r8
0x180026fb7  mov     [rcx], rdx
0x180026fba  mov     [rcx+8], rdx
0x180026fbe  mov     [rdx+8], r8
0x180026fc2  inc     dword ptr [rcx+10h]
0x180026fc5  mov     rax, rdx
0x180026fc8  retn
```
