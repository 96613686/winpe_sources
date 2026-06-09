# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x18001e060`
- end: `0x18001e0ad`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `77`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001b79c`
- `0x180024c44`

## callees

- `0x18001e060`

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
0x18001e060  mov     r10, r8
0x18001e063  sub     edx, 3
0x18001e066  jz      short loc_18001E073
0x18001e068  cmp     edx, 1
0x18001e06b  jnz     short locret_18001E0AC
0x18001e06d  lea     r9d, [rdx+1Fh]
0x18001e071  jmp     short loc_18001E079
0x18001e073  mov     r9d, 10h
0x18001e079  cmp     byte ptr [r10+1Eh], 0
0x18001e07e  mov     r8, [r8]
0x18001e081  jnz     short loc_18001E0A8
0x18001e083  cmp     byte ptr [r10+1Dh], 0
0x18001e088  jnz     short loc_18001E0A8
0x18001e08a  mov     eax, [r8]
0x18001e08d  test    al, 2
0x18001e08f  jz      short locret_18001E0AC
0x18001e091  mov     edx, eax
0x18001e093  xor     edx, ecx
0x18001e095  test    dl, 1
0x18001e098  jnz     short locret_18001E0AC
0x18001e09a  mov     edx, r9d
0x18001e09d  or      edx, eax
0x18001e09f  lock cmpxchg [r8], edx
0x18001e0a4  jnz     short loc_18001E08D
0x18001e0a6  retn
0x18001e0a8  lock or [r8], r9d
0x18001e0ac  retn
```
