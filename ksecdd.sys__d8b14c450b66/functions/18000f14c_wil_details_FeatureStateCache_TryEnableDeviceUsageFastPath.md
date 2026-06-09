# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x18000f14c`
- end: `0x18000f188`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `60`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000f2e0`

## callees

- `0x18000f14c`

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
  v4 = *Feature_Schannel_SslCopyTlsExtensions__private_descriptor[0];
  do
  {
    if ( (v4 & 2) == 0 )
      break;
    if ( ((a1 ^ (unsigned __int8)v4) & 1) != 0 )
      break;
    v5 = v4;
    v4 = _InterlockedCompareExchange(Feature_Schannel_SslCopyTlsExtensions__private_descriptor[0], v4 | v3, v4);
  }
  while ( v5 != v4 );
}

```

## disassembly

```asm
0x18000f14c  sub     edx, 3
0x18000f14f  jz      short loc_18000F15C
0x18000f151  cmp     edx, 1
0x18000f154  jnz     short locret_18000F187
0x18000f156  lea     r8d, [rdx+1Fh]
0x18000f15a  jmp     short loc_18000F162
0x18000f15c  mov     r8d, 10h
0x18000f162  mov     r9, cs:Feature_Schannel_SslCopyTlsExtensions__private_descriptor
0x18000f169  mov     eax, [r9]
0x18000f16c  jmp     short loc_18000F183
0x18000f16e  mov     edx, eax
0x18000f170  xor     edx, ecx
0x18000f172  test    dl, 1
0x18000f175  jnz     short locret_18000F187
0x18000f177  mov     edx, r8d
0x18000f17a  or      edx, eax
0x18000f17c  lock cmpxchg [r9], edx
0x18000f181  jz      short locret_18000F187
0x18000f183  test    al, 2
0x18000f185  jnz     short loc_18000F16E
0x18000f187  retn
```
