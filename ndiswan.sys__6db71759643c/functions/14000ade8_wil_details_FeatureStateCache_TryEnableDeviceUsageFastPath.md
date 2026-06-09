# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x14000ade8`
- end: `0x14000ae35`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140008530`

## callees

- `0x14000ade8`

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
0x14000ade8  mov     r10, r8
0x14000adeb  sub     edx, 3
0x14000adee  jz      short loc_14000ADFB
0x14000adf0  cmp     edx, 1
0x14000adf3  jnz     short locret_14000AE34
0x14000adf5  lea     r9d, [rdx+1Fh]
0x14000adf9  jmp     short loc_14000AE01
0x14000adfb  mov     r9d, 10h
0x14000ae01  cmp     byte ptr [r10+1Eh], 0
0x14000ae06  mov     r8, [r8]
0x14000ae09  jnz     short loc_14000AE30
0x14000ae0b  cmp     byte ptr [r10+1Dh], 0
0x14000ae10  jnz     short loc_14000AE30
0x14000ae12  mov     eax, [r8]
0x14000ae15  test    al, 2
0x14000ae17  jz      short locret_14000AE34
0x14000ae19  mov     edx, eax
0x14000ae1b  xor     edx, ecx
0x14000ae1d  test    dl, 1
0x14000ae20  jnz     short locret_14000AE34
0x14000ae22  mov     edx, r9d
0x14000ae25  or      edx, eax
0x14000ae27  lock cmpxchg [r8], edx
0x14000ae2c  jnz     short loc_14000AE15
0x14000ae2e  retn
0x14000ae30  lock or [r8], r9d
0x14000ae34  retn
```
