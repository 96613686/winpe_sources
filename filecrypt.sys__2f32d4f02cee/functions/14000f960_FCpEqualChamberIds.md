# FCpEqualChamberIds

- ea: `0x14000f960`
- end: `0x14000f992`
- name: `FCpEqualChamberIds`
- size: `50`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000f2f0`
- `0x1400101c0`

## callees

- `0x14000f960`

## pseudocode

```c
bool __fastcall FCpEqualChamberIds(unsigned __int16 *a1, unsigned __int16 *a2)
{
  signed __int64 v2; // r8
  int v3; // eax
  int v4; // edx

  if ( !a1 || !a2 )
    return a1 == a2;
  v2 = (char *)a2 - (char *)a1;
  do
  {
    v3 = *(unsigned __int16 *)((char *)a1 + v2);
    v4 = *a1 - v3;
    if ( v4 )
      break;
    ++a1;
  }
  while ( v3 );
  return v4 == 0;
}

```

## disassembly

```asm
0x14000f960  mov     r8, rdx
0x14000f963  test    rcx, rcx
0x14000f966  jz      short loc_14000F98B
0x14000f968  test    rdx, rdx
0x14000f96b  jz      short loc_14000F98B
0x14000f96d  sub     r8, rcx
0x14000f970  movzx   edx, word ptr [rcx]
0x14000f973  movzx   eax, word ptr [rcx+r8]
0x14000f978  sub     edx, eax
0x14000f97a  jnz     short loc_14000F984
0x14000f97c  add     rcx, 2
0x14000f980  test    eax, eax
0x14000f982  jnz     short loc_14000F970
0x14000f984  test    edx, edx
0x14000f986  setz    al
0x14000f989  retn
0x14000f98b  cmp     rcx, r8
0x14000f98e  setz    al
0x14000f991  retn
```
