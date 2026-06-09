# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x140002cf0`
- end: `0x140002d3d`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `77`
- prototype: `void __fastcall(unsigned __int8, int, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001b8c`

## callees

- `0x140002cf0`

## pseudocode

```c
void __fastcall wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(unsigned __int8 a1, int a2, __int64 a3)
{
  int v4; // edx
  unsigned int v5; // r9d
  volatile signed __int32 *v6; // r8
  signed __int32 v7; // eax
  signed __int32 v8; // ett

  v4 = a2 - 3;
  if ( v4 )
  {
    if ( v4 != 1 )
      return;
    v5 = 32;
  }
  else
  {
    v5 = 16;
  }
  v6 = *(volatile signed __int32 **)a3;
  if ( *(_BYTE *)(a3 + 30) || *(_BYTE *)(a3 + 29) )
  {
    _InterlockedOr(v6, v5);
  }
  else
  {
    v7 = *v6;
    do
    {
      if ( (v7 & 2) == 0 )
        break;
      if ( ((a1 ^ (unsigned __int8)v7) & 1) != 0 )
        break;
      v8 = v7;
      v7 = _InterlockedCompareExchange(v6, v7 | v5, v7);
    }
    while ( v8 != v7 );
  }
}

```

## disassembly

```asm
0x140002cf0  mov     r10, r8
0x140002cf3  sub     edx, 3
0x140002cf6  jz      short loc_140002D03
0x140002cf8  cmp     edx, 1
0x140002cfb  jnz     short locret_140002D3C
0x140002cfd  lea     r9d, [rdx+1Fh]
0x140002d01  jmp     short loc_140002D09
0x140002d03  mov     r9d, 10h
0x140002d09  cmp     byte ptr [r10+1Eh], 0
0x140002d0e  mov     r8, [r8]
0x140002d11  jnz     short loc_140002D38
0x140002d13  cmp     byte ptr [r10+1Dh], 0
0x140002d18  jnz     short loc_140002D38
0x140002d1a  mov     eax, [r8]
0x140002d1d  test    al, 2
0x140002d1f  jz      short locret_140002D3C
0x140002d21  mov     edx, eax
0x140002d23  xor     edx, ecx
0x140002d25  test    dl, 1
0x140002d28  jnz     short locret_140002D3C
0x140002d2a  mov     edx, r9d
0x140002d2d  or      edx, eax
0x140002d2f  lock cmpxchg [r8], edx
0x140002d34  jnz     short loc_140002D1D
0x140002d36  retn
0x140002d38  lock or [r8], r9d
0x140002d3c  retn
```
