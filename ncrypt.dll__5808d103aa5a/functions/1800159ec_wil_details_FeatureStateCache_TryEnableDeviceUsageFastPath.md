# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x1800159ec`
- end: `0x180015a37`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `75`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180012e00`
- `0x180015e8c`
- `0x1800164ac`
- `0x180019980`
- `0x18001c3a0`

## callees

- `0x1800159ec`

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
0x1800159ec  mov     r10, r8
0x1800159ef  sub     edx, 3
0x1800159f2  jnz     short loc_180015A16
0x1800159f4  lea     r9d, [rdx+10h]
0x1800159f8  cmp     byte ptr [r10+1Eh], 0
0x1800159fd  mov     r8, [r8]
0x180015a00  jnz     short loc_180015A11
0x180015a02  cmp     byte ptr [r10+1Dh], 0
0x180015a07  jnz     short loc_180015A11
0x180015a09  mov     eax, [r8]
0x180015a0c  test    al, 2
0x180015a0e  jnz     short loc_180015A21
0x180015a10  retn
0x180015a11  lock or [r8], r9d
0x180015a15  retn
0x180015a16  cmp     edx, 1
0x180015a19  jnz     short locret_180015A10
0x180015a1b  lea     r9d, [rdx+1Fh]
0x180015a1f  jmp     short loc_1800159F8
0x180015a21  mov     edx, eax
0x180015a23  xor     edx, ecx
0x180015a25  test    dl, 1
0x180015a28  jnz     short locret_180015A10
0x180015a2a  mov     edx, r9d
0x180015a2d  or      edx, eax
0x180015a2f  lock cmpxchg [r8], edx
0x180015a34  jnz     short loc_180015A0C
0x180015a36  retn
```
