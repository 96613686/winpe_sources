# SslpValidateMasterKeyHandle

- ea: `0x180007960`
- end: `0x18000797b`
- name: `SslpValidateMasterKeyHandle`
- size: `27`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180005ec0`
- `0x18000e320`
- `0x1800133f0`
- `0x18001e5c0`
- `0x18001edb0`

## callees

- `0x180007960`

## pseudocode

```c
_DWORD *__fastcall SslpValidateMasterKeyHandle(_DWORD *a1)
{
  _DWORD *result; // rax

  if ( !a1 || *a1 < 0x50u )
    return 0;
  result = 0;
  if ( a1[1] == 1936944181 )
    return a1;
  return result;
}

```

## disassembly

```asm
0x180007960  test    rcx, rcx
0x180007963  jz      short loc_180007978
0x180007965  cmp     dword ptr [rcx], 50h ; 'P'
0x180007968  jb      short loc_180007978
0x18000796a  xor     eax, eax
0x18000796c  cmp     dword ptr [rcx+4], 73736C35h
0x180007973  cmovz   rax, rcx
0x180007977  retn
0x180007978  xor     eax, eax
0x18000797a  retn
```
