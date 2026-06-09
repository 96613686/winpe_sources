# __std_type_info_compare

- ea: `0x18001ae98`
- end: `0x18001aebf`
- name: `__std_type_info_compare`
- size: `39`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001ac10`

## callees

- `0x18001ae98`

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
0x18001ae98  cmp     rcx, rdx
0x18001ae9b  jz      short loc_18001AEB6
0x18001ae9d  add     rdx, 9
0x18001aea1  lea     rax, [rcx+9]
0x18001aea5  sub     rdx, rax
0x18001aea8  mov     cl, [rax]
0x18001aeaa  cmp     cl, [rax+rdx]
0x18001aead  jnz     short loc_18001AEB9
0x18001aeaf  inc     rax
0x18001aeb2  test    cl, cl
0x18001aeb4  jnz     short loc_18001AEA8
0x18001aeb6  xor     eax, eax
0x18001aeb8  retn
0x18001aeb9  sbb     eax, eax
0x18001aebb  or      eax, 1
0x18001aebe  retn
```
