# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x18000f1ec`
- end: `0x18000f228`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000f348`

## callees

- `0x18000f1ec`

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
0x18000f1ec  sub     edx, 3
0x18000f1ef  jz      short loc_18000F1FC
0x18000f1f1  cmp     edx, 1
0x18000f1f4  jnz     short locret_18000F227
0x18000f1f6  lea     r8d, [rdx+1Fh]
0x18000f1fa  jmp     short loc_18000F202
0x18000f1fc  mov     r8d, 10h
0x18000f202  mov     r9, cs:Feature_Schannel_SslCopyTlsExtensions__private_descriptor
0x18000f209  mov     eax, [r9]
0x18000f20c  jmp     short loc_18000F223
0x18000f20e  mov     edx, eax
0x18000f210  xor     edx, ecx
0x18000f212  test    dl, 1
0x18000f215  jnz     short locret_18000F227
0x18000f217  mov     edx, r8d
0x18000f21a  or      edx, eax
0x18000f21c  lock cmpxchg [r9], edx
0x18000f221  jz      short locret_18000F227
0x18000f223  test    al, 2
0x18000f225  jnz     short loc_18000F20E
0x18000f227  retn
```
