# SslpValidateEphemeralHandle

- ea: `0x1800066f0`
- end: `0x18000670b`
- name: `SslpValidateEphemeralHandle`
- size: `27`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180006070`
- `0x180011f10`
- `0x180013c6c`
- `0x180013f08`
- `0x180022ca4`
- `0x1800237a0`
- `0x18002396c`

## callees

- `0x1800066f0`

## pseudocode

```c
_DWORD *__fastcall SslpValidateEphemeralHandle(_DWORD *a1)
{
  _DWORD *result; // rax

  if ( !a1 || *a1 < 0x28u )
    return 0;
  result = 0;
  if ( a1[1] == 1936944182 )
    return a1;
  return result;
}

```

## disassembly

```asm
0x1800066f0  test    rcx, rcx
0x1800066f3  jz      short loc_180006708
0x1800066f5  cmp     dword ptr [rcx], 28h ; '('
0x1800066f8  jb      short loc_180006708
0x1800066fa  xor     eax, eax
0x1800066fc  cmp     dword ptr [rcx+4], 73736C36h
0x180006703  cmovz   rax, rcx
0x180006707  retn
0x180006708  xor     eax, eax
0x18000670a  retn
```
