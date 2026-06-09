# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x140002a6c`
- end: `0x140002abb`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `79`
- prototype: `void __fastcall(unsigned __int8, int, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140002ac4`

## callees

- `0x140002a6c`

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
0x140002a6c  mov     r10, r8
0x140002a6f  sub     edx, 3
0x140002a72  jz      short loc_140002A7F
0x140002a74  cmp     edx, 1
0x140002a77  jnz     short locret_140002ABA
0x140002a79  lea     r9d, [rdx+1Fh]
0x140002a7d  jmp     short loc_140002A85
0x140002a7f  mov     r9d, 10h
0x140002a85  cmp     byte ptr [r10+1Eh], 0
0x140002a8a  mov     r8, [r8]
0x140002a8d  jnz     short loc_140002AB6
0x140002a8f  cmp     byte ptr [r10+1Dh], 0
0x140002a94  jnz     short loc_140002AB6
0x140002a96  mov     eax, [r8]
0x140002a99  jmp     short loc_140002AB0
0x140002a9b  mov     edx, eax
0x140002a9d  xor     edx, ecx
0x140002a9f  test    dl, 1
0x140002aa2  jnz     short locret_140002ABA
0x140002aa4  mov     edx, r9d
0x140002aa7  or      edx, eax
0x140002aa9  lock cmpxchg [r8], edx
0x140002aae  jz      short locret_140002ABA
0x140002ab0  test    al, 2
0x140002ab2  jnz     short loc_140002A9B
0x140002ab4  retn
0x140002ab6  lock or [r8], r9d
0x140002aba  retn
```
