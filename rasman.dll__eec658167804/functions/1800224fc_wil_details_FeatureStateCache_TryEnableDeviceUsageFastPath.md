# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x1800224fc`
- end: `0x180022548`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `76`
- prototype: `void __fastcall(unsigned __int8, int, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800226a8`

## callees

- `0x1800224fc`

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
0x1800224fc  mov     r10, r8
0x1800224ff  sub     edx, 3
0x180022502  jz      short loc_18002250F
0x180022504  cmp     edx, 1
0x180022507  jnz     short locret_180022547
0x180022509  lea     r9d, [rdx+1Fh]
0x18002250d  jmp     short loc_180022515
0x18002250f  mov     r9d, 10h
0x180022515  cmp     byte ptr [r10+1Eh], 0
0x18002251a  mov     r8, [r8]
0x18002251d  jnz     short loc_180022543
0x18002251f  cmp     byte ptr [r10+1Dh], 0
0x180022524  jnz     short loc_180022543
0x180022526  mov     eax, [r8]
0x180022529  test    al, 2
0x18002252b  jz      short locret_180022547
0x18002252d  mov     edx, eax
0x18002252f  xor     edx, ecx
0x180022531  test    dl, 1
0x180022534  jnz     short locret_180022547
0x180022536  mov     edx, r9d
0x180022539  or      edx, eax
0x18002253b  lock cmpxchg [r8], edx
0x180022540  jnz     short loc_180022529
0x180022542  retn
0x180022543  lock or [r8], r9d
0x180022547  retn
```
