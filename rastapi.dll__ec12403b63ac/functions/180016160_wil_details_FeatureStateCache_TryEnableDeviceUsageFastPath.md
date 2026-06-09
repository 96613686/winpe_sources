# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x180016160`
- end: `0x18001619c`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800163f0`

## callees

- `0x180016160`

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
  v4 = *Feature_VPN_BugFixes_25C_RasmansDependency__private_descriptor;
  do
  {
    if ( (v4 & 2) == 0 )
      break;
    if ( ((a1 ^ (unsigned __int8)v4) & 1) != 0 )
      break;
    v5 = v4;
    v4 = _InterlockedCompareExchange(Feature_VPN_BugFixes_25C_RasmansDependency__private_descriptor, v4 | v3, v4);
  }
  while ( v5 != v4 );
}

```

## disassembly

```asm
0x180016160  sub     edx, 3
0x180016163  jz      short loc_180016170
0x180016165  cmp     edx, 1
0x180016168  jnz     short locret_18001619B
0x18001616a  lea     r8d, [rdx+1Fh]
0x18001616e  jmp     short loc_180016176
0x180016170  mov     r8d, 10h
0x180016176  mov     r9, cs:Feature_VPN_BugFixes_25C_RasmansDependency__private_descriptor
0x18001617d  mov     eax, [r9]
0x180016180  jmp     short loc_180016197
0x180016182  mov     edx, eax
0x180016184  xor     edx, ecx
0x180016186  test    dl, 1
0x180016189  jnz     short locret_18001619B
0x18001618b  mov     edx, r8d
0x18001618e  or      edx, eax
0x180016190  lock cmpxchg [r9], edx
0x180016195  jz      short locret_18001619B
0x180016197  test    al, 2
0x180016199  jnz     short loc_180016182
0x18001619b  retn
```
