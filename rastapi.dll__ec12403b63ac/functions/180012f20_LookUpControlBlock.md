# LookUpControlBlock

- ea: `0x180012f20`
- end: `0x180012f5e`
- name: `LookUpControlBlock`
- size: `62`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f810`
- `0x18000fee0`
- `0x18000ff60`
- `0x1800101d0`
- `0x1800102b0`
- `0x180010330`
- `0x1800146e0`
- `0x1800148c0`

## callees

- `0x180012f20`

## pseudocode

```c
_QWORD *__fastcall LookUpControlBlock(_DWORD *a1)
{
  _QWORD *result; // rax
  _QWORD *v2; // rdx

  result = RasPortsList;
  v2 = RasPortsList;
  if ( !RasPortsList )
    return 0;
  do
  {
    if ( v2 == (_QWORD *)a1 && *a1 == 100997426 )
      return a1;
    v2 = (_QWORD *)v2[1];
  }
  while ( v2 );
  while ( (_DWORD *)result[111] != a1 )
  {
    result = (_QWORD *)result[1];
    if ( !result )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180012f20  mov     rax, cs:RasPortsList
0x180012f27  mov     rdx, rax
0x180012f2a  test    rax, rax
0x180012f2d  jz      short loc_180012F57
0x180012f2f  cmp     rdx, rcx
0x180012f32  jnz     short loc_180012F3C
0x180012f34  cmp     dword ptr [rcx], 6051932h
0x180012f3a  jz      short loc_180012F5A
0x180012f3c  mov     rdx, [rdx+8]
0x180012f40  test    rdx, rdx
0x180012f43  jnz     short loc_180012F2F
0x180012f45  cmp     [rax+378h], rcx
0x180012f4c  jz      short locret_180012F59
0x180012f4e  mov     rax, [rax+8]
0x180012f52  test    rax, rax
0x180012f55  jnz     short loc_180012F45
0x180012f57  xor     eax, eax
0x180012f59  retn
0x180012f5a  mov     rax, rcx
0x180012f5d  retn
```
