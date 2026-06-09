# NetProtocolType(x)

- ea: `0x10022871`
- end: `0x1002288a`
- name: `_NetProtocolType@4`
- size: `25`
- prototype: `int __thiscall(_DWORD)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x10026676`
- `0x10026772`
- `0x100268a0`
- `0x100268d8`
- `0x10026c60`
- `0x100278d3`

## callees

- `0x10022838`
- `0x10022871`

## pseudocode

```c
int __thiscall NetProtocolType(void *this)
{
  int v1; // ecx
  int result; // eax

  v1 = ProtocolPrefix(this);
  result = 0;
  if ( !v1 )
    return 1;
  if ( v1 == 1 )
    return 2;
  return result;
}

```

## disassembly

```asm
0x10022871  call    _ProtocolPrefix@4; ProtocolPrefix(x)
0x10022876  mov     ecx, eax
0x10022878  xor     eax, eax
0x1002287a  test    ecx, ecx
0x1002287c  jnz     short loc_10022880
0x1002287e  inc     eax
0x1002287f  retn
0x10022880  push    2
0x10022882  cmp     ecx, 1
0x10022885  pop     edx
0x10022886  cmovz   eax, edx
0x10022889  retn
```
