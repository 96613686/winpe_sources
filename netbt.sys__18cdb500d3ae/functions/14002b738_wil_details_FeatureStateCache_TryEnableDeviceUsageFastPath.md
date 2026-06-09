# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x14002b738`
- end: `0x14002b787`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14002b8a8`

## callees

- `0x14002b738`

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
0x14002b738  mov     r10, r8
0x14002b73b  sub     edx, 3
0x14002b73e  jz      short loc_14002B74B
0x14002b740  cmp     edx, 1
0x14002b743  jnz     short locret_14002B786
0x14002b745  lea     r9d, [rdx+1Fh]
0x14002b749  jmp     short loc_14002B751
0x14002b74b  mov     r9d, 10h
0x14002b751  cmp     byte ptr [r10+1Eh], 0
0x14002b756  mov     r8, [r8]
0x14002b759  jnz     short loc_14002B782
0x14002b75b  cmp     byte ptr [r10+1Dh], 0
0x14002b760  jnz     short loc_14002B782
0x14002b762  mov     eax, [r8]
0x14002b765  jmp     short loc_14002B77C
0x14002b767  mov     edx, eax
0x14002b769  xor     edx, ecx
0x14002b76b  test    dl, 1
0x14002b76e  jnz     short locret_14002B786
0x14002b770  mov     edx, r9d
0x14002b773  or      edx, eax
0x14002b775  lock cmpxchg [r8], edx
0x14002b77a  jz      short locret_14002B786
0x14002b77c  test    al, 2
0x14002b77e  jnz     short loc_14002B767
0x14002b780  retn
0x14002b782  lock or [r8], r9d
0x14002b786  retn
```
