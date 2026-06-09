# __std_type_info_compare

- ea: `0x180014b68`
- end: `0x180014b8f`
- name: `__std_type_info_compare`
- size: `39`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800169b8`

## callees

- `0x180014b68`

## pseudocode

```c
__int64 __fastcall _std_type_info_compare(__int64 a1, __int64 a2)
{
  char *v2; // rax
  __int64 v3; // rdx
  char v4; // cl

  if ( a1 == a2 )
    return 0;
  v2 = (char *)(a1 + 9);
  v3 = a2 - a1;
  while ( 1 )
  {
    v4 = *v2;
    if ( *v2 != v2[v3] )
      break;
    ++v2;
    if ( !v4 )
      return 0;
  }
  return (unsigned __int8)*v2 < (unsigned __int8)v2[v3] ? -1 : 1;
}

```

## disassembly

```asm
0x180014b68  cmp     rcx, rdx
0x180014b6b  jz      short loc_180014B86
0x180014b6d  add     rdx, 9
0x180014b71  lea     rax, [rcx+9]
0x180014b75  sub     rdx, rax
0x180014b78  mov     cl, [rax]
0x180014b7a  cmp     cl, [rax+rdx]
0x180014b7d  jnz     short loc_180014B89
0x180014b7f  inc     rax
0x180014b82  test    cl, cl
0x180014b84  jnz     short loc_180014B78
0x180014b86  xor     eax, eax
0x180014b88  retn
0x180014b89  sbb     eax, eax
0x180014b8b  or      eax, 1
0x180014b8e  retn
```
