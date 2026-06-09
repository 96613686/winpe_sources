# CxPlatHashtableRemove

- ea: `0x140038bc8`
- end: `0x140038bec`
- name: `CxPlatHashtableRemove`
- size: `36`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140005008`
- `0x14000b780`
- `0x14001d7f4`
- `0x14001de64`
- `0x140020880`
- `0x14003ff2c`

## callees

- `0x140038bc8`

## pseudocode

```c
__int64 *__fastcall CxPlatHashtableRemove(__int64 a1, __int64 *a2)
{
  __int64 *result; // rax
  __int64 v3; // rcx

  --*(_DWORD *)(a1 + 16);
  if ( *a2 == a2[1] )
    --*(_DWORD *)(a1 + 20);
  result = (__int64 *)a2[1];
  v3 = *a2;
  *result = *a2;
  *(_QWORD *)(v3 + 8) = result;
  return result;
}

```

## disassembly

```asm
0x140038bc8  or      r8d, 0FFFFFFFFh
0x140038bcc  add     [rcx+10h], r8d
0x140038bd0  mov     rax, [rdx+8]
0x140038bd4  cmp     [rdx], rax
0x140038bd7  jnz     short loc_140038BDD
0x140038bd9  add     [rcx+14h], r8d
0x140038bdd  mov     rax, [rdx+8]
0x140038be1  mov     rcx, [rdx]
0x140038be4  mov     [rax], rcx
0x140038be7  mov     [rcx+8], rax
0x140038beb  retn
```
