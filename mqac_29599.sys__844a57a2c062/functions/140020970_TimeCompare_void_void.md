# TimeCompare(void *,void *)

- ea: `0x140020970`
- end: `0x140020990`
- name: `?TimeCompare@@YAHPEAX0@Z`
- size: `32`
- prototype: `__int64 __fastcall(void *, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140020970`

## pseudocode

```c
__int64 __fastcall TimeCompare(_QWORD *a1, _QWORD *a2)
{
  __int64 v2; // rdx

  v2 = *a1 - *a2;
  if ( v2 <= 0 )
    return (unsigned int)(v2 >= 0) - 1;
  else
    return 1;
}

```

## disassembly

```asm
0x140020970  mov     rax, [rdx]
0x140020973  mov     rdx, [rcx]
0x140020976  sub     rdx, rax
0x140020979  test    rdx, rdx
0x14002097c  jle     short loc_140020985
0x14002097e  mov     eax, 1
0x140020983  retn
0x140020985  xor     eax, eax
0x140020987  test    rdx, rdx
0x14002098a  setns   al
0x14002098d  dec     eax
0x14002098f  retn
```
