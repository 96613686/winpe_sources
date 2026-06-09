# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x1400063d4`
- end: `0x1400063f3`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001187c`

## callees

- `0x1400063d4`

## pseudocode

```c
void *__fastcall wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(__int64 a1, int a2)
{
  int v2; // edx
  unsigned int v3; // ecx
  void *result; // rax

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
  result = wil_details_featureDescriptors_a;
  _InterlockedOr((volatile signed __int32 *)wil_details_featureDescriptors_a, v3);
  return result;
}

```

## disassembly

```asm
0x1400063d4  sub     edx, 3
0x1400063d7  jz      short loc_1400063E3
0x1400063d9  cmp     edx, 1
0x1400063dc  jnz     short locret_1400063F2
0x1400063de  lea     ecx, [rdx+1Fh]
0x1400063e1  jmp     short loc_1400063E8
0x1400063e3  mov     ecx, 10h
0x1400063e8  mov     rax, cs:wil_details_featureDescriptors_a
0x1400063ef  lock or [rax], ecx
0x1400063f2  retn
```
