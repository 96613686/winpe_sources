# ASN1EncSetError

- ea: `0x180007ed0`
- end: `0x180007eec`
- name: `ASN1EncSetError`
- size: `28`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x1800066a0`
- `0x180006850`
- `0x180006c50`
- `0x180006df0`
- `0x180006f30`
- `0x180007380`
- `0x1800074e0`
- `0x1800075e0`
- `0x18000a070`
- `0x18000a8a0`

## callees

- `0x180007ed0`

## pseudocode

```c
__int64 __fastcall ASN1EncSetError(__int64 a1, unsigned int a2)
{
  __int64 v2; // rax

  if ( a1 )
  {
    do
    {
      v2 = *(_QWORD *)(a1 + 64);
      *(_DWORD *)(a1 + 32) = a2;
      if ( a1 == v2 )
        break;
      a1 = v2;
    }
    while ( v2 );
  }
  return a2;
}

```

## disassembly

```asm
0x180007ed0  test    rcx, rcx
0x180007ed3  jz      short loc_180007EE9
0x180007ed5  mov     rax, [rcx+40h]
0x180007ed9  mov     [rcx+20h], edx
0x180007edc  cmp     rcx, rax
0x180007edf  jz      short loc_180007EE9
0x180007ee1  mov     rcx, rax
0x180007ee4  test    rax, rax
0x180007ee7  jnz     short loc_180007ED5
0x180007ee9  mov     eax, edx
0x180007eeb  retn
```
