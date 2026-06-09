# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x1800206e8`
- end: `0x180020724`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `60`
- prototype: `void __fastcall(unsigned __int8, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002072c`

## callees

- `0x1800206e8`

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
0x1800206e8  sub     edx, 3
0x1800206eb  jz      short loc_1800206F8
0x1800206ed  cmp     edx, 1
0x1800206f0  jnz     short locret_180020723
0x1800206f2  lea     r8d, [rdx+1Fh]
0x1800206f6  jmp     short loc_1800206FE
0x1800206f8  mov     r8d, 10h
0x1800206fe  mov     r9, cs:Feature_ShadowAdmin__private_descriptor
0x180020705  mov     eax, [r9]
0x180020708  jmp     short loc_18002071F
0x18002070a  mov     edx, eax
0x18002070c  xor     edx, ecx
0x18002070e  test    dl, 1
0x180020711  jnz     short locret_180020723
0x180020713  mov     edx, r8d
0x180020716  or      edx, eax
0x180020718  lock cmpxchg [r9], edx
0x18002071d  jz      short locret_180020723
0x18002071f  test    al, 2
0x180020721  jnz     short loc_18002070A
0x180020723  retn
```
