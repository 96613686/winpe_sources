# __std_type_info_compare

- ea: `0x180002c8c`
- end: `0x180002cb3`
- name: `__std_type_info_compare`
- size: `39`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004ba8`

## callees

- `0x180002c8c`

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
0x180002c8c  cmp     rcx, rdx
0x180002c8f  jz      short loc_180002CAA
0x180002c91  add     rdx, 9
0x180002c95  lea     rax, [rcx+9]
0x180002c99  sub     rdx, rax
0x180002c9c  mov     cl, [rax]
0x180002c9e  cmp     cl, [rax+rdx]
0x180002ca1  jnz     short loc_180002CAD
0x180002ca3  inc     rax
0x180002ca6  test    cl, cl
0x180002ca8  jnz     short loc_180002C9C
0x180002caa  xor     eax, eax
0x180002cac  retn
0x180002cad  sbb     eax, eax
0x180002caf  or      eax, 1
0x180002cb2  retn
```
