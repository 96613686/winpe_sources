# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x180018740`
- end: `0x18001878c`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `76`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800188f0`

## callees

- `0x180018740`

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
0x180018740  mov     r10, r8
0x180018743  sub     edx, 3
0x180018746  jz      short loc_180018753
0x180018748  cmp     edx, 1
0x18001874b  jnz     short locret_18001878B
0x18001874d  lea     r9d, [rdx+1Fh]
0x180018751  jmp     short loc_180018759
0x180018753  mov     r9d, 10h
0x180018759  cmp     byte ptr [r10+1Eh], 0
0x18001875e  mov     r8, [r8]
0x180018761  jnz     short loc_180018787
0x180018763  cmp     byte ptr [r10+1Dh], 0
0x180018768  jnz     short loc_180018787
0x18001876a  mov     eax, [r8]
0x18001876d  test    al, 2
0x18001876f  jz      short locret_18001878B
0x180018771  mov     edx, eax
0x180018773  xor     edx, ecx
0x180018775  test    dl, 1
0x180018778  jnz     short locret_18001878B
0x18001877a  mov     edx, r9d
0x18001877d  or      edx, eax
0x18001877f  lock cmpxchg [r8], edx
0x180018784  jnz     short loc_18001876D
0x180018786  retn
0x180018787  lock or [r8], r9d
0x18001878b  retn
```
