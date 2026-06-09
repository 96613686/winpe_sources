# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x180014ba8`
- end: `0x180014bf6`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `78`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180014e48`

## callees

- `0x180014ba8`

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
0x180014ba8  mov     r10, r8
0x180014bab  sub     edx, 3
0x180014bae  jz      short loc_180014BBB
0x180014bb0  cmp     edx, 1
0x180014bb3  jnz     short locret_180014BF5
0x180014bb5  lea     r9d, [rdx+1Fh]
0x180014bb9  jmp     short loc_180014BC1
0x180014bbb  mov     r9d, 10h
0x180014bc1  cmp     byte ptr [r10+1Eh], 0
0x180014bc6  mov     r8, [r8]
0x180014bc9  jnz     short loc_180014BF1
0x180014bcb  cmp     byte ptr [r10+1Dh], 0
0x180014bd0  jnz     short loc_180014BF1
0x180014bd2  mov     eax, [r8]
0x180014bd5  jmp     short loc_180014BEC
0x180014bd7  mov     edx, eax
0x180014bd9  xor     edx, ecx
0x180014bdb  test    dl, 1
0x180014bde  jnz     short locret_180014BF5
0x180014be0  mov     edx, r9d
0x180014be3  or      edx, eax
0x180014be5  lock cmpxchg [r8], edx
0x180014bea  jz      short locret_180014BF5
0x180014bec  test    al, 2
0x180014bee  jnz     short loc_180014BD7
0x180014bf0  retn
0x180014bf1  lock or [r8], r9d
0x180014bf5  retn
```
