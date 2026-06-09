# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x180007264`
- end: `0x1800072b0`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `76`
- prototype: `void __fastcall(unsigned __int8, int, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800026e0`

## callees

- `0x180007264`

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
0x180007264  mov     r10, r8
0x180007267  sub     edx, 3
0x18000726a  jz      short loc_180007277
0x18000726c  cmp     edx, 1
0x18000726f  jnz     short locret_1800072AF
0x180007271  lea     r9d, [rdx+1Fh]
0x180007275  jmp     short loc_18000727D
0x180007277  mov     r9d, 10h
0x18000727d  cmp     byte ptr [r10+1Eh], 0
0x180007282  mov     r8, [r8]
0x180007285  jnz     short loc_1800072AB
0x180007287  cmp     byte ptr [r10+1Dh], 0
0x18000728c  jnz     short loc_1800072AB
0x18000728e  mov     eax, [r8]
0x180007291  test    al, 2
0x180007293  jz      short locret_1800072AF
0x180007295  mov     edx, eax
0x180007297  xor     edx, ecx
0x180007299  test    dl, 1
0x18000729c  jnz     short locret_1800072AF
0x18000729e  mov     edx, r9d
0x1800072a1  or      edx, eax
0x1800072a3  lock cmpxchg [r8], edx
0x1800072a8  jnz     short loc_180007291
0x1800072aa  retn
0x1800072ab  lock or [r8], r9d
0x1800072af  retn
```
