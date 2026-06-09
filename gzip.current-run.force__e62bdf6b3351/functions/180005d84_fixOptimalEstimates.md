# fixOptimalEstimates

- ea: `0x180005d84`
- end: `0x180005de7`
- name: `fixOptimalEstimates`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002da0`

## callees

- `0x180005d84`

## pseudocode

```c
__int64 __fastcall fixOptimalEstimates(__int64 a1)
{
  __int64 v1; // rdx
  __int64 i; // rax
  __int64 j; // rax
  __int64 result; // rax

  v1 = *(_QWORD *)(a1 + 88);
  for ( i = 0; i != 256; ++i )
  {
    if ( !*(_BYTE *)(i + v1 + 555140) )
      *(_BYTE *)(i + v1 + 555140) = 13;
  }
  for ( j = 257; j != 288; ++j )
  {
    if ( !*(_BYTE *)(j + v1 + 555140) )
      *(_BYTE *)(j + v1 + 555140) = 12;
  }
  for ( result = 0; result != 32; ++result )
  {
    if ( !*(_BYTE *)(v1 + result + 555620) )
      *(_BYTE *)(v1 + result + 555620) = 10;
  }
  return result;
}

```

## disassembly

```asm
0x180005d84  mov     rdx, [rcx+58h]
0x180005d88  xor     ecx, ecx
0x180005d8a  mov     eax, ecx
0x180005d8c  cmp     [rax+rdx+87884h], cl
0x180005d93  jnz     short loc_180005D9D
0x180005d95  mov     byte ptr [rax+rdx+87884h], 0Dh
0x180005d9d  inc     rax
0x180005da0  cmp     rax, 100h
0x180005da6  jnz     short loc_180005D8C
0x180005da8  mov     eax, 101h
0x180005dad  cmp     [rax+rdx+87884h], cl
0x180005db4  jnz     short loc_180005DBE
0x180005db6  mov     byte ptr [rax+rdx+87884h], 0Ch
0x180005dbe  inc     rax
0x180005dc1  cmp     rax, 120h
0x180005dc7  jnz     short loc_180005DAD
0x180005dc9  mov     rax, rcx
0x180005dcc  cmp     [rdx+rax+87A64h], cl
0x180005dd3  jnz     short loc_180005DDD
0x180005dd5  mov     byte ptr [rdx+rax+87A64h], 0Ah
0x180005ddd  inc     rax
0x180005de0  cmp     rax, 20h ; ' '
0x180005de4  jnz     short loc_180005DCC
0x180005de6  retn
```
