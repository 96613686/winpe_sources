# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x140002ee0`
- end: `0x140002f2d`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `77`
- prototype: `void __fastcall(unsigned __int8, int, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001b8c`

## callees

- `0x140002ee0`

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
0x140002ee0  mov     r10, r8
0x140002ee3  sub     edx, 3
0x140002ee6  jz      short loc_140002EF3
0x140002ee8  cmp     edx, 1
0x140002eeb  jnz     short locret_140002F2C
0x140002eed  lea     r9d, [rdx+1Fh]
0x140002ef1  jmp     short loc_140002EF9
0x140002ef3  mov     r9d, 10h
0x140002ef9  cmp     byte ptr [r10+1Eh], 0
0x140002efe  mov     r8, [r8]
0x140002f01  jnz     short loc_140002F28
0x140002f03  cmp     byte ptr [r10+1Dh], 0
0x140002f08  jnz     short loc_140002F28
0x140002f0a  mov     eax, [r8]
0x140002f0d  test    al, 2
0x140002f0f  jz      short locret_140002F2C
0x140002f11  mov     edx, eax
0x140002f13  xor     edx, ecx
0x140002f15  test    dl, 1
0x140002f18  jnz     short locret_140002F2C
0x140002f1a  mov     edx, r9d
0x140002f1d  or      edx, eax
0x140002f1f  lock cmpxchg [r8], edx
0x140002f24  jnz     short loc_140002F0D
0x140002f26  retn
0x140002f28  lock or [r8], r9d
0x140002f2c  retn
```
