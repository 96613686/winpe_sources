# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x14000b0d8`
- end: `0x14000b0f7`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000a340`

## callees

- `0x14000b0d8`

## pseudocode

```c
int *__fastcall wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(__int64 a1, int a2)
{
  int v2; // edx
  unsigned int v3; // ecx
  int *result; // rax

  v2 = a2 - 3;
  if ( v2 )
  {
    if ( v2 != 1 )
      return result;
    v3 = 32;
  }
  else
  {
    v3 = 16;
  }
  result = wil_details_featureDescriptors_a[0];
  _InterlockedOr(wil_details_featureDescriptors_a[0], v3);
  return result;
}

```

## disassembly

```asm
0x14000b0d8  sub     edx, 3
0x14000b0db  jz      short loc_14000B0E7
0x14000b0dd  cmp     edx, 1
0x14000b0e0  jnz     short locret_14000B0F6
0x14000b0e2  lea     ecx, [rdx+1Fh]
0x14000b0e5  jmp     short loc_14000B0EC
0x14000b0e7  mov     ecx, 10h
0x14000b0ec  mov     rax, cs:wil_details_featureDescriptors_a
0x14000b0f3  lock or [rax], ecx
0x14000b0f6  retn
```
