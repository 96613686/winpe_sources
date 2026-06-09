# NetProtocolType(x)

- ea: `0x1000e350`
- end: `0x1000e377`
- name: `_NetProtocolType@4`
- size: `39`
- prototype: ``
- caller_count: `14`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1000b410`
- `0x1000b470`
- `0x1000b600`
- `0x1000b640`
- `0x1000b6d0`
- `0x1000b860`
- `0x1000bab0`
- `0x1000ed90`
- `0x1000f0e0`
- `0x10010450`
- `0x100108e0`
- `0x10011870`
- `0x10011d90`
- `0x1001f320`

## callees

- `0x1000e350`
- `0x1000e900`

## pseudocode

```c
int __stdcall NetProtocolType(int a1)
{
  int v1; // ecx
  int result; // eax

  v1 = ProtocolPrefix(a1);
  if ( !v1 )
    return 1;
  result = 0;
  if ( v1 == 1 )
    return 2;
  return result;
}

```

## disassembly

```asm
0x1000e350  push    [esp+arg_0]
0x1000e354  call    _ProtocolPrefix@4; ProtocolPrefix(x)
0x1000e359  mov     ecx, eax
0x1000e35b  test    ecx, ecx
0x1000e35d  jnz     short loc_1000E367
0x1000e35f  mov     eax, 1
0x1000e364  retn    4
0x1000e367  xor     eax, eax
0x1000e369  mov     edx, 2
0x1000e36e  cmp     ecx, 1
0x1000e371  cmovz   eax, edx
0x1000e374  retn    4
```
