# XdrEncodeIntUnsafe

- ea: `0x140011960`
- end: `0x14001197b`
- name: `XdrEncodeIntUnsafe`
- size: `27`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `19`
- callee_count: `1`
- tags: ``

## callers

- `0x1400029d0`
- `0x140004530`
- `0x14000df64`
- `0x14000e4ec`
- `0x14000f274`
- `0x14000fa80`
- `0x14000fb64`
- `0x14000fbc0`
- `0x140010904`
- `0x140011298`
- `0x140011984`
- `0x1400124ec`
- `0x140014d98`
- `0x14001e69c`
- `0x14001ea54`
- `0x14001f178`
- `0x14002a9e0`
- `0x14002b9b8`
- `0x140038e64`

## callees

- `0x140011960`

## pseudocode

```c
__int64 __fastcall XdrEncodeIntUnsafe(__int64 a1, unsigned int a2)
{
  __int64 v2; // rax
  __int64 result; // rax

  v2 = *(_QWORD *)(a1 + 72);
  if ( v2 )
    v2 = *(_QWORD *)(v2 + 64);
  *(_DWORD *)v2 = _byteswap_ulong(a2);
  result = *(_QWORD *)(a1 + 72);
  *(_QWORD *)(result + 64) += 4LL;
  return result;
}

```

## disassembly

```asm
0x140011960  mov     rax, [rcx+48h]
0x140011964  test    rax, rax
0x140011967  jz      short loc_14001196D
0x140011969  mov     rax, [rax+40h]
0x14001196d  bswap   edx
0x14001196f  mov     [rax], edx
0x140011971  mov     rax, [rcx+48h]
0x140011975  add     qword ptr [rax+40h], 4
0x14001197a  retn
```
