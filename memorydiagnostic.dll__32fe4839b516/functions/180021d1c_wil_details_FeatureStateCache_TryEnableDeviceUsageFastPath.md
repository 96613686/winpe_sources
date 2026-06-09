# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x180021d1c`
- end: `0x180021d68`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `76`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180021d70`

## callees

- `0x180021d1c`

## pseudocode

```c
void __fastcall wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(char a1, int a2)
{
  int v2; // edx
  int v3; // r8d
  signed __int32 v4; // eax
  signed __int32 v5; // r9d
  int v6; // edx
  int v7; // ecx

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
  v4 = *Feature_ShadowAdmin__private_descriptor;
  v5 = *Feature_ShadowAdmin__private_descriptor;
  v6 = *Feature_ShadowAdmin__private_descriptor;
  if ( (*Feature_ShadowAdmin__private_descriptor & 2) != 0 )
  {
    v7 = a1 & 1;
    do
    {
      if ( (v6 & 1) != v7 )
        break;
      v4 = _InterlockedCompareExchange(Feature_ShadowAdmin__private_descriptor, v4 | v3, v5);
      if ( v5 == v4 )
        break;
      v5 = v4;
      LOBYTE(v6) = v4;
    }
    while ( (v4 & 2) != 0 );
  }
}

```

## disassembly

```asm
0x180021d1c  mov     r10, cs:Feature_ShadowAdmin__private_descriptor
0x180021d23  sub     edx, 3
0x180021d26  jz      short loc_180021D33
0x180021d28  cmp     edx, 1
0x180021d2b  jnz     short locret_180021D67
0x180021d2d  lea     r8d, [rdx+1Fh]
0x180021d31  jmp     short loc_180021D39
0x180021d33  mov     r8d, 10h
0x180021d39  mov     eax, [r10]
0x180021d3c  mov     r9d, eax
0x180021d3f  mov     edx, eax
0x180021d41  test    al, 2
0x180021d43  jz      short locret_180021D67
0x180021d45  and     ecx, 1
0x180021d48  and     edx, 1
0x180021d4b  cmp     edx, ecx
0x180021d4d  jnz     short locret_180021D67
0x180021d4f  mov     edx, r8d
0x180021d52  or      edx, eax
0x180021d54  mov     eax, r9d
0x180021d57  lock cmpxchg [r10], edx
0x180021d5c  jz      short locret_180021D67
0x180021d5e  mov     r9d, eax
0x180021d61  mov     edx, eax
0x180021d63  test    al, 2
0x180021d65  jnz     short loc_180021D48
0x180021d67  retn
```
