# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x140029b7c`
- end: `0x140029bc9`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `77`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001c088`
- `0x140032734`

## callees

- `0x140029b7c`

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
0x140029b7c  mov     r10, r8
0x140029b7f  sub     edx, 3
0x140029b82  jz      short loc_140029B8F
0x140029b84  cmp     edx, 1
0x140029b87  jnz     short locret_140029BC8
0x140029b89  lea     r9d, [rdx+1Fh]
0x140029b8d  jmp     short loc_140029B95
0x140029b8f  mov     r9d, 10h
0x140029b95  cmp     byte ptr [r10+1Eh], 0
0x140029b9a  mov     r8, [r8]
0x140029b9d  jnz     short loc_140029BC4
0x140029b9f  cmp     byte ptr [r10+1Dh], 0
0x140029ba4  jnz     short loc_140029BC4
0x140029ba6  mov     eax, [r8]
0x140029ba9  test    al, 2
0x140029bab  jz      short locret_140029BC8
0x140029bad  mov     edx, eax
0x140029baf  xor     edx, ecx
0x140029bb1  test    dl, 1
0x140029bb4  jnz     short locret_140029BC8
0x140029bb6  mov     edx, r9d
0x140029bb9  or      edx, eax
0x140029bbb  lock cmpxchg [r8], edx
0x140029bc0  jnz     short loc_140029BA9
0x140029bc2  retn
0x140029bc4  lock or [r8], r9d
0x140029bc8  retn
```
