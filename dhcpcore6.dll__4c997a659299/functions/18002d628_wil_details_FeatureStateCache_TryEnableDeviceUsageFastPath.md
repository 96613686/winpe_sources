# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x18002d628`
- end: `0x18002d675`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `77`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002d67c`

## callees

- `0x18002d628`

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
0x18002d628  mov     r10, r8
0x18002d62b  sub     edx, 3
0x18002d62e  jz      short loc_18002D63B
0x18002d630  cmp     edx, 1
0x18002d633  jnz     short locret_18002D674
0x18002d635  lea     r9d, [rdx+1Fh]
0x18002d639  jmp     short loc_18002D641
0x18002d63b  mov     r9d, 10h
0x18002d641  cmp     byte ptr [r10+1Eh], 0
0x18002d646  mov     r8, [r8]
0x18002d649  jnz     short loc_18002D670
0x18002d64b  cmp     byte ptr [r10+1Dh], 0
0x18002d650  jnz     short loc_18002D670
0x18002d652  mov     eax, [r8]
0x18002d655  test    al, 2
0x18002d657  jz      short locret_18002D674
0x18002d659  mov     edx, eax
0x18002d65b  xor     edx, ecx
0x18002d65d  test    dl, 1
0x18002d660  jnz     short locret_18002D674
0x18002d662  mov     edx, r9d
0x18002d665  or      edx, eax
0x18002d667  lock cmpxchg [r8], edx
0x18002d66c  jnz     short loc_18002D655
0x18002d66e  retn
0x18002d670  lock or [r8], r9d
0x18002d674  retn
```
