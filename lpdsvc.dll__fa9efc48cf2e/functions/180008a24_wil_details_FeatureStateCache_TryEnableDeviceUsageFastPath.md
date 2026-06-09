# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x180008a24`
- end: `0x180008a60`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `60`
- prototype: `void __fastcall(unsigned __int8, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008cb4`

## callees

- `0x180008a24`

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
  v4 = *Feature_LpdDeprecationAndRemoval__private_descriptor[0];
  do
  {
    if ( (v4 & 2) == 0 )
      break;
    if ( ((a1 ^ (unsigned __int8)v4) & 1) != 0 )
      break;
    v5 = v4;
    v4 = _InterlockedCompareExchange(Feature_LpdDeprecationAndRemoval__private_descriptor[0], v4 | v3, v4);
  }
  while ( v5 != v4 );
}

```

## disassembly

```asm
0x180008a24  sub     edx, 3
0x180008a27  jz      short loc_180008A34
0x180008a29  cmp     edx, 1
0x180008a2c  jnz     short locret_180008A5F
0x180008a2e  lea     r8d, [rdx+1Fh]
0x180008a32  jmp     short loc_180008A3A
0x180008a34  mov     r8d, 10h
0x180008a3a  mov     r9, cs:Feature_LpdDeprecationAndRemoval__private_descriptor
0x180008a41  mov     eax, [r9]
0x180008a44  jmp     short loc_180008A5B
0x180008a46  mov     edx, eax
0x180008a48  xor     edx, ecx
0x180008a4a  test    dl, 1
0x180008a4d  jnz     short locret_180008A5F
0x180008a4f  mov     edx, r8d
0x180008a52  or      edx, eax
0x180008a54  lock cmpxchg [r9], edx
0x180008a59  jz      short locret_180008A5F
0x180008a5b  test    al, 2
0x180008a5d  jnz     short loc_180008A46
0x180008a5f  retn
```
