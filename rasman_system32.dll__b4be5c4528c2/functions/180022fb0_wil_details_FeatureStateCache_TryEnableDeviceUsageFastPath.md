# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x180022fb0`
- end: `0x180022ffd`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800231a0`

## callees

- `0x180022fb0`

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
0x180022fb0  mov     r10, r8
0x180022fb3  sub     edx, 3
0x180022fb6  jz      short loc_180022FC3
0x180022fb8  cmp     edx, 1
0x180022fbb  jnz     short locret_180022FFC
0x180022fbd  lea     r9d, [rdx+1Fh]
0x180022fc1  jmp     short loc_180022FC9
0x180022fc3  mov     r9d, 10h
0x180022fc9  cmp     byte ptr [r10+1Eh], 0
0x180022fce  mov     r8, [r8]
0x180022fd1  jnz     short loc_180022FF8
0x180022fd3  cmp     byte ptr [r10+1Dh], 0
0x180022fd8  jnz     short loc_180022FF8
0x180022fda  mov     eax, [r8]
0x180022fdd  test    al, 2
0x180022fdf  jz      short locret_180022FFC
0x180022fe1  mov     edx, eax
0x180022fe3  xor     edx, ecx
0x180022fe5  test    dl, 1
0x180022fe8  jnz     short locret_180022FFC
0x180022fea  mov     edx, r9d
0x180022fed  or      edx, eax
0x180022fef  lock cmpxchg [r8], edx
0x180022ff4  jnz     short loc_180022FDD
0x180022ff6  retn
0x180022ff8  lock or [r8], r9d
0x180022ffc  retn
```
