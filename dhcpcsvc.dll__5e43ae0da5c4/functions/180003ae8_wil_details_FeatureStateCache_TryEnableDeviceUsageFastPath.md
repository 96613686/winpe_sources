# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x180003ae8`
- end: `0x180003b34`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `76`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003530`

## callees

- `0x180003ae8`

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
0x180003ae8  mov     r10, r8
0x180003aeb  sub     edx, 3
0x180003aee  jz      short loc_180003AFB
0x180003af0  cmp     edx, 1
0x180003af3  jnz     short locret_180003B33
0x180003af5  lea     r9d, [rdx+1Fh]
0x180003af9  jmp     short loc_180003B01
0x180003afb  mov     r9d, 10h
0x180003b01  cmp     byte ptr [r10+1Eh], 0
0x180003b06  mov     r8, [r8]
0x180003b09  jnz     short loc_180003B2F
0x180003b0b  cmp     byte ptr [r10+1Dh], 0
0x180003b10  jnz     short loc_180003B2F
0x180003b12  mov     eax, [r8]
0x180003b15  test    al, 2
0x180003b17  jz      short locret_180003B33
0x180003b19  mov     edx, eax
0x180003b1b  xor     edx, ecx
0x180003b1d  test    dl, 1
0x180003b20  jnz     short locret_180003B33
0x180003b22  mov     edx, r9d
0x180003b25  or      edx, eax
0x180003b27  lock cmpxchg [r8], edx
0x180003b2c  jnz     short loc_180003B15
0x180003b2e  retn
0x180003b2f  lock or [r8], r9d
0x180003b33  retn
```
