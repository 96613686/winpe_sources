# HvStatspClientBufferLookupUserInstance

- ea: `0x140010130`
- end: `0x140010168`
- name: `HvStatspClientBufferLookupUserInstance`
- size: `56`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000e0b0`
- `0x1400101d0`

## callees

- `0x140010130`

## pseudocode

```c
_QWORD *__fastcall HvStatspClientBufferLookupUserInstance(_QWORD *a1, __int64 a2)
{
  _QWORD *result; // rax
  _QWORD *v4; // rdx
  _QWORD *v5; // rcx

  result = 0;
  if ( a2 )
  {
    v4 = a1 + 5;
    v5 = (_QWORD *)a1[5];
    while ( v5 != v4 )
    {
      result = v5 - 1;
      if ( *(v5 - 1) == a2 )
        break;
      v5 = (_QWORD *)*v5;
      result = 0;
    }
  }
  else if ( a1[3] || a1[4] )
  {
    return a1;
  }
  return result;
}

```

## disassembly

```asm
0x140010130  xor     eax, eax
0x140010132  mov     r8, rdx
0x140010135  test    rdx, rdx
0x140010138  jnz     short loc_14001014B
0x14001013a  cmp     [rcx+18h], rax
0x14001013e  jnz     short loc_140010146
0x140010140  cmp     [rcx+20h], rax
0x140010144  jz      short locret_140010167
0x140010146  mov     rax, rcx
0x140010149  retn
0x14001014b  lea     rdx, [rcx+28h]
0x14001014f  mov     rcx, [rdx]
0x140010152  jmp     short loc_140010162
0x140010154  lea     rax, [rcx-8]
0x140010158  cmp     [rax], r8
0x14001015b  jz      short locret_140010167
0x14001015d  mov     rcx, [rcx]
0x140010160  xor     eax, eax
0x140010162  cmp     rcx, rdx
0x140010165  jnz     short loc_140010154
0x140010167  retn
```
