# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x18000caa0`
- end: `0x18000cadc`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000cae4`

## callees

- `0x18000caa0`

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
  v4 = *Feature_ShadowAdmin__private_descriptor[0];
  do
  {
    if ( (v4 & 2) == 0 )
      break;
    if ( ((a1 ^ (unsigned __int8)v4) & 1) != 0 )
      break;
    v5 = v4;
    v4 = _InterlockedCompareExchange(Feature_ShadowAdmin__private_descriptor[0], v4 | v3, v4);
  }
  while ( v5 != v4 );
}

```

## disassembly

```asm
0x18000caa0  sub     edx, 3
0x18000caa3  jz      short loc_18000CAB0
0x18000caa5  cmp     edx, 1
0x18000caa8  jnz     short locret_18000CADB
0x18000caaa  lea     r8d, [rdx+1Fh]
0x18000caae  jmp     short loc_18000CAB6
0x18000cab0  mov     r8d, 10h
0x18000cab6  mov     r9, cs:Feature_ShadowAdmin__private_descriptor
0x18000cabd  mov     eax, [r9]
0x18000cac0  jmp     short loc_18000CAD7
0x18000cac2  mov     edx, eax
0x18000cac4  xor     edx, ecx
0x18000cac6  test    dl, 1
0x18000cac9  jnz     short locret_18000CADB
0x18000cacb  mov     edx, r8d
0x18000cace  or      edx, eax
0x18000cad0  lock cmpxchg [r9], edx
0x18000cad5  jz      short locret_18000CADB
0x18000cad7  test    al, 2
0x18000cad9  jnz     short loc_18000CAC2
0x18000cadb  retn
```
