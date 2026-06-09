# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x14001d358`
- end: `0x14001d394`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `60`
- prototype: `void __fastcall(unsigned __int8, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001d4b4`

## callees

- `0x14001d358`

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
0x14001d358  sub     edx, 3
0x14001d35b  jz      short loc_14001D368
0x14001d35d  cmp     edx, 1
0x14001d360  jnz     short locret_14001D393
0x14001d362  lea     r8d, [rdx+1Fh]
0x14001d366  jmp     short loc_14001D36E
0x14001d368  mov     r8d, 10h
0x14001d36e  mov     r9, cs:Feature_ShadowAdmin__private_descriptor
0x14001d375  mov     eax, [r9]
0x14001d378  jmp     short loc_14001D38F
0x14001d37a  mov     edx, eax
0x14001d37c  xor     edx, ecx
0x14001d37e  test    dl, 1
0x14001d381  jnz     short locret_14001D393
0x14001d383  mov     edx, r8d
0x14001d386  or      edx, eax
0x14001d388  lock cmpxchg [r9], edx
0x14001d38d  jz      short locret_14001D393
0x14001d38f  test    al, 2
0x14001d391  jnz     short loc_14001D37A
0x14001d393  retn
```
