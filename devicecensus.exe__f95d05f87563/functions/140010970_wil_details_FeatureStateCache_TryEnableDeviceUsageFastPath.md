# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x140010970`
- end: `0x1400109be`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `78`
- prototype: `void __fastcall(unsigned __int8, int, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140010c10`

## callees

- `0x140010970`

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
0x140010970  mov     r10, r8
0x140010973  sub     edx, 3
0x140010976  jz      short loc_140010983
0x140010978  cmp     edx, 1
0x14001097b  jnz     short locret_1400109BD
0x14001097d  lea     r9d, [rdx+1Fh]
0x140010981  jmp     short loc_140010989
0x140010983  mov     r9d, 10h
0x140010989  cmp     byte ptr [r10+1Eh], 0
0x14001098e  mov     r8, [r8]
0x140010991  jnz     short loc_1400109B9
0x140010993  cmp     byte ptr [r10+1Dh], 0
0x140010998  jnz     short loc_1400109B9
0x14001099a  mov     eax, [r8]
0x14001099d  jmp     short loc_1400109B4
0x14001099f  mov     edx, eax
0x1400109a1  xor     edx, ecx
0x1400109a3  test    dl, 1
0x1400109a6  jnz     short locret_1400109BD
0x1400109a8  mov     edx, r9d
0x1400109ab  or      edx, eax
0x1400109ad  lock cmpxchg [r8], edx
0x1400109b2  jz      short locret_1400109BD
0x1400109b4  test    al, 2
0x1400109b6  jnz     short loc_14001099F
0x1400109b8  retn
0x1400109b9  lock or [r8], r9d
0x1400109bd  retn
```
