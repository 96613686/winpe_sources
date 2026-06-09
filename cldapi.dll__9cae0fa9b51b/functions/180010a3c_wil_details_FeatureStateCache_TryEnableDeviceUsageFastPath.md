# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x180010a3c`
- end: `0x180010a78`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180010cb4`

## callees

- `0x180010a3c`

## pseudocode

```c
void __fastcall wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(unsigned __int8 a1, int a2)
{
  int v2; // edx
  int v3; // r8d
  signed __int32 v4; // eax
  signed __int32 v5; // ett

  v2 = a2 - 3;
  if ( v2 )
  {
    if ( v2 != 1 )
      return;
    v3 = 32;
  }
  else
  {
    v3 = 16;
  }
  v4 = *Feature_57207774__private_descriptor[0];
  do
  {
    if ( (v4 & 2) == 0 )
      break;
    if ( ((a1 ^ (unsigned __int8)v4) & 1) != 0 )
      break;
    v5 = v4;
    v4 = _InterlockedCompareExchange(Feature_57207774__private_descriptor[0], v4 | v3, v4);
  }
  while ( v5 != v4 );
}

```

## disassembly

```asm
0x180010a3c  sub     edx, 3
0x180010a3f  jz      short loc_180010A4C
0x180010a41  cmp     edx, 1
0x180010a44  jnz     short locret_180010A77
0x180010a46  lea     r8d, [rdx+1Fh]
0x180010a4a  jmp     short loc_180010A52
0x180010a4c  mov     r8d, 10h
0x180010a52  mov     r9, cs:Feature_57207774__private_descriptor
0x180010a59  mov     eax, [r9]
0x180010a5c  jmp     short loc_180010A73
0x180010a5e  mov     edx, eax
0x180010a60  xor     edx, ecx
0x180010a62  test    dl, 1
0x180010a65  jnz     short locret_180010A77
0x180010a67  mov     edx, r8d
0x180010a6a  or      edx, eax
0x180010a6c  lock cmpxchg [r9], edx
0x180010a71  jz      short locret_180010A77
0x180010a73  test    al, 2
0x180010a75  jnz     short loc_180010A5E
0x180010a77  retn
```
