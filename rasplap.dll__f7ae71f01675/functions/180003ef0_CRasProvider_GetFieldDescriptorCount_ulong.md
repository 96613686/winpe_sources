# CRasProvider::GetFieldDescriptorCount(ulong *)

- ea: `0x180003ef0`
- end: `0x180003f04`
- name: `?GetFieldDescriptorCount@CRasProvider@@UEAAJPEAK@Z`
- size: `20`
- prototype: `__int64 __fastcall(CRasProvider *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003ef0`

## pseudocode

```c
__int64 __fastcall CRasProvider::GetFieldDescriptorCount(CRasProvider *this, unsigned int *a2)
{
  if ( !a2 )
    return 2147942487LL;
  *a2 = 12;
  return 0;
}

```

## disassembly

```asm
0x180003ef0  test    rdx, rdx
0x180003ef3  jnz     short loc_180003EFB
0x180003ef5  mov     eax, 80070057h
0x180003efa  retn
0x180003efb  mov     dword ptr [rdx], 0Ch
0x180003f01  xor     eax, eax
0x180003f03  retn
```
